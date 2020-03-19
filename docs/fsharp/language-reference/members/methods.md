---
title: Methoden
description: Erfahren Sie, wie eine F-Methode eine Funktion ist, die einem Typ zugeordnet ist, der zum Verfügbarmachen und Implementieren der Funktionalität und des Verhaltens von Objekten und Typen verwendet wird.
ms.date: 11/04/2019
ms.openlocfilehash: 6f5ae76ea450b07763eb58d0c95b18b30f634551
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401064"
---
# <a name="methods"></a><span data-ttu-id="01784-103">Methoden</span><span class="sxs-lookup"><span data-stu-id="01784-103">Methods</span></span>

<span data-ttu-id="01784-104">Eine *Methode* ist eine Funktion, die einem Typ zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="01784-104">A *method* is a function that is associated with a type.</span></span> <span data-ttu-id="01784-105">In der objektorientierten Programmierung werden Methoden verwendet, um die Funktionalität und das Verhalten von Objekten und Typen verfügbar zu machen und zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="01784-105">In object-oriented programming, methods are used to expose and implement the functionality and behavior of objects and types.</span></span>

## <a name="syntax"></a><span data-ttu-id="01784-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="01784-106">Syntax</span></span>

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

## <a name="remarks"></a><span data-ttu-id="01784-107">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="01784-107">Remarks</span></span>

<span data-ttu-id="01784-108">In der vorherigen Syntax können Sie die verschiedenen Formen von Methodendeklarationen und -definitionen anzeigen.</span><span class="sxs-lookup"><span data-stu-id="01784-108">In the previous syntax, you can see the various forms of method declarations and definitions.</span></span> <span data-ttu-id="01784-109">In längeren Methodenkörpern folgt ein Zeilenumbruch dem Gleichheitszeichen (=), und der gesamte Methodenkörper wird eingerückt.</span><span class="sxs-lookup"><span data-stu-id="01784-109">In longer method bodies, a line break follows the equal sign (=), and the whole method body is indented.</span></span>

<span data-ttu-id="01784-110">Attribute können auf jede Methodendeklaration angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="01784-110">Attributes can be applied to any method declaration.</span></span> <span data-ttu-id="01784-111">Sie gehen der Syntax für eine Methodendefinition voran und werden in der Regel in einer separaten Zeile aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="01784-111">They precede the syntax for a method definition and are usually listed on a separate line.</span></span> <span data-ttu-id="01784-112">Weitere Informationen finden Sie unter [Attribute](../attributes.md).</span><span class="sxs-lookup"><span data-stu-id="01784-112">For more information, see [Attributes](../attributes.md).</span></span>

<span data-ttu-id="01784-113">Methoden können `inline`markiert werden.</span><span class="sxs-lookup"><span data-stu-id="01784-113">Methods can be marked `inline`.</span></span> <span data-ttu-id="01784-114">Informationen zu `inline` finden Sie unter [Inlinefunktionen](../functions/inline-functions.md).</span><span class="sxs-lookup"><span data-stu-id="01784-114">For information about `inline`, see [Inline Functions](../functions/inline-functions.md).</span></span>

<span data-ttu-id="01784-115">Nicht-Inline-Methoden können rekursiv innerhalb des Typs verwendet werden. Es besteht keine Notwendigkeit, `rec` das Schlüsselwort explizit zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="01784-115">Non-inline methods can be used recursively within the type; there is no need to explicitly use the `rec` keyword.</span></span>

## <a name="instance-methods"></a><span data-ttu-id="01784-116">Instanzmethoden</span><span class="sxs-lookup"><span data-stu-id="01784-116">Instance Methods</span></span>

