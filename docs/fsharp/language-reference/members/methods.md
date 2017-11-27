---
title: Methoden (F#)
description: "Erfahren Sie, wie eine f#-Methode ist eine Funktion, die ein Typ, der verwendet werden, zur Verfügung stellen, und implementieren die Funktionalität und Verhalten von Objekten und Typen zugeordnet."
keywords: Visual F#, F#, funktionale Programmierung
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 1febab3b-c922-49c6-889f-c22db107710c
ms.openlocfilehash: dae31abe6bb0773671b889646c9cceb410a492cd
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="methods"></a><span data-ttu-id="37e1a-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="37e1a-104">Methods</span></span>

<span data-ttu-id="37e1a-105">Ein *Methode* ist eine Funktion, die ein Typ zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="37e1a-105">A *method* is a function that is associated with a type.</span></span> <span data-ttu-id="37e1a-106">In einer objektorientierten Programmierung werden Methoden zur Verfügung stellen, und implementieren die Funktionalität und Verhalten von Objekten und Typen verwendet.</span><span class="sxs-lookup"><span data-stu-id="37e1a-106">In object-oriented programming, methods are used to expose and implement the functionality and behavior of objects and types.</span></span>


## <a name="syntax"></a><span data-ttu-id="37e1a-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="37e1a-107">Syntax</span></span>

```fsharp
// Instance method definition.
[ attributes ]
member [inline] self-identifier.method-nameparameter-list [ : return-type ]=
    method-body

// Static method definition.
[ attributes ]
static member [inline] method-nameparameter-list [ : return-type ]=
    method-body

// Abstract method declaration or virtual dispatch slot.
[ attributes ]
abstract member self-identifier.method-name : type-signature

// Virtual method declaration and default implementation.
[ attributes ]
abstract member [inline] self-identifier.method-name : type-signature
[ attributes ]
default member [inline] self-identifier.method-nameparameter-list[ : return-type ] =
    method-body

// Override of inherited virtual method.
[ attributes ]
override member [inline] self-identifier.method-nameparameter-list [ : return-type ]=
    method-body

// Optional and DefaultParameterValue attributes on input parameters
[ attributes ]
[ modifier ] member [inline] self-identifier.method-name ([<Optional; DefaultParameterValue([ default-value ])>] input) [ : return-type ]
```

## <a name="remarks"></a><span data-ttu-id="37e1a-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="37e1a-108">Remarks</span></span>
<span data-ttu-id="37e1a-109">In der vorherigen Syntax können Sie die verschiedenen Formen von Deklarationen und Definitionen finden Sie unter.</span><span class="sxs-lookup"><span data-stu-id="37e1a-109">In the previous syntax, you can see the various forms of method declarations and definitions.</span></span> <span data-ttu-id="37e1a-110">In längeren Methodentexte ein Zeilenumbruch folgt das Gleichheitszeichen (=) und der gesamte Methodentext eingezogen ist.</span><span class="sxs-lookup"><span data-stu-id="37e1a-110">In longer method bodies, a line break follows the equal sign (=), and the whole method body is indented.</span></span>

<span data-ttu-id="37e1a-111">Attribute können auf eine Methodendeklaration angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="37e1a-111">Attributes can be applied to any method declaration.</span></span> <span data-ttu-id="37e1a-112">Die Syntax für eine Methodendefinition vorausgehen, und sind in der Regel in einer eigenen Zeile aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="37e1a-112">They precede the syntax for a method definition and are usually listed on a separate line.</span></span> <span data-ttu-id="37e1a-113">Weitere Informationen finden Sie unter [Attribute](../attributes.md).</span><span class="sxs-lookup"><span data-stu-id="37e1a-113">For more information, see [Attributes](../attributes.md).</span></span>

<span data-ttu-id="37e1a-114">Methoden können markiert werden `inline`.</span><span class="sxs-lookup"><span data-stu-id="37e1a-114">Methods can be marked `inline`.</span></span> <span data-ttu-id="37e1a-115">Informationen zu `inline` finden Sie unter [Inlinefunktionen](../functions/inline-functions.md).</span><span class="sxs-lookup"><span data-stu-id="37e1a-115">For information about `inline`, see [Inline Functions](../functions/inline-functions.md).</span></span>

<span data-ttu-id="37e1a-116">Nicht-Inlinemethoden können rekursiv im Typ verwendet werden; Es ist nicht erforderlich, explizit verwenden die `rec` Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="37e1a-116">Non-inline methods can be used recursively within the type; there is no need to explicitly use the `rec` keyword.</span></span>


## <a name="instance-methods"></a><span data-ttu-id="37e1a-117">Instanzmethoden</span><span class="sxs-lookup"><span data-stu-id="37e1a-117">Instance Methods</span></span>
<span data-ttu-id="37e1a-118">Instanzmethoden werden mit der `member` Schlüsselwort und ein *Selbstbezeichner*, gefolgt von einem Punkt (.) und den Methodennamen und Parameter.</span><span class="sxs-lookup"><span data-stu-id="37e1a-118">Instance methods are declared with the `member` keyword and a *self-identifier*, followed by a period (.) and the method name and parameters.</span></span> <span data-ttu-id="37e1a-119">Wie bei der Fall ist `let` Bindungen, die *Parameterliste* kann ein Muster sein.</span><span class="sxs-lookup"><span data-stu-id="37e1a-119">As is the case for `let` bindings, the *parameter-list* can be a pattern.</span></span> <span data-ttu-id="37e1a-120">In der Regel setzen Sie Methode, die Parameter in Klammern in Tupelform, also die Möglichkeit Methoden angezeigt werden in F# erläutert werden, wenn sie in anderen .NET Framework-Sprachen erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="37e1a-120">Typically, you enclose method parameters in parentheses in a tuple form, which is the way methods appear in F# when they are created in other .NET Framework languages.</span></span> <span data-ttu-id="37e1a-121">Allerdings Curry-Form (Parameter durch Leerzeichen voneinander getrennt) ist auch häufig und andere Muster werden ebenfalls unterstützt.</span><span class="sxs-lookup"><span data-stu-id="37e1a-121">However, the curried form (parameters separated by spaces) is also common, and other patterns are supported also.</span></span>

<span data-ttu-id="37e1a-122">Das folgende Beispiel veranschaulicht die Definition und Verwendung von einer nicht abstrakten Instanzmethode auf.</span><span class="sxs-lookup"><span data-stu-id="37e1a-122">The following example illustrates the definition and use of a non-abstract instance method.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3401.fs)]

