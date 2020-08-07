---
title: 'Vorgehensweise: Filtern nach Elementnamen (LINQ to XML) (C#)'
description: Erfahren Sie, wie Sie beim Aufrufen einer Methode, die ein IEnumerable von XElement zurückgibt, nach dem Elementnamen filtern.
ms.date: 07/20/2015
ms.assetid: 1849fb03-f075-421f-863c-e8fb32773cdf
ms.openlocfilehash: be660a69b8d860ad907661ce17002379b8842121
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/28/2020
ms.locfileid: "87301748"
---
# <a name="how-to-filter-on-element-names-linq-to-xml-c"></a><span data-ttu-id="30ea5-103">Vorgehensweise: Filtern nach Elementnamen (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="30ea5-103">How to filter on element names (LINQ to XML) (C#)</span></span>
<span data-ttu-id="30ea5-104">Wenn Sie eine Methode aufrufen, die eine <xref:System.Collections.Generic.IEnumerable%601> von <xref:System.Xml.Linq.XElement> zurückgibt, können Sie eine Filterung nach Elementnamen vornehmen.</span><span class="sxs-lookup"><span data-stu-id="30ea5-104">When you call one of the methods that return <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XElement>, you can filter on the element name.</span></span>  
  
## <a name="example"></a><span data-ttu-id="30ea5-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="30ea5-105">Example</span></span>  
 <span data-ttu-id="30ea5-106">In diesem Beispiel wird eine Auflistung mit Nachfolgerelementen abgerufen, die gefiltert wird, damit sie nur die Nachfolgerelemente mit dem angegebenen Namen enthält.</span><span class="sxs-lookup"><span data-stu-id="30ea5-106">This example retrieves a collection of descendants that is filtered to contain only descendants with the specified name.</span></span>  
  
 <span data-ttu-id="30ea5-107">In diesem Beispiel wird das folgende XML-Dokument verwendet: [Beispiel-XML-Datei: Typische Bestellung (LINQ to XML)](./sample-xml-file-typical-purchase-order-linq-to-xml-1.md).</span><span class="sxs-lookup"><span data-stu-id="30ea5-107">This example uses the following XML document: [Sample XML File: Typical Purchase Order (LINQ to XML)](./sample-xml-file-typical-purchase-order-linq-to-xml-1.md).</span></span>  
  
```csharp  
XElement po = XElement.Load("PurchaseOrder.xml");  
IEnumerable<XElement> items =  
    from el in po.Descendants("ProductName")  
    select el;  
foreach(XElement prdName in items)  
    Console.WriteLine(prdName.Name + ":" + (string) prdName);  
```  
  
 <span data-ttu-id="30ea5-108">Dieser Code erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="30ea5-108">This code produces the following output:</span></span>  
  
```output  
ProductName:Lawnmower  
ProductName:Baby Monitor  
```  
  
 <span data-ttu-id="30ea5-109">Die anderen Methoden, die eine <xref:System.Collections.Generic.IEnumerable%601> von <xref:System.Xml.Linq.XElement>-Auflistungen zurückgeben, folgen dem gleichen Muster.</span><span class="sxs-lookup"><span data-stu-id="30ea5-109">The other methods that return <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XElement> collections follow the same pattern.</span></span> <span data-ttu-id="30ea5-110">Ihre Signaturen entsprechen denen von <xref:System.Xml.Linq.XContainer.Elements%2A> und <xref:System.Xml.Linq.XContainer.Descendants%2A>.</span><span class="sxs-lookup"><span data-stu-id="30ea5-110">Their signatures are similar to <xref:System.Xml.Linq.XContainer.Elements%2A> and <xref:System.Xml.Linq.XContainer.Descendants%2A>.</span></span> <span data-ttu-id="30ea5-111">Im Folgenden finden Sie eine vollständige Liste der Methoden, die gleiche Methodensignaturen besitzen:</span><span class="sxs-lookup"><span data-stu-id="30ea5-111">The following is the complete list of methods that have similar method signatures:</span></span>  
  
- <xref:System.Xml.Linq.XNode.Ancestors%2A>  
  
- <xref:System.Xml.Linq.XContainer.Descendants%2A>  
  
- <xref:System.Xml.Linq.XContainer.Elements%2A>  
  
- <xref:System.Xml.Linq.XNode.ElementsAfterSelf%2A>  
  
- <xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A>  
  
- <xref:System.Xml.Linq.XElement.AncestorsAndSelf%2A>  
  
- <xref:System.Xml.Linq.XElement.DescendantsAndSelf%2A>  
  
## <a name="example"></a><span data-ttu-id="30ea5-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="30ea5-112">Example</span></span>  
 <span data-ttu-id="30ea5-113">Im folgenden Beispiel wird dieselbe Abfrage für XML in einem Namespace gezeigt.</span><span class="sxs-lookup"><span data-stu-id="30ea5-113">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="30ea5-114">Weitere Informationen finden Sie unter [Namespaces: Übersicht (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="30ea5-114">For more information, see [Namespaces Overview (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="30ea5-115">In diesem Beispiel wird das folgende XML-Dokument verwendet: [Beispiel-XML-Datei: Typische Bestellung in einem Namespace](./sample-xml-file-typical-purchase-order-in-a-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="30ea5-115">This example uses the following XML document: [Sample XML File: Typical Purchase Order in a Namespace](./sample-xml-file-typical-purchase-order-in-a-namespace.md).</span></span>  
  
```csharp  
XNamespace aw = "http://www.adventure-works.com";  
XElement po = XElement.Load("PurchaseOrderInNamespace.xml");  
IEnumerable<XElement> items =  
    from el in po.Descendants(aw + "ProductName")  
    select el;  
foreach (XElement prdName in items)  
    Console.WriteLine(prdName.Name + ":" + (string)prdName);  
```  
  
 <span data-ttu-id="30ea5-116">Dieser Code erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="30ea5-116">This code produces the following output:</span></span>  
  
```output  
{http://www.adventure-works.com}ProductName:Lawnmower  
{http://www.adventure-works.com}ProductName:Baby Monitor  
```  
  
## <a name="see-also"></a><span data-ttu-id="30ea5-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="30ea5-117">See also</span></span>

- [<span data-ttu-id="30ea5-118">LINQ to XML Axes (C#) (LINQ to XML-Achsen (C#))</span><span class="sxs-lookup"><span data-stu-id="30ea5-118">LINQ to XML Axes (C#)</span></span>](./linq-to-xml-axes-overview.md)
