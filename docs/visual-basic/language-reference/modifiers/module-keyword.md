---
title: "Module &lt;keyword&gt; (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.ModuleAttribute"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Module keyword"
  - "Module modifier"
  - "attribute blocks, Module keyword"
ms.assetid: d971b940-05ab-4d56-8485-e3b8a661906b
caps.latest.revision: 13
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 13
---
# Module &lt;keyword&gt; (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Gibt an, dass ein Attribut am Anfang einer Quelldatei für die aktuelle Assembly gilt.  
  
## Hinweise  
 Viele Attribute betreffen ein einzelnes Programmierelement, z. B. eine Klasse oder eine Eigenschaft.  Ein solches Attribut wird angewendet, indem der Attributblock innerhalb spitzer Klammern \(`< >`\) direkt an die Deklarationsanweisung angehängt wird.  
  
 Wenn ein Attribut nicht nur das folgende Element, sondern das aktuelle Assemblymodul betrifft, stellen Sie den Attributblock an den Anfang der Quelldatei und kennzeichnen das Attribut mit dem `Module`\-Schlüsselwort.  Wenn es für die ganze Assembly gilt, verwenden Sie das [Assembly](../../../visual-basic/language-reference/modifiers/assembly.md)\-Schlüsselwort.  
  
 Der `Module`\-Modifizierer ist nicht mit der gleichnamigen [Module Statement](../../../visual-basic/language-reference/statements/module-statement.md) identisch.  
  
## Siehe auch  
 [Assembly](../../../visual-basic/language-reference/modifiers/assembly.md)   
 [Module Statement](../../../visual-basic/language-reference/statements/module-statement.md)   
 [Attribute](../Topic/Attributes%20\(C%23%20and%20Visual%20Basic\).md)