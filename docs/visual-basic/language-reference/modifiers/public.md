---
title: Öffentlich
ms.date: 07/20/2015
f1_keywords:
- vb.Public
helpviewer_keywords:
- Public keyword [Visual Basic]
- Public keyword [Visual Basic], syntax
- Public access modifier
ms.assetid: 284c9e1b-ed23-499b-9bc9-ad87c11485a5
ms.openlocfilehash: 35bf1a65e0b8f24a1263adc480719c69b95dff9b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351293"
---
# <a name="public-visual-basic"></a><span data-ttu-id="11749-102">Public (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="11749-102">Public (Visual Basic)</span></span>
<span data-ttu-id="11749-103">Gibt an, dass ein oder mehrere deklarierte Programmier Elemente über keine Zugriffs Einschränkungen verfügen.</span><span class="sxs-lookup"><span data-stu-id="11749-103">Specifies that one or more declared programming elements have no access restrictions.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="11749-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="11749-104">Remarks</span></span>  
 <span data-ttu-id="11749-105">Wenn Sie eine Komponente oder eine Gruppe von Komponenten veröffentlichen (z. b. eine Klassenbibliothek), möchten Sie in der Regel von jedem Code, der mit der Assembly interagiert, auf die Programmier Elemente zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="11749-105">If you are publishing a component or set of components, such as a class library, you usually want the programming elements to be accessible by any code that interoperates with your assembly.</span></span> <span data-ttu-id="11749-106">Um einen solchen uneingeschränkten Zugriff auf ein Element zu gewähren, können Sie es mit `Public`deklarieren.</span><span class="sxs-lookup"><span data-stu-id="11749-106">To confer such unlimited access on an element, you can declare it with `Public`.</span></span>  
  
 <span data-ttu-id="11749-107">Der öffentliche Zugriff ist die normale Ebene für ein Programmier Element, wenn Sie den Zugriff darauf nicht einschränken müssen.</span><span class="sxs-lookup"><span data-stu-id="11749-107">Public access is the normal level for a programming element when you do not need to limit access to it.</span></span> <span data-ttu-id="11749-108">Beachten Sie, dass die Zugriffsebene eines Elements, das in einer Schnittstelle, einem Modul, einer Klasse oder einer Struktur deklariert ist, standardmäßig `Public`, wenn Sie es nicht anders deklarieren.</span><span class="sxs-lookup"><span data-stu-id="11749-108">Note that the access level of an element declared within an interface, module, class, or structure defaults to `Public` if you do not declare it otherwise.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="11749-109">Regeln</span><span class="sxs-lookup"><span data-stu-id="11749-109">Rules</span></span>  
  
- <span data-ttu-id="11749-110">**Deklarations Kontext.**</span><span class="sxs-lookup"><span data-stu-id="11749-110">**Declaration Context.**</span></span> <span data-ttu-id="11749-111">Sie können `Public` nur auf der Ebene "Module", "Interface" oder "Namespace" verwenden.</span><span class="sxs-lookup"><span data-stu-id="11749-111">You can use `Public` only at module, interface, or namespace level.</span></span> <span data-ttu-id="11749-112">Dies bedeutet, dass der Deklarations Kontext für ein `Public` Element eine Quelldatei, ein Namespace, eine Schnittstelle, ein Modul, eine Klasse oder eine Struktur sein muss und keine Prozedur sein muss.</span><span class="sxs-lookup"><span data-stu-id="11749-112">This means the declaration context for a `Public` element must be a source file, namespace, interface, module, class, or structure, and cannot be a procedure.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="11749-113">Verhalten</span><span class="sxs-lookup"><span data-stu-id="11749-113">Behavior</span></span>  
  
- <span data-ttu-id="11749-114">**Zugriffsebene.**</span><span class="sxs-lookup"><span data-stu-id="11749-114">**Access Level.**</span></span> <span data-ttu-id="11749-115">Sämtlicher Code, der auf ein Modul, eine Klasse oder eine Struktur zugreifen kann, kann auf seine `Public` Elemente zugreifen.</span><span class="sxs-lookup"><span data-stu-id="11749-115">All code that can access a module, class, or structure can access its `Public` elements.</span></span>  
  
