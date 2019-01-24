---
title: Public (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Public
helpviewer_keywords:
- Public keyword [Visual Basic]
- Public keyword [Visual Basic], syntax
- Public access modifier
ms.assetid: 284c9e1b-ed23-499b-9bc9-ad87c11485a5
ms.openlocfilehash: 062d6276ab91705a4554da2afa8459a26453906f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54703613"
---
# <a name="public-visual-basic"></a><span data-ttu-id="59ad4-102">Public (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="59ad4-102">Public (Visual Basic)</span></span>
<span data-ttu-id="59ad4-103">Gibt an, dass eine oder mehrere deklarierte Programmierelemente über keine zugriffseinschränkungen verfügen.</span><span class="sxs-lookup"><span data-stu-id="59ad4-103">Specifies that one or more declared programming elements have no access restrictions.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="59ad4-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="59ad4-104">Remarks</span></span>  
 <span data-ttu-id="59ad4-105">Wenn Sie eine Komponente oder ein Satz von Komponenten, z. B. eine Klassenbibliothek, veröffentlichen möchten Sie in der Regel die Programmierelemente von jedem Code zugegriffen werden kann, die mit der Assembly interagiert.</span><span class="sxs-lookup"><span data-stu-id="59ad4-105">If you are publishing a component or set of components, such as a class library, you usually want the programming elements to be accessible by any code that interoperates with your assembly.</span></span> <span data-ttu-id="59ad4-106">Um solche unbegrenzten Zugriff auf ein Element gewähren zu können, deklarieren Sie es mit `Public`.</span><span class="sxs-lookup"><span data-stu-id="59ad4-106">To confer such unlimited access on an element, you can declare it with `Public`.</span></span>  
  
 <span data-ttu-id="59ad4-107">Öffentlicher Zugriff ist die normale Zugriffsebene für ein Programmierelement ein Element aus, wenn Sie nicht benötigen, um den Zugriff darauf einschränken.</span><span class="sxs-lookup"><span data-stu-id="59ad4-107">Public access is the normal level for a programming element when you do not need to limit access to it.</span></span> <span data-ttu-id="59ad4-108">Beachten Sie, dass die Zugriffsebene eines Elements innerhalb einer Schnittstelle, Modul, Klasse oder Struktur deklariert ist standardmäßig `Public` , wenn Sie es andernfalls nicht deklarieren.</span><span class="sxs-lookup"><span data-stu-id="59ad4-108">Note that the access level of an element declared within an interface, module, class, or structure defaults to `Public` if you do not declare it otherwise.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="59ad4-109">Regeln</span><span class="sxs-lookup"><span data-stu-id="59ad4-109">Rules</span></span>  
  
-   <span data-ttu-id="59ad4-110">**Deklarationskontext.**</span><span class="sxs-lookup"><span data-stu-id="59ad4-110">**Declaration Context.**</span></span> <span data-ttu-id="59ad4-111">Sie können `Public` nur auf Modul, Schnittstelle oder Namespace-Ebene.</span><span class="sxs-lookup"><span data-stu-id="59ad4-111">You can use `Public` only at module, interface, or namespace level.</span></span> <span data-ttu-id="59ad4-112">Dies bedeutet, dass der Deklarationskontext für eine `Public` Element muss eine Quelldatei, Namespace, Schnittstelle, Modul, Klasse oder Struktur sein, und keine Prozedur sein.</span><span class="sxs-lookup"><span data-stu-id="59ad4-112">This means the declaration context for a `Public` element must be a source file, namespace, interface, module, class, or structure, and cannot be a procedure.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="59ad4-113">Verhalten</span><span class="sxs-lookup"><span data-stu-id="59ad4-113">Behavior</span></span>  
  
-   <span data-ttu-id="59ad4-114">**Zugriffsebene.**</span><span class="sxs-lookup"><span data-stu-id="59ad4-114">**Access Level.**</span></span> <span data-ttu-id="59ad4-115">Sämtlicher Code, der ein Modul, Klasse oder Struktur zugreifen kann kann Zugriff auf seine `Public` Elemente.</span><span class="sxs-lookup"><span data-stu-id="59ad4-115">All code that can access a module, class, or structure can access its `Public` elements.</span></span>  
  
-   <span data-ttu-id="59ad4-116">**Der Standardzugriff.**</span><span class="sxs-lookup"><span data-stu-id="59ad4-116">**Default Access.**</span></span> <span data-ttu-id="59ad4-117">Lokale Variablen in eine Prozedur verfügen standardmäßig die öffentlichen Zugriff, und Sie können keine Zugriffsmodifizierer auf diesen.</span><span class="sxs-lookup"><span data-stu-id="59ad4-117">Local variables inside a procedure default to public access, and you cannot use any access modifiers on them.</span></span>  
  
-   <span data-ttu-id="59ad4-118">**Zugriffsmodifizierer.**</span><span class="sxs-lookup"><span data-stu-id="59ad4-118">**Access Modifiers.**</span></span> <span data-ttu-id="59ad4-119">Die Schlüsselwörter, die Zugriffsebene angeben heißen *Zugriffsmodifizierer*.</span><span class="sxs-lookup"><span data-stu-id="59ad4-119">The keywords that specify access level are called *access modifiers*.</span></span> <span data-ttu-id="59ad4-120">Einen Vergleich der Zugriffsmodifizierer, finden Sie unter [Zugriffsebenen in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="59ad4-120">For a comparison of the access modifiers, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 <span data-ttu-id="59ad4-121">Der `Public`-Modifizierer kann in folgenden Kontexten verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="59ad4-121">The `Public` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="59ad4-122">Class-Anweisung</span><span class="sxs-lookup"><span data-stu-id="59ad4-122">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [<span data-ttu-id="59ad4-123">Const-Anweisung</span><span class="sxs-lookup"><span data-stu-id="59ad4-123">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [<span data-ttu-id="59ad4-124">Declare-Anweisung</span><span class="sxs-lookup"><span data-stu-id="59ad4-124">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [<span data-ttu-id="59ad4-125">Delegate-Anweisung</span><span class="sxs-lookup"><span data-stu-id="59ad4-125">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [<span data-ttu-id="59ad4-126">Dim-Anweisung</span><span class="sxs-lookup"><span data-stu-id="59ad4-126">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="59ad4-127">Enum-Anweisung</span><span class="sxs-lookup"><span data-stu-id="59ad4-127">Enum Statement</span></span>](../../../visual-basic/language-reference/statements/enum-statement.md)  
  
 [<span data-ttu-id="59ad4-128">Event-Anweisung</span><span class="sxs-lookup"><span data-stu-id="59ad4-128">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [<span data-ttu-id="59ad4-129">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="59ad4-129">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="59ad4-130">Interface-Anweisung</span><span class="sxs-lookup"><span data-stu-id="59ad4-130">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [<span data-ttu-id="59ad4-131">Module-Anweisung</span><span class="sxs-lookup"><span data-stu-id="59ad4-131">Module Statement</span></span>](../../../visual-basic/language-reference/statements/module-statement.md)  
  
 [<span data-ttu-id="59ad4-132">Operator-Anweisung</span><span class="sxs-lookup"><span data-stu-id="59ad4-132">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 [<span data-ttu-id="59ad4-133">Property-Anweisung</span><span class="sxs-lookup"><span data-stu-id="59ad4-133">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="59ad4-134">Structure-Anweisung</span><span class="sxs-lookup"><span data-stu-id="59ad4-134">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [<span data-ttu-id="59ad4-135">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="59ad4-135">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="59ad4-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="59ad4-136">See also</span></span>
- [<span data-ttu-id="59ad4-137">Protected</span><span class="sxs-lookup"><span data-stu-id="59ad4-137">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)
- [<span data-ttu-id="59ad4-138">Friend</span><span class="sxs-lookup"><span data-stu-id="59ad4-138">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)
- [<span data-ttu-id="59ad4-139">Private</span><span class="sxs-lookup"><span data-stu-id="59ad4-139">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)
- [<span data-ttu-id="59ad4-140">Private Protected</span><span class="sxs-lookup"><span data-stu-id="59ad4-140">Private Protected</span></span>](private-protected.md)
- [<span data-ttu-id="59ad4-141">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="59ad4-141">Protected Friend</span></span>](protected-friend.md)
- [<span data-ttu-id="59ad4-142">Zugriffsebenen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="59ad4-142">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="59ad4-143">Verfahren</span><span class="sxs-lookup"><span data-stu-id="59ad4-143">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="59ad4-144">Strukturen</span><span class="sxs-lookup"><span data-stu-id="59ad4-144">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="59ad4-145">Objekte und Klassen</span><span class="sxs-lookup"><span data-stu-id="59ad4-145">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
