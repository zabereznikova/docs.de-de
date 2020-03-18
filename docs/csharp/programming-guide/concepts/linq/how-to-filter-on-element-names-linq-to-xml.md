---
title: 'Vorgehensweise: Filtern nach Elementnamen (LINQ to XML) (C#)'
ms.date: 07/20/2015
ms.assetid: 1849fb03-f075-421f-863c-e8fb32773cdf
ms.openlocfilehash: 74efb19ef5ec77ca29145d27a8e5aa977530b68b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "74141261"
---
# <a name="how-to-filter-on-element-names-linq-to-xml-c"></a>Vorgehensweise: Filtern nach Elementnamen (LINQ to XML) (C#)
Wenn Sie eine Methode aufrufen, die eine <xref:System.Collections.Generic.IEnumerable%601> von <xref:System.Xml.Linq.XElement> zurückgibt, können Sie eine Filterung nach Elementnamen vornehmen.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird eine Auflistung mit Nachfolgerelementen abgerufen, die gefiltert wird, damit sie nur die Nachfolgerelemente mit dem angegebenen Namen enthält.  
  
 Dieses Beispiel verwendet das folgende XML-Dokument: [Beispiel-XML-Datei: Typische Bestellung (LINQ to XML)](./sample-xml-file-typical-purchase-order-linq-to-xml-1.md).  
  
```csharp  
XElement po = XElement.Load("PurchaseOrder.xml");  
IEnumerable<XElement> items =  
    from el in po.Descendants("ProductName")  
    select el;  
foreach(XElement prdName in items)  
    Console.WriteLine(prdName.Name + ":" + (string) prdName);  
```  
  
 Dieser Code erzeugt die folgende Ausgabe:  
  
```output  
ProductName:Lawnmower  
ProductName:Baby Monitor  
```  
  
 Die anderen Methoden, die eine <xref:System.Collections.Generic.IEnumerable%601> von <xref:System.Xml.Linq.XElement>-Auflistungen zurückgeben, folgen dem gleichen Muster. Ihre Signaturen entsprechen denen von <xref:System.Xml.Linq.XContainer.Elements%2A> und <xref:System.Xml.Linq.XContainer.Descendants%2A>. Im Folgenden finden Sie eine vollständige Liste der Methoden, die gleiche Methodensignaturen besitzen:  
  
- <xref:System.Xml.Linq.XNode.Ancestors%2A>  
  
- <xref:System.Xml.Linq.XContainer.Descendants%2A>  
  
- <xref:System.Xml.Linq.XContainer.Elements%2A>  
  
- <xref:System.Xml.Linq.XNode.ElementsAfterSelf%2A>  
  
- <xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A>  
  
- <xref:System.Xml.Linq.XElement.AncestorsAndSelf%2A>  
  
- <xref:System.Xml.Linq.XElement.DescendantsAndSelf%2A>  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird dieselbe Abfrage für XML in einem Namespace gezeigt. Weitere Informationen finden Sie unter [Namespaces: Übersicht (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).  
  
 In diesem Beispiel wird das folgende XML-Dokument verwendet: [Beispiel-XML-Datei: Typische Bestellung in einem Namespace](./sample-xml-file-typical-purchase-order-in-a-namespace.md).  
  
```csharp  
XNamespace aw = "http://www.adventure-works.com";  
XElement po = XElement.Load("PurchaseOrderInNamespace.xml");  
IEnumerable<XElement> items =  
    from el in po.Descendants(aw + "ProductName")  
    select el;  
foreach (XElement prdName in items)  
    Console.WriteLine(prdName.Name + ":" + (string)prdName);  
```  
  
 Dieser Code erzeugt die folgende Ausgabe:  
  
```output  
{http://www.adventure-works.com}ProductName:Lawnmower  
{http://www.adventure-works.com}ProductName:Baby Monitor  
```  
  
## <a name="see-also"></a>Weitere Informationen

- [LINQ to XML Axes (C#) (LINQ to XML-Achsen (C#))](./linq-to-xml-axes-overview.md)
