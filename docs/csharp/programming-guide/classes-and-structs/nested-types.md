---
title: "Geschachtelte Typen (C#-Programmierhandbuch) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Geschachtelte Typen [C#]"
ms.assetid: f2e1b315-e3d1-48ce-977f-7bae0960ba99
caps.latest.revision: 13
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 13
---
# Geschachtelte Typen (C#-Programmierhandbuch)
Ein innerhalb einer [Klasse](../../../csharp/language-reference/keywords/class.md) oder [Struktur](../../../csharp/language-reference/keywords/struct.md) definierter Typ wird als geschachtelter Typ bezeichnet.  Beispiel:  
  
 [!code-cs[csProgGuideObjects#68](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/nested-types_1.cs)]  
  
 Unabhängig davon, ob die äußeren Typen Klassen oder Strukturen sind, sind geschachtelte Typen standardmäßig auf [private](../../../csharp/language-reference/keywords/private.md) festgelegt, können jedoch auch auf [public](../../../csharp/language-reference/keywords/public.md), protected internal, [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md) oder [private](../../../csharp/language-reference/keywords/private.md) festgelegt werden.  Im vorherigen Beispiel ist `Nested` für externe Typen nicht zugreifbar, kann aber wie folgt öffentlich gemacht werden:  
  
 [!code-cs[csProgGuideObjects#69](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/nested-types_2.cs)]  
  
 Der geschachtelte oder innere Typ kann auf den enthaltenden oder äußeren Typ zugreifen.  Um auf den äußeren \(enthaltenden\) Typ zuzugreifen, übergeben Sie ihn dem geschachtelten Typ als Konstruktor.  Beispiel:  
  
 [!code-cs[csProgGuideObjects#70](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/nested-types_3.cs)]  
  
 Ein geschachtelter Typ hat Zugriff auf alle Member, die für ihren äußeren \(enthaltenden\) Typ zugreifbar sind.  Er kann auf die Member des äußeren \(enthaltenden\) Typs zugreifen, die "private" oder "protected" sind, ebenso auf alle geerbten Member, die "private" oder "protected" sind.  
  
 In der vorherigen Deklaration ist `Container.Nested` der vollständige Name der Klasse `Nested`.  Mit diesem Namen wird wie folgt eine neue Instanz der geschachtelten Klasse erstellt:  
  
 [!code-cs[csProgGuideObjects#71](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/nested-types_4.cs)]  
  
## Siehe auch  
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Klassen und Strukturen](../../../csharp/programming-guide/classes-and-structs/index.md)   
 [Zugriffsmodifizierer](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)   
 [Konstruktoren](../../../csharp/programming-guide/classes-and-structs/constructors.md)