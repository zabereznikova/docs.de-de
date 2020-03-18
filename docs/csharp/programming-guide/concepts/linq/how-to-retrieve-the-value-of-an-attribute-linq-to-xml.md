---
title: 'Vorgehensweise: Abrufen des Werts eines Attributs (LINQ to XML) (C#)'
ms.date: 07/20/2015
ms.assetid: 817bbe89-5979-4234-bf0c-46f63692ac8c
ms.openlocfilehash: d5b8bb3b5857b82a61367953b8e1cd63bea90beb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "75347435"
---
# <a name="how-to-retrieve-the-value-of-an-attribute-linq-to-xml-c"></a>Vorgehensweise: Abrufen des Werts eines Attributs (LINQ to XML) (C#)
In diesem Thema wird gezeigt, wie Sie den Wert von Attributen abrufen können. Im Wesentlichen gibt es dafür zwei Möglichkeiten: Sie können ein <xref:System.Xml.Linq.XAttribute> in den gewünschten Typ umwandeln. Die Umwandlung des Inhalts des Elements oder Attributs in den angegebenen Typ erfolgt dann durch den expliziten Konvertierungsoperator. Die andere Möglichkeit besteht darin, die <xref:System.Xml.Linq.XAttribute.Value%2A>-Eigenschaft zu verwenden. In der Regel empfiehlt sich aber die Verwendung des Umwandlungsverfahrens. Wenn Sie das Attribut in einen Typ umwandeln, der NULL-Werte zulässt, ist der Code für das Abrufen des Werts eines Attributs, von dem nicht genau bekannt ist, ob es überhaupt vorhanden ist, einfacher zu schreiben. Beispiele für dieses Verfahren finden Sie unter [Vorgehensweise: Abrufen des Werts eines Elements (LINQ to XML) (C#)](./how-to-retrieve-the-value-of-an-element-linq-to-xml.md).  
  
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
  
```output  
<Root Attr="abcde" />  
abcde  
```  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie Sie den Wert eines Attributs für den Fall abrufen können, dass sich das Attribut in einem Namespace befindet. Weitere Informationen finden Sie unter [Namespaces: Übersicht (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).  
  
```csharp  
XNamespace aw = "http://www.adventure-works.com";  
XElement root = new XElement(aw + "Root",  
                    new XAttribute(aw + "Attr", "abcde")  
                );  
string str = (string)root.Attribute(aw + "Attr");  
Console.WriteLine(str);  
```  
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```output  
abcde  
```  
  
## <a name="see-also"></a>Weitere Informationen

- [LINQ to XML Axes (C#) (LINQ to XML-Achsen (C#))](./linq-to-xml-axes-overview.md)
