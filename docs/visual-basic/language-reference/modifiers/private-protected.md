---
title: Private Protected
ms.date: 05/10/2018
helpviewer_keywords:
- Private Protected keyword [Visual Basic]
- Private Protected keyword [Visual Basic], syntax
ms.openlocfilehash: b7d9f81e41950b92c787e2e50fb94fe3d7c07559
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84362228"
---
# <a name="private-protected-visual-basic"></a><span data-ttu-id="20539-102">Privat geschützt (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="20539-102">Private Protected (Visual Basic)</span></span>

<span data-ttu-id="20539-103">Die Schlüsselwortkombination `Private Protected` ist ein Zugriffsmodifizierer für Member.</span><span class="sxs-lookup"><span data-stu-id="20539-103">The `Private Protected` keyword combination is a member access modifier.</span></span> <span data-ttu-id="20539-104">Auf einen `Private Protected` Member kann von allen Membern in der enthaltenden Klasse sowie von Typen, die von der enthaltenden Klasse abgeleitet sind, zugegriffen werden. Dies ist jedoch nur möglich, wenn Sie in der enthaltenden Assembly gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="20539-104">A `Private Protected` member is accessible by all members in its containing class, as well as by types derived from the containing class, but only if they are found in its containing assembly.</span></span>

<span data-ttu-id="20539-105">Sie können `Private Protected` nur für Member von Klassen angeben. Sie können nicht auf Member einer Struktur anwenden, `Private Protected` da Strukturen nicht vererbt werden können.</span><span class="sxs-lookup"><span data-stu-id="20539-105">You can specify `Private Protected` only on members of classes; you cannot apply `Private Protected` to members of a structure because structures cannot be inherited.</span></span>

<span data-ttu-id="20539-106">Der `Private Protected` Zugriffsmodifizierer wird von Visual Basic 15,5 und höher unterstützt.</span><span class="sxs-lookup"><span data-stu-id="20539-106">The `Private Protected` access modifier is supported by Visual Basic 15.5 and later.</span></span> <span data-ttu-id="20539-107">Um es zu verwenden, können Sie das folgende-Element der Visual Basic Project- \* Datei (. vbproj) hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="20539-107">To use it, you can add the following element to your Visual Basic project (\*.vbproj) file.</span></span> <span data-ttu-id="20539-108">Solange Visual Basic 15,5 oder höher auf Ihrem System installiert ist, können Sie alle sprach Features nutzen, die von der neuesten Version des Visual Basic Compilers unterstützt werden:</span><span class="sxs-lookup"><span data-stu-id="20539-108">As long as Visual Basic 15.5 or later is installed on your system, it lets you take advantage of all the language features supported by the latest version of the Visual Basic compiler:</span></span>

