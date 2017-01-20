---
title: "?? Operator (C#-Referenz) | Microsoft Docs"
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
  - "??_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Operator ?? [C#]"
  - "Coalesce-Operator [C#]"
  - "Bedingter AND-Operator (&&) [C#]"
ms.assetid: 088b1f0d-c1af-4fe1-b4b8-196fd5ea9132
caps.latest.revision: 17
caps.handback.revision: 17
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# ?? Operator (C#-Referenz)
Der Operator `??` wird NULL\-Sammeloperator genannt.  Der linke Operand wird zurückgegeben, falls dieser nicht NULL ist. Andernfalls wird der rechte Operand zurückgegeben.  
  
## Hinweise  
 Ein Typ, der NULL\-Werte zulässt, kann einen Wert aus der Domäne des Typs repräsentieren, oder der Wert kann nicht definiert sein \(in diesem Fall ist der Wert NULL\).  Sie können mit der syntaktischen Ausdruckskraft des `??`\-Operators einen entsprechenden Wert \(den rechten Operand\) zurückgeben, wenn der linke Operand einen Typ aufweist, der NULL\-Werte zulässt und dessen Wert NULL ist.  Der Versuch, einen Werttyp, der auf NULL festgelegt werden kann, einem Werttyp, der nicht auf NULL festgelegt werden kann, ohne Verwendung des Operators `??` zuzuweisen, verursacht einen Kompilierungsfehler.  Wenn bei einer Typumwandlung der Werttyp, der auf NULL festgelegt werden kann, aktuell nicht definiert ist, wird eine `InvalidOperationException`\-Ausnahme ausgelöst.  
  
 Weitere Informationen finden Sie unter [Typen, die NULL\-Werte zulassen](../../../csharp/programming-guide/nullable-types/index.md).  
  
 Das Ergebnis eines ??\-Operators wird nicht als Konstante behandelt, auch wenn dessen zwei Argumente Konstanten sind.  
  
## Beispiel  
 [!code-cs[csRefOperators#53](../../../csharp/language-reference/operators/codesnippet/CSharp/csrefOperators/csrefOperators.cs#53)]  
  
## Siehe auch  
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C\#\-Operatoren](../../../csharp/language-reference/operators/index.md)   
 [Typen, die NULL\-Werte zulassen](../../../csharp/programming-guide/nullable-types/index.md)   
 [What Exactly Does 'Lifted' mean?](http://go.microsoft.com/fwlink/?LinkID=112382)