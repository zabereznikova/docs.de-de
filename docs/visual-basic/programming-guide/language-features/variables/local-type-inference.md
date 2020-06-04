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
ms.openlocfilehash: 3979396d32aa5d3b853aa087d43f70d5987e510b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410398"
---
# <a name="local-type-inference-visual-basic"></a><span data-ttu-id="b3d72-102">Lokaler Typrückschluss (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b3d72-102">Local Type Inference (Visual Basic)</span></span>

<span data-ttu-id="b3d72-103">Der Visual Basic-Compiler verwendet den *Typrückschluss* , um die Datentypen von lokalen Variablen zu bestimmen, die ohne-Klausel deklariert werden `As` .</span><span class="sxs-lookup"><span data-stu-id="b3d72-103">The Visual Basic compiler uses *type inference* to determine the data types of local variables declared without an `As` clause.</span></span> <span data-ttu-id="b3d72-104">Der Compiler leitet den Typ der Variablen vom Typ des Initialisierungs Ausdrucks ab.</span><span class="sxs-lookup"><span data-stu-id="b3d72-104">The compiler infers the type of the variable from the type of the initialization expression.</span></span> <span data-ttu-id="b3d72-105">Dadurch können Sie Variablen deklarieren, ohne explizit einen Typ anzugeben, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="b3d72-105">This enables you to declare variables without explicitly stating a type, as shown in the following example.</span></span> <span data-ttu-id="b3d72-106">Aufgrund der Deklarationen werden sowohl als `num1` auch `num2` als ganze Zahlen stark typisiert.</span><span class="sxs-lookup"><span data-stu-id="b3d72-106">As a result of the declarations, both `num1` and `num2` are strongly typed as integers.</span></span>

