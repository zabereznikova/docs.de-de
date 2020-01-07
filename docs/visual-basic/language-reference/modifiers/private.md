---
title: Private
ms.date: 07/20/2015
f1_keywords:
- vb.Private
helpviewer_keywords:
- Private keyword [Visual Basic]
- Private keyword [Visual Basic], syntax
ms.assetid: aba74a2e-5824-4613-bf63-b9ec7787f4e6
ms.openlocfilehash: 0c855c4e08b365b4cb75ab062d2ec304a79612ab
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75347917"
---
# <a name="private-visual-basic"></a><span data-ttu-id="424de-102">Private (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="424de-102">Private (Visual Basic)</span></span>
<span data-ttu-id="424de-103">Gibt an, dass auf ein oder mehrere deklarierte Programmier Elemente nur innerhalb Ihres Deklarations Kontexts zugegriffen werden kann, einschließlich aus allen enthaltenen Typen.</span><span class="sxs-lookup"><span data-stu-id="424de-103">Specifies that one or more declared programming elements are accessible only from within their declaration context, including from within any contained types.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="424de-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="424de-104">Remarks</span></span>  
 <span data-ttu-id="424de-105">Wenn ein Programmier Element proprietäre Funktionen darstellt oder vertrauliche Daten enthält, sollten Sie den Zugriff auf das Element in der Regel so streng wie möglich einschränken.</span><span class="sxs-lookup"><span data-stu-id="424de-105">If a programming element represents proprietary functionality, or contains confidential data, you usually want to limit access to it as strictly as possible.</span></span> <span data-ttu-id="424de-106">Die maximale Beschränkung erreichen Sie, indem nur das Modul, die Klasse oder die Struktur, die das Modul definiert, für den Zugriff zugelassen wird.</span><span class="sxs-lookup"><span data-stu-id="424de-106">You achieve the maximum limitation by allowing only the module, class, or structure that defines it to access it.</span></span> <span data-ttu-id="424de-107">Um den Zugriff auf ein Element auf diese Weise einzuschränken, können Sie es mit `Private`deklarieren.</span><span class="sxs-lookup"><span data-stu-id="424de-107">To limit access to an element in this way, you can declare it with `Private`.</span></span>  

> [!NOTE]
> <span data-ttu-id="424de-108">Sie können auch den [privaten geschützten](private-protected.md) Zugriffsmodifizierer verwenden, wodurch ein Member innerhalb dieser Klasse und aus abgeleiteten Klassen, die sich in der enthaltenden Assembly befinden, zugänglich ist.</span><span class="sxs-lookup"><span data-stu-id="424de-108">You can also use the [Private Protected](private-protected.md) access modifier, which makes a member accessible from within that class and from derived classes located in its containing assembly.</span></span>

## <a name="rules"></a><span data-ttu-id="424de-109">Regeln</span><span class="sxs-lookup"><span data-stu-id="424de-109">Rules</span></span>  

- <span data-ttu-id="424de-110">**Deklarations Kontext.**</span><span class="sxs-lookup"><span data-stu-id="424de-110">**Declaration Context.**</span></span> <span data-ttu-id="424de-111">Sie können `Private` nur auf Modulebene verwenden.</span><span class="sxs-lookup"><span data-stu-id="424de-111">You can use `Private` only at module level.</span></span> <span data-ttu-id="424de-112">Dies bedeutet, dass der Deklarations Kontext für ein `Private` Element ein Modul, eine Klasse oder eine Struktur sein muss und weder eine Quelldatei noch ein Namespace, eine Schnittstelle oder eine Prozedur sein darf.</span><span class="sxs-lookup"><span data-stu-id="424de-112">This means the declaration context for a `Private` element must be a module, class, or structure, and cannot be a source file, namespace, interface, or procedure.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="424de-113">Verhalten</span><span class="sxs-lookup"><span data-stu-id="424de-113">Behavior</span></span>  
  
