---
title: Geschachtelte Typen (C#-Programmierhandbuch)
ms.date: 07/10/2017
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- nested types [C#]
ms.assetid: f2e1b315-e3d1-48ce-977f-7bae0960ba99
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: ab13c68b638062ab89c90dbfc51b51b8d72d3bde
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="nested-types-c-programming-guide"></a>Geschachtelte Typen (C#-Programmierhandbuch)
Ein innerhalb einer [Klasse](../../../csharp/language-reference/keywords/class.md) oder [Struktur](../../../csharp/language-reference/keywords/struct.md) definierter Typ wird als geschachtelter Typ bezeichnet. Zum Beispiel:  
  
[!code-csharp[csProgGuideObjects#68](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/nested-types_1.cs)]  
  
Unabhängig davon, ob der äußere Typ eine Klasse oder eine Struktur ist, lautet die Standardeinstellung von geschachtelten Typen [private](../../../csharp/language-reference/keywords/private.md). Sie sind nur über ihren enthaltenden Typ zugänglich. Im vorherigen Beispiel konnten externe Typen nicht auf die `Nested`-Klasse zugreifen. 

Sie können auch einen [Zugriffsmodifizierer](../../language-reference/keywords/access-modifiers.md) angeben, um den Zugriff auf einen geschachtelten Typ wie folgt zu definieren:

- Geschachtelte Typen von einer **Klasse** kann [öffentlichen](../../../csharp/language-reference/keywords/public.md), [geschützt](../../../csharp/language-reference/keywords/protected.md), [interne](../../../csharp/language-reference/keywords/internal.md), [protected internal](../../../csharp/language-reference/keywords/protected-internal.md), [private](../../../csharp/language-reference/keywords/private.md) oder [privaten, geschützten](../../../csharp/language-reference/keywords/private-protected.md). 

   Definieren Sie jedoch eine `protected`, `protected internal` oder `private protected` geschachtelte Klasse innerhalb einer [versiegelte Klasse](../../language-reference/keywords/sealed.md) compilerwarnung generiert [CS0628](../../misc/cs0628.md), "neuer geschützter Member in einer versiegelten Klasse deklariert."
  
- Geschachtelte Typen einer **Struktur** können öffentlich ([public](../../../csharp/language-reference/keywords/public.md)), intern ([internal](../../../csharp/language-reference/keywords/internal.md)) oder privat ([private](../../../csharp/language-reference/keywords/private.md)) sein.
  
Im folgenden Beispiel wird die `Nested`-Klasse öffentlich gemacht:
  
[!code-csharp[csProgGuideObjects#69](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/nested-types_2.cs)]  
  
 Der geschachtelte oder innere Typ kann auf den enthaltenden oder äußeren Typ zugreifen. Um auf den enthaltenden Typ zuzugreifen, übergeben Sie ihn als Argument dem Konstruktor des geschachtelten Typs. Zum Beispiel:  
  
 [!code-csharp[csProgGuideObjects#70](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/nested-types_3.cs)]  
  
 Ein geschachtelter Typ hat Zugriff auf alle Member, die für ihren äußeren (enthaltenden) Typ zugreifbar sind. Er kann auf die Member des äußeren (enthaltenden) Typs zugreifen, die "private" oder "protected" sind, ebenso auf alle geerbten Member, die "private" oder "protected" sind.  
  
 In der vorherigen Deklaration ist `Nested` der vollständige Name der Klasse `Container.Nested`. Mit diesem Namen wird wie folgt eine neue Instanz der geschachtelten Klasse erstellt:  
  
 [!code-csharp[csProgGuideObjects#71](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/nested-types_4.cs)]  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
 [Klassen und Strukturen](../../../csharp/programming-guide/classes-and-structs/index.md)  
 [Zugriffsmodifizierer](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)  
 [Konstruktoren](../../../csharp/programming-guide/classes-and-structs/constructors.md)
