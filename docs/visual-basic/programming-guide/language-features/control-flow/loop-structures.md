---
title: Strukturen (Visual Basic)-Schleife | Microsoft-Dokumentation
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
- control flow, loops
- For keyword [Visual Basic], loop structures
- loops
- loop structures
- statements [Visual Basic], loop
- Do statement, Do loops
- conditional statements, loop structures
ms.assetid: ecacb09b-a4c9-42be-98b2-a15d368b5db8
caps.latest.revision: 18
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
ms.openlocfilehash: eba728d782bb5a6259467fb48f738f35580049c0
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="loop-structures-visual-basic"></a><span data-ttu-id="b3dfe-102">Schleifenstruktur (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b3dfe-102">Loop Structures (Visual Basic)</span></span>
[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="b3dfe-103">Schleifenstruktur können Sie eine oder mehrere Zeilen Code wiederholt auszuführen.</span><span class="sxs-lookup"><span data-stu-id="b3dfe-103"> loop structures allow you to run one or more lines of code repetitively.</span></span> <span data-ttu-id="b3dfe-104">Sie können die Anweisungen in einer Schleife wiederholen, bis eine Bedingung ist `True`, bis eine Bedingung `False`, oft, oder einmal für jedes Element in einer angegebenen Auflistung.</span><span class="sxs-lookup"><span data-stu-id="b3dfe-104">You can repeat the statements in a loop structure until a condition is `True`, until a condition is `False`, a specified number of times, or once for each element in a collection.</span></span>  
  
 <span data-ttu-id="b3dfe-105">Die folgende Abbildung zeigt eine Schleife, die eine Gruppe von Anweisungen ausgeführt wird, bis eine Bedingung erfüllt wird.</span><span class="sxs-lookup"><span data-stu-id="b3dfe-105">The following illustration shows a loop structure that runs a set of statements until a condition becomes true.</span></span>  
  
 <span data-ttu-id="b3dfe-106">![Flussdiagramm Do... Until-Schleife](../../../../visual-basic/programming-guide/language-features/control-flow/media/dountilloop.gif "DoUntilLoop")</span><span class="sxs-lookup"><span data-stu-id="b3dfe-106">![Flow chart of a Do...Until loop](../../../../visual-basic/programming-guide/language-features/control-flow/media/dountilloop.gif "DoUntilLoop")</span></span>  
<span data-ttu-id="b3dfe-107">Eine Gruppe von Anweisungen ausgeführt, bis eine Bedingung erfüllt wird.</span><span class="sxs-lookup"><span data-stu-id="b3dfe-107">Running a set of statements until a condition becomes true</span></span>  
  
## <a name="while-loops"></a><span data-ttu-id="b3dfe-108">While-Schleifen</span><span class="sxs-lookup"><span data-stu-id="b3dfe-108">While Loops</span></span>  
 <span data-ttu-id="b3dfe-109">The `While`... `End While` Konstruktion führt eine Gruppe von Anweisungen, solange die Bedingung angegeben werden, in der `While` -Anweisung ist `True`.</span><span class="sxs-lookup"><span data-stu-id="b3dfe-109">The `While`...`End While` construction runs a set of statements as long as the condition specified in the `While` statement is `True`.</span></span> <span data-ttu-id="b3dfe-110">Weitere Informationen finden Sie unter [während... While-Anweisung beendet](../../../../visual-basic/language-reference/statements/while-end-while-statement.md).</span><span class="sxs-lookup"><span data-stu-id="b3dfe-110">For more information, see [While...End While Statement](../../../../visual-basic/language-reference/statements/while-end-while-statement.md).</span></span>  
  
## <a name="do-loops"></a><span data-ttu-id="b3dfe-111">Do-Schleifen</span><span class="sxs-lookup"><span data-stu-id="b3dfe-111">Do Loops</span></span>  
 <span data-ttu-id="b3dfe-112">The `Do`... `Loop` Konstruktion können Sie eine Bedingung am Anfang oder am Ende einer Schleifenstruktur zu testen.</span><span class="sxs-lookup"><span data-stu-id="b3dfe-112">The `Do`...`Loop` construction allows you to test a condition at either the beginning or the end of a loop structure.</span></span> <span data-ttu-id="b3dfe-113">Sie können auch angeben, ob die Schleife wiederholt wird, solange die Bedingung ist `True` oder annimmt `True`.</span><span class="sxs-lookup"><span data-stu-id="b3dfe-113">You can also specify whether to repeat the loop while the condition remains `True` or until it becomes `True`.</span></span> <span data-ttu-id="b3dfe-114">Weitere Informationen finden Sie unter [tun... Loop-Anweisung](../../../../visual-basic/language-reference/statements/do-loop-statement.md).</span><span class="sxs-lookup"><span data-stu-id="b3dfe-114">For more information, see [Do...Loop Statement](../../../../visual-basic/language-reference/statements/do-loop-statement.md).</span></span>  
  
## <a name="for-loops"></a><span data-ttu-id="b3dfe-115">For-Schleifen</span><span class="sxs-lookup"><span data-stu-id="b3dfe-115">For Loops</span></span>  
 <span data-ttu-id="b3dfe-116">The `For`... `Next` zur Erstellung einer festgelegten Anzahl an, wie oft die Schleife ausführt.</span><span class="sxs-lookup"><span data-stu-id="b3dfe-116">The `For`...`Next` construction performs the loop a set number of times.</span></span> <span data-ttu-id="b3dfe-117">Eine Schleifensteuerungsvariable, so genannte verwendet eine *Leistungsindikator*, Einsatz von.</span><span class="sxs-lookup"><span data-stu-id="b3dfe-117">It uses a loop control variable, also called a *counter*, to keep track of the repetitions.</span></span> <span data-ttu-id="b3dfe-118">Angabe der Start- und Endwert für diesen Zähler, und Sie können optional angeben, den Betrag, den es über eine Wiederholung zur nächsten erhöht.</span><span class="sxs-lookup"><span data-stu-id="b3dfe-118">You specify the starting and ending values for this counter, and you can optionally specify the amount by which it increases from one repetition to the next.</span></span> <span data-ttu-id="b3dfe-119">Weitere Informationen finden Sie unter [für... Nächste Anweisung](../../../../visual-basic/language-reference/statements/for-next-statement.md).</span><span class="sxs-lookup"><span data-stu-id="b3dfe-119">For more information, see [For...Next Statement](../../../../visual-basic/language-reference/statements/for-next-statement.md).</span></span>  
  
## <a name="for-each-loops"></a><span data-ttu-id="b3dfe-120">For Each-Schleife</span><span class="sxs-lookup"><span data-stu-id="b3dfe-120">For Each Loops</span></span>  
 <span data-ttu-id="b3dfe-121">The `For Each`... `Next` Konstruktion wird eine Gruppe von Anweisungen, die einmal für jedes Element in einer Auflistung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="b3dfe-121">The `For Each`...`Next` construction runs a set of statements once for each element in a collection.</span></span> <span data-ttu-id="b3dfe-122">Sie geben die Schleifensteuerungsvariable, aber Sie haben keinen Anfangs- oder Endwert dieser bestimmen.</span><span class="sxs-lookup"><span data-stu-id="b3dfe-122">You specify the loop control variable, but you do not have to determine starting or ending values for it.</span></span> <span data-ttu-id="b3dfe-123">Weitere Informationen finden Sie unter [für jede... Nächste Anweisung](../../../../visual-basic/language-reference/statements/for-each-next-statement.md).</span><span class="sxs-lookup"><span data-stu-id="b3dfe-123">For more information, see [For Each...Next Statement](../../../../visual-basic/language-reference/statements/for-each-next-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3dfe-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b3dfe-124">See Also</span></span>  
 <span data-ttu-id="b3dfe-125">[Ablaufsteuerung](../../../../visual-basic/programming-guide/language-features/control-flow/index.md) </span><span class="sxs-lookup"><span data-stu-id="b3dfe-125">[Control Flow](../../../../visual-basic/programming-guide/language-features/control-flow/index.md) </span></span>  
<span data-ttu-id="b3dfe-126"> [Entscheidungsstrukturen](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md) </span><span class="sxs-lookup"><span data-stu-id="b3dfe-126"> [Decision Structures](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md) </span></span>  
<span data-ttu-id="b3dfe-127"> [Weitere Steuerungsstrukturen](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md) </span><span class="sxs-lookup"><span data-stu-id="b3dfe-127"> [Other Control Structures](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md) </span></span>  
<span data-ttu-id="b3dfe-128"> [Geschachtelte Steuerungsstrukturen](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)</span><span class="sxs-lookup"><span data-stu-id="b3dfe-128"> [Nested Control Structures](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)</span></span>
