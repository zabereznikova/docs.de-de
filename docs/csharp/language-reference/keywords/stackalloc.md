---
title: "stackalloc (C#-Referenz) | Microsoft Docs"
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
  - "stackalloc_CSharpKeyword"
  - "stackalloc"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "stackalloc-Schlüsselwort [C#]"
ms.assetid: adc04c28-3ed2-4326-807a-7545df92b852
caps.latest.revision: 27
caps.handback.revision: 27
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# stackalloc (C#-Referenz)
Das `stackalloc`\-Schlüsselwort wird in einem unsicheren Codekontext verwendet, um einen Speicherblock auf dem Stapel zu belegen.  
  
```  
int* block = stackalloc int[100];  
```  
  
## Hinweise  
 Das Schlüsselwort ist nur in den lokalen Variableninitialisierern gültig.  Im folgenden Code werden Compilerfehler verursacht.  
  
```  
int* block;  
// The following assignment statement causes compiler errors. You  
// can use stackalloc only when declaring and initializing a local   
// variable.  
block = stackalloc int[100];  
```  
  
 Da Zeigertypen beteiligt sind, verlangt `stackalloc` einen [unsicheren](../../../csharp/language-reference/keywords/unsafe.md) Kontext.  Weitere Informationen finden Sie unter [Unsicherer Code und Zeiger](../../../csharp/programming-guide/unsafe-code-pointers/index.md).  
  
 `stackalloc` kann mit [\_alloca](/visual-cpp/c-runtime-library/reference/alloca) in der C\-Laufzeitbibliothek verglichen werden.  
  
 Im folgenden Beispiel werden die ersten 20 Zahlen in der Fibonacci\-Sequenz berechnet und angezeigt.  Jede Zahl ist die Summe der vorherigen zwei Zahlen.  Im Code wird ein Speicherblock, der groß genug für 20 Elemente vom Typ `int` ist, auf dem Stapel reserviert, nicht auf dem Heap.  Die Adresse des Blocks wird im `fib`\-Zeiger gespeichert.  Dieser Speicher ist nicht der Garbage Collection unterworfen und muss daher nicht mit [fixed](../../../csharp/language-reference/keywords/fixed-statement.md) fixiert werden.  Die Lebensdauer des Speicherblocks ist auf die Lebensdauer der Methode begrenzt, in der er definiert ist.  Sie können den Speicher nicht freigeben, bevor die Methode einen Wert zurückgibt.  
  
## Beispiel  
 [!code-cs[csrefKeywordsOperator#15](../../../csharp/language-reference/keywords/codesnippet/CSharp/csrefKeywordsOperator/csrefKeywordsOperators.cs#15)]  
  
## Sicherheit  
 Unsicherer Code ist weniger sicher als sichere Alternativen.  Die Verwendung von `stackalloc` aktiviert jedoch automatisch Features zur Erkennung von Pufferüberläufen in der Common Language Runtime \(CLR\).  Wenn ein Pufferüberlauf festgestellt wird, wird der Prozess so schnell wie möglich beendet, um die Gefahr der Ausführung von bösartigem Code zu minimieren.  
  
## C\#\-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Siehe auch  
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C\#\-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)   
 [Operatorschlüsselwörter](../../../csharp/language-reference/keywords/operator-keywords.md)   
 [Unsicherer Code und Zeiger](../../../csharp/programming-guide/unsafe-code-pointers/index.md)