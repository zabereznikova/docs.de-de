---
title: statischen
ms.date: 07/20/2015
f1_keywords:
- vb.Static
helpviewer_keywords:
- static modifier
- Static keyword [Visual Basic]
ms.assetid: 19013910-4658-47b6-a22e-1744b527979e
ms.openlocfilehash: 2b7113424969b0b18c981b0c8932aeef3795ca4a
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90867666"
---
# <a name="static-visual-basic"></a><span data-ttu-id="5c20b-102">Static (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5c20b-102">Static (Visual Basic)</span></span>

<span data-ttu-id="5c20b-103">Gibt an, dass eine oder mehrere deklarierte lokale Variablen weiterhin vorhanden sein müssen, und behält ihre aktuellen Werte nach der Beendigung der Prozedur bei, in der Sie deklariert wurden.</span><span class="sxs-lookup"><span data-stu-id="5c20b-103">Specifies that one or more declared local variables are to continue to exist and retain their latest values after termination of the procedure in which they are declared.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5c20b-104">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="5c20b-104">Remarks</span></span>  

 <span data-ttu-id="5c20b-105">Normalerweise ist eine lokale Variable in einer Prozedur nicht mehr vorhanden, sobald die Prozedur beendet wird.</span><span class="sxs-lookup"><span data-stu-id="5c20b-105">Normally, a local variable in a procedure ceases to exist as soon as the procedure stops.</span></span> <span data-ttu-id="5c20b-106">Eine statische Variable ist weiterhin vorhanden und behält ihren letzten Wert bei.</span><span class="sxs-lookup"><span data-stu-id="5c20b-106">A static variable continues to exist and retains its most recent value.</span></span> <span data-ttu-id="5c20b-107">Wenn der Code das nächste Mal die Prozedur aufruft, wird die Variable nicht erneut initialisiert, und Sie enthält weiterhin den neuesten Wert, den Sie zugewiesen haben.</span><span class="sxs-lookup"><span data-stu-id="5c20b-107">The next time your code calls the procedure, the variable is not reinitialized, and it still holds the latest value that you assigned to it.</span></span> <span data-ttu-id="5c20b-108">Eine statische Variable ist für die Lebensdauer der Klasse oder des Moduls, in der Sie definiert ist, weiterhin vorhanden.</span><span class="sxs-lookup"><span data-stu-id="5c20b-108">A static variable continues to exist for the lifetime of the class or module that it is defined in.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="5c20b-109">Regeln</span><span class="sxs-lookup"><span data-stu-id="5c20b-109">Rules</span></span>  
  
- <span data-ttu-id="5c20b-110">**Deklarationskontext.**</span><span class="sxs-lookup"><span data-stu-id="5c20b-110">**Declaration Context.**</span></span> <span data-ttu-id="5c20b-111">Sie können `Static` nur für lokale Variablen verwenden.</span><span class="sxs-lookup"><span data-stu-id="5c20b-111">You can use `Static` only on local variables.</span></span> <span data-ttu-id="5c20b-112">Dies bedeutet, dass der Deklarations Kontext für eine `Static` Variable eine Prozedur oder ein Block in einer Prozedur sein muss. es kann sich dabei nicht um eine Quelldatei, einen Namespace, eine Klasse, eine Struktur oder ein Modul handeln.</span><span class="sxs-lookup"><span data-stu-id="5c20b-112">This means the declaration context for a `Static` variable must be a procedure or a block in a procedure, and it cannot be a source file, namespace, class, structure, or module.</span></span>  
  
     <span data-ttu-id="5c20b-113">Sie können nicht `Static` innerhalb einer Struktur Prozedur verwenden.</span><span class="sxs-lookup"><span data-stu-id="5c20b-113">You cannot use `Static` inside a structure procedure.</span></span>  
  
- <span data-ttu-id="5c20b-114">Die Datentypen `Static` lokaler Variablen können nicht abgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="5c20b-114">The data types of `Static` local variables cannot be inferred.</span></span> <span data-ttu-id="5c20b-115">Weitere Informationen finden Sie unter [lokaler Typrückschluss](../../programming-guide/language-features/variables/local-type-inference.md).</span><span class="sxs-lookup"><span data-stu-id="5c20b-115">For more information, see [Local Type Inference](../../programming-guide/language-features/variables/local-type-inference.md).</span></span>  
  
