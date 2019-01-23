---
title: Protected (Visual Basic)
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
ms.openlocfilehash: 40dda40f68e535380a82a241e3ccd383b0c9809f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54536294"
---
# <a name="protected-visual-basic"></a><span data-ttu-id="554a4-102">Protected (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="554a4-102">Protected (Visual Basic)</span></span>
<span data-ttu-id="554a4-103">Ein Zugriffsmodifizierer für Member, der angibt, dass eine oder mehrere Programmierelemente deklarierte sind nur von innerhalb ihrer eigenen Klasse oder von einer abgeleiteten Klasse zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="554a4-103">A member access modifier that specifies that one or more declared programming elements are accessible only from within their own class or from a derived class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="554a4-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="554a4-104">Remarks</span></span>  
 <span data-ttu-id="554a4-105">Manchmal enthält ein Programmierelement, das in einer Klasse deklariert, vertrauliche Daten oder eingeschränkten Code, und Sie Zugriff auf das Element einschränken möchten.</span><span class="sxs-lookup"><span data-stu-id="554a4-105">Sometimes a programming element declared in a class contains sensitive data or restricted code, and you want to limit access to the element.</span></span> <span data-ttu-id="554a4-106">Wenn die Klasse geerbt wird, und Sie erwarten, eine Hierarchie von abgeleiteten Klassen dass, sie für diese abgeleiteten Klassen Zugriff auf die Daten oder Code erforderlich sind möglicherweise jedoch.</span><span class="sxs-lookup"><span data-stu-id="554a4-106">However, if the class is inheritable and you expect a hierarchy of derived classes, it might be necessary for these derived classes to access the data or code.</span></span> <span data-ttu-id="554a4-107">In diesem Fall möchten Sie das Element, das sowohl von der Basisklasse als auch von allen abgeleiteten Klassen zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="554a4-107">In such a case, you want the element to be accessible both from the base class and from all derived classes.</span></span> <span data-ttu-id="554a4-108">Um den Zugriff auf ein Element auf diese Weise beschränken, deklarieren Sie es mit `Protected`.</span><span class="sxs-lookup"><span data-stu-id="554a4-108">To limit access to an element in this manner, you can declare it with `Protected`.</span></span>  

> [!NOTE]
> <span data-ttu-id="554a4-109">Die `Protected` Zugriffsmodifizierer mit zwei andere Modifizierer kombiniert werden kann:</span><span class="sxs-lookup"><span data-stu-id="554a4-109">The `Protected` access modifier can be combined with two other modifiers:</span></span>
> - <span data-ttu-id="554a4-110">Die [Protected Friend](protected-friend.md) Modifizierer macht einen Klassenmember kann innerhalb dieser Klasse, aus der gleichen Assembly, die in der die Klasse definiert ist und von abgeleiteten Klassen zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="554a4-110">The [Protected Friend](protected-friend.md) modifier makes a class member accessible from within that class, from derived classes, and from the same assembly in which the class is defined.</span></span> 
> - <span data-ttu-id="554a4-111">Die [Private Protected](private-protected.md) Modifizierer macht einen Klassenmember von abgeleiteten Typen, jedoch nur innerhalb der enthaltenden Assembly zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="554a4-111">The [Private Protected](private-protected.md) modifier makes a class member accessible by derived types, but only within its containing assembly.</span></span>
  
## <a name="rules"></a><span data-ttu-id="554a4-112">Regeln</span><span class="sxs-lookup"><span data-stu-id="554a4-112">Rules</span></span>  
  
-   <span data-ttu-id="554a4-113">**Deklarationskontext.**</span><span class="sxs-lookup"><span data-stu-id="554a4-113">**Declaration Context.**</span></span> <span data-ttu-id="554a4-114">Sie können `Protected` nur auf Klassenebene.</span><span class="sxs-lookup"><span data-stu-id="554a4-114">You can use `Protected` only at the class level.</span></span> <span data-ttu-id="554a4-115">Dies bedeutet, dass der Deklarationskontext für eine `Protected` Element muss eine Klasse sein, und eine Quelldatei, Namespace, Schnittstelle, Modul, Struktur oder Prozedur nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="554a4-115">This means the declaration context for a `Protected` element must be a class, and cannot be a source file, namespace, interface, module, structure, or procedure.</span></span>  

## <a name="behavior"></a><span data-ttu-id="554a4-116">Verhalten</span><span class="sxs-lookup"><span data-stu-id="554a4-116">Behavior</span></span>  
  
