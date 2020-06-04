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
ms.openlocfilehash: 35332e50227cdef6386362df17c10b5b2cdaa689
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84415348"
---
# <a name="public-visual-basic"></a><span data-ttu-id="e87be-102">Public (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e87be-102">Public (Visual Basic)</span></span>
<span data-ttu-id="e87be-103">Gibt an, dass ein oder mehrere deklarierte Programmier Elemente über keine Zugriffs Einschränkungen verfügen.</span><span class="sxs-lookup"><span data-stu-id="e87be-103">Specifies that one or more declared programming elements have no access restrictions.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e87be-104">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="e87be-104">Remarks</span></span>  
 <span data-ttu-id="e87be-105">Wenn Sie eine Komponente oder eine Gruppe von Komponenten veröffentlichen (z. b. eine Klassenbibliothek), möchten Sie in der Regel von jedem Code, der mit der Assembly interagiert, auf die Programmier Elemente zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="e87be-105">If you are publishing a component or set of components, such as a class library, you usually want the programming elements to be accessible by any code that interoperates with your assembly.</span></span> <span data-ttu-id="e87be-106">Um einen solchen uneingeschränkten Zugriff auf ein Element zu gewähren, können Sie es mit deklarieren `Public` .</span><span class="sxs-lookup"><span data-stu-id="e87be-106">To confer such unlimited access on an element, you can declare it with `Public`.</span></span>  
  
 <span data-ttu-id="e87be-107">Der öffentliche Zugriff ist die normale Ebene für ein Programmier Element, wenn Sie den Zugriff darauf nicht einschränken müssen.</span><span class="sxs-lookup"><span data-stu-id="e87be-107">Public access is the normal level for a programming element when you do not need to limit access to it.</span></span> <span data-ttu-id="e87be-108">Beachten Sie, dass die Zugriffsebene eines Elements, das innerhalb einer Schnittstelle, eines Moduls, einer Klasse oder einer Struktur deklariert ist, standardmäßig auf festgelegt ist, `Public` Wenn Sie es nicht andernfalls</span><span class="sxs-lookup"><span data-stu-id="e87be-108">Note that the access level of an element declared within an interface, module, class, or structure defaults to `Public` if you do not declare it otherwise.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="e87be-109">Regeln</span><span class="sxs-lookup"><span data-stu-id="e87be-109">Rules</span></span>  
  
- <span data-ttu-id="e87be-110">**Deklarationskontext.**</span><span class="sxs-lookup"><span data-stu-id="e87be-110">**Declaration Context.**</span></span> <span data-ttu-id="e87be-111">Sie können `Public` nur auf der Ebene "Module", "Interface" oder "Namespace" verwenden.</span><span class="sxs-lookup"><span data-stu-id="e87be-111">You can use `Public` only at module, interface, or namespace level.</span></span> <span data-ttu-id="e87be-112">Dies bedeutet, dass der Deklarations Kontext für ein- `Public` Element eine Quelldatei, ein Namespace, eine Schnittstelle, ein Modul, eine Klasse oder eine Struktur sein muss und keine Prozedur sein muss.</span><span class="sxs-lookup"><span data-stu-id="e87be-112">This means the declaration context for a `Public` element must be a source file, namespace, interface, module, class, or structure, and cannot be a procedure.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="e87be-113">Verhalten</span><span class="sxs-lookup"><span data-stu-id="e87be-113">Behavior</span></span>  
  
- <span data-ttu-id="e87be-114">**Zugriffsebene.**</span><span class="sxs-lookup"><span data-stu-id="e87be-114">**Access Level.**</span></span> <span data-ttu-id="e87be-115">Sämtlicher Code, der auf ein Modul, eine Klasse oder eine Struktur zugreifen kann, kann auf seine `Public` Elemente zugreifen.</span><span class="sxs-lookup"><span data-stu-id="e87be-115">All code that can access a module, class, or structure can access its `Public` elements.</span></span>  
  
- <span data-ttu-id="e87be-116">**Standard Zugriff.**</span><span class="sxs-lookup"><span data-stu-id="e87be-116">**Default Access.**</span></span> <span data-ttu-id="e87be-117">Lokale Variablen innerhalb einer Prozedur werden standardmäßig auf den öffentlichen Zugriff fest, und Sie können keine Zugriffsmodifizierer verwenden.</span><span class="sxs-lookup"><span data-stu-id="e87be-117">Local variables inside a procedure default to public access, and you cannot use any access modifiers on them.</span></span>  
  
