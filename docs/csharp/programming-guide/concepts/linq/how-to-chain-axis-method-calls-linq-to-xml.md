---
title: 'Vorgehensweise: Verketten von Achsenmethodenaufrufen (LINQ to XML) (C#) | Microsoft-Dokumentation'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 067e6da2-ee32-486d-803c-e611b328e39a
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
ms.translationtype: Human Translation
ms.sourcegitcommit: 400dfda51d978f35c3995f90840643aaff1b9c13
ms.openlocfilehash: bcd325d72ac14f2b33860fbc9e2662c33ca2703d
ms.contentlocale: de-de
ms.lasthandoff: 05/22/2017


---
# <a name="how-to-chain-axis-method-calls-linq-to-xml-c"></a>Vorgehensweise: Verketten von Achsenmethodenaufrufen (LINQ to XML) (C#)
Eine gebräuchliche Vorgehensweise im Code besteht darin, erst eine Achsenmethode und dann eine der Erweiterungsmethodenachsen aufzurufen.  
  
 Es gibt zwei Achsenmethoden mit dem Namen `Elements`, die eine Auflistung von Elementen zurückgeben: die <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=fullName>-Methode und die <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=fullName>-Methode. Sie können diese beiden Achsen kombinieren und dann nach allen Elementen eines angegebenen Namens auf einer bestimmten Ebene in der Struktur suchen.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel werden <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=fullName> und <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=fullName> verwendet, um "nach allen `Name`-Elementen in allen `Address`-Elementen in allen `PurchaseOrder`-Elementen" zu suchen.  
  
 In diesem Beispiel wird das folgende XML-Dokument verwendet: [Beispiel-XML-Datei: Mehrere Bestellungen (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md).  
  
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
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```  
<Name>Ellen Adams</Name>  
<Name>Tai Yee</Name>  
<Name>Cristian Osorio</Name>  
<Name>Cristian Osorio</Name>  
<Name>Jessica Arnold</Name>  
<Name>Jessica Arnold</Name>  
```  
  
 Das funktioniert, weil eine der Implementierungen der `Elements`-Achse als Erweiterungsmethode einer <xref:System.Collections.Generic.IEnumerable%601> von <xref:System.Xml.Linq.XContainer> verwendet wird. <xref:System.Xml.Linq.XElement> wird von <xref:System.Xml.Linq.XContainer> abgeleitet. Also können Sie die <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=fullName>-Methode in den Ergebnissen eines Aufrufs der <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=fullName>-Methode aufrufen.  
  
## <a name="example"></a>Beispiel  
 Es kann vorkommen, dass Sie alle Elemente auf einer bestimmten Elementebene abrufen möchten, wobei nicht bekannt ist, ob dazwischenkommende Vorgänger vorhanden sind. So können Sie z. B., wie im folgenden Dokument gezeigt, alle `ConfigParameter`-Elemente abrufen, die untergeordnete Elemente des `Customer`-Elements sind, nicht aber den `ConfigParameter`, der ein untergeordnetes Element des `Root`-Elements ist.  
  
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
  
 Dazu können Sie die <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=fullName>-Achse wie folgt verwenden:  
  
```csharp  
XElement root = XElement.Load("Irregular.xml");  
IEnumerable<XElement> configParameters =   
    root.Elements("Customer").Elements("Config").  
    Elements("ConfigParameter");  
foreach (XElement cp in configParameters)  
    Console.WriteLine(cp);  
```  
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```  
<ConfigParameter>FirstConfigParameter</ConfigParameter>  
<ConfigParameter>SecondConfigParameter</ConfigParameter>  
```  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird dieselbe Vorgehensweise für XML gezeigt, das sich in einem Namespace befindet. Weitere Informationen finden Sie unter [Working with XML Namespaces (C#) (Arbeiten mit XML-Namespaces (C#))](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md).  
  
 Dieses Beispiel verwendet das folgende XML-Dokument: [Beispiel-XML-Datei: mehrfache Bestellung in einem Namespace](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-in-a-namespace.md).  
  
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
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```  
<aw:Name xmlns:aw="http://www.adventure-works.com">Ellen Adams</aw:Name>  
<aw:Name xmlns:aw="http://www.adventure-works.com">Tai Yee</aw:Name>  
<aw:Name xmlns:aw="http://www.adventure-works.com">Cristian Osorio</aw:Name>  
<aw:Name xmlns:aw="http://www.adventure-works.com">Cristian Osorio</aw:Name>  
<aw:Name xmlns:aw="http://www.adventure-works.com">Jessica Arnold</aw:Name>  
<aw:Name xmlns:aw="http://www.adventure-works.com">Jessica Arnold</aw:Name>  
```  
  
## <a name="see-also"></a>Siehe auch  
 [LINQ to XML Axes (C#) (LINQ to XML-Achsen (C#))](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-axes.md)
