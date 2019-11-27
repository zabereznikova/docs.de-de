---
title: 'Gewusst wie: Überladen einer Prozedur mit einer unbestimmten Anzahl von Parametern'
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
ms.openlocfilehash: 047d566c13f03803d2e5c3bc6cce0db56df4a3f0
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345847"
---
# <a name="how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters-visual-basic"></a><span data-ttu-id="94443-102">Gewusst wie: Überladen einer Prozedur mit einer unbestimmten Anzahl von Parametern (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="94443-102">How to: Overload a Procedure that Takes an Indefinite Number of Parameters (Visual Basic)</span></span>
<span data-ttu-id="94443-103">Wenn eine Prozedur über einen [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) -Parameter verfügt, können Sie keine überladene Version definieren, die ein eindimensionales Array für das Parameter Array annimmt.</span><span class="sxs-lookup"><span data-stu-id="94443-103">If a procedure has a [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) parameter, you cannot define an overloaded version taking a one-dimensional array for the parameter array.</span></span> <span data-ttu-id="94443-104">Weitere Informationen finden Sie unter "implizite über Ladungen für einen ParamArray-Parameter" in über [Legungen zum Überladen von Prozeduren](./considerations-in-overloading-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="94443-104">For more information, see "Implicit Overloads for a ParamArray Parameter" in [Considerations in Overloading Procedures](./considerations-in-overloading-procedures.md).</span></span>  
  
### <a name="to-overload-a-procedure-that-takes-a-variable-number-of-parameters"></a><span data-ttu-id="94443-105">So überladen Sie eine Prozedur, die eine Variable Anzahl von Parametern annimmt</span><span class="sxs-lookup"><span data-stu-id="94443-105">To overload a procedure that takes a variable number of parameters</span></span>  
  
1. <span data-ttu-id="94443-106">Stellen Sie sicher, dass die Prozedur und die Aufruf Code Logik von überladenen Versionen mehr als von einem `ParamArray` Parameter profitieren.</span><span class="sxs-lookup"><span data-stu-id="94443-106">Ascertain that the procedure and calling code logic benefits from overloaded versions more than from a `ParamArray` parameter.</span></span> <span data-ttu-id="94443-107">Weitere Informationen finden Sie unter "über Ladungen und Parametern" in [überladenden Prozeduren](./considerations-in-overloading-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="94443-107">See "Overloads and ParamArrays" in [Considerations in Overloading Procedures](./considerations-in-overloading-procedures.md).</span></span>  
  
2. <span data-ttu-id="94443-108">Bestimmen Sie, welche Anzahl von bereitgestellten Werten die Prozedur im Variablen Teil der Parameterliste akzeptieren soll.</span><span class="sxs-lookup"><span data-stu-id="94443-108">Determine which numbers of supplied values the procedure should accept in the variable part of the parameter list.</span></span> <span data-ttu-id="94443-109">Dies kann die Groß-/Kleinschreibung ohne Wert einschließen und die Groß-/Kleinschreibung eines einzelnen eindimensionalen Arrays enthalten.</span><span class="sxs-lookup"><span data-stu-id="94443-109">This might include the case of no value, and it might include the case of a single one-dimensional array.</span></span>  
  
3. <span data-ttu-id="94443-110">Schreiben Sie für jede akzeptable Anzahl von bereitgestellten Werten eine `Sub` oder `Function` Deklarations Anweisung, die die entsprechende Parameterliste definiert.</span><span class="sxs-lookup"><span data-stu-id="94443-110">For each acceptable number of supplied values, write a `Sub` or `Function` declaration statement that defines the corresponding parameter list.</span></span> <span data-ttu-id="94443-111">Verwenden Sie in dieser überladenen Version weder das `Optional`-noch das `ParamArray`-Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="94443-111">Do not use either the `Optional` or the `ParamArray` keyword in this overloaded version.</span></span>  
  
4. <span data-ttu-id="94443-112">Stellen Sie in jeder Deklaration dem `Sub`-oder `Function`-Schlüsselwort mit dem [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) -Schlüsselwort voran.</span><span class="sxs-lookup"><span data-stu-id="94443-112">In each declaration, precede the `Sub` or `Function` keyword with the [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) keyword.</span></span>  
  
5. <span data-ttu-id="94443-113">Schreiben Sie nach jeder Deklaration den Prozedur Code, der ausgeführt werden soll, wenn der aufrufende Code Werte bereitstellt, die der Parameterliste der Deklaration entsprechen.</span><span class="sxs-lookup"><span data-stu-id="94443-113">Following each declaration, write the procedure code that should execute when the calling code supplies values corresponding to that declaration's parameter list.</span></span>  
  
6. <span data-ttu-id="94443-114">Beenden Sie die einzelnen Prozeduren entsprechend der Anweisung `End Sub` oder `End Function`.</span><span class="sxs-lookup"><span data-stu-id="94443-114">Terminate each procedure with the `End Sub` or `End Function` statement as appropriate.</span></span>  
  
## <a name="example"></a><span data-ttu-id="94443-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="94443-115">Example</span></span>  
 <span data-ttu-id="94443-116">Das folgende Beispiel zeigt eine Prozedur, die mit einem [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) -Parameter definiert wurde, und dann einen entsprechenden Satz überladener Prozeduren.</span><span class="sxs-lookup"><span data-stu-id="94443-116">The following example shows a procedure defined with a [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) parameter, and then an equivalent set of overloaded procedures.</span></span>  
  
 [!code-vb[VbVbcnProcedures#69](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#69)]  
  
 [!code-vb[VbVbcnProcedures#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#70)]  
  
 <span data-ttu-id="94443-117">Eine solche Prozedur kann nicht mit einer Parameterliste überladen werden, die ein eindimensionales Array für das Parameter Array annimmt.</span><span class="sxs-lookup"><span data-stu-id="94443-117">You cannot overload such a procedure with a parameter list that takes a one-dimensional array for the parameter array.</span></span> <span data-ttu-id="94443-118">Allerdings können Sie die Signaturen der anderen impliziten über Ladungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="94443-118">However, you can use the signatures of the other implicit overloads.</span></span> <span data-ttu-id="94443-119">Dies wird in den folgenden Deklarationen veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="94443-119">The following declarations illustrate this.</span></span>  
  
 [!code-vb[VbVbcnProcedures#71](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#71)]  
  
 <span data-ttu-id="94443-120">Der Code in den überladenen Versionen muss nicht prüfen, ob der aufrufende Code einen oder mehrere Werte für den `ParamArray` Parameter bereitgestellt hat, oder wenn ja, wie viele.</span><span class="sxs-lookup"><span data-stu-id="94443-120">The code in the overloaded versions does not have to test whether the calling code supplied one or more values for the `ParamArray` parameter, or if so, how many.</span></span> <span data-ttu-id="94443-121">Visual Basic übergibt die Steuerung an die Version, die der aufrufenden Argumentliste entspricht.</span><span class="sxs-lookup"><span data-stu-id="94443-121">Visual Basic passes control to the version matching the calling argument list.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="94443-122">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="94443-122">Compiling the Code</span></span>  
 <span data-ttu-id="94443-123">Da eine Prozedur mit einem `ParamArray`-Parameter einem Satz überladener Versionen entspricht, können Sie diese Prozedur nicht mit einer Parameterliste überladen, die einer dieser impliziten über Ladungen entspricht.</span><span class="sxs-lookup"><span data-stu-id="94443-123">Because a procedure with a `ParamArray` parameter is equivalent to a set of overloaded versions, you cannot overload such a procedure with a parameter list corresponding to any of these implicit overloads.</span></span> <span data-ttu-id="94443-124">Weitere Informationen finden Sie unter [Überlegungen zum Überladen von Prozeduren](./considerations-in-overloading-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="94443-124">For more information, see [Considerations in Overloading Procedures](./considerations-in-overloading-procedures.md).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="94443-125">.NET Framework-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="94443-125">.NET Framework Security</span></span>  
 <span data-ttu-id="94443-126">Wenn Sie sich mit einem Array befassen, das unbegrenzt groß sein kann, besteht das Risiko, dass eine interne Kapazität der Anwendung überschritten wird.</span><span class="sxs-lookup"><span data-stu-id="94443-126">Whenever you deal with an array which can be indefinitely large, there is a risk of overrunning some internal capacity of your application.</span></span> <span data-ttu-id="94443-127">Wenn Sie ein Parameter Array akzeptieren, sollten Sie auf die Länge des Arrays testen, das an den aufrufenden Code übergeben wurde, und die entsprechenden Schritte ausführen, wenn Sie für Ihre Anwendung zu groß sind.</span><span class="sxs-lookup"><span data-stu-id="94443-127">If you accept a parameter array, you should test for the length of the array the calling code passed to it, and take appropriate steps if it is too large for your application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94443-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="94443-128">See also</span></span>

- [<span data-ttu-id="94443-129">Verfahren</span><span class="sxs-lookup"><span data-stu-id="94443-129">Procedures</span></span>](./index.md)
- [<span data-ttu-id="94443-130">Parameter und Argumente von Prozeduren</span><span class="sxs-lookup"><span data-stu-id="94443-130">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="94443-131">Optionale Parameter</span><span class="sxs-lookup"><span data-stu-id="94443-131">Optional Parameters</span></span>](./optional-parameters.md)
- [<span data-ttu-id="94443-132">Parameterarrays</span><span class="sxs-lookup"><span data-stu-id="94443-132">Parameter Arrays</span></span>](./parameter-arrays.md)
- [<span data-ttu-id="94443-133">Prozedurüberladung</span><span class="sxs-lookup"><span data-stu-id="94443-133">Procedure Overloading</span></span>](./procedure-overloading.md)
- [<span data-ttu-id="94443-134">Problembehandlung bei Prozeduren</span><span class="sxs-lookup"><span data-stu-id="94443-134">Troubleshooting Procedures</span></span>](./troubleshooting-procedures.md)
- [<span data-ttu-id="94443-135">Gewusst wie: Definieren mehrerer Versionen einer Prozedur</span><span class="sxs-lookup"><span data-stu-id="94443-135">How to: Define Multiple Versions of a Procedure</span></span>](./how-to-define-multiple-versions-of-a-procedure.md)
- [<span data-ttu-id="94443-136">Gewusst wie: Aufrufen einer überladenen Prozedur</span><span class="sxs-lookup"><span data-stu-id="94443-136">How to: Call an Overloaded Procedure</span></span>](./how-to-call-an-overloaded-procedure.md)
- [<span data-ttu-id="94443-137">Gewusst wie: Überladen einer Prozedur mit optionalen Parametern</span><span class="sxs-lookup"><span data-stu-id="94443-137">How to: Overload a Procedure that Takes Optional Parameters</span></span>](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [<span data-ttu-id="94443-138">Überladungsauflösung</span><span class="sxs-lookup"><span data-stu-id="94443-138">Overload Resolution</span></span>](./overload-resolution.md)
