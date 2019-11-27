---
title: Lokaler Typrückschluss
ms.date: 07/20/2015
f1_keywords:
- local type inference
- vb.TypeInfer
helpviewer_keywords:
- Option Infer statement [Visual Basic]
- local type inference [Visual Basic]
- implicitly-typed local variables [Visual Basic]
- variables [Visual Basic], type inference
- inference [Visual Basic]
- type inference [Visual Basic]
ms.assetid: b8307f18-2e56-4ab3-a45a-826873f400f6
ms.openlocfilehash: f79ac70aecb5805a3a4a4fea8f7e7ccd3f8243fc
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351837"
---
# <a name="local-type-inference-visual-basic"></a><span data-ttu-id="263a0-102">Lokaler Typrückschluss (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="263a0-102">Local Type Inference (Visual Basic)</span></span>

<span data-ttu-id="263a0-103">Der Visual Basic-Compiler verwendet den *Typrückschluss* , um die Datentypen von lokalen Variablen zu bestimmen, die ohne `As`-Klausel deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="263a0-103">The Visual Basic compiler uses *type inference* to determine the data types of local variables declared without an `As` clause.</span></span> <span data-ttu-id="263a0-104">Der Compiler leitet den Typ der Variablen vom Typ des Initialisierungs Ausdrucks ab.</span><span class="sxs-lookup"><span data-stu-id="263a0-104">The compiler infers the type of the variable from the type of the initialization expression.</span></span> <span data-ttu-id="263a0-105">Dadurch können Sie Variablen deklarieren, ohne explizit einen Typ anzugeben, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="263a0-105">This enables you to declare variables without explicitly stating a type, as shown in the following example.</span></span> <span data-ttu-id="263a0-106">Aufgrund der Deklarationen werden sowohl `num1` als auch `num2` stark als ganze Zahlen typisiert.</span><span class="sxs-lookup"><span data-stu-id="263a0-106">As a result of the declarations, both `num1` and `num2` are strongly typed as integers.</span></span>

