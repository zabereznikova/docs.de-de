---
title: BLOB-e/a
ms.date: 12/13/2019
description: Erfahren Sie, wie Sie das BLOB-e/a-Feature von SQLite verwenden.
ms.openlocfilehash: 0c133deacdc19684eca3a6724fb398dc01fda558
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450303"
---
# <a name="blob-io"></a>BLOB-e/a

Sie können die Speicherauslastung beim Lesen und Schreiben von großen Objekten verringern, indem Sie die Daten in die und aus der Datenbank streamen. Dies kann besonders nützlich sein, wenn die Daten verarbeitet oder transformiert werden.

Beginnen Sie, indem Sie eine Zeile wie gewohnt einfügen. Verwenden Sie die `zeroblob()` SQL-Funktion, um Speicherplatz in der Datenbank zuzuweisen, der das große Objekt enthalten soll. Die `last_insert_rowid()`-Funktion bietet eine bequeme Möglichkeit, die ROWID zu erhalten.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/StreamingSample/Program.cs?name=snippet_Insert)]

Öffnen Sie nach dem Einfügen der Zeile einen Stream, um das große Objekt mit <xref:Microsoft.Data.Sqlite.SqliteBlob>zu schreiben.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/StreamingSample/Program.cs?name=snippet_Write)]

Um das große Objekt aus der Datenbank zu streamen, müssen Sie neben der Spalte des großen Objekts die ROWID oder eine der zugehörigen Aliase als hier anzeigen auswählen. Wenn Sie die ROWID nicht auswählen, wird das gesamte Objekt in den Arbeitsspeicher geladen. Das von `GetStream()` zurückgegebene Objekt wird `SqliteBlob`, wenn es ordnungsgemäß ausgeführt wird.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/StreamingSample/Program.cs?name=snippet_Read)]
