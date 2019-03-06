---
title: Friend (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Friend
helpviewer_keywords:
- Friend keyword [Visual Basic]
- Friend access modifier
- Friend keyword [Visual Basic], syntax
- Protected Friend keyword combination
- Friend keyword [Visual Basic], and Protected
ms.assetid: b664605e-1c79-4728-b996-aa59c50846bc
ms.openlocfilehash: 1e6dbaa9201d5c9cd902412797b2427ec488d014
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57371410"
---
# <a name="friend-visual-basic"></a><span data-ttu-id="6e0e6-102">Friend (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6e0e6-102">Friend (Visual Basic)</span></span>
<span data-ttu-id="6e0e6-103">Gibt an, dass eine oder mehrere deklarierte Programmierelemente nur innerhalb der Assembly zugegriffen werden, die ihre Deklaration enthält.</span><span class="sxs-lookup"><span data-stu-id="6e0e6-103">Specifies that one or more declared programming elements are accessible only from within the assembly that contains their declaration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6e0e6-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6e0e6-104">Remarks</span></span>  
 <span data-ttu-id="6e0e6-105">In vielen Fällen möchten Sie die Programmierelemente wie Klassen und Strukturen, um die gesamte Assembly, nicht nur von der Komponente verwendet werden, der sie deklariert.</span><span class="sxs-lookup"><span data-stu-id="6e0e6-105">In many cases, you want programming elements such as classes and structures to be used by the entire assembly, not only by the component that declares them.</span></span> <span data-ttu-id="6e0e6-106">Jedoch möglicherweise nicht diese sollen von Code außerhalb der Assembly (z. B., wenn die Anwendung proprietäre ist) zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="6e0e6-106">However, you might not want them to be accessible by code outside the assembly (for example, if the application is proprietary).</span></span> <span data-ttu-id="6e0e6-107">Wenn Sie den Zugriff auf ein Element auf diese Weise beschränken möchten, können Sie sie deklarieren, indem die `Friend` Modifizierer.</span><span class="sxs-lookup"><span data-stu-id="6e0e6-107">If you want to limit access to an element in this way, you can declare it by using the `Friend` modifier.</span></span>  
  
 <span data-ttu-id="6e0e6-108">Code in anderen Klassen, Strukturen und -Module, die auf die gleiche kompiliert werden Assembly kann auf alle zugreifen der `Friend` Elemente in dieser Assembly.</span><span class="sxs-lookup"><span data-stu-id="6e0e6-108">Code in other classes, structures, and modules that are compiled to the same assembly can access all the `Friend` elements in that assembly.</span></span>  
  
 <span data-ttu-id="6e0e6-109">`Friend` Zugriff ist häufig die bevorzugte für Programmierelemente von einer Anwendung, und `Friend` der Standardzugriff von einer Schnittstelle, ein Modul, eine Klasse oder eine Struktur ist.</span><span class="sxs-lookup"><span data-stu-id="6e0e6-109">`Friend` access is often the preferred level for an application's programming elements, and `Friend` is the default access level of an interface, a module, a class, or a structure.</span></span>  
  
 <span data-ttu-id="6e0e6-110">Sie können `Friend` nur auf das Modul, Schnittstelle oder Namespace-Ebene.</span><span class="sxs-lookup"><span data-stu-id="6e0e6-110">You can use `Friend` only at the module, interface, or namespace level.</span></span> <span data-ttu-id="6e0e6-111">Aus diesem Grund der Deklarationskontext für eine `Friend` Element muss eine Quelldatei, einem Namespace, eine Schnittstelle, ein Modul, eine Klasse oder eine Struktur sein und keine Prozedur sein.</span><span class="sxs-lookup"><span data-stu-id="6e0e6-111">Therefore, the declaration context for a `Friend` element must be a source file, a namespace, an interface, a module, a class, or a structure; it can't be a procedure.</span></span>  

> [!NOTE]
> <span data-ttu-id="6e0e6-112">Sie können auch die [Protected Friend](protected-friend.md) Zugriffsmodifizierer, wodurch einen Klassenmember kann innerhalb dieser Klasse, aus der gleichen Assembly, die in der die Klasse definiert ist und von abgeleiteten Klassen zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="6e0e6-112">You can also use the [Protected Friend](protected-friend.md) access modifier, which makes a class member accessible from within that class, from derived classes, and from the same assembly in which the class is defined.</span></span> <span data-ttu-id="6e0e6-113">Zum Einschränken des Zugriffs auf ein Element innerhalb seiner Klasse und von abgeleiteten Klassen in der gleichen Assembly, die Sie verwenden die [Private Protected](private-protected.md) Zugriffsmodifizierer.</span><span class="sxs-lookup"><span data-stu-id="6e0e6-113">To restrict access to a member from within its class and from derived classes in the same assembly, you use the [Private Protected](private-protected.md) access modifier.</span></span>

 <span data-ttu-id="6e0e6-114">Einen Vergleich der `Friend` und die andere Zugriffsmodifizierer, finden Sie unter [Zugriffsebenen in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="6e0e6-114">For a comparison of `Friend` and the other access modifiers, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6e0e6-115">Sie können angeben, dass eine andere Assembly Friend-Assembly, die ermöglicht, damit ein Zugriff auf alle Typen und Member, die als markiert sind `Friend`.</span><span class="sxs-lookup"><span data-stu-id="6e0e6-115">You can specify that another assembly is a friend assembly, which allows it to access all types and members that are marked as `Friend`.</span></span> <span data-ttu-id="6e0e6-116">Weitere Informationen finden Sie unter [Friend-Assemblys](../../../standard/assembly/friend-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="6e0e6-116">For more information, see [Friend Assemblies](../../../standard/assembly/friend-assemblies.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6e0e6-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6e0e6-117">Example</span></span>  
 <span data-ttu-id="6e0e6-118">Die folgende Klasse verwendet die `Friend` Modifizierer, um anderen Programmierungselementen innerhalb der gleichen Assembly auf bestimmte Member zugreifen zu können.</span><span class="sxs-lookup"><span data-stu-id="6e0e6-118">The following class uses the `Friend` modifier to allow other programming elements within the same assembly to access certain members.</span></span>  
  
 [!code-vb[VbVbalrAccessModifiers#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalraccessmodifiers/vb/class1.vb#1)]  
  
## <a name="usage"></a><span data-ttu-id="6e0e6-119">Verwendung</span><span class="sxs-lookup"><span data-stu-id="6e0e6-119">Usage</span></span>  
 <span data-ttu-id="6e0e6-120">Sie können die `Friend` Modifizierer in den folgenden Kontexten:</span><span class="sxs-lookup"><span data-stu-id="6e0e6-120">You can use the `Friend` modifier in these contexts:</span></span>  
  
 [<span data-ttu-id="6e0e6-121">Class-Anweisung</span><span class="sxs-lookup"><span data-stu-id="6e0e6-121">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [<span data-ttu-id="6e0e6-122">Const-Anweisung</span><span class="sxs-lookup"><span data-stu-id="6e0e6-122">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [<span data-ttu-id="6e0e6-123">Declare-Anweisung</span><span class="sxs-lookup"><span data-stu-id="6e0e6-123">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [<span data-ttu-id="6e0e6-124">Delegate-Anweisung</span><span class="sxs-lookup"><span data-stu-id="6e0e6-124">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [<span data-ttu-id="6e0e6-125">Dim-Anweisung</span><span class="sxs-lookup"><span data-stu-id="6e0e6-125">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="6e0e6-126">Enum-Anweisung</span><span class="sxs-lookup"><span data-stu-id="6e0e6-126">Enum Statement</span></span>](../../../visual-basic/language-reference/statements/enum-statement.md)  
  
 [<span data-ttu-id="6e0e6-127">Event-Anweisung</span><span class="sxs-lookup"><span data-stu-id="6e0e6-127">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [<span data-ttu-id="6e0e6-128">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="6e0e6-128">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="6e0e6-129">Interface-Anweisung</span><span class="sxs-lookup"><span data-stu-id="6e0e6-129">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [<span data-ttu-id="6e0e6-130">Module-Anweisung</span><span class="sxs-lookup"><span data-stu-id="6e0e6-130">Module Statement</span></span>](../../../visual-basic/language-reference/statements/module-statement.md)  
  
 [<span data-ttu-id="6e0e6-131">Property-Anweisung</span><span class="sxs-lookup"><span data-stu-id="6e0e6-131">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="6e0e6-132">Structure-Anweisung</span><span class="sxs-lookup"><span data-stu-id="6e0e6-132">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [<span data-ttu-id="6e0e6-133">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="6e0e6-133">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="6e0e6-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6e0e6-134">See also</span></span>
- <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>
- [<span data-ttu-id="6e0e6-135">Public</span><span class="sxs-lookup"><span data-stu-id="6e0e6-135">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)
- [<span data-ttu-id="6e0e6-136">Protected</span><span class="sxs-lookup"><span data-stu-id="6e0e6-136">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)
- [<span data-ttu-id="6e0e6-137">Private</span><span class="sxs-lookup"><span data-stu-id="6e0e6-137">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)
- [<span data-ttu-id="6e0e6-138">Private Protected</span><span class="sxs-lookup"><span data-stu-id="6e0e6-138">Private Protected</span></span>](./private-protected.md)
- [<span data-ttu-id="6e0e6-139">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="6e0e6-139">Protected Friend</span></span>](./protected-friend.md)
- [<span data-ttu-id="6e0e6-140">Zugriffsebenen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6e0e6-140">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="6e0e6-141">Verfahren</span><span class="sxs-lookup"><span data-stu-id="6e0e6-141">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="6e0e6-142">Strukturen</span><span class="sxs-lookup"><span data-stu-id="6e0e6-142">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="6e0e6-143">Objekte und Klassen</span><span class="sxs-lookup"><span data-stu-id="6e0e6-143">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
