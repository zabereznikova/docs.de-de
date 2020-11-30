---
title: Erstellen von neuen Knoten im Dokumentobjektmodell
ms.date: 03/30/2017
ms.assetid: 6c2b9789-b61a-49f9-b33f-db01a945edf2
ms.openlocfilehash: dea7add100fbdbb9e761fe39d0d824d27975757f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95704746"
---
# <a name="create-new-nodes-in-the-dom"></a>Erstellen von neuen Knoten im Dokumentobjektmodell

Das <xref:System.Xml.XmlDocument> verfügt über eine create-Methode für alle Knotentypen. Stellen Sie der Methode, falls erforderlich, einen Namen und Inhalt oder andere Parameter für die Knoten bereit, die Inhalt aufweisen (z. B. ein Textknoten), und der Knoten wird erstellt. Für die folgenden Methoden muss ein Name angegeben sein und es müssen einige andere Parameter ausgefüllt sein, damit ein entsprechender Knoten erstellt wird.  
  
- <xref:System.Xml.XmlDocument.CreateCDataSection%2A>  
  
- <xref:System.Xml.XmlDocument.CreateComment%2A>  
  
- <xref:System.Xml.XmlDocument.CreateDocumentFragment%2A>  
  
- <xref:System.Xml.XmlDocument.CreateDocumentType%2A>  
  
- <xref:System.Xml.XmlDocument.CreateElement%2A>  
  
- <xref:System.Xml.XmlDocument.CreateNode%2A>  
  
- <xref:System.Xml.XmlDocument.CreateProcessingInstruction%2A>  
  
- <xref:System.Xml.XmlDocument.CreateSignificantWhitespace%2A>  
  
- <xref:System.Xml.XmlDocument.CreateTextNode%2A>  
  
- <xref:System.Xml.XmlDocument.CreateWhitespace%2A>  
  
- <xref:System.Xml.XmlDocument.CreateXmlDeclaration%2A>  
  
 Für andere Knoten müssen über das Bereitstellen von Daten für Parameter hinausgehende Anforderungen erfüllt werden.  
  
 Informationen zu Attributen finden Sie unter [Erstellen von neuen Attributen für Elemente im Dokumentobjektmodell](creating-new-attributes-for-elements-in-the-dom.md). Informationen zur Validierung von Element- und Attributnamen finden Sie unter [Überprüfen von XML-Element- und -Attributnamen beim Erstellen neuer Knoten](xml-element-and-attribute-name-verification-when-creating-new-nodes.md). Informationen zum Erstellen von Entitätsverweisen finden Sie unter [Erstellen von neuen Entitätsverweisen](creating-new-entity-references.md). Informationen dazu, welche Auswirkungen Namespaces auf die Erweiterung von Entitätsverweisen haben, finden Sie unter [Auswirkungen von Namespaces auf die Entitätsverweiserweiterung für neue Knoten mit Elementen und Attributen](namespace-affect-on-entity-ref-expansion-for-new-nodes.md).  
  
 Nach dem Erstellen von neuen Knoten stehen verschiedene Methoden zum Einfügen der Knoten in die Struktur zur Verfügung. In der Tabelle sind die Methoden und eine Beschreibung der Position des neuen Knotens im XML-DOM (Dokumentobjektmodell) aufgelistet.  
  
|Methode|Knotenposition|  
|------------|--------------------|  
|<xref:System.Xml.XmlNode.InsertBefore%2A>|Vor dem Referenzknoten eingefügt. So fügen Sie beispielsweise den neuen Knoten an Position 5 ein:<br /><br /> `Dim refChild As XmlNode = node.ChildNodes(4) 'The reference is zero-based.node.InsertBefore(newChild, refChild);`<br /><br /> `XmlNode refChild = node.ChildNodes[4]; //The reference is zero-based. node.InsertBefore(newChild, refChild);`<br /><br /> Weitere Informationen finden Sie unter der Methode <xref:System.Xml.XmlNode.InsertBefore%2A>.|  
|<xref:System.Xml.XmlNode.InsertAfter%2A>|Nach dem Referenzknoten eingefügt. Zum Beispiel:<br /><br /> `node.InsertAfter(newChild, refChild)`<br /><br /> `node.InsertAfter(newChild, refChild);`<br /><br /> Weitere Informationen finden Sie unter der Methode <xref:System.Xml.XmlNode.InsertAfter%2A>.|  
|<xref:System.Xml.XmlNode.AppendChild%2A>|Fügt den Knoten am Ende der Liste der untergeordneten Knoten für den angegebenen Knoten an. Wenn der Knoten, der hinzugefügt wird, ein <xref:System.Xml.XmlDocumentFragment> ist, wird der gesamte Inhalt des Dokumentfragments in die Liste der untergeordneten Elemente dieses Knotens verschoben. Weitere Informationen finden Sie unter der Methode <xref:System.Xml.XmlNode.AppendChild%2A>.|  
|<xref:System.Xml.XmlNode.PrependChild%2A>|Fügt den Knoten am Anfang der Liste der untergeordneten Knoten für den angegebenen Knoten an. Wenn der Knoten, der hinzugefügt wird, ein <xref:System.Xml.XmlDocumentFragment> ist, wird der gesamte Inhalt des Dokumentfragments in die Liste der untergeordneten Elemente dieses Knotens verschoben. Weitere Informationen finden Sie unter der Methode <xref:System.Xml.XmlNode.PrependChild%2A>.|  
|<xref:System.Xml.XmlAttributeCollection.Append%2A>|Fügt am Ende der einem Element zugeordneten Attributauflistung einen <xref:System.Xml.XmlAttribute>-Knoten an. Weitere Informationen finden Sie unter der Methode <xref:System.Xml.XmlAttributeCollection.Append%2A>.|  
  
## <a name="see-also"></a>Siehe auch

- [XML-Dokumentobjektmodell (DOM)](xml-document-object-model-dom.md)
