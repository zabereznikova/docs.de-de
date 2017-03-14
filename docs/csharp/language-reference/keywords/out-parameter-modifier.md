---
title: "Modifizierer f&#252;r out-Parameter (C#-Verweis) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "out-Parameter [C#]"
  - "Parameter [C#], out"
ms.assetid: 3fce0dc5-03f4-4faa-bd61-36c41bc6baf1
caps.latest.revision: 9
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 9
---
# Modifizierer f&#252;r out-Parameter (C#-Verweis)
Das `out`\-Schlüsselwort bewirkt, dass Argumente als Verweis übergeben werden.  Dies entspricht dem [ref](../../../csharp/language-reference/keywords/ref.md)\-Schlüsselwort, abgesehen davon, dass für `ref` die Variable initialisiert werden muss, bevor sie übergeben wird.  Um einen `out`\-Parameter zu verwenden, müssen sowohl die Methodendefinition als auch die aufrufende Methode explizit das `out`\-Schlüsselwort verwenden.  Beispiel:  
  
 [!code-cs[csrefKeywordsMethodParams#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/out-parameter-modifier_1.cs)]  
  
 Als `out`\-Argument übergebene Variablen müssen zwar nicht initialisiert werden, bevor sie übergeben werden, aber die aufrufende Methode muss einen Wert zuweisen, bevor die Methode einen Wert zurückgibt.  
  
 Obwohl das `ref`\-Schlüsselwort und `out`\-Schlüsselwort das Verhalten der Laufzeit verändern, werden sie zur Kompilierzeit nicht als Teil der Methodensignatur betrachtet.  Daher können Methoden nicht überladen werden, wenn der Unterschied nur darin besteht, dass eine Methode ein `ref`\-Argument annimmt und die andere Methode ein `out`\-Argument.  Daher kann das folgende Codebeispiel nicht kompiliert werden:  
  
 [!code-cs[csrefKeywordsMethodParams#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/out-parameter-modifier_2.cs)]  
  
 Die Überladung ist jedoch möglich, wenn eine Methode ein `ref`\-Argument oder ein `out`\-Argument annimmt und die andere Methode keines der beiden Argumente verwendet. Beispiel:  
  
 [!code-cs[csrefKeywordsMethodParams#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/out-parameter-modifier_3.cs)]  
  
 Eigenschaften sind keine Variablen und können daher nicht als `out`\-Parameter übergeben werden.  
  
 Weitere Informationen zum Übergeben von Arrays finden Sie unter [Übergeben von Arrays mithilfe von "ref" und "out"](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md).  
  
 Sie können die `ref` und `out` Schlüsselwörter für die folgenden Arten von Methoden nicht verwenden:  
  
-   Async\-Methoden, die Sie definieren, indem Sie den [async](../../../csharp/language-reference/keywords/async.md)\-Modifizierer verwenden.  
  
-   Iteratormethoden, die eine [Rendite](../../../csharp/language-reference/keywords/yield.md) oder `yield break`\-Anweisung enthalten.  
  
## Beispiel  
 Das Deklarieren einer `out`\-Methode ist nützlich, wenn eine Methode mehrere Werte zurückgeben soll.  Im folgenden Beispiel wird `out` verwendet, um mit einem Methodenaufruf drei Variablen zurückzugeben.  Beachten Sie, dass das dritte Argument NULL zugewiesen wird.  Auf diese Weise können Methoden Werte optional zurückgeben.  
  
 [!code-cs[csrefKeywordsMethodParams#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/out-parameter-modifier_4.cs)]  
  
## C\#\-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## Siehe auch  
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C\#\-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)   
 [Methodenparameter](../../../csharp/language-reference/keywords/method-parameters.md)