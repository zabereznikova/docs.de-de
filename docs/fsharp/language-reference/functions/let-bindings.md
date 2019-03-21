---
title: let-Bindungen
description: Erfahren Sie, wie Sie mit einem F# "let" Bindung, die einen Bezeichner mit einem Wert oder einer Funktion verknüpft.
ms.date: 05/16/2016
ms.openlocfilehash: 45de82acf6f4423698cd8037266968e023f40dcb
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2018
ms.locfileid: "53612672"
---
# <a name="let-bindings"></a><span data-ttu-id="79939-103">let-Bindungen</span><span class="sxs-lookup"><span data-stu-id="79939-103">let Bindings</span></span>

<span data-ttu-id="79939-104">Ein *Bindung* ordnet einen Wert oder die Funktion einen Bezeichner.</span><span class="sxs-lookup"><span data-stu-id="79939-104">A *binding* associates an identifier with a value or function.</span></span> <span data-ttu-id="79939-105">Sie verwenden die `let` Schlüsselwort, um einen Namen auf einen Wert oder die Funktion zu binden.</span><span class="sxs-lookup"><span data-stu-id="79939-105">You use the `let` keyword to bind a name to a value or function.</span></span>

## <a name="syntax"></a><span data-ttu-id="79939-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="79939-106">Syntax</span></span>

```fsharp
// Binding a value:
let identifier-or-pattern [: type] =expressionbody-expression
// Binding a function value:
let identifier parameter-list [: return-type ] =expressionbody-expression
```

## <a name="remarks"></a><span data-ttu-id="79939-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="79939-107">Remarks</span></span>

<span data-ttu-id="79939-108">Die `let` -Schlüsselwort wird verwendet, in Bindungsausdrücken Werte oder Werte für einen oder mehrere Namen von Funktionen zu definieren.</span><span class="sxs-lookup"><span data-stu-id="79939-108">The `let` keyword is used in binding expressions to define values or function values for one or more names.</span></span> <span data-ttu-id="79939-109">Die einfachste Form der `let` Ausdruck bindet einen Namen wie folgt auf einen einfachen Wert.</span><span class="sxs-lookup"><span data-stu-id="79939-109">The simplest form of the `let` expression binds a name to a simple value, as follows.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1101.fs)]

<span data-ttu-id="79939-110">Wenn Sie den Ausdruck aus einem Bezeichner mit einer neuen Zeile trennen, müssen Sie jede Zeile des Ausdrucks, wie im folgenden Code eingerückt.</span><span class="sxs-lookup"><span data-stu-id="79939-110">If you separate the expression from the identifier by using a new line, you must indent each line of the expression, as in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1102.fs)]

<span data-ttu-id="79939-111">Statt einfach einen Namen, ein Muster, das Namen angegeben werden, z. B. eines Tupels, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="79939-111">Instead of just a name, a pattern that contains names can be specified, for example, a tuple, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1103.fs)]

<span data-ttu-id="79939-112">Die *Body-Ausdruck* ist der Ausdruck, der in der die Namen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="79939-112">The *body-expression* is the expression in which the names are used.</span></span> <span data-ttu-id="79939-113">Der Body-Ausdruck wird in einer eigenen Zeile, Einzug genau mit dem ersten Zeichen in der `let` Schlüsselwort:</span><span class="sxs-lookup"><span data-stu-id="79939-113">The body expression appears on its own line, indented to line up exactly with the first character in the `let` keyword:</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1104.fs)]

<span data-ttu-id="79939-114">Ein `let` -Bindung kann auf Modulebene, in der Definition eines Klassentyps oder in lokalen Bereichen, z. B. in einer Funktionsdefinition.</span><span class="sxs-lookup"><span data-stu-id="79939-114">A `let` binding can appear at the module level, in the definition of a class type, or in local scopes, such as in a function definition.</span></span> <span data-ttu-id="79939-115">Ein `let` Bindung auf der obersten Ebene in einem Modul oder in einen Klassentyp muss nicht Body-Ausdruck verfügen, aber auf andere Bereichsebenen, Text-Ausdruck ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="79939-115">A `let` binding at the top level in a module or in a class type does not need to have a body expression, but at other scope levels, the body expression is required.</span></span> <span data-ttu-id="79939-116">Die gebundenen Namen verwendet werden, nach dem Zeitpunkt der Definition, aber nicht an einem beliebigen Punkt vor der `let` Bindung angezeigt wird, wie im folgenden Code dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="79939-116">The bound names are usable after the point of definition, but not at any point before the `let` binding appears, as is illustrated in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1105.fs)]

