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
ms.openlocfilehash: a5e9161132ba6d571daa30ce82e1bfb1dd2b064f
ms.sourcegitcommit: 22c3c8f74eaa138dbbbb02eb7d720fce87fc30a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/17/2018
---
# <a name="public-visual-basic"></a><span data-ttu-id="267f3-102">Public (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="267f3-102">Public (Visual Basic)</span></span>
<span data-ttu-id="267f3-103">Gibt an, dass eine oder mehrere deklarierte Programmierelemente uneingeschränkt Zugriff haben.</span><span class="sxs-lookup"><span data-stu-id="267f3-103">Specifies that one or more declared programming elements have no access restrictions.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="267f3-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="267f3-104">Remarks</span></span>  
 <span data-ttu-id="267f3-105">Wenn Sie eine Komponente oder ein Satz von Komponenten, z. B. eine Klassenbibliothek, veröffentlichen möchten Sie in der Regel die Programmierelemente von jedem Code zugegriffen werden kann, die mit der Assembly interagiert.</span><span class="sxs-lookup"><span data-stu-id="267f3-105">If you are publishing a component or set of components, such as a class library, you usually want the programming elements to be accessible by any code that interoperates with your assembly.</span></span> <span data-ttu-id="267f3-106">Um solche unbegrenzten Zugriff auf ein Element zu gewähren, deklarieren Sie ihn mit `Public`.</span><span class="sxs-lookup"><span data-stu-id="267f3-106">To confer such unlimited access on an element, you can declare it with `Public`.</span></span>  
  
 <span data-ttu-id="267f3-107">Öffentlicher Zugriff ist der normale Ebene für ein Programmierelement, wenn Sie nicht benötigen, um den Zugriff darauf zu beschränken.</span><span class="sxs-lookup"><span data-stu-id="267f3-107">Public access is the normal level for a programming element when you do not need to limit access to it.</span></span> <span data-ttu-id="267f3-108">Beachten Sie, dass die Zugriffsebene eines Elements innerhalb einer Schnittstelle, Modul, Klasse oder Struktur deklariert wird standardmäßig auf `Public` , wenn Sie es andernfalls nicht deklarieren.</span><span class="sxs-lookup"><span data-stu-id="267f3-108">Note that the access level of an element declared within an interface, module, class, or structure defaults to `Public` if you do not declare it otherwise.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="267f3-109">Regeln</span><span class="sxs-lookup"><span data-stu-id="267f3-109">Rules</span></span>  
  
-   <span data-ttu-id="267f3-110">**Deklarationskontext.**</span><span class="sxs-lookup"><span data-stu-id="267f3-110">**Declaration Context.**</span></span> <span data-ttu-id="267f3-111">Sie können `Public` nur auf Modul, Schnittstelle oder Namespace-Ebene.</span><span class="sxs-lookup"><span data-stu-id="267f3-111">You can use `Public` only at module, interface, or namespace level.</span></span> <span data-ttu-id="267f3-112">Dies bedeutet, dass der Deklarationskontext für eine `Public` Element muss eine Quelldatei, Namespace, Schnittstelle, Modul, Klasse oder Struktur sein und darf keine Prozedur sein.</span><span class="sxs-lookup"><span data-stu-id="267f3-112">This means the declaration context for a `Public` element must be a source file, namespace, interface, module, class, or structure, and cannot be a procedure.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="267f3-113">Verhalten</span><span class="sxs-lookup"><span data-stu-id="267f3-113">Behavior</span></span>  
  
-   <span data-ttu-id="267f3-114">**Zugriffsebene.**</span><span class="sxs-lookup"><span data-stu-id="267f3-114">**Access Level.**</span></span> <span data-ttu-id="267f3-115">Der gesamte Code, der ein Modul, Klasse oder Struktur zugreifen kann erreichen die `Public` Elemente.</span><span class="sxs-lookup"><span data-stu-id="267f3-115">All code that can access a module, class, or structure can access its `Public` elements.</span></span>  
  
-   <span data-ttu-id="267f3-116">**Der Standardzugriff.**</span><span class="sxs-lookup"><span data-stu-id="267f3-116">**Default Access.**</span></span> <span data-ttu-id="267f3-117">Keine Zugriffsmodifizierer können keine lokale Variablen in einer Prozedur erhalten standardmäßig öffentlichen Zugriff, und Sie darauf.</span><span class="sxs-lookup"><span data-stu-id="267f3-117">Local variables inside a procedure default to public access, and you cannot use any access modifiers on them.</span></span>  
  
