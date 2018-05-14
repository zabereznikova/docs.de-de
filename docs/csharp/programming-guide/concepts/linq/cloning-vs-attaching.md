---
title: Klonen oder Anfügen (C#)
ms.date: 07/20/2015
ms.assetid: 357c5efa-7b73-4f14-aa67-6bebdba4e7ea
ms.openlocfilehash: 31b5498e18e63ffba357b34780c7eb388e08b37f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="cloning-vs-attaching-c"></a>Klonen oder Anfügen (C#)
Beim Hinzufügen von <xref:System.Xml.Linq.XNode> (inklusive <xref:System.Xml.Linq.XElement>)-Objekten oder <xref:System.Xml.Linq.XAttribute>-Objekten zu einer neuen Struktur werden die Objekte einfach an die XML-Struktur angefügt, falls der neue Inhalt kein übergeordnetes Element besitzt. Wenn der neue Inhalt bereits ein übergeordnetes Element besitzt und Bestandteil einer anderen XML-Struktur ist, wird er geklont. Der neu geklonte Inhalt wird dann an die XML-Struktur angefügt.  
  
## <a name="example"></a>Beispiel  
 Der folgende Code zeigt das Verhalten, wenn Sie einer Struktur ein übergeordnetes Element und ein Element ohne übergeordnetes Element hinzufügen:  
  
```csharp  
// Create a tree with a child element.  
XElement xmlTree1 = new XElement("Root",  
    new XElement("Child1", 1)  
);  
  
// Create an element that is not parented.  
XElement child2 = new XElement("Child2", 2);  
  
// Create a tree and add Child1 and Child2 to it.  
XElement xmlTree2 = new XElement("Root",  
    xmlTree1.Element("Child1"),  
    child2  
);  
  
// Compare Child1 identity.  
Console.WriteLine("Child1 was {0}",  
    xmlTree1.Element("Child1") == xmlTree2.Element("Child1") ?  
    "attached" : "cloned");  
  
// Compare Child2 identity.  
Console.WriteLine("Child2 was {0}",  
    child2 == xmlTree2.Element("Child2") ?  
    "attached" : "cloned");  
```  
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```  
Child1 was cloned  
Child2 was attached  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Creating XML Trees (C#) (Erstellen von XML-Strukturen (C#))](../../../../csharp/programming-guide/concepts/linq/creating-xml-trees.md)
