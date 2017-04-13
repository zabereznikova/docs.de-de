---
title: "Entfernen von Knoteninhalt im Dokumentobjektmodell | Microsoft Docs"
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
ms.assetid: 615d81a7-f44f-416c-a9ab-bfe03f85e6e4
caps.latest.revision: 3
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 3
---
# Entfernen von Knoteninhalt im Dokumentobjektmodell
Bei Knotentypen, die von <xref:System.Xml.XmlCharacterData> erben \(die Knotentypen <xref:System.Xml.XmlComment>, <xref:System.Xml.XmlText>, <xref:System.Xml.XmlCDataSection>, <xref:System.Xml.XmlWhitespace> und <xref:System.Xml.XmlSignificantWhitespace>\), können Sie Zeichen mithilfe der <xref:System.Xml.XmlCharacterData.DeleteData%2A>\-Methode entfernen. Diese löscht einen Bereich von Zeichen aus dem Knoten.  Wenn Sie Inhalte vollständig löschen möchten, entfernen Sie den Knoten, in dem der betreffende Inhalt vorliegt.  Wenn der Knoten erhalten bleiben soll, der Inhalt jedoch falsch ist, dann ändern Sie den Inhalt.  Weitere Informationen zum Ändern des Inhalts eines Knotens finden Sie unter [Ändern von Knoten, Inhalten und Werten in einem XML\-Dokument](../../../../docs/standard/data/xml/modifying-nodes-content-and-values-in-an-xml-document.md).  
  
## Siehe auch  
 [XML\-Dokumentobjektmodell \(DOM\)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)