```xml
<PropertyGroup>
   <LangVersion>latest</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="20539-109">Weitere Informationen finden Sie [unter Festlegen der Visual Basic Sprachversion](../configure-language-version.md).</span><span class="sxs-lookup"><span data-stu-id="20539-109">For more information see [setting the Visual Basic language version](../configure-language-version.md).</span></span>

> [!NOTE]
> <span data-ttu-id="20539-110">Wenn Sie in Visual Studio die F1-Hilfe in auswählen, `private protected` finden Sie Hilfe für [Privat](private.md) oder [geschützt](protected.md).</span><span class="sxs-lookup"><span data-stu-id="20539-110">In Visual Studio, selecting F1 help on `private protected` provides help for either [private](private.md) or [protected](protected.md).</span></span> <span data-ttu-id="20539-111">Die IDE wählt anstelle des Verbund Worts das einzelne Token unter dem Cursor aus.</span><span class="sxs-lookup"><span data-stu-id="20539-111">The IDE picks the single token under the cursor rather than the compound word.</span></span>

## <a name="rules"></a><span data-ttu-id="20539-112">Regeln</span><span class="sxs-lookup"><span data-stu-id="20539-112">Rules</span></span>

- <span data-ttu-id="20539-113">**Deklarationskontext.**</span><span class="sxs-lookup"><span data-stu-id="20539-113">**Declaration Context.**</span></span> <span data-ttu-id="20539-114">Sie können `Private Protected` nur auf Klassenebene verwenden.</span><span class="sxs-lookup"><span data-stu-id="20539-114">You can use `Private Protected` only at the class level.</span></span> <span data-ttu-id="20539-115">Dies bedeutet, dass der Deklarations Kontext für ein `Protected` -Element eine-Klasse sein muss und keine Quelldatei, ein Namespace, eine Schnittstelle, ein Modul, eine Struktur oder eine Prozedur sein darf.</span><span class="sxs-lookup"><span data-stu-id="20539-115">This means the declaration context for a `Protected` element must be a class, and cannot be a source file, namespace, interface, module, structure, or procedure.</span></span>

## <a name="behavior"></a><span data-ttu-id="20539-116">Verhalten</span><span class="sxs-lookup"><span data-stu-id="20539-116">Behavior</span></span>

- <span data-ttu-id="20539-117">**Zugriffsebene.**</span><span class="sxs-lookup"><span data-stu-id="20539-117">**Access Level.**</span></span> <span data-ttu-id="20539-118">Der gesamte Code in einer Klasse kann auf seine Elemente zugreifen.</span><span class="sxs-lookup"><span data-stu-id="20539-118">All code in a class can access its elements.</span></span> <span data-ttu-id="20539-119">Code in jeder Klasse, die von einer Basisklasse abgeleitet ist und in derselben Assembly enthalten ist, kann auf alle `Private Protected` Elemente der Basisklasse zugreifen.</span><span class="sxs-lookup"><span data-stu-id="20539-119">Code in any class that derives from a base class and is contained in the same assembly can access all the `Private Protected` elements of the base class.</span></span> <span data-ttu-id="20539-120">Allerdings kann der Code in jeder Klasse, die von einer Basisklasse abgeleitet ist und in einer anderen Assembly enthalten ist, nicht auf die Basisklassen `Private Protected` Elemente zugreifen.</span><span class="sxs-lookup"><span data-stu-id="20539-120">However, code in any class that derives from a base class and is contained in a different assembly can't access the base class `Private Protected` elements.</span></span>

- <span data-ttu-id="20539-121">**Zugriffsmodifizierer**</span><span class="sxs-lookup"><span data-stu-id="20539-121">**Access Modifiers.**</span></span> <span data-ttu-id="20539-122">Die Schlüsselwörter für die Zugriffsebene werden als *Zugriffsmodifizierer*bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="20539-122">The keywords that specify access level are called *access modifiers*.</span></span> <span data-ttu-id="20539-123">Einen Vergleich der Zugriffsmodifizierer finden Sie unter [Zugriffsebenen in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="20539-123">For a comparison of the access modifiers, see [Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span></span>

<span data-ttu-id="20539-124">Der `Private Protected`-Modifizierer kann in folgenden Kontexten verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="20539-124">The `Private Protected` modifier can be used in these contexts:</span></span>

- <span data-ttu-id="20539-125">[Class-Anweisung](../statements/class-statement.md) einer "netsted"-Klasse</span><span class="sxs-lookup"><span data-stu-id="20539-125">[Class Statement](../statements/class-statement.md) of a nested class</span></span>

- [<span data-ttu-id="20539-126">Const-Anweisung</span><span class="sxs-lookup"><span data-stu-id="20539-126">Const Statement</span></span>](../statements/const-statement.md)

- [<span data-ttu-id="20539-127">Declare Statement</span><span class="sxs-lookup"><span data-stu-id="20539-127">Declare Statement</span></span>](../statements/declare-statement.md)

- <span data-ttu-id="20539-128">[Delegatanweisung](../statements/delegate-statement.md) eines Delegaten, der in einer Klasse eingebettet ist</span><span class="sxs-lookup"><span data-stu-id="20539-128">[Delegate Statement](../statements/delegate-statement.md) of a delegate nested in a class</span></span>

- [<span data-ttu-id="20539-129">Dim-Anweisung</span><span class="sxs-lookup"><span data-stu-id="20539-129">Dim Statement</span></span>](../statements/dim-statement.md)

- <span data-ttu-id="20539-130">[Enumerationsanweisung](../statements/enum-statement.md) einer Enumeration, die in einer Klasse eingefügt ist</span><span class="sxs-lookup"><span data-stu-id="20539-130">[Enum Statement](../statements/enum-statement.md) of an enumeration nested in a class</span></span>

- [<span data-ttu-id="20539-131">Event-Anweisung</span><span class="sxs-lookup"><span data-stu-id="20539-131">Event Statement</span></span>](../statements/event-statement.md)

- [<span data-ttu-id="20539-132">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="20539-132">Function Statement</span></span>](../statements/function-statement.md)

- <span data-ttu-id="20539-133">[Interface-Anweisung](../statements/interface-statement.md) einer Schnittstelle, die in einer Klasse eingebettet ist</span><span class="sxs-lookup"><span data-stu-id="20539-133">[Interface Statement](../statements/interface-statement.md) of an interface nested in a class</span></span>

- [<span data-ttu-id="20539-134">Property Statement</span><span class="sxs-lookup"><span data-stu-id="20539-134">Property Statement</span></span>](../statements/property-statement.md)

- <span data-ttu-id="20539-135">[Structure-Anweisung](../statements/structure-statement.md) einer Struktur, die in einer Klasse eingebettet ist</span><span class="sxs-lookup"><span data-stu-id="20539-135">[Structure Statement](../statements/structure-statement.md) of a structure nested in a class</span></span>

- [<span data-ttu-id="20539-136">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="20539-136">Sub Statement</span></span>](../statements/sub-statement.md)

## <a name="see-also"></a><span data-ttu-id="20539-137">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="20539-137">See also</span></span>

- [<span data-ttu-id="20539-138">Öffentlich</span><span class="sxs-lookup"><span data-stu-id="20539-138">Public</span></span>](public.md)
- [<span data-ttu-id="20539-139">Gebieten</span><span class="sxs-lookup"><span data-stu-id="20539-139">Protected</span></span>](protected.md)
- [<span data-ttu-id="20539-140">Kollegen</span><span class="sxs-lookup"><span data-stu-id="20539-140">Friend</span></span>](friend.md)
- [<span data-ttu-id="20539-141">Privat</span><span class="sxs-lookup"><span data-stu-id="20539-141">Private</span></span>](private.md)
- [<span data-ttu-id="20539-142">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="20539-142">Protected Friend</span></span>](./protected-friend.md)
- [<span data-ttu-id="20539-143">Zugriffsebenen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="20539-143">Access levels in Visual Basic</span></span>](../../programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="20539-144">Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="20539-144">Procedures</span></span>](../../programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="20539-145">Strukturen</span><span class="sxs-lookup"><span data-stu-id="20539-145">Structures</span></span>](../../programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="20539-146">Objekte und Klassen</span><span class="sxs-lookup"><span data-stu-id="20539-146">Objects and Classes</span></span>](../../programming-guide/language-features/objects-and-classes/index.md)
