---
title: Überlegungen zur Prozedurüberladung
ms.date: 07/20/2015
helpviewer_keywords:
- signatures [Visual Basic], ParamArray arguments
- ParamArray keyword [Visual Basic], parameter arrays
- ParamArray keyword [Visual Basic], arguments and signatures
- function overloading [Visual Basic], implicit overloads for ParamArray
- ParamArray keyword [Visual Basic], signatures
- Visual Basic code, procedures
- arguments [Visual Basic], parameter arrays
- procedures [Visual Basic], overloading
- parameters [Visual Basic], lists
- function overloading [Visual Basic], typeless programming
- typeless programming
- function overloading [Visual Basic], restrictions
- arguments [Visual Basic], optional
- optional arguments [Visual Basic], overloading
- signatures [Visual Basic], procedure
- parameter lists [Visual Basic]
- parameter arrays [Visual Basic], overloading arguments
- Visual Basic code, parameter lists
- procedure overloading [Visual Basic], considerations
- Option Explicit statement [Visual Basic]
- restrictions [Visual Basic], overloading procedures
- procedures [Visual Basic], parameter lists
ms.assetid: a2001248-10d0-42c5-b0ce-eeedc987319f
ms.openlocfilehash: c4075c87df8b9daa56ca1d35e0d6661598895fdc
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403368"
---
# <a name="considerations-in-overloading-procedures-visual-basic"></a><span data-ttu-id="91d0a-102">Überlegungen zur Prozedurüberladung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="91d0a-102">Considerations in Overloading Procedures (Visual Basic)</span></span>
<span data-ttu-id="91d0a-103">Wenn Sie eine Prozedur überladen, müssen Sie für jede überladene Version eine andere *Signatur* verwenden.</span><span class="sxs-lookup"><span data-stu-id="91d0a-103">When you overload a procedure, you must use a different *signature* for each overloaded version.</span></span> <span data-ttu-id="91d0a-104">Dies bedeutet in der Regel, dass jede Version eine andere Parameterliste angeben muss.</span><span class="sxs-lookup"><span data-stu-id="91d0a-104">This usually means each version must specify a different parameter list.</span></span> <span data-ttu-id="91d0a-105">Weitere Informationen finden Sie unter "andere Signatur" in [Prozedur Überladung](./procedure-overloading.md).</span><span class="sxs-lookup"><span data-stu-id="91d0a-105">For more information, see "Different Signature" in [Procedure Overloading](./procedure-overloading.md).</span></span>  
  
 <span data-ttu-id="91d0a-106">Sie können eine `Function` Prozedur mit einer Prozedur überladen `Sub` und umgekehrt, wenn Sie über unterschiedliche Signaturen verfügen.</span><span class="sxs-lookup"><span data-stu-id="91d0a-106">You can overload a `Function` procedure with a `Sub` procedure, and vice versa, provided they have different signatures.</span></span> <span data-ttu-id="91d0a-107">Zwei über Ladungen können sich nur dadurch unterscheiden, dass ein Wert einen Rückgabewert aufweist und der andere nicht.</span><span class="sxs-lookup"><span data-stu-id="91d0a-107">Two overloads cannot differ only in that one has a return value and the other does not.</span></span>  
  
 <span data-ttu-id="91d0a-108">Sie können eine Eigenschaft auf die gleiche Weise überladen wie eine Prozedur und mit denselben Einschränkungen.</span><span class="sxs-lookup"><span data-stu-id="91d0a-108">You can overload a property the same way you overload a procedure, and with the same restrictions.</span></span> <span data-ttu-id="91d0a-109">Es ist jedoch nicht möglich, eine Prozedur mit einer-Eigenschaft zu überladen, oder umgekehrt.</span><span class="sxs-lookup"><span data-stu-id="91d0a-109">However, you cannot overload a procedure with a property, or vice versa.</span></span>  
  
