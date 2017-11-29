---
title: Return-Anweisung (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.Return
helpviewer_keywords:
- Return statement [Visual Basic], syntax
- control flow [Visual Basic], returning control to expressions
- Return statement [Visual Basic]
- expressions [Visual Basic], returning control to
ms.assetid: ac86e7f0-5a67-42c3-9834-0e0381efa3ec
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b66d16a249164b8989f05f10c785b97055bfde9e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="return-statement-visual-basic"></a><span data-ttu-id="8648b-102">Return-Anweisung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8648b-102">Return Statement (Visual Basic)</span></span>
<span data-ttu-id="8648b-103">Die Steuerung an den Code, aufgerufen zurückgegeben eine `Function`, `Sub`, `Get`, `Set`, oder `Operator` Prozedur.</span><span class="sxs-lookup"><span data-stu-id="8648b-103">Returns control to the code that called a `Function`, `Sub`, `Get`, `Set`, or `Operator` procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8648b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8648b-104">Syntax</span></span>  
  
```  
Return  
-or-  
Return expression  
```  
  
## <a name="part"></a><span data-ttu-id="8648b-105">Segment</span><span class="sxs-lookup"><span data-stu-id="8648b-105">Part</span></span>  
 `expression`  
 <span data-ttu-id="8648b-106">Erforderlich einer `Function`, `Get`, oder `Operator` Prozedur.</span><span class="sxs-lookup"><span data-stu-id="8648b-106">Required in a `Function`, `Get`, or `Operator` procedure.</span></span> <span data-ttu-id="8648b-107">Der Ausdruck den Wert an den aufrufenden Code zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="8648b-107">Expression that represents the value to be returned to the calling code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8648b-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8648b-108">Remarks</span></span>  
 <span data-ttu-id="8648b-109">In einer `Sub` oder `Set` Prozedur, die `Return` Anweisung entspricht einer `Exit Sub` oder `Exit Property` -Anweisung und `expression` muss nicht angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="8648b-109">In a `Sub` or `Set` procedure, the `Return` statement is equivalent to an `Exit Sub` or `Exit Property` statement, and `expression` must not be supplied.</span></span>  
  
 <span data-ttu-id="8648b-110">In einem `Function`, `Get`, oder `Operator` Prozedur, die `Return` -Anweisung muss enthalten `expression`, und `expression` muss in einen Datentyp, der in den Rückgabetyp der Prozedur konvertiert werden ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="8648b-110">In a `Function`, `Get`, or `Operator` procedure, the `Return` statement must include `expression`, and `expression` must evaluate to a data type that is convertible to the return type of the procedure.</span></span> <span data-ttu-id="8648b-111">In einem `Function` oder `Get` Prozedur, Sie haben auch die Alternative einen Ausdruck zuweisen, um den Namen der Prozedur, die als Rückgabewert dient, und klicken Sie dann Ausführen einer `Exit Function` oder `Exit Property` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="8648b-111">In a `Function` or `Get` procedure, you also have the alternative of assigning an expression to the procedure name to serve as the return value, and then executing an `Exit Function` or `Exit Property` statement.</span></span> <span data-ttu-id="8648b-112">In einer `Operator` Verfahren verwenden Sie `Return``expression`.</span><span class="sxs-lookup"><span data-stu-id="8648b-112">In an `Operator` procedure, you must use `Return``expression`.</span></span>  
  
 <span data-ttu-id="8648b-113">Sie können beliebig viele einschließen `Return` Anweisungen nach Bedarf in der gleichen Prozedur.</span><span class="sxs-lookup"><span data-stu-id="8648b-113">You can include as many `Return` statements as appropriate in the same procedure.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8648b-114">Der Code in eine `Finally` Block ausgeführt wird, nachdem ein `Return` -Anweisung in einer `Try` oder `Catch` Block ist aufgetreten, aber vor, `Return` -Anweisung ausführt.</span><span class="sxs-lookup"><span data-stu-id="8648b-114">The code in a `Finally` block runs after a `Return` statement in a `Try` or `Catch` block is encountered, but before that `Return` statement executes.</span></span> <span data-ttu-id="8648b-115">Ein `Return` -Anweisung kann nicht eingefügt werden, einem `Finally` Block.</span><span class="sxs-lookup"><span data-stu-id="8648b-115">A `Return` statement cannot be included in a `Finally` block.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8648b-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8648b-116">Example</span></span>  
 <span data-ttu-id="8648b-117">Im folgenden Beispiel wird die `Return` Anweisung mehrmals an den aufrufenden Code zurückgegeben werden soll, wenn die Prozedur keinen nichts weiter tun.</span><span class="sxs-lookup"><span data-stu-id="8648b-117">The following example uses the `Return` statement several times to return to the calling code when the procedure does not have to do anything else.</span></span>  
  
 [!code-vb[VbVbalrStatements#53](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/return-statement_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="8648b-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8648b-118">See Also</span></span>  
 [<span data-ttu-id="8648b-119">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="8648b-119">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
 [<span data-ttu-id="8648b-120">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="8648b-120">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [<span data-ttu-id="8648b-121">Get-Anweisung</span><span class="sxs-lookup"><span data-stu-id="8648b-121">Get Statement</span></span>](../../../visual-basic/language-reference/statements/get-statement.md)  
 [<span data-ttu-id="8648b-122">Set-Anweisung</span><span class="sxs-lookup"><span data-stu-id="8648b-122">Set Statement</span></span>](../../../visual-basic/language-reference/statements/set-statement.md)  
 [<span data-ttu-id="8648b-123">Operator-Anweisung</span><span class="sxs-lookup"><span data-stu-id="8648b-123">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)  
 [<span data-ttu-id="8648b-124">Property-Anweisung</span><span class="sxs-lookup"><span data-stu-id="8648b-124">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
 [<span data-ttu-id="8648b-125">Exit-Anweisung</span><span class="sxs-lookup"><span data-stu-id="8648b-125">Exit Statement</span></span>](../../../visual-basic/language-reference/statements/exit-statement.md)  
 [<span data-ttu-id="8648b-126">Try...Catch...Finally-Anweisung</span><span class="sxs-lookup"><span data-stu-id="8648b-126">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
