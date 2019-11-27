---
title: Schleifenstruktur
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
ms.openlocfilehash: 0a75205a7d52c332094d624d082e5db3e89447f5
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353914"
---
# <a name="loop-structures-visual-basic"></a><span data-ttu-id="eae4a-102">Schleifenstruktur (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="eae4a-102">Loop Structures (Visual Basic)</span></span>
<span data-ttu-id="eae4a-103">Mit Visual Basic Schleifen Strukturen können Sie eine oder mehrere Codezeilen wiederholt ausführen.</span><span class="sxs-lookup"><span data-stu-id="eae4a-103">Visual Basic loop structures allow you to run one or more lines of code repetitively.</span></span> <span data-ttu-id="eae4a-104">Sie können die-Anweisungen in einer Schleifen Struktur wiederholen, bis eine Bedingung `True`wird, bis eine Bedingung `False`, eine angegebene Anzahl von vorkommen oder einmal für jedes Element in einer Auflistung ist.</span><span class="sxs-lookup"><span data-stu-id="eae4a-104">You can repeat the statements in a loop structure until a condition is `True`, until a condition is `False`, a specified number of times, or once for each element in a collection.</span></span>  
  
 <span data-ttu-id="eae4a-105">Die folgende Abbildung zeigt eine Schleifen Struktur, die eine Reihe von-Anweisungen ausführt, bis eine Bedingung zutrifft:</span><span class="sxs-lookup"><span data-stu-id="eae4a-105">The following illustration shows a loop structure that runs a set of statements until a condition becomes true:</span></span>  
  
 ![Flussdiagramm, das einen Vorgang anzeigt... Until-Schleife.](./media/loop-structures/do-until-loop-true-condition.gif)  
  
## <a name="while-loops"></a><span data-ttu-id="eae4a-107">While-Schleifen</span><span class="sxs-lookup"><span data-stu-id="eae4a-107">While Loops</span></span>  
 <span data-ttu-id="eae4a-108">Die `While`...`End While` Konstruktion führt einen Satz von-Anweisungen aus, sofern die in der `While`-Anweisung angegebene Bedingung `True`ist.</span><span class="sxs-lookup"><span data-stu-id="eae4a-108">The `While`...`End While` construction runs a set of statements as long as the condition specified in the `While` statement is `True`.</span></span> <span data-ttu-id="eae4a-109">Weitere Informationen finden Sie unter [while... End While-Anweisung](../../../../visual-basic/language-reference/statements/while-end-while-statement.md).</span><span class="sxs-lookup"><span data-stu-id="eae4a-109">For more information, see [While...End While Statement](../../../../visual-basic/language-reference/statements/while-end-while-statement.md).</span></span>  
  
## <a name="do-loops"></a><span data-ttu-id="eae4a-110">Do-Schleifen</span><span class="sxs-lookup"><span data-stu-id="eae4a-110">Do Loops</span></span>  
 <span data-ttu-id="eae4a-111">Mit der `Do`...`Loop` Konstruktion können Sie eine Bedingung entweder am Anfang oder am Ende einer Schleifen Struktur testen.</span><span class="sxs-lookup"><span data-stu-id="eae4a-111">The `Do`...`Loop` construction allows you to test a condition at either the beginning or the end of a loop structure.</span></span> <span data-ttu-id="eae4a-112">Sie können auch angeben, ob die Schleife wiederholt werden soll, während die Bedingung `True` oder bis Sie `True`wird.</span><span class="sxs-lookup"><span data-stu-id="eae4a-112">You can also specify whether to repeat the loop while the condition remains `True` or until it becomes `True`.</span></span> <span data-ttu-id="eae4a-113">Weitere Informationen finden Sie unter [Do... Loop-Anweisung](../../../../visual-basic/language-reference/statements/do-loop-statement.md).</span><span class="sxs-lookup"><span data-stu-id="eae4a-113">For more information, see [Do...Loop Statement](../../../../visual-basic/language-reference/statements/do-loop-statement.md).</span></span>  
  
## <a name="for-loops"></a><span data-ttu-id="eae4a-114">For-Schleifen</span><span class="sxs-lookup"><span data-stu-id="eae4a-114">For Loops</span></span>  
 <span data-ttu-id="eae4a-115">Die `For`...`Next` Konstruktion führt die Schleife so oft aus, wie es festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="eae4a-115">The `For`...`Next` construction performs the loop a set number of times.</span></span> <span data-ttu-id="eae4a-116">Er verwendet eine Schleifen Steuerungs Variable, auch als " *Counter*" bezeichnet, um die Wiederholungen nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="eae4a-116">It uses a loop control variable, also called a *counter*, to keep track of the repetitions.</span></span> <span data-ttu-id="eae4a-117">Sie geben die Start-und Endwerte für diesen Zählers an, und Sie können optional den Betrag angeben, um den der Wert von einer Wiederholung zum nächsten erhöht wird.</span><span class="sxs-lookup"><span data-stu-id="eae4a-117">You specify the starting and ending values for this counter, and you can optionally specify the amount by which it increases from one repetition to the next.</span></span> <span data-ttu-id="eae4a-118">Weitere Informationen finden Sie unter [für... Next-Anweisung](../../../../visual-basic/language-reference/statements/for-next-statement.md).</span><span class="sxs-lookup"><span data-stu-id="eae4a-118">For more information, see [For...Next Statement](../../../../visual-basic/language-reference/statements/for-next-statement.md).</span></span>  
  
## <a name="for-each-loops"></a><span data-ttu-id="eae4a-119">For Each-Schleifen</span><span class="sxs-lookup"><span data-stu-id="eae4a-119">For Each Loops</span></span>  
 <span data-ttu-id="eae4a-120">Die `For Each`...`Next` Konstruktion führt einen Satz von Anweisungen einmal für jedes Element in einer Auflistung aus.</span><span class="sxs-lookup"><span data-stu-id="eae4a-120">The `For Each`...`Next` construction runs a set of statements once for each element in a collection.</span></span> <span data-ttu-id="eae4a-121">Sie geben die Schleifen Steuerungs Variable an, aber Sie müssen nicht die Anfangs-oder Endwerte dafür bestimmen.</span><span class="sxs-lookup"><span data-stu-id="eae4a-121">You specify the loop control variable, but you do not have to determine starting or ending values for it.</span></span> <span data-ttu-id="eae4a-122">Weitere Informationen finden Sie unter [for each... Next-Anweisung](../../../../visual-basic/language-reference/statements/for-each-next-statement.md).</span><span class="sxs-lookup"><span data-stu-id="eae4a-122">For more information, see [For Each...Next Statement](../../../../visual-basic/language-reference/statements/for-each-next-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eae4a-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="eae4a-123">See also</span></span>

- [<span data-ttu-id="eae4a-124">Ablaufsteuerung</span><span class="sxs-lookup"><span data-stu-id="eae4a-124">Control Flow</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)
- [<span data-ttu-id="eae4a-125">Entscheidungsstrukturen</span><span class="sxs-lookup"><span data-stu-id="eae4a-125">Decision Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)
- [<span data-ttu-id="eae4a-126">Weitere Steuerungsstrukturen</span><span class="sxs-lookup"><span data-stu-id="eae4a-126">Other Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)
- [<span data-ttu-id="eae4a-127">Geschachtelte Steuerungsstrukturen</span><span class="sxs-lookup"><span data-stu-id="eae4a-127">Nested Control Structures</span></span>](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
