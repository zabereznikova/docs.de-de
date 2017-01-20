---
title: "Gewusst wie: Abrufen der Adresse einer Variablen (C#-Programmierhandbuch) | Microsoft Docs"
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
  - "Zeigerausdrücke [C#], address-of-Operator"
  - "Zeiger [C#], & (Operator)"
  - "Variablen [C#], address of"
ms.assetid: 44fe2cd9-a64f-4ef5-be2a-09ce807c0182
caps.latest.revision: 19
caps.handback.revision: 19
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Gewusst wie: Abrufen der Adresse einer Variablen (C#-Programmierhandbuch)
Sie können den Adressoperator verwenden, um die Adresse eines unären Ausdrucks abzurufen, der eine fixierte Variable ergibt.  
  
```  
int number;  
int* p = &number; //address-of operator &  
```  
  
 Der Adressoperator kann nur auf eine Variable angewendet werden.  Wenn die Variable verschiebbar ist, können Sie die [fixed\-Anweisung](../../../csharp/language-reference/keywords/fixed-statement.md) verwenden, um die Variable vorübergehend zu fixieren, bevor Sie ihre Adresse abrufen.  
  
 Sie müssen dabei selbst sicherzustellen, dass die Variable initialisiert wird.  Der Compiler zeigt keine Fehlermeldung an, wenn die Variable nicht initialisiert wird.  
  
 Die Adresse einer Konstante oder eines Werts kann nicht abgerufen werden.  
  
## Beispiel  
 In diesem Beispiel wird der Zeiger `p` deklariert, der auf `int` zeigt. Anschließend wird dem Zeiger die Adresse der ganzzahligen Variablen `number` zugewiesen.  Die Variable `number` wird als Resultat der Zuweisung zu \*p initialisiert.  Durch Auskommentieren dieser Zuweisung wird die Initialisierung der Variablen `number` entfernt, aber es wird kein Kompilierungsfehler ausgegeben.  Beachten Sie die Verwendung des Operators für den [Memberzugriff](../../../csharp/programming-guide/unsafe-code-pointers/how-to-access-a-member-with-a-pointer.md) \(`->`\), um die im Zeiger gespeicherte Adresse abzurufen und anzuzeigen.  
  
 [!code-cs[csProgGuidePointers#7](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/Pointers/Pointers2.cs#7)]  
  
 [!code-cs[csProgGuidePointers#8](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/Pointers/Pointers.cs#8)]  
  
## Siehe auch  
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Zeigerausdrücke](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)   
 [Zeigertypen](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)   
 [Typen](../../../csharp/language-reference/keywords/types.md)   
 [Unsicher](../../../csharp/language-reference/keywords/unsafe.md)   
 [fixed\-Anweisung](../../../csharp/language-reference/keywords/fixed-statement.md)   
 [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md)