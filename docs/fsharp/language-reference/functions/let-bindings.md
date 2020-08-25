---
title: let-Bindungen
description: 'Erfahren Sie, wie Sie eine F #-"Let"-Bindung verwenden, die einen Bezeichner einem Wert oder einer Funktion zuordnet.'
ms.date: 05/16/2016
ms.openlocfilehash: 6f2396f480c5e6c631d0022f4732419ee5b07db6
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/25/2020
ms.locfileid: "88812223"
---
# <a name="let-bindings"></a><span data-ttu-id="5d56e-103">let-Bindungen</span><span class="sxs-lookup"><span data-stu-id="5d56e-103">let Bindings</span></span>

<span data-ttu-id="5d56e-104">Eine *Bindung* ordnet einen Bezeichner einem Wert oder einer Funktion zu.</span><span class="sxs-lookup"><span data-stu-id="5d56e-104">A *binding* associates an identifier with a value or function.</span></span> <span data-ttu-id="5d56e-105">Verwenden Sie das- `let` Schlüsselwort, um einen Namen an einen Wert oder eine Funktion zu binden.</span><span class="sxs-lookup"><span data-stu-id="5d56e-105">You use the `let` keyword to bind a name to a value or function.</span></span>

## <a name="syntax"></a><span data-ttu-id="5d56e-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="5d56e-106">Syntax</span></span>

```fsharp
// Binding a value:
let identifier-or-pattern [: type] =expressionbody-expression
// Binding a function value:
let identifier parameter-list [: return-type ] =expressionbody-expression
```

## <a name="remarks"></a><span data-ttu-id="5d56e-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5d56e-107">Remarks</span></span>

<span data-ttu-id="5d56e-108">Das `let` Schlüsselwort wird in Bindungs Ausdrücken verwendet, um Werte oder Funktions Werte für einen oder mehrere Namen zu definieren.</span><span class="sxs-lookup"><span data-stu-id="5d56e-108">The `let` keyword is used in binding expressions to define values or function values for one or more names.</span></span> <span data-ttu-id="5d56e-109">In der einfachsten Form des `let` Ausdrucks wird ein Name wie folgt an einen einfachen Wert gebunden.</span><span class="sxs-lookup"><span data-stu-id="5d56e-109">The simplest form of the `let` expression binds a name to a simple value, as follows.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1101.fs)]

<span data-ttu-id="5d56e-110">Wenn Sie den Ausdruck durch eine neue Zeile vom Bezeichner trennen, müssen Sie die einzelnen Zeilen des Ausdrucks einziehen, wie im folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="5d56e-110">If you separate the expression from the identifier by using a new line, you must indent each line of the expression, as in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1102.fs)]

<span data-ttu-id="5d56e-111">Anstelle eines Namens kann ein Muster, das Namen enthält, z. b. ein Tupel angegeben werden, wie im folgenden Code dargestellt.</span><span class="sxs-lookup"><span data-stu-id="5d56e-111">Instead of just a name, a pattern that contains names can be specified, for example, a tuple, as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1103.fs)]

<span data-ttu-id="5d56e-112">Der *Text Ausdruck* ist der Ausdruck, in dem die Namen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5d56e-112">The *body-expression* is the expression in which the names are used.</span></span> <span data-ttu-id="5d56e-113">Der Textkörper Ausdruck wird in einer eigenen Zeile angezeigt, um genau mit dem ersten Zeichen im- `let` Schlüsselwort zu versehen:</span><span class="sxs-lookup"><span data-stu-id="5d56e-113">The body expression appears on its own line, indented to line up exactly with the first character in the `let` keyword:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1104.fs)]

<span data-ttu-id="5d56e-114">Eine `let` Bindung kann auf Modulebene, in der Definition eines Klassen Typs oder in lokalen Bereichen (z. b. in einer Funktionsdefinition) vorkommen.</span><span class="sxs-lookup"><span data-stu-id="5d56e-114">A `let` binding can appear at the module level, in the definition of a class type, or in local scopes, such as in a function definition.</span></span> <span data-ttu-id="5d56e-115">Eine `let` Bindung auf der obersten Ebene eines Moduls oder eines Klassen Typs muss keinen Text Ausdruck aufweisen, aber auf anderen Bereichs Ebenen ist der Text Ausdruck erforderlich.</span><span class="sxs-lookup"><span data-stu-id="5d56e-115">A `let` binding at the top level in a module or in a class type does not need to have a body expression, but at other scope levels, the body expression is required.</span></span> <span data-ttu-id="5d56e-116">Die gebundenen Namen können nach dem Zeitpunkt der Definition verwendet werden, aber nicht an einem beliebigen Punkt `let` , bevor die Bindung angezeigt wird. Dies wird im folgenden Code veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="5d56e-116">The bound names are usable after the point of definition, but not at any point before the `let` binding appears, as is illustrated in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1105.fs)]

