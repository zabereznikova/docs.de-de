---
title: Geschachtelte Typen (C#-Programmierhandbuch)
ms.date: 07/10/2017
helpviewer_keywords:
- nested types [C#]
ms.assetid: f2e1b315-e3d1-48ce-977f-7bae0960ba99
ms.openlocfilehash: 57356fbf4bff218932d1f1b4c62532f10c175757
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="nested-types-c-programming-guide"></a><span data-ttu-id="e6ffb-102">Geschachtelte Typen (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="e6ffb-102">Nested Types (C# Programming Guide)</span></span>
<span data-ttu-id="e6ffb-103">Ein innerhalb einer [Klasse](../../../csharp/language-reference/keywords/class.md) oder [Struktur](../../../csharp/language-reference/keywords/struct.md) definierter Typ wird als geschachtelter Typ bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="e6ffb-103">A type defined within a [class](../../../csharp/language-reference/keywords/class.md) or [struct](../../../csharp/language-reference/keywords/struct.md) is called a nested type.</span></span> <span data-ttu-id="e6ffb-104">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="e6ffb-104">For example:</span></span>  
  
[!code-csharp[csProgGuideObjects#68](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/nested-types_1.cs)]  
  
<span data-ttu-id="e6ffb-105">Unabhängig davon, ob der äußere Typ eine Klasse oder eine Struktur ist, lautet die Standardeinstellung von geschachtelten Typen [private](../../../csharp/language-reference/keywords/private.md). Sie sind nur über ihren enthaltenden Typ zugänglich.</span><span class="sxs-lookup"><span data-stu-id="e6ffb-105">Regardless of whether the outer type is a class or a struct, nested types default to [private](../../../csharp/language-reference/keywords/private.md); they are accessible only from their containing type.</span></span> <span data-ttu-id="e6ffb-106">Im vorherigen Beispiel konnten externe Typen nicht auf die `Nested`-Klasse zugreifen.</span><span class="sxs-lookup"><span data-stu-id="e6ffb-106">In the previous example, the `Nested` class is inaccessible to external types.</span></span> 

<span data-ttu-id="e6ffb-107">Sie können auch einen [Zugriffsmodifizierer](../../language-reference/keywords/access-modifiers.md) angeben, um den Zugriff auf einen geschachtelten Typ wie folgt zu definieren:</span><span class="sxs-lookup"><span data-stu-id="e6ffb-107">You can also specify an [access modifier](../../language-reference/keywords/access-modifiers.md) to define the accessibility of a nested type, as follows:</span></span>

- <span data-ttu-id="e6ffb-108">Geschachtelte Typen von **class** können [public](../../../csharp/language-reference/keywords/public.md), [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md), [protected internal](../../../csharp/language-reference/keywords/protected-internal.md), [private](../../../csharp/language-reference/keywords/private.md) oder [private protected](../../../csharp/language-reference/keywords/private-protected.md) sein.</span><span class="sxs-lookup"><span data-stu-id="e6ffb-108">Nested types of a **class** can be [public](../../../csharp/language-reference/keywords/public.md), [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md), [protected internal](../../../csharp/language-reference/keywords/protected-internal.md), [private](../../../csharp/language-reference/keywords/private.md) or [private protected](../../../csharp/language-reference/keywords/private-protected.md).</span></span> 

   <span data-ttu-id="e6ffb-109">Durch das Definieren einer geschachtelten `protected`-, `protected internal`- oder `private protected`-Klasse innerhalb einer [versiegelten Klasse](../../language-reference/keywords/sealed.md) wird jedoch die Compilerwarnung [CS0628](../../misc/cs0628.md), „Neuer geschützter Member in versiegelter Klasse deklariert“, generiert.</span><span class="sxs-lookup"><span data-stu-id="e6ffb-109">However, defining a `protected`, `protected internal` or `private protected` nested class inside a [sealed class](../../language-reference/keywords/sealed.md) generates compiler warning [CS0628](../../misc/cs0628.md), "new protected member declared in sealed class."</span></span>
  
- <span data-ttu-id="e6ffb-110">Geschachtelte Typen einer **Struktur** können öffentlich ([public](../../../csharp/language-reference/keywords/public.md)), intern ([internal](../../../csharp/language-reference/keywords/internal.md)) oder privat ([private](../../../csharp/language-reference/keywords/private.md)) sein.</span><span class="sxs-lookup"><span data-stu-id="e6ffb-110">Nested types of a **struct** can be [public](../../../csharp/language-reference/keywords/public.md), [internal](../../../csharp/language-reference/keywords/internal.md), or [private](../../../csharp/language-reference/keywords/private.md).</span></span>
  
<span data-ttu-id="e6ffb-111">Im folgenden Beispiel wird die `Nested`-Klasse öffentlich gemacht:</span><span class="sxs-lookup"><span data-stu-id="e6ffb-111">The following example makes the `Nested` class public:</span></span>
  
[!code-csharp[csProgGuideObjects#69](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/nested-types_2.cs)]  
  
 <span data-ttu-id="e6ffb-112">Der geschachtelte oder innere Typ kann auf den enthaltenden oder äußeren Typ zugreifen.</span><span class="sxs-lookup"><span data-stu-id="e6ffb-112">The nested, or inner, type can access the containing, or outer, type.</span></span> <span data-ttu-id="e6ffb-113">Um auf den enthaltenden Typ zuzugreifen, übergeben Sie ihn als Argument dem Konstruktor des geschachtelten Typs.</span><span class="sxs-lookup"><span data-stu-id="e6ffb-113">To access the containing type, pass it as an argument to the constructor of the nested type.</span></span> <span data-ttu-id="e6ffb-114">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="e6ffb-114">For example:</span></span>  
  
 [!code-csharp[csProgGuideObjects#70](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/nested-types_3.cs)]  
  
 <span data-ttu-id="e6ffb-115">Ein geschachtelter Typ hat Zugriff auf alle Member, die für ihren äußeren (enthaltenden) Typ zugreifbar sind.</span><span class="sxs-lookup"><span data-stu-id="e6ffb-115">A nested type has access to all of the members that are accessible to its containing type.</span></span> <span data-ttu-id="e6ffb-116">Er kann auf die Member des äußeren (enthaltenden) Typs zugreifen, die "private" oder "protected" sind, ebenso auf alle geerbten Member, die "private" oder "protected" sind.</span><span class="sxs-lookup"><span data-stu-id="e6ffb-116">It can access private and protected members of the containing type, including any inherited protected members.</span></span>  
  
 <span data-ttu-id="e6ffb-117">In der vorherigen Deklaration ist `Nested` der vollständige Name der Klasse `Container.Nested`.</span><span class="sxs-lookup"><span data-stu-id="e6ffb-117">In the previous declaration, the full name of class `Nested` is `Container.Nested`.</span></span> <span data-ttu-id="e6ffb-118">Mit diesem Namen wird wie folgt eine neue Instanz der geschachtelten Klasse erstellt:</span><span class="sxs-lookup"><span data-stu-id="e6ffb-118">This is the name used to create a new instance of the nested class, as follows:</span></span>  
  
 [!code-csharp[csProgGuideObjects#71](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/nested-types_4.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="e6ffb-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e6ffb-119">See Also</span></span>  
 [<span data-ttu-id="e6ffb-120">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="e6ffb-120">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="e6ffb-121">Klassen und Strukturen</span><span class="sxs-lookup"><span data-stu-id="e6ffb-121">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)  
 [<span data-ttu-id="e6ffb-122">Zugriffsmodifizierer</span><span class="sxs-lookup"><span data-stu-id="e6ffb-122">Access Modifiers</span></span>](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)  
 [<span data-ttu-id="e6ffb-123">Konstruktoren</span><span class="sxs-lookup"><span data-stu-id="e6ffb-123">Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/constructors.md)
