---
title: "Teilausdruck (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- lambda expressions [Visual Basic], sub expression
- Sub Expression [Visual Basic]
- subroutines [Visual Basic], sub expressions
ms.assetid: 36b6bfd1-6539-4d8f-a5eb-6541a745ffde
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 43e35bd0386bc56478603ec36437981785cc8ffb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="sub-expression-visual-basic"></a><span data-ttu-id="7dd86-102">Teilausdruck (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7dd86-102">Sub Expression (Visual Basic)</span></span>
<span data-ttu-id="7dd86-103">Deklariert die Parameter und den Code, der einen Unterroutine Lambda-Ausdruck definieren.</span><span class="sxs-lookup"><span data-stu-id="7dd86-103">Declares the parameters and code that define a subroutine lambda expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7dd86-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7dd86-104">Syntax</span></span>  
  
```  
Sub ( [ parameterlist ] ) statement  
- or -  
Sub ( [ parameterlist ] )  
  [ statements ]  
End Sub  
```  
  
## <a name="parts"></a><span data-ttu-id="7dd86-105">Teile</span><span class="sxs-lookup"><span data-stu-id="7dd86-105">Parts</span></span>  
  
|<span data-ttu-id="7dd86-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="7dd86-106">Term</span></span>|<span data-ttu-id="7dd86-107">Definition</span><span class="sxs-lookup"><span data-stu-id="7dd86-107">Definition</span></span>|  
|---|---|  
|`parameterlist`|<span data-ttu-id="7dd86-108">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="7dd86-108">Optional.</span></span> <span data-ttu-id="7dd86-109">Eine Liste der Namen lokaler Variablen, die die Parameter der Prozedur darstellen.</span><span class="sxs-lookup"><span data-stu-id="7dd86-109">A list of local variable names that represent the parameters of the procedure.</span></span> <span data-ttu-id="7dd86-110">Die Klammern müssen vorhanden sein, auch wenn die Liste leer ist.</span><span class="sxs-lookup"><span data-stu-id="7dd86-110">The parentheses must be present even when the list is empty.</span></span> <span data-ttu-id="7dd86-111">Weitere Informationen finden Sie unter [Parameterliste](../../../visual-basic/language-reference/statements/parameter-list.md).</span><span class="sxs-lookup"><span data-stu-id="7dd86-111">For more information, see [Parameter List](../../../visual-basic/language-reference/statements/parameter-list.md).</span></span>|  
|`statement`|<span data-ttu-id="7dd86-112">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="7dd86-112">Required.</span></span> <span data-ttu-id="7dd86-113">Eine einzelne Anweisung.</span><span class="sxs-lookup"><span data-stu-id="7dd86-113">A single statement.</span></span>|  
|`statements`|<span data-ttu-id="7dd86-114">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="7dd86-114">Required.</span></span> <span data-ttu-id="7dd86-115">Eine Liste von Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="7dd86-115">A list of statements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7dd86-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7dd86-116">Remarks</span></span>  
 <span data-ttu-id="7dd86-117">Ein *Lambda-Ausdruck* Unterroutine vorstellen, die nicht über einen Namen verfügt ist und ausgeführt wird, eine oder mehrere Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="7dd86-117">A *lambda expression* is a subroutine that does not have a name and that executes one or more statements.</span></span> <span data-ttu-id="7dd86-118">Sie können einen Lambda-Ausdruck an einer beliebigen Stelle verwenden, dass Sie einen Delegattyp, außer als Argument verwenden können `RemoveHandler`.</span><span class="sxs-lookup"><span data-stu-id="7dd86-118">You can use a lambda expression anywhere that you can use a delegate type, except as an argument to `RemoveHandler`.</span></span> <span data-ttu-id="7dd86-119">Weitere Informationen über Delegaten und die Verwendung von Lambdaausdrücken mit Delegaten finden Sie unter [Delegate-Anweisung](../../../visual-basic/language-reference/statements/delegate-statement.md) und [gelockerte Delegatenkonvertierung](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).</span><span class="sxs-lookup"><span data-stu-id="7dd86-119">For more information about delegates, and the use of lambda expressions with delegates, see [Delegate Statement](../../../visual-basic/language-reference/statements/delegate-statement.md) and [Relaxed Delegate Conversion](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).</span></span>  
  
## <a name="lambda-expression-syntax"></a><span data-ttu-id="7dd86-120">Lambdaausdruckssyntax</span><span class="sxs-lookup"><span data-stu-id="7dd86-120">Lambda Expression Syntax</span></span>  
 <span data-ttu-id="7dd86-121">Die Syntax eines Lambda-Ausdrucks ähnelt dem von einer standard-Unterroutine.</span><span class="sxs-lookup"><span data-stu-id="7dd86-121">The syntax of a lambda expression resembles that of a standard subroutine.</span></span> <span data-ttu-id="7dd86-122">Die Unterschiede sind wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="7dd86-122">The differences are as follows:</span></span>  
  
-   <span data-ttu-id="7dd86-123">Ein Lambda-Ausdruck weist keine Namen auf.</span><span class="sxs-lookup"><span data-stu-id="7dd86-123">A lambda expression does not have a name.</span></span>  
  
-   <span data-ttu-id="7dd86-124">Ein Lambda-Ausdruck kann nicht verfügen über einen Modifizierer, wie z. B. `Overloads` oder `Overrides`.</span><span class="sxs-lookup"><span data-stu-id="7dd86-124">A lambda expression cannot have a modifier, such as `Overloads` or `Overrides`.</span></span>  
  
-   <span data-ttu-id="7dd86-125">Der Text eines einzeiligen Lambda-Ausdrucks muss es sich um eine Anweisung, kein Ausdruck sein.</span><span class="sxs-lookup"><span data-stu-id="7dd86-125">The body of a single-line lambda expression must be a statement, not an expression.</span></span> <span data-ttu-id="7dd86-126">Der Text kann einen Aufruf an eine Subprozedur, aber nicht auf einen Aufruf an eine Funktionsprozedur bestehen.</span><span class="sxs-lookup"><span data-stu-id="7dd86-126">The body can consist of a call to a sub procedure, but not a call to a function procedure.</span></span>  
  
-   <span data-ttu-id="7dd86-127">In einen Lambda-Ausdruck müssen entweder für alle Parameter angegeben haben, Datentypen oder alle Parameter abgeleitet werden müssen.</span><span class="sxs-lookup"><span data-stu-id="7dd86-127">In a lambda expression, either all parameters must have specified data types or all parameters must be inferred.</span></span>  
  
-   <span data-ttu-id="7dd86-128">Dies ist optional und `ParamArray` Parameter sind in Lambda-Ausdrücken nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="7dd86-128">Optional and `ParamArray` parameters are not permitted in lambda expressions.</span></span>  
  
-   <span data-ttu-id="7dd86-129">Generische Parameter sind in Lambda-Ausdrücken nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="7dd86-129">Generic parameters are not permitted in lambda expressions.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7dd86-130">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7dd86-130">Example</span></span>  
 <span data-ttu-id="7dd86-131">Es folgt ein Beispiel für einen Lambda-Ausdruck, der einen Wert in die Konsole schreibt.</span><span class="sxs-lookup"><span data-stu-id="7dd86-131">Following is an example of a lambda expression that writes a value to the console.</span></span> <span data-ttu-id="7dd86-132">Das Beispiel zeigt sowohl den einzeiligen und mehrzeiligen Lambda-Ausdruckssyntax für eine Unterroutine.</span><span class="sxs-lookup"><span data-stu-id="7dd86-132">The example shows both the single-line and multiline lambda expression syntax for a subroutine.</span></span> <span data-ttu-id="7dd86-133">Weitere Beispiele finden Sie unter [Lambda-Ausdrücke](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="7dd86-133">For more examples, see [Lambda Expressions](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).</span></span>  
  
 [!code-vb[VbVbalrLambdas#15](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/sub-expression_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="7dd86-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7dd86-134">See Also</span></span>  
 [<span data-ttu-id="7dd86-135">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="7dd86-135">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [<span data-ttu-id="7dd86-136">Lambda-Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="7dd86-136">Lambda Expressions</span></span>](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)  
 [<span data-ttu-id="7dd86-137">Operatoren und Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="7dd86-137">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)  
 [<span data-ttu-id="7dd86-138">Anweisungen</span><span class="sxs-lookup"><span data-stu-id="7dd86-138">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)  
 [<span data-ttu-id="7dd86-139">Gelockerte Delegatenkonvertierung</span><span class="sxs-lookup"><span data-stu-id="7dd86-139">Relaxed Delegate Conversion</span></span>](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