## <a name="function-bindings"></a><span data-ttu-id="5d56e-117">Funktions Bindungen</span><span class="sxs-lookup"><span data-stu-id="5d56e-117">Function Bindings</span></span>

<span data-ttu-id="5d56e-118">Funktions Bindungen folgen den Regeln für Wert Bindungen, außer dass Funktions Bindungen den Funktionsnamen und die Parameter enthalten, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="5d56e-118">Function bindings follow the rules for value bindings, except that function bindings include the function name and the parameters, as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1106.fs)]

<span data-ttu-id="5d56e-119">Im Allgemeinen sind Parameter Muster, z. b. ein tupelmuster:</span><span class="sxs-lookup"><span data-stu-id="5d56e-119">In general, parameters are patterns, such as a tuple pattern:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1107.fs)]

<span data-ttu-id="5d56e-120">Ein `let` Bindungs Ausdruck ergibt den Wert des letzten Ausdrucks.</span><span class="sxs-lookup"><span data-stu-id="5d56e-120">A `let` binding expression evaluates to the value of the last expression.</span></span> <span data-ttu-id="5d56e-121">Daher wird im folgenden Codebeispiel der Wert von `result` aus berechnet, der ergibt `100 * function3 (1, 2)` `300` .</span><span class="sxs-lookup"><span data-stu-id="5d56e-121">Therefore, in the following code example, the value of `result` is computed from `100 * function3 (1, 2)`, which evaluates to `300`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1109.fs)]

<span data-ttu-id="5d56e-122">Weitere Informationen finden Sie unter [Funktionen](index.md).</span><span class="sxs-lookup"><span data-stu-id="5d56e-122">For more information, see [Functions](index.md).</span></span>

## <a name="type-annotations"></a><span data-ttu-id="5d56e-123">Typanmerkungen</span><span class="sxs-lookup"><span data-stu-id="5d56e-123">Type Annotations</span></span>

<span data-ttu-id="5d56e-124">Sie können Typen für Parameter angeben, indem Sie einen Doppelpunkt (:) gefolgt von einem Typnamen, der in Klammern eingeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="5d56e-124">You can specify types for parameters by including a colon (:) followed by a type name, all enclosed in parentheses.</span></span> <span data-ttu-id="5d56e-125">Sie können auch den Typ des Rückgabewerts angeben, indem Sie den Doppelpunkt anfügen und nach dem letzten Parameter eingeben.</span><span class="sxs-lookup"><span data-stu-id="5d56e-125">You can also specify the type of the return value by appending the colon and type after the last parameter.</span></span> <span data-ttu-id="5d56e-126">Die vollständigen Typanmerkungen für `function1` , mit ganzen Zahlen als Parametertypen, lauten wie folgt.</span><span class="sxs-lookup"><span data-stu-id="5d56e-126">The full type annotations for `function1`, with integers as the parameter types, would be as follows.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1108.fs)]

<span data-ttu-id="5d56e-127">Wenn keine expliziten Typparameter vorhanden sind, wird der Typrückschluss verwendet, um die Typen von Parametern von Funktionen zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="5d56e-127">When there are no explicit type parameters, type inference is used to determine the types of parameters of functions.</span></span> <span data-ttu-id="5d56e-128">Dies kann den automatischen generalisieren des Typs eines Parameters einschließen, der generisch ist.</span><span class="sxs-lookup"><span data-stu-id="5d56e-128">This can include automatically generalizing the type of a parameter to be generic.</span></span>

<span data-ttu-id="5d56e-129">Weitere Informationen finden Sie unter [Automatische Generalisierung](../generics/automatic-generalization.md) und [Typrückschluss](../type-inference.md).</span><span class="sxs-lookup"><span data-stu-id="5d56e-129">For more information, see [Automatic Generalization](../generics/automatic-generalization.md) and [Type Inference](../type-inference.md).</span></span>

## <a name="let-bindings-in-classes"></a><span data-ttu-id="5d56e-130">let-Bindungen in Klassen</span><span class="sxs-lookup"><span data-stu-id="5d56e-130">let Bindings in Classes</span></span>

