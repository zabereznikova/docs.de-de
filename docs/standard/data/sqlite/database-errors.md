---
title: Datenbankfehler
ms.date: 12/13/2019
description: In diesem Artikel wird beschrieben, wie die Bibliothek Datenbankfehler und erneute Versuche behandelt.
ms.openlocfilehash: 9a613b6f94a89dc40e627c14f46836be77080035
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450489"
---
# <a name="database-errors"></a>Datenbankfehler

<xref:Microsoft.Data.Sqlite.SqliteException> wird ausgelöst, wenn ein SQLite-Fehler auftritt. Die Meldung wird von SQLite bereitgestellt. Die Eigenschaften `SqliteErrorCode` und `SqliteExtendedErrorCode` enthalten den SQLite-[Ergebniscode](https://www.sqlite.org/rescode.html) des Fehlers.

Fehler können immer dann auftreten, wenn Microsoft.Data.Sqlite mit der nativen SQLite-Bibliothek interagiert. In der folgenden Liste sind die Szenarios aufgeführt, in denen üblicherweise Fehler auftreten können:

* Öffnen einer Verbindung
* Beginnen einer Transaktion
* Ausführen eines Befehls
* Aufrufen von <xref:Microsoft.Data.Sqlite.SqliteDataReader.NextResult%2A>.

Denken Sie sorgfältig darüber nach, wie Ihre App diese Fehler behandeln soll.

## <a name="locking-retries-and-timeouts"></a>Sperrung, erneute Versuche und Timeouts

SQLite ist aggressiv, was das Sperren von Tabellen und Datenbankdateien betrifft. Wenn Ihre App gleichzeitigen Datenbankzugriff ermöglicht, treten wahrscheinlich Fehler aufgrund von starker Auslastung und Sperrung auf. Sie können viele Fehler minimieren, indem Sie einen [gemeinsamen Cache](connection-strings.md#cache) und [Write-Ahead-Protokollierung](async.md) verwenden.

Wenn Microsoft.Data.Sqlite einen Fehler aufgrund von starker Auslastung oder Sperrung feststellt, wird automatisch erneut versucht, den entsprechenden Befehl auszuführen, bis er erfolgreich ausgeführt wurde oder ein Timeout für den Befehl auftritt.

Sie können den Zeitraum für das Timeout von Befehlen verlängern, indem Sie <xref:Microsoft.Data.Sqlite.SqliteCommand.CommandTimeout%2A> festlegen. Der Standardzeitraum bis zum Timeout beträgt 30 Sekunden. Der Wert `0` bedeutet, dass kein Timeout auftritt.

```csharp
// Retry for 60 seconds while locked
command.CommandTimeout = 60;
```

Manchmal muss Microsoft.Data.Sqlite ein implizites Befehlsobjekt erstellen. Zum Beispiel bei BeginTransaction. Verwenden Sie <xref:Microsoft.Data.Sqlite.SqliteConnection.DefaultTimeout%2A>, um den Zeitraum bis zum Timeout für diese Befehle festzulegen.

```csharp
// Set the default timeout of all commands on this connection
connection.DefaultTimeout = 60;
```

## <a name="see-also"></a>Siehe auch

* [Ergebnis- und Fehlercodes](https://www.sqlite.org/rescode.html)
* [Dateisperrung und Parallelität in SQLite 3](https://www.sqlite.org/lockingv3.html)
* [Modus mit gemeinsamem Cache in SQLite](https://www.sqlite.org/sharedcache.html)
* [Write-Ahead-Protokollierung](https://www.sqlite.org/wal.html)
