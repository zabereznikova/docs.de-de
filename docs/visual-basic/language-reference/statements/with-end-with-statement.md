---
title: With...End With-Anweisung
ms.date: 07/20/2015
f1_keywords:
- vb.With
helpviewer_keywords:
- With keyword [Visual Basic]
- loop structures [Visual Basic], and With...End With statements
- execution [Visual Basic], on object
- instructions, repeating
- With...End With statements [Visual Basic]
- With statement [Visual Basic]
- With statement [Visual Basic], nesting
- objects [Visual Basic], accessing
- With block
- End keyword [Visual Basic], With...End With statements
ms.assetid: 340d5fbb-4f43-48ec-a024-80843c137817
ms.openlocfilehash: eb8790d0d8f82232a4b10e4e0e30165745c065c0
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352736"
---
# <a name="withend-with-statement-visual-basic"></a><span data-ttu-id="150d6-102">With...End With-Anweisung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="150d6-102">With...End With Statement (Visual Basic)</span></span>

<span data-ttu-id="150d6-103">Führt eine Reihe von Anweisungen aus, die wiederholt auf ein einzelnes Objekt oder eine einzelne Struktur verweisen, sodass die Anweisungen mittels vereinfachter Syntax auf Member des Objekts oder der Struktur zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="150d6-103">Executes a series of statements that repeatedly refer to a single object or structure so that the statements can use a simplified syntax when accessing members of the object or structure.</span></span>  <span data-ttu-id="150d6-104">Wenn Sie eine Struktur verwenden, können Sie nur die Werte von Membern lesen oder Methoden aufrufen; Sie erhalten eine Fehlermeldung, wenn Sie versuchen, Werte zu Membern einer Struktur zuzuweisen, die in einer `With...End With`-Anweisung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="150d6-104">When using a structure, you can only read the values of members or invoke methods, and you get an error if you try to assign values to members of a structure used in a `With...End With` statement.</span></span>

## <a name="syntax"></a><span data-ttu-id="150d6-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="150d6-105">Syntax</span></span>

```vb
With objectExpression
    [ statements ]
End With
```

## <a name="parts"></a><span data-ttu-id="150d6-106">-Komponenten</span><span class="sxs-lookup"><span data-stu-id="150d6-106">Parts</span></span>

|<span data-ttu-id="150d6-107">Begriff</span><span class="sxs-lookup"><span data-stu-id="150d6-107">Term</span></span>|<span data-ttu-id="150d6-108">Definition</span><span class="sxs-lookup"><span data-stu-id="150d6-108">Definition</span></span>|
|---|---|
|`objectExpression`|<span data-ttu-id="150d6-109">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="150d6-109">Required.</span></span> <span data-ttu-id="150d6-110">Ein Ausdruck, der zu einem Objekt ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="150d6-110">An expression that evaluates to an object.</span></span> <span data-ttu-id="150d6-111">Der Ausdruck kann von beliebiger Komplexität sein und wird nur einmal ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="150d6-111">The expression may be arbitrarily complex and is evaluated only once.</span></span> <span data-ttu-id="150d6-112">Der Ausdruck kann einen beliebigen Datentyp ergeben, u. a. auch einen elementaren Datentyp.</span><span class="sxs-lookup"><span data-stu-id="150d6-112">The expression can evaluate to any data type, including elementary types.</span></span>|
|`statements`|<span data-ttu-id="150d6-113">Optional.</span><span class="sxs-lookup"><span data-stu-id="150d6-113">Optional.</span></span> <span data-ttu-id="150d6-114">Eine oder mehrere Anweisungen zwischen `With` und `End With`, die auf Member eines Objekts verweisen können, das durch die Auswertung von `objectExpression` erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="150d6-114">One or more statements between `With` and `End With` that may refer to members of an object that's produced by the evaluation of `objectExpression`.</span></span>|
|`End With`|<span data-ttu-id="150d6-115">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="150d6-115">Required.</span></span> <span data-ttu-id="150d6-116">Beendet die Definition des `With`-Blocks.</span><span class="sxs-lookup"><span data-stu-id="150d6-116">Terminates the definition of the `With` block.</span></span>|

## <a name="remarks"></a><span data-ttu-id="150d6-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="150d6-117">Remarks</span></span>

<span data-ttu-id="150d6-118">Bei Verwendung von `With...End With` können Sie eine Reihe von Anweisungen für ein angegebenes Objekt ausführen, ohne den Namen des Objekts mehrmals angeben zu müssen.</span><span class="sxs-lookup"><span data-stu-id="150d6-118">By using `With...End With`, you can perform a series of statements on a specified object without specifying the name of the object multiple times.</span></span> <span data-ttu-id="150d6-119">Innerhalb eines `With`-Anweisungsblocks können Sie bei der Angabe eines Member des Objekts mit einem Punkt beginnen, als ob das `With`-Anweisungsobjekt dem Member vorausgehen würde.</span><span class="sxs-lookup"><span data-stu-id="150d6-119">Within a `With` statement block, you can specify a member of the object starting with a period, as if the `With` statement object preceded it.</span></span>