<span data-ttu-id="01784-117">Instanzmethoden werden mit `member` dem Schlüsselwort und einem *Selbstbezeichner*deklariert, gefolgt von einem Punkt (.) und dem Methodennamen und den Parametern.</span><span class="sxs-lookup"><span data-stu-id="01784-117">Instance methods are declared with the `member` keyword and a *self-identifier*, followed by a period (.) and the method name and parameters.</span></span> <span data-ttu-id="01784-118">Wie bei `let` Bindungen kann die *Parameterliste* ein Muster sein.</span><span class="sxs-lookup"><span data-stu-id="01784-118">As is the case for `let` bindings, the *parameter-list* can be a pattern.</span></span> <span data-ttu-id="01784-119">In der Regel schließen Sie Methodenparameter in Klammern in ein Tupelformular ein, d. h. die Art und Weise, wie Methoden in F- angezeigt werden, wenn sie in anderen .NET Framework-Sprachen erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="01784-119">Typically, you enclose method parameters in parentheses in a tuple form, which is the way methods appear in F# when they are created in other .NET Framework languages.</span></span> <span data-ttu-id="01784-120">Die Curryform (Parameter, die durch Leerzeichen getrennt sind) ist jedoch ebenfalls üblich, und andere Muster werden ebenfalls unterstützt.</span><span class="sxs-lookup"><span data-stu-id="01784-120">However, the curried form (parameters separated by spaces) is also common, and other patterns are supported also.</span></span>

<span data-ttu-id="01784-121">Das folgende Beispiel veranschaulicht die Definition und Verwendung einer nicht abstrakten Instanzmethode.</span><span class="sxs-lookup"><span data-stu-id="01784-121">The following example illustrates the definition and use of a non-abstract instance method.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3401.fs)]

<span data-ttu-id="01784-122">Verwenden Sie innerhalb von Instanzmethoden nicht den Selbstbezeichner, um auf Felder zuzugreifen, die mithilfe von let-Bindungen definiert wurden.</span><span class="sxs-lookup"><span data-stu-id="01784-122">Within instance methods, do not use the self identifier to access fields defined by using let bindings.</span></span> <span data-ttu-id="01784-123">Verwenden Sie den Selbstbezeichner, wenn Sie auf andere Member und Eigenschaften zugreifen.</span><span class="sxs-lookup"><span data-stu-id="01784-123">Use the self identifier when accessing other members and properties.</span></span>

## <a name="static-methods"></a><span data-ttu-id="01784-124">Statische Methoden</span><span class="sxs-lookup"><span data-stu-id="01784-124">Static Methods</span></span>

<span data-ttu-id="01784-125">Das `static` Schlüsselwort wird verwendet, um anzugeben, dass eine Methode ohne Instanz aufgerufen werden kann und keiner Objektinstanz zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="01784-125">The keyword `static` is used to specify that a method can be called without an instance and is not associated with an object instance.</span></span> <span data-ttu-id="01784-126">Andernfalls sind Methoden Instanzmethoden.</span><span class="sxs-lookup"><span data-stu-id="01784-126">Otherwise, methods are instance methods.</span></span>

<span data-ttu-id="01784-127">Das Beispiel im nächsten Abschnitt zeigt `let` Felder, die mit `member` dem Schlüsselwort deklariert wurden, Eigenschaftenmember, die mit dem Schlüsselwort deklariert wurden, und eine statische Methode, die mit dem `static` Schlüsselwort deklariert wurde.</span><span class="sxs-lookup"><span data-stu-id="01784-127">The example in the next section shows fields declared with the `let` keyword, property members declared with the `member` keyword, and a static method declared with the `static` keyword.</span></span>

<span data-ttu-id="01784-128">Das folgende Beispiel veranschaulicht die Definition und Verwendung statischer Methoden.</span><span class="sxs-lookup"><span data-stu-id="01784-128">The following example illustrates the definition and use of static methods.</span></span> <span data-ttu-id="01784-129">Angenommen, diese Methodendefinitionen `SomeType` befinden sich in der Klasse im vorherigen Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="01784-129">Assume that these method definitions are in the `SomeType` class in the previous section.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3402.fs)]

## <a name="abstract-and-virtual-methods"></a><span data-ttu-id="01784-130">Abstrakte und virtuelle Methoden</span><span class="sxs-lookup"><span data-stu-id="01784-130">Abstract and Virtual Methods</span></span>

