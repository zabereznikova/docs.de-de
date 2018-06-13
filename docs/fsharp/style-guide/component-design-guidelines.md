---
title: F#-Komponente Entwurfsrichtlinien
description: Erfahren Sie, die Richtlinien zum Schreiben von F#-Komponenten, die für die Nutzung durch andere Aufrufer vorgesehen.
ms.date: 05/14/2018
ms.openlocfilehash: 7e71710b1bc2fe3e8d7a5a091513a1432650dc04
ms.sourcegitcommit: 43924acbdbb3981d103e11049bbe460457d42073
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/23/2018
ms.locfileid: "34458085"
---
# <a name="f-component-design-guidelines"></a>F#-Komponente Entwurfsrichtlinien

Dieses Dokument stellt einen Satz von Richtlinien zum Entwerfen einer Komponente für f#-Programmierung, basierend auf den F#-Komponente Entwurfsrichtlinien, 14, Microsoft Research und [eine andere Version](https://fsharp.org/specs/component-design-guidelines/) ursprünglich curated und von der F#-Software Foundation verwaltet.

Dieses Dokument wird davon ausgegangen, dass Sie mit der f#-Programmierung vertraut sind. Vielen Dank für ihre Beiträge und hilfreiche Feedback auf verschiedenen Versionen dieses Handbuchs f#-Community.

## <a name="overview"></a>Übersicht

Dieses Dokument untersucht die Probleme im Zusammenhang mit der F#-Komponentenentwurf und die sicherheitscodierung. Eine Komponente kann Folgendes bedeuten:

* Eine Ebene in f#-Projekts, das externe Consumer innerhalb dieses Projekts verfügt.
* Eine Bibliothek hinweg Assembly für die Verwendung von f#-Code vorgesehen.
* Eine Bibliothek für die Nutzung von jeder Assembly hinweg vorgesehen.
* Eine Bibliothek, die für die Verteilung über ein paketrepository gedacht sind, wie z. B. [NuGet](https://nuget.org).

Führen Sie die in diesem Artikel beschriebene Techniken der [fünf Prinzipien der gute f#-Code](index.md#five-principles-of-good-f-code), und daher beide funktionale nutzen und die Objekt-Programmierung nach Bedarf.

Unabhängig von der Methodik Flächen der Komponente und Bibliothek-Designer eine Reihe von praktische und prosaischen Problemen, beim Versuch, eine API zu erstellen, die von Entwicklern am einfachsten verwendet werden kann. Zudem Anwendung von der [Entwurfsrichtlinien von .NET Bibliothek](../../standard/design-guidelines/index.md) wird Sie beim Erstellen eines konsistenten Satz von APIs, nutzen angenehmeren sind, lenken.

## <a name="general-guidelines"></a>Allgemeine Richtlinien

Es gibt einige universelle Richtlinien, die für f#-Bibliotheken, unabhängig von der die Zielgruppe für die Bibliothek gelten.

### <a name="learn-the-net-library-design-guidelines"></a>Erfahren Sie, die Entwurfsrichtlinien für .NET-Bibliothek

Unabhängig von der Art der F#-codieren, Sie nehmen, ist es sinnvoll sein, eine ausreichende praktische Kenntnisse der [Entwurfsrichtlinien von .NET Bibliothek](../../standard/design-guidelines/index.md). Die meisten anderen f# und .NET Programmierer werden mit diesen Richtlinien vertraut sein, und .NET Code entsprechen, diese erwarten.

Die Entwurfsrichtlinien von .NET Bibliothek bieten eine allgemeine Anleitung Bezug auf Benennung, Entwerfen von Klassen und Schnittstellen, Member-Entwurf (Eigenschaften, Methoden, Ereignisse usw.) und vieles mehr, und sind eine nützliche ersten Punkt des Verweises für eine Vielzahl von Leitfaden zum Design.

### <a name="add-xml-documentation-comments-to-your-code"></a>XML-Dokumentationskommentare in den Code hinzufügen

XML-Dokumentation von öffentlichen APIs stellen Sie sicher, dass Benutzer hervorragende Intellisense und den QuickInfos abrufen können, verwenden diese Typen und Member, und aktivieren erstellen Dokumentation für die Bibliothek von Dateien. Finden Sie unter der [XML-Dokumentation](../language-reference/xml-documentation.md) über verschiedene XML‑Tags, die für zusätzliche Markup im Xmldoc Kommentare verwendet werden können.

```fsharp
/// A class for representing (x,y) coordinates
type Point =

    /// Computes the distance between this point and another
    member DistanceTo : otherPoint:Point -> float
```

Sie können auch die Kurzform XML-Kommentare verwenden (`/// comment`), oder die standardmäßigen XML-Kommentare (`///<summary>comment</summary>`).

### <a name="consider-using-explicit-signature-files-fsi-for-stable-library-and-component-apis"></a>Erwägen Sie explizite Signaturdateien (".FSI") für stabile und APIs-Komponente

Verwenden explizite Signaturen Dateien in F#-Bibliothek bietet eine kurze Zusammenfassung der öffentliche API, die jeweils sichergestellt wird, dass Sie wissen, die vollständigen öffentliche Oberfläche der Bibliothek als auch bietet eine saubere Trennung zwischen Dokumentation öffentliche und interne Details zur Implementierung. Beachten Sie, dass die Signaturdateien Unstimmigkeiten hinzufügen, ändern die öffentliche API durch Anfordern von Änderungen, die in der Implementierung und die Signatur Dateien vorgenommen werden. Daher sollten Signaturdateien in der Regel nur eingeführt werden, wenn eine API größtenteils durchgeführten Konsolidierung werden und ist nicht mehr erwartungsgemäß erheblich ändern.

### <a name="always-follow-best-practices-for-using-strings-in-net"></a>Führen Sie immer die bewährte Methoden für die Verwendung von Zeichenfolgen in .NET

Führen Sie die [bewährte Methoden für die Verwendung von Zeichenfolgen in .NET](../../standard/base-types/best-practices-strings.md) Anleitung. Insbesondere immer explizit *kulturellen Absicht* in der Konvertierung und Vergleich von Zeichenfolgen (falls zutreffend).

## <a name="guidelines-for-f-facing-libraries"></a>Richtlinien für f#-Bibliotheken zugängliche

In diesem Abschnitt werden Empfehlungen für die Entwicklung von öffentlichen f#-Bibliotheken; zugängliche d. h. Bibliotheken Verfügbarmachen von öffentlichen APIs, die von F#-Entwicklern genutzt werden sollen. Es gibt eine Vielzahl von Bibliotheksentwurf Empfehlungen gelten speziell für f#. In Ermangelung der spezifischen Empfehlungen, die folgen, werden die Entwurfsrichtlinien von .NET Bibliothek fallback Anleitungen.

### <a name="naming-conventions"></a>Namenskonventionen 

#### <a name="use-net-naming-and-capitalization-conventions"></a>Verwenden Sie Benennungskonventionen für .NET benennen und Groß-/Kleinschreibung

In der folgenden Tabelle folgt .NET benennen und Groß-/Kleinschreibung die Konventionen. Es sind kleine Ergänzungen auch f#-Konstrukte enthalten.

| Konstrukt | Case | Segment | Beispiele | Hinweise |
|-----------|------|------|----------|-------|
| Konkrete Typen | "PascalCase" | Nomen / adjektivische | Liste, Double, komplexe | Konkrete Typen sind Strukturen, Klassen, Enumerationen, Delegaten, Datensätze und Unions. Obwohl Typnamen traditionell Kleinbuchstaben in mit OCaml handelt, hat f# das .NET Benennungsschema für Typen eingeführt.
| DLLs           | "PascalCase" |                 | Fabrikam.Core.dll |  |
| Union-tags     | "PascalCase" | Nomen | Einige hinzuzufügen, Erfolg | Verwenden Sie ein Präfix nicht in öffentlichen APIs. Verwenden Sie optional ein Präfix, wenn interne, z. B. ''' Teams geben = TAlpha | TBeta | TDelta. "" |
| event          | "PascalCase" | Verb | ValueChanged / ValueChanging |  |
| Ausnahmen     | "PascalCase" |      | WebException | Name sollte mit "Ausnahme" enden. |
| Feld          | "PascalCase" | Nomen | CurrentName  | |
| Schnittstellentypen |  "PascalCase" | Nomen / adjektivische | IDisposable | Name sollte mit "I" beginnen. |
| Methode |  "PascalCase" |  Verb | ToString | |
| Namespace | "PascalCase" | | Microsoft.FSharp.Core | Verwenden Sie in der Regel `<Organization>.<Technology>[.<Subnamespace>]`, obwohl die Organisation gelöscht werden, wenn die Technologie unabhängig von der Organisation ist. |
| Parameter | camelCase ändern möchten | Nomen |  TypeName, Transform, Bereich | |
| Werte (intern) | camelCase ändern möchten oder "PascalCase" | Nomen / Verb |  GetValue myTable |
| Werte (extern) | camelCase ändern möchten oder "PascalCase" | Nomen-verb  | List.Map Dates.Today | Let-Bindung Werte sind häufig öffentlich, beim traditionellen funktionale Entwurfsmuster stehenden. Allerdings verwenden Sie im Allgemeinen "PascalCase" Wenn der Bezeichner der anderen .NET-Sprachen verwendet werden kann. |
| Eigenschaft  | "PascalCase"  | Nomen / adjektivische  | IsEndOfFile BackColor  | Boolesche Eigenschaften, die in der Regel verwenden, und kann und abstimmungszeuge, wie in IsEndOfFile nicht IsNotEndOfFile sein.

#### <a name="avoid-abbreviations"></a>Vermeiden von Abkürzungen

Die Richtlinien .NET abgeraten werden die Verwendung von Abkürzungen (z. B. "verwenden `OnButtonClick` statt `OnBtnClick`"). Allgemeine Abkürzungen wie z. B. `Async` für "Asynchrone", toleriert werden. Diese Richtlinie ist für die funktionale Programmierung manchmal ignoriert. beispielsweise `List.iter` verwendet eine Abkürzung für "Iteration". Aus diesem Grund mithilfe von Abkürzungen tendenziell um eine genauere speichersteuerung in f# toleriert werden-zu-f#-Programmierung, aber immer noch in der Regel in öffentlichen Komponentenentwurf vermieden werden sollte.

#### <a name="avoid-casing-name-collisions"></a>Vermeiden Sie die Groß-/Kleinschreibung Namenskonflikte

Die Richtlinien .NET sagen, dass die Groß-/Kleinschreibung allein verwendet werden, um Namenskonflikte, zu unterscheiden, da einige Clientsprachen (z. B. Visual Basic) sind, die Groß-/Kleinschreibung.

#### <a name="use-acronyms-where-appropriate"></a>Verwenden Sie bei Bedarf Akronyme

Akronyme, wie z. B. XML sind keine Abkürzungen und werden häufig in .NET-Bibliotheken uncapitalized Format (Xml) verwendet. Nur bekannte, bekannter Akronyme vorgesehen.

#### <a name="use-pascalcase-for-generic-parameter-names"></a>Verwenden Sie "PascalCase" für generische parameter

Verwenden Sie "PascalCase" für generische Parameternamen in öffentlichen APIs, einschließlich für f#-Bibliotheken nach. Insbesondere verwenden Sie Namen wie `T`, `U`, `T1`, `T2` für beliebige generische Parameter, und wenn bestimmte Namen Sinn, klicken Sie dann für f#-nach außen verfügbaren Bibliotheken verwenden Sie Namen wie `Key`, `Value`, `Arg`(aber nicht z. B. `TKey`).

#### <a name="use-either-pascalcase-or-camelcase-for-public-functions-and-values-in-f-modules"></a>Verwenden Sie "PascalCase" oder camelCase ändern möchten, für öffentliche Funktionen und die Werte in F#-Modulen

camelCase ändern möchten dient für öffentliche Funktionen, die darauf ausgelegt sind, verwendet werden, nicht qualifizierten (z. B. `invalidArg`), und für die "standard Auflistungsfunktionen" (z. B. List.map). In beiden Fällen verhalten sich die Funktionsnamen ähnlich wie Schlüsselwörter in der Sprache.

### <a name="object-type-and-module-design"></a>-Objekt, Typ und Modul Entwurf

#### <a name="use-namespaces-or-modules-to-contain-your-types-and-modules"></a>Verwenden von Namespaces oder der Module, enthalten die Typen und die Module

Jede f#-Datei in eine Komponente sollte eine Namespacedeklaration oder eine Moduldeklaration beginnen.

```fsharp
namespace Fabrikam.BasicOperationsAndTypes

type ObjectType1() =
    ...

type ObjectType2() =
     ...

module CommonOperations =
    ...
```

oder

```fsharp
module Fabrikam.BasicOperationsAndTypes

type ObjectType1() =
    ...

type ObjectType2() =
    ...

module CommonOperations =
    ...
```

Die Unterschiede zwischen der Verwendung von Modulen und Namespaces zum Organisieren von Code auf der obersten Ebene sind wie folgt:

* Namespaces können mehrere Dateien umfassen.
* Namespaces darf keine f#-Funktionen enthalten, es sei denn, sie in einem inneren-Modul
* Der Code für ein beliebiges Modul angegebenen muss innerhalb einer einzelnen Datei enthalten sein
* Module der obersten Ebene können f#-Funktionen ohne die Notwendigkeit eines inneren Moduls enthalten.

Die Wahl zwischen einem Namespace der obersten Ebene oder das Modul wirkt sich auf der kompilierten Form des Codes und daher wirken sich die Ansicht aus anderen Ihre API schließlich außerhalb von f#-Code verwendet werden sollen.

#### <a name="use-methods-and-properties-for-operations-intrinsic-to-object-types"></a>Verwenden von Methoden und Eigenschaften für Vorgänge für Objekte des Typs

Wenn Sie mit Objekten arbeiten, empfiehlt es sich um sicherzustellen, dass nutzbar Funktionalität als Methoden und Eigenschaften für diesen Typ implementiert wird.

```fsharp
type HardwareDevice() =

    member this.ID = ...

    member this.SupportedProtocols = ...

type HashTable<'Key,'Value>(comparer: IEqualityComparer<'Key>) =

    member this.Add(key, value) = ...

    member this.ContainsKey(key) = ...

    member this.ContainsValue(value) = ...
```

Der Großteil der Funktionalität für ein bestimmtes Element muss unbedingt nicht in diesen Member implementiert werden, aber der nutzbar Teil dieser Funktionalität werden sollte.

#### <a name="use-classes-to-encapsulate-mutable-state"></a>Verwenden von Klassen zum Kapseln von veränderlichen Zustand

In F# erläutert werden muss dies nur, dass der Status nicht bereits von einem anderen Sprachkonstrukt, z. B. ein Abschluss, Sequenzausdruck oder asynchrone Berechnung gekapselt ist, in denen erfolgen.

```fsharp
type Counter() =
    // let-bound values are private in classes.
    let mutable count = 0

    member this.Next() =
        count <- count + 1
        count
```

#### <a name="use-interfaces-to-group-related-operations"></a>Verwenden Sie Schnittstellen, um Gruppen verwandte Vorgänge

Verwenden Sie Schnittstellentypen werden zur Darstellung von einer Reihe von Vorgängen. Dies ist die bevorzugte zu anderen Optionen, z. B. Tupel von Funktionen oder Funktionen Datensätze.

```fsharp
type Serializer =
    abstract Serialize<'T> : preserveRefEq: bool -> value: 'T -> string
    abstract Deserialize<'T> : preserveRefEq: bool -> pickle: string -> 'T
```

Vorzuziehen:

```fsharp
type Serializer<'T> = {
    Serialize : bool -> 'T -> string
    Deserialize : bool -> string -> 'T
}
```

Schnittstellen sind erstrangige Konzepte in .NET, das Sie verwenden können, um zu erreichen, was Funktionselemente normalerweise Sie erlangen. Darüber hinaus können sie zum Codieren von existenzielle Typen in das Programm die Datensätze von Funktionen nicht verwendet werden.

#### <a name="use-a-module-to-group-functions-which-act-on-collections"></a>Verwenden Sie ein Modul, um die tätig Gruppenfunktionen Auflistungen

Wenn Sie einen Auflistungstyp definieren, verwenden Sie möglicherweise ein Standardsatz von Vorgängen wie `CollectionType.map` und `CollectionType.iter`) für neuer Sammlungstypen.

```fsharp
module CollectionType =
    let map f c =
        ...
    let iter f c =
        ...
```

Wenn Sie solche ein Moduls enthalten, führen Sie die standardmäßigen Benennungskonventionen für FSharp.Core-Funktionen.

#### <a name="use-a-module-to-group-functions-for-common-canonical-functions-especially-in-math-and-dsl-libraries"></a>Verwenden Sie ein Modul Gruppenfunktionen für allgemeine, kanonische Funktionen, insbesondere in mathematischen und DSL-Bibliotheken

Beispielsweise `Microsoft.FSharp.Core.Operators` ist eine Auflistung automatisch geöffnete, der Funktionen der obersten Ebene (z. B. `abs` und `sin`) von FSharp.Core.dll bereitgestellt.

Entsprechend kann eine Bibliothek Statistiken ein Moduls mit Funktionen enthalten `erf` und `erfc`, wobei dieses Modul dient, explizit oder automatisch geöffnet werden.

#### <a name="consider-using-requirequalifiedaccess-and-carefully-apply-autoopen-attributes"></a>RequireQualifiedAccess in Betracht, und wenden sorgfältig AutoOpen-Attribute

Hinzufügen der `[<RequireQualifiedAccess>]` Attribut auf ein Modul gibt an, dass das Modul kann nicht geöffnet werden, dass Verweise auf die Elemente des Moduls explizite benötigen Zugriff qualifiziert. Z. B. die `Microsoft.FSharp.Collections.List` -Modul ist dieses Attribut.

Dies ist hilfreich, wenn Funktionen und Werte im Modul Namen haben, die wahrscheinlich einen Konflikt mit Namen in anderen Modulen ausgeführt werden. Einen qualifizierten Zugriff erfordern, kann erheblich die langfristige Verwaltbarkeit und die Evolvability einer Bibliothek erhöhen.

Hinzufügen der `[<AutoOpen>]` Attribut auf ein Modul bedeutet, dass das Modul wird geöffnet, wenn der übergeordnete Namespace geöffnet wird. Die `[<AutoOpen>]` Attribut möglicherweise auch zu einer Assembly an, dass ein Modul, das automatisch geöffnet wird, wenn die Assembly verwiesen wird, angewendet werden.

Angenommen, eine Statistik Bibliothek **MathsHeaven.Statistics** enthält möglicherweise eine `module MathsHeaven.Statistics.Operators` , die Funktionen enthalten `erf` und `erfc`. Es ist angemessen, markieren Sie dieses Modul als `[<AutoOpen>]`. Dies bedeutet, dass `open MathsHeaven.Statistics` wird auch dieses Modul geöffnet, und schalten Sie die Namen `erf` und `erfc` einbinden. Eine andere funktionierende nutzen `[<AutoOpen>]` für Module mit Erweiterungsmethoden ist.

Lösen von `[<AutoOpen>]` führt zu einem belasteten Namespaces und das Attribut sollte mit Vorsicht verwendet werden. Für bestimmte Bibliotheken in bestimmten Domänen, zielgerichtete Verwendung von `[<AutoOpen>]` zu bessere Nutzbarkeit führen kann.

#### <a name="consider-defining-operator-members-on-classes-where-using-well-known-operators-is-appropriate"></a>Definieren Sie Operator Member für Klassen, die mithilfe von bekannter Operatoren geeignet ist

In einigen Fällen werden Klassen verwendet, um mathematische Konstrukte wie Vektoren zu modellieren. Bei der Domäne, die modelliert werden bekannte Operatoren sind, eignet sie als Mitglieder für die Klasse zu definieren.

```fsharp
type Vector(x:float) =

    member v.X = x

    static member (*) (vector:Vector, scalar:float) = Vector(vector.X * scalar)

    static member (+) (vector1:Vector, vector2:Vector) = Vector(vector1.X + vector2.X)

let v = Vector(5.0)

let u = v * 10.0
```

In dieser Anleitung entspricht .NET Hilfestellungen für diese Typen. Allerdings kann es wichtig sein, außerdem im F#-Code wie dies zulässt, dass diese Typen in Verbindung mit der f#-Funktionen und Methoden mit Membereinschränkungen, z. B. List.sumBy verwendet werden.

#### <a name="consider-using-compiledname-to-provide-a-net-friendly-name-for-other-net-language-consumers"></a>Erwägen Sie CompiledName bereitstellen ein. NET-Anzeigenamen für andere .NET Language-Consumer

In einigen Fällen möchten Sie Sie möglicherweise etwas in ein Format für F#-Consumer nennen (z. B. ein statischer Member in Kleinbuchstaben Kanton als handele es sich um ein Modul-gebundenen Funktionen), jedoch über einen anderen Stil für den Namen, wenn es in eine Assembly kompiliert wird. Sie können die `[<CompiledName>]` Attribut nutzen die Assembly nicht f#-Code ein anderen Format bereit.

```fsharp
type Vector(x:float, y:float) =

    member v.X = x
    member v.Y = y

    [<CompiledName("Create")>]
    static member create x y = Vector (x, y)

let v = Vector.create 5.0 3.0
```

Mithilfe von `[<CompiledName>]`, können Sie .NET Benennungskonventionen für nicht F#-Consumern der Assembly.

#### <a name="use-method-overloading-for-member-functions-if-doing-so-provides-a-simpler-api"></a>Verwenden Sie Methode für Memberfunktionen zu überladen, wenn so eine einfachere-API bereitgestellt werden

Überladen von Methoden ist ein leistungsstarkes Tool zur Vereinfachung einer API, die ähnliche Funktionen ausführen muss, aber mit verschiedenen Optionen oder Argumente.

```fsharp
type Logger() =

    member this.Log(message) =
        ...
    member this.Log(message, retryPolicy) =
        ...
```

In F# erläutert werden ist es eher üblich, dass die Anzahl von Argumenten anstelle der Datentypen der Argumente überladen.

#### <a name="hide-the-representations-of-record-and-union-types-if-the-design-of-these-types-is-likely-to-evolve"></a>Blenden Sie die Darstellung des Datensatzes und union-Typen aus, wenn der Entwurf dieser Typen weiterentwickelt wird

Vermeiden Sie die konkrete Darstellungen von Objekten offenzulegen. Z. B. die konkrete Darstellung des <xref:System.DateTime> Werte ist von der externen, öffentliche API des Entwurfs .NET Bibliothek nicht offen gelegt. Zur Laufzeit weiß der Common Language Runtime die Commit-Implementierung, die in der gesamten Ausführung verwendet werden. Allerdings nicht kompilierter Code selbst Abhängigkeiten von den konkreten Darstellung zu übernehmen.

#### <a name="avoid-the-use-of-implementation-inheritance-for-extensibility"></a>Vermeiden Sie die Verwendung von implementierungsvererbung für Erweiterbarkeit

In F# erläutert werden ist die implementierungsvererbung selten verwendet. Darüber hinaus sind Vererbungshierarchien häufig komplex und schwierig zu ändern, wenn neue Anforderungen eingehen. Vererbung-Implementierung befindet sich noch in f# für Kompatibilität und seltenen Fällen, bei denen es die beste Lösung eines Problems, aber alternative Techniken sollten beim Entwerfen der Polymorphie, z. B.-Implementierung in F#-Programmen gesucht.

### <a name="function-and-member-signatures"></a>Funktion und Element-Signaturen

#### <a name="use-tuples-for-return-values-when-returning-a-small-number-of-multiple-unrelated-values"></a>Verwenden Sie Tupel für Rückgabewerte, wenn eine kleine Anzahl von mehreren nicht verknüpften Werten zurückgeben

Hier ist ein gutes Beispiel für die Verwendung eines Tupels in einem Rückgabetyp:

```fsharp
val divrem : BigInteger -> BigInteger -> BigInteger * BigInteger
```

Rückgabetypen Sie für die, die viele Komponenten enthält, oder wenn Komponenten mit einer einzelnen identifizierbaren Entität verknüpft sind, erwägen Sie, mithilfe eines benannten Typs statt eines tupelausdrucks.

#### <a name="use-asynct-for-async-programming-at-f-api-boundaries"></a>Verwendung `Async<T>` für asynchrone Programmierung an den Begrenzungen der f#-API

Es ist ein entsprechender synchronen Vorgang mit dem Namen `Operation` zurückgibt eine `T`, den Namen der asynchrone Vorgang sollte `AsyncOperation` zurückgibt `Async<T>` oder `OperationAsync` zurückgibt `Task<T>`. Für häufig verwendete Typen von .NET Begin/End-Methoden verfügbar zu machen, die in Betracht `Async.FromBeginEnd` zum Schreiben von Erweiterungsmethoden als Fassade das f# asynchrone Programmiermodell für die .NET APIs bereitstellen.

```fsharp
type SomeType =
    member this.Compute(x:int) : int =
        ...
    member this.AsyncCompute(x:int) : Async<int> =
        ...

type System.ServiceModel.Channels.IInputChannel with
    member this.AsyncReceive() =
        ...
```

### <a name="exceptions"></a>Ausnahmen

Ausnahmen sind in .NET herausragende; d. h., sollten sie nicht häufig zur Laufzeit auftreten. Wenn dies der Fall, wird die darin enthaltenen Informationen nützlich. Ausnahmen sind ein Kern erstklassige Konzept von .NET. Daher IT folgt, die entsprechende Anwendung der Ausnahmen als Teil des Entwurfs der Schnittstelle einer Komponente verwendet werden sollten.

#### <a name="follow-the-net-guidelines-for-exceptions"></a>Befolgen Sie die .NET Richtlinien für Ausnahmen

Die [Entwurfsrichtlinien von .NET Bibliothek](../../standard/design-guidelines/exceptions.md) hervorragende Ratschläge für die Verwendung von Ausnahmen im Kontext der Programmierung für alle .NET erteilen. Nachfolgend sind einige der folgenden Richtlinien:

* Verwenden Sie Ausnahmen nicht für normale ablaufsteuerung aus. Obwohl diese Technik in Sprachen wie z. B. mit OCaml häufig verwendet wird, ist fehleranfälliger und kann auf .NET ineffizient sein. Stattdessen empfiehlt es sich, eine `None` Optionswert um einen Fehler anzugeben, dass eine gemeinsame oder erwarteten vorkommen.

* Dokumentieren Sie Ausnahmen, die von den Komponenten ausgelöst, wenn eine Funktion falsch verwendet wird.

* Wenn möglich, nutzen Sie vorhandene Ausnahmen von den System-Namespaces. Vermeiden Sie <xref:System.ApplicationException>, obwohl.

* Lösen Sie nicht <xref:System.Exception> Wenn es werden mit Escapezeichen versehen für Benutzercode. Dies schließt die Verwendung von vermeiden `failwith`, `failwithf`, die praktische Funktionen für die Verwendung in Skripts und Code in der Entwicklung sind, jedoch daraus f# Bibliothekscode zugunsten einen spezifischeren Ausnahmetyp auslösen.

* Verwendung `nullArg`, `invalidArg`, und `invalidOp` als Mechanismus zum lösen <xref:System.ArgumentNullException>, <xref:System.ArgumentException>, und <xref:System.InvalidOperationException> gegebenenfalls.

#### <a name="consider-using-option-values-for-return-types-when-failure-is-not-an-exceptional-scenario"></a>Erwägen Sie Optionswerte für Rückgabetypen Wenn war keiner außergewöhnlichen Szenario

Der Ansatz .NET Ausnahmen ist, dass sie "herausragende;" werden soll Sie sollten also relativ selten auftreten. Einige Vorgänge (z. B. eine Tabelle suchen) können jedoch häufig fehlschlagen. F#-Optionswerte sind eine ausgezeichnete Möglichkeit, die Rückgabetypen dieser Vorgänge darstellen. Diese Vorgänge werden konventionell mit dem Präfix "Try" starten:

```fsharp
// bad: throws exception if no element meets criteria
member this.FindFirstIndex(pred : 'T -> bool) : int =
    ...

// bad: returns -1 if no element meets criteria
member this.FindFirstIndex(pred : 'T -> bool) : int =
    ...

// good: returns None if no element meets criteria
member this.TryFindFirstIndex(pred : 'T -> bool) : int option =
    ...
```

### <a name="extension-members"></a>Erweiterungsmember

#### <a name="carefully-apply-f-extension-members-in-f-to-f-components"></a>Sorgfältig gelten f# Erweiterungsmember in f#-zu-Komponenten [F#]

F#-Erweiterungsmember sollte im Allgemeinen nur für Vorgänge verwendet werden, die den Abschluss von systeminternen Vorgänge, die einen Typ in den meisten ihrer Arten der Verwendung zugeordnet werden. Eine allgemeine Verwendung ist APIs ermöglichen die idiomatische für f# für verschiedene .NET Datentypen sind:

```fsharp
type System.ServiceModel.Channels.IInputChannel with
    member this.AsyncReceive() =
        Async.FromBeginEnd(this.BeginReceive, this.EndReceive)

type System.Collections.Generic.IDictionary<'Key,'Value> with
    member this.TryGet key =
        let ok, v = this.TryGetValue key
        if ok then Some v else None
```

### <a name="union-types"></a>Union-Typen

#### <a name="use-discriminated-unions-instead-of-class-hierarchies-for-tree-structured-data"></a>Verwenden von Unterscheidungs-Unions statt Klassenhierarchien für Strukturbaums Daten

Baumähnlichen Strukturen sind rekursiv definiert. Dies ist mit Vererbung umständliche aber elegante mit Unterscheidungs-Unions.

```fsharp
type BST<'T> =
    | Empty
    | Node of 'T * BST<'T> * BST<'T>
```

Darstellen von baumähnlichen Daten mit Unterscheidungs-Unions können Sie auch Exhaustiveness Mustervergleich profitieren.

#### <a name="use-requirequalifiedaccess-on-union-types-whose-case-names-are-not-sufficiently-unique"></a>Verwendung `[<RequireQualifiedAccess>]` auf union-Typen, deren Namen mit Groß-/Kleinschreibung nicht ausreichend eindeutig sind.

Sie können selbst in einer Domäne gefunden werden, in dem gleichnamigen jede Funktion einen Namen für unterschiedliche Dinge, wie z. B. Unterscheidungs-Union-Fälle. Sie können `[<RequireQualifiedAccess>]` um Groß-/Kleinschreibung Namen zu unterscheiden, um zu vermeiden, verwirrend Fehler aufgrund von shadowing von abhängt, die die Reihenfolge der Auslösung `open` Anweisungen

#### <a name="hide-the-representations-of-discriminated-unions-for-binary-compatible-apis-if-the-design-of-these-types-is-likely-to-evolve"></a>Blenden Sie die Darstellung der Unterscheidungs-Unions für binäre kompatibel APIs, wenn der Entwurf dieser Typen weiterentwickelt wird

Unions-Typen beruhen auf f# Mustervergleich Forms für eine kompakte Programmiermodell. Wie bereits erwähnt, sollten Sie vermeiden, Darstellungen konkreter Daten offenzulegen, wenn der Entwurf dieser Typen weiterentwickelt wird.

Z. B. die Darstellung des eine Unterscheidungs-Union kann ausgeblendet werden, mit einer privaten oder internen-Deklaration, oder indem Sie eine Signaturdatei.

```fsharp
type Union =
    private
    | CaseA of int
    | CaseB of string
```

Wenn Sie Unterscheidungs-Unions wahllos offenlegen, möglicherweise finden Sie es schwer zu Version die Bibliothek ohne Unterbrechung von Benutzercode. Erwägen Sie stattdessen eine oder mehrere aktive Muster gestatten Mustervergleich über Werte des Typs offenzulegen.

Aktive Muster bieten eine alternative Möglichkeit zum Bereitstellen f# Consumer Musterabgleich Verfügbarmachen von F#-Union-Typen direkt zu vermeiden.

### <a name="inline-functions-and-member-constraints"></a>Inlinefunktionen und Membereinschränkungen

#### <a name="define-generic-numeric-algorithms-using-inline-functions-with-implied-member-constraints-and-statically-resolved-generic-types"></a>Definieren von generischen numerischen Algorithmen, die Verwendung von Inlinefunktionen mit impliziten Membereinschränkungen und statisch aufgelösten generischen Typen

Arithmetische Member und F#-Vergleich Einschränkungen sind ein Standard für f#-Programmierung. Beachten Sie z. B. folgenden Code:

```fsharp
let inline highestCommonFactor a b =
    let rec loop a b =
        if a = LanguagePrimitives.GenericZero<_> then b
        elif a < b then loop a (b - a)
        else loop (a - b) b
    loop a b
```

Der Typ dieser Funktion lautet wie folgt:

```fsharp
val inline highestCommonFactor : ^T -> ^T -> ^T
                when ^T : (static member Zero : ^T)
                and ^T : (static member ( - ) : ^T * ^T -> ^T)
                and ^T : equality
                and ^T : comparison
```

Dies ist eine passende Funktion für eine öffentliche API in einer mathematischen Bibliothek.

#### <a name="avoid-using-member-constraints-to-simulate-type-classes-and-duck-typing"></a>Vermeiden Sie die Verwendung von Membereinschränkungen um zu simulieren, Klassen und Ente eingeben

Es ist möglich, simulieren "Wildenten eingeben" mit der F#-Member-Einschränkungen. Allerdings Elemente, die Stellen mithilfe dieses sollten nicht im Allgemeinen in f# verwendet-zu-Entwürfe für f#-Bibliothek. Dies ist da Bibliothek Entwürfe anhand von unbekannten oder nicht standardmäßigen implizite Einschränkungen eher dazu führen, dass der Benutzercode unflexibel und an einem bestimmten Framework-Muster gebunden werden.

Darüber hinaus ist eine gute Chance, die starke Nutzung von Membereinschränkungen auf diese Weise zu sehr langen kompilierzeiten führen kann.

### <a name="operator-definitions"></a>Operatordefinitionen

#### <a name="avoid-defining-custom-symbolic-operators"></a>Vermeiden Sie definieren von benutzerdefinierten symbolischen Operatoren

Benutzerdefinierte Operatoren sind in einigen Situationen wichtig und höchst Hilfereiche Schreibweisen Geräten innerhalb einer große Text der Implementierungscode. Für neue Benutzer einer Bibliothek sind benannte Funktionen häufig einfacher zu verwenden. Darüber hinaus benutzerdefinierte symbolische Operatoren Dokument schwer sein, und Benutzer gefunden schwieriger, um Hilfe für Operatoren, die aufgrund von vorhandenen Einschränkungen bei der IDE und suchen Sie Module zu suchen.

Daher ist es am besten, veröffentlichen Sie Ihre Funktionalität wie benannten Funktionen und Elemente, und nur, wenn die notationsvorteile überwiegen, die Dokumentation und cognitive Kosten müssen sie außerdem die Operatoren für diese Funktionalität verfügbar zu machen.

### <a name="units-of-measure"></a>Maßeinheiten

#### <a name="carefully-use-units-of-measure-for-added-type-safety-in-f-code"></a>Verwenden Sie sorgfältig Maßeinheiten für hinzugefügte typsicherheit in f#-code

Zusätzliche typisierungsinformationen Einheiten des Measures wird gelöscht, wenn Sie von anderen .NET-Programmiersprachen angezeigt. Denken Sie daran, dass Visual Studio .NET Komponenten, Tools und Reflektion Typen sans Einheiten angezeigt werden. C#-Consumer werden angezeigt, z. B. `float` statt `float<kg>`.

### <a name="type-abbreviations"></a>Typabkürzungen

#### <a name="carefully-use-type-abbreviations-to-simplify-f-code"></a>Typabkürzungen bedacht zu verwenden, um f#-Code zu vereinfachen.

Visual Studio .NET Komponenten, Tools und Reflektion werden nicht auf die abgekürzte Namen für Typen angezeigt. Bedeutender Verwendung von typabkürzungen kann auch eine Domäne angezeigt, je komplexer als es tatsächlich ist die konnte Consumer zu verwechseln, vornehmen.

#### <a name="avoid-type-abbreviations-for-public-types-whose-members-and-properties-should-be-intrinsically-different-to-those-available-on-the-type-being-abbreviated"></a>Vermeiden Sie typabkürzungen für öffentliche Typen, deren Elemente und Eigenschaften verfügbar sind, auf den Typ wird abgekürzt systemintern verschiedene werden soll

In diesem Fall wird der Typ wird abgekürzt viel über die Darstellung des aktuellen Typs definiert wird. Stattdessen umschließen Sie die Abkürzung in einen Klassentyp oder einen einzelnen Fall Unterscheidungs-Union (oder, wenn Leistung wichtig ist, erwägen Sie einen Strukturtyp um zu umschließen die Abkürzung).

Beispielsweise ist es verlockend, um eine Zuordnung mit mehreren als Sonderfall einer F#-Zuordnung, z. B. zu definieren:

```fsharp
type MultiMap<'Key,'Value> = Map<'Key,'Value list>
```

Allerdings die logischen Punktnotation Vorgänge für diesen Typ sind nicht identisch mit der Vorgänge auf einer Karte, – beispielsweise ist es sinnvoll, ordnen Sie die Lookup-Operator. [Key] Rückgabe der leere Liste, wenn der Schlüssel nicht im Wörterbuch, anstatt durch das Auslösen einer Ausnahme ist.

## <a name="guidelines-for-libraries-for-use-from-other-net-languages"></a>Richtlinien für die Bibliotheken für die Verwendung der anderen .NET-Sprachen

Bei Bibliotheken für die Verwendung anderer Sprachen .NET zu entwerfen, ist es wichtig, entsprechen die [Entwurfsrichtlinien von .NET Bibliothek](../../standard/design-guidelines/index.md). In diesem Dokument diese Bibliotheken herkömmlichen .NET Bibliotheken, im Gegensatz zu f# beschriftet-zugängliche Bibliotheken, die f# verwenden ohne Einschränkung erstellt. Entwerfen von herkömmlichen .NET Bibliotheken bedeutet Bereitstellen von vertraut sind und idiomatische-APIs, die konsistent mit dem Rest des .NET Framework minimieren die Verwendung von f#-spezifische Konstrukte in der öffentlichen API. Die Regeln werden in den folgenden Abschnitten erläutert.

### <a name="namespace-and-type-design-for-libraries-for-use-from-other-net-languages"></a>Namespace und Typ Entwurf (für Bibliotheken für die Verwendung anderer Sprachen .NET)

#### <a name="apply-the-net-naming-conventions-to-the-public-api-of-your-components"></a>Übernehmen Sie die .NET-Namenskonventionen, um die öffentliche API-Komponenten

Achten Sie besonders auf die Verwendung von abgekürzten Namen und die .NET Groß-/Kleinschreibung Richtlinien.

```fsharp
type pCoord = ...
    member this.theta = ...

type PolarCoordinate = ...
    member this.Theta = ...
```

#### <a name="use-namespaces-types-and-members-as-the-primary-organizational-structure-for-your-components"></a>Verwenden von Namespaces, Typen und Membern als die primäre Organisationsstruktur für Ihre Komponenten

Alle Dateien, die mit öffentlichen Funktionen sollten beginnen mit einer `namespace` Deklaration und die nur öffentliche Entitäten in Namespaces Typen werden sollte. Verwenden Sie F#-Module nicht.

Verwenden Sie nicht öffentlich Module, um Implementierungscode Hilfsprogramm Typen und Hilfsfunktionen aufzunehmen.

Statische Typen sollte bevorzugte mit Modulen, sie können für die zukünftige Evolution der API Überladen von Operatoren und anderer .NET API Entwurfskonzepte verwenden, die nicht in F#-Modulen verwendet werden kann.

Beispielsweise anstelle der folgenden öffentlichen API:

```fsharp
module Fabrikam

module Utilities =
    let Name = "Bob"
    let Add2 x y = x + y
    let Add3 x y z = x + y + z
```

Erwägen Sie stattdessen die:

```fsharp
namespace Fabrikam

[<AbstractClass; Sealed>]
type Utilities =
    static member Name = "Bob"
    static member Add(x,y) = x + y
    static member Add(x,y,z) = x + y + z
```

#### <a name="use-f-record-types-in-vanilla-net-apis-if-the-design-of-the-types-wont-evolve"></a>Verwenden Sie f# Datensatztypen in Vanille .NET APIs, wenn der Entwurf der Typen weiterentwickelt wird nicht

F#-Datensatztypen, die in einer einfachen .NET Klasse kompiliert werden. Diese sind für einige einfachen, stabilen Typen in APIs geeignet. Verwenden Sie die `[<NoEquality>]` und `[<NoComparison>]` Attribute, um die automatische Generierung von Schnittstellen zu unterdrücken. Vermeiden Sie auch die Verwendung von änderbare Datensatzfelder in Vanille-.NET APIs als diese macht eines öffentlichen Felds. In Betracht gezogen Sie, ob eine Klasse eine flexiblere Option für die Entwicklung der API bereitstellen möchten.

Beispielsweise macht die folgenden f#-Code die öffentliche API für einen Consumer, c# verfügbar:

F# ERLÄUTERT WERDEN:

```fsharp
[<NoEquality; NoComparison>]
type MyRecord =
    { FirstThing : int
        SecondThing : string }
```

C#:

```csharp
public sealed class MyRecord
{
    public MyRecord(int firstThing, string secondThing);
    public int FirstThing { get; }
    public string SecondThing { get; }
}
```

#### <a name="hide-the-representation-of-f-union-types-in-vanilla-net-apis"></a>Die Darstellung der union f#-Typen in Vanille-.NET APIs ausblenden

F#-union-Typen werden im Allgemeinen nicht verwendet über komponentenbegrenzungen hinweg, sogar für f#-zu-F#-Programmierung. Sie sind eine ausgezeichnete Implementierung Gerät intern für Komponenten und -Bibliotheken verwendet.

Beim Entwerfen eines herkömmlichen .NET API sollten Sie die Darstellung eines union-Typs mit einem privaten Deklaration oder eine Signaturdatei ausblenden.

```fsharp
type PropLogic =
    private
    | And of PropLogic * PropLogic
    | Not of PropLogic
    | True
```

Sie können auch Typen erweitern, die intern eine union Darstellung mit Elementen verwenden, um eine gewünschte bereitzustellen. NET-verbundene-API.

```fsharp
type PropLogic =
    private
    | And of PropLogic * PropLogic
    | Not of PropLogic
    | True

    /// A public member for use from C#
    member x.Evaluate =
        match x with
        | And(a,b) -> a.Evaluate && b.Evaluate
        | Not a -> not a.Evaluate
        | True -> true

    /// A public member for use from C#
    static member CreateAnd(a,b) = And(a,b)
```

#### <a name="design-gui-and-other-components-using-the-design-patterns-of-the-framework"></a>Design-GUI und andere Komponenten, die mit den Entwurfsmustern von framework

Es sind viele verschiedene Frameworks im .NET, z. B. WinForms, WPF und ASP.NET verfügbar. Benennen und Entwurf Konventionen für die einzelnen sollte verwendet werden, wenn Sie Komponenten für die Verwendung in diesen Frameworks entwerfen. Übernehmen Sie für WPF-Programmierung, z. B. WPF-Entwurfsmuster für die Klassen, mit denen, die Sie entwerfen. Verwenden Sie für Modelle im Programmierung der Benutzeroberfläche, Entwurfsmuster, z. B. Ereignisse, und Sammlungen benachrichtigungsbasierter, z. B. die finden Sie in <xref:System.Collections.ObjectModel>.

### <a name="object-and-member-design-for-libraries-for-use-from-other-net-languages"></a>Objekt und Element-Entwurf (für Bibliotheken für die Verwendung anderer Sprachen .NET)

#### <a name="use-the-clievent-attribute-to-expose-net-events"></a>Verwenden Sie das CLIEvent-Attribut .NET Ereignisse verfügbar machen.

Erstellen einer `DelegateEvent` mit einer bestimmten .NET Delegattyp, der ein Objekt akzeptiert und `EventArgs` (anstelle einer `Event`, die gerade verwendet die `FSharpHandler` standardmäßig Typ), damit die Ereignisse auf die vertraute Weise für andere Sprachen .NET veröffentlicht werden.

```fsharp
type MyBadType() =
    let myEv = new Event<int>()

    [<CLIEvent>]
    member this.MyEvent = myEv.Publish

type MyEventArgs(x:int) =
    inherit System.EventArgs()
    member this.X = x

    /// A type in a component designed for use from other .NET languages
type MyGoodType() =
    let myEv = new DelegateEvent<EventHandler<MyEventArgs>>()

    [<CLIEvent>]
    member this.MyEvent = myEv.Publish
```

#### <a name="expose-asynchronous-operations-as-methods-which-return-net-tasks"></a>Asynchrone Vorgänge als Methoden, die .NET Aufgaben zurückzugeben verfügbar gemacht.

Aufgaben werden in .NET zum aktive asynchrone Berechnungen darstellen. Aufgaben sind im Allgemeinen weniger als f# festgelegte `Async<T>` Objekte, da sie die Aufgaben "bereits ausgeführt" darstellen und nicht zusammen Möglichkeiten bestehen können, parallele Komposition ausführen oder das Ausblenden der Weitergabe von Abbruch Signale und andere, kontextbezogene Parameter.

Allerdings sind Methoden, die Aufgaben zurückzugeben, ungeachtet der standarddarstellung der asynchronen Programmierung in .NET.

```fsharp
/// A type in a component designed for use from other .NET languages
type MyType() =

    let compute (x: int) : Async<int> = async { ... }

    member this.ComputeAsync(x) = compute x |> Async.StartAsTask
```

Sie werden häufig auch als explizites Abbruchtoken akzeptieren möchten:

```fsharp
/// A type in a component designed for use from other .NET languages
type MyType() =
    let compute(x:int) : Async<int> = async { ... }
    member this.ComputeAsTask(x, cancellationToken) = Async.StartAsTask(compute x, cancellationToken)
```

#### <a name="use-net-delegate-types-instead-of-f-function-types"></a>Verwenden von .NET Delegattypen anstelle von f#-Typen-Funktion

Hier "f# Funktionstypen" bedeutet "Pfeil"-Typen wie `int -> int`.

Statt diesen:

```fsharp
member this.Transform(f:int->int) =
    ...
```

Vorgehensweise:

```fsharp
member this.Transform(f:Func<int,int>) =
    ...
```

Der f#-Funktionstyps wird als `class FSharpFunc<T,U>` für andere Sprachen .NET und eignet sich weniger für die Sprachfeatures und Tools, die Delegattypen kennen. Beim Erstellen einer .NET Framework 3.5 oder höher abzielt höherer Ordnung-Methode der `System.Func` und `System.Action` Delegaten sind die richtigen APIs veröffentlichen, damit .NET Entwickler diese APIs in einer Weise niedrig problemlose nutzen. (Wenn .NET Framework 2.0 abzielen, werden systemdefinierte Delegattypen mehr beschränkt. das bedeutet, mithilfe von vordefinierten Delegattypen wie z. B. `System.Converter<T,U>` oder einen bestimmten Delegattyp zu definieren.)

Auf der Seite kippen .NET Delegaten sind nicht für f# natürliche-zugängliche Bibliotheken (finden Sie im nächsten Abschnitt in f#-Bibliotheken nach). Daher ist eine verbreitete Implementierungsstrategie beim Entwickeln von höherer Ordnung Methoden für herkömmlichen .NET-Bibliotheken, erstellen alle die Implementierung mit f#-Typen-Funktion, und klicken Sie dann der öffentlichen API mithilfe von Delegaten als dünne Fassade über die tatsächliche f# -Implementierung.

#### <a name="use-the-trygetvalue-pattern-instead-of-returning-f-option-values-and-prefer-method-overloading-to-taking-f-option-values-as-arguments"></a>Verwenden Sie das TryGetValue-Muster, anstatt von f#-Optionswerte und bevorzugen Sie Überladen von Methoden mit dem Erstellen der Optionswerte f# als Argumente

Häufige Muster von der Verwendung für den F#-Option-Typ in-APIs sind besser in Vanille implementiert .NET APIs, die mit standardmäßigen .NET entwerfen Techniken. Anstatt einen f#-Wert, erwägen Sie den Rückgabetyp Bool plus ein Out-Parameter wie das Muster "TryGetValue". Und statt f# Optionswerte als Parameter zu verwenden, bietet sich das Überladen von Methoden oder optionale Argumente.

```fsharp
member this.ReturnOption() = Some 3

member this.ReturnBoolAndOut(outVal : byref<int>) =
    outVal <- 3
    true

member this.ParamOption(x : int, y : int option) =
    match y with
    | Some y2 -> x + y2
    | None -> x

member this.ParamOverload(x : int) = x

member this.ParamOverload(x : int, y : int) = x + y
```

#### <a name="use-the-net-collection-interface-types-ienumerablet-and-idictionarykeyvalue-for-parameters-and-return-values"></a>Verwenden Sie die .NET sammlungsschnittstelle Typen IEnumerable\<T\> und IDictionary\<Schlüssel, Wert\> für Parameter und Rückgabewerte

Vermeiden Sie die Verwendung der konkreten Auflistungstypen, z. B. .NET Arrays `T[]`, f#-Typen `list<T>`, `Map<Key,Value>` und `Set<T>`, und .NET konkreten Auflistungstypen wie `Dictionary<Key,Value>`. Die Entwurfsrichtlinien von .NET Bibliothek haben gut Bezug auf das Verwenden von unterschiedlichen Auflistungstypen, z. B. `IEnumerable<T>`. Einige verwenden von Arrays (`T[]`) in einigen Fällen aus Gründen, die Leistung akzeptabel ist. Beachten Sie insbesondere, dass `seq<T>` wird nur der F#-alias für `IEnumerable<T>`, und daher Seq ist häufig für eines herkömmlichen .NET API einen entsprechenden Typ.

Stattdessen führt der F#:

```fsharp
member this.PrintNames(names : string list) =
    ...
```

Verwenden Sie F#-Sequenzen:

```fsharp
member this.PrintNames(names : seq<string>) =
    ...
```

#### <a name="use-the-unit-type-as-the-only-input-type-of-a-method-to-define-a-zero-argument-method-or-as-the-only-return-type-to-define-a-void-returning-method"></a>Unit-Typ als des einzigen Typs der Eingabe einer Methode verwenden, definieren Sie die Methode eine NULL-Argument, oder als die einzige Rückgabetyp definieren eine "void" zurückgebende-Methode

Vermeiden Sie andere Verwendungen des Typs der. Dies sind gute:

```fsharp
✔ member this.NoArguments() = 3

✔ member this.ReturnVoid(x : int) = ()
```

Dies ist ungültig:

```fsharp
member this.WrongUnit( x:unit, z:int) = ((), ())
```

#### <a name="check-for-null-values-on-vanilla-net-api-boundaries"></a>Überprüfen Sie null-Werte auf herkömmlichen .NET API-Grenzen

F#-Implementierungscode tendenziell weniger null-Werte, aufgrund der unveränderliche Entwurfsmuster und Einschränkungen bei der Verwendung des null-Literale für f#-Typen enthalten. Anderssprachige .NET verwenden häufig sehr viel häufiger null als Wert. Aus diesem Grund sollten F#-Code, der ein herkömmlichen .NET API verfügbar macht, ist Überprüfen der Parameter für Null-Zeichen an der Grenze der API und verhindern, dass diese Werte fließen tiefer in den f#-Code-Implementierung. Die `isNull` Funktion oder einen Mustervergleich für die `null` Muster kann verwendet werden.

```fsharp
let checkNonNull argName (arg: obj) =
    match arg with
    | null -> nullArg argName
    | _ -> ()

let checkNonNull` argName (arg: obj) =
    if isNull arg then nullArg argName
    else ()
```

#### <a name="avoid-using-tuples-as-return-values"></a>Vermeiden Sie die Verwendung von Tupeln als Rückgabewerte

Bevorzugen Sie stattdessen einen benannten Typ die aggregierten Daten enthalten oder mit dem out-Parameter mehrere Werte zurückgeben zurückgeben. Trotz Tupel und Tupel Struktur in .NET geben (einschließlich der C#-sprachunterstützung für die Struktur Tupel), häufig nicht die ideale und die erforderliche-API für .NET-Entwickler sie.

#### <a name="avoid-the-use-of-currying-of-parameters"></a>Vermeiden Sie die Verwendung von currying von Parametern

Verwenden Sie stattdessen .NET Aufrufkonventionen ``Method(arg1,arg2,…,argN)``.

```fsharp
member this.TupledArguments(str, num) = String.replicate num str
```

Tipp: Wenn Sie Bibliotheken zur Verwendung in jeder .NET-Sprache entwerfen, besteht kein Ersatz für tatsächlich auf diese Weise einige experimentellen (c# und Visual Basic Programmieren um sicherzustellen, dass Ihre Bibliotheken "Verhalten nach rechts" aus, aus dieser Sprachen. Sie können auch Tools, z. B. Reflector .NET und Visual Studio-Objektkatalog verwenden, um sicherzustellen, dass Bibliotheken und deren Dokumentation, wie Entwickler erwartet angezeigt werden.

## <a name="appendix"></a>Anhang

### <a name="end-to-end-example-of-designing-f-code-for-use-by-other-net-languages"></a>Entwerfen von f#-Code für die Verwendung von anderen .NET-Programmiersprachen End-to-End-Beispiel

Betrachten Sie die folgende Klasse:

```fsharp
open System

type Point1(angle,radius) =
    new() = Point1(angle=0.0, radius=0.0)
    member x.Angle = angle
    member x.Radius = radius
    member x.Stretch(l) = Point1(angle=x.Angle, radius=x.Radius * l)
    member x.Warp(f) = Point1(angle=f(x.Angle), radius=x.Radius)
    static member Circle(n) =
        [ for i in 1..n -> Point1(angle=2.0*Math.PI/float(n), radius=1.0) ]
```

Der abgeleitete f#-Typ dieser Klasse lautet wie folgt:

```fsharp
type Point1 =
    new : unit -> Point1
    new : angle:double * radius:double -> Point1
    static member Circle : n:int -> Point1 list
    member Stretch : l:double -> Point1
    member Warp : f:(double -> double) -> Point1
    member Angle : double
    member Radius : double
```

Wir sehen Sie sich wie ein Programmierer, die unter Verwendung einer anderen .NET-Programmiersprache dieser f#-Typ angezeigt wird. Beispielsweise ist die ungefähre c# "Signatur" wie folgt:

```csharp
// C# signature for the unadjusted Point1 class
public class Point1
{
    public Point1();

    public Point1(double angle, double radius);

    public static Microsoft.FSharp.Collections.List<Point1> Circle(int count);

    public Point1 Stretch(double factor);

    public Point1 Warp(Microsoft.FSharp.Core.FastFunc<double,double> transform);

    public double Angle { get; }

    public double Radius { get; }
}
```

Es gibt einige wichtige Punkte zu beachten, über wie F#-Konstrukte hier darstellt. Zum Beispiel:

* Metadaten, z. B. Argumentnamen wurde beibehalten.

* F#-Methoden, die zwei Argumente werden C#-Methoden, die zwei Argumente.

* Funktionen und Listen werden Verweise auf die entsprechenden Typen in der f#-Bibliothek.

Der folgende Code zeigt, wie zum Anpassen dieses Codes, um Folgendes zu berücksichtigen.

```fsharp
namespace SuperDuperFSharpLibrary.Types

type RadialPoint(angle:double, radius:double) =

    /// Return a point at the origin
    new() = RadialPoint(angle=0.0, radius=0.0)

    /// The angle to the point, from the x-axis
    member x.Angle = angle

    /// The distance to the point, from the origin
    member x.Radius = radius

    /// Return a new point, with radius multiplied by the given factor
    member x.Stretch(factor) =
        RadialPoint(angle=angle, radius=radius * factor)

    /// Return a new point, with angle transformed by the function
    member x.Warp(transform:Func<_,_>) =
        RadialPoint(angle=transform.Invoke angle, radius=radius)

    /// Return a sequence of points describing an approximate circle using
    /// the given count of points
    static member Circle(count) =
        seq { for i in 1..count ->
                RadialPoint(angle=2.0*Math.PI/float(count), radius=1.0) }
```

Der abgeleitete f#-Typ des Codes lautet wie folgt:

```fsharp
type RadialPoint =
    new : unit -> RadialPoint
    new : angle:double * radius:double -> RadialPoint
    static member Circle : count:int -> seq<RadialPoint>
    member Stretch : factor:double -> RadialPoint
    member Warp : transform:System.Func<double,double> -> RadialPoint
    member Angle : double
    member Radius : double
```

Die C#-Signatur ist jetzt wie folgt aus:

```csharp
public class RadialPoint
{
    public RadialPoint();

    public RadialPoint(double angle, double radius);

    public static System.Collections.Generic.IEnumerable<RadialPoint> Circle(int count);

    public RadialPoint Stretch(double factor);

    public RadialPoint Warp(System.Func<double,double> transform);

    public double Angle { get; }

    public double Radius { get; }
}
```

Fehlerbehebungen vorgenommen, um diesen Typ für die Verwendung vorbereiten, als Teil einer herkömmlichen .NET Bibliothek sind wie folgt:

* Mehrere Namen angepasst: `Point1`, `n`, `l`, und `f` ist seit `RadialPoint`, `count`, `factor`, und `transform`zugeordnet.

* Verwendet einen Rückgabetyp von `seq<RadialPoint>` anstelle von `RadialPoint list` durch Ändern einer Liste der Erstellung mit `[ ... ]` einer Sequenz Konstruktion mit `IEnumerable<RadialPoint>`.

* Verwendet den Delegattyp .NET `System.Func` anstelle eines f#-Funktionstyps.

Dies macht es viel nützlicher in C#-Code nutzen.
