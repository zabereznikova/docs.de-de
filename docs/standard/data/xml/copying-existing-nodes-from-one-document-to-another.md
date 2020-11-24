---
title: Kopieren bestehender Knoten aus einem Dokument in ein anderes
ms.date: 03/30/2017
ms.assetid: 3caa78c1-3448-4b7b-b83c-228ee857635e
ms.openlocfilehash: f4d58fa5aafdd48feff1a768ab0463ac09315476
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94829608"
---
# <a name="copying-existing-nodes-from-one-document-to-another"></a>Kopieren bestehender Knoten aus einem Dokument in ein anderes
Die **ImportNode**-Methode ist das Verfahren, mit dem Sie einen Knoten oder eine ganze Knotenunterstruktur von einem **XmlDocument** in ein anderes kopieren können. Der Knoten, der von dem Aufruf zurückgegeben wird, ist eine Kopie des Knotens aus dem Quelldokument, einschließlich Attributwerten, Knotennamen, Knotentyp und allen namespacebezogenen Attributen wie Präfix, lokaler Name und Namespace-URI (Uniform Resource Identifier). Das Quelldokument bleibt dabei unverändert. Nachdem Sie den Knoten importiert haben, müssen Sie ihn noch der Struktur hinzufügen, indem Sie eine der Methoden zum Einfügen von Knoten verwenden.  
  
 Sobald der Knoten an das neue Dokument angehängt worden ist, ist das neue Dokument Eigentümer des Knotens. Grund hierfür ist, dass jeder Knoten, wenn er erstellt wird, zu einem Dokument gehört, das sein Eigentümer ist. Dies ist auch der Fall, wenn die Knoten in unterschiedlichen Dokumentfragmenten erstellt werden. Dies ist eine XML-DOM-spezifische (Dokumentobjektmodell) Anforderung, die durch den Factoryerstellungsentwurf für die **XmlDocument**-Klasse durchgesetzt wird. So stellt z.B. **CreateElement** die einzige Möglichkeit zum Erstellen neuer Knoten dar.  
  
 Je nach Knotentyp des importierten Knotens und dem Wert des *deep*-Parameters werden ggf. zusätzliche Informationen kopiert. Diese Methode gibt das Verhalten wieder, das erwartet würde, wenn ein Fragment eines XML- oder HTML-Quellcodes aus einem Dokument in ein anderes kopiert würde, und berücksichtigt die Tatsache, dass bei XML die beiden Dokumente unterschiedliche DTDs (Document Type Definitions) aufweisen können.  
  
 In der folgenden Tabelle wird das spezielle Verhalten für jeden Knotentyp veranschaulicht, der importiert werden kann.  
  
|Knotentyp|*deep*-Parameter ist „true“|*deep*-Parameter ist „false“|  
|---------------|------------------------------|-------------------------------|  
|XmlAttribute|Die <xref:System.Xml.XmlAttribute.Specified%2A> ist im XmlAttribute auf **true** festgelegt. Die untergeordneten Elemente des **XmlAttribute**-Quellknotens werden rekursiv importiert. Die daraus resultierenden Knoten werden neu assembliert und bilden die entsprechende Unterstruktur.|Der *deep*-Parameter gilt nicht für **XmlAttribute**-Knoten, da diese beim Importieren stets ihre untergeordneten Knoten mitnehmen.|  
|XmlCDataSection|Kopiert den Knoten einschließlich der zugehörigen Daten.|Kopiert den Knoten einschließlich der zugehörigen Daten.|  
|XmlComment|Kopiert den Knoten einschließlich der zugehörigen Daten.|Kopiert den Knoten einschließlich der zugehörigen Daten.|  
|XmlDocumentFragment|Die untergeordneten Elemente des Quellknotens werden rekursiv importiert. Die daraus resultierenden Knoten werden neu assembliert und bilden die entsprechende Teilstruktur.|Ein leeres **XmlDocumentFragment** wird erstellt.|  
|XmlDocumentType|Kopiert den Knoten einschließlich der zugehörigen Daten.*|Kopiert den Knoten einschließlich der zugehörigen Daten.*|  
|XmlElement|Die untergeordneten Elemente des Quellelements werden rekursiv importiert. Die daraus resultierenden Knoten werden neu assembliert und bilden die entsprechende Teilstruktur. **Hinweis**:  Standardattribute werden nicht kopiert. Wenn das Dokument, in das importiert wird, Standardattribute für diesen Elementnamen definiert, werden diese zugewiesen.|Die angegebenen Attributknoten des Quellelements werden importiert, und die generierten **XmlAttribute**-Knoten werden an das neue Element angehängt. Die untergeordneten Knoten werden nicht kopiert. **Hinweis**:  Standardattribute werden nicht kopiert. Wenn das Dokument, in das importiert wird, Standardattribute für diesen Elementnamen definiert, werden diese zugewiesen.|  
|XmlEntityReference|Da im Quell- und Zieldokument die Entitäten unterschiedlich definiert sein können, kopiert diese Methode nur den **XmlEntityReference**-Knoten. Der Ersetzungstext ist davon nicht betroffen. Wenn die Entität des Zieldokuments definiert ist, wird deren Wert zugewiesen.|Da im Quell- und Zieldokument die Entitäten unterschiedlich definiert sein können, kopiert diese Methode nur den **XmlEntityReference**-Knoten. Der Ersetzungstext ist davon nicht betroffen. Wenn die Entität des Zieldokuments definiert ist, wird deren Wert zugewiesen.|  
|XmlProcessingInstruction|Kopiert den Ziel- und Datenwert des importierten Knotens.|Kopiert den Ziel- und Datenwert des importierten Knotens.|  
|XmlText|Kopiert den Knoten einschließlich der zugehörigen Daten.|Kopiert den Knoten einschließlich der zugehörigen Daten.|  
|XmlSignificantWhitespace|Kopiert den Knoten einschließlich der zugehörigen Daten.|Kopiert den Knoten einschließlich der zugehörigen Daten.|  
|XmlWhitespace|Kopiert den Knoten einschließlich der zugehörigen Daten.|Kopiert den Knoten einschließlich der zugehörigen Daten.|  
|XmlDeclaration|Kopiert den Ziel- und Datenwert des importierten Knotens.|Kopiert den Ziel- und Datenwert des importierten Knotens.|  
|Alle anderen Knotentypen.|Diese Knotentypen können nicht importiert werden.|Diese Knotentypen können nicht importiert werden.|  
  
> [!NOTE]
> Obwohl DocumentType-Knoten importiert werden können, kann ein Dokument nur einen DocumentType aufweisen. Sobald Sie also den Dokumenttyp importiert haben, müssen Sie vor dem Einsetzen in die Struktur sicherstellen, dass sich in dem Dokument kein anderer Dokumenttyp befindet. Informationen zum Entfernen von Knoten finden Sie unter [Entfernen von Knoten, Inhalten und Werten aus einem XML-Dokument](removing-nodes-content-and-values-from-an-xml-document.md).  
  
## <a name="see-also"></a>Siehe auch

- [XML-Dokumentobjektmodell (DOM)](xml-document-object-model-dom.md)
