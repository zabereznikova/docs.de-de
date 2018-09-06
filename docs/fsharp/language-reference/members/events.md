---
title: Ereignisse (F#)
description: Erfahren Sie, wie F#-Ereignisse ermöglichen, die in der GUI-Programmierung wichtig sind Benutzeraktionen Funktionsaufrufe zugeordnet werden soll.
ms.date: 05/16/2016
ms.openlocfilehash: ce547bc9ec7b5e0ef9a7492c0889bb690e3040c2
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "43871932"
---
# <a name="events"></a>Ereignisse

> [!NOTE]
Mit dem API-Referenz-Link in diesem Artikel gelangen Sie auf MSDN.  Die docs.microsoft.com-API-Referenz ist nicht abgeschlossen.

Mit Ereignissen ordnen Sie Benutzeraktionen Funktionsaufrufe zu. Sie sind wichtig in der GUI-Programmierung. Ereignisse können auch von den Anwendungen oder dem Betriebssystem ausgelöst werden.

## <a name="handling-events"></a>Behandeln von Ereignissen

Wenn Sie eine GUI-Bibliothek, z. B. Windows Forms oder Windows Presentation Foundation (WPF), verwenden, wird ein großer Anteil des Codes in der Anwendung aufgrund von Ereignissen ausgeführt, die durch die Bibliothek vordefiniert sind. Diese vordefinierten Ereignisse sind Member von GUI-Klassen, z. B. Forms und Control. Sie können einem bereits vorhandenen Ereignis benutzerdefiniertes Verhalten, z. B. das Klicken auf eine Schaltfläche, hinzufügen, indem Sie auf das entsprechende Ereignis (z. B. das `Click`-Ereignis der `Form`-Klasse) verweisen und die `Add`-Methode aufrufen, wie im folgenden Code gezeigt. Lassen Sie bei der Ausführung in F# Interactive den Aufruf von `System.Windows.Forms.Application.Run(System.Windows.Forms.Form)` weg.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3601.fs)]

Der Typ der `Add`-Methode ist `('a -> unit) -> unit`. Daher akzeptiert die Ereignishandlermethode einen Parameter, in der Regel die Ereignisargumente, und gibt `unit` zurück. Im vorherigen Beispiel ist der Ereignishandler ein Lambda-Ausdruck. Der Ereignishandler kann auch ein Funktionswert sein, wie im folgenden Codebeispiel. Im folgenden Codebeispiel wird auch die Verwendung der Ereignishandlerparameter veranschaulicht, die spezifische Informationen für den Typ des Ereignisses bereitstellen. Für ein `MouseMove`-Ereignis übergibt das System ein `System.Windows.Forms.MouseEventArgs`-Objekt, das die `X`- und `Y`-Position des Zeigers enthält.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3602.fs)]

## <a name="creating-custom-events"></a>Erstellen von benutzerdefinierten Ereignissen

F#-Ereignisse werden durch die F#-dargestellt [Ereignis](https://msdn.microsoft.com/library/f3b47c8a-4ee5-4ce8-9a72-ad305a17c4b9) Klasse implementiert die [IEvent](https://msdn.microsoft.com/library/8dbca0df-f8a1-40bd-8d50-aa26f6a8b862) Schnittstelle. `IEvent` ist eine Schnittstelle, die kombiniert die Funktionalität zweier anderer Schnittstellen `System.IObservable<'T>` und [IDelegateEvent](https://msdn.microsoft.com/library/3d849465-6b8e-4fc5-b36c-2941d734268a). Daher verfügen `Event`s über die gleiche Funktionalität wie Delegaten in anderen Sprachen und zusätzlich über die Funktionen von `IObservable`. F#-Ereignisse unterstützen somit die Ereignisfilterung und das Verwenden von F#-Funktionen der ersten Klasse und von Lambda-Ausdrücken als Ereignishandler. Diese Funktionalität wird bereitgestellt, der [Event-Modul](https://msdn.microsoft.com/library/8b883baa-a460-4840-9baa-de8260351bc7).

