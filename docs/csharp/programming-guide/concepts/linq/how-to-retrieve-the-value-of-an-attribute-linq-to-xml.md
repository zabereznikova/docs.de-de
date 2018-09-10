---
title: 'Vorgehensweise: Abrufen des Werts eines Attributs (LINQ to XML) (C#)'
ms.date: 07/20/2015
ms.assetid: 817bbe89-5979-4234-bf0c-46f63692ac8c
ms.openlocfilehash: a78cda390cc7b3d489cfda212cf8fb8111e4dde2
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43501503"
---
# <a name="how-to-retrieve-the-value-of-an-attribute-linq-to-xml-c"></a>Vorgehensweise: Abrufen des Werts eines Attributs (LINQ to XML) (C#)
In diesem Thema wird gezeigt, wie Sie den Wert von Attributen abrufen können. Im Wesentlichen gibt es dafür zwei Möglichkeiten: Sie können ein <xref:System.Xml.Linq.XAttribute> in den gewünschten Typ umwandeln. Die Umwandlung des Inhalts des Elements oder Attributs in den angegebenen Typ erfolgt dann durch den expliziten Konvertierungsoperator. Die andere Möglichkeit besteht darin, die <xref:System.Xml.Linq.XAttribute.Value%2A>-Eigenschaft zu verwenden. In der Regel empfiehlt sich aber die Verwendung des Umwandlungsverfahrens. Wenn Sie das Attribut in einen Typ umwandeln, der NULL-Werte zulässt, ist der Code für das Abrufen des Werts eines Attributs, von dem nicht genau bekannt ist, ob es überhaupt vorhanden ist, einfacher zu schreiben. Beispiele für dieses Verfahren finden Sie unter [How to: Retrieve the Value of an Element (LINQ to XML) (C#) (Vorgehensweise: Abrufen des Werts eines Elements (LINQ to XML) (C#))](../../../../csharp/programming-guide/concepts/linq/how-to-retrieve-the-value-of-an-element-linq-to-xml.md).  
  
## <a name="example"></a>Beispiel  
 Zum Abrufen des Werts eines Attributs wandeln Sie einfach nur das <xref:System.Xml.Linq.XAttribute>-Objekt in den gewünschten Typ um.  
  
```csharp  
XElement root = new XElement("Root",  
                    new XAttribute("Attr", "abcde")  
                );  
Console.WriteLine(root);  
string str = (string)root.Attribute("Attr");  
Console.WriteLine(str);  
```  
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```  
<Root Attr="abcde" />  
abcde  
```  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie Sie den Wert eines Attributs für den Fall abrufen können, dass sich das Attribut in einem Namespace befindet. Weitere Informationen finden Sie unter [Working with XML Namespaces (C#) (Arbeiten mit XML-Namespaces (C#))](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md).  
  
```csharp  
XNamespace aw = "http://www.adventure-works.com";  
XElement root = new XElement(aw + "Root",  
                    new XAttribute(aw + "Attr", "abcde")  
                );  
string str = (string)root.Attribute(aw + "Attr");  
Console.WriteLine(str);  
```  
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```  
abcde  
```  
  
## <a name="see-also"></a>Siehe auch

- [LINQ to XML Axes (C#) (LINQ to XML-Achsen (C#))](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-axes.md)
