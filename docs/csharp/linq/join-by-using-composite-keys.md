---
title: "Verknüpfen mithilfe eines zusammengesetzten Schlüssels"
description: "Vorgehensweise: Verknüpfen mithilfe eines zusammengesetzten Schlüssels."
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: da70b54d-3213-45eb-8437-fbe75cbcf935
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: e3e860729ca9267d29ba105ac03ebe22a70b1762
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="join-by-using-composite-keys"></a><span data-ttu-id="12138-104">Verknüpfen mithilfe eines zusammengesetzten Schlüssels</span><span class="sxs-lookup"><span data-stu-id="12138-104">Join by using composite keys</span></span>

<span data-ttu-id="12138-105">In diesem Beispiel erfahren Sie, wie sie Verknüpfungsvorgänge durchführen können, in denen Sie mehr als einen Schlüssel zur Definition einer Übereinstimmung verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="12138-105">This example shows how to perform join operations in which you want to use more than one key to define a match.</span></span> <span data-ttu-id="12138-106">Dies können Sie mithilfe eines zusammengesetzten Schlüssels machen.</span><span class="sxs-lookup"><span data-stu-id="12138-106">This is accomplished by using a composite key.</span></span> <span data-ttu-id="12138-107">Ein zusammengesetzter Schlüssel wird als anonymer oder benannter Typ mit den Werten, die Sie vergleichen möchten, erstellt.</span><span class="sxs-lookup"><span data-stu-id="12138-107">You create a composite key as an anonymous type or named typed with the values that you want to compare.</span></span> <span data-ttu-id="12138-108">Wenn die Abfragevariable methodengrenzenübergreifend übergeben wird, verwenden Sie einen benannten Typ, der <xref:System.Object.Equals%2A> und <xref:System.Object.GetHashCode%2A> für den Schlüssel außer Kraft setzt.</span><span class="sxs-lookup"><span data-stu-id="12138-108">If the query variable will be passed across method boundaries, use a named type that overrides <xref:System.Object.Equals%2A> and <xref:System.Object.GetHashCode%2A> for the key.</span></span> <span data-ttu-id="12138-109">Der Name der Eigenschaften und die Reihenfolge, in der diese auftreten, muss in jedem Schlüssel identisch sein.</span><span class="sxs-lookup"><span data-stu-id="12138-109">The names of the properties, and the order in which they occur, must be identical in each key.</span></span>  
  
## <a name="example"></a><span data-ttu-id="12138-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="12138-110">Example</span></span>  
 <span data-ttu-id="12138-111">In folgendem Beispiel erfahren Sie, wie Sie einen zusammengesetzten Schlüssel verwenden können, um Daten aus drei Tabellen zu verknüpfen:</span><span class="sxs-lookup"><span data-stu-id="12138-111">The following example demonstrates how to use a composite key to join data from three tables:</span></span>  
  
```csharp  
var query = from o in db.Orders  
    from p in db.Products  
    join d in db.OrderDetails   
        on new {o.OrderID, p.ProductID} equals new {d.OrderID,        d.ProductID} into details  
        from d in details  
        select new {o.OrderID, p.ProductID, d.UnitPrice};  
```  
  
 <span data-ttu-id="12138-112">Typrückschluss für zusammengesetzte Schlüssel hängt von den Namen der Eigenschaften in den Schlüsseln und deren Reihenfolge ab.</span><span class="sxs-lookup"><span data-stu-id="12138-112">Type inference on composite keys depends on the names of the properties in the keys, and the order in which they occur.</span></span> <span data-ttu-id="12138-113">Wenn die Eigenschaften der Quellsequenz nicht dieselben Namen haben, müssen Sie ihnen im Schlüssel neue Namen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="12138-113">If the properties in the source sequences do not have the same names, you must assign new names in the keys.</span></span> <span data-ttu-id="12138-114">Wenn in den Tabellen `Orders` und `OrderDetails` beispielsweise unterschiedliche Namen für die Spalten verwendet werden, können Sie zusammengesetzte Schlüssel erstellen, indem Sie identische Namen in den anonymen Typen zuweisen:</span><span class="sxs-lookup"><span data-stu-id="12138-114">For example, if the `Orders` table and `OrderDetails` table each used different names for their columns, you could create composite keys by assigning identical names in the anonymous types:</span></span>  
  
```csharp  
join...on new {Name = o.CustomerName, ID = o.CustID} equals   
    new {Name = d.CustName, ID = d.CustID }  
```  
  
 <span data-ttu-id="12138-115">Zusammengesetzte Schlüssel können auch in einer `group`-Klausel verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="12138-115">Composite keys can be also used in a `group` clause.</span></span>  

## <a name="see-also"></a><span data-ttu-id="12138-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="12138-116">See also</span></span>  
 <span data-ttu-id="12138-117">[LINQ-Abfrageausdrücke](index.md) </span><span class="sxs-lookup"><span data-stu-id="12138-117">[LINQ query expressions](index.md) </span></span>  
 <span data-ttu-id="12138-118">[Join-Klausel](../language-reference/keywords/join-clause.md) </span><span class="sxs-lookup"><span data-stu-id="12138-118">[join clause](../language-reference/keywords/join-clause.md) </span></span>  
 [<span data-ttu-id="12138-119">group-Klausel</span><span class="sxs-lookup"><span data-stu-id="12138-119">group clause</span></span>](../language-reference/keywords/group-clause.md)

