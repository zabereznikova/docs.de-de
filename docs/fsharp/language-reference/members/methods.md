---
title: Methoden
description: Erfahren Sie, F# wie eine Methode eine Funktion ist, die einem Typ zugeordnet ist, mit dem die Funktionen und das Verhalten von Objekten und Typen verfügbar gemacht und implementiert werden.
ms.date: 11/04/2019
ms.openlocfilehash: 6f5ae76ea450b07763eb58d0c95b18b30f634551
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73976650"
---
# <a name="methods"></a><span data-ttu-id="6221b-103">Methoden</span><span class="sxs-lookup"><span data-stu-id="6221b-103">Methods</span></span>

<span data-ttu-id="6221b-104">Eine *Methode* ist eine-Funktion, die einem-Typ zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="6221b-104">A *method* is a function that is associated with a type.</span></span> <span data-ttu-id="6221b-105">Bei der objektorientierten Programmierung werden Methoden verwendet, um die Funktionalität und das Verhalten von Objekten und Typen verfügbar zu machen und zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="6221b-105">In object-oriented programming, methods are used to expose and implement the functionality and behavior of objects and types.</span></span>

## <a name="syntax"></a><span data-ttu-id="6221b-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="6221b-106">Syntax</span></span>

```fsharp
// Instance method definition.
[ attributes ]
member [inline] self-identifier.method-name parameter-list [ : return-type ] =
    method-body

// Static method definition.
[ attributes ]
static member [inline] method-name parameter-list [ : return-type ] =
    method-body

// Abstract method declaration or virtual dispatch slot.
[ attributes ]
abstract member method-name : type-signature

// Virtual method declaration and default implementation.
[ attributes ]
abstract member method-name : type-signature
[ attributes ]
default self-identifier.method-name parameter-list [ : return-type ] =
    method-body

// Override of inherited virtual method.
[ attributes ]
override self-identifier.method-name parameter-list [ : return-type ] =
    method-body

// Optional and DefaultParameterValue attributes on input parameters
[ attributes ]
[ modifier ] member [inline] self-identifier.method-name ([<Optional; DefaultParameterValue( default-value )>] input) [ : return-type ]
```

## <a name="remarks"></a><span data-ttu-id="6221b-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6221b-107">Remarks</span></span>

<span data-ttu-id="6221b-108">In der vorherigen Syntax können Sie die verschiedenen Formen von Methoden Deklarationen und-Definitionen sehen.</span><span class="sxs-lookup"><span data-stu-id="6221b-108">In the previous syntax, you can see the various forms of method declarations and definitions.</span></span> <span data-ttu-id="6221b-109">In längeren Methoden Texten folgt ein Zeilenumbruch dem Gleichheitszeichen (=), und der gesamte Methoden Text wird eingezogen.</span><span class="sxs-lookup"><span data-stu-id="6221b-109">In longer method bodies, a line break follows the equal sign (=), and the whole method body is indented.</span></span>

<span data-ttu-id="6221b-110">Attribute können auf jede Methoden Deklaration angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="6221b-110">Attributes can be applied to any method declaration.</span></span> <span data-ttu-id="6221b-111">Sie sind der Syntax für eine Methoden Definition vorangestellt und werden in der Regel in einer separaten Zeile aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="6221b-111">They precede the syntax for a method definition and are usually listed on a separate line.</span></span> <span data-ttu-id="6221b-112">Weitere Informationen finden Sie unter [Attribute](../attributes.md).</span><span class="sxs-lookup"><span data-stu-id="6221b-112">For more information, see [Attributes](../attributes.md).</span></span>

<span data-ttu-id="6221b-113">Methoden können als `inline`gekennzeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="6221b-113">Methods can be marked `inline`.</span></span> <span data-ttu-id="6221b-114">Informationen zu `inline` finden Sie unter [Inlinefunktionen](../functions/inline-functions.md).</span><span class="sxs-lookup"><span data-stu-id="6221b-114">For information about `inline`, see [Inline Functions](../functions/inline-functions.md).</span></span>

<span data-ttu-id="6221b-115">Nicht Inline-Methoden können rekursiv innerhalb des Typs verwendet werden. Es ist nicht erforderlich, explizit das `rec`-Schlüsselwort zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="6221b-115">Non-inline methods can be used recursively within the type; there is no need to explicitly use the `rec` keyword.</span></span>

