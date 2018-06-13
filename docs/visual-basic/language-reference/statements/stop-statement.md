---
title: Stop-Anweisung (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Stop
helpviewer_keywords:
- breakpoints, Stop statements
- Stop statements [Visual Basic], syntax
- Stop statements [Visual Basic]
- execution [Visual Basic], suspending
- processing, interrupting
- processes, interrupting
- execution [Visual Basic], stopping
ms.assetid: c9a9fde0-d649-4662-9bef-bd0146ebc2a7
ms.openlocfilehash: 955a3b6a2f7dc1d0e9823ed6d500ab7f7f9fe5b2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33599134"
---
# <a name="stop-statement-visual-basic"></a><span data-ttu-id="93d43-102">Stop-Anweisung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="93d43-102">Stop Statement (Visual Basic)</span></span>
<span data-ttu-id="93d43-103">Hält die Ausführung.</span><span class="sxs-lookup"><span data-stu-id="93d43-103">Suspends execution.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="93d43-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="93d43-104">Syntax</span></span>  
  
```  
Stop  
```  
  
## <a name="remarks"></a><span data-ttu-id="93d43-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="93d43-105">Remarks</span></span>  
 <span data-ttu-id="93d43-106">Sie können platzieren `Stop` -Anweisungen an einer beliebigen Stelle in Prozeduren Ausführung zu unterbrechen.</span><span class="sxs-lookup"><span data-stu-id="93d43-106">You can place `Stop` statements anywhere in procedures to suspend execution.</span></span> <span data-ttu-id="93d43-107">Mithilfe der `Stop` -Anweisung entspricht dem Festlegen eines Haltepunkts im Code.</span><span class="sxs-lookup"><span data-stu-id="93d43-107">Using the `Stop` statement is similar to setting a breakpoint in the code.</span></span>  
  
 <span data-ttu-id="93d43-108">Die `Stop` Anweisung hält die Ausführung, aber im Gegensatz zu `End`, schließen Sie alle Dateien oder keine Variablen löschen, es sei denn, sie in eine kompilierte ausführbare Datei (.exe) entdeckt wird.</span><span class="sxs-lookup"><span data-stu-id="93d43-108">The `Stop` statement suspends execution, but unlike `End`, it does not close any files or clear any variables, unless it is encountered in a compiled executable (.exe) file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="93d43-109">Wenn die `Stop` -Anweisung im Code, der außerhalb der integrierten Entwicklungsumgebung (IDE) ausgeführt wird, wird der Debugger aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="93d43-109">If the `Stop` statement is encountered in code that is running outside of the integrated development environment (IDE), the debugger is invoked.</span></span> <span data-ttu-id="93d43-110">Dies gilt unabhängig davon, ob der Code im Debuggen "oder" Retail-Modus kompiliert wurde.</span><span class="sxs-lookup"><span data-stu-id="93d43-110">This is true regardless of whether the code was compiled in debug or retail mode.</span></span>  
  
## <a name="example"></a><span data-ttu-id="93d43-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="93d43-111">Example</span></span>  
 <span data-ttu-id="93d43-112">Dieses Beispiel verwendet die `Stop` Anweisung Anhalten der Ausführung für jede Iteration durch die `For...Next` Schleife.</span><span class="sxs-lookup"><span data-stu-id="93d43-112">This example uses the `Stop` statement to suspend execution for each iteration through the `For...Next` loop.</span></span>  
  
 [!code-vb[VbVbalrStatements#56](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/stop-statement_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="93d43-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="93d43-113">See Also</span></span>  
 [<span data-ttu-id="93d43-114">End-Anweisung</span><span class="sxs-lookup"><span data-stu-id="93d43-114">End Statement</span></span>](../../../visual-basic/language-reference/statements/end-statement.md)