## <a name="alternatives-to-overloaded-versions"></a><span data-ttu-id="91d0a-110">Alternativen zu überladenen Versionen</span><span class="sxs-lookup"><span data-stu-id="91d0a-110">Alternatives to Overloaded Versions</span></span>  
 <span data-ttu-id="91d0a-111">Manchmal gibt es Alternativen zu überladenen Versionen, insbesondere dann, wenn das vorhanden sein von Argumenten optional ist oder die Zahl variabel ist.</span><span class="sxs-lookup"><span data-stu-id="91d0a-111">You sometimes have alternatives to overloaded versions, particularly when the presence of arguments is optional or their number is variable.</span></span>  
  
 <span data-ttu-id="91d0a-112">Beachten Sie, dass optionale Argumente nicht notwendigerweise von allen Sprachen unterstützt werden und Parameter Arrays auf Visual Basic beschränkt sind.</span><span class="sxs-lookup"><span data-stu-id="91d0a-112">Keep in mind that optional arguments are not necessarily supported by all languages, and parameter arrays are limited to Visual Basic.</span></span> <span data-ttu-id="91d0a-113">Wenn Sie eine Prozedur schreiben, die wahrscheinlich aus Code aufgerufen wird, der in einer von mehreren Sprachen geschrieben wurde, bieten überladene Versionen die größte Flexibilität.</span><span class="sxs-lookup"><span data-stu-id="91d0a-113">If you are writing a procedure that is likely to be called from code written in any of several different languages, overloaded versions offer the greatest flexibility.</span></span>  
  
### <a name="overloads-and-optional-arguments"></a><span data-ttu-id="91d0a-114">Über Ladungen und optionale Argumente</span><span class="sxs-lookup"><span data-stu-id="91d0a-114">Overloads and Optional Arguments</span></span>  
 <span data-ttu-id="91d0a-115">Wenn der Aufruf Code ein oder mehrere Argumente optional angeben oder weglassen kann, können Sie mehrere überladene Versionen definieren oder optionale Parameter verwenden.</span><span class="sxs-lookup"><span data-stu-id="91d0a-115">When the calling code can optionally supply or omit one or more arguments, you can define multiple overloaded versions or use optional parameters.</span></span>  
  
#### <a name="when-to-use-overloaded-versions"></a><span data-ttu-id="91d0a-116">Verwendung von überladenen Versionen</span><span class="sxs-lookup"><span data-stu-id="91d0a-116">When to Use Overloaded Versions</span></span>  
 <span data-ttu-id="91d0a-117">In den folgenden Fällen können Sie eine Reihe von überladenen Versionen definieren:</span><span class="sxs-lookup"><span data-stu-id="91d0a-117">You can consider defining a series of overloaded versions in the following cases:</span></span>  
  
- <span data-ttu-id="91d0a-118">Die Logik im Prozedur Code unterscheidet sich erheblich, je nachdem, ob der aufrufende Code ein optionales Argument bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="91d0a-118">The logic in the procedure code is significantly different depending on whether the calling code supplies an optional argument or not.</span></span>  
  
- <span data-ttu-id="91d0a-119">Der Prozedur Code kann nicht zuverlässig überprüfen, ob der aufrufende Code ein optionales Argument bereitgestellt hat.</span><span class="sxs-lookup"><span data-stu-id="91d0a-119">The procedure code cannot reliably test whether the calling code has supplied an optional argument.</span></span> <span data-ttu-id="91d0a-120">Dies ist z. b. der Fall, wenn es keinen möglichen Kandidaten für einen Standardwert gibt, den der aufrufende Code nicht bereitstellen konnte.</span><span class="sxs-lookup"><span data-stu-id="91d0a-120">This is the case, for example, if there is no possible candidate for a default value that the calling code could not be expected to supply.</span></span>  
  
#### <a name="when-to-use-optional-parameters"></a><span data-ttu-id="91d0a-121">Verwendung optionaler Parameter</span><span class="sxs-lookup"><span data-stu-id="91d0a-121">When to Use Optional Parameters</span></span>  
 <span data-ttu-id="91d0a-122">In den folgenden Fällen bevorzugen Sie möglicherweise einen oder mehrere optionale Parameter:</span><span class="sxs-lookup"><span data-stu-id="91d0a-122">You might prefer one or more optional parameters in the following cases:</span></span>  
  
