---
title: Kopieren bestehender Knoten aus einem Dokument in ein anderes
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3caa78c1-3448-4b7b-b83c-228ee857635e
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 0f20e5bd595c8eb49360e58f281a8cf6eda89acf
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="copying-existing-nodes-from-one-document-to-another"></a>Kopieren bestehender Knoten aus einem Dokument in ein anderes
Die **ImportNode** Methode ist der Mechanismus, mit dem einen Knoten oder einer ganzen Knotenteilstruktur von einem Knotenteilstruktur **XmlDocument** in eine andere. Der Knoten, der von dem Aufruf zurückgegeben wird, ist eine Kopie des Knotens aus dem Quelldokument, einschließlich Attributwerten, Knotennamen, Knotentyp und allen namespacebezogenen Attributen wie Präfix, lokaler Name und Namespace-URI (Uniform Resource Identifier). Das Quelldokument bleibt dabei unverändert. Nachdem Sie den Knoten importiert haben, müssen Sie ihn noch der Struktur hinzufügen, indem Sie eine der Methoden zum Einfügen von Knoten verwenden.  
  
 Sobald der Knoten an das neue Dokument angehängt worden ist, ist das neue Dokument Eigentümer des Knotens. Grund hierfür ist, dass jeder Knoten, wenn er erstellt wird, zu einem Dokument gehört, das sein Eigentümer ist. Dies ist auch der Fall, wenn die Knoten in unterschiedlichen Dokumentfragmenten erstellt werden. Dies ist eine Voraussetzung für die XML-(DOKUMENTOBJEKTMODELL) und durch den Factoryerstellungsentwurf erzwungen werden, auf die **XmlDocument** Klasse. Beispielsweise **CreateElement**, ist die einzige Möglichkeit zum Erstellen neuer Knoten.  
  
 Abhängig vom Knotentyp des importierten Knotens und der Wert von der *Tiefe* Parameter, zusätzliche Informationen kopiert. Diese Methode gibt das Verhalten wieder, das erwartet würde, wenn ein Fragment eines XML- oder HTML-Quellcodes aus einem Dokument in ein anderes kopiert würde, und berücksichtigt die Tatsache, dass bei XML die beiden Dokumente unterschiedliche DTDs (Document Type Definitions) aufweisen können.  
  
 In der folgenden Tabelle wird das spezielle Verhalten für jeden Knotentyp veranschaulicht, der importiert werden kann.  
  
|Knotentyp|*Umfassende* Parameter ist "true"|*Umfassende* Parameter ist "false"|  
|---------------|------------------------------|-------------------------------|  
|XmlAttribute|Die <xref:System.Xml.XmlAttribute.Specified%2A> festgelegt ist, um **"true"** XmlAttribute. Die Nachfolger der Quelle **XmlAttribute** werden rekursiv importiert und die daraus resultierenden Knoten werden neu assembliert bilden die entsprechende Teilstruktur.|Die *Tiefe* Parameter gilt nicht für **XmlAttribute** Knoten, da sie deren untergeordnete Knoten beim Importieren stets ausführen.|  
|XmlCDataSection|Kopiert den Knoten einschließlich der zugehörigen Daten.|Kopiert den Knoten einschließlich der zugehörigen Daten.|  
|XmlComment|Kopiert den Knoten einschließlich der zugehörigen Daten.|Kopiert den Knoten einschließlich der zugehörigen Daten.|  
|XmlDocumentFragment|Die untergeordneten Elemente des Quellknotens werden rekursiv importiert. Die daraus resultierenden Knoten werden neu assembliert und bilden die entsprechende Teilstruktur.|Ein leeres **XmlDocumentFragment** wird erstellt.|  
|XmlDocumentType|Kopiert den Knoten einschließlich der zugehörigen Daten.*|Kopiert den Knoten einschließlich der zugehörigen Daten.*|  
|XmlElement|Die untergeordneten Elemente des Quellelements werden rekursiv importiert. Die daraus resultierenden Knoten werden neu assembliert und bilden die entsprechende Teilstruktur. **Hinweis:** Standardattribute werden nicht kopiert. Wenn das Dokument, in das importiert wird, Standardattribute für diesen Elementnamen definiert, werden diese zugewiesen.|Angegebene Attribut Knoten des Quellelements werden importiert, und die generierten **XmlAttribute** Knoten an das neue Element angefügt sind. Die untergeordneten Knoten werden nicht kopiert. **Hinweis:** Standardattribute werden nicht kopiert. Wenn das Dokument, in das importiert wird, Standardattribute für diesen Elementnamen definiert, werden diese zugewiesen.|  
|XmlEntityReference|Da die Quell- und Zieldokument die Entitäten, die unterschiedlich definiert sein können, kopiert diese Methode nur den **XmlEntityReference** Knoten. Der Ersetzungstext ist davon nicht betroffen. Wenn die Entität des Zieldokuments definiert ist, wird deren Wert zugewiesen.|Da die Quell- und Zieldokument die Entitäten, die unterschiedlich definiert sein können, kopiert diese Methode nur den **XmlEntityReference** Knoten. Der Ersetzungstext ist davon nicht betroffen. Wenn die Entität des Zieldokuments definiert ist, wird deren Wert zugewiesen.|  
|XmlProcessingInstruction|Kopiert den Ziel- und Datenwert des importierten Knotens.|Kopiert den Ziel- und Datenwert des importierten Knotens.|  
|XmlText|Kopiert den Knoten einschließlich der zugehörigen Daten.|Kopiert den Knoten einschließlich der zugehörigen Daten.|  
|XmlSignificantWhitespace|Kopiert den Knoten einschließlich der zugehörigen Daten.|Kopiert den Knoten einschließlich der zugehörigen Daten.|  
|XmlWhitespace|Kopiert den Knoten einschließlich der zugehörigen Daten.|Kopiert den Knoten einschließlich der zugehörigen Daten.|  
|XmlDeclaration|Kopiert den Ziel- und Datenwert des importierten Knotens.|Kopiert den Ziel- und Datenwert des importierten Knotens.|  
|Alle anderen Knotentypen.|Diese Knotentypen können nicht importiert werden.|Diese Knotentypen können nicht importiert werden.|  
  
> [!NOTE]
>  Obwohl DocumentType-Knoten importiert werden können, kann ein Dokument nur einen DocumentType aufweisen. Sobald Sie also den Dokumenttyp importiert haben, müssen Sie vor dem Einsetzen in die Struktur sicherstellen, dass sich in dem Dokument kein anderer Dokumenttyp befindet. Informationen zum Entfernen von Knoten finden Sie unter [Entfernen von Knoten, Inhalten und Werten aus einem XML-Dokument](../../../../docs/standard/data/xml/removing-nodes-content-and-values-from-an-xml-document.md).  
  
## <a name="see-also"></a>Siehe auch  
 [XML-Dokumentobjektmodell (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
