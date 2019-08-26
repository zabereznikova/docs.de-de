---
title: 'Vorgehensweise: Abrufen einer Elementauflistung (LINQ to XML) (C#)'
ms.date: 07/20/2015
ms.assetid: b849668c-7976-4974-b8e1-1cd587d34258
ms.openlocfilehash: 0ca40b77a78f155292dfbb26471442450bf16b9b
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/19/2019
ms.locfileid: "69592641"
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
  
```  
Name: Address  
Name: Address  
Name: DeliveryNotes  
Name: Items  
```  
  
## <a name="see-also"></a>Siehe auch

- [LINQ to XML Axes (C#) (LINQ to XML-Achsen (C#))](./linq-to-xml-axes-overview.md)
