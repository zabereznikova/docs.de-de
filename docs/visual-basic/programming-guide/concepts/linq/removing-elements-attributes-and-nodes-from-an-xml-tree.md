---
title: Entfernen von Elementen, Attributen und Knoten aus einem XML-Baum
ms.date: 07/20/2015
ms.assetid: 5cf21919-4360-4b49-b29d-58ea3164ac72
ms.openlocfilehash: f8be7fe521fb3c2662b105e34fd96fea1d1ac6e7
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84413405"
---
# <a name="removing-elements-attributes-and-nodes-from-an-xml-tree-visual-basic"></a>Entfernen von Elementen, Attributen und Knoten aus einer XML-Struktur (Visual Basic)
Sie können eine XML-Struktur ändern, indem Sie Elemente, Attribute und andere Knotentypen entfernen.  
  
 Das Entfernen eines einzelnen Elements oder Attributs aus einem XML-Dokument ist unkompliziert. Wenn Sie aber Auflistungen von Elementen oder Attributen entfernen, sollten Sie zuerst eine Auflistung in einer Liste materialisieren, bevor Sie die Elemente oder Attribute aus der Liste löschen. Verwenden Sie dazu am besten die <xref:System.Xml.Linq.Extensions.Remove%2A>-Erweiterungsmethode, die diese Aufgabe für Sie übernimmt.  
  
 Der Hauptgrund für diese Vorgehensweise besteht darin, dass die meisten Auflistungen, die Sie aus einer XML-Struktur abrufen, mit verzögerter Ausführung zurückgegeben werden. Wenn Sie die Auflistungen nicht zunächst in einer Liste materialisieren oder wenn Sie nicht die Erweiterungsmethoden verwenden, kommt es möglicherweise zu einer bestimmten Form von Fehlern. Weitere Informationen finden Sie unter [Fehler mit gemischtem deklarativem Code/imperativem Code (LINQ to XML) (Visual Basic)](mixed-declarative-code-imperative-code-bugs-linq-to-xml.md).  
  
 Die folgenden Methoden entfernen Knoten und Attribute aus einer XML-Struktur.  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XAttribute.Remove%2A?displayProperty=nameWithType>|Entfernt einen <xref:System.Xml.Linq.XAttribute> aus seinem übergeordneten Knoten.|  
|<xref:System.Xml.Linq.XContainer.RemoveNodes%2A?displayProperty=nameWithType>|Entfernt die untergeordneten Knoten aus einem <xref:System.Xml.Linq.XContainer>.|  
|<xref:System.Xml.Linq.XElement.RemoveAll%2A?displayProperty=nameWithType>|Entfernt Inhalt und Attribute aus einem <xref:System.Xml.Linq.XElement>.|  
|<xref:System.Xml.Linq.XElement.RemoveAttributes%2A?displayProperty=nameWithType>|Entfernt die Attribute eines <xref:System.Xml.Linq.XElement>.|  
|<xref:System.Xml.Linq.XElement.SetAttributeValue%2A?displayProperty=nameWithType>|Entfernt das Attribut, wenn Sie als Wert `null` übergeben.|  
|<xref:System.Xml.Linq.XElement.SetElementValue%2A?displayProperty=nameWithType>|Entfernt das untergeordnete Element, wenn Sie als Wert `null` übergeben.|  
|<xref:System.Xml.Linq.XNode.Remove%2A?displayProperty=nameWithType>|Entfernt einen <xref:System.Xml.Linq.XNode> aus seinem übergeordneten Knoten.|  
|<xref:System.Xml.Linq.Extensions.Remove%2A?displayProperty=nameWithType>|Entfernt jedes Attribut oder Element in der Quellauflistung aus seinem übergeordneten Element.|  
  
## <a name="example"></a>Beispiel  
  
### <a name="description"></a>Beschreibung  
 In diesem Beispiel werden drei Ansätze zum Entfernen von Elementen gezeigt. Zuerst entfernt das Beispiel ein einzelnes Element. Als Zweites ruft das Beispiel eine Auflistung von Elementen ab, materialisiert sie mit dem <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType>-Operator und entfernt die Auflistung. Zum Schluss ruft das Beispiel eine Auflistung von Elementen ab und entfernt diese mit der <xref:System.Xml.Linq.Extensions.Remove%2A>-Erweiterungsmethode.  
  
 Weitere Informationen zum- <xref:System.Linq.Enumerable.ToList%2A> Operator finden Sie unter [Datentypen (Visual Basic)](converting-data-types.md).  
  
### <a name="code"></a>Code  
  
```vb  
Dim root As XElement = _  
    <Root>  
        <Child1>  
            <GrandChild1/>  
            <GrandChild2/>  
            <GrandChild3/>  
        </Child1>  
        <Child2>  
            <GrandChild4/>  
            <GrandChild5/>  
            <GrandChild6/>  
        </Child2>  
        <Child3>  
            <GrandChild7/>  
            <GrandChild8/>  
            <GrandChild9/>  
        </Child3>  
    </Root>  
root.<Child1>.<GrandChild1>.Remove()  
root.<Child2>.Elements().ToList().Remove()  
root.<Child3>.Elements().Remove()  
Console.WriteLine(root)  
```  
  
### <a name="comments"></a>Kommentare  
 Dieser Code erzeugt die folgende Ausgabe:  
  
```xml  
<Root>  
  <Child1>  
    <GrandChild2 />  
    <GrandChild3 />  
  </Child1>  
  <Child2 />  
  <Child3 />  
</Root>  
```  
  
 Beachten Sie, dass das erste Element der zweiten Unterebene aus `Child1` entfernt wurde. Alle Elemente der zweiten Unterebene wurden aus `Child2` und `Child3` entfernt.  
  
## <a name="see-also"></a>Weitere Informationen

- [Ändern von XML-Strukturen (LINQ to XML) (Visual Basic)](modifying-xml-trees-linq-to-xml.md)
