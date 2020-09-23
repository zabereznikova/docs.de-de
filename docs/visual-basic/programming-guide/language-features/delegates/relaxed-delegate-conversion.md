---
title: Gelockerte Delegatenkonvertierung
ms.date: 07/20/2015
helpviewer_keywords:
- relaxed delegate conversion [Visual Basic]
- delegates [Visual Basic], relaxed conversion
- conversions [Visual Basic], relaxed delegate
ms.assetid: 64f371d0-5416-4f65-b23b-adcbf556e81c
ms.openlocfilehash: b914d0479f160199744a8f9923c0bebc87321329
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91086074"
---
# <a name="relaxed-delegate-conversion-visual-basic"></a><span data-ttu-id="192bb-102">Gelockerte Delegatenkonvertierung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="192bb-102">Relaxed Delegate Conversion (Visual Basic)</span></span>

<span data-ttu-id="192bb-103">Eine gelockerte Delegatkonvertierung ermöglicht Ihnen das Zuweisen von subs und Funktionen zu Delegaten oder Handlern, auch wenn Ihre Signaturen nicht identisch sind.</span><span class="sxs-lookup"><span data-stu-id="192bb-103">Relaxed delegate conversion enables you to assign subs and functions to delegates or handlers even when their signatures are not identical.</span></span> <span data-ttu-id="192bb-104">Daher wird die Bindung an Delegaten konsistent mit der Bindung, die für Methodenaufrufe bereits zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="192bb-104">Therefore, binding to delegates becomes consistent with the binding already allowed for method invocations.</span></span>  
  
## <a name="parameters-and-return-type"></a><span data-ttu-id="192bb-105">Parameter und Rückgabetyp</span><span class="sxs-lookup"><span data-stu-id="192bb-105">Parameters and Return Type</span></span>  

 <span data-ttu-id="192bb-106">Anstelle der genauen Signatur Übereinstimmung erfordert die gelockerte Konvertierung, dass die folgenden Bedingungen erfüllt sind, wenn `Option Strict` auf festgelegt ist `On` :</span><span class="sxs-lookup"><span data-stu-id="192bb-106">In place of exact signature match, relaxed conversion requires that the following conditions be met when `Option Strict` is set to `On`:</span></span>  
  