- <span data-ttu-id="424de-114">**Zugriffsebene.**</span><span class="sxs-lookup"><span data-stu-id="424de-114">**Access Level.**</span></span> <span data-ttu-id="424de-115">Der gesamte Code in einem Deklarations Kontext kann auf seine `Private` Elemente zugreifen.</span><span class="sxs-lookup"><span data-stu-id="424de-115">All code within a declaration context can access its `Private` elements.</span></span> <span data-ttu-id="424de-116">Dies schließt Code in einem enthaltenen Typ ein, z. b. eine geschachtelte Klasse oder einen Zuweisungs Ausdruck in einer Enumeration.</span><span class="sxs-lookup"><span data-stu-id="424de-116">This includes code within a contained type, such as a nested class or an assignment expression in an enumeration.</span></span> <span data-ttu-id="424de-117">Kein Code außerhalb des Deklarations Kontexts kann auf seine `Private` Elemente zugreifen.</span><span class="sxs-lookup"><span data-stu-id="424de-117">No code outside of the declaration context can access its `Private` elements.</span></span>  
  
- <span data-ttu-id="424de-118">**Zugriffsmodifizierer**</span><span class="sxs-lookup"><span data-stu-id="424de-118">**Access Modifiers.**</span></span> <span data-ttu-id="424de-119">Die Schlüsselwörter für die Zugriffsebene werden als *Zugriffsmodifizierer*bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="424de-119">The keywords that specify access level are called *access modifiers*.</span></span> <span data-ttu-id="424de-120">Einen Vergleich der Zugriffsmodifizierer finden Sie unter [Zugriffsebenen in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="424de-120">For a comparison of the access modifiers, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 <span data-ttu-id="424de-121">Der `Private`-Modifizierer kann in folgenden Kontexten verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="424de-121">The `Private` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="424de-122">Class-Anweisung</span><span class="sxs-lookup"><span data-stu-id="424de-122">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [<span data-ttu-id="424de-123">Const-Anweisung</span><span class="sxs-lookup"><span data-stu-id="424de-123">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [<span data-ttu-id="424de-124">Declare Statement</span><span class="sxs-lookup"><span data-stu-id="424de-124">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [<span data-ttu-id="424de-125">Delegate-Anweisung</span><span class="sxs-lookup"><span data-stu-id="424de-125">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [<span data-ttu-id="424de-126">Dim-Anweisung</span><span class="sxs-lookup"><span data-stu-id="424de-126">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="424de-127">Enum-Anweisung</span><span class="sxs-lookup"><span data-stu-id="424de-127">Enum Statement</span></span>](../../../visual-basic/language-reference/statements/enum-statement.md)  
  
 [<span data-ttu-id="424de-128">Event-Anweisung</span><span class="sxs-lookup"><span data-stu-id="424de-128">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [<span data-ttu-id="424de-129">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="424de-129">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="424de-130">Interface-Anweisung</span><span class="sxs-lookup"><span data-stu-id="424de-130">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [<span data-ttu-id="424de-131">Property-Anweisung</span><span class="sxs-lookup"><span data-stu-id="424de-131">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="424de-132">Structure-Anweisung</span><span class="sxs-lookup"><span data-stu-id="424de-132">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [<span data-ttu-id="424de-133">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="424de-133">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="424de-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="424de-134">See also</span></span>

- [<span data-ttu-id="424de-135">Public</span><span class="sxs-lookup"><span data-stu-id="424de-135">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)
- [<span data-ttu-id="424de-136">Protected</span><span class="sxs-lookup"><span data-stu-id="424de-136">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)
- [<span data-ttu-id="424de-137">Friend</span><span class="sxs-lookup"><span data-stu-id="424de-137">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)
- [<span data-ttu-id="424de-138">Private Protected</span><span class="sxs-lookup"><span data-stu-id="424de-138">Private Protected</span></span>](./private-protected.md)
- [<span data-ttu-id="424de-139">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="424de-139">Protected Friend</span></span>](./protected-friend.md)
- [<span data-ttu-id="424de-140">Zugriffsebenen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="424de-140">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="424de-141">Verfahren</span><span class="sxs-lookup"><span data-stu-id="424de-141">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="424de-142">Strukturen</span><span class="sxs-lookup"><span data-stu-id="424de-142">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="424de-143">Objekte und Klassen</span><span class="sxs-lookup"><span data-stu-id="424de-143">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
