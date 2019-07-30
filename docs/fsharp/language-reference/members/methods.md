---
title: Methoden
description: Erfahren Sie, F# wie eine Methode eine Funktion ist, die einem Typ zugeordnet ist, mit dem die Funktionen und das Verhalten von Objekten und Typen verfügbar gemacht und implementiert werden.
ms.date: 05/16/2016
ms.openlocfilehash: 13503690a59ace13dacba93b6fce9ea3240c5cc2
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "68627438"
---
# <a name="methods"></a><span data-ttu-id="0f54d-103">Methoden</span><span class="sxs-lookup"><span data-stu-id="0f54d-103">Methods</span></span>

<span data-ttu-id="0f54d-104">Eine *Methode* ist eine-Funktion, die einem-Typ zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="0f54d-104">A *method* is a function that is associated with a type.</span></span> <span data-ttu-id="0f54d-105">Bei der objektorientierten Programmierung werden Methoden verwendet, um die Funktionalität und das Verhalten von Objekten und Typen verfügbar zu machen und zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="0f54d-105">In object-oriented programming, methods are used to expose and implement the functionality and behavior of objects and types.</span></span>

## <a name="syntax"></a><span data-ttu-id="0f54d-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="0f54d-106">Syntax</span></span>

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

## <a name="remarks"></a><span data-ttu-id="0f54d-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0f54d-107">Remarks</span></span>

<span data-ttu-id="0f54d-108">In der vorherigen Syntax können Sie die verschiedenen Formen von Methoden Deklarationen und-Definitionen sehen.</span><span class="sxs-lookup"><span data-stu-id="0f54d-108">In the previous syntax, you can see the various forms of method declarations and definitions.</span></span> <span data-ttu-id="0f54d-109">In längeren Methoden Texten folgt ein Zeilenumbruch dem Gleichheitszeichen (=), und der gesamte Methoden Text wird eingezogen.</span><span class="sxs-lookup"><span data-stu-id="0f54d-109">In longer method bodies, a line break follows the equal sign (=), and the whole method body is indented.</span></span>

<span data-ttu-id="0f54d-110">Attribute können auf jede Methoden Deklaration angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="0f54d-110">Attributes can be applied to any method declaration.</span></span> <span data-ttu-id="0f54d-111">Sie sind der Syntax für eine Methoden Definition vorangestellt und werden in der Regel in einer separaten Zeile aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="0f54d-111">They precede the syntax for a method definition and are usually listed on a separate line.</span></span> <span data-ttu-id="0f54d-112">Weitere Informationen finden Sie unter [Attribute](../attributes.md).</span><span class="sxs-lookup"><span data-stu-id="0f54d-112">For more information, see [Attributes](../attributes.md).</span></span>

<span data-ttu-id="0f54d-113">Methoden können als gekennzeichnet `inline`werden.</span><span class="sxs-lookup"><span data-stu-id="0f54d-113">Methods can be marked `inline`.</span></span> <span data-ttu-id="0f54d-114">Informationen zu `inline` finden Sie unter [Inlinefunktionen](../functions/inline-functions.md).</span><span class="sxs-lookup"><span data-stu-id="0f54d-114">For information about `inline`, see [Inline Functions](../functions/inline-functions.md).</span></span>

<span data-ttu-id="0f54d-115">Nicht Inline-Methoden können rekursiv innerhalb des Typs verwendet werden. Es ist nicht erforderlich, explizit das `rec` Schlüsselwort zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="0f54d-115">Non-inline methods can be used recursively within the type; there is no need to explicitly use the `rec` keyword.</span></span>

## <a name="instance-methods"></a><span data-ttu-id="0f54d-116">Instanzmethoden</span><span class="sxs-lookup"><span data-stu-id="0f54d-116">Instance Methods</span></span>

