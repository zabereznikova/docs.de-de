---
title: "Die funktionsauswertung ist deaktiviert, da eine frühere funktionsevaluierung das Zeitlimit | Microsoft-Dokumentation"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30957
- vbc30957
dev_langs:
- VB
helpviewer_keywords:
- BC30957
ms.assetid: 561e593a-f50a-4b72-a708-4cab60ec7b28
caps.latest.revision: 7
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
ms.openlocfilehash: 127f89f4c7ddaf794f58707d8925731a511f3740
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="function-evaluation-is-disabled-because-a-previous-function-evaluation-timed-out"></a><span data-ttu-id="7fac0-102">Die Funktionsauswertung ist deaktiviert, da eine frühere Funktionsevaluierung das Zeitlimit überschritten hat.</span><span class="sxs-lookup"><span data-stu-id="7fac0-102">Function evaluation is disabled because a previous function evaluation timed out</span></span>
<span data-ttu-id="7fac0-103">Die Funktionsauswertung ist deaktiviert, da eine frühere Funktionsevaluierung das Zeitlimit überschritten hat.</span><span class="sxs-lookup"><span data-stu-id="7fac0-103">Function evaluation is disabled because a previous function evaluation timed out.</span></span> <span data-ttu-id="7fac0-104">Wenn Sie die Funktionsauswertung wieder aktivieren möchten, starten Sie den Einzelschrittdurchlauf oder das Debuggen erneut</span><span class="sxs-lookup"><span data-stu-id="7fac0-104">To re-enable function evaluation, step again or restart debugging.</span></span>  
  
 <span data-ttu-id="7fac0-105">Im Visual Studio-Debugger gibt ein Ausdruck einen Prozeduraufruf an, doch das Timeout einer anderen Evaluierung wurde überschritten.</span><span class="sxs-lookup"><span data-stu-id="7fac0-105">In the Visual Studio debugger, an expression specifies a procedure call, but another evaluation has timed out.</span></span>  
  
 <span data-ttu-id="7fac0-106">Mögliche Ursachen für das Timeout eines Prozeduraufrufs zählt eine oder *Endlosschleife*.</span><span class="sxs-lookup"><span data-stu-id="7fac0-106">Possible causes for a procedure call to time out include an infinite loop or *endless loop*.</span></span> <span data-ttu-id="7fac0-107">Weitere Informationen finden Sie unter [für... Nächste Anweisung](../../../visual-basic/language-reference/statements/for-next-statement.md).</span><span class="sxs-lookup"><span data-stu-id="7fac0-107">For more information, see [For...Next Statement](../../../visual-basic/language-reference/statements/for-next-statement.md).</span></span>  
  
 <span data-ttu-id="7fac0-108">Eine besondere Variante einer Endlosschleife stellt *Rekursion*.</span><span class="sxs-lookup"><span data-stu-id="7fac0-108">A special case of an infinite loop is *recursion*.</span></span> <span data-ttu-id="7fac0-109">Weitere Informationen finden Sie unter [rekursive Prozeduren](../../../visual-basic/programming-guide/language-features/procedures/recursive-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="7fac0-109">For more information, see [Recursive Procedures](../../../visual-basic/programming-guide/language-features/procedures/recursive-procedures.md).</span></span>  
  
 <span data-ttu-id="7fac0-110">**Fehler-ID:** BC30957</span><span class="sxs-lookup"><span data-stu-id="7fac0-110">**Error ID:** BC30957</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="7fac0-111">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="7fac0-111">To correct this error</span></span>  
  
1.  <span data-ttu-id="7fac0-112">Bestimmen Sie nach Möglichkeit die vorherige Funktionsevaluierung und die Ursache für das Timeout.</span><span class="sxs-lookup"><span data-stu-id="7fac0-112">If possible, determine what the previous function evaluation was and what caused it to time out.</span></span> <span data-ttu-id="7fac0-113">Andernfalls kann dieser Fehler erneut auftreten.</span><span class="sxs-lookup"><span data-stu-id="7fac0-113">Otherwise, you might encounter this error again.</span></span>  
  
2.  <span data-ttu-id="7fac0-114">Führen Sie entweder den Einzelschrittdurchlauf des Debugger erneut aus, oder beenden Sie das Debuggen, und starten Sie den Debugvorgang neu.</span><span class="sxs-lookup"><span data-stu-id="7fac0-114">Either step the debugger again, or terminate and restart debugging.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7fac0-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7fac0-115">See Also</span></span>  
 <span data-ttu-id="7fac0-116">[Debuggen in Visual Studio](https://docs.microsoft.com/visualstudio/debugger/debugging-in-visual-studio) </span><span class="sxs-lookup"><span data-stu-id="7fac0-116">[Debugging in Visual Studio](https://docs.microsoft.com/visualstudio/debugger/debugging-in-visual-studio) </span></span>  
<span data-ttu-id="7fac0-117"> [Navigieren im Code mit dem Debugger](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger)</span><span class="sxs-lookup"><span data-stu-id="7fac0-117"> [Navigating through Code with the Debugger](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger)</span></span>
