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
ms.openlocfilehash: 80065cabcacdcf44b04fef7bacb978ca9c8077ae
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61791911"
---
# <a name="procedure-parameters-and-arguments-visual-basic"></a><span data-ttu-id="2078c-102">Parameter und Argumente von Prozeduren (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2078c-102">Procedure Parameters and Arguments (Visual Basic)</span></span>
<span data-ttu-id="2078c-103">In den meisten Fällen benötigt eine Prozedur einige Informationen zu den Umständen zusammen, die in denen sie aufgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="2078c-103">In most cases, a procedure needs some information about the circumstances in which it has been called.</span></span> <span data-ttu-id="2078c-104">Eine Prozedur, die wiederholte oder freigegebene Aufgaben ausführt, verwendet verschiedene Informationen für jeden Aufruf an.</span><span class="sxs-lookup"><span data-stu-id="2078c-104">A procedure that performs repeated or shared tasks uses different information for each call.</span></span> <span data-ttu-id="2078c-105">Diese Informationen bestehen aus Variablen, Konstanten und Ausdrücke, die Sie beim Aufruf an die Prozedur übergeben.</span><span class="sxs-lookup"><span data-stu-id="2078c-105">This information consists of variables, constants, and expressions that you pass to the procedure when you call it.</span></span>  
  
 <span data-ttu-id="2078c-106">Ein *Parameter* stellt einen Wert, der die Prozedur erwartet, Sie dass angeben, wenn Sie sie aufrufen.</span><span class="sxs-lookup"><span data-stu-id="2078c-106">A *parameter* represents a value that the procedure expects you to supply when you call it.</span></span> <span data-ttu-id="2078c-107">Die Deklaration der Prozedur definiert die Parameter an.</span><span class="sxs-lookup"><span data-stu-id="2078c-107">The procedure's declaration defines its parameters.</span></span>  
  
 <span data-ttu-id="2078c-108">Sie können eine Prozedur ohne Parameter, der einen Parameter oder mehr als eine definieren.</span><span class="sxs-lookup"><span data-stu-id="2078c-108">You can define a procedure with no parameters, one parameter, or more than one.</span></span> <span data-ttu-id="2078c-109">Wird aufgerufen, der Teil der Definition der Prozedur, der angibt, die Parameter der *Parameterliste*.</span><span class="sxs-lookup"><span data-stu-id="2078c-109">The part of the procedure definition that specifies the parameters is called the *parameter list*.</span></span>  
  
 <span data-ttu-id="2078c-110">Ein *Argument* stellt den Wert, der Sie angeben, Parameter einer Prozedur dar, wenn Sie die Prozedur aufrufen.</span><span class="sxs-lookup"><span data-stu-id="2078c-110">An *argument* represents the value you supply to a procedure parameter when you call the procedure.</span></span> <span data-ttu-id="2078c-111">Der aufrufende Code stellt die Argumente bereit, wenn sie die Prozedur aufruft.</span><span class="sxs-lookup"><span data-stu-id="2078c-111">The calling code supplies the arguments when it calls the procedure.</span></span> <span data-ttu-id="2078c-112">Wird aufgerufen, der Teil der Aufruf der Prozedur, der angibt, die Argumente der *Argumentliste*.</span><span class="sxs-lookup"><span data-stu-id="2078c-112">The part of the procedure call that specifies the arguments is called the *argument list*.</span></span>  
  
 <span data-ttu-id="2078c-113">Die folgende Abbildung zeigt den Code, der die Prozedur aufruft `safeSquareRoot` von zwei verschiedenen Stellen.</span><span class="sxs-lookup"><span data-stu-id="2078c-113">The following illustration shows code calling the procedure `safeSquareRoot` from two different places.</span></span> <span data-ttu-id="2078c-114">Beim erste Aufruf übergibt den Wert der Variablen `x` (4.0) an den Parameter `number`, und der Rückgabewert in `root` (2.0) der Variablen zugewiesen `y`.</span><span class="sxs-lookup"><span data-stu-id="2078c-114">The first call passes the value of the variable `x` (4.0) to the parameter `number`, and the return value in `root` (2.0) is assigned to the variable `y`.</span></span> <span data-ttu-id="2078c-115">Beim zweiten Aufruf wird den Literalwert 9.0 auf `number`, und weist den Rückgabewert (3.0) Variablen `z`.</span><span class="sxs-lookup"><span data-stu-id="2078c-115">The second call passes the literal value 9.0 to `number`, and assigns the return value (3.0) to variable `z`.</span></span>  
  
 ![Diagramm zeigt das Übergeben eines Arguments an einen parameter](./media/procedure-parameters-and-arguments/pass-argument-parameter.gif)  
  
 <span data-ttu-id="2078c-117">Weitere Informationen finden Sie unter [Unterschiede zwischen Parametern und Argumenten](./differences-between-parameters-and-arguments.md).</span><span class="sxs-lookup"><span data-stu-id="2078c-117">For more information, see [Differences Between Parameters and Arguments](./differences-between-parameters-and-arguments.md).</span></span>  
  