- <span data-ttu-id="192bb-107">Eine erweiternde Konvertierung muss vom Datentyp der einzelnen Delegatparameter bis zu dem Datentyp des entsprechenden Parameters der zugewiesenen Funktion oder durch vorhanden sein `Sub` .</span><span class="sxs-lookup"><span data-stu-id="192bb-107">A widening conversion must exist from the data type of each delegate parameter to the data type of the corresponding parameter of the assigned function or `Sub`.</span></span> <span data-ttu-id="192bb-108">Im folgenden Beispiel verfügt der Delegat `Del1` über einen Parameter, einen `Integer` .</span><span class="sxs-lookup"><span data-stu-id="192bb-108">In the following example, the delegate `Del1` has one parameter, an `Integer`.</span></span> <span data-ttu-id="192bb-109">Der-Parameter `m` in den zugewiesenen Lambda-Ausdrücken muss einen Datentyp aufweisen, für den eine erweiternde Konvertierung von vorhanden ist `Integer` , z `Long` . b `Double` . oder.</span><span class="sxs-lookup"><span data-stu-id="192bb-109">Parameter `m` in the assigned lambda expressions must have a data type for which there is a widening conversion from `Integer`, such as `Long` or `Double`.</span></span>  
  
     [!code-vb[VbVbalrRelaxedDelegates#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#1)]  
  
     [!code-vb[VbVbalrRelaxedDelegates#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#2)]  
  
     <span data-ttu-id="192bb-110">Einschränkende Konvertierungen sind nur zulässig `Option Strict` , wenn auf festgelegt ist `Off` .</span><span class="sxs-lookup"><span data-stu-id="192bb-110">Narrowing conversions are permitted only when `Option Strict` is set to `Off`.</span></span>  
  
     [!code-vb[VbVbalrRelaxedDelegates#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module2.vb#8)]  
  
- <span data-ttu-id="192bb-111">Eine erweiternde Konvertierung muss in umgekehrter Richtung vom Rückgabetyp der zugewiesenen Funktion oder `Sub` zum Rückgabetyp des Delegaten vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="192bb-111">A widening conversion must exist in the opposite direction from the return type of the assigned function or `Sub` to the return type of the delegate.</span></span> <span data-ttu-id="192bb-112">In den folgenden Beispielen muss der Text der einzelnen zugewiesenen Lambda-Ausdrücke zu einem Datentyp ausgewertet werden, der zu erweitert `Integer` wird, da der Rückgabetyp von `del1` ist `Integer` .</span><span class="sxs-lookup"><span data-stu-id="192bb-112">In the following examples, the body of each assigned lambda expression must evaluate to a data type that widens to `Integer` because the return type of `del1` is `Integer`.</span></span>  
  
     [!code-vb[VbVbalrRelaxedDelegates#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#3)]  
  
 <span data-ttu-id="192bb-113">Wenn `Option Strict` auf festgelegt ist `Off` , wird die erweiternde Einschränkung in beide Richtungen entfernt.</span><span class="sxs-lookup"><span data-stu-id="192bb-113">If `Option Strict` is set to `Off`, the widening restriction is removed in both directions.</span></span>  
  
 [!code-vb[VbVbalrRelaxedDelegates#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module2.vb#4)]  
  
## <a name="omitting-parameter-specifications"></a><span data-ttu-id="192bb-114">Weglassen von Parameter Spezifikationen</span><span class="sxs-lookup"><span data-stu-id="192bb-114">Omitting Parameter Specifications</span></span>  

 <span data-ttu-id="192bb-115">Mit gelockerten Delegaten können Sie auch die Parameter Spezifikationen in der zugewiesenen Methode vollständig weglassen:</span><span class="sxs-lookup"><span data-stu-id="192bb-115">Relaxed delegates also allow you to completely omit parameter specifications in the assigned method:</span></span>  
  
 [!code-vb[VbVbalrRelaxedDelegates#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#5)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#6)]  
  
 <span data-ttu-id="192bb-116">Beachten Sie, dass Sie einige Parameter nicht angeben können, und lassen Sie andere aus.</span><span class="sxs-lookup"><span data-stu-id="192bb-116">Note that you cannot specify some parameters and omit others.</span></span>  
  
 [!code-vb[VbVbalrRelaxedDelegates#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#15)]  
  
 <span data-ttu-id="192bb-117">Die Möglichkeit, Parameter auszulassen, ist in einer Situation hilfreich, z. b. beim Definieren eines Ereignis Handlers, bei dem mehrere komplexe Parameter beteiligt sind.</span><span class="sxs-lookup"><span data-stu-id="192bb-117">The ability to omit parameters is helpful in a situation such as defining an event handler, where several complex parameters are involved.</span></span> <span data-ttu-id="192bb-118">Die Argumente für einige Ereignishandler werden nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="192bb-118">The arguments to some event handlers are not used.</span></span> <span data-ttu-id="192bb-119">Stattdessen greift der Handler direkt auf den Zustand des Steuer Elements zu, für das das Ereignis registriert ist, und ignoriert die Argumente.</span><span class="sxs-lookup"><span data-stu-id="192bb-119">Instead, the handler directly accesses the state of the control on which the event is registered, and ignores the arguments.</span></span> <span data-ttu-id="192bb-120">Mit gelockerten Delegaten können Sie die Argumente in solchen Deklarationen weglassen, wenn keine Mehrdeutigkeiten entstehen.</span><span class="sxs-lookup"><span data-stu-id="192bb-120">Relaxed delegates allow you to omit the arguments in such declarations when no ambiguities result.</span></span> <span data-ttu-id="192bb-121">Im folgenden Beispiel kann die vollständig angegebene Methode `OnClick` als umgeschrieben werden `RelaxedOnClick` .</span><span class="sxs-lookup"><span data-stu-id="192bb-121">In the following example, the fully specified method `OnClick` can be rewritten as `RelaxedOnClick`.</span></span>  
  
```vb  
Sub OnClick(ByVal sender As Object, ByVal e As EventArgs) Handles b.Click  
    MessageBox.Show("Hello World from" + b.Text)  
End Sub  
  
Sub RelaxedOnClick() Handles b.Click  
    MessageBox.Show("Hello World from" + b.Text)  
End Sub  
```  
  
## <a name="addressof-examples"></a><span data-ttu-id="192bb-122">AddressOf-Beispiele</span><span class="sxs-lookup"><span data-stu-id="192bb-122">AddressOf Examples</span></span>  

 <span data-ttu-id="192bb-123">In den vorherigen Beispielen werden Lambda Ausdrücke verwendet, um die Typbeziehungen leicht zu erkennen.</span><span class="sxs-lookup"><span data-stu-id="192bb-123">Lambda expressions are used in the previous examples to make the type relationships easy to see.</span></span> <span data-ttu-id="192bb-124">Allerdings sind die gleichen Lockerungen für delegatzuweisungen zulässig, die `AddressOf` , `Handles` oder verwenden `AddHandler` .</span><span class="sxs-lookup"><span data-stu-id="192bb-124">However, the same relaxations are permitted for delegate assignments that use `AddressOf`, `Handles`, or `AddHandler`.</span></span>  
  
 <span data-ttu-id="192bb-125">Im folgenden Beispiel `f1` können Funktionen, `f2` , `f3` und `f4` zugewiesen werden `Del1` .</span><span class="sxs-lookup"><span data-stu-id="192bb-125">In the following example, functions `f1`, `f2`, `f3`, and `f4` can all be assigned to `Del1`.</span></span>  
  
 [!code-vb[VbVbalrRelaxedDelegates#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#1)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#7)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#9)]  
  
 <span data-ttu-id="192bb-126">Das folgende Beispiel ist nur gültig `Option Strict` , wenn auf festgelegt ist `Off` .</span><span class="sxs-lookup"><span data-stu-id="192bb-126">The following example is valid only when `Option Strict` is set to `Off`.</span></span>  
  
 [!code-vb[VbVbalrRelaxedDelegates#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module2.vb#14)]  
  
## <a name="dropping-function-returns"></a><span data-ttu-id="192bb-127">Verwerfen von Funktions Rückgaben</span><span class="sxs-lookup"><span data-stu-id="192bb-127">Dropping Function Returns</span></span>  

 <span data-ttu-id="192bb-128">Eine gelockerte Delegatkonvertierung ermöglicht Ihnen das Zuweisen einer Funktion zu einem Delegaten `Sub` , wodurch der Rückgabewert der Funktion tatsächlich ignoriert wird.</span><span class="sxs-lookup"><span data-stu-id="192bb-128">Relaxed delegate conversion enables you to assign a function to a `Sub` delegate, effectively ignoring the return value of the function.</span></span> <span data-ttu-id="192bb-129">Es ist jedoch nicht möglich, einem Funktions Delegaten eine zuzuweisen `Sub` .</span><span class="sxs-lookup"><span data-stu-id="192bb-129">However, you cannot assign a `Sub` to a function delegate.</span></span> <span data-ttu-id="192bb-130">Im folgenden Beispiel wird die Adresse der-Funktion dem-Delegaten `doubler` zugewiesen `Sub` `Del3` .</span><span class="sxs-lookup"><span data-stu-id="192bb-130">In the following example, the address of function `doubler` is assigned to `Sub` delegate `Del3`.</span></span>  
  
 [!code-vb[VbVbalrRelaxedDelegates#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#10)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrRelaxedDelegates/VB/Module1.vb#11)]  
  
## <a name="see-also"></a><span data-ttu-id="192bb-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="192bb-131">See also</span></span>

- [<span data-ttu-id="192bb-132">Lambda-Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="192bb-132">Lambda Expressions</span></span>](../procedures/lambda-expressions.md)
- [<span data-ttu-id="192bb-133">Widening and Narrowing Conversions</span><span class="sxs-lookup"><span data-stu-id="192bb-133">Widening and Narrowing Conversions</span></span>](../data-types/widening-and-narrowing-conversions.md)
- [<span data-ttu-id="192bb-134">Delegaten</span><span class="sxs-lookup"><span data-stu-id="192bb-134">Delegates</span></span>](index.md)
- [<span data-ttu-id="192bb-135">Gewusst wie: Übergeben von Prozeduren an eine andere Prozedur in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="192bb-135">How to: Pass Procedures to Another Procedure in Visual Basic</span></span>](how-to-pass-procedures-to-another-procedure.md)
- [<span data-ttu-id="192bb-136">Lokaler Typrückschluss</span><span class="sxs-lookup"><span data-stu-id="192bb-136">Local Type Inference</span></span>](../variables/local-type-inference.md)
- [<span data-ttu-id="192bb-137">Option Strict-Anweisung</span><span class="sxs-lookup"><span data-stu-id="192bb-137">Option Strict Statement</span></span>](../../../language-reference/statements/option-strict-statement.md)
