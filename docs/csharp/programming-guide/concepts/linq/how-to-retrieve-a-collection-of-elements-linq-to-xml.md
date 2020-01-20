---
title: 'Vorgehensweise: Abrufen einer Elementauflistung (LINQ to XML) (C#)'
ms.date: 07/20/2015
ms.assetid: b849668c-7976-4974-b8e1-1cd587d34258
ms.openlocfilehash: 89799b17115fb56a93bda5fbc144b21b334a6974
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75345019"
---
# <a name="how-to-retrieve-a-collection-of-elements-linq-to-xml-c"></a>Vorgehensweise: Abrufen einer Elementauflistung (LINQ to XML) (C#)
In diesem Thema wird die <xref:System.Xml.Linq.XContainer.Elements%2A>-Methode erläutert. Diese Methode ruft eine Auflistung der untergeordneten Elemente eines Elements ab.  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel durchläuft die untergeordneten Elemente des `purchaseOrder`-Elements.  
  
 In diesem Beispiel wird das folgende XML-Dokument verwendet: [Beispiel-XML-Datei: Typische Bestellung (LINQ to XML)](./sample-xml-file-typical-purchase-order-linq-to-xml-1.md).  
  
```csharp  
XElement po = XElement.Load("PurchaseOrder.xml");  
IEnumerable<XElement> childElements =  
    from el in po.Elements()  
    select el;  
foreach (XElement el in childElements)  
    Console.WriteLine("Name: " + el.Name);  
```  
  
 Folgende Ergebnisse werden zurückgegeben:  
  
```output  
Name: Address  
Name: Address  
Name: DeliveryNotes  
Name: Items  
```  
  
## <a name="see-also"></a>Siehe auch

- [LINQ to XML Axes (C#) (LINQ to XML-Achsen (C#))](./linq-to-xml-axes-overview.md)