<span data-ttu-id="01784-131">Das `abstract` Schlüsselwort gibt an, dass eine Methode über einen virtuellen Dispatch-Slot und möglicherweise keine Definition in der Klasse verfügt.</span><span class="sxs-lookup"><span data-stu-id="01784-131">The keyword `abstract` indicates that a method has a virtual dispatch slot and might not have a definition in the class.</span></span> <span data-ttu-id="01784-132">Ein *virtueller Dispatch-Slot* ist ein Eintrag in einer intern verwalteten Funktionstabelle, der zur Laufzeit zum Nachschlagen virtueller Funktionsaufrufe in einem objektorientierten Typ verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="01784-132">A *virtual dispatch slot* is an entry in an internally maintained table of functions that is used at run time to look up virtual function calls in an object-oriented type.</span></span> <span data-ttu-id="01784-133">Der virtuelle Dispatch-Mechanismus ist der Mechanismus, der *Polymorphismus*implementiert, ein wichtiges Merkmal der objektorientierten Programmierung.</span><span class="sxs-lookup"><span data-stu-id="01784-133">The virtual dispatch mechanism is the mechanism that implements *polymorphism*, an important feature of object-oriented programming.</span></span> <span data-ttu-id="01784-134">Eine Klasse, die über mindestens eine abstrakte Methode ohne Definition verfügt, ist eine *abstrakte Klasse,* was bedeutet, dass keine Instanzen dieser Klasse erstellt werden können.</span><span class="sxs-lookup"><span data-stu-id="01784-134">A class that has at least one abstract method without a definition is an *abstract class*, which means that no instances can be created of that class.</span></span> <span data-ttu-id="01784-135">Weitere Informationen zu abstrakten Klassen finden Sie unter [Abstrakte Klassen](../abstract-classes.md).</span><span class="sxs-lookup"><span data-stu-id="01784-135">For more information about abstract classes, see [Abstract Classes](../abstract-classes.md).</span></span>

<span data-ttu-id="01784-136">Abstrakte Methodendeklarationen enthalten keinen Methodentext.</span><span class="sxs-lookup"><span data-stu-id="01784-136">Abstract method declarations do not include a method body.</span></span> <span data-ttu-id="01784-137">Stattdessen folgt auf den Namen der Methode ein Doppelpunkt (:) und eine Typsignatur für die Methode.</span><span class="sxs-lookup"><span data-stu-id="01784-137">Instead, the name of the method is followed by a colon (:) and a type signature for the method.</span></span> <span data-ttu-id="01784-138">Die Typsignatur einer Methode entspricht der von IntelliSense angezeigten, wenn Sie den Mauszeiger über einen Methodennamen im Visual Studio-Code-Editor anhalten, außer ohne Parameternamen.</span><span class="sxs-lookup"><span data-stu-id="01784-138">The type signature of a method is the same as that shown by IntelliSense when you pause the mouse pointer over a method name in the Visual Studio Code Editor, except without parameter names.</span></span> <span data-ttu-id="01784-139">Typsignaturen werden auch vom Interpreter fsi.exe angezeigt, wenn Sie interaktiv arbeiten.</span><span class="sxs-lookup"><span data-stu-id="01784-139">Type signatures are also displayed by the interpreter, fsi.exe, when you are working interactively.</span></span> <span data-ttu-id="01784-140">Die Typsignatur einer Methode wird gebildet, indem die Typen der Parameter aufgelistet werden, gefolgt vom Rückgabetyp mit entsprechenden Trennzeichen.</span><span class="sxs-lookup"><span data-stu-id="01784-140">The type signature of a method is formed by listing out the types of the parameters, followed by the return type, with appropriate separator symbols.</span></span> <span data-ttu-id="01784-141">Curry-Parameter werden `->` durch und Tupelparameter `*`durch getrennt.</span><span class="sxs-lookup"><span data-stu-id="01784-141">Curried parameters are separated by `->` and tuple parameters are separated by `*`.</span></span> <span data-ttu-id="01784-142">Der Rückgabewert wird immer durch `->` ein Symbol von den Argumenten getrennt.</span><span class="sxs-lookup"><span data-stu-id="01784-142">The return value is always separated from the arguments by a `->` symbol.</span></span> <span data-ttu-id="01784-143">Klammern können verwendet werden, um komplexe Parameter zu gruppieren, z. B. wenn ein Funktionstyp ein Parameter ist, oder um anzugeben, wann ein Tupel als einzelner Parameter und nicht als zwei Parameter behandelt wird.</span><span class="sxs-lookup"><span data-stu-id="01784-143">Parentheses can be used to group complex parameters, such as when a function type is a parameter, or to indicate when a tuple is treated as a single parameter rather than as two parameters.</span></span>

