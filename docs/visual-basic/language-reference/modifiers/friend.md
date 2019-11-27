---
title: Friend
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
ms.openlocfilehash: 98f8ed947c9f4376c5778011a3a91ca8b094f9ec
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351566"
---
# <a name="friend-visual-basic"></a><span data-ttu-id="bf67b-102">Friend (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bf67b-102">Friend (Visual Basic)</span></span>
<span data-ttu-id="bf67b-103">Gibt an, dass auf ein oder mehrere deklarierte Programmier Elemente nur innerhalb der Assembly, die ihre Deklaration enthält, zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="bf67b-103">Specifies that one or more declared programming elements are accessible only from within the assembly that contains their declaration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bf67b-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="bf67b-104">Remarks</span></span>  
 <span data-ttu-id="bf67b-105">In vielen Fällen sollen Programmier Elemente, wie z. b. Klassen und Strukturen, von der gesamten Assembly verwendet werden, nicht nur von der Komponente, von der Sie deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="bf67b-105">In many cases, you want programming elements such as classes and structures to be used by the entire assembly, not only by the component that declares them.</span></span> <span data-ttu-id="bf67b-106">Allerdings möchten Sie möglicherweise nicht, dass Sie über Code außerhalb der Assembly zugänglich sind (z. b. wenn die Anwendung proprietär ist).</span><span class="sxs-lookup"><span data-stu-id="bf67b-106">However, you might not want them to be accessible by code outside the assembly (for example, if the application is proprietary).</span></span> <span data-ttu-id="bf67b-107">Wenn Sie den Zugriff auf ein Element auf diese Weise einschränken möchten, können Sie es mit dem `Friend`-Modifizierer deklarieren.</span><span class="sxs-lookup"><span data-stu-id="bf67b-107">If you want to limit access to an element in this way, you can declare it by using the `Friend` modifier.</span></span>  
  
 <span data-ttu-id="bf67b-108">Code in anderen Klassen, Strukturen und Modulen, die in derselben Assembly kompiliert werden, kann auf alle `Friend` Elemente in der Assembly zugreifen.</span><span class="sxs-lookup"><span data-stu-id="bf67b-108">Code in other classes, structures, and modules that are compiled to the same assembly can access all the `Friend` elements in that assembly.</span></span>  
  
 <span data-ttu-id="bf67b-109">`Friend` Access ist oft die bevorzugte Ebene für die Programmier Elemente einer Anwendung, und `Friend` ist die Standard Zugriffsebene einer Schnittstelle, eines Moduls, einer Klasse oder einer Struktur.</span><span class="sxs-lookup"><span data-stu-id="bf67b-109">`Friend` access is often the preferred level for an application's programming elements, and `Friend` is the default access level of an interface, a module, a class, or a structure.</span></span>  
  
 <span data-ttu-id="bf67b-110">Sie können `Friend` nur auf der Ebene "Module", "Interface" oder "Namespace" verwenden.</span><span class="sxs-lookup"><span data-stu-id="bf67b-110">You can use `Friend` only at the module, interface, or namespace level.</span></span> <span data-ttu-id="bf67b-111">Daher muss der Deklarations Kontext für ein `Friend` Element eine Quelldatei, ein Namespace, eine Schnittstelle, ein Modul, eine Klasse oder eine Struktur sein. Es kann sich dabei nicht um eine Prozedur handeln.</span><span class="sxs-lookup"><span data-stu-id="bf67b-111">Therefore, the declaration context for a `Friend` element must be a source file, a namespace, an interface, a module, a class, or a structure; it can't be a procedure.</span></span>  

