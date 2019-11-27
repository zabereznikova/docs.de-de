---
title: Geschützt
ms.date: 07/20/2015
f1_keywords:
- vb.Protected
helpviewer_keywords:
- Protected Friend keyword combination
- Protected keyword [Visual Basic], and Friend
- Protected keyword [Visual Basic], syntax
- Protected access modifier
- Protected keyword [Visual Basic]
ms.assetid: 74ad3d56-309f-49d2-b60c-1d0157d010e8
ms.openlocfilehash: 740c998b8a6ccc6798bce37e9b08e408dac7c17d
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351304"
---
# <a name="protected-visual-basic"></a><span data-ttu-id="74002-102">Protected (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="74002-102">Protected (Visual Basic)</span></span>

<span data-ttu-id="74002-103">Ein Member-Zugriffsmodifizierer, der angibt, dass auf ein oder mehrere deklarierte Programmier Elemente nur aus ihrer eigenen Klasse oder aus einer abgeleiteten Klasse zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="74002-103">A member access modifier that specifies that one or more declared programming elements are accessible only from within their own class or from a derived class.</span></span>

## <a name="remarks"></a><span data-ttu-id="74002-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="74002-104">Remarks</span></span>

<span data-ttu-id="74002-105">Manchmal enthält ein in einer Klasse deklariertes Programmier Element sensible Daten oder eingeschränkten Code, und Sie möchten den Zugriff auf das Element einschränken.</span><span class="sxs-lookup"><span data-stu-id="74002-105">Sometimes a programming element declared in a class contains sensitive data or restricted code, and you want to limit access to the element.</span></span> <span data-ttu-id="74002-106">Wenn die Klasse jedoch vererbbar ist und Sie eine Hierarchie abgeleiteter Klassen erwarten, kann es erforderlich sein, dass diese abgeleiteten Klassen auf die Daten oder den Code zugreifen.</span><span class="sxs-lookup"><span data-stu-id="74002-106">However, if the class is inheritable and you expect a hierarchy of derived classes, it might be necessary for these derived classes to access the data or code.</span></span> <span data-ttu-id="74002-107">In einem solchen Fall soll der Zugriff auf das Element sowohl von der Basisklasse als auch von allen abgeleiteten Klassen erfolgen.</span><span class="sxs-lookup"><span data-stu-id="74002-107">In such a case, you want the element to be accessible both from the base class and from all derived classes.</span></span> <span data-ttu-id="74002-108">Um den Zugriff auf ein Element auf diese Weise einzuschränken, können Sie es mit `Protected`deklarieren.</span><span class="sxs-lookup"><span data-stu-id="74002-108">To limit access to an element in this manner, you can declare it with `Protected`.</span></span>

> [!NOTE]
> <span data-ttu-id="74002-109">Der `Protected` Zugriffsmodifizierer kann mit zwei anderen Modifizierern kombiniert werden:</span><span class="sxs-lookup"><span data-stu-id="74002-109">The `Protected` access modifier can be combined with two other modifiers:</span></span>
>
> - <span data-ttu-id="74002-110">Der [Protected Friend](protected-friend.md) -Modifizierer macht einen Klassenmember aus dieser Klasse, aus abgeleiteten Klassen und aus derselben Assembly, in der die Klasse definiert ist, zugänglich.</span><span class="sxs-lookup"><span data-stu-id="74002-110">The [Protected Friend](protected-friend.md) modifier makes a class member accessible from within that class, from derived classes, and from the same assembly in which the class is defined.</span></span>
> - <span data-ttu-id="74002-111">Der [private geschützte](private-protected.md) Modifizierer macht einen Klassenmember für abgeleitete Typen zugänglich, aber nur innerhalb der enthaltenden Assembly.</span><span class="sxs-lookup"><span data-stu-id="74002-111">The [Private Protected](private-protected.md) modifier makes a class member accessible by derived types, but only within its containing assembly.</span></span>

## <a name="rules"></a><span data-ttu-id="74002-112">Regeln</span><span class="sxs-lookup"><span data-stu-id="74002-112">Rules</span></span>

<span data-ttu-id="74002-113">**Deklarations Kontext.**</span><span class="sxs-lookup"><span data-stu-id="74002-113">**Declaration Context.**</span></span> <span data-ttu-id="74002-114">Sie können `Protected` nur auf Klassenebene verwenden.</span><span class="sxs-lookup"><span data-stu-id="74002-114">You can use `Protected` only at the class level.</span></span> <span data-ttu-id="74002-115">Dies bedeutet, dass der Deklarations Kontext für ein `Protected` Element eine Klasse sein muss und keine Quelldatei, ein Namespace, eine Schnittstelle, ein Modul, eine Struktur oder eine Prozedur sein darf.</span><span class="sxs-lookup"><span data-stu-id="74002-115">This means the declaration context for a `Protected` element must be a class, and cannot be a source file, namespace, interface, module, structure, or procedure.</span></span>

## <a name="behavior"></a><span data-ttu-id="74002-116">Verhalten</span><span class="sxs-lookup"><span data-stu-id="74002-116">Behavior</span></span>

