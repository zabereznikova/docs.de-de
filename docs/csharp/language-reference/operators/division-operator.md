---
title: "Operator / (C#-Referenz) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "/_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "/ (Operator) [C#]"
  - "Divisionsoperator [C#]"
ms.assetid: d155e496-678f-4efa-bebe-2bd08da2c5af
caps.latest.revision: 21
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 21
---
# Operator / (C#-Referenz)
Der Divisionsoperator \(`/`\) dividiert seinen ersten Operanden durch seinen zweiten Operanden.  Für alle numerischen Typen sind Divisionsoperatoren vordefiniert.  
  
## Hinweise  
 Benutzerdefinierte Typen können den Operator `/` überladen \(siehe [Operator](../../../csharp/language-reference/keywords/operator.md)\).  Durch Überladen des Operators `/` wird implizit der [Operator \/\=](../../../csharp/language-reference/operators/subtraction-assignment-operator.md) überladen.  
  
 Wenn Sie zwei ganze Zahlen teilen, ist das Ergebnis immer eine ganze Zahl.  Beispiel: Das Ergebnis von 7 \/ 3 ist 2.  Bestimmen Sie die restlichen 7 \/ 3, verwenden Sie den Restwertoperator \([%](../../../csharp/language-reference/operators/modulus-operator.md)\).  Um den Quotienten als rationale Zahl oder Bruch zu erhalten, legen Sie den Datentyp von Dividend und Divisor auf `float` oder auf `double` fest.  Sie können den Typ implizit zuweisen, wenn Sie eine Ziffer rechts vom Dezimalkomma, wie im folgenden Beispiel setzen der Dividend oder Divisor als Dezimalzahl Ausdrücken.  
  
## Beispiel  
 [!code-cs[csRefOperators#42](../../../csharp/language-reference/operators/codesnippet/CSharp/division-operator_1.cs)]  
  
## Siehe auch  
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C\#\-Operatoren](../../../csharp/language-reference/operators/index.md)