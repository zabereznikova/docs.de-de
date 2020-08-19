---
title: Ereignisse
description: 'Erfahren Sie, wie Sie mithilfe von F #-Ereignissen Funktionsaufrufe mit Benutzeraktionen verknüpfen können, die bei der GUI-Programmierung wichtig sind.'
ms.date: 08/15/2020
ms.openlocfilehash: 42783255412d56c6ff6729694c31d0868ed99633
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/18/2020
ms.locfileid: "88559192"
---
# <a name="events"></a><span data-ttu-id="c0928-103">Events</span><span class="sxs-lookup"><span data-stu-id="c0928-103">Events</span></span>

<span data-ttu-id="c0928-104">Mit Ereignissen ordnen Sie Benutzeraktionen Funktionsaufrufe zu. Sie sind wichtig in der GUI-Programmierung.</span><span class="sxs-lookup"><span data-stu-id="c0928-104">Events enable you to associate function calls with user actions and are important in GUI programming.</span></span> <span data-ttu-id="c0928-105">Ereignisse können auch von den Anwendungen oder dem Betriebssystem ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="c0928-105">Events can also be triggered by your applications or by the operating system.</span></span>

## <a name="handling-events"></a><span data-ttu-id="c0928-106">Behandeln von Ereignissen</span><span class="sxs-lookup"><span data-stu-id="c0928-106">Handling Events</span></span>

<span data-ttu-id="c0928-107">Wenn Sie eine GUI-Bibliothek, z. B. Windows Forms oder Windows Presentation Foundation (WPF), verwenden, wird ein großer Anteil des Codes in der Anwendung aufgrund von Ereignissen ausgeführt, die durch die Bibliothek vordefiniert sind.</span><span class="sxs-lookup"><span data-stu-id="c0928-107">When you use a GUI library like Windows Forms or Windows Presentation Foundation (WPF), much of the code in your application runs in response to events that are predefined by the library.</span></span> <span data-ttu-id="c0928-108">Diese vordefinierten Ereignisse sind Member von GUI-Klassen, z. B. Forms und Control.</span><span class="sxs-lookup"><span data-stu-id="c0928-108">These predefined events are members of GUI classes such as forms and controls.</span></span> <span data-ttu-id="c0928-109">Sie können einem bereits vorhandenen Ereignis benutzerdefiniertes Verhalten, z. B. das Klicken auf eine Schaltfläche, hinzufügen, indem Sie auf das entsprechende Ereignis (z. B. das `Click`-Ereignis der `Form`-Klasse) verweisen und die `Add`-Methode aufrufen, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="c0928-109">You can add custom behavior to a preexisting event, such as a button click, by referencing the specific named event of interest (for example, the `Click` event of the `Form` class) and invoking the `Add` method, as shown in the following code.</span></span> <span data-ttu-id="c0928-110">Lassen Sie bei der Ausführung in F# Interactive den Aufruf von `System.Windows.Forms.Application.Run(System.Windows.Forms.Form)` weg.</span><span class="sxs-lookup"><span data-stu-id="c0928-110">If you run this from F# Interactive, omit the call to `System.Windows.Forms.Application.Run(System.Windows.Forms.Form)`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet3601.fs)]