<span data-ttu-id="5d56e-131">Eine `let` Bindung kann in einem Klassentyp, jedoch nicht in einer Struktur oder einem Daten Satz Typen vorkommen.</span><span class="sxs-lookup"><span data-stu-id="5d56e-131">A `let` binding can appear in a class type but not in a structure or record type.</span></span> <span data-ttu-id="5d56e-132">Damit eine Let-Bindung in einem Klassentyp verwendet werden kann, muss die Klasse über einen primären Konstruktor verfügen.</span><span class="sxs-lookup"><span data-stu-id="5d56e-132">To use a let binding in a class type, the class must have a primary constructor.</span></span> <span data-ttu-id="5d56e-133">Konstruktorparameter müssen nach dem Typnamen in der Klassendefinition angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="5d56e-133">Constructor parameters must appear after the type name in the class definition.</span></span> <span data-ttu-id="5d56e-134">Eine `let` Bindung in einem Klassentyp definiert private Felder und Member für diesen Klassentyp und `do` bildet in Verbindung mit Bindungen im Typ den Code für den primären Konstruktor für den Typ.</span><span class="sxs-lookup"><span data-stu-id="5d56e-134">A `let` binding in a class type defines private fields and members for that class type and, together with `do` bindings in the type, forms the code for the primary constructor for the type.</span></span> <span data-ttu-id="5d56e-135">Die folgenden Codebeispiele zeigen eine `MyClass` -Klasse mit privaten Feldern `field1` und `field2` .</span><span class="sxs-lookup"><span data-stu-id="5d56e-135">The following code examples show a class `MyClass` with private fields `field1` and `field2`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1110.fs)]

<span data-ttu-id="5d56e-136">Die Bereiche von `field1` und `field2` sind auf den Typ beschränkt, in dem Sie deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="5d56e-136">The scopes of `field1` and `field2` are limited to the type in which they are declared.</span></span> <span data-ttu-id="5d56e-137">Weitere Informationen finden Sie unter [ `let` Bindungen in Klassen](../members/let-bindings-in-classes.md) und [Klassen](../classes.md).</span><span class="sxs-lookup"><span data-stu-id="5d56e-137">For more information, see [`let` Bindings in Classes](../members/let-bindings-in-classes.md) and [Classes](../classes.md).</span></span>

## <a name="type-parameters-in-let-bindings"></a><span data-ttu-id="5d56e-138">Typparameter in let-Bindungen</span><span class="sxs-lookup"><span data-stu-id="5d56e-138">Type Parameters in let Bindings</span></span>

<span data-ttu-id="5d56e-139">Eine `let` Bindung auf Modulebene, in einem Typ oder in einem Berechnungs Ausdruck kann explizite Typparameter aufweisen.</span><span class="sxs-lookup"><span data-stu-id="5d56e-139">A `let` binding at the module level, in a type, or in a computation expression can have explicit type parameters.</span></span> <span data-ttu-id="5d56e-140">Eine Let-Bindung in einem Ausdruck, z. b. innerhalb einer Funktionsdefinition, darf keine Typparameter aufweisen.</span><span class="sxs-lookup"><span data-stu-id="5d56e-140">A let binding in an expression, such as within a function definition, cannot have type parameters.</span></span> <span data-ttu-id="5d56e-141">Weitere Informationen finden Sie unter [Generics](../generics/index.md).</span><span class="sxs-lookup"><span data-stu-id="5d56e-141">For more information, see [Generics](../generics/index.md).</span></span>

## <a name="attributes-on-let-bindings"></a><span data-ttu-id="5d56e-142">Attribute bei let-Bindungen</span><span class="sxs-lookup"><span data-stu-id="5d56e-142">Attributes on let Bindings</span></span>

<span data-ttu-id="5d56e-143">Attribute können auf Bindungen auf oberster Ebene `let` in einem Modul angewendet werden, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="5d56e-143">Attributes can be applied to top-level `let` bindings in a module, as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1111.fs)]

## <a name="scope-and-accessibility-of-let-bindings"></a><span data-ttu-id="5d56e-144">Bereich und Barrierefreiheit von let-Bindungen</span><span class="sxs-lookup"><span data-stu-id="5d56e-144">Scope and Accessibility of Let Bindings</span></span>