## <a name="function-bindings"></a><span data-ttu-id="79939-117">Funktionsbindungen</span><span class="sxs-lookup"><span data-stu-id="79939-117">Function Bindings</span></span>

<span data-ttu-id="79939-118">Funktionsbindungen folgen den Regeln für Wert Bindungen an, mit dem Unterschied, dass funktionsbindungen den Namen der Funktion und die Parameter enthalten, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="79939-118">Function bindings follow the rules for value bindings, except that function bindings include the function name and the parameters, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1106.fs)]

<span data-ttu-id="79939-119">Parameter sind im allgemeinen Muster wie z.B. einem Tupelmuster:</span><span class="sxs-lookup"><span data-stu-id="79939-119">In general, parameters are patterns, such as a tuple pattern:</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1107.fs)]

<span data-ttu-id="79939-120">Ein `let` Bindungsausdruck ergibt den Wert des letzten Ausdrucks.</span><span class="sxs-lookup"><span data-stu-id="79939-120">A `let` binding expression evaluates to the value of the last expression.</span></span> <span data-ttu-id="79939-121">Aus diesem Grund in der folgenden Codebeispiel wird der Wert des `result` wird berechnet aus `100 * function3 (1, 2)`, ergibt die `300`.</span><span class="sxs-lookup"><span data-stu-id="79939-121">Therefore, in the following code example, the value of `result` is computed from `100 * function3 (1, 2)`, which evaluates to `300`.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1109.fs)]

<span data-ttu-id="79939-122">Weitere Informationen finden Sie unter [Funktionen](index.md).</span><span class="sxs-lookup"><span data-stu-id="79939-122">For more information, see [Functions](index.md).</span></span>

## <a name="type-annotations"></a><span data-ttu-id="79939-123">Typanmerkungen</span><span class="sxs-lookup"><span data-stu-id="79939-123">Type Annotations</span></span>

<span data-ttu-id="79939-124">Sie können die Typen für Parameter angeben, durch einen Doppelpunkt (:) gefolgt von einem Typnamen alle Elemente in Klammern einschließen.</span><span class="sxs-lookup"><span data-stu-id="79939-124">You can specify types for parameters by including a colon (:) followed by a type name, all enclosed in parentheses.</span></span> <span data-ttu-id="79939-125">Sie können auch den Typ des Rückgabewerts angeben, durch den Doppelpunkt und den Typ nach dem letzten Parameter anfügen.</span><span class="sxs-lookup"><span data-stu-id="79939-125">You can also specify the type of the return value by appending the colon and type after the last parameter.</span></span> <span data-ttu-id="79939-126">Die vollständige typanmerkungen für `function1`, mit ganzen Zahlen als Parametertypen, würde wie folgt lauten.</span><span class="sxs-lookup"><span data-stu-id="79939-126">The full type annotations for `function1`, with integers as the parameter types, would be as follows.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1108.fs)]

<span data-ttu-id="79939-127">Wenn keine expliziten Typ-Parameter vorhanden sind, wird den Typrückschluss verwendet, um zu bestimmen, die Typen der Parameter von Funktionen.</span><span class="sxs-lookup"><span data-stu-id="79939-127">When there are no explicit type parameters, type inference is used to determine the types of parameters of functions.</span></span> <span data-ttu-id="79939-128">Dies kann beinhalten, automatisch eine Generalisierung des Typs eines Parameters generisch sein.</span><span class="sxs-lookup"><span data-stu-id="79939-128">This can include automatically generalizing the type of a parameter to be generic.</span></span>

<span data-ttu-id="79939-129">Weitere Informationen finden Sie unter [automatische Verallgemeinerung](../generics/automatic-generalization.md) und [Typrückschluss](../type-inference.md).</span><span class="sxs-lookup"><span data-stu-id="79939-129">For more information, see [Automatic Generalization](../generics/automatic-generalization.md) and [Type Inference](../type-inference.md).</span></span>

## <a name="let-bindings-in-classes"></a><span data-ttu-id="79939-130">let-Bindungen in Klassen</span><span class="sxs-lookup"><span data-stu-id="79939-130">let Bindings in Classes</span></span>

