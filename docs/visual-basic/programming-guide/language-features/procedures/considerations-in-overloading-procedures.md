---
title: "Überlegungen zur prozedurüberladung (Visual Basic) | Microsoft-Dokumentation"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- signatures, ParamArray arguments
- ParamArray keyword, parameter arrays
- ParamArray keyword, arguments and signatures
- function overloading, implicit overloads for ParamArray
- ParamArray keyword, signatures
- Visual Basic code, procedures
- arguments [Visual Basic], parameter arrays
- procedures, overloading
- parameters, lists
- function overloading, typeless programming
- typeless programming
- function overloading, restrictions
- arguments [Visual Basic], optional
- optional arguments, overloading
- signatures, procedure
- parameter lists
- parameter arrays, overloading arguments
- Visual Basic code, parameter lists
- procedure overloading, considerations
- Option Explicit statement
- restrictions, overloading procedures
- procedures, parameter lists
ms.assetid: a2001248-10d0-42c5-b0ce-eeedc987319f
caps.latest.revision: 26
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 486e6c08fe6284cc9b5856fb848f7307a5651120
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="considerations-in-overloading-procedures-visual-basic"></a><span data-ttu-id="c1ae0-102">Überlegungen zur Prozedurüberladung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c1ae0-102">Considerations in Overloading Procedures (Visual Basic)</span></span>
<span data-ttu-id="c1ae0-103">Wenn Sie eine Prozedur überladen, müssen Sie ein anderes verwenden *Signatur* für jede überladene Version.</span><span class="sxs-lookup"><span data-stu-id="c1ae0-103">When you overload a procedure, you must use a different *signature* for each overloaded version.</span></span> <span data-ttu-id="c1ae0-104">Dies bedeutet normalerweise, dass jede Version eine andere Parameterliste angeben muss.</span><span class="sxs-lookup"><span data-stu-id="c1ae0-104">This usually means each version must specify a different parameter list.</span></span> <span data-ttu-id="c1ae0-105">Weitere Informationen finden Sie unter "Andere Signatur" in [Prozedurüberladung](./procedure-overloading.md).</span><span class="sxs-lookup"><span data-stu-id="c1ae0-105">For more information, see "Different Signature" in [Procedure Overloading](./procedure-overloading.md).</span></span>  
  
 <span data-ttu-id="c1ae0-106">Sie können überladen eine `Function` Prozedur mit einem `Sub` Verfahren und umgekehrt, sofern sie unterschiedliche Signaturen besitzen.</span><span class="sxs-lookup"><span data-stu-id="c1ae0-106">You can overload a `Function` procedure with a `Sub` procedure, and vice versa, provided they have different signatures.</span></span> <span data-ttu-id="c1ae0-107">Zwei Überladungen können nicht unterscheiden sich nur darin, dass eine verfügt über einen Rückgabewert und die andere nicht.</span><span class="sxs-lookup"><span data-stu-id="c1ae0-107">Two overloads cannot differ only in that one has a return value and the other does not.</span></span>  
  
 <span data-ttu-id="c1ae0-108">Sie können die gleiche Weise, die Sie überladen eine Prozedur, eine Eigenschaft überladen und mit den gleichen Einschränkungen.</span><span class="sxs-lookup"><span data-stu-id="c1ae0-108">You can overload a property the same way you overload a procedure, and with the same restrictions.</span></span> <span data-ttu-id="c1ae0-109">Aber Sie können nicht überladen einer Prozedur mit einer Eigenschaft (oder umgekehrt).</span><span class="sxs-lookup"><span data-stu-id="c1ae0-109">However, you cannot overload a procedure with a property, or vice versa.</span></span>  
  
