---
title: Überlegungen zur Prozedurüberladung (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
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
caps.latest.revision: 26
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ac4bc47f9e781f83c7930efffedd40d9c25c2ec2
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="considerations-in-overloading-procedures-visual-basic"></a><span data-ttu-id="b1c35-102">Überlegungen zur Prozedurüberladung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b1c35-102">Considerations in Overloading Procedures (Visual Basic)</span></span>
<span data-ttu-id="b1c35-103">Wenn Sie eine Prozedur zu überladen, müssen Sie ein anderes verwenden *Signatur* für jede überladene Version.</span><span class="sxs-lookup"><span data-stu-id="b1c35-103">When you overload a procedure, you must use a different *signature* for each overloaded version.</span></span> <span data-ttu-id="b1c35-104">Dies bedeutet normalerweise, dass jede Version eine andere Parameterliste angeben muss.</span><span class="sxs-lookup"><span data-stu-id="b1c35-104">This usually means each version must specify a different parameter list.</span></span> <span data-ttu-id="b1c35-105">Weitere Informationen finden Sie unter "Andere Signatur" in [Prozedurüberladung](./procedure-overloading.md).</span><span class="sxs-lookup"><span data-stu-id="b1c35-105">For more information, see "Different Signature" in [Procedure Overloading](./procedure-overloading.md).</span></span>  
  
 <span data-ttu-id="b1c35-106">Sie können überladen eine `Function` Prozedur mit einer `Sub` Prozedur, und umgekehrt, sofern sie über andere Signaturen verfügen.</span><span class="sxs-lookup"><span data-stu-id="b1c35-106">You can overload a `Function` procedure with a `Sub` procedure, and vice versa, provided they have different signatures.</span></span> <span data-ttu-id="b1c35-107">Zwei Überladungen können nicht unterscheiden sich nur darin, dass eine über einen Rückgabewert verfügt, und die andere nicht aber.</span><span class="sxs-lookup"><span data-stu-id="b1c35-107">Two overloads cannot differ only in that one has a return value and the other does not.</span></span>  
  
 <span data-ttu-id="b1c35-108">Sie können die gleiche Weise, die Sie überladen eine Prozedur, eine Eigenschaft überladen und mit den gleichen Einschränkungen.</span><span class="sxs-lookup"><span data-stu-id="b1c35-108">You can overload a property the same way you overload a procedure, and with the same restrictions.</span></span> <span data-ttu-id="b1c35-109">Sie können keine jedoch Überladen einer Prozedur mit einer Eigenschaft (oder umgekehrt).</span><span class="sxs-lookup"><span data-stu-id="b1c35-109">However, you cannot overload a procedure with a property, or vice versa.</span></span>  
  
## <a name="alternatives-to-overloaded-versions"></a><span data-ttu-id="b1c35-110">Alternativen zu überladenen Versionen</span><span class="sxs-lookup"><span data-stu-id="b1c35-110">Alternatives to Overloaded Versions</span></span>  
 <span data-ttu-id="b1c35-111">Alternativen zu überladenen Versionen haben manchmal insbesondere dann, wenn das Vorhandensein von Argumenten ist eine optionale oder deren Anzahl ist die Variable ein.</span><span class="sxs-lookup"><span data-stu-id="b1c35-111">You sometimes have alternatives to overloaded versions, particularly when the presence of arguments is optional or their number is variable.</span></span>  
  
 <span data-ttu-id="b1c35-112">Bedenken Sie, dass optionale Argumente werden nicht unbedingt von allen Sprachen unterstützt, und Parameterarrays Visual Basic beschränkt sind.</span><span class="sxs-lookup"><span data-stu-id="b1c35-112">Keep in mind that optional arguments are not necessarily supported by all languages, and parameter arrays are limited to Visual Basic.</span></span> <span data-ttu-id="b1c35-113">Wenn Sie eine Prozedur schreiben, die wahrscheinlich in einem der anderen Sprachen geschriebenen Code aufgerufen werden, überladene bieten Versionen die größte Flexibilität.</span><span class="sxs-lookup"><span data-stu-id="b1c35-113">If you are writing a procedure that is likely to be called from code written in any of several different languages, overloaded versions offer the greatest flexibility.</span></span>  
  
### <a name="overloads-and-optional-arguments"></a><span data-ttu-id="b1c35-114">Überladungen und optionale Argumente</span><span class="sxs-lookup"><span data-stu-id="b1c35-114">Overloads and Optional Arguments</span></span>  
 <span data-ttu-id="b1c35-115">Wenn der aufrufende Code kann optional angeben oder ein oder mehrere Argumente auslassen, können Sie mehrere überladene Versionen definieren oder optionale Parameter verwenden.</span><span class="sxs-lookup"><span data-stu-id="b1c35-115">When the calling code can optionally supply or omit one or more arguments, you can define multiple overloaded versions or use optional parameters.</span></span>  
  
#### <a name="when-to-use-overloaded-versions"></a><span data-ttu-id="b1c35-116">Überladene Versionen verwenden</span><span class="sxs-lookup"><span data-stu-id="b1c35-116">When to Use Overloaded Versions</span></span>  
 <span data-ttu-id="b1c35-117">Sie können in Betracht ziehen, definieren eine Reihe von überladenen Versionen in den folgenden Fällen:</span><span class="sxs-lookup"><span data-stu-id="b1c35-117">You can consider defining a series of overloaded versions in the following cases:</span></span>  
  
-   <span data-ttu-id="b1c35-118">Die Logik im Code Prozedur ist erheblich variieren, je nachdem, ob der aufrufende Code ein optionales Argument bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="b1c35-118">The logic in the procedure code is significantly different depending on whether the calling code supplies an optional argument or not.</span></span>  
  
-   <span data-ttu-id="b1c35-119">Der Code die Prozedur kann nicht zuverlässig testen Sie, ob der aufrufende Code ein optionale Argument bereitgestellt hat.</span><span class="sxs-lookup"><span data-stu-id="b1c35-119">The procedure code cannot reliably test whether the calling code has supplied an optional argument.</span></span> <span data-ttu-id="b1c35-120">Dies ist die Groß-/Kleinschreibung, z. B. liegt keine möglichen Kandidaten für einen Standardwert an, die der aufrufende Code konnte nicht zu erwarten.</span><span class="sxs-lookup"><span data-stu-id="b1c35-120">This is the case, for example, if there is no possible candidate for a default value that the calling code could not be expected to supply.</span></span>  
  
#### <a name="when-to-use-optional-parameters"></a><span data-ttu-id="b1c35-121">Optionale Parameter verwenden.</span><span class="sxs-lookup"><span data-stu-id="b1c35-121">When to Use Optional Parameters</span></span>  
 <span data-ttu-id="b1c35-122">Möglicherweise bevorzugen Sie einen oder mehrere optionale Parameter in den folgenden Fällen:</span><span class="sxs-lookup"><span data-stu-id="b1c35-122">You might prefer one or more optional parameters in the following cases:</span></span>  
  
-   <span data-ttu-id="b1c35-123">Die einzige erforderliche Aktion, wenn der aufrufende Code ein optionale Argument nicht angegeben wird ist, der Parameter auf den Standardwert festgelegt.</span><span class="sxs-lookup"><span data-stu-id="b1c35-123">The only required action when the calling code does not supply an optional argument is to set the parameter to a default value.</span></span> <span data-ttu-id="b1c35-124">In diesem Fall der Code kann weniger kompliziert, wenn Sie eine einzelne Version mit einem oder mehreren definieren `Optional` Parameter.</span><span class="sxs-lookup"><span data-stu-id="b1c35-124">In such a case, the procedure code can be less complicated if you define a single version with one or more `Optional` parameters.</span></span>  
  
 <span data-ttu-id="b1c35-125">Weitere Informationen finden Sie unter [optionale Parameter](./optional-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="b1c35-125">For more information, see [Optional Parameters](./optional-parameters.md).</span></span>  
  
### <a name="overloads-and-paramarrays"></a><span data-ttu-id="b1c35-126">Überladungen und ParamArrays</span><span class="sxs-lookup"><span data-stu-id="b1c35-126">Overloads and ParamArrays</span></span>  
 <span data-ttu-id="b1c35-127">Wenn der aufrufende Code eine Variable Anzahl von Argumenten übergeben kann, können Sie mehrere überladene Versionen definieren oder ein Parameterarray verwenden.</span><span class="sxs-lookup"><span data-stu-id="b1c35-127">When the calling code can pass a variable number of arguments, you can define multiple overloaded versions or use a parameter array.</span></span>  
  
#### <a name="when-to-use-overloaded-versions"></a><span data-ttu-id="b1c35-128">Überladene Versionen verwenden</span><span class="sxs-lookup"><span data-stu-id="b1c35-128">When to Use Overloaded Versions</span></span>  
 <span data-ttu-id="b1c35-129">Sie können in Betracht ziehen, definieren eine Reihe von überladenen Versionen in den folgenden Fällen:</span><span class="sxs-lookup"><span data-stu-id="b1c35-129">You can consider defining a series of overloaded versions in the following cases:</span></span>  
  
-   <span data-ttu-id="b1c35-130">Sie wissen, dass der aufrufende Code nie mehr als eine geringe Anzahl von an das Parameterarray übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="b1c35-130">You know that the calling code never passes more than a small number of values to the parameter array.</span></span>  
  
-   <span data-ttu-id="b1c35-131">Die Logik im Code Prozedur ist erheblich variieren, je nachdem wie viele Werte, die der aufrufende Code übergibt.</span><span class="sxs-lookup"><span data-stu-id="b1c35-131">The logic in the procedure code is significantly different depending on how many values the calling code passes.</span></span>  
  
-   <span data-ttu-id="b1c35-132">Der aufrufende Code kann Werte mit unterschiedlichen Datentypen übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="b1c35-132">The calling code can pass values of different data types.</span></span>  
  
#### <a name="when-to-use-a-parameter-array"></a><span data-ttu-id="b1c35-133">Ein Parameterarray verwenden.</span><span class="sxs-lookup"><span data-stu-id="b1c35-133">When to Use a Parameter Array</span></span>  
 <span data-ttu-id="b1c35-134">Sie werden von besser bedient ein `ParamArray` Parameter in den folgenden Fällen:</span><span class="sxs-lookup"><span data-stu-id="b1c35-134">You are better served by a `ParamArray` parameter in the following cases:</span></span>  
  
-   <span data-ttu-id="b1c35-135">Sie sind nicht wie viele Werte prognostizieren der aufrufende Code an das Parameterarray übergeben kann, und es ist möglicherweise eine große Anzahl.</span><span class="sxs-lookup"><span data-stu-id="b1c35-135">You are not able to predict how many values the calling code can pass to the parameter array, and it could be a large number.</span></span>  
  
-   <span data-ttu-id="b1c35-136">Logik der Prozedur eignet sich für alle Werte, die der aufrufende Code übergibt die im Wesentlichen die gleichen Vorgänge für jeden Wert durchführen, durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="b1c35-136">The procedure logic lends itself to iterating through all the values the calling code passes, performing essentially the same operations on every value.</span></span>  
  
 <span data-ttu-id="b1c35-137">Weitere Informationen finden Sie unter [Parameterarrays](./parameter-arrays.md).</span><span class="sxs-lookup"><span data-stu-id="b1c35-137">For more information, see [Parameter Arrays](./parameter-arrays.md).</span></span>  
  
## <a name="implicit-overloads-for-optional-parameters"></a><span data-ttu-id="b1c35-138">Implizite Überladungen für optionale Parameter</span><span class="sxs-lookup"><span data-stu-id="b1c35-138">Implicit Overloads for Optional Parameters</span></span>  
 <span data-ttu-id="b1c35-139">Eine Prozedur mit einem [Optional](../../../../visual-basic/language-reference/modifiers/optional.md) entspricht zwei überladenen Prozeduren, mit dem optionalen Parameter und eine ohne Parameter.</span><span class="sxs-lookup"><span data-stu-id="b1c35-139">A procedure with an [Optional](../../../../visual-basic/language-reference/modifiers/optional.md) parameter is equivalent to two overloaded procedures, one with the optional parameter and one without it.</span></span> <span data-ttu-id="b1c35-140">Eine solche Prozedur kann nicht mit einer Parameterliste, die einer der folgenden entspricht überladen werden.</span><span class="sxs-lookup"><span data-stu-id="b1c35-140">You cannot overload such a procedure with a parameter list corresponding to either of these.</span></span> <span data-ttu-id="b1c35-141">Die folgenden Deklarationen veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="b1c35-141">The following declarations illustrate this.</span></span>  
  
 [!code-vb[VbVbcnProcedures#58](./codesnippet/VisualBasic/considerations-in-overloading-procedures_1.vb)]  
  
 [!code-vb[VbVbcnProcedures#60](./codesnippet/VisualBasic/considerations-in-overloading-procedures_2.vb)]  
  
 [!code-vb[VbVbcnProcedures#61](./codesnippet/VisualBasic/considerations-in-overloading-procedures_3.vb)]  
  
 <span data-ttu-id="b1c35-142">Für eine Prozedur mit mehr als ein optionaler Parameter ist es eine Reihe von implizite Überladungen, eingetroffen von Logik, die im vorherigen Beispiel ähnelt.</span><span class="sxs-lookup"><span data-stu-id="b1c35-142">For a procedure with more than one optional parameter, there is a set of implicit overloads, arrived at by logic similar to that in the preceding example.</span></span>  
  
## <a name="implicit-overloads-for-a-paramarray-parameter"></a><span data-ttu-id="b1c35-143">Implizite Überladungen für ParamArray-Parameter</span><span class="sxs-lookup"><span data-stu-id="b1c35-143">Implicit Overloads for a ParamArray Parameter</span></span>  
 <span data-ttu-id="b1c35-144">Der Compiler betrachtet eine Prozedur mit einem [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) Parameter haben eine unendliche Anzahl von Überladungen, die in der aufrufende Code wie folgt an das Parameterarray übergibt sich dadurch voneinander unterscheiden:</span><span class="sxs-lookup"><span data-stu-id="b1c35-144">The compiler considers a procedure with a [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) parameter to have an infinite number of overloads, differing from each other in what the calling code passes to the parameter array, as follows:</span></span>  
  
-   <span data-ttu-id="b1c35-145">Eine Überladung für, wenn der aufrufende Code nicht Argument bereitgestellt der `ParamArray`</span><span class="sxs-lookup"><span data-stu-id="b1c35-145">One overload for when the calling code does not supply an argument to the `ParamArray`</span></span>  
  
-   <span data-ttu-id="b1c35-146">Eine Überladung für, wenn der aufrufende Code ein eindimensionales Array vom liefert die `ParamArray` Elementtyp.</span><span class="sxs-lookup"><span data-stu-id="b1c35-146">One overload for when the calling code supplies a one-dimensional array of the `ParamArray` element type</span></span>  
  
-   <span data-ttu-id="b1c35-147">Für jede positive ganze Zahl, eine Überladung für, wenn der aufrufende Code die Anzahl der Argumente, aller liefert die `ParamArray` Elementtyp.</span><span class="sxs-lookup"><span data-stu-id="b1c35-147">For every positive integer, one overload for when the calling code supplies that number of arguments, each of the `ParamArray` element type</span></span>  
  
 <span data-ttu-id="b1c35-148">Die folgenden Deklarationen veranschaulichen diese implizite Überladungen.</span><span class="sxs-lookup"><span data-stu-id="b1c35-148">The following declarations illustrate these implicit overloads.</span></span>  
  
 [!code-vb[VbVbcnProcedures#68](./codesnippet/VisualBasic/considerations-in-overloading-procedures_4.vb)]  
  
 [!code-vb[VbVbcnProcedures#70](./codesnippet/VisualBasic/considerations-in-overloading-procedures_5.vb)]  
  
 <span data-ttu-id="b1c35-149">Sie können sich nicht auf eine solche Prozedur mit einer Parameterliste überladen, die ein eindimensionales Array für das Parameterarray akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="b1c35-149">You cannot overload such a procedure with a parameter list that takes a one-dimensional array for the parameter array.</span></span> <span data-ttu-id="b1c35-150">Allerdings können Sie die Signaturen der implizite Überladungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="b1c35-150">However, you can use the signatures of the other implicit overloads.</span></span> <span data-ttu-id="b1c35-151">Die folgenden Deklarationen veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="b1c35-151">The following declarations illustrate this.</span></span>  
  
 [!code-vb[VbVbcnProcedures#71](./codesnippet/VisualBasic/considerations-in-overloading-procedures_6.vb)]  
  
## <a name="typeless-programming-as-an-alternative-to-overloading"></a><span data-ttu-id="b1c35-152">Programmierung ohne Datentypen als Alternative zum Überladen</span><span class="sxs-lookup"><span data-stu-id="b1c35-152">Typeless Programming as an Alternative to Overloading</span></span>  
 <span data-ttu-id="b1c35-153">Wenn den aufrufenden Code auf einen Parameter unterschiedliche Datentypen übergeben werden sollen, ist ein alternativer Ansatz Programmierung ohne Datentypen.</span><span class="sxs-lookup"><span data-stu-id="b1c35-153">If you want to allow the calling code to pass different data types to a parameter, an alternative approach is typeless programming.</span></span> <span data-ttu-id="b1c35-154">Sie können festlegen, dass der Switch die typüberprüfung `Off` entweder mit der [Option Strict-Anweisung](../../../../visual-basic/language-reference/statements/option-strict-statement.md) oder [/optionstrict](../../../../visual-basic/reference/command-line-compiler/optionstrict.md) -Compileroption.</span><span class="sxs-lookup"><span data-stu-id="b1c35-154">You can set the type checking switch to `Off` with either the [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md) or the [/optionstrict](../../../../visual-basic/reference/command-line-compiler/optionstrict.md) compiler option.</span></span> <span data-ttu-id="b1c35-155">Dann müssen Sie keinen Datentyp für den Parameter zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="b1c35-155">Then you do not have to declare the parameter's data type.</span></span> <span data-ttu-id="b1c35-156">Dieser Ansatz hat jedoch die folgenden Nachteile im Vergleich zum Überladen:</span><span class="sxs-lookup"><span data-stu-id="b1c35-156">However, this approach has the following disadvantages compared to overloading:</span></span>  
  
-   <span data-ttu-id="b1c35-157">Programmierung ohne Datentypen erzeugt der Ausführungscode für weniger effizient.</span><span class="sxs-lookup"><span data-stu-id="b1c35-157">Typeless programming produces less efficient execution code.</span></span>  
  
-   <span data-ttu-id="b1c35-158">Die Prozedur muss für jeden Datentyp testen, dessen Übergabe.</span><span class="sxs-lookup"><span data-stu-id="b1c35-158">The procedure must test for every data type it anticipates being passed.</span></span>  
  
-   <span data-ttu-id="b1c35-159">Der Compiler kann nicht auf einen Fehler signalisieren, wenn der aufrufende Code einen Datentyp übergibt, den die Prozedur nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="b1c35-159">The compiler cannot signal an error if the calling code passes a data type that the procedure does not support.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1c35-160">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b1c35-160">See Also</span></span>  
 [<span data-ttu-id="b1c35-161">Verfahren</span><span class="sxs-lookup"><span data-stu-id="b1c35-161">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="b1c35-162">Parameter und Argumente von Prozeduren</span><span class="sxs-lookup"><span data-stu-id="b1c35-162">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="b1c35-163">Problembehandlung bei Prozeduren</span><span class="sxs-lookup"><span data-stu-id="b1c35-163">Troubleshooting Procedures</span></span>](./troubleshooting-procedures.md)  
 [<span data-ttu-id="b1c35-164">Gewusst wie: Definieren mehrerer Versionen einer Prozedur</span><span class="sxs-lookup"><span data-stu-id="b1c35-164">How to: Define Multiple Versions of a Procedure</span></span>](./how-to-define-multiple-versions-of-a-procedure.md)  
 [<span data-ttu-id="b1c35-165">Gewusst wie: Aufrufen einer überladenen Prozedur</span><span class="sxs-lookup"><span data-stu-id="b1c35-165">How to: Call an Overloaded Procedure</span></span>](./how-to-call-an-overloaded-procedure.md)  
 [<span data-ttu-id="b1c35-166">Gewusst wie: Überladen einer Prozedur mit optionalen Parametern</span><span class="sxs-lookup"><span data-stu-id="b1c35-166">How to: Overload a Procedure that Takes Optional Parameters</span></span>](./how-to-overload-a-procedure-that-takes-optional-parameters.md)  
 [<span data-ttu-id="b1c35-167">Gewusst wie: Überladen einer Prozedur mit einer unbestimmten Anzahl von Parametern</span><span class="sxs-lookup"><span data-stu-id="b1c35-167">How to: Overload a Procedure that Takes an Indefinite Number of Parameters</span></span>](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)  
 [<span data-ttu-id="b1c35-168">Überladungsauflösung</span><span class="sxs-lookup"><span data-stu-id="b1c35-168">Overload Resolution</span></span>](./overload-resolution.md)  
 [<span data-ttu-id="b1c35-169">Overloads</span><span class="sxs-lookup"><span data-stu-id="b1c35-169">Overloads</span></span>](../../../../visual-basic/language-reference/modifiers/overloads.md)