<span data-ttu-id="150d6-120">Wenn Sie beispielsweise mehrere verschiedene Eigenschaften eines einzelnen Objekts ändern möchten, fügen Sie die Anweisungen für die Eigenschaftenzuweisungen in den `With...End With`-Block ein. Sie müssen dann nicht in jeder Eigenschaftenzuweisung auf das Objekt verweisen, sondern es genügt ein einziger Verweis auf das Objekt.</span><span class="sxs-lookup"><span data-stu-id="150d6-120">For example, to change multiple properties on a single object, place the property assignment statements inside the `With...End With` block, referring to the object only once instead of once for each property assignment.</span></span>

<span data-ttu-id="150d6-121">Wenn der Code auf dasselbe Objekt in mehreren Anweisungen zugreift, bietet die `With`-Anweisung folgende Vorteile:</span><span class="sxs-lookup"><span data-stu-id="150d6-121">If your code accesses the same object in multiple statements, you gain the following benefits by using the `With` statement:</span></span>

- <span data-ttu-id="150d6-122">Sie müssen einen komplexen Ausdruck nicht mehrmals auswerten oder das Ergebnis einer temporären Variablen zuweisen, auch wenn Sie mehrmals auf die Member des Ausdrucks verweisen möchten.</span><span class="sxs-lookup"><span data-stu-id="150d6-122">You don't need to evaluate a complex expression multiple times or assign the result to a temporary variable to refer to its members multiple times.</span></span>

- <span data-ttu-id="150d6-123">Der Code wird lesbarer, da wiederkehrende qualifizierende Ausdrücke vermieden werden.</span><span class="sxs-lookup"><span data-stu-id="150d6-123">You make your code more readable by eliminating repetitive qualifying expressions.</span></span>

<span data-ttu-id="150d6-124">Der Datentyp `objectExpression` kann ein beliebiger Klassen- oder Strukturtyp und sogar ein elementarer Visual Basic-Typ sein, z. B. `Integer`.</span><span class="sxs-lookup"><span data-stu-id="150d6-124">The data type of `objectExpression` can be any class or structure type or even a Visual Basic elementary type such as `Integer`.</span></span>  <span data-ttu-id="150d6-125">Wenn `objectExpression` kein Objekt liefert, können Sie nur die Werte der Member lesen oder Methoden aufrufen; Sie erhalten eine Fehlermeldung, wenn Sie versuchen, Werte zu Membern einer Struktur zuzuweisen, die in einer `With...End With`-Anweisung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="150d6-125">If `objectExpression` results in anything other than an object, you can only read the values of its members or invoke methods, and you get an error if you try to assign values to members of a structure used in a `With...End With` statement.</span></span>  <span data-ttu-id="150d6-126">Denselben Fehler würden Sie erhalten, wenn Sie eine Methode aufrufen, die eine Struktur zurückgegeben hat und unmittelbar auf einen Wert zugreifen und diesen einem Member des Funktionsergebnisses zuweisen, z. B. `GetAPoint().x = 1`.</span><span class="sxs-lookup"><span data-stu-id="150d6-126">This is the same error you would get if you invoked a method that returned a structure and immediately accessed and assigned a value to a member of the function’s result, such as `GetAPoint().x = 1`.</span></span>  <span data-ttu-id="150d6-127">Das Problem in beiden Fällen besteht darin, dass die Struktur nur in der Aufrufliste vorhanden ist und es in solchen Fällen keine Möglichkeit für einen Member einer geänderten Struktur gibt, Daten so an eine Position zu schreiben, dass die Änderung durch anderen Code im Programm berücksichtigt werden kann.</span><span class="sxs-lookup"><span data-stu-id="150d6-127">The problem in both cases is that the structure exists only on the call stack, and there is no way a modified structure member in these situations can write to  a location such that any other code in the program can observe the change.</span></span>

<span data-ttu-id="150d6-128">`objectExpression` wird nach Eintragung in den Block einmal ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="150d6-128">The `objectExpression` is evaluated once, upon entry into the block.</span></span> <span data-ttu-id="150d6-129">Es gibt keine Möglichkeit, `objectExpression` aus dem `With`-Block heraus neu zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="150d6-129">You can't reassign the `objectExpression` from within the `With` block.</span></span>

<span data-ttu-id="150d6-130">In einem `With`-Block können Sie nur auf die Methoden und Eigenschaften des angegebenen Objekts zugreifen, ohne sie zu qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="150d6-130">Within a `With` block, you can access the methods and properties of only the specified object without qualifying them.</span></span> <span data-ttu-id="150d6-131">Sie können zwar auch Methoden und Eigenschaften anderer Objekte verwenden, diese müssen Sie jedoch mit dem Objektnamen qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="150d6-131">You can use methods and properties of other objects, but you must qualify them with their object names.</span></span>

