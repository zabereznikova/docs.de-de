---
title: Gelockert Delegatenkonvertierung (Visual Basic) | Microsoft-Dokumentation
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
- relaxed delegate conversion [Visual Basic]
- delegates [Visual Basic], relaxed conversion
- conversions, relaxed delegate
ms.assetid: 64f371d0-5416-4f65-b23b-adcbf556e81c
caps.latest.revision: 19
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
ms.openlocfilehash: 016c808145f7faba26a288cd5075f10d7f5279d5
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="relaxed-delegate-conversion-visual-basic"></a><span data-ttu-id="ac535-102">Gelockerte Delegatenkonvertierung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ac535-102">Relaxed Delegate Conversion (Visual Basic)</span></span>
<span data-ttu-id="ac535-103">Gelockerte delegatenkonvertierung können Sie Funktionen und Subroutinen Delegaten und Handler zuweisen, selbst wenn die Signaturen nicht identisch sind.</span><span class="sxs-lookup"><span data-stu-id="ac535-103">Relaxed delegate conversion enables you to assign subs and functions to delegates or handlers even when their signatures are not identical.</span></span> <span data-ttu-id="ac535-104">Das Binden an Delegaten ist deshalb konsistent mit dem bereits zulässigen Binden für Methodenaufrufe.</span><span class="sxs-lookup"><span data-stu-id="ac535-104">Therefore, binding to delegates becomes consistent with the binding already allowed for method invocations.</span></span>  
  
## <a name="parameters-and-return-type"></a><span data-ttu-id="ac535-105">Parameter und Rückgabetyp</span><span class="sxs-lookup"><span data-stu-id="ac535-105">Parameters and Return Type</span></span>  
 <span data-ttu-id="ac535-106">Anstelle der Signatur genaue Übereinstimmung gelockerte Konvertierung muss Folgendes erfüllt sein beim `Option Strict` Wert `On`:</span><span class="sxs-lookup"><span data-stu-id="ac535-106">In place of exact signature match, relaxed conversion requires that the following conditions be met when `Option Strict` is set to `On`:</span></span>  
  