<span data-ttu-id="37e1a-123">Innerhalb von Instanzmethoden verwenden Sie nicht des Selbstbezeichners Zugriff Feldern mit Let-Bindungen definiert.</span><span class="sxs-lookup"><span data-stu-id="37e1a-123">Within instance methods, do not use the self identifier to access fields defined by using let bindings.</span></span> <span data-ttu-id="37e1a-124">Verwenden Sie beim Zugriff auf andere Elemente und Eigenschaften des Selbstbezeichners.</span><span class="sxs-lookup"><span data-stu-id="37e1a-124">Use the self identifier when accessing other members and properties.</span></span>


## <a name="static-methods"></a><span data-ttu-id="37e1a-125">Statische Methoden</span><span class="sxs-lookup"><span data-stu-id="37e1a-125">Static Methods</span></span>
<span data-ttu-id="37e1a-126">Das Schlüsselwort `static` wird verwendet, um anzugeben, dass eine Methode ohne Instanz aufgerufen werden kann und keine Objektinstanz zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="37e1a-126">The keyword `static` is used to specify that a method can be called without an instance and is not associated with an object instance.</span></span> <span data-ttu-id="37e1a-127">Andernfalls sind Methoden Instanzmethoden.</span><span class="sxs-lookup"><span data-stu-id="37e1a-127">Otherwise, methods are instance methods.</span></span>

<span data-ttu-id="37e1a-128">Im Beispiel im nächsten Abschnitt zeigt Felder an, die mit deklariert die `let` Schlüsselwort, Eigenschaftenmember deklariert, mit der `member` -Schlüsselwort verwenden und eine statische Methode deklariert, mit der `static` Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="37e1a-128">The example in the next section shows fields declared with the `let` keyword, property members declared with the `member` keyword, and a static method declared with the `static` keyword.</span></span>

<span data-ttu-id="37e1a-129">Das folgende Beispiel veranschaulicht die Definition und Verwendung von statischen Methoden.</span><span class="sxs-lookup"><span data-stu-id="37e1a-129">The following example illustrates the definition and use of static methods.</span></span> <span data-ttu-id="37e1a-130">Angenommen, dass diese Methodendefinitionen sind die `SomeType` Klasse im vorherigen Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="37e1a-130">Assume that these method definitions are in the `SomeType` class in the previous section.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3402.fs)]