[!code-vb[VbVbalrTypeInference#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#1)]

> [!NOTE]
> <span data-ttu-id="b3d72-107">Wenn Sie `num2` im vorherigen Beispiel nicht als typisieren möchten `Integer` , können Sie einen anderen Typ mithilfe einer Deklaration wie `Dim num3 As Object = 3` oder angeben `Dim num4 As Double = 3` .</span><span class="sxs-lookup"><span data-stu-id="b3d72-107">If you do not want `num2` in the previous example to be typed as an `Integer`, you can specify another type by using a declaration like `Dim num3 As Object = 3` or `Dim num4 As Double = 3`.</span></span>

> [!NOTE]
> <span data-ttu-id="b3d72-108">Der Typrückschluss kann nur für nicht statische lokale Variablen verwendet werden. Sie kann nicht verwendet werden, um den Typ der Klassen Felder, Eigenschaften oder Funktionen zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="b3d72-108">Type inference can be used only for non-static local variables; it cannot be used to determine the type of class fields, properties, or functions.</span></span>

<span data-ttu-id="b3d72-109">Der lokale Typrückschluss gilt für die Prozedur Ebene.</span><span class="sxs-lookup"><span data-stu-id="b3d72-109">Local type inference applies at procedure level.</span></span> <span data-ttu-id="b3d72-110">Sie kann nicht zum Deklarieren von Variablen auf Modulebene verwendet werden (innerhalb einer Klasse, Struktur, eines Moduls oder einer Schnittstelle, aber nicht innerhalb einer Prozedur oder eines Blocks).</span><span class="sxs-lookup"><span data-stu-id="b3d72-110">It cannot be used to declare variables at module level (within a class, structure, module, or interface but not within a procedure or block).</span></span> <span data-ttu-id="b3d72-111">Wenn `num2` im vorherigen Beispiel ein Feld einer Klasse statt einer lokalen Variablen in einer Prozedur wäre, würde die Deklaration einen Fehler mit `Option Strict` on verursachen und `num2` als `Object` mit Off klassifiziert werden `Option Strict` .</span><span class="sxs-lookup"><span data-stu-id="b3d72-111">If `num2` in the previous example were a field of a class instead of a local variable in a procedure, the declaration would cause an error with `Option Strict` on, and would classify `num2` as an `Object` with `Option Strict` off.</span></span> <span data-ttu-id="b3d72-112">Ebenso gilt der lokale Typrückschluss nicht für Variablen auf Prozedur Ebene, die als deklariert wurden `Static` .</span><span class="sxs-lookup"><span data-stu-id="b3d72-112">Similarly, local type inference does not apply to procedure level variables declared as `Static`.</span></span>

## <a name="type-inference-vs-late-binding"></a><span data-ttu-id="b3d72-113">Typrückschluss und späte Bindung</span><span class="sxs-lookup"><span data-stu-id="b3d72-113">Type Inference vs. Late Binding</span></span>

<span data-ttu-id="b3d72-114">Code, der den Typrückschluss verwendet, ähnelt dem Code, der die späte Bindung verwendet.</span><span class="sxs-lookup"><span data-stu-id="b3d72-114">Code that uses type inference resembles code that relies on late binding.</span></span> <span data-ttu-id="b3d72-115">Der Typrückschluss gibt jedoch die Variable stark ein, anstatt Sie als zu belassen `Object` .</span><span class="sxs-lookup"><span data-stu-id="b3d72-115">However, type inference strongly types the variable instead of leaving it as `Object`.</span></span> <span data-ttu-id="b3d72-116">Der Compiler verwendet den Initialisierer einer Variablen, um den Typ der Variable zur Kompilierzeit zu bestimmen, um früh gebundenen Code zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="b3d72-116">The compiler uses a variable's initializer to determine the variable's type at compile time to produce early-bound code.</span></span> <span data-ttu-id="b3d72-117">Im vorherigen Beispiel wird, `num2` wie, `num1` als typisiert `Integer` .</span><span class="sxs-lookup"><span data-stu-id="b3d72-117">In the previous example, `num2`, like `num1`, is typed as an `Integer`.</span></span>

<span data-ttu-id="b3d72-118">Das Verhalten früh gebundener Variablen unterscheidet sich von der von spät gebundenen Variablen, für die der Typ nur zur Laufzeit bekannt ist.</span><span class="sxs-lookup"><span data-stu-id="b3d72-118">The behavior of early-bound variables differs from that of late-bound variables, for which the type is known only at run time.</span></span> <span data-ttu-id="b3d72-119">Wenn Sie den Typ früh wissen, kann der Compiler Probleme vor der Ausführung erkennen, Speicher exakt zuordnen und andere Optimierungen durchführen.</span><span class="sxs-lookup"><span data-stu-id="b3d72-119">Knowing the type early enables the compiler to identify problems before execution, allocate memory precisely, and perform other optimizations.</span></span> <span data-ttu-id="b3d72-120">Die frühe Bindung ermöglicht außerdem der Visual Basic integrierten Entwicklungsumgebung (Integrated Development Environment, IDE), IntelliSense-Hilfe zu den Membern eines Objekts bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="b3d72-120">Early binding also enables the Visual Basic integrated development environment (IDE) to provide IntelliSense Help about the members of an object.</span></span> <span data-ttu-id="b3d72-121">Die frühe Bindung wird auch für die Leistung bevorzugt.</span><span class="sxs-lookup"><span data-stu-id="b3d72-121">Early binding is also preferred for performance.</span></span> <span data-ttu-id="b3d72-122">Dies liegt daran, dass alle in einer spät gebundenen Variablen gespeicherten Daten als Typ umschließt werden müssen `Object` und der Zugriff auf Member des Typs zur Laufzeit das Programm verlangsamt.</span><span class="sxs-lookup"><span data-stu-id="b3d72-122">This is because all data stored in a late-bound variable must be wrapped as type `Object`, and accessing members of the type at run time makes the program slower.</span></span>

## <a name="examples"></a><span data-ttu-id="b3d72-123">Beispiele</span><span class="sxs-lookup"><span data-stu-id="b3d72-123">Examples</span></span>

<span data-ttu-id="b3d72-124">Der Typrückschluss tritt auf, wenn eine lokale Variable ohne eine `As` -Klausel deklariert und initialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="b3d72-124">Type inference occurs when a local variable is declared without an `As` clause and initialized.</span></span> <span data-ttu-id="b3d72-125">Der Compiler verwendet den Typ des zugewiesenen anfangs Werts als Typ der Variablen.</span><span class="sxs-lookup"><span data-stu-id="b3d72-125">The compiler uses the type of the assigned initial value as the type of the variable.</span></span> <span data-ttu-id="b3d72-126">Jede der folgenden Codezeilen deklariert z. b. eine Variable vom Typ `String` .</span><span class="sxs-lookup"><span data-stu-id="b3d72-126">For example, each of the following lines of code declares a variable of type `String`.</span></span>

[!code-vb[VbVbalrTypeInference#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#2)]

<span data-ttu-id="b3d72-127">Der folgende Code veranschaulicht zwei äquivalente Möglichkeiten, ein Array von ganzen Zahlen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="b3d72-127">The following code demonstrates two equivalent ways to create an array of integers.</span></span>

[!code-vb[VbVbalrTypeInference#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#3)]

<span data-ttu-id="b3d72-128">Es ist praktisch, mit dem Typrückschluss den Typ einer Schleifen Steuerungsvariablen zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="b3d72-128">It is convenient to use type inference to determine the type of a loop control variable.</span></span> <span data-ttu-id="b3d72-129">Im folgenden Code geht der Compiler davon aus, dass `number` ein ist, `Integer` da `someNumbers2` aus dem vorherigen Beispiel ein Array aus ganzen Zahlen ist.</span><span class="sxs-lookup"><span data-stu-id="b3d72-129">In the following code, the compiler infers that `number` is an `Integer` because `someNumbers2` from the previous example is an array of integers.</span></span>

[!code-vb[VbVbalrTypeInference#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#4)]

<span data-ttu-id="b3d72-130">Der lokale Typrückschluss kann in-Anweisungen verwendet werden `Using` , um den Typ des Ressourcen namensfest zulegen, wie im folgenden Beispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="b3d72-130">Local type inference can be used in `Using` statements to establish the type of the resource name, as the following example demonstrates.</span></span>

[!code-vb[VbVbalrTypeInference#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#7)]

<span data-ttu-id="b3d72-131">Der Typ einer Variablen kann auch von den Rückgabe Werten von Functions abgeleitet werden, wie im folgenden Beispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="b3d72-131">The type of a variable can also be inferred from the return values of functions, as the following example demonstrates.</span></span> <span data-ttu-id="b3d72-132">`pList1`Und `pList2` sind Arrays von-Prozessen, da `Process.GetProcesses` ein Array von-Prozessen zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="b3d72-132">Both `pList1` and `pList2` are arrays of processes because `Process.GetProcesses` returns an array of processes.</span></span>

[!code-vb[VbVbalrTypeInference#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#5)]

## <a name="option-infer"></a><span data-ttu-id="b3d72-133">Option Infer</span><span class="sxs-lookup"><span data-stu-id="b3d72-133">Option Infer</span></span>

<span data-ttu-id="b3d72-134">`Option Infer`ermöglicht Ihnen, anzugeben, ob der lokale Typrückschluss in einer bestimmten Datei zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="b3d72-134">`Option Infer` enables you specify whether local type inference is allowed in a particular file.</span></span> <span data-ttu-id="b3d72-135">Wenn Sie oder zum Blockieren der Option aktivieren möchten, geben Sie eine der folgenden Anweisungen am Anfang der Datei ein.</span><span class="sxs-lookup"><span data-stu-id="b3d72-135">To enable or to block the option, type one of the following statements at the start of the file.</span></span>

`Option Infer On`

`Option Infer Off`

<span data-ttu-id="b3d72-136">Wenn Sie im Code keinen Wert für angeben `Option Infer` , ist der Compilerstandardwert `Option Infer On` .</span><span class="sxs-lookup"><span data-stu-id="b3d72-136">If you do not specify a value for `Option Infer` in your code, the compiler default is `Option Infer On`.</span></span>

<span data-ttu-id="b3d72-137">Wenn der in einer Datei für `Option Infer` festgelegte Wert mit dem in der IDE oder in der Befehlszeile festgelegten Wert im Konflikt steht, hat der Wert in der Datei Vorrang.</span><span class="sxs-lookup"><span data-stu-id="b3d72-137">If the value set for `Option Infer` in a file conflicts with the value set in the IDE or on the command line, the value in the file has precedence.</span></span>

<span data-ttu-id="b3d72-138">Weitere Informationen finden Sie unter [Option Infer-Anweisung](../../../language-reference/statements/option-infer-statement.md) und [Kompilierungs Seite, Projekt-Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="b3d72-138">For more information, see [Option Infer Statement](../../../language-reference/statements/option-infer-statement.md) and [Compile Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic).</span></span>

## <a name="see-also"></a><span data-ttu-id="b3d72-139">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b3d72-139">See also</span></span>

- [<span data-ttu-id="b3d72-140">Anonyme Typen</span><span class="sxs-lookup"><span data-stu-id="b3d72-140">Anonymous Types</span></span>](../objects-and-classes/anonymous-types.md)
- [<span data-ttu-id="b3d72-141">Frühe und späte Bindung</span><span class="sxs-lookup"><span data-stu-id="b3d72-141">Early and Late Binding</span></span>](../early-late-binding/index.md)
- [<span data-ttu-id="b3d72-142">For Each...Next-Anweisung</span><span class="sxs-lookup"><span data-stu-id="b3d72-142">For Each...Next Statement</span></span>](../../../language-reference/statements/for-each-next-statement.md)
- [<span data-ttu-id="b3d72-143">For...Next-Anweisung</span><span class="sxs-lookup"><span data-stu-id="b3d72-143">For...Next Statement</span></span>](../../../language-reference/statements/for-next-statement.md)
- [<span data-ttu-id="b3d72-144">Option Infer-Anweisung</span><span class="sxs-lookup"><span data-stu-id="b3d72-144">Option Infer Statement</span></span>](../../../language-reference/statements/option-infer-statement.md)
- [<span data-ttu-id="b3d72-145">-optioninfer</span><span class="sxs-lookup"><span data-stu-id="b3d72-145">-optioninfer</span></span>](../../../reference/command-line-compiler/optioninfer.md)
- [<span data-ttu-id="b3d72-146">Einführung in LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b3d72-146">Introduction to LINQ in Visual Basic</span></span>](../linq/introduction-to-linq.md)
