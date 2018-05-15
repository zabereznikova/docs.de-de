---
title: Resume-Anweisung
ms.date: 07/20/2015
f1_keywords:
- vb.Resume
- vb.ResumeNext
helpviewer_keywords:
- Next statement [Visual Basic], Resume
- Resume Next statement [Visual Basic]
- execution [Visual Basic], resuming
- run-time errors [Visual Basic], resuming after
- Resume statement [Visual Basic], syntax
- errors [Visual Basic], resuming after
- Error statement [Visual Basic], and Resume statement
- execution
- Resume statement [Visual Basic]
ms.assetid: e24d058b-1a5c-4274-acb9-7d295d3ea537
ms.openlocfilehash: 1d03f631893be51529f29af824de0d684bf43804
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="resume-statement"></a><span data-ttu-id="56134-102">Resume-Anweisung</span><span class="sxs-lookup"><span data-stu-id="56134-102">Resume Statement</span></span>
<span data-ttu-id="56134-103">Setzt die Ausführung fort, nachdem eine Fehlerbehandlungsroutine abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="56134-103">Resumes execution after an error-handling routine is finished.</span></span>  
  
 <span data-ttu-id="56134-104">Es wird empfohlen, strukturierte Ausnahmebehandlung im Code nach Möglichkeit statt mit der unstrukturierten Ausnahmebehandlung zu verwenden und die `On Error` und `Resume` Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="56134-104">We suggest that you use structured exception handling in your code whenever possible, rather than using unstructured exception handling and the `On Error` and `Resume` statements.</span></span> <span data-ttu-id="56134-105">Weitere Informationen finden Sie unter [Try...Catch...Finally-Anweisung](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span><span class="sxs-lookup"><span data-stu-id="56134-105">For more information, see [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56134-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="56134-106">Syntax</span></span>  
  
```  
Resume [ Next | line ]  
```  
  
## <a name="parts"></a><span data-ttu-id="56134-107">Teile</span><span class="sxs-lookup"><span data-stu-id="56134-107">Parts</span></span>  
 `Resume`  
 <span data-ttu-id="56134-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="56134-108">Required.</span></span> <span data-ttu-id="56134-109">Wenn in der gleichen Prozedur wie der Fehlerhandler der Fehler aufgetreten ist, setzt die Ausführung mit der Anweisung, die den Fehler verursacht hat.</span><span class="sxs-lookup"><span data-stu-id="56134-109">If the error occurred in the same procedure as the error handler, execution resumes with the statement that caused the error.</span></span> <span data-ttu-id="56134-110">Wenn der Fehler in einer aufgerufenen Prozedur setzt die Ausführung bei der Anweisung, die zuletzt aus der Prozedur mit der Fehlerbehandlungsroutine aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="56134-110">If the error occurred in a called procedure, execution resumes at the statement that last called out of the procedure containing the error-handling routine.</span></span>  
  
 `Next`  
 <span data-ttu-id="56134-111">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="56134-111">Optional.</span></span> <span data-ttu-id="56134-112">Wenn in der gleichen Prozedur wie der Fehlerhandler der Fehler aufgetreten ist, setzt die Ausführung mit der Anweisung sofort nach der Anweisung, die den Fehler verursacht hat.</span><span class="sxs-lookup"><span data-stu-id="56134-112">If the error occurred in the same procedure as the error handler, execution resumes with the statement immediately following the statement that caused the error.</span></span> <span data-ttu-id="56134-113">Wenn der Fehler in einer aufgerufenen Prozedur die Ausführung wird fortgesetzt, mit der Anweisung sofort nach der Anweisung, die zuletzt aus der Prozedur mit der Fehlerbehandlungsroutine aufgerufen (oder `On Error Resume Next` Anweisung).</span><span class="sxs-lookup"><span data-stu-id="56134-113">If the error occurred in a called procedure, execution resumes with the statement immediately following the statement that last called out of the procedure containing the error-handling routine (or `On Error Resume Next` statement).</span></span>  
  
 `line`  
 <span data-ttu-id="56134-114">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="56134-114">Optional.</span></span> <span data-ttu-id="56134-115">Die Ausführung wird fortgesetzt, in der Befehlszeile angegeben werden, in das erforderliche `line` Argument.</span><span class="sxs-lookup"><span data-stu-id="56134-115">Execution resumes at the line specified in the required `line` argument.</span></span> <span data-ttu-id="56134-116">Die `line` Argument ist eine zeilenbezeichnung oder Zeilennummer und muss in der gleichen Prozedur wie der Fehlerhandler.</span><span class="sxs-lookup"><span data-stu-id="56134-116">The `line` argument is a line label or line number and must be in the same procedure as the error handler.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="56134-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="56134-117">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="56134-118">Wir empfehlen die Verwendung von strukturierter Ausnahmebehandlung im Code nach Möglichkeit statt mit der unstrukturierten Ausnahmebehandlung und das `On Error` und `Resume` Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="56134-118">We recommend that you use structured exception handling in your code whenever possible, rather than using unstructured exception handling and the `On Error` and `Resume` statements.</span></span> <span data-ttu-id="56134-119">Weitere Informationen finden Sie unter [Try...Catch...Finally-Anweisung](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span><span class="sxs-lookup"><span data-stu-id="56134-119">For more information, see [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span>  
  
 <span data-ttu-id="56134-120">Bei Verwendung einer `Resume` Anweisung überall außer in eine Fehlerbehandlungsroutine, ein Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="56134-120">If you use a `Resume` statement anywhere other than in an error-handling routine, an error occurs.</span></span>  
  
 <span data-ttu-id="56134-121">Die `Resume` Anweisung kann nicht verwendet werden, in einer Prozedur, deren enthält eine `Try...Catch...Finally` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="56134-121">The `Resume` statement cannot be used in any procedure that contains a `Try...Catch...Finally` statement.</span></span>  
  
## <a name="example"></a><span data-ttu-id="56134-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="56134-122">Example</span></span>  
 <span data-ttu-id="56134-123">Dieses Beispiel verwendet die `Resume` Anweisung für die Fehlerbehandlung in einer Prozedur zu beenden, und klicken Sie dann fortsetzen Ausführung mit der Anweisung, die den Fehler verursacht hat.</span><span class="sxs-lookup"><span data-stu-id="56134-123">This example uses the `Resume` statement to end error handling in a procedure and then resume execution with the statement that caused the error.</span></span> <span data-ttu-id="56134-124">Fehlernummer 55 generiert, um die Verwendung der veranschaulichen die `Resume` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="56134-124">Error number 55 is generated to illustrate use of the `Resume` statement.</span></span>  
  
 [!code-vb[VbVbalrErrorHandling#16](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/resume-statement_1.vb)]  
  
## <a name="requirements"></a><span data-ttu-id="56134-125">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="56134-125">Requirements</span></span>  
 <span data-ttu-id="56134-126">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span><span class="sxs-lookup"><span data-stu-id="56134-126">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span></span>  
  
 <span data-ttu-id="56134-127">**Assembly:** Visual Basic-Laufzeitbibliothek (in "Microsoft.VisualBasic.dll")</span><span class="sxs-lookup"><span data-stu-id="56134-127">**Assembly:** Visual Basic Runtime Library (in Microsoft.VisualBasic.dll)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56134-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="56134-128">See Also</span></span>  
 [<span data-ttu-id="56134-129">Try...Catch...Finally-Anweisung</span><span class="sxs-lookup"><span data-stu-id="56134-129">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)  
 [<span data-ttu-id="56134-130">Error-Anweisung</span><span class="sxs-lookup"><span data-stu-id="56134-130">Error Statement</span></span>](../../../visual-basic/language-reference/statements/error-statement.md)  
 [<span data-ttu-id="56134-131">On Error-Anweisung</span><span class="sxs-lookup"><span data-stu-id="56134-131">On Error Statement</span></span>](../../../visual-basic/language-reference/statements/on-error-statement.md)
