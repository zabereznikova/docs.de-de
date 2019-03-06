---
title: Privat geschützt (Visual Basic)
ms.date: 05/10/2018
helpviewer_keywords:
- Private Protected keyword [Visual Basic]
- Private Protected keyword [Visual Basic], syntax
ms.openlocfilehash: fea43558ac0fe8181f2786b69f2621346d446b2e
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57376389"
---
# <a name="private-protected-visual-basic"></a><span data-ttu-id="edc6d-102">Privat geschützt (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="edc6d-102">Private Protected (Visual Basic)</span></span>

<span data-ttu-id="edc6d-103">Die Schlüsselwortkombination `Private Protected` ist ein Zugriffsmodifizierer für Member.</span><span class="sxs-lookup"><span data-stu-id="edc6d-103">The `Private Protected` keyword combination is a member access modifier.</span></span> <span data-ttu-id="edc6d-104">Ein `Private Protected` angehört, zugegriffen werden kann, indem Sie alle Elemente in der enthaltenden Klasse sowie Typen, die von der enthaltenden Klasse abgeleitet, jedoch nur, wenn sie in der enthaltenden Assembly gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="edc6d-104">A `Private Protected` member is accessible by all members in its containing class, as well as by types derived from the containing class, but only if they are found in its containing assembly.</span></span>

<span data-ttu-id="edc6d-105">Sie können angeben, `Private Protected` nur auf Member von Klassen; Sie können nicht angewendet werden `Private Protected` zu Membern einer Struktur da Strukturen nicht geerbt werden können.</span><span class="sxs-lookup"><span data-stu-id="edc6d-105">You can specify `Private Protected` only on members of classes; you cannot apply `Private Protected` to members of a structure because structures cannot be inherited.</span></span>

<span data-ttu-id="edc6d-106">Die `Private Protected` Zugriffsmodifizierer wird von Visual Basic 15.5 und höher unterstützt.</span><span class="sxs-lookup"><span data-stu-id="edc6d-106">The `Private Protected` access modifier is supported by Visual Basic 15.5 and later.</span></span> <span data-ttu-id="edc6d-107">Sie können das folgende Element auf Visual Basic-Projekt hinzufügen, um es zu verwenden (\*.vbproj) Datei.</span><span class="sxs-lookup"><span data-stu-id="edc6d-107">To use it, you can add the following element to your Visual Basic project (\*.vbproj) file.</span></span> <span data-ttu-id="edc6d-108">Solange Visual Basic 15.5 oder höher auf Ihrem System installiert ist, können dass Sie alle der Features von Programmiersprachen unterstützt werden, indem Sie die neueste Version von Visual Basic-Compiler nutzen:</span><span class="sxs-lookup"><span data-stu-id="edc6d-108">As long as Visual Basic 15.5 or later is installed on your system, it lets you take advantage of all the language features supported by the latest version of the Visual Basic compiler:</span></span>

