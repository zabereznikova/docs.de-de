---
title: "/pdb (C# Compiler Options) | Microsoft Docs"
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
  - "/pdb"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "-pdb compiler option [C#]"
  - "pdb compiler option [C#]"
  - "/pdb compiler option [C#]"
ms.assetid: e9d0f96a-5b75-45d6-9765-92538dd5f823
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# /pdb (C# Compiler Options)
Die **\/pdb**\-Compileroption gibt den Namen und den Speicherort der Debugsymboldatei an.  
  
## Syntax  
  
```  
/pdb:filename  
```  
  
## Argumente  
 `filename`  
 Name und Speicherort der Debugsymboldatei.  
  
## Hinweise  
 Wenn Sie [\/debug \(Emit Debugging Information\)](../../../csharp/language-reference/compiler-options/debug-compiler-option.md) angeben, erstellt der Compiler eine PDB\-Datei im selben Verzeichnis, in dem er die Ausgabedatei \(EXE oder DLL\) erstellt, und mit demselben Dateinamen wie die Ausgabedatei.  
  
 Mit **\/pdb** können Sie einen Dateinamen und Speicherort für die PDB\-Datei angeben, die vom Standardnamen und \-speicherort verschieden sind.  
  
 Diese Compileroption kann weder in der Entwicklungsumgebung von Visual Studio eingestellt noch programmgesteuert geändert werden.  
  
## Beispiel  
 Kompilieren von `t.cs` und Erstellen einer PDB\-Datei mit dem Namen tt.pdb:  
  
```  
csc /debug /pdb:tt t.cs  
```  
  
## Siehe auch  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [Gewusst wie: Ändern von Projekteigenschaften und Konfigurationseinstellungen](http://msdn.microsoft.com/de-de/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)