---
title: Überlegungen zur Prozedurüberladung (Visual Basic)
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
ms.openlocfilehash: f14cc28960af28530bda9a78c1309dea10c18b8f
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58815595"
---
# <a name="considerations-in-overloading-procedures-visual-basic"></a><span data-ttu-id="b447d-102">Überlegungen zur Prozedurüberladung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b447d-102">Considerations in Overloading Procedures (Visual Basic)</span></span>
<span data-ttu-id="b447d-103">Wenn Sie eine Prozedur zu überladen, müssen Sie einen anderen verwenden *Signatur* für jede überladene Version.</span><span class="sxs-lookup"><span data-stu-id="b447d-103">When you overload a procedure, you must use a different *signature* for each overloaded version.</span></span> <span data-ttu-id="b447d-104">Dies bedeutet normalerweise, dass jede Version eine anderen Parameterliste angeben muss.</span><span class="sxs-lookup"><span data-stu-id="b447d-104">This usually means each version must specify a different parameter list.</span></span> <span data-ttu-id="b447d-105">Weitere Informationen finden Sie unter "Andere Signatur" in [Prozedurüberladung](./procedure-overloading.md).</span><span class="sxs-lookup"><span data-stu-id="b447d-105">For more information, see "Different Signature" in [Procedure Overloading](./procedure-overloading.md).</span></span>  
  
 <span data-ttu-id="b447d-106">Überladen Sie eine `Function` Prozedur mit einer `Sub` Verfahren und umgekehrt, sofern sie verschiedene Signaturen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="b447d-106">You can overload a `Function` procedure with a `Sub` procedure, and vice versa, provided they have different signatures.</span></span> <span data-ttu-id="b447d-107">Zwei Überladungen dürfen sich nicht nur darin, dass eine einen Rückgabewert hat und die andere nicht aber unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="b447d-107">Two overloads cannot differ only in that one has a return value and the other does not.</span></span>  
  
 <span data-ttu-id="b447d-108">Sie können die gleiche Weise, die Sie überladen eine Prozedur, eine Eigenschaft überladen und mit denselben Einschränkungen.</span><span class="sxs-lookup"><span data-stu-id="b447d-108">You can overload a property the same way you overload a procedure, and with the same restrictions.</span></span> <span data-ttu-id="b447d-109">Aber Sie können nicht überladen einer Prozedur mit einer Eigenschaft (oder umgekehrt).</span><span class="sxs-lookup"><span data-stu-id="b447d-109">However, you cannot overload a procedure with a property, or vice versa.</span></span>  
  
## <a name="alternatives-to-overloaded-versions"></a><span data-ttu-id="b447d-110">Alternativen zu überladenen Versionen</span><span class="sxs-lookup"><span data-stu-id="b447d-110">Alternatives to Overloaded Versions</span></span>  
 <span data-ttu-id="b447d-111">Sie müssen manchmal Alternativen für die überladene Versionen, insbesondere dann, wenn das Vorhandensein von Argumenten optional ist, oder deren Anzahl ist die Variable.</span><span class="sxs-lookup"><span data-stu-id="b447d-111">You sometimes have alternatives to overloaded versions, particularly when the presence of arguments is optional or their number is variable.</span></span>  
  
 <span data-ttu-id="b447d-112">Bedenken Sie, dass optionale Argumente werden nicht unbedingt von allen Sprachen unterstützt, und Parameterarrays in Visual Basic beschränkt sind.</span><span class="sxs-lookup"><span data-stu-id="b447d-112">Keep in mind that optional arguments are not necessarily supported by all languages, and parameter arrays are limited to Visual Basic.</span></span> <span data-ttu-id="b447d-113">Wenn Sie eine Prozedur, die wahrscheinlich Schreiben für den Aufruf aus Code in einer von mehreren verschiedenen Sprachen geschrieben wurden, überladene bieten Versionen die größte Flexibilität.</span><span class="sxs-lookup"><span data-stu-id="b447d-113">If you are writing a procedure that is likely to be called from code written in any of several different languages, overloaded versions offer the greatest flexibility.</span></span>  
  
