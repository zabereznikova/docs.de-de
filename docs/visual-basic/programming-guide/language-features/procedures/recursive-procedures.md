---
title: Rekursive Prozeduren (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Visual Basic code, procedures
- procedures [Visual Basic], that call themselves
- procedures [Visual Basic], recursive
- procedures [Visual Basic], calling
- recursive procedures
- functions [Visual Basic], calling recursively
- recursion
ms.assetid: ba1d3962-b4c3-48d3-875e-96fdb4198327
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 471746f4412b61c9782e8019aa8a9ec6221afb04
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="recursive-procedures-visual-basic"></a><span data-ttu-id="be349-102">Rekursive Prozeduren (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="be349-102">Recursive Procedures (Visual Basic)</span></span>
<span data-ttu-id="be349-103">Ein *rekursive* Prozedur ist eine, die sich selbst aufruft.</span><span class="sxs-lookup"><span data-stu-id="be349-103">A *recursive* procedure is one that calls itself.</span></span> <span data-ttu-id="be349-104">Im Allgemeinen ist dies nicht die effizienteste Methode, Visual Basic-Code zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="be349-104">In general, this is not the most effective way to write Visual Basic code.</span></span>  
  
 <span data-ttu-id="be349-105">Im folgenden Verfahren wird die Rekursion berechnet die Fakultät des ursprünglichen Arguments.</span><span class="sxs-lookup"><span data-stu-id="be349-105">The following procedure uses recursion to calculate the factorial of its original argument.</span></span>  
  
 [!code-vb[VbVbcnProcedures#51](./codesnippet/VisualBasic/recursive-procedures_1.vb)]  
  
## <a name="considerations-with-recursive-procedures"></a><span data-ttu-id="be349-106">Überlegungen zu mit rekursive Prozeduren</span><span class="sxs-lookup"><span data-stu-id="be349-106">Considerations with Recursive Procedures</span></span>  
 <span data-ttu-id="be349-107">**Beschränkenden Bedingungen**.</span><span class="sxs-lookup"><span data-stu-id="be349-107">**Limiting Conditions**.</span></span> <span data-ttu-id="be349-108">Sie müssen eine rekursive Prozedur für mindestens eine Bedingung zu testen, die die Rekursion beendet entwerfen, und müssen Sie auch die Groß-/Kleinschreibung, in denen keine solche Bedingung, in eine angemessene Anzahl von rekursiven Aufrufen erfüllt ist, behandeln.</span><span class="sxs-lookup"><span data-stu-id="be349-108">You must design a recursive procedure to test for at least one condition that can terminate the recursion, and you must also handle the case where no such condition is satisfied within a reasonable number of recursive calls.</span></span> <span data-ttu-id="be349-109">Ohne mindestens eine Bedingung, die ohne Fehler erfüllt werden kann, wird die Prozedur ein erhöhtes Risiko der Ausführung in einer Endlosschleife ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="be349-109">Without at least one condition that can be met without fail, your procedure runs a high risk of executing in an infinite loop.</span></span>  
  
 <span data-ttu-id="be349-110">**Speichernutzung**.</span><span class="sxs-lookup"><span data-stu-id="be349-110">**Memory Usage**.</span></span> <span data-ttu-id="be349-111">Die Anwendung verfügt über eine begrenzte Menge an Speicherplatz für lokale Variablen.</span><span class="sxs-lookup"><span data-stu-id="be349-111">Your application has a limited amount of space for local variables.</span></span> <span data-ttu-id="be349-112">Jedes Mal eine Prozedur aufruft, verwendet es weiterer Speicherplatz für zusätzliche Kopien ihrer lokalen Variablen.</span><span class="sxs-lookup"><span data-stu-id="be349-112">Each time a procedure calls itself, it uses more of that space for additional copies of its local variables.</span></span> <span data-ttu-id="be349-113">Wenn dieser Prozess unbestimmte Zeit weiterhin besteht, wird letztendlich eine <xref:System.StackOverflowException> Fehler.</span><span class="sxs-lookup"><span data-stu-id="be349-113">If this process continues indefinitely, it eventually causes a <xref:System.StackOverflowException> error.</span></span>  
  
 <span data-ttu-id="be349-114">**Effizienz**.</span><span class="sxs-lookup"><span data-stu-id="be349-114">**Efficiency**.</span></span> <span data-ttu-id="be349-115">Sie können fast immer eine Schleife für die Rekursion ersetzen.</span><span class="sxs-lookup"><span data-stu-id="be349-115">You can almost always substitute a loop for recursion.</span></span> <span data-ttu-id="be349-116">Eine Schleife muss sich nicht auf den Aufwand für das Übergeben von Argumenten, Initialisieren von zusätzlichem Speicher und Zurückgeben von Werten aus.</span><span class="sxs-lookup"><span data-stu-id="be349-116">A loop does not have the overhead of passing arguments, initializing additional storage, and returning values.</span></span> <span data-ttu-id="be349-117">Die Leistung kann sich wesentlich besser ohne rekursive Aufrufe sein.</span><span class="sxs-lookup"><span data-stu-id="be349-117">Your performance can be much better without recursive calls.</span></span>  
  
 <span data-ttu-id="be349-118">**Gegenseitige Rekursion**.</span><span class="sxs-lookup"><span data-stu-id="be349-118">**Mutual Recursion**.</span></span> <span data-ttu-id="be349-119">Sie können eine sehr schlechte Leistung oder sogar eine unendliche Schleife beobachten, ob zwei Prozeduren gegenseitig aufrufen.</span><span class="sxs-lookup"><span data-stu-id="be349-119">You might observe very poor performance, or even an infinite loop, if two procedures call each other.</span></span> <span data-ttu-id="be349-120">Ein solcher Entwurf bietet die gleichen Probleme als ein rekursives Prozedur, aber möglicherweise schwerer zu erkennen und zu debuggen.</span><span class="sxs-lookup"><span data-stu-id="be349-120">Such a design presents the same problems as a single recursive procedure, but can be harder to detect and debug.</span></span>  
  
 <span data-ttu-id="be349-121">**Aufrufen mit Klammern**.</span><span class="sxs-lookup"><span data-stu-id="be349-121">**Calling with Parentheses**.</span></span> <span data-ttu-id="be349-122">Wenn eine `Function` Prozedur ruft sich selbst rekursiv, Sie müssen den Prozedurnamen mit Klammern folgen, auch wenn es keine Argumentliste enthalten.</span><span class="sxs-lookup"><span data-stu-id="be349-122">When a `Function` procedure calls itself recursively, you must follow the procedure name with parentheses, even if there is no argument list.</span></span> <span data-ttu-id="be349-123">Der Funktionsname stammt, andernfalls als, das den Rückgabewert der Funktion darstellt.</span><span class="sxs-lookup"><span data-stu-id="be349-123">Otherwise, the function name is taken as representing the return value of the function.</span></span>  
  
 <span data-ttu-id="be349-124">**Testen von**.</span><span class="sxs-lookup"><span data-stu-id="be349-124">**Testing**.</span></span> <span data-ttu-id="be349-125">Wenn Sie eine rekursive Prozedur schreiben, sollten Sie es sehr sorgfältig testen, um sicherzustellen, dass es immer eine einschränkende Bedingung erfüllt.</span><span class="sxs-lookup"><span data-stu-id="be349-125">If you write a recursive procedure, you should test it very carefully to make sure it always meets some limiting condition.</span></span> <span data-ttu-id="be349-126">Sie sollten auch sicherstellen, dass nicht genügend Arbeitsspeicher aufgrund von zu viele rekursive Aufrufe ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="be349-126">You should also ensure that you cannot run out of memory due to having too many recursive calls.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be349-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="be349-127">See Also</span></span>  
 <xref:System.StackOverflowException>  
 [<span data-ttu-id="be349-128">Verfahren</span><span class="sxs-lookup"><span data-stu-id="be349-128">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="be349-129">Sub-Prozeduren</span><span class="sxs-lookup"><span data-stu-id="be349-129">Sub Procedures</span></span>](./sub-procedures.md)  
 [<span data-ttu-id="be349-130">Function-Prozeduren</span><span class="sxs-lookup"><span data-stu-id="be349-130">Function Procedures</span></span>](./function-procedures.md)  
 [<span data-ttu-id="be349-131">Eigenschaftenprozeduren</span><span class="sxs-lookup"><span data-stu-id="be349-131">Property Procedures</span></span>](./property-procedures.md)  
 [<span data-ttu-id="be349-132">Operatorprozeduren</span><span class="sxs-lookup"><span data-stu-id="be349-132">Operator Procedures</span></span>](./operator-procedures.md)  
 [<span data-ttu-id="be349-133">Parameter und Argumente von Prozeduren</span><span class="sxs-lookup"><span data-stu-id="be349-133">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="be349-134">Prozedurüberladung</span><span class="sxs-lookup"><span data-stu-id="be349-134">Procedure Overloading</span></span>](./procedure-overloading.md)  
 [<span data-ttu-id="be349-135">Problembehandlung bei Prozeduren</span><span class="sxs-lookup"><span data-stu-id="be349-135">Troubleshooting Procedures</span></span>](./troubleshooting-procedures.md)  
 [<span data-ttu-id="be349-136">Schleifenstruktur</span><span class="sxs-lookup"><span data-stu-id="be349-136">Loop Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)  
 [<span data-ttu-id="be349-137">Problembehandlung bei Ausnahmen: System.StackOverflowException</span><span class="sxs-lookup"><span data-stu-id="be349-137">Troubleshooting Exceptions: System.StackOverflowException</span></span>](http://msdn.microsoft.com/library/51b71217-c507-4f5b-bc35-0236180d7968)
