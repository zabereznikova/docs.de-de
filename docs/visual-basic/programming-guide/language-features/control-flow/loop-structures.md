---
title: Schleifenstrukturen
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
ms.openlocfilehash: 3f60e9dc83dc7174e765903be13f2870ea40ce4c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403516"
---
# <a name="loop-structures-visual-basic"></a><span data-ttu-id="25111-102">Schleifenstruktur (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="25111-102">Loop Structures (Visual Basic)</span></span>
<span data-ttu-id="25111-103">Mit Visual Basic Schleifen Strukturen können Sie eine oder mehrere Codezeilen wiederholt ausführen.</span><span class="sxs-lookup"><span data-stu-id="25111-103">Visual Basic loop structures allow you to run one or more lines of code repetitively.</span></span> <span data-ttu-id="25111-104">Sie können die Anweisungen in einer Schleifen Struktur wiederholen, bis eine Bedingung, eine `True` `False` angegebene Anzahl von vorkommen oder einmal für jedes Element in einer Auflistung ist.</span><span class="sxs-lookup"><span data-stu-id="25111-104">You can repeat the statements in a loop structure until a condition is `True`, until a condition is `False`, a specified number of times, or once for each element in a collection.</span></span>  
  
 <span data-ttu-id="25111-105">Die folgende Abbildung zeigt eine Schleifen Struktur, die eine Reihe von-Anweisungen ausführt, bis eine Bedingung zutrifft:</span><span class="sxs-lookup"><span data-stu-id="25111-105">The following illustration shows a loop structure that runs a set of statements until a condition becomes true:</span></span>  
  
 ![Flussdiagramm, das einen Vorgang anzeigt... Until-Schleife.](./media/loop-structures/do-until-loop-true-condition.gif)  
  
## <a name="while-loops"></a><span data-ttu-id="25111-107">While-Schleifen</span><span class="sxs-lookup"><span data-stu-id="25111-107">While Loops</span></span>  
 <span data-ttu-id="25111-108">Die `While` ...- `End While` Konstruktion führt einen Satz von-Anweisungen aus, sofern die in der-Anweisung angegebene Bedingung `While` ist `True` .</span><span class="sxs-lookup"><span data-stu-id="25111-108">The `While`...`End While` construction runs a set of statements as long as the condition specified in the `While` statement is `True`.</span></span> <span data-ttu-id="25111-109">Weitere Informationen finden Sie unter [while... End While-Anweisung](../../../language-reference/statements/while-end-while-statement.md).</span><span class="sxs-lookup"><span data-stu-id="25111-109">For more information, see [While...End While Statement](../../../language-reference/statements/while-end-while-statement.md).</span></span>  
  
## <a name="do-loops"></a><span data-ttu-id="25111-110">Do-Schleifen</span><span class="sxs-lookup"><span data-stu-id="25111-110">Do Loops</span></span>  
 <span data-ttu-id="25111-111">`Do`Mit der...- `Loop` Konstruktion können Sie eine Bedingung entweder am Anfang oder am Ende einer Schleifen Struktur testen.</span><span class="sxs-lookup"><span data-stu-id="25111-111">The `Do`...`Loop` construction allows you to test a condition at either the beginning or the end of a loop structure.</span></span> <span data-ttu-id="25111-112">Sie können auch angeben, ob die Schleife wiederholt werden soll, während die Bedingung verbleibt `True` oder bis Sie zu wird `True` .</span><span class="sxs-lookup"><span data-stu-id="25111-112">You can also specify whether to repeat the loop while the condition remains `True` or until it becomes `True`.</span></span> <span data-ttu-id="25111-113">Weitere Informationen finden Sie unter [Do... Loop-Anweisung](../../../language-reference/statements/do-loop-statement.md).</span><span class="sxs-lookup"><span data-stu-id="25111-113">For more information, see [Do...Loop Statement](../../../language-reference/statements/do-loop-statement.md).</span></span>  
  
## <a name="for-loops"></a><span data-ttu-id="25111-114">For-Schleifen</span><span class="sxs-lookup"><span data-stu-id="25111-114">For Loops</span></span>  
 <span data-ttu-id="25111-115">Die `For` ...- `Next` Konstruktion führt die Schleife so oft aus, wie es festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="25111-115">The `For`...`Next` construction performs the loop a set number of times.</span></span> <span data-ttu-id="25111-116">Er verwendet eine Schleifen Steuerungs Variable, auch als " *Counter*" bezeichnet, um die Wiederholungen nachzuverfolgen.</span><span class="sxs-lookup"><span data-stu-id="25111-116">It uses a loop control variable, also called a *counter*, to keep track of the repetitions.</span></span> <span data-ttu-id="25111-117">Sie geben die Start-und Endwerte für diesen Zählers an, und Sie können optional den Betrag angeben, um den der Wert von einer Wiederholung zum nächsten erhöht wird.</span><span class="sxs-lookup"><span data-stu-id="25111-117">You specify the starting and ending values for this counter, and you can optionally specify the amount by which it increases from one repetition to the next.</span></span> <span data-ttu-id="25111-118">Weitere Informationen finden Sie unter [für... Next-Anweisung](../../../language-reference/statements/for-next-statement.md).</span><span class="sxs-lookup"><span data-stu-id="25111-118">For more information, see [For...Next Statement](../../../language-reference/statements/for-next-statement.md).</span></span>  
  
## <a name="for-each-loops"></a><span data-ttu-id="25111-119">For Each-Schleifen</span><span class="sxs-lookup"><span data-stu-id="25111-119">For Each Loops</span></span>  
 <span data-ttu-id="25111-120">Die `For Each` ...- `Next` Konstruktion führt einen Satz von-Anweisungen einmal für jedes Element in einer Auflistung aus.</span><span class="sxs-lookup"><span data-stu-id="25111-120">The `For Each`...`Next` construction runs a set of statements once for each element in a collection.</span></span> <span data-ttu-id="25111-121">Sie geben die Schleifen Steuerungs Variable an, aber Sie müssen nicht die Anfangs-oder Endwerte dafür bestimmen.</span><span class="sxs-lookup"><span data-stu-id="25111-121">You specify the loop control variable, but you do not have to determine starting or ending values for it.</span></span> <span data-ttu-id="25111-122">Weitere Informationen finden Sie unter [for each... Next-Anweisung](../../../language-reference/statements/for-each-next-statement.md).</span><span class="sxs-lookup"><span data-stu-id="25111-122">For more information, see [For Each...Next Statement](../../../language-reference/statements/for-each-next-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25111-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="25111-123">See also</span></span>

- [<span data-ttu-id="25111-124">Ablauf Steuerung</span><span class="sxs-lookup"><span data-stu-id="25111-124">Control Flow</span></span>](index.md)
- [<span data-ttu-id="25111-125">Entscheidungsstrukturen</span><span class="sxs-lookup"><span data-stu-id="25111-125">Decision Structures</span></span>](decision-structures.md)
- [<span data-ttu-id="25111-126">Weitere Steuerungsstrukturen</span><span class="sxs-lookup"><span data-stu-id="25111-126">Other Control Structures</span></span>](other-control-structures.md)
- [<span data-ttu-id="25111-127">Geschachtelte Steuerungsstrukturen</span><span class="sxs-lookup"><span data-stu-id="25111-127">Nested Control Structures</span></span>](nested-control-structures.md)
