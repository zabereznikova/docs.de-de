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
# <a name="blob-io"></a><span data-ttu-id="1dda3-103">Blob-E/A</span><span class="sxs-lookup"><span data-stu-id="1dda3-103">Blob I/O</span></span>

<span data-ttu-id="1dda3-104">Sie können die Speicherauslastung beim Lesen und Schreiben von Large Objects verringern, indem Sie die Daten in die und aus der Datenbank streamen.</span><span class="sxs-lookup"><span data-stu-id="1dda3-104">You can reduce memory usage while reading and writing large objects by streaming the data into and out of the database.</span></span> <span data-ttu-id="1dda3-105">Das kann besonders nützlich sein, wenn die Daten analysiert oder transformiert werden.</span><span class="sxs-lookup"><span data-stu-id="1dda3-105">This can be especially useful when parsing or transforming the data.</span></span>

<span data-ttu-id="1dda3-106">Fügen Sie zunächst wie gewohnt eine Zeile ein.</span><span class="sxs-lookup"><span data-stu-id="1dda3-106">Start by inserting a row as normal.</span></span> <span data-ttu-id="1dda3-107">Verwenden Sie dann die SQL-Funktion `zeroblob()`, um in der Datenbank den Speicherplatz für das Large Object zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="1dda3-107">Use the `zeroblob()` SQL function to allocate space in the database to hold the large object.</span></span> <span data-ttu-id="1dda3-108">Die `last_insert_rowid()`-Funktion ist eine gute Möglichkeit, den ROWID-Wert abzurufen.</span><span class="sxs-lookup"><span data-stu-id="1dda3-108">The `last_insert_rowid()` function provides a convenient way to get its rowid.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/StreamingSample/Program.cs?name=snippet_Insert)]

<span data-ttu-id="1dda3-109">Öffnen Sie nach dem Einfügen der Zeile einen Stream, um das Large Object mithilfe von <xref:Microsoft.Data.Sqlite.SqliteBlob> zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="1dda3-109">After inserting the row, open a stream to write the large object using <xref:Microsoft.Data.Sqlite.SqliteBlob>.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/StreamingSample/Program.cs?name=snippet_Write)]

<span data-ttu-id="1dda3-110">Sie können das Large Object aus der Datenbank streamen, indem Sie wie hier veranschaulicht den ROWID-Wert oder einen der zugehörigen Aliase neben der Spalte des Large Object auswählen.</span><span class="sxs-lookup"><span data-stu-id="1dda3-110">To stream the large object out of the database, you must select the rowid or one of its aliases as show here in addition to the large object's column.</span></span> <span data-ttu-id="1dda3-111">Wenn Sie den ROWID-Wert nicht auswählen, wird das gesamte Objekt in den Arbeitsspeicher geladen.</span><span class="sxs-lookup"><span data-stu-id="1dda3-111">If you don't select the rowid, the entire object will be loaded into memory.</span></span> <span data-ttu-id="1dda3-112">Das von `GetStream()` zurückgegebene Objekt wird ein `SqliteBlob`-Objekt, wenn Sie richtig vorgegangen sind.</span><span class="sxs-lookup"><span data-stu-id="1dda3-112">The object returned by `GetStream()` will be a `SqliteBlob` when done correctly.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/StreamingSample/Program.cs?name=snippet_Read)]