- <span data-ttu-id="74002-117">**Zugriffsebene.**</span><span class="sxs-lookup"><span data-stu-id="74002-117">**Access Level.**</span></span> <span data-ttu-id="74002-118">Der gesamte Code in einer Klasse kann auf seine Elemente zugreifen.</span><span class="sxs-lookup"><span data-stu-id="74002-118">All code in a class can access its elements.</span></span> <span data-ttu-id="74002-119">Code in jeder Klasse, die von einer Basisklasse abgeleitet wird, kann auf alle `Protected` Elemente der Basisklasse zugreifen.</span><span class="sxs-lookup"><span data-stu-id="74002-119">Code in any class that derives from a base class can access all the `Protected` elements of the base class.</span></span> <span data-ttu-id="74002-120">Dies gilt für alle Generations Generierungen.</span><span class="sxs-lookup"><span data-stu-id="74002-120">This is true for all generations of derivation.</span></span> <span data-ttu-id="74002-121">Dies bedeutet, dass eine Klasse auf `Protected` Elemente der Basisklasse der Basisklasse usw. zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="74002-121">This means that a class can access `Protected` elements of the base class of the base class, and so on.</span></span>

     <span data-ttu-id="74002-122">Geschützter Zugriff ist keine übergeordnete Gruppe oder eine Teilmenge des Friend-Zugriffs.</span><span class="sxs-lookup"><span data-stu-id="74002-122">Protected access is not a superset or subset of friend access.</span></span>

- <span data-ttu-id="74002-123">**Zugriffsmodifizierer**</span><span class="sxs-lookup"><span data-stu-id="74002-123">**Access Modifiers.**</span></span> <span data-ttu-id="74002-124">Die Schlüsselwörter für die Zugriffsebene werden als *Zugriffsmodifizierer*bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="74002-124">The keywords that specify access level are called *access modifiers*.</span></span> <span data-ttu-id="74002-125">Einen Vergleich der Zugriffsmodifizierer finden Sie unter [Zugriffsebenen in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="74002-125">For a comparison of the access modifiers, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>

<span data-ttu-id="74002-126">Der `Protected`-Modifizierer kann in folgenden Kontexten verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="74002-126">The `Protected` modifier can be used in these contexts:</span></span>

- [<span data-ttu-id="74002-127">Class-Anweisung</span><span class="sxs-lookup"><span data-stu-id="74002-127">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)

- [<span data-ttu-id="74002-128">Const-Anweisung</span><span class="sxs-lookup"><span data-stu-id="74002-128">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)

- [<span data-ttu-id="74002-129">Declare-Anweisung</span><span class="sxs-lookup"><span data-stu-id="74002-129">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)

- [<span data-ttu-id="74002-130">Delegate-Anweisung</span><span class="sxs-lookup"><span data-stu-id="74002-130">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)

- [<span data-ttu-id="74002-131">Dim-Anweisung</span><span class="sxs-lookup"><span data-stu-id="74002-131">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)

- [<span data-ttu-id="74002-132">Enum-Anweisung</span><span class="sxs-lookup"><span data-stu-id="74002-132">Enum Statement</span></span>](../../../visual-basic/language-reference/statements/enum-statement.md)

- [<span data-ttu-id="74002-133">Event-Anweisung</span><span class="sxs-lookup"><span data-stu-id="74002-133">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)

- [<span data-ttu-id="74002-134">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="74002-134">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)

- [<span data-ttu-id="74002-135">Interface-Anweisung</span><span class="sxs-lookup"><span data-stu-id="74002-135">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)

- [<span data-ttu-id="74002-136">Property-Anweisung</span><span class="sxs-lookup"><span data-stu-id="74002-136">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)

- [<span data-ttu-id="74002-137">Structure-Anweisung</span><span class="sxs-lookup"><span data-stu-id="74002-137">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)

- [<span data-ttu-id="74002-138">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="74002-138">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)

## <a name="see-also"></a><span data-ttu-id="74002-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="74002-139">See also</span></span>

- [<span data-ttu-id="74002-140">Public</span><span class="sxs-lookup"><span data-stu-id="74002-140">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)
- [<span data-ttu-id="74002-141">Friend</span><span class="sxs-lookup"><span data-stu-id="74002-141">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)
- [<span data-ttu-id="74002-142">Private</span><span class="sxs-lookup"><span data-stu-id="74002-142">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)
- [<span data-ttu-id="74002-143">Private Protected</span><span class="sxs-lookup"><span data-stu-id="74002-143">Private Protected</span></span>](private-protected.md)
- [<span data-ttu-id="74002-144">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="74002-144">Protected Friend</span></span>](protected-friend.md)
- [<span data-ttu-id="74002-145">Zugriffsebenen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="74002-145">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="74002-146">Verfahren</span><span class="sxs-lookup"><span data-stu-id="74002-146">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="74002-147">Strukturen</span><span class="sxs-lookup"><span data-stu-id="74002-147">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="74002-148">Objekte und Klassen</span><span class="sxs-lookup"><span data-stu-id="74002-148">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
