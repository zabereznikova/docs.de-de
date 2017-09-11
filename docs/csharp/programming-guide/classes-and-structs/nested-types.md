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
# <a name="nested-types-c-programming-guide"></a><span data-ttu-id="f433e-102">Geschachtelte Typen (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="f433e-102">Nested Types (C# Programming Guide)</span></span>
<span data-ttu-id="f433e-103">Ein innerhalb einer [Klasse](../../../csharp/language-reference/keywords/class.md) oder [Struktur](../../../csharp/language-reference/keywords/struct.md) definierter Typ wird als geschachtelter Typ bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="f433e-103">A type defined within a [class](../../../csharp/language-reference/keywords/class.md) or [struct](../../../csharp/language-reference/keywords/struct.md) is called a nested type.</span></span> <span data-ttu-id="f433e-104">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="f433e-104">For example:</span></span>  
  
<span data-ttu-id="f433e-105">[!code-cs[csProgGuideObjects#68](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/nested-types_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="f433e-105">[!code-cs[csProgGuideObjects#68](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/nested-types_1.cs)]</span></span>  
  
<span data-ttu-id="f433e-106">Unabhängig davon, ob der äußere Typ eine Klasse oder eine Struktur ist, lautet die Standardeinstellung von geschachtelten Typen [private](../../../csharp/language-reference/keywords/private.md). Sie sind nur über ihren enthaltenden Typ zugänglich.</span><span class="sxs-lookup"><span data-stu-id="f433e-106">Regardless of whether the outer type is a class or a struct, nested types default to [private](../../../csharp/language-reference/keywords/private.md); they are accessible only from their containing type.</span></span> <span data-ttu-id="f433e-107">Im vorherigen Beispiel konnten externe Typen nicht auf die `Nested`-Klasse zugreifen.</span><span class="sxs-lookup"><span data-stu-id="f433e-107">In the previous example, the `Nested` class is inaccessible to external types.</span></span> 

<span data-ttu-id="f433e-108">Sie können auch einen [Zugriffsmodifizierer](../../language-reference/keywords/access-modifiers.md) angeben, um den Zugriff auf einen geschachtelten Typ wie folgt zu definieren:</span><span class="sxs-lookup"><span data-stu-id="f433e-108">You can also specify an [access modifier](../../language-reference/keywords/access-modifiers.md) to define the accessibility of a nested type, as follows:</span></span>

- <span data-ttu-id="f433e-109">Geschachtelte Typen einer **Klasse** können öffentlich ([public](../../../csharp/language-reference/keywords/public.md)), geschützt ([protected](../../../csharp/language-reference/keywords/protected.md)), intern ([internal](../../../csharp/language-reference/keywords/internal.md)), intern geschützt (`protected internal`) oder privat ([private](../../../csharp/language-reference/keywords/private.md)) sein.</span><span class="sxs-lookup"><span data-stu-id="f433e-109">Nested types of a **class** can be [public](../../../csharp/language-reference/keywords/public.md), [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md), `protected internal`, or [private](../../../csharp/language-reference/keywords/private.md).</span></span> 

   <span data-ttu-id="f433e-110">Durch das Definieren einer geschachtelten `protected`- oder `protected internal`-Klasse innerhalb einer [versiegelten Klasse](../../language-reference/keywords/sealed.md) wird jedoch die Compilerwarnung generiert [CS0628](../../misc/cs0628.md), „Neues geschütztes Element deklariert in versiegelter Klasse“, generiert.</span><span class="sxs-lookup"><span data-stu-id="f433e-110">However, defining a `protected` or `protected internal` nested class inside a [sealed class](../../language-reference/keywords/sealed.md) generates compiler warning [CS0628](../../misc/cs0628.md), "new protected member declared in sealed class."</span></span>
  
- <span data-ttu-id="f433e-111">Geschachtelte Typen einer **Struktur** können öffentlich ([public](../../../csharp/language-reference/keywords/public.md)), intern ([internal](../../../csharp/language-reference/keywords/internal.md)) oder privat ([private](../../../csharp/language-reference/keywords/private.md)) sein.</span><span class="sxs-lookup"><span data-stu-id="f433e-111">Nested types of a **struct** can be [public](../../../csharp/language-reference/keywords/public.md), [internal](../../../csharp/language-reference/keywords/internal.md), or [private](../../../csharp/language-reference/keywords/private.md).</span></span>
  
<span data-ttu-id="f433e-112">Im folgenden Beispiel wird die `Nested`-Klasse öffentlich gemacht:</span><span class="sxs-lookup"><span data-stu-id="f433e-112">The following example makes the `Nested` class public:</span></span>
  
<span data-ttu-id="f433e-113">[!code-cs[csProgGuideObjects#69](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/nested-types_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="f433e-113">[!code-cs[csProgGuideObjects#69](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/nested-types_2.cs)]</span></span>  
  
 <span data-ttu-id="f433e-114">Der geschachtelte oder innere Typ kann auf den enthaltenden oder äußeren Typ zugreifen.</span><span class="sxs-lookup"><span data-stu-id="f433e-114">The nested, or inner, type can access the containing, or outer, type.</span></span> <span data-ttu-id="f433e-115">Um auf den enthaltenden Typ zuzugreifen, übergeben Sie ihn als Argument dem Konstruktor des geschachtelten Typs.</span><span class="sxs-lookup"><span data-stu-id="f433e-115">To access the containing type, pass it as an argument to the constructor of the nested type.</span></span> <span data-ttu-id="f433e-116">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="f433e-116">For example:</span></span>  
  
 <span data-ttu-id="f433e-117">[!code-cs[csProgGuideObjects#70](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/nested-types_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="f433e-117">[!code-cs[csProgGuideObjects#70](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/nested-types_3.cs)]</span></span>  
  
 <span data-ttu-id="f433e-118">Ein geschachtelter Typ hat Zugriff auf alle Member, die für ihren äußeren (enthaltenden) Typ zugreifbar sind.</span><span class="sxs-lookup"><span data-stu-id="f433e-118">A nested type has access to all of the members that are accessible to its containing type.</span></span> <span data-ttu-id="f433e-119">Er kann auf die Member des äußeren (enthaltenden) Typs zugreifen, die "private" oder "protected" sind, ebenso auf alle geerbten Member, die "private" oder "protected" sind.</span><span class="sxs-lookup"><span data-stu-id="f433e-119">It can access private and protected members of the containing type, including any inherited protected members.</span></span>  
  
 <span data-ttu-id="f433e-120">In der vorherigen Deklaration ist `Nested` der vollständige Name der Klasse `Container.Nested`.</span><span class="sxs-lookup"><span data-stu-id="f433e-120">In the previous declaration, the full name of class `Nested` is `Container.Nested`.</span></span> <span data-ttu-id="f433e-121">Mit diesem Namen wird wie folgt eine neue Instanz der geschachtelten Klasse erstellt:</span><span class="sxs-lookup"><span data-stu-id="f433e-121">This is the name used to create a new instance of the nested class, as follows:</span></span>  
  
 <span data-ttu-id="f433e-122">[!code-cs[csProgGuideObjects#71](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/nested-types_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="f433e-122">[!code-cs[csProgGuideObjects#71](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/nested-types_4.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f433e-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f433e-123">See Also</span></span>  
 <span data-ttu-id="f433e-124">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="f433e-124">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="f433e-125">[Klassen und Strukturen](../../../csharp/programming-guide/classes-and-structs/index.md) </span><span class="sxs-lookup"><span data-stu-id="f433e-125">[Classes and Structs](../../../csharp/programming-guide/classes-and-structs/index.md) </span></span>  
 <span data-ttu-id="f433e-126">[Zugriffsmodifizierer](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="f433e-126">[Access Modifiers](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md) </span></span>  
 [<span data-ttu-id="f433e-127">Konstruktoren</span><span class="sxs-lookup"><span data-stu-id="f433e-127">Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/constructors.md)

