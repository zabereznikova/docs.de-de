---
title: "Ausw&#228;hlen von XML-Daten mit &#39;XPathNavigator&#39; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
ms.assetid: c268c49e-32b9-4171-b782-dcb7b065fa73
caps.latest.revision: 2
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 2
---
# Ausw&#228;hlen von XML-Daten mit &#39;XPathNavigator&#39;
Die <xref:System.Xml.XPath.XPathNavigator>\-Klasse stellt eine Gruppe von Methoden bereit, mit denen eine Gruppe von Knoten in einem <xref:System.Xml.XPath.XPathDocument>\-Objekt oder einem <xref:System.Xml.XmlDocument>\-Objekt mithilfe eines XPath\-Ausdrucks ausgewählt werden können.  Sobald die Knoten ausgewählt sind, können die ausgewählten Knoten durchlaufen werden.  
  
## Auswahlmethoden von "XPathNavigator"  
 Die <xref:System.Xml.XPath.XPathNavigator>\-Klasse stellt eine Gruppe von Methoden bereit, mit denen eine Gruppe von Knoten in einem <xref:System.Xml.XPath.XPathDocument>\-Objekt oder einem <xref:System.Xml.XmlDocument>\-Objekt mithilfe eines XPath\-Ausdrucks ausgewählt werden können.  Die <xref:System.Xml.XPath.XPathNavigator>\-Klasse stellt außerdem eine Gruppe optimierter Methoden bereit, mit denen übergeordnete, direkt untergeordnete und indirekt untergeordnete Knoten schneller als bei Verwendung eines XPath\-Ausdrucks ausgewählt werden können.  Die ausgewählte Knotengruppe wird in einem <xref:System.Xml.XPath.XPathNodeIterator>\-Objekt oder \(falls es sich um nur einen ausgewählten Knoten handelt\) in einem <xref:System.Xml.XPath.XPathNavigator>\-Objekt zurückgegeben.  
  
### Auswählen von Knoten mithilfe von XPath\-Ausdrücken  
 Verwenden Sie eine der folgenden Auswahlmethoden, um eine Gruppe von Knoten mithilfe eines XPath\-Ausdrucks auszuwählen.  
  
-   <xref:System.Xml.XPath.XPathNavigator.Select%2A>  
  
-   <xref:System.Xml.XPath.XPathNavigator.SelectSingleNode%2A>  
  
 Bei einem Aufruf geben diese Methoden eine Knotengruppe zurück, die Sie mithilfe eines <xref:System.Xml.XPath.XPathNodeIterator>\-Objekts oder \(falls es sich um nur einen ausgewählten Knoten handelt\) eines <xref:System.Xml.XPath.XPathNavigator>\-Objekts frei durchsuchen können.  
  
 Das Navigieren mithilfe eines <xref:System.Xml.XPath.XPathNodeIterator>\-Objekts hat keine Auswirkungen auf die Position des <xref:System.Xml.XPath.XPathNavigator>\-Objekts, das zum Erstellen verwendet wurde.  Das von der <xref:System.Xml.XPath.XPathNavigator.SelectSingleNode%2A>\-Methode zurückgegebene <xref:System.Xml.XPath.XPathNavigator>\-Objekt wird auf dem einzelnen zurückgegebenen Knoten positioniert und hat keine Auswirkung auf die Position des <xref:System.Xml.XPath.XPathNavigator>\-Objekts, mit dem es erstellt wurde.  
  
 Im folgenden Beispiel wird das Erstellen eines <xref:System.Xml.XPath.XPathNavigator>\-Objekts aus einem <xref:System.Xml.XPath.XPathDocument>\-Objekts veranschaulicht. Außerdem werden die Verwendung der <xref:System.Xml.XPath.XPathNavigator.Select%2A>\-Methode zum Auswählen der Knoten im <xref:System.Xml.XPath.XPathDocument>\-Objekt sowie die Verwendung des <xref:System.Xml.XPath.XPathNodeIterator>\-Objekts zum Durchlaufen der ausgewählten Knoten dargestellt.  
  
```vb  
Dim document As XPathDocument = New XPathDocument("books.xml")  
Dim navigator As XPathNavigator = document.CreateNavigator()  
Dim nodes As XPathNodeIterator = navigator.Select("/bookstore/book")  
  
While nodes.MoveNext()  
    Console.WriteLine(nodes.Current.Name)  
End While  
```  
  
```csharp  
XPathDocument document = new XPathDocument("books.xml");  
XPathNavigator navigator = document.CreateNavigator();  
XPathNodeIterator nodes = navigator.Select("/bookstore/book");  
  
while(nodes.MoveNext())  
{  
    Console.WriteLine(nodes.Current.Name);  
}  
```  
  
 In diesem Beispiel wird die Datei `books.xml` als Eingabe verwendet.  
  
 [!code-xml[XPathXMLExamples#1](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/books.xml#1)]  
  
### Optimierte Auswahlmethoden  
 Die Methoden <xref:System.Xml.XPath.XPathNavigator.SelectChildren%2A>, <xref:System.Xml.XPath.XPathNavigator.SelectAncestors%2A> und <xref:System.Xml.XPath.XPathNavigator.SelectDescendants%2A> der <xref:System.Xml.XPath.XPathNavigator>\-Klasse stellen XPath\-Ausdrücke dar, mit denen normalerweise direkt untergeordnete sowie indirekt untergeordnete und übergeordnete Knoten abgerufen werden.  Diese Methoden tragen zur Leistungsoptimierung bei und sind schneller als die entsprechenden XPath\-Ausdrücke.  Die Methoden <xref:System.Xml.XPath.XPathNavigator.SelectChildren%2A>, <xref:System.Xml.XPath.XPathNavigator.SelectAncestors%2A> und <xref:System.Xml.XPath.XPathNavigator.SelectDescendants%2A> wählen übergeordnete, direkt untergeordnete und indirekt untergeordnete Knoten auf der Grundlage eines <xref:System.Xml.XPath.XPathNodeType>\-Werts oder des lokalen Namens und des Namespace\-URIs der auszuwählenden Knoten aus.  Die ausgewählten übergeordneten, direkt untergeordneten und indirekt untergeordneten Knoten werden in einem <xref:System.Xml.XPath.XPathNodeIterator>\-Objekt zurückgegeben.  
  
## Siehe auch  
 <xref:System.Xml.XmlDocument>   
 <xref:System.Xml.XPath.XPathDocument>   
 <xref:System.Xml.XPath.XPathNavigator>   
 [Verarbeiten von XML\-Daten mithilfe des XPath\-Datenmodells](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)   
 [Auswerten von XPath\-Ausdrücken mit "XPathNavigator"](../../../../docs/standard/data/xml/evaluate-xpath-expressions-using-xpathnavigator.md)   
 [Vergleich von Knoten mit "XPathNavigator"](../../../../docs/standard/data/xml/matching-nodes-using-xpathnavigator.md)   
 [In XPath\-Abfragen erkannte Knotentypen](../../../../docs/standard/data/xml/node-types-recognized-with-xpath-queries.md)   
 [XPath\-Abfragen und Namespaces](../../../../docs/standard/data/xml/xpath-queries-and-namespaces.md)   
 [Kompilierte XPath\-Ausdrücke](../../../../docs/standard/data/xml/compiled-xpath-expressions.md)