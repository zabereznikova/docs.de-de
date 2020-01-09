---
title: Transaktionen
ms.date: 12/13/2019
description: Erfahren Sie, wie Sie Transaktionen verwenden.
ms.openlocfilehash: 4b72a1573a560ffd1bfd0f54d46ab3b135280976
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450381"
---
# <a name="transactions"></a>Transaktionen

Mit Transaktionen können Sie mehrere SQL-Anweisungen in einer einzelnen Arbeitseinheit gruppieren, die als eine atomarische Einheit an die Datenbank übergeben wird. Wenn eine Anweisung in der Transaktion fehlschlägt, können die von den vorherigen Anweisungen vorgenommenen Änderungen rückgängig gemacht werden. Der anfängliche Status der Datenbank, in dem die Transaktion gestartet wurde, wird beibehalten. Die Verwendung einer Transaktion kann auch die Leistung von SQLite verbessern, wenn Sie zahlreiche Änderungen an der Datenbank gleichzeitig durchführen.

## <a name="concurrency"></a>Nebenläufigkeit

In SQLite darf jeweils nur eine Transaktion die Änderungen in der Datenbank ausstehend haben. Aus diesem Grund kann bei Aufrufen von <xref:Microsoft.Data.Sqlite.SqliteConnection.BeginTransaction%2A> und den `Execute` Methoden auf <xref:Microsoft.Data.Sqlite.SqliteCommand> ein Timeout auftreten, wenn eine andere Transaktion zu lange dauert.

Weitere Informationen zu sperren, Wiederholungen und Timeouts finden Sie unter [Datenbankfehler](database-errors.md).

## <a name="isolation-levels"></a>Isolationsgrade

Transaktionen sind standardmäßig in SQLite **serialisierbar** . Diese Isolationsstufe gewährleistet, dass alle innerhalb einer Transaktion vorgenommenen Änderungen vollständig isoliert sind. Andere Anweisungen, die außerhalb der Transaktion ausgeführt werden, sind von den Änderungen der Transaktion nicht betroffen.

SQLite unterstützt bei Verwendung eines freigegebenen Caches auch **Lesevorgänge ohne** Commit. Diese Ebene ermöglicht Dirty Reads, nicht wiederholbare Lesevorgänge und Phantom Werte:

- Eine *Dirty Read* tritt auf, wenn Änderungen, die in einer Transaktion ausstehen, von einer Abfrage außerhalb der Transaktion zurückgegeben werden, für die Änderungen in der Transaktion wird jedoch ein Rollback ausgeführt. Die Ergebnisse enthalten Daten, die niemals tatsächlich an die Datenbank übertragen wurden.

- Ein *nicht wiederholbarer Lese* Vorgang tritt auf, wenn eine Transaktion die gleiche Zeile zweimal abfragt. die Ergebnisse unterscheiden sich jedoch, weil Sie von einer anderen Transaktion zwischen den beiden Abfragen geändert wurden.

- *Phantoms* sind Zeilen, die geändert oder hinzugefügt werden, um die WHERE-Klausel einer Abfrage während einer Transaktion zu erfüllen. Wenn dies zulässig ist, kann dieselbe Abfrage andere Zeilen zurückgeben, wenn Sie zweimal in derselben Transaktion ausgeführt wird.

Microsoft. Data. sqlite behandelt den IsolationLevel, der an <xref:Microsoft.Data.Sqlite.SqliteConnection.BeginTransaction%2A> als minimale Ebene übertragen wird. Die tatsächliche Isolationsstufe wird entweder als Lese-oder serialisierbar herauf gestuft.

Der folgende Code simuliert eine Dirty Read. Beachten Sie, dass die Verbindungs Zeichenfolge `Cache=Shared`enthalten muss.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DirtyReadSample/Program.cs?name=snippet_DirtyRead)]
