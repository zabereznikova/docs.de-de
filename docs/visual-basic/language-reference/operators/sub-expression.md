---
title: Teilausdruck (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- lambda expressions [Visual Basic], sub expression
- Sub Expression [Visual Basic]
- subroutines [Visual Basic], sub expressions
ms.assetid: 36b6bfd1-6539-4d8f-a5eb-6541a745ffde
ms.openlocfilehash: 5e8c66f4f2b21a890b8c61e6fc642ce276df6f60
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56966722"
---
# <a name="sub-expression-visual-basic"></a><span data-ttu-id="1d223-102">Teilausdruck (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1d223-102">Sub Expression (Visual Basic)</span></span>
<span data-ttu-id="1d223-103">Deklariert die Parameter und den Code, der einen Unterroutine Lambda-Ausdruck definieren.</span><span class="sxs-lookup"><span data-stu-id="1d223-103">Declares the parameters and code that define a subroutine lambda expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d223-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1d223-104">Syntax</span></span>  
  
```  
Sub ( [ parameterlist ] ) statement  
- or -  
Sub ( [ parameterlist ] )  
  [ statements ]  
End Sub  
```  
  
## <a name="parts"></a><span data-ttu-id="1d223-105">Teile</span><span class="sxs-lookup"><span data-stu-id="1d223-105">Parts</span></span>  
  
|<span data-ttu-id="1d223-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="1d223-106">Term</span></span>|<span data-ttu-id="1d223-107">Definition</span><span class="sxs-lookup"><span data-stu-id="1d223-107">Definition</span></span>|  
|---|---|  
|`parameterlist`|<span data-ttu-id="1d223-108">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="1d223-108">Optional.</span></span> <span data-ttu-id="1d223-109">Eine Liste von Namen lokaler Variablen, die die Parameter der Prozedur darstellen.</span><span class="sxs-lookup"><span data-stu-id="1d223-109">A list of local variable names that represent the parameters of the procedure.</span></span> <span data-ttu-id="1d223-110">Die Klammern müssen vorhanden sein, selbst wenn die Liste leer ist.</span><span class="sxs-lookup"><span data-stu-id="1d223-110">The parentheses must be present even when the list is empty.</span></span> <span data-ttu-id="1d223-111">Weitere Informationen finden Sie unter [Parameter List](../../../visual-basic/language-reference/statements/parameter-list.md).</span><span class="sxs-lookup"><span data-stu-id="1d223-111">For more information, see [Parameter List](../../../visual-basic/language-reference/statements/parameter-list.md).</span></span>|  
|`statement`|<span data-ttu-id="1d223-112">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="1d223-112">Required.</span></span> <span data-ttu-id="1d223-113">Eine einzelne Anweisung.</span><span class="sxs-lookup"><span data-stu-id="1d223-113">A single statement.</span></span>|  
|`statements`|<span data-ttu-id="1d223-114">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="1d223-114">Required.</span></span> <span data-ttu-id="1d223-115">Eine Liste von Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="1d223-115">A list of statements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1d223-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1d223-116">Remarks</span></span>  
 <span data-ttu-id="1d223-117">Ein *Lambda-Ausdruck* ist eine Unterroutine, die nicht über einen Namen verfügt, und eine oder mehrere Anweisungen ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="1d223-117">A *lambda expression* is a subroutine that does not have a name and that executes one or more statements.</span></span> <span data-ttu-id="1d223-118">Sie können einen Lambda-Ausdruck an einer beliebigen Stelle, dass Sie einen Delegattyp, außer als Argument verwenden können `RemoveHandler`.</span><span class="sxs-lookup"><span data-stu-id="1d223-118">You can use a lambda expression anywhere that you can use a delegate type, except as an argument to `RemoveHandler`.</span></span> <span data-ttu-id="1d223-119">Weitere Informationen zu Delegaten und die Verwendung von Lambdaausdrücken mit Delegaten finden Sie unter [Delegate-Anweisung](../../../visual-basic/language-reference/statements/delegate-statement.md) und [gelockerte Delegatenkonvertierung](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).</span><span class="sxs-lookup"><span data-stu-id="1d223-119">For more information about delegates, and the use of lambda expressions with delegates, see [Delegate Statement](../../../visual-basic/language-reference/statements/delegate-statement.md) and [Relaxed Delegate Conversion](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).</span></span>  
  
## <a name="lambda-expression-syntax"></a><span data-ttu-id="1d223-120">Lambdaausdruckssyntax</span><span class="sxs-lookup"><span data-stu-id="1d223-120">Lambda Expression Syntax</span></span>  
 <span data-ttu-id="1d223-121">Die Syntax eines Lambda-Ausdrucks ähnelt eine standard-Unterroutine.</span><span class="sxs-lookup"><span data-stu-id="1d223-121">The syntax of a lambda expression resembles that of a standard subroutine.</span></span> <span data-ttu-id="1d223-122">Die Unterschiede sind wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="1d223-122">The differences are as follows:</span></span>  
  
-   <span data-ttu-id="1d223-123">Ein Lambda-Ausdruck ist nicht auf einen Namen haben.</span><span class="sxs-lookup"><span data-stu-id="1d223-123">A lambda expression does not have a name.</span></span>  
  
-   <span data-ttu-id="1d223-124">Ein Lambda-Ausdruck kann nicht verfügen über einen Modifizierer, z. B. `Overloads` oder `Overrides`.</span><span class="sxs-lookup"><span data-stu-id="1d223-124">A lambda expression cannot have a modifier, such as `Overloads` or `Overrides`.</span></span>  
  
-   <span data-ttu-id="1d223-125">Der Text eines einzeiligen Lambda-Ausdrucks muss es sich um eine Anweisung, die kein Ausdruck sein.</span><span class="sxs-lookup"><span data-stu-id="1d223-125">The body of a single-line lambda expression must be a statement, not an expression.</span></span> <span data-ttu-id="1d223-126">Der Text kann einen Aufruf an eine Subprozedur, aber nicht aus einem Aufruf einer Funktion Prozedur bestehen.</span><span class="sxs-lookup"><span data-stu-id="1d223-126">The body can consist of a call to a sub procedure, but not a call to a function procedure.</span></span>  
  
-   <span data-ttu-id="1d223-127">Alle Parameter in einem Lambdaausdruck entweder müssen angegeben haben, dass die Datentypen oder für alle Parameter abgeleitet werden müssen.</span><span class="sxs-lookup"><span data-stu-id="1d223-127">In a lambda expression, either all parameters must have specified data types or all parameters must be inferred.</span></span>  
  
-   <span data-ttu-id="1d223-128">Optionale und `ParamArray` Parameter sind in Lambda-Ausdrücken nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="1d223-128">Optional and `ParamArray` parameters are not permitted in lambda expressions.</span></span>  
  
-   <span data-ttu-id="1d223-129">Generische Parameter sind in Lambda-Ausdrücken nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="1d223-129">Generic parameters are not permitted in lambda expressions.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1d223-130">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1d223-130">Example</span></span>  
 <span data-ttu-id="1d223-131">Es folgt ein Beispiel für einen Lambda-Ausdruck, der einen Wert an die Konsole schreibt.</span><span class="sxs-lookup"><span data-stu-id="1d223-131">Following is an example of a lambda expression that writes a value to the console.</span></span> <span data-ttu-id="1d223-132">Das Beispiel zeigt sowohl den einzeiligen und mehrzeiligen Lambda-Ausdruckssyntax für eine Unterroutine.</span><span class="sxs-lookup"><span data-stu-id="1d223-132">The example shows both the single-line and multiline lambda expression syntax for a subroutine.</span></span> <span data-ttu-id="1d223-133">Weitere Beispiele finden Sie unter [Lambda-Ausdrücke](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="1d223-133">For more examples, see [Lambda Expressions](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).</span></span>  
  
 [!code-vb[VbVbalrLambdas#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#15)]  
  
## <a name="see-also"></a><span data-ttu-id="1d223-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1d223-134">See also</span></span>
- [<span data-ttu-id="1d223-135">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="1d223-135">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="1d223-136">Lambda-Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="1d223-136">Lambda Expressions</span></span>](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
- [<span data-ttu-id="1d223-137">Operatoren und Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="1d223-137">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
- [<span data-ttu-id="1d223-138">Anweisungen</span><span class="sxs-lookup"><span data-stu-id="1d223-138">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
- [<span data-ttu-id="1d223-139">Gelockerte Delegatenkonvertierung</span><span class="sxs-lookup"><span data-stu-id="1d223-139">Relaxed Delegate Conversion</span></span>](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
