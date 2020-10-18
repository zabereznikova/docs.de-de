---
title: Die Funktionsauswertung ist deaktiviert, da eine frühere Funktionsevaluierung das Zeitlimit überschritten hat.
ms.date: 07/20/2015
f1_keywords:
- bc30957
- vbc30957
helpviewer_keywords:
- BC30957
ms.assetid: 561e593a-f50a-4b72-a708-4cab60ec7b28
ms.openlocfilehash: 6367553df38a7ccf3b4afbeec877f88fc3d3a1da
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92160684"
---
# <a name="bc30957-function-evaluation-is-disabled-because-a-previous-function-evaluation-timed-out"></a><span data-ttu-id="c932a-102">BC30957: die Funktions Auswertung ist deaktiviert, da bei einer vorherigen Funktions Auswertung ein Timeout aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="c932a-102">BC30957: Function evaluation is disabled because a previous function evaluation timed out</span></span>

<span data-ttu-id="c932a-103">Die Funktions Auswertung ist deaktiviert, da bei einer vorherigen Funktions Auswertung ein Timeout aufgetreten ist. Um die Funktions Auswertung wieder zu aktivieren, müssen Sie erneut ausführen oder das Debugging neu starten.</span><span class="sxs-lookup"><span data-stu-id="c932a-103">Function evaluation is disabled because a previous function evaluation timed out. To re-enable function evaluation, step again or restart debugging.</span></span>

 <span data-ttu-id="c932a-104">Im Visual Studio-Debugger gibt ein Ausdruck einen Prozeduraufruf an, doch das Timeout einer anderen Evaluierung wurde überschritten.</span><span class="sxs-lookup"><span data-stu-id="c932a-104">In the Visual Studio debugger, an expression specifies a procedure call, but another evaluation has timed out.</span></span>

 <span data-ttu-id="c932a-105">Mögliche Ursachen für einen Prozedur Aufruf zum Timeout sind eine Endlosschleife oder eine *Endlosschleife*.</span><span class="sxs-lookup"><span data-stu-id="c932a-105">Possible causes for a procedure call to time out include an infinite loop or *endless loop*.</span></span> <span data-ttu-id="c932a-106">Weitere Informationen finden Sie unter [für... Next-Anweisung](../statements/for-next-statement.md).</span><span class="sxs-lookup"><span data-stu-id="c932a-106">For more information, see [For...Next Statement](../statements/for-next-statement.md).</span></span>

 <span data-ttu-id="c932a-107">Ein Sonderfall einer Endlosschleife ist *Rekursion*.</span><span class="sxs-lookup"><span data-stu-id="c932a-107">A special case of an infinite loop is *recursion*.</span></span> <span data-ttu-id="c932a-108">Weitere Informationen finden Sie unter [Rekursive Prozeduren](../../programming-guide/language-features/procedures/recursive-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="c932a-108">For more information, see [Recursive Procedures](../../programming-guide/language-features/procedures/recursive-procedures.md).</span></span>

 <span data-ttu-id="c932a-109">**Fehler-ID:** BC30957</span><span class="sxs-lookup"><span data-stu-id="c932a-109">**Error ID:** BC30957</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="c932a-110">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="c932a-110">To correct this error</span></span>

1. <span data-ttu-id="c932a-111">Legen Sie nach Möglichkeit fest, was die vorherige Funktions Auswertung war und was zu einem Timeout geführt hat. Andernfalls kann dieser Fehler erneut auftreten.</span><span class="sxs-lookup"><span data-stu-id="c932a-111">If possible, determine what the previous function evaluation was and what caused it to time out. Otherwise, you might encounter this error again.</span></span>

2. <span data-ttu-id="c932a-112">Führen Sie entweder den Einzelschrittdurchlauf des Debugger erneut aus, oder beenden Sie das Debuggen, und starten Sie den Debugvorgang neu.</span><span class="sxs-lookup"><span data-stu-id="c932a-112">Either step the debugger again, or terminate and restart debugging.</span></span>

## <a name="see-also"></a><span data-ttu-id="c932a-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c932a-113">See also</span></span>

- [<span data-ttu-id="c932a-114">Debuggen in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="c932a-114">Debugging in Visual Studio</span></span>](/visualstudio/debugger/debugger-feature-tour)
- [<span data-ttu-id="c932a-115">Navigieren im Code mit dem Debugger</span><span class="sxs-lookup"><span data-stu-id="c932a-115">Navigating through Code with the Debugger</span></span>](/visualstudio/debugger/navigating-through-code-with-the-debugger)