## <a name="abstract-and-virtual-methods"></a><span data-ttu-id="37e1a-131">Abstrakte und virtuelle Methoden</span><span class="sxs-lookup"><span data-stu-id="37e1a-131">Abstract and Virtual Methods</span></span>
<span data-ttu-id="37e1a-132">Das Schlüsselwort `abstract` gibt an, dass eine Methode verfügt über einen virtuellen Dispatch-Slot und möglicherweise nicht in der Klasse.</span><span class="sxs-lookup"><span data-stu-id="37e1a-132">The keyword `abstract` indicates that a method has a virtual dispatch slot and might not have a definition in the class.</span></span> <span data-ttu-id="37e1a-133">Ein *virtuellen Dispatch-Slot* wird ein Eintrag in einer internen Tabelle von Funktionen, die zur Laufzeit verwendet wird, suchen Sie die virtuelle Funktion, die in einem Typ mit dem objektorientierten aufruft.</span><span class="sxs-lookup"><span data-stu-id="37e1a-133">A *virtual dispatch slot* is an entry in an internally maintained table of functions that is used at run time to look up virtual function calls in an object-oriented type.</span></span> <span data-ttu-id="37e1a-134">Der virtuelle Dispatchmechanismus ist der Mechanismus, der implementiert *Polymorphie*, ein wichtiges Feature von einer objektorientierten Programmierung.</span><span class="sxs-lookup"><span data-stu-id="37e1a-134">The virtual dispatch mechanism is the mechanism that implements *polymorphism*, an important feature of object-oriented programming.</span></span> <span data-ttu-id="37e1a-135">Ist eine Klasse, die mindestens eine abstrakte Methode ohne Definition verfügt über eine *abstrakte Klasse*, was bedeutet, dass keine Instanz dieser Klasse erstellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="37e1a-135">A class that has at least one abstract method without a definition is an *abstract class*, which means that no instances can be created of that class.</span></span> <span data-ttu-id="37e1a-136">Weitere Informationen zu abstrakten Klassen finden Sie unter [abstrakte Klassen](../abstract-classes.md).</span><span class="sxs-lookup"><span data-stu-id="37e1a-136">For more information about abstract classes, see [Abstract Classes](../abstract-classes.md).</span></span>

<span data-ttu-id="37e1a-137">Abstrakten Methodendeklarationen enthalten keine keinen Methodentext.</span><span class="sxs-lookup"><span data-stu-id="37e1a-137">Abstract method declarations do not include a method body.</span></span> <span data-ttu-id="37e1a-138">Stattdessen folgt der Name der Methode von einem Doppelpunkt (:)) und eine Typsignatur für die Methode.</span><span class="sxs-lookup"><span data-stu-id="37e1a-138">Instead, the name of the method is followed by a colon (:) and a type signature for the method.</span></span> <span data-ttu-id="37e1a-139">Die Typsignatur einer Methode ist identisch, die von IntelliSense angezeigt werden, wenn Sie den Mauszeiger über den Namen einer Methode im Code-Editor von Visual Studio außer ohne Parameternamen anhalten.</span><span class="sxs-lookup"><span data-stu-id="37e1a-139">The type signature of a method is the same as that shown by IntelliSense when you pause the mouse pointer over a method name in the Visual Studio Code Editor, except without parameter names.</span></span> <span data-ttu-id="37e1a-140">Typsignaturen werden ebenfalls von den Interpreter fsi.exe, angezeigt, wenn Sie interaktiv arbeiten.</span><span class="sxs-lookup"><span data-stu-id="37e1a-140">Type signatures are also displayed by the interpreter, fsi.exe, when you are working interactively.</span></span> <span data-ttu-id="37e1a-141">Die Typsignatur einer Methode wird durch die Typen der Parameter, gefolgt von den Rückgabetyp mit entsprechenden Trennzeichensymbole gebildet.</span><span class="sxs-lookup"><span data-stu-id="37e1a-141">The type signature of a method is formed by listing out the types of the parameters, followed by the return type, with appropriate separator symbols.</span></span> <span data-ttu-id="37e1a-142">Mit Currying Parameter werden getrennt vom `->` und Tupel-Parameter werden getrennt vom `*`.</span><span class="sxs-lookup"><span data-stu-id="37e1a-142">Curried parameters are separated by `->` and tuple parameters are separated by `*`.</span></span> <span data-ttu-id="37e1a-143">Der Rückgabewert ist immer aus den Argumenten von getrennt ein `->` Symbol.</span><span class="sxs-lookup"><span data-stu-id="37e1a-143">The return value is always separated from the arguments by a `->` symbol.</span></span> <span data-ttu-id="37e1a-144">Klammern können verwendet werden, zu komplexe Parameter, z. B. wenn ein Funktionstyp einen Parameter, wird Gruppe oder um anzugeben, wenn ein Tupel als einen einzelnen Parameter anstatt als zwei Parameter behandelt wird.</span><span class="sxs-lookup"><span data-stu-id="37e1a-144">Parentheses can be used to group complex parameters, such as when a function type is a parameter, or to indicate when a tuple is treated as a single parameter rather than as two parameters.</span></span>