<span data-ttu-id="0f54d-117">Instanzmethoden werden mit dem `member` -Schlüsselwort und einem *selbst Bezeichner*, gefolgt von einem-Wert (.) und dem Methodennamen und-Parametern, deklariert.</span><span class="sxs-lookup"><span data-stu-id="0f54d-117">Instance methods are declared with the `member` keyword and a *self-identifier*, followed by a period (.) and the method name and parameters.</span></span> <span data-ttu-id="0f54d-118">Wie bei `let` Bindungen, kann die *Parameter-List* ein Muster sein.</span><span class="sxs-lookup"><span data-stu-id="0f54d-118">As is the case for `let` bindings, the *parameter-list* can be a pattern.</span></span> <span data-ttu-id="0f54d-119">In der Regel setzen Sie Methode, die Parameter in Klammern in einem Formular handelt es sich die Methoden wie Tupel werden angezeigt in F#, wenn sie in anderen .NET Framework-Sprachen erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="0f54d-119">Typically, you enclose method parameters in parentheses in a tuple form, which is the way methods appear in F# when they are created in other .NET Framework languages.</span></span> <span data-ttu-id="0f54d-120">Das Curry-Formular (durch Leerzeichen getrennte Parameter) ist jedoch ebenfalls üblich, und andere Muster werden ebenfalls unterstützt.</span><span class="sxs-lookup"><span data-stu-id="0f54d-120">However, the curried form (parameters separated by spaces) is also common, and other patterns are supported also.</span></span>

<span data-ttu-id="0f54d-121">Im folgenden Beispiel werden die Definition und die Verwendung einer nicht abstrakten Instanzmethode veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="0f54d-121">The following example illustrates the definition and use of a non-abstract instance method.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3401.fs)]

<span data-ttu-id="0f54d-122">Verwenden Sie in Instanzmethoden den Self-Identifier nicht für den Zugriff auf Felder, die mithilfe von let-Bindungen definiert wurden.</span><span class="sxs-lookup"><span data-stu-id="0f54d-122">Within instance methods, do not use the self identifier to access fields defined by using let bindings.</span></span> <span data-ttu-id="0f54d-123">Verwenden Sie den selbst Bezeichner, wenn Sie auf andere Member und Eigenschaften zugreifen.</span><span class="sxs-lookup"><span data-stu-id="0f54d-123">Use the self identifier when accessing other members and properties.</span></span>

## <a name="static-methods"></a><span data-ttu-id="0f54d-124">Statische Methoden</span><span class="sxs-lookup"><span data-stu-id="0f54d-124">Static Methods</span></span>

<span data-ttu-id="0f54d-125">Das- `static` Schlüsselwort wird verwendet, um anzugeben, dass eine Methode ohne eine-Instanz aufgerufen werden kann und keiner Objektinstanz zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="0f54d-125">The keyword `static` is used to specify that a method can be called without an instance and is not associated with an object instance.</span></span> <span data-ttu-id="0f54d-126">Andernfalls sind Methoden Instanzmethoden.</span><span class="sxs-lookup"><span data-stu-id="0f54d-126">Otherwise, methods are instance methods.</span></span>

<span data-ttu-id="0f54d-127">Das Beispiel im nächsten Abschnitt zeigt Felder, die mit dem `let` -Schlüsselwort deklariert werden, mit `member` dem-Schlüsselwort deklarierte Eigenschaften und eine `static` statische Methode, die mit dem-Schlüsselwort deklariert wurde.</span><span class="sxs-lookup"><span data-stu-id="0f54d-127">The example in the next section shows fields declared with the `let` keyword, property members declared with the `member` keyword, and a static method declared with the `static` keyword.</span></span>

<span data-ttu-id="0f54d-128">Das folgende Beispiel veranschaulicht die Definition und Verwendung statischer Methoden.</span><span class="sxs-lookup"><span data-stu-id="0f54d-128">The following example illustrates the definition and use of static methods.</span></span> <span data-ttu-id="0f54d-129">Nehmen Sie an, dass sich diese Methoden `SomeType` Definitionen in der-Klasse des vorherigen Abschnitts befinden.</span><span class="sxs-lookup"><span data-stu-id="0f54d-129">Assume that these method definitions are in the `SomeType` class in the previous section.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3402.fs)]

## <a name="abstract-and-virtual-methods"></a><span data-ttu-id="0f54d-130">Abstrakte und virtuelle Methoden</span><span class="sxs-lookup"><span data-stu-id="0f54d-130">Abstract and Virtual Methods</span></span>

