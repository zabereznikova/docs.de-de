---
title: Parameter und Argumente von Prozeduren (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], arguments
- procedures [Visual Basic], argument lists
- values [Visual Basic], passing to procedures
- arguments [Visual Basic], passing
- procedures [Visual Basic], parameters
- Visual Basic code, argument lists
- Visual Basic code, procedures
- parameters [Visual Basic], Visual Basic procedures
- parameters [Visual Basic], lists
- arguments [Visual Basic], Visual Basic procedures
- arguments [Visual Basic], procedures
- parameter lists [Visual Basic]
- Visual Basic code, parameter lists
- argument lists [Visual Basic]
- procedures [Visual Basic], parameter lists
ms.assetid: ff275aff-aa13-40df-bd4c-63486db8c1e9
ms.openlocfilehash: b0ab186945b456d7fb4dde3f52724b08a99e2827
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33652499"
---
# <a name="procedure-parameters-and-arguments-visual-basic"></a><span data-ttu-id="a31e0-102">Parameter und Argumente von Prozeduren (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a31e0-102">Procedure Parameters and Arguments (Visual Basic)</span></span>
<span data-ttu-id="a31e0-103">In den meisten Fällen benötigt eine Prozedur einige Informationen zu den Umständen zusammen, in welcher er aufgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="a31e0-103">In most cases, a procedure needs some information about the circumstances in which it has been called.</span></span> <span data-ttu-id="a31e0-104">Eine Prozedur, die wiederholte oder freigegebene Aufgaben ausführt, werden unterschiedliche Informationen für jeden Aufruf verwendet.</span><span class="sxs-lookup"><span data-stu-id="a31e0-104">A procedure that performs repeated or shared tasks uses different information for each call.</span></span> <span data-ttu-id="a31e0-105">Diese Informationen besteht aus Variablen, Konstanten und Ausdrücke, die Sie an die Prozedur übergeben, wenn Sie sie aufrufen.</span><span class="sxs-lookup"><span data-stu-id="a31e0-105">This information consists of variables, constants, and expressions that you pass to the procedure when you call it.</span></span>  
  
 <span data-ttu-id="a31e0-106">Ein *Parameter* stellt einen Wert, der die Prozedur erwartet, Sie angeben dass, wenn Sie sie aufrufen.</span><span class="sxs-lookup"><span data-stu-id="a31e0-106">A *parameter* represents a value that the procedure expects you to supply when you call it.</span></span> <span data-ttu-id="a31e0-107">Die Deklaration der Prozedur definiert seine Parameter.</span><span class="sxs-lookup"><span data-stu-id="a31e0-107">The procedure's declaration defines its parameters.</span></span>  
  
 <span data-ttu-id="a31e0-108">Sie können eine Prozedur ohne Parameter, einen Parameter oder mehrere definieren.</span><span class="sxs-lookup"><span data-stu-id="a31e0-108">You can define a procedure with no parameters, one parameter, or more than one.</span></span> <span data-ttu-id="a31e0-109">Wird aufgerufen, der Teil der Definition der Prozedur, der angibt, die Parameter der *Parameterliste*.</span><span class="sxs-lookup"><span data-stu-id="a31e0-109">The part of the procedure definition that specifies the parameters is called the *parameter list*.</span></span>  
  
 <span data-ttu-id="a31e0-110">Ein *Argument* stellt den Wert, die Sie angeben, einen Prozedurparameter dar, wenn Sie die Prozedur aufrufen.</span><span class="sxs-lookup"><span data-stu-id="a31e0-110">An *argument* represents the value you supply to a procedure parameter when you call the procedure.</span></span> <span data-ttu-id="a31e0-111">Der aufrufende Code bereitstellt die Argumente, wenn er die Prozedur aufruft.</span><span class="sxs-lookup"><span data-stu-id="a31e0-111">The calling code supplies the arguments when it calls the procedure.</span></span> <span data-ttu-id="a31e0-112">Wird aufgerufen, der Teil des Prozeduraufrufs, der angibt, die Argumente der *Argumentliste*.</span><span class="sxs-lookup"><span data-stu-id="a31e0-112">The part of the procedure call that specifies the arguments is called the *argument list*.</span></span>  
  
 <span data-ttu-id="a31e0-113">Die folgende Abbildung zeigt den Aufruf der Prozedur Code `safeSquareRoot` aus zwei verschiedenen Orten.</span><span class="sxs-lookup"><span data-stu-id="a31e0-113">The following illustration shows code calling the procedure `safeSquareRoot` from two different places.</span></span> <span data-ttu-id="a31e0-114">Der erste Aufruf übergibt den Wert der Variablen `x` (4.0) an den Parameter `number`, und der Rückgabewert in `root` (2.0) wird der Variablen zugewiesen `y`.</span><span class="sxs-lookup"><span data-stu-id="a31e0-114">The first call passes the value of the variable `x` (4.0) to the parameter `number`, and the return value in `root` (2.0) is assigned to the variable `y`.</span></span> <span data-ttu-id="a31e0-115">Der zweite Aufruf übergibt den Literalwert 9.0, `number`, und weist den Rückgabewert (3.0) Variablen `z`.</span><span class="sxs-lookup"><span data-stu-id="a31e0-115">The second call passes the literal value 9.0 to `number`, and assigns the return value (3.0) to variable `z`.</span></span>  
  
 <span data-ttu-id="a31e0-116">![Grafisches Diagramm der Argumentübergabe an Parameter](./media/parametersargue.gif "ParametersArgue")</span><span class="sxs-lookup"><span data-stu-id="a31e0-116">![Graphic diagram of passing argument to parameter](./media/parametersargue.gif "ParametersArgue")</span></span>  
