---
title: Call-Anweisung (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.Call
helpviewer_keywords:
- procedures [Visual Basic], Call statement
- Call statement [Visual Basic]
- procedures [Visual Basic], calling
ms.assetid: e5b31571-6867-406f-b8e7-a3f9aae4723a
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c72450fd6f931f36f640d3e384a6fd38d57a7a23
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="call-statement-visual-basic"></a><span data-ttu-id="8e7a5-102">Call-Anweisung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8e7a5-102">Call Statement (Visual Basic)</span></span>
<span data-ttu-id="8e7a5-103">Überträgt die Steuerung an eine `Function`, `Sub`, oder eine Dynamic Link Library (DLL)-Prozedur.</span><span class="sxs-lookup"><span data-stu-id="8e7a5-103">Transfers control to a `Function`, `Sub`, or dynamic-link library (DLL) procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e7a5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8e7a5-104">Syntax</span></span>  
  
```  
[ Call ] procedureName [ (argumentList) ]  
```  
  
## <a name="parts"></a><span data-ttu-id="8e7a5-105">Teile</span><span class="sxs-lookup"><span data-stu-id="8e7a5-105">Parts</span></span>  
 `procedureName`  
 <span data-ttu-id="8e7a5-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="8e7a5-106">Required.</span></span> <span data-ttu-id="8e7a5-107">Der Name der Prozedur aufrufen.</span><span class="sxs-lookup"><span data-stu-id="8e7a5-107">Name of the procedure to call.</span></span>  
  
 `argumentList`  
 <span data-ttu-id="8e7a5-108">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="8e7a5-108">Optional.</span></span> <span data-ttu-id="8e7a5-109">Liste der Variablen oder Ausdrücke, die Argumente, die an die Prozedur übergeben werden, wenn sie aufgerufen wird, darstellt.</span><span class="sxs-lookup"><span data-stu-id="8e7a5-109">List of variables or expressions representing arguments that are passed to the procedure when it is called.</span></span> <span data-ttu-id="8e7a5-110">Mehrere Argumente werden durch Kommas getrennt.</span><span class="sxs-lookup"><span data-stu-id="8e7a5-110">Multiple arguments are separated by commas.</span></span> <span data-ttu-id="8e7a5-111">Wenn Sie aufnehmen `argumentList`, müssen Sie es in Klammern einschließen.</span><span class="sxs-lookup"><span data-stu-id="8e7a5-111">If you include `argumentList`, you must enclose it in parentheses.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8e7a5-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8e7a5-112">Remarks</span></span>  
 <span data-ttu-id="8e7a5-113">Sie können die `Call` -Schlüsselwort, wenn Sie eine Prozedur aufrufen.</span><span class="sxs-lookup"><span data-stu-id="8e7a5-113">You can use the `Call` keyword when you call a procedure.</span></span> <span data-ttu-id="8e7a5-114">Für die meisten Prozeduraufrufe müssen Sie keine dieses Schlüsselwort verwenden.</span><span class="sxs-lookup"><span data-stu-id="8e7a5-114">For most procedure calls, you aren’t required to use this  keyword.</span></span>  
  
 <span data-ttu-id="8e7a5-115">In der Regel die `Call` -Schlüsselwort, wenn der aufgerufene Ausdruck nicht mit einem Bezeichner gestartet.</span><span class="sxs-lookup"><span data-stu-id="8e7a5-115">You typically use the `Call` keyword when the called expression doesn’t start with an identifier.</span></span> <span data-ttu-id="8e7a5-116">Verwenden der `Call` Schlüsselwort für andere Zwecke nicht empfohlen.</span><span class="sxs-lookup"><span data-stu-id="8e7a5-116">Use of the `Call` keyword for other uses isn’t recommended.</span></span>  
  
 <span data-ttu-id="8e7a5-117">Wenn die Prozedur einen Wert zurückgibt, der `Call` Anweisung wird diese verworfen.</span><span class="sxs-lookup"><span data-stu-id="8e7a5-117">If the procedure returns a value, the `Call` statement discards it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8e7a5-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8e7a5-118">Example</span></span>  
 <span data-ttu-id="8e7a5-119">Der folgende Code zeigt zwei Beispiele, in denen die `Call` Schlüsselwort ist erforderlich, um eine Prozedur aufrufen.</span><span class="sxs-lookup"><span data-stu-id="8e7a5-119">The following code shows two examples where the `Call` keyword is necessary to call a procedure.</span></span> <span data-ttu-id="8e7a5-120">In beiden Beispielen beginnt der aufgerufene Ausdruck mit einem Bezeichner nicht.</span><span class="sxs-lookup"><span data-stu-id="8e7a5-120">In both examples, the called expression doesn't start with an identifier.</span></span>  
  
 [!code-vb[VbVbalrStatements#97](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/call-statement_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="8e7a5-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8e7a5-121">See Also</span></span>  
 [<span data-ttu-id="8e7a5-122">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="8e7a5-122">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
 [<span data-ttu-id="8e7a5-123">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="8e7a5-123">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [<span data-ttu-id="8e7a5-124">Declare-Anweisung</span><span class="sxs-lookup"><span data-stu-id="8e7a5-124">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
 [<span data-ttu-id="8e7a5-125">Lambda-Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="8e7a5-125">Lambda Expressions</span></span>](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
