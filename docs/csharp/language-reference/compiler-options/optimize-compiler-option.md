---
title: "/optimize (C# Compiler Options) | Microsoft Docs"
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
  - "/optimize"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "/optimize compiler option [C#]"
  - "-o compiler option [C#]"
  - "optimize compiler option [C#]"
  - "/o compiler option [C#]"
  - "-optimize compiler option [C#]"
  - "compiler optimization [C#]"
  - "o compiler option [C#]"
ms.assetid: 6dd5b6f2-cd1d-4593-a9f4-1c2ed9404ca0
caps.latest.revision: 15
caps.handback.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# /optimize (C# Compiler Options)
Die Option **\/optimize** aktiviert oder deaktiviert die vom Compiler durchgeführten Optimierungen, damit die Ausgabedatei kleiner, schneller und effizienter wird.  
  
## Syntax  
  
```  
/optimize[+ | -]  
```  
  
## Hinweise  
 Darüber hinaus wird die Common Language Runtime durch **\/optimize** angewiesen, den Code zur Laufzeit zu optimieren.  
  
 Standardmäßig sind Optimierungen deaktiviert.  Mithilfe von **\/optimize\+** werden Optimierungen aktiviert.  
  
 Beim Erstellen eines Moduls, das von einer Assembly verwendet werden soll, müssen dieselben **\/optimize**\-Einstellungen verwendet werden wie für die Assembly.  
  
 **\/o** ist die Kurzform von **\/optimize**.  
  
 Die Optionen **\/optimize** und [\/debug](../../../csharp/language-reference/compiler-options/debug-compiler-option.md) können kombiniert werden.  
  
### So legen Sie diese Compileroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie die **Eigenschaften**\-Seite des Projekts.  
  
2.  Klicken Sie auf die Eigenschaftenseite **Erstellen**.  
  
3.  Ändern Sie die Eigenschaft **Code optimieren**.  
  
 Informationen darüber, wie Sie diese Compileroption programmgesteuert festlegen können, finden Sie unter <xref:VSLangProj80.CSharpProjectConfigurationProperties3.Optimize%2A>.  
  
## Beispiel  
 In diesem Beispiel wird `t2.cs`  kompiliert, wobei Compileroptimierungen aktiviert werden:  
  
```  
csc t2.cs /optimize  
```  
  
## Siehe auch  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [Gewusst wie: Ändern von Projekteigenschaften und Konfigurationseinstellungen](http://msdn.microsoft.com/de-de/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)