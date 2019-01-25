---
title: Throw-Anweisung (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Throw
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
ms.openlocfilehash: 9af1436af950346eef572c34b9d42da3e8c8cf24
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54671160"
---
# <a name="throw-statement-visual-basic"></a><span data-ttu-id="6fe1c-102">Throw-Anweisung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6fe1c-102">Throw Statement (Visual Basic)</span></span>
<span data-ttu-id="6fe1c-103">Löst eine Ausnahme in einer Prozedur.</span><span class="sxs-lookup"><span data-stu-id="6fe1c-103">Throws an exception within a procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6fe1c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6fe1c-104">Syntax</span></span>  
  
```  
Throw [ expression ]  
```  
  
## <a name="part"></a><span data-ttu-id="6fe1c-105">Segment</span><span class="sxs-lookup"><span data-stu-id="6fe1c-105">Part</span></span>  
 `expression`  
 <span data-ttu-id="6fe1c-106">Enthält Informationen über die Ausnahme ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="6fe1c-106">Provides information about the exception to be thrown.</span></span> <span data-ttu-id="6fe1c-107">Optional, wenn im wohnen eine `Catch` -Anweisung, andernfalls erforderlich.</span><span class="sxs-lookup"><span data-stu-id="6fe1c-107">Optional when residing in a `Catch` statement, otherwise required.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6fe1c-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6fe1c-108">Remarks</span></span>  
 <span data-ttu-id="6fe1c-109">Die `Throw` -Anweisung löst eine Ausnahme, die Sie mit Code für die strukturierte Ausnahmebehandlung (`Try`... `Catch`... `Finally`) oder Code für die unstrukturierte Ausnahmebehandlung (`On Error GoTo`).</span><span class="sxs-lookup"><span data-stu-id="6fe1c-109">The `Throw` statement throws an exception that you can handle with structured exception-handling code (`Try`...`Catch`...`Finally`) or unstructured exception-handling code (`On Error GoTo`).</span></span> <span data-ttu-id="6fe1c-110">Sie können die `Throw` Anweisung, um Fehler in Ihrem Code abfangen, da es sich bei Visual Basic die Aufrufliste nach oben verschoben, bis den entsprechenden Code für die Behandlung von Ausnahmen gefunden.</span><span class="sxs-lookup"><span data-stu-id="6fe1c-110">You can use the `Throw` statement to trap errors within your code because Visual Basic moves up the call stack until it finds the appropriate exception-handling code.</span></span>  
  
 <span data-ttu-id="6fe1c-111">Ein `Throw` -Anweisung keinen Ausdruck kann nur verwendet werden, einem `Catch` -Anweisung, in dem Fall die Anweisung die Ausnahme, die gerade verarbeitet wird, indem Sie erneut die `Catch` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="6fe1c-111">A `Throw` statement with no expression can only be used in a `Catch` statement, in which case the statement rethrows the exception currently being handled by the `Catch` statement.</span></span>  
  
 <span data-ttu-id="6fe1c-112">Die `Throw` Anweisung setzt die Aufrufliste für den `expression` Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="6fe1c-112">The `Throw` statement resets the call stack for the `expression` exception.</span></span> <span data-ttu-id="6fe1c-113">Wenn `expression` nicht angegeben wird, die Aufrufliste unverändert.</span><span class="sxs-lookup"><span data-stu-id="6fe1c-113">If `expression` is not provided, the call stack is left unchanged.</span></span> <span data-ttu-id="6fe1c-114">Sie erreichen die Aufrufliste für die Ausnahme über die <xref:System.Exception.StackTrace%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="6fe1c-114">You can access the call stack for the exception through the <xref:System.Exception.StackTrace%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6fe1c-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6fe1c-115">Example</span></span>  
 <span data-ttu-id="6fe1c-116">Der folgende code verwendet die `Throw` Anweisung eine Ausnahme ausgelöst:</span><span class="sxs-lookup"><span data-stu-id="6fe1c-116">The following code uses the `Throw` statement to throw an exception:</span></span>  
  
 [!code-vb[VbVbalrStatements#84](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/throw-statement_1.vb)]  
  
## <a name="requirements"></a><span data-ttu-id="6fe1c-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6fe1c-117">Requirements</span></span>  
 <span data-ttu-id="6fe1c-118">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span><span class="sxs-lookup"><span data-stu-id="6fe1c-118">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span></span>  
  
 <span data-ttu-id="6fe1c-119">**Modul:** `Interaction`</span><span class="sxs-lookup"><span data-stu-id="6fe1c-119">**Module:** `Interaction`</span></span>  
  
 <span data-ttu-id="6fe1c-120">**Assembly:** Visual Basic Runtime Library (in Microsoft.VisualBasic.dll)</span><span class="sxs-lookup"><span data-stu-id="6fe1c-120">**Assembly:** Visual Basic Runtime Library (in Microsoft.VisualBasic.dll)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6fe1c-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6fe1c-121">See also</span></span>
- [<span data-ttu-id="6fe1c-122">Try...Catch...Finally-Anweisung</span><span class="sxs-lookup"><span data-stu-id="6fe1c-122">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [<span data-ttu-id="6fe1c-123">On Error-Anweisung</span><span class="sxs-lookup"><span data-stu-id="6fe1c-123">On Error Statement</span></span>](../../../visual-basic/language-reference/statements/on-error-statement.md)
