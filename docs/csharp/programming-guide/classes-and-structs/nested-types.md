---
title: Geschachtelte Typen – C#-Programmierhandbuch
description: Ein innerhalb einer Klasse, Struktur oder Schnittstelle definierter Typ wird in C# als geschachtelter Typ bezeichnet.
ms.date: 02/08/2020
helpviewer_keywords:
- nested types [C#]
ms.assetid: f2e1b315-e3d1-48ce-977f-7bae0960ba99
ms.openlocfilehash: 0741ae88103b16ce34fd5a38b789beaf428e734a
ms.sourcegitcommit: 0014aa4d5cb2da56a70e03fc68f663d64df5247a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/09/2020
ms.locfileid: "96918579"
---
# <a name="nested-types-c-programming-guide"></a><span data-ttu-id="ad042-103">Geschachtelte Typen (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="ad042-103">Nested Types (C# Programming Guide)</span></span>

<span data-ttu-id="ad042-104">Typen, die in einer [Klasse](../../language-reference/keywords/class.md), einer [Struktur](../../language-reference/builtin-types/struct.md), einem [Delegat](../../language-reference/builtin-types/reference-types.md#the-delegate-type) oder einer [Schnittstelle](../../language-reference/keywords/interface.md) definiert werden, werden als geschachtelte Typen bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="ad042-104">A type defined within a [class](../../language-reference/keywords/class.md), [struct](../../language-reference/builtin-types/struct.md), [delegate](../../language-reference/builtin-types/reference-types.md#the-delegate-type) or [interface](../../language-reference/keywords/interface.md) is called a nested type.</span></span> <span data-ttu-id="ad042-105">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="ad042-105">For example</span></span>

[!code-csharp[DeclareNestedClass](~/samples/snippets/csharp/objectoriented/nestedtypes.cs#DeclareNestedClass)]

<span data-ttu-id="ad042-106">Unabhängig davon, ob es sich beim äußeren Typ um eine Klasse, Schnittstelle oder Struktur handelt, sind geschachtelte Typen standardmäßig [privat](../../language-reference/keywords/private.md), d. h. sie sind nur über den enthaltenden Typ zugänglich.</span><span class="sxs-lookup"><span data-stu-id="ad042-106">Regardless of whether the outer type is a class, interface, or struct, nested types default to [private](../../language-reference/keywords/private.md); they are accessible only from their containing type.</span></span> <span data-ttu-id="ad042-107">Im vorherigen Beispiel konnten externe Typen nicht auf die `Nested`-Klasse zugreifen.</span><span class="sxs-lookup"><span data-stu-id="ad042-107">In the previous example, the `Nested` class is inaccessible to external types.</span></span>

<span data-ttu-id="ad042-108">Sie können auch einen [Zugriffsmodifizierer](../../language-reference/keywords/access-modifiers.md) angeben, um den Zugriff auf einen geschachtelten Typ wie folgt zu definieren:</span><span class="sxs-lookup"><span data-stu-id="ad042-108">You can also specify an [access modifier](../../language-reference/keywords/access-modifiers.md) to define the accessibility of a nested type, as follows:</span></span>

- <span data-ttu-id="ad042-109">Geschachtelte Typen von **class** können [public](../../language-reference/keywords/public.md), [protected](../../language-reference/keywords/protected.md), [internal](../../language-reference/keywords/internal.md), [protected internal](../../language-reference/keywords/protected-internal.md), [private](../../language-reference/keywords/private.md) oder [private protected](../../language-reference/keywords/private-protected.md) sein.</span><span class="sxs-lookup"><span data-stu-id="ad042-109">Nested types of a **class** can be [public](../../language-reference/keywords/public.md), [protected](../../language-reference/keywords/protected.md), [internal](../../language-reference/keywords/internal.md), [protected internal](../../language-reference/keywords/protected-internal.md), [private](../../language-reference/keywords/private.md) or [private protected](../../language-reference/keywords/private-protected.md).</span></span>

   <span data-ttu-id="ad042-110">Durch das Definieren einer geschachtelten `protected`-, `protected internal`- oder `private protected`-Klasse innerhalb einer [versiegelten Klasse](../../language-reference/keywords/sealed.md) wird jedoch die Compilerwarnung [CS0628](../../misc/cs0628.md), „Neuer geschützter Member in versiegelter Klasse deklariert“, generiert.</span><span class="sxs-lookup"><span data-stu-id="ad042-110">However, defining a `protected`, `protected internal` or `private protected` nested class inside a [sealed class](../../language-reference/keywords/sealed.md) generates compiler warning [CS0628](../../misc/cs0628.md), "new protected member declared in sealed class."</span></span>
  
- <span data-ttu-id="ad042-111">Geschachtelte Typen einer **Struktur** können öffentlich ([public](../../language-reference/keywords/public.md)), intern ([internal](../../language-reference/keywords/internal.md)) oder privat ([private](../../language-reference/keywords/private.md)) sein.</span><span class="sxs-lookup"><span data-stu-id="ad042-111">Nested types of a **struct** can be [public](../../language-reference/keywords/public.md), [internal](../../language-reference/keywords/internal.md), or [private](../../language-reference/keywords/private.md).</span></span>

<span data-ttu-id="ad042-112">Im folgenden Beispiel wird die `Nested`-Klasse öffentlich gemacht:</span><span class="sxs-lookup"><span data-stu-id="ad042-112">The following example makes the `Nested` class public:</span></span>

[!code-csharp[PublicNestedClass](~/samples/snippets/csharp/objectoriented/nestedtypes.cs#PublicNestedClass)]

<span data-ttu-id="ad042-113">Der geschachtelte oder innere Typ kann auf den enthaltenden oder äußeren Typ zugreifen.</span><span class="sxs-lookup"><span data-stu-id="ad042-113">The nested, or inner, type can access the containing, or outer, type.</span></span> <span data-ttu-id="ad042-114">Um auf den enthaltenden Typ zuzugreifen, übergeben Sie ihn als Argument dem Konstruktor des geschachtelten Typs.</span><span class="sxs-lookup"><span data-stu-id="ad042-114">To access the containing type, pass it as an argument to the constructor of the nested type.</span></span> <span data-ttu-id="ad042-115">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="ad042-115">For example:</span></span>

[!code-csharp[DeclareNestedInstance](~/samples/snippets/csharp/objectoriented/nestedtypes.cs#DeclareNestedInstance)]

<span data-ttu-id="ad042-116">Ein geschachtelter Typ hat Zugriff auf alle Member, die für ihren äußeren (enthaltenden) Typ zugreifbar sind.</span><span class="sxs-lookup"><span data-stu-id="ad042-116">A nested type has access to all of the members that are accessible to its containing type.</span></span> <span data-ttu-id="ad042-117">Er kann auf die Member des äußeren (enthaltenden) Typs zugreifen, die "private" oder "protected" sind, ebenso auf alle geerbten Member, die "private" oder "protected" sind.</span><span class="sxs-lookup"><span data-stu-id="ad042-117">It can access private and protected members of the containing type, including any inherited protected members.</span></span>

<span data-ttu-id="ad042-118">In der vorherigen Deklaration ist `Nested` der vollständige Name der Klasse `Container.Nested`.</span><span class="sxs-lookup"><span data-stu-id="ad042-118">In the previous declaration, the full name of class `Nested` is `Container.Nested`.</span></span> <span data-ttu-id="ad042-119">Mit diesem Namen wird wie folgt eine neue Instanz der geschachtelten Klasse erstellt:</span><span class="sxs-lookup"><span data-stu-id="ad042-119">This is the name used to create a new instance of the nested class, as follows:</span></span>

[!code-csharp[UseNestedInstance](~/samples/snippets/csharp/objectoriented/nestedtypes.cs#UseNestedInstance)]

## <a name="see-also"></a><span data-ttu-id="ad042-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ad042-120">See also</span></span>

- [<span data-ttu-id="ad042-121">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="ad042-121">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="ad042-122">Klassen und Strukturen</span><span class="sxs-lookup"><span data-stu-id="ad042-122">Classes and Structs</span></span>](./index.md)
- [<span data-ttu-id="ad042-123">Zugriffsmodifizierer</span><span class="sxs-lookup"><span data-stu-id="ad042-123">Access Modifiers</span></span>](./access-modifiers.md)
- [<span data-ttu-id="ad042-124">Konstruktoren</span><span class="sxs-lookup"><span data-stu-id="ad042-124">Constructors</span></span>](./constructors.md)
