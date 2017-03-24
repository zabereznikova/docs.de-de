---
title: "XML entity references are not supported | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc31180"
  - "bc31180"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC31180"
ms.assetid: 2a393327-d8e2-4187-85b1-642b4f53b4ae
caps.latest.revision: 6
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 6
---
# XML entity references are not supported
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Ein in der XML 1.0\-Spezifikation nicht definierter Entitätsverweis \(z. B. `©`\) ist als Wert für ein XML\-Literal enthalten.  Nur die XML\-Entitätsverweise `&`, `"`, `<`, `>` und `'` werden in XML\-Literalen unterstützt.  
  
 **Fehler\-ID:** BC31180  
  
### So beheben Sie diesen Fehler  
  
-   Entfernen Sie den nicht unterstützten Entitätsverweis.  
  
## Siehe auch  
 [XML Literals and the XML 1.0 Specification](../../../visual-basic/programming-guide/language-features/xml/xml-literals-and-the-xml-1-0-specification.md)   
 [XML Literals](../../../visual-basic/language-reference/xml-literals/index.md)   
 [XML](../../../visual-basic/programming-guide/language-features/xml/index.md)