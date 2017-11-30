---
title: let-Bindungen (F#)
description: Informationen Sie zum Verwenden einer F#-"-Bindung, die einen Bezeichner mit einem Wert oder die Funktion ordnet let".
keywords: Visual F#, F#, funktionale Programmierung
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: bee69edc-d5ae-46bd-8b56-f02d97725d0d
ms.openlocfilehash: a57c5572e4bb5a3777c928dd572b7a84d4f0a334
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="let-bindings"></a><span data-ttu-id="14dbf-104">let-Bindungen</span><span class="sxs-lookup"><span data-stu-id="14dbf-104">let Bindings</span></span>

<span data-ttu-id="14dbf-105">Ein *Bindung* ordnet einen Bezeichner mit einem Wert oder einer Funktion.</span><span class="sxs-lookup"><span data-stu-id="14dbf-105">A *binding* associates an identifier with a value or function.</span></span> <span data-ttu-id="14dbf-106">Sie verwenden die `let` Schlüsselwort, einen Namen auf einen Wert oder eine Funktion zu binden.</span><span class="sxs-lookup"><span data-stu-id="14dbf-106">You use the `let` keyword to bind a name to a value or function.</span></span>

## <a name="syntax"></a><span data-ttu-id="14dbf-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="14dbf-107">Syntax</span></span>

```fsharp
// Binding a value:
let identifier-or-pattern [: type] =expressionbody-expression
// Binding a function value:
let identifier parameter-list [: return-type ] =expressionbody-expression
```

## <a name="remarks"></a><span data-ttu-id="14dbf-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="14dbf-108">Remarks</span></span>

<span data-ttu-id="14dbf-109">Die `let` -Schlüsselwort wird verwendet, bei der Bindung Ausdrücke, um Werte oder Funktionswerte für einen oder mehrere Namen definieren.</span><span class="sxs-lookup"><span data-stu-id="14dbf-109">The `let` keyword is used in binding expressions to define values or function values for one or more names.</span></span> <span data-ttu-id="14dbf-110">Die einfachste Form der `let` Ausdruck bindet einen Namen wie folgt auf einen einfachen Wert.</span><span class="sxs-lookup"><span data-stu-id="14dbf-110">The simplest form of the `let` expression binds a name to a simple value, as follows.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1101.fs)]

<span data-ttu-id="14dbf-111">Wenn Sie den Ausdruck aus einem Bezeichner mit einer neuen Zeile trennen, muss jede Zeile des Ausdrucks, wie im folgenden Code einrücken</span><span class="sxs-lookup"><span data-stu-id="14dbf-111">If you separate the expression from the identifier by using a new line, you must indent each line of the expression, as in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1102.fs)]

<span data-ttu-id="14dbf-112">Anstatt nur einen Namen ein Muster, das Namen enthält, kann angegeben werden, z. B. eines Tupels, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="14dbf-112">Instead of just a name, a pattern that contains names can be specified, for example, a tuple, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1103.fs)]

<span data-ttu-id="14dbf-113">Die *Text-Ausdruck* ist der Ausdruck in der die Namen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="14dbf-113">The *body-expression* is the expression in which the names are used.</span></span> <span data-ttu-id="14dbf-114">Text-Ausdruck wird in einer eigenen Zeile, Einzug genau mit dem ersten Zeichen in der `let` Schlüsselwort:</span><span class="sxs-lookup"><span data-stu-id="14dbf-114">The body expression appears on its own line, indented to line up exactly with the first character in the `let` keyword:</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1104.fs)]

<span data-ttu-id="14dbf-115">Ein `let` -Bindung kann auf Modulebene, in der Definition eines Klassentyps oder in lokalen Gültigkeitsbereichen, z. B. in einer Funktionsdefinition.</span><span class="sxs-lookup"><span data-stu-id="14dbf-115">A `let` binding can appear at the module level, in the definition of a class type, or in local scopes, such as in a function definition.</span></span> <span data-ttu-id="14dbf-116">Ein `let` auf der obersten Ebene in einem Modul oder in einen Klassentyp Bindung muss nicht Body-Ausdruck verfügen, jedoch auf andere Bereichsebenen Textausdruck erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="14dbf-116">A `let` binding at the top level in a module or in a class type does not need to have a body expression, but at other scope levels, the body expression is required.</span></span> <span data-ttu-id="14dbf-117">Die gebundenen Namen verwendet werden, nach dem Zeitpunkt der Definition, jedoch nicht zu einem beliebigen Zeitpunkt vor der `let` Bindung angezeigt wird, wie im folgenden Code veranschaulicht wird.</span><span class="sxs-lookup"><span data-stu-id="14dbf-117">The bound names are usable after the point of definition, but not at any point before the `let` binding appears, as is illustrated in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1105.fs)]
    
