---
title: Navigieren in Knotengruppen mit "XPathNavigator"
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 1a954b41-7173-40bc-8544-d430f209b1e5
ms.openlocfilehash: 132154afdfd3e5bd6769bfcce338e598136e7515
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84288757"
---
# <a name="node-set-navigation-using-xpathnavigator"></a>Navigieren in Knotengruppen mit "XPathNavigator"
Sie können mit den Navigationsmethoden für Knotengruppen der <xref:System.Xml.XPath.XPathDocument>-Klasse durch Knoten in einem <xref:System.Xml.XmlDocument> oder <xref:System.Xml.XPath.XPathNavigator> navigieren. Sie können durch alle Knoten oder durch eine von den Auswahlmethoden der <xref:System.Xml.XPath.XPathNavigator>-Klasse zurückgegebene Gruppe von Knoten navigieren.  
  
## <a name="element-node-set-navigation"></a>Navigation durch Gruppen von Elementknoten  
 Die <xref:System.Xml.XPath.XPathNavigator>-Klasse stellt mehrere Methoden zum Navigieren durch Elementknoten bereit. In der folgenden Tabelle sind die verfügbaren Navigationsmethoden mit einer Beschreibung ihrer Wirkungsweise aufgeführt. Methoden zur Navigation durch Attribut- und Namespaceknoten sind nicht aufgeführt.  
  
 Weitere Informationen zum Auswählen von Knoten in einem <xref:System.Xml.XPath.XPathNavigator>-Objekt finden Sie unter [Auswählen, Auswerten und Zuordnen von XML-Daten mithilfe von XPathNavigator](selecting-evaluating-and-matching-xml-data-using-xpathnavigator.md). Weitere Informationen zum Navigieren durch Attribut-und Namespaceknoten finden Sie unter [Navigieren durch Attribut- und Namespaceknoten mit XPathNavigator](attribute-and-namespace-node-navigation-using-xpathnavigator.md).  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|<xref:System.Xml.XPath.XPathNavigator.MoveTo%2A>|Positioniert den <xref:System.Xml.XPath.XPathNavigator> auf die Position des angegebenen <xref:System.Xml.XPath.XPathNavigator>.|  
|<xref:System.Xml.XPath.XPathNavigator.MoveToChild%2A>|Positioniert den <xref:System.Xml.XPath.XPathNavigator> auf einen dem aktuellen Knoten untergeordneten Knoten.|  
|<xref:System.Xml.XPath.XPathNavigator.MoveToFirst%2A>|Positioniert den <xref:System.Xml.XPath.XPathNavigator> auf den ersten dem aktuellen Knoten nebengeordneten Knoten.|  
|<xref:System.Xml.XPath.XPathNavigator.MoveToFirstChild%2A>|Positioniert den <xref:System.Xml.XPath.XPathNavigator> auf den ersten dem aktuellen Knoten untergeordneten Knoten.|  
|<xref:System.Xml.XPath.XPathNavigator.MoveToFollowing%2A>|Positioniert den <xref:System.Xml.XPath.XPathNavigator> auf das nächste Element in Dokumentreihenfolge.|  
|<xref:System.Xml.XPath.XPathNavigator.MoveToId%2A>|Positioniert den <xref:System.Xml.XPath.XPathNavigator> auf den Knoten, der ein Attribut vom Typ `ID` aufweist und einen dem angegebenen <xref:System.String> entsprechenden Wert besitzt.|  
|<xref:System.Xml.XPath.XPathNavigator.MoveToNext%2A>|Positioniert den <xref:System.Xml.XPath.XPathNavigator> auf den nächsten dem aktuellen Knoten nebengeordneten Knoten.|  
|<xref:System.Xml.XPath.XPathNavigator.MoveToParent%2A>|Positioniert den <xref:System.Xml.XPath.XPathNavigator> auf den dem aktuellen Knoten übergeordneten Knoten.|  
|<xref:System.Xml.XPath.XPathNavigator.MoveToPrevious%2A>|Positioniert den <xref:System.Xml.XPath.XPathNavigator> auf den vorhergehenden nebengeordneten Knoten des aktuellen Knotens.|  
|<xref:System.Xml.XPath.XPathNavigator.MoveToRoot%2A>|Positioniert den <xref:System.Xml.XPath.XPathNavigator> auf den Stammknoten des XML-Dokuments.|  
  
## <a name="comments-and-processing-instruction-node-navigation"></a>Navigation durch Kommentare und Knoten mit Verarbeitungsanweisungen  
 Die folgenden Methoden der <xref:System.Xml.XPath.XPathNavigator>-Klasse sind zum Positionieren auf Kommentare und Verarbeitungsanweisungen in einem XML-Dokument bestimmt.  
  
- <xref:System.Xml.XPath.XPathNavigator.MoveTo%2A>  
  
- <xref:System.Xml.XPath.XPathNavigator.MoveToNext%2A>  
  
- <xref:System.Xml.XPath.XPathNavigator.MoveToPrevious%2A>  
  
- <xref:System.Xml.XPath.XPathNavigator.MoveToFirst%2A>  
  
- <xref:System.Xml.XPath.XPathNavigator.MoveToFirstChild%2A>  
  
- <xref:System.Xml.XPath.XPathNavigator.MoveToChild%2A>  
  
- <xref:System.Xml.XPath.XPathNavigator.MoveToParent%2A>  
  
- <xref:System.Xml.XPath.XPathNavigator.MoveToId%2A>  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Xml.XmlDocument>
- <xref:System.Xml.XPath.XPathDocument>
- <xref:System.Xml.XPath.XPathNavigator>
- [Verarbeiten von XML-Daten mithilfe des XPath-Datenmodells](process-xml-data-using-the-xpath-data-model.md)
- [Das Navigieren durch Attribut- und Namespaceknoten mit XPathNavigator](attribute-and-namespace-node-navigation-using-xpathnavigator.md)
- [Extrahieren von XML-Daten mit XPathNavigator](extract-xml-data-using-xpathnavigator.md)
- [Zugreifen auf streng typisierte XML-Daten mit XPathNavigator](accessing-strongly-typed-xml-data-using-xpathnavigator.md)
