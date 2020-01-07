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
# <a name="blob-io"></a><span data-ttu-id="26b68-103">BLOB-e/a</span><span class="sxs-lookup"><span data-stu-id="26b68-103">Blob I/O</span></span>

<span data-ttu-id="26b68-104">Sie können die Speicherauslastung beim Lesen und Schreiben von großen Objekten verringern, indem Sie die Daten in die und aus der Datenbank streamen.</span><span class="sxs-lookup"><span data-stu-id="26b68-104">You can reduce memory usage while reading and writing large objects by streaming the data into and out of the database.</span></span> <span data-ttu-id="26b68-105">Dies kann besonders nützlich sein, wenn die Daten verarbeitet oder transformiert werden.</span><span class="sxs-lookup"><span data-stu-id="26b68-105">This can be especially useful when parsing or transforming the data.</span></span>

<span data-ttu-id="26b68-106">Beginnen Sie, indem Sie eine Zeile wie gewohnt einfügen.</span><span class="sxs-lookup"><span data-stu-id="26b68-106">Start by inserting a row as normal.</span></span> <span data-ttu-id="26b68-107">Verwenden Sie die `zeroblob()` SQL-Funktion, um Speicherplatz in der Datenbank zuzuweisen, der das große Objekt enthalten soll.</span><span class="sxs-lookup"><span data-stu-id="26b68-107">Use the `zeroblob()` SQL function to allocate space in the database to hold the large object.</span></span> <span data-ttu-id="26b68-108">Die `last_insert_rowid()`-Funktion bietet eine bequeme Möglichkeit, die ROWID zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="26b68-108">The `last_insert_rowid()` function provides a convenient way to get its rowid.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/StreamingSample/Program.cs?name=snippet_Insert)]

<span data-ttu-id="26b68-109">Öffnen Sie nach dem Einfügen der Zeile einen Stream, um das große Objekt mit <xref:Microsoft.Data.Sqlite.SqliteBlob>zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="26b68-109">After inserting the row, open a stream to write the large object using <xref:Microsoft.Data.Sqlite.SqliteBlob>.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/StreamingSample/Program.cs?name=snippet_Write)]

<span data-ttu-id="26b68-110">Um das große Objekt aus der Datenbank zu streamen, müssen Sie neben der Spalte des großen Objekts die ROWID oder eine der zugehörigen Aliase als hier anzeigen auswählen.</span><span class="sxs-lookup"><span data-stu-id="26b68-110">To stream the large object out of the database, you must select the rowid or one of its aliases as show here in addition to the large object's column.</span></span> <span data-ttu-id="26b68-111">Wenn Sie die ROWID nicht auswählen, wird das gesamte Objekt in den Arbeitsspeicher geladen.</span><span class="sxs-lookup"><span data-stu-id="26b68-111">If you don't select the rowid, the entire object will be loaded into memory.</span></span> <span data-ttu-id="26b68-112">Das von `GetStream()` zurückgegebene Objekt wird `SqliteBlob`, wenn es ordnungsgemäß ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="26b68-112">The object returned by `GetStream()` will be a `SqliteBlob` when done correctly.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/StreamingSample/Program.cs?name=snippet_Read)]
