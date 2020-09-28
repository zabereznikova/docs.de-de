---
title: Transaktionen
ms.date: 09/08/2020
description: Hier erfahren Sie, wie Sie Transaktionen einsetzen.
ms.openlocfilehash: 50c4cd1023eac892cafc3ae4395e9168bd8e9f36
ms.sourcegitcommit: aa6d8a90a4f5d8fe0f6e967980b8c98433f05a44
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/16/2020
ms.locfileid: "90678861"
---
# <a name="transactions"></a>Transaktionen

Mit Transaktionen können Sie mehrere SQL-Anweisungen in einer einzelnen Arbeitseinheit gruppieren, die als unteilbare Einheit an die Datenbank übergeben wird. Schlägt eine Anweisung innerhalb der Transaktion fehl, können die durch die vorherigen Anweisungen vorgenommenen Änderungen durch ein Rollback rückgängig gemacht werden. Der Anfangszustand der Datenbank vor Beginn der Transaktion wird beibehalten. Bei der gleichzeitigen Ausführung von zahlreichen Änderungen können Sie durch den Einsatz einer Transaktion auch die Leistung von SQLite verbessern.

## <a name="concurrency"></a>Parallelität

In SQLite darf jeweils nur eine Transaktion über ausstehende Änderungen in der Datenbank verfügen. Daher kann bei einem Aufruf der Methoden <xref:Microsoft.Data.Sqlite.SqliteConnection.BeginTransaction%2A> und `Execute` in der <xref:Microsoft.Data.Sqlite.SqliteCommand>-Klasse ein Timeout auftreten, wenn die Ausführung einer anderen Transaktion zu lange dauert.

Weitere Informationen zu Sperren, erneuten Versuchen und Timeouts finden Sie unter [Datenbankfehler](database-errors.md).

## <a name="isolation-levels"></a>Isolationsgrade

Standardmäßig sind Transaktionen in SQLite **serialisierbar**. Mit dieser Isolationsstufe wird sichergestellt, dass alle innerhalb einer Transaktion vorgenommenen Änderungen vollständig isoliert sind. Außerhalb der Transaktion ausgeführte Anweisungen sind von den Änderungen der Transaktion nicht betroffen.

Bei Verwendung eines freigegebenen Caches unterstützt SQLite auch die Isolationsstufe **Lesen ohne Commit**. In dieser Stufe sind „Dirty Reads“, nicht wiederholbare Lesevorgänge und Phantomlesevorgänge zulässig:

- Bei einem *Dirty Read* genannten Lesevorgang werden in einer Transaktion ausstehende Änderungen von einer Abfrage außerhalb der Transaktion zurückgegeben. Für die Änderungen innerhalb der Transaktion wird jedoch ein Rollback ausgeführt. Die Ergebnisse enthalten Daten, für die kein echter Commit in der Datenbank ausgeführt wurde.

- Bei einem *nicht wiederholbaren Lesevorgang* wird eine Zeile zweimal von einer Transaktion abgefragt, jedoch mit unterschiedlichen Ergebnissen, da die Zeile zwischen den beiden Abfragen von einer anderen Transaktion geändert wurde.

- Bei einem *Phantomlesevorgang* sind Zeilen vorhanden, die zur Erfüllung der WHERE-Klausel einer Abfrage während einer Transaktion geändert oder hinzugefügt wurden. Ist ein solcher Vorgang zulässig, kann eine Abfrage unterschiedliche Zeilen zurückgeben, wenn sie zweimal in derselben Transaktion ausgeführt wird.

Microsoft.Data.Sqlite behandelt den für „IsolationLevel“ an <xref:Microsoft.Data.Sqlite.SqliteConnection.BeginTransaction%2A> übergegebenen Wert als Mindeststufe. Die tatsächliche Isolationsstufe wird höhergestuft auf „Lesen ohne Commit“ oder „serialisierbar“.

Mit dem folgenden Code wird ein „Dirty Read“ simuliert. Beachten Sie, dass die Verbindungszeichenfolge `Cache=Shared` enthalten muss.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DirtyReadSample/Program.cs?name=snippet_DirtyRead)]

## <a name="deferred-transactions"></a>Verzögerte Transaktionen

Ab der Version 5.0 von Microsoft.Data.Sqlite können Transaktionen verzögert werden. Dadurch wird die Erstellung der tatsächlichen Transaktion in der Datenbank so lange verzögert, bis der erste Befehl ausgeführt wird. Außerdem wird für die Transaktion dadurch allmählich ein Upgrade von einer Lesetransaktion zu einer Schreibtransaktion durchgeführt, wie es von den jeweiligen Befehlen erfordert wird. Dies kann hilfreich sein, wenn während der Transaktion gleichzeitiger Zugriff auf die Datenbank ermöglicht werden soll.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DeferredTransactionSample/Program.cs?name=snippet_DeferredTransaction)]

> [!WARNING]
> Bei Befehlen innerhalb einer verzögerten Transaktion können Fehler auftreten, wenn sie dazu führen, dass für die Transaktion ein Upgrade von einer Lesetransaktion zu einer Schreibtransaktion durchgeführt wird, noch während die Datenbank gesperrt ist. Wenn dies geschieht, muss die Anwendung die gesamte Transaktion neu ausführen.
