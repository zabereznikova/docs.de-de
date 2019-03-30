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
ms.openlocfilehash: c09c0bdee0e8740abb7cc085f0796048a5db150c
ms.sourcegitcommit: 15ab532fd5e1f8073a4b678922d93b68b521bfa0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/29/2019
ms.locfileid: "58654366"
---
# <a name="loop-structures-visual-basic"></a><span data-ttu-id="0e119-102">Schleifenstruktur (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0e119-102">Loop Structures (Visual Basic)</span></span>
<span data-ttu-id="0e119-103">Visual Basic-Schleifenstruktur können Sie eine oder mehrere Zeilen Code wiederholt auszuführen.</span><span class="sxs-lookup"><span data-stu-id="0e119-103">Visual Basic loop structures allow you to run one or more lines of code repetitively.</span></span> <span data-ttu-id="0e119-104">Sie können die Anweisungen in einer Schleifenstruktur wiederholen, bis eine Bedingung ist `True`, bis eine Bedingung ist `False`, eine Zahl, die mehrmals oder einmal für jedes Element in einer angegebenen Auflistung.</span><span class="sxs-lookup"><span data-stu-id="0e119-104">You can repeat the statements in a loop structure until a condition is `True`, until a condition is `False`, a specified number of times, or once for each element in a collection.</span></span>  
  
 <span data-ttu-id="0e119-105">Die folgende Abbildung zeigt eine Schleifenstruktur, die einen Satz von Anweisungen ausgeführt, bis eine Bedingung erfüllt wird:</span><span class="sxs-lookup"><span data-stu-id="0e119-105">The following illustration shows a loop structure that runs a set of statements until a condition becomes true:</span></span>  
  
 ![Flussdiagramm, das zeigt, wie eine Do... Until-Schleife.](./media/loop-structures/do-until-loop-true-condition.gif)  
  
## <a name="while-loops"></a><span data-ttu-id="0e119-107">While-Schleifen</span><span class="sxs-lookup"><span data-stu-id="0e119-107">While Loops</span></span>  
 <span data-ttu-id="0e119-108">Die `While`... `End While` Konstruktion wird eine Reihe von Anweisungen ausgeführt, solange die Bedingung in angegeben die `While` -Anweisung ist `True`.</span><span class="sxs-lookup"><span data-stu-id="0e119-108">The `While`...`End While` construction runs a set of statements as long as the condition specified in the `While` statement is `True`.</span></span> <span data-ttu-id="0e119-109">Weitere Informationen finden Sie unter [während... While-Anweisung enden](../../../../visual-basic/language-reference/statements/while-end-while-statement.md).</span><span class="sxs-lookup"><span data-stu-id="0e119-109">For more information, see [While...End While Statement](../../../../visual-basic/language-reference/statements/while-end-while-statement.md).</span></span>  
  
## <a name="do-loops"></a><span data-ttu-id="0e119-110">Do-Schleifen</span><span class="sxs-lookup"><span data-stu-id="0e119-110">Do Loops</span></span>  
 <span data-ttu-id="0e119-111">Die `Do`... `Loop` Konstruktion können Sie eine Bedingung auf den Anfang oder Ende einer Schleifenstruktur zu testen.</span><span class="sxs-lookup"><span data-stu-id="0e119-111">The `Do`...`Loop` construction allows you to test a condition at either the beginning or the end of a loop structure.</span></span> <span data-ttu-id="0e119-112">Sie können auch angeben, ob die Schleife wiederholt wird, solange die Bedingung bleibt `True` oder bis er wieder ist `True`.</span><span class="sxs-lookup"><span data-stu-id="0e119-112">You can also specify whether to repeat the loop while the condition remains `True` or until it becomes `True`.</span></span> <span data-ttu-id="0e119-113">Weitere Informationen finden Sie unter [tun... Until...Loop-Anweisung](../../../../visual-basic/language-reference/statements/do-loop-statement.md).</span><span class="sxs-lookup"><span data-stu-id="0e119-113">For more information, see [Do...Loop Statement](../../../../visual-basic/language-reference/statements/do-loop-statement.md).</span></span>  
  
## <a name="for-loops"></a><span data-ttu-id="0e119-114">For-Schleifen</span><span class="sxs-lookup"><span data-stu-id="0e119-114">For Loops</span></span>  
 <span data-ttu-id="0e119-115">Die `For`... `Next` Konstruktion führt eine festgelegte Anzahl an, wie oft die Schleife.</span><span class="sxs-lookup"><span data-stu-id="0e119-115">The `For`...`Next` construction performs the loop a set number of times.</span></span> <span data-ttu-id="0e119-116">Er verwendet eine Loop-Steuerelementvariable, die so genannte eine *Leistungsindikator*, zum Nachverfolgen der Wiederholungen.</span><span class="sxs-lookup"><span data-stu-id="0e119-116">It uses a loop control variable, also called a *counter*, to keep track of the repetitions.</span></span> <span data-ttu-id="0e119-117">Sie die Start- und Endwerte für diesen Zähler angeben und optional können Sie angeben, die Menge, die mit der sie über eine Wiederholung an den nächsten erhöht.</span><span class="sxs-lookup"><span data-stu-id="0e119-117">You specify the starting and ending values for this counter, and you can optionally specify the amount by which it increases from one repetition to the next.</span></span> <span data-ttu-id="0e119-118">Weitere Informationen finden Sie unter [für... Nächste Anweisung](../../../../visual-basic/language-reference/statements/for-next-statement.md).</span><span class="sxs-lookup"><span data-stu-id="0e119-118">For more information, see [For...Next Statement](../../../../visual-basic/language-reference/statements/for-next-statement.md).</span></span>  
  
## <a name="for-each-loops"></a><span data-ttu-id="0e119-119">Foreach-Schleifen</span><span class="sxs-lookup"><span data-stu-id="0e119-119">For Each Loops</span></span>  
 <span data-ttu-id="0e119-120">Die `For Each`... `Next` Konstruktion wird eine Reihe von Anweisungen, die einmal für jedes Element in einer Sammlung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="0e119-120">The `For Each`...`Next` construction runs a set of statements once for each element in a collection.</span></span> <span data-ttu-id="0e119-121">Sie geben die Loop-Steuerelementvariable, aber Sie müssen nicht bestimmt werden, starten oder den Endwert dieser.</span><span class="sxs-lookup"><span data-stu-id="0e119-121">You specify the loop control variable, but you do not have to determine starting or ending values for it.</span></span> <span data-ttu-id="0e119-122">Weitere Informationen finden Sie unter [für jede... Nächste Anweisung](../../../../visual-basic/language-reference/statements/for-each-next-statement.md).</span><span class="sxs-lookup"><span data-stu-id="0e119-122">For more information, see [For Each...Next Statement](../../../../visual-basic/language-reference/statements/for-each-next-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e119-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0e119-123">See also</span></span>
- [<span data-ttu-id="0e119-124">Ablaufsteuerung</span><span class="sxs-lookup"><span data-stu-id="0e119-124">Control Flow</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)
- [<span data-ttu-id="0e119-125">Entscheidungsstrukturen</span><span class="sxs-lookup"><span data-stu-id="0e119-125">Decision Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)
- [<span data-ttu-id="0e119-126">Weitere Steuerungsstrukturen</span><span class="sxs-lookup"><span data-stu-id="0e119-126">Other Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)
- [<span data-ttu-id="0e119-127">Geschachtelte Steuerungsstrukturen</span><span class="sxs-lookup"><span data-stu-id="0e119-127">Nested Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