- <span data-ttu-id="5c20b-116">**Kombinierte Modifizierer.**</span><span class="sxs-lookup"><span data-stu-id="5c20b-116">**Combined Modifiers.**</span></span> <span data-ttu-id="5c20b-117">Sie können nicht `Static` mit `ReadOnly` , `Shadows` oder `Shared` in derselben Deklaration angeben.</span><span class="sxs-lookup"><span data-stu-id="5c20b-117">You cannot specify `Static` together with `ReadOnly`, `Shadows`, or `Shared` in the same declaration.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="5c20b-118">Verhalten</span><span class="sxs-lookup"><span data-stu-id="5c20b-118">Behavior</span></span>  

 <span data-ttu-id="5c20b-119">Wenn Sie eine statische Variable in einer Prozedur deklarieren `Shared` , ist nur eine Kopie der statischen Variablen für die gesamte Anwendung verfügbar.</span><span class="sxs-lookup"><span data-stu-id="5c20b-119">When you declare a static variable in a `Shared` procedure, only one copy of the static variable is available for the whole application.</span></span> <span data-ttu-id="5c20b-120">Sie können eine `Shared` Prozedur mit dem Klassennamen, nicht mit einer Variablen, die auf eine Instanz der-Klasse verweist, abrufen.</span><span class="sxs-lookup"><span data-stu-id="5c20b-120">You call a `Shared` procedure by using the class name, not a variable that points to an instance of the class.</span></span>  
  
 <span data-ttu-id="5c20b-121">Wenn Sie in einer Prozedur, die nicht ist, eine statische Variable deklarieren `Shared` , ist nur eine Kopie der Variablen für jede Instanz der Klasse verfügbar.</span><span class="sxs-lookup"><span data-stu-id="5c20b-121">When you declare a static variable in a procedure that isn't `Shared`, only one copy of the variable is available for each instance of the class.</span></span> <span data-ttu-id="5c20b-122">Sie können eine nicht freigegebene Prozedur mit einer Variablen aufzurufen, die auf eine bestimmte Instanz der-Klasse verweist.</span><span class="sxs-lookup"><span data-stu-id="5c20b-122">You call a non-shared procedure by using a variable that points to a specific instance of the class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5c20b-123">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5c20b-123">Example</span></span>  

 <span data-ttu-id="5c20b-124">Das folgende Beispiel veranschaulicht die Verwendung von `Static`.</span><span class="sxs-lookup"><span data-stu-id="5c20b-124">The following example demonstrates the use of `Static`.</span></span>  
  
 [!code-vb[VbVbalrKeywords#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#5)]  
  
 <span data-ttu-id="5c20b-125">Die `Static` Variable `totalSales` wird nur einmal auf 0 initialisiert.</span><span class="sxs-lookup"><span data-stu-id="5c20b-125">The `Static` variable `totalSales` is initialized to 0 only one time.</span></span> <span data-ttu-id="5c20b-126">Jedes Mal, wenn Sie eingeben `updateSales` , `totalSales` hat immer noch den neuesten Wert, den Sie für ihn berechnet haben.</span><span class="sxs-lookup"><span data-stu-id="5c20b-126">Each time that you enter `updateSales`, `totalSales` still has the most recent value that you calculated for it.</span></span>  
  
 <span data-ttu-id="5c20b-127">Der- `Static` Modifizierer kann in diesem Kontext verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="5c20b-127">The `Static` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="5c20b-128">Dim-Anweisung</span><span class="sxs-lookup"><span data-stu-id="5c20b-128">Dim Statement</span></span>](../statements/dim-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="5c20b-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5c20b-129">See also</span></span>

- [<span data-ttu-id="5c20b-130">Shadows</span><span class="sxs-lookup"><span data-stu-id="5c20b-130">Shadows</span></span>](shadows.md)
- [<span data-ttu-id="5c20b-131">Freigegeben</span><span class="sxs-lookup"><span data-stu-id="5c20b-131">Shared</span></span>](shared.md)
- [<span data-ttu-id="5c20b-132">Lebensdauer in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5c20b-132">Lifetime in Visual Basic</span></span>](../../programming-guide/language-features/declared-elements/lifetime.md)
- [<span data-ttu-id="5c20b-133">Variablen Deklaration</span><span class="sxs-lookup"><span data-stu-id="5c20b-133">Variable Declaration</span></span>](../../programming-guide/language-features/variables/variable-declaration.md)
- [<span data-ttu-id="5c20b-134">Strukturen</span><span class="sxs-lookup"><span data-stu-id="5c20b-134">Structures</span></span>](../../programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="5c20b-135">Lokaler Typrückschluss</span><span class="sxs-lookup"><span data-stu-id="5c20b-135">Local Type Inference</span></span>](../../programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="5c20b-136">Objekte und Klassen</span><span class="sxs-lookup"><span data-stu-id="5c20b-136">Objects and Classes</span></span>](../../programming-guide/language-features/objects-and-classes/index.md)