[!code-vb[VbVbalrTypeInference#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#1)]

> [!NOTE]
> <span data-ttu-id="263a0-107">Wenn Sie `num2` im vorherigen Beispiel nicht als `Integer`typisieren möchten, können Sie einen anderen Typ mithilfe einer Deklaration wie `Dim num3 As Object = 3` oder `Dim num4 As Double = 3`angeben.</span><span class="sxs-lookup"><span data-stu-id="263a0-107">If you do not want `num2` in the previous example to be typed as an `Integer`, you can specify another type by using a declaration like `Dim num3 As Object = 3` or `Dim num4 As Double = 3`.</span></span>

> [!NOTE]
> <span data-ttu-id="263a0-108">Der Typrückschluss kann nur für nicht statische lokale Variablen verwendet werden. Sie kann nicht verwendet werden, um den Typ der Klassen Felder, Eigenschaften oder Funktionen zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="263a0-108">Type inference can be used only for non-static local variables; it cannot be used to determine the type of class fields, properties, or functions.</span></span>

<span data-ttu-id="263a0-109">Der lokale Typrückschluss gilt für die Prozedur Ebene.</span><span class="sxs-lookup"><span data-stu-id="263a0-109">Local type inference applies at procedure level.</span></span> <span data-ttu-id="263a0-110">Sie kann nicht zum Deklarieren von Variablen auf Modulebene verwendet werden (innerhalb einer Klasse, Struktur, eines Moduls oder einer Schnittstelle, aber nicht innerhalb einer Prozedur oder eines Blocks).</span><span class="sxs-lookup"><span data-stu-id="263a0-110">It cannot be used to declare variables at module level (within a class, structure, module, or interface but not within a procedure or block).</span></span> <span data-ttu-id="263a0-111">Wenn `num2` im vorherigen Beispiel ein Feld einer Klasse anstelle einer lokalen Variablen in einer Prozedur wäre, würde die Deklaration einen Fehler bei `Option Strict` auf verursachen und `num2` als `Object` mit `Option Strict` aus klassifizieren.</span><span class="sxs-lookup"><span data-stu-id="263a0-111">If `num2` in the previous example were a field of a class instead of a local variable in a procedure, the declaration would cause an error with `Option Strict` on, and would classify `num2` as an `Object` with `Option Strict` off.</span></span> <span data-ttu-id="263a0-112">Ebenso gilt der lokale Typrückschluss nicht für Variablen auf Prozedur Ebene, die als `Static`deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="263a0-112">Similarly, local type inference does not apply to procedure level variables declared as `Static`.</span></span>

## <a name="type-inference-vs-late-binding"></a><span data-ttu-id="263a0-113">Typrückschluss und späte Bindung</span><span class="sxs-lookup"><span data-stu-id="263a0-113">Type Inference vs. Late Binding</span></span>

<span data-ttu-id="263a0-114">Code, der den Typrückschluss verwendet, ähnelt dem Code, der die späte Bindung verwendet.</span><span class="sxs-lookup"><span data-stu-id="263a0-114">Code that uses type inference resembles code that relies on late binding.</span></span> <span data-ttu-id="263a0-115">Der Typrückschluss gibt jedoch die Variable stark aus, anstatt Sie als `Object`zu belassen.</span><span class="sxs-lookup"><span data-stu-id="263a0-115">However, type inference strongly types the variable instead of leaving it as `Object`.</span></span> <span data-ttu-id="263a0-116">Der Compiler verwendet den Initialisierer einer Variablen, um den Typ der Variable zur Kompilierzeit zu bestimmen, um früh gebundenen Code zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="263a0-116">The compiler uses a variable's initializer to determine the variable's type at compile time to produce early-bound code.</span></span> <span data-ttu-id="263a0-117">Im vorherigen Beispiel wird `num2`, wie `num1`, als `Integer`typisiert.</span><span class="sxs-lookup"><span data-stu-id="263a0-117">In the previous example, `num2`, like `num1`, is typed as an `Integer`.</span></span>

<span data-ttu-id="263a0-118">Das Verhalten früh gebundener Variablen unterscheidet sich von der von spät gebundenen Variablen, für die der Typ nur zur Laufzeit bekannt ist.</span><span class="sxs-lookup"><span data-stu-id="263a0-118">The behavior of early-bound variables differs from that of late-bound variables, for which the type is known only at run time.</span></span> <span data-ttu-id="263a0-119">Wenn Sie den Typ früh wissen, kann der Compiler Probleme vor der Ausführung erkennen, Speicher exakt zuordnen und andere Optimierungen durchführen.</span><span class="sxs-lookup"><span data-stu-id="263a0-119">Knowing the type early enables the compiler to identify problems before execution, allocate memory precisely, and perform other optimizations.</span></span> <span data-ttu-id="263a0-120">Die frühe Bindung ermöglicht außerdem der Visual Basic integrierten Entwicklungsumgebung (Integrated Development Environment, IDE), IntelliSense-Hilfe zu den Membern eines Objekts bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="263a0-120">Early binding also enables the Visual Basic integrated development environment (IDE) to provide IntelliSense Help about the members of an object.</span></span> <span data-ttu-id="263a0-121">Die frühe Bindung wird auch für die Leistung bevorzugt.</span><span class="sxs-lookup"><span data-stu-id="263a0-121">Early binding is also preferred for performance.</span></span> <span data-ttu-id="263a0-122">Dies liegt daran, dass alle in einer spät gebundenen Variablen gespeicherten Daten als Typ `Object`umschließt werden müssen und der Zugriff auf Member des Typs zur Laufzeit das Programm verlangsamt.</span><span class="sxs-lookup"><span data-stu-id="263a0-122">This is because all data stored in a late-bound variable must be wrapped as type `Object`, and accessing members of the type at run time makes the program slower.</span></span>

## <a name="examples"></a><span data-ttu-id="263a0-123">Beispiele</span><span class="sxs-lookup"><span data-stu-id="263a0-123">Examples</span></span>

<span data-ttu-id="263a0-124">Der Typrückschluss tritt auf, wenn eine lokale Variable ohne eine `As`-Klausel deklariert und initialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="263a0-124">Type inference occurs when a local variable is declared without an `As` clause and initialized.</span></span> <span data-ttu-id="263a0-125">Der Compiler verwendet den Typ des zugewiesenen anfangs Werts als Typ der Variablen.</span><span class="sxs-lookup"><span data-stu-id="263a0-125">The compiler uses the type of the assigned initial value as the type of the variable.</span></span> <span data-ttu-id="263a0-126">Jede der folgenden Codezeilen deklariert z. b. eine Variable vom Typ `String`.</span><span class="sxs-lookup"><span data-stu-id="263a0-126">For example, each of the following lines of code declares a variable of type `String`.</span></span>

[!code-vb[VbVbalrTypeInference#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#2)]

<span data-ttu-id="263a0-127">Der folgende Code veranschaulicht zwei äquivalente Möglichkeiten, ein Array von ganzen Zahlen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="263a0-127">The following code demonstrates two equivalent ways to create an array of integers.</span></span>

[!code-vb[VbVbalrTypeInference#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#3)]

<span data-ttu-id="263a0-128">Es ist praktisch, mit dem Typrückschluss den Typ einer Schleifen Steuerungsvariablen zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="263a0-128">It is convenient to use type inference to determine the type of a loop control variable.</span></span> <span data-ttu-id="263a0-129">Im folgenden Code geht der Compiler davon aus, dass `number` ein `Integer` ist, da `someNumbers2` aus dem vorherigen Beispiel ein Array aus ganzen Zahlen ist.</span><span class="sxs-lookup"><span data-stu-id="263a0-129">In the following code, the compiler infers that `number` is an `Integer` because `someNumbers2` from the previous example is an array of integers.</span></span>

[!code-vb[VbVbalrTypeInference#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#4)]

<span data-ttu-id="263a0-130">Der lokale Typrückschluss kann in `Using`-Anweisungen verwendet werden, um den Typ des Ressourcen namensfest zulegen, wie im folgenden Beispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="263a0-130">Local type inference can be used in `Using` statements to establish the type of the resource name, as the following example demonstrates.</span></span>

[!code-vb[VbVbalrTypeInference#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#7)]

<span data-ttu-id="263a0-131">Der Typ einer Variablen kann auch von den Rückgabe Werten von Functions abgeleitet werden, wie im folgenden Beispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="263a0-131">The type of a variable can also be inferred from the return values of functions, as the following example demonstrates.</span></span> <span data-ttu-id="263a0-132">Sowohl `pList1` als auch `pList2` sind Arrays von Prozessen, da `Process.GetProcesses` ein Array von Prozessen zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="263a0-132">Both `pList1` and `pList2` are arrays of processes because `Process.GetProcesses` returns an array of processes.</span></span>

[!code-vb[VbVbalrTypeInference#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#5)]

## <a name="option-infer"></a><span data-ttu-id="263a0-133">Option Infer</span><span class="sxs-lookup"><span data-stu-id="263a0-133">Option Infer</span></span>

<span data-ttu-id="263a0-134">mithilfe `Option Infer` können Sie angeben, ob der lokale Typrückschluss in einer bestimmten Datei zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="263a0-134">`Option Infer` enables you specify whether local type inference is allowed in a particular file.</span></span> <span data-ttu-id="263a0-135">Wenn Sie oder zum Blockieren der Option aktivieren möchten, geben Sie eine der folgenden Anweisungen am Anfang der Datei ein.</span><span class="sxs-lookup"><span data-stu-id="263a0-135">To enable or to block the option, type one of the following statements at the start of the file.</span></span>

`Option Infer On`

`Option Infer Off`

<span data-ttu-id="263a0-136">Wenn Sie keinen Wert für `Option Infer` im Code angeben, wird der Compilerstandard `Option Infer On`.</span><span class="sxs-lookup"><span data-stu-id="263a0-136">If you do not specify a value for `Option Infer` in your code, the compiler default is `Option Infer On`.</span></span>

<span data-ttu-id="263a0-137">Wenn der in einer Datei für `Option Infer` festgelegte Wert mit dem in der IDE oder in der Befehlszeile festgelegten Wert im Konflikt steht, hat der Wert in der Datei Vorrang.</span><span class="sxs-lookup"><span data-stu-id="263a0-137">If the value set for `Option Infer` in a file conflicts with the value set in the IDE or on the command line, the value in the file has precedence.</span></span>

<span data-ttu-id="263a0-138">Weitere Informationen finden Sie unter [Option Infer-Anweisung](../../../../visual-basic/language-reference/statements/option-infer-statement.md) und [Kompilierungs Seite, Projekt-Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="263a0-138">For more information, see [Option Infer Statement](../../../../visual-basic/language-reference/statements/option-infer-statement.md) and [Compile Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic).</span></span>

## <a name="see-also"></a><span data-ttu-id="263a0-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="263a0-139">See also</span></span>

- [<span data-ttu-id="263a0-140">Anonyme Typen</span><span class="sxs-lookup"><span data-stu-id="263a0-140">Anonymous Types</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
- [<span data-ttu-id="263a0-141">Frühes und spätes Binden</span><span class="sxs-lookup"><span data-stu-id="263a0-141">Early and Late Binding</span></span>](../../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)
- [<span data-ttu-id="263a0-142">For Each...Next-Anweisung</span><span class="sxs-lookup"><span data-stu-id="263a0-142">For Each...Next Statement</span></span>](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)
- [<span data-ttu-id="263a0-143">For...Next-Anweisung</span><span class="sxs-lookup"><span data-stu-id="263a0-143">For...Next Statement</span></span>](../../../../visual-basic/language-reference/statements/for-next-statement.md)
- [<span data-ttu-id="263a0-144">Option Infer-Anweisung</span><span class="sxs-lookup"><span data-stu-id="263a0-144">Option Infer Statement</span></span>](../../../../visual-basic/language-reference/statements/option-infer-statement.md)
- [<span data-ttu-id="263a0-145">-optioninfer</span><span class="sxs-lookup"><span data-stu-id="263a0-145">-optioninfer</span></span>](../../../../visual-basic/reference/command-line-compiler/optioninfer.md)
- [<span data-ttu-id="263a0-146">Einführung in LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="263a0-146">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
