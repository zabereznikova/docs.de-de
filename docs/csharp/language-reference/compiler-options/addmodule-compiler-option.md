---
title: "/addmodule (C# Compiler Options) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "/addmodule"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "/addmodule compiler option [C#]"
  - "-addmodule compiler option [C#]"
  - "addmodule compiler option [C#]"
ms.assetid: ed604546-0dc2-4bd4-9a3e-610a8d973e58
caps.latest.revision: 13
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 13
---
# /addmodule (C# Compiler Options)
Mit dieser Option wird der aktuellen Kompilation ein Modul hinzugefügt, das mit dem Schalter target:module erstellt wurde.  
  
## Syntax  
  
```  
/addmodule:file[;file2]  
```  
  
## Argumente  
 `file`, `file2`  
 eine Ausgabedatei, die Metadaten enthält.  Die Datei kann kein Assemblymanifest enthalten.  Wenn mehrere Dateien importiert werden sollen, trennen Sie die Dateinamen durch ein Komma oder Semikolon voneinander.  
  
## Hinweise  
 Alle Module, die mit **\/addmodule** hinzugefügt werden, müssen sich im selben Verzeichnis wie die Ausgabedatei zur Laufzeit befinden.  Das heißt, Sie können ein Modul in einem beliebigen Verzeichnis zur Kompilierungszeit angeben, aber das Modul muss sich zur Laufzeit im Anwendungsverzeichnis befinden.  Wenn sich das Modul zur Laufzeit nicht im Anwendungsverzeichnis befindet, erhalten Sie die Ausnahme <xref:System.TypeLoadException>.  
  
 Die Datei \(`file`\) kann keine Assembly enthalten.  Wenn die Ausgabedatei beispielsweise mit [\/target:module](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md) erstellt wurde, können ihre Metadaten mit **\/addmodule** importiert werden.  
  
 Wenn die Ausgabedatei mit einer anderen **\/target**\-Option als **\/target:module** erstellt wurde, können ihre Metadaten nicht mit **\/addmodule**, sondern mit [\/reference](../../../csharp/language-reference/compiler-options/reference-compiler-option.md) importiert werden.  
  
 Diese Compileroption ist in Visual Studio nicht verfügbar; Projekte können nicht auf Module verweisen.  Außerdem kann diese Compileroption nicht programmgesteuert geändert werden.  
  
## Beispiel  
 In diesem Beispiel werden die Quelldatei `input.cs` kompiliert und Metadaten aus `metad1.netmodule` und `metad2.netmodule` für die Erstellung von `out.exe` hinzugefügt:  
  
```  
csc /addmodule:metad1.netmodule;metad2.netmodule /out:out.exe input.cs  
```  
  
## Siehe auch  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [Gewusst wie: Ändern von Projekteigenschaften und Konfigurationseinstellungen](http://msdn.microsoft.com/de-de/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)   
 [Mehrfachdateiassemblys](../Topic/Multifile%20Assemblies.md)   
 [Gewusst wie: Erstellen einer Mehrfachdateiassembly](../Topic/How%20to:%20Build%20a%20Multifile%20Assembly.md)