<span data-ttu-id="c0928-111">Der Typ der `Add`-Methode ist `('a -> unit) -> unit`.</span><span class="sxs-lookup"><span data-stu-id="c0928-111">The type of the `Add` method is `('a -> unit) -> unit`.</span></span> <span data-ttu-id="c0928-112">Daher akzeptiert die Ereignishandlermethode einen Parameter, in der Regel die Ereignisargumente, und gibt `unit` zurück.</span><span class="sxs-lookup"><span data-stu-id="c0928-112">Therefore, the event handler method takes one parameter, typically the event arguments, and returns `unit`.</span></span> <span data-ttu-id="c0928-113">Im vorherigen Beispiel ist der Ereignishandler ein Lambdaausdruck.</span><span class="sxs-lookup"><span data-stu-id="c0928-113">The previous example shows the event handler as a lambda expression.</span></span> <span data-ttu-id="c0928-114">Der Ereignishandler kann auch ein Funktionswert sein, wie im folgenden Codebeispiel.</span><span class="sxs-lookup"><span data-stu-id="c0928-114">The event handler can also be a function value, as in the following code example.</span></span> <span data-ttu-id="c0928-115">Im folgenden Codebeispiel wird auch die Verwendung der Ereignishandlerparameter veranschaulicht, die spezifische Informationen für den Typ des Ereignisses bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="c0928-115">The following code example also shows the use of the event handler parameters, which provide information specific to the type of event.</span></span> <span data-ttu-id="c0928-116">Für ein `MouseMove`-Ereignis übergibt das System ein `System.Windows.Forms.MouseEventArgs`-Objekt, das die `X`- und `Y`-Position des Zeigers enthält.</span><span class="sxs-lookup"><span data-stu-id="c0928-116">For a `MouseMove` event, the system passes a `System.Windows.Forms.MouseEventArgs` object, which contains the `X` and `Y` position of the pointer.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet3602.fs)]

## <a name="creating-custom-events"></a><span data-ttu-id="c0928-117">Erstellen von benutzerdefinierten Ereignissen</span><span class="sxs-lookup"><span data-stu-id="c0928-117">Creating Custom Events</span></span>

<span data-ttu-id="c0928-118">F #-Ereignisse werden durch den f #- [Ereignistyp](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-fsharpevent-1.html) dargestellt, der die [IEvent](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-ievent-1.html) -Schnittstelle implementiert.</span><span class="sxs-lookup"><span data-stu-id="c0928-118">F# events are represented by the F# [Event](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-fsharpevent-1.html) type, which implements the [IEvent](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-ievent-1.html) interface.</span></span> <span data-ttu-id="c0928-119">`IEvent` ist selbst eine Schnittstelle, die die Funktionalität zweier anderer Schnittstellen kombiniert, `System.IObservable<'T>` und [IDelegateEvent](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-idelegateevent-1.html).</span><span class="sxs-lookup"><span data-stu-id="c0928-119">`IEvent` is itself an interface that combines the functionality of two other interfaces, `System.IObservable<'T>` and [IDelegateEvent](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-idelegateevent-1.html).</span></span> <span data-ttu-id="c0928-120">Daher verfügen `Event`s über die gleiche Funktionalität wie Delegaten in anderen Sprachen und zusätzlich über die Funktionen von `IObservable`. F#-Ereignisse unterstützen somit die Ereignisfilterung und das Verwenden von F#-Funktionen der ersten Klasse und von Lambda-Ausdrücken als Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="c0928-120">Therefore, `Event`s have the equivalent functionality of delegates in other languages, plus the additional functionality from `IObservable`, which means that F# events support event filtering and using F# first-class functions and lambda expressions as event handlers.</span></span> <span data-ttu-id="c0928-121">Diese Funktionalität wird im- [Ereignis Modul](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-eventmodule.html)bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="c0928-121">This functionality is provided in the [Event module](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-eventmodule.html).</span></span>