<span data-ttu-id="0f54d-131">Das Schlüssel `abstract` Wort gibt an, dass eine Methode einen virtuellen dispatchslot hat und möglicherweise keine Definition in der Klasse aufweist.</span><span class="sxs-lookup"><span data-stu-id="0f54d-131">The keyword `abstract` indicates that a method has a virtual dispatch slot and might not have a definition in the class.</span></span> <span data-ttu-id="0f54d-132">Ein *virtueller dispatchslot* ist ein Eintrag in einer intern verwalteten Tabelle von Funktionen, die zur Laufzeit verwendet wird, um virtuelle Funktionsaufrufe in einem objektorientierten Typ zu suchen.</span><span class="sxs-lookup"><span data-stu-id="0f54d-132">A *virtual dispatch slot* is an entry in an internally maintained table of functions that is used at run time to look up virtual function calls in an object-oriented type.</span></span> <span data-ttu-id="0f54d-133">Der virtuelle Dispatchmechanismus ist der Mechanismus, der *Polymorphie*implementiert, ein wichtiges Feature der objektorientierten Programmierung.</span><span class="sxs-lookup"><span data-stu-id="0f54d-133">The virtual dispatch mechanism is the mechanism that implements *polymorphism*, an important feature of object-oriented programming.</span></span> <span data-ttu-id="0f54d-134">Eine Klasse, die über mindestens eine abstrakte Methode ohne Definition verfügt, ist eine *abstrakte Klasse*, was bedeutet, dass keine Instanzen dieser Klasse erstellt werden können.</span><span class="sxs-lookup"><span data-stu-id="0f54d-134">A class that has at least one abstract method without a definition is an *abstract class*, which means that no instances can be created of that class.</span></span> <span data-ttu-id="0f54d-135">Weitere Informationen zu abstrakten Klassen finden Sie unter [abstrakte Klassen](../abstract-classes.md).</span><span class="sxs-lookup"><span data-stu-id="0f54d-135">For more information about abstract classes, see [Abstract Classes](../abstract-classes.md).</span></span>

<span data-ttu-id="0f54d-136">Abstrakte Methoden Deklarationen enthalten keinen Methoden Text.</span><span class="sxs-lookup"><span data-stu-id="0f54d-136">Abstract method declarations do not include a method body.</span></span> <span data-ttu-id="0f54d-137">Stattdessen folgt der Name der Methode einem Doppelpunkt (:) und eine Typsignatur für die Methode.</span><span class="sxs-lookup"><span data-stu-id="0f54d-137">Instead, the name of the method is followed by a colon (:) and a type signature for the method.</span></span> <span data-ttu-id="0f54d-138">Die Typsignatur einer Methode ist identisch mit der, die von IntelliSense angezeigt wird, wenn Sie den Mauszeiger über einen Methodennamen im Visual Studio Code-Editor bewegen, außer ohne Parameternamen.</span><span class="sxs-lookup"><span data-stu-id="0f54d-138">The type signature of a method is the same as that shown by IntelliSense when you pause the mouse pointer over a method name in the Visual Studio Code Editor, except without parameter names.</span></span> <span data-ttu-id="0f54d-139">Typsignaturen werden auch vom Interpreter "FSI. exe" angezeigt, wenn Sie interaktiv arbeiten.</span><span class="sxs-lookup"><span data-stu-id="0f54d-139">Type signatures are also displayed by the interpreter, fsi.exe, when you are working interactively.</span></span> <span data-ttu-id="0f54d-140">Die Typsignatur einer Methode wird gebildet, indem die Typen der Parameter, gefolgt vom Rückgabetyp, mit entsprechenden Trennzeichen aufgelistet werden.</span><span class="sxs-lookup"><span data-stu-id="0f54d-140">The type signature of a method is formed by listing out the types of the parameters, followed by the return type, with appropriate separator symbols.</span></span> <span data-ttu-id="0f54d-141">Curry-Parameter werden durch `->` getrennt, und tupelparameter werden durch `*`getrennt.</span><span class="sxs-lookup"><span data-stu-id="0f54d-141">Curried parameters are separated by `->` and tuple parameters are separated by `*`.</span></span> <span data-ttu-id="0f54d-142">Der Rückgabewert wird immer von den Argumenten durch ein `->` Symbol getrennt.</span><span class="sxs-lookup"><span data-stu-id="0f54d-142">The return value is always separated from the arguments by a `->` symbol.</span></span> <span data-ttu-id="0f54d-143">Klammern können verwendet werden, um komplexe Parameter zu gruppieren, z. b. Wenn ein Funktionstyp ein Parameter ist, oder um anzugeben, dass ein Tupel als einzelner Parameter und nicht als zwei Parameter behandelt wird.</span><span class="sxs-lookup"><span data-stu-id="0f54d-143">Parentheses can be used to group complex parameters, such as when a function type is a parameter, or to indicate when a tuple is treated as a single parameter rather than as two parameters.</span></span>

