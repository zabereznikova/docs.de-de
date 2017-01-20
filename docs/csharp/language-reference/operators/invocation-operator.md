---
title: "Operator () (C#-Referenz) | Microsoft Docs"
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
  - "()_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "()-Operator [C#]"
  - "Umwandlungsoperator [C#]"
  - "Typkonvertierung [C#], ()-Operator"
ms.assetid: 846e1f94-8a8c-42fc-a42c-fbd38e70d8cc
caps.latest.revision: 22
caps.handback.revision: 22
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Operator () (C#-Referenz)
Klammern werden nicht nur für die Angabe der Reihenfolge von Vorgängen in einem Ausdruck, sondern auch für die folgenden Aufgaben verwendet:  
  
1.  Angeben von Typumwandlungen oder Konvertierungen.  
  
     [!code-cs[csRefOperators#1](../../../csharp/language-reference/operators/codesnippet/CSharp/csrefOperators/csrefOperators.cs#1)]  
  
2.  Aufrufen von Methoden oder Delegaten.  
  
     [!code-cs[csRefOperators#2](../../../csharp/language-reference/operators/codesnippet/CSharp/csrefOperators/csrefOperators.cs#2)]  
  
## Hinweise  
 Eine Typumwandlung ruft explizit den Operator zum Konvertieren des Typs auf. Ist kein solcher Konvertierungsoperator vorhanden, tritt bei der Typumwandlung ein Fehler auf.  Informationen zur Definition eines Konvertierungsoperators finden Sie unter [explicit](../../../csharp/language-reference/keywords/explicit.md) und unter [implicit](../../../csharp/language-reference/keywords/implicit.md).  
  
 Der Operator `()` kann nicht überladen werden.  
  
 Weitere Informationen finden Sie unter [Umwandlung und Typkonvertierungen](../../../csharp/programming-guide/types/casting-and-type-conversions.md).  
  
 Ein Umwandlungsausdruck kann unter Umständen zu mehrdeutiger Syntax führen.  Der Ausdruck `(x)–y` kann z. B. als Typumwandlungsausdruck \(Umwandlung von \-y in den Typ x\) oder als ein mit einem Ausdruck in Klammern kombinierter additiver Ausdruck zur Berechnung des Werts von x \- y interpretiert werden.  
  
 Weitere Informationen zum Aufrufen von Methoden finden Sie unter [Methoden](../../../csharp/programming-guide/classes-and-structs/methods.md).  
  
## C\#\-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Siehe auch  
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C\#\-Operatoren](../../../csharp/language-reference/operators/index.md)