---
title: Static (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Static
helpviewer_keywords:
- static modifier
- Static keyword [Visual Basic]
ms.assetid: 19013910-4658-47b6-a22e-1744b527979e
ms.openlocfilehash: f1031fe005a2fc264b50116b8ea3311dc7065dbc
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64647642"
---
# <a name="static-visual-basic"></a><span data-ttu-id="e7bf5-102">Static (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e7bf5-102">Static (Visual Basic)</span></span>
<span data-ttu-id="e7bf5-103">Gibt an, dass eine oder mehrere deklarierte Variablen sind weiterhin vorhanden, und behalten ihre aktuellen Werte nach dem Beenden der Prozedur, in der sie deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="e7bf5-103">Specifies that one or more declared local variables are to continue to exist and retain their latest values after termination of the procedure in which they are declared.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e7bf5-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e7bf5-104">Remarks</span></span>  
 <span data-ttu-id="e7bf5-105">Normalerweise wird eine lokale Variable in einer Prozedur vorhanden ist, sobald die Prozedur beendet wird.</span><span class="sxs-lookup"><span data-stu-id="e7bf5-105">Normally, a local variable in a procedure ceases to exist as soon as the procedure stops.</span></span> <span data-ttu-id="e7bf5-106">Eine statische Variable bleibt erhalten und den aktuellen Wert beibehält.</span><span class="sxs-lookup"><span data-stu-id="e7bf5-106">A static variable continues to exist and retains its most recent value.</span></span> <span data-ttu-id="e7bf5-107">Das nächste Mal, das der Code der Prozedur wird, die Variable wird nicht erneut initialisiert, und sie behält den aktuellen Wert, den Sie zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="e7bf5-107">The next time your code calls the procedure, the variable is not reinitialized, and it still holds the latest value that you assigned to it.</span></span> <span data-ttu-id="e7bf5-108">Eine statische Variable bleibt für die Lebensdauer der Klasse oder des Moduls vorhanden sein, die sie in definiert ist.</span><span class="sxs-lookup"><span data-stu-id="e7bf5-108">A static variable continues to exist for the lifetime of the class or module that it is defined in.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="e7bf5-109">Regeln</span><span class="sxs-lookup"><span data-stu-id="e7bf5-109">Rules</span></span>  
  
- <span data-ttu-id="e7bf5-110">**Deklarationskontext.**</span><span class="sxs-lookup"><span data-stu-id="e7bf5-110">**Declaration Context.**</span></span> <span data-ttu-id="e7bf5-111">Sie können `Static` nur für lokale Variablen.</span><span class="sxs-lookup"><span data-stu-id="e7bf5-111">You can use `Static` only on local variables.</span></span> <span data-ttu-id="e7bf5-112">Dies bedeutet, dass der Deklarationskontext für eine `Static` Variable muss eine Prozedur oder einen Block in einer Prozedur, und ist nicht möglich Quelldatei, Namespace, Klasse, Struktur oder Moduls.</span><span class="sxs-lookup"><span data-stu-id="e7bf5-112">This means the declaration context for a `Static` variable must be a procedure or a block in a procedure, and it cannot be a source file, namespace, class, structure, or module.</span></span>  
  
     <span data-ttu-id="e7bf5-113">Sie können keine `Static` innerhalb einer Strukturprozedur.</span><span class="sxs-lookup"><span data-stu-id="e7bf5-113">You cannot use `Static` inside a structure procedure.</span></span>  
  
- <span data-ttu-id="e7bf5-114">Die Datentypen der `Static` lokale Variablen können nicht abgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="e7bf5-114">The data types of `Static` local variables cannot be inferred.</span></span> <span data-ttu-id="e7bf5-115">Weitere Informationen finden Sie unter [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span><span class="sxs-lookup"><span data-stu-id="e7bf5-115">For more information, see [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span></span>  
  
- <span data-ttu-id="e7bf5-116">**Kombinierte Modifizierer.**</span><span class="sxs-lookup"><span data-stu-id="e7bf5-116">**Combined Modifiers.**</span></span> <span data-ttu-id="e7bf5-117">Sie können keine angeben `Static` zusammen mit `ReadOnly`, `Shadows`, oder `Shared` in der gleichen Deklaration.</span><span class="sxs-lookup"><span data-stu-id="e7bf5-117">You cannot specify `Static` together with `ReadOnly`, `Shadows`, or `Shared` in the same declaration.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="e7bf5-118">Verhalten</span><span class="sxs-lookup"><span data-stu-id="e7bf5-118">Behavior</span></span>  
 <span data-ttu-id="e7bf5-119">Wenn Sie deklarieren eine statische Variable in einem `Shared` Verfahren nur eine Kopie der statischen Variable steht für die gesamte Anwendung.</span><span class="sxs-lookup"><span data-stu-id="e7bf5-119">When you declare a static variable in a `Shared` procedure, only one copy of the static variable is available for the whole application.</span></span> <span data-ttu-id="e7bf5-120">Rufen Sie eine `Shared` name Prozedur mithilfe der Klasse, die nicht auf eine Variable, die auf eine Instanz der Klasse verweist.</span><span class="sxs-lookup"><span data-stu-id="e7bf5-120">You call a `Shared` procedure by using the class name, not a variable that points to an instance of the class.</span></span>  
  
 <span data-ttu-id="e7bf5-121">Wenn Sie eine statische Variable in einer Prozedur, die nicht deklarieren `Shared`, nur eine Kopie der Variablen für jede Instanz der Klasse zur Verfügung steht.</span><span class="sxs-lookup"><span data-stu-id="e7bf5-121">When you declare a static variable in a procedure that isn't `Shared`, only one copy of the variable is available for each instance of the class.</span></span> <span data-ttu-id="e7bf5-122">Sie können eine nicht freigegebene Prozedur aufrufen, mithilfe einer Variablen, die auf eine bestimmte Instanz der Klasse verweist.</span><span class="sxs-lookup"><span data-stu-id="e7bf5-122">You call a non-shared procedure by using a variable that points to a specific instance of the class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e7bf5-123">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e7bf5-123">Example</span></span>  
 <span data-ttu-id="e7bf5-124">Das folgende Beispiel veranschaulicht die Verwendung von `Static`.</span><span class="sxs-lookup"><span data-stu-id="e7bf5-124">The following example demonstrates the use of `Static`.</span></span>  
  
 [!code-vb[VbVbalrKeywords#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#5)]  
  
 <span data-ttu-id="e7bf5-125">Die `Static` Variable `totalSales` wird nur ein Mal mit 0 initialisiert.</span><span class="sxs-lookup"><span data-stu-id="e7bf5-125">The `Static` variable `totalSales` is initialized to 0 only one time.</span></span> <span data-ttu-id="e7bf5-126">Jedes Mal, den Sie eingeben `updateSales`, `totalSales` noch immer den letzten Wert an, die Sie dafür berechnet.</span><span class="sxs-lookup"><span data-stu-id="e7bf5-126">Each time that you enter `updateSales`, `totalSales` still has the most recent value that you calculated for it.</span></span>  
  
 <span data-ttu-id="e7bf5-127">Die `Static` Modifizierer kann in diesem Kontext verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="e7bf5-127">The `Static` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="e7bf5-128">Dim-Anweisung</span><span class="sxs-lookup"><span data-stu-id="e7bf5-128">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="e7bf5-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e7bf5-129">See also</span></span>

- [<span data-ttu-id="e7bf5-130">Shadows</span><span class="sxs-lookup"><span data-stu-id="e7bf5-130">Shadows</span></span>](../../../visual-basic/language-reference/modifiers/shadows.md)
- [<span data-ttu-id="e7bf5-131">Shared</span><span class="sxs-lookup"><span data-stu-id="e7bf5-131">Shared</span></span>](../../../visual-basic/language-reference/modifiers/shared.md)
- [<span data-ttu-id="e7bf5-132">Lebensdauer in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e7bf5-132">Lifetime in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)
- [<span data-ttu-id="e7bf5-133">Variablendeklaration</span><span class="sxs-lookup"><span data-stu-id="e7bf5-133">Variable Declaration</span></span>](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [<span data-ttu-id="e7bf5-134">Strukturen</span><span class="sxs-lookup"><span data-stu-id="e7bf5-134">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="e7bf5-135">Lokaler Typrückschluss</span><span class="sxs-lookup"><span data-stu-id="e7bf5-135">Local Type Inference</span></span>](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="e7bf5-136">Objekte und Klassen</span><span class="sxs-lookup"><span data-stu-id="e7bf5-136">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