Zum Erstellen eines Ereignisses für eine Klasse, das sich wie ein beliebiges anderes .NET Framework-Ereignis verhält, fügen Sie der Klasse eine `let`-Bindung hinzu, die ein `Event` als Feld in einer Klasse definiert. Sie können den gewünschten Ereignisargumenttyp als Typargument angeben oder den Wert freilassen und einen geeigneten Wert durch den Compiler bestimmen lassen. Sie müssen außerdem einen Ereignismember definieren, der das Ereignis als CLI-Ereignis verfügbar macht. Dieser Member müssen die [CLIEvent](https://msdn.microsoft.com/library/d359f1dd-ffa5-42fb-8808-b4c8131a0333) Attribut. Wird es wie eine Eigenschaft deklariert, und seine Implementierung ist einfach einen Aufruf der [veröffentlichen](https://msdn.microsoft.com/library/b0fdaad5-25e5-43d0-9c0c-ce37c4aeb68e) Eigenschaft des Ereignisses. Benutzer der Klasse können die `Add`-Methode des veröffentlichten Ereignisses verwenden, um einen Handler hinzuzufügen. Das Argument für die `Add`-Methode kann ein Lambda-Ausdruck sein. Sie können die `Trigger`-Eigenschaft des Ereignisses verwenden, um das Ereignis auszulösen und das Argument an die Handlerfunktion zu übergeben. Dies wird im folgenden Codebeispiel veranschaulicht. In diesem Beispiel ist das abgeleitete Typargument für das Ereignis ein Tupel, das die Argumente für den Lambda-Ausdruck darstellt.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3605.fs)]

Die Ausgabe lautet wie folgt.

```
Event1 occurred! Object data: Hello World!
```

Die zusätzliche vom `Event`-Modul bereitgestellte Funktionalität wird hier veranschaulicht. Im folgenden Codebeispiel wird die grundlegende Verwendung von `Event.create` zur Erstellung eines Ereignisses und einer Triggermethode, zum Hinzufügen zweier Ereignishandler in der Form von Lambda-Ausdrücken und dem Auslösen des Ereignisses zur Ausführung beider Lambda-Ausdrücke dargestellt.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3603.fs)]

Der obige Code gibt Folgendes aus.

```
Event occurred.
Given a value: Event occurred.
```

## <a name="processing-event-streams"></a>Verarbeiten von Ereignisstreams

Statt einfach einen Ereignishandler für ein Ereignis mithilfe der [Event.add](https://msdn.microsoft.com/library/10670d3b-8d47-4f6e-b8df-ebc6f64ef4fd) -Funktion können Sie die Funktionen in der `Event` Modul, um ereignisdatenströme Prozess Ereignisstreams hochgradig Benutzerdefiniert. Hierzu verwenden Sie den Vorwärtspipeoperator (`|>`) zusammen mit dem Ereignis als ersten Wert in einer Reihe von Funktionsaufrufen und die `Event`-Modulfunktionen als nachfolgende Funktionsaufrufe.

Im folgenden Codebeispiel wird die Einrichtung eines Ereignisses gezeigt, für das der Handler nur unter bestimmten Bedingungen aufgerufen wird.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet3604.fs)]

Die [Observable-Modul](https://msdn.microsoft.com/library/16b8610b-b30a-4df7-aa99-d9d352276227) enthält ähnliche Funktionen, die auf Observable-Objekte ausgeführt werden. Observable-Objekte sind Ereignissen ähnlich, abonnieren Ereignisse aber nur, wenn sie selbst abonniert werden.

## <a name="implementing-an-interface-event"></a>Implementieren eines Schnittstellenereignisses

Häufig beginnen Sie beim Entwickeln von UI-Komponenten, indem Sie ein neues Formular oder ein neues Steuerelement erstellen, das von einem vorhandenen Formular oder Steuerelement erbt. Ereignisse werden oft für eine Schnittstelle definiert, und in diesem Fall müssen Sie die Schnittstelle implementieren, um das Ereignis zu implementieren. Die `System.ComponentModel.INotifyPropertyChanged`-Schnittstelle definiert ein einzelnes `System.ComponentModel.INotifyPropertyChanged.PropertyChanged`-Ereignis. Der folgende Code veranschaulicht die Implementierung des Ereignisses, das von dieser geerbten Schnittstelle definiert wurde:

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
        this.Click |> Event.add(fun evArgs -> this.Property1 <- "text2"
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

Wenn Sie das Ereignis im Konstruktor einbinden möchten, ist der Code etwas komplizierter, da sich die Ereignisverknüpfung wie im folgenden Beispiel in einem `then`-Block in einem zusätzlichen Konstruktor befinden muss:

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
        this.Click |> Event.add(fun evArgs -> this.Property1 <- "text2"
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

## <a name="see-also"></a>Siehe auch

- [Mitglieder](index.md)
- [Behandeln und Auslösen von Ereignissen](../../../../docs/standard/events/index.md)
- [Lambdaausdrücke: Das `fun` Schlüsselwort](../functions/lambda-expressions-the-fun-keyword.md)
- [Control.Event-Modul](https://msdn.microsoft.com/visualfsharpdocs/conceptual/control.event-module-%5bfsharp%5d)
- [Control.Event&#60;t&#62; Klasse](https://msdn.microsoft.com/visualfsharpdocs/conceptual/control.event%5b%27t%5d-class-%5bfsharp%5d)
- [Control.Event&#60;'Delegat', Args&#62; Klasse](https://msdn.microsoft.com/visualfsharpdocs/conceptual/control.event%5b%27delegate%2c%27args%5d-class-%5bfsharp%5d)