<span data-ttu-id="0f54d-144">Sie können auch abstrakten Methoden Standarddefinitionen übergeben, indem Sie die Definition der-Klasse hinzufügen `default` und das-Schlüsselwort verwenden, wie im Syntax Block in diesem Thema gezeigt.</span><span class="sxs-lookup"><span data-stu-id="0f54d-144">You can also give abstract methods default definitions by adding the definition to the class and using the `default` keyword, as shown in the syntax block in this topic.</span></span> <span data-ttu-id="0f54d-145">Eine abstrakte Methode, die eine Definition in derselben Klasse aufweist, entspricht einer virtuellen Methode in anderen .NET Framework Sprachen.</span><span class="sxs-lookup"><span data-stu-id="0f54d-145">An abstract method that has a definition in the same class is equivalent to a virtual method in other .NET Framework languages.</span></span> <span data-ttu-id="0f54d-146">Unabhängig davon, ob eine Definition vorhanden ist `abstract` , erstellt das Schlüsselwort einen neuen dispatchslot in der virtuellen Funktions Tabelle für die Klasse.</span><span class="sxs-lookup"><span data-stu-id="0f54d-146">Whether or not a definition exists, the `abstract` keyword creates a new dispatch slot in the virtual function table for the class.</span></span>

<span data-ttu-id="0f54d-147">Unabhängig davon, ob eine Basisklasse die abstrakten Methoden implementiert, können abgeleitete Klassen Implementierungen abstrakter Methoden bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="0f54d-147">Regardless of whether a base class implements its abstract methods, derived classes can provide implementations of abstract methods.</span></span> <span data-ttu-id="0f54d-148">Um eine abstrakte Methode in einer abgeleiteten Klasse zu implementieren, definieren Sie eine Methode, die den gleichen Namen und die gleiche Signatur in der abgeleiteten `default` Klasse aufweist, mit Ausnahme des `override` -oder-Schlüssel Worts, und stellen den Methoden Text bereit.</span><span class="sxs-lookup"><span data-stu-id="0f54d-148">To implement an abstract method in a derived class, define a method that has the same name and signature in the derived class, except use the `override` or `default` keyword, and provide the method body.</span></span> <span data-ttu-id="0f54d-149">Die Schlüssel `override` Wörter `default` und bedeuten genau dasselbe.</span><span class="sxs-lookup"><span data-stu-id="0f54d-149">The keywords `override` and `default` mean exactly the same thing.</span></span> <span data-ttu-id="0f54d-150">Verwenden `override` Sie, wenn die neue Methode eine Basisklassen Implementierung überschreibt `default` . verwenden Sie diese Methode, wenn Sie in derselben Klasse wie die ursprüngliche abstrakte Deklaration eine Implementierung erstellen.</span><span class="sxs-lookup"><span data-stu-id="0f54d-150">Use `override` if the new method overrides a base class implementation; use `default` when you create an implementation in the same class as the original abstract declaration.</span></span> <span data-ttu-id="0f54d-151">Verwenden Sie das `abstract` -Schlüsselwort nicht für die Methode, die die Methode implementiert, die in der Basisklasse als abstrakt deklariert wurde.</span><span class="sxs-lookup"><span data-stu-id="0f54d-151">Do not use the `abstract` keyword on the method that implements the method that was declared abstract in the base class.</span></span>

<span data-ttu-id="0f54d-152">Das folgende Beispiel veranschaulicht eine abstrakte Methode `Rotate` mit einer Standard Implementierung, die einer .NET Framework virtuellen Methode entspricht.</span><span class="sxs-lookup"><span data-stu-id="0f54d-152">The following example illustrates an abstract method `Rotate` that has a default implementation, the equivalent of a .NET Framework virtual method.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3403.fs)]

<span data-ttu-id="0f54d-153">Im folgenden Beispiel wird eine abgeleitete Klasse veranschaulicht, die eine Basisklassen Methode überschreibt.</span><span class="sxs-lookup"><span data-stu-id="0f54d-153">The following example illustrates a derived class that overrides a base class method.</span></span> <span data-ttu-id="0f54d-154">In diesem Fall wird das Verhalten durch die-Überschreibung geändert, sodass die-Methode nichts bewirkt.</span><span class="sxs-lookup"><span data-stu-id="0f54d-154">In this case, the override changes the behavior so that the method does nothing.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3404.fs)]

