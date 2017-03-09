---
title: "Arithmetische Operationen f&#252;r Zeiger (C#-Programmierhandbuch) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Zeiger [C#], Arithmetische Operationen"
ms.assetid: d4f0b623-827e-45ce-8649-cfcebc8692aa
caps.latest.revision: 18
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 18
---
# Arithmetische Operationen f&#252;r Zeiger (C#-Programmierhandbuch)
Dieses Thema behandelt die Bearbeitung von Zeigern mithilfe der arithmetischen Operatoren `+` und **\-**.  
  
> [!NOTE]
>  Sie können keine arithmetischen Operationen auf void\-Zeigern ausführen.  
  
## Addieren und Subtrahieren von numerischen Werten zu bzw. von Zeigern  
 Sie können einen Wert `n` vom Typ [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md) oder [ulong](../../../csharp/language-reference/keywords/ulong.md) einem Zeiger `p` `` beliebigen Typs außer `void*` hinzufügen.  Das Ergebnis `p+n` ist der Zeiger, der sich aus der Addition `n * sizeof(p) to the address of p` ergibt.  Auf ähnliche Weise ist `p-n` der Zeiger, der sich ergibt, wenn `n * sizeof(p)` von der Adresse von `p` subtrahiert wird.  
  
## Subtrahieren von Zeigern  
 Sie können auch Zeiger mit identischem Typ subtrahieren.  Das Ergebnis ist immer vom Typ `long`.  Wenn z. B. `p1` und `p2` Zeiger des Typs `pointer-type*` sind, dann ergibt der Ausdruck `p1-p2`:  
  
 `((long)p1 - (long)p2)/sizeof(pointer_type)`  
  
 Es werden keine Ausnahmen generiert, wenn die arithmetische Operation die Domänengrenzen des Zeigertyps überschreitet, und das Ergebnis hängt von der Implementierung ab.  
  
## Beispiel  
 [!code-cs[csProgGuidePointers#14](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/csharp/Pointers/Pointers2.cs#14)]  
  
 [!code-cs[csProgGuidePointers#15](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/csharp/Pointers/Pointers.cs#15)]  
  
## C\#\-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Siehe auch  
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Unsicherer Code und Zeiger](../../../csharp/programming-guide/unsafe-code-pointers/index.md)   
 [Zeigerausdrücke](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)   
 [C\#\-Operatoren](../../../csharp/language-reference/operators/index.md)   
 [Bearbeiten von Zeigern](../../../csharp/programming-guide/unsafe-code-pointers/manipulating-pointers.md)   
 [Zeigertypen](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)   
 [Typen](../../../csharp/language-reference/keywords/types.md)   
 [Unsicher](../../../csharp/language-reference/keywords/unsafe.md)   
 [fixed\-Anweisung](../../../csharp/language-reference/keywords/fixed-statement.md)   
 [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md)