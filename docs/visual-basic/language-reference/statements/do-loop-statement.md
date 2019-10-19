---
title: Do...Loop-Anweisung (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Do
- vb.Loop
- vb.Until
helpviewer_keywords:
- conditional statements [Visual Basic], Do�Loop
- while statement [Visual Basic], Do...Loop
- execution [Visual Basic], conditional
- Do loops
- Until keyword [Visual Basic], Do...Loop statement
- Do...Loop statement
- instructions, repeating
- Do statement [Visual Basic]
- Exit statement [Visual Basic], in Do...Loop statements
- loop structures [Visual Basic], Do�Loop statements
- do-while statements [Visual Basic]
- loops, exiting
- Loop keyword [Visual Basic], Do...Loop statement
ms.assetid: 892f9096-b3e2-4aee-834d-83bc4e2c379d
ms.openlocfilehash: eff5239e07ca27f40ece5af68f46c491be91cf09
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2019
ms.locfileid: "72583442"
---
# <a name="doloop-statement-visual-basic"></a><span data-ttu-id="c758d-102">Do...Loop-Anweisung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c758d-102">Do...Loop Statement (Visual Basic)</span></span>
<span data-ttu-id="c758d-103">Wiederholt einen Anweisungsblock, während eine `Boolean` Bedingung `True` ist oder bis die Bedingung `True` wird.</span><span class="sxs-lookup"><span data-stu-id="c758d-103">Repeats a block of statements while a `Boolean` condition is `True` or until the condition becomes `True`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c758d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c758d-104">Syntax</span></span>  
  
```vb  
Do { While | Until } condition  
    [ statements ]  
    [ Continue Do ]  
    [ statements ]  
    [ Exit Do ]  
    [ statements ]  
Loop  
' -or-  
Do  
    [ statements ]  
    [ Continue Do ]  
    [ statements ]  
    [ Exit Do ]  
    [ statements ]  
Loop { While | Until } condition  
```  
  
## <a name="parts"></a><span data-ttu-id="c758d-105">Teile</span><span class="sxs-lookup"><span data-stu-id="c758d-105">Parts</span></span>  
  
|<span data-ttu-id="c758d-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="c758d-106">Term</span></span>|<span data-ttu-id="c758d-107">Definition</span><span class="sxs-lookup"><span data-stu-id="c758d-107">Definition</span></span>|  
|---|---|  
|`Do`|<span data-ttu-id="c758d-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="c758d-108">Required.</span></span> <span data-ttu-id="c758d-109">Startet die Definition der `Do` Schleife.</span><span class="sxs-lookup"><span data-stu-id="c758d-109">Starts the definition of the `Do` loop.</span></span>|  
|`While`|<span data-ttu-id="c758d-110">Erforderlich, außer wenn `Until` verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c758d-110">Required unless `Until` is used.</span></span> <span data-ttu-id="c758d-111">Wiederholen Sie die Schleife, bis `condition` `False` ist.</span><span class="sxs-lookup"><span data-stu-id="c758d-111">Repeat the loop until `condition` is `False`.</span></span>|  
|`Until`|<span data-ttu-id="c758d-112">Erforderlich, außer wenn `While` verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c758d-112">Required unless `While` is used.</span></span> <span data-ttu-id="c758d-113">Wiederholen Sie die Schleife, bis `condition` `True` ist.</span><span class="sxs-lookup"><span data-stu-id="c758d-113">Repeat the loop until `condition` is `True`.</span></span>|  
|`condition`|<span data-ttu-id="c758d-114">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="c758d-114">Optional.</span></span> <span data-ttu-id="c758d-115">`Boolean` Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="c758d-115">`Boolean` expression.</span></span> <span data-ttu-id="c758d-116">Wenn `condition` `Nothing` ist, wird es von Visual Basic als `False` behandelt.</span><span class="sxs-lookup"><span data-stu-id="c758d-116">If `condition` is `Nothing`, Visual Basic treats it as `False`.</span></span>|  
|`statements`|<span data-ttu-id="c758d-117">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="c758d-117">Optional.</span></span> <span data-ttu-id="c758d-118">Eine oder mehrere-Anweisungen, die wiederholt werden, während oder bis `condition` sind `True`.</span><span class="sxs-lookup"><span data-stu-id="c758d-118">One or more statements that are repeated while, or until, `condition` is `True`.</span></span>|  
|`Continue Do`|<span data-ttu-id="c758d-119">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="c758d-119">Optional.</span></span> <span data-ttu-id="c758d-120">Überträgt die Steuerung an die nächste Iterations `Do` Schleife.</span><span class="sxs-lookup"><span data-stu-id="c758d-120">Transfers control to the next iteration of the `Do` loop.</span></span>|  
|`Exit Do`|<span data-ttu-id="c758d-121">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="c758d-121">Optional.</span></span> <span data-ttu-id="c758d-122">Überträgt die Steuerung aus der `Do` Schleife.</span><span class="sxs-lookup"><span data-stu-id="c758d-122">Transfers control out of the `Do` loop.</span></span>|  
|`Loop`|<span data-ttu-id="c758d-123">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="c758d-123">Required.</span></span> <span data-ttu-id="c758d-124">Beendet die Definition der `Do` Schleife.</span><span class="sxs-lookup"><span data-stu-id="c758d-124">Terminates the definition of the `Do` loop.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c758d-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c758d-125">Remarks</span></span>  
 <span data-ttu-id="c758d-126">Verwenden Sie eine `Do...Loop` Struktur, wenn Sie eine Reihe von Anweisungen beliebig oft wiederholen möchten, bis eine Bedingung erfüllt ist.</span><span class="sxs-lookup"><span data-stu-id="c758d-126">Use a `Do...Loop` structure when you want to repeat a set of statements an indefinite number of times, until a condition is satisfied.</span></span> <span data-ttu-id="c758d-127">Wenn Sie die-Anweisungen in einer festgelegten Anzahl von Wiederholungen wiederholen möchten, wird [für... Die nächste Anweisung](../../../visual-basic/language-reference/statements/for-next-statement.md) ist in der Regel eine bessere Wahl.</span><span class="sxs-lookup"><span data-stu-id="c758d-127">If you want to repeat the statements a set number of times, the [For...Next Statement](../../../visual-basic/language-reference/statements/for-next-statement.md) is usually a better choice.</span></span>  
  
 <span data-ttu-id="c758d-128">Sie können entweder `While` oder `Until` verwenden, um `condition` anzugeben, aber nicht beides.</span><span class="sxs-lookup"><span data-stu-id="c758d-128">You can use either `While` or `Until` to specify `condition`, but not both.</span></span>  
  
 <span data-ttu-id="c758d-129">Sie können `condition` nur einmal entweder am Anfang oder am Ende der Schleife testen.</span><span class="sxs-lookup"><span data-stu-id="c758d-129">You can test `condition` only one time, at either the start or the end of the loop.</span></span> <span data-ttu-id="c758d-130">Wenn Sie `condition` am Anfang der Schleife testen (in der `Do`-Anweisung), wird die Schleife möglicherweise nicht einmal ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="c758d-130">If you test `condition` at the start of the loop (in the `Do` statement), the loop might not run even one time.</span></span> <span data-ttu-id="c758d-131">Wenn Sie am Ende der Schleife testen (in der `Loop`-Anweisung), wird die Schleife immer mindestens einmal ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="c758d-131">If you test at the end of the loop (in the `Loop` statement), the loop always runs at least one time.</span></span>  
  
 <span data-ttu-id="c758d-132">Die Bedingung ergibt in der Regel einen Vergleich zweier Werte, kann jedoch ein beliebiger Ausdruck sein, der zu einem [booleschen Datentyp](../../../visual-basic/language-reference/data-types/boolean-data-type.md) Wert (`True` oder `False`) ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="c758d-132">The condition usually results from a comparison of two values, but it can be any expression that evaluates to a [Boolean Data Type](../../../visual-basic/language-reference/data-types/boolean-data-type.md) value (`True` or `False`).</span></span> <span data-ttu-id="c758d-133">Dies umfasst auch Werte anderer Datentypen, z. b. numerischer Typen, die in `Boolean` konvertiert wurden.</span><span class="sxs-lookup"><span data-stu-id="c758d-133">This includes values of other data types, such as numeric types, that have been converted to `Boolean`.</span></span>  
  
 <span data-ttu-id="c758d-134">Sie können `Do` Schleifen schachteln, indem Sie eine Schleife in eine andere einfügen.</span><span class="sxs-lookup"><span data-stu-id="c758d-134">You can nest `Do` loops by putting one loop within another.</span></span> <span data-ttu-id="c758d-135">Sie können auch verschiedene Arten von Steuerungsstrukturen ineinander schachteln.</span><span class="sxs-lookup"><span data-stu-id="c758d-135">You can also nest different kinds of control structures within each other.</span></span> <span data-ttu-id="c758d-136">Weitere Informationen finden Sie unter [Struktur von Struktur Steuer](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)Elementen.</span><span class="sxs-lookup"><span data-stu-id="c758d-136">For more information, see [Nested Control Structures](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c758d-137">Die `Do...Loop` Struktur bietet mehr Flexibilität als die [Zeit... End While-Anweisung](../../../visual-basic/language-reference/statements/while-end-while-statement.md) , da Sie Ihnen ermöglicht, zu entscheiden, ob die Schleife beendet werden soll, wenn `condition` beendet `True` wird, oder wenn Sie zum ersten Mal `True` wird.</span><span class="sxs-lookup"><span data-stu-id="c758d-137">The `Do...Loop` structure gives you more flexibility than the [While...End While Statement](../../../visual-basic/language-reference/statements/while-end-while-statement.md) because it enables you to decide whether to end the loop when `condition` stops being `True` or when it first becomes `True`.</span></span> <span data-ttu-id="c758d-138">Außerdem können Sie `condition` entweder am Anfang oder am Ende der Schleife testen.</span><span class="sxs-lookup"><span data-stu-id="c758d-138">It also enables you to test `condition` at either the start or the end of the loop.</span></span>  
  
## <a name="exit-do"></a><span data-ttu-id="c758d-139">Beenden</span><span class="sxs-lookup"><span data-stu-id="c758d-139">Exit Do</span></span>  
 <span data-ttu-id="c758d-140">Die [Exit Do](../../../visual-basic/language-reference/statements/exit-statement.md) -Anweisung kann eine alternative Möglichkeit zum Beenden einer `Do…Loop` bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="c758d-140">The [Exit Do](../../../visual-basic/language-reference/statements/exit-statement.md) statement can provide an alternative way to exit a `Do…Loop`.</span></span> <span data-ttu-id="c758d-141">`Exit Do` überträgt die Steuerung sofort an die Anweisung, die auf die `Loop` Anweisung folgt.</span><span class="sxs-lookup"><span data-stu-id="c758d-141">`Exit Do` transfers control immediately to the statement that follows the `Loop` statement.</span></span>  
  
 <span data-ttu-id="c758d-142">`Exit Do` wird häufig verwendet, wenn eine bestimmte Bedingung ausgewertet wird, z. b. in einer `If...Then...Else` Struktur.</span><span class="sxs-lookup"><span data-stu-id="c758d-142">`Exit Do` is often used after some condition is evaluated, for example in an `If...Then...Else` structure.</span></span> <span data-ttu-id="c758d-143">Möglicherweise möchten Sie eine Schleife beenden, wenn Sie eine Bedingung erkennen, die es unnötig oder unmöglich macht, die Iteration fortzusetzen, z. b. einen fehlerhaften Wert oder eine Beendigungs Anforderung.</span><span class="sxs-lookup"><span data-stu-id="c758d-143">You might want to exit a loop if you detect a condition that makes it unnecessary or impossible to continue iterating, such as an erroneous value or a termination request.</span></span> <span data-ttu-id="c758d-144">Eine Verwendung von `Exit Do` besteht darin, auf eine Bedingung zu testen, die eine *Endlosschleife*verursachen könnte. Dies ist eine Schleife, die eine große oder sogar unendliche Anzahl von Zeiten ausführen kann.</span><span class="sxs-lookup"><span data-stu-id="c758d-144">One use of `Exit Do` is to test for a condition that could cause an *endless loop*, which is a loop that could run a large or even infinite number of times.</span></span> <span data-ttu-id="c758d-145">Mit `Exit Do` können Sie die Schleife mit Escapezeichen versehen.</span><span class="sxs-lookup"><span data-stu-id="c758d-145">You can use `Exit Do` to escape the loop.</span></span>  
  
 <span data-ttu-id="c758d-146">Sie können beliebig viele `Exit Do` Anweisungen in einem `Do…Loop` einschließen.</span><span class="sxs-lookup"><span data-stu-id="c758d-146">You can include any number of `Exit Do` statements anywhere in a `Do…Loop`.</span></span>  
  
 <span data-ttu-id="c758d-147">Wenn Sie in geschachtelten `Do` Schleifen verwendet wird, überträgt `Exit Do` die Steuerung aus der innersten Schleife und in die nächsthöhere Schachtelungs Ebene.</span><span class="sxs-lookup"><span data-stu-id="c758d-147">When used within nested `Do` loops, `Exit Do` transfers control out of the innermost loop and into the next higher level of nesting.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c758d-148">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c758d-148">Example</span></span>  
 <span data-ttu-id="c758d-149">Im folgenden Beispiel werden die Anweisungen in der-Schleife weiterhin ausgeführt, bis die `index`-Variable größer als 10 ist.</span><span class="sxs-lookup"><span data-stu-id="c758d-149">In the following example, the statements in the loop continue to run until the `index` variable is greater than 10.</span></span> <span data-ttu-id="c758d-150">Die `Until`-Klausel befindet sich am Ende der Schleife.</span><span class="sxs-lookup"><span data-stu-id="c758d-150">The `Until` clause is at the end of the loop.</span></span>  
  
 [!code-vb[VbVbalrStatements#131](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#131)]  
  
## <a name="example"></a><span data-ttu-id="c758d-151">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c758d-151">Example</span></span>  
 <span data-ttu-id="c758d-152">Im folgenden Beispiel wird anstelle einer `Until`-Klausel eine `While`-Klausel verwendet, und `condition` wird am Anfang der Schleife anstelle von am Ende getestet.</span><span class="sxs-lookup"><span data-stu-id="c758d-152">The following example uses a `While` clause instead of an `Until` clause, and `condition` is tested at the start of the loop instead of at the end.</span></span>  
  
 [!code-vb[VbVbalrStatements#132](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#132)]  
  
## <a name="example"></a><span data-ttu-id="c758d-153">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c758d-153">Example</span></span>  
 <span data-ttu-id="c758d-154">Im folgenden Beispiel beendet `condition` die Schleife, wenn die `index` Variable größer als 100 ist.</span><span class="sxs-lookup"><span data-stu-id="c758d-154">In the following example, `condition` stops the loop when the `index` variable is greater than 100.</span></span> <span data-ttu-id="c758d-155">Die `If` Anweisung in der Schleife bewirkt jedoch, dass die `Exit Do` Anweisung die Schleife beendet, wenn die Index Variable größer als 10 ist.</span><span class="sxs-lookup"><span data-stu-id="c758d-155">The `If` statement in the loop, however, causes the `Exit Do` statement to stop the loop when the index variable is greater than 10.</span></span>  
  
 [!code-vb[VbVbalrStatements#133](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#133)]  
  
## <a name="example"></a><span data-ttu-id="c758d-156">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c758d-156">Example</span></span>  
 <span data-ttu-id="c758d-157">Im folgenden Beispiel werden alle Zeilen in einer Textdatei gelesen.</span><span class="sxs-lookup"><span data-stu-id="c758d-157">The following example reads all lines in a text file.</span></span> <span data-ttu-id="c758d-158">Die <xref:System.IO.File.OpenText%2A>-Methode öffnet die Datei und gibt eine <xref:System.IO.StreamReader> zurück, die die Zeichen liest.</span><span class="sxs-lookup"><span data-stu-id="c758d-158">The <xref:System.IO.File.OpenText%2A> method opens the file and returns a <xref:System.IO.StreamReader> that reads the characters.</span></span> <span data-ttu-id="c758d-159">In der `Do...Loop` Bedingung bestimmt die <xref:System.IO.StreamReader.Peek%2A>-Methode des `StreamReader`, ob zusätzliche Zeichen vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="c758d-159">In the `Do...Loop` condition, the <xref:System.IO.StreamReader.Peek%2A> method of the `StreamReader` determines whether there are any additional characters.</span></span>  
  
 [!code-vb[VbVbalrStatements#134](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#134)]  
  
## <a name="see-also"></a><span data-ttu-id="c758d-160">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c758d-160">See also</span></span>

- [<span data-ttu-id="c758d-161">Schleifenstruktur</span><span class="sxs-lookup"><span data-stu-id="c758d-161">Loop Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [<span data-ttu-id="c758d-162">For...Next-Anweisung</span><span class="sxs-lookup"><span data-stu-id="c758d-162">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [<span data-ttu-id="c758d-163">Boolean-Datentyp</span><span class="sxs-lookup"><span data-stu-id="c758d-163">Boolean Data Type</span></span>](../../../visual-basic/language-reference/data-types/boolean-data-type.md)
- [<span data-ttu-id="c758d-164">Geschachtelte Steuerungsstrukturen</span><span class="sxs-lookup"><span data-stu-id="c758d-164">Nested Control Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [<span data-ttu-id="c758d-165">Exit-Anweisung</span><span class="sxs-lookup"><span data-stu-id="c758d-165">Exit Statement</span></span>](../../../visual-basic/language-reference/statements/exit-statement.md)
- [<span data-ttu-id="c758d-166">While...End While-Anweisung</span><span class="sxs-lookup"><span data-stu-id="c758d-166">While...End While Statement</span></span>](../../../visual-basic/language-reference/statements/while-end-while-statement.md)