<span data-ttu-id="01784-144">Sie können auch abstrakte Methoden Standarddefinitionen geben, indem `default` Sie die Definition zur Klasse hinzufügen und das Schlüsselwort verwenden, wie im Syntaxblock in diesem Thema gezeigt.</span><span class="sxs-lookup"><span data-stu-id="01784-144">You can also give abstract methods default definitions by adding the definition to the class and using the `default` keyword, as shown in the syntax block in this topic.</span></span> <span data-ttu-id="01784-145">Eine abstrakte Methode mit einer Definition in derselben Klasse entspricht einer virtuellen Methode in anderen .NET Framework-Sprachen.</span><span class="sxs-lookup"><span data-stu-id="01784-145">An abstract method that has a definition in the same class is equivalent to a virtual method in other .NET Framework languages.</span></span> <span data-ttu-id="01784-146">Unabhängig davon, ob eine `abstract` Definition vorhanden ist oder nicht, erstellt das Schlüsselwort einen neuen Dispatch-Slot in der virtuellen Funktionstabelle für die Klasse.</span><span class="sxs-lookup"><span data-stu-id="01784-146">Whether or not a definition exists, the `abstract` keyword creates a new dispatch slot in the virtual function table for the class.</span></span>

<span data-ttu-id="01784-147">Unabhängig davon, ob eine Basisklasse ihre abstrakten Methoden implementiert, können abgeleitete Klassen Implementierungen abstrakter Methoden bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="01784-147">Regardless of whether a base class implements its abstract methods, derived classes can provide implementations of abstract methods.</span></span> <span data-ttu-id="01784-148">Um eine abstrakte Methode in einer abgeleiteten Klasse zu implementieren, definieren Sie eine `override` Methode, die denselben Namen und dieselbe Signatur in der abgeleiteten Klasse hat, außer verwenden Sie das schlüsselwortgebende Wort, `default` und stellen Sie den Methodentext bereit.</span><span class="sxs-lookup"><span data-stu-id="01784-148">To implement an abstract method in a derived class, define a method that has the same name and signature in the derived class, except use the `override` or `default` keyword, and provide the method body.</span></span> <span data-ttu-id="01784-149">Die `override` Schlüsselwörter `default` und bedeuten genau das gleiche.</span><span class="sxs-lookup"><span data-stu-id="01784-149">The keywords `override` and `default` mean exactly the same thing.</span></span> <span data-ttu-id="01784-150">Verwenden `override` Sie diese Methode, wenn die neue Methode eine Basisklassenimplementierung überschreibt. verwenden `default` Sie, wenn Sie eine Implementierung in derselben Klasse wie die ursprüngliche abstrakte Deklaration erstellen.</span><span class="sxs-lookup"><span data-stu-id="01784-150">Use `override` if the new method overrides a base class implementation; use `default` when you create an implementation in the same class as the original abstract declaration.</span></span> <span data-ttu-id="01784-151">Verwenden Sie `abstract` das Schlüsselwort nicht für die Methode, die die Methode implementiert, die in der Basisklasse als abstrakt deklariert wurde.</span><span class="sxs-lookup"><span data-stu-id="01784-151">Do not use the `abstract` keyword on the method that implements the method that was declared abstract in the base class.</span></span>

<span data-ttu-id="01784-152">Im folgenden Beispiel wird `Rotate` eine abstrakte Methode mit einer Standardimplementierung veranschaulicht, die einer virtuellen .NET Framework-Methode entspricht.</span><span class="sxs-lookup"><span data-stu-id="01784-152">The following example illustrates an abstract method `Rotate` that has a default implementation, the equivalent of a .NET Framework virtual method.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3403.fs)]

<span data-ttu-id="01784-153">Das folgende Beispiel veranschaulicht eine abgeleitete Klasse, die eine Basisklassenmethode überschreibt.</span><span class="sxs-lookup"><span data-stu-id="01784-153">The following example illustrates a derived class that overrides a base class method.</span></span> <span data-ttu-id="01784-154">In diesem Fall ändert die Außerkraftsetzung das Verhalten, sodass die Methode nichts bewirkt.</span><span class="sxs-lookup"><span data-stu-id="01784-154">In this case, the override changes the behavior so that the method does nothing.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3404.fs)]

