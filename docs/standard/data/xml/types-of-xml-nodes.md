---
title: XML-Knotentypen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 71d03b78-6898-4ce7-b0fc-1282573f31f7
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 3914a2c5c06a2cc73f14bc473984094b474d537e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="types-of-xml-nodes"></a>XML-Knotentypen
Wenn ein XML-Dokument als Knotenstruktur in den Speicher eingelesen wird, werden die Knotentypen für die Knoten beim Erstellen festgelegt. Das XML-DOM (Document Object Model, Dokumentobjektmodell) umfasst mehrere Knotentypen, die vom W3C (World Wide Web Consortium) festgelegt wurden und in Abschnitt 1.1.1, "The DOM Structure Model", aufgeführt sind. In der folgenden Tabelle sind die Knotentypen sowie das jedem Knotentyp zugewiesene Objekt und eine kurze Beschreibung enthalten.  
  
|DOM-Knotentyp|Objekt|Beschreibung|  
|-------------------|------------|-----------------|  
|Dokument|<xref:System.Xml.XmlDocument>|Der Container für alle Knoten in der Struktur. 	Er wird auch als Dokumentstamm bezeichnet und ist nicht immer mit dem Stammelement identisch.|  
|DocumentFragment|<xref:System.Xml.XmlDocumentFragment>|Eine temporäre Sammlung, die einen oder mehrere Knoten ohne Struktur enthält.|  
|DocumentType|<xref:System.Xml.XmlDocumentType>|Stellt den `<!DOCTYPE…>`-Knoten dar.|  
|EntityReference|<xref:System.Xml.XmlEntityReference>|Stellt den Text des nicht erweiterten Entitätsverweises dar.|  
|Element|<xref:System.Xml.XmlElement>|Stellt einen Elementknoten dar.|  
|Attr|<xref:System.Xml.XmlAttribute>|Ist ein Attribut eines Elements.|  
|ProcessingInstruction|<xref:System.Xml.XmlProcessingInstruction>|Ist ein Verarbeitungsanweisungsknoten.|  
|Kommentar|<xref:System.Xml.XmlComment>|Ein Kommentarknoten.|  
|Text|<xref:System.Xml.XmlText>|Zu einem Element oder Attribut gehöriger Text.|  
|CDATASection|<xref:System.Xml.XmlCDataSection>|Stellt CDATA dar.|  
|Entität|<xref:System.Xml.XmlEntity>|	Stellt die `<!ENTITY…>`-Deklarationen in einem XML-Dokument dar, entweder aus einer internen DTD-Untergruppe (Document Type Definition, Dokumenttypdefinition) oder aus externen DTDs und Parameterentitäten.|  
|Notation|<xref:System.Xml.XmlNotation>|Stellt eine in der DTD deklarierte Notation dar.|  
  
 Auch wenn ein Attribut (*Attr*) wird in der W3C DOM Level 1 Abschnitt 1.2 grundlegende Schnittstellen als Knoten, wird dieses kein untergeordnetes Element eines Elementknotens betrachtet.  
  
 In der folgenden Tabelle sind zusätzliche Knotentypen aufgeführt, die nicht durch das W3C definiert aus, jedoch in der Microsoft .NET Framework-Objektmodell als zur Verfügung stehen **XmlNodeType** Enumerationen. Daher ist bei diesen Knotentypen keine entsprechende Spalte für den DOM-Knotentyp vorhanden.  
  
|Knotentyp|Beschreibung|  
|---------------|-----------------|  
|<xref:System.Xml.XmlDeclaration>|Stellt den Deklarationsknoten `<?xml version="1.0"…>` dar.|  
|<xref:System.Xml.XmlSignificantWhitespace>|Stellt signifikanten Leerraum, d. h. Leerraum in gemischtem Inhalt, dar.|  
|<xref:System.Xml.XmlWhitespace>|Stellt den Leerraum im Inhalt eines Elements dar.|  
|EndElement|Zurückgegeben, wenn **XmlReader** Ruft am Ende eines Elements.<br /><br /> XML-Beispieldatei:  **\< /item >**<br /><br /> Weitere Informationen finden Sie unter <xref:System.Xml.XmlNodeType>.|  
|EndEntity|Zurückgegeben, wenn **XmlReader** Ruft am Ende der entitätsersetzung infolge eines Aufrufs für <xref:System.Xml.XmlReader.ResolveEntity%2A>. Weitere Informationen finden Sie unter <xref:System.Xml.XmlNodeType>.|  
  
 Ein Codebeispiel, in dem XML- und ein Case-Konstrukts für die Knotentypen, um Informationen über den Knoten und dessen Inhalt drucken verwendet, finden Sie unter <xref:System.Xml.XmlSignificantWhitespace.NodeType%2A>.  
  
 Weitere Informationen zur Objekthierarchie der Knotentypen und ihren entsprechenden Objektnamen finden Sie unter [Hierarchie im XML-Dokumentobjektmodell (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom-hierarchy.md). Weitere Informationen zu den in der Knotenstruktur erstellten Objekten finden Sie unter [Zuordnen der Objekthierarchie zu XML-Daten](../../../../docs/standard/data/xml/mapping-the-object-hierarchy-to-xml-data.md).  
  
## <a name="see-also"></a>Siehe auch  
 [XML-Dokumentobjektmodell (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
