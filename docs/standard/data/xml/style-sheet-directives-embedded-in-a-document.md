---
title: "In ein Dokument eingebettete Stylesheetdirektiven | Microsoft Docs"
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
ms.assetid: d79fb295-ebc7-438d-ba1b-05be7d534834
caps.latest.revision: 4
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 4
---
# In ein Dokument eingebettete Stylesheetdirektiven
Gelegentlich enthält vorhandener XML\-Code die Stylesheetdirektive `<?xml:stylesheet?>`.  Microsoft Internet Explorer akzeptiert diese als Alternative zur `<?xml-stylesheet?>`\-Syntax.  Wenn die XML\-Daten, wie im Folgenden dargestellt, eine `<?xml:stylesheet?>`\-Direktive enthalten, wird durch den Versuch, diese Daten in das Dokumentobjektmodell \(DOM\) zu laden, eine Ausnahme ausgelöst.  
  
```  
<?xml version="1.0" ?>  
<?xml:stylesheet type="text/xsl" href="test2.xsl"?>  
<root>  
    <test>Node 1</test>  
    <test>Node 2</test>  
</root>  
```  
  
 Der Grund hierfür ist, dass `<?xml:stylesheet?>` als unzulässige **ProcessingInstruction** für das DOM gilt.  Bei einer **ProcessingInstruction** kann es sich, gemäß der Spezifikation "Namespaces in XML", nur um NCNames \(Namen ohne Doppelpunkt\) handeln, und nicht um QNames \(qualifizierte Namen\).  
  
 Aus Abschnitt 6 der Spezifikation "Namespaces in XML" ergibt sich Folgendes: Wenn die **Load**\-Methode und die **LoadXml**\-Methode entsprechend der Spezifikation verwendet werden, hat dies in einem Dokument folgende Auswirkungen:  
  
-   Alle Elementtypen und Attributnamen enthalten entweder keinen oder einen Doppelpunkt.  
  
-   In Entitätsnamen, "ProcessingInstruction"\-Zielen oder Notationsnamen ist kein Doppelpunkt enthalten.  
  
 Da `<?xml:stylesheet?>` einen Doppelpunkt enthält, verstößt der Name gegen die zweite der obigen Regeln.  
  
 Gemäß der W3C\-Empfehlung "Associating Style Sheets with XML documents Version 1.0" \(unter www.w3.org\/TR\/xml\-stylesheet zu finden\), lautet die Verarbeitungsanweisung zum Verknüpfen eines XSL\-Stylesheets mit einem XML\-Dokument `<?xml-stylesheet?>`, d. h., der Doppelpunkt wird durch einen Bindestrich ersetzt.  
  
## Siehe auch  
 [XML\-Dokumentobjektmodell \(DOM\)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)