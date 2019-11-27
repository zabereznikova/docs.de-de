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
# <a name="private-protected-visual-basic"></a><span data-ttu-id="158e6-102">Privat geschützt (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="158e6-102">Private Protected (Visual Basic)</span></span>

<span data-ttu-id="158e6-103">Die Schlüsselwortkombination `Private Protected` ist ein Zugriffsmodifizierer für Member.</span><span class="sxs-lookup"><span data-stu-id="158e6-103">The `Private Protected` keyword combination is a member access modifier.</span></span> <span data-ttu-id="158e6-104">Auf einen `Private Protected` Member kann sowohl von allen Membern in der enthaltenden Klasse als auch von Typen, die von der enthaltenden Klasse abgeleitet sind, zugegriffen werden, jedoch nur, wenn Sie in der enthaltenden Assembly gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="158e6-104">A `Private Protected` member is accessible by all members in its containing class, as well as by types derived from the containing class, but only if they are found in its containing assembly.</span></span>

<span data-ttu-id="158e6-105">Sie können `Private Protected` nur für Member von Klassen angeben. Sie können `Private Protected` nicht auf Member einer Struktur anwenden, da Strukturen nicht vererbt werden können.</span><span class="sxs-lookup"><span data-stu-id="158e6-105">You can specify `Private Protected` only on members of classes; you cannot apply `Private Protected` to members of a structure because structures cannot be inherited.</span></span>

<span data-ttu-id="158e6-106">Der `Private Protected` Zugriffsmodifizierer wird von Visual Basic 15,5 und höher unterstützt.</span><span class="sxs-lookup"><span data-stu-id="158e6-106">The `Private Protected` access modifier is supported by Visual Basic 15.5 and later.</span></span> <span data-ttu-id="158e6-107">Um es zu verwenden, können Sie das folgende-Element der Visual Basic Project-Datei (\*. vbproj) hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="158e6-107">To use it, you can add the following element to your Visual Basic project (\*.vbproj) file.</span></span> <span data-ttu-id="158e6-108">Solange Visual Basic 15,5 oder höher auf Ihrem System installiert ist, können Sie alle sprach Features nutzen, die von der neuesten Version des Visual Basic Compilers unterstützt werden:</span><span class="sxs-lookup"><span data-stu-id="158e6-108">As long as Visual Basic 15.5 or later is installed on your system, it lets you take advantage of all the language features supported by the latest version of the Visual Basic compiler:</span></span>

