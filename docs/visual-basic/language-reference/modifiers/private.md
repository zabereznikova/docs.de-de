---
title: Private (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Private
helpviewer_keywords:
- Private keyword [Visual Basic]
- Private keyword [Visual Basic], syntax
ms.assetid: aba74a2e-5824-4613-bf63-b9ec7787f4e6
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 07450c2a5443bf6bc147cad2cfc779072bfc363b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="private-visual-basic"></a><span data-ttu-id="8dc2c-102">Private (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8dc2c-102">Private (Visual Basic)</span></span>
<span data-ttu-id="8dc2c-103">Gibt an, dass eine oder mehrere deklarierte Programmierelemente nur aus ihrem Deklarationskontext einschließlich alle darin enthaltenen Typen aus zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="8dc2c-103">Specifies that one or more declared programming elements are accessible only from within their declaration context, including from within any contained types.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8dc2c-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8dc2c-104">Remarks</span></span>  
 <span data-ttu-id="8dc2c-105">Wenn ein Programmierelement proprietäre Funktionalität darstellt oder vertrauliche Daten enthält, sollten Sie in der Regel den Zugriff darauf so stark wie möglich einschränken.</span><span class="sxs-lookup"><span data-stu-id="8dc2c-105">If a programming element represents proprietary functionality, or contains confidential data, you usually want to limit access to it as strictly as possible.</span></span> <span data-ttu-id="8dc2c-106">Sie erreichen die maximale Beschränkung, nur das Modul, Klasse oder Struktur, die definiert, wenn Sie darauf zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="8dc2c-106">You achieve the maximum limitation by allowing only the module, class, or structure that defines it to access it.</span></span> <span data-ttu-id="8dc2c-107">Um den Zugriff auf ein Element auf diese Weise beschränken möchten, deklarieren Sie es mit `Private`.</span><span class="sxs-lookup"><span data-stu-id="8dc2c-107">To limit access to an element in this way, you can declare it with `Private`.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="8dc2c-108">Regeln</span><span class="sxs-lookup"><span data-stu-id="8dc2c-108">Rules</span></span>  
  
-   <span data-ttu-id="8dc2c-109">**Deklarationskontext.**</span><span class="sxs-lookup"><span data-stu-id="8dc2c-109">**Declaration Context.**</span></span> <span data-ttu-id="8dc2c-110">Sie können `Private` nur auf Modulebene verwenden.</span><span class="sxs-lookup"><span data-stu-id="8dc2c-110">You can use `Private` only at module level.</span></span> <span data-ttu-id="8dc2c-111">Dies bedeutet, dass der Deklarationskontext für eine `Private` Element ein Modul, Klasse oder Struktur, und eine Quelldatei, Namespace, Schnittstelle oder Prozedur nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="8dc2c-111">This means the declaration context for a `Private` element must be a module, class, or structure, and cannot be a source file, namespace, interface, or procedure.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="8dc2c-112">Verhalten</span><span class="sxs-lookup"><span data-stu-id="8dc2c-112">Behavior</span></span>  
  
-   <span data-ttu-id="8dc2c-113">**Zugriffsebene.**</span><span class="sxs-lookup"><span data-stu-id="8dc2c-113">**Access Level.**</span></span> <span data-ttu-id="8dc2c-114">Der gesamte Code in einem Deklarationskontext erreichen die `Private` Elemente.</span><span class="sxs-lookup"><span data-stu-id="8dc2c-114">All code within a declaration context can access its `Private` elements.</span></span> <span data-ttu-id="8dc2c-115">Dies schließt Code innerhalb eines enthaltenen Typs, z. B. eine geschachtelte Klasse oder ein Zuweisungsausdruck in einer Enumeration.</span><span class="sxs-lookup"><span data-stu-id="8dc2c-115">This includes code within a contained type, such as a nested class or an assignment expression in an enumeration.</span></span> <span data-ttu-id="8dc2c-116">Kein Code außerhalb der Deklarationskontext erreichen die `Private` Elemente.</span><span class="sxs-lookup"><span data-stu-id="8dc2c-116">No code outside of the declaration context can access its `Private` elements.</span></span>  
  
-   <span data-ttu-id="8dc2c-117">**Zugriffsmodifizierer.**</span><span class="sxs-lookup"><span data-stu-id="8dc2c-117">**Access Modifiers.**</span></span> <span data-ttu-id="8dc2c-118">Die Schlüsselwörter, die Zugriffsebene angeben heißen *Zugriffsmodifizierer*.</span><span class="sxs-lookup"><span data-stu-id="8dc2c-118">The keywords that specify access level are called *access modifiers*.</span></span> <span data-ttu-id="8dc2c-119">Einen Vergleich der Zugriffsmodifizierer, finden Sie unter [Zugriffsebenen in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="8dc2c-119">For a comparison of the access modifiers, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 <span data-ttu-id="8dc2c-120">Der `Private`-Modifizierer kann in folgenden Kontexten verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="8dc2c-120">The `Private` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="8dc2c-121">Class-Anweisung</span><span class="sxs-lookup"><span data-stu-id="8dc2c-121">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [<span data-ttu-id="8dc2c-122">Const-Anweisung</span><span class="sxs-lookup"><span data-stu-id="8dc2c-122">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [<span data-ttu-id="8dc2c-123">Declare-Anweisung</span><span class="sxs-lookup"><span data-stu-id="8dc2c-123">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [<span data-ttu-id="8dc2c-124">Delegate-Anweisung</span><span class="sxs-lookup"><span data-stu-id="8dc2c-124">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [<span data-ttu-id="8dc2c-125">Dim-Anweisung</span><span class="sxs-lookup"><span data-stu-id="8dc2c-125">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="8dc2c-126">Enum-Anweisung</span><span class="sxs-lookup"><span data-stu-id="8dc2c-126">Enum Statement</span></span>](../../../visual-basic/language-reference/statements/enum-statement.md)  
  
 [<span data-ttu-id="8dc2c-127">Event-Anweisung</span><span class="sxs-lookup"><span data-stu-id="8dc2c-127">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [<span data-ttu-id="8dc2c-128">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="8dc2c-128">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="8dc2c-129">Interface-Anweisung</span><span class="sxs-lookup"><span data-stu-id="8dc2c-129">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [<span data-ttu-id="8dc2c-130">Property-Anweisung</span><span class="sxs-lookup"><span data-stu-id="8dc2c-130">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="8dc2c-131">Structure-Anweisung</span><span class="sxs-lookup"><span data-stu-id="8dc2c-131">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [<span data-ttu-id="8dc2c-132">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="8dc2c-132">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="8dc2c-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8dc2c-133">See Also</span></span>  
 [<span data-ttu-id="8dc2c-134">Public</span><span class="sxs-lookup"><span data-stu-id="8dc2c-134">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)  
 [<span data-ttu-id="8dc2c-135">Protected</span><span class="sxs-lookup"><span data-stu-id="8dc2c-135">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)  
 [<span data-ttu-id="8dc2c-136">Friend</span><span class="sxs-lookup"><span data-stu-id="8dc2c-136">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)  
 [<span data-ttu-id="8dc2c-137">Zugriffsebenen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8dc2c-137">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)  
 [<span data-ttu-id="8dc2c-138">Verfahren</span><span class="sxs-lookup"><span data-stu-id="8dc2c-138">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
 [<span data-ttu-id="8dc2c-139">Strukturen</span><span class="sxs-lookup"><span data-stu-id="8dc2c-139">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [<span data-ttu-id="8dc2c-140">Objekte und Klassen</span><span class="sxs-lookup"><span data-stu-id="8dc2c-140">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