<span data-ttu-id="37e1a-145">Sie können auch geben abstrakte Methoden Default-Definitionen durch die Definition der Klasse hinzufügen und mithilfe der `default` -Schlüsselwort, wie in der Syntaxblock in diesem Thema gezeigt.</span><span class="sxs-lookup"><span data-stu-id="37e1a-145">You can also give abstract methods default definitions by adding the definition to the class and using the `default` keyword, as shown in the syntax block in this topic.</span></span> <span data-ttu-id="37e1a-146">Eine abstrakte Methode, die eine Definition in der gleichen Klasse hat entspricht eine virtuelle Methode in anderen .NET Framework-Sprachen.</span><span class="sxs-lookup"><span data-stu-id="37e1a-146">An abstract method that has a definition in the same class is equivalent to a virtual method in other .NET Framework languages.</span></span> <span data-ttu-id="37e1a-147">Gibt an, ob eine Definition vorhanden ist, die `abstract` Schlüsselwort erstellt einen neuen Dispatch-Platz in die virtuelle Funktionstabelle für die Klasse.</span><span class="sxs-lookup"><span data-stu-id="37e1a-147">Whether or not a definition exists, the `abstract` keyword creates a new dispatch slot in the virtual function table for the class.</span></span>

<span data-ttu-id="37e1a-148">Unabhängig davon, ob eine Basisklasse abstrakten Methoden implementiert können abgeleitete Klassen die Implementierung der abstrakten Methoden angeben.</span><span class="sxs-lookup"><span data-stu-id="37e1a-148">Regardless of whether a base class implements its abstract methods, derived classes can provide implementations of abstract methods.</span></span> <span data-ttu-id="37e1a-149">Um eine abstrakte Methode in einer abgeleiteten Klasse zu implementieren, definieren Sie eine Methode mit dem gleichen Namen und derselben Signatur in der abgeleiteten Klasse, mit Ausnahme der Verwendung der `override` oder `default` -Schlüsselwort, und geben Sie den Methodentext.</span><span class="sxs-lookup"><span data-stu-id="37e1a-149">To implement an abstract method in a derived class, define a method that has the same name and signature in the derived class, except use the `override` or `default` keyword, and provide the method body.</span></span> <span data-ttu-id="37e1a-150">Die Schlüsselwörter `override` und `default` genau dieselbe Bedeutung.</span><span class="sxs-lookup"><span data-stu-id="37e1a-150">The keywords `override` and `default` mean exactly the same thing.</span></span> <span data-ttu-id="37e1a-151">Verwenden Sie `override` verwenden, wenn die neue Methode überschreibt die basisklassenimplementierung; `default` beim Erstellen einer Implementierung in der gleichen Klasse wie die ursprüngliche abstrakte Deklaration.</span><span class="sxs-lookup"><span data-stu-id="37e1a-151">Use `override` if the new method overrides a base class implementation; use `default` when you create an implementation in the same class as the original abstract declaration.</span></span> <span data-ttu-id="37e1a-152">Verwenden Sie nicht die `abstract` -Schlüsselwort in der Methode, die die Methode implementiert, die in der Basisklasse abstrakt deklariert wurde.</span><span class="sxs-lookup"><span data-stu-id="37e1a-152">Do not use the `abstract` keyword on the method that implements the method that was declared abstract in the base class.</span></span>

<span data-ttu-id="37e1a-153">Das folgende Beispiel veranschaulicht eine abstrakte Methode `Rotate` , besitzt eine Standardimplementierung, die Entsprechung einer virtuellen .NET Framework-Methode.</span><span class="sxs-lookup"><span data-stu-id="37e1a-153">The following example illustrates an abstract method `Rotate` that has a default implementation, the equivalent of a .NET Framework virtual method.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3403.fs)]