- <span data-ttu-id="91d0a-123">Die einzige erforderliche Aktion, wenn der aufrufende Code kein optionales Argument bereitstellt, besteht darin, den-Parameter auf einen Standardwert festzulegen.</span><span class="sxs-lookup"><span data-stu-id="91d0a-123">The only required action when the calling code does not supply an optional argument is to set the parameter to a default value.</span></span> <span data-ttu-id="91d0a-124">In einem solchen Fall kann der Prozedur Code weniger kompliziert sein, wenn Sie eine einzelne Version mit einem oder mehreren `Optional` Parametern definieren.</span><span class="sxs-lookup"><span data-stu-id="91d0a-124">In such a case, the procedure code can be less complicated if you define a single version with one or more `Optional` parameters.</span></span>  
  
 <span data-ttu-id="91d0a-125">Weitere Informationen finden Sie unter [optionale Parameter](./optional-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="91d0a-125">For more information, see [Optional Parameters](./optional-parameters.md).</span></span>  
  
### <a name="overloads-and-paramarrays"></a><span data-ttu-id="91d0a-126">Über Ladungen und Parametern</span><span class="sxs-lookup"><span data-stu-id="91d0a-126">Overloads and ParamArrays</span></span>  
 <span data-ttu-id="91d0a-127">Wenn der Aufruf Code eine Variable Anzahl von Argumenten übergeben kann, können Sie mehrere überladene Versionen definieren oder ein Parameter Array verwenden.</span><span class="sxs-lookup"><span data-stu-id="91d0a-127">When the calling code can pass a variable number of arguments, you can define multiple overloaded versions or use a parameter array.</span></span>  
  
#### <a name="when-to-use-overloaded-versions"></a><span data-ttu-id="91d0a-128">Verwendung von überladenen Versionen</span><span class="sxs-lookup"><span data-stu-id="91d0a-128">When to Use Overloaded Versions</span></span>  
 <span data-ttu-id="91d0a-129">In den folgenden Fällen können Sie eine Reihe von überladenen Versionen definieren:</span><span class="sxs-lookup"><span data-stu-id="91d0a-129">You can consider defining a series of overloaded versions in the following cases:</span></span>  
  
- <span data-ttu-id="91d0a-130">Sie wissen, dass der aufrufenden Code niemals mehr als eine kleine Anzahl von Werten an das Parameter Array übergibt.</span><span class="sxs-lookup"><span data-stu-id="91d0a-130">You know that the calling code never passes more than a small number of values to the parameter array.</span></span>  
  
- <span data-ttu-id="91d0a-131">Die Logik im Prozedur Code unterscheidet sich deutlich von der Anzahl der Werte, die der Aufruf Code übergibt.</span><span class="sxs-lookup"><span data-stu-id="91d0a-131">The logic in the procedure code is significantly different depending on how many values the calling code passes.</span></span>  
  
- <span data-ttu-id="91d0a-132">Der Aufruf Code kann Werte verschiedener Datentypen übergeben.</span><span class="sxs-lookup"><span data-stu-id="91d0a-132">The calling code can pass values of different data types.</span></span>  
  
#### <a name="when-to-use-a-parameter-array"></a><span data-ttu-id="91d0a-133">Verwendung eines Parameter Arrays</span><span class="sxs-lookup"><span data-stu-id="91d0a-133">When to Use a Parameter Array</span></span>  
 <span data-ttu-id="91d0a-134">In den folgenden Fällen ist es besser, einen `ParamArray` Parameter zu übertragen:</span><span class="sxs-lookup"><span data-stu-id="91d0a-134">You are better served by a `ParamArray` parameter in the following cases:</span></span>  
  
- <span data-ttu-id="91d0a-135">Sie können nicht vorhersagen, wie viele Werte der aufrufende Code an das Parameter Array übergeben kann, und es kann eine große Zahl sein.</span><span class="sxs-lookup"><span data-stu-id="91d0a-135">You are not able to predict how many values the calling code can pass to the parameter array, and it could be a large number.</span></span>  
  
- <span data-ttu-id="91d0a-136">Die Prozedur Logik eignet sich zum Durchlaufen aller Werte, die der aufrufende Code übergibt, und führt im Wesentlichen die gleichen Vorgänge für jeden Wert aus.</span><span class="sxs-lookup"><span data-stu-id="91d0a-136">The procedure logic lends itself to iterating through all the values the calling code passes, performing essentially the same operations on every value.</span></span>  
  
 <span data-ttu-id="91d0a-137">Weitere Informationen finden Sie unter [Parameter Arrays](./parameter-arrays.md).</span><span class="sxs-lookup"><span data-stu-id="91d0a-137">For more information, see [Parameter Arrays](./parameter-arrays.md).</span></span>  
  
## <a name="implicit-overloads-for-optional-parameters"></a><span data-ttu-id="91d0a-138">Implizite über Ladungen für optionale Parameter</span><span class="sxs-lookup"><span data-stu-id="91d0a-138">Implicit Overloads for Optional Parameters</span></span>  
 <span data-ttu-id="91d0a-139">Eine Prozedur mit einem [optionalen](../../../language-reference/modifiers/optional.md) Parameter entspricht zwei überladenen Prozeduren, eine mit dem optionalen Parameter und eine ohne Sie.</span><span class="sxs-lookup"><span data-stu-id="91d0a-139">A procedure with an [Optional](../../../language-reference/modifiers/optional.md) parameter is equivalent to two overloaded procedures, one with the optional parameter and one without it.</span></span> <span data-ttu-id="91d0a-140">Eine solche Prozedur kann nicht mit einer Parameterliste überladen werden, die einer dieser beiden entspricht.</span><span class="sxs-lookup"><span data-stu-id="91d0a-140">You cannot overload such a procedure with a parameter list corresponding to either of these.</span></span> <span data-ttu-id="91d0a-141">Dies wird in den folgenden Deklarationen veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="91d0a-141">The following declarations illustrate this.</span></span>  
  
 [!code-vb[VbVbcnProcedures#58](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#58)]  
  
 [!code-vb[VbVbcnProcedures#60](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#60)]  
  
 [!code-vb[VbVbcnProcedures#61](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#61)]  
  
 <span data-ttu-id="91d0a-142">Für eine Prozedur mit mehr als einem optionalen Parameter gibt es eine Reihe impliziter über Ladungen, die mit der Logik erreicht werden, die im vorherigen Beispiel ähnlich ist.</span><span class="sxs-lookup"><span data-stu-id="91d0a-142">For a procedure with more than one optional parameter, there is a set of implicit overloads, arrived at by logic similar to that in the preceding example.</span></span>  
  
## <a name="implicit-overloads-for-a-paramarray-parameter"></a><span data-ttu-id="91d0a-143">Implizite über Ladungen für einen ParamArray-Parameter</span><span class="sxs-lookup"><span data-stu-id="91d0a-143">Implicit Overloads for a ParamArray Parameter</span></span>  
 <span data-ttu-id="91d0a-144">Der Compiler betrachtet eine Prozedur mit einem [ParamArray](../../../language-reference/modifiers/paramarray.md) -Parameter so, dass eine unendliche Anzahl von über Ladungen vorhanden ist, die sich voneinander unterscheiden, wenn der aufrufende Code wie folgt an das Parameter Array übergeben wird:</span><span class="sxs-lookup"><span data-stu-id="91d0a-144">The compiler considers a procedure with a [ParamArray](../../../language-reference/modifiers/paramarray.md) parameter to have an infinite number of overloads, differing from each other in what the calling code passes to the parameter array, as follows:</span></span>  
  
- <span data-ttu-id="91d0a-145">Eine Überladung für den Fall, dass der aufrufende Code kein Argument für den`ParamArray`</span><span class="sxs-lookup"><span data-stu-id="91d0a-145">One overload for when the calling code does not supply an argument to the `ParamArray`</span></span>  
  
- <span data-ttu-id="91d0a-146">Eine Überladung für den Fall, dass der aufrufenden Code ein eindimensionales Array vom Elementtyp bereitstellt. `ParamArray`</span><span class="sxs-lookup"><span data-stu-id="91d0a-146">One overload for when the calling code supplies a one-dimensional array of the `ParamArray` element type</span></span>  
  
- <span data-ttu-id="91d0a-147">Für jede positive ganze Zahl eine Überladung für den Fall, dass der aufrufenden Code diese Anzahl von Argumenten bereitstellt, jeweils der `ParamArray` Elementtyp.</span><span class="sxs-lookup"><span data-stu-id="91d0a-147">For every positive integer, one overload for when the calling code supplies that number of arguments, each of the `ParamArray` element type</span></span>  
  
 <span data-ttu-id="91d0a-148">Die folgenden Deklarationen veranschaulichen diese impliziten über Ladungen.</span><span class="sxs-lookup"><span data-stu-id="91d0a-148">The following declarations illustrate these implicit overloads.</span></span>  
  
 [!code-vb[VbVbcnProcedures#68](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#68)]  
  
 [!code-vb[VbVbcnProcedures#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#70)]  
  
 <span data-ttu-id="91d0a-149">Eine solche Prozedur kann nicht mit einer Parameterliste überladen werden, die ein eindimensionales Array für das Parameter Array annimmt.</span><span class="sxs-lookup"><span data-stu-id="91d0a-149">You cannot overload such a procedure with a parameter list that takes a one-dimensional array for the parameter array.</span></span> <span data-ttu-id="91d0a-150">Allerdings können Sie die Signaturen der anderen impliziten über Ladungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="91d0a-150">However, you can use the signatures of the other implicit overloads.</span></span> <span data-ttu-id="91d0a-151">Dies wird in den folgenden Deklarationen veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="91d0a-151">The following declarations illustrate this.</span></span>  
  
 [!code-vb[VbVbcnProcedures#71](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#71)]  
  
## <a name="typeless-programming-as-an-alternative-to-overloading"></a><span data-ttu-id="91d0a-152">Typlose Programmierung als Alternative zum Überladen</span><span class="sxs-lookup"><span data-stu-id="91d0a-152">Typeless Programming as an Alternative to Overloading</span></span>  
 <span data-ttu-id="91d0a-153">Wenn Sie zulassen möchten, dass der aufrufende Code verschiedene Datentypen an einen Parameter übergibt, ist eine alternative Methode die typlose Programmierung.</span><span class="sxs-lookup"><span data-stu-id="91d0a-153">If you want to allow the calling code to pass different data types to a parameter, an alternative approach is typeless programming.</span></span> <span data-ttu-id="91d0a-154">Sie können den Schalter für die Typüberprüfung auf festlegen, indem Sie `Off` entweder die [Option Strict-Anweisung](../../../language-reference/statements/option-strict-statement.md) oder die [-optionstrict-](../../../reference/command-line-compiler/optionstrict.md) Compileroption festlegen.</span><span class="sxs-lookup"><span data-stu-id="91d0a-154">You can set the type checking switch to `Off` with either the [Option Strict Statement](../../../language-reference/statements/option-strict-statement.md) or the [-optionstrict](../../../reference/command-line-compiler/optionstrict.md) compiler option.</span></span> <span data-ttu-id="91d0a-155">Dann müssen Sie den Datentyp des Parameters nicht deklarieren.</span><span class="sxs-lookup"><span data-stu-id="91d0a-155">Then you do not have to declare the parameter's data type.</span></span> <span data-ttu-id="91d0a-156">Allerdings hat dieser Ansatz im Vergleich zum Überladen folgende Nachteile:</span><span class="sxs-lookup"><span data-stu-id="91d0a-156">However, this approach has the following disadvantages compared to overloading:</span></span>  
  
- <span data-ttu-id="91d0a-157">Die typlose Programmierung erzeugt weniger effizienten Ausführungs Code.</span><span class="sxs-lookup"><span data-stu-id="91d0a-157">Typeless programming produces less efficient execution code.</span></span>  
  
- <span data-ttu-id="91d0a-158">Die Prozedur muss auf jeden Datentyp testen, der für die Übergabe erwartet wird.</span><span class="sxs-lookup"><span data-stu-id="91d0a-158">The procedure must test for every data type it anticipates being passed.</span></span>  
  
- <span data-ttu-id="91d0a-159">Der Compiler kann keinen Fehler signalisieren, wenn der aufrufende Code einen Datentyp übergibt, den die Prozedur nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="91d0a-159">The compiler cannot signal an error if the calling code passes a data type that the procedure does not support.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91d0a-160">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="91d0a-160">See also</span></span>

- [<span data-ttu-id="91d0a-161">Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="91d0a-161">Procedures</span></span>](./index.md)
- [<span data-ttu-id="91d0a-162">Parameter und Argumente von Prozeduren</span><span class="sxs-lookup"><span data-stu-id="91d0a-162">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="91d0a-163">Problembehandlung bei Prozeduren</span><span class="sxs-lookup"><span data-stu-id="91d0a-163">Troubleshooting Procedures</span></span>](./troubleshooting-procedures.md)
- [<span data-ttu-id="91d0a-164">Vorgehensweise: Definieren mehrerer Versionen einer Prozedur</span><span class="sxs-lookup"><span data-stu-id="91d0a-164">How to: Define Multiple Versions of a Procedure</span></span>](./how-to-define-multiple-versions-of-a-procedure.md)
- [<span data-ttu-id="91d0a-165">Vorgehensweise: Aufrufen einer überladenen Prozedur</span><span class="sxs-lookup"><span data-stu-id="91d0a-165">How to: Call an Overloaded Procedure</span></span>](./how-to-call-an-overloaded-procedure.md)
- [<span data-ttu-id="91d0a-166">Vorgehensweise: Überladen einer Prozedur mit optionalen Parametern</span><span class="sxs-lookup"><span data-stu-id="91d0a-166">How to: Overload a Procedure that Takes Optional Parameters</span></span>](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [<span data-ttu-id="91d0a-167">Vorgehensweise: Überladen einer Prozedur mit einer unbestimmten Anzahl von Parametern</span><span class="sxs-lookup"><span data-stu-id="91d0a-167">How to: Overload a Procedure that Takes an Indefinite Number of Parameters</span></span>](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [<span data-ttu-id="91d0a-168">Überladungs Auflösung</span><span class="sxs-lookup"><span data-stu-id="91d0a-168">Overload Resolution</span></span>](./overload-resolution.md)
- [<span data-ttu-id="91d0a-169">Overloads</span><span class="sxs-lookup"><span data-stu-id="91d0a-169">Overloads</span></span>](../../../language-reference/modifiers/overloads.md)
