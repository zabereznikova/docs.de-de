---
title: 'Vorgehensweise: Suchen nach Elementen in einem Namespace (XPath-LINQ to XML) (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: c7cb3b77-3424-4b54-9efa-4dc715948e41
ms.openlocfilehash: 3e8220c1dc34a56306d78db5d90ab5697ba5f632
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54714784"
---
# <a name="how-to-find-elements-in-a-namespace-xpath-linq-to-xml-visual-basic"></a><span data-ttu-id="4e94c-102">Vorgehensweise: Suchen nach Elementen in einem Namespace (XPath-LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4e94c-102">How to: Find Elements in a Namespace (XPath-LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="4e94c-103">XPath-Ausdrücke können nach Knoten in einem bestimmten Namespace suchen.</span><span class="sxs-lookup"><span data-stu-id="4e94c-103">XPath expressions can find nodes in a particular namespace.</span></span> <span data-ttu-id="4e94c-104">Zum Angeben der Namespaces werden Namespacepräfixe verwendet.</span><span class="sxs-lookup"><span data-stu-id="4e94c-104">XPath expressions use namespace prefixes for specifying namespaces.</span></span> <span data-ttu-id="4e94c-105">Wenn Sie einen XPath-Ausdruck, der Namespacepräfixe enthält, analysieren möchten, müssen Sie den XPath-Methoden ein Objekt übergeben, das <xref:System.Xml.IXmlNamespaceResolver> implementiert.</span><span class="sxs-lookup"><span data-stu-id="4e94c-105">To parse an XPath expression that contains namespace prefixes, you must pass an object to the XPath methods that implements <xref:System.Xml.IXmlNamespaceResolver>.</span></span> <span data-ttu-id="4e94c-106">In diesem Beispiel wird <xref:System.Xml.XmlNamespaceManager> verwendet.</span><span class="sxs-lookup"><span data-stu-id="4e94c-106">This example uses <xref:System.Xml.XmlNamespaceManager>.</span></span>  
  
 <span data-ttu-id="4e94c-107">Der XPath-Ausdruck lautet:</span><span class="sxs-lookup"><span data-stu-id="4e94c-107">The XPath expression is:</span></span>  
  
 `./aw:*`  
  
## <a name="example"></a><span data-ttu-id="4e94c-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4e94c-108">Example</span></span>  
 <span data-ttu-id="4e94c-109">Das folgende Beispiel liest eine XML-Struktur, die zwei Namespaces enthält.</span><span class="sxs-lookup"><span data-stu-id="4e94c-109">The following example reads an XML tree that contains two namespaces.</span></span> <span data-ttu-id="4e94c-110">Zum Lesen des XML-Dokuments kommt dabei ein <xref:System.Xml.XmlReader> zum Einsatz.</span><span class="sxs-lookup"><span data-stu-id="4e94c-110">It uses an <xref:System.Xml.XmlReader> to read the XML document.</span></span> <span data-ttu-id="4e94c-111">Anschließend werden eine <xref:System.Xml.XmlNameTable> aus dem <xref:System.Xml.XmlReader> und ein <xref:System.Xml.XmlNamespaceManager> aus der <xref:System.Xml.XmlNameTable> abgerufen.</span><span class="sxs-lookup"><span data-stu-id="4e94c-111">It then gets an <xref:System.Xml.XmlNameTable> from the <xref:System.Xml.XmlReader>, and an <xref:System.Xml.XmlNamespaceManager> from the <xref:System.Xml.XmlNameTable>.</span></span> <span data-ttu-id="4e94c-112">Beim Auswählen von Elementen wird der <xref:System.Xml.XmlNamespaceManager> verwendet.</span><span class="sxs-lookup"><span data-stu-id="4e94c-112">It uses the <xref:System.Xml.XmlNamespaceManager> when selecting elements.</span></span>  
  
```vb  
Dim reader As XmlReader = _  
        XmlReader.Create("ConsolidatedPurchaseOrders.xml")  
Dim root As XElement = XElement.Load(reader)  
Dim nameTable As XmlNameTable = reader.NameTable  
Dim namespaceManager As XmlNamespaceManager = New XmlNamespaceManager(nameTable)  
namespaceManager.AddNamespace("aw", "http://www.adventure-works.com")  
  
Dim list1 As IEnumerable(Of XElement) = _  
        root.XPathSelectElements("./aw:*", namespaceManager)  
Dim list2 As IEnumerable(Of XElement) = _  
    From el In root.Elements() _  
    Where el.Name.Namespace = "http://www.adventure-works.com" _  
    Select el  
  
If list1.Count() = list2.Count() And _  
        list1.Intersect(list2).Count() = list1.Count() Then  
    Console.WriteLine("Results are identical")  
Else  
    Console.WriteLine("Results differ")  
End If  
For Each el As XElement In list2  
    Console.WriteLine(el)  
Next  
```  
  
 <span data-ttu-id="4e94c-113">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="4e94c-113">This example produces the following output:</span></span>  
  
```  
Results are identical  
<aw:PurchaseOrder PONumber="11223" Date="2000-01-15" xmlns:aw="http://www.adventure-works.com">  
    <aw:ShippingAddress>  
      <aw:Name>Chris Preston</aw:Name>  
      <aw:Street>123 Main St.</aw:Street>  
      <aw:City>Seattle</aw:City>  
      <aw:State>WA</aw:State>  
      <aw:Zip>98113</aw:Zip>  
      <aw:Country>USA</aw:Country>  
    </aw:ShippingAddress>  
    <aw:BillingAddress>  
      <aw:Name>Chris Preston</aw:Name>  
      <aw:Street>123 Main St.</aw:Street>  
      <aw:City>Seattle</aw:City>  
      <aw:State>WA</aw:State>  
      <aw:Zip>98113</aw:Zip>  
      <aw:Country>USA</aw:Country>  
    </aw:BillingAddress>  
    <aw:DeliveryInstructions>Ship only complete order.</aw:DeliveryInstructions>  
    <aw:Item PartNum="LIT-01">  
      <aw:ProductID>Litware Networking Card</aw:ProductID>  
      <aw:Qty>1</aw:Qty>  
      <aw:Price>20.99</aw:Price>  
    </aw:Item>  
    <aw:Item PartNum="LIT-25">  
      <aw:ProductID>Litware 17in LCD Monitor</aw:ProductID>  
      <aw:Qty>1</aw:Qty>  
      <aw:Price>199.99</aw:Price>  
    </aw:Item>  
  </aw:PurchaseOrder>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4e94c-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4e94c-114">See also</span></span>
- [<span data-ttu-id="4e94c-115">LINQ to XML für XPath-Benutzer (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4e94c-115">LINQ to XML for XPath Users (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