### <a name="overloads-and-optional-arguments"></a><span data-ttu-id="b447d-114">Überladungen und optionale Argumente</span><span class="sxs-lookup"><span data-stu-id="b447d-114">Overloads and Optional Arguments</span></span>  
 <span data-ttu-id="b447d-115">Wenn der aufrufende Code kann optional angeben oder ein oder mehrere Argumente auslassen, können Sie mehrere überladene Versionen definieren oder optionale Parameter verwenden.</span><span class="sxs-lookup"><span data-stu-id="b447d-115">When the calling code can optionally supply or omit one or more arguments, you can define multiple overloaded versions or use optional parameters.</span></span>  
  
#### <a name="when-to-use-overloaded-versions"></a><span data-ttu-id="b447d-116">Überladene Versionen verwenden.</span><span class="sxs-lookup"><span data-stu-id="b447d-116">When to Use Overloaded Versions</span></span>  
 <span data-ttu-id="b447d-117">Sie können in Betracht ziehen, eine Reihe von überladenen Versionen definiert, in den folgenden Fällen:</span><span class="sxs-lookup"><span data-stu-id="b447d-117">You can consider defining a series of overloaded versions in the following cases:</span></span>  
  
-   <span data-ttu-id="b447d-118">Die Logik im Code Prozedur unterscheidet sich erheblich abhängig davon, ob der aufrufende Code ein optionales Argument bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="b447d-118">The logic in the procedure code is significantly different depending on whether the calling code supplies an optional argument or not.</span></span>  
  
-   <span data-ttu-id="b447d-119">Code der Prozedur kann nicht zuverlässig zu testen, ob der aufrufende Code ein optionales Argument angegeben hat.</span><span class="sxs-lookup"><span data-stu-id="b447d-119">The procedure code cannot reliably test whether the calling code has supplied an optional argument.</span></span> <span data-ttu-id="b447d-120">Dies ist der Fall, z. B. liegt keine möglichen Kandidaten für einen Standardwert an, die der aufrufende Code konnte nicht zu erwarten.</span><span class="sxs-lookup"><span data-stu-id="b447d-120">This is the case, for example, if there is no possible candidate for a default value that the calling code could not be expected to supply.</span></span>  
  
#### <a name="when-to-use-optional-parameters"></a><span data-ttu-id="b447d-121">Optionale Parameter verwenden.</span><span class="sxs-lookup"><span data-stu-id="b447d-121">When to Use Optional Parameters</span></span>  
 <span data-ttu-id="b447d-122">Möglicherweise bevorzugen Sie einen oder mehrere optionale Parameter in den folgenden Fällen:</span><span class="sxs-lookup"><span data-stu-id="b447d-122">You might prefer one or more optional parameters in the following cases:</span></span>  
  
