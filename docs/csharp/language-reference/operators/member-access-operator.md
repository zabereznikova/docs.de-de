---
title: ". Operator (C#-Referenz) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "._CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - ". Operator [C#]"
  - "Punktoperator (.) [C#]"
  - "Memberzugriffsoperator (.) [C#]"
ms.assetid: a1f54b52-b686-4ae5-a48e-a2a9ebd0eb7b
caps.latest.revision: 21
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 21
---
# . Operator (C#-Referenz)
Der Punktoperator \(`.`\) wird für Memberzugriff verwendet.  Der Punktoperator gibt einen Member von einem Typ oder einem Namespace an.  Der Punktoperator wird beispielsweise verwendet, um auf bestimmte Methoden in .NET Framework\-Klassenbibliotheken zuzugreifen:  
  
 [!code-cs[csRefOperators#16](../../../csharp/language-reference/operators/codesnippet/csharp/csrefOperators/csrefOperators.cs#16)]  
  
 Betrachten Sie z. B. die folgende Klasse:  
  
 [!code-cs[csRefOperators#17](../../../csharp/language-reference/operators/codesnippet/csharp/csrefOperators/csrefOperators.cs#17)]  
  
 [!code-cs[csRefOperators#18](../../../csharp/language-reference/operators/codesnippet/csharp/csrefOperators/csrefOperators.cs#18)]  
  
 Die `s`\-Variable weist die beiden Member `a` und `b` auf. Um auf sie zuzugreifen, wird der Punktoperator verwendet:  
  
 [!code-cs[csRefOperators#19](../../../csharp/language-reference/operators/codesnippet/csharp/csrefOperators/csrefOperators.cs#19)]  
  
 Der Punkt wird auch dazu verwendet, gekennzeichnete Namen zu verwenden, also Namen, die z. B. den Namespace oder die Schnittstelle angeben, wozu sie gehören.  
  
 [!code-cs[csRefOperators#20](../../../csharp/language-reference/operators/codesnippet/csharp/csrefOperators/csrefOperators.cs#20)]  
  
 Durch die using\-Direktive wird ein Teil der Namenskennzeichnung optional:  
  
 [!code-cs[csRefOperators#21](../../../csharp/language-reference/operators/codesnippet/csharp/csrefOperators/csrefOperators.cs#21)]  
  
 Ist aber ein Bezeichner mehrdeutig, muss er gekennzeichnet werden:  
  
 [!code-cs[csRefOperators#22](../../../csharp/language-reference/operators/codesnippet/csharp/csrefOperators/csrefOperators.cs#22)]  
  
## C\#\-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Siehe auch  
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C\#\-Operatoren](../../../csharp/language-reference/operators/index.md)