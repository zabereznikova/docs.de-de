---
title: Schleifenstruktur (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- control flow [Visual Basic], loops
- For keyword [Visual Basic], loop structures
- loops
- loop structures [Visual Basic]
- statements [Visual Basic], loop
- Do statement [Visual Basic], Do loops
- conditional statements [Visual Basic], loop structures
ms.assetid: ecacb09b-a4c9-42be-98b2-a15d368b5db8
ms.openlocfilehash: b72eef632b4564abc69e6ebef43b940eb0950e9a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54523388"
---
# <a name="loop-structures-visual-basic"></a><span data-ttu-id="3c2fb-102">Schleifenstruktur (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3c2fb-102">Loop Structures (Visual Basic)</span></span>
<span data-ttu-id="3c2fb-103">Visual Basic-Schleifenstruktur können Sie eine oder mehrere Zeilen Code wiederholt auszuführen.</span><span class="sxs-lookup"><span data-stu-id="3c2fb-103">Visual Basic loop structures allow you to run one or more lines of code repetitively.</span></span> <span data-ttu-id="3c2fb-104">Sie können die Anweisungen in einer Schleifenstruktur wiederholen, bis eine Bedingung ist `True`, bis eine Bedingung ist `False`, eine Zahl, die mehrmals oder einmal für jedes Element in einer angegebenen Auflistung.</span><span class="sxs-lookup"><span data-stu-id="3c2fb-104">You can repeat the statements in a loop structure until a condition is `True`, until a condition is `False`, a specified number of times, or once for each element in a collection.</span></span>  
  
 <span data-ttu-id="3c2fb-105">Die folgende Abbildung zeigt eine Schleifenstruktur, die einen Satz von Anweisungen ausgeführt, bis eine Bedingung erfüllt wird.</span><span class="sxs-lookup"><span data-stu-id="3c2fb-105">The following illustration shows a loop structure that runs a set of statements until a condition becomes true.</span></span>  
  
 <span data-ttu-id="3c2fb-106">![Flussdiagramm der Do... Until-Schleife](../../../../visual-basic/programming-guide/language-features/control-flow/media/dountilloop.gif "DoUntilLoop")</span><span class="sxs-lookup"><span data-stu-id="3c2fb-106">![Flow chart of a Do...Until loop](../../../../visual-basic/programming-guide/language-features/control-flow/media/dountilloop.gif "DoUntilLoop")</span></span>  
<span data-ttu-id="3c2fb-107">Einen Satz von Anweisungen ausgeführt, bis eine Bedingung erfüllt wird.</span><span class="sxs-lookup"><span data-stu-id="3c2fb-107">Running a set of statements until a condition becomes true</span></span>  
  
## <a name="while-loops"></a><span data-ttu-id="3c2fb-108">While-Schleifen</span><span class="sxs-lookup"><span data-stu-id="3c2fb-108">While Loops</span></span>  
 <span data-ttu-id="3c2fb-109">Die `While`... `End While` Konstruktion wird eine Reihe von Anweisungen ausgeführt, solange die Bedingung in angegeben die `While` -Anweisung ist `True`.</span><span class="sxs-lookup"><span data-stu-id="3c2fb-109">The `While`...`End While` construction runs a set of statements as long as the condition specified in the `While` statement is `True`.</span></span> <span data-ttu-id="3c2fb-110">Weitere Informationen finden Sie unter [während... While-Anweisung enden](../../../../visual-basic/language-reference/statements/while-end-while-statement.md).</span><span class="sxs-lookup"><span data-stu-id="3c2fb-110">For more information, see [While...End While Statement](../../../../visual-basic/language-reference/statements/while-end-while-statement.md).</span></span>  
  
## <a name="do-loops"></a><span data-ttu-id="3c2fb-111">Do-Schleifen</span><span class="sxs-lookup"><span data-stu-id="3c2fb-111">Do Loops</span></span>  
 <span data-ttu-id="3c2fb-112">Die `Do`... `Loop` Konstruktion können Sie eine Bedingung auf den Anfang oder Ende einer Schleifenstruktur zu testen.</span><span class="sxs-lookup"><span data-stu-id="3c2fb-112">The `Do`...`Loop` construction allows you to test a condition at either the beginning or the end of a loop structure.</span></span> <span data-ttu-id="3c2fb-113">Sie können auch angeben, ob die Schleife wiederholt wird, solange die Bedingung bleibt `True` oder bis er wieder ist `True`.</span><span class="sxs-lookup"><span data-stu-id="3c2fb-113">You can also specify whether to repeat the loop while the condition remains `True` or until it becomes `True`.</span></span> <span data-ttu-id="3c2fb-114">Weitere Informationen finden Sie unter [tun... Until...Loop-Anweisung](../../../../visual-basic/language-reference/statements/do-loop-statement.md).</span><span class="sxs-lookup"><span data-stu-id="3c2fb-114">For more information, see [Do...Loop Statement](../../../../visual-basic/language-reference/statements/do-loop-statement.md).</span></span>  
  
## <a name="for-loops"></a><span data-ttu-id="3c2fb-115">For-Schleifen</span><span class="sxs-lookup"><span data-stu-id="3c2fb-115">For Loops</span></span>  
 <span data-ttu-id="3c2fb-116">Die `For`... `Next` Konstruktion führt eine festgelegte Anzahl an, wie oft die Schleife.</span><span class="sxs-lookup"><span data-stu-id="3c2fb-116">The `For`...`Next` construction performs the loop a set number of times.</span></span> <span data-ttu-id="3c2fb-117">Er verwendet eine Loop-Steuerelementvariable, die so genannte eine *Leistungsindikator*, zum Nachverfolgen der Wiederholungen.</span><span class="sxs-lookup"><span data-stu-id="3c2fb-117">It uses a loop control variable, also called a *counter*, to keep track of the repetitions.</span></span> <span data-ttu-id="3c2fb-118">Sie die Start- und Endwerte für diesen Zähler angeben und optional können Sie angeben, die Menge, die mit der sie über eine Wiederholung an den nächsten erhöht.</span><span class="sxs-lookup"><span data-stu-id="3c2fb-118">You specify the starting and ending values for this counter, and you can optionally specify the amount by which it increases from one repetition to the next.</span></span> <span data-ttu-id="3c2fb-119">Weitere Informationen finden Sie unter [für... Nächste Anweisung](../../../../visual-basic/language-reference/statements/for-next-statement.md).</span><span class="sxs-lookup"><span data-stu-id="3c2fb-119">For more information, see [For...Next Statement](../../../../visual-basic/language-reference/statements/for-next-statement.md).</span></span>  
  
## <a name="for-each-loops"></a><span data-ttu-id="3c2fb-120">Foreach-Schleifen</span><span class="sxs-lookup"><span data-stu-id="3c2fb-120">For Each Loops</span></span>  
 <span data-ttu-id="3c2fb-121">Die `For Each`... `Next` Konstruktion wird eine Reihe von Anweisungen, die einmal für jedes Element in einer Sammlung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="3c2fb-121">The `For Each`...`Next` construction runs a set of statements once for each element in a collection.</span></span> <span data-ttu-id="3c2fb-122">Sie geben die Loop-Steuerelementvariable, aber Sie müssen nicht bestimmt werden, starten oder den Endwert dieser.</span><span class="sxs-lookup"><span data-stu-id="3c2fb-122">You specify the loop control variable, but you do not have to determine starting or ending values for it.</span></span> <span data-ttu-id="3c2fb-123">Weitere Informationen finden Sie unter [für jede... Nächste Anweisung](../../../../visual-basic/language-reference/statements/for-each-next-statement.md).</span><span class="sxs-lookup"><span data-stu-id="3c2fb-123">For more information, see [For Each...Next Statement](../../../../visual-basic/language-reference/statements/for-each-next-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c2fb-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3c2fb-124">See also</span></span>
- [<span data-ttu-id="3c2fb-125">Ablaufsteuerung</span><span class="sxs-lookup"><span data-stu-id="3c2fb-125">Control Flow</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)
- [<span data-ttu-id="3c2fb-126">Entscheidungsstrukturen</span><span class="sxs-lookup"><span data-stu-id="3c2fb-126">Decision Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)
- [<span data-ttu-id="3c2fb-127">Weitere Steuerungsstrukturen</span><span class="sxs-lookup"><span data-stu-id="3c2fb-127">Other Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)
- [<span data-ttu-id="3c2fb-128">Geschachtelte Steuerungsstrukturen</span><span class="sxs-lookup"><span data-stu-id="3c2fb-128">Nested Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