<span data-ttu-id="150d6-132">Sie können eine `With...End With`-Anweisung in eine andere einfügen.</span><span class="sxs-lookup"><span data-stu-id="150d6-132">You can place one `With...End With` statement within another.</span></span> <span data-ttu-id="150d6-133">Geschachtelte `With...End With`-Anweisungen sind möglicherweise unübersichtlich, wenn die Objekte, auf die verwiesen wird, aus dem Kontext heraus nicht nachvollziehbar sind.</span><span class="sxs-lookup"><span data-stu-id="150d6-133">Nested `With...End With` statements may be confusing if the objects that are being referred to aren't clear from context.</span></span> <span data-ttu-id="150d6-134">Sie müssen einen vollqualifizierten Verweis auf ein Objekt angeben, das sich in einem äußeren `With`-Block befindet, wenn aus einem inneren `With`-Block auf das Objekt verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="150d6-134">You must provide a fully qualified reference to an object that's in an outer `With` block when the object is referenced from within an inner `With` block.</span></span>

<span data-ttu-id="150d6-135">Sie können von außerhalb eines Blocks keine Verzweigung in einen `With`-Anweisungsblock vornehmen.</span><span class="sxs-lookup"><span data-stu-id="150d6-135">You can't branch into a `With` statement block from outside the block.</span></span>

<span data-ttu-id="150d6-136">Sofern der Block keine Schleife enthält, werden die Anweisungen nur einmal ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="150d6-136">Unless the block contains a loop, the statements run only once.</span></span> <span data-ttu-id="150d6-137">Sie können verschiedene Arten von Steuerungsstrukturen schachteln.</span><span class="sxs-lookup"><span data-stu-id="150d6-137">You can nest different kinds of control structures.</span></span> <span data-ttu-id="150d6-138">Weitere Informationen finden Sie unter [Struktur von Struktur Steuer](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)Elementen.</span><span class="sxs-lookup"><span data-stu-id="150d6-138">For more information, see [Nested Control Structures](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).</span></span>

> [!NOTE]
> <span data-ttu-id="150d6-139">Das `With`-Schlüsselwort kann auch in Objektinitialisierern verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="150d6-139">You can use the `With` keyword in object initializers also.</span></span> <span data-ttu-id="150d6-140">Weitere Informationen und Beispiele finden Sie unter [Objektinitialisierer: benannte und anonyme Typen](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md) und [Anonyme Typen](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="150d6-140">For more information and examples, see [Object Initializers: Named and Anonymous Types](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md) and [Anonymous Types](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span></span>
>
> <span data-ttu-id="150d6-141">Wenn Sie einen `With`-Block nur zum Initialisieren der Eigenschaften oder Felder eines soeben instanziierten Objekts verwenden, sollten Sie stattdessen einen Objektinitialisierer verwenden.</span><span class="sxs-lookup"><span data-stu-id="150d6-141">If you're using a `With` block only to initialize the properties or fields of an object that you've just instantiated, consider using an object initializer instead.</span></span>

## <a name="example"></a><span data-ttu-id="150d6-142">Beispiel</span><span class="sxs-lookup"><span data-stu-id="150d6-142">Example</span></span>

<span data-ttu-id="150d6-143">Im folgenden Beispiel führt jeder `With`-Block eine Reihe von Anweisungen für ein einzelnes Objekt aus.</span><span class="sxs-lookup"><span data-stu-id="150d6-143">In the following example, each `With` block executes a series of statements on a single object.</span></span>

[!code-vb[VbVbalrWithStatement#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrwithstatement/vb/mainwindow.xaml.vb#2)]

## <a name="example"></a><span data-ttu-id="150d6-144">Beispiel</span><span class="sxs-lookup"><span data-stu-id="150d6-144">Example</span></span>

<span data-ttu-id="150d6-145">Im folgenden Beispiel werden `With…End With`-Anweisungen geschachtelt.</span><span class="sxs-lookup"><span data-stu-id="150d6-145">The following example nests `With…End With` statements.</span></span> <span data-ttu-id="150d6-146">In der geschachtelten `With`-Anweisung verweist die Syntax auf das innere Objekt.</span><span class="sxs-lookup"><span data-stu-id="150d6-146">Within the nested `With` statement, the syntax refers to the inner object.</span></span>

[!code-vb[VbVbalrWithStatement#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvbalrwithstatement/vb/mainwindow.xaml.vb#1)]

## <a name="see-also"></a><span data-ttu-id="150d6-147">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="150d6-147">See also</span></span>

- <xref:System.Collections.Generic.List%601>
- [<span data-ttu-id="150d6-148">Geschachtelte Steuerungsstrukturen</span><span class="sxs-lookup"><span data-stu-id="150d6-148">Nested Control Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [<span data-ttu-id="150d6-149">Objektinitialisierer: Benannte und anonyme Typen</span><span class="sxs-lookup"><span data-stu-id="150d6-149">Object Initializers: Named and Anonymous Types</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [<span data-ttu-id="150d6-150">Anonyme Typen</span><span class="sxs-lookup"><span data-stu-id="150d6-150">Anonymous Types</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
