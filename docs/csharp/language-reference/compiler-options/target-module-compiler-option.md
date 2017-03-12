---
title: "/target:module (C# Compiler Options) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "/target:module"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "-target compiler options [C#], /target:module"
  - "target compiler options [C#], /target:module"
  - "/target compiler options [C#], /target:module"
ms.assetid: 9af1e4fa-c749-44e7-ae58-90a3d05d4e72
caps.latest.revision: 11
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 11
---
# /target:module (C# Compiler Options)
Diese Option bewirkt, dass der Compiler kein Assemblymanifest generiert.  
  
## Syntax  
  
```  
/target:module  
```  
  
## Hinweise  
 Standardmäßig weist die Ausgabedatei, die erstellt wird, indem sie mit dieser Option kompiliert, eine Erweiterung von .netmodule.  
  
 Eine Datei, die kein Assemblymanifest aufweist, kann nicht von der .NET Framework\-Common Language Runtime geladen werden.  Allerdings können Sie eine solche Datei mithilfe von [\/addmodule](../../../csharp/language-reference/compiler-options/addmodule-compiler-option.md) in das Assemblymanifest einer Assembly aufnehmen.  
  
 Wenn in einer einzigen Kompilierung mehrere Module erstellt werden, stehen die [internen](../../../csharp/language-reference/keywords/internal.md) Typen eines Moduls den anderen Modulen in der Kompilierung zur Verfügung.  Wenn Code in einem Modul auf `internal`\-Typen in einem anderen Modul verweist, müssen beide Module mithilfe von **\/addmodule** in ein Assemblymanifest aufgenommen werden.  
  
 Das Erstellen von Modulen wird in der Visual Studio\-Entwicklungsumgebung nicht unterstützt.  
  
 Informationen über das programmgesteuerte Festlegen dieser Compileroption finden Sie unter <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.  
  
## Beispiel  
 In diesem Beispiel wird `in.cs` kompiliert und `in.netmodule` erstellt:  
  
```  
csc /target:module in.cs  
```  
  
## Siehe auch  
 [\/target \(Specify Output File Format\)](../../../csharp/language-reference/compiler-options/target-compiler-option.md)   
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)