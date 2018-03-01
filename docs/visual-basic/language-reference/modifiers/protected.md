---
title: Protected (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Protected
helpviewer_keywords:
- Protected Friend keyword combination
- Protected keyword [Visual Basic], and Friend
- Protected keyword [Visual Basic], syntax
- Protected access modifier
- Protected keyword [Visual Basic]
ms.assetid: 74ad3d56-309f-49d2-b60c-1d0157d010e8
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2d0cc7a0cb626a9ec8e2a0e47abc02e5268aed56
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="protected-visual-basic"></a><span data-ttu-id="d59e1-102">Protected (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d59e1-102">Protected (Visual Basic)</span></span>
<span data-ttu-id="d59e1-103">Gibt an, dass eine oder mehrere deklarierte Programmierelemente nur aus ihrer eigenen Klasse oder von einer abgeleiteten Klasse zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="d59e1-103">Specifies that one or more declared programming elements are accessible only from within their own class or from a derived class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d59e1-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d59e1-104">Remarks</span></span>  
 <span data-ttu-id="d59e1-105">Manchmal enthält ein Programmierelement in einer Klasse deklariert, vertrauliche Daten oder eingeschränkten Code, und Sie den Zugriff auf das Element einschränken möchten.</span><span class="sxs-lookup"><span data-stu-id="d59e1-105">Sometimes a programming element declared in a class contains sensitive data or restricted code, and you want to limit access to the element.</span></span> <span data-ttu-id="d59e1-106">Jedoch wenn die Klasse vererbbar ist, und Sie erwarten, eine Hierarchie von abgeleiteten Klassen dass, es für diese abgeleiteten Klassen den Zugriff auf die Daten oder Code möglicherweise erforderlich.</span><span class="sxs-lookup"><span data-stu-id="d59e1-106">However, if the class is inheritable and you expect a hierarchy of derived classes, it might be necessary for these derived classes to access the data or code.</span></span> <span data-ttu-id="d59e1-107">In einem solchen Fall möchten Sie das Element aus der Basisklasse und aus allen abgeleiteten Klassen zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="d59e1-107">In such a case, you want the element to be accessible both from the base class and from all derived classes.</span></span> <span data-ttu-id="d59e1-108">Um den Zugriff auf ein Element auf diese Weise beschränken möchten, deklarieren Sie es mit `Protected`.</span><span class="sxs-lookup"><span data-stu-id="d59e1-108">To limit access to an element in this manner, you can declare it with `Protected`.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="d59e1-109">Regeln</span><span class="sxs-lookup"><span data-stu-id="d59e1-109">Rules</span></span>  
  
-   <span data-ttu-id="d59e1-110">**Deklarationskontext.**</span><span class="sxs-lookup"><span data-stu-id="d59e1-110">**Declaration Context.**</span></span> <span data-ttu-id="d59e1-111">Sie können `Protected` nur auf Klassenebene.</span><span class="sxs-lookup"><span data-stu-id="d59e1-111">You can use `Protected` only at class level.</span></span> <span data-ttu-id="d59e1-112">Dies bedeutet, dass der Deklarationskontext für eine `Protected` Element muss eine Klasse sein, und eine Quelldatei, Namespace, Schnittstelle, Modul, Struktur oder Prozedur nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="d59e1-112">This means the declaration context for a `Protected` element must be a class, and cannot be a source file, namespace, interface, module, structure, or procedure.</span></span>  
  
-   <span data-ttu-id="d59e1-113">**Kombinierte Modifizierer.**</span><span class="sxs-lookup"><span data-stu-id="d59e1-113">**Combined Modifiers.**</span></span> <span data-ttu-id="d59e1-114">Sie können die `Protected` Modifizierer zusammen mit der ["Friend"](../../../visual-basic/language-reference/modifiers/friend.md) Modifizierer in der gleichen Deklaration.</span><span class="sxs-lookup"><span data-stu-id="d59e1-114">You can use the `Protected` modifier together with the [Friend](../../../visual-basic/language-reference/modifiers/friend.md) modifier in the same declaration.</span></span> <span data-ttu-id="d59e1-115">Diese Kombination wird die deklarierte Elemente an einer beliebigen Stelle in der gleichen Assembly, von ihrer eigenen Klasse und von abgeleiteten Klassen zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="d59e1-115">This combination makes the declared elements accessible from anywhere in the same assembly, from their own class, and from derived classes.</span></span> <span data-ttu-id="d59e1-116">Sie können angeben, `Protected Friend` nur auf Member von Klassen.</span><span class="sxs-lookup"><span data-stu-id="d59e1-116">You can specify `Protected Friend` only on members of classes.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="d59e1-117">Verhalten</span><span class="sxs-lookup"><span data-stu-id="d59e1-117">Behavior</span></span>  
  
-   <span data-ttu-id="d59e1-118">**Zugriffsebene.**</span><span class="sxs-lookup"><span data-stu-id="d59e1-118">**Access Level.**</span></span> <span data-ttu-id="d59e1-119">Der gesamte Code in einer Klasse kann ihre Elemente zugreifen.</span><span class="sxs-lookup"><span data-stu-id="d59e1-119">All code in a class can access its elements.</span></span> <span data-ttu-id="d59e1-120">Code in einer Klasse, die von einer Basisklasse abgeleitet ist, kann auf alle zugreifen die `Protected` Elemente der Basisklasse.</span><span class="sxs-lookup"><span data-stu-id="d59e1-120">Code in any class that derives from a base class can access all the `Protected` elements of the base class.</span></span> <span data-ttu-id="d59e1-121">Dies gilt für alle Generationen der Ableitung.</span><span class="sxs-lookup"><span data-stu-id="d59e1-121">This is true for all generations of derivation.</span></span> <span data-ttu-id="d59e1-122">Dies bedeutet, dass eine Klasse zugreifen kann `Protected` Elemente der Basisklasse der Basisklasse und So weiter.</span><span class="sxs-lookup"><span data-stu-id="d59e1-122">This means that a class can access `Protected` elements of the base class of the base class, and so on.</span></span>  
  
     <span data-ttu-id="d59e1-123">Geschützter Zugriff ist eine Obermenge oder eine Teilmenge der Friend-Zugriff.</span><span class="sxs-lookup"><span data-stu-id="d59e1-123">Protected access is not a superset or subset of friend access.</span></span>  
  
-   <span data-ttu-id="d59e1-124">**Zugriffsmodifizierer.**</span><span class="sxs-lookup"><span data-stu-id="d59e1-124">**Access Modifiers.**</span></span> <span data-ttu-id="d59e1-125">Die Schlüsselwörter, die Zugriffsebene angeben heißen *Zugriffsmodifizierer*.</span><span class="sxs-lookup"><span data-stu-id="d59e1-125">The keywords that specify access level are called *access modifiers*.</span></span> <span data-ttu-id="d59e1-126">Einen Vergleich der Zugriffsmodifizierer, finden Sie unter [Zugriffsebenen in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="d59e1-126">For a comparison of the access modifiers, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 <span data-ttu-id="d59e1-127">Der `Protected`-Modifizierer kann in folgenden Kontexten verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="d59e1-127">The `Protected` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="d59e1-128">Class-Anweisung</span><span class="sxs-lookup"><span data-stu-id="d59e1-128">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [<span data-ttu-id="d59e1-129">Const-Anweisung</span><span class="sxs-lookup"><span data-stu-id="d59e1-129">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [<span data-ttu-id="d59e1-130">Declare-Anweisung</span><span class="sxs-lookup"><span data-stu-id="d59e1-130">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [<span data-ttu-id="d59e1-131">Delegate-Anweisung</span><span class="sxs-lookup"><span data-stu-id="d59e1-131">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [<span data-ttu-id="d59e1-132">Dim-Anweisung</span><span class="sxs-lookup"><span data-stu-id="d59e1-132">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="d59e1-133">Enum-Anweisung</span><span class="sxs-lookup"><span data-stu-id="d59e1-133">Enum Statement</span></span>](../../../visual-basic/language-reference/statements/enum-statement.md)  
  
 [<span data-ttu-id="d59e1-134">Event-Anweisung</span><span class="sxs-lookup"><span data-stu-id="d59e1-134">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [<span data-ttu-id="d59e1-135">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="d59e1-135">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="d59e1-136">Interface-Anweisung</span><span class="sxs-lookup"><span data-stu-id="d59e1-136">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [<span data-ttu-id="d59e1-137">Property-Anweisung</span><span class="sxs-lookup"><span data-stu-id="d59e1-137">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="d59e1-138">Structure-Anweisung</span><span class="sxs-lookup"><span data-stu-id="d59e1-138">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [<span data-ttu-id="d59e1-139">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="d59e1-139">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="d59e1-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d59e1-140">See Also</span></span>  
 [<span data-ttu-id="d59e1-141">Public</span><span class="sxs-lookup"><span data-stu-id="d59e1-141">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)  
 [<span data-ttu-id="d59e1-142">Friend</span><span class="sxs-lookup"><span data-stu-id="d59e1-142">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)  
 [<span data-ttu-id="d59e1-143">Private</span><span class="sxs-lookup"><span data-stu-id="d59e1-143">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)  
 [<span data-ttu-id="d59e1-144">Zugriffsebenen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d59e1-144">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)  
 [<span data-ttu-id="d59e1-145">Verfahren</span><span class="sxs-lookup"><span data-stu-id="d59e1-145">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
 [<span data-ttu-id="d59e1-146">Strukturen</span><span class="sxs-lookup"><span data-stu-id="d59e1-146">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [<span data-ttu-id="d59e1-147">Objekte und Klassen</span><span class="sxs-lookup"><span data-stu-id="d59e1-147">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