<span data-ttu-id="5d56e-145">Der Gültigkeitsbereich einer mit einer Let-Bindung deklarierten Entität ist auf den Teil des enthaltenden Bereichs beschränkt (z. b. eine Funktion, ein Modul, eine Datei oder eine Klasse), nachdem die Bindung angezeigt wurde.</span><span class="sxs-lookup"><span data-stu-id="5d56e-145">The scope of an entity declared with a let binding is limited to the portion of the containing scope (such as a function, module, file or class) after the binding appears.</span></span> <span data-ttu-id="5d56e-146">Daher kann man sagen, dass eine Let-Bindung einen Namen in einen Bereich einführt.</span><span class="sxs-lookup"><span data-stu-id="5d56e-146">Therefore, it can be said that a let binding introduces a name into a scope.</span></span> <span data-ttu-id="5d56e-147">In einem Modul ist ein Let-gebundener Wert oder eine Funktion für Clients eines Moduls zugänglich, solange auf das Modul zugegriffen werden kann, da die let-Bindungen in einem Modul in öffentliche Funktionen des Moduls kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="5d56e-147">In a module, a let-bound value or function is accessible to clients of a module as long as the module is accessible, since the let bindings in a module are compiled into public functions of the module.</span></span> <span data-ttu-id="5d56e-148">Im Gegensatz dazu sind Bindungen in einer Klasse für die Klasse privat.</span><span class="sxs-lookup"><span data-stu-id="5d56e-148">By contrast, let bindings in a class are private to the class.</span></span>

<span data-ttu-id="5d56e-149">Funktionen in Modulen müssen normalerweise durch den Namen des Moduls qualifiziert werden, wenn Sie vom Client Code verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5d56e-149">Normally, functions in modules must be qualified by the name of the module when used by client code.</span></span> <span data-ttu-id="5d56e-150">Wenn ein Modul z. b `Module1` . über eine Funktion verfügt `function1` , geben die Benutzer an, dass auf `Module1.function1` die Funktion verwiesen werden soll.</span><span class="sxs-lookup"><span data-stu-id="5d56e-150">For example, if a module `Module1` has a function `function1`, users would specify `Module1.function1` to refer to the function.</span></span>

<span data-ttu-id="5d56e-151">Benutzer eines Moduls können eine Import Deklaration verwenden, um die Funktionen innerhalb dieses Moduls zur Verwendung verfügbar zu machen, ohne dass der Modulname qualifiziert ist.</span><span class="sxs-lookup"><span data-stu-id="5d56e-151">Users of a module may use an import declaration to make the functions within that module available for use without being qualified by the module name.</span></span> <span data-ttu-id="5d56e-152">Im soeben erwähnten Beispiel können Benutzer des Moduls in diesem Fall das Modul öffnen, indem Sie die Import Deklaration öffnen `Module1` und anschließend direkt auf verweisen `function1` .</span><span class="sxs-lookup"><span data-stu-id="5d56e-152">In the example just mentioned, users of the module can in that case open the module by using the import declaration open `Module1` and thereafter refer to `function1` directly.</span></span>

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

<span data-ttu-id="5d56e-153">Einige Module verfügen über das-Attribut "Requirements [qualifiedaccess](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-requirequalifiedaccessattribute.html)", was bedeutet, dass die Funktionen, die Sie verfügbar machen, mit dem Namen des Moduls qualifiziert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="5d56e-153">Some modules have the attribute [RequireQualifiedAccess](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-requirequalifiedaccessattribute.html), which means that the functions that they expose must be qualified with the name of the module.</span></span> <span data-ttu-id="5d56e-154">Das F #-Listen Modul verfügt beispielsweise über dieses Attribut.</span><span class="sxs-lookup"><span data-stu-id="5d56e-154">For example, the F# List module has this attribute.</span></span>

<span data-ttu-id="5d56e-155">Weitere Informationen zu Modulen und zur Zugriffs Steuerung finden Sie unter [Module](../modules.md) und [Access Control](../access-control.md).</span><span class="sxs-lookup"><span data-stu-id="5d56e-155">For more information on modules and access control, see [Modules](../modules.md) and [Access Control](../access-control.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="5d56e-156">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5d56e-156">See also</span></span>

- [<span data-ttu-id="5d56e-157">Funktionen</span><span class="sxs-lookup"><span data-stu-id="5d56e-157">Functions</span></span>](index.md)
- [<span data-ttu-id="5d56e-158">`let` Bindungen in Klassen</span><span class="sxs-lookup"><span data-stu-id="5d56e-158">`let` Bindings in Classes</span></span>](../members/let-bindings-in-classes.md)
