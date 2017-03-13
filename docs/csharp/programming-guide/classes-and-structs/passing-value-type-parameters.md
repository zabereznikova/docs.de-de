---
title: "&#220;bergeben von Werttypparametern (C#-Programmierhandbuch) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Methodenparameter [C#], Werttypen"
  - "Parameter [C#], Wert"
ms.assetid: 193ab86f-5f9b-4359-ac29-7cdf8afad3a6
caps.latest.revision: 17
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 17
---
# &#220;bergeben von Werttypparametern (C#-Programmierhandbuch)
In einer [Werttypvariablen](../../../csharp/language-reference/keywords/value-types.md) sind die Daten direkt enthalten, während eine [Verweistypvariable](../../../csharp/language-reference/keywords/reference-types.md) einen Verweis auf die Daten enthält.  Ein Werttyp die Variable an eine Methode als Wert übergeben bedeutet die Übergabe einer Kopie der Variablen an die Methode.  Alle Änderungen am Parameter, die innerhalb der Methode haben keinen Einfluss auf den ursprünglichen Daten stattfinden, die in der Argument die Variable gespeichert werden.  Wenn Sie die aufgerufene Methode den Wert des Parameters ändern möchten, müssen Sie ihn durch einen Verweis, mit [ref](../../../csharp/language-reference/keywords/ref.md) oder des [Timeout](../../../csharp/language-reference/keywords/out.md)\-Schlüsselwort übergeben.  Der Einfachheit halber wird in den folgenden Beispielen `ref` verwendet.  
  
## Übergeben von Werttypen als Wert  
 Im folgenden Beispiel werden Werttypparameter als Wert übergeben.  Die `n`\-Variable wird der `SquareIt`\-Methode als Wert übergeben.  Alle Änderungen, die innerhalb der Methode vorgenommen werden, wirken sich nicht auf den ursprünglichen Wert der Variablen aus.  
  
 [!code-cs[csProgGuideParameters#3](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-value-type-parameters_1.cs)]  
  
 Variable `n` ist ein Werttyp.  Er enthält seine Daten, den Wert `5`.  Wenn `SquareIt` aufgerufen wird, wird der Inhalt von `n` in den Parameter `x` kopiert, der in der Methode quadriert wird.  In `Main`Allerdings ist der Wert von `n` gleich, nachdem er die `SquareIt`\-Methode aufgerufen hat, die er zuvor befand.  Die Änderung, die innerhalb der Methode ausgeführt wird, wirkt sich nur auf die lokale Variable `x`.  
  
## Übergeben von Werttypen als Verweis  
 Das folgende Beispiel entspricht dem vorhergehenden Beispiel, mit dem Unterschied, dass das Argument `ref` wird als Parameter übergeben.  Der Wert des zugrunde liegenden `n`Arguments wird geändert, wenn `x` in der Methode geändert wird.  
  
 [!code-cs[csProgGuideParameters#4](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-value-type-parameters_2.cs)]  
  
 In diesem Beispiel wird nicht der Wert von `n`, sondern vielmehr ein Verweis auf `n` übergeben.  Der Parameter `x` ist kein [int](../../../csharp/language-reference/keywords/int.md), sondern ein Verweis auf `int` \(in diesem Fall ein Verweis auf `n`\).  Wenn `x` innerhalb der Methode quadriert, was tatsächlich quadriert wird, was `x` verweist, ist `n`.  
  
## Vertauschen von Werttypen  
 Ein allgemeines Beispiel einer Änderung der Werte der Argumente ist eine Austausch Methode, in der Sie zwei Variablen an die Methode übergeben, und die Methode lagert ihre Inhalte aus.  Sie müssen die Argumente der Austausch Methode durch einen Verweis übergeben.  Andernfalls lagern Sie lokale Kopien der Parameter innerhalb der Methode aus, und keine Änderung wird in der aufrufenden Methode ein.  Das folgende Beispiel lagert ganzzahligen Werten aus.  
  
 [!code-cs[csProgGuideParameters#5](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-value-type-parameters_3.cs)]  
  
 Wenn Sie die `SwapByRef`\-Methode aufrufen, verwenden Sie das Schlüsselwort im Aufruf `ref` , wie im folgenden Beispiel gezeigt.  
  
 [!code-cs[csProgGuideParameters#6](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-value-type-parameters_4.cs)]  
  
## Siehe auch  
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Übergeben von Parametern](../../../csharp/programming-guide/classes-and-structs/passing-parameters.md)   
 [Übergeben von Verweistypparametern](../../../csharp/programming-guide/classes-and-structs/passing-reference-type-parameters.md)