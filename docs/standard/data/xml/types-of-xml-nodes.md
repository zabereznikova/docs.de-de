---
title: "XML-Knotentypen | Microsoft Docs"
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
ms.assetid: 71d03b78-6898-4ce7-b0fc-1282573f31f7
caps.latest.revision: 4
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 3
---
# XML-Knotentypen
Wenn ein XML\-Dokument als Knotenstruktur in den Speicher eingelesen wird, werden die Knotentypen für die Knoten beim Erstellen festgelegt.  Das XML\-DOM \(Document Object Model, Dokumentobjektmodell\) umfasst mehrere Knotentypen, die vom W3C \(World Wide Web Consortium\) festgelegt wurden und in Abschnitt 1.1.1, "The DOM Structure Model", aufgeführt sind.  In der folgenden Tabelle sind die Knotentypen sowie das jedem Knotentyp zugewiesene Objekt und eine kurze Beschreibung enthalten.  
  
|DOM\-Knotentyp|Objekt|Beschreibung|  
|--------------------|------------|------------------|  
|Document|[XmlDocument\-Klasse](frlrfSystemXmlXmlDocumentClassTopic)|Der Container für alle Knoten in der Struktur.  	Er wird auch als Dokumentstamm bezeichnet und ist nicht immer mit dem Stammelement identisch.|  
|DocumentFragment|[XmlDocumentFragment\-Klasse](frlrfSystemXmlXmlDocumentFragmentClassTopic)|Eine temporäre Sammlung, die einen oder mehrere Knoten ohne Struktur enthält.|  
|DocumentType|[XmlDocumentType\-Klasse](frlrfSystemXmlXmlDocumentTypeClassTopic)|Stellt den `<!DOCTYPE…>`\-Knoten dar.|  
|EntityReference|[XmlEntityReference\-Klasse](frlrfSystemXmlXmlEntityReferenceClassTopic)|Stellt den Text des nicht erweiterten Entitätsverweises dar.|  
|Element|[XmlElement\-Klasse](frlrfSystemXmlXmlElementClassTopic)|Stellt einen Elementknoten dar.|  
|Attr|[XmlAttribute\-Klasse](frlrfSystemXmlXmlAttributeClassTopic)|Ist ein Attribut eines Elements.|  
|ProcessingInstruction|[XmlProcessingInstruction\-Klasse](frlrfSystemXmlXmlProcessingInstructionClassTopic)|Ist ein Verarbeitungsanweisungsknoten.|  
|Kommentar|[XmlComment\-Klasse](frlrfSystemXmlXmlCommentClassTopic)|Ein Kommentarknoten.|  
|Text|[XmlText\-Klasse](frlrfSystemXmlXmlTextClassTopic)|Zu einem Element oder Attribut gehöriger Text.|  
|CDATASection|[XmlCDataSection\-Klasse](frlrfSystemXmlXmlCDataSectionClassTopic)|Stellt CDATA dar.|  
|Entität|[XmlEntity\-Klasse](frlrfSystemXmlXmlEntityClassTopic)|Stellt die `<!ENTITY…>`\-Deklarationen in einem XML\-Dokument dar, entweder aus einer internen DTD\-Untergruppe \(Document Type Definition, Dokumenttypdefinition\) oder aus externen DTDs und Parameterentitäten.|  
|Notation|[XmlNotation\-Klasse](frlrfSystemXmlXmlNotationClassTopic)|Stellt eine in der DTD deklarierte Notation dar.|  
  
 Auch wenn ein Attribut \(*attr*\) in Abschnitt 1.2, "Fundamental Interfaces", des W3C\-DOMs, Level 1, als Knoten aufgeführt wird, gilt es nicht als untergeordnetes Element eines Elementknotens.  
  
 In der folgenden Tabelle sind zusätzliche Knotentypen aufgeführt, die nicht vom W3C definiert wurden, jedoch im Microsot .NET Framework\-Objektmodell als **XmlNodeType**\-Enumerationen zur Verfügung stehen.  Daher ist bei diesen Knotentypen keine entsprechende Spalte für den DOM\-Knotentyp vorhanden.  
  
|Knotentyp|Beschreibung|  
|---------------|------------------|  
|<xref:System.Xml.XmlDeclaration>|Stellt den Deklarationsknoten `<?xml version="1.0"…>` dar.|  
|<xref:System.Xml.XmlSignificantWhitespace>|Stellt signifikanten Leerraum, d. h. Leerraum in gemischtem Inhalt, dar.|  
|<xref:System.Xml.XmlWhitespace>|Stellt den Leerraum im Inhalt eines Elements dar.|  
|EndElement|Wird zurückgegeben, wenn der **XmlReader** das End eines Elements erreicht.<br /><br /> Beispiel\-XML: **\<\/item\>**<br /><br /> Weitere Informationen finden Sie unter [XmlNodeType\-Enumeration](frlrfSystemXmlXmlNodeTypeClassTopic).|  
|EndEntity|Wird zurückgegeben, wenn der **XmlReader** aufgrund eines Aufrufs von <xref:System.Xml.XmlReader.ResolveEntity%2A> das Ende der Entitätsersetzung erreicht.  Weitere Informationen finden Sie unter [XmlNodeType\-Enumeration](frlrfSystemXmlXmlNodeTypeClassTopic).|  
  
 Ein Codebeispiel, in dem XML\-Daten eingelesen und mithilfe eines case\-Konstrukts für die Knotentypen Informationen zum Knoten und dessen Inhalt gedruckt werden, finden Sie unter der [XmlSignificantWhitespace.NodeType\-Eigenschaft](frlrfSystemXmlXmlSignificantWhitespaceClassNodeTypeTopic).  
  
 Weitere Informationen zur Objekthierarchie der Knotentypen und ihren entsprechenden Objektnamen finden Sie unter [Hierarchie im XML\-Dokumentobjektmodell \(DOM\)](../../../../docs/standard/data/xml/xml-document-object-model-dom-hierarchy.md).  Weitere Informationen über die Objekte, die in der Knotenstruktur erstellt werden, finden Sie unter [Zuordnen der Objekthierarchie zu XML\-Daten](../../../../docs/standard/data/xml/mapping-the-object-hierarchy-to-xml-data.md).  
  
## Siehe auch  
 [XML\-Dokumentobjektmodell \(DOM\)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)