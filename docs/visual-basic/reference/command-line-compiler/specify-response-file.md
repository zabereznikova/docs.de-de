---
title: "@ (Specify Response File) (Visual Basic) | Microsoft Docs"
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
  - "@ (Specify Response File) compiler option [Visual Basic]"
ms.assetid: a6847eaa-e5f9-4303-9421-45b55484b9ca
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 15
---
# @ (Specify Response File) (Visual Basic)
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Gibt eine Datei an, die Compileroptionen und zu kompilierende Quellcodedateien enthält.  
  
## Syntax  
  
```  
@response_file  
```  
  
## Argumente  
 `response_file`  
 Erforderlich.  Eine Datei, in der Compileroptionen oder zu kompilierende Quellcodedateien aufgeführt werden.  Schließen Sie den Dateinamen in Anführungszeichen \(" "\) ein, wenn der Name ein Leerzeichen enthält.  
  
## Hinweise  
 Der Compiler verarbeitet die angegebenen Compileroptionen und Quellcodedateien in einer Antwortdatei, als ob sie in der Befehlszeile eingegeben worden wären.  
  
 Wenn Sie mehrere Antwortdateien für eine Kompilierung benötigen, geben Sie mehrere Antwortdateioptionen an, beispielsweise folgende.  
  
```  
@file1.rsp @file2.rsp  
```  
  
 In einer Antwortdatei können mehrere Compileroptionen und Quellcodedateien in einer Zeile stehen.  Eine einzelne Compileroption muss in einer Zeile stehen, d. h., sie darf sich nicht über mehrere Zeilen erstrecken.  Antwortdateien können Kommentare enthalten, die mit dem Symbol `#` beginnen.  
  
 Sie können in die Befehlszeile eingegebene Optionen mit Optionen kombinieren, die in einer oder mehreren Antwortdateien angegeben wurden.  Der Compiler verarbeitet die Befehlsoptionen in der Reihenfolge ihres Auftretens.  Daher können Befehlszeilenargumente vorher aufgelistete Optionen in Antwortdateien überschreiben.  Umgekehrt überschreiben Optionen in einer Antwortdatei Optionen, die vorher in der Befehlszeile oder in anderen Antwortdateien angegeben wurden.  
  
 Visual Basic stellt die Datei Vbc.rsp bereit, die sich im selben Verzeichnis wie die Datei Vbc.exe befindet.  Die Datei Vbc.rsp ist standardmäßig vorhanden, es sei denn, die `/noconfig`\-Option wird verwendet.  Weitere Informationen finden Sie unter [\/noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md).  
  
> [!NOTE]
>  Die `@`\-Option ist innerhalb der Entwicklungsumgebung von Visual Studio nicht verfügbar, sondern nur bei der Kompilierung über die Befehlszeile.  
  
## Beispiel  
 Die folgenden Zeilen stammen aus einer Beispielantwortdatei.  
  
```  
# build the first output file  
/target:exe   
/out:MyExe.exe  
source1.vb   
source2.vb  
```  
  
## Beispiel  
 Im folgenden Beispiel wird gezeigt, wie die `@`\-Option mit der Antwortdatei mit dem Namen `File1.rsp` verwendet wird.  
  
```  
vbc @file1.rsp  
```  
  
## Siehe auch  
 [Visual Basic Command\-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [\/noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md)   
 [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)