## <a name="instance-methods"></a><span data-ttu-id="6221b-116">Instanzmethoden</span><span class="sxs-lookup"><span data-stu-id="6221b-116">Instance Methods</span></span>

<span data-ttu-id="6221b-117">Instanzmethoden werden mit dem `member`-Schlüsselwort und einem *selbst Bezeichner*, gefolgt von einem (.) und dem Methodennamen und Parametern, deklariert.</span><span class="sxs-lookup"><span data-stu-id="6221b-117">Instance methods are declared with the `member` keyword and a *self-identifier*, followed by a period (.) and the method name and parameters.</span></span> <span data-ttu-id="6221b-118">Wie es bei `let` Bindungen der Fall ist, kann die *Parameter-List* ein Muster sein.</span><span class="sxs-lookup"><span data-stu-id="6221b-118">As is the case for `let` bindings, the *parameter-list* can be a pattern.</span></span> <span data-ttu-id="6221b-119">In der Regel schließen Sie Methoden Parameter in Klammern in einem tupelformular ein. Dies ist die Methode, mit der Methoden F# in anderen .NET Framework Sprachen erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="6221b-119">Typically, you enclose method parameters in parentheses in a tuple form, which is the way methods appear in F# when they are created in other .NET Framework languages.</span></span> <span data-ttu-id="6221b-120">Das Curry-Formular (durch Leerzeichen getrennte Parameter) ist jedoch ebenfalls üblich, und andere Muster werden ebenfalls unterstützt.</span><span class="sxs-lookup"><span data-stu-id="6221b-120">However, the curried form (parameters separated by spaces) is also common, and other patterns are supported also.</span></span>

<span data-ttu-id="6221b-121">Im folgenden Beispiel werden die Definition und die Verwendung einer nicht abstrakten Instanzmethode veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="6221b-121">The following example illustrates the definition and use of a non-abstract instance method.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3401.fs)]

<span data-ttu-id="6221b-122">Verwenden Sie in Instanzmethoden den Self-Identifier nicht für den Zugriff auf Felder, die mithilfe von let-Bindungen definiert wurden.</span><span class="sxs-lookup"><span data-stu-id="6221b-122">Within instance methods, do not use the self identifier to access fields defined by using let bindings.</span></span> <span data-ttu-id="6221b-123">Verwenden Sie den selbst Bezeichner, wenn Sie auf andere Member und Eigenschaften zugreifen.</span><span class="sxs-lookup"><span data-stu-id="6221b-123">Use the self identifier when accessing other members and properties.</span></span>

## <a name="static-methods"></a><span data-ttu-id="6221b-124">Statische Methoden</span><span class="sxs-lookup"><span data-stu-id="6221b-124">Static Methods</span></span>

<span data-ttu-id="6221b-125">Das Schlüsselwort `static` wird verwendet, um anzugeben, dass eine Methode ohne eine-Instanz aufgerufen werden kann und keiner Objektinstanz zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="6221b-125">The keyword `static` is used to specify that a method can be called without an instance and is not associated with an object instance.</span></span> <span data-ttu-id="6221b-126">Andernfalls sind Methoden Instanzmethoden.</span><span class="sxs-lookup"><span data-stu-id="6221b-126">Otherwise, methods are instance methods.</span></span>

<span data-ttu-id="6221b-127">Im Beispiel im nächsten Abschnitt werden Felder angezeigt, die mit dem `let`-Schlüsselwort, mit dem Schlüsselwort `member` deklarierte Eigenschafts Member und eine statische Methode, die mit dem `static`-Schlüsselwort deklariert wurde.</span><span class="sxs-lookup"><span data-stu-id="6221b-127">The example in the next section shows fields declared with the `let` keyword, property members declared with the `member` keyword, and a static method declared with the `static` keyword.</span></span>

<span data-ttu-id="6221b-128">Das folgende Beispiel veranschaulicht die Definition und Verwendung statischer Methoden.</span><span class="sxs-lookup"><span data-stu-id="6221b-128">The following example illustrates the definition and use of static methods.</span></span> <span data-ttu-id="6221b-129">Nehmen Sie an, dass sich diese Methoden Definitionen in der `SomeType`-Klasse des vorherigen Abschnitts befinden.</span><span class="sxs-lookup"><span data-stu-id="6221b-129">Assume that these method definitions are in the `SomeType` class in the previous section.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3402.fs)]

## <a name="abstract-and-virtual-methods"></a><span data-ttu-id="6221b-130">Abstrakte und virtuelle Methoden</span><span class="sxs-lookup"><span data-stu-id="6221b-130">Abstract and Virtual Methods</span></span>