## <a name="overloaded-methods"></a><span data-ttu-id="0f54d-155">Überladene Methoden</span><span class="sxs-lookup"><span data-stu-id="0f54d-155">Overloaded Methods</span></span>

<span data-ttu-id="0f54d-156">Überladene Methoden sind Methoden, die über identische Namen in einem bestimmten Typ verfügen, aber über unterschiedliche Argumente verfügen.</span><span class="sxs-lookup"><span data-stu-id="0f54d-156">Overloaded methods are methods that have identical names in a given type but that have different arguments.</span></span> <span data-ttu-id="0f54d-157">In F# sind optionale Argumente in der Regel überladene Methoden verwendet.</span><span class="sxs-lookup"><span data-stu-id="0f54d-157">In F#, optional arguments are usually used instead of overloaded methods.</span></span> <span data-ttu-id="0f54d-158">Allerdings sind überladene Methoden in der Sprache zulässig, vorausgesetzt, dass sich die Argumente in der tupelform und nicht in der Cursor Form befinden.</span><span class="sxs-lookup"><span data-stu-id="0f54d-158">However, overloaded methods are permitted in the language, provided that the arguments are in tuple form, not curried form.</span></span>

## <a name="optional-arguments"></a><span data-ttu-id="0f54d-159">Optionale Argumente</span><span class="sxs-lookup"><span data-stu-id="0f54d-159">Optional Arguments</span></span>

<span data-ttu-id="0f54d-160">Ab F# 4.1, können Sie auch optionale Argumente hat den Standardwert des Parameters in Methoden verfügen.</span><span class="sxs-lookup"><span data-stu-id="0f54d-160">Starting with F# 4.1, you can also have optional arguments with a default parameter value in methods.</span></span>  <span data-ttu-id="0f54d-161">Dies dient der Erleichterung der Interoperation mit C# Code.</span><span class="sxs-lookup"><span data-stu-id="0f54d-161">This is to help facilitate interoperation with C# code.</span></span>  <span data-ttu-id="0f54d-162">Im folgenden Beispiel wird die Syntax veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="0f54d-162">The following example demonstrates the syntax:</span></span>

```fsharp
// A class with a method M, which takes in an optional integer argument.
type C() =
    __.M([<Optional; DefaultParameterValue(12)>] i) = i + 1
```

<span data-ttu-id="0f54d-163">Beachten Sie, dass der in `DefaultParameterValue` übergebene Wert dem Eingabetyp entsprechen muss.</span><span class="sxs-lookup"><span data-stu-id="0f54d-163">Note that the value passed in for `DefaultParameterValue` must match the input type.</span></span>  <span data-ttu-id="0f54d-164">Im obigen Beispiel ist es ein `int`.</span><span class="sxs-lookup"><span data-stu-id="0f54d-164">In the above sample, it is an `int`.</span></span>  <span data-ttu-id="0f54d-165">Der Versuch, einen nicht ganzzahligen Wert `DefaultParameterValue` in zu übergeben, führt zu einem Kompilierungsfehler.</span><span class="sxs-lookup"><span data-stu-id="0f54d-165">Attempting to pass a non-integer value into `DefaultParameterValue` would result in a compile error.</span></span>

## <a name="example-properties-and-methods"></a><span data-ttu-id="0f54d-166">Beispiel: Eigenschaften und Methoden</span><span class="sxs-lookup"><span data-stu-id="0f54d-166">Example: Properties and Methods</span></span>

<span data-ttu-id="0f54d-167">Das folgende Beispiel enthält einen Typ, der Beispiele für Felder, private Funktionen, Eigenschaften und eine statische Methode enthält.</span><span class="sxs-lookup"><span data-stu-id="0f54d-167">The following example contains a type that has examples of fields, private functions, properties, and a static method.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3406.fs)]

## <a name="see-also"></a><span data-ttu-id="0f54d-168">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0f54d-168">See also</span></span>

- [<span data-ttu-id="0f54d-169">Mitglieder</span><span class="sxs-lookup"><span data-stu-id="0f54d-169">Members</span></span>](index.md)