-   <span data-ttu-id="554a4-117">**Zugriffsebene.**</span><span class="sxs-lookup"><span data-stu-id="554a4-117">**Access Level.**</span></span> <span data-ttu-id="554a4-118">Gesamten Code in einer Klasse kann Zugriff auf die Elemente auf.</span><span class="sxs-lookup"><span data-stu-id="554a4-118">All code in a class can access its elements.</span></span> <span data-ttu-id="554a4-119">Code in einer Klasse, die von einer Basisklasse abgeleitet wird, kann auf alle zugreifen der `Protected` Elemente der Basisklasse.</span><span class="sxs-lookup"><span data-stu-id="554a4-119">Code in any class that derives from a base class can access all the `Protected` elements of the base class.</span></span> <span data-ttu-id="554a4-120">Dies gilt für alle Generationen der Ableitung.</span><span class="sxs-lookup"><span data-stu-id="554a4-120">This is true for all generations of derivation.</span></span> <span data-ttu-id="554a4-121">Dies bedeutet, dass der Zugriff auf eine Klasse kann `Protected` Elemente der Basisklasse der Basisklasse und So weiter.</span><span class="sxs-lookup"><span data-stu-id="554a4-121">This means that a class can access `Protected` elements of the base class of the base class, and so on.</span></span>  
  
     <span data-ttu-id="554a4-122">Geschützter Zugriff ist nicht auf, eine Obermenge oder eine Teilmenge der Friend-Zugriff.</span><span class="sxs-lookup"><span data-stu-id="554a4-122">Protected access is not a superset or subset of friend access.</span></span>  
  
-   <span data-ttu-id="554a4-123">**Zugriffsmodifizierer.**</span><span class="sxs-lookup"><span data-stu-id="554a4-123">**Access Modifiers.**</span></span> <span data-ttu-id="554a4-124">Die Schlüsselwörter, die Zugriffsebene angeben heißen *Zugriffsmodifizierer*.</span><span class="sxs-lookup"><span data-stu-id="554a4-124">The keywords that specify access level are called *access modifiers*.</span></span> <span data-ttu-id="554a4-125">Einen Vergleich der Zugriffsmodifizierer, finden Sie unter [Zugriffsebenen in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="554a4-125">For a comparison of the access modifiers, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 <span data-ttu-id="554a4-126">Der `Protected`-Modifizierer kann in folgenden Kontexten verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="554a4-126">The `Protected` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="554a4-127">Class-Anweisung</span><span class="sxs-lookup"><span data-stu-id="554a4-127">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [<span data-ttu-id="554a4-128">Const-Anweisung</span><span class="sxs-lookup"><span data-stu-id="554a4-128">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [<span data-ttu-id="554a4-129">Declare-Anweisung</span><span class="sxs-lookup"><span data-stu-id="554a4-129">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [<span data-ttu-id="554a4-130">Delegate-Anweisung</span><span class="sxs-lookup"><span data-stu-id="554a4-130">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [<span data-ttu-id="554a4-131">Dim-Anweisung</span><span class="sxs-lookup"><span data-stu-id="554a4-131">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="554a4-132">Enum-Anweisung</span><span class="sxs-lookup"><span data-stu-id="554a4-132">Enum Statement</span></span>](../../../visual-basic/language-reference/statements/enum-statement.md)  
  
 [<span data-ttu-id="554a4-133">Event-Anweisung</span><span class="sxs-lookup"><span data-stu-id="554a4-133">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [<span data-ttu-id="554a4-134">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="554a4-134">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="554a4-135">Interface-Anweisung</span><span class="sxs-lookup"><span data-stu-id="554a4-135">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [<span data-ttu-id="554a4-136">Property-Anweisung</span><span class="sxs-lookup"><span data-stu-id="554a4-136">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="554a4-137">Structure-Anweisung</span><span class="sxs-lookup"><span data-stu-id="554a4-137">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [<span data-ttu-id="554a4-138">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="554a4-138">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="554a4-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="554a4-139">See also</span></span>
- [<span data-ttu-id="554a4-140">Public</span><span class="sxs-lookup"><span data-stu-id="554a4-140">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)
- [<span data-ttu-id="554a4-141">Friend</span><span class="sxs-lookup"><span data-stu-id="554a4-141">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)
- [<span data-ttu-id="554a4-142">Private</span><span class="sxs-lookup"><span data-stu-id="554a4-142">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)
- [<span data-ttu-id="554a4-143">Private Protected</span><span class="sxs-lookup"><span data-stu-id="554a4-143">Private Protected</span></span>](private-protected.md)
- [<span data-ttu-id="554a4-144">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="554a4-144">Protected Friend</span></span>](protected-friend.md)
- [<span data-ttu-id="554a4-145">Zugriffsebenen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="554a4-145">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="554a4-146">Verfahren</span><span class="sxs-lookup"><span data-stu-id="554a4-146">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="554a4-147">Strukturen</span><span class="sxs-lookup"><span data-stu-id="554a4-147">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="554a4-148">Objekte und Klassen</span><span class="sxs-lookup"><span data-stu-id="554a4-148">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