<span data-ttu-id="6221b-131">Das Schlüsselwort `abstract` gibt an, dass eine Methode einen virtuellen dispatchslot hat und möglicherweise keine Definition in der Klasse aufweist.</span><span class="sxs-lookup"><span data-stu-id="6221b-131">The keyword `abstract` indicates that a method has a virtual dispatch slot and might not have a definition in the class.</span></span> <span data-ttu-id="6221b-132">Ein *virtueller dispatchslot* ist ein Eintrag in einer intern verwalteten Tabelle von Funktionen, die zur Laufzeit verwendet wird, um virtuelle Funktionsaufrufe in einem objektorientierten Typ zu suchen.</span><span class="sxs-lookup"><span data-stu-id="6221b-132">A *virtual dispatch slot* is an entry in an internally maintained table of functions that is used at run time to look up virtual function calls in an object-oriented type.</span></span> <span data-ttu-id="6221b-133">Der virtuelle Dispatchmechanismus ist der Mechanismus, der *Polymorphie*implementiert, ein wichtiges Feature der objektorientierten Programmierung.</span><span class="sxs-lookup"><span data-stu-id="6221b-133">The virtual dispatch mechanism is the mechanism that implements *polymorphism*, an important feature of object-oriented programming.</span></span> <span data-ttu-id="6221b-134">Eine Klasse, die über mindestens eine abstrakte Methode ohne Definition verfügt, ist eine *abstrakte Klasse*, was bedeutet, dass keine Instanzen dieser Klasse erstellt werden können.</span><span class="sxs-lookup"><span data-stu-id="6221b-134">A class that has at least one abstract method without a definition is an *abstract class*, which means that no instances can be created of that class.</span></span> <span data-ttu-id="6221b-135">Weitere Informationen zu abstrakten Klassen finden Sie unter [abstrakte Klassen](../abstract-classes.md).</span><span class="sxs-lookup"><span data-stu-id="6221b-135">For more information about abstract classes, see [Abstract Classes](../abstract-classes.md).</span></span>

<span data-ttu-id="6221b-136">Abstrakte Methoden Deklarationen enthalten keinen Methoden Text.</span><span class="sxs-lookup"><span data-stu-id="6221b-136">Abstract method declarations do not include a method body.</span></span> <span data-ttu-id="6221b-137">Stattdessen folgt der Name der Methode einem Doppelpunkt (:) und eine Typsignatur für die Methode.</span><span class="sxs-lookup"><span data-stu-id="6221b-137">Instead, the name of the method is followed by a colon (:) and a type signature for the method.</span></span> <span data-ttu-id="6221b-138">Die Typsignatur einer Methode ist identisch mit der, die von IntelliSense angezeigt wird, wenn Sie den Mauszeiger über einen Methodennamen im Visual Studio Code-Editor bewegen, außer ohne Parameternamen.</span><span class="sxs-lookup"><span data-stu-id="6221b-138">The type signature of a method is the same as that shown by IntelliSense when you pause the mouse pointer over a method name in the Visual Studio Code Editor, except without parameter names.</span></span> <span data-ttu-id="6221b-139">Typsignaturen werden auch vom Interpreter "FSI. exe" angezeigt, wenn Sie interaktiv arbeiten.</span><span class="sxs-lookup"><span data-stu-id="6221b-139">Type signatures are also displayed by the interpreter, fsi.exe, when you are working interactively.</span></span> <span data-ttu-id="6221b-140">Die Typsignatur einer Methode wird gebildet, indem die Typen der Parameter, gefolgt vom Rückgabetyp, mit entsprechenden Trennzeichen aufgelistet werden.</span><span class="sxs-lookup"><span data-stu-id="6221b-140">The type signature of a method is formed by listing out the types of the parameters, followed by the return type, with appropriate separator symbols.</span></span> <span data-ttu-id="6221b-141">Currried-Parameter werden durch `->` getrennt, und tupelparameter werden durch `*`getrennt.</span><span class="sxs-lookup"><span data-stu-id="6221b-141">Curried parameters are separated by `->` and tuple parameters are separated by `*`.</span></span> <span data-ttu-id="6221b-142">Der Rückgabewert wird immer von den Argumenten durch ein `->` Symbol getrennt.</span><span class="sxs-lookup"><span data-stu-id="6221b-142">The return value is always separated from the arguments by a `->` symbol.</span></span> <span data-ttu-id="6221b-143">Klammern können verwendet werden, um komplexe Parameter zu gruppieren, z. b. Wenn ein Funktionstyp ein Parameter ist, oder um anzugeben, dass ein Tupel als einzelner Parameter und nicht als zwei Parameter behandelt wird.</span><span class="sxs-lookup"><span data-stu-id="6221b-143">Parentheses can be used to group complex parameters, such as when a function type is a parameter, or to indicate when a tuple is treated as a single parameter rather than as two parameters.</span></span>

