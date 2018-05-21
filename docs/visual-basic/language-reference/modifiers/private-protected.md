---
title: Private, Protected (Visual Basic)
ms.date: 05/10/2018
helpviewer_keywords:
- Private Protected keyword [Visual Basic]
- Private Protected keyword [Visual Basic], syntax
ms.openlocfilehash: 23fd6583182a1fee544d0458dc3fc390aed86b9f
ms.sourcegitcommit: 22c3c8f74eaa138dbbbb02eb7d720fce87fc30a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/17/2018
---
# <a name="private-protected-visual-basic"></a><span data-ttu-id="5563a-102">Private, Protected (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5563a-102">Private Protected (Visual Basic)</span></span>

<span data-ttu-id="5563a-103">Die Schlüsselwortkombination `Private Protected` ist ein Zugriffsmodifizierer für Member.</span><span class="sxs-lookup"><span data-stu-id="5563a-103">The `Private Protected` keyword combination is a member access modifier.</span></span> <span data-ttu-id="5563a-104">Ein `Private Protected` angehört, zugegriffen werden kann, durch alle Elemente in der enthaltenden Klasse und von Typen, die von der enthaltenden Klasse abgeleitet, jedoch nur, wenn sie in der enthaltenden Assembly gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="5563a-104">A `Private Protected` member is accessible by all members in its containing class, as well as by types derived from the containing class, but only if they are found in its containing assembly.</span></span> 

<span data-ttu-id="5563a-105">Sie können angeben, `Private Protected` nur auf Member von Klassen; können nicht angewendet `Private Protected` zu Membern einer Struktur da Strukturen können nicht vererbt werden.</span><span class="sxs-lookup"><span data-stu-id="5563a-105">You can specify `Private Protected` only on members of classes; you cannot apply `Private Protected` to members of a structure because structures cannot be inherited.</span></span>

<span data-ttu-id="5563a-106">Die `Private Protected` Zugriffsmodifizierer wird von Visual Basic 15.5 und höher unterstützt.</span><span class="sxs-lookup"><span data-stu-id="5563a-106">The `Private Protected` access modifier is supported by Visual Basic 15.5 and later.</span></span> <span data-ttu-id="5563a-107">Um es zu verwenden, können Sie das folgende Element der Visual Basic-Projektdatei (\*.vbproj) hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="5563a-107">To use it, you can add the following element to your Visual Basic project (\*.vbproj) file.</span></span> <span data-ttu-id="5563a-108">Wie lange wie Visual Basic 15.5 oder höher auf Ihrem System installiert ist, können sie alle von der neuesten Version von Visual Basic-Compiler unterstützt Sprachfunktionen zu nutzen:</span><span class="sxs-lookup"><span data-stu-id="5563a-108">As long as Visual Basic 15.5 or later is installed on your system, it lets you take advantage of all the language features supported by the latest version of the Visual Basic compiler:</span></span>

```xml
<PropertyGroup>
   <LangVersion>latest</LangVersion>
</PropertyGroup>
```

> [!NOTE]
> <span data-ttu-id="5563a-109">Wählen Sie in Visual Studio F1-Hilfe auf `private protected` enthält die Hilfe für entweder [private](private.md) oder [geschützt](protected.md).</span><span class="sxs-lookup"><span data-stu-id="5563a-109">In Visual Studio, selecting F1 help on `private protected` provides help for either [private](private.md) or [protected](protected.md).</span></span> <span data-ttu-id="5563a-110">Die IDE wählt der einzelnen Tokens, das unter den Cursor und nicht als zusammengesetztes Wort.</span><span class="sxs-lookup"><span data-stu-id="5563a-110">The IDE picks the single token under the cursor rather than the compound word.</span></span>

## <a name="rules"></a><span data-ttu-id="5563a-111">Regeln</span><span class="sxs-lookup"><span data-stu-id="5563a-111">Rules</span></span>

- <span data-ttu-id="5563a-112">**Deklarationskontext.**</span><span class="sxs-lookup"><span data-stu-id="5563a-112">**Declaration Context.**</span></span> <span data-ttu-id="5563a-113">Sie können `Private Protected` nur auf Klassenebene.</span><span class="sxs-lookup"><span data-stu-id="5563a-113">You can use `Private Protected` only at the class level.</span></span> <span data-ttu-id="5563a-114">Dies bedeutet, dass der Deklarationskontext für eine `Protected` Element muss eine Klasse sein, und eine Quelldatei, Namespace, Schnittstelle, Modul, Struktur oder Prozedur nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="5563a-114">This means the declaration context for a `Protected` element must be a class, and cannot be a source file, namespace, interface, module, structure, or procedure.</span></span>

## <a name="behavior"></a><span data-ttu-id="5563a-115">Verhalten</span><span class="sxs-lookup"><span data-stu-id="5563a-115">Behavior</span></span>

- <span data-ttu-id="5563a-116">**Zugriffsebene.**</span><span class="sxs-lookup"><span data-stu-id="5563a-116">**Access Level.**</span></span> <span data-ttu-id="5563a-117">Der gesamte Code in einer Klasse kann ihre Elemente zugreifen.</span><span class="sxs-lookup"><span data-stu-id="5563a-117">All code in a class can access its elements.</span></span> <span data-ttu-id="5563a-118">Code in einer Klasse, die von einer Basisklasse abgeleitet ist und in derselben Assembly enthalten ist, kann auf alle zugreifen die `Private Protected` Elemente der Basisklasse.</span><span class="sxs-lookup"><span data-stu-id="5563a-118">Code in any class that derives from a base class and is contained in the same assembly can access all the `Private Protected` elements of the base class.</span></span> <span data-ttu-id="5563a-119">Jedoch nicht der Code in einer Klasse, die von einer Basisklasse abgeleitet ist und in einer anderen Assembly enthalten ist die Basisklasse der Klasse zugreifen `Private Protected` Elemente.</span><span class="sxs-lookup"><span data-stu-id="5563a-119">However, code in any class that derives from a base class and is contained in a different assembly can't access the base class `Private Protected` elements.</span></span>

