---
title: Transaktionen
ms.date: 12/13/2019
description: Hier erfahren Sie, wie Sie Transaktionen einsetzen.
ms.openlocfilehash: 4b72a1573a560ffd1bfd0f54d46ab3b135280976
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450381"
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