<span data-ttu-id="79939-131">Ein `let` -Bindung kann in einen Klassentyp jedoch nicht in einer Struktur oder einem Datensatztyp.</span><span class="sxs-lookup"><span data-stu-id="79939-131">A `let` binding can appear in a class type but not in a structure or record type.</span></span> <span data-ttu-id="79939-132">Um eine Let-Bindung in einen Klassentyp zu verwenden, muss die Klasse über einen primären Konstruktor verfügen.</span><span class="sxs-lookup"><span data-stu-id="79939-132">To use a let binding in a class type, the class must have a primary constructor.</span></span> <span data-ttu-id="79939-133">Konstruktorparameter müssen nach dem Namen des Typs in der Klassendefinition angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="79939-133">Constructor parameters must appear after the type name in the class definition.</span></span> <span data-ttu-id="79939-134">Ein `let` Bindung in einen Klassentyp definiert wird, private Felder und Elemente für dieses Klassentyps und zusammen mit `do` Bindungen in den Typ, bildet den Code für den primären Konstruktor für den Typ.</span><span class="sxs-lookup"><span data-stu-id="79939-134">A `let` binding in a class type defines private fields and members for that class type and, together with `do` bindings in the type, forms the code for the primary constructor for the type.</span></span> <span data-ttu-id="79939-135">Die folgenden Codebeispiele zeigen eine Klasse `MyClass` private Felder `field1` und `field2`.</span><span class="sxs-lookup"><span data-stu-id="79939-135">The following code examples show a class `MyClass` with private fields `field1` and `field2`.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1110.fs)]

<span data-ttu-id="79939-136">Die Bereiche der `field1` und `field2` sind beschränkt auf den Typ, in dem sie deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="79939-136">The scopes of `field1` and `field2` are limited to the type in which they are declared.</span></span> <span data-ttu-id="79939-137">Weitere Informationen finden Sie unter [ `let` Bindungen in Klassen](../members/let-bindings-in-classes.md) und [Klassen](../classes.md).</span><span class="sxs-lookup"><span data-stu-id="79939-137">For more information, see [`let` Bindings in Classes](../members/let-bindings-in-classes.md) and [Classes](../classes.md).</span></span>

## <a name="type-parameters-in-let-bindings"></a><span data-ttu-id="79939-138">Typparameter in let-Bindungen</span><span class="sxs-lookup"><span data-stu-id="79939-138">Type Parameters in let Bindings</span></span>

<span data-ttu-id="79939-139">Ein `let` Bindung auf Modulebene, in einen Typ oder in einem Berechnungsausdruck kann explizite Typparameter haben.</span><span class="sxs-lookup"><span data-stu-id="79939-139">A `let` binding at the module level, in a type, or in a computation expression can have explicit type parameters.</span></span> <span data-ttu-id="79939-140">Eine Let-Bindung in einem Ausdruck, z. B. innerhalb einer Funktionsdefinition, dürfen keine Typparameter aufweisen.</span><span class="sxs-lookup"><span data-stu-id="79939-140">A let binding in an expression, such as within a function definition, cannot have type parameters.</span></span> <span data-ttu-id="79939-141">Weitere Informationen finden Sie unter [Generics](../generics/index.md).</span><span class="sxs-lookup"><span data-stu-id="79939-141">For more information, see [Generics](../generics/index.md).</span></span>

## <a name="attributes-on-let-bindings"></a><span data-ttu-id="79939-142">Attribute in let-Bindungen</span><span class="sxs-lookup"><span data-stu-id="79939-142">Attributes on let Bindings</span></span>

<span data-ttu-id="79939-143">Attribute können auf der obersten Ebene angewendet werden `let` Bindungen in einem Modul, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="79939-143">Attributes can be applied to top-level `let` bindings in a module, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1111.fs)]

## <a name="scope-and-accessibility-of-let-bindings"></a><span data-ttu-id="79939-144">Bereich und der Zugriff von Let-Bindungen</span><span class="sxs-lookup"><span data-stu-id="79939-144">Scope and Accessibility of Let Bindings</span></span>