- <span data-ttu-id="5563a-120">**Zugriffsmodifizierer.**</span><span class="sxs-lookup"><span data-stu-id="5563a-120">**Access Modifiers.**</span></span> <span data-ttu-id="5563a-121">Die Schlüsselwörter, die Zugriffsebene angeben heißen *Zugriffsmodifizierer*.</span><span class="sxs-lookup"><span data-stu-id="5563a-121">The keywords that specify access level are called *access modifiers*.</span></span> <span data-ttu-id="5563a-122">Einen Vergleich der Zugriffsmodifizierer, finden Sie unter [Zugriffsebenen in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="5563a-122">For a comparison of the access modifiers, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>
  
 <span data-ttu-id="5563a-123">Der `Private Protected`-Modifizierer kann in folgenden Kontexten verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="5563a-123">The `Private Protected` modifier can be used in these contexts:</span></span>  
  
 <span data-ttu-id="5563a-124">[Class-Anweisung](../../../visual-basic/language-reference/statements/class-statement.md) einer geschachtelten Klasse</span><span class="sxs-lookup"><span data-stu-id="5563a-124">[Class Statement](../../../visual-basic/language-reference/statements/class-statement.md) of a nested class</span></span>  
  
 [<span data-ttu-id="5563a-125">Const-Anweisung</span><span class="sxs-lookup"><span data-stu-id="5563a-125">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [<span data-ttu-id="5563a-126">Declare-Anweisung</span><span class="sxs-lookup"><span data-stu-id="5563a-126">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 <span data-ttu-id="5563a-127">[Delegate-Anweisung](../../../visual-basic/language-reference/statements/delegate-statement.md) eines Delegaten, die in einer Klasse geschachtelt sind</span><span class="sxs-lookup"><span data-stu-id="5563a-127">[Delegate Statement](../../../visual-basic/language-reference/statements/delegate-statement.md) of a delegate nested in a class</span></span>  
  
 [<span data-ttu-id="5563a-128">Dim-Anweisung</span><span class="sxs-lookup"><span data-stu-id="5563a-128">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 <span data-ttu-id="5563a-129">[Enum-Anweisung](../../../visual-basic/language-reference/statements/enum-statement.md) von einer Eumeration, die in einer Klasse geschachtelt sind</span><span class="sxs-lookup"><span data-stu-id="5563a-129">[Enum Statement](../../../visual-basic/language-reference/statements/enum-statement.md) of an eumeration nested in a class</span></span> 
  
 [<span data-ttu-id="5563a-130">Event-Anweisung</span><span class="sxs-lookup"><span data-stu-id="5563a-130">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [<span data-ttu-id="5563a-131">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="5563a-131">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 <span data-ttu-id="5563a-132">[Interface-Anweisung](../../../visual-basic/language-reference/statements/interface-statement.md) einer Schnittstelle, die in einer Klasse geschachtelt sind</span><span class="sxs-lookup"><span data-stu-id="5563a-132">[Interface Statement](../../../visual-basic/language-reference/statements/interface-statement.md) of an interface nested in a class</span></span> 
  
 [<span data-ttu-id="5563a-133">Property-Anweisung</span><span class="sxs-lookup"><span data-stu-id="5563a-133">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 <span data-ttu-id="5563a-134">[Struktur der Anweisung](../../../visual-basic/language-reference/statements/structure-statement.md) einer Struktur geschachtelt werden, in einer Klasse</span><span class="sxs-lookup"><span data-stu-id="5563a-134">[Structure Statement](../../../visual-basic/language-reference/statements/structure-statement.md) of a structure nested in a class</span></span> 
  
 [<span data-ttu-id="5563a-135">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="5563a-135">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="5563a-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5563a-136">See Also</span></span>

[<span data-ttu-id="5563a-137">Public</span><span class="sxs-lookup"><span data-stu-id="5563a-137">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)  
[<span data-ttu-id="5563a-138">Protected</span><span class="sxs-lookup"><span data-stu-id="5563a-138">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)  
<span data-ttu-id="5563a-139">["Friend"](friend.md) </span><span class="sxs-lookup"><span data-stu-id="5563a-139">[Friend](friend.md) </span></span>  
[<span data-ttu-id="5563a-140">Private</span><span class="sxs-lookup"><span data-stu-id="5563a-140">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)  
<span data-ttu-id="5563a-141">[Protected Friend](./protected-friend.md) </span><span class="sxs-lookup"><span data-stu-id="5563a-141">[Protected Friend](./protected-friend.md) </span></span>  
[<span data-ttu-id="5563a-142">Zugriffsebenen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5563a-142">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)  
[<span data-ttu-id="5563a-143">Verfahren</span><span class="sxs-lookup"><span data-stu-id="5563a-143">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
[<span data-ttu-id="5563a-144">Strukturen</span><span class="sxs-lookup"><span data-stu-id="5563a-144">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
[<span data-ttu-id="5563a-145">Objekte und Klassen</span><span class="sxs-lookup"><span data-stu-id="5563a-145">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
