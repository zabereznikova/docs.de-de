---
title: Hinzufügen von Elementen, Attributen und Knoten zu einem XML-Baum (C#)
ms.date: 07/20/2015
ms.assetid: db911e4f-40aa-499a-9500-a9763bb6df56
ms.openlocfilehash: 20d8d9d9c592f5f570d7c94298dcee41763c1f1f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79169574"
---
# <a name="adding-elements-attributes-and-nodes-to-an-xml-tree-c"></a>Hinzufügen von Elementen, Attributen und Knoten zu einem XML-Baum (C#)
Sie können einer vorhandenen XML-Struktur Inhalt (Elemente, Attribute, Kommentare, Verarbeitungsanweisungen, Text und CDATA) hinzufügen.  
  
## <a name="methods-for-adding-content"></a>Methoden zum Hinzufügen von Inhalt  
 Die folgenden Methoden fügen einem <xref:System.Xml.Linq.XElement> oder einem <xref:System.Xml.Linq.XDocument> untergeordneten Inhalt hinzu:  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XContainer.Add%2A>|Fügt Inhalt am Ende des untergeordneten Inhalts des <xref:System.Xml.Linq.XContainer> hinzu.|  
|<xref:System.Xml.Linq.XContainer.AddFirst%2A>|Fügt Inhalt vor dem untergeordneten Inhalt des <xref:System.Xml.Linq.XContainer> hinzu.|  
  
 Die folgenden Methoden fügen Inhalt als nebengeordnete Knoten eines <xref:System.Xml.Linq.XNode> hinzu. Der Knoten, dem Sie am häufigsten nebengeordneten Inhalt hinzufügen, ist <xref:System.Xml.Linq.XElement>, obwohl Sie gültigen nebengeordneten Inhalt auch anderen Knotentypen hinzufügen können, z. B. <xref:System.Xml.Linq.XText> oder <xref:System.Xml.Linq.XComment>.  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XNode.AddAfterSelf%2A>|Fügt Inhalt nach dem <xref:System.Xml.Linq.XNode> hinzu.|  
|<xref:System.Xml.Linq.XNode.AddBeforeSelf%2A>|Fügt Inhalt vor dem <xref:System.Xml.Linq.XNode> hinzu.|  
  
## <a name="example"></a>Beispiel  
  
### <a name="description"></a>Beschreibung  
 Das folgende Beispiel erstellt zwei XML-Strukturen und ändert dann eine der beiden Strukturen:  
  
### <a name="code"></a>Code  
  
```csharp  
XElement srcTree = new XElement("Root",
    new XElement("Element1", 1),  
    new XElement("Element2", 2),  
    new XElement("Element3", 3),  
    new XElement("Element4", 4),  
    new XElement("Element5", 5)  
);  
XElement xmlTree = new XElement("Root",  
    new XElement("Child1", 1),  
    new XElement("Child2", 2),  
    new XElement("Child3", 3),  
    new XElement("Child4", 4),  
    new XElement("Child5", 5)  
);  
xmlTree.Add(new XElement("NewChild", "new content"));  
xmlTree.Add(  
    from el in srcTree.Elements()  
    where (int)el > 3  
    select el  
);  
// Even though Child9 does not exist in srcTree, the following statement will not  
// throw an exception, and nothing will be added to xmlTree.  
xmlTree.Add(srcTree.Element("Child9"));  
Console.WriteLine(xmlTree);  
```  
  
### <a name="comments"></a>Kommentare  
 Dieser Code erzeugt die folgende Ausgabe:  
  
```xml  
<Root>  
  <Child1>1</Child1>  
  <Child2>2</Child2>  
  <Child3>3</Child3>  
  <Child4>4</Child4>  
  <Child5>5</Child5>  
  <NewChild>new content</NewChild>  
  <Element4>4</Element4>  
  <Element5>5</Element5>  
</Root>  
```  
  