-   <span data-ttu-id="267f3-118">**Zugriffsmodifizierer.**</span><span class="sxs-lookup"><span data-stu-id="267f3-118">**Access Modifiers.**</span></span> <span data-ttu-id="267f3-119">Die Schlüsselwörter, die Zugriffsebene angeben heißen *Zugriffsmodifizierer*.</span><span class="sxs-lookup"><span data-stu-id="267f3-119">The keywords that specify access level are called *access modifiers*.</span></span> <span data-ttu-id="267f3-120">Einen Vergleich der Zugriffsmodifizierer, finden Sie unter [Zugriffsebenen in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="267f3-120">For a comparison of the access modifiers, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 <span data-ttu-id="267f3-121">Der `Public`-Modifizierer kann in folgenden Kontexten verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="267f3-121">The `Public` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="267f3-122">Class-Anweisung</span><span class="sxs-lookup"><span data-stu-id="267f3-122">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [<span data-ttu-id="267f3-123">Const-Anweisung</span><span class="sxs-lookup"><span data-stu-id="267f3-123">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [<span data-ttu-id="267f3-124">Declare-Anweisung</span><span class="sxs-lookup"><span data-stu-id="267f3-124">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [<span data-ttu-id="267f3-125">Delegate-Anweisung</span><span class="sxs-lookup"><span data-stu-id="267f3-125">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [<span data-ttu-id="267f3-126">Dim-Anweisung</span><span class="sxs-lookup"><span data-stu-id="267f3-126">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="267f3-127">Enum-Anweisung</span><span class="sxs-lookup"><span data-stu-id="267f3-127">Enum Statement</span></span>](../../../visual-basic/language-reference/statements/enum-statement.md)  
  
 [<span data-ttu-id="267f3-128">Event-Anweisung</span><span class="sxs-lookup"><span data-stu-id="267f3-128">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [<span data-ttu-id="267f3-129">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="267f3-129">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="267f3-130">Interface-Anweisung</span><span class="sxs-lookup"><span data-stu-id="267f3-130">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [<span data-ttu-id="267f3-131">Module-Anweisung</span><span class="sxs-lookup"><span data-stu-id="267f3-131">Module Statement</span></span>](../../../visual-basic/language-reference/statements/module-statement.md)  
  
 [<span data-ttu-id="267f3-132">Operator-Anweisung</span><span class="sxs-lookup"><span data-stu-id="267f3-132">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 [<span data-ttu-id="267f3-133">Property-Anweisung</span><span class="sxs-lookup"><span data-stu-id="267f3-133">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="267f3-134">Structure-Anweisung</span><span class="sxs-lookup"><span data-stu-id="267f3-134">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [<span data-ttu-id="267f3-135">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="267f3-135">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="267f3-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="267f3-136">See Also</span></span>  
 [<span data-ttu-id="267f3-137">Protected</span><span class="sxs-lookup"><span data-stu-id="267f3-137">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)  
 [<span data-ttu-id="267f3-138">Friend</span><span class="sxs-lookup"><span data-stu-id="267f3-138">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)  
 [<span data-ttu-id="267f3-139">Private</span><span class="sxs-lookup"><span data-stu-id="267f3-139">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)  
 <span data-ttu-id="267f3-140">[Geschützt privat](private-protected.md) </span><span class="sxs-lookup"><span data-stu-id="267f3-140">[Private Protected](private-protected.md) </span></span>  
 <span data-ttu-id="267f3-141">[Protected Friend](protected-friend.md) </span><span class="sxs-lookup"><span data-stu-id="267f3-141">[Protected Friend](protected-friend.md) </span></span>  
 [<span data-ttu-id="267f3-142">Zugriffsebenen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="267f3-142">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)  
 [<span data-ttu-id="267f3-143">Verfahren</span><span class="sxs-lookup"><span data-stu-id="267f3-143">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
 [<span data-ttu-id="267f3-144">Strukturen</span><span class="sxs-lookup"><span data-stu-id="267f3-144">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [<span data-ttu-id="267f3-145">Objekte und Klassen</span><span class="sxs-lookup"><span data-stu-id="267f3-145">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