```xml
<PropertyGroup>
   <LangVersion>latest</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="edc6d-109">Weitere Informationen finden Sie unter [Festlegen der Sprache Visual Basic-Version](../../language-reference/configure-language-version.md).</span><span class="sxs-lookup"><span data-stu-id="edc6d-109">For more information see [setting the Visual Basic language version](../../language-reference/configure-language-version.md).</span></span>

> [!NOTE]
> <span data-ttu-id="edc6d-110">Wählen Sie in Visual Studio F1-Hilfe auf `private protected` enthält die Hilfe für entweder [private](private.md) oder [geschützt](protected.md).</span><span class="sxs-lookup"><span data-stu-id="edc6d-110">In Visual Studio, selecting F1 help on `private protected` provides help for either [private](private.md) or [protected](protected.md).</span></span> <span data-ttu-id="edc6d-111">Die IDE wählt die einzelne Token unter dem Cursor anstatt der zusammengesetzte Begriff.</span><span class="sxs-lookup"><span data-stu-id="edc6d-111">The IDE picks the single token under the cursor rather than the compound word.</span></span>

## <a name="rules"></a><span data-ttu-id="edc6d-112">Regeln</span><span class="sxs-lookup"><span data-stu-id="edc6d-112">Rules</span></span>

- <span data-ttu-id="edc6d-113">**Deklarationskontext.**</span><span class="sxs-lookup"><span data-stu-id="edc6d-113">**Declaration Context.**</span></span> <span data-ttu-id="edc6d-114">Sie können `Private Protected` nur auf Klassenebene.</span><span class="sxs-lookup"><span data-stu-id="edc6d-114">You can use `Private Protected` only at the class level.</span></span> <span data-ttu-id="edc6d-115">Dies bedeutet, dass der Deklarationskontext für eine `Protected` Element muss eine Klasse sein, und eine Quelldatei, Namespace, Schnittstelle, Modul, Struktur oder Prozedur nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="edc6d-115">This means the declaration context for a `Protected` element must be a class, and cannot be a source file, namespace, interface, module, structure, or procedure.</span></span>

## <a name="behavior"></a><span data-ttu-id="edc6d-116">Verhalten</span><span class="sxs-lookup"><span data-stu-id="edc6d-116">Behavior</span></span>

- <span data-ttu-id="edc6d-117">**Zugriffsebene.**</span><span class="sxs-lookup"><span data-stu-id="edc6d-117">**Access Level.**</span></span> <span data-ttu-id="edc6d-118">Gesamten Code in einer Klasse kann Zugriff auf die Elemente auf.</span><span class="sxs-lookup"><span data-stu-id="edc6d-118">All code in a class can access its elements.</span></span> <span data-ttu-id="edc6d-119">Code in einer Klasse, die von einer Basisklasse abgeleitet wird und in derselben Assembly enthalten ist, kann auf alle zugreifen der `Private Protected` Elemente der Basisklasse.</span><span class="sxs-lookup"><span data-stu-id="edc6d-119">Code in any class that derives from a base class and is contained in the same assembly can access all the `Private Protected` elements of the base class.</span></span> <span data-ttu-id="edc6d-120">Jedoch nicht im Code jeder Klasse, die von einer Basisklasse abgeleitet wird und in einer anderen Assembly enthalten ist die Basisklasse der Klasse zugreifen `Private Protected` Elemente.</span><span class="sxs-lookup"><span data-stu-id="edc6d-120">However, code in any class that derives from a base class and is contained in a different assembly can't access the base class `Private Protected` elements.</span></span>

- <span data-ttu-id="edc6d-121">**Zugriffsmodifizierer.**</span><span class="sxs-lookup"><span data-stu-id="edc6d-121">**Access Modifiers.**</span></span> <span data-ttu-id="edc6d-122">Die Schlüsselwörter, die Zugriffsebene angeben heißen *Zugriffsmodifizierer*.</span><span class="sxs-lookup"><span data-stu-id="edc6d-122">The keywords that specify access level are called *access modifiers*.</span></span> <span data-ttu-id="edc6d-123">Einen Vergleich der Zugriffsmodifizierer, finden Sie unter [Zugriffsebenen in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="edc6d-123">For a comparison of the access modifiers, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>

<span data-ttu-id="edc6d-124">Der `Private Protected`-Modifizierer kann in folgenden Kontexten verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="edc6d-124">The `Private Protected` modifier can be used in these contexts:</span></span>

- <span data-ttu-id="edc6d-125">[Class-Anweisung](../../../visual-basic/language-reference/statements/class-statement.md) einer geschachtelten Klasse</span><span class="sxs-lookup"><span data-stu-id="edc6d-125">[Class Statement](../../../visual-basic/language-reference/statements/class-statement.md) of a nested class</span></span>

- [<span data-ttu-id="edc6d-126">Const-Anweisung</span><span class="sxs-lookup"><span data-stu-id="edc6d-126">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)

- [<span data-ttu-id="edc6d-127">Declare-Anweisung</span><span class="sxs-lookup"><span data-stu-id="edc6d-127">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)

- <span data-ttu-id="edc6d-128">[Delegate-Anweisung](../../../visual-basic/language-reference/statements/delegate-statement.md) eines Delegaten, die in einer Klasse geschachtelt sind</span><span class="sxs-lookup"><span data-stu-id="edc6d-128">[Delegate Statement](../../../visual-basic/language-reference/statements/delegate-statement.md) of a delegate nested in a class</span></span>

- [<span data-ttu-id="edc6d-129">Dim-Anweisung</span><span class="sxs-lookup"><span data-stu-id="edc6d-129">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)

- <span data-ttu-id="edc6d-130">[Enum-Anweisung](../../../visual-basic/language-reference/statements/enum-statement.md) einer Enumeration, die in einer Klasse geschachtelt sind</span><span class="sxs-lookup"><span data-stu-id="edc6d-130">[Enum Statement](../../../visual-basic/language-reference/statements/enum-statement.md) of an enumeration nested in a class</span></span>

- [<span data-ttu-id="edc6d-131">Event-Anweisung</span><span class="sxs-lookup"><span data-stu-id="edc6d-131">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)

- [<span data-ttu-id="edc6d-132">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="edc6d-132">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)

- <span data-ttu-id="edc6d-133">[Interface-Anweisung](../../../visual-basic/language-reference/statements/interface-statement.md) einer Schnittstelle, die in einer Klasse geschachtelt sind</span><span class="sxs-lookup"><span data-stu-id="edc6d-133">[Interface Statement](../../../visual-basic/language-reference/statements/interface-statement.md) of an interface nested in a class</span></span>

- [<span data-ttu-id="edc6d-134">Property-Anweisung</span><span class="sxs-lookup"><span data-stu-id="edc6d-134">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)

- <span data-ttu-id="edc6d-135">[Strukturieren Sie die Anweisung](../../../visual-basic/language-reference/statements/structure-statement.md) einer Struktur geschachtelt werden, in einer Klasse</span><span class="sxs-lookup"><span data-stu-id="edc6d-135">[Structure Statement](../../../visual-basic/language-reference/statements/structure-statement.md) of a structure nested in a class</span></span>

- [<span data-ttu-id="edc6d-136">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="edc6d-136">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)

## <a name="see-also"></a><span data-ttu-id="edc6d-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="edc6d-137">See also</span></span>

- [<span data-ttu-id="edc6d-138">Public</span><span class="sxs-lookup"><span data-stu-id="edc6d-138">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)
- [<span data-ttu-id="edc6d-139">Protected</span><span class="sxs-lookup"><span data-stu-id="edc6d-139">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)
- [<span data-ttu-id="edc6d-140">Friend</span><span class="sxs-lookup"><span data-stu-id="edc6d-140">Friend</span></span>](friend.md)
- [<span data-ttu-id="edc6d-141">Private</span><span class="sxs-lookup"><span data-stu-id="edc6d-141">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)
- [<span data-ttu-id="edc6d-142">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="edc6d-142">Protected Friend</span></span>](./protected-friend.md)
- [<span data-ttu-id="edc6d-143">Zugriffsebenen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="edc6d-143">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="edc6d-144">Verfahren</span><span class="sxs-lookup"><span data-stu-id="edc6d-144">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="edc6d-145">Strukturen</span><span class="sxs-lookup"><span data-stu-id="edc6d-145">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="edc6d-146">Objekte und Klassen</span><span class="sxs-lookup"><span data-stu-id="edc6d-146">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
