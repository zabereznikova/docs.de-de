---
title: 'Gewusst wie: Überladen einer Prozedur mit optionalen Parametern'
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
ms.openlocfilehash: 4d31980e4b968cff274091ba4f307dffddab1100
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350865"
---
# <a name="how-to-overload-a-procedure-that-takes-optional-parameters-visual-basic"></a><span data-ttu-id="df60d-102">Gewusst wie: Überladen einer Prozedur mit optionalen Parametern (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="df60d-102">How to: Overload a Procedure that Takes Optional Parameters (Visual Basic)</span></span>
<span data-ttu-id="df60d-103">Wenn eine Prozedur über mindestens einen [optionalen](../../../../visual-basic/language-reference/modifiers/optional.md) Parameter verfügt, können Sie keine überladene Version definieren, die mit einer der impliziten über Ladungen übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="df60d-103">If a procedure has one or more [Optional](../../../../visual-basic/language-reference/modifiers/optional.md) parameters, you cannot define an overloaded version matching any of its implicit overloads.</span></span> <span data-ttu-id="df60d-104">Weitere Informationen finden Sie unter "implizite über Ladungen für optionale Parameter" in über [Legungen zu überladenden Prozeduren](./considerations-in-overloading-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="df60d-104">For more information, see "Implicit Overloads for Optional Parameters" in [Considerations in Overloading Procedures](./considerations-in-overloading-procedures.md).</span></span>  
  
## <a name="one-optional-parameter"></a><span data-ttu-id="df60d-105">Ein optionaler Parameter</span><span class="sxs-lookup"><span data-stu-id="df60d-105">One Optional Parameter</span></span>  
  
#### <a name="to-overload-a-procedure-that-takes-one-optional-parameter"></a><span data-ttu-id="df60d-106">So überladen Sie eine Prozedur, die einen optionalen Parameter annimmt</span><span class="sxs-lookup"><span data-stu-id="df60d-106">To overload a procedure that takes one optional parameter</span></span>  
  
1. <span data-ttu-id="df60d-107">Schreiben Sie eine `Sub` oder `Function` Deklarations Anweisung, die den optionalen Parameter in der Parameterliste enthält.</span><span class="sxs-lookup"><span data-stu-id="df60d-107">Write a `Sub` or `Function` declaration statement that includes the optional parameter in the parameter list.</span></span> <span data-ttu-id="df60d-108">Verwenden Sie das `Optional`-Schlüsselwort nicht in dieser überladenen Version.</span><span class="sxs-lookup"><span data-stu-id="df60d-108">Do not use the `Optional` keyword in this overloaded version.</span></span>  
  
2. <span data-ttu-id="df60d-109">Vor dem `Sub` oder `Function`-Schlüsselwort mit dem [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) -Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="df60d-109">Precede the `Sub` or `Function` keyword with the [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) keyword.</span></span>  
  
3. <span data-ttu-id="df60d-110">Schreiben Sie den Prozedur Code, der ausgeführt werden soll, wenn der aufrufende Code das optionale Argument bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="df60d-110">Write the procedure code that should execute when the calling code supplies the optional argument.</span></span>  
  
4. <span data-ttu-id="df60d-111">Beenden Sie die Prozedur mit der Anweisung `End Sub` oder `End Function`.</span><span class="sxs-lookup"><span data-stu-id="df60d-111">Terminate the procedure with the `End Sub` or `End Function` statement as appropriate.</span></span>  
  
5. <span data-ttu-id="df60d-112">Schreiben Sie eine zweite Deklarations Anweisung, die mit der ersten Deklaration identisch ist, mit dem Unterschied, dass Sie nicht den optionalen Parameter in der Parameterliste enthält.</span><span class="sxs-lookup"><span data-stu-id="df60d-112">Write a second declaration statement that is identical to the first declaration except that it does not include the optional parameter in the parameter list.</span></span>  
  
6. <span data-ttu-id="df60d-113">Schreiben Sie den Prozedur Code, der ausgeführt werden soll, wenn der aufrufende Code das optionale Argument nicht bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="df60d-113">Write the procedure code that should execute when the calling code does not supply the optional argument.</span></span> <span data-ttu-id="df60d-114">Beenden Sie die Prozedur mit der Anweisung `End Sub` oder `End Function`.</span><span class="sxs-lookup"><span data-stu-id="df60d-114">Terminate the procedure with the `End Sub` or `End Function` statement as appropriate.</span></span>  
  
     <span data-ttu-id="df60d-115">Das folgende Beispiel zeigt eine Prozedur, die mit einem optionalen Parameter definiert ist, einen entsprechenden Satz von zwei überladenen Prozeduren und schließlich Beispiele für ungültige und gültige überladene Versionen.</span><span class="sxs-lookup"><span data-stu-id="df60d-115">The following example shows a procedure defined with an optional parameter,  an equivalent set of two overloaded procedures, and finally examples of both invalid and valid overloaded versions.</span></span>  
  
     [!code-vb[VbVbcnProcedures#59](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#59)]  
  
     [!code-vb[VbVbcnProcedures#60](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#60)]  
  
     [!code-vb[VbVbcnProcedures#61](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#61)]  
  
## <a name="multiple-optional-parameters"></a><span data-ttu-id="df60d-116">Mehrere optionale Parameter</span><span class="sxs-lookup"><span data-stu-id="df60d-116">Multiple Optional Parameters</span></span>  
 <span data-ttu-id="df60d-117">Für eine Prozedur mit mehr als einem optionalen Parameter benötigen Sie normalerweise mehr als zwei überladene Versionen.</span><span class="sxs-lookup"><span data-stu-id="df60d-117">For a procedure with more than one optional parameter, you normally need more than two overloaded versions.</span></span> <span data-ttu-id="df60d-118">Wenn z. b. zwei optionale Parameter vorhanden sind und der Aufruf Code die einzelnen Parameter unabhängig vom anderen angeben oder weglassen kann, benötigen Sie vier überladene Versionen, eine für jede mögliche Kombination von bereitgestellten Argumenten.</span><span class="sxs-lookup"><span data-stu-id="df60d-118">For example, if there are two optional parameters, and the calling code can supply or omit each one independently of the other, you need four overloaded versions, one for each possible combination of supplied arguments.</span></span>  
  
 <span data-ttu-id="df60d-119">Wenn die Anzahl der optionalen Parameter zunimmt, erhöht sich die Komplexität der Überladung.</span><span class="sxs-lookup"><span data-stu-id="df60d-119">As the number of optional parameters increases, the complexity of the overloading increases.</span></span> <span data-ttu-id="df60d-120">Wenn keine Kombinationen von bereitgestellten Argumenten zulässig sind, benötigen Sie für N optionale Parameter 2 ^ N überladene Versionen.</span><span class="sxs-lookup"><span data-stu-id="df60d-120">Unless some combinations of supplied arguments are not acceptable, for N optional parameters you need 2 ^ N overloaded versions.</span></span> <span data-ttu-id="df60d-121">Abhängig von der Art der Prozedur können Sie feststellen, dass die Übersichtlichkeit der Logik den zusätzlichen Aufwand zum Definieren aller überladenen Versionen rechtfertigt.</span><span class="sxs-lookup"><span data-stu-id="df60d-121">Depending on the nature of the procedure, you might find that the clarity of logic justifies the extra effort of defining all the overloaded versions.</span></span>  
  
#### <a name="to-overload-a-procedure-that-takes-more-than-one-optional-parameter"></a><span data-ttu-id="df60d-122">So überladen Sie eine Prozedur, die mehr als einen optionalen Parameter annimmt</span><span class="sxs-lookup"><span data-stu-id="df60d-122">To overload a procedure that takes more than one optional parameter</span></span>  
  
1. <span data-ttu-id="df60d-123">Bestimmen Sie, welche Kombinationen von optionalen Argumenten für die Logik der Prozedur zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="df60d-123">Determine which combinations of supplied optional arguments are acceptable to the logic of the procedure.</span></span> <span data-ttu-id="df60d-124">Eine akzeptable Kombination kann auftreten, wenn ein optionaler Parameter von einem anderen abhängig ist.</span><span class="sxs-lookup"><span data-stu-id="df60d-124">An unacceptable combination might arise if one optional parameter depends on another.</span></span> <span data-ttu-id="df60d-125">Wenn z. b. ein Parameter den Namen einer Person akzeptiert und ein anderer das Alter der Person annimmt, ist eine Kombination von Argumenten, die das Alter angeben, aber nicht den Namen weglassen, nicht akzeptabel.</span><span class="sxs-lookup"><span data-stu-id="df60d-125">For example, if one parameter accepts a person's name and another accepts the person's age, a combination of arguments supplying the age but omitting the name is unacceptable.</span></span>  
  
2. <span data-ttu-id="df60d-126">Schreiben Sie für jede akzeptable Kombination von angegebenen optionalen Argumenten eine `Sub`-oder `Function` Deklarations Anweisung, die die entsprechende Parameterliste definiert.</span><span class="sxs-lookup"><span data-stu-id="df60d-126">For each acceptable combination of supplied optional arguments, write a `Sub` or `Function` declaration statement that defines the corresponding parameter list.</span></span> <span data-ttu-id="df60d-127">Verwenden Sie das `Optional`-Schlüsselwort nicht.</span><span class="sxs-lookup"><span data-stu-id="df60d-127">Do not use the `Optional` keyword.</span></span>  
  
3. <span data-ttu-id="df60d-128">Stellen Sie in jeder Deklaration dem `Sub`-oder `Function`-Schlüsselwort mit dem [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) -Schlüsselwort voran.</span><span class="sxs-lookup"><span data-stu-id="df60d-128">In each declaration, precede the `Sub` or `Function` keyword with the [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) keyword.</span></span>  
  
4. <span data-ttu-id="df60d-129">Schreiben Sie nach jeder Deklaration den Prozedur Code, der ausgeführt werden soll, wenn der aufrufende Code eine Argumentliste bereitstellt, die der Parameterliste der Deklaration entspricht.</span><span class="sxs-lookup"><span data-stu-id="df60d-129">Following each declaration, write the procedure code that should execute when the calling code supplies an argument list corresponding to that declaration's parameter list.</span></span>  
  
5. <span data-ttu-id="df60d-130">Beenden Sie die einzelnen Prozeduren entsprechend der Anweisung `End Sub` oder `End Function`.</span><span class="sxs-lookup"><span data-stu-id="df60d-130">Terminate each procedure with the `End Sub` or `End Function` statement as appropriate.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df60d-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="df60d-131">See also</span></span>

- [<span data-ttu-id="df60d-132">Verfahren</span><span class="sxs-lookup"><span data-stu-id="df60d-132">Procedures</span></span>](./index.md)
- [<span data-ttu-id="df60d-133">Parameter und Argumente von Prozeduren</span><span class="sxs-lookup"><span data-stu-id="df60d-133">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="df60d-134">Optionale Parameter</span><span class="sxs-lookup"><span data-stu-id="df60d-134">Optional Parameters</span></span>](./optional-parameters.md)
- [<span data-ttu-id="df60d-135">Parameterarrays</span><span class="sxs-lookup"><span data-stu-id="df60d-135">Parameter Arrays</span></span>](./parameter-arrays.md)
- [<span data-ttu-id="df60d-136">Prozedurüberladung</span><span class="sxs-lookup"><span data-stu-id="df60d-136">Procedure Overloading</span></span>](./procedure-overloading.md)
- [<span data-ttu-id="df60d-137">Problembehandlung bei Prozeduren</span><span class="sxs-lookup"><span data-stu-id="df60d-137">Troubleshooting Procedures</span></span>](./troubleshooting-procedures.md)
- [<span data-ttu-id="df60d-138">Gewusst wie: Definieren mehrerer Versionen einer Prozedur</span><span class="sxs-lookup"><span data-stu-id="df60d-138">How to: Define Multiple Versions of a Procedure</span></span>](./how-to-define-multiple-versions-of-a-procedure.md)
- [<span data-ttu-id="df60d-139">Gewusst wie: Aufrufen einer überladenen Prozedur</span><span class="sxs-lookup"><span data-stu-id="df60d-139">How to: Call an Overloaded Procedure</span></span>](./how-to-call-an-overloaded-procedure.md)
- [<span data-ttu-id="df60d-140">Gewusst wie: Überladen einer Prozedur mit einer unbestimmten Anzahl von Parametern</span><span class="sxs-lookup"><span data-stu-id="df60d-140">How to: Overload a Procedure that Takes an Indefinite Number of Parameters</span></span>](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [<span data-ttu-id="df60d-141">Überladungsauflösung</span><span class="sxs-lookup"><span data-stu-id="df60d-141">Overload Resolution</span></span>](./overload-resolution.md)
