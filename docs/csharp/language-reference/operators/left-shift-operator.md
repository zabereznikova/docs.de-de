---
title: "Operator &lt;&lt; (C#-Referenz) | Microsoft Docs"
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
  - "<<_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "<< (Operator) [C#]"
  - "Linksschiebeoperator (<<) [C#]"
ms.assetid: a654eb56-1ff7-4bf3-9064-b631be0cdccc
caps.latest.revision: 18
caps.handback.revision: 18
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Operator &lt;&lt; (C#-Referenz)
Der Linksschiebeoperator \(`<<`\) verschiebt seinen ersten Operanden um die durch seinen zweiten Operanden angegebene Bitanzahl nach links.  Der Typ des zweiten Operanden muss ein [int](../../../csharp/language-reference/keywords/int.md) oder ein Typ sein, der eine vordefinierte implizite numerische Konvertierung in `int` hat.  
  
## Hinweise  
 Wenn der erste Operand [int](../../../csharp/language-reference/keywords/int.md) oder [uint](../../../csharp/language-reference/keywords/uint.md) \(32 Bit\) ist, wird die Anzahl der Bitverschiebungen durch die fünf niedrigstwertigen Bits des zweiten Operanden angegeben.  Das heißt, die tatsächliche Verschiebung beträgt 0 bis 31 Bits.  
  
 Wenn der erste Operand [long](../../../csharp/language-reference/keywords/long.md) oder [ulong](../../../csharp/language-reference/keywords/ulong.md) \(64 Bit\) ist, wird die Anzahl der Bitverschiebungen durch die sechs niedrigstwertigen Bits des zweiten Operanden angegeben.  Das heißt, die tatsächliche Verschiebung beträgt 0 bis 63 Bits.  
  
 Alle höherwertigen Bits außerhalb des Bereichs des ersten Operanden nach der Verschiebung werden verworfen, und die niederwertigen leeren Bits werden mit Nullen aufgefüllt.  Schiebeoperationen lösen nie Überläufe aus.  
  
 Benutzerdefinierte Typen können den Operator `<<` überladen \(siehe [Operator](../../../csharp/language-reference/keywords/operator.md)\). Als Typ des ersten Operanden muss der benutzerdefinierte Typ verwendet werden, und als Typ des zweiten Operanden muss `int` verwendet werden.  Beim Überladen eines binären Operators wird implizit auch der zugehörige Zuweisungsoperator überladen, falls vorhanden.  
  
## Beispiel  
 [!code-cs[csRefOperators#14](../../../csharp/language-reference/operators/codesnippet/CSharp/csrefOperators/csrefOperators.cs#14)]  
  
## Kommentare  
 Beachten Sie, dass `i<<1` und `i<<33` das gleiche Ergebnis ausgeben, da die fünf niedrigwertigen Bits von 1 und 33 übereinstimmen.  
  
## Siehe auch  
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C\#\-Operatoren](../../../csharp/language-reference/operators/index.md)