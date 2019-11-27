---
title: 'Gewusst wie: Verketten von Aufrufen des Axis-Methode (LINQ to XML)'
ms.date: 07/20/2015
ms.assetid: e4e22942-39bd-460f-b3c0-9f09e53d3aa9
ms.openlocfilehash: de6fbec9fa7948c618252415774ff6a2e9289c74
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346941"
---
# <a name="how-to-chain-axis-method-calls-linq-to-xml-visual-basic"></a><span data-ttu-id="7d916-102">Gewusst wie: Verketten von Achsen Methoden aufrufen (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7d916-102">How to: Chain Axis Method Calls (LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="7d916-103">Eine gebräuchliche Vorgehensweise im Code besteht darin, erst eine Achsenmethode und dann eine der Erweiterungsmethodenachsen aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="7d916-103">A common pattern that you will use in your code is to call an axis method, then call one of the extension method axes.</span></span>  
  
 <span data-ttu-id="7d916-104">Es gibt zwei Achsenmethoden mit dem Namen `Elements`, die eine Auflistung von Elementen zurückgeben: die <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType>-Methode und die <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=nameWithType>-Methode.</span><span class="sxs-lookup"><span data-stu-id="7d916-104">There are two axes with the name of `Elements` that return a collection of elements: the <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType> method and the <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="7d916-105">Sie können diese beiden Achsen kombinieren und dann nach allen Elementen eines angegebenen Namens auf einer bestimmten Ebene in der Struktur suchen.</span><span class="sxs-lookup"><span data-stu-id="7d916-105">You can combine these two axes to find all elements of a specified name at a given depth in the tree.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7d916-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7d916-106">Example</span></span>  
 <span data-ttu-id="7d916-107">In diesem Beispiel werden <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType> und <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=nameWithType> verwendet, um "nach allen `Name`-Elementen in allen `Address`-Elementen in allen `PurchaseOrder`-Elementen" zu suchen.</span><span class="sxs-lookup"><span data-stu-id="7d916-107">This example uses <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType> and <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=nameWithType> to find all `Name` elements in all `Address` elements in all `PurchaseOrder` elements.</span></span>  
  
 <span data-ttu-id="7d916-108">In diesem Beispiel wird das folgende XML-Dokument verwendet: [Beispiel-XML-Datei: Mehrere Bestellungen (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="7d916-108">This example uses the following XML document: [Sample XML File: Multiple Purchase Orders (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span></span>  
  
```vb  
Dim purchaseOrders As XElement = XElement.Load("PurchaseOrders.xml")  
Dim names As IEnumerable(Of XElement) = _  
    From el In purchaseOrders.<PurchaseOrder>.<Address>.<Name> _  
    Select el  
For Each e As XElement In names  
    Console.WriteLine(e)  
Next  
```  
  
 <span data-ttu-id="7d916-109">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="7d916-109">This example produces the following output:</span></span>  
  
```xml  
<Name>Ellen Adams</Name>  
<Name>Tai Yee</Name>  
<Name>Cristian Osorio</Name>  
<Name>Cristian Osorio</Name>  
<Name>Jessica Arnold</Name>  
<Name>Jessica Arnold</Name>  
```  
  
 <span data-ttu-id="7d916-110">Das funktioniert, weil eine der Implementierungen der `Elements`-Achse als Erweiterungsmethode einer <xref:System.Collections.Generic.IEnumerable%601> von <xref:System.Xml.Linq.XContainer> verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="7d916-110">This works because one of the implementations of the `Elements` axis is as an extension method on <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XContainer>.</span></span> <span data-ttu-id="7d916-111"><xref:System.Xml.Linq.XElement> wird von <xref:System.Xml.Linq.XContainer> abgeleitet. Also können Sie die <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=nameWithType>-Methode in den Ergebnissen eines Aufrufs der <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType>-Methode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="7d916-111"><xref:System.Xml.Linq.XElement> derives from <xref:System.Xml.Linq.XContainer>, so you can call the <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=nameWithType> method on the results of a call to the <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7d916-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7d916-112">Example</span></span>  
 <span data-ttu-id="7d916-113">Es kann vorkommen, dass Sie alle Elemente auf einer bestimmten Elementebene abrufen möchten, wobei nicht bekannt ist, ob dazwischenkommende Vorgänger vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="7d916-113">Sometimes you want to retrieve all elements at a particular element depth when there might or might not be intervening ancestors.</span></span> <span data-ttu-id="7d916-114">So können Sie z. B., wie im folgenden Dokument gezeigt, alle `ConfigParameter`-Elemente abrufen, die untergeordnete Elemente des `Customer`-Elements sind, nicht aber den `ConfigParameter`, der ein untergeordnetes Element des `Root`-Elements ist.</span><span class="sxs-lookup"><span data-stu-id="7d916-114">For example, in the following document, you might want to retrieve all the `ConfigParameter` elements that are children of the `Customer` element, but not the `ConfigParameter` that is a child of the `Root` element.</span></span>  
  
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
  
 <span data-ttu-id="7d916-115">Dazu können Sie die <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=nameWithType>-Achse wie folgt verwenden:</span><span class="sxs-lookup"><span data-stu-id="7d916-115">To do this, you can use the <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=nameWithType> axis, as follows:</span></span>  
  
```vb  
Dim root As XElement = XElement.Load("Irregular.xml")  
Dim configParameters As IEnumerable(Of XElement) = _  
    root.<Customer>.<Config>.<ConfigParameter>  
For Each cp As XElement In configParameters  
    Console.WriteLine(cp)  
Next  
```  
  
 <span data-ttu-id="7d916-116">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="7d916-116">This example produces the following output:</span></span>  
  
```xml  
<ConfigParameter>FirstConfigParameter</ConfigParameter>  
<ConfigParameter>SecondConfigParameter</ConfigParameter>  
```  
  
## <a name="example"></a><span data-ttu-id="7d916-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7d916-117">Example</span></span>  
 <span data-ttu-id="7d916-118">Im folgenden Beispiel wird dieselbe Vorgehensweise für XML gezeigt, das sich in einem Namespace befindet.</span><span class="sxs-lookup"><span data-stu-id="7d916-118">The following example shows the same technique for XML that is in a namespace.</span></span> <span data-ttu-id="7d916-119">Weitere Informationen finden Sie unter [Übersicht über Namespaces (LINQ to XML) (Visual Basic)](namespaces-overview-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="7d916-119">For more information, see [Namespaces Overview (LINQ to XML) (Visual Basic)](namespaces-overview-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="7d916-120">Dieses Beispiel verwendet das folgende XML-Dokument: [Beispiel-XML-Datei: mehrfache Bestellung in einem Namespace](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-in-a-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="7d916-120">This example uses the following XML document: [Sample XML File: Multiple Purchase Orders in a Namespace](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-in-a-namespace.md).</span></span>  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim purchaseOrders As XElement = XElement.Load("PurchaseOrdersInNamespace.xml")  
        Dim names As IEnumerable(Of XElement) = _  
            From el In purchaseOrders.<aw:PurchaseOrder>.<aw:Address>.<aw:Name> _  
            Select el  
        For Each e As XElement In names  
            Console.WriteLine(e)  
        Next  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="7d916-121">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="7d916-121">This example produces the following output:</span></span>  
  
```xml  
<aw:Name xmlns:aw="http://www.adventure-works.com">Ellen Adams</aw:Name>  
<aw:Name xmlns:aw="http://www.adventure-works.com">Tai Yee</aw:Name>  
<aw:Name xmlns:aw="http://www.adventure-works.com">Cristian Osorio</aw:Name>  
<aw:Name xmlns:aw="http://www.adventure-works.com">Cristian Osorio</aw:Name>  
<aw:Name xmlns:aw="http://www.adventure-works.com">Jessica Arnold</aw:Name>  
<aw:Name xmlns:aw="http://www.adventure-works.com">Jessica Arnold</aw:Name>  
```  
  
## <a name="see-also"></a><span data-ttu-id="7d916-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7d916-122">See also</span></span>

- [<span data-ttu-id="7d916-123">LINQ to XML-Achsen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7d916-123">LINQ to XML Axes (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md)
