---
title: Methoden (F#)
description: Erfahren Sie, wie eine F#-Methode eine Funktion, die ein Typ, der verwendet werden, um verfügbar zu machen, und implementieren Sie die Funktionalität und Verhalten von Objekten und Typen zugeordnet ist.
ms.date: 05/16/2016
ms.openlocfilehash: 02d5a7d22d1ce79a06e15462637c373b33623f61
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "43871237"
---
# <a name="methods"></a><span data-ttu-id="1b8fb-103">Methoden</span><span class="sxs-lookup"><span data-stu-id="1b8fb-103">Methods</span></span>

<span data-ttu-id="1b8fb-104">Ein *Methode* ist eine Funktion, die einem Typ zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="1b8fb-104">A *method* is a function that is associated with a type.</span></span> <span data-ttu-id="1b8fb-105">In der objektorientierten Programmierung werden Methoden verfügbar machen, und implementieren die Funktionalität und Verhalten von Objekten und Typen verwendet.</span><span class="sxs-lookup"><span data-stu-id="1b8fb-105">In object-oriented programming, methods are used to expose and implement the functionality and behavior of objects and types.</span></span>

## <a name="syntax"></a><span data-ttu-id="1b8fb-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="1b8fb-106">Syntax</span></span>

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

## <a name="remarks"></a><span data-ttu-id="1b8fb-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1b8fb-107">Remarks</span></span>

<span data-ttu-id="1b8fb-108">In der vorherigen Syntax ist sehen Sie die verschiedenen Formen von Deklarationen und Definitionen.</span><span class="sxs-lookup"><span data-stu-id="1b8fb-108">In the previous syntax, you can see the various forms of method declarations and definitions.</span></span> <span data-ttu-id="1b8fb-109">In Methodentexten länger ein Zeilenumbruch folgt das Gleichheitszeichen (=) und der gesamten Methodentext eingezogen ist.</span><span class="sxs-lookup"><span data-stu-id="1b8fb-109">In longer method bodies, a line break follows the equal sign (=), and the whole method body is indented.</span></span>

<span data-ttu-id="1b8fb-110">Attribute können auf eine Methodendeklaration angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="1b8fb-110">Attributes can be applied to any method declaration.</span></span> <span data-ttu-id="1b8fb-111">Sie die Syntax für eine Methodendefinition vorausgehen und sind in der Regel in einer eigenen Zeile aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="1b8fb-111">They precede the syntax for a method definition and are usually listed on a separate line.</span></span> <span data-ttu-id="1b8fb-112">Weitere Informationen finden Sie unter [Attribute](../attributes.md).</span><span class="sxs-lookup"><span data-stu-id="1b8fb-112">For more information, see [Attributes](../attributes.md).</span></span>

<span data-ttu-id="1b8fb-113">Methoden können markiert werden `inline`.</span><span class="sxs-lookup"><span data-stu-id="1b8fb-113">Methods can be marked `inline`.</span></span> <span data-ttu-id="1b8fb-114">Informationen zu `inline` finden Sie unter [Inlinefunktionen](../functions/inline-functions.md).</span><span class="sxs-lookup"><span data-stu-id="1b8fb-114">For information about `inline`, see [Inline Functions](../functions/inline-functions.md).</span></span>

<span data-ttu-id="1b8fb-115">Nicht-Inline-Methoden können rekursiv innerhalb des Typs verwendet werden; besteht keine Notwendigkeit, die explizit die `rec` Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="1b8fb-115">Non-inline methods can be used recursively within the type; there is no need to explicitly use the `rec` keyword.</span></span>

## <a name="instance-methods"></a><span data-ttu-id="1b8fb-116">Instanzmethoden</span><span class="sxs-lookup"><span data-stu-id="1b8fb-116">Instance Methods</span></span>

<span data-ttu-id="1b8fb-117">Instanzmethoden werden mit der `member` Schlüsselwort und *Selbstbezeichner*, gefolgt von einem Punkt (.) und dem Methodennamen und Parameter.</span><span class="sxs-lookup"><span data-stu-id="1b8fb-117">Instance methods are declared with the `member` keyword and a *self-identifier*, followed by a period (.) and the method name and parameters.</span></span> <span data-ttu-id="1b8fb-118">Wie bei der Fall ist `let` Bindungen, die *Parameterliste* kann ein Muster sein.</span><span class="sxs-lookup"><span data-stu-id="1b8fb-118">As is the case for `let` bindings, the *parameter-list* can be a pattern.</span></span> <span data-ttu-id="1b8fb-119">In der Regel setzen Sie Methode, die Parameter in Klammern in einem Formular handelt es sich die Methoden wie Tupel werden angezeigt in f#, wenn sie in anderen .NET Framework-Sprachen erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="1b8fb-119">Typically, you enclose method parameters in parentheses in a tuple form, which is the way methods appear in F# when they are created in other .NET Framework languages.</span></span> <span data-ttu-id="1b8fb-120">Allerdings wird die Curry-Form (Parameter durch Leerzeichen getrennt) ist auch üblich, und andere Muster werden ebenfalls unterstützt.</span><span class="sxs-lookup"><span data-stu-id="1b8fb-120">However, the curried form (parameters separated by spaces) is also common, and other patterns are supported also.</span></span>

<span data-ttu-id="1b8fb-121">Das folgende Beispiel veranschaulicht die Definition und Verwendung einer nicht abstrakten Instanzmethode.</span><span class="sxs-lookup"><span data-stu-id="1b8fb-121">The following example illustrates the definition and use of a non-abstract instance method.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3401.fs)]

