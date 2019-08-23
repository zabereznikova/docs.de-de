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
ms.openlocfilehash: 36cf71529b1f81c27881638d788117222c37171d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69955883"
---
# <a name="new-operator-visual-basic"></a><span data-ttu-id="341ae-102">Operator New (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="341ae-102">New Operator (Visual Basic)</span></span>
<span data-ttu-id="341ae-103">Führt eine `New` -Klausel ein, um eine neue Objektinstanz zu erstellen, gibt eine Konstruktoreinschränkung für einen Typparameter `Sub` an oder identifiziert eine Prozedur als Klassenkonstruktor.</span><span class="sxs-lookup"><span data-stu-id="341ae-103">Introduces a `New` clause to create a new object instance, specifies a constructor constraint on a type parameter, or identifies a `Sub` procedure as a class constructor.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="341ae-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="341ae-104">Remarks</span></span>  
 <span data-ttu-id="341ae-105">In einer Deklaration oder Zuweisungsanweisung `New` muss eine-Klausel eine definierte Klasse angeben, aus der die Instanz erstellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="341ae-105">In a declaration or assignment statement, a `New` clause must specify a defined class from which the instance can be created.</span></span> <span data-ttu-id="341ae-106">Dies bedeutet, dass die Klasse einen oder mehrere Konstruktoren verfügbar machen muss, auf die der aufrufenden Code zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="341ae-106">This means that the class must expose one or more constructors that the calling code can access.</span></span>  
  
 <span data-ttu-id="341ae-107">Sie können eine `New` -Klausel in einer Deklarations Anweisung oder einer Zuweisungsanweisung verwenden.</span><span class="sxs-lookup"><span data-stu-id="341ae-107">You can use a `New` clause in a declaration statement or an assignment statement.</span></span> <span data-ttu-id="341ae-108">Wenn die Anweisung ausgeführt wird, wird der entsprechende Konstruktor der angegebenen Klasse aufgerufen, wobei alle von Ihnen bereitgestellten Argumente übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="341ae-108">When the statement runs, it calls the appropriate constructor of the specified class, passing any arguments you have supplied.</span></span> <span data-ttu-id="341ae-109">Dies wird im folgenden Beispiel veranschaulicht, indem Instanzen `Customer` einer Klasse erstellt werden, die über zwei Konstruktoren verfügt, eine, die keine Parameter annimmt, und eine Klasse, die einen String-Parameter annimmt.</span><span class="sxs-lookup"><span data-stu-id="341ae-109">The following example demonstrates this by creating instances of a `Customer` class that has two constructors, one that takes no parameters and one that takes a string parameter.</span></span>  
  
 [!code-vb[VbVbalrKeywords#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class6.vb#11)]  
  
 <span data-ttu-id="341ae-110">Da Arrays Klassen sind, `New` kann eine neue Array Instanz erstellen, wie in den folgenden Beispielen gezeigt.</span><span class="sxs-lookup"><span data-stu-id="341ae-110">Since arrays are classes, `New` can create a new array instance, as shown in the following examples.</span></span>  
  
 [!code-vb[VbVbalrKeywords#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class6.vb#12)]  
  
 <span data-ttu-id="341ae-111">Der Common Language Runtime (CLR) löst einen <xref:System.OutOfMemoryException> Fehler aus, wenn nicht genügend Arbeitsspeicher vorhanden ist, um die neue Instanz zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="341ae-111">The common language runtime (CLR) throws an <xref:System.OutOfMemoryException> error if there is insufficient memory to create the new instance.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="341ae-112">Das `New` -Schlüsselwort wird auch in Typparameter Listen verwendet, um anzugeben, dass der angegebene Typ einen zugänglichen Parameter losen Konstruktor verfügbar machen muss.</span><span class="sxs-lookup"><span data-stu-id="341ae-112">The `New` keyword is also used in type parameter lists to specify that the supplied type must expose an accessible parameterless constructor.</span></span> <span data-ttu-id="341ae-113">Weitere Informationen zu Typparametern und Einschränkungen finden Sie unter [Type List](../../../visual-basic/language-reference/statements/type-list.md).</span><span class="sxs-lookup"><span data-stu-id="341ae-113">For more information about type parameters and constraints, see [Type List](../../../visual-basic/language-reference/statements/type-list.md).</span></span>  
  
 <span data-ttu-id="341ae-114">Zum Erstellen einer konstruktorprozedur für eine Klasse legen Sie den Namen einer `Sub` Prozedur auf das `New` Schlüsselwort fest.</span><span class="sxs-lookup"><span data-stu-id="341ae-114">To create a constructor procedure for a class, set the name of a `Sub` procedure to the `New` keyword.</span></span> <span data-ttu-id="341ae-115">Weitere Informationen finden [Sie unter Objekt Lebensdauer: Die Art und Weise, wie](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)Objekte erstellt und zerstört werden.</span><span class="sxs-lookup"><span data-stu-id="341ae-115">For more information, see [Object Lifetime: How Objects Are Created and Destroyed](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).</span></span>  
  
 <span data-ttu-id="341ae-116">Das `New`-Schlüsselwort kann in den folgenden Kontexten verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="341ae-116">The `New` keyword can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="341ae-117">Dim-Anweisung</span><span class="sxs-lookup"><span data-stu-id="341ae-117">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [<span data-ttu-id="341ae-118">Of</span><span class="sxs-lookup"><span data-stu-id="341ae-118">Of</span></span>](../../../visual-basic/language-reference/statements/of-clause.md)  
  
 [<span data-ttu-id="341ae-119">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="341ae-119">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="341ae-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="341ae-120">See also</span></span>

- <xref:System.OutOfMemoryException>
- [<span data-ttu-id="341ae-121">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="341ae-121">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
- [<span data-ttu-id="341ae-122">Typliste</span><span class="sxs-lookup"><span data-stu-id="341ae-122">Type List</span></span>](../../../visual-basic/language-reference/statements/type-list.md)
- [<span data-ttu-id="341ae-123">Generic Types in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="341ae-123">Generic Types in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="341ae-124">Objekt Lebensdauer: Erstellen und zerstören von Objekten</span><span class="sxs-lookup"><span data-stu-id="341ae-124">Object Lifetime: How Objects Are Created and Destroyed</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