> [!NOTE]
> <span data-ttu-id="bf67b-112">Sie können auch den [geschützten Friend](protected-friend.md) -Zugriffsmodifizierer verwenden, der einen Klassenmember aus dieser Klasse, aus abgeleiteten Klassen und aus der gleichen Assembly, in der die Klasse definiert ist, zugänglich macht.</span><span class="sxs-lookup"><span data-stu-id="bf67b-112">You can also use the [Protected Friend](protected-friend.md) access modifier, which makes a class member accessible from within that class, from derived classes, and from the same assembly in which the class is defined.</span></span> <span data-ttu-id="bf67b-113">Um den Zugriff auf ein Member innerhalb seiner Klasse und von abgeleiteten Klassen in derselben Assembly einzuschränken, verwenden Sie den [privaten geschützten](private-protected.md) Zugriffsmodifizierer.</span><span class="sxs-lookup"><span data-stu-id="bf67b-113">To restrict access to a member from within its class and from derived classes in the same assembly, you use the [Private Protected](private-protected.md) access modifier.</span></span>

 <span data-ttu-id="bf67b-114">Einen Vergleich der `Friend` und der anderen Zugriffsmodifizierer finden Sie unter [Zugriffsebenen in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="bf67b-114">For a comparison of `Friend` and the other access modifiers, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="bf67b-115">Sie können angeben, dass eine andere Assembly eine Friend-Assembly ist, die es ermöglicht, auf alle Typen und Member zuzugreifen, die als `Friend`gekennzeichnet sind.</span><span class="sxs-lookup"><span data-stu-id="bf67b-115">You can specify that another assembly is a friend assembly, which allows it to access all types and members that are marked as `Friend`.</span></span> <span data-ttu-id="bf67b-116">Weitere Informationen finden Sie unter [Friend-Assemblys](../../../standard/assembly/friend.md).</span><span class="sxs-lookup"><span data-stu-id="bf67b-116">For more information, see [Friend Assemblies](../../../standard/assembly/friend.md).</span></span>

## <a name="example"></a><span data-ttu-id="bf67b-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bf67b-117">Example</span></span>  
 <span data-ttu-id="bf67b-118">In der folgenden Klasse wird der `Friend` Modifizierer verwendet, damit andere Programmier Elemente innerhalb derselben Assembly auf bestimmte Member zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="bf67b-118">The following class uses the `Friend` modifier to allow other programming elements within the same assembly to access certain members.</span></span>  
  
 [!code-vb[VbVbalrAccessModifiers#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalraccessmodifiers/vb/class1.vb#1)]  
  
## <a name="usage"></a><span data-ttu-id="bf67b-119">Verwendung</span><span class="sxs-lookup"><span data-stu-id="bf67b-119">Usage</span></span>  
 <span data-ttu-id="bf67b-120">Sie können den `Friend` Modifizierer in diesen Kontexten verwenden:</span><span class="sxs-lookup"><span data-stu-id="bf67b-120">You can use the `Friend` modifier in these contexts:</span></span>  
  
 [<span data-ttu-id="bf67b-121">Class-Anweisung</span><span class="sxs-lookup"><span data-stu-id="bf67b-121">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [<span data-ttu-id="bf67b-122">Const-Anweisung</span><span class="sxs-lookup"><span data-stu-id="bf67b-122">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [<span data-ttu-id="bf67b-123">Declare-Anweisung</span><span class="sxs-lookup"><span data-stu-id="bf67b-123">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [<span data-ttu-id="bf67b-124">Delegate-Anweisung</span><span class="sxs-lookup"><span data-stu-id="bf67b-124">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [<span data-ttu-id="bf67b-125">Dim-Anweisung</span><span class="sxs-lookup"><span data-stu-id="bf67b-125">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="bf67b-126">Enum-Anweisung</span><span class="sxs-lookup"><span data-stu-id="bf67b-126">Enum Statement</span></span>](../../../visual-basic/language-reference/statements/enum-statement.md)  
  
 [<span data-ttu-id="bf67b-127">Event-Anweisung</span><span class="sxs-lookup"><span data-stu-id="bf67b-127">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [<span data-ttu-id="bf67b-128">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="bf67b-128">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="bf67b-129">Interface-Anweisung</span><span class="sxs-lookup"><span data-stu-id="bf67b-129">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [<span data-ttu-id="bf67b-130">Module-Anweisung</span><span class="sxs-lookup"><span data-stu-id="bf67b-130">Module Statement</span></span>](../../../visual-basic/language-reference/statements/module-statement.md)  
  
 [<span data-ttu-id="bf67b-131">Property-Anweisung</span><span class="sxs-lookup"><span data-stu-id="bf67b-131">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="bf67b-132">Structure-Anweisung</span><span class="sxs-lookup"><span data-stu-id="bf67b-132">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [<span data-ttu-id="bf67b-133">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="bf67b-133">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="bf67b-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bf67b-134">See also</span></span>

- <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>
- [<span data-ttu-id="bf67b-135">Public</span><span class="sxs-lookup"><span data-stu-id="bf67b-135">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)
- [<span data-ttu-id="bf67b-136">Protected</span><span class="sxs-lookup"><span data-stu-id="bf67b-136">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)
- [<span data-ttu-id="bf67b-137">Private</span><span class="sxs-lookup"><span data-stu-id="bf67b-137">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)
- [<span data-ttu-id="bf67b-138">Private Protected</span><span class="sxs-lookup"><span data-stu-id="bf67b-138">Private Protected</span></span>](./private-protected.md)
- [<span data-ttu-id="bf67b-139">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="bf67b-139">Protected Friend</span></span>](./protected-friend.md)
- [<span data-ttu-id="bf67b-140">Zugriffsebenen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="bf67b-140">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="bf67b-141">Verfahren</span><span class="sxs-lookup"><span data-stu-id="bf67b-141">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="bf67b-142">Strukturen</span><span class="sxs-lookup"><span data-stu-id="bf67b-142">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="bf67b-143">Objekte und Klassen</span><span class="sxs-lookup"><span data-stu-id="bf67b-143">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