<span data-ttu-id="1b8fb-122">Innerhalb von Instanzenmethoden verwenden Sie nicht des Selbstbezeichners Access-Feldern, die mit der Let-Bindungen definiert.</span><span class="sxs-lookup"><span data-stu-id="1b8fb-122">Within instance methods, do not use the self identifier to access fields defined by using let bindings.</span></span> <span data-ttu-id="1b8fb-123">Verwenden Sie den Self-Bezeichner, den Zugriff auf andere Elemente und Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="1b8fb-123">Use the self identifier when accessing other members and properties.</span></span>

## <a name="static-methods"></a><span data-ttu-id="1b8fb-124">Statische Methoden</span><span class="sxs-lookup"><span data-stu-id="1b8fb-124">Static Methods</span></span>

<span data-ttu-id="1b8fb-125">Das Schlüsselwort `static` wird verwendet, um anzugeben, dass eine Methode kann, ohne eine Instanz aufgerufen werden aus, und keine Objektinstanz zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="1b8fb-125">The keyword `static` is used to specify that a method can be called without an instance and is not associated with an object instance.</span></span> <span data-ttu-id="1b8fb-126">Andernfalls sind die Methoden Instanzmethoden zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="1b8fb-126">Otherwise, methods are instance methods.</span></span>

<span data-ttu-id="1b8fb-127">Im Beispiel im nächsten Abschnitt zeigt die Felder, die mit dem deklariert die `let` Schlüsselwort Eigenschaftenmember deklariert, mit der `member` -Schlüsselwort, und eine statische Methode deklariert, mit der `static` Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="1b8fb-127">The example in the next section shows fields declared with the `let` keyword, property members declared with the `member` keyword, and a static method declared with the `static` keyword.</span></span>

<span data-ttu-id="1b8fb-128">Das folgende Beispiel veranschaulicht die Definition und Verwendung von statischen Methoden.</span><span class="sxs-lookup"><span data-stu-id="1b8fb-128">The following example illustrates the definition and use of static methods.</span></span> <span data-ttu-id="1b8fb-129">Wird davon ausgegangen, dass diese Methodendefinitionen sind die `SomeType` Klasse, die im vorherigen Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="1b8fb-129">Assume that these method definitions are in the `SomeType` class in the previous section.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3402.fs)]

## <a name="abstract-and-virtual-methods"></a><span data-ttu-id="1b8fb-130">Abstrakte und virtuelle Methoden</span><span class="sxs-lookup"><span data-stu-id="1b8fb-130">Abstract and Virtual Methods</span></span>

