---
title: Blob-E/A
ms.date: 12/13/2019
description: Informationen zum Blob-E/A-Feature von SQLite
ms.openlocfilehash: 0c133deacdc19684eca3a6724fb398dc01fda558
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450303"
---
# <a name="blob-io"></a>Blob-E/A

Sie können die Speicherauslastung beim Lesen und Schreiben von Large Objects verringern, indem Sie die Daten in die und aus der Datenbank streamen. Das kann besonders nützlich sein, wenn die Daten analysiert oder transformiert werden.

Fügen Sie zunächst wie gewohnt eine Zeile ein. Verwenden Sie dann die SQL-Funktion `zeroblob()`, um in der Datenbank den Speicherplatz für das Large Object zuzuweisen. Die `last_insert_rowid()`-Funktion ist eine gute Möglichkeit, den ROWID-Wert abzurufen.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/StreamingSample/Program.cs?name=snippet_Insert)]

Öffnen Sie nach dem Einfügen der Zeile einen Stream, um das Large Object mithilfe von <xref:Microsoft.Data.Sqlite.SqliteBlob> zu schreiben.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/StreamingSample/Program.cs?name=snippet_Write)]

Sie können das Large Object aus der Datenbank streamen, indem Sie wie hier veranschaulicht den ROWID-Wert oder einen der zugehörigen Aliase neben der Spalte des Large Object auswählen. Wenn Sie den ROWID-Wert nicht auswählen, wird das gesamte Objekt in den Arbeitsspeicher geladen. Das von `GetStream()` zurückgegebene Objekt wird ein `SqliteBlob`-Objekt, wenn Sie richtig vorgegangen sind.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/StreamingSample/Program.cs?name=snippet_Read)]
