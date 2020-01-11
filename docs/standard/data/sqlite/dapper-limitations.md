---
title: Dappereinschränkungen
ms.date: 12/13/2019
description: Beschreibt einige der Einschränkungen, die bei der Verwendung von dapperauftreten werden.
ms.openlocfilehash: 396507f25f591a9ab5c3bb07c0af6fd8d175e4ea
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901199"
---
# <a name="dapper-limitations"></a><span data-ttu-id="59ad5-103">Dappereinschränkungen</span><span class="sxs-lookup"><span data-stu-id="59ad5-103">Dapper limitations</span></span>

<span data-ttu-id="59ad5-104">Es gibt einige Einschränkungen, die Sie beachten sollten, wenn Sie Microsoft. Data. sqlite mit [dapperverwenden](https://stackexchange.github.io/Dapper/).</span><span class="sxs-lookup"><span data-stu-id="59ad5-104">There are a few limitations you should be aware of when using Microsoft.Data.Sqlite with [Dapper](https://stackexchange.github.io/Dapper/).</span></span>

## <a name="parameters"></a><span data-ttu-id="59ad5-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="59ad5-105">Parameters</span></span>

<span data-ttu-id="59ad5-106">Bei sqlite-Parameternamen wird Groß-/Kleinschreibung beachtet</span><span class="sxs-lookup"><span data-stu-id="59ad5-106">SQLite parameter names are case-sensitive.</span></span> <span data-ttu-id="59ad5-107">Stellen Sie sicher, dass die in SQL verwendeten Parameternamen der Groß-/Kleinschreibung der Eigenschaften des anonymen Objekts entsprechen.</span><span class="sxs-lookup"><span data-stu-id="59ad5-107">Ensure that the parameter names used in SQL match the case of the anonymous object's properties.</span></span> <span data-ttu-id="59ad5-108">Problem [#18861](https://github.com/dotnet/efcore/issues/18861) würde diese Vorgehensweise verbessern.</span><span class="sxs-lookup"><span data-stu-id="59ad5-108">Issue [#18861](https://github.com/dotnet/efcore/issues/18861) would improve this experience.</span></span>

<span data-ttu-id="59ad5-109">Dappererwartet auch, dass Parameter das `@` Präfix verwenden.</span><span class="sxs-lookup"><span data-stu-id="59ad5-109">Dapper also expects parameters to use the `@` prefix.</span></span> <span data-ttu-id="59ad5-110">Andere Präfixe funktionieren nicht.</span><span class="sxs-lookup"><span data-stu-id="59ad5-110">Other prefixes won't work.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DapperSample/Program.cs?name=snippet_Parameter)]

## <a name="data-types"></a><span data-ttu-id="59ad5-111">Datentypen</span><span class="sxs-lookup"><span data-stu-id="59ad5-111">Data types</span></span>

<span data-ttu-id="59ad5-112">Dapperliest Werte mithilfe des sqlitedatareader-Indexers.</span><span class="sxs-lookup"><span data-stu-id="59ad5-112">Dapper reads values using the SqliteDataReader indexer.</span></span> <span data-ttu-id="59ad5-113">Der Rückgabetyp dieses Indexers ist Object, d. h., es werden nur die Werte Long, Double, String oder Byte [] zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="59ad5-113">The return type of this indexer is object, which means it will only ever return long, double, string, or byte[] values.</span></span> <span data-ttu-id="59ad5-114">Weitere Informationen finden Sie unter [Datentypen](types.md).</span><span class="sxs-lookup"><span data-stu-id="59ad5-114">For more information, see [Data types](types.md).</span></span> <span data-ttu-id="59ad5-115">Dapperverarbeitet die meisten Konvertierungen zwischen diesen und anderen primitiven Typen.</span><span class="sxs-lookup"><span data-stu-id="59ad5-115">Dapper handles most conversions between these and other primitive types.</span></span> <span data-ttu-id="59ad5-116">Leider werden `DateTimeOffset`, `Guid`oder `TimeSpan`nicht behandelt.</span><span class="sxs-lookup"><span data-stu-id="59ad5-116">Unfortunately, it doesn't handle `DateTimeOffset`, `Guid`, or `TimeSpan`.</span></span> <span data-ttu-id="59ad5-117">Erstellen Sie Typhandler, wenn Sie diese Typen in ihren Ergebnissen verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="59ad5-117">Create type handlers if you want to use these types in your results.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DapperSample/Program.cs?name=snippet_TypeHandlers)]

<span data-ttu-id="59ad5-118">Vergessen Sie nicht, die Typhandler vor der Abfrage hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="59ad5-118">Don't forget to add the type handlers before querying.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DapperSample/Program.cs?name=snippet_AddTypeHandlers)]

## <a name="see-also"></a><span data-ttu-id="59ad5-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="59ad5-119">See also</span></span>

* [<span data-ttu-id="59ad5-120">Datentypen</span><span class="sxs-lookup"><span data-stu-id="59ad5-120">Data types</span></span>](types.md)
* [<span data-ttu-id="59ad5-121">Async-Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="59ad5-121">Async limitations</span></span>](async.md)
