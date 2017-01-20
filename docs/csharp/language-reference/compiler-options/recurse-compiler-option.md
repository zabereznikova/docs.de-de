---
title: "/recurse (C# Compiler Options) | Microsoft Docs"
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
  - "/recurse"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "/recurse compiler option [C#]"
  - "recurse compiler option [C#]"
  - "-recurse compiler option [C#]"
ms.assetid: 4e8212e5-04e3-45b1-8a42-41bc50e683b0
caps.latest.revision: 12
caps.handback.revision: 12
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# /recurse (C# Compiler Options)
Mit der Option \/recurse können Sie die Quellcodedateien in allen untergeordneten Verzeichnissen des angegebenen Verzeichnisses \(dir\) oder des Projektverzeichnisses kompilieren.  
  
## Syntax  
  
```  
/recurse:[dir\]file  
```  
  
## Argumente  
 `dir` \(optional\)  
 Das Verzeichnis, in dem die Suche beginnen soll.  Wird dieses nicht angegeben, beginnt die Suche im Projektverzeichnis.  
  
 `file`  
 Die zu suchende\(n\) Datei\(en\).  Platzhalterzeichen sind zulässig.  
  
## Hinweise  
 Mit der Option **\/recurse** können Sie die Quellcodedateien in allen untergeordneten Verzeichnissen entweder des angegebenen Verzeichnisses \(`dir`\) oder des Projektverzeichnisses kompilieren.  
  
 Sie können in einem Dateinamen Platzhalter verwenden, um alle entsprechenden Dateien im Projektverzeichnis zu kompilieren, ohne **\/recurse** verwenden zu müssen.  
  
 Diese Compileroption steht in Visual Studio nicht zur Verfügung. Sie kann nicht programmgesteuert geändert werden.  
  
## Beispiel  
 Alle C\#\-Dateien im aktuellen Verzeichnis werden kompiliert:  
  
```  
csc *.cs  
```  
  
 Alle C\#\-Dateien im Verzeichnis **dir1\\dir2** und in allen darunter befindlichen Verzeichnissen werden kompiliert, und die Datei **dir2.dll** wird generiert:  
  
```  
csc /target:library /out:dir2.dll /recurse:dir1\dir2\*.cs  
```  
  
## Siehe auch  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [Gewusst wie: Ändern von Projekteigenschaften und Konfigurationseinstellungen](http://msdn.microsoft.com/de-de/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)