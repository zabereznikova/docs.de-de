---
title: 'Vorgehensweise: Suchen nach Elementen in einem Namespace (XPath-LINQ to XML) (C#)'
ms.date: 07/20/2015
ms.assetid: cae1c4ac-6cd5-46cf-9b1c-bd85bc9b7ea9
ms.openlocfilehash: da9d819be5234a2429b6eab276f89bd0d877d4a7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "74141068"
---
# <a name="how-to-find-elements-in-a-namespace-xpath-linq-to-xml-c"></a>Vorgehensweise: Suchen nach Elementen in einem Namespace (XPath-LINQ to XML) (C#)

XPath-Ausdrücke können nach Knoten in einem bestimmten Namespace suchen. Zum Angeben der Namespaces werden Namespacepräfixe verwendet. Wenn Sie einen XPath-Ausdruck, der Namespacepräfixe enthält, analysieren möchten, müssen Sie den XPath-Methoden ein Objekt übergeben, das <xref:System.Xml.IXmlNamespaceResolver> implementiert. In diesem Beispiel wird <xref:System.Xml.XmlNamespaceManager> verwendet.

Der XPath-Ausdruck lautet:

`./aw:*`

## <a name="example"></a>Beispiel

Das folgende Beispiel liest eine XML-Struktur, die zwei Namespaces enthält. Zum Lesen des XML-Dokuments kommt dabei ein <xref:System.Xml.XmlReader> zum Einsatz. Anschließend werden eine <xref:System.Xml.XmlNameTable> aus dem <xref:System.Xml.XmlReader> und ein <xref:System.Xml.XmlNamespaceManager> aus der <xref:System.Xml.XmlNameTable> abgerufen. Beim Auswählen von Elementen wird der <xref:System.Xml.XmlNamespaceManager> verwendet.

```csharp
XmlReader reader = XmlReader.Create("ConsolidatedPurchaseOrders.xml");
XElement root = XElement.Load(reader);
XmlNameTable nameTable = reader.NameTable;
XmlNamespaceManager namespaceManager = new XmlNamespaceManager(nameTable);
namespaceManager.AddNamespace("aw", "http://www.adventure-works.com");
IEnumerable<XElement> list1 = root.XPathSelectElements("./aw:*", namespaceManager);
IEnumerable<XElement> list2 =
    from el in root.Elements()
    where el.Name.Namespace == "http://www.adventure-works.com"
    select el;
if (list1.Count() == list2.Count() &&
        list1.Intersect(list2).Count() == list1.Count())
    Console.WriteLine("Results are identical");
else
    Console.WriteLine("Results differ");
foreach (XElement el in list2)
    Console.WriteLine(el);
```

Dieses Beispiel erzeugt die folgende Ausgabe:

```output
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
