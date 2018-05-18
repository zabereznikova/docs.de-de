---
title: In ein Dokument eingebettete Stylesheetanweisungen
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: d79fb295-ebc7-438d-ba1b-05be7d534834
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2fa671304c611db571b160cd1d960b83bf451c9a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="style-sheet-directives-embedded-in-a-document"></a>In ein Dokument eingebettete Stylesheetanweisungen
Gelegentlich enthält vorhandener XML-Code die Stylesheetdirektive `<?xml:stylesheet?>`. Microsoft Internet Explorer akzeptiert diese als Alternative zur `<?xml-stylesheet?>`-Syntax. Wenn die XML-Daten, wie im Folgenden dargestellt, eine `<?xml:stylesheet?>`-Direktive enthalten, wird durch den Versuch, diese Daten in das Dokumentobjektmodell (DOM) zu laden, eine Ausnahme ausgelöst.  
  
```xml  
<?xml version="1.0" ?>  
<?xml:stylesheet type="text/xsl" href="test2.xsl"?>  
<root>  
    <test>Node 1</test>  
    <test>Node 2</test>  
</root>  
```  
  
 Der Grund hierfür ist, dass `<?xml:stylesheet?>` als ungültige **ProcessingInstruction** für das DOM gilt. Bei einer **ProcessingInstruction** kann es sich, gemäß der Spezifikation „Namespaces in XML“, nur um Namen ohne Doppelpunkt (NCNames) handeln, und nicht um qualifizierte Namen (QNames).  
  
 Aus Abschnitt 6 der Spezifikation „Namespaces in XML“ ergibt sich Folgendes: Wenn die **Load**-Methode und die **LoadXml**-Methode entsprechend der Spezifikation verwendet werden, hat dies in einem Dokument folgende Auswirkungen:  
  
-   Alle Elementtypen und Attributnamen enthalten entweder keinen oder einen Doppelpunkt.  
  
-   In Entitätsnamen, "ProcessingInstruction"-Zielen oder Notationsnamen ist kein Doppelpunkt enthalten.  
  
 Da `<?xml:stylesheet?>` einen Doppelpunkt enthält, verstößt der Name gegen die zweite der obigen Regeln.  
  
 Gemäß der W3C-Empfehlung "Associating Style Sheets with XML documents Version 1.0" (unter www.w3.org/TR/xml-stylesheet zu finden), lautet die Verarbeitungsanweisung zum Verknüpfen eines XSL-Stylesheets mit einem XML-Dokument `<?xml-stylesheet?>`, d. h., der Doppelpunkt wird durch einen Bindestrich ersetzt.  
  
## <a name="see-also"></a>Siehe auch  
 [XML-Dokumentobjektmodell (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
