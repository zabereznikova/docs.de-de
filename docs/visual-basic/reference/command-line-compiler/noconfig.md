---
title: "/noconfig | Microsoft Docs"
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
  - "noconfig compiler option [Visual Basic]"
  - "-noconfig compiler option [Visual Basic]"
  - "/noconfig compiler option [Visual Basic]"
ms.assetid: a7405067-bd21-4171-adf4-a126fa3ad6c3
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 15
---
# /noconfig
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Gibt an, dass der Compiler nicht automatisch auf die im Allgemeinen verwendeten [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)]\-Assemblys verweisen oder den `System`\-Namespace und den `Microsoft.VisualBasic`\-Namespace importieren soll.  
  
## Syntax  
  
```  
/noconfig  
```  
  
## Hinweise  
 Durch die Option `/noconfig` wird der Compiler angewiesen, die Kompilierung nicht unter Verwendung der Datei Vbc.rsp auszuführen, die sich im selben Verzeichnis wie die Datei Vbc.exe befindet.  Die Datei Vbc.rsp verweist auf die im Allgemeinen verwendeten [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)]\-Assemblys und importiert den `System`\-Namespace und den `Microsoft.VisualBasic`\-Namespace.  Der Compiler verweist implizit auf die Assembly System.dll, es sei denn, die Option `/nostdlib` wird angegeben.  Die Option `/nostdlib` bewirkt, dass der Compiler nicht mit Vbc.rsp kompiliert oder automatisch auf die Assembly System.dll verweist.  
  
> [!NOTE]
>  Auf die Assembly Mscorlib.dll und auf die Assembly Microsoft.VisualBasic.dll wird immer verwiesen.  
  
 Sie können die Datei Vbc.rsp bearbeiten, sodass sie zusätzliche Compileroptionen angibt, die in jeder Vbc.exe\-Kompilierung enthalten sein sollen \(außer bei Angabe der `/noconfig`\-Option\).  Weitere Informationen finden Sie unter [@ \(Specify Response File\)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md).  
  
 Der Compiler verarbeitet die an den `vbc`\-Befehl übergebenen Optionen zuletzt.  Daher wird jede in der Datei Vbc.rsp festgelegte Optionseinstellung durch die entsprechende in der Befehlszeile angegebene Option überschrieben.  
  
> [!NOTE]
>  Die `/noconfig`\-Option ist innerhalb der Entwicklungsumgebung von Visual Studio nicht verfügbar, sondern nur bei der Kompilierung über die Befehlszeile.  
  
## Siehe auch  
 [\/nostdlib](../../../visual-basic/reference/command-line-compiler/nostdlib.md)   
 [Visual Basic Command\-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [@ \(Specify Response File\)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md)   
 [\/reference](../../../visual-basic/reference/command-line-compiler/reference.md)