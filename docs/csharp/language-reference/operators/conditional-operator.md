---
title: "Operator&#160;?: (C#-Referenz) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "?:_CSharpKeyword"
  - "?_CSharpKeyword"
  - ":_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "?: (Operator) [C#]"
  - "Bedingter Operator (?:) [C#]"
ms.assetid: e83a17f1-7500-48ba-8bee-2fbc4c847af4
caps.latest.revision: 23
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 21
---
# Operator&#160;?: (C#-Referenz)
Der bedingte Operator \(`?:`\) gibt abhängig vom Wert eines booleschen Ausdrucks einen von zwei Werten zurück.  Nachfolgend ist die Syntax für den bedingten Operator aufgeführt.  
  
```  
condition ? first_expression : second_expression;  
```  
  
## Hinweise  
 `condition` muss mit `true` oder `false` ausgewertet werden.  Wenn `condition` den Wert `true` hat, wird `first_expression` ausgewertet.  Wenn `condition` den Wert `false` hat, wird `second_expression` ausgewertet.  Nur einer der beiden Ausdrücke wird ausgewertet.  
  
 Entweder muss der Typ von `first_expression` und `second_expression` identisch sein, oder es muss eine implizite Konvertierung von einem Typ in einen anderen vorhanden sein.  
  
 Sie können mithilfe des bedingten Operators Berechnungen präziser ausdrücken, die andernfalls möglicherweise eine `if-else`\-Konstruktion benötigen.  Im folgenden Code wird z. B. zuerst eine `if`\-Anweisung und anschließend ein bedingter Operator verwendet, um eine ganze Zahl als positiv oder negativ zu klassifizieren.  
  
```  
  
int input = Convert.ToInt32(Console.ReadLine());  
string classify;  
  
// if-else construction.  
if (input > 0)  
    classify = "positive";  
else  
    classify = "negative";  
  
// ?: conditional operator.  
classify = (input > 0) ? "positive" : "negative";  
  
```  
  
 Der bedingte Operator ist rechtsassoziativ.  Der Ausdruck `a ? b : c ? d : e` wird als `a ? b : (c ? d : e)` und nicht als `(a ? b : c) ? d : e` ausgewertet.  
  
 Der bedingte Operator kann nicht überladen werden.  
  
## Beispiel  
 [!code-cs[csRefOperators#41](../../../csharp/language-reference/operators/codesnippet/csharp/csrefOperators/csrefOperators.cs#41)]  
  
## Siehe auch  
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C\#\-Operatoren](../../../csharp/language-reference/operators/index.md)   
 [if\-else](../../../csharp/language-reference/keywords/if-else.md)