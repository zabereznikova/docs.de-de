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
ms.openlocfilehash: 95137a9f6a4a4a18655b51b95300bfaf93cca193
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74333030"
---
# <a name="resume-statement"></a><span data-ttu-id="4fc18-102">Resume-Anweisung</span><span class="sxs-lookup"><span data-stu-id="4fc18-102">Resume Statement</span></span>
<span data-ttu-id="4fc18-103">Setzt die Ausführung fort, nachdem eine Fehler Behandlungs Routine abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="4fc18-103">Resumes execution after an error-handling routine is finished.</span></span>  
  
 <span data-ttu-id="4fc18-104">Es wird empfohlen, dass Sie nach Möglichkeit eine strukturierte Ausnahmebehandlung in Ihrem Code verwenden, anstatt eine unstrukturierte Ausnahmebehandlung und die Anweisungen `On Error` und `Resume` zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="4fc18-104">We suggest that you use structured exception handling in your code whenever possible, rather than using unstructured exception handling and the `On Error` and `Resume` statements.</span></span> <span data-ttu-id="4fc18-105">Weitere Informationen finden Sie unter [Try...Catch...Finally-Anweisung](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span><span class="sxs-lookup"><span data-stu-id="4fc18-105">For more information, see [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4fc18-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="4fc18-106">Syntax</span></span>  
  
```vb  
Resume [ Next | line ]  
```  
  
## <a name="parts"></a><span data-ttu-id="4fc18-107">-Komponenten</span><span class="sxs-lookup"><span data-stu-id="4fc18-107">Parts</span></span>  
 `Resume`  
 <span data-ttu-id="4fc18-108">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="4fc18-108">Required.</span></span> <span data-ttu-id="4fc18-109">Wenn der Fehler in derselben Prozedur wie der Fehlerhandler aufgetreten ist, wird die Ausführung mit der Anweisung fortgesetzt, die den Fehler verursacht hat.</span><span class="sxs-lookup"><span data-stu-id="4fc18-109">If the error occurred in the same procedure as the error handler, execution resumes with the statement that caused the error.</span></span> <span data-ttu-id="4fc18-110">Wenn der Fehler in einer aufgerufenen Prozedur aufgetreten ist, wird die Ausführung bei der Anweisung fortgesetzt, die zuletzt von der Prozedur mit der Fehler Behandlungs Routine aufgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="4fc18-110">If the error occurred in a called procedure, execution resumes at the statement that last called out of the procedure containing the error-handling routine.</span></span>  
  
 `Next`  
 <span data-ttu-id="4fc18-111">Optional.</span><span class="sxs-lookup"><span data-stu-id="4fc18-111">Optional.</span></span> <span data-ttu-id="4fc18-112">Wenn der Fehler in derselben Prozedur wie der Fehlerhandler aufgetreten ist, wird die Ausführung mit der Anweisung unmittelbar nach der Anweisung fortgesetzt, die den Fehler verursacht hat.</span><span class="sxs-lookup"><span data-stu-id="4fc18-112">If the error occurred in the same procedure as the error handler, execution resumes with the statement immediately following the statement that caused the error.</span></span> <span data-ttu-id="4fc18-113">Wenn der Fehler in einer aufgerufenen Prozedur aufgetreten ist, wird die Ausführung mit der Anweisung unmittelbar nach der Anweisung fortgesetzt, die zuletzt von der Prozedur mit der Fehler Behandlungs Routine (oder `On Error Resume Next` Anweisung) aufgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="4fc18-113">If the error occurred in a called procedure, execution resumes with the statement immediately following the statement that last called out of the procedure containing the error-handling routine (or `On Error Resume Next` statement).</span></span>  
  
 `line`  
 <span data-ttu-id="4fc18-114">Optional.</span><span class="sxs-lookup"><span data-stu-id="4fc18-114">Optional.</span></span> <span data-ttu-id="4fc18-115">Die Ausführung wird in der Zeile fortgesetzt, die im erforderlichen `line` Argument angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="4fc18-115">Execution resumes at the line specified in the required `line` argument.</span></span> <span data-ttu-id="4fc18-116">Das `line`-Argument ist eine Zeilen Bezeichnung oder Zeilennummer und muss sich in derselben Prozedur wie der Fehlerhandler befinden.</span><span class="sxs-lookup"><span data-stu-id="4fc18-116">The `line` argument is a line label or line number and must be in the same procedure as the error handler.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4fc18-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4fc18-117">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4fc18-118">Es empfiehlt sich, nach Möglichkeit eine strukturierte Ausnahmebehandlung in Ihrem Code zu verwenden, anstatt eine unstrukturierte Ausnahmebehandlung und die Anweisungen `On Error` und `Resume` zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="4fc18-118">We recommend that you use structured exception handling in your code whenever possible, rather than using unstructured exception handling and the `On Error` and `Resume` statements.</span></span> <span data-ttu-id="4fc18-119">Weitere Informationen finden Sie unter [Try...Catch...Finally-Anweisung](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span><span class="sxs-lookup"><span data-stu-id="4fc18-119">For more information, see [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span>  
  
 <span data-ttu-id="4fc18-120">Wenn Sie eine `Resume`-Anweisung an einer anderen Stelle als in einer Fehler Behandlungs Routine verwenden, tritt ein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="4fc18-120">If you use a `Resume` statement anywhere other than in an error-handling routine, an error occurs.</span></span>  
  
 <span data-ttu-id="4fc18-121">Die `Resume`-Anweisung kann nicht in Prozeduren verwendet werden, die eine `Try...Catch...Finally`-Anweisung enthalten.</span><span class="sxs-lookup"><span data-stu-id="4fc18-121">The `Resume` statement cannot be used in any procedure that contains a `Try...Catch...Finally` statement.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4fc18-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4fc18-122">Example</span></span>  
 <span data-ttu-id="4fc18-123">In diesem Beispiel wird die `Resume`-Anweisung verwendet, um die Fehlerbehandlung in einer Prozedur zu beenden und dann die Ausführung mit der Anweisung fortzusetzen, die den Fehler verursacht hat</span><span class="sxs-lookup"><span data-stu-id="4fc18-123">This example uses the `Resume` statement to end error handling in a procedure and then resume execution with the statement that caused the error.</span></span> <span data-ttu-id="4fc18-124">Die Fehlernummer 55 wird generiert, um die Verwendung der `Resume`-Anweisung zu veranschaulichen.</span><span class="sxs-lookup"><span data-stu-id="4fc18-124">Error number 55 is generated to illustrate use of the `Resume` statement.</span></span>  
  
 [!code-vb[VbVbalrErrorHandling#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrErrorHandling/VB/Class1.vb#16)]  
  
## <a name="requirements"></a><span data-ttu-id="4fc18-125">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="4fc18-125">Requirements</span></span>  
 <span data-ttu-id="4fc18-126">**Namespace:** [Microsoft. VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span><span class="sxs-lookup"><span data-stu-id="4fc18-126">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span></span>  
  
 <span data-ttu-id="4fc18-127">**Assembly:** Visual Basic-Lauf Zeit Bibliothek (in "Microsoft. VisualBasic. dll")</span><span class="sxs-lookup"><span data-stu-id="4fc18-127">**Assembly:** Visual Basic Runtime Library (in Microsoft.VisualBasic.dll)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4fc18-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4fc18-128">See also</span></span>

- [<span data-ttu-id="4fc18-129">Try...Catch...Finally-Anweisung</span><span class="sxs-lookup"><span data-stu-id="4fc18-129">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [<span data-ttu-id="4fc18-130">Error-Anweisung</span><span class="sxs-lookup"><span data-stu-id="4fc18-130">Error Statement</span></span>](../../../visual-basic/language-reference/statements/error-statement.md)
- [<span data-ttu-id="4fc18-131">On Error-Anweisung</span><span class="sxs-lookup"><span data-stu-id="4fc18-131">On Error Statement</span></span>](../../../visual-basic/language-reference/statements/on-error-statement.md)
