---
title: Private (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Private
helpviewer_keywords:
- Private keyword [Visual Basic]
- Private keyword [Visual Basic], syntax
ms.assetid: aba74a2e-5824-4613-bf63-b9ec7787f4e6
ms.openlocfilehash: d6e28e5e87c3a88e4db3fc81177894683dbb0908
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58819475"
---
# <a name="private-visual-basic"></a><span data-ttu-id="cfd93-102">Private (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cfd93-102">Private (Visual Basic)</span></span>
<span data-ttu-id="cfd93-103">Gibt an, dass eine oder mehrere deklarierte Programmierelemente nur aus ihrem Deklarationskontext einschließlich aus in alle enthaltenen Typen zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="cfd93-103">Specifies that one or more declared programming elements are accessible only from within their declaration context, including from within any contained types.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cfd93-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="cfd93-104">Remarks</span></span>  
 <span data-ttu-id="cfd93-105">Wenn ein Programmierelement proprietäre Funktionalität darstellt, oder vertrauliche Daten enthält, möchten Sie in der Regel den Zugriff darauf so stark wie möglich einschränken.</span><span class="sxs-lookup"><span data-stu-id="cfd93-105">If a programming element represents proprietary functionality, or contains confidential data, you usually want to limit access to it as strictly as possible.</span></span> <span data-ttu-id="cfd93-106">Sie erreichen die Beschränkung auf maximal ermöglicht nur die Module, Klasse oder Struktur, die definiert, um darauf zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="cfd93-106">You achieve the maximum limitation by allowing only the module, class, or structure that defines it to access it.</span></span> <span data-ttu-id="cfd93-107">Um den Zugriff auf ein Element auf diese Weise beschränken, deklarieren Sie es mit `Private`.</span><span class="sxs-lookup"><span data-stu-id="cfd93-107">To limit access to an element in this way, you can declare it with `Private`.</span></span>  

> [!NOTE]
> <span data-ttu-id="cfd93-108">Sie können auch die [Private Protected](private-protected.md) Zugriffsmodifizierer, dadurch wird ein Element aus zugegriffen werden, in der betreffenden Klasse und von abgeleiteten Klassen, die sich in der enthaltenden Assembly befinden.</span><span class="sxs-lookup"><span data-stu-id="cfd93-108">You can also use the [Private Protected](private-protected.md) access modifier, which makes a member accessible from within that class and from derived classes located in its containing assembly.</span></span>

## <a name="rules"></a><span data-ttu-id="cfd93-109">Regeln</span><span class="sxs-lookup"><span data-stu-id="cfd93-109">Rules</span></span>  

-   <span data-ttu-id="cfd93-110">**Deklarationskontext.**</span><span class="sxs-lookup"><span data-stu-id="cfd93-110">**Declaration Context.**</span></span> <span data-ttu-id="cfd93-111">Sie können `Private` nur auf Modulebene verwenden.</span><span class="sxs-lookup"><span data-stu-id="cfd93-111">You can use `Private` only at module level.</span></span> <span data-ttu-id="cfd93-112">Dies bedeutet, dass der Deklarationskontext für eine `Private` Element muss ein Modul, Klasse oder Struktur sein, und eine Quelldatei, Namespace, Schnittstelle oder Prozedur nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="cfd93-112">This means the declaration context for a `Private` element must be a module, class, or structure, and cannot be a source file, namespace, interface, or procedure.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="cfd93-113">Verhalten</span><span class="sxs-lookup"><span data-stu-id="cfd93-113">Behavior</span></span>  
  
-   <span data-ttu-id="cfd93-114">**Zugriffsebene.**</span><span class="sxs-lookup"><span data-stu-id="cfd93-114">**Access Level.**</span></span> <span data-ttu-id="cfd93-115">Sämtlichen Code innerhalb einer Deklarationskontext kann Zugriff auf seine `Private` Elemente.</span><span class="sxs-lookup"><span data-stu-id="cfd93-115">All code within a declaration context can access its `Private` elements.</span></span> <span data-ttu-id="cfd93-116">Dies schließt Code innerhalb eines enthaltenen Typs, z. B. eine geschachtelte Klasse oder eines Zuweisungsausdrucks in einer Enumeration.</span><span class="sxs-lookup"><span data-stu-id="cfd93-116">This includes code within a contained type, such as a nested class or an assignment expression in an enumeration.</span></span> <span data-ttu-id="cfd93-117">Kein Code außerhalb der Deklarationskontext kann Zugriff auf seine `Private` Elemente.</span><span class="sxs-lookup"><span data-stu-id="cfd93-117">No code outside of the declaration context can access its `Private` elements.</span></span>  
  
-   <span data-ttu-id="cfd93-118">**Zugriffsmodifizierer.**</span><span class="sxs-lookup"><span data-stu-id="cfd93-118">**Access Modifiers.**</span></span> <span data-ttu-id="cfd93-119">Die Schlüsselwörter, die Zugriffsebene angeben heißen *Zugriffsmodifizierer*.</span><span class="sxs-lookup"><span data-stu-id="cfd93-119">The keywords that specify access level are called *access modifiers*.</span></span> <span data-ttu-id="cfd93-120">Einen Vergleich der Zugriffsmodifizierer, finden Sie unter [Zugriffsebenen in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="cfd93-120">For a comparison of the access modifiers, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 <span data-ttu-id="cfd93-121">Der `Private`-Modifizierer kann in folgenden Kontexten verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="cfd93-121">The `Private` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="cfd93-122">Class-Anweisung</span><span class="sxs-lookup"><span data-stu-id="cfd93-122">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [<span data-ttu-id="cfd93-123">Const-Anweisung</span><span class="sxs-lookup"><span data-stu-id="cfd93-123">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [<span data-ttu-id="cfd93-124">Declare-Anweisung</span><span class="sxs-lookup"><span data-stu-id="cfd93-124">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [<span data-ttu-id="cfd93-125">Delegate-Anweisung</span><span class="sxs-lookup"><span data-stu-id="cfd93-125">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [<span data-ttu-id="cfd93-126">Dim-Anweisung</span><span class="sxs-lookup"><span data-stu-id="cfd93-126">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="cfd93-127">Enum-Anweisung</span><span class="sxs-lookup"><span data-stu-id="cfd93-127">Enum Statement</span></span>](../../../visual-basic/language-reference/statements/enum-statement.md)  
  
 [<span data-ttu-id="cfd93-128">Event-Anweisung</span><span class="sxs-lookup"><span data-stu-id="cfd93-128">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [<span data-ttu-id="cfd93-129">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="cfd93-129">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="cfd93-130">Interface-Anweisung</span><span class="sxs-lookup"><span data-stu-id="cfd93-130">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [<span data-ttu-id="cfd93-131">Property-Anweisung</span><span class="sxs-lookup"><span data-stu-id="cfd93-131">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="cfd93-132">Structure-Anweisung</span><span class="sxs-lookup"><span data-stu-id="cfd93-132">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [<span data-ttu-id="cfd93-133">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="cfd93-133">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="cfd93-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cfd93-134">See also</span></span>

- [<span data-ttu-id="cfd93-135">Public</span><span class="sxs-lookup"><span data-stu-id="cfd93-135">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)
- [<span data-ttu-id="cfd93-136">Protected</span><span class="sxs-lookup"><span data-stu-id="cfd93-136">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)
- [<span data-ttu-id="cfd93-137">Friend</span><span class="sxs-lookup"><span data-stu-id="cfd93-137">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)
- [<span data-ttu-id="cfd93-138">Private Protected</span><span class="sxs-lookup"><span data-stu-id="cfd93-138">Private Protected</span></span>](./private-protected.md)
- <span data-ttu-id="cfd93-139">[Protected Friend](./protected-friend.md)[Zugriffsebenen in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)</span><span class="sxs-lookup"><span data-stu-id="cfd93-139">[Protected Friend](./protected-friend.md)    [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)</span></span>
- [<span data-ttu-id="cfd93-140">Verfahren</span><span class="sxs-lookup"><span data-stu-id="cfd93-140">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="cfd93-141">Strukturen</span><span class="sxs-lookup"><span data-stu-id="cfd93-141">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="cfd93-142">Objekte und Klassen</span><span class="sxs-lookup"><span data-stu-id="cfd93-142">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