## <a name="overloaded-methods"></a><span data-ttu-id="01784-155">Überladene Methoden</span><span class="sxs-lookup"><span data-stu-id="01784-155">Overloaded Methods</span></span>

<span data-ttu-id="01784-156">Überladene Methoden sind Methoden, die identische Namen in einem bestimmten Typ haben, aber unterschiedliche Argumente aufweisen.</span><span class="sxs-lookup"><span data-stu-id="01784-156">Overloaded methods are methods that have identical names in a given type but that have different arguments.</span></span> <span data-ttu-id="01784-157">Optionale Argumente werden in der Regel anstelle von überladenen Methoden verwendet.</span><span class="sxs-lookup"><span data-stu-id="01784-157">In F#, optional arguments are usually used instead of overloaded methods.</span></span> <span data-ttu-id="01784-158">Überladene Methoden sind jedoch in der Sprache zulässig, vorausgesetzt, die Argumente sind in Tupelform und nicht in Curryform.</span><span class="sxs-lookup"><span data-stu-id="01784-158">However, overloaded methods are permitted in the language, provided that the arguments are in tuple form, not curried form.</span></span>

## <a name="optional-arguments"></a><span data-ttu-id="01784-159">Optionale Argumente</span><span class="sxs-lookup"><span data-stu-id="01784-159">Optional Arguments</span></span>

<span data-ttu-id="01784-160">Ab F-4.1 können Sie auch optionale Argumente mit einem Standardparameterwert in Methoden haben.</span><span class="sxs-lookup"><span data-stu-id="01784-160">Starting with F# 4.1, you can also have optional arguments with a default parameter value in methods.</span></span>  <span data-ttu-id="01784-161">Dies soll die Zusammenarbeit mit dem Code von C-Code erleichtern.</span><span class="sxs-lookup"><span data-stu-id="01784-161">This is to help facilitate interoperation with C# code.</span></span>  <span data-ttu-id="01784-162">Im folgenden Beispiel wird die Syntax veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="01784-162">The following example demonstrates the syntax:</span></span>

```fsharp
// A class with a method M, which takes in an optional integer argument.
type C() =
    _.M([<Optional; DefaultParameterValue(12)>] i) = i + 1
```

<span data-ttu-id="01784-163">Beachten Sie, dass `DefaultParameterValue` der übergebene Wert mit dem Eingabetyp übereinstimmen muss.</span><span class="sxs-lookup"><span data-stu-id="01784-163">Note that the value passed in for `DefaultParameterValue` must match the input type.</span></span>  <span data-ttu-id="01784-164">In der obigen Stichprobe `int`ist es eine .</span><span class="sxs-lookup"><span data-stu-id="01784-164">In the above sample, it is an `int`.</span></span>  <span data-ttu-id="01784-165">Der Versuch, einen Nicht-Ganzzahlwert `DefaultParameterValue` zu übergeben, würde zu einem Kompilierungsfehler führen.</span><span class="sxs-lookup"><span data-stu-id="01784-165">Attempting to pass a non-integer value into `DefaultParameterValue` would result in a compile error.</span></span>

## <a name="example-properties-and-methods"></a><span data-ttu-id="01784-166">Beispiel: Eigenschaften und Methoden</span><span class="sxs-lookup"><span data-stu-id="01784-166">Example: Properties and Methods</span></span>

<span data-ttu-id="01784-167">Das folgende Beispiel enthält einen Typ mit Beispielen für Felder, private Funktionen, Eigenschaften und eine statische Methode.</span><span class="sxs-lookup"><span data-stu-id="01784-167">The following example contains a type that has examples of fields, private functions, properties, and a static method.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3406.fs)]

## <a name="see-also"></a><span data-ttu-id="01784-168">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="01784-168">See also</span></span>

- [<span data-ttu-id="01784-169">Mitglieder</span><span class="sxs-lookup"><span data-stu-id="01784-169">Members</span></span>](index.md)
