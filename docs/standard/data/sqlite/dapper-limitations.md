---
title: Dapper-Einschränkungen
ms.date: 12/13/2019
description: In diesem Artikel werden einige Einschränkungen bei der Verwendung von Dapper beschrieben.
ms.openlocfilehash: 396507f25f591a9ab5c3bb07c0af6fd8d175e4ea
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901199"
---
# <a name="dapper-limitations"></a><span data-ttu-id="01545-103">Dapper-Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="01545-103">Dapper limitations</span></span>

<span data-ttu-id="01545-104">Es gibt ein paar Einschränkungen, die Sie beachten sollten, wenn Sie Microsoft.Data.Sqlite mit [Dapper](https://stackexchange.github.io/Dapper/)verwenden.</span><span class="sxs-lookup"><span data-stu-id="01545-104">There are a few limitations you should be aware of when using Microsoft.Data.Sqlite with [Dapper](https://stackexchange.github.io/Dapper/).</span></span>

## <a name="parameters"></a><span data-ttu-id="01545-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="01545-105">Parameters</span></span>

<span data-ttu-id="01545-106">Bei SQLite-Parameternamen wird die Groß-/Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="01545-106">SQLite parameter names are case-sensitive.</span></span> <span data-ttu-id="01545-107">Stellen Sie sicher, dass bei den in SQL verwendeten Parameternamen die Groß-/Kleinschreibung mit der der Eigenschaften des anonymen Objekts übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="01545-107">Ensure that the parameter names used in SQL match the case of the anonymous object's properties.</span></span> <span data-ttu-id="01545-108">Durch Issue [18861](https://github.com/dotnet/efcore/issues/18861) konnte dieses Verhalten optimiert werden.</span><span class="sxs-lookup"><span data-stu-id="01545-108">Issue [#18861](https://github.com/dotnet/efcore/issues/18861) would improve this experience.</span></span>

<span data-ttu-id="01545-109">Dapper erwartet auch, dass Parameter das Präfix `@` verwenden.</span><span class="sxs-lookup"><span data-stu-id="01545-109">Dapper also expects parameters to use the `@` prefix.</span></span> <span data-ttu-id="01545-110">Andere Präfixe funktionieren nicht.</span><span class="sxs-lookup"><span data-stu-id="01545-110">Other prefixes won't work.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DapperSample/Program.cs?name=snippet_Parameter)]

## <a name="data-types"></a><span data-ttu-id="01545-111">Datentypen</span><span class="sxs-lookup"><span data-stu-id="01545-111">Data types</span></span>

<span data-ttu-id="01545-112">Dapper liest Werte mithilfe des SqliteDataReader-Indexers.</span><span class="sxs-lookup"><span data-stu-id="01545-112">Dapper reads values using the SqliteDataReader indexer.</span></span> <span data-ttu-id="01545-113">Der Rückgabetyp dieses Indexers ist Objekt. Das bedeutet, es werden nur Werte vom Typ long, double, string oder byte[] zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="01545-113">The return type of this indexer is object, which means it will only ever return long, double, string, or byte[] values.</span></span> <span data-ttu-id="01545-114">Weitere Informationen finden Sie unter [Datentypen](types.md).</span><span class="sxs-lookup"><span data-stu-id="01545-114">For more information, see [Data types](types.md).</span></span> <span data-ttu-id="01545-115">Dapper führt die meisten der Konvertierungen zwischen diesen und anderen primitiven Typen durch.</span><span class="sxs-lookup"><span data-stu-id="01545-115">Dapper handles most conversions between these and other primitive types.</span></span> <span data-ttu-id="01545-116">Leider werden `DateTimeOffset`, `Guid` und `TimeSpan` nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="01545-116">Unfortunately, it doesn't handle `DateTimeOffset`, `Guid`, or `TimeSpan`.</span></span> <span data-ttu-id="01545-117">Erstellen Sie Typhandler, wenn Sie diese Typen in Ihren Ergebnissen verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="01545-117">Create type handlers if you want to use these types in your results.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DapperSample/Program.cs?name=snippet_TypeHandlers)]

<span data-ttu-id="01545-118">Vergessen Sie nicht, die Typhandler vor der Abfrage hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="01545-118">Don't forget to add the type handlers before querying.</span></span>

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/DapperSample/Program.cs?name=snippet_AddTypeHandlers)]

## <a name="see-also"></a><span data-ttu-id="01545-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="01545-119">See also</span></span>

* [<span data-ttu-id="01545-120">Datentypen</span><span class="sxs-lookup"><span data-stu-id="01545-120">Data types</span></span>](types.md)
* [<span data-ttu-id="01545-121">Async-Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="01545-121">Async limitations</span></span>](async.md)
