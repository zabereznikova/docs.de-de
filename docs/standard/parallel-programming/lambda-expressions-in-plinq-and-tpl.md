---
title: "Lambda Expressions in PLINQ and TPL | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Func delegate, creating with lambda expression"
  - "Action delegate, creating with lambda expression"
  - "lambda expressions, with Action and Func"
ms.assetid: 645b2c17-29d0-4ffa-8684-430743cc2f2d
caps.latest.revision: 12
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# Lambda Expressions in PLINQ and TPL
Die Task Parallel Library \(TPL\) enthält viele Methoden, die eine der <xref:System.Func%601?displayProperty=fullName>\- oder <xref:System.Action?displayProperty=fullName>\-Delegatfamilien als Eingabeparameter zulassen.  Sie verwenden diese Delegaten zur Übergabe der benutzerdefinierten Programmlogik an die parallele Schleife, Aufgabe oder Abfrage.  In den Codebeispielen für TPL und PLINQ werden Lambda\-Ausdrücke verwendet, um Instanzen dieser Delegaten als Inlinecodeblöcke zu erstellen.  Dieses Thema bietet eine kurze Einführung in Func und Action und zeigt, wie Sie Lambda\-Ausdrücke in der Task Parallel Library und in PLINQ verwenden.  
  
 **Hinweis** Weitere Informationen zu Delegaten im Allgemeinen finden Sie unter [Delegaten](../Topic/Delegates%20\(C%23%20Programming%20Guide\).md) und [Delegates](../Topic/Delegates%20\(Visual%20Basic\).md).  Weitere Informationen zu Lambda\-Ausdrücken in C\# und [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] finden Sie unter [Lambda\-Ausdrücke](../Topic/Lambda%20Expressions%20\(C%23%20Programming%20Guide\).md) und [Lambda Expressions](../Topic/Lambda%20Expressions%20\(Visual%20Basic\).md).  
  
## Func\-Delegat  
 Ein `Func`\-Delegat kapselt eine Methode, die einen Wert zurückgibt.  In einer Func\-Signatur gibt der letzte bzw. der am weitesten rechts stehende Typparameter immer den Rückgabetyp an.  Eine häufige Ursache von Compilerfehlern ist der Versuch, zwei Eingabeparameter an eine <xref:System.Func%602?displayProperty=fullName> zu übergeben. Dieser Typ akzeptiert jedoch nur einen Eingabeparameter.  Die .NET Framework\-Klassenbibliothek definiert 17 Versionen von `Func`: <xref:System.Func%601?displayProperty=fullName>, <xref:System.Func%602?displayProperty=fullName>, <xref:System.Func%603?displayProperty=fullName> usw. bis <xref:System.Func%6017?displayProperty=fullName>.  
  
## Action\-Delegat  
 Ein <xref:System.Action?displayProperty=fullName>\-Delegat kapselt eine Methode \(Untermethode in [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]\), die keinen Wert oder [void](../Topic/void%20\(C%23%20Reference\).md) zurückgibt.  In einer Signatur vom Typ "Action" stellen die Typparameter nur Eingabeparameter dar.  Die .NET Framework\-Klassenbibliothek definiert wie bei Func 17 Versionen von Action, von einer Version ohne Typparameter bis zu einer Version mit 16 Typparametern.  
  
## Beispiel  
 Im folgenden Beispiel für die <xref:System.Threading.Tasks.Parallel.ForEach%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%601%7D%2CSystem.Func%7B%60%600%2CSystem.Threading.Tasks.ParallelLoopState%2C%60%601%2C%60%601%7D%2CSystem.Action%7B%60%601%7D%29?displayProperty=fullName>\-Methode wird gezeigt, wie der Func\-Delegat und der Action\-Delegat mit Lambda\-Ausdrücken angegeben werden.  
  
 [!code-csharp[System.Threading.Tasks.Parallel#02](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.threading.tasks.parallel/cs/parallelforeach.cs#02)]
 [!code-vb[System.Threading.Tasks.Parallel#02](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.threading.tasks.parallel/vb/parallelforeach.vb#02)]  
  
## Siehe auch  
 [Parallel Programming](../../../docs/standard/parallel-programming/index.md)