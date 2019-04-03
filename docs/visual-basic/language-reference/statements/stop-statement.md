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
ms.openlocfilehash: 80d6734945324f3f517b256051486273f6b687ec
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58827990"
---
# <a name="stop-statement-visual-basic"></a><span data-ttu-id="85215-102">Stop-Anweisung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="85215-102">Stop Statement (Visual Basic)</span></span>
<span data-ttu-id="85215-103">Hält die Ausführung.</span><span class="sxs-lookup"><span data-stu-id="85215-103">Suspends execution.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85215-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="85215-104">Syntax</span></span>  
  
```  
Stop  
```  
  
## <a name="remarks"></a><span data-ttu-id="85215-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="85215-105">Remarks</span></span>  
 <span data-ttu-id="85215-106">Sie können platzieren `Stop` -Anweisungen an einer beliebigen Stelle in Prozeduren, die Ausführung anzuhalten.</span><span class="sxs-lookup"><span data-stu-id="85215-106">You can place `Stop` statements anywhere in procedures to suspend execution.</span></span> <span data-ttu-id="85215-107">Mithilfe der `Stop` -Anweisung entspricht dem Festlegen eines Haltepunkts im Code.</span><span class="sxs-lookup"><span data-stu-id="85215-107">Using the `Stop` statement is similar to setting a breakpoint in the code.</span></span>  
  
 <span data-ttu-id="85215-108">Die `Stop` Anweisung hält die Ausführung, aber im Gegensatz zu `End`, keine Dateien schließen oder löschen Sie alle Variablen, es sei denn, es in eine kompilierte ausführbare Datei (.exe)-Datei gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="85215-108">The `Stop` statement suspends execution, but unlike `End`, it does not close any files or clear any variables, unless it is encountered in a compiled executable (.exe) file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="85215-109">Wenn die `Stop` -Anweisung im Code, der außerhalb der integrierten Entwicklungsumgebung (IDE) ausgeführt wird, wird der Debugger aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="85215-109">If the `Stop` statement is encountered in code that is running outside of the integrated development environment (IDE), the debugger is invoked.</span></span> <span data-ttu-id="85215-110">Dies gilt unabhängig davon, ob der Code im Debug-oder Retailmodus kompiliert wurde.</span><span class="sxs-lookup"><span data-stu-id="85215-110">This is true regardless of whether the code was compiled in debug or retail mode.</span></span>  
  
## <a name="example"></a><span data-ttu-id="85215-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="85215-111">Example</span></span>  
 <span data-ttu-id="85215-112">Dieses Beispiel verwendet die `Stop` Anweisung, um die Ausführung bei jeder Iteration der `For...Next` Schleife.</span><span class="sxs-lookup"><span data-stu-id="85215-112">This example uses the `Stop` statement to suspend execution for each iteration through the `For...Next` loop.</span></span>  
  
 [!code-vb[VbVbalrStatements#56](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#56)]  
  
## <a name="see-also"></a><span data-ttu-id="85215-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="85215-113">See also</span></span>

- [<span data-ttu-id="85215-114">End-Anweisung</span><span class="sxs-lookup"><span data-stu-id="85215-114">End Statement</span></span>](../../../visual-basic/language-reference/statements/end-statement.md)
