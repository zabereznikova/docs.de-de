---
title: "Implizit typisierte Arrays (C#-Programmierhandbuch) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Arrays [C#], Implizit typisiert"
  - "C#-Sprache, Implizit typisierte Arrays"
  - "Implizit typisierte Arrays [C#]"
ms.assetid: e05be95c-6732-403d-ae42-b35f057cbbea
caps.latest.revision: 13
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 13
---
# Implizit typisierte Arrays (C#-Programmierhandbuch)
Sie können ein implizit typisiertes Array erstellen, in das der Typ der Arrayinstanz aus den Elementen, die im Arrayinitialisierer angegeben werden, abgeleitet wird.  Die Regeln für implizit typisierte Variablen gelten auch für implizit typisierte Arrays.  Weitere Informationen finden Sie unter [Implizit typisierte lokale Variablen](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md).  
  
 Implizit typisierte Arrays werden normalerweise in Abfrageausdrücken zusammen mit anonymen Typen sowie Objekt\- und Auflistungsinitialisierern verwendet.  
  
 In den folgenden Beispielen wird gezeigt, wie ein implizit typisiertes Array erstellt wird:  
  
 [!code-cs[csProgGuideLINQ#37](../../../csharp/programming-guide/arrays/codesnippet/CSharp/implicitly-typed-arrays_1.cs)]  
  
 Beachten Sie im vorherigen Beispiel, dass bei implizit typisierten Arrays keine rechteckigen Klammern links in der Initialisierungsanweisung verwendet werden.  Beachten Sie auch, dass verzweigte Arrays mit `new []` initialisiert werden, genau wie eindimensionale Arrays.  
  
## Implizit typisierte Arrays in Objektinitialisierern  
 Wenn Sie einen anonymen Typ erstellen, der ein Array enthält, muss das Array im Objektinitialisierer des Typs impliziert typisiert sein.  Im folgenden Beispiel ist `contacts` ein implizit typisiertes Array anonymer Typen, von denen jeder ein Array mit dem Namen `PhoneNumbers` enthält.  Beachten Sie, dass das `var`\-Schlüsselwort nicht in den Objektinitialisierern verwendet wird.  
  
 [!code-cs[csProgGuideLINQ#38](../../../csharp/programming-guide/arrays/codesnippet/CSharp/implicitly-typed-arrays_2.cs)]  
  
## Siehe auch  
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Implizit typisierte lokale Variablen](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md)   
 [Arrays](../../../csharp/programming-guide/arrays/index.md)   
 [Anonyme Typen](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)   
 [Objekt\- und Auflistungsinitialisierer](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md)   
 [var](../../../csharp/language-reference/keywords/var.md)   
 [LINQ\-Abfrageausdrücke](../../../csharp/programming-guide/linq-query-expressions/index.md)