<span data-ttu-id="c0928-122">Zum Erstellen eines Ereignisses für eine Klasse, das sich wie ein beliebiges anderes .NET Framework-Ereignis verhält, fügen Sie der Klasse eine `let`-Bindung hinzu, die ein `Event` als Feld in einer Klasse definiert.</span><span class="sxs-lookup"><span data-stu-id="c0928-122">To create an event on a class that acts just like any other .NET Framework event, add to the class a `let` binding that defines an `Event` as a field in a class.</span></span> <span data-ttu-id="c0928-123">Sie können den gewünschten Ereignisargumenttyp als Typargument angeben oder den Wert freilassen und einen geeigneten Wert durch den Compiler bestimmen lassen.</span><span class="sxs-lookup"><span data-stu-id="c0928-123">You can specify the desired event argument type as the type argument, or leave it blank and have the compiler infer the appropriate type.</span></span> <span data-ttu-id="c0928-124">Sie müssen außerdem einen Ereignismember definieren, der das Ereignis als CLI-Ereignis verfügbar macht.</span><span class="sxs-lookup"><span data-stu-id="c0928-124">You also must define an event member that exposes the event as a CLI event.</span></span> <span data-ttu-id="c0928-125">Dieser Member sollte über das [clievent](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-clieventattribute.html) -Attribut verfügen.</span><span class="sxs-lookup"><span data-stu-id="c0928-125">This member should have the [CLIEvent](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-clieventattribute.html) attribute.</span></span> <span data-ttu-id="c0928-126">Sie wird wie eine Eigenschaft deklariert, und ihre Implementierung ist lediglich ein aufrufungsort der [Publish](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-fsharpevent-1.html#Publish) -Eigenschaft des Ereignisses.</span><span class="sxs-lookup"><span data-stu-id="c0928-126">It is declared like a property and its implementation is just a call to the [Publish](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-fsharpevent-1.html#Publish) property of the event.</span></span> <span data-ttu-id="c0928-127">Benutzer der Klasse können die `Add`-Methode des veröffentlichten Ereignisses verwenden, um einen Handler hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="c0928-127">Users of your class can use the `Add` method of the published event to add a handler.</span></span> <span data-ttu-id="c0928-128">Das Argument für die `Add`-Methode kann ein Lambda-Ausdruck sein.</span><span class="sxs-lookup"><span data-stu-id="c0928-128">The argument for the `Add` method can be a lambda expression.</span></span> <span data-ttu-id="c0928-129">Sie können die `Trigger`-Eigenschaft des Ereignisses verwenden, um das Ereignis auszulösen und das Argument an die Handlerfunktion zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="c0928-129">You can use the `Trigger` property of the event to raise the event, passing the arguments to the handler function.</span></span> <span data-ttu-id="c0928-130">Dies wird im folgenden Codebeispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="c0928-130">The following code example illustrates this.</span></span> <span data-ttu-id="c0928-131">In diesem Beispiel ist das abgeleitete Typargument für das Ereignis ein Tupel, das die Argumente für den Lambdaausdruck darstellt.</span><span class="sxs-lookup"><span data-stu-id="c0928-131">In this example, the inferred type argument for the event is a tuple, which represents the arguments for the lambda expression.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet3605.fs)]

<span data-ttu-id="c0928-132">Die Ausgabe lautet wie folgt.</span><span class="sxs-lookup"><span data-stu-id="c0928-132">The output is as follows.</span></span>

```console
Event1 occurred! Object data: Hello World!
```

<span data-ttu-id="c0928-133">Die zusätzliche vom `Event`-Modul bereitgestellte Funktionalität wird hier veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="c0928-133">The additional functionality provided by the `Event` module is illustrated here.</span></span> <span data-ttu-id="c0928-134">Im folgenden Codebeispiel wird die grundlegende Verwendung von `Event.create` zur Erstellung eines Ereignisses und einer Triggermethode, zum Hinzufügen zweier Ereignishandler in der Form von Lambdaausdrücken und dem Auslösen des Ereignisses zur Ausführung beider Lambdaausdrücke dargestellt.</span><span class="sxs-lookup"><span data-stu-id="c0928-134">The following code example illustrates the basic use of `Event.create` to create an event and a trigger method, add two event handlers in the form of lambda expressions, and then trigger the event to execute both lambda expressions.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet3603.fs)]

<span data-ttu-id="c0928-135">Der obige Code gibt Folgendes aus.</span><span class="sxs-lookup"><span data-stu-id="c0928-135">The output of the previous code is as follows.</span></span>

```console
Event occurred.
Given a value: Event occurred.
```

## <a name="processing-event-streams"></a><span data-ttu-id="c0928-136">Verarbeiten von Ereignisstreams</span><span class="sxs-lookup"><span data-stu-id="c0928-136">Processing Event Streams</span></span>

