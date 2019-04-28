---
title: Rekursive Prozeduren (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- procedures [Visual Basic], that call themselves
- procedures [Visual Basic], recursive
- procedures [Visual Basic], calling
- recursive procedures
- functions [Visual Basic], calling recursively
- recursion
ms.assetid: ba1d3962-b4c3-48d3-875e-96fdb4198327
ms.openlocfilehash: de9a2af9fc3cd78879b6525245727a6f52d51c63
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61791845"
---
# <a name="recursive-procedures-visual-basic"></a><span data-ttu-id="cb47a-102">Rekursive Prozeduren (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cb47a-102">Recursive Procedures (Visual Basic)</span></span>
<span data-ttu-id="cb47a-103">Ein *rekursive* Verfahren ist ein, der sich selbst aufruft.</span><span class="sxs-lookup"><span data-stu-id="cb47a-103">A *recursive* procedure is one that calls itself.</span></span> <span data-ttu-id="cb47a-104">Im Allgemeinen ist dies nicht die effektivste Möglichkeit, Visual Basic-Code zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="cb47a-104">In general, this is not the most effective way to write Visual Basic code.</span></span>  
  
 <span data-ttu-id="cb47a-105">Das folgende Verfahren verwendet die Rekursion berechnet die Fakultät des ursprünglichen Arguments.</span><span class="sxs-lookup"><span data-stu-id="cb47a-105">The following procedure uses recursion to calculate the factorial of its original argument.</span></span>  
  
 [!code-vb[VbVbcnProcedures#51](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#51)]  
  
## <a name="considerations-with-recursive-procedures"></a><span data-ttu-id="cb47a-106">Überlegungen zu mit rekursive Prozeduren</span><span class="sxs-lookup"><span data-stu-id="cb47a-106">Considerations with Recursive Procedures</span></span>  
 <span data-ttu-id="cb47a-107">**Beschränkenden Bedingungen**.</span><span class="sxs-lookup"><span data-stu-id="cb47a-107">**Limiting Conditions**.</span></span> <span data-ttu-id="cb47a-108">Müssen Sie eine rekursive Prozedur zum Prüfen auf mindestens eine Bedingung, die die Rekursion beendet werden kann, entwerfen, und Sie müssen auch die Groß-/Kleinschreibung, keine solche Bedingung, in eine angemessene Anzahl von rekursiven Aufrufe erfüllt ist, behandeln.</span><span class="sxs-lookup"><span data-stu-id="cb47a-108">You must design a recursive procedure to test for at least one condition that can terminate the recursion, and you must also handle the case where no such condition is satisfied within a reasonable number of recursive calls.</span></span> <span data-ttu-id="cb47a-109">Ohne mindestens eine Bedingung, die ohne Fehler erfüllt werden können, führt Ihre Prozedur ein erhöhtes Risiko für die Ausführung in eine Endlosschleife.</span><span class="sxs-lookup"><span data-stu-id="cb47a-109">Without at least one condition that can be met without fail, your procedure runs a high risk of executing in an infinite loop.</span></span>  
  
 <span data-ttu-id="cb47a-110">**Speichernutzung**.</span><span class="sxs-lookup"><span data-stu-id="cb47a-110">**Memory Usage**.</span></span> <span data-ttu-id="cb47a-111">Ihre Anwendung verfügt über eine begrenzte Menge an Speicherplatz für lokale Variablen.</span><span class="sxs-lookup"><span data-stu-id="cb47a-111">Your application has a limited amount of space for local variables.</span></span> <span data-ttu-id="cb47a-112">Jedes Mal eine Prozedur sich selbst aufruft wird weiterer Speicherplatz für zusätzliche Kopien der zugehörigen lokalen Variablen.</span><span class="sxs-lookup"><span data-stu-id="cb47a-112">Each time a procedure calls itself, it uses more of that space for additional copies of its local variables.</span></span> <span data-ttu-id="cb47a-113">Wenn dieser Prozess auf unbestimmte Zeit weiterhin besteht, wird letztendlich eine <xref:System.StackOverflowException> Fehler.</span><span class="sxs-lookup"><span data-stu-id="cb47a-113">If this process continues indefinitely, it eventually causes a <xref:System.StackOverflowException> error.</span></span>  
  
 <span data-ttu-id="cb47a-114">**Effizienz**.</span><span class="sxs-lookup"><span data-stu-id="cb47a-114">**Efficiency**.</span></span> <span data-ttu-id="cb47a-115">Sie können fast immer eine Schleife für die Rekursion ersetzen.</span><span class="sxs-lookup"><span data-stu-id="cb47a-115">You can almost always substitute a loop for recursion.</span></span> <span data-ttu-id="cb47a-116">Eine Schleife muss sich nicht auf den Aufwand für das Übergeben von Argumenten, initialisieren zusätzlichen Speicher und Zurückgeben von Werten aus.</span><span class="sxs-lookup"><span data-stu-id="cb47a-116">A loop does not have the overhead of passing arguments, initializing additional storage, and returning values.</span></span> <span data-ttu-id="cb47a-117">Die Leistung kann ohne rekursive Aufrufe viel besser sein.</span><span class="sxs-lookup"><span data-stu-id="cb47a-117">Your performance can be much better without recursive calls.</span></span>  
  
 <span data-ttu-id="cb47a-118">**Gegenseitige Rekursion**.</span><span class="sxs-lookup"><span data-stu-id="cb47a-118">**Mutual Recursion**.</span></span> <span data-ttu-id="cb47a-119">Sie können sehr schlechte Leistung oder sogar eine unendliche Schleife, beobachten, wenn zwei Prozeduren gegenseitig aufrufen.</span><span class="sxs-lookup"><span data-stu-id="cb47a-119">You might observe very poor performance, or even an infinite loop, if two procedures call each other.</span></span> <span data-ttu-id="cb47a-120">Ein solcher Entwurf stellt die gleichen Probleme wie eine einzelne rekursive Prozedur, aber Sie können nicht so leicht erkennen und zu debuggen.</span><span class="sxs-lookup"><span data-stu-id="cb47a-120">Such a design presents the same problems as a single recursive procedure, but can be harder to detect and debug.</span></span>  
  
 <span data-ttu-id="cb47a-121">**Aufrufen von in Klammern**.</span><span class="sxs-lookup"><span data-stu-id="cb47a-121">**Calling with Parentheses**.</span></span> <span data-ttu-id="cb47a-122">Wenn eine `Function` Prozedur rekursiv aufruft, müssen Sie den Namen der Prozedur mit Klammern, befolgen, auch wenn keine Argumentliste vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="cb47a-122">When a `Function` procedure calls itself recursively, you must follow the procedure name with parentheses, even if there is no argument list.</span></span> <span data-ttu-id="cb47a-123">Der Funktionsname stammt, andernfalls als, das den Rückgabewert der Funktion darstellt.</span><span class="sxs-lookup"><span data-stu-id="cb47a-123">Otherwise, the function name is taken as representing the return value of the function.</span></span>  
  
 <span data-ttu-id="cb47a-124">**Testen von**.</span><span class="sxs-lookup"><span data-stu-id="cb47a-124">**Testing**.</span></span> <span data-ttu-id="cb47a-125">Wenn Sie eine rekursive Prozedur schreiben, sollten Sie sie sorgfältig testen, um sicherzustellen, dass es immer eine einschränkende Bedingung erfüllt.</span><span class="sxs-lookup"><span data-stu-id="cb47a-125">If you write a recursive procedure, you should test it very carefully to make sure it always meets some limiting condition.</span></span> <span data-ttu-id="cb47a-126">Sie sollten auch sicherstellen, dass Sie nicht genügend Arbeitsspeicher aufgrund zu viele rekursive Aufrufe nicht ausführen können.</span><span class="sxs-lookup"><span data-stu-id="cb47a-126">You should also ensure that you cannot run out of memory due to having too many recursive calls.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb47a-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cb47a-127">See also</span></span>

- <xref:System.StackOverflowException>
- [<span data-ttu-id="cb47a-128">Verfahren</span><span class="sxs-lookup"><span data-stu-id="cb47a-128">Procedures</span></span>](./index.md)
- [<span data-ttu-id="cb47a-129">Sub-Prozeduren</span><span class="sxs-lookup"><span data-stu-id="cb47a-129">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="cb47a-130">Function-Prozeduren</span><span class="sxs-lookup"><span data-stu-id="cb47a-130">Function Procedures</span></span>](./function-procedures.md)
- [<span data-ttu-id="cb47a-131">Eigenschaftenprozeduren</span><span class="sxs-lookup"><span data-stu-id="cb47a-131">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="cb47a-132">Operatorprozeduren</span><span class="sxs-lookup"><span data-stu-id="cb47a-132">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="cb47a-133">Parameter und Argumente von Prozeduren</span><span class="sxs-lookup"><span data-stu-id="cb47a-133">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="cb47a-134">Prozedurüberladung</span><span class="sxs-lookup"><span data-stu-id="cb47a-134">Procedure Overloading</span></span>](./procedure-overloading.md)
- [<span data-ttu-id="cb47a-135">Problembehandlung bei Prozeduren</span><span class="sxs-lookup"><span data-stu-id="cb47a-135">Troubleshooting Procedures</span></span>](./troubleshooting-procedures.md)
- [<span data-ttu-id="cb47a-136">Schleifenstruktur</span><span class="sxs-lookup"><span data-stu-id="cb47a-136">Loop Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
