---
title: "true-Operator (C#-Referenz) | Microsoft Docs"
ms.custom: ""
ms.date: "01/05/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "true-Operator [C#]"
ms.assetid: acaba817-5da5-4364-b3b2-2e5c75ec1839
caps.latest.revision: 19
caps.handback.revision: 19
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# true-Operator (C#-Referenz)
Gibt den [booleschen](../../../csharp/language-reference/keywords/bool.md) Wert `true` zurück, um anzugeben, dass ein Operand auf True festgelegt ist, und gibt andernfalls `false` zurück.  
  
 Vor C\# 2.0 wurden der `true`\-Operator und der `false`\-Operator zum Erstellen benutzerdefinierter auf NULL festlegbarer Werttypen verwendet, die mit bestimmten Typen kompatibel sind, z. B. `SqlBool`.  Die Programmiersprache bietet nun jedoch integrierte Unterstützung für auf NULL festlegbare Werttypen, und nach Möglichkeit sollten Sie statt der Überladung des `true`\-Operators und des `false`\-Operators diese verwenden.  Weitere Informationen finden Sie unter [Typen, die NULL\-Werte zulassen](../../../csharp/programming-guide/nullable-types/index.md).  
  
 Bei auf NULL festlegbaren booleschen Werten ist der Ausdruck `a != b` nicht notwendigerweise gleich `!(a == b)`, da einer der Werte oder beide Werte NULL sein können.  Sie müssen den `true`\-Operator und den `false`\-Operator getrennt überladen, um die NULL\-Werte im Ausdruck richtig zu bezeichnen.  Das folgende Beispiel veranschaulicht die Überladung und Verwendung des `true`\-Operators und des `false`\-Operators.  
  
 [!code-cs[csrefKeywordsOperator#16](../../../csharp/language-reference/keywords/codesnippet/CSharp/csrefKeywordsOperator/csrefKeywordsOperators.cs#16)]  
  
 Ein Typ, der den `true`\-Operator und den `false`\-Operator überlädt, kann für den steuernden Ausdruck in den Anweisungen [if](../../../csharp/language-reference/keywords/if-else.md), [do](../../../csharp/language-reference/keywords/do.md), [while](../../../csharp/language-reference/keywords/while.md) und [for](../../../csharp/language-reference/keywords/for.md) sowie in [bedingten Ausdrücken](../../../csharp/language-reference/operators/conditional-operator.md) verwendet werden.  
  
 Wenn ein Typ den Operator `true` definiert, muss er auch den Operator [false](../../../csharp/language-reference/keywords/false.md) definieren.  
  
 Die bedingten logischen Operatoren \([&&](../../../csharp/language-reference/operators/conditional-and-operator.md) und [&#124;&#124;](../../../csharp/language-reference/operators/conditional-or-operator.md)\) können von einem Typ nicht direkt überladen werden. Eine vergleichbare Wirkung kann jedoch erzielt werden durch Überladung der regulären logischen Operatoren und der Operatoren `true` und `false`.  
  
## C\#\-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Siehe auch  
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C\#\-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)   
 [C\#\-Operatoren](../../../csharp/language-reference/operators/index.md)   
 [Falsch](../../../csharp/language-reference/keywords/false.md)