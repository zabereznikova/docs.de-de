---
title: Friend (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.Friend
helpviewer_keywords:
- Friend keyword [Visual Basic]
- Friend access modifier
- Friend keyword [Visual Basic], syntax
- Protected Friend keyword combination
- Friend keyword [Visual Basic], and Protected
ms.assetid: b664605e-1c79-4728-b996-aa59c50846bc
caps.latest.revision: "25"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 32f993e4b9bcd126ebb6d70310fc0781e8b137b9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="friend-visual-basic"></a><span data-ttu-id="5a969-102">Friend (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5a969-102">Friend (Visual Basic)</span></span>
<span data-ttu-id="5a969-103">Gibt an, dass eine oder mehrere deklarierte Programmierelemente nur innerhalb der Assembly zugegriffen werden, die ihre Deklaration enthält.</span><span class="sxs-lookup"><span data-stu-id="5a969-103">Specifies that one or more declared programming elements are accessible only from within the assembly that contains their declaration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5a969-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5a969-104">Remarks</span></span>  
 <span data-ttu-id="5a969-105">In vielen Fällen möchten Sie die Programmierelemente, wie Klassen und Strukturen, die durch die gesamte Assembly, nicht nur von der Komponente verwendet werden, der sie deklariert.</span><span class="sxs-lookup"><span data-stu-id="5a969-105">In many cases, you want programming elements such as classes and structures to be used by the entire assembly, not only by the component that declares them.</span></span> <span data-ttu-id="5a969-106">Allerdings können Sie nicht sinnvoll Code außerhalb der Assembly (z. B., wenn die Anwendung proprietären ist) zugänglich sein.</span><span class="sxs-lookup"><span data-stu-id="5a969-106">However, you might not want them to be accessible by code outside the assembly (for example, if the application is proprietary).</span></span> <span data-ttu-id="5a969-107">Wenn Sie den Zugriff auf ein Element auf diese Weise beschränken möchten, können Sie sie deklarieren, indem die `Friend` Modifizierer.</span><span class="sxs-lookup"><span data-stu-id="5a969-107">If you want to limit access to an element in this way, you can declare it by using the `Friend` modifier.</span></span>  
  
 <span data-ttu-id="5a969-108">Code in anderen Klassen, Strukturen und Module, die auf den gleichen kompiliert werden Assembly zugreifen kann alle der `Friend` Elemente in dieser Assembly.</span><span class="sxs-lookup"><span data-stu-id="5a969-108">Code in other classes, structures, and modules that are compiled to the same assembly can access all the `Friend` elements in that assembly.</span></span>  
  
 <span data-ttu-id="5a969-109">`Friend`Zugriff ist häufig die bevorzugte für eine Anwendung Programmierelemente, und `Friend` ist der Standardzugriff von einer Schnittstelle, ein Modul, eine Klasse oder eine Struktur.</span><span class="sxs-lookup"><span data-stu-id="5a969-109">`Friend` access is often the preferred level for an application's programming elements, and `Friend` is the default access level of an interface, a module, a class, or a structure.</span></span>  
  
 <span data-ttu-id="5a969-110">Sie können `Friend` nur auf das Modul, Schnittstelle oder Namespace-Ebene.</span><span class="sxs-lookup"><span data-stu-id="5a969-110">You can use `Friend` only at the module, interface, or namespace level.</span></span> <span data-ttu-id="5a969-111">Aus diesem Grund der Deklarationskontext für eine `Friend` Element muss eine Quelldatei, einen Namespace, eine Schnittstelle, ein Modul, eine Klasse oder eine Struktur sein; eine Prozedur kann nicht mehr.</span><span class="sxs-lookup"><span data-stu-id="5a969-111">Therefore, the declaration context for a `Friend` element must be a source file, a namespace, an interface, a module, a class, or a structure; it can't be a procedure.</span></span>  
  
 <span data-ttu-id="5a969-112">Können Sie die `Friend` Modifizierer in Verbindung mit der [geschützte](../../../visual-basic/language-reference/modifiers/protected.md) Modifizierer in der gleichen Deklaration.</span><span class="sxs-lookup"><span data-stu-id="5a969-112">You can use the `Friend` modifier in conjunction with the [Protected](../../../visual-basic/language-reference/modifiers/protected.md) modifier in the same declaration.</span></span> <span data-ttu-id="5a969-113">Diese Kombination überträgt sowohl `Friend` und geschützten Zugriff auf deklarierte Elemente, sodass sie über eine beliebige Stelle in der gleichen Assembly, von ihrer eigenen Klasse und von abgeleiteten Klassen zugänglich sind.</span><span class="sxs-lookup"><span data-stu-id="5a969-113">This combination confers both `Friend` access and protected access on the declared elements, so they are accessible from anywhere in the same assembly, from their own class, and from derived classes.</span></span> <span data-ttu-id="5a969-114">Sie können angeben, `Protected Friend` nur auf Member von Klassen.</span><span class="sxs-lookup"><span data-stu-id="5a969-114">You can specify `Protected Friend` only on members of classes.</span></span>  
  
 <span data-ttu-id="5a969-115">Einen Vergleich der `Friend` und anderen Zugriffsmodifizierer, finden Sie unter [Zugriffsebenen in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="5a969-115">For a comparison of `Friend` and the other access modifiers, see [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5a969-116">Sie können angeben, dass eine andere Assembly ein Friend-Assembly ist, womit Zugriff auf alle Typen und Member, die als markiert sind `Friend`.</span><span class="sxs-lookup"><span data-stu-id="5a969-116">You can specify that another assembly is a friend assembly, which allows it to access all types and members that are marked as `Friend`.</span></span> <span data-ttu-id="5a969-117">Weitere Informationen finden Sie unter [Friend-Assemblys](http://msdn.microsoft.com/library/df0c70ea-2c2a-4bdc-9526-df951ad2d055).</span><span class="sxs-lookup"><span data-stu-id="5a969-117">For more information, see [Friend Assemblies](http://msdn.microsoft.com/library/df0c70ea-2c2a-4bdc-9526-df951ad2d055).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5a969-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5a969-118">Example</span></span>  
 <span data-ttu-id="5a969-119">Die folgende Klasse verwendet die `Friend` Modifizierer, um andere Programmierelemente in derselben Assembly auf bestimmte Member zugreifen zu können.</span><span class="sxs-lookup"><span data-stu-id="5a969-119">The following class uses the `Friend` modifier to allow other programming elements within the same assembly to access certain members.</span></span>  
  
 [!code-vb[VbVbalrAccessModifiers#1](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/friend_1.vb)]  
  
## <a name="usage"></a><span data-ttu-id="5a969-120">Verwendung</span><span class="sxs-lookup"><span data-stu-id="5a969-120">Usage</span></span>  
 <span data-ttu-id="5a969-121">Sie können die `Friend` Modifizierer in diesen Kontexten:</span><span class="sxs-lookup"><span data-stu-id="5a969-121">You can use the `Friend` modifier in these contexts:</span></span>  
  
 [<span data-ttu-id="5a969-122">Class-Anweisung</span><span class="sxs-lookup"><span data-stu-id="5a969-122">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [<span data-ttu-id="5a969-123">Const-Anweisung</span><span class="sxs-lookup"><span data-stu-id="5a969-123">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [<span data-ttu-id="5a969-124">Declare-Anweisung</span><span class="sxs-lookup"><span data-stu-id="5a969-124">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [<span data-ttu-id="5a969-125">Delegate-Anweisung</span><span class="sxs-lookup"><span data-stu-id="5a969-125">Delegate Statement</span></span>](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [<span data-ttu-id="5a969-126">Dim-Anweisung</span><span class="sxs-lookup"><span data-stu-id="5a969-126">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="5a969-127">Enum-Anweisung</span><span class="sxs-lookup"><span data-stu-id="5a969-127">Enum Statement</span></span>](../../../visual-basic/language-reference/statements/enum-statement.md)  
  
 [<span data-ttu-id="5a969-128">Event-Anweisung</span><span class="sxs-lookup"><span data-stu-id="5a969-128">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [<span data-ttu-id="5a969-129">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="5a969-129">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="5a969-130">Interface-Anweisung</span><span class="sxs-lookup"><span data-stu-id="5a969-130">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [<span data-ttu-id="5a969-131">Module-Anweisung</span><span class="sxs-lookup"><span data-stu-id="5a969-131">Module Statement</span></span>](../../../visual-basic/language-reference/statements/module-statement.md)  
  
 [<span data-ttu-id="5a969-132">Property-Anweisung</span><span class="sxs-lookup"><span data-stu-id="5a969-132">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="5a969-133">Structure-Anweisung</span><span class="sxs-lookup"><span data-stu-id="5a969-133">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [<span data-ttu-id="5a969-134">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="5a969-134">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="5a969-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5a969-135">See Also</span></span>  
 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>  
 [<span data-ttu-id="5a969-136">Public</span><span class="sxs-lookup"><span data-stu-id="5a969-136">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)  
 [<span data-ttu-id="5a969-137">Protected</span><span class="sxs-lookup"><span data-stu-id="5a969-137">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)  
 [<span data-ttu-id="5a969-138">Private</span><span class="sxs-lookup"><span data-stu-id="5a969-138">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)  
 [<span data-ttu-id="5a969-139">Zugriffsebenen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5a969-139">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)  
 [<span data-ttu-id="5a969-140">Verfahren</span><span class="sxs-lookup"><span data-stu-id="5a969-140">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
 [<span data-ttu-id="5a969-141">Strukturen</span><span class="sxs-lookup"><span data-stu-id="5a969-141">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [<span data-ttu-id="5a969-142">Objekte und Klassen</span><span class="sxs-lookup"><span data-stu-id="5a969-142">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