## <a name="function-bindings"></a><span data-ttu-id="14dbf-118">Funktionsbindungen</span><span class="sxs-lookup"><span data-stu-id="14dbf-118">Function Bindings</span></span>

<span data-ttu-id="14dbf-119">Funktionsbindungen Regeln den für Wert Bindungen, mit dem Unterschied, dass funktionsbindungen den Funktionsnamen und die Parameter enthalten, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="14dbf-119">Function bindings follow the rules for value bindings, except that function bindings include the function name and the parameters, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1106.fs)]

<span data-ttu-id="14dbf-120">Parameter sind im allgemeinen Mustern, z. B. ein Tupelmuster:</span><span class="sxs-lookup"><span data-stu-id="14dbf-120">In general, parameters are patterns, such as a tuple pattern:</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1107.fs)]

<span data-ttu-id="14dbf-121">Ein `let` binden Ausdruck ergibt den Wert des letzten Ausdrucks.</span><span class="sxs-lookup"><span data-stu-id="14dbf-121">A `let` binding expression evaluates to the value of the last expression.</span></span> <span data-ttu-id="14dbf-122">Aus diesem Grund in die im folgenden Codebeispiel wird der Wert der `result` errechnet sich aus `100 * function3 (1, 2)`, ergibt die `300`.</span><span class="sxs-lookup"><span data-stu-id="14dbf-122">Therefore, in the following code example, the value of `result` is computed from `100 * function3 (1, 2)`, which evaluates to `300`.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1109.fs)]

<span data-ttu-id="14dbf-123">Weitere Informationen finden Sie unter [Funktionen](index.md).</span><span class="sxs-lookup"><span data-stu-id="14dbf-123">For more information, see [Functions](index.md).</span></span>

## <a name="type-annotations"></a><span data-ttu-id="14dbf-124">Typanmerkungen</span><span class="sxs-lookup"><span data-stu-id="14dbf-124">Type Annotations</span></span>

<span data-ttu-id="14dbf-125">Sie können Typen für Parameter angeben, durch einen Doppelpunkt (:) gefolgt vom Typnamen, alle Elemente in Klammern einschließen.</span><span class="sxs-lookup"><span data-stu-id="14dbf-125">You can specify types for parameters by including a colon (:) followed by a type name, all enclosed in parentheses.</span></span> <span data-ttu-id="14dbf-126">Sie können auch den Typ des Rückgabewerts angeben, durch den Doppelpunkt und den Typ nach dem letzten Parameter anfügen.</span><span class="sxs-lookup"><span data-stu-id="14dbf-126">You can also specify the type of the return value by appending the colon and type after the last parameter.</span></span> <span data-ttu-id="14dbf-127">Die vollständige typanmerkungen für `function1`, mit ganzen Zahlen als Parametertypen, wäre wie folgt.</span><span class="sxs-lookup"><span data-stu-id="14dbf-127">The full type annotations for `function1`, with integers as the parameter types, would be as follows.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1108.fs)]

<span data-ttu-id="14dbf-128">Wenn keine explizite Typparameter vorhanden sind, wird Typrückschluss verwendet, um die Typen der Parameter von Funktionen zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="14dbf-128">When there are no explicit type parameters, type inference is used to determine the types of parameters of functions.</span></span> <span data-ttu-id="14dbf-129">Dazu gehören das automatisch durch das Verallgemeinern von den Typ eines Parameters generisch sein.</span><span class="sxs-lookup"><span data-stu-id="14dbf-129">This can include automatically generalizing the type of a parameter to be generic.</span></span>

<span data-ttu-id="14dbf-130">Weitere Informationen finden Sie unter [automatische Verallgemeinerung](../generics/automatic-generalization.md) und [Typrückschluss](../type-inference.md).</span><span class="sxs-lookup"><span data-stu-id="14dbf-130">For more information, see [Automatic Generalization](../generics/automatic-generalization.md) and [Type Inference](../type-inference.md).</span></span>

## <a name="let-bindings-in-classes"></a><span data-ttu-id="14dbf-131">let-Bindungen in Klassen</span><span class="sxs-lookup"><span data-stu-id="14dbf-131">let Bindings in Classes</span></span>

