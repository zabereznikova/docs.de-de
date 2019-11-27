---
title: Teilausdruck
ms.date: 07/20/2015
helpviewer_keywords:
- lambda expressions [Visual Basic], sub expression
- Sub Expression [Visual Basic]
- subroutines [Visual Basic], sub expressions
ms.assetid: 36b6bfd1-6539-4d8f-a5eb-6541a745ffde
ms.openlocfilehash: d284e629ea0b0a4e9b6eb9e098612bb07c38723b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350900"
---
# <a name="sub-expression-visual-basic"></a><span data-ttu-id="34364-102">Teilausdruck (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="34364-102">Sub Expression (Visual Basic)</span></span>
<span data-ttu-id="34364-103">Deklariert die Parameter und den Code, die einen Lambda Ausdruck für die Unterroutine definieren.</span><span class="sxs-lookup"><span data-stu-id="34364-103">Declares the parameters and code that define a subroutine lambda expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34364-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="34364-104">Syntax</span></span>  
  
```vb  
Sub ( [ parameterlist ] ) statement  
- or -  
Sub ( [ parameterlist ] )  
  [ statements ]  
End Sub  
```  
  
## <a name="parts"></a><span data-ttu-id="34364-105">-Komponenten</span><span class="sxs-lookup"><span data-stu-id="34364-105">Parts</span></span>  
  
|<span data-ttu-id="34364-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="34364-106">Term</span></span>|<span data-ttu-id="34364-107">Definition</span><span class="sxs-lookup"><span data-stu-id="34364-107">Definition</span></span>|  
|---|---|  
|`parameterlist`|<span data-ttu-id="34364-108">Optional.</span><span class="sxs-lookup"><span data-stu-id="34364-108">Optional.</span></span> <span data-ttu-id="34364-109">Eine Liste der Namen der lokalen Variablen, die die Parameter der Prozedur darstellen.</span><span class="sxs-lookup"><span data-stu-id="34364-109">A list of local variable names that represent the parameters of the procedure.</span></span> <span data-ttu-id="34364-110">Die Klammern müssen auch dann vorhanden sein, wenn die Liste leer ist.</span><span class="sxs-lookup"><span data-stu-id="34364-110">The parentheses must be present even when the list is empty.</span></span> <span data-ttu-id="34364-111">Weitere Informationen finden Sie unter [Parameter List](../../../visual-basic/language-reference/statements/parameter-list.md).</span><span class="sxs-lookup"><span data-stu-id="34364-111">For more information, see [Parameter List](../../../visual-basic/language-reference/statements/parameter-list.md).</span></span>|  
|`statement`|<span data-ttu-id="34364-112">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="34364-112">Required.</span></span> <span data-ttu-id="34364-113">Eine einzelne Anweisung.</span><span class="sxs-lookup"><span data-stu-id="34364-113">A single statement.</span></span>|  
|`statements`|<span data-ttu-id="34364-114">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="34364-114">Required.</span></span> <span data-ttu-id="34364-115">Eine Liste mit Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="34364-115">A list of statements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="34364-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="34364-116">Remarks</span></span>  
 <span data-ttu-id="34364-117">Ein *Lambda-Ausdruck* ist eine Unterroutine, die keinen Namen hat und eine oder mehrere-Anweisungen ausführt.</span><span class="sxs-lookup"><span data-stu-id="34364-117">A *lambda expression* is a subroutine that does not have a name and that executes one or more statements.</span></span> <span data-ttu-id="34364-118">Sie können einen Lambda-Ausdruck überall dort verwenden, wo Sie einen Delegattyp verwenden können, außer als Argument für `RemoveHandler`.</span><span class="sxs-lookup"><span data-stu-id="34364-118">You can use a lambda expression anywhere that you can use a delegate type, except as an argument to `RemoveHandler`.</span></span> <span data-ttu-id="34364-119">Weitere Informationen zu Delegaten und zur Verwendung von Lambda-Ausdrücken mit Delegaten finden Sie unter [delegatanweisung](../../../visual-basic/language-reference/statements/delegate-statement.md) und [gelockerte Delegatenkonvertierung](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).</span><span class="sxs-lookup"><span data-stu-id="34364-119">For more information about delegates, and the use of lambda expressions with delegates, see [Delegate Statement](../../../visual-basic/language-reference/statements/delegate-statement.md) and [Relaxed Delegate Conversion](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).</span></span>  
  
