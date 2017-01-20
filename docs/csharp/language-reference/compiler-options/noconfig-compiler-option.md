---
title: "/noconfig (C# Compiler Options) | Microsoft Docs"
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
  - "/noconfig"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "/noconfig compiler option [C#]"
  - "csc.rsp"
  - "-noconfig compiler option [C#]"
  - "noconfig compiler option [C#]"
ms.assetid: cd26967e-e494-4c8c-b5c9-af13b2f78b2e
caps.latest.revision: 11
caps.handback.revision: 11
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# /noconfig (C# Compiler Options)
Durch die Option **\/noconfig** wird der Compiler angewiesen, die Kompilierung nicht unter Verwendung der Datei csc.rsp auszuführen, die sich im selben Verzeichnis befindet wie die Datei csc.exe und von dort aus geladen wird.  
  
## Syntax  
  
```  
/noconfig  
```  
  
## Hinweise  
 In der Datei **csc.rsp** wird auf alle Assemblys verwiesen, die mit .NET Framework geliefert wurden.  Welche Verweise von der Visual Studio .NET\-Entwicklungsumgebung berücksichtigt werden, hängt vom Projekttyp ab.  
  
 Sie können die Datei **csc.rsp** bearbeiten und \(mit Ausnahme der Option **\/noconfig**\) beliebige zusätzliche Compileroptionen angeben, die in allen Befehlszeilenkompilierungen von **csc.exe** ausgeführt werden sollen.  
  
 Der Compiler verarbeitet die an den **csc**\-Befehl übergebenen Optionen zuletzt.  Daher wird jede in der Datei **csc.rsp** festgelegte Optionseinstellung durch die entsprechende, in der Befehlszeile angegebene Option überschrieben.  
  
 Wenn der Compiler nicht nach den Einstellungen in der Datei **csc.rsp** suchen und diese verwenden soll, geben Sie **\/noconfig** an.  
  
 Diese Compileroption steht in Visual Studio nicht zur Verfügung. Sie kann nicht programmgesteuert geändert werden.  
  
## Siehe auch  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [Gewusst wie: Ändern von Projekteigenschaften und Konfigurationseinstellungen](http://msdn.microsoft.com/de-de/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)