<span data-ttu-id="37e1a-154">Das folgende Beispiel veranschaulicht eine abgeleitete Klasse, die eine Basisklassenmethode überschreibt.</span><span class="sxs-lookup"><span data-stu-id="37e1a-154">The following example illustrates a derived class that overrides a base class method.</span></span> <span data-ttu-id="37e1a-155">In diesem Fall ändert die Überschreibung das Verhalten, damit die Methode keine Aktionen ausführt.</span><span class="sxs-lookup"><span data-stu-id="37e1a-155">In this case, the override changes the behavior so that the method does nothing.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3404.fs)]

## <a name="overloaded-methods"></a><span data-ttu-id="37e1a-156">Überladene Methoden</span><span class="sxs-lookup"><span data-stu-id="37e1a-156">Overloaded Methods</span></span>
<span data-ttu-id="37e1a-157">Überladene Methoden sind Methoden, die über identische Namen in einem bestimmten Typ verfügen, die über andere Argumente verfügen.</span><span class="sxs-lookup"><span data-stu-id="37e1a-157">Overloaded methods are methods that have identical names in a given type but that have different arguments.</span></span> <span data-ttu-id="37e1a-158">In F# erläutert werden werden optionale Argumente in der Regel überladene Methoden verwendet.</span><span class="sxs-lookup"><span data-stu-id="37e1a-158">In F#, optional arguments are usually used instead of overloaded methods.</span></span> <span data-ttu-id="37e1a-159">Überladene Methoden sind jedoch in der Sprache zulässig, vorausgesetzt, dass die Argumente in Tupelform und nicht mit Currying Formular sind.</span><span class="sxs-lookup"><span data-stu-id="37e1a-159">However, overloaded methods are permitted in the language, provided that the arguments are in tuple form, not curried form.</span></span>

## <a name="optional-arguments"></a><span data-ttu-id="37e1a-160">Optionale Argumente</span><span class="sxs-lookup"><span data-stu-id="37e1a-160">Optional Arguments</span></span>

<span data-ttu-id="37e1a-161">Ab f# 4.1, können Sie auch optionale Argumente mit einem Standard-Parameterwert in Methoden verfügen.</span><span class="sxs-lookup"><span data-stu-id="37e1a-161">Starting with F# 4.1, you can also have optional arguments with a default parameter value in methods.</span></span>  <span data-ttu-id="37e1a-162">Dies ist die Interoperation mit C#-Code zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="37e1a-162">This is to help facilitate interoperation with C# code.</span></span>  <span data-ttu-id="37e1a-163">Im folgende Beispiel wird die Syntax veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="37e1a-163">The following example demonstrates the syntax:</span></span>

```fsharp
// A class with a method M, which takes in an optional integer argument.
type C() =
    __.M([<Optional; DefaultParameterValue(12)>] i) = i + 1
```

<span data-ttu-id="37e1a-164">Beachten Sie, die für der Wert übergeben `DefaultParameterValue` muss den Typ der Eingabe übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="37e1a-164">Note that the value passed in for `DefaultParameterValue` must match the input type.</span></span>  <span data-ttu-id="37e1a-165">Im obigen Beispiel ist ein `int`.</span><span class="sxs-lookup"><span data-stu-id="37e1a-165">In the above sample, it is an `int`.</span></span>  <span data-ttu-id="37e1a-166">Bei dem Versuch, einen nicht ganzzahlige Wert übergeben `DefaultParameterValue` in einem Kompilierungsfehler führen würde.</span><span class="sxs-lookup"><span data-stu-id="37e1a-166">Attempting to pass a non-integer value into `DefaultParameterValue` would result in a compile error.</span></span>

## <a name="example-properties-and-methods"></a><span data-ttu-id="37e1a-167">Beispiel: Eigenschaften und Methoden</span><span class="sxs-lookup"><span data-stu-id="37e1a-167">Example: Properties and Methods</span></span>
<span data-ttu-id="37e1a-168">Das folgende Beispiel enthält einen Typ, der Beispiele für Felder, private Funktionen, Eigenschaften und eine statische Methode enthält.</span><span class="sxs-lookup"><span data-stu-id="37e1a-168">The following example contains a type that has examples of fields, private functions, properties, and a static method.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3406.fs)]

## <a name="see-also"></a><span data-ttu-id="37e1a-169">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="37e1a-169">See Also</span></span>
[<span data-ttu-id="37e1a-170">Mitglieder</span><span class="sxs-lookup"><span data-stu-id="37e1a-170">Members</span></span>](index.md)