<span data-ttu-id="14dbf-132">Ein `let` -Bindung kann in einem Klassentyp sein, aber nicht in eine Struktur oder ein Datensatztyp.</span><span class="sxs-lookup"><span data-stu-id="14dbf-132">A `let` binding can appear in a class type but not in a structure or record type.</span></span> <span data-ttu-id="14dbf-133">Um eine Let-Bindung in einem Klassentyp zu verwenden, muss die Klasse einen primären Konstruktor verfügen.</span><span class="sxs-lookup"><span data-stu-id="14dbf-133">To use a let binding in a class type, the class must have a primary constructor.</span></span> <span data-ttu-id="14dbf-134">Konstruktorparameter müssen nach dem Namen des Typs in der Klassendefinition angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="14dbf-134">Constructor parameters must appear after the type name in the class definition.</span></span> <span data-ttu-id="14dbf-135">Ein `let` Bindung in einen Klassentyp definiert private Felder und Member für diesen Klassentyp und zusammen mit `do` Bindungen in den Typ bildet den Code für den primären Konstruktor für den Typ.</span><span class="sxs-lookup"><span data-stu-id="14dbf-135">A `let` binding in a class type defines private fields and members for that class type and, together with `do` bindings in the type, forms the code for the primary constructor for the type.</span></span> <span data-ttu-id="14dbf-136">Die folgenden Codebeispiele zeigen eine Klasse `MyClass` private Felder `field1` und `field2`.</span><span class="sxs-lookup"><span data-stu-id="14dbf-136">The following code examples show a class `MyClass` with private fields `field1` and `field2`.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1110.fs)]

<span data-ttu-id="14dbf-137">Die Bereiche des `field1` und `field2` sind beschränkt auf den Typ, in dem sie deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="14dbf-137">The scopes of `field1` and `field2` are limited to the type in which they are declared.</span></span> <span data-ttu-id="14dbf-138">Weitere Informationen finden Sie unter [ `let` Bindungen in Klassen](../members/let-bindings-in-classes.md) und [Klassen](../classes.md).</span><span class="sxs-lookup"><span data-stu-id="14dbf-138">For more information, see [`let` Bindings in Classes](../members/let-bindings-in-classes.md) and [Classes](../classes.md).</span></span>

## <a name="type-parameters-in-let-bindings"></a><span data-ttu-id="14dbf-139">Typparameter in let-Bindungen</span><span class="sxs-lookup"><span data-stu-id="14dbf-139">Type Parameters in let Bindings</span></span>

<span data-ttu-id="14dbf-140">Ein `let` Bindung auf Modulebene, in einen Typ oder einen Ausdruck für die Berechnung kann explizite Typparameter verfügen.</span><span class="sxs-lookup"><span data-stu-id="14dbf-140">A `let` binding at the module level, in a type, or in a computation expression can have explicit type parameters.</span></span> <span data-ttu-id="14dbf-141">Eine Let-Bindung in einem Ausdruck, z. B. innerhalb einer Funktionsdefinition dürfen keine Typparameter aufweisen.</span><span class="sxs-lookup"><span data-stu-id="14dbf-141">A let binding in an expression, such as within a function definition, cannot have type parameters.</span></span> <span data-ttu-id="14dbf-142">Weitere Informationen finden Sie unter [Generika](../generics/index.md).</span><span class="sxs-lookup"><span data-stu-id="14dbf-142">For more information, see [Generics](../generics/index.md).</span></span>

## <a name="attributes-on-let-bindings"></a><span data-ttu-id="14dbf-143">Attribute auf let-Bindungen</span><span class="sxs-lookup"><span data-stu-id="14dbf-143">Attributes on let Bindings</span></span>

<span data-ttu-id="14dbf-144">Attribute können auf der obersten Ebene angewendet werden `let` Bindungen in einem Modul, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="14dbf-144">Attributes can be applied to top-level `let` bindings in a module, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1111.fs)]
    
## <a name="scope-and-accessibility-of-let-bindings"></a><span data-ttu-id="14dbf-145">Bereich und der Zugriff von Let-Bindungen</span><span class="sxs-lookup"><span data-stu-id="14dbf-145">Scope and Accessibility of Let Bindings</span></span>

