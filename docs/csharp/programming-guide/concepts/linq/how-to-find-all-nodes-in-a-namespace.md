---
title: 'Vorgehensweise: Suchen aller Knoten in einem Namespace (C#)'
ms.date: 07/20/2015
ms.assetid: 3a38b913-a53e-4d0e-a19d-8782bffd3364
ms.openlocfilehash: 0675795da7c190e6d105ac61027c28f161961099
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/02/2018
ms.locfileid: "48033115"
---
# <a name="how-to-find-all-nodes-in-a-namespace-c"></a><span data-ttu-id="50463-102">Vorgehensweise: Suchen aller Knoten in einem Namespace (C#)</span><span class="sxs-lookup"><span data-stu-id="50463-102">How to: Find All Nodes in a Namespace (C#)</span></span>
<span data-ttu-id="50463-103">Sie können nach den Namespaces der einzelnen Elemente oder Attribute filtern und so alle Knoten im jeweiligen Namespace ermitteln.</span><span class="sxs-lookup"><span data-stu-id="50463-103">You can filter on the namespace of each element or attribute to find all nodes in that particular namespace.</span></span>  
  
## <a name="example"></a><span data-ttu-id="50463-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="50463-104">Example</span></span>  
 <span data-ttu-id="50463-105">Das folgende Beispiel erstellt eine XML-Struktur mit zwei Namespaces.</span><span class="sxs-lookup"><span data-stu-id="50463-105">The following example creates an XML tree with two namespaces.</span></span> <span data-ttu-id="50463-106">Anschließend durchläuft das Beispiel die Struktur und gibt die Namen aller Elemente und Attribute in einem dieser Namespaces aus.</span><span class="sxs-lookup"><span data-stu-id="50463-106">It then iterates through the tree and prints the names of all the elements and attributes in one of those namespaces.</span></span>  
  
```csharp  
string markup = @"<aw:Root xmlns:aw='http://www.adventure-works.com' xmlns:fc='www.fourthcoffee.com'>  
  <fc:Child1>abc</fc:Child1>  
  <fc:Child2>def</fc:Child2>  
  <aw:Child3>ghi</aw:Child3>  
  <fc:Child4>  
    <fc:GrandChild1>jkl</fc:GrandChild1>  
    <aw:GrandChild2>mno</aw:GrandChild2>  
  </fc:Child4>  
</aw:Root>";  
XElement xmlTree = XElement.Parse(markup);  
Console.WriteLine("Nodes in the http://www.adventure-works.com namespace");  
IEnumerable<XElement> awElements =  
    from el in xmlTree.Descendants()  
    where el.Name.Namespace == "http://www.adventure-works.com"  
    select el;  
foreach (XElement el in awElements)  
    Console.WriteLine(el.Name.ToString());  
```  
  
 <span data-ttu-id="50463-107">Dieser Code erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="50463-107">This code produces the following output:</span></span>  
  
```  
Nodes in the http://www.adventure-works.com namespace  
{http://www.adventure-works.com}Child3  
{http://www.adventure-works.com}GrandChild2  
```  
  
## <a name="example"></a><span data-ttu-id="50463-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="50463-108">Example</span></span>  
 <span data-ttu-id="50463-109">Die XML-Datei, auf die die folgende Abfrage zugreift, enthält Aufträge in zwei verschiedenen Namespaces.</span><span class="sxs-lookup"><span data-stu-id="50463-109">The XML file accessed by the following query contains purchase orders in two different namespaces.</span></span> <span data-ttu-id="50463-110">Die Abfrage erstellt eine neue Struktur, die nur die Elemente in einem der Namespaces enthält.</span><span class="sxs-lookup"><span data-stu-id="50463-110">The query creates a new tree with just the elements in one of the namespaces.</span></span>  
  
 <span data-ttu-id="50463-111">Dieses Beispiel verwendet das folgende XML-Dokument: [Beispiel-XML-Datei: Konsolidierte Bestellungen](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-consolidated-purchase-orders.md).</span><span class="sxs-lookup"><span data-stu-id="50463-111">This example uses the following XML document: [Sample XML File: Consolidated Purchase Orders](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-consolidated-purchase-orders.md).</span></span>  
  
```csharp  
XDocument cpo = XDocument.Load("ConsolidatedPurchaseOrders.xml");  
XNamespace aw = "http://www.adventure-works.com";  
XElement newTree = new XElement("Root",  
    from el in cpo.Root.Elements()  
    where el.Name.Namespace == aw  
    select el  
);  
Console.WriteLine(newTree);  
```  
  
 <span data-ttu-id="50463-112">Dieser Code erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="50463-112">This code produces the following output:</span></span>  
  
```xml  
<Root>  
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
</Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="50463-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="50463-113">See Also</span></span>

- [<span data-ttu-id="50463-114">Basic Queries (LINQ to XML) (C#) (Standardabfragen (LINQ to XML) (C#))</span><span class="sxs-lookup"><span data-stu-id="50463-114">Basic Queries (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)
