---
title: Throw-Anweisung (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.Throw
helpviewer_keywords:
- structured exception handling, throw statements
- try-catch exception handling, throw statements
- throw statement [Visual Basic], about throw statements
- throwing exceptions, throw statement
- exception handling, throw statement
- On Error statement [Visual Basic], throwing exceptions
- throwing exceptions
- exception handling, unstructured
- throw statement [Visual Basic]
ms.assetid: a6e07406-5c8a-4498-87a2-8339f3651d62
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 50ada551c32b8296f0dad2ae929ca9c81a14a711
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="throw-statement-visual-basic"></a><span data-ttu-id="0cdb6-102">Throw-Anweisung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0cdb6-102">Throw Statement (Visual Basic)</span></span>
<span data-ttu-id="0cdb6-103">Löst eine Ausnahme innerhalb einer Prozedur.</span><span class="sxs-lookup"><span data-stu-id="0cdb6-103">Throws an exception within a procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0cdb6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0cdb6-104">Syntax</span></span>  
  
```  
Throw [ expression ]  
```  
  
## <a name="part"></a><span data-ttu-id="0cdb6-105">Segment</span><span class="sxs-lookup"><span data-stu-id="0cdb6-105">Part</span></span>  
 `expression`  
 <span data-ttu-id="0cdb6-106">Enthält Informationen über die Ausnahme ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="0cdb6-106">Provides information about the exception to be thrown.</span></span> <span data-ttu-id="0cdb6-107">Optional, wenn im wohnen eine `Catch` -Anweisung, ansonsten erforderlich.</span><span class="sxs-lookup"><span data-stu-id="0cdb6-107">Optional when residing in a `Catch` statement, otherwise required.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0cdb6-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0cdb6-108">Remarks</span></span>  
 <span data-ttu-id="0cdb6-109">Die `Throw` -Anweisung löst eine Ausnahme, die Sie, mit dem Code für die strukturierte Ausnahmebehandlung behandeln können (`Try`... `Catch`... `Finally`) oder Code für die unstrukturierte Ausnahmebehandlung (`On Error GoTo`).</span><span class="sxs-lookup"><span data-stu-id="0cdb6-109">The `Throw` statement throws an exception that you can handle with structured exception-handling code (`Try`...`Catch`...`Finally`) or unstructured exception-handling code (`On Error GoTo`).</span></span> <span data-ttu-id="0cdb6-110">Sie können die `Throw` Anweisung, um Fehler im Code abfangen, da Visual Basic der Aufrufliste verschoben, bis die entsprechenden Ausnahmebehandlungscode gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="0cdb6-110">You can use the `Throw` statement to trap errors within your code because Visual Basic moves up the call stack until it finds the appropriate exception-handling code.</span></span>  
  
 <span data-ttu-id="0cdb6-111">Ein `Throw` Anweisung ohne Ausdruck kann nur verwendet werden, einem `Catch` -Anweisung, in dem Fall die Anweisung die Ausnahme, die gerade verarbeitet wird löst, indem Sie die `Catch` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="0cdb6-111">A `Throw` statement with no expression can only be used in a `Catch` statement, in which case the statement rethrows the exception currently being handled by the `Catch` statement.</span></span>  
  
 <span data-ttu-id="0cdb6-112">Die `Throw` Anweisung setzt die Aufrufliste für die `expression` Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="0cdb6-112">The `Throw` statement resets the call stack for the `expression` exception.</span></span> <span data-ttu-id="0cdb6-113">Wenn `expression` nicht angegeben wird, die Aufrufliste unverändert.</span><span class="sxs-lookup"><span data-stu-id="0cdb6-113">If `expression` is not provided, the call stack is left unchanged.</span></span> <span data-ttu-id="0cdb6-114">Sie erreichen die Aufrufliste für die Ausnahme über die <xref:System.Exception.StackTrace%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="0cdb6-114">You can access the call stack for the exception through the <xref:System.Exception.StackTrace%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0cdb6-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0cdb6-115">Example</span></span>  
 <span data-ttu-id="0cdb6-116">Der folgende code verwendet die `Throw` Anweisung eine Ausnahme ausgelöst:</span><span class="sxs-lookup"><span data-stu-id="0cdb6-116">The following code uses the `Throw` statement to throw an exception:</span></span>  
  
 [!code-vb[VbVbalrStatements#84](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/throw-statement_1.vb)]  
  
## <a name="requirements"></a><span data-ttu-id="0cdb6-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0cdb6-117">Requirements</span></span>  
 <span data-ttu-id="0cdb6-118">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span><span class="sxs-lookup"><span data-stu-id="0cdb6-118">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span></span>  
  
 <span data-ttu-id="0cdb6-119">**Modul:**`Interaction`</span><span class="sxs-lookup"><span data-stu-id="0cdb6-119">**Module:** `Interaction`</span></span>  
  
 <span data-ttu-id="0cdb6-120">**Assembly:** Visual Basic-Laufzeitbibliothek (in "Microsoft.VisualBasic.dll")</span><span class="sxs-lookup"><span data-stu-id="0cdb6-120">**Assembly:** Visual Basic Runtime Library (in Microsoft.VisualBasic.dll)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0cdb6-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0cdb6-121">See Also</span></span>  
 [<span data-ttu-id="0cdb6-122">Try...Catch...Finally-Anweisung</span><span class="sxs-lookup"><span data-stu-id="0cdb6-122">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)  
 [<span data-ttu-id="0cdb6-123">On Error-Anweisung</span><span class="sxs-lookup"><span data-stu-id="0cdb6-123">On Error Statement</span></span>](../../../visual-basic/language-reference/statements/on-error-statement.md)
