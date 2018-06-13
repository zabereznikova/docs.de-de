---
title: Static (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Static
helpviewer_keywords:
- static modifier
- Static keyword [Visual Basic]
ms.assetid: 19013910-4658-47b6-a22e-1744b527979e
ms.openlocfilehash: 2cbd99a026a5ebf0e215ee5732d62ccf639d3836
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33602053"
---
# <a name="static-visual-basic"></a><span data-ttu-id="06d78-102">Static (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="06d78-102">Static (Visual Basic)</span></span>
<span data-ttu-id="06d78-103">Gibt an, dass eine oder mehrere deklarierte lokale Variablen weiterhin vorhanden sein und behalten die neuesten Werte nach dem Beenden der Prozedur, in der sie deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="06d78-103">Specifies that one or more declared local variables are to continue to exist and retain their latest values after termination of the procedure in which they are declared.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="06d78-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="06d78-104">Remarks</span></span>  
 <span data-ttu-id="06d78-105">Normalerweise wird eine lokale Variable in einer Prozedur vorhanden ist, sobald die Prozedur beendet wird.</span><span class="sxs-lookup"><span data-stu-id="06d78-105">Normally, a local variable in a procedure ceases to exist as soon as the procedure stops.</span></span> <span data-ttu-id="06d78-106">Eine statische Variable bleibt erhalten und behält den letzten Wert.</span><span class="sxs-lookup"><span data-stu-id="06d78-106">A static variable continues to exist and retains its most recent value.</span></span> <span data-ttu-id="06d78-107">Das nächste Mal, das Ihr Code die Prozedur aufruft. die Variable wird nicht erneut initialisiert, und sie behält den neuesten-Wert, den Sie zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="06d78-107">The next time your code calls the procedure, the variable is not reinitialized, and it still holds the latest value that you assigned to it.</span></span> <span data-ttu-id="06d78-108">Eine statische Variable bleibt für die Lebensdauer der Klasse oder des Moduls vorhanden sein, die in der Sie definiert ist.</span><span class="sxs-lookup"><span data-stu-id="06d78-108">A static variable continues to exist for the lifetime of the class or module that it is defined in.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="06d78-109">Regeln</span><span class="sxs-lookup"><span data-stu-id="06d78-109">Rules</span></span>  
  
-   <span data-ttu-id="06d78-110">**Deklarationskontext.**</span><span class="sxs-lookup"><span data-stu-id="06d78-110">**Declaration Context.**</span></span> <span data-ttu-id="06d78-111">Sie können `Static` nur auf lokale Variablen.</span><span class="sxs-lookup"><span data-stu-id="06d78-111">You can use `Static` only on local variables.</span></span> <span data-ttu-id="06d78-112">Dies bedeutet, dass der Deklarationskontext für eine `Static` Variable eine Prozedur oder einen Block in einer Prozedur sein muss, und keine Quelldatei, Namespace, Klasse, Struktur oder Modul.</span><span class="sxs-lookup"><span data-stu-id="06d78-112">This means the declaration context for a `Static` variable must be a procedure or a block in a procedure, and it cannot be a source file, namespace, class, structure, or module.</span></span>  
  
     <span data-ttu-id="06d78-113">Sie können keine `Static` innerhalb einer Strukturprozedur.</span><span class="sxs-lookup"><span data-stu-id="06d78-113">You cannot use `Static` inside a structure procedure.</span></span>  
  
-   <span data-ttu-id="06d78-114">Die Datentypen der `Static` lokale Variablen können nicht abgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="06d78-114">The data types of `Static` local variables cannot be inferred.</span></span> <span data-ttu-id="06d78-115">Weitere Informationen finden Sie unter [lokalen Typrückschluss](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span><span class="sxs-lookup"><span data-stu-id="06d78-115">For more information, see [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span></span>  
  
-   <span data-ttu-id="06d78-116">**Kombinierte Modifizierer.**</span><span class="sxs-lookup"><span data-stu-id="06d78-116">**Combined Modifiers.**</span></span> <span data-ttu-id="06d78-117">Sie können keine angeben `Static` zusammen mit `ReadOnly`, `Shadows`, oder `Shared` in der gleichen Deklaration.</span><span class="sxs-lookup"><span data-stu-id="06d78-117">You cannot specify `Static` together with `ReadOnly`, `Shadows`, or `Shared` in the same declaration.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="06d78-118">Verhalten</span><span class="sxs-lookup"><span data-stu-id="06d78-118">Behavior</span></span>  
 <span data-ttu-id="06d78-119">Wenn Sie eine statische Variable in Deklarieren einer `Shared` Prozedur, die nur eine Kopie der statischen Variablen ist für die gesamte Anwendung verfügbar.</span><span class="sxs-lookup"><span data-stu-id="06d78-119">When you declare a static variable in a `Shared` procedure, only one copy of the static variable is available for the whole application.</span></span> <span data-ttu-id="06d78-120">Rufen Sie eine `Shared` Prozedur mit der Klasse benennen, nicht auf eine Variable, die auf eine Instanz der Klasse verweist.</span><span class="sxs-lookup"><span data-stu-id="06d78-120">You call a `Shared` procedure by using the class name, not a variable that points to an instance of the class.</span></span>  
  
 <span data-ttu-id="06d78-121">Wenn Sie eine statische Variable in einer Prozedur, die nicht deklarieren `Shared`, nur eine Kopie der Variablen für jede Instanz der Klasse zur Verfügung steht.</span><span class="sxs-lookup"><span data-stu-id="06d78-121">When you declare a static variable in a procedure that isn't `Shared`, only one copy of the variable is available for each instance of the class.</span></span> <span data-ttu-id="06d78-122">Rufen Sie eine nicht freigegebene Prozedur mithilfe einer Variablen, die auf eine bestimmte Instanz der Klasse verweist.</span><span class="sxs-lookup"><span data-stu-id="06d78-122">You call a non-shared procedure by using a variable that points to a specific instance of the class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="06d78-123">Beispiel</span><span class="sxs-lookup"><span data-stu-id="06d78-123">Example</span></span>  
 <span data-ttu-id="06d78-124">Das folgende Beispiel veranschaulicht die Verwendung von `Static`.</span><span class="sxs-lookup"><span data-stu-id="06d78-124">The following example demonstrates the use of `Static`.</span></span>  
  
 [!code-vb[VbVbalrKeywords#5](../../../visual-basic/language-reference/codesnippet/VisualBasic/static_1.vb)]  
  
 <span data-ttu-id="06d78-125">Die `Static` Variable `totalSales` wird nur einmal mit 0 initialisiert.</span><span class="sxs-lookup"><span data-stu-id="06d78-125">The `Static` variable `totalSales` is initialized to 0 only one time.</span></span> <span data-ttu-id="06d78-126">Jedes Mal, den Sie eingeben `updateSales`, `totalSales` immer noch den letzten Wert an, die Sie dafür berechnet.</span><span class="sxs-lookup"><span data-stu-id="06d78-126">Each time that you enter `updateSales`, `totalSales` still has the most recent value that you calculated for it.</span></span>  
  
 <span data-ttu-id="06d78-127">Die `Static` Modifizierer kann in diesem Kontext verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="06d78-127">The `Static` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="06d78-128">Dim-Anweisung</span><span class="sxs-lookup"><span data-stu-id="06d78-128">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="06d78-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="06d78-129">See Also</span></span>  
 [<span data-ttu-id="06d78-130">Shadows</span><span class="sxs-lookup"><span data-stu-id="06d78-130">Shadows</span></span>](../../../visual-basic/language-reference/modifiers/shadows.md)  
 [<span data-ttu-id="06d78-131">Shared</span><span class="sxs-lookup"><span data-stu-id="06d78-131">Shared</span></span>](../../../visual-basic/language-reference/modifiers/shared.md)  
 [<span data-ttu-id="06d78-132">Lebensdauer in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="06d78-132">Lifetime in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)  
 [<span data-ttu-id="06d78-133">Variablendeklaration</span><span class="sxs-lookup"><span data-stu-id="06d78-133">Variable Declaration</span></span>](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)  
 [<span data-ttu-id="06d78-134">Strukturen</span><span class="sxs-lookup"><span data-stu-id="06d78-134">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [<span data-ttu-id="06d78-135">Lokaler Typrückschluss</span><span class="sxs-lookup"><span data-stu-id="06d78-135">Local Type Inference</span></span>](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [<span data-ttu-id="06d78-136">Objekte und Klassen</span><span class="sxs-lookup"><span data-stu-id="06d78-136">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