<span data-ttu-id="6221b-144">Sie können auch abstrakten Methoden Standarddefinitionen übergeben, indem Sie der-Klasse die Definition hinzufügen und das `default`-Schlüsselwort verwenden, wie im Syntax Block in diesem Thema gezeigt.</span><span class="sxs-lookup"><span data-stu-id="6221b-144">You can also give abstract methods default definitions by adding the definition to the class and using the `default` keyword, as shown in the syntax block in this topic.</span></span> <span data-ttu-id="6221b-145">Eine abstrakte Methode, die eine Definition in derselben Klasse aufweist, entspricht einer virtuellen Methode in anderen .NET Framework Sprachen.</span><span class="sxs-lookup"><span data-stu-id="6221b-145">An abstract method that has a definition in the same class is equivalent to a virtual method in other .NET Framework languages.</span></span> <span data-ttu-id="6221b-146">Unabhängig davon, ob eine Definition vorhanden ist, erstellt das `abstract`-Schlüsselwort einen neuen dispatchslot in der virtuellen Funktions Tabelle für die-Klasse.</span><span class="sxs-lookup"><span data-stu-id="6221b-146">Whether or not a definition exists, the `abstract` keyword creates a new dispatch slot in the virtual function table for the class.</span></span>

<span data-ttu-id="6221b-147">Unabhängig davon, ob eine Basisklasse die abstrakten Methoden implementiert, können abgeleitete Klassen Implementierungen abstrakter Methoden bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="6221b-147">Regardless of whether a base class implements its abstract methods, derived classes can provide implementations of abstract methods.</span></span> <span data-ttu-id="6221b-148">Um eine abstrakte Methode in einer abgeleiteten Klasse zu implementieren, definieren Sie eine Methode, die den gleichen Namen und die gleiche Signatur in der abgeleiteten Klasse aufweist, mit der Ausnahme, dass Sie das-Schlüsselwort `override` oder `default` verwenden und den Methoden Text angeben</span><span class="sxs-lookup"><span data-stu-id="6221b-148">To implement an abstract method in a derived class, define a method that has the same name and signature in the derived class, except use the `override` or `default` keyword, and provide the method body.</span></span> <span data-ttu-id="6221b-149">Die Schlüsselwörter `override` und `default` bedeuten genau dasselbe.</span><span class="sxs-lookup"><span data-stu-id="6221b-149">The keywords `override` and `default` mean exactly the same thing.</span></span> <span data-ttu-id="6221b-150">Verwenden Sie `override`, wenn die neue Methode eine Basisklassen Implementierung überschreibt. Verwenden Sie `default`, wenn Sie in derselben Klasse wie die ursprüngliche abstrakte Deklaration eine Implementierung erstellen.</span><span class="sxs-lookup"><span data-stu-id="6221b-150">Use `override` if the new method overrides a base class implementation; use `default` when you create an implementation in the same class as the original abstract declaration.</span></span> <span data-ttu-id="6221b-151">Verwenden Sie das `abstract`-Schlüsselwort nicht für die Methode, die die Methode implementiert, die in der Basisklasse als abstrakt deklariert wurde.</span><span class="sxs-lookup"><span data-stu-id="6221b-151">Do not use the `abstract` keyword on the method that implements the method that was declared abstract in the base class.</span></span>

<span data-ttu-id="6221b-152">Das folgende Beispiel veranschaulicht eine abstrakte Methode `Rotate`, die über eine Standard Implementierung verfügt, die einer .NET Framework virtuellen Methode entspricht.</span><span class="sxs-lookup"><span data-stu-id="6221b-152">The following example illustrates an abstract method `Rotate` that has a default implementation, the equivalent of a .NET Framework virtual method.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3403.fs)]

