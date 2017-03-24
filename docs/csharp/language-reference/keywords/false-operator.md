---
title: "false-Operator (C#-Referenz) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "false-Operatorschlüsselwort [C#]"
ms.assetid: 81a888fd-011e-4589-b242-6c261fea505e
caps.latest.revision: 21
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 21
---
# false-Operator (C#-Referenz)
Gibt den [booleschen](../../../csharp/language-reference/keywords/bool.md) Wert `true` zurück, um anzugeben, dass ein Operand `false` ist, und gibt andernfalls `false` zurück.  
  
 Vor C\# 2.0 wurden der `true`\-Operator und der `false`\-Operator zum Erstellen benutzerdefinierter auf NULL festlegbarer Werttypen verwendet, die mit bestimmten Typen kompatibel sind, z. B. `SqlBool`.  Die Programmiersprache bietet nun jedoch integrierte Unterstützung für auf NULL festlegbare Werttypen, und nach Möglichkeit sollten Sie statt der Überladung des `true`\-Operators und des `false`\-Operators diese verwenden.  Weitere Informationen finden Sie unter [Typen, die NULL\-Werte zulassen](../../../csharp/programming-guide/nullable-types/index.md).  
  
 Bei auf NULL festlegbaren booleschen Werten ist der Ausdruck `a != b` nicht notwendigerweise gleich `!(a == b)`, da einer der Werte oder beide Werte NULL sein können.  Sie müssen den `true`\-Operator und den `false`\-Operator einzeln überladen, um die NULL\-Werte im Ausdruck ordnungsgemäß zu behandeln.  Das folgende Beispiel veranschaulicht die Überladung und Verwendung des `true`\-Operators und des `false`\-Operators.  
  
 [!code-cs[csrefKeywordsOperator#16](../../../csharp/language-reference/keywords/codesnippet/CSharp/false-operator_1.cs)]  
  
 Ein Typ, der den `true`\-Operator und den `false`\-Operator überlädt, kann für den steuernden Ausdruck in den Anweisungen [if](../../../csharp/language-reference/keywords/if-else.md), [do](../../../csharp/language-reference/keywords/do.md), [while](../../../csharp/language-reference/keywords/while.md) und [for](../../../csharp/language-reference/keywords/for.md) sowie in [bedingten Ausdrücken](../../../csharp/language-reference/operators/conditional-operator.md) verwendet werden.  
  
 Wenn ein Typ den Operator `false` definiert, muss er auch den Operator [true](../../../csharp/language-reference/keywords/true.md) definieren.  
  
 Die bedingten logischen Operatoren \([&&](../../../csharp/language-reference/operators/conditional-and-operator.md) und [&#124;&#124;](../../../csharp/language-reference/operators/conditional-or-operator.md)\) können von einem Typ nicht direkt überladen werden. Eine vergleichbare Wirkung kann jedoch durch Überladung der regulären logischen Operatoren und der Operatoren `true` und `false` erzielt werden.  
  
## C\#\-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Siehe auch  
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C\#\-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)   
 [C\#\-Operatoren](../../../csharp/language-reference/operators/index.md)   
 [true](../../../csharp/language-reference/keywords/true.md)