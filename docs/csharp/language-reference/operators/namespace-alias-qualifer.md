---
title: "Operator :: (C#-Referenz) | Microsoft Docs"
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
  - "::_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "::-Operator [C#]"
  - "Operator für die Qualifizierung eines Namespacealias (::) [C#]"
  - "Namespaces [C#], ::-Operator"
ms.assetid: 698b5a73-85cf-4e0e-9e8e-6496887f8527
caps.latest.revision: 21
caps.handback.revision: 21
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Operator :: (C#-Referenz)
Der Namespacealiasqualifizierer \(`::`\) wird verwendet, um nach Bezeichnern zu suchen.  Er wird immer zwischen zwei Bezeichnern angeordnet, wie in diesem Beispiel:  
  
 [!code-cs[csRefOperators#27](../../../csharp/language-reference/operators/codesnippet/CSharp/csrefOperators/csrefOperators.cs#27)]  
  
## Hinweise  
 Der Namespacealiasqualifizierer kann `global` sein.  Dies ruft eine Suche im globalen Namespace auf statt in einem Aliasnamespace.  
  
## Weitere Informationen  
 Ein Beispiel für die Verwendung des Operators `::` finden Sie im folgenden Abschnitt:  
  
-   [Gewusst wie: Verwenden des globalen Namespacealias](../../../csharp/programming-guide/namespaces/how-to-use-the-global-namespace-alias.md)  
  
## C\#\-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Siehe auch  
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C\#\-Operatoren](../../../csharp/language-reference/operators/index.md)   
 [Namespaceschlüsselwörter](../../../csharp/language-reference/keywords/namespace-keywords.md)   
 [. Operator](../../../csharp/language-reference/operators/member-access-operator.md)   
 [extern\-Alias](../../../csharp/language-reference/keywords/extern-alias.md)