```xml
<PropertyGroup>
   <LangVersion>latest</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="158e6-109">Weitere Informationen finden Sie [unter Festlegen der Visual Basic Sprachversion](../../language-reference/configure-language-version.md).</span><span class="sxs-lookup"><span data-stu-id="158e6-109">For more information see [setting the Visual Basic language version](../../language-reference/configure-language-version.md).</span></span>

> [!NOTE]
> <span data-ttu-id="158e6-110">Wenn Sie in Visual Studio die F1-Hilfe auf `private protected` auswählen, finden Sie Hilfe für [Privat](private.md) oder [geschützt](protected.md).</span><span class="sxs-lookup"><span data-stu-id="158e6-110">In Visual Studio, selecting F1 help on `private protected` provides help for either [private](private.md) or [protected](protected.md).</span></span> <span data-ttu-id="158e6-111">Die IDE wählt anstelle des Verbund Worts das einzelne Token unter dem Cursor aus.</span><span class="sxs-lookup"><span data-stu-id="158e6-111">The IDE picks the single token under the cursor rather than the compound word.</span></span>

## <a name="rules"></a><span data-ttu-id="158e6-112">Regeln</span><span class="sxs-lookup"><span data-stu-id="158e6-112">Rules</span></span>

- <span data-ttu-id="158e6-113">**Deklarations Kontext.**</span><span class="sxs-lookup"><span data-stu-id="158e6-113">**Declaration Context.**</span></span> <span data-ttu-id="158e6-114">Sie können `Private Protected` nur auf Klassenebene verwenden.</span><span class="sxs-lookup"><span data-stu-id="158e6-114">You can use `Private Protected` only at the class level.</span></span> <span data-ttu-id="158e6-115">Dies bedeutet, dass der Deklarations Kontext für ein `Protected` Element eine Klasse sein muss und keine Quelldatei, ein Namespace, eine Schnittstelle, ein Modul, eine Struktur oder eine Prozedur sein darf.</span><span class="sxs-lookup"><span data-stu-id="158e6-115">This means the declaration context for a `Protected` element must be a class, and cannot be a source file, namespace, interface, module, structure, or procedure.</span></span>

## <a name="behavior"></a><span data-ttu-id="158e6-116">Verhalten</span><span class="sxs-lookup"><span data-stu-id="158e6-116">Behavior</span></span>

- <span data-ttu-id="158e6-117">**Zugriffsebene.**</span><span class="sxs-lookup"><span data-stu-id="158e6-117">**Access Level.**</span></span> <span data-ttu-id="158e6-118">Der gesamte Code in einer Klasse kann auf seine Elemente zugreifen.</span><span class="sxs-lookup"><span data-stu-id="158e6-118">All code in a class can access its elements.</span></span> <span data-ttu-id="158e6-119">Code in jeder Klasse, die von einer Basisklasse abgeleitet ist und in derselben Assembly enthalten ist, kann auf alle `Private Protected` Elemente der Basisklasse zugreifen.</span><span class="sxs-lookup"><span data-stu-id="158e6-119">Code in any class that derives from a base class and is contained in the same assembly can access all the `Private Protected` elements of the base class.</span></span> <span data-ttu-id="158e6-120">Allerdings kann Code in einer beliebigen Klasse, die von einer Basisklasse abgeleitet ist und in einer anderen Assembly enthalten ist, nicht auf die `Private Protected` Elemente der Basisklasse zugreifen.</span><span class="sxs-lookup"><span data-stu-id="158e6-120">However, code in any class that derives from a base class and is contained in a different assembly can't access the base class `Private Protected` elements.</span></span>

- <span data-ttu-id="158e6-121">**Zugriffsmodifizierer**</span><span class="sxs-lookup"><span data-stu-id="158e6-121">**Access Modifiers.**</span></span> <span data-ttu-id="158e6-122">Die Schlüsselwörter für die Zugriffsebene werden als *Zugriffsmodifizierer*bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="158e6-122">The keywords that specify access level are called *access modifiers*.</span></span> <span data-ttu-id="158e6-123">Einen Vergleich der Zugriffsmodifizierer finden Sie unter [Zugriffsebenen in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="158e6-123">For a comparison of the access modifiers, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>

<span data-ttu-id="158e6-124">Der `Private Protected`-Modifizierer kann in folgenden Kontexten verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="158e6-124">The `Private Protected` modifier can be used in these contexts:</span></span>

- <span data-ttu-id="158e6-125">[Class-Anweisung](../../../visual-basic/language-reference/statements/class-statement.md) einer "netsted"-Klasse</span><span class="sxs-lookup"><span data-stu-id="158e6-125">[Class Statement](../../../visual-basic/language-reference/statements/class-statement.md) of a nested class</span></span>

- [<span data-ttu-id="158e6-126">Const-Anweisung</span><span class="sxs-lookup"><span data-stu-id="158e6-126">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)

- [<span data-ttu-id="158e6-127">Declare-Anweisung</span><span class="sxs-lookup"><span data-stu-id="158e6-127">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)

- <span data-ttu-id="158e6-128">[Delegatanweisung](../../../visual-basic/language-reference/statements/delegate-statement.md) eines Delegaten, der in einer Klasse eingebettet ist</span><span class="sxs-lookup"><span data-stu-id="158e6-128">[Delegate Statement](../../../visual-basic/language-reference/statements/delegate-statement.md) of a delegate nested in a class</span></span>

- [<span data-ttu-id="158e6-129">Dim-Anweisung</span><span class="sxs-lookup"><span data-stu-id="158e6-129">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)

- <span data-ttu-id="158e6-130">[Enumerationsanweisung](../../../visual-basic/language-reference/statements/enum-statement.md) einer Enumeration, die in einer Klasse eingefügt ist</span><span class="sxs-lookup"><span data-stu-id="158e6-130">[Enum Statement](../../../visual-basic/language-reference/statements/enum-statement.md) of an enumeration nested in a class</span></span>

- [<span data-ttu-id="158e6-131">Event-Anweisung</span><span class="sxs-lookup"><span data-stu-id="158e6-131">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)

- [<span data-ttu-id="158e6-132">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="158e6-132">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)

- <span data-ttu-id="158e6-133">[Interface-Anweisung](../../../visual-basic/language-reference/statements/interface-statement.md) einer Schnittstelle, die in einer Klasse eingebettet ist</span><span class="sxs-lookup"><span data-stu-id="158e6-133">[Interface Statement](../../../visual-basic/language-reference/statements/interface-statement.md) of an interface nested in a class</span></span>

- [<span data-ttu-id="158e6-134">Property-Anweisung</span><span class="sxs-lookup"><span data-stu-id="158e6-134">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)

- <span data-ttu-id="158e6-135">[Structure-Anweisung](../../../visual-basic/language-reference/statements/structure-statement.md) einer Struktur, die in einer Klasse eingebettet ist</span><span class="sxs-lookup"><span data-stu-id="158e6-135">[Structure Statement](../../../visual-basic/language-reference/statements/structure-statement.md) of a structure nested in a class</span></span>

- [<span data-ttu-id="158e6-136">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="158e6-136">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)

## <a name="see-also"></a><span data-ttu-id="158e6-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="158e6-137">See also</span></span>

- [<span data-ttu-id="158e6-138">Public</span><span class="sxs-lookup"><span data-stu-id="158e6-138">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)
- [<span data-ttu-id="158e6-139">Protected</span><span class="sxs-lookup"><span data-stu-id="158e6-139">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)
- [<span data-ttu-id="158e6-140">Friend</span><span class="sxs-lookup"><span data-stu-id="158e6-140">Friend</span></span>](friend.md)
- [<span data-ttu-id="158e6-141">Private</span><span class="sxs-lookup"><span data-stu-id="158e6-141">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)
- [<span data-ttu-id="158e6-142">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="158e6-142">Protected Friend</span></span>](./protected-friend.md)
- [<span data-ttu-id="158e6-143">Zugriffsebenen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="158e6-143">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="158e6-144">Verfahren</span><span class="sxs-lookup"><span data-stu-id="158e6-144">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="158e6-145">Strukturen</span><span class="sxs-lookup"><span data-stu-id="158e6-145">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="158e6-146">Objekte und Klassen</span><span class="sxs-lookup"><span data-stu-id="158e6-146">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