<span data-ttu-id="6221b-153">Im folgenden Beispiel wird eine abgeleitete Klasse veranschaulicht, die eine Basisklassen Methode überschreibt.</span><span class="sxs-lookup"><span data-stu-id="6221b-153">The following example illustrates a derived class that overrides a base class method.</span></span> <span data-ttu-id="6221b-154">In diesem Fall wird das Verhalten durch die-Überschreibung geändert, sodass die-Methode nichts bewirkt.</span><span class="sxs-lookup"><span data-stu-id="6221b-154">In this case, the override changes the behavior so that the method does nothing.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3404.fs)]

## <a name="overloaded-methods"></a><span data-ttu-id="6221b-155">Überladene Methoden</span><span class="sxs-lookup"><span data-stu-id="6221b-155">Overloaded Methods</span></span>

<span data-ttu-id="6221b-156">Überladene Methoden sind Methoden, die über identische Namen in einem bestimmten Typ verfügen, aber über unterschiedliche Argumente verfügen.</span><span class="sxs-lookup"><span data-stu-id="6221b-156">Overloaded methods are methods that have identical names in a given type but that have different arguments.</span></span> <span data-ttu-id="6221b-157">In F#werden in der Regel optionale Argumente anstelle von überladenen Methoden verwendet.</span><span class="sxs-lookup"><span data-stu-id="6221b-157">In F#, optional arguments are usually used instead of overloaded methods.</span></span> <span data-ttu-id="6221b-158">Allerdings sind überladene Methoden in der Sprache zulässig, vorausgesetzt, dass sich die Argumente in der tupelform und nicht in der Cursor Form befinden.</span><span class="sxs-lookup"><span data-stu-id="6221b-158">However, overloaded methods are permitted in the language, provided that the arguments are in tuple form, not curried form.</span></span>

## <a name="optional-arguments"></a><span data-ttu-id="6221b-159">Optionale Argumente</span><span class="sxs-lookup"><span data-stu-id="6221b-159">Optional Arguments</span></span>

<span data-ttu-id="6221b-160">Ab F# 4,1 können Sie auch optionale Argumente mit einem Standardparameter Wert in-Methoden haben.</span><span class="sxs-lookup"><span data-stu-id="6221b-160">Starting with F# 4.1, you can also have optional arguments with a default parameter value in methods.</span></span>  <span data-ttu-id="6221b-161">Dies dient der Erleichterung der Interoperation mit C# Code.</span><span class="sxs-lookup"><span data-stu-id="6221b-161">This is to help facilitate interoperation with C# code.</span></span>  <span data-ttu-id="6221b-162">Im folgenden Beispiel wird die Syntax veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="6221b-162">The following example demonstrates the syntax:</span></span>

```fsharp
// A class with a method M, which takes in an optional integer argument.
type C() =
    _.M([<Optional; DefaultParameterValue(12)>] i) = i + 1
```

<span data-ttu-id="6221b-163">Beachten Sie, dass der für `DefaultParameterValue` übergebene Wert dem Eingabetyp entsprechen muss.</span><span class="sxs-lookup"><span data-stu-id="6221b-163">Note that the value passed in for `DefaultParameterValue` must match the input type.</span></span>  <span data-ttu-id="6221b-164">Im obigen Beispiel handelt es sich um einen `int`.</span><span class="sxs-lookup"><span data-stu-id="6221b-164">In the above sample, it is an `int`.</span></span>  <span data-ttu-id="6221b-165">Der Versuch, einen nicht ganzzahligen Wert in `DefaultParameterValue` zu übergeben, führt zu einem Kompilierungsfehler.</span><span class="sxs-lookup"><span data-stu-id="6221b-165">Attempting to pass a non-integer value into `DefaultParameterValue` would result in a compile error.</span></span>

## <a name="example-properties-and-methods"></a><span data-ttu-id="6221b-166">Beispiel: Eigenschaften und Methoden</span><span class="sxs-lookup"><span data-stu-id="6221b-166">Example: Properties and Methods</span></span>

<span data-ttu-id="6221b-167">Das folgende Beispiel enthält einen Typ, der Beispiele für Felder, private Funktionen, Eigenschaften und eine statische Methode enthält.</span><span class="sxs-lookup"><span data-stu-id="6221b-167">The following example contains a type that has examples of fields, private functions, properties, and a static method.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3406.fs)]

## <a name="see-also"></a><span data-ttu-id="6221b-168">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6221b-168">See also</span></span>

- [<span data-ttu-id="6221b-169">Mitglieder</span><span class="sxs-lookup"><span data-stu-id="6221b-169">Members</span></span>](index.md)
