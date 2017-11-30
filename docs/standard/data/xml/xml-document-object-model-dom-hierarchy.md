---
title: Hierarchie im XML-Dokumentobjektmodell (DOM)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9d187d4f-c76e-4223-a670-cc290783ce47
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 6dec61860fba5815b1dae802d280e8df6628ab91
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="xml-document-object-model-dom-hierarchy"></a>Hierarchie im XML-Dokumentobjektmodell (DOM)
In der folgenden Abbildung wird die Klassenhierarchie für das XML-Document Object Model (DOM – Dokumentobjektmodell) veranschaulicht; dabei ist der W3C-Name (World Wide Web Consortium) an den relevanten Stellen zusammen mit dem Klassennamen angegeben.  
  
 ![XML-Dokumentobjektmodell &#40; DOM &#41; Hierarchie](../../../../docs/standard/data/xml/media/dom-class-hierarchy.gif "Dom_class_hierarchy")  
Hierarchie im XML-Dokumentobjektmodell (DOM)  
  
 Die folgenden Klassen erben nicht von der **XmlNode**:  
  
-   **XmlImplementation**  
  
-   **XmlNamedNodeMap**  
  
-   **XmlNodeList**  
  
-   **"XmlNodeChangedEventArgs"**  
  
 Die **XmlImplementation** Klasse wird verwendet, um ein XML-Dokument zu erstellen. Weitere Informationen finden Sie unter [Erstellen eines XML-Dokuments](../../../../docs/standard/data/xml/xml-document-creation.md).  
  
 Die **XmlNamedNodeMap** -Klasse behandelt eine ungeordnete Gruppe von Knoten. Weitere Informationen finden Sie unter [Abrufen von ungeordneten Knoten anhand des Namens oder Indexes](../../../../docs/standard/data/xml/unordered-node-retrieval-by-name-or-index.md).  
  
 Die **XmlNodeList** -Klasse behandelt eine geordnete Liste von Knoten. Weitere Informationen finden Sie unter [Abrufen von geordneten Knoten über einen Index](../../../../docs/standard/data/xml/ordered-node-retrieval-by-index.md).  
  
 Die **"XmlNodeChangedEventArgs"** -Klasse behandelt Ereignishandler registriert, auf die **XmlDocument**. Weitere Informationen finden Sie unter [Ereignisbehandlung in einem XML-Dokument mit "XmlNodeChangedEventArgs"](../../../../docs/standard/data/xml/event-handling-in-an-xml-document-using-the-xmlnodechangedeventargs.md).  
  
 Die **XmlLinkedNode** Klasse erbt von **XmlNode**. Ihr Zweck besteht im Überschreiben zweier Methoden von **XmlNode**: die **PreviousSibling** und **NextSibling** Methoden. Diese überschriebenen Methoden werden dann geerbt und von verwendet **XmlCharacterData**, **XmlDeclaration**, **XmlDocumentType**, **XmlElement**, **XmlEntityReference**, und **XmlProcessingInstruction**, wobei es sich um Klassen, die vorherige und nächste gleichgeordnete.  
  
## <a name="see-also"></a>Siehe auch  
 [XML-Dokumentobjektmodell (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
