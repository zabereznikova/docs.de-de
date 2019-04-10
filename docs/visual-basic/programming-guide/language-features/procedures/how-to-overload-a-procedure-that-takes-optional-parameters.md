---
title: 'Vorgehensweise: Überladen einer Prozedur mit optionalen Parametern (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], parameters
- procedure overloading [Visual Basic], optional parameters
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedure parameters
- procedures [Visual Basic], overloading
- procedures [Visual Basic], multiple versions
ms.assetid: 825f9d56-4cde-43fd-993a-b9171717e2eb
ms.openlocfilehash: 58c52a7d73efbd96d772dd85d6bf2c9084fb1241
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59320227"
---
# <a name="how-to-overload-a-procedure-that-takes-optional-parameters-visual-basic"></a><span data-ttu-id="77732-102">Vorgehensweise: Überladen einer Prozedur mit optionalen Parametern (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="77732-102">How to: Overload a Procedure that Takes Optional Parameters (Visual Basic)</span></span>
<span data-ttu-id="77732-103">Weist eine Prozedur, eine oder mehrere [Optional](../../../../visual-basic/language-reference/modifiers/optional.md) Parameter können nicht Sie eine überladene Version, die die implizite Überladungen übereinstimmende definieren.</span><span class="sxs-lookup"><span data-stu-id="77732-103">If a procedure has one or more [Optional](../../../../visual-basic/language-reference/modifiers/optional.md) parameters, you cannot define an overloaded version matching any of its implicit overloads.</span></span> <span data-ttu-id="77732-104">Weitere Informationen finden Sie unter "Implizite Überladungen für optionale Parameter" in [Überlegungen zu überladen von Prozeduren](./considerations-in-overloading-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="77732-104">For more information, see "Implicit Overloads for Optional Parameters" in [Considerations in Overloading Procedures](./considerations-in-overloading-procedures.md).</span></span>  
  
## <a name="one-optional-parameter"></a><span data-ttu-id="77732-105">Ein optionaler Parameter</span><span class="sxs-lookup"><span data-stu-id="77732-105">One Optional Parameter</span></span>  
  
#### <a name="to-overload-a-procedure-that-takes-one-optional-parameter"></a><span data-ttu-id="77732-106">Um eine Prozedur zu überladen, die einen optionalen Parameter akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="77732-106">To overload a procedure that takes one optional parameter</span></span>  
  
1. <span data-ttu-id="77732-107">Schreiben einer `Sub` oder `Function` -deklarationsanweisung in Verbindung, die den optionalen Parameter in der Parameterliste enthält.</span><span class="sxs-lookup"><span data-stu-id="77732-107">Write a `Sub` or `Function` declaration statement that includes the optional parameter in the parameter list.</span></span> <span data-ttu-id="77732-108">Verwenden Sie nicht die `Optional` -Schlüsselwort in die überladene Version.</span><span class="sxs-lookup"><span data-stu-id="77732-108">Do not use the `Optional` keyword in this overloaded version.</span></span>  
  
2. <span data-ttu-id="77732-109">Vorausgehen der `Sub` oder `Function` Schlüsselwort mit dem [Überladungen](../../../../visual-basic/language-reference/modifiers/overloads.md) Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="77732-109">Precede the `Sub` or `Function` keyword with the [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) keyword.</span></span>  
  
3. <span data-ttu-id="77732-110">Schreiben Sie den Code der Prozedur, der ausgeführt werden soll, wenn der aufrufende Code das optionale Argument bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="77732-110">Write the procedure code that should execute when the calling code supplies the optional argument.</span></span>  
  
4. <span data-ttu-id="77732-111">Beenden Sie die Prozedur mit der `End Sub` oder `End Function` Anweisung entsprechend.</span><span class="sxs-lookup"><span data-stu-id="77732-111">Terminate the procedure with the `End Sub` or `End Function` statement as appropriate.</span></span>  
  
5. <span data-ttu-id="77732-112">Schreiben Sie eine zweite deklarationsanweisung, die auf die erste Deklaration identisch ist, mit dem Unterschied, dass den optionalen Parameter in der Liste nicht enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="77732-112">Write a second declaration statement that is identical to the first declaration except that it does not include the optional parameter in the parameter list.</span></span>  
  
6. <span data-ttu-id="77732-113">Schreiben Sie den Code der Prozedur, der ausgeführt werden soll, wenn der aufrufende Code das optionale Argument nicht angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="77732-113">Write the procedure code that should execute when the calling code does not supply the optional argument.</span></span> <span data-ttu-id="77732-114">Beenden Sie die Prozedur mit der `End Sub` oder `End Function` Anweisung entsprechend.</span><span class="sxs-lookup"><span data-stu-id="77732-114">Terminate the procedure with the `End Sub` or `End Function` statement as appropriate.</span></span>  
  
     <span data-ttu-id="77732-115">Das folgende Beispiel zeigt eine Prozedur mit einem optionalen Parameter, einen entsprechenden Satz von zwei überladenen Prozeduren und schließlich Beispiele von ungültigen und gültigen überladenen Versionen definiert.</span><span class="sxs-lookup"><span data-stu-id="77732-115">The following example shows a procedure defined with an optional parameter,  an equivalent set of two overloaded procedures, and finally examples of both invalid and valid overloaded versions.</span></span>  
  
     [!code-vb[VbVbcnProcedures#59](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#59)]  
  
     [!code-vb[VbVbcnProcedures#60](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#60)]  
  
     [!code-vb[VbVbcnProcedures#61](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#61)]  
  
## <a name="multiple-optional-parameters"></a><span data-ttu-id="77732-116">Mehrere optionale Parameter</span><span class="sxs-lookup"><span data-stu-id="77732-116">Multiple Optional Parameters</span></span>  
 <span data-ttu-id="77732-117">Für eine Prozedur mit mehr als einen optionalen Parameter benötigen Sie normalerweise mehr als zwei überladene Versionen.</span><span class="sxs-lookup"><span data-stu-id="77732-117">For a procedure with more than one optional parameter, you normally need more than two overloaded versions.</span></span> <span data-ttu-id="77732-118">Beispielsweise benötigen, wenn zwei optionale Parameter vorhanden sind und der aufrufende Code angeben kann, oder lassen Sie die jeweils unabhängig voneinander Sie vier überladene Versionen für jede mögliche Kombination von der angegebenen Argumente.</span><span class="sxs-lookup"><span data-stu-id="77732-118">For example, if there are two optional parameters, and the calling code can supply or omit each one independently of the other, you need four overloaded versions, one for each possible combination of supplied arguments.</span></span>  
  
 <span data-ttu-id="77732-119">Mit zunehmender Anzahl Optionaler Parameter, erhöht die Komplexität der überladen.</span><span class="sxs-lookup"><span data-stu-id="77732-119">As the number of optional parameters increases, the complexity of the overloading increases.</span></span> <span data-ttu-id="77732-120">Wenn einige Kombinationen der bereitgestellten Argumente nicht akzeptabel sind, für N optionale Parameter benötigen Sie 2 ^ N überladene Versionen.</span><span class="sxs-lookup"><span data-stu-id="77732-120">Unless some combinations of supplied arguments are not acceptable, for N optional parameters you need 2 ^ N overloaded versions.</span></span> <span data-ttu-id="77732-121">Je nach Art der Prozedur stellen Sie möglicherweise fest, dass die Verständlichkeit der Logik den zusätzlichen Aufwand für alle überladenen Versionen definiert rechtfertigt.</span><span class="sxs-lookup"><span data-stu-id="77732-121">Depending on the nature of the procedure, you might find that the clarity of logic justifies the extra effort of defining all the overloaded versions.</span></span>  
  
#### <a name="to-overload-a-procedure-that-takes-more-than-one-optional-parameter"></a><span data-ttu-id="77732-122">Um eine Prozedur zu überladen, die mehr als einen optionalen Parameter akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="77732-122">To overload a procedure that takes more than one optional parameter</span></span>  
  
1. <span data-ttu-id="77732-123">Bestimmen Sie, welche Kombinationen der bereitgestellten optionalen Argumente an die Logik der Prozedur zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="77732-123">Determine which combinations of supplied optional arguments are acceptable to the logic of the procedure.</span></span> <span data-ttu-id="77732-124">Eine unannehmbare Kombination kann auftreten, wenn Sie einen Optionaler Parameter von einer anderen abhängt.</span><span class="sxs-lookup"><span data-stu-id="77732-124">An unacceptable combination might arise if one optional parameter depends on another.</span></span> <span data-ttu-id="77732-125">Beispielsweise ist, wenn Sie einen Parameter akzeptiert, Name des Partners, und eine andere akzeptiert die Spouse Alter, eine Kombination von Argumenten, die das Alter angeben, aber wenn den Namen nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="77732-125">For example, if one parameter accepts a spouse's name and another accepts the spouse's age, a combination of arguments supplying the age but omitting the name is unacceptable.</span></span>  
  
2. <span data-ttu-id="77732-126">Schreiben Sie für jede zulässige Kombination bereitgestellte optionale Argumente, eine `Sub` oder `Function` -deklarationsanweisung in Verbindung, die die entsprechenden Parameterliste definiert.</span><span class="sxs-lookup"><span data-stu-id="77732-126">For each acceptable combination of supplied optional arguments, write a `Sub` or `Function` declaration statement that defines the corresponding parameter list.</span></span> <span data-ttu-id="77732-127">Verwenden Sie nicht die `Optional` Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="77732-127">Do not use the `Optional` keyword.</span></span>  
  
3. <span data-ttu-id="77732-128">In jeder Deklaration vorausgehen der `Sub` oder `Function` Schlüsselwort mit dem [Überladungen](../../../../visual-basic/language-reference/modifiers/overloads.md) Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="77732-128">In each declaration, precede the `Sub` or `Function` keyword with the [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) keyword.</span></span>  
  
4. <span data-ttu-id="77732-129">Schreiben Sie nach jeder Deklaration den Code der Prozedur, der ausgeführt werden soll, wenn der aufrufende Code eine Argumentliste, die für diese Deklaration in der Parameterliste bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="77732-129">Following each declaration, write the procedure code that should execute when the calling code supplies an argument list corresponding to that declaration's parameter list.</span></span>  
  
5. <span data-ttu-id="77732-130">Beenden Sie jede Prozedur mit der `End Sub` oder `End Function` Anweisung entsprechend.</span><span class="sxs-lookup"><span data-stu-id="77732-130">Terminate each procedure with the `End Sub` or `End Function` statement as appropriate.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77732-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="77732-131">See also</span></span>

- [<span data-ttu-id="77732-132">Verfahren</span><span class="sxs-lookup"><span data-stu-id="77732-132">Procedures</span></span>](./index.md)
- [<span data-ttu-id="77732-133">Parameter und Argumente von Prozeduren</span><span class="sxs-lookup"><span data-stu-id="77732-133">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="77732-134">Optionale Parameter</span><span class="sxs-lookup"><span data-stu-id="77732-134">Optional Parameters</span></span>](./optional-parameters.md)
- [<span data-ttu-id="77732-135">Parameterarrays</span><span class="sxs-lookup"><span data-stu-id="77732-135">Parameter Arrays</span></span>](./parameter-arrays.md)
- [<span data-ttu-id="77732-136">Prozedurüberladung</span><span class="sxs-lookup"><span data-stu-id="77732-136">Procedure Overloading</span></span>](./procedure-overloading.md)
- [<span data-ttu-id="77732-137">Problembehandlung bei Prozeduren</span><span class="sxs-lookup"><span data-stu-id="77732-137">Troubleshooting Procedures</span></span>](./troubleshooting-procedures.md)
- [<span data-ttu-id="77732-138">Vorgehensweise: Definieren mehrerer Versionen einer Prozedur</span><span class="sxs-lookup"><span data-stu-id="77732-138">How to: Define Multiple Versions of a Procedure</span></span>](./how-to-define-multiple-versions-of-a-procedure.md)
- [<span data-ttu-id="77732-139">Vorgehensweise: Aufrufen einer überladenen Prozedur</span><span class="sxs-lookup"><span data-stu-id="77732-139">How to: Call an Overloaded Procedure</span></span>](./how-to-call-an-overloaded-procedure.md)
- [<span data-ttu-id="77732-140">Vorgehensweise: Überladen einer Prozedur mit einer unbestimmten Anzahl von Parametern</span><span class="sxs-lookup"><span data-stu-id="77732-140">How to: Overload a Procedure that Takes an Indefinite Number of Parameters</span></span>](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [<span data-ttu-id="77732-141">Overload Resolution</span><span class="sxs-lookup"><span data-stu-id="77732-141">Overload Resolution</span></span>](./overload-resolution.md)
