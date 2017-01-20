---
title: "@ (C# Compiler Options) | Microsoft Docs"
ms.custom: ""
ms.date: "01/05/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "@"
dev_langs: 
  - "CSharp"
  - "CSharp"
helpviewer_keywords: 
  - "response files, specifying for compilation [C#]"
  - "@ compiler option"
ms.assetid: dda4fa9f-a02c-400f-8b6a-d58834e13d7f
caps.latest.revision: 9
caps.handback.revision: 9
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# @ (C# Compiler Options)
Die Option @ gibt eine Datei an, die Compileroptionen und zu kompilierende Quellcodedateien enthält.  
  
## Syntax  
  
```  
@response_file  
```  
  
## Argumente  
 `response_file`  
 Eine Datei, in der Compileroptionen oder zu kompilierende Quellcodedateien aufgelistet werden.  
  
## Hinweise  
 Der Compiler verarbeitet diese Compileroptionen und Quellcodedateien, als ob sie in der Befehlszeile eingegeben worden wären.  
  
 Wenn Sie mehrere Antwortdateien für eine Kompilierung benötigen, geben Sie mehrere Antwortdateioptionen an.  Beispiel:  
  
```  
@file1.rsp @file2.rsp  
```  
  
 In einer Antwortdatei können mehrere Compileroptionen und Quellcodedateien in einer Zeile stehen.  Eine einzelne Compileroption muss in einer Zeile stehen, d. h., sie darf sich nicht über mehrere Zeilen erstrecken.  Antwortdateien können Kommentare enthalten, die mit dem Symbol \# beginnen.  
  
 Das Angeben von Compileroptionen von einer Antwortdatei aus entspricht dem Ausgeben dieser Befehle über die Befehlszeile.  Weitere Informationen finden Sie unter [Erstellen von der Befehlszeile aus](../../../csharp/language-reference/compiler-options/how-to-set-environment-variables-for-the-visual-studio-command-line.md).  
  
 Der Compiler verarbeitet die Befehlsoptionen in der Reihenfolge ihres Auftretens.  Daher können Befehlszeilenargumente vorher aufgelistete Optionen in Antwortdateien überschreiben.  Umgekehrt überschreiben Optionen in einer Antwortdatei Optionen, die vorher in der Befehlszeile oder in anderen Antwortdateien aufgelistet wurden.  
  
 C\# stellt die Datei **csc.rsp** bereit, die sich im selben Verzeichnis wie die Datei **csc.exe** befindet.  Weitere Informationen über die Datei **csc.rsp** finden Sie unter[\/noconfig](../../../csharp/language-reference/compiler-options/noconfig-compiler-option.md).  
  
 Diese Compileroption kann weder in der Entwicklungsumgebung von Visual Studio eingestellt noch programmgesteuert geändert werden.  
  
## Beispiel  
 Die folgenden Zeilen sind einer Beispielantwortdatei entnommen:  
  
```  
# build the first output file  
/target:exe /out:MyExe.exe source1.cs source2.cs  
```  
  
## Siehe auch  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)