---
title: Datenbankfehler
ms.date: 12/13/2019
description: Beschreibt, wie Datenbankfehler und-Zurückhaltung von der Bibliothek behandelt werden.
ms.openlocfilehash: 9a613b6f94a89dc40e627c14f46836be77080035
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450489"
---
# <a name="database-errors"></a>Datenbankfehler

<xref:Microsoft.Data.Sqlite.SqliteException> wird ausgelöst, wenn ein sqlite-Fehler auftritt. Die Meldung wird von SQLite bereitgestellt. Die Eigenschaften `SqliteErrorCode` und `SqliteExtendedErrorCode` enthalten den SQLite- [Ergebniscode](https://www.sqlite.org/rescode.html) des Fehlers.

Fehler können immer auftreten, wenn "Microsoft. Data. sqlite" mit der systemeigenen SQLite-Bibliothek interagiert. In der folgenden Liste werden häufige Szenarien angezeigt, in denen Fehler auftreten können:

* Öffnen einer Verbindung.
* Beginnen einer Transaktion.
* Ausführen eines Befehls
* Aufrufen von <xref:Microsoft.Data.Sqlite.SqliteDataReader.NextResult%2A>.

Berücksichtigen Sie sorgfältig, wie Ihre APP diese Fehler behandelt.

## <a name="locking-retries-and-timeouts"></a>Sperren, Wiederholungen und Timeouts

SQLite ist aggressiv, wenn es um das Sperren von Tabellen und Datenbankdateien geht. Wenn Ihre APP gleichzeitigen Datenbankzugriff ermöglicht, treten wahrscheinlich Fehler aufgrund von ausgelasteten und gesperrten Fehlern auf. Sie können viele Fehler verringern, indem Sie einen frei [gegebenen Cache](connection-strings.md#cache) und eine [Write-Ahead-Protokollierung](async.md)verwenden.

Wenn "Microsoft. Data. sqlite" einen stark ausgelasteten oder gesperrten Fehler feststellt, wird der Vorgang automatisch wiederholt, bis der Vorgang erfolgreich ist oder das Befehls Timeout erreicht wird.

Sie können das Timeout des Befehls erhöhen, indem Sie <xref:Microsoft.Data.Sqlite.SqliteCommand.CommandTimeout%2A>festlegen. Der Standardwert für das Timeout beträgt 30 Sekunden. Der Wert `0` bedeutet, dass kein Timeout auftritt.

```csharp
// Retry for 60 seconds while locked
command.CommandTimeout = 60;
```

Microsoft. Data. sqlite muss manchmal ein implizites Befehls Objekt erstellen. Beispielsweise während BeginTransaction. Verwenden Sie <xref:Microsoft.Data.Sqlite.SqliteConnection.DefaultTimeout%2A>, um das Timeout für diese Befehle festzulegen.

```csharp
// Set the default timeout of all commands on this connection
connection.DefaultTimeout = 60;
```

## <a name="see-also"></a>Siehe auch

* [SQLite-Fehler Codes](https://www.sqlite.org/rescode.html)
* [Dateisperren in SQLite](https://www.sqlite.org/lockingv3.html)
* [Modus für freigegebenen Cache](https://www.sqlite.org/sharedcache.html)
* [Write-Ahead-Protokollierung](https://www.sqlite.org/wal.html)
