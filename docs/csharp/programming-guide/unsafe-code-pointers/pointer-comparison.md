---
title: "Zeigervergleich (C#-Programmierhandbuch) | Microsoft Docs"
ms.custom: ""
ms.date: "01/05/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Zeiger [C#], Vergleich"
ms.assetid: fcafd514-7405-4deb-8490-cc58efda5495
caps.latest.revision: 14
caps.handback.revision: 14
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Zeigervergleich (C#-Programmierhandbuch)
Sie können die folgenden Operatoren verwenden, um Zeigertypen zu vergleichen:  
  
 **\=\=   \!\=   \<   \>   \<\=   \>\=**  
  
 Die Vergleichsoperatoren vergleichen die Adressen der beiden Operanden, als ob es sich um ganze Zahlen ohne Vorzeichen handelte.  
  
## Beispiel  
 [!code-cs[csProgGuidePointers#16](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/Pointers/Pointers2.cs#16)]  
  
 [!code-cs[csProgGuidePointers#17](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/Pointers/Pointers.cs#17)]  
  
## Beispielausgabe  
 `True`  
  
 `False`  
  
## Siehe auch  
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Zeigerausdrücke](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)   
 [C\#\-Operatoren](../../../csharp/language-reference/operators/index.md)   
 [Bearbeiten von Zeigern](../../../csharp/programming-guide/unsafe-code-pointers/manipulating-pointers.md)   
 [Zeigertypen](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)   
 [Typen](../../../csharp/language-reference/keywords/types.md)   
 [Unsicher](../../../csharp/language-reference/keywords/unsafe.md)   
 [fixed\-Anweisung](../../../csharp/language-reference/keywords/fixed-statement.md)   
 [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md)