## <a name="alternatives-to-overloaded-versions"></a><span data-ttu-id="c1ae0-110">Alternativen zu überladenen Versionen</span><span class="sxs-lookup"><span data-stu-id="c1ae0-110">Alternatives to Overloaded Versions</span></span>  
 <span data-ttu-id="c1ae0-111">Sie müssen manchmal Alternativen zu überladenen Versionen, insbesondere wenn das Vorhandensein von Argumenten optional ist oder deren Anzahl Variable ist.</span><span class="sxs-lookup"><span data-stu-id="c1ae0-111">You sometimes have alternatives to overloaded versions, particularly when the presence of arguments is optional or their number is variable.</span></span>  
  
 <span data-ttu-id="c1ae0-112">Denken Sie daran, die optionale Argumente nicht unbedingt von allen Sprachen unterstützt werden und Parameterarrays sind beschränkt auf [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span><span class="sxs-lookup"><span data-stu-id="c1ae0-112">Keep in mind that optional arguments are not necessarily supported by all languages, and parameter arrays are limited to [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span></span> <span data-ttu-id="c1ae0-113">Wenn Sie eine Prozedur schreiben, die wahrscheinlich in einem der anderen Sprachen geschriebenen Code aufgerufen werden, überladene bieten Versionen die größte Flexibilität.</span><span class="sxs-lookup"><span data-stu-id="c1ae0-113">If you are writing a procedure that is likely to be called from code written in any of several different languages, overloaded versions offer the greatest flexibility.</span></span>  
  
### <a name="overloads-and-optional-arguments"></a><span data-ttu-id="c1ae0-114">Overloads und optionale Argumente</span><span class="sxs-lookup"><span data-stu-id="c1ae0-114">Overloads and Optional Arguments</span></span>  
 <span data-ttu-id="c1ae0-115">Wenn der aufrufende Code kann optional angeben oder ein oder mehrere Argumente auslassen, können Sie mehrere überladene Versionen definieren oder optionale Parameter verwenden.</span><span class="sxs-lookup"><span data-stu-id="c1ae0-115">When the calling code can optionally supply or omit one or more arguments, you can define multiple overloaded versions or use optional parameters.</span></span>  
  
#### <a name="when-to-use-overloaded-versions"></a><span data-ttu-id="c1ae0-116">Verwendung von überladenen Versionen</span><span class="sxs-lookup"><span data-stu-id="c1ae0-116">When to Use Overloaded Versions</span></span>  
 <span data-ttu-id="c1ae0-117">Sie können in Betracht ziehen, definieren eine Reihe von überladenen Versionen in den folgenden Fällen:</span><span class="sxs-lookup"><span data-stu-id="c1ae0-117">You can consider defining a series of overloaded versions in the following cases:</span></span>  
  
-   <span data-ttu-id="c1ae0-118">Die Logik im Code Prozedur ist erheblich variieren, je nachdem, ob der aufrufende Code ein optionales Argument bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="c1ae0-118">The logic in the procedure code is significantly different depending on whether the calling code supplies an optional argument or not.</span></span>  
  
-   <span data-ttu-id="c1ae0-119">Prozedurcode kann nicht zuverlässig testen Sie, ob der aufrufende Code ein optionales Argument angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="c1ae0-119">The procedure code cannot reliably test whether the calling code has supplied an optional argument.</span></span> <span data-ttu-id="c1ae0-120">Dies ist der Fall, z. B. ist es keinen möglichen Kandidaten für einen Standardwert, der der Aufrufcode nicht zu erwarten angeben.</span><span class="sxs-lookup"><span data-stu-id="c1ae0-120">This is the case, for example, if there is no possible candidate for a default value that the calling code could not be expected to supply.</span></span>  
  
#### <a name="when-to-use-optional-parameters"></a><span data-ttu-id="c1ae0-121">Optionale Parameter verwenden.</span><span class="sxs-lookup"><span data-stu-id="c1ae0-121">When to Use Optional Parameters</span></span>  
 <span data-ttu-id="c1ae0-122">Sie können eine oder mehrere optionale Parameter in den folgenden Fällen bevorzugen:</span><span class="sxs-lookup"><span data-stu-id="c1ae0-122">You might prefer one or more optional parameters in the following cases:</span></span>  
  
-   <span data-ttu-id="c1ae0-123">Die einzige erforderliche Aktion, wenn der aufrufende Code ein optionale Argument nicht angegeben wird, ist den Parameter einen Standardwert festlegen.</span><span class="sxs-lookup"><span data-stu-id="c1ae0-123">The only required action when the calling code does not supply an optional argument is to set the parameter to a default value.</span></span> <span data-ttu-id="c1ae0-124">In diesem Fall der Code weniger kompliziert sein, wenn Sie eine einzelne Version mit einem oder mehreren definieren `Optional` Parameter.</span><span class="sxs-lookup"><span data-stu-id="c1ae0-124">In such a case, the procedure code can be less complicated if you define a single version with one or more `Optional` parameters.</span></span>  
  
 <span data-ttu-id="c1ae0-125">Weitere Informationen finden Sie unter [optionale Parameter](./optional-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="c1ae0-125">For more information, see [Optional Parameters](./optional-parameters.md).</span></span>  
  
### <a name="overloads-and-paramarrays"></a><span data-ttu-id="c1ae0-126">Overloads und ParamArrays</span><span class="sxs-lookup"><span data-stu-id="c1ae0-126">Overloads and ParamArrays</span></span>  
 <span data-ttu-id="c1ae0-127">Wenn der aufrufende Code eine Variable Anzahl von Argumenten übergeben kann, können Sie mehrere überladene Versionen definieren oder ein Parameterarray verwenden.</span><span class="sxs-lookup"><span data-stu-id="c1ae0-127">When the calling code can pass a variable number of arguments, you can define multiple overloaded versions or use a parameter array.</span></span>  
  
#### <a name="when-to-use-overloaded-versions"></a><span data-ttu-id="c1ae0-128">Verwendung von überladenen Versionen</span><span class="sxs-lookup"><span data-stu-id="c1ae0-128">When to Use Overloaded Versions</span></span>  
 <span data-ttu-id="c1ae0-129">Sie können in Betracht ziehen, definieren eine Reihe von überladenen Versionen in den folgenden Fällen:</span><span class="sxs-lookup"><span data-stu-id="c1ae0-129">You can consider defining a series of overloaded versions in the following cases:</span></span>  
  
-   <span data-ttu-id="c1ae0-130">Sie wissen, dass der aufrufende Code mehr als eine kleine Anzahl von Werten nie an den Parameterarray übergibt.</span><span class="sxs-lookup"><span data-stu-id="c1ae0-130">You know that the calling code never passes more than a small number of values to the parameter array.</span></span>  
  
-   <span data-ttu-id="c1ae0-131">Die Logik im Code Prozedur ist erheblich variieren, je nachdem wie viele Werte, die der aufrufende Code übergeben.</span><span class="sxs-lookup"><span data-stu-id="c1ae0-131">The logic in the procedure code is significantly different depending on how many values the calling code passes.</span></span>  
  
-   <span data-ttu-id="c1ae0-132">Der aufrufende Code kann es sich um Werte mit unterschiedlichen Datentypen übergeben.</span><span class="sxs-lookup"><span data-stu-id="c1ae0-132">The calling code can pass values of different data types.</span></span>  
  
#### <a name="when-to-use-a-parameter-array"></a><span data-ttu-id="c1ae0-133">Verwenden Sie ein Parameterarray</span><span class="sxs-lookup"><span data-stu-id="c1ae0-133">When to Use a Parameter Array</span></span>  
 <span data-ttu-id="c1ae0-134">Werden Sie besser von bedient ein `ParamArray` Parameter in den folgenden Fällen:</span><span class="sxs-lookup"><span data-stu-id="c1ae0-134">You are better served by a `ParamArray` parameter in the following cases:</span></span>  
  
-   <span data-ttu-id="c1ae0-135">Sie können nicht für die Vorhersage wie viele Werte der Aufrufcode an den Parameterarray übergeben kann, und dies möglicherweise eine große Anzahl.</span><span class="sxs-lookup"><span data-stu-id="c1ae0-135">You are not able to predict how many values the calling code can pass to the parameter array, and it could be a large number.</span></span>  
  
-   <span data-ttu-id="c1ae0-136">Logik der Prozedur bietet sich für alle Werte, die der aufrufende Code im Wesentlichen die gleichen Vorgänge für jeden Wert ausführen übergibt, durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="c1ae0-136">The procedure logic lends itself to iterating through all the values the calling code passes, performing essentially the same operations on every value.</span></span>  
  
 <span data-ttu-id="c1ae0-137">Weitere Informationen finden Sie unter [Parameterarrays](./parameter-arrays.md).</span><span class="sxs-lookup"><span data-stu-id="c1ae0-137">For more information, see [Parameter Arrays](./parameter-arrays.md).</span></span>  
  
## <a name="implicit-overloads-for-optional-parameters"></a><span data-ttu-id="c1ae0-138">Implizite Überladungen für optionale Parameter</span><span class="sxs-lookup"><span data-stu-id="c1ae0-138">Implicit Overloads for Optional Parameters</span></span>  
 <span data-ttu-id="c1ae0-139">Eine Prozedur mit einem [Optional](../../../../visual-basic/language-reference/modifiers/optional.md) Parameter entspricht zwei überladenen Prozeduren, einer mit dem optionalen Parameter und einer ohne.</span><span class="sxs-lookup"><span data-stu-id="c1ae0-139">A procedure with an [Optional](../../../../visual-basic/language-reference/modifiers/optional.md) parameter is equivalent to two overloaded procedures, one with the optional parameter and one without it.</span></span> <span data-ttu-id="c1ae0-140">Diese Prozedur kann nicht mit einer Liste von Parametern für eine der folgenden überladen werden.</span><span class="sxs-lookup"><span data-stu-id="c1ae0-140">You cannot overload such a procedure with a parameter list corresponding to either of these.</span></span> <span data-ttu-id="c1ae0-141">Die folgenden Deklarationen verdeutlichen dies.</span><span class="sxs-lookup"><span data-stu-id="c1ae0-141">The following declarations illustrate this.</span></span>  
  
 <span data-ttu-id="c1ae0-142">[!code-vb[VbVbcnProcedures&#58;](./codesnippet/VisualBasic/considerations-in-overloading-procedures_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="c1ae0-142">[!code-vb[VbVbcnProcedures#58](./codesnippet/VisualBasic/considerations-in-overloading-procedures_1.vb)]</span></span>  
  
 <span data-ttu-id="c1ae0-143">[!code-vb[VbVbcnProcedures&60;](./codesnippet/VisualBasic/considerations-in-overloading-procedures_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="c1ae0-143">[!code-vb[VbVbcnProcedures#60](./codesnippet/VisualBasic/considerations-in-overloading-procedures_2.vb)]</span></span>  
  
 <span data-ttu-id="c1ae0-144">[!code-vb[VbVbcnProcedures&#61;](./codesnippet/VisualBasic/considerations-in-overloading-procedures_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="c1ae0-144">[!code-vb[VbVbcnProcedures#61](./codesnippet/VisualBasic/considerations-in-overloading-procedures_3.vb)]</span></span>  
  
 <span data-ttu-id="c1ae0-145">Eine Prozedur mit mehreren optionalen Parameter ist es eine Gruppe implizite Überladungen, die Logik, die im vorherigen Beispiel ähnelt angekommen.</span><span class="sxs-lookup"><span data-stu-id="c1ae0-145">For a procedure with more than one optional parameter, there is a set of implicit overloads, arrived at by logic similar to that in the preceding example.</span></span>  
  
## <a name="implicit-overloads-for-a-paramarray-parameter"></a><span data-ttu-id="c1ae0-146">Implizite Überladungen für ParamArray-Parameter</span><span class="sxs-lookup"><span data-stu-id="c1ae0-146">Implicit Overloads for a ParamArray Parameter</span></span>  
 <span data-ttu-id="c1ae0-147">Der Compiler betrachtet eine Prozedur mit einem [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) Parameter haben eine unendliche Anzahl von Überladungen, unterscheiden sich voneinander in der aufrufende Code wie folgt an den Parameterarray übergibt:</span><span class="sxs-lookup"><span data-stu-id="c1ae0-147">The compiler considers a procedure with a [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) parameter to have an infinite number of overloads, differing from each other in what the calling code passes to the parameter array, as follows:</span></span>  
  
-   <span data-ttu-id="c1ae0-148">Eine Überladung für den Fall der aufrufende Code kein Argument übergibt die`ParamArray`</span><span class="sxs-lookup"><span data-stu-id="c1ae0-148">One overload for when the calling code does not supply an argument to the `ParamArray`</span></span>  
  
-   <span data-ttu-id="c1ae0-149">Eine Überladung für Wenn der aufrufende Code ein eindimensionales Array von stellt die `ParamArray` Elementtyp</span><span class="sxs-lookup"><span data-stu-id="c1ae0-149">One overload for when the calling code supplies a one-dimensional array of the `ParamArray` element type</span></span>  
  
-   <span data-ttu-id="c1ae0-150">Für jede positive ganze Zahl eine Überladung für der aufrufende Code diese Anzahl von Argumenten, die jeweils von liefert die `ParamArray` Elementtyp</span><span class="sxs-lookup"><span data-stu-id="c1ae0-150">For every positive integer, one overload for when the calling code supplies that number of arguments, each of the `ParamArray` element type</span></span>  
  
 <span data-ttu-id="c1ae0-151">Die folgenden Deklarationen veranschaulichen diese implizite Überladungen.</span><span class="sxs-lookup"><span data-stu-id="c1ae0-151">The following declarations illustrate these implicit overloads.</span></span>  
  
 <span data-ttu-id="c1ae0-152">[!code-vb[VbVbcnProcedures&#68;](./codesnippet/VisualBasic/considerations-in-overloading-procedures_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="c1ae0-152">[!code-vb[VbVbcnProcedures#68](./codesnippet/VisualBasic/considerations-in-overloading-procedures_4.vb)]</span></span>  
  
 <span data-ttu-id="c1ae0-153">[!code-vb[VbVbcnProcedures&#70;](./codesnippet/VisualBasic/considerations-in-overloading-procedures_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="c1ae0-153">[!code-vb[VbVbcnProcedures#70](./codesnippet/VisualBasic/considerations-in-overloading-procedures_5.vb)]</span></span>  
  
 <span data-ttu-id="c1ae0-154">Sie können nicht eine solche Prozedur mit einer Parameterliste überladen, die ein eindimensionales Array für das Parameterarray akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="c1ae0-154">You cannot overload such a procedure with a parameter list that takes a one-dimensional array for the parameter array.</span></span> <span data-ttu-id="c1ae0-155">Sie können jedoch die Signaturen von anderen implizite Überladungen.</span><span class="sxs-lookup"><span data-stu-id="c1ae0-155">However, you can use the signatures of the other implicit overloads.</span></span> <span data-ttu-id="c1ae0-156">Die folgenden Deklarationen verdeutlichen dies.</span><span class="sxs-lookup"><span data-stu-id="c1ae0-156">The following declarations illustrate this.</span></span>  
  
 <span data-ttu-id="c1ae0-157">[!code-vb[VbVbcnProcedures&#71;](./codesnippet/VisualBasic/considerations-in-overloading-procedures_6.vb)]</span><span class="sxs-lookup"><span data-stu-id="c1ae0-157">[!code-vb[VbVbcnProcedures#71](./codesnippet/VisualBasic/considerations-in-overloading-procedures_6.vb)]</span></span>  
  
## <a name="typeless-programming-as-an-alternative-to-overloading"></a><span data-ttu-id="c1ae0-158">Programmierung ohne Datentypen als Alternative zur Überladung</span><span class="sxs-lookup"><span data-stu-id="c1ae0-158">Typeless Programming as an Alternative to Overloading</span></span>  
 <span data-ttu-id="c1ae0-159">Wenn den aufrufenden Code unterschiedliche Datentypen an einen Parameter übergeben werden soll, ist eine alternative Methode Programmierung ohne Datentypen.</span><span class="sxs-lookup"><span data-stu-id="c1ae0-159">If you want to allow the calling code to pass different data types to a parameter, an alternative approach is typeless programming.</span></span> <span data-ttu-id="c1ae0-160">Lassen sich die Schalter für die Typprüfung `Off` entweder mit der [Option Strict-Anweisung](../../../../visual-basic/language-reference/statements/option-strict-statement.md) oder [/optionstrict](../../../../visual-basic/reference/command-line-compiler/optionstrict.md) (Compileroption).</span><span class="sxs-lookup"><span data-stu-id="c1ae0-160">You can set the type checking switch to `Off` with either the [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md) or the [/optionstrict](../../../../visual-basic/reference/command-line-compiler/optionstrict.md) compiler option.</span></span> <span data-ttu-id="c1ae0-161">Dann müssen Sie keinen Datentyp des Parameters zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="c1ae0-161">Then you do not have to declare the parameter's data type.</span></span> <span data-ttu-id="c1ae0-162">Dieser Ansatz hat jedoch die folgenden Nachteile im Vergleich zum Überladen:</span><span class="sxs-lookup"><span data-stu-id="c1ae0-162">However, this approach has the following disadvantages compared to overloading:</span></span>  
  
-   <span data-ttu-id="c1ae0-163">Programmierung ohne Datentypen ergibt weniger effizienten Ausführungscode.</span><span class="sxs-lookup"><span data-stu-id="c1ae0-163">Typeless programming produces less efficient execution code.</span></span>  
  
-   <span data-ttu-id="c1ae0-164">Die Prozedur muss für jeden Datentyp testen, dessen Übergabe.</span><span class="sxs-lookup"><span data-stu-id="c1ae0-164">The procedure must test for every data type it anticipates being passed.</span></span>  
  
-   <span data-ttu-id="c1ae0-165">Der Compiler kann nicht auf einen Fehler signalisieren, wenn der aufrufende Code einen Datentyp übergibt, den die Prozedur nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="c1ae0-165">The compiler cannot signal an error if the calling code passes a data type that the procedure does not support.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1ae0-166">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c1ae0-166">See Also</span></span>  
 <span data-ttu-id="c1ae0-167">[Verfahren](./index.md) </span><span class="sxs-lookup"><span data-stu-id="c1ae0-167">[Procedures](./index.md) </span></span>  
<span data-ttu-id="c1ae0-168"> [Prozedurparameter und Argumente](./procedure-parameters-and-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="c1ae0-168"> [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md) </span></span>  
<span data-ttu-id="c1ae0-169"> [Problembehandlung bei Prozeduren](./troubleshooting-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="c1ae0-169"> [Troubleshooting Procedures](./troubleshooting-procedures.md) </span></span>  
<span data-ttu-id="c1ae0-170"> [Gewusst wie: Definieren mehrerer Versionen einer Prozedur](./how-to-define-multiple-versions-of-a-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="c1ae0-170"> [How to: Define Multiple Versions of a Procedure](./how-to-define-multiple-versions-of-a-procedure.md) </span></span>  
<span data-ttu-id="c1ae0-171"> [Gewusst wie: Aufrufen einer überladenen Prozedur](./how-to-call-an-overloaded-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="c1ae0-171"> [How to: Call an Overloaded Procedure](./how-to-call-an-overloaded-procedure.md) </span></span>  
<span data-ttu-id="c1ae0-172"> [Gewusst wie: überladen eine Prozedur mit optionalen Parametern](./how-to-overload-a-procedure-that-takes-optional-parameters.md) </span><span class="sxs-lookup"><span data-stu-id="c1ae0-172"> [How to: Overload a Procedure that Takes Optional Parameters](./how-to-overload-a-procedure-that-takes-optional-parameters.md) </span></span>  
<span data-ttu-id="c1ae0-173"> [Gewusst wie: überladen eine Prozedur mit einer unbestimmten Anzahl von Parametern](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md) </span><span class="sxs-lookup"><span data-stu-id="c1ae0-173"> [How to: Overload a Procedure that Takes an Indefinite Number of Parameters](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md) </span></span>  
<span data-ttu-id="c1ae0-174"> [Überladungsauflösung](./overload-resolution.md) </span><span class="sxs-lookup"><span data-stu-id="c1ae0-174"> [Overload Resolution](./overload-resolution.md) </span></span>  
<span data-ttu-id="c1ae0-175"> [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md)</span><span class="sxs-lookup"><span data-stu-id="c1ae0-175"> [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md)</span></span>
