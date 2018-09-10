---
title: 'Vorgehensweise: Abrufen einer Attributauflistung (LINQ to XML) (C#)'
ms.date: 07/20/2015
ms.assetid: a49ee7a3-b2c2-4d49-9b5c-b7c6c41f4f13
ms.openlocfilehash: e872d0fefa5ea3c25208bf5deab42b59b5b7d5b0
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43526932"
---
# <a name="how-to-retrieve-a-collection-of-attributes-linq-to-xml-c"></a>Vorgehensweise: Abrufen einer Attributauflistung (LINQ to XML) (C#)
Dieses Thema enthält eine Einführung in die <xref:System.Xml.Linq.XElement.Attributes%2A>-Klasse. Diese Methode ruft die Attribute eines Elements ab.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie die Auflistung von Attributen eines Elements durchlaufen werden kann.  
  
```csharp  
XElement val = new XElement("Value",  
    new XAttribute("ID", "1243"),  
    new XAttribute("Type", "int"),  
    new XAttribute("ConvertableTo", "double"),  
    "100");  
IEnumerable<XAttribute> listOfAttributes =  
    from att in val.Attributes()  
    select att;  
foreach (XAttribute a in listOfAttributes)  
    Console.WriteLine(a);  
```  
  
 Dieser Code erzeugt die folgende Ausgabe:  
  
```  
ID="1243"  
Type="int"  
ConvertableTo="double"  
```  
  
## <a name="see-also"></a>Siehe auch

- [LINQ to XML Axes (C#) (LINQ to XML-Achsen (C#))](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-axes.md)
