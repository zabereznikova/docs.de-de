---
title: "#Region Directive | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Region"
  - "vb.#Region"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Visual Basic compiler, compiler directives"
  - "#region directive"
  - "region directive (#region)"
  - "#Region keyword"
ms.assetid: 90a6a104-3cbf-47d0-bdc4-b585d0921b87
caps.latest.revision: 14
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 14
---
# #Region Directive
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Reduziert Codeabschnitte in Visual Basic\-Dateien und blendet sie aus.  
  
## Syntax  
  
```  
  
        #Region "identifier_string"  
#End Region  
```  
  
## Teile  
  
|||  
|-|-|  
|Begriff|Definition|  
|`identifier_string`|Erforderlich.  Eine Zeichenfolge, die als Bereichtitel fungiert, wenn sie reduziert ist.  Bereiche werden standardmäßig reduziert.|  
|`#End Region`|Beendet den `#Region`\-Block.|  
  
## Hinweise  
 Mit der `#Region`\-Direktive können Sie einen Codeblock festlegen, der bei Verwendung der Gliederungsfunktion des Code\-Editors von Visual Studio erweitert oder reduziert werden soll.  Sie können Bereiche innerhalb von anderen Bereichen platzieren, oder *schachteln*, damit ähnliche Bereiche zusammen gruppiert sind.  
  
## Beispiel  
 Dieses Beispiel verwendet die `#Region`\-Direktive.  
  
 [!code-vb[VbVbalrConditionalComp#4](../../../visual-basic/language-reference/directives/codesnippet/VisualBasic/region-directive_1.vb)]  
  
## Siehe auch  
 [\#If...Then...\#Else Directives](../../../visual-basic/language-reference/directives/if-then-else-directives.md)   
 [Gliedern](/visual-studio/ide/outlining)   
 [How to: Collapse and Hide Sections of Code](../../../visual-basic/programming-guide/program-structure/how-to-collapse-and-hide-sections-of-code.md)