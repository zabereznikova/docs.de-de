---
title: "In XPath-Abfragen erkannte Knotentypen | Microsoft Docs"
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
ms.assetid: 1d33e22d-18e5-43f8-a466-2e3d0a8dd094
caps.latest.revision: 2
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 2
---
# In XPath-Abfragen erkannte Knotentypen
Die in einer XPath\-Abfrage erkannten Knotentypen sind nicht dieselben wie die Knotentypen des DOM \(Document Object Model\).  
  
## W3C\-XPath\-Knotentypen  
 Die in einer XPath\-Abfrage erkannten Knotentypen sind nicht dieselben Knotentypen wie die Knotentypen des DOM \(Document Object Model\).  Es folgen die von der <xref:System.Xml.XPath.XPathNodeType>\-Enumeration dargestellten XPath\-Knotentypen.  
  
-   <xref:System.Xml.XPath.XPathNodeType>  
  
-   <xref:System.Xml.XPath.XPathNodeType>  
  
-   <xref:System.Xml.XPath.XPathNodeType>  
  
-   <xref:System.Xml.XPath.XPathNodeType>  
  
-   <xref:System.Xml.XPath.XPathNodeType>  
  
-   <xref:System.Xml.XPath.XPathNodeType>  
  
-   <xref:System.Xml.XPath.XPathNodeType>  
  
-   <xref:System.Xml.XPath.XPathNodeType>  
  
-   <xref:System.Xml.XPath.XPathNodeType>  
  
-   <xref:System.Xml.XPath.XPathNodeType>  
  
 Diesen Knotentypen liegt das XPath\-Datenmodell zu Grunde, dessen Knoten vom XML\-Infoset abgeleitet sind.  Der <xref:System.Xml.XPath.XPathNodeType>\-Knotentyp und der <xref:System.Xml.XPath.XPathNodeType>\-Knotentyp sind Microsoft .NET Framework\-Erweiterungen der im XPath\-Datenmodell beschriebenen Basisknotentypen.  
  
 Der Attributknotentyp wird im XPath\-Datenmodell und im DOM unterschiedlich verwendet.  Im XPath\-Datenmodell ist dem Elementknoten eine Gruppe von Attributknoten zugeordnet, und der Elementknoten ist der übergeordnete Knoten jedes Attributknotens.  Im DOM ist der Elementknoten dagegen der Besitzer und nicht der übergeordnete Knoten.  In beiden Modellen werden Attribut\- und Namespaceknoten nicht als untergeordnete Knoten des Elementknotens betrachtet.  
  
 Der Namespaceknotentyp ist eine Erweiterung des XPath\-Datenmodells, der nicht als DOM\-Knotentyp erkannt wird.  
  
 Weitere Informationen zum Navigieren durch Element\-, Attribut\- und Namespaceknoten finden Sie unter den Themen [Navigieren in Knotengruppen mit "XPathNavigator"](../../../../docs/standard/data/xml/node-set-navigation-using-xpathnavigator.md) und [Das Navigieren durch Attribut\- und Namespaceknoten mit "XPathNavigator"](../../../../docs/standard/data/xml/attribute-and-namespace-node-navigation-using-xpathnavigator.md).  
  
## Siehe auch  
 <xref:System.Xml.XmlDocument>   
 <xref:System.Xml.XPath.XPathDocument>   
 <xref:System.Xml.XPath.XPathNavigator>   
 [Verarbeiten von XML\-Daten mithilfe des XPath\-Datenmodells](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)   
 [Auswählen von XML\-Daten mit 'XPathNavigator'](../../../../docs/standard/data/xml/select-xml-data-using-xpathnavigator.md)   
 [Auswerten von XPath\-Ausdrücken mit "XPathNavigator"](../../../../docs/standard/data/xml/evaluate-xpath-expressions-using-xpathnavigator.md)   
 [Vergleich von Knoten mit "XPathNavigator"](../../../../docs/standard/data/xml/matching-nodes-using-xpathnavigator.md)   
 [XPath\-Abfragen und Namespaces](../../../../docs/standard/data/xml/xpath-queries-and-namespaces.md)   
 [Kompilierte XPath\-Ausdrücke](../../../../docs/standard/data/xml/compiled-xpath-expressions.md)