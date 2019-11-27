---
title: Rekursive Prozeduren
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
ms.openlocfilehash: 646d4e29ed7a0b6367d4b35a7f8641bcf659e616
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352556"
---
# <a name="recursive-procedures-visual-basic"></a><span data-ttu-id="421f3-102">Rekursive Prozeduren (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="421f3-102">Recursive Procedures (Visual Basic)</span></span>

<span data-ttu-id="421f3-103">Eine *rekursive* Prozedur ist eine, die sich selbst aufruft.</span><span class="sxs-lookup"><span data-stu-id="421f3-103">A *recursive* procedure is one that calls itself.</span></span> <span data-ttu-id="421f3-104">Im Allgemeinen ist dies nicht die effektivste Methode, Visual Basic Code zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="421f3-104">In general, this is not the most effective way to write Visual Basic code.</span></span>  
  
 <span data-ttu-id="421f3-105">Im folgenden Verfahren wird Rekursion verwendet, um die Fakultät des ursprünglichen Arguments zu berechnen.</span><span class="sxs-lookup"><span data-stu-id="421f3-105">The following procedure uses recursion to calculate the factorial of its original argument.</span></span>  
  
 [!code-vb[VbVbcnProcedures#51](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#51)]  
  
## <a name="considerations-with-recursive-procedures"></a><span data-ttu-id="421f3-106">Überlegungen zu rekursiven Verfahren</span><span class="sxs-lookup"><span data-stu-id="421f3-106">Considerations with Recursive Procedures</span></span>

 <span data-ttu-id="421f3-107">**Einschränkende Bedingungen**.</span><span class="sxs-lookup"><span data-stu-id="421f3-107">**Limiting Conditions**.</span></span> <span data-ttu-id="421f3-108">Sie müssen eine rekursive Prozedur entwerfen, um mindestens eine Bedingung zu testen, die die Rekursion beenden kann. Außerdem müssen Sie den Fall behandeln, in dem eine solche Bedingung innerhalb einer angemessenen Anzahl von rekursiven Aufrufen nicht erfüllt wird.</span><span class="sxs-lookup"><span data-stu-id="421f3-108">You must design a recursive procedure to test for at least one condition that can terminate the recursion, and you must also handle the case where no such condition is satisfied within a reasonable number of recursive calls.</span></span> <span data-ttu-id="421f3-109">Wenn mindestens eine Bedingung nicht erfüllt werden kann, ohne dass ein Fehler auftritt, führt Ihre Prozedur ein hohes Risiko für die Ausführung in einer Endlosschleife aus.</span><span class="sxs-lookup"><span data-stu-id="421f3-109">Without at least one condition that can be met without fail, your procedure runs a high risk of executing in an infinite loop.</span></span>

 <span data-ttu-id="421f3-110">**Speichernutzung**.</span><span class="sxs-lookup"><span data-stu-id="421f3-110">**Memory Usage**.</span></span> <span data-ttu-id="421f3-111">Die Anwendung verfügt über einen begrenzten Speicherplatz für lokale Variablen.</span><span class="sxs-lookup"><span data-stu-id="421f3-111">Your application has a limited amount of space for local variables.</span></span> <span data-ttu-id="421f3-112">Jedes Mal, wenn eine Prozedur sich selbst aufruft, verwendet Sie mehr von diesem Bereich für zusätzliche Kopien Ihrer lokalen Variablen.</span><span class="sxs-lookup"><span data-stu-id="421f3-112">Each time a procedure calls itself, it uses more of that space for additional copies of its local variables.</span></span> <span data-ttu-id="421f3-113">Wenn dieser Prozess unbegrenzt fortgesetzt wird, verursacht er letztendlich einen <xref:System.StackOverflowException> Fehler.</span><span class="sxs-lookup"><span data-stu-id="421f3-113">If this process continues indefinitely, it eventually causes a <xref:System.StackOverflowException> error.</span></span>

 <span data-ttu-id="421f3-114">**Effizienz**:</span><span class="sxs-lookup"><span data-stu-id="421f3-114">**Efficiency**.</span></span> <span data-ttu-id="421f3-115">Sie können eine Schleife fast immer für Rekursion ersetzen.</span><span class="sxs-lookup"><span data-stu-id="421f3-115">You can almost always substitute a loop for recursion.</span></span> <span data-ttu-id="421f3-116">Eine-Schleife hat nicht den mehr Aufwand, um Argumente zu übergeben, zusätzlichen Speicher zu initialisieren und Werte zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="421f3-116">A loop does not have the overhead of passing arguments, initializing additional storage, and returning values.</span></span> <span data-ttu-id="421f3-117">Die Leistung kann sich ohne rekursive Aufrufe erheblich verbessern.</span><span class="sxs-lookup"><span data-stu-id="421f3-117">Your performance can be much better without recursive calls.</span></span>

 <span data-ttu-id="421f3-118">**Gegenseitige Rekursion**.</span><span class="sxs-lookup"><span data-stu-id="421f3-118">**Mutual Recursion**.</span></span> <span data-ttu-id="421f3-119">Sie können eine sehr schlechte Leistung oder sogar eine Endlosschleife beobachten, wenn zwei Prozeduren einander aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="421f3-119">You might observe very poor performance, or even an infinite loop, if two procedures call each other.</span></span> <span data-ttu-id="421f3-120">Ein solcher Entwurf zeigt dieselben Probleme wie eine einzelne rekursive Prozedur, kann jedoch schwieriger zu erkennen und zu debuggen sein.</span><span class="sxs-lookup"><span data-stu-id="421f3-120">Such a design presents the same problems as a single recursive procedure, but can be harder to detect and debug.</span></span>

 <span data-ttu-id="421f3-121">**Aufrufen von mit Klammern**.</span><span class="sxs-lookup"><span data-stu-id="421f3-121">**Calling with Parentheses**.</span></span> <span data-ttu-id="421f3-122">Wenn eine `Function` Prozedur sich selbst rekursiv aufruft, müssen Sie den Namen der Prozedur mit Klammern befolgen, auch wenn keine Argumentliste vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="421f3-122">When a `Function` procedure calls itself recursively, you must follow the procedure name with parentheses, even if there is no argument list.</span></span> <span data-ttu-id="421f3-123">Andernfalls wird der Funktionsname als Darstellung des Rückgabewerts der Funktion verwendet.</span><span class="sxs-lookup"><span data-stu-id="421f3-123">Otherwise, the function name is taken as representing the return value of the function.</span></span>

 <span data-ttu-id="421f3-124">**Testen**.</span><span class="sxs-lookup"><span data-stu-id="421f3-124">**Testing**.</span></span> <span data-ttu-id="421f3-125">Wenn Sie eine rekursive Prozedur schreiben, sollten Sie Sie sehr sorgfältig testen, um sicherzustellen, dass Sie immer eine einschränkende Bedingung erfüllt.</span><span class="sxs-lookup"><span data-stu-id="421f3-125">If you write a recursive procedure, you should test it very carefully to make sure it always meets some limiting condition.</span></span> <span data-ttu-id="421f3-126">Sie sollten auch sicherstellen, dass nicht genügend Arbeitsspeicher verfügbar ist, weil zu viele rekursive Aufrufe vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="421f3-126">You should also ensure that you cannot run out of memory due to having too many recursive calls.</span></span>

## <a name="see-also"></a><span data-ttu-id="421f3-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="421f3-127">See also</span></span>

- <xref:System.StackOverflowException>
- [<span data-ttu-id="421f3-128">Verfahren</span><span class="sxs-lookup"><span data-stu-id="421f3-128">Procedures</span></span>](index.md)
- [<span data-ttu-id="421f3-129">Sub-Prozeduren</span><span class="sxs-lookup"><span data-stu-id="421f3-129">Sub Procedures</span></span>](sub-procedures.md)
- [<span data-ttu-id="421f3-130">Function-Prozeduren</span><span class="sxs-lookup"><span data-stu-id="421f3-130">Function Procedures</span></span>](function-procedures.md)
- [<span data-ttu-id="421f3-131">Eigenschaftenprozeduren</span><span class="sxs-lookup"><span data-stu-id="421f3-131">Property Procedures</span></span>](property-procedures.md)
- [<span data-ttu-id="421f3-132">Operatorprozeduren</span><span class="sxs-lookup"><span data-stu-id="421f3-132">Operator Procedures</span></span>](operator-procedures.md)
- [<span data-ttu-id="421f3-133">Parameter und Argumente von Prozeduren</span><span class="sxs-lookup"><span data-stu-id="421f3-133">Procedure Parameters and Arguments</span></span>](procedure-parameters-and-arguments.md)
- [<span data-ttu-id="421f3-134">Prozedurüberladung</span><span class="sxs-lookup"><span data-stu-id="421f3-134">Procedure Overloading</span></span>](procedure-overloading.md)
- [<span data-ttu-id="421f3-135">Problembehandlung bei Prozeduren</span><span class="sxs-lookup"><span data-stu-id="421f3-135">Troubleshooting Procedures</span></span>](troubleshooting-procedures.md)
- [<span data-ttu-id="421f3-136">Schleifenstruktur</span><span class="sxs-lookup"><span data-stu-id="421f3-136">Loop Structures</span></span>](../control-flow/loop-structures.md)
