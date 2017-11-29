---
title: Operator New (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "23"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 74f0352379e861ad135ea23d31ea07d638f9e6c1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="new-operator-visual-basic"></a><span data-ttu-id="40b71-102">Operator New (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="40b71-102">New Operator (Visual Basic)</span></span>
<span data-ttu-id="40b71-103">Führt eine `New` -Klausel, um eine neue Objektinstanz erstellt gibt eine Konstruktoreinschränkung für einen Typparameter, oder gibt einen `Sub` Prozedur als ein Klassenkonstruktor.</span><span class="sxs-lookup"><span data-stu-id="40b71-103">Introduces a `New` clause to create a new object instance, specifies a constructor constraint on a type parameter, or identifies a `Sub` procedure as a class constructor.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="40b71-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="40b71-104">Remarks</span></span>  
 <span data-ttu-id="40b71-105">In einer Deklaration oder zuweisungsanweisung eine `New` -Klausel muss eine definierte Klasse, von dem die Instanz erstellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="40b71-105">In a declaration or assignment statement, a `New` clause must specify a defined class from which the instance can be created.</span></span> <span data-ttu-id="40b71-106">Dies bedeutet, dass die Klasse einen oder mehrere Konstruktoren verfügbar machen muss, die der aufrufende Code zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="40b71-106">This means that the class must expose one or more constructors that the calling code can access.</span></span>  
  
 <span data-ttu-id="40b71-107">Sie können eine `New` -Klausel in einer deklarationsanweisung oder eine zuweisungsanweisung.</span><span class="sxs-lookup"><span data-stu-id="40b71-107">You can use a `New` clause in a declaration statement or an assignment statement.</span></span> <span data-ttu-id="40b71-108">Wenn die Anweisung ausgeführt wird, ruft es den entsprechenden Konstruktor der angegebenen Klasse, und übergeben von Argumenten, die Sie angegeben haben.</span><span class="sxs-lookup"><span data-stu-id="40b71-108">When the statement runs, it calls the appropriate constructor of the specified class, passing any arguments you have supplied.</span></span> <span data-ttu-id="40b71-109">Das folgende Beispiel zeigt dies durch Erstellen von Instanzen von einem `Customer` Klasse, die zwei Konstruktoren aufweist, eine, die keine Parameter akzeptiert und eine, die einen Zeichenfolgenparameter annimmt.</span><span class="sxs-lookup"><span data-stu-id="40b71-109">The following example demonstrates this by creating instances of a `Customer` class that has two constructors, one that takes no parameters and one that takes a string parameter.</span></span>  
  
 [!code-vb[VbVbalrKeywords#11](../../../visual-basic/language-reference/codesnippet/VisualBasic/new-operator_1.vb)]  
  
 <span data-ttu-id="40b71-110">Da Arrays Klassen sind `New` können eine neue Arrayinstanz erstellen, wie in den folgenden Beispielen gezeigt.</span><span class="sxs-lookup"><span data-stu-id="40b71-110">Since arrays are classes, `New` can create a new array instance, as shown in the following examples.</span></span>  
  
 [!code-vb[VbVbalrKeywords#12](../../../visual-basic/language-reference/codesnippet/VisualBasic/new-operator_2.vb)]  
  
 <span data-ttu-id="40b71-111">Löst die common Language Runtime (CLR) eine <xref:System.OutOfMemoryException> Fehlermeldung, wenn nicht genügend zum Erstellen der neuen Instanz Arbeitsspeicher.</span><span class="sxs-lookup"><span data-stu-id="40b71-111">The common language runtime (CLR) throws an <xref:System.OutOfMemoryException> error if there is insufficient memory to create the new instance.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="40b71-112">Die `New` -Schlüsselwort wird auch in Typparameterlisten verwendet, um anzugeben, dass der angegebene Typ einen zugänglichen parameterlosen Konstruktor verfügbar machen muss.</span><span class="sxs-lookup"><span data-stu-id="40b71-112">The `New` keyword is also used in type parameter lists to specify that the supplied type must expose an accessible parameterless constructor.</span></span> <span data-ttu-id="40b71-113">Weitere Informationen über Typparameter und Einschränkungen finden Sie unter [Typliste](../../../visual-basic/language-reference/statements/type-list.md).</span><span class="sxs-lookup"><span data-stu-id="40b71-113">For more information about type parameters and constraints, see [Type List](../../../visual-basic/language-reference/statements/type-list.md).</span></span>  
  
 <span data-ttu-id="40b71-114">Um eine Konstruktorprozedur für eine Klasse zu erstellen, legen Sie den Namen des eine `Sub` Vorgehensweise der `New` Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="40b71-114">To create a constructor procedure for a class, set the name of a `Sub` procedure to the `New` keyword.</span></span> <span data-ttu-id="40b71-115">Weitere Informationen finden Sie unter [Objektlebensdauer: wie Objekte erstellen und zerstören sind](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).</span><span class="sxs-lookup"><span data-stu-id="40b71-115">For more information, see [Object Lifetime: How Objects Are Created and Destroyed](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).</span></span>  
  
 <span data-ttu-id="40b71-116">Das `New`-Schlüsselwort kann in den folgenden Kontexten verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="40b71-116">The `New` keyword can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="40b71-117">Dim-Anweisung</span><span class="sxs-lookup"><span data-stu-id="40b71-117">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="40b71-118">Of</span><span class="sxs-lookup"><span data-stu-id="40b71-118">Of</span></span>](../../../visual-basic/language-reference/statements/of-clause.md)  
  
 [<span data-ttu-id="40b71-119">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="40b71-119">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="40b71-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="40b71-120">See Also</span></span>  
 <xref:System.OutOfMemoryException>  
 [<span data-ttu-id="40b71-121">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="40b71-121">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)  
 [<span data-ttu-id="40b71-122">Typliste</span><span class="sxs-lookup"><span data-stu-id="40b71-122">Type List</span></span>](../../../visual-basic/language-reference/statements/type-list.md)  
 [<span data-ttu-id="40b71-123">Generische Typen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="40b71-123">Generic Types in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [<span data-ttu-id="40b71-124">Objektlebensdauer: Erstellen und Zerstören von Objekten</span><span class="sxs-lookup"><span data-stu-id="40b71-124">Object Lifetime: How Objects Are Created and Destroyed</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
