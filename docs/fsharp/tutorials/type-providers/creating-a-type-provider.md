---
title: 'Tutorial: Erstellen eines Typanbieters'
description: Erfahren Sie, wie Sie Ihre eigenen Anbieter vom Typ F in F-3.0 erstellen, indem Sie mehrere einfache Typanbieter untersuchen, um die grundlegenden Konzepte zu veranschaulichen.
ms.date: 11/04/2019
ms.openlocfilehash: 3b8145d4c2d8bf96b6dcf66de02e9f2d83927d74
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186124"
---
# <a name="tutorial-create-a-type-provider"></a>Tutorial: Erstellen eines Typanbieters

Der Typanbietermechanismus in F- ist ein wesentlicher Teil seiner Unterstützung für die Informations-Reich-Programmierung. In diesem Lernprogramm wird erläutert, wie Sie eigene Typanbieter erstellen können, indem Schritt für Schritt mehrere einfache Typanbieter entwickelt und an diesen die grundlegenden Konzepte veranschaulicht werden. Weitere Informationen zum Typanbietermechanismus in F' finden Sie unter [Typanbieter](index.md).

Das Ökosystem "F" enthält eine Reihe von Typanbietern für häufig verwendete Internet- und Unternehmensdatendienste. Beispiel:

- [FSharp.Data](https://fsharp.github.io/FSharp.Data/) enthält Typanbieter für JSON-, XML-, CSV- und HTML-Dokumentformate.

- [SQLProvider](https://fsprojects.github.io/SQLProvider/) bietet stark typisierten Zugriff auf SQL-Datenbanken über eine Objektzuordnung und F-LINQ-Abfragen für diese Datenquellen.

- [FSharp.Data.SqlClient](https://fsprojects.github.io/FSharp.Data.SqlClient/) verfügt über eine Reihe von Typanbietern für die zur Kompilierungszeit überprüfte Einbettung von T-SQL in F.

- [FSharp.Data.TypeProviders](https://fsprojects.github.io/FSharp.Data.TypeProviders/) ist ein älterer Satz von Typanbietern, die nur mit .NET Framework-Programmierung für den Zugriff auf SQL-, Entity Framework-, OData- und WSDL-Datendienste verwendet werden können.

Bei Bedarf können Sie eigene benutzerdefinierte Typanbieter erstellen oder auf Typanbieter verweisen, die von anderen Entwicklern erstellt wurden. Angenommen, in einer Organisation wird ein Datendienst verwendet, der eine große und wachsende Anzahl von benannten Datasets bereitstellt, die alle ein eigenes, stabiles Datenschema verwenden. Für diesen Dienst können Sie einen Typanbieter erstellen, der die Schemas liest und dem Programmierer alle aktuellen Datasets mit starker Typisierung zur Verfügung stellt.

## <a name="before-you-start"></a>Vorbereitungen

Der Typanbietermechanismus ist hauptsächlich für das Einfügen von stabilen Räumen für Daten- und Dienstinformationen in die F#-Programmierung vorgesehen.

Der Mechanismus ist nicht für das Einfügen von Informationsräumen gedacht, deren Schemas während der Programmausführung Änderungen unterliegen, die für die Programmlogik relevant sind. Auch die sprachübergreifende Metaprogrammierung gehört nicht zu den Entwurfszielen für diesen Mechanismus, obwohl solche Szenerien in einigen Fällen durchaus auftreten können. Sie sollten diesen Mechanismus nur verwenden, wenn dies erforderlich ist und sich durch die Entwicklung eines Typanbieters ein deutlicher Mehrwert für die Programmierung erreichen lässt.

Schreiben Sie keinen Typanbieter in Situationen, in denen kein Schema verfügbar ist. Entsprechend sollten Sie den Einsatz eines Typanbieters auch dann vermeiden, wenn eine gewöhnliche (oder sogar schon vorhandene) .NET-Bibliothek ausreichen würde.

Bevor Sie beginnen, stellen Sie sich die folgenden Fragen:

- Steht ein Schema für die Informationsquelle zur Verfügung? Wenn dies der Fall ist, wie erfolgt die Zuordnung in das Typsystem von F# und .NET?

- Kann eine vorhandene (dynamisch typisierte) API als Ausgangspunkt für die Implementierung verwendet werden?

- Haben Sie und die Organisation genügend Verwendungsfälle definieren können, sodass der Aufwand für die Entwicklung eines Typanbieters gerechtfertigt ist? Würde eine normale .NET-Bibliothek den Anforderungen ebenso genügen?

- Wie häufig und wie umfassend wird sich das Schema ändern?

- Ändert es sich während der Programmierungsphase?

- Ändert es sich während einzelner Programmierungssitzungen?

- Ändert es sich während der Programmausführung?

Typanbieter sind für Situationen geeignet, in denen das Schema zur Laufzeit und während der Lebensdauer des kompilierten Codes stabil ist.

## <a name="a-simple-type-provider"></a>Ein einfacher Typanbieter

Dieses Beispiel ist Samples.HelloWorldTypeProvider, ähnlich `examples` den Beispielen im Verzeichnis des [F-Typanbieter-SDK](https://github.com/fsprojects/FSharp.TypeProviders.SDK/). Der Anbieter stellt einen "Typenraum" mit 100 gelöschten Typen zur Verfügung, wie der folgenden Code zeigt, in dem F#-Signatursyntax verwendet wird und Details für alle Typen außer `Type1` weggelassen wurden. Weitere Informationen zu löschten Typen finden Sie weiter unten in diesem Thema unter Details zu [erased Provided Types.](#details-about-erased-provided-types)

```fsharp
namespace Samples.HelloWorldTypeProvider

type Type1 =
    /// This is a static property.
    static member StaticProperty : string

    /// This constructor takes no arguments.
    new : unit -> Type1

    /// This constructor takes one argument.
    new : data:string -> Type1

    /// This is an instance property.
    member InstanceProperty : int

    /// This is an instance method.
    member InstanceMethod : x:int -> char

    nested type NestedType =
        /// This is StaticProperty1 on NestedType.
        static member StaticProperty1 : string
        …
        /// This is StaticProperty100 on NestedType.
        static member StaticProperty100 : string

type Type2 =
…
…

type Type100 =
…
```

Beachten Sie, dass der Satz der bereitgestellten Typen und Member statisch verfügbar gemacht wird. In diesem Beispiel wird die Möglichkeit von Anbietern, Typen abhängig von einem Schema bereitzustellen, nicht verwendet. Die Implementierung des Typanbieters wird im folgenden Code erläutert. Die Details werden in den folgenden Abschnitten dieses Themas behandelt.

> [!WARNING]
> Es kann Unterschiede zwischen diesem Code und den Online-Beispielen geben.

```fsharp
namespace Samples.FSharp.HelloWorldTypeProvider

open System
open System.Reflection
open ProviderImplementation.ProvidedTypes
open FSharp.Core.CompilerServices
open FSharp.Quotations

// This type defines the type provider. When compiled to a DLL, it can be added
// as a reference to an F# command-line compilation, script, or project.
[<TypeProvider>]
type SampleTypeProvider(config: TypeProviderConfig) as this =

  // Inheriting from this type provides implementations of ITypeProvider
  // in terms of the provided types below.
  inherit TypeProviderForNamespaces(config)

  let namespaceName = "Samples.HelloWorldTypeProvider"
  let thisAssembly = Assembly.GetExecutingAssembly()

  // Make one provided type, called TypeN.
  let makeOneProvidedType (n:int) =
  …
  // Now generate 100 types
  let types = [ for i in 1 .. 100 -> makeOneProvidedType i ]

  // And add them to the namespace
  do this.AddNamespace(namespaceName, types)

[<assembly:TypeProviderAssembly>]
do()
```

Um diesen Anbieter zu verwenden, öffnen Sie eine separate Instanz von Visual Studio, erstellen Sie ein Skript für das F-Skript, und fügen Sie dann einen Verweis auf den Anbieter aus Ihrem Skript hinzu, indem Sie #r verwenden, wie der folgende Code zeigt:

```fsharp
#r @".\bin\Debug\Samples.HelloWorldTypeProvider.dll"

let obj1 = Samples.HelloWorldTypeProvider.Type1("some data")

let obj2 = Samples.HelloWorldTypeProvider.Type1("some other data")

obj1.InstanceProperty
obj2.InstanceProperty

[ for index in 0 .. obj1.InstanceProperty-1 -> obj1.InstanceMethod(index) ]
[ for index in 0 .. obj2.InstanceProperty-1 -> obj2.InstanceMethod(index) ]

let data1 = Samples.HelloWorldTypeProvider.Type1.NestedType.StaticProperty35
```

Suchen Sie dann nach den Typen im `Samples.HelloWorldTypeProvider`-Namespace, der vom Typanbieter generiert wird.

Bevor Sie den Anbieter neu kompilieren, stellen Sie sicher, dass alle Instanzen von Visual Studio und F# Interactive, die die Anbieter-DLL verwenden, geschlossen wurden. Andernfalls tritt ein Buildfehler auf, da die Ausgabe-DLL gesperrt ist.

Zum Debuggen dieses Anbieters mithilfe von print-Anweisungen erstellen Sie ein Skript, das ein Problem mit dem Anbieter erzeugt, und verwenden Sie dann den folgenden Code:

```console
fsc.exe -r:bin\Debug\HelloWorldTypeProvider.dll script.fsx
```

Um diesen Anbieter mithilfe von Visual Studio zu debuggen, öffnen Sie die Developer-Eingabeaufforderung für Visual Studio mit administrativen Anmeldeinformationen, und führen Sie den folgenden Befehl aus:

```console
devenv.exe /debugexe fsc.exe -r:bin\Debug\HelloWorldTypeProvider.dll script.fsx
```

Öffnen Sie alternativ Visual Studio, öffnen Sie `Debug/Attach to process…`das Debugmenü, wählen Sie , und fügen Sie es an einen anderen `devenv` Prozess an, bei dem Sie Ihr Skript bearbeiten. Mit dieser Methode können Sie leichter eine ganz bestimmte Logik im Typanbieter überprüfen, da Sie in der zweiten Instanz interaktiv Ausdrücke eingeben können (mit vollständiger IntelliSense-Unterstützung und anderen Funktionen).

Sie können die Debugging-Option Nur eigenen Code deaktivieren, um Fehler in generiertem Code besser identifizieren zu können. Informationen zum Aktivieren oder Deaktivieren dieser Funktion finden Sie unter [Navigieren durch Code mit dem Debugger](/visualstudio/debugger/navigating-through-code-with-the-debugger). Sie können auch das Abfangen von Ausnahmeausnahmen der ersten Chance festlegen, indem Sie das `Debug` Menü öffnen und dann `Exceptions` die Tasten Strg+Alt+E auswählen, um das `Exceptions` Dialogfeld zu öffnen. Aktivieren Sie in `Common Language Runtime Exceptions`diesem Dialogfeld unter das `Thrown` Kontrollkästchen.

### <a name="implementation-of-the-type-provider"></a>Implementierung des Typanbieters

In diesem Abschnitt werden die wichtigsten Schritte bei der Implementierung eines Typanbieters erläutert. Zuerst definieren Sie den Typ für den benutzerdefinierten Typanbieter selbst:

```fsharp
[<TypeProvider>]
type SampleTypeProvider(config: TypeProviderConfig) as this =
```

Dieser Typ muss öffentlich sein, und Sie müssen ihn mit dem [TypeProvider-Attribut](https://msdn.microsoft.com/library/bdf7b036-7490-4ace-b79f-c5f1b1b37947) markieren, damit der Compiler den Typanbieter erkennt, wenn ein separates F-Projekt auf die Assembly verweist, die den Typ enthält. Der *Konfigurationsparameter* ist optional und enthält, falls vorhanden, kontextbezogene Konfigurationsinformationen für die Typanbieterinstanz, die der F-Compiler erstellt.

Als Nächstes implementieren Sie die [ITypeProvider-Schnittstelle.](https://msdn.microsoft.com/library/2c2b0571-843d-4a7d-95d4-0a7510ed5e2f) In diesem Fall verwenden Sie den `TypeProviderForNamespaces`-Typ aus der `ProvidedTypes`-API als Basistyp. Dieser Hilfstyp kann eine endliche Auflistung vorzeitig bereitgestellter Namespaces bereitstellen, von denen jeder direkt eine begrenzte Zahl fester, vorzeitig bereitgestellter Typen enthält. In diesem Zusammenhang generiert der Anbieter *eifrig* Typen, auch wenn sie nicht benötigt oder verwendet werden.

```fsharp
inherit TypeProviderForNamespaces(config)
```

Als Nächstes definieren Sie lokale private Werte, um den Namespace für die bereitgestellten Typen anzugeben, und suchen die eigentliche Typanbieterassembly. Diese Assembly wird später als logisch übergeordneter Typ der bereitgestellten gelöschten Typen verwendet.

```fsharp
let namespaceName = "Samples.HelloWorldTypeProvider"
let thisAssembly = Assembly.GetExecutingAssembly()
```

Als Nächstes erstellen Sie eine Funktion, um jeden der Typen Type1 bis Type100 bereitzustellen. Diese Funktion wird weiter unten in diesem Thema ausführlicher erläutert.

```fsharp
let makeOneProvidedType (n:int) = …
```

Anschließend generieren Sie die 100 bereitgestellten Typen:

```fsharp
let types = [ for i in 1 .. 100 -> makeOneProvidedType i ]
```

Als Nächstes fügen Sie die Typen als bereitgestellten Namespace hinzu:

```fsharp
do this.AddNamespace(namespaceName, types)
```

Zum Schluss fügen Sie ein Assemblyattribut hinzu, das angibt, dass Sie eine Typanbieter-DLL erstellen:

```fsharp
[<assembly:TypeProviderAssembly>]
do()
```

### <a name="providing-one-type-and-its-members"></a>Bereitstellen eines einzelnen Typs und seiner Member

Die `makeOneProvidedType`-Funktion übernimmt die eigentliche Verarbeitung bei der Bereitstellung eines Typs.

```fsharp
let makeOneProvidedType (n:int) =
…
```

In diesem Schritt wird die Implementierung dieser Funktion beschrieben. Erstellen Sie zunächst den bereitgestellten Typ (beispielsweise Type1, wenn n=1, oder Type57, wenn n=57).

```fsharp
// This is the provided type. It is an erased provided type and, in compiled code,
// will appear as type 'obj'.
let t = ProvidedTypeDefinition(thisAssembly, namespaceName,
                               "Type" + string n,
                               baseType = Some typeof<obj>)
```

Beachten Sie die folgenden Punkte:

- Dieser bereitgestellte Typ wird gelöscht.  Da Sie angeben, dass `obj`der Basistyp ist, werden Instanzen als Werte vom Typ [obj](https://msdn.microsoft.com/library/dcf2430f-702b-40e5-a0a1-97518bf137f7) im kompilierten Code angezeigt.

- Wenn Sie einen nicht geschachtelten Typ angeben, müssen Sie die Assembly und den Namespace angeben. Bei gelöschten Typen sollte die Assembly die Typanbieterassembly selbst sein.

Als Nächstes fügen Sie dem Typ eine XML-Dokumentation hinzu. Diese Dokumentation wird verzögert, d. h., sie wird erst bei Bedarf berechnet, wenn der Hostcompiler sie benötigt.

```fsharp
t.AddXmlDocDelayed (fun () -> sprintf "This provided type %s" ("Type" + string n))
```

Als Nächstes fügen Sie dem Typ eine statische bereitgestellte Eigenschaft hinzu:

```fsharp
let staticProp = ProvidedProperty(propertyName = "StaticProperty",
                                  propertyType = typeof<string>,
                                  isStatic = true,
                                  getterCode = (fun args -> <@@ "Hello!" @@>))
```

Beim Abrufen dieser Eigenschaft wird immer die Zeichenfolge "Hello!" zurückgegeben. Der `GetterCode` für die Eigenschaft verwendet ein F#-Zitat, das den Code darstellt, den der Hostcompiler zum Abrufen der Eigenschaft generiert. Weitere Informationen zu Angeboten finden Sie unter [Code-Angebote (F-Nr.)](https://msdn.microsoft.com/library/6f055397-a1f0-4f9a-927c-f0d7c6951155).

Fügen Sie der Eigenschaft eine XML-Dokumentation hinzu.

```fsharp
staticProp.AddXmlDocDelayed(fun () -> "This is a static property")
```

Fügen Sie jetzt die bereitgestellte Eigenschaft an den bereitgestellten Typ an. Sie müssen einen bereitgestellten Member an genau einen Typ anfügen. Andernfalls kann auf den Member nicht zugegriffen werden.

```fsharp
t.AddMember staticProp
```

Erstellen Sie jetzt einen bereitgestellten Konstruktor ohne Parameter.

```fsharp
let ctor = ProvidedConstructor(parameters = [ ],
                               invokeCode = (fun args -> <@@ "The object data" :> obj @@>))
```

Der `InvokeCode` für den Konstruktor gibt ein F#-Zitat zurück, das den Code darstellt, den der Hostcompiler generiert, wenn der Konstruktor aufgerufen wird. Sie können beispielsweise folgenden Konstruktor verwenden:

```fsharp
new Type10()
```

Eine Instanz des angegebenen Typs wird mit den ihm zugrunde liegenden Daten erstellt ("The object data"). Der zitierte Code enthält eine Konvertierung in [obj,](https://msdn.microsoft.com/library/dcf2430f-702b-40e5-a0a1-97518bf137f7) da dieser Typ die Löschung dieses bereitgestellten Typs ist (wie Sie angegeben haben, als Sie den angegebenen Typ deklariert haben).

Fügen Sie dem Konstruktor eine XML-Dokumentation hinzu, und fügen Sie dann den bereitgestellten Konstruktor dem bereitgestellten Typ hinzu:

```fsharp
ctor.AddXmlDocDelayed(fun () -> "This is a constructor")

t.AddMember ctor
```

Erstellen Sie einen zweiten bereitgestellten Konstruktor mit einem Parameter:

```fsharp
let ctor2 =
ProvidedConstructor(parameters = [ ProvidedParameter("data",typeof<string>) ],
                    invokeCode = (fun args -> <@@ (%%(args.[0]) : string) :> obj @@>))
```

Der `InvokeCode` für den Konstruktor gibt erneut ein F#-Zitat zurück, das den Code darstellt, den der Hostcompiler bei einem Aufruf der Methode generiert. Sie können beispielsweise folgenden Konstruktor verwenden:

```fsharp
new Type10("ten")
```

Eine Instanz des bereitgestellten Typs wird mit den im zugrunde liegenden Daten erstellt ("ten"). Sie haben wahrscheinlich schon bemerkt, dass die `InvokeCode`-Funktion ein Zitat zurückgibt. Die Eingabe für diese Funktion ist eine Liste von Ausdrücken: ein Ausdruck pro Konstruktorparameter. In diesem Fall ist in `args.[0]` ein Ausdruck verfügbar, der den einzelnen Parameterwert darstellt. Der Code für einen Aufruf des Konstruktors wandelt den Rückgabewert in den gelöschten Typ `obj` um. Nachdem Sie dem Typ den zweiten bereitgestellten Konstruktor hinzugefügt haben, erstellen Sie eine bereitgestellte Instanzeigenschaft:

```fsharp
let instanceProp =
    ProvidedProperty(propertyName = "InstanceProperty",
                     propertyType = typeof<int>,
                     getterCode= (fun args ->
                        <@@ ((%%(args.[0]) : obj) :?> string).Length @@>))
instanceProp.AddXmlDocDelayed(fun () -> "This is an instance property")
t.AddMember instanceProp
```

Beim Abrufen dieser Eigenschaft wird die Länge der Zeichenfolge (des Darstellungsobjekts) zurückgegeben. Die `GetterCode`-Eigenschaft gibt ein F#-Zitat zurück, das den Code angibt, der vom Hostcompiler zum Abrufen der Eigenschaft generiert wird. Wie `InvokeCode` gibt die `GetterCode`-Funktion ein Zitat zurück. Der Hostcompiler ruft diese Funktion mit einer Argumentliste auf. In diesem Fall enthalten die Argumente nur den einzelnen Ausdruck, der die Instanz darstellt, `args.[0]`auf der der Getter aufgerufen wird, auf die Sie mithilfe von zugreifen können. Die Implementierung `GetterCode` von dann spleißt in das `obj`Ergebnisangebot beim löschten Typ, und eine Umwandlung wird verwendet, um den Mechanismus des Compilers zum Überprüfen von Typen zu erfüllen, dass das Objekt eine Zeichenfolge ist. Der nächste Abschnitt von `makeOneProvidedType` stellt eine Instanzmethode mit einem Parameter bereit.

```fsharp
let instanceMeth =
    ProvidedMethod(methodName = "InstanceMethod",
                   parameters = [ProvidedParameter("x",typeof<int>)],
                   returnType = typeof<char>,
                   invokeCode = (fun args ->
                       <@@ ((%%(args.[0]) : obj) :?> string).Chars(%%(args.[1]) : int) @@>))

instanceMeth.AddXmlDocDelayed(fun () -> "This is an instance method")
// Add the instance method to the type.
t.AddMember instanceMeth
```

Zum Schluss wird ein geschachtelter Typ erstellt, der 100 geschachtelte Eigenschaften enthält. Die Erstellung dieses geschachtelten Typs und seiner Eigenschaften wird verzögert, d. h., er wird erst bei Bedarf berechnet.

```fsharp
t.AddMembersDelayed(fun () ->
  let nestedType = ProvidedTypeDefinition("NestedType", Some typeof<obj>)

  nestedType.AddMembersDelayed (fun () ->
    let staticPropsInNestedType =
      [
          for i in 1 .. 100 ->
              let valueOfTheProperty = "I am string "  + string i

              let p =
                ProvidedProperty(propertyName = "StaticProperty" + string i,
                  propertyType = typeof<string>,
                  isStatic = true,
                  getterCode= (fun args -> <@@ valueOfTheProperty @@>))

              p.AddXmlDocDelayed(fun () ->
                  sprintf "This is StaticProperty%d on NestedType" i)

              p
      ]

    staticPropsInNestedType)

  [nestedType])
```

### <a name="details-about-erased-provided-types"></a>Details über gelöschte bereitgestellte Typen

Das Beispiel in diesem Abschnitt enthält nur *erasierte bereitgestellte Typen,* die in den folgenden Situationen besonders nützlich sind:

- Wenn Sie einen Anbieter für einen Informationsraum schreiben, der nur Daten und Methoden enthält.

- Wenn Sie einen Anbieter schreiben, bei dem zur Laufzeit für die Verwendung des Informationsraums keine exakte Typsemantik erforderlich ist.

- Wenn Sie einen Anbieter für einen Informationsraum schreiben, der so groß ist und so viele Verbindungen verwendet, dass es technisch nicht möglich ist, echte .NET-Typen für den Informationsraum zu generieren.

In diesem Beispiel wird jeder bereitgestellte Typ zu `obj` gelöscht, und alle Verwendungen des Typs erscheinen im kompilierten Code als `obj`. Tatsächlich sind die zugrunde liegenden Objekte in diesen Beispielen Zeichenfolgen, der Typ im kompilierten .NET-Code ist jedoch `System.Object`. Wie bei jeder Verwendung der Typlöschung können Sie explizites Boxing und Unboxing sowie Umwandlungen verwenden, um gelöschte Typen zu unterlaufen. In diesem Fall kann eine ungültige Umwandlungsausnahme auftreten, wenn das Objekt verwendet wird. Eine Anbieterlaufzeit kann ihren eigenen privaten Darstellungstyp definieren, um falsche Darstellungen zu vermeiden. In F# selbst können Sie keine gelöschten Typen definieren. Nur bereitgestellte Typen dürfen gelöscht werden. Sie müssen sich darüber im Klaren sein, welche Auswirkungen, sowohl praktisch als auch semantisch, die Verwendung von gelöschten Typen für Ihren Typanbieter hat, im Vergleich zu einem Anbieter, der selbst gelöschte Typen bereitstellt. Ein gelöschter Typ hat keinen tatsächlichen .NET-Typ. Daher können Sie keine genaue Reflektion über den Typ ausführen, und Sie unterlaufen möglicherweise gelöschte Typen, wenn Sie zur Laufzeit Umwandlungen oder andere Techniken verwenden, die zur Laufzeit eine exakte Typsemantik erfordern. Die Subversion gelöschter Typen führt zur Laufzeit häufig zu Ausnahmen bei der Typumwandlung.

### <a name="choosing-representations-for-erased-provided-types"></a>Auswählen von Darstellungen für gelöschte bereitgestellte Typen

Für einige Verwendungen von gelöschten bereitgestellten Typen ist keine Darstellung erforderlich. Zum Beispiel kann der gelöschte bereitgestellte Typ ausschließlich statische Eigenschaften und Member enthalten, aber keine Konstruktoren, sodass keine Methoden oder Eigenschaften eine Instanz des Typs zurückgeben. Wenn Instanzen eines gelöschten bereitgestellten Typ verfügbar sind, berücksichtigen Sie die folgenden Fragen:

**Was ist die Löschung eines bereitgestellten Typs?**

- Die Löschung eines bereitgestellten Typs bezeichnet die Darstellung des Typs im kompilierten .NET-Code.

- Die Löschung eines bereitgestellten gelöschten Klassentyps ist immer der erste nicht gelöschte Basistyp in die Vererbungskette des Typs.

- Die Löschung eines bereitgestellten gelöschten Schnittstellentyps ist immer `System.Object`.

**Was sind die Darstellungen eines bereitgestellten Typs?**

- Der Satz möglicher Objekte für einen gelöschten bereitgestellten Typ wird als Darstellungen des Typs bezeichnet. Im Beispiel in diesem Dokument sind die Darstellungen aller gelöschten bereitgestellten Typen `Type1..Type100` immer Zeichenfolgenobjekte.

Alle Darstellungen eines angegebenen Typs müssen mit der Löschung des bereitgestellten Typs kompatibel sein. (Andernfalls gibt entweder der F#-Compiler einen Fehler aufgrund der Verwendung des Typanbieters aus, oder es wird nicht überprüfbarer und ungültiger .NET-Code generiert. Ein Typanbieter ist nicht gültig, wenn er Code zurückgibt, der eine ungültige Darstellung angibt.)

Sie können die Darstellung für bereitgestellte Objekte anhand eines der folgenden, häufig verwendeten Ansätze wählen:

- Wenn Sie einfach einen stark typisierten Wrapper für einen vorhandenen .NET-Typ bereitstellen, ist es meist sinnvoll, diesen .NET-Typ als Löschung für den Typ zu wählen, Instanzen dieses Typs als Darstellungen zu verwenden oder beide Wege zu wählen. Dieser Ansatz ist geeignet, wenn die meisten der vorhandenen Methoden für diesen Typ auch dann noch Sinn machen, wenn die stark typisierte Version verwendet wird.

- Wenn Sie eine API erstellen möchten, die sich deutlich von allen vorhandenen .NET-APIs unterscheidet, ist es sinnvoll, Laufzeittypen zu erstellen, die als Typlöschungen und Darstellungen für die bereitgestellten Typen verwendet werden.

Das Beispiel in diesem Dokument werden Zeichenfolgen als Darstellungen der bereitgestellten Objekte verwendet. Häufig kann es sinnvoll sein, andere Objekte als Darstellungen zu verwenden. Beispielsweise können Sie ein Wörterbuch als Eigenschaftensammlung verwenden:

```fsharp
ProvidedConstructor(parameters = [],
    invokeCode= (fun args -> <@@ (new Dictionary<string,obj>()) :> obj @@>))
```

Alternativ können Sie einen Typ im Typanbieter definieren, der zur Laufzeit zusammen mit einem oder mehreren Laufzeitvorgängen verwendet wird, um die Darstellung zu bilden:

```fsharp
type DataObject() =
    let data = Dictionary<string,obj>()
    member x.RuntimeOperation() = data.Count
```

Bereitgestellte Member können dann Instanzen dieses Objekttyps erstellen:

```fsharp
ProvidedConstructor(parameters = [],
    invokeCode= (fun args -> <@@ (new DataObject()) :> obj @@>))
```

In diesem Fall können Sie (optional) diesen Typ als Typlöschung verwenden, indem Sie den Typ beim Erstellen der `baseType` als `ProvidedTypeDefinition` angeben:

```fsharp
ProvidedTypeDefinition(…, baseType = Some typeof<DataObject> )
…
ProvidedConstructor(…, InvokeCode = (fun args -> <@@ new DataObject() @@>), …)
```

### <a name="key-lessons"></a>Hauptlektionen

Im vorherigen Abschnitt wurde das Erstellen eines einfachen gelöschten Typanbieters erläutert, der einen Typenbereich, Eigenschaften und Methoden bereitstellt. Im Abschnitt wurde außerdem das Konzept der Typlöschung erläutert, und es wurden einige der Vor- und Nachteile beim Bereitstellen gelöschter Typen durch einen Typanbieter sowie mögliche Darstellungen für gelöschte Typen behandelt.

## <a name="a-type-provider-that-uses-static-parameters"></a>Ein Typanbieter, der statische Parameter verwendet

Die Möglichkeit, Typanbieter durch statische Daten zu parametrisieren, eröffnet viele interessante Szenarien, sogar in Fällen, in denen der Anbieter gar nicht auf lokale oder Remotedaten zugreifen muss. In diesem Abschnitt lernen Sie einige der grundlegenden Techniken für den Entwurf eines solchen Anbieters kennen.

### <a name="type-checked-regex-provider"></a>Typgeprüfter Regex-Anbieter

Angenommen, Sie möchten einen Typanbieter für reguläre Ausdrücke implementieren, der die .NET-Bibliotheken von <xref:System.Text.RegularExpressions.Regex> in einer Schnittstelle umschließt, die zur Laufzeit die folgenden Garantien bereitstellt:

- Überprüfen, ob ein regulärer Ausdruck gültig ist.

- Bereitstellen benannter Eigenschaften für Übereinstimmungen, die auf vorhandenen Gruppennamen im regulären Ausdruck basieren.

In diesem Abschnitt wird erläutert, wie Sie mit Typanbietern einen `RegexTyped`-Typ erstellen, in dem über das reguläre Ausdrucksmuster Parameter erstellt werden, um die zuvor genannten Funktionen bereitzustellen. Der Compiler meldet einen Fehler, wenn das angegebene Muster ungültig ist, und der Typanbieter kann die Gruppen aus dem Muster extrahieren und sie bei Übereinstimmungen als benannte Eigenschaften verfügbar machen. Wenn Sie einen Typanbieter entwerfen, sollten Sie berücksichtigen, in welcher Form die API den Endbenutzern zur Verfügung gestellt wird und wie der Entwurf in .NET-Code übersetzt wird. Im folgenden Beispiel wird gezeigt, wie eine solche API verwendet wird, um die Komponenten einer Ortskennzahl zu ermitteln:

```fsharp
type T = RegexTyped< @"(?<AreaCode>^\d{3})-(?<PhoneNumber>\d{3}-\d{4}$)">
let reg = T()
let result = T.IsMatch("425-555-2345")
let r = reg.Match("425-555-2345").Group_AreaCode.Value //r equals "425"
```

Im folgenden Beispiel wird gezeigt, wie der Typanbieter diese Aufrufe übersetzt:

```fsharp
let reg = new Regex(@"(?<AreaCode>^\d{3})-(?<PhoneNumber>\d{3}-\d{4}$)")
let result = reg.IsMatch("425-123-2345")
let r = reg.Match("425-123-2345").Groups.["AreaCode"].Value //r equals "425"
```

Beachten Sie folgende Punkte:

- Der Regex-Standardtyp stellt den parametrisierten `RegexTyped`-Typ dar.

- Der `RegexTyped`-Konstruktor führt zu einem Aufruf des Regex-Konstruktors und übergibt als Muster das statische Typargument.

- Die Ergebnisse der `Match`-Methode werden durch den <xref:System.Text.RegularExpressions.Match>-Standardtyp dargestellt.

- Für jede benannte Gruppe wird eine bereitgestellte Eigenschaft erzeugt, und bei einem Zugriff auf die Eigenschaft wird ein Indexer verwendet, um eine `Groups`-Auflistung der Übereinstimmungen abzurufen.

Der folgende Code enthält die Kernlogik für die Implementierung eines solchen Anbieters, wobei in diesem Beispiel allerdings das Hinzufügen der Member zum bereitgestellten Typ ausgelassen wird. Weitere Informationen über die hinzugefügten Member finden Sie im entsprechenden Abschnitt weiter unten in diesem Thema. Für den vollständigen Code laden Sie das Beispiel aus dem [Beispielpaket "F" 3.0](https://archive.codeplex.com/?p=fsharp3sample) auf der CodePlex-Website herunter.

```fsharp
namespace Samples.FSharp.RegexTypeProvider

open System.Reflection
open Microsoft.FSharp.Core.CompilerServices
open Samples.FSharp.ProvidedTypes
open System.Text.RegularExpressions

[<TypeProvider>]
type public CheckedRegexProvider() as this =
    inherit TypeProviderForNamespaces()

    // Get the assembly and namespace used to house the provided types
    let thisAssembly = Assembly.GetExecutingAssembly()
    let rootNamespace = "Samples.FSharp.RegexTypeProvider"
    let baseTy = typeof<obj>
    let staticParams = [ProvidedStaticParameter("pattern", typeof<string>)]

    let regexTy = ProvidedTypeDefinition(thisAssembly, rootNamespace, "RegexTyped", Some baseTy)

    do regexTy.DefineStaticParameters(
        parameters=staticParams,
        instantiationFunction=(fun typeName parameterValues ->

          match parameterValues with
          | [| :? string as pattern|] ->

            // Create an instance of the regular expression.
            //
            // This will fail with System.ArgumentException if the regular expression is not valid.
            // The exception will escape the type provider and be reported in client code.
            let r = System.Text.RegularExpressions.Regex(pattern)

            // Declare the typed regex provided type.
            // The type erasure of this type is 'obj', even though the representation will always be a Regex
            // This, combined with hiding the object methods, makes the IntelliSense experience simpler.
            let ty =
              ProvidedTypeDefinition(
                thisAssembly,
                rootNamespace,
                typeName,
                baseType = Some baseTy)

            ...

            ty
          | _ -> failwith "unexpected parameter values"))

    do this.AddNamespace(rootNamespace, [regexTy])

[<TypeProviderAssembly>]
do ()
```

Beachten Sie folgende Punkte:

- Der Typanbieter erwartet zwei statische Parameter: `pattern`, ein erforderlicher Parameter, und den optionalen Parameter `options` (für den ein Standardwert bereitgestellt wird).

- Nachdem die statischen Argumente angegeben sind, erstellen Sie eine Instanz des regulären Ausdrucks. Diese Instanz löst eine Ausnahme aus, wenn der Regex-Ausdruck fehlerhaft ist, und der Fehler wird den Benutzern gemeldet.

- Innerhalb des `DefineStaticParameters`-Rückrufs definieren Sie den Typ, der zurückgegeben wird, nachdem die Argumente angegeben wurden.

- Diese Code legt `HideObjectMethods` fest, um die Methoden in der IntelliSense-Unterstützung zu unterdrücken. Dieses Attribut führt dazu, dass die Member `Equals`, `GetHashCode`, `Finalize` und `GetType` nicht in den IntelliSense-Listen für ein bereitgestelltes Objekt angezeigt werden.

- Sie verwenden `obj` als Basistyp der Methode. Für die Laufzeitdarstellung dieses Typs wird jedoch ein `Regex`-Objekt verwendet, wie im folgenden Beispiel gezeigt.

- Der Aufruf des `Regex`-Konstruktors löst eine <xref:System.ArgumentException> aus, wenn ein regulärer Ausdruck ungültig ist. Der Compiler fängt diese Ausnahme ab und gibt im Visual Studio-Editor oder zur Kompilierzeit eine Fehlermeldung an den Benutzer aus. Diese Ausnahme ermöglicht es, reguläre Ausdrücke zu überprüfen, ohne die Anwendung ausführen zu müssen.

Der oben definierte Typ ist bisher wenig nützlich, da er noch keine sinnvollen Methoden oder Eigenschaften enthält. Fügen Sie zuerst eine statische `IsMatch`-Methode hinzu:

```fsharp
let isMatch =
    ProvidedMethod(
        methodName = "IsMatch",
        parameters = [ProvidedParameter("input", typeof<string>)],
        returnType = typeof<bool>,
        isStatic = true,
        invokeCode = fun args -> <@@ Regex.IsMatch(%%args.[0], pattern) @@>)

isMatch.AddXmlDoc "Indicates whether the regular expression finds a match in the specified input string."
ty.AddMember isMatch
```

Der vorherige Code definiert eine `IsMatch`-Methode, die eine Zeichenfolge als Eingabe erwartet und `bool` zurückgibt. Der einzige schwierige Teil ist die Verwendung des `args`-Arguments innerhalb der `InvokeCode`-Definition. In diesem Beispiel ist `args` eine Liste mit Zitaten, die die Argumente für diese Methode darstellen. Wenn die Methode eine Instanzmethode ist, stellt das erste Argument das `this`-Argument dar. Bei einer statischen Methode sind alle Argumente einfach nur die expliziten Argumente der Methode. Beachten Sie, dass der Typ des zitierten Werts dem angegebenen Rückgabetyp entsprechen muss (in diesem Fall `bool`). Beachten Sie auch, dass dieser Code die `AddXmlDoc`-Methode verwendet, um sicherzustellen, dass die bereitgestellte Methode über eine sinnvolle Dokumentation verfügt, die Sie über IntelliSense zur Verfügung stellen können.

Als Nächstes fügen Sie eine Instanz der Match-Methode hinzu. Diese Methode muss jedoch einen Wert eines bereitgestellten `Match`-Typs zurückgeben, damit stark typisiert auf die Gruppen zugegriffen werden kann. Daher deklarieren Sie zuerst den `Match`-Typ. Da dieser Typ abhängig ist von dem Muster, das als statisches Argument übergeben wurde, muss dieser Typ innerhalb der parametrisierten Typdefinition geschachtelt werden:

```fsharp
let matchTy =
    ProvidedTypeDefinition(
        "MatchType",
        baseType = Some baseTy,
        hideObjectMethods = true)

ty.AddMember matchTy
```

Anschließend fügen Sie dem Match-Typ für jede Gruppe eine Eigenschaft hinzu. Zur Laufzeit wird eine Übereinstimmung als <xref:System.Text.RegularExpressions.Match>-Wert dargestellt, sodass das Zitat, das die Eigenschaft definiert, die indizierte <xref:System.Text.RegularExpressions.Match.Groups>-Eigenschaft verwenden muss, um die entsprechende Gruppe abzurufen.

```fsharp
for group in r.GetGroupNames() do
    // Ignore the group named 0, which represents all input.
    if group <> "0" then
    let prop =
      ProvidedProperty(
        propertyName = group,
        propertyType = typeof<Group>,
        getterCode = fun args -> <@@ ((%%args.[0]:obj) :?> Match).Groups.[group] @@>)
        prop.AddXmlDoc(sprintf @"Gets the ""%s"" group from this match" group)
    matchTy.AddMember prop
```

Achten Sie auch hier darauf, dass der bereitgestellten Eigenschaft eine XML-Dokumentation hinzugefügt wird. Beachten Sie außerdem, dass eine Eigenschaft gelesen werden kann, wenn eine `GetterCode`-Funktion bereitgestellt wird, und dass Eigenschaft geschrieben werden kann, wenn eine `SetterCode`-Funktion bereitgestellt wird. Die resultierende Eigenschaft ist also schreibgeschützt.

Nun können Sie eine Instanzmethode erstellen, die einen Wert dieses `Match`-Typs zurückgibt:

```fsharp
let matchMethod =
    ProvidedMethod(
        methodName = "Match",
        parameters = [ProvidedParameter("input", typeof<string>)],
        returnType = matchTy,
        invokeCode = fun args -> <@@ ((%%args.[0]:obj) :?> Regex).Match(%%args.[1]) :> obj @@>)

matchMeth.AddXmlDoc "Searches the specified input string for the first occurrence of this regular expression"

ty.AddMember matchMeth
```

Da Sie eine Instanzmethode erstellen, stellt `args.[0]` die `RegexTyped`-Instanz dar, für die die Methode aufgerufen wird, und `args.[1]` das Eingabeargument.

Stellen Sie abschließend einen Konstruktor bereit, damit Instanzen des bereitgestellten Typs erstellt werden können.

```fsharp
let ctor =
    ProvidedConstructor(
        parameters = [],
        invokeCode = fun args -> <@@ Regex(pattern, options) :> obj @@>)

ctor.AddXmlDoc("Initializes a regular expression instance.")

ty.AddMember ctor
```

Der Konstruktor führt bei der Löschung zur Erstellung einer einfachen .NET Regex-Standardinstanz, die wiederum in einem Objekt geschachtelt wird, da `obj` die Löschung des bereitgestellten Typs ist. Mit dieser Änderung kann die API des Beispiels nun so verwendet werden, wie zuvor in diesem Thema beschrieben. Der folgende Code ist vollständig:

```fsharp
namespace Samples.FSharp.RegexTypeProvider

open System.Reflection
open Microsoft.FSharp.Core.CompilerServices
open Samples.FSharp.ProvidedTypes
open System.Text.RegularExpressions

[<TypeProvider>]
type public CheckedRegexProvider() as this =
    inherit TypeProviderForNamespaces()

    // Get the assembly and namespace used to house the provided types.
    let thisAssembly = Assembly.GetExecutingAssembly()
    let rootNamespace = "Samples.FSharp.RegexTypeProvider"
    let baseTy = typeof<obj>
    let staticParams = [ProvidedStaticParameter("pattern", typeof<string>)]

    let regexTy = ProvidedTypeDefinition(thisAssembly, rootNamespace, "RegexTyped", Some baseTy)

    do regexTy.DefineStaticParameters(
        parameters=staticParams,
        instantiationFunction=(fun typeName parameterValues ->

            match parameterValues with
            | [| :? string as pattern|] ->

                // Create an instance of the regular expression.

                let r = System.Text.RegularExpressions.Regex(pattern)

                // Declare the typed regex provided type.

                let ty =
                    ProvidedTypeDefinition(
                        thisAssembly,
                        rootNamespace,
                        typeName,
                        baseType = Some baseTy)

                ty.AddXmlDoc "A strongly typed interface to the regular expression '%s'"

                // Provide strongly typed version of Regex.IsMatch static method.
                let isMatch =
                    ProvidedMethod(
                        methodName = "IsMatch",
                        parameters = [ProvidedParameter("input", typeof<string>)],
                        returnType = typeof<bool>,
                        isStatic = true,
                        invokeCode = fun args -> <@@ Regex.IsMatch(%%args.[0], pattern) @@>)

                isMatch.AddXmlDoc "Indicates whether the regular expression finds a match in the specified input string"

                ty.AddMember isMatch

                // Provided type for matches
                // Again, erase to obj even though the representation will always be a Match
                let matchTy =
                    ProvidedTypeDefinition(
                        "MatchType",
                        baseType = Some baseTy,
                        hideObjectMethods = true)

                // Nest the match type within parameterized Regex type.
                ty.AddMember matchTy

                // Add group properties to match type
                for group in r.GetGroupNames() do
                    // Ignore the group named 0, which represents all input.
                    if group <> "0" then
                        let prop =
                          ProvidedProperty(
                            propertyName = group,
                            propertyType = typeof<Group>,
                            getterCode = fun args -> <@@ ((%%args.[0]:obj) :?> Match).Groups.[group] @@>)
                        prop.AddXmlDoc(sprintf @"Gets the ""%s"" group from this match" group)
                        matchTy.AddMember(prop)

                // Provide strongly typed version of Regex.Match instance method.
                let matchMeth =
                  ProvidedMethod(
                    methodName = "Match",
                    parameters = [ProvidedParameter("input", typeof<string>)],
                    returnType = matchTy,
                    invokeCode = fun args -> <@@ ((%%args.[0]:obj) :?> Regex).Match(%%args.[1]) :> obj @@>)
                matchMeth.AddXmlDoc "Searches the specified input string for the first occurrence of this regular expression"

                ty.AddMember matchMeth

                // Declare a constructor.
                let ctor =
                  ProvidedConstructor(
                    parameters = [],
                    invokeCode = fun args -> <@@ Regex(pattern) :> obj @@>)

                // Add documentation to the constructor.
                ctor.AddXmlDoc "Initializes a regular expression instance"

                ty.AddMember ctor

                ty
            | _ -> failwith "unexpected parameter values"))

    do this.AddNamespace(rootNamespace, [regexTy])

[<TypeProviderAssembly>]
do ()
```

### <a name="key-lessons"></a>Hauptlektionen

In diesem Abschnitt wird erläutert, wie ein Typanbieter erstellt wird, der seine statischen Parameter verarbeitet. Der Anbieter überprüft den statischen Parameter und stellt Vorgänge auf Grundlage des ermittelten Werts bereit.

## <a name="a-type-provider-that-is-backed-by-local-data"></a>Ein Typanbieter, der lokale Daten verarbeitet

Häufig sollen mithilfe von Typanbietern APIs bereitgestellt werden, die nicht nur auf statischen Parametern, sondern zusätzlich auf Informationen von lokalen oder Remotesystemen basieren. In diesem Abschnitt werden Typanbieter erläutert, die auf lokalen Daten basieren, z. B. auf lokalen Datendateien.

### <a name="simple-csv-file-provider"></a>Einfacher CSV-Dateianbieter

Als einfaches Beispiel soll ein Typanbieter für den Zugriff auf wissenschaftliche Daten im CSV-Format (Comma Separated Value) betrachtet werden. In diesem Abschnitt wird davon ausgegangen, dass die CSV-Dateien eine Kopfzeile gefolgt von den Gleitkommadaten enthalten, wie in der folgenden Tabelle gezeigt:

|Abstand (Meter)|Zeit (Sekunden)|
|----------------|-------------|
|50.0|3,7|
|100.0|5,2|
|150.0|6.4|

In diesem Abschnitt wird erläutert, wie Sie einen Typ bereitstellen, mit dem Sie Zeilen mit einer `Distance`-Eigenschaft vom Typ `float<meter>` und einer `Time`-Eigenschaft vom Typ `float<second>` abrufen können. Der Einfachheit halber wird Folgendes vorausgesetzt:

- Kopfzeilennamen sind entweder einheitslos oder haben das Formular "Name (Einheit)" und enthalten keine Kommas.

- Einheiten sind alle System International (SI)-Einheiten, wie das [Microsoft.FSharp.Data.UnitSystems.SI.UnitNames Module (F)-Modul](https://msdn.microsoft.com/library/3cb43485-11f5-4aa7-a779-558f19d4013b) definiert.

- Bei den Einheiten handelt es sich nur um einfache Einheiten (z. B. Meter) und nicht um zusammengesetzte Einheiten (z. B. Meter/Sekunde).

- Alle Spalten enthalten Gleitkommadaten.

Bei einer umfassenderen Anbieterimplementierung könnten diese Einschränkungen gelockert werden.

Auch hier sollte im ersten Schritt überlegt werden, wie die fertige API aussehen soll. Wenn die Datei `info.csv` mit dem Inhalt der vorherigen Tabelle vorliegt (in einem durch Trennzeichen getrennten Format), sollten Benutzer, die diesen Anbieter später verwenden, einen Code ähnlich dem folgenden Beispiel schreiben können:

```fsharp
let info = new MiniCsv<"info.csv">()
for row in info.Data do
let time = row.Time
printfn "%f" (float time)
```

In diesem Fall sollte der Compiler diese Aufrufe ähnlich wie im folgenden Beispiel konvertieren:

```fsharp
let info = new CsvFile("info.csv")
for row in info.Data do
let (time:float) = row.[1]
printfn "%f" (float time)
```

Für eine optimale Übersetzung muss der Typanbieter einen echten `CsvFile`-Typ in der Assembly des Typanbieters definieren. Typanbieter basieren häufig auf einer Reihe von Hilfstypen und -methoden, um wichtige Logikabschnitte zu umschließen. Da die Maßeinheiten zur Laufzeit gelöscht werden, können Sie `float[]` als gelöschten Typ für eine Zeile verwenden. Der Compiler behandelt jede Spalte als eigenen Typ mit eigener Maßeinheit. Zum Beispiel hat die erste Spalte im Beispiel den Typ `float<meter>`, die zweite den Typ `float<second>` usw. Dennoch kann die gelöschte Darstellung vergleichsweise einfach ausfallen.

Im folgenden Codebeispiel wird die Kernimplementierung veranschaulicht.

```fsharp
// Simple type wrapping CSV data
type CsvFile(filename) =
    // Cache the sequence of all data lines (all lines but the first)
    let data =
        seq {
            for line in File.ReadAllLines(filename) |> Seq.skip 1 ->
                line.Split(',') |> Array.map float
        }
        |> Seq.cache
    member _.Data = data

[<TypeProvider>]
type public MiniCsvProvider(cfg:TypeProviderConfig) as this =
    inherit TypeProviderForNamespaces(cfg)

    // Get the assembly and namespace used to house the provided types.
    let asm = System.Reflection.Assembly.GetExecutingAssembly()
    let ns = "Samples.FSharp.MiniCsvProvider"

    // Create the main provided type.
    let csvTy = ProvidedTypeDefinition(asm, ns, "MiniCsv", Some(typeof<obj>))

    // Parameterize the type by the file to use as a template.
    let filename = ProvidedStaticParameter("filename", typeof<string>)
    do csvTy.DefineStaticParameters([filename], fun tyName [| :? string as filename |] ->

        // Resolve the filename relative to the resolution folder.
        let resolvedFilename = Path.Combine(cfg.ResolutionFolder, filename)

        // Get the first line from the file.
        let headerLine = File.ReadLines(resolvedFilename) |> Seq.head

        // Define a provided type for each row, erasing to a float[].
        let rowTy = ProvidedTypeDefinition("Row", Some(typeof<float[]>))

        // Extract header names from the file, splitting on commas.
        // use Regex matching to get the position in the row at which the field occurs
        let headers = Regex.Matches(headerLine, "[^,]+")

        // Add one property per CSV field.
        for i in 0 .. headers.Count - 1 do
            let headerText = headers.[i].Value

            // Try to decompose this header into a name and unit.
            let fieldName, fieldTy =
                let m = Regex.Match(headerText, @"(?<field>.+) \((?<unit>.+)\)")
                if m.Success then

                    let unitName = m.Groups.["unit"].Value
                    let units = ProvidedMeasureBuilder.Default.SI unitName
                    m.Groups.["field"].Value, ProvidedMeasureBuilder.Default.AnnotateType(typeof<float>,[units])

                else
                    // no units, just treat it as a normal float
                    headerText, typeof<float>

            let prop =
                ProvidedProperty(fieldName, fieldTy,
                    getterCode = fun [row] -> <@@ (%%row:float[]).[i] @@>)

            // Add metadata that defines the property's location in the referenced file.
            prop.AddDefinitionLocation(1, headers.[i].Index + 1, filename)
            rowTy.AddMember(prop)

        // Define the provided type, erasing to CsvFile.
        let ty = ProvidedTypeDefinition(asm, ns, tyName, Some(typeof<CsvFile>))

        // Add a parameterless constructor that loads the file that was used to define the schema.
        let ctor0 =
            ProvidedConstructor([],
                invokeCode = fun [] -> <@@ CsvFile(resolvedFilename) @@>)
        ty.AddMember ctor0

        // Add a constructor that takes the file name to load.
        let ctor1 = ProvidedConstructor([ProvidedParameter("filename", typeof<string>)],
            invokeCode = fun [filename] -> <@@ CsvFile(%%filename) @@>)
        ty.AddMember ctor1

        // Add a more strongly typed Data property, which uses the existing property at runtime.
        let prop =
            ProvidedProperty("Data", typedefof<seq<_>>.MakeGenericType(rowTy),
                getterCode = fun [csvFile] -> <@@ (%%csvFile:CsvFile).Data @@>)
        ty.AddMember prop

        // Add the row type as a nested type.
        ty.AddMember rowTy
        ty)

    // Add the type to the namespace.
    do this.AddNamespace(ns, [csvTy])
```

Beachten Sie die folgenden Punkte in der Implementierung:

- Überladene Konstruktoren gestatten es, entweder die ursprüngliche Datei oder eine andere Datei mit einem identischen Schema zu laden. Dieses Vorgehen ist üblich, wenn Sie einen Typanbieter für lokale oder Remotedatenquellen schreiben. Es ermöglicht die Verwendung einer lokalen Datei als Vorlage für die Remotedaten.

- Sie können den [TypeProviderConfig-Wert](https://msdn.microsoft.com/library/1cda7b9a-3d07-475d-9315-d65e1c97eb44) verwenden, der an den Typanbieterkonstruktor übergeben wird, um relative Dateinamen aufzulösen.

- Sie können die `AddDefinitionLocation`-Methode verwenden, um den Speicherort der bereitgestellten Eigenschaften zu definieren. Wenn Sie eine `Go To Definition` bereitgestellte Eigenschaft verwenden, wird die CSV-Datei in Visual Studio geöffnet.

- Sie können den `ProvidedMeasureBuilder`-Typ verwenden, um nach den SI-Einheiten zu suchen und die relevanten `float<_>`-Typen zu generieren.

### <a name="key-lessons"></a>Hauptlektionen

In diesem Abschnitt wurde erläutert, wie ein Typanbieter für eine lokale Datenquelle mit einem einfachen Schema erstellt werden kann, wenn das Schema in der Datenquelle selbst enthalten ist.

## <a name="going-further"></a>Weiterführende Themen

Die folgenden Abschnitte enthalten Vorschläge für das weitere selbstständige Lernen.

### <a name="a-look-at-the-compiled-code-for-erased-types"></a>Ein Blick auf den kompilierten Code für gelöschte Typen

Damit Sie einen Eindruck davon bekommen, welchen Einfluss die Verwendung des Typanbieters auf den ausgegebenen Code hat, betrachten Sie die folgende Funktion unter Verwendung des `HelloWorldTypeProvider`, der weiter oben in diesem Thema verwendet wurde.

```fsharp
let function1 () =
    let obj1 = Samples.HelloWorldTypeProvider.Type1("some data")
    obj1.InstanceProperty
```

Im Folgenden sehen Sie eine Abbildung des resultierenden Codes, der mit ildasm.exe dekompiliert wurde:

```il
.class public abstract auto ansi sealed Module1
extends [mscorlib]System.Object
{
.custom instance void [FSharp.Core]Microsoft.FSharp.Core.CompilationMappingAtt
ribute::.ctor(valuetype [FSharp.Core]Microsoft.FSharp.Core.SourceConstructFlags)
= ( 01 00 07 00 00 00 00 00 )
.method public static int32  function1() cil managed
{
// Code size       24 (0x18)
.maxstack  3
.locals init ([0] object obj1)
IL_0000:  nop
IL_0001:  ldstr      "some data"
IL_0006:  unbox.any  [mscorlib]System.Object
IL_000b:  stloc.0
IL_000c:  ldloc.0
IL_000d:  call       !!0 [FSharp.Core_2]Microsoft.FSharp.Core.LanguagePrimit
ives/IntrinsicFunctions::UnboxGeneric<string>(object)
IL_0012:  callvirt   instance int32 [mscorlib_3]System.String::get_Length()
IL_0017:  ret
} // end of method Module1::function1

} // end of class Module1
```

Wie das Beispiel zeigt, wurden alle Erwähnungen des Typs `Type1` und der `InstanceProperty`-Eigenschaft gelöscht, sodass nur noch die Vorgänge und Laufzeittypen vorhanden sind.

### <a name="design-and-naming-conventions-for-type-providers"></a>Entwurf- und Namenskonventionen für Typanbieter

Beachten Sie die folgenden Konventionen, wenn Sie Typanbieter erstellen.

**Anbieter für Konnektivitätsprotokolle** Im Allgemeinen sollten die Namen der meisten Anbieter-DLLs für Daten- und Dienstkonnektivitätsprotokolle, z. B. OData- oder SQL-Verbindungen, endend `TypeProvider` oder `TypeProviders`enden. Verwenden Sie z. B. einen DLL-Namen ähnlich der folgenden Zeichenfolge:

`Fabrikam.Management.BasicTypeProviders.dll`

Stellen Sie sicher, dass die bereitgestellten Typen Member des richtigen Namespace sind, und geben Sie das Konnektivitätsprotokoll an, das Sie implementiert haben:

```fsharp
  Fabrikam.Management.BasicTypeProviders.WmiConnection<…>
  Fabrikam.Management.BasicTypeProviders.DataProtocolConnection<…>
```

**Utility Provider für allgemeine Codierung**.  Hilfstypanbieter, wie der zuvor erstellte Anbieter für reguläre Ausdrücke, können in einer Basisbibliothek enthalten sein, wie das folgende Beispiel zeigt:

```fsharp
#r "Fabrikam.Core.Text.Utilities.dll"
```

In diesem Fall würde der bereitgestellte Typ an einer geeigneten Stelle entsprechend den normalen .NET-Entwurfskonventionen erscheinen:

```fsharp
  open Fabrikam.Core.Text.RegexTyped

  let regex = new RegexTyped<"a+b+a+b+">()
```

**Singleton-Datenquellen**. Einige Typanbieter stellen eine Verbindung mit einer einzelnen dedizierten Datenquelle her und machen ausschließlich Daten verfügbar. In diesem Fall sollten Sie das `TypeProvider`-Suffix weglassen und die normalen Konventionen für die .NET-Benennung befolgen:

```fsharp
#r "Fabrikam.Data.Freebase.dll"

let data = Fabrikam.Data.Freebase.Astronomy.Asteroids
```

Weitere Informationen finden Sie in der `GetConnection`-Entwurfskonvention, die weiter unten in diesem Thema beschrieben wird.

### <a name="design-patterns-for-type-providers"></a>Entwurfsmuster für Typanbieter

In den folgenden Abschnitten werden Entwurfsmuster beschrieben, die Sie beim Erstellen von Typanbietern heranziehen können.

#### <a name="the-getconnection-design-pattern"></a>Das Entwurfsmuster GetConnection

Die meisten Typanbieter sollten unter Beachtung des `GetConnection`-Musters geschrieben werden, das von den Typanbietern in FSharp.Data.TypeProviders.dll verwendet wird, wie im folgenden Beispiel gezeigt:

```fsharp
#r "Fabrikam.Data.WebDataStore.dll"

type Service = Fabrikam.Data.WebDataStore<…static connection parameters…>

let connection = Service.GetConnection(…dynamic connection parameters…)

let data = connection.Astronomy.Asteroids
```

#### <a name="type-providers-backed-by-remote-data-and-services"></a>Typanbieter, die auf Remotedaten und -dienste zugreifen

Bevor Sie einen Typanbieter erstellen, der auf Remotedaten und -dienste zugreift, müssen Sie einige Probleme berücksichtigen, die bei der Programmierung von Verbindungen auftreten können. Folgende Überlegungen sollten Sie berücksichtigen:

- Schemazuordnung

- Aktivität und Ungültigkeit bei Schemaänderungen

- Zwischenspeicherung von Schemas

- Asynchrone Implementierungen von Datenzugriffsvorgängen

- Unterstützen von Abfragen, einschließlich LINQ-Abfragen

- Anmeldeinformationen und Authentifizierung

Die Probleme werden in diesem Thema nicht weiter im Detail erläutert.

### <a name="additional-authoring-techniques"></a>Weitere Techniken für Entwurf und Erstellung

Wenn Sie eigene Typanbieter schreiben, können die folgenden zusätzlichen Techniken ebenfalls hilfreich sein.

### <a name="creating-types-and-members-on-demand"></a>Erstellen von Typen und Membern nach Bedarf

Die ProvidedType-API stellt verzögerte Versionen von AddMember zur Verfügung.

```fsharp
  type ProvidedType =
      member AddMemberDelayed  : (unit -> MemberInfo)      -> unit
      member AddMembersDelayed : (unit -> MemberInfo list) -> unit
```

Diese Versionen werden verwendet, um Typenräume zu erstellen, die erst bei Bedarf generiert werden.

### <a name="providing-array-types-and-generic-type-instantiations"></a>Bereitstellen von Arraytypen und generischen Typinstanziierungen

Sie erstellen bereitgestellte Member (deren Signaturen Arraytypen, Byref-Typen und `MakeArrayType`Instanziierungen generischer Typen enthalten), indem Sie die normale , `MakePointerType`und `MakeGenericType` für jede Instanz von <xref:System.Type>, einschließlich `ProvidedTypeDefinitions`.

> [!NOTE]
> In einigen Fällen müssen Sie den `ProvidedTypeBuilder.MakeGenericType`Helfer in verwenden.  Weitere Informationen finden Sie in der [Dokumentation zum Typanbieter-SDK.](https://github.com/fsprojects/FSharp.TypeProviders.SDK/blob/master/README.md#explicit-construction-of-code-makegenerictype-makegenericmethod-and-uncheckedquotations)

### <a name="providing-unit-of-measure-annotations"></a>Bereitstellen von Maßeinheiten als Anmerkung

Die ProvidedTypes-API stellt Hilfsprogramme zur Angabe von Maßeinheiten für Werte bereit. Um beispielsweise den Typ `float<kg>` bereitzustellen, verwenden Sie folgenden Code:

```fsharp
  let measures = ProvidedMeasureBuilder.Default
  let kg = measures.SI "kilogram"
  let m = measures.SI "meter"
  let float_kg = measures.AnnotateType(typeof<float>,[kg])
```

  Um den Typ `Nullable<decimal<kg/m^2>>` bereitzustellen, verwenden Sie folgenden Code:

```fsharp
  let kgpm2 = measures.Ratio(kg, measures.Square m)
  let dkgpm2 = measures.AnnotateType(typeof<decimal>,[kgpm2])
  let nullableDecimal_kgpm2 = typedefof<System.Nullable<_>>.MakeGenericType [|dkgpm2 |]
```

### <a name="accessing-project-local-or-script-local-resources"></a>Zugreifen auf lokale Ressourcen im Projekt oder in einem Skript

Jede Instanz eines Typanbieters kann während der Erstellung als `TypeProviderConfig`-Wert angegeben werden. Dieser Wert enthält den „Auflösungsordner“ für den Anbieter (dass heißt, den Projektordner für die Kompilierung oder das Verzeichnis, das ein Skript enthält), die Liste der Assemblys, auf die verwiesen wird, und einige andere Informationen.

### <a name="invalidation"></a>Aufheben einer Validierung

Anbieter können Signale zum Aufheben einer Validierung auslösen, um den F#-Sprachdienst zu benachrichtigen, dass sich die Schemaannahmen möglicherweise geändert haben. Bei einer Invalidierung wird die Typüberprüfung wiederholt, sofern der Anbieter in Visual Studio gehostet wird. Dieses Signal wird ignoriert, wenn der Anbieter in F# Interactive oder vom F#-Compiler (fsc.exe) gehostet wird.

### <a name="caching-schema-information"></a>Zwischenspeichern von Schemainformationen

Anbieter müssen für den Zugriff auf Schemainformationen häufig einen Cache verwenden. Die zwischengespeicherten Daten sollten unter einem Dateinamen gespeichert werden, der als statischer Parameter oder in den Benutzerdaten angegeben wird. Ein Beispiel für die Schemazwischenspeicherung ist der `LocalSchemaFile`-Parameter in den Typanbietern in der `FSharp.Data.TypeProviders`-Assembly. In der Implementierung dieser Anbieter weist der statische Parameter den Typanbieter an, die Schemainformationen aus der angegebenen lokalen Datei abzurufen, anstatt über das Netzwerk auf die Datenquelle zuzugreifen. Um zwischengespeicherte Schemainformationen verwenden zu können, müssen Sie außerdem den statischen Parameter `ForceUpdate` auf `false` festlegen. Sie können ein ähnliches Verfahren verwenden, um sowohl online als auch offline Datenzugriffe zu ermöglichen.

### <a name="backing-assembly"></a>Unterstützungsassembly

Wenn Sie `.dll` eine `.exe` oder eine Datei kompilieren, wird die unterstützende DLL-Datei für generierte Typen statisch mit der resultierenden Assembly verknüpft. Dieser Link wird erstellt, indem die IL-Typdefinitionen (Intermediate Language) und alle verwalteten Ressourcen aus der Unterstützungsassembly in die endgültige Assembly kopiert werden. Wenn Sie F# Interactive verwenden, wird die zugrunde liegende DLL-Datei nicht kopiert und stattdessen direkt in den F# Interactive-Prozess geladen.

### <a name="exceptions-and-diagnostics-from-type-providers"></a>Ausnahmen und Diagnose von Typanbietern

Jede Verwendung der Member von bereitgestellten Typen kann eine Ausnahme auslösen. Wenn ein Typanbieter eine Ausnahme auslöst, ordnet der Hostcompiler den Fehler immer einem bestimmten Typanbieter zu.

- Typanbieterausnahmen sollten niemals zu internen Compilerfehlern führen.

- Typanbieter können keine Warnungen ausgeben.

- Wenn ein Typanbieter im F#-Compiler, in einer F#-Entwicklungsumgebung oder in F# Interactive gehostet wird, werden alle Ausnahmen dieses Anbieters abgefangen. Die Message-Eigenschaft enthält dabei immer den Fehlertext, und es wird keine Stapelüberwachung angezeigt. Wenn Sie eine Ausnahme auslösen möchten, können Sie `System.NotSupportedException`die `System.IO.IOException` `System.Exception`folgenden Beispiele auslösen: , , .

#### <a name="providing-generated-types"></a>Bereitstellen von generierten Typen

Bisher wurde in diesem Dokument erläutert, wie ausgeahandelte Typen zur Verfügung gebracht werden können. Sie können den Typanbietermechanismus in F# auch verwenden, um generierte Typen bereitzustellen, die als echte .NET-Typdefinitionen in das Programm des Benutzers übernommen werden. Auf generierte bereitgestellte Typen müssen Sie über die Typdefinition verweisen.

```fsharp
open Microsoft.FSharp.TypeProviders

type Service = ODataService<"http://services.odata.org/Northwind/Northwind.svc/">
```

Der Hilfscode "ProvidedTypes-0.2", der Teil der Version 3.0 von F# ist, bietet nur eine eingeschränkte Unterstützung für das Bereitstellen von generierten Typen. Die folgenden Aussagen müssen für eine generierte Typdefinition zutreffen:

- `isErased` muss auf `false` festgelegt werden.

- Der generierte Typ muss einem `ProvidedAssembly()`neu erstellten hinzugefügt werden, der einen Container für generierte Codefragmente darstellt.

- Der Anbieter muss über eine Assembly verfügen, der eine tatsächliche .NET-DLL-Datei mit einer entsprechenden, auf dem Datenträger verfügbaren DLL-Datei zugrunde liegt.

## <a name="rules-and-limitations"></a>Regeln und Einschränkungen

Berücksichtigen Sie beim Schreiben von Typanbietern die folgenden Regeln und Einschränkungen.

### <a name="provided-types-must-be-reachable"></a>Vorausgesetzt, typen müssen erreichbar sein

Alle bereitgestellten Typen müssen für die nicht geschachtelten Typen erreichbar sein. Die nicht geschachtelten Typen werden im Aufruf des `TypeProviderForNamespaces`-Konstruktors oder bei einem Aufruf von `AddNamespace` übergeben. Wenn der Anbieter z. B. den Typ `StaticClass.P : T` bereitstellt, müssen Sie sicherstellen, dass T entweder ein nicht geschachtelter Typ ist oder unter einem Typ geschachtelt wird.

Einige Anbieter verwenden beispielsweise eine statische Klasse wie `DataTypes`, die diese `T1, T2, T3, ...`-Typen enthält. Andernfalls wird ein Fehler mit der Meldung ausgegeben, dass in der Assembly A ein Verweis auf den Typ T enthalten ist, der Typ aber in dieser Assembly nicht gefunden wurde. Wenn dieser Fehler angezeigt wird, stellen Sie sicher, dass alle Untertypen für die Anbietertypen erreichbar sind. Hinweis: `T1, T2, T3...` Diese Typen werden als *On-the-fly-Typen* bezeichnet. Denken Sie daran, diese in einen erreichbaren Namespace oder in einen übergeordneten Typ einzufügen.

### <a name="limitations-of-the-type-provider-mechanism"></a>Einschränkungen des Typanbietermechanismus

Für den Typanbietermechanismus in F# gelten folgende Einschränkungen:

- Die zugrunde liegende Infrastruktur für Typanbieter in F# unterstützt keine generischen bereitgestellten Typen und keine generischen bereitgestellten Methoden.

- Der Mechanismus unterstützt keine geschachtelten Typen mit statischen Parametern.

## <a name="development-tips"></a>Tipps für die Entwicklung

Während des Entwicklungsprozesses finden Sie möglicherweise folgende Hilfreiche:

### <a name="run-two-instances-of-visual-studio"></a>Ausführen von zwei Instanzen von Visual Studio

Sie können den Typanbieter in einer Instanz entwickeln und in der anderen Instanz testen, da die Test-IDE eine Sperre für die DLL-Datei definiert, die verhindert, dass der Typanbieter neu erstellt wird. Daher müssen Sie die zweite Instanz von Visual Studio schließen, wenn der Anbieter in der ersten Instanz erstellt wird, und anschließend die zweite Instanz erneut öffnen, sobald die Erstellung abgeschlossen ist.

### <a name="debug-type-providers-by-using-invocations-of-fscexe"></a>Debugtypanbieter mithilfe von Aufrufen von fsc.exe

Sie können Typanbieter mit den folgenden Tools aufrufen:

- fsc.exe (der F#-Befehlszeilencompiler)

- fsi.exe (der F# Interactive-Compiler)

- devenv.exe (Visual Studio)

In vielen Fällen können Typanbieter am einfachsten debuggt werden, indem Sie fsc.exe zusammen mit einer Testskriptdatei verwenden (z. B. script.fsx). Sie können ein Debugger von einer Eingabeaufforderung aus starten.

```console
devenv /debugexe fsc.exe script.fsx
```

  Zur Protokollierung können Sie die normale Ausgabe auf die Standardausgabe verwenden.

## <a name="see-also"></a>Weitere Informationen

- [Typanbieter](index.md)
- [Das Type Provider SDK](https://github.com/fsprojects/FSharp.TypeProviders.SDK)
