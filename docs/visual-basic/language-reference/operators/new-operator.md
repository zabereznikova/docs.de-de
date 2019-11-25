---
title: New-Operator
ms.date: 07/20/2015
f1_keywords:
- vb.new
- vb.NewConstraint
helpviewer_keywords:
- constraints, Visual Basic generic types
- generics [Visual Basic], constraints
- constraints, New keyword [Visual Basic]
- New constraint
- New keyword [Visual Basic]
ms.assetid: d7d566d7-fe0e-4336-91f7-641a542de4d0
ms.openlocfilehash: 27b5b4516ef729045036c36fedc24b6c576a4f61
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348319"
---
# <a name="new-operator-visual-basic"></a><span data-ttu-id="0aaa4-102">Operator New (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0aaa4-102">New Operator (Visual Basic)</span></span>

<span data-ttu-id="0aaa4-103">Introduces a `New` clause to create a new object instance, specifies a constructor constraint on a type parameter, or identifies a `Sub` procedure as a class constructor.</span><span class="sxs-lookup"><span data-stu-id="0aaa4-103">Introduces a `New` clause to create a new object instance, specifies a constructor constraint on a type parameter, or identifies a `Sub` procedure as a class constructor.</span></span>

## <a name="remarks"></a><span data-ttu-id="0aaa4-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0aaa4-104">Remarks</span></span>

<span data-ttu-id="0aaa4-105">In a declaration or assignment statement, a `New` clause must specify a defined class from which the instance can be created.</span><span class="sxs-lookup"><span data-stu-id="0aaa4-105">In a declaration or assignment statement, a `New` clause must specify a defined class from which the instance can be created.</span></span> <span data-ttu-id="0aaa4-106">This means that the class must expose one or more constructors that the calling code can access.</span><span class="sxs-lookup"><span data-stu-id="0aaa4-106">This means that the class must expose one or more constructors that the calling code can access.</span></span>

<span data-ttu-id="0aaa4-107">You can use a `New` clause in a declaration statement or an assignment statement.</span><span class="sxs-lookup"><span data-stu-id="0aaa4-107">You can use a `New` clause in a declaration statement or an assignment statement.</span></span> <span data-ttu-id="0aaa4-108">When the statement runs, it calls the appropriate constructor of the specified class, passing any arguments you have supplied.</span><span class="sxs-lookup"><span data-stu-id="0aaa4-108">When the statement runs, it calls the appropriate constructor of the specified class, passing any arguments you have supplied.</span></span> <span data-ttu-id="0aaa4-109">The following example demonstrates this by creating instances of a `Customer` class that has two constructors, one that takes no parameters and one that takes a string parameter:</span><span class="sxs-lookup"><span data-stu-id="0aaa4-109">The following example demonstrates this by creating instances of a `Customer` class that has two constructors, one that takes no parameters and one that takes a string parameter:</span></span>

[!code-vb[VbVbalrKeywords#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class6.vb#11)]

<span data-ttu-id="0aaa4-110">Since arrays are classes, `New` can create a new array instance, as shown in the following example:</span><span class="sxs-lookup"><span data-stu-id="0aaa4-110">Since arrays are classes, `New` can create a new array instance, as shown in the following example:</span></span>

[!code-vb[VbVbalrKeywords#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class6.vb#12)]

<span data-ttu-id="0aaa4-111">The common language runtime (CLR) throws an <xref:System.OutOfMemoryException> error if there is insufficient memory to create the new instance.</span><span class="sxs-lookup"><span data-stu-id="0aaa4-111">The common language runtime (CLR) throws an <xref:System.OutOfMemoryException> error if there is insufficient memory to create the new instance.</span></span>

> [!NOTE]
> <span data-ttu-id="0aaa4-112">The `New` keyword is also used in type parameter lists to specify that the supplied type must expose an accessible parameterless constructor.</span><span class="sxs-lookup"><span data-stu-id="0aaa4-112">The `New` keyword is also used in type parameter lists to specify that the supplied type must expose an accessible parameterless constructor.</span></span> <span data-ttu-id="0aaa4-113">For more information about type parameters and constraints, see [Type List](../statements/type-list.md).</span><span class="sxs-lookup"><span data-stu-id="0aaa4-113">For more information about type parameters and constraints, see [Type List](../statements/type-list.md).</span></span>

<span data-ttu-id="0aaa4-114">To create a constructor procedure for a class, set the name of a `Sub` procedure to the `New` keyword.</span><span class="sxs-lookup"><span data-stu-id="0aaa4-114">To create a constructor procedure for a class, set the name of a `Sub` procedure to the `New` keyword.</span></span> <span data-ttu-id="0aaa4-115">For more information, see [Object Lifetime: How Objects Are Created and Destroyed](../../programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).</span><span class="sxs-lookup"><span data-stu-id="0aaa4-115">For more information, see [Object Lifetime: How Objects Are Created and Destroyed](../../programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).</span></span>

<span data-ttu-id="0aaa4-116">Das `New`-Schlüsselwort kann in den folgenden Kontexten verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="0aaa4-116">The `New` keyword can be used in these contexts:</span></span>

- [<span data-ttu-id="0aaa4-117">Dim-Anweisung</span><span class="sxs-lookup"><span data-stu-id="0aaa4-117">Dim Statement</span></span>](../statements/dim-statement.md)
- [<span data-ttu-id="0aaa4-118">Of</span><span class="sxs-lookup"><span data-stu-id="0aaa4-118">Of</span></span>](../statements/of-clause.md)
- [<span data-ttu-id="0aaa4-119">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="0aaa4-119">Sub Statement</span></span>](../statements/sub-statement.md)

## <a name="see-also"></a><span data-ttu-id="0aaa4-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0aaa4-120">See also</span></span>

- <xref:System.OutOfMemoryException>
- [<span data-ttu-id="0aaa4-121">Stichwörter</span><span class="sxs-lookup"><span data-stu-id="0aaa4-121">Keywords</span></span>](../keywords/index.md)
- [<span data-ttu-id="0aaa4-122">Typliste</span><span class="sxs-lookup"><span data-stu-id="0aaa4-122">Type List</span></span>](../statements/type-list.md)
- [<span data-ttu-id="0aaa4-123">Generic Types in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0aaa4-123">Generic Types in Visual Basic</span></span>](../../programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="0aaa4-124">Objektlebensdauer: Erstellen und Zerstören von Objekten</span><span class="sxs-lookup"><span data-stu-id="0aaa4-124">Object Lifetime: How Objects Are Created and Destroyed</span></span>](../../programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
