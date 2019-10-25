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
ms.openlocfilehash: c0870f4b056658a22928769c369024cdda24f354
ms.sourcegitcommit: 9bd1c09128e012b6e34bdcbdf3576379f58f3137
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/23/2019
ms.locfileid: "72799037"
---
# <a name="new-operator-visual-basic"></a><span data-ttu-id="59682-102">Operator New (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="59682-102">New Operator (Visual Basic)</span></span>

<span data-ttu-id="59682-103">Führt eine `New`-Klausel ein, um eine neue Objektinstanz zu erstellen, gibt eine Konstruktoreinschränkung für einen Typparameter an oder identifiziert eine `Sub` Prozedur als Klassenkonstruktor.</span><span class="sxs-lookup"><span data-stu-id="59682-103">Introduces a `New` clause to create a new object instance, specifies a constructor constraint on a type parameter, or identifies a `Sub` procedure as a class constructor.</span></span>

## <a name="remarks"></a><span data-ttu-id="59682-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="59682-104">Remarks</span></span>

<span data-ttu-id="59682-105">In einer Deklaration oder Zuweisungsanweisung muss eine `New`-Klausel eine definierte Klasse angeben, aus der die Instanz erstellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="59682-105">In a declaration or assignment statement, a `New` clause must specify a defined class from which the instance can be created.</span></span> <span data-ttu-id="59682-106">Dies bedeutet, dass die Klasse einen oder mehrere Konstruktoren verfügbar machen muss, auf die der aufrufenden Code zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="59682-106">This means that the class must expose one or more constructors that the calling code can access.</span></span>

<span data-ttu-id="59682-107">Sie können eine `New`-Klausel in einer Deklarations Anweisung oder einer Zuweisungsanweisung verwenden.</span><span class="sxs-lookup"><span data-stu-id="59682-107">You can use a `New` clause in a declaration statement or an assignment statement.</span></span> <span data-ttu-id="59682-108">Wenn die Anweisung ausgeführt wird, wird der entsprechende Konstruktor der angegebenen Klasse aufgerufen, wobei alle von Ihnen bereitgestellten Argumente übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="59682-108">When the statement runs, it calls the appropriate constructor of the specified class, passing any arguments you have supplied.</span></span> <span data-ttu-id="59682-109">Dies wird im folgenden Beispiel veranschaulicht, indem Instanzen einer `Customer`-Klasse erstellt werden, die zwei Konstruktoren hat, eine ohne Parameter und eine, die einen Zeichen folgen Parameter annimmt:</span><span class="sxs-lookup"><span data-stu-id="59682-109">The following example demonstrates this by creating instances of a `Customer` class that has two constructors, one that takes no parameters and one that takes a string parameter:</span></span>

[!code-vb[VbVbalrKeywords#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class6.vb#11)]

<span data-ttu-id="59682-110">Da Arrays Klassen sind, können `New` eine neue Array Instanz erstellen, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="59682-110">Since arrays are classes, `New` can create a new array instance, as shown in the following example:</span></span>

[!code-vb[VbVbalrKeywords#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class6.vb#12)]

<span data-ttu-id="59682-111">Der Common Language Runtime (CLR) löst einen <xref:System.OutOfMemoryException> Fehler aus, wenn nicht genügend Arbeitsspeicher vorhanden ist, um die neue Instanz zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="59682-111">The common language runtime (CLR) throws an <xref:System.OutOfMemoryException> error if there is insufficient memory to create the new instance.</span></span>

> [!NOTE]
> <span data-ttu-id="59682-112">Das `New`-Schlüsselwort wird auch in Typparameter Listen verwendet, um anzugeben, dass der angegebene Typ einen zugänglichen Parameter losen Konstruktor verfügbar machen muss.</span><span class="sxs-lookup"><span data-stu-id="59682-112">The `New` keyword is also used in type parameter lists to specify that the supplied type must expose an accessible parameterless constructor.</span></span> <span data-ttu-id="59682-113">Weitere Informationen zu Typparametern und Einschränkungen finden Sie unter [Type List](../statements/type-list.md).</span><span class="sxs-lookup"><span data-stu-id="59682-113">For more information about type parameters and constraints, see [Type List](../statements/type-list.md).</span></span>

<span data-ttu-id="59682-114">Wenn Sie eine konstruktorprozedur für eine Klasse erstellen möchten, legen Sie den Namen einer `Sub` Prozedur auf das `New`-Schlüsselwort fest.</span><span class="sxs-lookup"><span data-stu-id="59682-114">To create a constructor procedure for a class, set the name of a `Sub` procedure to the `New` keyword.</span></span> <span data-ttu-id="59682-115">Weitere Informationen finden Sie unter [Objekt Lebensdauer: Erstellen und zerstören von Objekten](../../programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).</span><span class="sxs-lookup"><span data-stu-id="59682-115">For more information, see [Object Lifetime: How Objects Are Created and Destroyed](../../programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).</span></span>

<span data-ttu-id="59682-116">Das `New`-Schlüsselwort kann in den folgenden Kontexten verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="59682-116">The `New` keyword can be used in these contexts:</span></span>

- [<span data-ttu-id="59682-117">Dim-Anweisung</span><span class="sxs-lookup"><span data-stu-id="59682-117">Dim Statement</span></span>](../statements/dim-statement.md)
- [<span data-ttu-id="59682-118">Of</span><span class="sxs-lookup"><span data-stu-id="59682-118">Of</span></span>](../statements/of-clause.md)
- [<span data-ttu-id="59682-119">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="59682-119">Sub Statement</span></span>](../statements/sub-statement.md)

## <a name="see-also"></a><span data-ttu-id="59682-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="59682-120">See also</span></span>

- <xref:System.OutOfMemoryException>
- [<span data-ttu-id="59682-121">Stichwörter</span><span class="sxs-lookup"><span data-stu-id="59682-121">Keywords</span></span>](../keywords/index.md)
- [<span data-ttu-id="59682-122">Typliste</span><span class="sxs-lookup"><span data-stu-id="59682-122">Type List</span></span>](../statements/type-list.md)
- [<span data-ttu-id="59682-123">Generic Types in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="59682-123">Generic Types in Visual Basic</span></span>](../../programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="59682-124">Objektlebensdauer: Erstellen und Zerstören von Objekten</span><span class="sxs-lookup"><span data-stu-id="59682-124">Object Lifetime: How Objects Are Created and Destroyed</span></span>](../../programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
