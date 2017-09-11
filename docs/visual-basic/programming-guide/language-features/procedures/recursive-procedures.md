---
title: Rekursive Prozeduren (Visual Basic) | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- Visual Basic code, procedures
- procedures, that call themselves
- procedures, recursive
- procedures, calling
- recursive procedures
- functions [Visual Basic], calling recursively
- recursion
ms.assetid: ba1d3962-b4c3-48d3-875e-96fdb4198327
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 5e4838bb14125dcfd27798acf0c196f351ba5b90
ms.contentlocale: de-de
ms.lasthandoff: 05/19/2017

---
# <a name="recursive-procedures-visual-basic"></a><span data-ttu-id="fe5c1-102">Rekursive Prozeduren (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fe5c1-102">Recursive Procedures (Visual Basic)</span></span>
<span data-ttu-id="fe5c1-103">Ein *rekursive* Prozedur ist eine, die sich selbst aufruft.</span><span class="sxs-lookup"><span data-stu-id="fe5c1-103">A *recursive* procedure is one that calls itself.</span></span> <span data-ttu-id="fe5c1-104">Im Allgemeinen, dies ist nicht die effizienteste Methode zum Schreiben [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Code.</span><span class="sxs-lookup"><span data-stu-id="fe5c1-104">In general, this is not the most effective way to write [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] code.</span></span>  
  
 <span data-ttu-id="fe5c1-105">Die folgende Prozedur verwendet die Rekursion berechnet die Fakultät ihres ursprünglichen Arguments.</span><span class="sxs-lookup"><span data-stu-id="fe5c1-105">The following procedure uses recursion to calculate the factorial of its original argument.</span></span>  
  
 <span data-ttu-id="fe5c1-106">[!code-vb[VbVbcnProcedures&51;](./codesnippet/VisualBasic/recursive-procedures_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="fe5c1-106">[!code-vb[VbVbcnProcedures#51](./codesnippet/VisualBasic/recursive-procedures_1.vb)]</span></span>  
  
## <a name="considerations-with-recursive-procedures"></a><span data-ttu-id="fe5c1-107">Zu rekursive Prozeduren</span><span class="sxs-lookup"><span data-stu-id="fe5c1-107">Considerations with Recursive Procedures</span></span>  
 <span data-ttu-id="fe5c1-108">**Beschränkenden Bedingungen**.</span><span class="sxs-lookup"><span data-stu-id="fe5c1-108">**Limiting Conditions**.</span></span> <span data-ttu-id="fe5c1-109">Sie müssen eine rekursive Prozedur für mindestens eine Bedingung zu testen, die die Rekursion beendet entwerfen, und Sie müssen auch den Fall, in dem keine solchen Bedingung, innerhalb einer angemessenen Anzahl von rekursiven Aufrufen erfüllt ist, behandeln.</span><span class="sxs-lookup"><span data-stu-id="fe5c1-109">You must design a recursive procedure to test for at least one condition that can terminate the recursion, and you must also handle the case where no such condition is satisfied within a reasonable number of recursive calls.</span></span> <span data-ttu-id="fe5c1-110">Ohne mindestens eine Bedingung, die fehlerfrei erfüllt werden kann, wird die Prozedur ein erhöhtes Risiko für die Ausführung in einer Endlosschleife ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="fe5c1-110">Without at least one condition that can be met without fail, your procedure runs a high risk of executing in an infinite loop.</span></span>  
  
 <span data-ttu-id="fe5c1-111">**Speicherverwendung**.</span><span class="sxs-lookup"><span data-stu-id="fe5c1-111">**Memory Usage**.</span></span> <span data-ttu-id="fe5c1-112">Ihre Anwendung hat eine begrenzte Menge an Speicherplatz für lokale Variablen.</span><span class="sxs-lookup"><span data-stu-id="fe5c1-112">Your application has a limited amount of space for local variables.</span></span> <span data-ttu-id="fe5c1-113">Jedes Mal eine Prozedur aufruft, wird weiterer Speicherplatz für zusätzliche Kopien ihrer lokalen Variablen.</span><span class="sxs-lookup"><span data-stu-id="fe5c1-113">Each time a procedure calls itself, it uses more of that space for additional copies of its local variables.</span></span> <span data-ttu-id="fe5c1-114">Wenn dieser Vorgang unendlich lange fortsetzt, wird letztendlich eine <xref:System.StackOverflowException>Fehler.</xref:System.StackOverflowException></span><span class="sxs-lookup"><span data-stu-id="fe5c1-114">If this process continues indefinitely, it eventually causes a <xref:System.StackOverflowException> error.</span></span>  
  
 <span data-ttu-id="fe5c1-115">**Effizienz**.</span><span class="sxs-lookup"><span data-stu-id="fe5c1-115">**Efficiency**.</span></span> <span data-ttu-id="fe5c1-116">Sie können fast immer eine Schleife für die Rekursion ersetzen.</span><span class="sxs-lookup"><span data-stu-id="fe5c1-116">You can almost always substitute a loop for recursion.</span></span> <span data-ttu-id="fe5c1-117">Eine Schleife muss nicht den Aufwand für das Übergeben von Argumenten, Initialisieren von zusätzlichem Speicher und das Zurückgeben von Werten.</span><span class="sxs-lookup"><span data-stu-id="fe5c1-117">A loop does not have the overhead of passing arguments, initializing additional storage, and returning values.</span></span> <span data-ttu-id="fe5c1-118">Die Leistung kann ohne rekursive Aufrufe viel besser sein.</span><span class="sxs-lookup"><span data-stu-id="fe5c1-118">Your performance can be much better without recursive calls.</span></span>  
  
 <span data-ttu-id="fe5c1-119">**Gegenseitige Rekursion**.</span><span class="sxs-lookup"><span data-stu-id="fe5c1-119">**Mutual Recursion**.</span></span> <span data-ttu-id="fe5c1-120">Sie können eine sehr schlechte Leistung oder sogar eine Endlosschleife, beobachten, wenn zwei Prozeduren einander aufrufen.</span><span class="sxs-lookup"><span data-stu-id="fe5c1-120">You might observe very poor performance, or even an infinite loop, if two procedures call each other.</span></span> <span data-ttu-id="fe5c1-121">Ein solcher Entwurf stellt die gleichen Probleme wie eine einzelne rekursive Prozedur, aber möglicherweise schwerer zu erkennen und zu debuggen.</span><span class="sxs-lookup"><span data-stu-id="fe5c1-121">Such a design presents the same problems as a single recursive procedure, but can be harder to detect and debug.</span></span>  
  
 <span data-ttu-id="fe5c1-122">**Aufrufe mit Klammern**.</span><span class="sxs-lookup"><span data-stu-id="fe5c1-122">**Calling with Parentheses**.</span></span> <span data-ttu-id="fe5c1-123">Wenn ein `Function` Prozedur ruft sich selbst rekursiv, Sie müssen den Namen der Prozedur mit Klammern folgen, selbst wenn keine Argumentliste vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="fe5c1-123">When a `Function` procedure calls itself recursively, you must follow the procedure name with parentheses, even if there is no argument list.</span></span> <span data-ttu-id="fe5c1-124">Andernfalls stammt der Funktionsname als Rückgabewert der Funktion.</span><span class="sxs-lookup"><span data-stu-id="fe5c1-124">Otherwise, the function name is taken as representing the return value of the function.</span></span>  
  
 <span data-ttu-id="fe5c1-125">**Testen von**.</span><span class="sxs-lookup"><span data-stu-id="fe5c1-125">**Testing**.</span></span> <span data-ttu-id="fe5c1-126">Wenn Sie eine rekursive Prozedur schreiben, sollten Sie es sehr sorgfältig testen, um sicherzustellen, dass es immer eine einschränkende Bedingung erfüllt.</span><span class="sxs-lookup"><span data-stu-id="fe5c1-126">If you write a recursive procedure, you should test it very carefully to make sure it always meets some limiting condition.</span></span> <span data-ttu-id="fe5c1-127">Sie sollten auch sicherstellen, dass nicht genügend Arbeitsspeicher nicht durch zu viele rekursive Aufrufe ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="fe5c1-127">You should also ensure that you cannot run out of memory due to having too many recursive calls.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe5c1-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fe5c1-128">See Also</span></span>  
 <span data-ttu-id="fe5c1-129"><xref:System.StackOverflowException></xref:System.StackOverflowException></span><span class="sxs-lookup"><span data-stu-id="fe5c1-129"><xref:System.StackOverflowException></span></span>   
<span data-ttu-id="fe5c1-130"> [Verfahren](./index.md) </span><span class="sxs-lookup"><span data-stu-id="fe5c1-130"> [Procedures](./index.md) </span></span>  
<span data-ttu-id="fe5c1-131"> [Sub-Prozeduren](./sub-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="fe5c1-131"> [Sub Procedures](./sub-procedures.md) </span></span>  
<span data-ttu-id="fe5c1-132"> [Function-Prozeduren](./function-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="fe5c1-132"> [Function Procedures](./function-procedures.md) </span></span>  
<span data-ttu-id="fe5c1-133"> [Property-Prozeduren](./property-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="fe5c1-133"> [Property Procedures](./property-procedures.md) </span></span>  
<span data-ttu-id="fe5c1-134"> [Operatorprozeduren](./operator-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="fe5c1-134"> [Operator Procedures](./operator-procedures.md) </span></span>  
<span data-ttu-id="fe5c1-135"> [Prozedurparameter und Argumente](./procedure-parameters-and-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="fe5c1-135"> [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md) </span></span>  
<span data-ttu-id="fe5c1-136"> [Prozedurüberladung](./procedure-overloading.md) </span><span class="sxs-lookup"><span data-stu-id="fe5c1-136"> [Procedure Overloading](./procedure-overloading.md) </span></span>  
<span data-ttu-id="fe5c1-137"> [Problembehandlung bei Prozeduren](./troubleshooting-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="fe5c1-137"> [Troubleshooting Procedures](./troubleshooting-procedures.md) </span></span>  
<span data-ttu-id="fe5c1-138"> [Schleifenstruktur](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md) </span><span class="sxs-lookup"><span data-stu-id="fe5c1-138"> [Loop Structures](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md) </span></span>  
<span data-ttu-id="fe5c1-139"> [Problembehandlung bei Ausnahmen: System.StackOverflowException](http://msdn.microsoft.com/library/51b71217-c507-4f5b-bc35-0236180d7968)</span><span class="sxs-lookup"><span data-stu-id="fe5c1-139"> [Troubleshooting Exceptions: System.StackOverflowException](http://msdn.microsoft.com/library/51b71217-c507-4f5b-bc35-0236180d7968)</span></span>