-   <span data-ttu-id="b447d-123">Die einzige erforderliche Aktion, wenn der aufrufende Code ein optionale Argument nicht angegeben wird, ist den Parameter auf einen Standardwert festlegen.</span><span class="sxs-lookup"><span data-stu-id="b447d-123">The only required action when the calling code does not supply an optional argument is to set the parameter to a default value.</span></span> <span data-ttu-id="b447d-124">In diesem Fall der Code der Prozedur kann weniger kompliziert sein, wenn Sie eine einzelne Version mit einem oder mehreren definieren `Optional` Parameter.</span><span class="sxs-lookup"><span data-stu-id="b447d-124">In such a case, the procedure code can be less complicated if you define a single version with one or more `Optional` parameters.</span></span>  
  
 <span data-ttu-id="b447d-125">Weitere Informationen finden Sie unter [optionale Parameter](./optional-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="b447d-125">For more information, see [Optional Parameters](./optional-parameters.md).</span></span>  
  
### <a name="overloads-and-paramarrays"></a><span data-ttu-id="b447d-126">Überladungen und ParamArrays</span><span class="sxs-lookup"><span data-stu-id="b447d-126">Overloads and ParamArrays</span></span>  
 <span data-ttu-id="b447d-127">Wenn der aufrufende Code eine Variable Anzahl von Argumenten übergeben kann, können Sie mehrere überladene Versionen definieren oder ein Parameterarray verwenden.</span><span class="sxs-lookup"><span data-stu-id="b447d-127">When the calling code can pass a variable number of arguments, you can define multiple overloaded versions or use a parameter array.</span></span>  
  
#### <a name="when-to-use-overloaded-versions"></a><span data-ttu-id="b447d-128">Überladene Versionen verwenden.</span><span class="sxs-lookup"><span data-stu-id="b447d-128">When to Use Overloaded Versions</span></span>  
 <span data-ttu-id="b447d-129">Sie können in Betracht ziehen, eine Reihe von überladenen Versionen definiert, in den folgenden Fällen:</span><span class="sxs-lookup"><span data-stu-id="b447d-129">You can consider defining a series of overloaded versions in the following cases:</span></span>  
  
-   <span data-ttu-id="b447d-130">Sie wissen, dass der aufrufende Code nie mehr als eine kleine Anzahl von Werten für das Parameterarray erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="b447d-130">You know that the calling code never passes more than a small number of values to the parameter array.</span></span>  
  
-   <span data-ttu-id="b447d-131">Die Logik im Code Prozedur ist erheblich variieren, je nachdem wie viele Werte, die der aufrufende Code übergeben.</span><span class="sxs-lookup"><span data-stu-id="b447d-131">The logic in the procedure code is significantly different depending on how many values the calling code passes.</span></span>  
  
-   <span data-ttu-id="b447d-132">Der aufrufende Code kann es sich um die Werte mit unterschiedlichen Datentypen übergeben.</span><span class="sxs-lookup"><span data-stu-id="b447d-132">The calling code can pass values of different data types.</span></span>  
  
#### <a name="when-to-use-a-parameter-array"></a><span data-ttu-id="b447d-133">Ein Parameterarray verwenden.</span><span class="sxs-lookup"><span data-stu-id="b447d-133">When to Use a Parameter Array</span></span>  
 <span data-ttu-id="b447d-134">Sie sind besser geeignet, indem eine `ParamArray` Parameter in den folgenden Fällen:</span><span class="sxs-lookup"><span data-stu-id="b447d-134">You are better served by a `ParamArray` parameter in the following cases:</span></span>  
  
-   <span data-ttu-id="b447d-135">Sie können nicht vorhersagen, wie viele Werte der aufrufende Code für das Parameterarray übergeben kann, und möglicherweise eine große Anzahl.</span><span class="sxs-lookup"><span data-stu-id="b447d-135">You are not able to predict how many values the calling code can pass to the parameter array, and it could be a large number.</span></span>  
  
-   <span data-ttu-id="b447d-136">Logik der Prozedur eignet sich für alle Werte, die der aufrufende Code im Wesentlichen die gleichen Vorgänge für jeden Wert ausführen besteht, durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="b447d-136">The procedure logic lends itself to iterating through all the values the calling code passes, performing essentially the same operations on every value.</span></span>  
  
 <span data-ttu-id="b447d-137">Weitere Informationen finden Sie unter [Parameterarrays](./parameter-arrays.md).</span><span class="sxs-lookup"><span data-stu-id="b447d-137">For more information, see [Parameter Arrays](./parameter-arrays.md).</span></span>  
  
## <a name="implicit-overloads-for-optional-parameters"></a><span data-ttu-id="b447d-138">Implizite Überladungen für optionale Parameter</span><span class="sxs-lookup"><span data-stu-id="b447d-138">Implicit Overloads for Optional Parameters</span></span>  
 <span data-ttu-id="b447d-139">Eine Prozedur mit einem [Optional](../../../../visual-basic/language-reference/modifiers/optional.md) entspricht zwei überladenen Prozeduren, mit dem optionalen Parameter und eine ohne Parameter.</span><span class="sxs-lookup"><span data-stu-id="b447d-139">A procedure with an [Optional](../../../../visual-basic/language-reference/modifiers/optional.md) parameter is equivalent to two overloaded procedures, one with the optional parameter and one without it.</span></span> <span data-ttu-id="b447d-140">Sie können keine solche Prozedur mit einer Parameterliste entspricht, die an einen der beiden überladen.</span><span class="sxs-lookup"><span data-stu-id="b447d-140">You cannot overload such a procedure with a parameter list corresponding to either of these.</span></span> <span data-ttu-id="b447d-141">Die folgenden Deklarationen veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="b447d-141">The following declarations illustrate this.</span></span>  
  
 [!code-vb[VbVbcnProcedures#58](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#58)]  
  
 [!code-vb[VbVbcnProcedures#60](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#60)]  
  
 [!code-vb[VbVbcnProcedures#61](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#61)]  
  
 <span data-ttu-id="b447d-142">Für eine Prozedur mit mehr als einen optionalen Parameter ist es ein Satz von implizite Überladungen, jeweils aussagekräftige Testabfragen Durchführen von Logik, die im vorherigen Beispiel ähnelt.</span><span class="sxs-lookup"><span data-stu-id="b447d-142">For a procedure with more than one optional parameter, there is a set of implicit overloads, arrived at by logic similar to that in the preceding example.</span></span>  
  
## <a name="implicit-overloads-for-a-paramarray-parameter"></a><span data-ttu-id="b447d-143">Implizite Überladungen für ParamArray-Parameter</span><span class="sxs-lookup"><span data-stu-id="b447d-143">Implicit Overloads for a ParamArray Parameter</span></span>  
 <span data-ttu-id="b447d-144">Der Compiler betrachtet eine Prozedur mit einem [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) Parameter, um eine unbegrenzte Anzahl von Überladungen, die in der aufrufende Code wie folgt auf das Parameterarray übergibt sich dadurch voneinander unterscheiden zu erhalten:</span><span class="sxs-lookup"><span data-stu-id="b447d-144">The compiler considers a procedure with a [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) parameter to have an infinite number of overloads, differing from each other in what the calling code passes to the parameter array, as follows:</span></span>  
  
-   <span data-ttu-id="b447d-145">Eine Überladung für Wenn der aufrufende Code kein Argument übergibt die `ParamArray`</span><span class="sxs-lookup"><span data-stu-id="b447d-145">One overload for when the calling code does not supply an argument to the `ParamArray`</span></span>  
  
-   <span data-ttu-id="b447d-146">Eine Überladung für, wenn der aufrufende Code ein eindimensionales Array stellt die `ParamArray` Elementtyp</span><span class="sxs-lookup"><span data-stu-id="b447d-146">One overload for when the calling code supplies a one-dimensional array of the `ParamArray` element type</span></span>  
  
-   <span data-ttu-id="b447d-147">Für jede positive ganze Zahl, eine Überladung für, wenn der aufrufende Code diese Anzahl von Argumenten, die jeweils der stellt der `ParamArray` Elementtyp</span><span class="sxs-lookup"><span data-stu-id="b447d-147">For every positive integer, one overload for when the calling code supplies that number of arguments, each of the `ParamArray` element type</span></span>  
  
 <span data-ttu-id="b447d-148">Die folgenden Deklarationen veranschaulichen diese implizite Überladungen.</span><span class="sxs-lookup"><span data-stu-id="b447d-148">The following declarations illustrate these implicit overloads.</span></span>  
  
 [!code-vb[VbVbcnProcedures#68](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#68)]  
  
 [!code-vb[VbVbcnProcedures#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#70)]  
  
 <span data-ttu-id="b447d-149">Sie können sich nicht auf eine solche Prozedur mit einer Parameterliste überladen, die ein eindimensionales Array für das Parameterarray akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="b447d-149">You cannot overload such a procedure with a parameter list that takes a one-dimensional array for the parameter array.</span></span> <span data-ttu-id="b447d-150">Allerdings können Sie die Signaturen der anderen implizite Überladungen.</span><span class="sxs-lookup"><span data-stu-id="b447d-150">However, you can use the signatures of the other implicit overloads.</span></span> <span data-ttu-id="b447d-151">Die folgenden Deklarationen veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="b447d-151">The following declarations illustrate this.</span></span>  
  
 [!code-vb[VbVbcnProcedures#71](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#71)]  
  
## <a name="typeless-programming-as-an-alternative-to-overloading"></a><span data-ttu-id="b447d-152">Programmierung ohne Datentypen als Alternative zum Überladen</span><span class="sxs-lookup"><span data-stu-id="b447d-152">Typeless Programming as an Alternative to Overloading</span></span>  
 <span data-ttu-id="b447d-153">Wenn den aufrufenden Code unterschiedliche Datentypen auf einen Parameter übergeben werden sollen, ist ein alternativer Ansatz Programmierung ohne Datentypen.</span><span class="sxs-lookup"><span data-stu-id="b447d-153">If you want to allow the calling code to pass different data types to a parameter, an alternative approach is typeless programming.</span></span> <span data-ttu-id="b447d-154">Sie können festlegen, der Switch die typüberprüfung `Off` entweder mit der [Option Strict-Anweisung](../../../../visual-basic/language-reference/statements/option-strict-statement.md) oder [/optionstrict](../../../../visual-basic/reference/command-line-compiler/optionstrict.md) -Compileroption.</span><span class="sxs-lookup"><span data-stu-id="b447d-154">You can set the type checking switch to `Off` with either the [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md) or the [/optionstrict](../../../../visual-basic/reference/command-line-compiler/optionstrict.md) compiler option.</span></span> <span data-ttu-id="b447d-155">Dann müssen Sie keinen Datentyp des Parameters zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="b447d-155">Then you do not have to declare the parameter's data type.</span></span> <span data-ttu-id="b447d-156">Dieser Ansatz weist jedoch die folgenden Nachteile im Vergleich zum Überladen:</span><span class="sxs-lookup"><span data-stu-id="b447d-156">However, this approach has the following disadvantages compared to overloading:</span></span>  
  
-   <span data-ttu-id="b447d-157">Programmierung ohne Datentypen erzeugt Ausführungscode weniger effizient.</span><span class="sxs-lookup"><span data-stu-id="b447d-157">Typeless programming produces less efficient execution code.</span></span>  
  
-   <span data-ttu-id="b447d-158">Die Prozedur muss für jeden Datentyp testen dessen Übergabe.</span><span class="sxs-lookup"><span data-stu-id="b447d-158">The procedure must test for every data type it anticipates being passed.</span></span>  
  
-   <span data-ttu-id="b447d-159">Der Compiler kann nicht auf einen Fehler signalisieren, wenn der aufrufende Code einen Datentyp übergibt, den die Prozedur nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="b447d-159">The compiler cannot signal an error if the calling code passes a data type that the procedure does not support.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b447d-160">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b447d-160">See also</span></span>

- [<span data-ttu-id="b447d-161">Verfahren</span><span class="sxs-lookup"><span data-stu-id="b447d-161">Procedures</span></span>](./index.md)
- [<span data-ttu-id="b447d-162">Parameter und Argumente von Prozeduren</span><span class="sxs-lookup"><span data-stu-id="b447d-162">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="b447d-163">Problembehandlung bei Prozeduren</span><span class="sxs-lookup"><span data-stu-id="b447d-163">Troubleshooting Procedures</span></span>](./troubleshooting-procedures.md)
- [<span data-ttu-id="b447d-164">Vorgehensweise: Definieren Sie mehrerer Versionen einer Prozedur</span><span class="sxs-lookup"><span data-stu-id="b447d-164">How to: Define Multiple Versions of a Procedure</span></span>](./how-to-define-multiple-versions-of-a-procedure.md)
- [<span data-ttu-id="b447d-165">Vorgehensweise: Aufrufen einer überladenen Prozedur</span><span class="sxs-lookup"><span data-stu-id="b447d-165">How to: Call an Overloaded Procedure</span></span>](./how-to-call-an-overloaded-procedure.md)
- [<span data-ttu-id="b447d-166">Vorgehensweise: Überladen einer Prozedur mit optionalen Parametern</span><span class="sxs-lookup"><span data-stu-id="b447d-166">How to: Overload a Procedure that Takes Optional Parameters</span></span>](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [<span data-ttu-id="b447d-167">Vorgehensweise: Überladen einer Prozedur mit einer unbestimmten Anzahl von Parametern</span><span class="sxs-lookup"><span data-stu-id="b447d-167">How to: Overload a Procedure that Takes an Indefinite Number of Parameters</span></span>](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [<span data-ttu-id="b447d-168">Überladungsauflösung</span><span class="sxs-lookup"><span data-stu-id="b447d-168">Overload Resolution</span></span>](./overload-resolution.md)
- [<span data-ttu-id="b447d-169">Overloads</span><span class="sxs-lookup"><span data-stu-id="b447d-169">Overloads</span></span>](../../../../visual-basic/language-reference/modifiers/overloads.md)