<span data-ttu-id="c0928-137">Anstatt lediglich einen Ereignishandler für ein Ereignis mithilfe der Funktion " [Event. Add](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-eventmodule.html#add) " hinzuzufügen, können Sie die Funktionen im Modul verwenden, `Event` um Streams von Ereignissen auf hochgradig angepasste Weise zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="c0928-137">Instead of just adding an event handler for an event by using the [Event.add](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-eventmodule.html#add) function, you can use the functions in the `Event` module to process streams of events in highly customized ways.</span></span> <span data-ttu-id="c0928-138">Hierzu verwenden Sie den Vorwärtspipeoperator (`|>`) zusammen mit dem Ereignis als ersten Wert in einer Reihe von Funktionsaufrufen und die `Event`-Modulfunktionen als nachfolgende Funktionsaufrufe.</span><span class="sxs-lookup"><span data-stu-id="c0928-138">To do this, you use the forward pipe (`|>`) together with the event as the first value in a series of function calls, and the `Event` module functions as subsequent function calls.</span></span>

<span data-ttu-id="c0928-139">Im folgenden Codebeispiel wird die Einrichtung eines Ereignisses gezeigt, für das der Handler nur unter bestimmten Bedingungen aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="c0928-139">The following code example shows how to set up an event for which the handler is only called under certain conditions.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet3604.fs)]

<span data-ttu-id="c0928-140">Das [Observable-Modul](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-observablemodule.html) enthält ähnliche Funktionen, die für Observable-Objekte verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="c0928-140">The [Observable module](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-observablemodule.html) contains similar functions that operate on observable objects.</span></span> <span data-ttu-id="c0928-141">Observable-Objekte sind Ereignissen ähnlich, abonnieren Ereignisse aber nur, wenn sie selbst abonniert werden.</span><span class="sxs-lookup"><span data-stu-id="c0928-141">Observable objects are similar to events but only actively subscribe to events if they themselves are being subscribed to.</span></span>

## <a name="implementing-an-interface-event"></a><span data-ttu-id="c0928-142">Implementieren eines Schnittstellenereignisses</span><span class="sxs-lookup"><span data-stu-id="c0928-142">Implementing an Interface Event</span></span>

<span data-ttu-id="c0928-143">Häufig beginnen Sie beim Entwickeln von UI-Komponenten, indem Sie ein neues Formular oder ein neues Steuerelement erstellen, das von einem vorhandenen Formular oder Steuerelement erbt.</span><span class="sxs-lookup"><span data-stu-id="c0928-143">As you develop UI components, you often start by creating a new form or a new control that inherits from an existing form or control.</span></span> <span data-ttu-id="c0928-144">Ereignisse werden oft für eine Schnittstelle definiert, und in diesem Fall müssen Sie die Schnittstelle implementieren, um das Ereignis zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="c0928-144">Events are frequently defined on an interface, and, in that case, you must implement the interface to implement the event.</span></span> <span data-ttu-id="c0928-145">Die `System.ComponentModel.INotifyPropertyChanged`-Schnittstelle definiert ein einzelnes `System.ComponentModel.INotifyPropertyChanged.PropertyChanged`-Ereignis.</span><span class="sxs-lookup"><span data-stu-id="c0928-145">The `System.ComponentModel.INotifyPropertyChanged` interface defines a single `System.ComponentModel.INotifyPropertyChanged.PropertyChanged` event.</span></span> <span data-ttu-id="c0928-146">Der folgende Code veranschaulicht die Implementierung des Ereignisses, das von dieser geerbten Schnittstelle definiert wurde:</span><span class="sxs-lookup"><span data-stu-id="c0928-146">The following code illustrates how to implement the event that this inherited interface defined:</span></span>