<span data-ttu-id="79939-145">Der Bereich einer Entität, die mit einer Let-Bindung deklariert ist beschränkt, der Teil des enthaltenden Bereich (z. B. eine Funktion, Modul, Datei oder Klasse), wenn die Bindung angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="79939-145">The scope of an entity declared with a let binding is limited to the portion of the containing scope (such as a function, module, file or class) after the binding appears.</span></span> <span data-ttu-id="79939-146">Aus diesem Grund kann es gilt, dass eine Let-Bindung über einen Namen in einem Bereich einführt.</span><span class="sxs-lookup"><span data-stu-id="79939-146">Therefore, it can be said that a let binding introduces a name into a scope.</span></span> <span data-ttu-id="79939-147">In einem Modul kann die einer Let gebundenen Wert oder eine Funktion für die Clients eines Moduls zugegriffen werden, solange das Modul zugegriffen werden kann, ist, da die Let-Bindungen in einem Modul in öffentliche Funktionen des Moduls kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="79939-147">In a module, a let-bound value or function is accessible to clients of a module as long as the module is accessible, since the let bindings in a module are compiled into public functions of the module.</span></span> <span data-ttu-id="79939-148">Im Gegensatz dazu sind die Let-Bindungen in einer Klasse auf die Klasse privat.</span><span class="sxs-lookup"><span data-stu-id="79939-148">By contrast, let bindings in a class are private to the class.</span></span>

<span data-ttu-id="79939-149">Funktionen in Modulen müssen in der Regel durch den Namen des Moduls, die bei der Verwendung von Clientcode qualifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="79939-149">Normally, functions in modules must be qualified by the name of the module when used by client code.</span></span> <span data-ttu-id="79939-150">Angenommen, ein Modul `Module1` verfügt über eine Funktion `function1`, Benutzer geben `Module1.function1` , an die Funktion zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="79939-150">For example, if a module `Module1` has a function `function1`, users would specify `Module1.function1` to refer to the function.</span></span>

<span data-ttu-id="79939-151">Eine Importdeklaration können Benutzer von einem Modul um die Funktionen innerhalb dieses Moduls verfügbar zu machen, ohne die, die durch den Namen des Moduls gekennzeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="79939-151">Users of a module may use an import declaration to make the functions within that module available for use without being qualified by the module name.</span></span> <span data-ttu-id="79939-152">Im eben erwähnten Beispiel Benutzer des Moduls können in diesem Fall öffnen Sie das Modul mithilfe der Import-Deklaration Open `Module1` und verweisen Sie anschließend auf `function1` direkt.</span><span class="sxs-lookup"><span data-stu-id="79939-152">In the example just mentioned, users of the module can in that case open the module by using the import declaration open `Module1` and thereafter refer to `function1` directly.</span></span>

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

<span data-ttu-id="79939-153">Einige Module verfügen über das Attribut [RequireQualifiedAccess](https://msdn.microsoft.com/library/8b9b6ade-0471-4413-ac5d-638cd0de5f15), was bedeutet, dass die Funktionen, die sie verfügbar machen, die mit dem Namen des Moduls gekennzeichnet sein müssen.</span><span class="sxs-lookup"><span data-stu-id="79939-153">Some modules have the attribute [RequireQualifiedAccess](https://msdn.microsoft.com/library/8b9b6ade-0471-4413-ac5d-638cd0de5f15), which means that the functions that they expose must be qualified with the name of the module.</span></span> <span data-ttu-id="79939-154">Z. B. die F# List-Modul hat dieses Attribut.</span><span class="sxs-lookup"><span data-stu-id="79939-154">For example, the F# List module has this attribute.</span></span>

<span data-ttu-id="79939-155">Weitere Informationen zu Modulen und Access Control, finden Sie unter [Module](../modules.md) und [Zugriffssteuerung](../access-control.md).</span><span class="sxs-lookup"><span data-stu-id="79939-155">For more information on modules and access control, see [Modules](../modules.md) and [Access Control](../access-control.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="79939-156">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="79939-156">See also</span></span>

- [<span data-ttu-id="79939-157">Funktionen</span><span class="sxs-lookup"><span data-stu-id="79939-157">Functions</span></span>](index.md)
- [<span data-ttu-id="79939-158">`let`-Bindungen in Klassen</span><span class="sxs-lookup"><span data-stu-id="79939-158">`let` Bindings in Classes</span></span>](../members/let-bindings-in-classes.md)