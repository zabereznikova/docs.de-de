---
title: "Gewusst wie: Abrufen des Werts einer Zeigervariablen (C#-Programmierhandbuch) | Microsoft Docs"
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
  - "Zeigerausdrücke [C#], Dereferenzierung"
  - "Zeiger [C#], *-Operator"
  - "Zeiger [C#], Dereferenzierung"
  - "Variablen [C#], Zeiger"
ms.assetid: 460a813a-4995-44c1-9de2-213b91dc7668
caps.latest.revision: 17
caps.handback.revision: 17
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Gewusst wie: Abrufen des Werts einer Zeigervariablen (C#-Programmierhandbuch)
Verwenden Sie den Zeigerdereferenzierungsoperator, um die Variable an dem Speicherort abzurufen, auf den der Zeiger verweist.  Der Ausdruck hat das folgende Format, wobei  `p` ein Zeigertyp ist:  
  
```  
*p;  
```  
  
 Der unäre Dereferenzierungsoperator kann nur auf Ausdrücke angewendet werden, die vom Zeigertyp sind.  Außerdem kann er nicht auf einen [void](../../../csharp/language-reference/keywords/void.md)\-Zeiger angewendet werden.  
  
 Das Ergebnis einer Anwendung des Dereferenzierungsoperators auf einen [NULL](../../../csharp/language-reference/keywords/null.md)\-Zeiger hängt von der Implementierung ab.  
  
## Beispiel  
 Im folgenden Beispiel wird mit Zeigern verschiedener Typen auf eine Variable vom Typ `char` zugegriffen.  Beachten Sie, dass die Adresse von `theChar` von Ausführung zu Ausführung variiert, da die für eine Variable reservierte physikalische Speicheradresse nicht immer dieselbe ist.  
  
 [!code-cs[csProgGuidePointers#5](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/Pointers/Pointers2.cs#5)]  
  
 [!code-cs[csProgGuidePointers#6](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/Pointers/Pointers.cs#6)]  
  
  **Value of theChar \= Z**   
**Address of theChar \= 12F718**  
**Value of pChar \= Z**   
**Value of pInt \= 90**    
## Siehe auch  
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Zeigerausdrücke](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)   
 [Zeigertypen](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)   
 [Typen](../../../csharp/language-reference/keywords/types.md)   
 [Unsicher](../../../csharp/language-reference/keywords/unsafe.md)   
 [fixed\-Anweisung](../../../csharp/language-reference/keywords/fixed-statement.md)   
 [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md)