<span data-ttu-id="1b8fb-131">Das Schlüsselwort `abstract` gibt an, dass eine Methode befindet sich einen virtueller Dispatch-Slot und kann keine Definition in der Klasse.</span><span class="sxs-lookup"><span data-stu-id="1b8fb-131">The keyword `abstract` indicates that a method has a virtual dispatch slot and might not have a definition in the class.</span></span> <span data-ttu-id="1b8fb-132">Ein *virtueller Dispatch-Slot* ist ein Eintrag in einer intern verwalteten Tabelle von Funktionen, die zur Laufzeit verwendet wird, suchen Sie die virtuelle Funktion, die in einem objektorientierten Typ aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="1b8fb-132">A *virtual dispatch slot* is an entry in an internally maintained table of functions that is used at run time to look up virtual function calls in an object-oriented type.</span></span> <span data-ttu-id="1b8fb-133">Der virtueller Dispatch-Mechanismus ist der Mechanismus, der implementiert *Polymorphie*, ein wichtiges Merkmal der objektorientierten Programmierung.</span><span class="sxs-lookup"><span data-stu-id="1b8fb-133">The virtual dispatch mechanism is the mechanism that implements *polymorphism*, an important feature of object-oriented programming.</span></span> <span data-ttu-id="1b8fb-134">Eine Klasse, die mindestens eine abstrakte Methode ohne Definition ist eine *abstrakte Klasse*, was bedeutet, dass keine Instanzen dieser Klasse erstellt werden können.</span><span class="sxs-lookup"><span data-stu-id="1b8fb-134">A class that has at least one abstract method without a definition is an *abstract class*, which means that no instances can be created of that class.</span></span> <span data-ttu-id="1b8fb-135">Weitere Informationen zu abstrakten Klassen finden Sie unter [abstrakte Klassen](../abstract-classes.md).</span><span class="sxs-lookup"><span data-stu-id="1b8fb-135">For more information about abstract classes, see [Abstract Classes](../abstract-classes.md).</span></span>

<span data-ttu-id="1b8fb-136">Abstrakte Methodendeklarationen beinhalten keinen Methodentext.</span><span class="sxs-lookup"><span data-stu-id="1b8fb-136">Abstract method declarations do not include a method body.</span></span> <span data-ttu-id="1b8fb-137">Stattdessen folgt der Name der Methode von einem Doppelpunkt (:) und eine Typsignatur für die Methode.</span><span class="sxs-lookup"><span data-stu-id="1b8fb-137">Instead, the name of the method is followed by a colon (:) and a type signature for the method.</span></span> <span data-ttu-id="1b8fb-138">Die Typsignatur einer Methode ist identisch, die von IntelliSense angezeigt werden, wenn Sie den Mauszeiger über den Namen einer Methode in der Visual Studio Code-Editor, mit Ausnahme ohne Parameternamen anhalten.</span><span class="sxs-lookup"><span data-stu-id="1b8fb-138">The type signature of a method is the same as that shown by IntelliSense when you pause the mouse pointer over a method name in the Visual Studio Code Editor, except without parameter names.</span></span> <span data-ttu-id="1b8fb-139">Typsignaturen werden ebenfalls durch den Interpreter fsi.exe, angezeigt, wenn Sie interaktiv arbeiten.</span><span class="sxs-lookup"><span data-stu-id="1b8fb-139">Type signatures are also displayed by the interpreter, fsi.exe, when you are working interactively.</span></span> <span data-ttu-id="1b8fb-140">Die Typsignatur einer Methode wird durch die Typen der Parameter, gefolgt von den Rückgabetyp, mit der entsprechenden Trennzeichen gebildet.</span><span class="sxs-lookup"><span data-stu-id="1b8fb-140">The type signature of a method is formed by listing out the types of the parameters, followed by the return type, with appropriate separator symbols.</span></span> <span data-ttu-id="1b8fb-141">Curry-Parameter werden durch getrennt `->` und Tupel-Parameter werden durch getrennt `*`.</span><span class="sxs-lookup"><span data-stu-id="1b8fb-141">Curried parameters are separated by `->` and tuple parameters are separated by `*`.</span></span> <span data-ttu-id="1b8fb-142">Der Rückgabewert ist immer getrennt aus den Argumenten von einem `->` Symbol.</span><span class="sxs-lookup"><span data-stu-id="1b8fb-142">The return value is always separated from the arguments by a `->` symbol.</span></span> <span data-ttu-id="1b8fb-143">Klammern können verwendet werden, um komplexe Parameter, z. B. wenn ein Funktionstyp einen Parameter, wird zu gruppieren oder um anzugeben, wenn ein Tupel als einen einzelnen Parameter anstatt als zwei Parameter behandelt wird.</span><span class="sxs-lookup"><span data-stu-id="1b8fb-143">Parentheses can be used to group complex parameters, such as when a function type is a parameter, or to indicate when a tuple is treated as a single parameter rather than as two parameters.</span></span>