- <span data-ttu-id="11749-116">**Standard Zugriff.**</span><span class="sxs-lookup"><span data-stu-id="11749-116">**Default Access.**</span></span> <span data-ttu-id="11749-117">Lokale Variablen innerhalb einer Prozedur werden standardmäßig auf den öffentlichen Zugriff fest, und Sie können keine Zugriffsmodifizierer verwenden.</span><span class="sxs-lookup"><span data-stu-id="11749-117">Local variables inside a procedure default to public access, and you cannot use any access modifiers on them.</span></span>  
  
- <span data-ttu-id="11749-118">**Zugriffsmodifizierer**</span><span class="sxs-lookup"><span data-stu-id="11749-118">**Access Modifiers.**</span></span> <span data-ttu-id="11749-119">Die Schlüsselwörter für die Zugriffsebene werden als *Zugriffsmodifizierer*bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="11749-119">The keywords that specify access level are called *access modifiers*.</span></span> <span data-ttu-id="11749-120">Einen Vergleich der Zugriffsmodifizierer finden Sie unter [Zugriffsebenen in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="11749-120">For a comparison of the access modifiers, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 <span data-ttu-id="11749-121">Der `Public`-Modifizierer kann in folgenden Kontexten verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="11749-121">The `Public` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="11749-122">Class-Anweisung</span><span class="sxs-lookup"><span data-stu-id="11749-122">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [<span data-ttu-id="11749-123">Const-Anweisung</span><span class="sxs-lookup"><span data-stu-id="11749-123">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [<span data-ttu-id="11749-124">Declare-Anweisung</span><span class="sxs-lookup"><span data-stu-id="11749-124">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [<span data-ttu-id="11749-125">Delegate-Anweisung</span><span class="sxs-lookup"><span data-stu-id="11749-125">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [<span data-ttu-id="11749-126">Dim-Anweisung</span><span class="sxs-lookup"><span data-stu-id="11749-126">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="11749-127">Enum-Anweisung</span><span class="sxs-lookup"><span data-stu-id="11749-127">Enum Statement</span></span>](../../../visual-basic/language-reference/statements/enum-statement.md)  
  
 [<span data-ttu-id="11749-128">Event-Anweisung</span><span class="sxs-lookup"><span data-stu-id="11749-128">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [<span data-ttu-id="11749-129">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="11749-129">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="11749-130">Interface-Anweisung</span><span class="sxs-lookup"><span data-stu-id="11749-130">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [<span data-ttu-id="11749-131">Module-Anweisung</span><span class="sxs-lookup"><span data-stu-id="11749-131">Module Statement</span></span>](../../../visual-basic/language-reference/statements/module-statement.md)  
  
 [<span data-ttu-id="11749-132">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="11749-132">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 [<span data-ttu-id="11749-133">Property-Anweisung</span><span class="sxs-lookup"><span data-stu-id="11749-133">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="11749-134">Structure-Anweisung</span><span class="sxs-lookup"><span data-stu-id="11749-134">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [<span data-ttu-id="11749-135">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="11749-135">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="11749-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="11749-136">See also</span></span>

- [<span data-ttu-id="11749-137">Protected</span><span class="sxs-lookup"><span data-stu-id="11749-137">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)
- [<span data-ttu-id="11749-138">Friend</span><span class="sxs-lookup"><span data-stu-id="11749-138">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)
- [<span data-ttu-id="11749-139">Private</span><span class="sxs-lookup"><span data-stu-id="11749-139">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)
- [<span data-ttu-id="11749-140">Private Protected</span><span class="sxs-lookup"><span data-stu-id="11749-140">Private Protected</span></span>](private-protected.md)
- [<span data-ttu-id="11749-141">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="11749-141">Protected Friend</span></span>](protected-friend.md)
- [<span data-ttu-id="11749-142">Zugriffsebenen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="11749-142">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="11749-143">Verfahren</span><span class="sxs-lookup"><span data-stu-id="11749-143">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="11749-144">Strukturen</span><span class="sxs-lookup"><span data-stu-id="11749-144">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="11749-145">Objekte und Klassen</span><span class="sxs-lookup"><span data-stu-id="11749-145">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
