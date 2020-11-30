---
title: Hierarchie im XML-Dokumentobjektmodell (DOM)
ms.date: 03/30/2017
ms.assetid: 9d187d4f-c76e-4223-a670-cc290783ce47
ms.openlocfilehash: 24ef51a18392fe3034e64bd585d879941fca4b95
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95718357"
---
# <a name="xml-document-object-model-dom-hierarchy"></a>Hierarchie im XML-Dokumentobjektmodell (DOM)

In der folgenden Abbildung wird die Klassenhierarchie für das XML-Document Object Model (DOM – Dokumentobjektmodell) veranschaulicht; dabei ist der W3C-Name (World Wide Web Consortium) an den relevanten Stellen zusammen mit dem Klassennamen angegeben.  
  
 ![Hierarchie im XML-Dokumentobjektmodell &#40;DOM&#41;](media/dom-class-hierarchy.gif "Dom_class_hierarchy")  
Hierarchie im XML-Dokumentobjektmodell (DOM)  
  
 Die folgenden Klassen erben nicht vom **XmlNode**:  
  
- **XmlImplementation**  
  
- **XmlNamedNodeMap**  
  
- **XmlNodeList**  
  
- **XmlNodeChangedEventArgs**  
  
 Die **XmlImplementation**-Klasse wird zum Erstellen eines XML-Dokuments verwendet. Weitere Informationen finden Sie unter [Erstellen eines XML-Dokuments](xml-document-creation.md).  
  
 Die **XmlNamedNodeMap**-Klasse behandelt eine ungeordnete Knotengruppe. Weitere Informationen finden Sie unter [Abrufen von ungeordneten Knoten anhand des Namens oder Indexes](unordered-node-retrieval-by-name-or-index.md).  
  
 Die **XmlNodeList**-Klasse behandelt eine geordnete Knotenliste. Weitere Informationen finden Sie unter [Abrufen von geordneten Knoten anhand des Indexes](ordered-node-retrieval-by-index.md).  
  
 Die **XmlNodeChangedEventArgs**-Klasse behandelt Ereignishandler, die im **XmlDocument** registriert sind. Weitere Informationen finden Sie unter [Ereignisbehandlung in einem XML-Dokument mit „XmlNodeChangedEventArgs“](event-handling-in-an-xml-document-using-the-xmlnodechangedeventargs.md).  
  
 Die **XmlLinkedNode**-Klasse erbt vom **XmlNode**. Der Zweck besteht im Überschreiben zweier Methoden von **XmlNode**: die **PreviousSibling**-Methode und die **NextSibling**-Methode. Diese überschriebenen Methoden werden dann geerbt und von **XmlCharacterData**, **XmlDeclaration**, **XmlDocumentType**, **XmlElement**, **XmlEntityReference** und **XmlProcessingInstruction** verwendet. Dabei handelt es sich um Klassen, die vorherige und nächste gleichgeordnete Elemente aufweisen.  
  
## <a name="see-also"></a>Siehe auch

- [XML-Dokumentobjektmodell (DOM)](xml-document-object-model-dom.md)