```fsharp
module CustomForm

open System.Windows.Forms
open System.ComponentModel

type AppForm() as this =
    inherit Form()

    // Define the propertyChanged event.
    let propertyChanged = Event<PropertyChangedEventHandler, PropertyChangedEventArgs>()
    let mutable underlyingValue = "text0"

    // Set up a click event to change the properties.
    do
        this.Click |> Event.add(fun evArgs ->
            this.Property1 <- "text2"
            this.Property2 <- "text3")

    // This property does not have the property-changed event set.
    member val Property1 : string = "text" with get, set

    // This property has the property-changed event set.
    member this.Property2
        with get() = underlyingValue
        and set(newValue) =
            underlyingValue <- newValue
            propertyChanged.Trigger(this, new PropertyChangedEventArgs("Property2"))

    // Expose the PropertyChanged event as a first class .NET event.
    [<CLIEvent>]
    member this.PropertyChanged = propertyChanged.Publish

    // Define the add and remove methods to implement this interface.
    interface INotifyPropertyChanged with
        member this.add_PropertyChanged(handler) = propertyChanged.Publish.AddHandler(handler)
        member this.remove_PropertyChanged(handler) = propertyChanged.Publish.RemoveHandler(handler)

    // This is the event-handler method.
    member this.OnPropertyChanged(args : PropertyChangedEventArgs) =
        let newProperty = this.GetType().GetProperty(args.PropertyName)
        let newValue = newProperty.GetValue(this :> obj) :?> string
        printfn "Property %s changed its value to %s" args.PropertyName newValue

// Create a form, hook up the event handler, and start the application.
let appForm = new AppForm()
let inpc = appForm :> INotifyPropertyChanged
inpc.PropertyChanged.Add(appForm.OnPropertyChanged)
Application.Run(appForm)
```

<span data-ttu-id="c0928-147">Wenn Sie das Ereignis im Konstruktor einbinden möchten, ist der Code etwas komplizierter, da sich die Ereignisverknüpfung wie im folgenden Beispiel in einem `then`-Block in einem zusätzlichen Konstruktor befinden muss:</span><span class="sxs-lookup"><span data-stu-id="c0928-147">If you want to hook up the event in the constructor, the code is a bit more complicated because the event hookup must be in a `then` block in an additional constructor, as in the following example:</span></span>

```fsharp
module CustomForm

open System.Windows.Forms
open System.ComponentModel

// Create a private constructor with a dummy argument so that the public
// constructor can have no arguments.
type AppForm private (dummy) as this =
    inherit Form()

    // Define the propertyChanged event.
    let propertyChanged = Event<PropertyChangedEventHandler, PropertyChangedEventArgs>()
    let mutable underlyingValue = "text0"

    // Set up a click event to change the properties.
    do
        this.Click |> Event.add(fun evArgs ->
            this.Property1 <- "text2"
            this.Property2 <- "text3")

    // This property does not have the property changed event set.
    member val Property1 : string = "text" with get, set

    // This property has the property changed event set.
    member this.Property2
        with get() = underlyingValue
        and set(newValue) =
            underlyingValue <- newValue
            propertyChanged.Trigger(this, new PropertyChangedEventArgs("Property2"))

    [<CLIEvent>]
    member this.PropertyChanged = propertyChanged.Publish

    // Define the add and remove methods to implement this interface.
    interface INotifyPropertyChanged with
        member this.add_PropertyChanged(handler) = this.PropertyChanged.AddHandler(handler)
        member this.remove_PropertyChanged(handler) = this.PropertyChanged.RemoveHandler(handler)

    // This is the event handler method.
    member this.OnPropertyChanged(args : PropertyChangedEventArgs) =
        let newProperty = this.GetType().GetProperty(args.PropertyName)
        let newValue = newProperty.GetValue(this :> obj) :?> string
        printfn "Property %s changed its value to %s" args.PropertyName newValue

    new() as this =
        new AppForm(0)
        then
            let inpc = this :> INotifyPropertyChanged
            inpc.PropertyChanged.Add(this.OnPropertyChanged)

// Create a form, hook up the event handler, and start the application.
let appForm = new AppForm()
Application.Run(appForm)
```

## <a name="see-also"></a><span data-ttu-id="c0928-148">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c0928-148">See also</span></span>

- [<span data-ttu-id="c0928-149">Mitglieder</span><span class="sxs-lookup"><span data-stu-id="c0928-149">Members</span></span>](index.md)
- [<span data-ttu-id="c0928-150">Behandeln und Auswerfen von Ereignissen</span><span class="sxs-lookup"><span data-stu-id="c0928-150">Handling and Raising Events</span></span>](../../../standard/events/index.md)
- [<span data-ttu-id="c0928-151">Lambda-Ausdrücke: das- `fun` Schlüsselwort</span><span class="sxs-lookup"><span data-stu-id="c0928-151">Lambda Expressions: The `fun` Keyword</span></span>](../functions/lambda-expressions-the-fun-keyword.md)
