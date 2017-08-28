---
title: Geschachtelte Typen (C#-Programmierhandbuch)
ms.date: 2017-07-10
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- nested types [C#]
ms.assetid: f2e1b315-e3d1-48ce-977f-7bae0960ba99
caps.latest.revision: 13
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 853ec746d9be01ed63d7a229ca86e99d9f192374
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="nested-types-c-programming-guide"></a>Geschachtelte Typen (C#-Programmierhandbuch)
Ein innerhalb einer [Klasse](../../../csharp/language-reference/keywords/class.md) oder [Struktur](../../../csharp/language-reference/keywords/struct.md) definierter Typ wird als geschachtelter Typ bezeichnet. Zum Beispiel:  
  
[!code-cs[csProgGuideObjects#68](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/nested-types_1.cs)]  
  
Unabhängig davon, ob der äußere Typ eine Klasse oder eine Struktur ist, lautet die Standardeinstellung von geschachtelten Typen [private](../../../csharp/language-reference/keywords/private.md). Sie sind nur über ihren enthaltenden Typ zugänglich. Im vorherigen Beispiel konnten externe Typen nicht auf die `Nested`-Klasse zugreifen. 

Sie können auch einen [Zugriffsmodifizierer](../../language-reference/keywords/access-modifiers.md) angeben, um den Zugriff auf einen geschachtelten Typ wie folgt zu definieren:

- Geschachtelte Typen einer **Klasse** können öffentlich ([public](../../../csharp/language-reference/keywords/public.md)), geschützt ([protected](../../../csharp/language-reference/keywords/protected.md)), intern ([internal](../../../csharp/language-reference/keywords/internal.md)), intern geschützt (`protected internal`) oder privat ([private](../../../csharp/language-reference/keywords/private.md)) sein. 

   Durch das Definieren einer geschachtelten `protected`- oder `protected internal`-Klasse innerhalb einer [versiegelten Klasse](../../language-reference/keywords/sealed.md) wird jedoch die Compilerwarnung generiert [CS0628](../../misc/cs0628.md), „Neues geschütztes Element deklariert in versiegelter Klasse“, generiert.
  
- Geschachtelte Typen einer **Struktur** können öffentlich ([public](../../../csharp/language-reference/keywords/public.md)), intern ([internal](../../../csharp/language-reference/keywords/internal.md)) oder privat ([private](../../../csharp/language-reference/keywords/private.md)) sein.
  
Im folgenden Beispiel wird die `Nested`-Klasse öffentlich gemacht:
  
[!code-cs[csProgGuideObjects#69](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/nested-types_2.cs)]  
  
 Der geschachtelte oder innere Typ kann auf den enthaltenden oder äußeren Typ zugreifen. Um auf den enthaltenden Typ zuzugreifen, übergeben Sie ihn als Argument dem Konstruktor des geschachtelten Typs. Zum Beispiel:  
  
 [!code-cs[csProgGuideObjects#70](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/nested-types_3.cs)]  
  
 Ein geschachtelter Typ hat Zugriff auf alle Member, die für ihren äußeren (enthaltenden) Typ zugreifbar sind. Er kann auf die Member des äußeren (enthaltenden) Typs zugreifen, die "private" oder "protected" sind, ebenso auf alle geerbten Member, die "private" oder "protected" sind.  
  
 In der vorherigen Deklaration ist `Nested` der vollständige Name der Klasse `Container.Nested`. Mit diesem Namen wird wie folgt eine neue Instanz der geschachtelten Klasse erstellt:  
  
 [!code-cs[csProgGuideObjects#71](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/nested-types_4.cs)]  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Klassen und Strukturen](../../../csharp/programming-guide/classes-and-structs/index.md)   
 [Zugriffsmodifizierer](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)   
 [Konstruktoren](../../../csharp/programming-guide/classes-and-structs/constructors.md)

