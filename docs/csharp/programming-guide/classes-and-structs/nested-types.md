---
title: Geschachtelte Typen – C#-Programmierhandbuch
description: Ein innerhalb einer Klasse, Struktur oder Schnittstelle definierter Typ wird in C# als geschachtelter Typ bezeichnet.
ms.date: 02/08/2020
helpviewer_keywords:
- nested types [C#]
ms.assetid: f2e1b315-e3d1-48ce-977f-7bae0960ba99
ms.openlocfilehash: 9e1c6c1e8b22b5447d43915ab02984aa13146301
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/21/2020
ms.locfileid: "86864942"
---
# <a name="nested-types-c-programming-guide"></a><span data-ttu-id="150e6-103">Geschachtelte Typen (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="150e6-103">Nested Types (C# Programming Guide)</span></span>

<span data-ttu-id="150e6-104">Ein innerhalb einer [Klasse](../../language-reference/keywords/class.md), [Struktur](../../language-reference/builtin-types/struct.md) oder [Schnittstelle](../../language-reference/keywords/interface.md) definierter Typ wird als geschachtelter Typ bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="150e6-104">A type defined within a [class](../../language-reference/keywords/class.md), [struct](../../language-reference/builtin-types/struct.md), or [interface](../../language-reference/keywords/interface.md) is called a nested type.</span></span> <span data-ttu-id="150e6-105">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="150e6-105">For example</span></span>

[!code-csharp[DeclareNestedClass](~/samples/snippets/csharp/objectoriented/nestedtypes.cs#DeclareNestedClass)]

<span data-ttu-id="150e6-106">Unabhängig davon, ob es sich beim äußeren Typ um eine Klasse, Schnittstelle oder Struktur handelt, sind geschachtelte Typen standardmäßig [privat](../../language-reference/keywords/private.md), d. h. sie sind nur über den enthaltenden Typ zugänglich.</span><span class="sxs-lookup"><span data-stu-id="150e6-106">Regardless of whether the outer type is a class, interface, or struct, nested types default to [private](../../language-reference/keywords/private.md); they are accessible only from their containing type.</span></span> <span data-ttu-id="150e6-107">Im vorherigen Beispiel konnten externe Typen nicht auf die `Nested`-Klasse zugreifen.</span><span class="sxs-lookup"><span data-stu-id="150e6-107">In the previous example, the `Nested` class is inaccessible to external types.</span></span>

<span data-ttu-id="150e6-108">Sie können auch einen [Zugriffsmodifizierer](../../language-reference/keywords/access-modifiers.md) angeben, um den Zugriff auf einen geschachtelten Typ wie folgt zu definieren:</span><span class="sxs-lookup"><span data-stu-id="150e6-108">You can also specify an [access modifier](../../language-reference/keywords/access-modifiers.md) to define the accessibility of a nested type, as follows:</span></span>

- <span data-ttu-id="150e6-109">Geschachtelte Typen von **class** können [public](../../language-reference/keywords/public.md), [protected](../../language-reference/keywords/protected.md), [internal](../../language-reference/keywords/internal.md), [protected internal](../../language-reference/keywords/protected-internal.md), [private](../../language-reference/keywords/private.md) oder [private protected](../../language-reference/keywords/private-protected.md) sein.</span><span class="sxs-lookup"><span data-stu-id="150e6-109">Nested types of a **class** can be [public](../../language-reference/keywords/public.md), [protected](../../language-reference/keywords/protected.md), [internal](../../language-reference/keywords/internal.md), [protected internal](../../language-reference/keywords/protected-internal.md), [private](../../language-reference/keywords/private.md) or [private protected](../../language-reference/keywords/private-protected.md).</span></span>

   <span data-ttu-id="150e6-110">Durch das Definieren einer geschachtelten `protected`-, `protected internal`- oder `private protected`-Klasse innerhalb einer [versiegelten Klasse](../../language-reference/keywords/sealed.md) wird jedoch die Compilerwarnung [CS0628](../../misc/cs0628.md), „Neuer geschützter Member in versiegelter Klasse deklariert“, generiert.</span><span class="sxs-lookup"><span data-stu-id="150e6-110">However, defining a `protected`, `protected internal` or `private protected` nested class inside a [sealed class](../../language-reference/keywords/sealed.md) generates compiler warning [CS0628](../../misc/cs0628.md), "new protected member declared in sealed class."</span></span>
  
- <span data-ttu-id="150e6-111">Geschachtelte Typen einer **Struktur** können öffentlich ([public](../../language-reference/keywords/public.md)), intern ([internal](../../language-reference/keywords/internal.md)) oder privat ([private](../../language-reference/keywords/private.md)) sein.</span><span class="sxs-lookup"><span data-stu-id="150e6-111">Nested types of a **struct** can be [public](../../language-reference/keywords/public.md), [internal](../../language-reference/keywords/internal.md), or [private](../../language-reference/keywords/private.md).</span></span>

<span data-ttu-id="150e6-112">Im folgenden Beispiel wird die `Nested`-Klasse öffentlich gemacht:</span><span class="sxs-lookup"><span data-stu-id="150e6-112">The following example makes the `Nested` class public:</span></span>

[!code-csharp[PublicNestedClass](~/samples/snippets/csharp/objectoriented/nestedtypes.cs#PublicNestedClass)]

<span data-ttu-id="150e6-113">Der geschachtelte oder innere Typ kann auf den enthaltenden oder äußeren Typ zugreifen.</span><span class="sxs-lookup"><span data-stu-id="150e6-113">The nested, or inner, type can access the containing, or outer, type.</span></span> <span data-ttu-id="150e6-114">Um auf den enthaltenden Typ zuzugreifen, übergeben Sie ihn als Argument dem Konstruktor des geschachtelten Typs.</span><span class="sxs-lookup"><span data-stu-id="150e6-114">To access the containing type, pass it as an argument to the constructor of the nested type.</span></span> <span data-ttu-id="150e6-115">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="150e6-115">For example:</span></span>

[!code-csharp[DeclareNestedInstance](~/samples/snippets/csharp/objectoriented/nestedtypes.cs#DeclareNestedInstance)]

<span data-ttu-id="150e6-116">Ein geschachtelter Typ hat Zugriff auf alle Member, die für ihren äußeren (enthaltenden) Typ zugreifbar sind.</span><span class="sxs-lookup"><span data-stu-id="150e6-116">A nested type has access to all of the members that are accessible to its containing type.</span></span> <span data-ttu-id="150e6-117">Er kann auf die Member des äußeren (enthaltenden) Typs zugreifen, die "private" oder "protected" sind, ebenso auf alle geerbten Member, die "private" oder "protected" sind.</span><span class="sxs-lookup"><span data-stu-id="150e6-117">It can access private and protected members of the containing type, including any inherited protected members.</span></span>

<span data-ttu-id="150e6-118">In der vorherigen Deklaration ist `Nested` der vollständige Name der Klasse `Container.Nested`.</span><span class="sxs-lookup"><span data-stu-id="150e6-118">In the previous declaration, the full name of class `Nested` is `Container.Nested`.</span></span> <span data-ttu-id="150e6-119">Mit diesem Namen wird wie folgt eine neue Instanz der geschachtelten Klasse erstellt:</span><span class="sxs-lookup"><span data-stu-id="150e6-119">This is the name used to create a new instance of the nested class, as follows:</span></span>

[!code-csharp[UseNestedInstance](~/samples/snippets/csharp/objectoriented/nestedtypes.cs#UseNestedInstance)]

## <a name="see-also"></a><span data-ttu-id="150e6-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="150e6-120">See also</span></span>

- [<span data-ttu-id="150e6-121">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="150e6-121">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="150e6-122">Klassen und Strukturen</span><span class="sxs-lookup"><span data-stu-id="150e6-122">Classes and Structs</span></span>](./index.md)
- [<span data-ttu-id="150e6-123">Zugriffsmodifizierer</span><span class="sxs-lookup"><span data-stu-id="150e6-123">Access Modifiers</span></span>](./access-modifiers.md)
- [<span data-ttu-id="150e6-124">Konstruktoren</span><span class="sxs-lookup"><span data-stu-id="150e6-124">Constructors</span></span>](./constructors.md)
