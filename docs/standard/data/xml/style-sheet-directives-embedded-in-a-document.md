---
title: In ein Dokument eingebettete Stylesheetanweisungen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d79fb295-ebc7-438d-ba1b-05be7d534834
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 8c5cfcc9f35e4a07e9426a4dd24c1e2f04985f16
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="style-sheet-directives-embedded-in-a-document"></a>In ein Dokument eingebettete Stylesheetanweisungen
Gelegentlich enthält vorhandener XML-Code die Stylesheetdirektive `<?xml:stylesheet?>`. Microsoft Internet Explorer akzeptiert diese als Alternative zu den `<?xml-stylesheet?>` Syntax. Wenn die XML-Daten, wie im Folgenden dargestellt, eine `<?xml:stylesheet?>`-Direktive enthalten, wird durch den Versuch, diese Daten in das Dokumentobjektmodell (DOM) zu laden, eine Ausnahme ausgelöst.  
  
```xml  
<?xml version="1.0" ?>  
<?xml:stylesheet type="text/xsl" href="test2.xsl"?>  
<root>  
    <test>Node 1</test>  
    <test>Node 2</test>  
</root>  
```  
  
 Dies geschieht, weil die `<?xml:stylesheet?>` gilt eine ungültige **ProcessingInstruction** auf das DOM. Alle **ProcessingInstruction**, gemäß der Namespaces in XML-Spezifikation, ohne Doppelpunkt NCNames (Namen) ist nur möglich, und nicht qualifizierte Namen (QNames).  
  
 Aus Abschnitt 6 der Namespaces in XML-Spezifikation, den Effekt des Ausführens der **laden** und **LoadXml** Methoden entsprechen der Spezifikation verwendet werden, in einem Dokument:  
  
-   Alle Elementtypen und Attributnamen enthalten entweder keinen oder einen Doppelpunkt.  
  
-   In Entitätsnamen, "ProcessingInstruction"-Zielen oder Notationsnamen ist kein Doppelpunkt enthalten.  
  
 Da `<?xml:stylesheet?>` einen Doppelpunkt enthält, verstößt der Name gegen die zweite der obigen Regeln.  
  
 Gemäß der W3C-Empfehlung "Associating Style Sheets with XML documents Version 1.0" (unter www.w3.org/TR/xml-stylesheet zu finden), lautet die Verarbeitungsanweisung zum Verknüpfen eines XSL-Stylesheets mit einem XML-Dokument `<?xml-stylesheet?>`, d. h., der Doppelpunkt wird durch einen Bindestrich ersetzt.  
  
## <a name="see-also"></a>Siehe auch  
 [XML-Dokumentobjektmodell (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
