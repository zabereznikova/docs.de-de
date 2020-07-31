---
title: 'Vorgehensweise: Verketten von Achsenmethodenaufrufen (LINQ to XML) (C#)'
description: Die Beispiele für LINQ to XML in C# zeigen die Aufrufe von zwei Achsen, um alle Elemente eines bestimmten Namens auf einer bestimmten Ebene im Baum zu finden.
ms.date: 07/20/2015
ms.assetid: 067e6da2-ee32-486d-803c-e611b328e39a
ms.openlocfilehash: f26efd2ca918fd36916eb4f01462af70066219a0
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2020
ms.locfileid: "87105383"
---
# <a name="how-to-chain-axis-method-calls-linq-to-xml-c"></a><span data-ttu-id="7d859-103">Vorgehensweise: Verketten von Achsenmethodenaufrufen (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="7d859-103">How to chain axis method calls (LINQ to XML) (C#)</span></span>
<span data-ttu-id="7d859-104">Eine gebräuchliche Vorgehensweise im Code besteht darin, erst eine Achsenmethode und dann eine der Erweiterungsmethodenachsen aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="7d859-104">A common pattern that you will use in your code is to call an axis method, then call one of the extension method axes.</span></span>  
  
 <span data-ttu-id="7d859-105">Es gibt zwei Achsenmethoden mit dem Namen `Elements`, die eine Auflistung von Elementen zurückgeben: die <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType>-Methode und die <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=nameWithType>-Methode.</span><span class="sxs-lookup"><span data-stu-id="7d859-105">There are two axes with the name of `Elements` that return a collection of elements: the <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType> method and the <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="7d859-106">Sie können diese beiden Achsen kombinieren und dann nach allen Elementen eines angegebenen Namens auf einer bestimmten Ebene in der Struktur suchen.</span><span class="sxs-lookup"><span data-stu-id="7d859-106">You can combine these two axes to find all elements of a specified name at a given depth in the tree.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7d859-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7d859-107">Example</span></span>  
 <span data-ttu-id="7d859-108">In diesem Beispiel werden <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType> und <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=nameWithType> verwendet, um "nach allen `Name`-Elementen in allen `Address`-Elementen in allen `PurchaseOrder`-Elementen" zu suchen.</span><span class="sxs-lookup"><span data-stu-id="7d859-108">This example uses <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType> and <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=nameWithType> to find all `Name` elements in all `Address` elements in all `PurchaseOrder` elements.</span></span>  
  
 <span data-ttu-id="7d859-109">In diesem Beispiel wird das folgende XML-Dokument verwendet: [Beispiel-XML-Datei: Mehrere Bestellungen (LINQ to XML)](./sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="7d859-109">This example uses the following XML document: [Sample XML File: Multiple Purchase Orders (LINQ to XML)](./sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span></span>  
  
```csharp  
XElement purchaseOrders = XElement.Load("PurchaseOrders.xml");  
IEnumerable<XElement> names =  
    from el in purchaseOrders  
        .Elements("PurchaseOrder")  
        .Elements("Address")  
        .Elements("Name")  
    select el;  
foreach (XElement e in names)  
    Console.WriteLine(e);  
```  
  
 <span data-ttu-id="7d859-110">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="7d859-110">This example produces the following output:</span></span>  
  
```xml  
<Name>Ellen Adams</Name>  
<Name>Tai Yee</Name>  
<Name>Cristian Osorio</Name>  
<Name>Cristian Osorio</Name>  
<Name>Jessica Arnold</Name>  
<Name>Jessica Arnold</Name>  
```  
  
 <span data-ttu-id="7d859-111">Das funktioniert, weil eine der Implementierungen der `Elements`-Achse als Erweiterungsmethode einer <xref:System.Collections.Generic.IEnumerable%601> von <xref:System.Xml.Linq.XContainer> verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="7d859-111">This works because one of the implementations of the `Elements` axis is as an extension method on <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XContainer>.</span></span> <span data-ttu-id="7d859-112"><xref:System.Xml.Linq.XElement> wird von <xref:System.Xml.Linq.XContainer> abgeleitet. Also können Sie die <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=nameWithType>-Methode in den Ergebnissen eines Aufrufs der <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType>-Methode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="7d859-112"><xref:System.Xml.Linq.XElement> derives from <xref:System.Xml.Linq.XContainer>, so you can call the <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=nameWithType> method on the results of a call to the <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7d859-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7d859-113">Example</span></span>  
 <span data-ttu-id="7d859-114">Es kann vorkommen, dass Sie alle Elemente auf einer bestimmten Elementebene abrufen möchten, wobei nicht bekannt ist, ob dazwischenkommende Vorgänger vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="7d859-114">Sometimes you want to retrieve all elements at a particular element depth when there might or might not be intervening ancestors.</span></span> <span data-ttu-id="7d859-115">So können Sie z. B., wie im folgenden Dokument gezeigt, alle `ConfigParameter`-Elemente abrufen, die untergeordnete Elemente des `Customer`-Elements sind, nicht aber den `ConfigParameter`, der ein untergeordnetes Element des `Root`-Elements ist.</span><span class="sxs-lookup"><span data-stu-id="7d859-115">For example, in the following document, you might want to retrieve all the `ConfigParameter` elements that are children of the `Customer` element, but not the `ConfigParameter` that is a child of the `Root` element.</span></span>  
  
```xml  
<Root>  
  <ConfigParameter>RootConfigParameter</ConfigParameter>  
  <Customer>  
    <Name>Frank</Name>  
    <Config>  
      <ConfigParameter>FirstConfigParameter</ConfigParameter>  
    </Config>  
  </Customer>  
  <Customer>  
    <Name>Bob</Name>  
    <!--This customer doesn't have a Config element-->  
  </Customer>  
  <Customer>  
    <Name>Bill</Name>  
    <Config>  
      <ConfigParameter>SecondConfigParameter</ConfigParameter>  
    </Config>  
  </Customer>  
</Root>  
```  
  
 <span data-ttu-id="7d859-116">Dazu können Sie die <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=nameWithType>-Achse wie folgt verwenden:</span><span class="sxs-lookup"><span data-stu-id="7d859-116">To do this, you can use the <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=nameWithType> axis, as follows:</span></span>  
  
```csharp  
XElement root = XElement.Load("Irregular.xml");  
IEnumerable<XElement> configParameters =
    root.Elements("Customer").Elements("Config").  
    Elements("ConfigParameter");  
foreach (XElement cp in configParameters)  
    Console.WriteLine(cp);  
```  
  
 <span data-ttu-id="7d859-117">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="7d859-117">This example produces the following output:</span></span>  
  
```xml  
<ConfigParameter>FirstConfigParameter</ConfigParameter>  
<ConfigParameter>SecondConfigParameter</ConfigParameter>  
```  
  
## <a name="example"></a><span data-ttu-id="7d859-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7d859-118">Example</span></span>  
 <span data-ttu-id="7d859-119">Im folgenden Beispiel wird dieselbe Vorgehensweise für XML gezeigt, das sich in einem Namespace befindet.</span><span class="sxs-lookup"><span data-stu-id="7d859-119">The following example shows the same technique for XML that is in a namespace.</span></span> <span data-ttu-id="7d859-120">Weitere Informationen finden Sie unter [Namespaces: Übersicht (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="7d859-120">For more information, see [Namespaces Overview (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="7d859-121">In diesem Beispiel wird das folgende XML-Dokument verwendet: [Beispiel-XML-Datei: Mehrere Bestellungen in einem Namespace](./sample-xml-file-multiple-purchase-orders-in-a-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="7d859-121">This example uses the following XML document: [Sample XML File: Multiple Purchase Orders in a Namespace](./sample-xml-file-multiple-purchase-orders-in-a-namespace.md).</span></span>  
  
```csharp  
XNamespace aw = "http://www.adventure-works.com";  
XElement purchaseOrders = XElement.Load("PurchaseOrdersInNamespace.xml");  
IEnumerable<XElement> names =  
    from el in purchaseOrders  
        .Elements(aw + "PurchaseOrder")  
        .Elements(aw + "Address")  
        .Elements(aw + "Name")  
    select el;  
foreach (XElement e in names)  
    Console.WriteLine(e);  
```  
  
 <span data-ttu-id="7d859-122">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="7d859-122">This example produces the following output:</span></span>  
  
```xml  
<aw:Name xmlns:aw="http://www.adventure-works.com">Ellen Adams</aw:Name>  
<aw:Name xmlns:aw="http://www.adventure-works.com">Tai Yee</aw:Name>  
<aw:Name xmlns:aw="http://www.adventure-works.com">Cristian Osorio</aw:Name>  
<aw:Name xmlns:aw="http://www.adventure-works.com">Cristian Osorio</aw:Name>  
<aw:Name xmlns:aw="http://www.adventure-works.com">Jessica Arnold</aw:Name>  
<aw:Name xmlns:aw="http://www.adventure-works.com">Jessica Arnold</aw:Name>  
```  
  
## <a name="see-also"></a><span data-ttu-id="7d859-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7d859-123">See also</span></span>

- [<span data-ttu-id="7d859-124">LINQ to XML Axes (C#) (LINQ to XML-Achsen (C#))</span><span class="sxs-lookup"><span data-stu-id="7d859-124">LINQ to XML Axes (C#)</span></span>](linq-to-xml-axes-overview.md)
