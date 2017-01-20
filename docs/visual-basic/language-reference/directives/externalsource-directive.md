---
title: "#ExternalSource Directive | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "#Externalsource"
  - "#ExternalSource"
  - "vb.ExternalSource"
  - "Externalsource"
  - "vb.#ExternalSource"
  - "ExternalSource"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "ExternalSource directive (#ExternalSource)"
  - "#ExternalSource directive"
ms.assetid: 243bc6a2-34c3-4eeb-a776-9fd2bf988149
caps.latest.revision: 160
caps.handback.revision: 160
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# #ExternalSource Directive
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Gibt eine Zuordnung von bestimmten Quellcodezeilen zu externem Text an.  
  
## Syntax  
  
```  
#ExternalSource( StringLiteral , IntLiteral )  
    [ LogicalLine+ ]  
#End ExternalSource  
```  
  
## Teile  
 `StringLiteral`  
 Der Pfad für die externe Quelle.  
  
 `IntLiteral`  
 Die Zeilennummer der ersten Zeile der externen Quelle.  
  
 `LogicalLine`  
 Die Zeile, in der der Fehler in der externen Quelle auftritt.  
  
 `#End ExternalSource`  
 Beendet den `#ExternalSource`\-Block.  
  
## Hinweise  
 Diese Direktive wird nur vom Compiler und vom Debugger verwendet.  
  
 Eine Quelldatei kann Direktiven für externe Quellen enthalten. Diese geben eine Zuordnung zwischen bestimmten Codezeilen in der Quelldatei und externem Text an, z. B. einer ASPX\-Datei.  Treten während der Kompilierung Fehler im angegebenen Quellcode auf, gelten diese als aus der externen Quelle stammend.  
  
 Direktiven für externen Code haben keinerlei Auswirkungen auf die Kompilierung und können nicht geschachtelt werden.  Sie sind lediglich für die interne Verwendung der Anwendung bestimmt.  
  
## Siehe auch  
 [Conditional Compilation](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)