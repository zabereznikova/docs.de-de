---
title: Resume-Anweisung (Visual Basic)
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
ms.openlocfilehash: 796342d17b0d0f1a642aff381274746d1fda3559
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61783915"
---
# <a name="resume-statement"></a><span data-ttu-id="dcd6a-102">Resume-Anweisung</span><span class="sxs-lookup"><span data-stu-id="dcd6a-102">Resume Statement</span></span>
<span data-ttu-id="dcd6a-103">Setzt die Ausführung fort, nachdem eine Fehlerbehandlungsroutine abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="dcd6a-103">Resumes execution after an error-handling routine is finished.</span></span>  
  
 <span data-ttu-id="dcd6a-104">Es wird empfohlen, dass Sie die strukturierte Ausnahmebehandlung im Code nach Möglichkeit anstelle der Verwendung nicht strukturierte Ausnahmebehandlung verwenden und die `On Error` und `Resume` Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="dcd6a-104">We suggest that you use structured exception handling in your code whenever possible, rather than using unstructured exception handling and the `On Error` and `Resume` statements.</span></span> <span data-ttu-id="dcd6a-105">Weitere Informationen finden Sie unter [Try...Catch...Finally-Anweisung](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span><span class="sxs-lookup"><span data-stu-id="dcd6a-105">For more information, see [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dcd6a-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="dcd6a-106">Syntax</span></span>  
  
```  
Resume [ Next | line ]  
```  
  
## <a name="parts"></a><span data-ttu-id="dcd6a-107">Teile</span><span class="sxs-lookup"><span data-stu-id="dcd6a-107">Parts</span></span>  
 `Resume`  
 <span data-ttu-id="dcd6a-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="dcd6a-108">Required.</span></span> <span data-ttu-id="dcd6a-109">Wenn der Fehler in der gleichen Prozedur wie der Fehlerhandler, setzt die Ausführung mit der Anweisung, die den Fehler verursacht hat.</span><span class="sxs-lookup"><span data-stu-id="dcd6a-109">If the error occurred in the same procedure as the error handler, execution resumes with the statement that caused the error.</span></span> <span data-ttu-id="dcd6a-110">Wenn der Fehler in einer aufgerufenen Prozedur setzt die Ausführung bei der Anweisung, die aus der Prozedur die Fehlerbehandlungsroutine mit dem letzten Aufruf.</span><span class="sxs-lookup"><span data-stu-id="dcd6a-110">If the error occurred in a called procedure, execution resumes at the statement that last called out of the procedure containing the error-handling routine.</span></span>  
  
 `Next`  
 <span data-ttu-id="dcd6a-111">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="dcd6a-111">Optional.</span></span> <span data-ttu-id="dcd6a-112">Wenn der Fehler in der gleichen Prozedur wie der Fehlerhandler, setzt die Ausführung mit der Anweisung sofort nach der Anweisung, die den Fehler verursacht hat.</span><span class="sxs-lookup"><span data-stu-id="dcd6a-112">If the error occurred in the same procedure as the error handler, execution resumes with the statement immediately following the statement that caused the error.</span></span> <span data-ttu-id="dcd6a-113">Wenn der Fehler in einer aufgerufenen Prozedur Ausführung fortgesetzt wird, mit der Anweisung sofort nach der Anweisung, die aus der Prozedur die Fehlerbehandlungsroutine mit dem letzten Aufruf (oder `On Error Resume Next` Anweisung).</span><span class="sxs-lookup"><span data-stu-id="dcd6a-113">If the error occurred in a called procedure, execution resumes with the statement immediately following the statement that last called out of the procedure containing the error-handling routine (or `On Error Resume Next` statement).</span></span>  
  
 `line`  
 <span data-ttu-id="dcd6a-114">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="dcd6a-114">Optional.</span></span> <span data-ttu-id="dcd6a-115">Ausführung fortgesetzt wird, in der Zeile, die in die erforderlichen angegebenen `line` Argument.</span><span class="sxs-lookup"><span data-stu-id="dcd6a-115">Execution resumes at the line specified in the required `line` argument.</span></span> <span data-ttu-id="dcd6a-116">Die `line` Argument ist eine zeilenbezeichnung oder Zeilennummer und muss in der gleichen Prozedur wie der Fehlerhandler.</span><span class="sxs-lookup"><span data-stu-id="dcd6a-116">The `line` argument is a line label or line number and must be in the same procedure as the error handler.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dcd6a-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="dcd6a-117">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dcd6a-118">Es wird empfohlen, dass Sie die strukturierte Ausnahmebehandlung im Code nach Möglichkeit anstelle der Verwendung nicht strukturierte Ausnahmebehandlung verwenden und die `On Error` und `Resume` Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="dcd6a-118">We recommend that you use structured exception handling in your code whenever possible, rather than using unstructured exception handling and the `On Error` and `Resume` statements.</span></span> <span data-ttu-id="dcd6a-119">Weitere Informationen finden Sie unter [Try...Catch...Finally-Anweisung](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span><span class="sxs-lookup"><span data-stu-id="dcd6a-119">For more information, see [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span>  
  
 <span data-ttu-id="dcd6a-120">Bei Verwendung einer `Resume` Anweisung überall außer in einer Fehlerbehandlungsroutine, ein Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="dcd6a-120">If you use a `Resume` statement anywhere other than in an error-handling routine, an error occurs.</span></span>  
  
 <span data-ttu-id="dcd6a-121">Die `Resume` Anweisung kann nicht verwendet werden, in einer beliebigen Prozedur, die enthält eine `Try...Catch...Finally` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="dcd6a-121">The `Resume` statement cannot be used in any procedure that contains a `Try...Catch...Finally` statement.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dcd6a-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="dcd6a-122">Example</span></span>  
 <span data-ttu-id="dcd6a-123">Dieses Beispiel verwendet die `Resume` Anweisung, um die Fehlerbehandlung in einer Prozedur beendet, und klicken Sie dann fortsetzen Ausführung mit der Anweisung, die den Fehler verursacht hat.</span><span class="sxs-lookup"><span data-stu-id="dcd6a-123">This example uses the `Resume` statement to end error handling in a procedure and then resume execution with the statement that caused the error.</span></span> <span data-ttu-id="dcd6a-124">Fehlernummer 55 wird generiert, um die Verwendung von veranschaulichen die `Resume` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="dcd6a-124">Error number 55 is generated to illustrate use of the `Resume` statement.</span></span>  
  
 [!code-vb[VbVbalrErrorHandling#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrErrorHandling/VB/Class1.vb#16)]  
  
## <a name="requirements"></a><span data-ttu-id="dcd6a-125">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="dcd6a-125">Requirements</span></span>  
 <span data-ttu-id="dcd6a-126">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span><span class="sxs-lookup"><span data-stu-id="dcd6a-126">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span></span>  
  
 <span data-ttu-id="dcd6a-127">**Assembly:** Visual Basic Runtime Library (in Microsoft.VisualBasic.dll)</span><span class="sxs-lookup"><span data-stu-id="dcd6a-127">**Assembly:** Visual Basic Runtime Library (in Microsoft.VisualBasic.dll)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dcd6a-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dcd6a-128">See also</span></span>

- [<span data-ttu-id="dcd6a-129">Try...Catch...Finally-Anweisung</span><span class="sxs-lookup"><span data-stu-id="dcd6a-129">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [<span data-ttu-id="dcd6a-130">Error-Anweisung</span><span class="sxs-lookup"><span data-stu-id="dcd6a-130">Error Statement</span></span>](../../../visual-basic/language-reference/statements/error-statement.md)
- [<span data-ttu-id="dcd6a-131">On Error-Anweisung</span><span class="sxs-lookup"><span data-stu-id="dcd6a-131">On Error Statement</span></span>](../../../visual-basic/language-reference/statements/on-error-statement.md)