<span data-ttu-id="a31e0-117">Ein Argument übergeben an einen parameter</span><span class="sxs-lookup"><span data-stu-id="a31e0-117">Passing an argument to a parameter</span></span>  
  
 <span data-ttu-id="a31e0-118">Weitere Informationen finden Sie unter [Unterschiede zwischen Parametern und Argumenten](./differences-between-parameters-and-arguments.md).</span><span class="sxs-lookup"><span data-stu-id="a31e0-118">For more information, see [Differences Between Parameters and Arguments](./differences-between-parameters-and-arguments.md).</span></span>  
  
## <a name="parameter-data-type"></a><span data-ttu-id="a31e0-119">Datentyp des Parameters</span><span class="sxs-lookup"><span data-stu-id="a31e0-119">Parameter Data Type</span></span>  
 <span data-ttu-id="a31e0-120">Definieren Sie einen Datentyp für einen Parameter mithilfe der `As` -Klausel in der Deklaration.</span><span class="sxs-lookup"><span data-stu-id="a31e0-120">You define a data type for a parameter by using the `As` clause in its declaration.</span></span> <span data-ttu-id="a31e0-121">Die folgende Funktion akzeptiert z. B. eine Zeichenfolge und eine ganze Zahl.</span><span class="sxs-lookup"><span data-stu-id="a31e0-121">For example, the following function accepts a string and an integer.</span></span>  
  
 [!code-vb[VbVbcnProcedures#32](./codesnippet/VisualBasic/procedure-parameters-and-arguments_1.vb)]  
  
 <span data-ttu-id="a31e0-122">Wenn die Überprüfung des Typs wechseln ([Option Strict-Anweisung](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) ist `Off,` der `As` -Klausel ist optional, außer, dass wenn ein Parameter verwendet wird, alle Parameter muss verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a31e0-122">If the type checking switch ([Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) is `Off,` the `As` clause is optional, except that if any one parameter uses it, all parameters must use it.</span></span> <span data-ttu-id="a31e0-123">Wenn die typüberprüfung `On`, die `As` -Klausel ist für alle Parameter der Prozedur erforderlich.</span><span class="sxs-lookup"><span data-stu-id="a31e0-123">If type checking is `On`, the `As` clause is required for all procedure parameters.</span></span>  
  
 <span data-ttu-id="a31e0-124">Wenn der aufrufende Code erwartet ein Argument mit einem Datentyp unterscheiden, die von den entsprechenden Parameter anzugeben, wie z. B. `Byte` auf eine `String` Parameter, sie müssen einen der folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="a31e0-124">If the calling code expects to supply an argument with a data type different from that of its corresponding parameter, such as `Byte` to a `String` parameter, it must do one of the following:</span></span>  
  
-   <span data-ttu-id="a31e0-125">Geben Sie nur Argumente mit Datentypen, die auf den Parameterdatentyp erweitert werden;</span><span class="sxs-lookup"><span data-stu-id="a31e0-125">Supply only arguments with data types that widen to the parameter data type;</span></span>  
  
-   <span data-ttu-id="a31e0-126">Legen Sie `Option Strict Off` ermöglicht implizite einschränkende Konvertierungen; oder</span><span class="sxs-lookup"><span data-stu-id="a31e0-126">Set `Option Strict Off` to allow implicit narrowing conversions; or</span></span>  
  
-   <span data-ttu-id="a31e0-127">Verwenden Sie ein Konvertierungsschlüsselwort, um den Datentyp explizit zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="a31e0-127">Use a conversion keyword to explicitly convert the data type.</span></span>  
  
### <a name="type-parameters"></a><span data-ttu-id="a31e0-128">Typparameter</span><span class="sxs-lookup"><span data-stu-id="a31e0-128">Type Parameters</span></span>  
 <span data-ttu-id="a31e0-129">Ein *generische Prozedur* definiert auch eine oder mehrere *Typparameter* zusätzlich zu den normalen Parametern.</span><span class="sxs-lookup"><span data-stu-id="a31e0-129">A *generic procedure* also defines one or more *type parameters* in addition to its normal parameters.</span></span> <span data-ttu-id="a31e0-130">Eine generische Prozedur kann der aufrufenden Code unterschiedliche Datentypen jedes Mal übergeben sie die Prozedur aufruft, damit sie die Datentypen jeder einzelne Aufruf-Anforderungen anpassen kann.</span><span class="sxs-lookup"><span data-stu-id="a31e0-130">A generic procedure allows the calling code to pass different data types each time it calls the procedure, so it can tailor the data types to the requirements of each individual call.</span></span> <span data-ttu-id="a31e0-131">Siehe [Generic Procedures in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="a31e0-131">See [Generic Procedures in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-procedures.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a31e0-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a31e0-132">See Also</span></span>  
 [<span data-ttu-id="a31e0-133">Verfahren</span><span class="sxs-lookup"><span data-stu-id="a31e0-133">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="a31e0-134">Sub-Prozeduren</span><span class="sxs-lookup"><span data-stu-id="a31e0-134">Sub Procedures</span></span>](./sub-procedures.md)  
 [<span data-ttu-id="a31e0-135">Function-Prozeduren</span><span class="sxs-lookup"><span data-stu-id="a31e0-135">Function Procedures</span></span>](./function-procedures.md)  
 [<span data-ttu-id="a31e0-136">Eigenschaftenprozeduren</span><span class="sxs-lookup"><span data-stu-id="a31e0-136">Property Procedures</span></span>](./property-procedures.md)  
 [<span data-ttu-id="a31e0-137">Operatorprozeduren</span><span class="sxs-lookup"><span data-stu-id="a31e0-137">Operator Procedures</span></span>](./operator-procedures.md)  
 [<span data-ttu-id="a31e0-138">Gewusst wie: Definieren eines Parameters für eine Prozedur</span><span class="sxs-lookup"><span data-stu-id="a31e0-138">How to: Define a Parameter for a Procedure</span></span>](./how-to-define-a-parameter-for-a-procedure.md)  
 [<span data-ttu-id="a31e0-139">Gewusst wie: Übergeben von Argumenten an eine Prozedur</span><span class="sxs-lookup"><span data-stu-id="a31e0-139">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)  
 [<span data-ttu-id="a31e0-140">Übergeben von Argumenten als Wert und als Verweis</span><span class="sxs-lookup"><span data-stu-id="a31e0-140">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)  
 [<span data-ttu-id="a31e0-141">Prozedurüberladung</span><span class="sxs-lookup"><span data-stu-id="a31e0-141">Procedure Overloading</span></span>](./procedure-overloading.md)  
 [<span data-ttu-id="a31e0-142">Konvertierungen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a31e0-142">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
