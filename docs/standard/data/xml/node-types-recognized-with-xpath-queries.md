---
title: In XPath-Abfragen erkannte Knotentypen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1d33e22d-18e5-43f8-a466-2e3d0a8dd094
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: db309bf0d04dfab4fd9fbdd2c8b145c1705d8428
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="node-types-recognized-with-xpath-queries"></a>In XPath-Abfragen erkannte Knotentypen
Die in einer XPath-Abfrage erkannten Knotentypen sind nicht dieselben wie die Knotentypen des DOM (Document Object Model).  
  
## <a name="w3c-xpath-node-types"></a>W3C-XPath-Knotentypen  
 Die in einer XPath-Abfrage erkannten Knotentypen sind nicht dieselben Knotentypen wie die Knotentypen des DOM (Document Object Model). Es folgen die von der <xref:System.Xml.XPath.XPathNodeType>-Enumeration dargestellten XPath-Knotentypen.  
  
-   <xref:System.Xml.XPath.XPathNodeType.All>  
  
-   <xref:System.Xml.XPath.XPathNodeType.Attribute>  
  
-   <xref:System.Xml.XPath.XPathNodeType.Comment>  
  
-   <xref:System.Xml.XPath.XPathNodeType.Element>  
  
-   <xref:System.Xml.XPath.XPathNodeType.Namespace>  
  
-   <xref:System.Xml.XPath.XPathNodeType.ProcessingInstruction>  
  
-   <xref:System.Xml.XPath.XPathNodeType.Root>  
  
-   <xref:System.Xml.XPath.XPathNodeType.SignificantWhitespace>  
  
-   <xref:System.Xml.XPath.XPathNodeType.Text>  
  
-   <xref:System.Xml.XPath.XPathNodeType.Whitespace>  
  
 Diesen Knotentypen liegt das XPath-Datenmodell zu Grunde, dessen Knoten vom XML-Infoset abgeleitet sind. Der <xref:System.Xml.XPath.XPathNodeType.SignificantWhitespace>-Knotentyp und der <xref:System.Xml.XPath.XPathNodeType.Whitespace>-Knotentyp sind Microsoft .NET Framework-Erweiterungen der im XPath-Datenmodell beschriebenen Basisknotentypen.  
  
 Der Attributknotentyp wird im XPath-Datenmodell und im DOM unterschiedlich verwendet. Im XPath-Datenmodell ist dem Elementknoten eine Gruppe von Attributknoten zugeordnet, und der Elementknoten ist der übergeordnete Knoten jedes Attributknotens. Im DOM ist der Elementknoten dagegen der Besitzer und nicht der übergeordnete Knoten. In beiden Modellen werden Attribut- und Namespaceknoten nicht als untergeordnete Knoten des Elementknotens betrachtet.  
  
 Der Namespaceknotentyp ist eine Erweiterung des XPath-Datenmodells, der nicht als DOM-Knotentyp erkannt wird.  
  
 Weitere Informationen zum Navigieren durch Element-, Attribut-und Namespaceknoten finden Sie in den Themen [Navigieren in Knotengruppen mit XPathNavigator](../../../../docs/standard/data/xml/node-set-navigation-using-xpathnavigator.md) und [Navigieren durch Attribut- und Namespaceknoten mit XPathNavigator](../../../../docs/standard/data/xml/attribute-and-namespace-node-navigation-using-xpathnavigator.md).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Xml.XmlDocument>  
 <xref:System.Xml.XPath.XPathDocument>  
 <xref:System.Xml.XPath.XPathNavigator>  
 [Verarbeiten von XML-Daten mithilfe des XPath-Datenmodells](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)  
 [Auswählen von XML-Daten mit XPathNavigator](../../../../docs/standard/data/xml/select-xml-data-using-xpathnavigator.md)  
 [Auswerten von XPath-Ausdrücken mit XPathNavigator](../../../../docs/standard/data/xml/evaluate-xpath-expressions-using-xpathnavigator.md)  
 [Vergleich von Knoten mit XPathNavigator](../../../../docs/standard/data/xml/matching-nodes-using-xpathnavigator.md)  
 [XPath-Abfragen und Namespaces](../../../../docs/standard/data/xml/xpath-queries-and-namespaces.md)  
 [Kompilierte XPath-Ausdrücke](../../../../docs/standard/data/xml/compiled-xpath-expressions.md)
