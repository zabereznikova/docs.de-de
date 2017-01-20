---
title: "Gewusst wie: Inkrementieren und Dekrementieren von Zeigern (C#-Programmierhandbuch) | Microsoft Docs"
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
  - "Zeigerausdrücke [C#], Inkrementieren und Dekrementieren"
  - "Zeiger [C#], Inkrementieren und Dekrementieren"
ms.assetid: 1b8b9281-44ee-485a-9045-3db38a4b4b89
caps.latest.revision: 20
caps.handback.revision: 20
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Gewusst wie: Inkrementieren und Dekrementieren von Zeigern (C#-Programmierhandbuch)
Verwenden Sie die Operatoren zum Inkrementieren und Dekrementieren \(`++` und `--`\), um die Zeigerposition eines Zeigers vom Typ pointer\-type\* um [sizeof](../../../csharp/language-reference/keywords/sizeof.md) \(`pointer-type`\) zu ändern.  Die Ausdrücke zum Inkrementieren und Dekrementieren haben folgende Form:  
  
```  
++p;  
p++;  
--p;  
p--;  
```  
  
 Die Operatoren "Inkrement" und "Dekrement" können mit Ausnahme des `void*`\-Typs auf Zeiger jeden Typs angewendet werden.  
  
 Durch die Anwendung des Operators "Inkrement" auf einen Zeiger vom Typ `pointer-type` wird [sizeof](../../../csharp/language-reference/keywords/sizeof.md) \(`pointer-type`\) zur Adresse hinzugefügt, die in der Zeigervariablen enthalten ist.  
  
 Durch die Anwendung des Operators "Dekrement" auf einen Zeiger vom Typ `pointer-type` wird `sizeof` \(`pointer-type`\) aus der Adresse entfernt, die in der Zeigervariablen enthalten ist.  
  
 Es werden keine Ausnahmen generiert, wenn die Operation die Domänengrenzen des Zeigertyps überschreitet, und das Ergebnis hängt von der Implementierung ab.  
  
## Beispiel  
 In diesem Beispiel wird ein Array schrittweise durchlaufen, indem der Zeiger um die Größe von `int` erhöht wird.  Mit jedem Schritt wird die Adresse und der Inhalt des Arrayelements angezeigt.  
  
 [!code-cs[csProgGuidePointers#3](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/Pointers/Pointers2.cs#3)]  
  
 [!code-cs[csProgGuidePointers#13](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/Pointers/Pointers.cs#13)]  
  
  **Value:0 @ Address:12860272**  
**Value:1 @ Address:12860276**  
**Value:2 @ Address:12860280**  
**Value:3 @ Address:12860284**  
**Value:4 @ Address:12860288**   
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