<span data-ttu-id="14dbf-146">Der Bereich einer Entität mit einem Let-Bindung deklariert ist beschränkt auf den Bereich des enthaltenden Bereich (z. B. eine Funktion, Modul, Datei oder Klasse), nachdem die Bindung angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="14dbf-146">The scope of an entity declared with a let binding is limited to the portion of the containing scope (such as a function, module, file or class) after the binding appears.</span></span> <span data-ttu-id="14dbf-147">Aus diesem Grund kann gesagt werden, dass eine Bindung ermöglichen einen Namen in den Gültigkeitsbereich einer führt.</span><span class="sxs-lookup"><span data-stu-id="14dbf-147">Therefore, it can be said that a let binding introduces a name into a scope.</span></span> <span data-ttu-id="14dbf-148">In einem Modul ist die einem Let-Grenzwert oder Funktion zugegriffen werden kann, um Clients eines Moduls, solange das Modul zugegriffen werden kann, ist, da der öffentliche Funktionen des Moduls der Let-Bindungen in einem Modul kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="14dbf-148">In a module, a let-bound value or function is accessible to clients of a module as long as the module is accessible, since the let bindings in a module are compiled into public functions of the module.</span></span> <span data-ttu-id="14dbf-149">Im Gegensatz dazu sind Let-Bindungen in einer Klasse für die Klasse privat.</span><span class="sxs-lookup"><span data-stu-id="14dbf-149">By contrast, let bindings in a class are private to the class.</span></span>

<span data-ttu-id="14dbf-150">Funktionen in Modulen müssen in der Regel wird durch den Namen des Moduls bei Verwendung durch Clientcode gekennzeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="14dbf-150">Normally, functions in modules must be qualified by the name of the module when used by client code.</span></span> <span data-ttu-id="14dbf-151">Angenommen, ein Modul `Module1` verfügt über eine Funktion `function1`, Benutzer angeben würden `Module1.function1` zum Verweisen auf die Funktion.</span><span class="sxs-lookup"><span data-stu-id="14dbf-151">For example, if a module `Module1` has a function `function1`, users would specify `Module1.function1` to refer to the function.</span></span>

<span data-ttu-id="14dbf-152">Benutzer eines Moduls können eine Importdeklaration verwenden, um die Funktionen in diesem Modul für die Verwendung verfügbar zu machen, ohne wird durch den Namen des Moduls gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="14dbf-152">Users of a module may use an import declaration to make the functions within that module available for use without being qualified by the module name.</span></span> <span data-ttu-id="14dbf-153">Im Beispiel aufgeführten Benutzer des Moduls können in diesem Fall öffnen Sie das Modul mithilfe der Import-Deklaration öffnen `Module1` und danach auf verweisen `function1` direkt.</span><span class="sxs-lookup"><span data-stu-id="14dbf-153">In the example just mentioned, users of the module can in that case open the module by using the import declaration open `Module1` and thereafter refer to `function1` directly.</span></span>

```fsharp
module Module1 =
    let function1 x = x + 1.0

module Module2 =
    let function2 x =
        Module1.function1 x

open Module1

let function3 x =
    function1 x
```

<span data-ttu-id="14dbf-154">Einige Module verfügen über Attribute [RequireQualifiedAccess](https://msdn.microsoft.com/library/8b9b6ade-0471-4413-ac5d-638cd0de5f15), was bedeutet, dass die Funktionen, die sie verfügbar machen, die mit dem Namen des Moduls gekennzeichnet sein müssen.</span><span class="sxs-lookup"><span data-stu-id="14dbf-154">Some modules have the attribute [RequireQualifiedAccess](https://msdn.microsoft.com/library/8b9b6ade-0471-4413-ac5d-638cd0de5f15), which means that the functions that they expose must be qualified with the name of the module.</span></span> <span data-ttu-id="14dbf-155">Der F#-List-Modul hat z. B. dieses Attribut.</span><span class="sxs-lookup"><span data-stu-id="14dbf-155">For example, the F# List module has this attribute.</span></span>

<span data-ttu-id="14dbf-156">Weitere Informationen zu Modulen und Steuerung des Zugriffs, finden Sie unter [Module](../modules.md) und [Access Control](../access-control.md).</span><span class="sxs-lookup"><span data-stu-id="14dbf-156">For more information on modules and access control, see [Modules](../modules.md) and [Access Control](../access-control.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="14dbf-157">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="14dbf-157">See Also</span></span>

[<span data-ttu-id="14dbf-158">Funktionen</span><span class="sxs-lookup"><span data-stu-id="14dbf-158">Functions</span></span>](index.md)

[<span data-ttu-id="14dbf-159">`let`-Bindungen in Klassen</span><span class="sxs-lookup"><span data-stu-id="14dbf-159">`let` Bindings in Classes</span></span>](../members/let-bindings-in-classes.md)
