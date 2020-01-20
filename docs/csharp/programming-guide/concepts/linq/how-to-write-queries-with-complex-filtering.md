---
title: 'Vorgehensweise: Schreiben von Abfragen mit komplexer Filterung (C#)'
ms.date: 07/20/2015
ms.assetid: 4065d901-cf89-4e47-8bf9-abb65acfb003
ms.openlocfilehash: a4918631fed21967b402c5c56cfb8a211d44c139
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75337363"
---
# <a name="how-to-write-queries-with-complex-filtering-c"></a><span data-ttu-id="d0b80-102">Vorgehensweise: Schreiben von Abfragen mit komplexer Filterung (C#)</span><span class="sxs-lookup"><span data-stu-id="d0b80-102">How to write queries with complex filtering (C#)</span></span>
<span data-ttu-id="d0b80-103">Es kann vorkommen, dass Sie LINQ to XML-Abfragen mit komplexen Filtern schreiben möchten.</span><span class="sxs-lookup"><span data-stu-id="d0b80-103">Sometimes you want to write LINQ to XML queries with complex filters.</span></span> <span data-ttu-id="d0b80-104">Vielleicht möchten Sie z. B. auf diese Weise nach allen Elementen suchen, die ein untergeordnetes Element mit einem bestimmten Namen und einem bestimmten Wert besitzen.</span><span class="sxs-lookup"><span data-stu-id="d0b80-104">For example, you might have to find all elements that have a child element with a particular name and value.</span></span> <span data-ttu-id="d0b80-105">In diesem Thema finden Sie ein Beispiel für das Schreiben von Fragen mit komplexer Filterung.</span><span class="sxs-lookup"><span data-stu-id="d0b80-105">This topic gives an example of writing a query with complex filtering.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d0b80-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d0b80-106">Example</span></span>  
 <span data-ttu-id="d0b80-107">Dieses Beispiel zeigt, wie Sie nach allen `PurchaseOrder`-Elementen suchen können, die ein untergeordnetes `Address`-Element mit einem `Type`-Attribut "Shipping" und einem untergeordneten `State`-Element "NY" besitzen.</span><span class="sxs-lookup"><span data-stu-id="d0b80-107">This example shows how to find all `PurchaseOrder` elements that have a child `Address` element that has a `Type` attribute equal to "Shipping" and a child `State` element equal to "NY".</span></span> <span data-ttu-id="d0b80-108">Das Beispiel verwendet eine geschachtelte Abfrage in der `Where`-Klausel, und der `Any`-Operator gibt `true` zurück, sofern die Auflistung überhaupt Elemente enthält.</span><span class="sxs-lookup"><span data-stu-id="d0b80-108">It uses a nested query in the `Where` clause, and the `Any` operator returns `true` if the collection has any elements in it.</span></span> <span data-ttu-id="d0b80-109">Weitere Informationen zu methodenbasierter Abfragesyntax finden Sie unter [Abfragesyntax und Methodensyntax in LINQ](./query-syntax-and-method-syntax-in-linq.md).</span><span class="sxs-lookup"><span data-stu-id="d0b80-109">For information about using method-based query syntax, see [Query Syntax and Method Syntax in LINQ](./query-syntax-and-method-syntax-in-linq.md).</span></span>  
  
 <span data-ttu-id="d0b80-110">In diesem Beispiel wird das folgende XML-Dokument verwendet: [Beispiel-XML-Datei: Mehrere Bestellungen (LINQ to XML)](./sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="d0b80-110">This example uses the following XML document: [Sample XML File: Multiple Purchase Orders (LINQ to XML)](./sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="d0b80-111">Weitere Informationen zum `Any`-Operator finden Sie unter [Quantifier Operations (C#) (Quantifizierervorgänge (C#))](./quantifier-operations.md).</span><span class="sxs-lookup"><span data-stu-id="d0b80-111">For more information about the `Any` operator, see [Quantifier Operations (C#)](./quantifier-operations.md).</span></span>  
  
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
  
 <span data-ttu-id="d0b80-112">Dieser Code erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="d0b80-112">This code produces the following output:</span></span>  
  
```output  
99505  
```  
  
## <a name="example"></a><span data-ttu-id="d0b80-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d0b80-113">Example</span></span>  
 <span data-ttu-id="d0b80-114">Im folgenden Beispiel wird dieselbe Abfrage für XML in einem Namespace gezeigt.</span><span class="sxs-lookup"><span data-stu-id="d0b80-114">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="d0b80-115">Weitere Informationen finden Sie unter [Namespaces: Übersicht (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="d0b80-115">For more information, see [Namespaces Overview (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="d0b80-116">In diesem Beispiel wird das folgende XML-Dokument verwendet: [Beispiel-XML-Datei: Mehrere Bestellungen in einem Namespace](./sample-xml-file-multiple-purchase-orders-in-a-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="d0b80-116">This example uses the following XML document: [Sample XML File: Multiple Purchase Orders in a Namespace](./sample-xml-file-multiple-purchase-orders-in-a-namespace.md).</span></span>  
  
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
  
 <span data-ttu-id="d0b80-117">Dieser Code erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="d0b80-117">This code produces the following output:</span></span>  
  
```output  
99505  
```  
  
## <a name="see-also"></a><span data-ttu-id="d0b80-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d0b80-118">See also</span></span>

- <xref:System.Xml.Linq.XElement.Attribute%2A>
- <xref:System.Xml.Linq.XContainer.Elements%2A>
- [<span data-ttu-id="d0b80-119">Projection Operations (C#) (Projektionsvorgänge (C#))</span><span class="sxs-lookup"><span data-stu-id="d0b80-119">Projection Operations (C#)</span></span>](./projection-operations.md)
- [<span data-ttu-id="d0b80-120">Quantifizierer-Vorgänge (C#)</span><span class="sxs-lookup"><span data-stu-id="d0b80-120">Quantifier Operations (C#)</span></span>](./quantifier-operations.md)