## <a name="parameter-data-type"></a><span data-ttu-id="2078c-118">Parameterdatentyp</span><span class="sxs-lookup"><span data-stu-id="2078c-118">Parameter Data Type</span></span>  
 <span data-ttu-id="2078c-119">Sie definieren einen Datentyp für einen Parameter mithilfe der `As` -Klausel in der Deklaration.</span><span class="sxs-lookup"><span data-stu-id="2078c-119">You define a data type for a parameter by using the `As` clause in its declaration.</span></span> <span data-ttu-id="2078c-120">Die folgende Funktion akzeptiert z. B. eine Zeichenfolge und einer ganzen Zahl.</span><span class="sxs-lookup"><span data-stu-id="2078c-120">For example, the following function accepts a string and an integer.</span></span>  
  
 [!code-vb[VbVbcnProcedures#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#32)]  
  
 <span data-ttu-id="2078c-121">Wenn die typüberprüfung wechseln ([Option Strict-Anweisung](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) ist `Off,` der `As` -Klausel ist optional, mit dem Unterschied, dass wenn einen Parameter verwendet wird, alle Parameter verwendet werden müssen.</span><span class="sxs-lookup"><span data-stu-id="2078c-121">If the type checking switch ([Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) is `Off,` the `As` clause is optional, except that if any one parameter uses it, all parameters must use it.</span></span> <span data-ttu-id="2078c-122">Wenn die typüberprüfung ist `On`, `As` -Klausel ist für alle Parameter der Prozedur erforderlich.</span><span class="sxs-lookup"><span data-stu-id="2078c-122">If type checking is `On`, the `As` clause is required for all procedure parameters.</span></span>  
  
 <span data-ttu-id="2078c-123">Wenn der aufrufende Code erwartet ein Argument mit einem Datentyp, der sich von der entsprechenden Parameter bereitstellen, wie `Byte` auf eine `String` -Parameter müssen einen der folgenden:</span><span class="sxs-lookup"><span data-stu-id="2078c-123">If the calling code expects to supply an argument with a data type different from that of its corresponding parameter, such as `Byte` to a `String` parameter, it must do one of the following:</span></span>  
  
- <span data-ttu-id="2078c-124">Geben Sie nur Argumente mit den Datentypen, die auf der Parameterdatentyp erweitert werden;</span><span class="sxs-lookup"><span data-stu-id="2078c-124">Supply only arguments with data types that widen to the parameter data type;</span></span>  
  
- <span data-ttu-id="2078c-125">Legen Sie `Option Strict Off` können implizite einschränkende Konvertierungen; oder</span><span class="sxs-lookup"><span data-stu-id="2078c-125">Set `Option Strict Off` to allow implicit narrowing conversions; or</span></span>  
  
- <span data-ttu-id="2078c-126">Verwenden Sie eine Konvertierungsschlüsselwort, um den Datentyp explizit konvertieren.</span><span class="sxs-lookup"><span data-stu-id="2078c-126">Use a conversion keyword to explicitly convert the data type.</span></span>  
  
### <a name="type-parameters"></a><span data-ttu-id="2078c-127">Typparameter</span><span class="sxs-lookup"><span data-stu-id="2078c-127">Type Parameters</span></span>  
 <span data-ttu-id="2078c-128">Ein *generische Prozedur* definiert auch eine oder mehrere *Typparameter* zusätzlich zu den normalen Parametern.</span><span class="sxs-lookup"><span data-stu-id="2078c-128">A *generic procedure* also defines one or more *type parameters* in addition to its normal parameters.</span></span> <span data-ttu-id="2078c-129">Eine generische Prozedur kann der aufrufenden Code unterschiedliche Datentypen jedes Mal übergeben sie der Prozedur wird, damit sie die Datentypen, die Anforderungen eines einzelnen Aufrufs anpassen kann.</span><span class="sxs-lookup"><span data-stu-id="2078c-129">A generic procedure allows the calling code to pass different data types each time it calls the procedure, so it can tailor the data types to the requirements of each individual call.</span></span> <span data-ttu-id="2078c-130">Siehe [Generic Procedures in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="2078c-130">See [Generic Procedures in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-procedures.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2078c-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2078c-131">See also</span></span>

- [<span data-ttu-id="2078c-132">Verfahren</span><span class="sxs-lookup"><span data-stu-id="2078c-132">Procedures</span></span>](./index.md)
- [<span data-ttu-id="2078c-133">Sub-Prozeduren</span><span class="sxs-lookup"><span data-stu-id="2078c-133">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="2078c-134">Function-Prozeduren</span><span class="sxs-lookup"><span data-stu-id="2078c-134">Function Procedures</span></span>](./function-procedures.md)
- [<span data-ttu-id="2078c-135">Eigenschaftenprozeduren</span><span class="sxs-lookup"><span data-stu-id="2078c-135">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="2078c-136">Operatorprozeduren</span><span class="sxs-lookup"><span data-stu-id="2078c-136">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="2078c-137">Vorgehensweise: Definieren eines Parameters für eine Prozedur</span><span class="sxs-lookup"><span data-stu-id="2078c-137">How to: Define a Parameter for a Procedure</span></span>](./how-to-define-a-parameter-for-a-procedure.md)
- [<span data-ttu-id="2078c-138">Vorgehensweise: Übergeben von Argumenten an eine Prozedur</span><span class="sxs-lookup"><span data-stu-id="2078c-138">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)
- [<span data-ttu-id="2078c-139">Übergeben von Argumenten als Wert und als Verweis</span><span class="sxs-lookup"><span data-stu-id="2078c-139">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="2078c-140">Prozedurüberladung</span><span class="sxs-lookup"><span data-stu-id="2078c-140">Procedure Overloading</span></span>](./procedure-overloading.md)
- [<span data-ttu-id="2078c-141">Typkonvertierung in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2078c-141">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
