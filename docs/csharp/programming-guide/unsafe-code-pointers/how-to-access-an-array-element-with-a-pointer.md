---
title: "Gewusst wie: Zugreifen auf ein Arrayelement mit einem Zeiger (C#-Programmierhandbuch) | Microsoft Docs"
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
  - "Zeiger [C#], Arrayzugriff"
ms.assetid: 6c46f2af-a730-4855-8638-f136d9abaa12
caps.latest.revision: 16
caps.handback.revision: 16
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Gewusst wie: Zugreifen auf ein Arrayelement mit einem Zeiger (C#-Programmierhandbuch)
In einem unsicheren Kontext können Sie mittels Zeigerelementzugriff auf ein Element im Speicher zugreifen, wie im folgenden Beispiel gezeigt:  
  
```  
 char* charPointer = stackalloc char[123];  
for (int i = 65; i < 123; i++)  
{  
    charPointer[i] = (char)i; //access array elements  
}  
```  
  
 Der Ausdruck in eckigen Klammern muss implizit in `int`, `uint`, `long` oder `ulong` konvertierbar sein.  Die Operation p\[e\] entspricht \*\(p\+e\).  Wie in C und C\+\+ überprüft der Zeigerelementzugriff keine Fehler außerhalb des gültigen Bereichs.  
  
## Beispiel  
 In diesem Beispiel werden dem Zeichenarray `charPointer` 123 Speicheradressen zugeordnet.  Das Array wird verwendet, um die Klein\- und Großbuchstaben in zwei [for](../../../csharp/language-reference/keywords/for.md)\-Schleifen anzuzeigen.  
  
 Beachten Sie, dass der Ausdruck `charPointer[i]` und der Ausdruck `*(charPointer + i)` äquivalent sind. Sie erhalten dasselbe Ergebnis, unabhängig davon, welchen Ausdruck Sie verwenden.  
  
 [!code-cs[csProgGuidePointers#11](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/Pointers/Pointers2.cs#11)]  
  
 [!code-cs[csProgGuidePointers#12](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/Pointers/Pointers.cs#12)]  
  
  **Großbuchstaben:**  
**ABCDEFGHIJKLMNOPQRSTUVWXYZ**  
**Kleinbuchstaben:**  
**abcdefghijklmnopqrstuvwxyz**   
## Siehe auch  
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Zeigerausdrücke](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)   
 [Zeigertypen](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)   
 [Typen](../../../csharp/language-reference/keywords/types.md)   
 [Unsicher](../../../csharp/language-reference/keywords/unsafe.md)   
 [fixed\-Anweisung](../../../csharp/language-reference/keywords/fixed-statement.md)   
 [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md)