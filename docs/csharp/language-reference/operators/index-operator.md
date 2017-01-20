---
title: "Operator (C#-Referenz) | Microsoft Docs"
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
  - "[]_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Indexoperator [C#]"
  - "Eckige Klammern [ ] (Operator) [C#]"
  - "[] (Operator) [C#]"
  - "Indizierungsoperator [C#]"
ms.assetid: 5c16bb45-88f7-45ff-b42c-1af1972b042c
caps.latest.revision: 20
caps.handback.revision: 20
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Operator (C#-Referenz)
Eckige Klammern \(`[]`\) werden für Arrays, Indexer und Attribute verwendet.  Sie können auch mit Zeigern verwendet werden.  
  
## Hinweise  
 Ein Arraytyp ist ein Typ, auf den `[]` folgen.  
  
 [!code-cs[csRefOperators#43](../../../csharp/language-reference/operators/codesnippet/CSharp/csrefOperators/csrefOperators.cs#43)]  
  
 Um auf ein Element eines Arrays zuzugreifen, wird der Index des gewünschten Elements in eckige Klammern eingeschlossen:  
  
 [!code-cs[csRefOperators#44](../../../csharp/language-reference/operators/codesnippet/CSharp/csrefOperators/csrefOperators.cs#44)]  
  
 Eine Ausnahme wird ausgelöst, wenn sich ein Arrayindex außerhalb des gültigen Bereichs befindet.  
  
 Der Arrayindizierungsoperator kann nicht überladen werden. Typen können jedoch Indexer und Eigenschaften definieren, die mindestens einen Parameter aufweisen.  Indexerparameter werden so wie Arrayindizes in eckige Klammern eingeschlossen. Indexerparameter können aber als beliebiger Typ deklariert werden, während Arrayindizes immer ganzzahlig sein müssen.  
  
 .NET Framework definiert z. B. einen `Hashtable`\-Typ, der Schlüssel und Werte beliebigen Typs verknüpft:  
  
 [!code-cs[csRefOperators#45](../../../csharp/language-reference/operators/codesnippet/CSharp/csrefOperators/csrefOperators.cs#45)]  
  
 Eckige Klammern werden auch verwendet, um [Attribute](../Topic/Attributes%20\(C%23%20and%20Visual%20Basic\).md) anzugeben:  
  
 [!code-cs[csRefOperators#46](../../../csharp/language-reference/operators/codesnippet/CSharp/csrefOperators/csrefOperators.cs#46)]  
  
 Sie können eckige Klammern verwenden, um die Indizierung eines Zeigers aufzuheben:  
  
 [!code-cs[csRefOperators#47](../../../csharp/language-reference/operators/codesnippet/CSharp/csrefOperators/csrefOperators.cs#47)]  
  
 Es wird keine Überprüfung der Grenzen durchgeführt.  
  
## C\#\-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Siehe auch  
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C\#\-Operatoren](../../../csharp/language-reference/operators/index.md)   
 [Arrays](../../../csharp/programming-guide/arrays/index.md)   
 [Indexer](../../../csharp/programming-guide/indexers/index.md)   
 [Unsicher](../../../csharp/language-reference/keywords/unsafe.md)   
 [fixed\-Anweisung](../../../csharp/language-reference/keywords/fixed-statement.md)