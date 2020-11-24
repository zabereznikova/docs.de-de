---
title: XML-Knotentypen
ms.date: 03/30/2017
ms.assetid: 71d03b78-6898-4ce7-b0fc-1282573f31f7
ms.openlocfilehash: 97458fc26b3c63dd6d7882c180192aef63109e1a
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94824596"
---
# <a name="types-of-xml-nodes"></a>XML-Knotentypen
Wenn ein XML-Dokument als Knotenstruktur in den Speicher eingelesen wird, werden die Knotentypen für die Knoten beim Erstellen festgelegt. Das XML-DOM (Document Object Model, Dokumentobjektmodell) umfasst mehrere Knotentypen, die vom W3C (World Wide Web Consortium) festgelegt wurden und in Abschnitt 1.1.1, "The DOM Structure Model", aufgeführt sind. In der folgenden Tabelle sind die Knotentypen sowie das jedem Knotentyp zugewiesene Objekt und eine kurze Beschreibung enthalten.  
  
|DOM-Knotentyp|Object|Beschreibung|  
|-------------------|------------|-----------------|  
|Dokument|<xref:System.Xml.XmlDocument>|Der Container für alle Knoten in der Struktur. Er wird auch als Dokumentstamm bezeichnet und ist nicht immer mit dem Stammelement identisch.|  
|DocumentFragment|<xref:System.Xml.XmlDocumentFragment>|Eine temporäre Sammlung, die einen oder mehrere Knoten ohne Struktur enthält.|  
|DocumentType|<xref:System.Xml.XmlDocumentType>|Stellt den `<!DOCTYPE…>`-Knoten dar.|  
|EntityReference|<xref:System.Xml.XmlEntityReference>|Stellt den Text des nicht erweiterten Entitätsverweises dar.|  
|Element|<xref:System.Xml.XmlElement>|Stellt einen Elementknoten dar.|  
|Attr|<xref:System.Xml.XmlAttribute>|Ist ein Attribut eines Elements.|  
|ProcessingInstruction|<xref:System.Xml.XmlProcessingInstruction>|Ist ein Verarbeitungsanweisungsknoten.|  
|Kommentar|<xref:System.Xml.XmlComment>|Ein Kommentarknoten.|  
|Text|<xref:System.Xml.XmlText>|Zu einem Element oder Attribut gehöriger Text.|  
|CDATASection|<xref:System.Xml.XmlCDataSection>|Stellt CDATA dar.|  
|Entität|<xref:System.Xml.XmlEntity>|Stellt die `<!ENTITY…>`-Deklarationen in einem XML-Dokument dar, entweder aus einer internen DTD-Untergruppe (Document Type Definition, Dokumenttypdefinition) oder aus externen DTDs und Parameterentitäten.|  
|Notation|<xref:System.Xml.XmlNotation>|Stellt eine in der DTD deklarierte Notation dar.|  
  
 Auch wenn ein Attribut (*attr*) in Abschnitt 1.2, „Fundamental Interfaces“, des W3C-DOMs, Level 1, als Knoten aufgeführt wird, gilt es nicht als untergeordnetes Element eines Elementknotens.  
  
 In der folgenden Tabelle sind zusätzliche Knotentypen aufgeführt, die nicht vom W3C definiert wurden, jedoch im Microsoft .NET Framework-Objektmodell als **XmlNodeType**-Enumerationen zur Verfügung stehen. Daher ist bei diesen Knotentypen keine entsprechende Spalte für den DOM-Knotentyp vorhanden.  
  
|Knotentyp|Beschreibung|  
|---------------|-----------------|  
|<xref:System.Xml.XmlDeclaration>|Stellt den Deklarationsknoten `<?xml version="1.0"…>` dar.|  
|<xref:System.Xml.XmlSignificantWhitespace>|Stellt signifikanten Leerraum, d. h. Leerraum in gemischtem Inhalt, dar.|  
|<xref:System.Xml.XmlWhitespace>|Stellt den Leerraum im Inhalt eines Elements dar.|  
|EndElement|Wird zurückgegeben, wenn der **XmlReader** das Ende eines Elements erreicht.<br /><br /> Beispiel-XML: **\</item>**<br /><br /> Weitere Informationen finden Sie unter <xref:System.Xml.XmlNodeType>.|  
|EndEntity|Wird zurückgegeben, wenn der **XmlReader** aufgrund eines Aufrufs von <xref:System.Xml.XmlReader.ResolveEntity%2A> das Ende der Entitätsersetzung erreicht. Weitere Informationen finden Sie unter <xref:System.Xml.XmlNodeType>.|  
  
 Ein Codebeispiel, in dem XML-Daten eingelesen und mithilfe eines case-Konstrukts für die Knotentypen Informationen zum Knoten und dessen Inhalt gedruckt werden, finden Sie unter der <xref:System.Xml.XmlSignificantWhitespace.NodeType%2A>-Eigenschaft.  
  
 Weitere Informationen zur Objekthierarchie der Knotentypen und ihren entsprechenden Objektnamen finden Sie unter [Hierarchie im XML-Dokumentobjektmodell (DOM)](xml-document-object-model-dom-hierarchy.md). Weitere Informationen zu den in der Knotenstruktur erstellten Objekten finden Sie unter [Zuordnen der Objekthierarchie zu XML-Daten](mapping-the-object-hierarchy-to-xml-data.md).  
  
## <a name="see-also"></a>Siehe auch

- [XML-Dokumentobjektmodell (DOM)](xml-document-object-model-dom.md)
