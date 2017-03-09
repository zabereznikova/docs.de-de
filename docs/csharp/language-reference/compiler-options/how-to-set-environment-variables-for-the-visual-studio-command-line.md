---
title: "How to: Set Environment Variables for the Visual Studio Command Line | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "cs.build.commandline"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "csc.exe, command-line builds"
  - "Visual C#, command-line builds"
  - "command-line compilers, Visual C#"
  - "Vsvars32.bat"
  - "builds [C#], command-line"
  - "compilers, invoking from command line"
  - "Vcvars32.bat file"
  - "command line [C#], building from"
  - "Visual C# compiler, enabling"
  - "compiling source code, from command line"
ms.assetid: 7ec09480-5612-4f6a-8d00-ad90ea9bca5d
caps.latest.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 15
---
# How to: Set Environment Variables for the Visual Studio Command Line
Die Umgebungsvariablen, die für Befehlszeilenbuilds erforderlich sind, werden durch die Datei VSVARS32.BAT festgelegt.  Weitere Informationen über "vsvars32.bat" finden Sie im [Knowledge Base\-Artikel Q248802](http://go.microsoft.com/fwlink/?LinkId=225042).  
  
 Falls die aktuelle Version von Visual Studio auf einem Computer installiert ist, der zusätzlich über eine frühere Version von Visual Studio verfügt, sollten Sie die Dateien VSVARS32.BAT und VCVARS32.BAT nicht aus unterschiedlichen Versionen im selben Eingabeaufforderungsfenster ausführen.  
  
### So führen Sie VSVARS32.BAT aus  
  
1.  Öffnen Sie über das Menü **Start** die **Developer\-Eingabeaufforderung für VS2012**.  
  
2.  Wechseln Sie zu "Program Files\\Microsoft Visual Studio *Version*\\Common7\\Tools" oder zum Unterverzeichnis Ihrer Installation "Program Files \(x86\)\\Microsoft Visual Studio *Version*\\Common7\\Tools".  
  
3.  Führen Sie VSVARS32.BAT aus, indem Sie VSVARS32 eingeben.  
  
    > [!CAUTION]
    >  VSVARS32.BAT kann auf verschiedenen Computern unterschiedlich sein.  Falls die Datei VSVARS32.BAT nicht vorhanden oder beschädigt ist, sollten Sie sie nicht durch die VSVARS32.BAT\-Datei eines anderen Computers ersetzen.  Führen Sie stattdessen Setup erneut aus, um die fehlende Datei zu ersetzen.  
  
## Siehe auch  
 [Command\-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)