---
title: Private Protected
ms.date: 05/10/2018
helpviewer_keywords:
- Private Protected keyword [Visual Basic]
- Private Protected keyword [Visual Basic], syntax
ms.openlocfilehash: 265141f77f4a61a61414a07214830feaa8a1ab05
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351347"
---
# <a name="private-protected-visual-basic"></a><span data-ttu-id="45df1-102">Private Protected (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="45df1-102">Private Protected (Visual Basic)</span></span>

<span data-ttu-id="45df1-103">Die Schlüsselwortkombination `Private Protected` ist ein Zugriffsmodifizierer für Member.</span><span class="sxs-lookup"><span data-stu-id="45df1-103">The `Private Protected` keyword combination is a member access modifier.</span></span> <span data-ttu-id="45df1-104">A `Private Protected` member is accessible by all members in its containing class, as well as by types derived from the containing class, but only if they are found in its containing assembly.</span><span class="sxs-lookup"><span data-stu-id="45df1-104">A `Private Protected` member is accessible by all members in its containing class, as well as by types derived from the containing class, but only if they are found in its containing assembly.</span></span>

<span data-ttu-id="45df1-105">You can specify `Private Protected` only on members of classes; you cannot apply `Private Protected` to members of a structure because structures cannot be inherited.</span><span class="sxs-lookup"><span data-stu-id="45df1-105">You can specify `Private Protected` only on members of classes; you cannot apply `Private Protected` to members of a structure because structures cannot be inherited.</span></span>

<span data-ttu-id="45df1-106">The `Private Protected` access modifier is supported by Visual Basic 15.5 and later.</span><span class="sxs-lookup"><span data-stu-id="45df1-106">The `Private Protected` access modifier is supported by Visual Basic 15.5 and later.</span></span> <span data-ttu-id="45df1-107">To use it, you can add the following element to your Visual Basic project (\*.vbproj) file.</span><span class="sxs-lookup"><span data-stu-id="45df1-107">To use it, you can add the following element to your Visual Basic project (\*.vbproj) file.</span></span> <span data-ttu-id="45df1-108">As long as Visual Basic 15.5 or later is installed on your system, it lets you take advantage of all the language features supported by the latest version of the Visual Basic compiler:</span><span class="sxs-lookup"><span data-stu-id="45df1-108">As long as Visual Basic 15.5 or later is installed on your system, it lets you take advantage of all the language features supported by the latest version of the Visual Basic compiler:</span></span>