- <span data-ttu-id="e87be-118">**Zugriffsmodifizierer**</span><span class="sxs-lookup"><span data-stu-id="e87be-118">**Access Modifiers.**</span></span> <span data-ttu-id="e87be-119">Die Schlüsselwörter für die Zugriffsebene werden als *Zugriffsmodifizierer*bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="e87be-119">The keywords that specify access level are called *access modifiers*.</span></span> <span data-ttu-id="e87be-120">Einen Vergleich der Zugriffsmodifizierer finden Sie unter [Zugriffsebenen in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="e87be-120">For a comparison of the access modifiers, see [Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 <span data-ttu-id="e87be-121">Der `Public`-Modifizierer kann in folgenden Kontexten verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="e87be-121">The `Public` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="e87be-122">Class-Anweisung</span><span class="sxs-lookup"><span data-stu-id="e87be-122">Class Statement</span></span>](../statements/class-statement.md)  
  
 [<span data-ttu-id="e87be-123">Const-Anweisung</span><span class="sxs-lookup"><span data-stu-id="e87be-123">Const Statement</span></span>](../statements/const-statement.md)  
  
 [<span data-ttu-id="e87be-124">Declare Statement</span><span class="sxs-lookup"><span data-stu-id="e87be-124">Declare Statement</span></span>](../statements/declare-statement.md)  
  
 [<span data-ttu-id="e87be-125">Delegate-Anweisung</span><span class="sxs-lookup"><span data-stu-id="e87be-125">Delegate Statement</span></span>](../statements/delegate-statement.md)  
  
 [<span data-ttu-id="e87be-126">Dim-Anweisung</span><span class="sxs-lookup"><span data-stu-id="e87be-126">Dim Statement</span></span>](../statements/dim-statement.md)  
  
 [<span data-ttu-id="e87be-127">Enum-Anweisung</span><span class="sxs-lookup"><span data-stu-id="e87be-127">Enum Statement</span></span>](../statements/enum-statement.md)  
  
 [<span data-ttu-id="e87be-128">Event-Anweisung</span><span class="sxs-lookup"><span data-stu-id="e87be-128">Event Statement</span></span>](../statements/event-statement.md)  
  
 [<span data-ttu-id="e87be-129">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="e87be-129">Function Statement</span></span>](../statements/function-statement.md)  
  
 [<span data-ttu-id="e87be-130">Interface-Anweisung</span><span class="sxs-lookup"><span data-stu-id="e87be-130">Interface Statement</span></span>](../statements/interface-statement.md)  
  
 [<span data-ttu-id="e87be-131">Module-Anweisung</span><span class="sxs-lookup"><span data-stu-id="e87be-131">Module Statement</span></span>](../statements/module-statement.md)  
  
 [<span data-ttu-id="e87be-132">Operator Statement</span><span class="sxs-lookup"><span data-stu-id="e87be-132">Operator Statement</span></span>](../statements/operator-statement.md)  
  
 [<span data-ttu-id="e87be-133">Property Statement</span><span class="sxs-lookup"><span data-stu-id="e87be-133">Property Statement</span></span>](../statements/property-statement.md)  
  
 [<span data-ttu-id="e87be-134">Structure Statement</span><span class="sxs-lookup"><span data-stu-id="e87be-134">Structure Statement</span></span>](../statements/structure-statement.md)  
  
 [<span data-ttu-id="e87be-135">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="e87be-135">Sub Statement</span></span>](../statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="e87be-136">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e87be-136">See also</span></span>

- [<span data-ttu-id="e87be-137">Gebieten</span><span class="sxs-lookup"><span data-stu-id="e87be-137">Protected</span></span>](protected.md)
- [<span data-ttu-id="e87be-138">Kollegen</span><span class="sxs-lookup"><span data-stu-id="e87be-138">Friend</span></span>](friend.md)
- [<span data-ttu-id="e87be-139">Privat</span><span class="sxs-lookup"><span data-stu-id="e87be-139">Private</span></span>](private.md)
- [<span data-ttu-id="e87be-140">Privat geschützt</span><span class="sxs-lookup"><span data-stu-id="e87be-140">Private Protected</span></span>](private-protected.md)
- [<span data-ttu-id="e87be-141">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="e87be-141">Protected Friend</span></span>](protected-friend.md)
- [<span data-ttu-id="e87be-142">Zugriffsebenen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e87be-142">Access levels in Visual Basic</span></span>](../../programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="e87be-143">Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="e87be-143">Procedures</span></span>](../../programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="e87be-144">Strukturen</span><span class="sxs-lookup"><span data-stu-id="e87be-144">Structures</span></span>](../../programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="e87be-145">Objekte und Klassen</span><span class="sxs-lookup"><span data-stu-id="e87be-145">Objects and Classes</span></span>](../../programming-guide/language-features/objects-and-classes/index.md)
