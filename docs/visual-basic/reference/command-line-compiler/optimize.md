---
title: "/optimize | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "optimize compiler option [Visual Basic]"
  - "/optimize compiler option [Visual Basic]"
  - "optimization, enabling"
  - "-optimize compiler option [Visual Basic]"
ms.assetid: fcba4a97-3622-4b87-a891-0f77deab4998
caps.latest.revision: 15
caps.handback.revision: 15
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# /optimize
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Aktiviert oder deaktiviert Compileroptimierungen.  
  
## Syntax  
  
```  
/optimize[ + | - ]  
```  
  
## Argumente  
  
|||  
|-|-|  
|Begriff|Definition|  
|`+`  &#124; `-`|Optional.  Die `/optimize-`\-Option deaktiviert Compileroptimierungen.  Die `/optimize+`\-Option aktiviert Optimierungen.  Standardmäßig sind Optimierungen deaktiviert.|  
  
## Hinweise  
 Compileroptimierungen bewirken eine kleinere, schnellere und effizientere Ausgabedatei.  Da sie den Code in der Ausgabedatei jedoch neu anordnen, wird das Debuggen durch `/optimize+` möglicherweise erschwert.  
  
 Alle mit `/target:module` für eine Assembly generierten Module müssen die gleichen `/optimize`\-Einstellungen wie die Assembly verwenden.  Weitere Informationen finden Sie unter [\/target](../../../visual-basic/reference/command-line-compiler/target.md).  
  
 Die `/optimize`\-Option kann mit der `/debug`\-Option kombiniert werden.  
  
||  
|-|  
|So legen Sie \/optimize in der integrierten Entwicklungsumgebung von Visual Studio fest|  
|1.  Wählen Sie im **Projektmappen\-Explorer** ein Projekt aus.  Klicken Sie im Menü **Projekt** auf **Eigenschaften**.<br />     Weitere Informationen finden Sie unter [Introduction to the Project Designer](http://msdn.microsoft.com/de-de/898dd854-c98d-430c-ba1b-a913ce3c73d7).<br />2.  Klicken Sie auf die Registerkarte **Kompilieren**.<br />3.  Klicken Sie auf die Schaltfläche **Erweitert**.<br />4.  Ändern Sie das Kontrollkästchen **Optimierungen aktivieren**.|  
  
## Beispiel  
 Mit dem folgenden Code wird `T2.vb` kompiliert, und Compileroptimierungen werden aktiviert.  
  
```  
vbc t2.vb /optimize  
```  
  
## Siehe auch  
 [Visual Basic Command\-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [\/debug](../../../visual-basic/reference/command-line-compiler/debug.md)   
 [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [\/target](../../../visual-basic/reference/command-line-compiler/target.md)