<span data-ttu-id="1b8fb-144">Sie können auch erteilen, abstrakte Methoden Default-Definitionen durch die Definition der Klasse hinzufügen und Verwenden der `default` -Schlüsselwort, wie in den Syntaxblock "in diesem Thema dargestellt.</span><span class="sxs-lookup"><span data-stu-id="1b8fb-144">You can also give abstract methods default definitions by adding the definition to the class and using the `default` keyword, as shown in the syntax block in this topic.</span></span> <span data-ttu-id="1b8fb-145">Eine abstrakte Methode, die eine Definition in der gleichen Klasse entspricht einer virtuellen Methode in anderen .NET Framework-Sprachen.</span><span class="sxs-lookup"><span data-stu-id="1b8fb-145">An abstract method that has a definition in the same class is equivalent to a virtual method in other .NET Framework languages.</span></span> <span data-ttu-id="1b8fb-146">Gibt an, ob eine Definition vorhanden ist, die `abstract` Schlüsselwort erstellt einen neuen Dispatchslot in der virtuellen Funktionstabelle für die Klasse.</span><span class="sxs-lookup"><span data-stu-id="1b8fb-146">Whether or not a definition exists, the `abstract` keyword creates a new dispatch slot in the virtual function table for the class.</span></span>

<span data-ttu-id="1b8fb-147">Unabhängig davon, ob eine Basisklasse abstrakten Methoden implementiert können abgeleitete Klassen über Implementierungen von abstrakten Methoden bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="1b8fb-147">Regardless of whether a base class implements its abstract methods, derived classes can provide implementations of abstract methods.</span></span> <span data-ttu-id="1b8fb-148">Um eine abstrakte Methode in einer abgeleiteten Klasse zu implementieren, definieren Sie eine Methode mit dem gleichen Namen und die Signatur in der abgeleiteten Klasse, mit Ausnahme der Verwendung der `override` oder `default` -Schlüsselwort, und geben Sie den Methodentext.</span><span class="sxs-lookup"><span data-stu-id="1b8fb-148">To implement an abstract method in a derived class, define a method that has the same name and signature in the derived class, except use the `override` or `default` keyword, and provide the method body.</span></span> <span data-ttu-id="1b8fb-149">Die Schlüsselwörter `override` und `default` genau dieselbe Bedeutung.</span><span class="sxs-lookup"><span data-stu-id="1b8fb-149">The keywords `override` and `default` mean exactly the same thing.</span></span> <span data-ttu-id="1b8fb-150">Verwenden Sie `override` verwenden, wenn die neue Methode eine Implementierung der Basisklasse; überschreibt `default` bei der Erstellung einer Implementierung in der gleichen Klasse wie die ursprünglichen abstrakten Deklaration.</span><span class="sxs-lookup"><span data-stu-id="1b8fb-150">Use `override` if the new method overrides a base class implementation; use `default` when you create an implementation in the same class as the original abstract declaration.</span></span> <span data-ttu-id="1b8fb-151">Verwenden Sie nicht die `abstract` -Schlüsselwort in die Methode, die die Methode implementiert, die abstrakte in der Basisklasse deklariert wurde.</span><span class="sxs-lookup"><span data-stu-id="1b8fb-151">Do not use the `abstract` keyword on the method that implements the method that was declared abstract in the base class.</span></span>

<span data-ttu-id="1b8fb-152">Das folgende Beispiel veranschaulicht eine abstrakte Methode `Rotate` eine Standardimplementierung, die Entsprechung einer virtuellen .NET Framework-Methode aufweist.</span><span class="sxs-lookup"><span data-stu-id="1b8fb-152">The following example illustrates an abstract method `Rotate` that has a default implementation, the equivalent of a .NET Framework virtual method.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3403.fs)]

