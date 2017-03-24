---
title: "Operator&#160;&gt;&gt; (C#-Referenz) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - ">>_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - ">> (Operator) [C#]"
  - "Rechtsschiebeoperator (>>) [C#]"
ms.assetid: a07f8679-d318-4ef8-b38b-65903efb8056
caps.latest.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 15
---
# Operator&#160;&gt;&gt; (C#-Referenz)
Der Rechtsschiebeoperator \(`>>`\) verschiebt den ersten Operanden um die durch den zweiten Operanden angegebene Zahl von Bits nach rechts.  
  
## Hinweise  
 Wenn der erste Operand [int](../../../csharp/language-reference/keywords/int.md) oder [uint](../../../csharp/language-reference/keywords/uint.md) \(32 Bit\) ist, wird die Anzahl der Bitverschiebungen durch die fünf niedrigstwertigen Bits des zweiten Operanden angegeben \(zweiter Operand & 0x1f\).  
  
 Wenn der erste Operand [long](../../../csharp/language-reference/keywords/long.md) oder [ulong](../../../csharp/language-reference/keywords/ulong.md) \(64 Bit\) ist, wird die Anzahl der Bitverschiebungen durch die sechs niedrigstwertigen Bits des zweiten Operanden angegeben \(zweiter Operand & 0x3f\).  
  
 Wenn der erste Operand vom Typ [int](../../../csharp/language-reference/keywords/int.md) oder [long](../../../csharp/language-reference/keywords/long.md) ist, ist das Nach\-Rechts\-Schieben ein arithmetisches Schieben \(höherwertige leere Bits enthalten das Vorzeichenbit\).  Wenn der erste Operand vom Typ [uint](../../../csharp/language-reference/keywords/uint.md) oder [ulong](../../../csharp/language-reference/keywords/ulong.md) ist, ist das Nach\-Rechts\-Schieben ein logisches Schieben \(höherwertige Bits werden mit Nullen aufgefüllt\).  
  
 Benutzerdefinierte Typen können den Operator `>>` überladen. Als Typ des ersten Operanden muss der benutzerdefinierte Typ verwendet werden, und als Typ des zweiten Operanden muss [int](../../../csharp/language-reference/keywords/int.md) verwendet werden.  Weitere Informationen finden Sie unter [Operator](../../../csharp/language-reference/keywords/operator.md).  Beim Überladen eines binären Operators wird implizit auch der zugehörige Zuweisungsoperator überladen, falls vorhanden.  
  
## Beispiel  
 [!code-cs[csRefOperators#26](../../../csharp/language-reference/operators/codesnippet/CSharp/right-shift-operator_1.cs)]  
  
## Siehe auch  
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C\#\-Operatoren](../../../csharp/language-reference/operators/index.md)