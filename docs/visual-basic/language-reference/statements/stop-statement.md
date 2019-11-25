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
ms.openlocfilehash: 497c5f207b2228412411cc3eb01976564f82bd6c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346464"
---
# <a name="stop-statement-visual-basic"></a><span data-ttu-id="d2bf3-102">Stop-Anweisung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d2bf3-102">Stop Statement (Visual Basic)</span></span>
<span data-ttu-id="d2bf3-103">Suspends execution.</span><span class="sxs-lookup"><span data-stu-id="d2bf3-103">Suspends execution.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2bf3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d2bf3-104">Syntax</span></span>  
  
```vb  
Stop  
```  
  
## <a name="remarks"></a><span data-ttu-id="d2bf3-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d2bf3-105">Remarks</span></span>  
 <span data-ttu-id="d2bf3-106">You can place `Stop` statements anywhere in procedures to suspend execution.</span><span class="sxs-lookup"><span data-stu-id="d2bf3-106">You can place `Stop` statements anywhere in procedures to suspend execution.</span></span> <span data-ttu-id="d2bf3-107">Using the `Stop` statement is similar to setting a breakpoint in the code.</span><span class="sxs-lookup"><span data-stu-id="d2bf3-107">Using the `Stop` statement is similar to setting a breakpoint in the code.</span></span>  
  
 <span data-ttu-id="d2bf3-108">The `Stop` statement suspends execution, but unlike `End`, it does not close any files or clear any variables, unless it is encountered in a compiled executable (.exe) file.</span><span class="sxs-lookup"><span data-stu-id="d2bf3-108">The `Stop` statement suspends execution, but unlike `End`, it does not close any files or clear any variables, unless it is encountered in a compiled executable (.exe) file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d2bf3-109">If the `Stop` statement is encountered in code that is running outside of the integrated development environment (IDE), the debugger is invoked.</span><span class="sxs-lookup"><span data-stu-id="d2bf3-109">If the `Stop` statement is encountered in code that is running outside of the integrated development environment (IDE), the debugger is invoked.</span></span> <span data-ttu-id="d2bf3-110">This is true regardless of whether the code was compiled in debug or retail mode.</span><span class="sxs-lookup"><span data-stu-id="d2bf3-110">This is true regardless of whether the code was compiled in debug or retail mode.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d2bf3-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d2bf3-111">Example</span></span>  
 <span data-ttu-id="d2bf3-112">This example uses the `Stop` statement to suspend execution for each iteration through the `For...Next` loop.</span><span class="sxs-lookup"><span data-stu-id="d2bf3-112">This example uses the `Stop` statement to suspend execution for each iteration through the `For...Next` loop.</span></span>  
  
 [!code-vb[VbVbalrStatements#56](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#56)]  
  
## <a name="see-also"></a><span data-ttu-id="d2bf3-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d2bf3-113">See also</span></span>

- [<span data-ttu-id="d2bf3-114">End-Anweisung</span><span class="sxs-lookup"><span data-stu-id="d2bf3-114">End Statement</span></span>](../../../visual-basic/language-reference/statements/end-statement.md)
