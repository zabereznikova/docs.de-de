---
title: "/nostdlib (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "nostdlib compiler option [Visual Basic]"
  - "-nostdlib compiler option [Visual Basic]"
  - "/nostdlib compiler option [Visual Basic]"
ms.assetid: 140381b8-dc96-4ad5-ae11-792c9ed0be4d
caps.latest.revision: 18
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 18
---
# /nostdlib (Visual Basic)
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Bewirkt, dass der Compiler nicht automatisch auf die Standardbibliotheken verweist.  
  
## Syntax  
  
```  
/nostdlib  
```  
  
## Hinweise  
 Die Option `/nostdlib` entfernt den automatischen Verweis auf die Assembly System.dll und verhindert, dass der Compiler die Datei Vbc.rsp liest.  Die Datei Vbc.rsp \(befindet sich im selben Verzeichnis wie die Datei Vbc.exe\) verweist auf die häufig verwendeten [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]\-Assemblys und importiert den `System`\-Namespace und den `Microsoft.VisualBasic`\-Namespace.  
  
> [!NOTE]
>  Auf die Assembly Mscorlib.dll und auf die Assembly Microsoft.VisualBasic.dll wird immer verwiesen.  
  
> [!NOTE]
>  Die Option `/nostdlib` ist nicht innerhalb der Entwicklungsumgebung von Visual Studio verfügbar, sondern nur bei der Kompilierung über die Befehlszeile.  
  
## Beispiel  
 Im folgenden Code wird `T2.vb` kompiliert, ohne auf die Standardbibliotheken zu verweisen.  Sie müssen die Konstante für bedingte Kompilierung `_MYTYPE` auf die Zeichenfolge "Empty" festlegen, um das `My`\-Objekt zu entfernen.  
  
```  
vbc /nostdlib /define:_MYTYPE=\"Empty\" T2.vb  
```  
  
## Siehe auch  
 [\/noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md)   
 [Visual Basic Command\-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [Customizing Which Objects are Available in My](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)