```xml
<PropertyGroup>
   <LangVersion>latest</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="45df1-109">For more information see [setting the Visual Basic language version](../../language-reference/configure-language-version.md).</span><span class="sxs-lookup"><span data-stu-id="45df1-109">For more information see [setting the Visual Basic language version](../../language-reference/configure-language-version.md).</span></span>

> [!NOTE]
> <span data-ttu-id="45df1-110">In Visual Studio, selecting F1 help on `private protected` provides help for either [private](private.md) or [protected](protected.md).</span><span class="sxs-lookup"><span data-stu-id="45df1-110">In Visual Studio, selecting F1 help on `private protected` provides help for either [private](private.md) or [protected](protected.md).</span></span> <span data-ttu-id="45df1-111">The IDE picks the single token under the cursor rather than the compound word.</span><span class="sxs-lookup"><span data-stu-id="45df1-111">The IDE picks the single token under the cursor rather than the compound word.</span></span>

## <a name="rules"></a><span data-ttu-id="45df1-112">Regeln</span><span class="sxs-lookup"><span data-stu-id="45df1-112">Rules</span></span>

- <span data-ttu-id="45df1-113">**Declaration Context.**</span><span class="sxs-lookup"><span data-stu-id="45df1-113">**Declaration Context.**</span></span> <span data-ttu-id="45df1-114">You can use `Private Protected` only at the class level.</span><span class="sxs-lookup"><span data-stu-id="45df1-114">You can use `Private Protected` only at the class level.</span></span> <span data-ttu-id="45df1-115">This means the declaration context for a `Protected` element must be a class, and cannot be a source file, namespace, interface, module, structure, or procedure.</span><span class="sxs-lookup"><span data-stu-id="45df1-115">This means the declaration context for a `Protected` element must be a class, and cannot be a source file, namespace, interface, module, structure, or procedure.</span></span>

## <a name="behavior"></a><span data-ttu-id="45df1-116">Verhalten</span><span class="sxs-lookup"><span data-stu-id="45df1-116">Behavior</span></span>

- <span data-ttu-id="45df1-117">**Access Level.**</span><span class="sxs-lookup"><span data-stu-id="45df1-117">**Access Level.**</span></span> <span data-ttu-id="45df1-118">All code in a class can access its elements.</span><span class="sxs-lookup"><span data-stu-id="45df1-118">All code in a class can access its elements.</span></span> <span data-ttu-id="45df1-119">Code in any class that derives from a base class and is contained in the same assembly can access all the `Private Protected` elements of the base class.</span><span class="sxs-lookup"><span data-stu-id="45df1-119">Code in any class that derives from a base class and is contained in the same assembly can access all the `Private Protected` elements of the base class.</span></span> <span data-ttu-id="45df1-120">However, code in any class that derives from a base class and is contained in a different assembly can't access the base class `Private Protected` elements.</span><span class="sxs-lookup"><span data-stu-id="45df1-120">However, code in any class that derives from a base class and is contained in a different assembly can't access the base class `Private Protected` elements.</span></span>

- <span data-ttu-id="45df1-121">**Access Modifiers.**</span><span class="sxs-lookup"><span data-stu-id="45df1-121">**Access Modifiers.**</span></span> <span data-ttu-id="45df1-122">The keywords that specify access level are called *access modifiers*.</span><span class="sxs-lookup"><span data-stu-id="45df1-122">The keywords that specify access level are called *access modifiers*.</span></span> <span data-ttu-id="45df1-123">For a comparison of the access modifiers, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="45df1-123">For a comparison of the access modifiers, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>

<span data-ttu-id="45df1-124">Der `Private Protected`-Modifizierer kann in folgenden Kontexten verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="45df1-124">The `Private Protected` modifier can be used in these contexts:</span></span>

- <span data-ttu-id="45df1-125">[Class Statement](../../../visual-basic/language-reference/statements/class-statement.md) of a nested class</span><span class="sxs-lookup"><span data-stu-id="45df1-125">[Class Statement](../../../visual-basic/language-reference/statements/class-statement.md) of a nested class</span></span>

- [<span data-ttu-id="45df1-126">Const-Anweisung</span><span class="sxs-lookup"><span data-stu-id="45df1-126">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)

- [<span data-ttu-id="45df1-127">Declare-Anweisung</span><span class="sxs-lookup"><span data-stu-id="45df1-127">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)

- <span data-ttu-id="45df1-128">[Delegate Statement](../../../visual-basic/language-reference/statements/delegate-statement.md) of a delegate nested in a class</span><span class="sxs-lookup"><span data-stu-id="45df1-128">[Delegate Statement](../../../visual-basic/language-reference/statements/delegate-statement.md) of a delegate nested in a class</span></span>

- [<span data-ttu-id="45df1-129">Dim-Anweisung</span><span class="sxs-lookup"><span data-stu-id="45df1-129">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)

- <span data-ttu-id="45df1-130">[Enum Statement](../../../visual-basic/language-reference/statements/enum-statement.md) of an enumeration nested in a class</span><span class="sxs-lookup"><span data-stu-id="45df1-130">[Enum Statement](../../../visual-basic/language-reference/statements/enum-statement.md) of an enumeration nested in a class</span></span>

- [<span data-ttu-id="45df1-131">Event-Anweisung</span><span class="sxs-lookup"><span data-stu-id="45df1-131">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)

- [<span data-ttu-id="45df1-132">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="45df1-132">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)

- <span data-ttu-id="45df1-133">[Interface Statement](../../../visual-basic/language-reference/statements/interface-statement.md) of an interface nested in a class</span><span class="sxs-lookup"><span data-stu-id="45df1-133">[Interface Statement](../../../visual-basic/language-reference/statements/interface-statement.md) of an interface nested in a class</span></span>

- [<span data-ttu-id="45df1-134">Property-Anweisung</span><span class="sxs-lookup"><span data-stu-id="45df1-134">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)

- <span data-ttu-id="45df1-135">[Structure Statement](../../../visual-basic/language-reference/statements/structure-statement.md) of a structure nested in a class</span><span class="sxs-lookup"><span data-stu-id="45df1-135">[Structure Statement](../../../visual-basic/language-reference/statements/structure-statement.md) of a structure nested in a class</span></span>

- [<span data-ttu-id="45df1-136">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="45df1-136">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)

## <a name="see-also"></a><span data-ttu-id="45df1-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="45df1-137">See also</span></span>

- [<span data-ttu-id="45df1-138">Public</span><span class="sxs-lookup"><span data-stu-id="45df1-138">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)
- [<span data-ttu-id="45df1-139">Protected</span><span class="sxs-lookup"><span data-stu-id="45df1-139">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)
- [<span data-ttu-id="45df1-140">Friend</span><span class="sxs-lookup"><span data-stu-id="45df1-140">Friend</span></span>](friend.md)
- [<span data-ttu-id="45df1-141">Private</span><span class="sxs-lookup"><span data-stu-id="45df1-141">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)
- [<span data-ttu-id="45df1-142">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="45df1-142">Protected Friend</span></span>](./protected-friend.md)
- [<span data-ttu-id="45df1-143">Access levels in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="45df1-143">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="45df1-144">Verfahren</span><span class="sxs-lookup"><span data-stu-id="45df1-144">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="45df1-145">Strukturen</span><span class="sxs-lookup"><span data-stu-id="45df1-145">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="45df1-146">Objekte und Klassen</span><span class="sxs-lookup"><span data-stu-id="45df1-146">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
