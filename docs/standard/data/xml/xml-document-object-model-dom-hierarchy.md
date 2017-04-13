---
title: "Hierarchie im XML-Dokumentobjektmodell (DOM) | Microsoft Docs"
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
ms.assetid: 9d187d4f-c76e-4223-a670-cc290783ce47
caps.latest.revision: 3
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 3
---
# Hierarchie im XML-Dokumentobjektmodell (DOM)
In der folgenden Abbildung wird die Klassenhierarchie für das XML\-Document Object Model \(DOM – Dokumentobjektmodell\) veranschaulicht; dabei ist der W3C\-Name \(World Wide Web Consortium\) an den relevanten Stellen zusammen mit dem Klassennamen angegeben.  
  
 ![Hierarchie im XML&#45;Dokumentobjektmodell &#40;DOM&#41;](../../../../docs/standard/data/xml/media/dom-class-hierarchy.gif "Dom\_class\_hierarchy")  
Hierarchie im XML\-Dokumentobjektmodell \(DOM\)  
  
 Die folgenden Klassen erben nicht vom **XmlNode**:  
  
-   **XmlImplementation**  
  
-   **XmlNamedNodeMap**  
  
-   **XmlNodeList**  
  
-   **XmlNodeChangedEventArgs**  
  
 Die **XmlImplementation**\-Klasse wird zum Erstellen eines XML\-Dokuments verwendet.  Weitere Informationen finden Sie unter [Erstellen eines XML\-Dokuments](../../../../docs/standard/data/xml/xml-document-creation.md).  
  
 Die **XmlNamedNodeMap**\-Klasse behandelt eine ungeordnete Knotengruppe.  Weitere Informationen finden Sie unter [Abrufen von ungeordneten Knoten anhand des Namens oder Indexes](../../../../docs/standard/data/xml/unordered-node-retrieval-by-name-or-index.md).  
  
 Die **XmlNodeList**\-Klasse behandelt eine geordnete Knotengruppe.  Weitere Informationen finden Sie unter [Abrufen von geordneten Knoten anhand des Indexes](../../../../docs/standard/data/xml/ordered-node-retrieval-by-index.md).  
  
 Die **XmlNodeChangedEventArgs**\-Klasse behandelt Ereignishandler, die im **XmlDocument** registriert sind.  Weitere Informationen finden Sie unter [Ereignisbehandlung in einem XML\-Dokument mit "XmlNodeChangedEventArgs"](../../../../docs/standard/data/xml/event-handling-in-an-xml-document-using-the-xmlnodechangedeventargs.md).  
  
 Die **XmlLinkedNode**\-Klasse erbt vom **XmlNode**.  Der Zweck besteht im Überschreiben zweier Methoden von **XmlNode**: die **PreviousSibling**\-Methode und die **NextSibling**\-Methode.  Diese überschriebenen Methoden werden dann geerbt und von **XmlCharacterData**, **XmlDeclaration**, **XmlDocumentType**, **XmlElement**, **XmlEntityReference** und **XmlProcessingInstruction** verwendet. Dabei handelt es sich um Klassen, die vorherige und nächste gleichgeordnete Klassen aufweisen.  
  
## Siehe auch  
 [XML\-Dokumentobjektmodell \(DOM\)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)