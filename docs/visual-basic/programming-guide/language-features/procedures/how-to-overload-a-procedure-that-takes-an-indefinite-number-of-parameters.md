---
title: 'Gewusst wie: Überladen einer Prozedur mit einer unbestimmten Anzahl von Parametern (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], parameters
- procedure overloading [Visual Basic], indefinite number of parameters
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedure parameters
- procedures [Visual Basic], overloading
- procedures [Visual Basic], multiple versions
ms.assetid: c7042de2-2422-4039-94e8-ac298896af69
ms.openlocfilehash: 026dd59db135e8b195ae014aaff5e3a6a7846fc7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33651491"
---
# <a name="how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters-visual-basic"></a><span data-ttu-id="6d525-102">Gewusst wie: Überladen einer Prozedur mit einer unbestimmten Anzahl von Parametern (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6d525-102">How to: Overload a Procedure that Takes an Indefinite Number of Parameters (Visual Basic)</span></span>
<span data-ttu-id="6d525-103">Wenn eine Prozedur besitzt einen [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) Parameter keine überladene Version ein eindimensionales Array für das Parameterarray definieren.</span><span class="sxs-lookup"><span data-stu-id="6d525-103">If a procedure has a [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) parameter, you cannot define an overloaded version taking a one-dimensional array for the parameter array.</span></span> <span data-ttu-id="6d525-104">Weitere Informationen finden Sie unter "Implizite Überladungen für ein ParamArray-Parameter" in [Überlegungen in Überladen von Prozeduren](./considerations-in-overloading-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="6d525-104">For more information, see "Implicit Overloads for a ParamArray Parameter" in [Considerations in Overloading Procedures](./considerations-in-overloading-procedures.md).</span></span>  
  
### <a name="to-overload-a-procedure-that-takes-a-variable-number-of-parameters"></a><span data-ttu-id="6d525-105">So überladen eine Prozedur ausgeführt wird, die eine Variable Anzahl von Parametern</span><span class="sxs-lookup"><span data-stu-id="6d525-105">To overload a procedure that takes a variable number of parameters</span></span>  
  
1.  <span data-ttu-id="6d525-106">Ermitteln Sie, dass die Prozedur und Aufrufen von Code Logik Vorteile von Versionen aus mehr als überladene eine `ParamArray` Parameter.</span><span class="sxs-lookup"><span data-stu-id="6d525-106">Ascertain that the procedure and calling code logic benefits from overloaded versions more than from a `ParamArray` parameter.</span></span> <span data-ttu-id="6d525-107">Finden Sie unter "Überladungen und ParamArrays" in [Überlegungen zur prozedurüberladung](./considerations-in-overloading-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="6d525-107">See "Overloads and ParamArrays" in [Considerations in Overloading Procedures](./considerations-in-overloading-procedures.md).</span></span>  
  
2.  <span data-ttu-id="6d525-108">Bestimmen Sie die Anzahl der bereitgestellten Werte die Prozedur in der Variable Teil der Parameterliste akzeptieren soll.</span><span class="sxs-lookup"><span data-stu-id="6d525-108">Determine which numbers of supplied values the procedure should accept in the variable part of the parameter list.</span></span> <span data-ttu-id="6d525-109">Dazu gehören beispielsweise die Groß-/Kleinschreibung kein Wert ggf., und diese den Fall eines einzelnen eindimensionalen Arrays.</span><span class="sxs-lookup"><span data-stu-id="6d525-109">This might include the case of no value, and it might include the case of a single one-dimensional array.</span></span>  
  
3.  <span data-ttu-id="6d525-110">Schreiben Sie für jede zulässige Anzahl der bereitgestellten Werte, eine `Sub` oder `Function` deklarationsanweisung, mit dem die Parameterliste der entsprechenden definiert.</span><span class="sxs-lookup"><span data-stu-id="6d525-110">For each acceptable number of supplied values, write a `Sub` or `Function` declaration statement that defines the corresponding parameter list.</span></span> <span data-ttu-id="6d525-111">Verwenden Sie weder die `Optional` oder `ParamArray` Schlüsselwort in dieser überladenen Version.</span><span class="sxs-lookup"><span data-stu-id="6d525-111">Do not use either the `Optional` or the `ParamArray` keyword in this overloaded version.</span></span>  
  
4.  <span data-ttu-id="6d525-112">In jede Deklaration davor der `Sub` oder `Function` Schlüsselwort mit der [überlädt](../../../../visual-basic/language-reference/modifiers/overloads.md) Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="6d525-112">In each declaration, precede the `Sub` or `Function` keyword with the [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) keyword.</span></span>  
  
5.  <span data-ttu-id="6d525-113">Schreiben Sie nach jeder Deklaration der Prozedurcode, der ausgeführt werden soll, wenn der aufrufende Code Werten, die diese Deklaration Parameterliste bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="6d525-113">Following each declaration, write the procedure code that should execute when the calling code supplies values corresponding to that declaration's parameter list.</span></span>  
  
6.  <span data-ttu-id="6d525-114">Beenden Sie jede Prozedur mit der `End Sub` oder `End Function` Anweisung entsprechend.</span><span class="sxs-lookup"><span data-stu-id="6d525-114">Terminate each procedure with the `End Sub` or `End Function` statement as appropriate.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6d525-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6d525-115">Example</span></span>  
 <span data-ttu-id="6d525-116">Das folgende Beispiel zeigt eine Prozedur mit definiert eine [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) übergeben wird, und kein äquivalenter Satz einer überladenen Prozeduren.</span><span class="sxs-lookup"><span data-stu-id="6d525-116">The following example shows a procedure defined with a [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) parameter, and then an equivalent set of overloaded procedures.</span></span>  
  
 [!code-vb[VbVbcnProcedures#69](./codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters_1.vb)]  
  
 [!code-vb[VbVbcnProcedures#70](./codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters_2.vb)]  
  
 <span data-ttu-id="6d525-117">Sie können sich nicht auf eine solche Prozedur mit einer Parameterliste überladen, die ein eindimensionales Array für das Parameterarray akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="6d525-117">You cannot overload such a procedure with a parameter list that takes a one-dimensional array for the parameter array.</span></span> <span data-ttu-id="6d525-118">Allerdings können Sie die Signaturen der implizite Überladungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="6d525-118">However, you can use the signatures of the other implicit overloads.</span></span> <span data-ttu-id="6d525-119">Die folgenden Deklarationen veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="6d525-119">The following declarations illustrate this.</span></span>  
  
 [!code-vb[VbVbcnProcedures#71](./codesnippet/VisualBasic/how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters_3.vb)]  
  
 <span data-ttu-id="6d525-120">Der Code der überladenen Versionen muss keine testen, ob der aufrufende Code eine oder mehrere Werte für bereitgestellt der `ParamArray` Parameter, oder wenn dies der Fall ist, wie viele.</span><span class="sxs-lookup"><span data-stu-id="6d525-120">The code in the overloaded versions does not have to test whether the calling code supplied one or more values for the `ParamArray` parameter, or if so, how many.</span></span> <span data-ttu-id="6d525-121">Visual Basic übergibt die Steuerung an die Version der aufrufenden Argumentliste entspricht.</span><span class="sxs-lookup"><span data-stu-id="6d525-121">Visual Basic passes control to the version matching the calling argument list.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="6d525-122">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="6d525-122">Compiling the Code</span></span>  
 <span data-ttu-id="6d525-123">Da eine Prozedur mit einem `ParamArray` Parameter entspricht einem Satz von überladenen Versionen, eine solche Prozedur mit einer Parameterliste entspricht einem beliebigen diese implizite Überladungen können nicht überladen werden können.</span><span class="sxs-lookup"><span data-stu-id="6d525-123">Because a procedure with a `ParamArray` parameter is equivalent to a set of overloaded versions, you cannot overload such a procedure with a parameter list corresponding to any of these implicit overloads.</span></span> <span data-ttu-id="6d525-124">Weitere Informationen finden Sie unter [Überlegungen in Überladen von Prozeduren](./considerations-in-overloading-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="6d525-124">For more information, see [Considerations in Overloading Procedures](./considerations-in-overloading-procedures.md).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="6d525-125">.NET Framework-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="6d525-125">.NET Framework Security</span></span>  
 <span data-ttu-id="6d525-126">Wenn Sie mit einem Array, das unendlich groß sein kann arbeiten, besteht die Gefahr, dass einige interne Kapazität der Anwendung überschritten.</span><span class="sxs-lookup"><span data-stu-id="6d525-126">Whenever you deal with an array which can be indefinitely large, there is a risk of overrunning some internal capacity of your application.</span></span> <span data-ttu-id="6d525-127">Wenn Sie ein Parameterarray akzeptieren, sollten Sie für die Länge des Arrays an der aufrufende Code testen und entsprechende Maßnahmen ergreifen, wenn sie für Ihre Anwendung zu groß ist.</span><span class="sxs-lookup"><span data-stu-id="6d525-127">If you accept a parameter array, you should test for the length of the array the calling code passed to it, and take appropriate steps if it is too large for your application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d525-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6d525-128">See Also</span></span>  
 [<span data-ttu-id="6d525-129">Verfahren</span><span class="sxs-lookup"><span data-stu-id="6d525-129">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="6d525-130">Parameter und Argumente von Prozeduren</span><span class="sxs-lookup"><span data-stu-id="6d525-130">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="6d525-131">Optionale Parameter</span><span class="sxs-lookup"><span data-stu-id="6d525-131">Optional Parameters</span></span>](./optional-parameters.md)  
 [<span data-ttu-id="6d525-132">Parameterarrays</span><span class="sxs-lookup"><span data-stu-id="6d525-132">Parameter Arrays</span></span>](./parameter-arrays.md)  
 [<span data-ttu-id="6d525-133">Prozedurüberladung</span><span class="sxs-lookup"><span data-stu-id="6d525-133">Procedure Overloading</span></span>](./procedure-overloading.md)  
 [<span data-ttu-id="6d525-134">Problembehandlung bei Prozeduren</span><span class="sxs-lookup"><span data-stu-id="6d525-134">Troubleshooting Procedures</span></span>](./troubleshooting-procedures.md)  
 [<span data-ttu-id="6d525-135">Gewusst wie: Definieren mehrerer Versionen einer Prozedur</span><span class="sxs-lookup"><span data-stu-id="6d525-135">How to: Define Multiple Versions of a Procedure</span></span>](./how-to-define-multiple-versions-of-a-procedure.md)  
 [<span data-ttu-id="6d525-136">Gewusst wie: Aufrufen einer überladenen Prozedur</span><span class="sxs-lookup"><span data-stu-id="6d525-136">How to: Call an Overloaded Procedure</span></span>](./how-to-call-an-overloaded-procedure.md)  
 [<span data-ttu-id="6d525-137">Gewusst wie: Überladen einer Prozedur mit optionalen Parametern</span><span class="sxs-lookup"><span data-stu-id="6d525-137">How to: Overload a Procedure that Takes Optional Parameters</span></span>](./how-to-overload-a-procedure-that-takes-optional-parameters.md)  
 [<span data-ttu-id="6d525-138">Überladungsauflösung</span><span class="sxs-lookup"><span data-stu-id="6d525-138">Overload Resolution</span></span>](./overload-resolution.md)
