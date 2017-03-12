---
title: "/codepage (C# Compiler Options) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "/codepage"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "/codepage compiler option [C#]"
  - "codepage compiler option [C#]"
  - "-codepage compiler option [C#]"
ms.assetid: 75942989-b69a-4308-90a0-840c73d2c478
caps.latest.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 15
---
# /codepage (C# Compiler Options)
Diese Option gibt an, welche Codepage beim Kompilieren verwendet werden soll, wenn die erforderliche Seite nicht die aktuelle Standardcodepage für das System ist.  
  
## Syntax  
  
```  
/codepage:id  
```  
  
## Argumente  
 `id`  
 die ID der Codepage, die für alle Quellcodedateien in der Kompilierung verwendet werden soll.  
  
## Hinweise  
 Wenn Sie eine oder mehrere Quellcodedateien kompilieren, für die beim Erstellen nicht die Verwendung der Standardcodepage auf dem Computer festgelegt wurde, können Sie die **\/codepage**\-Option verwenden, um anzugeben, welche Codeseite verwendet werden soll.  **\/codepage** wirkt sich auf alle bei der Kompilierung verwendeten Quellcodedateien aus.  
  
 Wenn die Quellcodedateien mit der auf dem Computer aktivierten Codepage oder mit UNICODE bzw. UTF\-8 erstellt wurden, müssen Sie **\/codepage** nicht verwenden.  
  
 Siehe [GetCPInfo](http://go.microsoft.com/fwlink/?LinkId=148371) zu Informationen darüber, wie ermittelt, welche Codepages auf das System unterstützt werden.  
  
 Diese Compileroption steht in Visual Studio nicht zur Verfügung. Sie kann nicht programmgesteuert geändert werden.  
  
## Siehe auch  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [Gewusst wie: Ändern von Projekteigenschaften und Konfigurationseinstellungen](http://msdn.microsoft.com/de-de/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)