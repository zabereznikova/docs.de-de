---
title: Verknüpfen mithilfe zusammengesetzter Schlüssel (LINQ in C#)
description: In diesem Artikel erfahren Sie, wie Sie Verknüpfungen mithilfe zusammengesetzter Schlüssel in LINQ erstellen.
ms.date: 12/1/2016
ms.assetid: da70b54d-3213-45eb-8437-fbe75cbcf935
ms.openlocfilehash: ae37d03f996f0b0cc184a86663f16d62e6c29c69
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2018
ms.locfileid: "46711063"
---
# <a name="join-by-using-composite-keys"></a><span data-ttu-id="3b46f-103">Verknüpfen mithilfe eines zusammengesetzten Schlüssels</span><span class="sxs-lookup"><span data-stu-id="3b46f-103">Join by using composite keys</span></span>

<span data-ttu-id="3b46f-104">In diesem Beispiel erfahren Sie, wie sie Verknüpfungsvorgänge durchführen können, in denen Sie mehr als einen Schlüssel zur Definition einer Übereinstimmung verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="3b46f-104">This example shows how to perform join operations in which you want to use more than one key to define a match.</span></span> <span data-ttu-id="3b46f-105">Dies können Sie mithilfe eines zusammengesetzten Schlüssels machen.</span><span class="sxs-lookup"><span data-stu-id="3b46f-105">This is accomplished by using a composite key.</span></span> <span data-ttu-id="3b46f-106">Ein zusammengesetzter Schlüssel wird als anonymer oder benannter Typ mit den Werten, die Sie vergleichen möchten, erstellt.</span><span class="sxs-lookup"><span data-stu-id="3b46f-106">You create a composite key as an anonymous type or named typed with the values that you want to compare.</span></span> <span data-ttu-id="3b46f-107">Wenn die Abfragevariable methodengrenzenübergreifend übergeben wird, verwenden Sie einen benannten Typ, der <xref:System.Object.Equals%2A> und <xref:System.Object.GetHashCode%2A> für den Schlüssel außer Kraft setzt.</span><span class="sxs-lookup"><span data-stu-id="3b46f-107">If the query variable will be passed across method boundaries, use a named type that overrides <xref:System.Object.Equals%2A> and <xref:System.Object.GetHashCode%2A> for the key.</span></span> <span data-ttu-id="3b46f-108">Der Name der Eigenschaften und die Reihenfolge, in der diese auftreten, muss in jedem Schlüssel identisch sein.</span><span class="sxs-lookup"><span data-stu-id="3b46f-108">The names of the properties, and the order in which they occur, must be identical in each key.</span></span>

## <a name="example"></a><span data-ttu-id="3b46f-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3b46f-109">Example</span></span>

<span data-ttu-id="3b46f-110">In folgendem Beispiel erfahren Sie, wie Sie einen zusammengesetzten Schlüssel verwenden können, um Daten aus drei Tabellen zu verknüpfen:</span><span class="sxs-lookup"><span data-stu-id="3b46f-110">The following example demonstrates how to use a composite key to join data from three tables:</span></span>

```csharp
var query = from o in db.Orders
    from p in db.Products
    join d in db.OrderDetails
        on new {o.OrderID, p.ProductID} equals new {d.OrderID, d.ProductID} into details
        from d in details
        select new {o.OrderID, p.ProductID, d.UnitPrice};
```

<span data-ttu-id="3b46f-111">Typrückschluss für zusammengesetzte Schlüssel hängt von den Namen der Eigenschaften in den Schlüsseln und deren Reihenfolge ab.</span><span class="sxs-lookup"><span data-stu-id="3b46f-111">Type inference on composite keys depends on the names of the properties in the keys, and the order in which they occur.</span></span> <span data-ttu-id="3b46f-112">Wenn die Eigenschaften der Quellsequenz nicht dieselben Namen haben, müssen Sie ihnen im Schlüssel neue Namen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="3b46f-112">If the properties in the source sequences don't have the same names, you must assign new names in the keys.</span></span> <span data-ttu-id="3b46f-113">Wenn in den Tabellen `Orders` und `OrderDetails` beispielsweise unterschiedliche Namen für die Spalten verwendet werden, können Sie zusammengesetzte Schlüssel erstellen, indem Sie identische Namen in den anonymen Typen zuweisen:</span><span class="sxs-lookup"><span data-stu-id="3b46f-113">For example, if the `Orders` table and `OrderDetails` table each used different names for their columns, you could create composite keys by assigning identical names in the anonymous types:</span></span>

```csharp
join...on new {Name = o.CustomerName, ID = o.CustID} equals
    new {Name = d.CustName, ID = d.CustID }
```

<span data-ttu-id="3b46f-114">Zusammengesetzte Schlüssel können auch in einer `group`-Klausel verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3b46f-114">Composite keys can be also used in a `group` clause.</span></span>

## <a name="see-also"></a><span data-ttu-id="3b46f-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3b46f-115">See also</span></span>

- [<span data-ttu-id="3b46f-116">Language-Integrated Query (LINQ)</span><span class="sxs-lookup"><span data-stu-id="3b46f-116">Language Integrated Query (LINQ)</span></span>](index.md)  
- [<span data-ttu-id="3b46f-117">join-Klausel</span><span class="sxs-lookup"><span data-stu-id="3b46f-117">join clause</span></span>](../language-reference/keywords/join-clause.md)  
- [<span data-ttu-id="3b46f-118">group-Klausel</span><span class="sxs-lookup"><span data-stu-id="3b46f-118">group clause</span></span>](../language-reference/keywords/group-clause.md)  