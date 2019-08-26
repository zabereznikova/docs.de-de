---
title: Geschachtelte Typen – C#-Programmierhandbuch
ms.custom: seodec18
ms.date: 07/10/2017
helpviewer_keywords:
- nested types [C#]
ms.assetid: f2e1b315-e3d1-48ce-977f-7bae0960ba99
ms.openlocfilehash: de2e369702c48047835bc49b98df8f48fbd13480
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/19/2019
ms.locfileid: "69596522"
---
# <a name="nested-types-c-programming-guide"></a><span data-ttu-id="af03a-102">Geschachtelte Typen (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="af03a-102">Nested Types (C# Programming Guide)</span></span>
<span data-ttu-id="af03a-103">Ein innerhalb einer [Klasse](../../language-reference/keywords/class.md) oder [Struktur](../../language-reference/keywords/struct.md) definierter Typ wird als geschachtelter Typ bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="af03a-103">A type defined within a [class](../../language-reference/keywords/class.md) or [struct](../../language-reference/keywords/struct.md) is called a nested type.</span></span> <span data-ttu-id="af03a-104">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="af03a-104">For example:</span></span>  
  
 [!code-csharp[csProgGuideObjects#68](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#68)]  
  
<span data-ttu-id="af03a-105">Unabhängig davon, ob der äußere Typ eine Klasse oder eine Struktur ist, lautet die Standardeinstellung von geschachtelten Typen [private](../../language-reference/keywords/private.md). Sie sind nur über ihren enthaltenden Typ zugänglich.</span><span class="sxs-lookup"><span data-stu-id="af03a-105">Regardless of whether the outer type is a class or a struct, nested types default to [private](../../language-reference/keywords/private.md); they are accessible only from their containing type.</span></span> <span data-ttu-id="af03a-106">Im vorherigen Beispiel konnten externe Typen nicht auf die `Nested`-Klasse zugreifen.</span><span class="sxs-lookup"><span data-stu-id="af03a-106">In the previous example, the `Nested` class is inaccessible to external types.</span></span> 

<span data-ttu-id="af03a-107">Sie können auch einen [Zugriffsmodifizierer](../../language-reference/keywords/access-modifiers.md) angeben, um den Zugriff auf einen geschachtelten Typ wie folgt zu definieren:</span><span class="sxs-lookup"><span data-stu-id="af03a-107">You can also specify an [access modifier](../../language-reference/keywords/access-modifiers.md) to define the accessibility of a nested type, as follows:</span></span>

- <span data-ttu-id="af03a-108">Geschachtelte Typen von **class** können [public](../../language-reference/keywords/public.md), [protected](../../language-reference/keywords/protected.md), [internal](../../language-reference/keywords/internal.md), [protected internal](../../language-reference/keywords/protected-internal.md), [private](../../language-reference/keywords/private.md) oder [private protected](../../language-reference/keywords/private-protected.md) sein.</span><span class="sxs-lookup"><span data-stu-id="af03a-108">Nested types of a **class** can be [public](../../language-reference/keywords/public.md), [protected](../../language-reference/keywords/protected.md), [internal](../../language-reference/keywords/internal.md), [protected internal](../../language-reference/keywords/protected-internal.md), [private](../../language-reference/keywords/private.md) or [private protected](../../language-reference/keywords/private-protected.md).</span></span> 

   <span data-ttu-id="af03a-109">Durch das Definieren einer geschachtelten `protected`-, `protected internal`- oder `private protected`-Klasse innerhalb einer [versiegelten Klasse](../../language-reference/keywords/sealed.md) wird jedoch die Compilerwarnung [CS0628](../../misc/cs0628.md), „Neuer geschützter Member in versiegelter Klasse deklariert“, generiert.</span><span class="sxs-lookup"><span data-stu-id="af03a-109">However, defining a `protected`, `protected internal` or `private protected` nested class inside a [sealed class](../../language-reference/keywords/sealed.md) generates compiler warning [CS0628](../../misc/cs0628.md), "new protected member declared in sealed class."</span></span>
  
- <span data-ttu-id="af03a-110">Geschachtelte Typen einer **Struktur** können öffentlich ([public](../../language-reference/keywords/public.md)), intern ([internal](../../language-reference/keywords/internal.md)) oder privat ([private](../../language-reference/keywords/private.md)) sein.</span><span class="sxs-lookup"><span data-stu-id="af03a-110">Nested types of a **struct** can be [public](../../language-reference/keywords/public.md), [internal](../../language-reference/keywords/internal.md), or [private](../../language-reference/keywords/private.md).</span></span>
  
<span data-ttu-id="af03a-111">Im folgenden Beispiel wird die `Nested`-Klasse öffentlich gemacht:</span><span class="sxs-lookup"><span data-stu-id="af03a-111">The following example makes the `Nested` class public:</span></span>
  
 [!code-csharp[csProgGuideObjects#69](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#69)]  
  
 <span data-ttu-id="af03a-112">Der geschachtelte oder innere Typ kann auf den enthaltenden oder äußeren Typ zugreifen.</span><span class="sxs-lookup"><span data-stu-id="af03a-112">The nested, or inner, type can access the containing, or outer, type.</span></span> <span data-ttu-id="af03a-113">Um auf den enthaltenden Typ zuzugreifen, übergeben Sie ihn als Argument dem Konstruktor des geschachtelten Typs.</span><span class="sxs-lookup"><span data-stu-id="af03a-113">To access the containing type, pass it as an argument to the constructor of the nested type.</span></span> <span data-ttu-id="af03a-114">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="af03a-114">For example:</span></span>  
  
 [!code-csharp[csProgGuideObjects#70](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#70)]  
  
 <span data-ttu-id="af03a-115">Ein geschachtelter Typ hat Zugriff auf alle Member, die für ihren äußeren (enthaltenden) Typ zugreifbar sind.</span><span class="sxs-lookup"><span data-stu-id="af03a-115">A nested type has access to all of the members that are accessible to its containing type.</span></span> <span data-ttu-id="af03a-116">Er kann auf die Member des äußeren (enthaltenden) Typs zugreifen, die "private" oder "protected" sind, ebenso auf alle geerbten Member, die "private" oder "protected" sind.</span><span class="sxs-lookup"><span data-stu-id="af03a-116">It can access private and protected members of the containing type, including any inherited protected members.</span></span>  
  
 <span data-ttu-id="af03a-117">In der vorherigen Deklaration ist `Nested` der vollständige Name der Klasse `Container.Nested`.</span><span class="sxs-lookup"><span data-stu-id="af03a-117">In the previous declaration, the full name of class `Nested` is `Container.Nested`.</span></span> <span data-ttu-id="af03a-118">Mit diesem Namen wird wie folgt eine neue Instanz der geschachtelten Klasse erstellt:</span><span class="sxs-lookup"><span data-stu-id="af03a-118">This is the name used to create a new instance of the nested class, as follows:</span></span>  
  
 [!code-csharp[csProgGuideObjects#71](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#71)]  
  
## <a name="see-also"></a><span data-ttu-id="af03a-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="af03a-119">See also</span></span>

- [<span data-ttu-id="af03a-120">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="af03a-120">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="af03a-121">Klassen und Strukturen</span><span class="sxs-lookup"><span data-stu-id="af03a-121">Classes and Structs</span></span>](./index.md)
- [<span data-ttu-id="af03a-122">Zugriffsmodifizierer</span><span class="sxs-lookup"><span data-stu-id="af03a-122">Access Modifiers</span></span>](./access-modifiers.md)
- [<span data-ttu-id="af03a-123">Konstruktoren</span><span class="sxs-lookup"><span data-stu-id="af03a-123">Constructors</span></span>](./constructors.md)
