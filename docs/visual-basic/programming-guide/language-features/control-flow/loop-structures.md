---
title: Schleifenstruktur (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- control flow [Visual Basic], loops
- For keyword [Visual Basic], loop structures
- loops
- loop structures [Visual Basic]
- statements [Visual Basic], loop
- Do statement [Visual Basic], Do loops
- conditional statements [Visual Basic], loop structures
ms.assetid: ecacb09b-a4c9-42be-98b2-a15d368b5db8
caps.latest.revision: 18
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8c13f2cc6546a652f0967bd83369d8af5998f7e2
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="loop-structures-visual-basic"></a><span data-ttu-id="364fe-102">Schleifenstruktur (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="364fe-102">Loop Structures (Visual Basic)</span></span>
<span data-ttu-id="364fe-103">Visual Basic-Schleifenstruktur ermöglichen Ihnen, eine oder mehrere Codezeilen wiederholt auszuführen.</span><span class="sxs-lookup"><span data-stu-id="364fe-103">Visual Basic loop structures allow you to run one or more lines of code repetitively.</span></span> <span data-ttu-id="364fe-104">Sie können die Anweisungen in einer Schleifenstruktur wiederholen, bis eine Bedingung ist `True`, bis eine Bedingung ist `False`, eine angegebene Anzahl, wie oft oder einmal für jedes Element in einer Auflistung.</span><span class="sxs-lookup"><span data-stu-id="364fe-104">You can repeat the statements in a loop structure until a condition is `True`, until a condition is `False`, a specified number of times, or once for each element in a collection.</span></span>  
  
 <span data-ttu-id="364fe-105">Die folgende Abbildung zeigt eine Schleifenstruktur, die eine Reihe von Anweisungen ausgeführt, bis eine Bedingung "true" ist.</span><span class="sxs-lookup"><span data-stu-id="364fe-105">The following illustration shows a loop structure that runs a set of statements until a condition becomes true.</span></span>  
  
 <span data-ttu-id="364fe-106">![Flussdiagramm des einem stimmen... Schleife](../../../../visual-basic/programming-guide/language-features/control-flow/media/dountilloop.gif "DoUntilLoop")</span><span class="sxs-lookup"><span data-stu-id="364fe-106">![Flow chart of a Do...Until loop](../../../../visual-basic/programming-guide/language-features/control-flow/media/dountilloop.gif "DoUntilLoop")</span></span>  
<span data-ttu-id="364fe-107">Eine Reihe von Anweisungen ausgeführt, bis eine Bedingung "true" ist.</span><span class="sxs-lookup"><span data-stu-id="364fe-107">Running a set of statements until a condition becomes true</span></span>  
  
## <a name="while-loops"></a><span data-ttu-id="364fe-108">While-Schleifen</span><span class="sxs-lookup"><span data-stu-id="364fe-108">While Loops</span></span>  
 <span data-ttu-id="364fe-109">Die `While`... `End While` Konstruktion führt eine Reihe von Anweisungen aus, solange die Bedingung angegeben werden, in der `While` -Anweisung ist `True`.</span><span class="sxs-lookup"><span data-stu-id="364fe-109">The `While`...`End While` construction runs a set of statements as long as the condition specified in the `While` statement is `True`.</span></span> <span data-ttu-id="364fe-110">Weitere Informationen finden Sie unter [während... While-Anweisung enden](../../../../visual-basic/language-reference/statements/while-end-while-statement.md).</span><span class="sxs-lookup"><span data-stu-id="364fe-110">For more information, see [While...End While Statement](../../../../visual-basic/language-reference/statements/while-end-while-statement.md).</span></span>  
  
## <a name="do-loops"></a><span data-ttu-id="364fe-111">Do-Schleifen</span><span class="sxs-lookup"><span data-stu-id="364fe-111">Do Loops</span></span>  
 <span data-ttu-id="364fe-112">Die `Do`... `Loop` Konstruktion können Sie eine Bedingung am Anfang oder Ende einer Schleifenstruktur zu testen.</span><span class="sxs-lookup"><span data-stu-id="364fe-112">The `Do`...`Loop` construction allows you to test a condition at either the beginning or the end of a loop structure.</span></span> <span data-ttu-id="364fe-113">Sie können auch angeben, ob die Schleife wiederholt wird, während die Bedingung bleibt `True` oder bis er wieder ist `True`.</span><span class="sxs-lookup"><span data-stu-id="364fe-113">You can also specify whether to repeat the loop while the condition remains `True` or until it becomes `True`.</span></span> <span data-ttu-id="364fe-114">Weitere Informationen finden Sie unter [werden... Loop-Anweisung](../../../../visual-basic/language-reference/statements/do-loop-statement.md).</span><span class="sxs-lookup"><span data-stu-id="364fe-114">For more information, see [Do...Loop Statement](../../../../visual-basic/language-reference/statements/do-loop-statement.md).</span></span>  
  
## <a name="for-loops"></a><span data-ttu-id="364fe-115">For-Schleifen</span><span class="sxs-lookup"><span data-stu-id="364fe-115">For Loops</span></span>  
 <span data-ttu-id="364fe-116">Die `For`... `Next` Konstruktion führt die Schleife eine festgelegte Anzahl von Zeiten.</span><span class="sxs-lookup"><span data-stu-id="364fe-116">The `For`...`Next` construction performs the loop a set number of times.</span></span> <span data-ttu-id="364fe-117">Er verwendet eine Loop-Steuerelementvariable, die so genannte eine *Leistungsindikator*, zum Nachverfolgen der Wiederholungen.</span><span class="sxs-lookup"><span data-stu-id="364fe-117">It uses a loop control variable, also called a *counter*, to keep track of the repetitions.</span></span> <span data-ttu-id="364fe-118">Sie geben die Start- und Endwerten für diesen Leistungsindikator, und Sie können optional angeben, die Menge von der aus eine Wiederholung zur nächsten erhöht gleichzeitig die.</span><span class="sxs-lookup"><span data-stu-id="364fe-118">You specify the starting and ending values for this counter, and you can optionally specify the amount by which it increases from one repetition to the next.</span></span> <span data-ttu-id="364fe-119">Weitere Informationen finden Sie unter [für... Nächste Anweisung](../../../../visual-basic/language-reference/statements/for-next-statement.md).</span><span class="sxs-lookup"><span data-stu-id="364fe-119">For more information, see [For...Next Statement](../../../../visual-basic/language-reference/statements/for-next-statement.md).</span></span>  
  
## <a name="for-each-loops"></a><span data-ttu-id="364fe-120">For Each-Schleife</span><span class="sxs-lookup"><span data-stu-id="364fe-120">For Each Loops</span></span>  
 <span data-ttu-id="364fe-121">Die `For Each`... `Next` Konstruktion wird eine Reihe von Anweisungen, die einmal für jedes Element in einer Auflistung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="364fe-121">The `For Each`...`Next` construction runs a set of statements once for each element in a collection.</span></span> <span data-ttu-id="364fe-122">Geben Sie die Loop-Steuerelementvariable, aber Sie müssen keine Anfangs- oder Endwert dafür bestimmen.</span><span class="sxs-lookup"><span data-stu-id="364fe-122">You specify the loop control variable, but you do not have to determine starting or ending values for it.</span></span> <span data-ttu-id="364fe-123">Weitere Informationen finden Sie unter [für jede... Nächste Anweisung](../../../../visual-basic/language-reference/statements/for-each-next-statement.md).</span><span class="sxs-lookup"><span data-stu-id="364fe-123">For more information, see [For Each...Next Statement](../../../../visual-basic/language-reference/statements/for-each-next-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="364fe-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="364fe-124">See Also</span></span>  
 [<span data-ttu-id="364fe-125">Ablaufsteuerung</span><span class="sxs-lookup"><span data-stu-id="364fe-125">Control Flow</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)  
 [<span data-ttu-id="364fe-126">Entscheidungsstrukturen</span><span class="sxs-lookup"><span data-stu-id="364fe-126">Decision Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)  
 [<span data-ttu-id="364fe-127">Weitere Steuerungsstrukturen</span><span class="sxs-lookup"><span data-stu-id="364fe-127">Other Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)  
 [<span data-ttu-id="364fe-128">Geschachtelte Steuerungsstrukturen</span><span class="sxs-lookup"><span data-stu-id="364fe-128">Nested Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