## <a name="lambda-expression-syntax"></a><span data-ttu-id="34364-120">Lambdaausdruckssyntax</span><span class="sxs-lookup"><span data-stu-id="34364-120">Lambda Expression Syntax</span></span>  
 <span data-ttu-id="34364-121">Die Syntax eines Lambda-Ausdrucks ähnelt der einer Standard Unterroutine.</span><span class="sxs-lookup"><span data-stu-id="34364-121">The syntax of a lambda expression resembles that of a standard subroutine.</span></span> <span data-ttu-id="34364-122">Es gibt die folgenden Unterschiede:</span><span class="sxs-lookup"><span data-stu-id="34364-122">The differences are as follows:</span></span>  
  
- <span data-ttu-id="34364-123">Ein Lambda-Ausdruck weist keinen Namen auf.</span><span class="sxs-lookup"><span data-stu-id="34364-123">A lambda expression does not have a name.</span></span>  
  
- <span data-ttu-id="34364-124">Ein Lambda-Ausdruck kann keinen Modifizierer haben, z. b. `Overloads` oder `Overrides`.</span><span class="sxs-lookup"><span data-stu-id="34364-124">A lambda expression cannot have a modifier, such as `Overloads` or `Overrides`.</span></span>  
  
- <span data-ttu-id="34364-125">Der Text eines einzeiligen Lambda Ausdrucks muss eine-Anweisung und kein Ausdruck sein.</span><span class="sxs-lookup"><span data-stu-id="34364-125">The body of a single-line lambda expression must be a statement, not an expression.</span></span> <span data-ttu-id="34364-126">Der Text kann aus einem aufzurufenden Teil Prozedur-, aber keinem Aufrufvorgang einer Funktions Prozedur bestehen.</span><span class="sxs-lookup"><span data-stu-id="34364-126">The body can consist of a call to a sub procedure, but not a call to a function procedure.</span></span>  
  
- <span data-ttu-id="34364-127">In einem Lambda-Ausdruck müssen entweder alle Parameter über bestimmte Datentypen verfügen, oder alle Parameter müssen abgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="34364-127">In a lambda expression, either all parameters must have specified data types or all parameters must be inferred.</span></span>  
  
- <span data-ttu-id="34364-128">Optionale Parameter und `ParamArray` Parameter sind in Lambda-Ausdrücken nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="34364-128">Optional and `ParamArray` parameters are not permitted in lambda expressions.</span></span>  
  
- <span data-ttu-id="34364-129">Generische Parameter sind in Lambda-Ausdrücken nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="34364-129">Generic parameters are not permitted in lambda expressions.</span></span>  
  
## <a name="example"></a><span data-ttu-id="34364-130">Beispiel</span><span class="sxs-lookup"><span data-stu-id="34364-130">Example</span></span>  
 <span data-ttu-id="34364-131">Im folgenden finden Sie ein Beispiel für einen Lambda-Ausdruck, der einen Wert in die Konsole schreibt.</span><span class="sxs-lookup"><span data-stu-id="34364-131">Following is an example of a lambda expression that writes a value to the console.</span></span> <span data-ttu-id="34364-132">Das Beispiel zeigt die einzeilige und die mehrzeilige Lambda-Ausdruckssyntax für eine Unterroutine.</span><span class="sxs-lookup"><span data-stu-id="34364-132">The example shows both the single-line and multiline lambda expression syntax for a subroutine.</span></span> <span data-ttu-id="34364-133">Weitere Beispiele finden Sie unter [Lambda-Ausdrücke](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="34364-133">For more examples, see [Lambda Expressions](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).</span></span>  
  
 [!code-vb[VbVbalrLambdas#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#15)]  
  
## <a name="see-also"></a><span data-ttu-id="34364-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="34364-134">See also</span></span>

- [<span data-ttu-id="34364-135">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="34364-135">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="34364-136">Lambda-Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="34364-136">Lambda Expressions</span></span>](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
- [<span data-ttu-id="34364-137">Operatoren und Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="34364-137">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
- [<span data-ttu-id="34364-138">Anweisungen</span><span class="sxs-lookup"><span data-stu-id="34364-138">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
- [<span data-ttu-id="34364-139">Gelockerte Delegatenkonvertierung</span><span class="sxs-lookup"><span data-stu-id="34364-139">Relaxed Delegate Conversion</span></span>](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
