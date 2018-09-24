---
title: 'Vorgehensweise: Suchen des Stammelements (XPath-LINQ to XML) (C#)'
ms.date: 07/20/2015
ms.assetid: 4fd824e0-4d39-429b-b092-f6a5c046ee6c
ms.openlocfilehash: a0197a34f2e9d1b42a71d3c8cb1a4281ba495c4f
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2018
ms.locfileid: "46710987"
---
# <a name="how-to-find-the-root-element-xpath-linq-to-xml-c"></a>Vorgehensweise: Suchen des Stammelements (XPath-LINQ to XML) (C#)
In diesem Thema wird gezeigt, wie Sie mit XPath und mit [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] das Stammelement ermitteln können.  
  
 Der XPath-Ausdruck lautet:  
  
 `/PurchaseOrders`  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel sucht nach dem Stammelement.  
  
 Dieses Beispiel verwendet das folgende XML-Dokument: [Beispiel-XML-Datei: Mehrere Bestellungen (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md).  
  
```csharp  
XDocument po = XDocument.Load("PurchaseOrders.xml");  
  
// LINQ to XML query  
XElement el1 = po.Root;  
  
// XPath expression  
XElement el2 = po.XPathSelectElement("/PurchaseOrders");  
  
if (el1 == el2)  
    Console.WriteLine("Results are identical");  
else  
    Console.WriteLine("Results differ");  
Console.WriteLine(el1.Name);  
```  
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```  
Results are identical  
PurchaseOrders  
```  
  
## <a name="see-also"></a>Siehe auch

- [LINQ to XML für XPath-Benutzer (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
