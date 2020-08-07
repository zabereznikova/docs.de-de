---
title: 'Vorgehensweise: Schreiben von Abfragen mit komplexer Filterung (C#)'
description: Erfahren Sie, wie Sie LINQ to XML-Abfragen mit komplexen Filtern schreiben. Hier finden Sie Codebeispiele und weitere Ressourcen.
ms.date: 07/20/2015
ms.assetid: 4065d901-cf89-4e47-8bf9-abb65acfb003
ms.openlocfilehash: 5d2c1aafc210b35d4d6b1f1b2d74b11966d90c80
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/28/2020
ms.locfileid: "87303425"
---
# <a name="how-to-write-queries-with-complex-filtering-c"></a><span data-ttu-id="e0fd1-104">Vorgehensweise: Schreiben von Abfragen mit komplexer Filterung (C#)</span><span class="sxs-lookup"><span data-stu-id="e0fd1-104">How to write queries with complex filtering (C#)</span></span>
<span data-ttu-id="e0fd1-105">Es kann vorkommen, dass Sie LINQ to XML-Abfragen mit komplexen Filtern schreiben möchten.</span><span class="sxs-lookup"><span data-stu-id="e0fd1-105">Sometimes you want to write LINQ to XML queries with complex filters.</span></span> <span data-ttu-id="e0fd1-106">Vielleicht möchten Sie z. B. auf diese Weise nach allen Elementen suchen, die ein untergeordnetes Element mit einem bestimmten Namen und einem bestimmten Wert besitzen.</span><span class="sxs-lookup"><span data-stu-id="e0fd1-106">For example, you might have to find all elements that have a child element with a particular name and value.</span></span> <span data-ttu-id="e0fd1-107">In diesem Thema finden Sie ein Beispiel für das Schreiben von Fragen mit komplexer Filterung.</span><span class="sxs-lookup"><span data-stu-id="e0fd1-107">This topic gives an example of writing a query with complex filtering.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e0fd1-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e0fd1-108">Example</span></span>  
 <span data-ttu-id="e0fd1-109">Dieses Beispiel zeigt, wie Sie nach allen `PurchaseOrder`-Elementen suchen können, die ein untergeordnetes `Address`-Element mit einem `Type`-Attribut "Shipping" und einem untergeordneten `State`-Element "NY" besitzen.</span><span class="sxs-lookup"><span data-stu-id="e0fd1-109">This example shows how to find all `PurchaseOrder` elements that have a child `Address` element that has a `Type` attribute equal to "Shipping" and a child `State` element equal to "NY".</span></span> <span data-ttu-id="e0fd1-110">Das Beispiel verwendet eine geschachtelte Abfrage in der `Where`-Klausel, und der `Any`-Operator gibt `true` zurück, sofern die Auflistung überhaupt Elemente enthält.</span><span class="sxs-lookup"><span data-stu-id="e0fd1-110">It uses a nested query in the `Where` clause, and the `Any` operator returns `true` if the collection has any elements in it.</span></span> <span data-ttu-id="e0fd1-111">Weitere Informationen zu methodenbasierter Abfragesyntax finden Sie unter [Abfragesyntax und Methodensyntax in LINQ](./query-syntax-and-method-syntax-in-linq.md).</span><span class="sxs-lookup"><span data-stu-id="e0fd1-111">For information about using method-based query syntax, see [Query Syntax and Method Syntax in LINQ](./query-syntax-and-method-syntax-in-linq.md).</span></span>  
  
 <span data-ttu-id="e0fd1-112">In diesem Beispiel wird das folgende XML-Dokument verwendet: [Beispiel-XML-Datei: Mehrere Bestellungen (LINQ to XML)](./sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="e0fd1-112">This example uses the following XML document: [Sample XML File: Multiple Purchase Orders (LINQ to XML)](./sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="e0fd1-113">Weitere Informationen zum `Any`-Operator finden Sie unter [Quantifier Operations (C#) (Quantifizierervorgänge (C#))](./quantifier-operations.md).</span><span class="sxs-lookup"><span data-stu-id="e0fd1-113">For more information about the `Any` operator, see [Quantifier Operations (C#)](./quantifier-operations.md).</span></span>  
  
```csharp  
XElement root = XElement.Load("PurchaseOrders.xml");  
IEnumerable<XElement> purchaseOrders =  
    from el in root.Elements("PurchaseOrder")  
    where
        (from add in el.Elements("Address")  
        where  
            (string)add.Attribute("Type") == "Shipping" &&  
            (string)add.Element("State") == "NY"  
        select add)  
        .Any()  
    select el;  
foreach (XElement el in purchaseOrders)  
    Console.WriteLine((string)el.Attribute("PurchaseOrderNumber"));  
```  
  
 <span data-ttu-id="e0fd1-114">Dieser Code erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="e0fd1-114">This code produces the following output:</span></span>  
  
```output  
99505  
```  
  
## <a name="example"></a><span data-ttu-id="e0fd1-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e0fd1-115">Example</span></span>  
 <span data-ttu-id="e0fd1-116">Im folgenden Beispiel wird dieselbe Abfrage für XML in einem Namespace gezeigt.</span><span class="sxs-lookup"><span data-stu-id="e0fd1-116">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="e0fd1-117">Weitere Informationen finden Sie unter [Namespaces: Übersicht (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="e0fd1-117">For more information, see [Namespaces Overview (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="e0fd1-118">In diesem Beispiel wird das folgende XML-Dokument verwendet: [Beispiel-XML-Datei: Mehrere Bestellungen in einem Namespace](./sample-xml-file-multiple-purchase-orders-in-a-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="e0fd1-118">This example uses the following XML document: [Sample XML File: Multiple Purchase Orders in a Namespace](./sample-xml-file-multiple-purchase-orders-in-a-namespace.md).</span></span>  
  
```csharp  
XElement root = XElement.Load("PurchaseOrdersInNamespace.xml");  
XNamespace aw = "http://www.adventure-works.com";  
IEnumerable<XElement> purchaseOrders =  
    from el in root.Elements(aw + "PurchaseOrder")  
    where  
        (from add in el.Elements(aw + "Address")  
         where  
             (string)add.Attribute(aw + "Type") == "Shipping" &&  
             (string)add.Element(aw + "State") == "NY"  
         select add)  
        .Any()  
    select el;  
foreach (XElement el in purchaseOrders)  
    Console.WriteLine((string)el.Attribute(aw + "PurchaseOrderNumber"));  
```  
  
 <span data-ttu-id="e0fd1-119">Dieser Code erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="e0fd1-119">This code produces the following output:</span></span>  
  
```output  
99505  
```  
  
## <a name="see-also"></a><span data-ttu-id="e0fd1-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e0fd1-120">See also</span></span>

- <xref:System.Xml.Linq.XElement.Attribute%2A>
- <xref:System.Xml.Linq.XContainer.Elements%2A>
- [<span data-ttu-id="e0fd1-121">Projection Operations (C#) (Projektionsvorgänge (C#))</span><span class="sxs-lookup"><span data-stu-id="e0fd1-121">Projection Operations (C#)</span></span>](./projection-operations.md)
- [<span data-ttu-id="e0fd1-122">Quantifizierer-Vorgänge (C#)</span><span class="sxs-lookup"><span data-stu-id="e0fd1-122">Quantifier Operations (C#)</span></span>](./quantifier-operations.md)
