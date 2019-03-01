---
title: Operator New (Visual Basic)
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
ms.openlocfilehash: dda23ef3ff49bd32474f39f5ae1807e57bdc2a62
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56980463"
---
# <a name="new-operator-visual-basic"></a><span data-ttu-id="25fc6-102">Operator New (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="25fc6-102">New Operator (Visual Basic)</span></span>
<span data-ttu-id="25fc6-103">Führt eine `New` -Klausel zum Erstellen einer neuen Objektinstanz gibt eine Konstruktoreinschränkung für einen Typparameter oder identifiziert eine `Sub` Prozedur als ein Klassenkonstruktor.</span><span class="sxs-lookup"><span data-stu-id="25fc6-103">Introduces a `New` clause to create a new object instance, specifies a constructor constraint on a type parameter, or identifies a `Sub` procedure as a class constructor.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="25fc6-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="25fc6-104">Remarks</span></span>  
 <span data-ttu-id="25fc6-105">In einer Deklaration oder zuweisungsanweisung eine `New` -Klausel muss angeben eine definierte Klasse, die von dem die Instanz erstellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="25fc6-105">In a declaration or assignment statement, a `New` clause must specify a defined class from which the instance can be created.</span></span> <span data-ttu-id="25fc6-106">Dies bedeutet, dass die Klasse einen oder mehrere Konstruktoren verfügbar machen muss, die der aufrufende Code zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="25fc6-106">This means that the class must expose one or more constructors that the calling code can access.</span></span>  
  
 <span data-ttu-id="25fc6-107">Sie können eine `New` -Klausel in einer deklarationsanweisung oder eine zuweisungsanweisung.</span><span class="sxs-lookup"><span data-stu-id="25fc6-107">You can use a `New` clause in a declaration statement or an assignment statement.</span></span> <span data-ttu-id="25fc6-108">Wenn die Anweisung ausgeführt wird, ruft er den entsprechenden Konstruktor der angegebenen Klasse und übergeben von Argumenten, die Sie angegeben haben.</span><span class="sxs-lookup"><span data-stu-id="25fc6-108">When the statement runs, it calls the appropriate constructor of the specified class, passing any arguments you have supplied.</span></span> <span data-ttu-id="25fc6-109">Das folgende Beispiel zeigt dies durch das Erstellen von Instanzen von einem `Customer` -Klasse, die zwei Konstruktoren, die keine Parameter akzeptiert und eine, die einen Zeichenfolgenparameter akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="25fc6-109">The following example demonstrates this by creating instances of a `Customer` class that has two constructors, one that takes no parameters and one that takes a string parameter.</span></span>  
  
 [!code-vb[VbVbalrKeywords#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class6.vb#11)]  
  
 <span data-ttu-id="25fc6-110">Da Arrays Klassen sind `New` können eine neues Array-Instanz erstellen, wie in den folgenden Beispielen gezeigt.</span><span class="sxs-lookup"><span data-stu-id="25fc6-110">Since arrays are classes, `New` can create a new array instance, as shown in the following examples.</span></span>  
  
 [!code-vb[VbVbalrKeywords#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class6.vb#12)]  
  
 <span data-ttu-id="25fc6-111">Löst die common Language Runtime (CLR) eine <xref:System.OutOfMemoryException> Fehler, wenn nicht genügend zum Erstellen der neuen Instanz Arbeitsspeicher.</span><span class="sxs-lookup"><span data-stu-id="25fc6-111">The common language runtime (CLR) throws an <xref:System.OutOfMemoryException> error if there is insufficient memory to create the new instance.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="25fc6-112">Die `New` -Schlüsselwort wird auch in der Parameterliste des Typs verwendet, um anzugeben, dass der angegebene Typ der einen zugänglichen parameterlosen Konstruktor verfügbar machen muss.</span><span class="sxs-lookup"><span data-stu-id="25fc6-112">The `New` keyword is also used in type parameter lists to specify that the supplied type must expose an accessible parameterless constructor.</span></span> <span data-ttu-id="25fc6-113">Weitere Informationen über Typparameter und Einschränkungen finden Sie unter [Typliste](../../../visual-basic/language-reference/statements/type-list.md).</span><span class="sxs-lookup"><span data-stu-id="25fc6-113">For more information about type parameters and constraints, see [Type List](../../../visual-basic/language-reference/statements/type-list.md).</span></span>  
  
 <span data-ttu-id="25fc6-114">Um eine Konstruktorprozedur für eine Klasse zu erstellen, legen Sie den Namen des eine `Sub` Vorgehensweise die `New` Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="25fc6-114">To create a constructor procedure for a class, set the name of a `Sub` procedure to the `New` keyword.</span></span> <span data-ttu-id="25fc6-115">Weitere Informationen finden Sie unter [Object Lifetime: Wie die Objekte erstellt und zerstört werden](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).</span><span class="sxs-lookup"><span data-stu-id="25fc6-115">For more information, see [Object Lifetime: How Objects Are Created and Destroyed](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).</span></span>  
  
 <span data-ttu-id="25fc6-116">Das `New`-Schlüsselwort kann in den folgenden Kontexten verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="25fc6-116">The `New` keyword can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="25fc6-117">Dim-Anweisung</span><span class="sxs-lookup"><span data-stu-id="25fc6-117">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="25fc6-118">Of</span><span class="sxs-lookup"><span data-stu-id="25fc6-118">Of</span></span>](../../../visual-basic/language-reference/statements/of-clause.md)  
  
 [<span data-ttu-id="25fc6-119">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="25fc6-119">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="25fc6-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="25fc6-120">See also</span></span>
- <xref:System.OutOfMemoryException>
- [<span data-ttu-id="25fc6-121">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="25fc6-121">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
- [<span data-ttu-id="25fc6-122">Typliste</span><span class="sxs-lookup"><span data-stu-id="25fc6-122">Type List</span></span>](../../../visual-basic/language-reference/statements/type-list.md)
- [<span data-ttu-id="25fc6-123">Generic Types in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="25fc6-123">Generic Types in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="25fc6-124">Objektlebensdauer: Wie die Objekte erstellt und zerstört werden</span><span class="sxs-lookup"><span data-stu-id="25fc6-124">Object Lifetime: How Objects Are Created and Destroyed</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
