---
title: Stop-Anweisung
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
ms.openlocfilehash: 2ef1e2f9045e5509e11557c9fdaf3edd2786b72c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404225"
---
# <a name="stop-statement-visual-basic"></a><span data-ttu-id="07427-102">Stop-Anweisung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="07427-102">Stop Statement (Visual Basic)</span></span>
<span data-ttu-id="07427-103">Hält die Ausführung an.</span><span class="sxs-lookup"><span data-stu-id="07427-103">Suspends execution.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="07427-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="07427-104">Syntax</span></span>  
  
```vb  
Stop  
```  
  
## <a name="remarks"></a><span data-ttu-id="07427-105">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="07427-105">Remarks</span></span>  
 <span data-ttu-id="07427-106">Sie können- `Stop` Anweisungen überall in Prozeduren platzieren, um die Ausführung anzuhalten.</span><span class="sxs-lookup"><span data-stu-id="07427-106">You can place `Stop` statements anywhere in procedures to suspend execution.</span></span> <span data-ttu-id="07427-107">Die Verwendung der- `Stop` Anweisung ähnelt dem Festlegen eines Breakpoints im Code.</span><span class="sxs-lookup"><span data-stu-id="07427-107">Using the `Stop` statement is similar to setting a breakpoint in the code.</span></span>  
  
 <span data-ttu-id="07427-108">Die- `Stop` Anweisung hält die Ausführung an, aber im Gegensatz dazu `End` schließt Sie keine Dateien oder löscht Variablen, es sei denn, Sie findet in einer kompilierten ausführbaren Datei (. exe).</span><span class="sxs-lookup"><span data-stu-id="07427-108">The `Stop` statement suspends execution, but unlike `End`, it does not close any files or clear any variables, unless it is encountered in a compiled executable (.exe) file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="07427-109">Wenn die- `Stop` Anweisung im Code gefunden wird, der außerhalb der integrierten Entwicklungsumgebung (Integrated Development Environment, IDE) ausgeführt wird, wird der Debugger aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="07427-109">If the `Stop` statement is encountered in code that is running outside of the integrated development environment (IDE), the debugger is invoked.</span></span> <span data-ttu-id="07427-110">Dies gilt unabhängig davon, ob der Code im Debug-oder Einzelhandels Modus kompiliert wurde.</span><span class="sxs-lookup"><span data-stu-id="07427-110">This is true regardless of whether the code was compiled in debug or retail mode.</span></span>  
  
## <a name="example"></a><span data-ttu-id="07427-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="07427-111">Example</span></span>  
 <span data-ttu-id="07427-112">In diesem Beispiel wird die- `Stop` Anweisung verwendet, um die Ausführung für jede Iterations Schleife durch die- `For...Next` Schleife anzuhalten.</span><span class="sxs-lookup"><span data-stu-id="07427-112">This example uses the `Stop` statement to suspend execution for each iteration through the `For...Next` loop.</span></span>  
  
 [!code-vb[VbVbalrStatements#56](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#56)]  
  
## <a name="see-also"></a><span data-ttu-id="07427-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="07427-113">See also</span></span>

- [<span data-ttu-id="07427-114">End-Anweisung</span><span class="sxs-lookup"><span data-stu-id="07427-114">End Statement</span></span>](end-statement.md)