<span data-ttu-id="1b8fb-153">Im folgende Beispiel wird veranschaulicht, eine abgeleitete Klasse, die eine Basisklassenmethode überschreibt.</span><span class="sxs-lookup"><span data-stu-id="1b8fb-153">The following example illustrates a derived class that overrides a base class method.</span></span> <span data-ttu-id="1b8fb-154">In diesem Fall ändert der außer Kraft setzen das Verhalten so, dass die Methode keine Aktion ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="1b8fb-154">In this case, the override changes the behavior so that the method does nothing.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3404.fs)]

## <a name="overloaded-methods"></a><span data-ttu-id="1b8fb-155">Überladene Methoden</span><span class="sxs-lookup"><span data-stu-id="1b8fb-155">Overloaded Methods</span></span>

<span data-ttu-id="1b8fb-156">Überladene Methoden sind Methoden, die über identische Namen in einem bestimmten Typ verfügen jedoch über unterschiedliche Argumente.</span><span class="sxs-lookup"><span data-stu-id="1b8fb-156">Overloaded methods are methods that have identical names in a given type but that have different arguments.</span></span> <span data-ttu-id="1b8fb-157">In f# sind optionale Argumente in der Regel überladene Methoden verwendet.</span><span class="sxs-lookup"><span data-stu-id="1b8fb-157">In F#, optional arguments are usually used instead of overloaded methods.</span></span> <span data-ttu-id="1b8fb-158">Überladene Methoden sind jedoch in der Sprache zulässig, vorausgesetzt, dass die Argumente in Tupelform und nicht Curry-Form sind.</span><span class="sxs-lookup"><span data-stu-id="1b8fb-158">However, overloaded methods are permitted in the language, provided that the arguments are in tuple form, not curried form.</span></span>

## <a name="optional-arguments"></a><span data-ttu-id="1b8fb-159">Optionale Argumente</span><span class="sxs-lookup"><span data-stu-id="1b8fb-159">Optional Arguments</span></span>

<span data-ttu-id="1b8fb-160">Ab f# 4.1, können Sie auch optionale Argumente hat den Standardwert des Parameters in Methoden verfügen.</span><span class="sxs-lookup"><span data-stu-id="1b8fb-160">Starting with F# 4.1, you can also have optional arguments with a default parameter value in methods.</span></span>  <span data-ttu-id="1b8fb-161">Dadurch wird die Interoperation mit C#-Code zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="1b8fb-161">This is to help facilitate interoperation with C# code.</span></span>  <span data-ttu-id="1b8fb-162">Im folgende Beispiel wird die Syntax veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="1b8fb-162">The following example demonstrates the syntax:</span></span>

```fsharp
// A class with a method M, which takes in an optional integer argument.
type C() =
    __.M([<Optional; DefaultParameterValue(12)>] i) = i + 1
```

<span data-ttu-id="1b8fb-163">Beachten Sie, die der Wert für übergeben `DefaultParameterValue` muss den Eingabetyp übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="1b8fb-163">Note that the value passed in for `DefaultParameterValue` must match the input type.</span></span>  <span data-ttu-id="1b8fb-164">Im obigen Beispiel ist es ein `int`.</span><span class="sxs-lookup"><span data-stu-id="1b8fb-164">In the above sample, it is an `int`.</span></span>  <span data-ttu-id="1b8fb-165">Es wird versucht, einen nicht ganzzahligen Wert in übergeben `DefaultParameterValue` führt zu einem Kompilierungsfehler.</span><span class="sxs-lookup"><span data-stu-id="1b8fb-165">Attempting to pass a non-integer value into `DefaultParameterValue` would result in a compile error.</span></span>

## <a name="example-properties-and-methods"></a><span data-ttu-id="1b8fb-166">Beispiel: Eigenschaften und Methoden</span><span class="sxs-lookup"><span data-stu-id="1b8fb-166">Example: Properties and Methods</span></span>

<span data-ttu-id="1b8fb-167">Das folgende Beispiel enthält einen Typ, der Beispiele für Felder, Eigenschaften, private Funktionen und eine statische Methode enthält.</span><span class="sxs-lookup"><span data-stu-id="1b8fb-167">The following example contains a type that has examples of fields, private functions, properties, and a static method.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3406.fs)]

## <a name="see-also"></a><span data-ttu-id="1b8fb-168">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1b8fb-168">See also</span></span>

- [<span data-ttu-id="1b8fb-169">Mitglieder</span><span class="sxs-lookup"><span data-stu-id="1b8fb-169">Members</span></span>](index.md)