-   <span data-ttu-id="ac535-107">Eine erweiternde Konvertierung bestehen aus den Datentyp jedes Parameters Delegaten in den Datentyp des entsprechenden Parameters der zugewiesenen Funktion oder `Sub`.</span><span class="sxs-lookup"><span data-stu-id="ac535-107">A widening conversion must exist from the data type of each delegate parameter to the data type of the corresponding parameter of the assigned function or `Sub`.</span></span> <span data-ttu-id="ac535-108">Im folgenden Beispiel den Delegaten `Del1` verfügt über einen Parameter, ein `Integer`.</span><span class="sxs-lookup"><span data-stu-id="ac535-108">In the following example, the delegate `Del1` has one parameter, an `Integer`.</span></span> <span data-ttu-id="ac535-109">Parameter `m` Ausdrücke müssen in der zugewiesenen Lambda-Ausdruck einen Datentyp für die von eine erweiternde Konvertierung vorhanden ist `Integer`, wie z. B. `Long` oder `Double`.</span><span class="sxs-lookup"><span data-stu-id="ac535-109">Parameter `m` in the assigned lambda expressions must have a data type for which there is a widening conversion from `Integer`, such as `Long` or `Double`.</span></span>  
  
     <span data-ttu-id="ac535-110">[!code-vb[VbVbalrRelaxedDelegates&#1;](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="ac535-110">[!code-vb[VbVbalrRelaxedDelegates#1](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_1.vb)]</span></span>  
  
     <span data-ttu-id="ac535-111">[!code-vb[VbVbalrRelaxedDelegates&#2;](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="ac535-111">[!code-vb[VbVbalrRelaxedDelegates#2](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_2.vb)]</span></span>  
  
     <span data-ttu-id="ac535-112">Einschränkende Konvertierungen dürfen nur, wenn `Option Strict` Wert `Off`.</span><span class="sxs-lookup"><span data-stu-id="ac535-112">Narrowing conversions are permitted only when `Option Strict` is set to `Off`.</span></span>  
  
     <span data-ttu-id="ac535-113">[!code-vb[VbVbalrRelaxedDelegates&#8;](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="ac535-113">[!code-vb[VbVbalrRelaxedDelegates#8](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_3.vb)]</span></span>  
  
-   <span data-ttu-id="ac535-114">Eine erweiternde Konvertierung muss vorhanden sein, in die entgegengesetzte Richtung vom Rückgabetyp der zugeordneten Funktion oder `Sub` in den Rückgabetyp des Delegaten.</span><span class="sxs-lookup"><span data-stu-id="ac535-114">A widening conversion must exist in the opposite direction from the return type of the assigned function or `Sub` to the return type of the delegate.</span></span> <span data-ttu-id="ac535-115">In den folgenden Beispielen muss der Text jedes zugewiesenen Lambda-Ausdrucks in einen Datentyp, der erweitert ausgewertet `Integer` , da der Rückgabetyp der `del1` ist `Integer`.</span><span class="sxs-lookup"><span data-stu-id="ac535-115">In the following examples, the body of each assigned lambda expression must evaluate to a data type that widens to `Integer` because the return type of `del1` is `Integer`.</span></span>  
  
     <span data-ttu-id="ac535-116">[!code-vb[VbVbalrRelaxedDelegates&3;](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="ac535-116">[!code-vb[VbVbalrRelaxedDelegates#3](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_4.vb)]</span></span>  
  
 <span data-ttu-id="ac535-117">Wenn `Option Strict` Wert `Off`, die erweiternde Einschränkung in beide Richtungen entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="ac535-117">If `Option Strict` is set to `Off`, the widening restriction is removed in both directions.</span></span>  
  
 <span data-ttu-id="ac535-118">[!code-vb[VbVbalrRelaxedDelegates&4;](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="ac535-118">[!code-vb[VbVbalrRelaxedDelegates#4](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_5.vb)]</span></span>  
  
## <a name="omitting-parameter-specifications"></a><span data-ttu-id="ac535-119">Auslassen von Parameterspezifikationen</span><span class="sxs-lookup"><span data-stu-id="ac535-119">Omitting Parameter Specifications</span></span>  
 <span data-ttu-id="ac535-120">Lockere Delegaten können auch Sie Parameterspezifikationen in der zugewiesenen Methode vollständig auslassen:</span><span class="sxs-lookup"><span data-stu-id="ac535-120">Relaxed delegates also allow you to completely omit parameter specifications in the assigned method:</span></span>  
  
 <span data-ttu-id="ac535-121">[!code-vb[VbVbalrRelaxedDelegates&5;](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_6.vb)]</span><span class="sxs-lookup"><span data-stu-id="ac535-121">[!code-vb[VbVbalrRelaxedDelegates#5](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_6.vb)]</span></span>  
  
 <span data-ttu-id="ac535-122">[!code-vb[VbVbalrRelaxedDelegates&6;](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_7.vb)]</span><span class="sxs-lookup"><span data-stu-id="ac535-122">[!code-vb[VbVbalrRelaxedDelegates#6](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_7.vb)]</span></span>  
  
 <span data-ttu-id="ac535-123">Beachten Sie, dass Sie nicht einige Parameter angeben und anderen weglassen.</span><span class="sxs-lookup"><span data-stu-id="ac535-123">Note that you cannot specify some parameters and omit others.</span></span>  
  
 <span data-ttu-id="ac535-124">[!code-vb[VbVbalrRelaxedDelegates&#15;](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_8.vb)]</span><span class="sxs-lookup"><span data-stu-id="ac535-124">[!code-vb[VbVbalrRelaxedDelegates#15](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_8.vb)]</span></span>  
  
 <span data-ttu-id="ac535-125">Die Möglichkeit, Parameter auslassen, empfiehlt sich in einer Situation wie definieren einen Ereignishandler, in dem mehrere komplexe Parameter beteiligt sind.</span><span class="sxs-lookup"><span data-stu-id="ac535-125">The ability to omit parameters is helpful in a situation such as defining an event handler, where several complex parameters are involved.</span></span> <span data-ttu-id="ac535-126">Die Argumente für einige Ereignishandler werden nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="ac535-126">The arguments to some event handlers are not used.</span></span> <span data-ttu-id="ac535-127">Stattdessen greift der Handler direkt über den Zustand des Steuerelements auf dem das Ereignis registriert ist, und ignoriert die Argumente.</span><span class="sxs-lookup"><span data-stu-id="ac535-127">Instead, the handler directly accesses the state of the control on which the event is registered, and ignores the arguments.</span></span> <span data-ttu-id="ac535-128">Lockere Delegaten ermöglichen Ihnen, lassen Sie die Argumente in dieser Erklärung, wenn keine Mehrdeutigkeiten auftreten.</span><span class="sxs-lookup"><span data-stu-id="ac535-128">Relaxed delegates allow you to omit the arguments in such declarations when no ambiguities result.</span></span> <span data-ttu-id="ac535-129">Im folgenden Beispiel, die vollständig angegebene Methode `OnClick` kann wie folgt umgeschrieben werden `RelaxedOnClick`.</span><span class="sxs-lookup"><span data-stu-id="ac535-129">In the following example, the fully specified method `OnClick` can be rewritten as `RelaxedOnClick`.</span></span>  
  
```vb  
Sub OnClick(ByVal sender As Object, ByVal e As EventArgs) Handles b.Click  
    MessageBox.Show("Hello World from" + b.Text)  
End Sub  
  
Sub RelaxedOnClick() Handles b.Click  
    MessageBox.Show("Hello World from" + b.Text)  
End Sub  
```  
  
## <a name="addressof-examples"></a><span data-ttu-id="ac535-130">AddressOf-Beispiele</span><span class="sxs-lookup"><span data-stu-id="ac535-130">AddressOf Examples</span></span>  
 <span data-ttu-id="ac535-131">Lambda-Ausdrücke werden in den vorherigen Beispielen zum typbeziehungen finden Sie unter vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="ac535-131">Lambda expressions are used in the previous examples to make the type relationships easy to see.</span></span> <span data-ttu-id="ac535-132">Die gleichen Relaxations sind jedoch zulässig, für die Zuweisung von Delegaten, mit denen `AddressOf`, `Handles`, oder `AddHandler`.</span><span class="sxs-lookup"><span data-stu-id="ac535-132">However, the same relaxations are permitted for delegate assignments that use `AddressOf`, `Handles`, or `AddHandler`.</span></span>  
  
 <span data-ttu-id="ac535-133">Im folgenden Beispiel funktioniert `f1`, `f2`, `f3`, und `f4` können alle zugewiesen werden `Del1`.</span><span class="sxs-lookup"><span data-stu-id="ac535-133">In the following example, functions `f1`, `f2`, `f3`, and `f4` can all be assigned to `Del1`.</span></span>  
  
 <span data-ttu-id="ac535-134">[!code-vb[VbVbalrRelaxedDelegates&#1;](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="ac535-134">[!code-vb[VbVbalrRelaxedDelegates#1](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_1.vb)]</span></span>  
  
 <span data-ttu-id="ac535-135">[!code-vb[VbVbalrRelaxedDelegates&#7;](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_9.vb)]</span><span class="sxs-lookup"><span data-stu-id="ac535-135">[!code-vb[VbVbalrRelaxedDelegates#7](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_9.vb)]</span></span>  
  
 <span data-ttu-id="ac535-136">[!code-vb[VbVbalrRelaxedDelegates&#9;](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_10.vb)]</span><span class="sxs-lookup"><span data-stu-id="ac535-136">[!code-vb[VbVbalrRelaxedDelegates#9](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_10.vb)]</span></span>  
  
 <span data-ttu-id="ac535-137">Das folgende Beispiel ist nur gültig, wenn `Option Strict` Wert `Off`.</span><span class="sxs-lookup"><span data-stu-id="ac535-137">The following example is valid only when `Option Strict` is set to `Off`.</span></span>  
  
 <span data-ttu-id="ac535-138">[!code-vb[VbVbalrRelaxedDelegates&14;](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_11.vb)]</span><span class="sxs-lookup"><span data-stu-id="ac535-138">[!code-vb[VbVbalrRelaxedDelegates#14](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_11.vb)]</span></span>  
  
## <a name="dropping-function-returns"></a><span data-ttu-id="ac535-139">Funktionsrückgabewerten</span><span class="sxs-lookup"><span data-stu-id="ac535-139">Dropping Function Returns</span></span>  
 <span data-ttu-id="ac535-140">Gelockerte delegatenkonvertierung ermöglicht es Ihnen, eine Funktion zum Zuweisen einer `Sub` -Delegaten effektiv ignoriert den Rückgabewert der Funktion.</span><span class="sxs-lookup"><span data-stu-id="ac535-140">Relaxed delegate conversion enables you to assign a function to a `Sub` delegate, effectively ignoring the return value of the function.</span></span> <span data-ttu-id="ac535-141">Sie können keine zuweisen eine `Sub` einen Funktionsdelegaten.</span><span class="sxs-lookup"><span data-stu-id="ac535-141">However, you cannot assign a `Sub` to a function delegate.</span></span> <span data-ttu-id="ac535-142">Im folgenden Beispiel wird die Adresse der Funktion `doubler` zugewiesen `Sub` Delegieren `Del3`.</span><span class="sxs-lookup"><span data-stu-id="ac535-142">In the following example, the address of function `doubler` is assigned to `Sub` delegate `Del3`.</span></span>  
  
 <span data-ttu-id="ac535-143">[!code-vb[VbVbalrRelaxedDelegates&#10;](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_12.vb)]</span><span class="sxs-lookup"><span data-stu-id="ac535-143">[!code-vb[VbVbalrRelaxedDelegates#10](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_12.vb)]</span></span>  
  
 <span data-ttu-id="ac535-144">[!code-vb[VbVbalrRelaxedDelegates&#11;](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_13.vb)]</span><span class="sxs-lookup"><span data-stu-id="ac535-144">[!code-vb[VbVbalrRelaxedDelegates#11](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_13.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac535-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ac535-145">See Also</span></span>  
 <span data-ttu-id="ac535-146">[Lambda-Ausdrücke](../../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="ac535-146">[Lambda Expressions](../../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md) </span></span>  
<span data-ttu-id="ac535-147"> [Erweiternde und eingrenzende Konvertierungen](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) </span><span class="sxs-lookup"><span data-stu-id="ac535-147"> [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) </span></span>  
<span data-ttu-id="ac535-148"> [Delegaten](../../../../visual-basic/programming-guide/language-features/delegates/index.md) </span><span class="sxs-lookup"><span data-stu-id="ac535-148"> [Delegates](../../../../visual-basic/programming-guide/language-features/delegates/index.md) </span></span>  
<span data-ttu-id="ac535-149"> [Gewusst wie: Übergeben von Prozeduren an eine andere Prozedur in Visual Basic](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="ac535-149"> [How to: Pass Procedures to Another Procedure in Visual Basic](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md) </span></span>  
<span data-ttu-id="ac535-150"> [Lokaler Typrückschluss](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) </span><span class="sxs-lookup"><span data-stu-id="ac535-150"> [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) </span></span>  
<span data-ttu-id="ac535-151"> [Option Strict-Anweisung](../../../../visual-basic/language-reference/statements/option-strict-statement.md)</span><span class="sxs-lookup"><span data-stu-id="ac535-151"> [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)</span></span>
