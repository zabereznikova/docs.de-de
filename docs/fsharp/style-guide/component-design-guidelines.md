---
title: F#Richtlinien zum Entwerfen der Komponente
description: Erfahren Sie, die Richtlinien für das Schreiben von F# Komponenten, die für die Nutzung durch andere Aufrufer vorgesehen.
ms.date: 05/14/2018
ms.openlocfilehash: c61e4cd9098388b356c71c325d66c760fa866cf0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61902160"
---
# <a name="f-component-design-guidelines"></a>F#Richtlinien zum Entwerfen der Komponente

In diesem Dokument ist ein Satz von Komponente-Entwurfsrichtlinien für F#-Programmierung, basierend auf den F#-Komponente Entwurfsrichtlinien, v14, Microsoft Research und [eine andere Version](https://fsharp.org/specs/component-design-guidelines/) ursprünglich kuratierten und von der F# Software Foundation verwaltet wird.

In diesem Dokument wird vorausgesetzt, Sie sind vertraut mit F# programmieren. Vielen Dank an die F# Community für ihre Beiträge und hilfreiche Feedback an den verschiedenen Versionen dieses Handbuchs.

## <a name="overview"></a>Übersicht

In diesem Dokument untersucht einige der Probleme im Zusammenhang mit F# Komponente entwerfen und Programmieren. Eine Komponente kann Folgendes bedeuten:

* Eine Ebene in Ihrer F# -Projekts, externe Consumer innerhalb dieses Projekts verfügt.
* Eine Bibliothek, für die Nutzung von F# Code über assemblygrenzen hinweg.
* Eine Bibliothek, die für die Nutzung von jeder .NET-Sprache nichtüber assemblygrenzen hinweg vorgesehen.
* Eine Bibliothek, für die Verteilung über ein paketrepository, z. B. [NuGet](https://nuget.org).

In diesem Artikel beschriebene Verfahren führen Sie die [fünf Prinzipien guten F# Code](index.md#five-principles-of-good-f-code), und daher sowohl funktionale als nutzen und Objekt nach Bedarf programmieren.

Unabhängig von der Methodik steht der Designer-Komponente und die Bibliothek eine Reihe von praktischen und prosaischen Problemen an, beim Versuch, eine API erstellen, die problemlos von Entwicklern verwendet werden kann. Gewissenhaft Anwendung von der [.NET Klassenbibliotheken – Entwurfsrichtlinien](../../standard/design-guidelines/index.md) werden Sie beim Erstellen eines konsistenten Satz von APIs, nutzen angenehme sind, nach steuern.

## <a name="general-guidelines"></a>Allgemeine Richtlinien

Es gibt einige universelle Richtlinien, die für F#-Bibliotheken, unabhängig davon, die Zielgruppe für die Bibliothek gelten.

### <a name="learn-the-net-library-design-guidelines"></a>Erfahren Sie, die .NET Klassenbibliotheken – Entwurfsrichtlinien

Unabhängig von der Art der F# codieren Sie durchführen, es ist sinnvoll, eine ausreichende praktische Kenntnisse in der [.NET Klassenbibliotheken – Entwurfsrichtlinien](../../standard/design-guidelines/index.md). Die meisten anderen F# und .NET Programmierer werden mit diesen Richtlinien vertraut sein und erwarten, dass .NET Code, um sie zu entsprechen.

Die .NET Klassenbibliotheken – Entwurfsrichtlinien enthalten eine allgemeine Anleitung zur Benennung, Entwerfen von Klassen und Schnittstellen, Member-Entwurf (Eigenschaften, Methoden, Ereignisse usw.) und vieles mehr, und sind eine nützliche erste Anlaufpunkt für eine Vielzahl von Entwurfsrichtlinien.

### <a name="add-xml-documentation-comments-to-your-code"></a>Hinzufügen von XML-Dokumentationskommentare zu code

XML-Dokumentation in öffentlichen APIs stellen Sie sicher, dass Benutzer erhalten können, hervorragende Intellisense und den QuickInfos beim Verwenden dieser Typen und Member, und aktivieren, Erstellen von Dokumentation für die Bibliothek von Dateien. Finden Sie unter den [XML-Dokumentation](../language-reference/xml-documentation.md) über verschiedene XML‑Tags, die für zusätzliches Markup in Xmldoc Kommentare verwendet werden können.

```fsharp
/// A class for representing (x,y) coordinates
type Point =

    /// Computes the distance between this point and another
    member DistanceTo: otherPoint:Point -> float
```

Sie können entweder die kurze Form von XML-Kommentare verwenden (`/// comment`), oder die standard-XML-Kommentaren (`///<summary>comment</summary>`).

### <a name="consider-using-explicit-signature-files-fsi-for-stable-library-and-component-apis"></a>Erwägen Sie die Verwendung von expliziten Signaturdateien (".FSI") für stabile und Komponenten-APIs

Verwendung von expliziten Signaturen-Dateien in ein F# -Bibliothek bietet eine kurze Zusammenfassung der öffentliche API nutzen, die jeweils sichergestellt wird, dass Sie wissen, dass die vollständige öffentliche Oberfläche Ihrer Bibliothek bietet eine saubere Trennung zwischen öffentlichen Dokumentation und interne Details zur Implementierung. Beachten Sie, dass die Signaturdateien Reibung hinzufügen, ändern die öffentliche API nutzen, durch das Anfordern von Änderungen, die in der Implementierung und den Signatur-Dateien vorgenommen werden. Daher sollten Signaturdateien in der Regel nur eingeführt werden, wenn eine API größtenteils durchgeführten Konsolidierung werden und muss nicht mehr ändern.

### <a name="always-follow-best-practices-for-using-strings-in-net"></a>Befolgen Sie stets die bewährte Methoden für die Verwendung von Zeichenfolgen in .NET

Führen Sie [bewährte Methoden für die Verwendung von Zeichenfolgen in .NET](../../standard/base-types/best-practices-strings.md) Anleitungen. Insbesondere immer explizit *kulturellen Absicht* in die Konvertierung und Vergleich von Zeichenfolgen (falls zutreffend).

## <a name="guidelines-for-f-facing-libraries"></a>Richtlinien für F#-Bibliotheken für

In diesem Abschnitt werden die Empfehlungen für die Entwicklung von öffentlichen F#-Bibliotheken für d. h. Bibliotheken Verfügbarmachen von öffentlichen APIs, die von F#-Entwickler verwendet werden sollen. Es gibt eine Vielzahl von Empfehlungen für den Bibliothek-Entwurf gelten speziell für F#. Keine spezifischen Empfehlungen, die folgen, sind die .NET Klassenbibliotheken – Entwurfsrichtlinien die fallback-Anleitung.

### <a name="naming-conventions"></a>Namenskonventionen 

#### <a name="use-net-naming-and-capitalization-conventions"></a>Verwenden Sie .NET benennen und Groß-/Kleinschreibung die Konventionen

In der folgende Tabelle werden die .NET benennen und Groß-/Kleinschreibung-Konventionen befolgt. Es gibt kleine Erweiterungen auch F#-Konstrukte enthalten.

| Konstrukt | Case | Segment | Beispiele | Hinweise |
|-----------|------|------|----------|-------|
| Konkrete Typen | PascalCase | Nomen / adjektivische | Liste, Double, komplexe | Konkrete Typen sind Strukturen, Klassen, Enumerationen, Delegaten, Datensätze und Unions. Obwohl Typnamen traditionell in mit OCaml Kleinbuchstaben sind, hat F# das Benennungsschema für .NET für Typen übernommen.
| DLLs           | PascalCase |                 | Fabrikam.Core.dll |  |
| Union-tags     | PascalCase | Nomen | Einige hinzuzufügen, Erfolg | Verwenden Sie ein Präfix nicht in öffentlichen APIs aus. Verwenden Sie optional ein Präfix, bei der internen, z. B. `type Teams = TAlpha | TBeta | TDelta.` |
| event          | PascalCase | Verb | ValueChanged / ValueChanging |  |
| Ausnahmen     | PascalCase |      | WebException | Name sollte mit "Exception" enden. |
| Feld          | PascalCase | Nomen | CurrentName  | |
| Schnittstellentypen |  PascalCase | Nomen / adjektivische | IDisposable | Name sollte mit "I" beginnen. |
| Methode |  PascalCase |  Verb | ToString | |
| Namespace | PascalCase | | Microsoft.FSharp.Core | In der Regel `<Organization>.<Technology>[.<Subnamespace>]`, jedoch nicht die Organisation löschen, wenn die Technologie unabhängig von der Organisation ist. |
| Parameter | camelCase | Nomen |  typeName, transform, range | |
| Lassen Sie die Werte (intern) | CamelCase oder PascalCase | Nomen / Verb |  getValue, myTable |
| Lassen Sie die Werte (extern) | CamelCase oder PascalCase | Substantiv Verb /  | List.map, Dates.Today | Let gebundenen Werte sind oft öffentlich, wenn herkömmliche funktionale Entwurfsmuster zu befolgen. Im Allgemeinen verwenden Sie jedoch PascalCase, wenn der Bezeichner, die von anderen .NET-Sprachen verwendet werden kann. |
| Eigenschaft  | PascalCase  | Nomen / adjektivische  | IsEndOfFile, BackColor  | Boolesche Eigenschaften, die in der Regel verwendet wird und können und sollten positive, wie IsEndOfFile, nicht IsNotEndOfFile.

#### <a name="avoid-abbreviations"></a>Vermeiden Sie Abkürzungen

Die .NET Richtlinien davon abhalten, die Verwendung von Abkürzungen (z. B. "verwenden `OnButtonClick` statt `OnBtnClick`"). Allgemeine Abkürzungen, z. B. `Async` für "Asynchron", werden toleriert. Diese Richtlinie wird für die funktionale Programmierung manchmal ignoriert. z. B. `List.iter` verwendet eine Abkürzung für "durchlaufen". Aus diesem Grund mit Abkürzungen tendenziell in höherem Maß in F# toleriert werden-zu-F#-Programmierung, aber immer noch in der Regel in öffentlichen Komponentenentwurf vermieden werden sollte.

#### <a name="avoid-casing-name-collisions"></a>Vermeiden Sie die Groß-/Kleinschreibung von Namenskonflikten

Die Richtlinien für die .NET sagen, dass die Groß-/Kleinschreibung allein verwendet werden kann, Namenskonflikte, zu unterscheiden, da einige Clientsprachen (z. B. Visual Basic), Groß-/Kleinschreibung sind.

#### <a name="use-acronyms-where-appropriate"></a>Verwenden Sie bei Bedarf Akronyme

Akronyme, wie z. B. XML sind keine Abkürzungen und werden häufig in .NET-Bibliotheken uncapitalized Format (Xml) verwendet. Nur sollte bekannte und weithin anerkannter Akronyme verwendet werden.

#### <a name="use-pascalcase-for-generic-parameter-names"></a>Verwendung von PascalCase für generischen Parameternamen

Verwenden Sie PascalCase für den generischen Parameternamen in öffentlichen APIs, einschließlich für F#-Bibliotheken nach. Insbesondere verwenden Sie Namen wie `T`, `U`, `T1`, `T2` für beliebige generische Parameter, und wenn bestimmte Namen sinnvoll, klicken Sie dann für F#-zugängliche Bibliotheken verwenden Sie Namen wie `Key`, `Value`, `Arg`(aber nicht z. B. `TKey`).

#### <a name="use-either-pascalcase-or-camelcase-for-public-functions-and-values-in-f-modules"></a>Verwenden Sie entweder "PascalCase" oder "CamelCase für öffentliche Funktionen und die Werte in F# Module

CamelCase dient für öffentliche Funktionen, die verwendet werden, dienen nicht qualifizierten (z. B. `invalidArg`), und für die "Standardsammlung Functions" (z. B. List.map). In beiden Fällen verhalten sich die Namen der Funktionen ähnlich wie Schlüsselwörter in der Sprache.

### <a name="object-type-and-module-design"></a>-Objekt, Typ und Modul-Entwurf

#### <a name="use-namespaces-or-modules-to-contain-your-types-and-modules"></a>Verwenden von Namespaces oder Module, Ihre Typen und Module enthalten

Jede F#-Datei in eine Komponente, die mit einer Namespacedeklaration oder eine Moduldeklaration beginnen soll.

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

Die Unterschiede zwischen der Verwendung von Modulen und Namespaces zum Organisieren von Code auf der obersten Ebene sind wie folgt aus:

* Namespaces können mehrere Dateien umfassen.
* Namespaces darf keine F#-Funktionen enthalten, es sei denn, sie in einem inneren Modul
* Der Code für jedes angegebene Modul muss innerhalb einer einzelnen Datei enthalten sein
* Module auf oberster Ebene können F#-Funktionen ohne die Notwendigkeit eines inneren Moduls enthalten.

Die Wahl zwischen einem der obersten Ebene Namespace oder Modul wirkt sich auf die kompilierte Form des Codes und daher wirken sich die Ansicht von anderen .NET-Sprachen Ihrer API schließlich genutzt werden sollen außerhalb von F# Code.

#### <a name="use-methods-and-properties-for-operations-intrinsic-to-object-types"></a>Verwenden von Methoden und Eigenschaften für Vorgänge, die systeminterne Objekte des Typs

Bei der Arbeit mit Objekten empfiehlt es sich um sicherzustellen, dass genutzt werden Funktionen wie Methoden und Eigenschaften für diesen Typ implementiert wird.

```fsharp
type HardwareDevice() =

    member this.ID = ...

    member this.SupportedProtocols = ...

type HashTable<'Key,'Value>(comparer: IEqualityComparer<'Key>) =

    member this.Add(key, value) = ...

    member this.ContainsKey(key) = ...

    member this.ContainsValue(value) = ...
```

Der Großteil der Funktionalität für ein bestimmtes Element muss unbedingt nicht in diesen Member implementiert werden, aber die Information, diese Funktionalität genutzt werden muss.

#### <a name="use-classes-to-encapsulate-mutable-state"></a>Verwenden von Klassen zum Kapseln von veränderlichen Zustands

In F#, dies nur, dass der Status nicht bereits von einem anderen Sprachkonstrukt, z. B. eine Closure, Sequenzausdruck oder asynchrone Berechnung gekapselt ist, in denen erfolgen muss.

```fsharp
type Counter() =
    // let-bound values are private in classes.
    let mutable count = 0

    member this.Next() =
        count <- count + 1
        count
```

#### <a name="use-interfaces-to-group-related-operations"></a>Verwenden Sie Schnittstellen gruppiert verwandte Vorgänge

Verwenden Sie Schnittstellentypen, um eine Reihe von Vorgängen darzustellen. Dies wird zu anderen Optionen, wie Tupel von Funktionen oder Datensätze Funktionen bevorzugt.

```fsharp
type Serializer =
    abstract Serialize<'T>: preserveRefEq: bool -> value: 'T -> string
    abstract Deserialize<'T>: preserveRefEq: bool -> pickle: string -> 'T
```

Vorzuziehen:

```fsharp
type Serializer<'T> = {
    Serialize: bool -> 'T -> string
    Deserialize: bool -> string -> 'T
}
```

Schnittstellen sind erstklassige Konzepte in .NET, die Sie verwenden können, um zu erreichen, was Funktionselemente normalerweise Sie erhalten. Darüber hinaus können sie um existenzielle Typen in das Programm zu codieren, der Datensätze von Funktionen können nicht verwendet werden.

#### <a name="use-a-module-to-group-functions-which-act-on-collections"></a>Verwenden eines Moduls, das die dienen Funktionen für Sammlungen

Wenn Sie einen Auflistungstyp definieren, geben Sie ggf. ein standardmäßigen Satz von Vorgängen wie `CollectionType.map` und `CollectionType.iter`) für die neue Sammlungstypen.

```fsharp
module CollectionType =
    let map f c =
        ...
    let iter f c =
        ...
```

Wenn Sie ein solches Modul einschließen, führen Sie die standardmäßigen Benennungskonventionen für Funktionen in FSharp.Core gefunden.

#### <a name="use-a-module-to-group-functions-for-common-canonical-functions-especially-in-math-and-dsl-libraries"></a>Verwenden eines Moduls, das Funktionen für allgemeine, kanonische Funktionen, insbesondere in Mathematik und DSL-Bibliotheken

Z. B. `Microsoft.FSharp.Core.Operators` ist eine automatisch geöffnete Sammlung von Funktionen der obersten Ebene (z. B. `abs` und `sin`) von FSharp.Core.dll bereitgestellt.

Entsprechend kann eine Statistik-Bibliothek ein Modul mit Funktionen enthalten `erf` und `erfc`, wo dieses Modul dient, explizit oder automatisch geöffnet werden.

#### <a name="consider-using-requirequalifiedaccess-and-carefully-apply-autoopen-attributes"></a>RequireQualifiedAccess in Betracht, und wenden Sie sorgfältig AutoOpen-Attribute

Hinzufügen der `[<RequireQualifiedAccess>]` Attribut auf ein Modul gibt an, dass das Modul kann nicht geöffnet werden, dass Verweise auf die Elemente des Moduls explizite benötigen Zugriff qualifizierten. Z. B. die `Microsoft.FSharp.Collections.List` Modul verfügt über dieses Attribut.

Dies ist nützlich, wenn Funktionen und Werte im Modul Namen haben, die einen Konflikt mit den Namen in anderen Modulen wahrscheinlich sind. Qualifizierten Zugriff erfordern, kann erheblich die langfristige wartbarkeit und Evolvability einer Bibliothek erhöhen.

Hinzufügen der `[<AutoOpen>]` Attribut auf ein Modul bedeutet, dass das Modul wird geöffnet, wenn der übergeordnete Namespace geöffnet wird. Die `[<AutoOpen>]` Attribut kann auch auf eine Assembly an, die automatisch geöffnet wird, wenn die Assembly verwiesen wird, ist ein Modul angewendet werden.

Beispielsweise eine Statistik Bibliothek **MathsHeaven.Statistics** enthält möglicherweise eine `module MathsHeaven.Statistics.Operators` , das Funktionen enthält `erf` und `erfc`. Es ist sinnvoll, markieren Sie dieses Modul als `[<AutoOpen>]`. Dies bedeutet, dass `open MathsHeaven.Statistics` außerdem öffnen Sie dieses Modul, und schalten Sie die Namen `erf` und `erfc` in den Bereich. Verwenden Sie einen anderen funktionierenden von `[<AutoOpen>]` für Module mit Erweiterungsmethoden bereit ist.

Der übermäßigen Verwendung `[<AutoOpen>]` Leads auf belasteten Namespaces und das Attribut sollte mit Vorsicht verwendet werden. Für bestimmte Bibliotheken in bestimmten Domänen, zielgerichtete Verwendung von `[<AutoOpen>]` zu besserer benutzerfreundlichkeit führen kann.

#### <a name="consider-defining-operator-members-on-classes-where-using-well-known-operators-is-appropriate"></a>Betrachten Sie die Definition von Operator Member für Klassen, die mit bekannten Operatoren geeignet ist

Manchmal werden Klassen zum Modellieren von mathematischer Konstrukten, z. B. Vektoren verwendet. Wenn die Domäne, die modelliert werden bekannte Operatoren verfügt, ist das Definieren sie als Member der Klasse systeminterne hilfreich.

```fsharp
type Vector(x: float) =

    member v.X = x

    static member (*) (vector: Vector, scalar: float) = Vector(vector.X * scalar)

    static member (+) (vector1: Vector, vector2: Vector) = Vector(vector1.X + vector2.X)

let v = Vector(5.0)

let u = v * 10.0
```

Diese Anleitung entspricht .NET Hilfestellungen für diese Typen. Allerdings kann es außerdem wichtig sein in F#-Programmierung, da dadurch diese Typen, die in Verbindung mit der F#-Funktionen und Methoden mit Membereinschränkungen, z. B. List.sumBy verwendet werden können.

#### <a name="consider-using-compiledname-to-provide-a-net-friendly-name-for-other-net-language-consumers"></a>Erwägen Sie die Verwendung von CompiledName bereitstellen ein. NET-Anzeigenamen für andere .NET Language-Consumer

In einigen Fällen möglicherweise möchten Sie ein Element in ein Format für Namen F# Consumern (z. B. ein statischer Member in Kleinbuchstaben, damit er angezeigt wird als handele es sich um eine Modul-Bound-Funktion), aber haben Sie einen anderen Stil für den Namen ein, wenn sie in eine Assembly kompiliert wird. Können Sie die `[<CompiledName>]` Attribut geben Sie einen anderen Stil für nicht F# Code, in der Assemblys.

```fsharp
type Vector(x:float, y:float) =

    member v.X = x
    member v.Y = y

    [<CompiledName("Create")>]
    static member create x y = Vector (x, y)

let v = Vector.create 5.0 3.0
```

Mithilfe von `[<CompiledName>]`, können Sie Konventionen für .NET nicht F# Consumern der Assembly.

#### <a name="use-method-overloading-for-member-functions-if-doing-so-provides-a-simpler-api"></a>Verwenden Sie Überladen von Methoden für Memberfunktionen, wenn so eine einfachere API bereitgestellt werden

Überladen von Methoden ist ein leistungsfähiges Tool für die Vereinfachung einer API, die ähnliche Funktionen ausführen muss, aber mit verschiedenen Optionen oder Argumente.

```fsharp
type Logger() =

    member this.Log(message) =
        ...
    member this.Log(message, retryPolicy) =
        ...
```

In F# ist es eher üblich, dass die Anzahl von Argumenten statt Typen der Argumente zu überladen.

#### <a name="hide-the-representations-of-record-and-union-types-if-the-design-of-these-types-is-likely-to-evolve"></a>Blenden Sie die Darstellung des Datensatzes und union-Typen aus, wenn das Design dieser Typen voraussichtlich weiterentwickelt werden

Vermeiden Sie die konkrete Darstellungen von Objekten offenzulegen. Z. B. die konkrete Repräsentation der <xref:System.DateTime> Werte von der externen, öffentliche API des Entwurfs .NET Bibliothek nicht angezeigt wird. Zur Laufzeit weiß der Common Language Runtime die Commit-Implementierung, die in der gesamten Ausführung verwendet werden. Allerdings nicht kompilierter Code selbst abhängig von der konkrete Repräsentation übernommen.

#### <a name="avoid-the-use-of-implementation-inheritance-for-extensibility"></a>Vermeiden Sie die Verwendung der implementierungsvererbung für die Erweiterbarkeit

In F# wird die implementierungsvererbung selten verwendet. Darüber hinaus sind Vererbungshierarchien häufig komplex und schwierig zu ändern, wenn neue Anforderungen eingehen. Implementierung der Vererbung noch vorhanden ist, im F# für Kompatibilität und seltenen Fällen, in denen die beste Lösung für ein Problem aufgetreten ist, aber die alternative Techniken gesucht werden soll, in, Ihre F# Programme beim Entwerfen der Polymorphie, wie z. B. Schnittstelle -Implementierung.

### <a name="function-and-member-signatures"></a>Funktion und Element-Signaturen

#### <a name="use-tuples-for-return-values-when-returning-a-small-number-of-multiple-unrelated-values"></a>Verwenden Sie Tupel für die Rückgabe von Werten, wenn eine kleine Anzahl von mehreren nicht verknüpften Werten zurückgibt

Hier ist ein gutes Beispiel für die Verwendung eines Tupels in einem Rückgabetyp:

```fsharp
val divrem: BigInteger -> BigInteger -> BigInteger * BigInteger
```

Für zurückgeben Sie, die viele Komponenten enthält, oder wenn es sich bei die Komponenten mit einer einzelnen identifizierbaren Entität verknüpft sind, sollten Sie einen benannten Typ anstelle eines Tupels verwenden.

#### <a name="use-asynct-for-async-programming-at-f-api-boundaries"></a>Verwendung `Async<T>` für asynchrone Programmierung an den Begrenzungen der F#-API

Es ist ein entsprechender synchroner Vorgang, der mit dem Namen `Operation` zurückgibt eine `T`, und klicken Sie dann der asynchronen Vorgang benannt werden sollen `AsyncOperation` zurückgegeben `Async<T>` oder `OperationAsync` zurückgegeben `Task<T>`. Für häufig verwendete .NET Typen, die Begin/End-Methoden verfügbar machen können Sie mithilfe von `Async.FromBeginEnd` zum Schreiben von Erweiterungsmethoden bereit, die als eine Fassade zum Bereitstellen der F# asynchrone Programmiermodell, das auf diese .NET APIs.

```fsharp
type SomeType =
    member this.Compute(x:int): int =
        ...
    member this.AsyncCompute(x:int): Async<int> =
        ...

type System.ServiceModel.Channels.IInputChannel with
    member this.AsyncReceive() =
        ...
```

### <a name="exceptions"></a>Ausnahmen

Finden Sie unter [Fehlerverwaltung](conventions.md#error-management) angemessene Verwendung von Ausnahmen, Ergebnisse und Optionen zu erfahren.

### <a name="extension-members"></a>Erweiterungsmember

#### <a name="carefully-apply-f-extension-members-in-f-to-f-components"></a>Sorgfältig anwenden F# Erweiterungsmember in F#-zu-F#-Komponenten

F#Erweiterungsmember sollte in der Regel nur für Vorgänge verwendet werden, die in der Closure systeminterne Vorgänge, die einem Typ in den meisten ihrer Arten der Verwendung zugeordnet sind. Eine übliche Verwendung besteht darin, APIs bereit, die idiomatische F# für verschiedene .NET Datentypen sind:

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

#### <a name="use-discriminated-unions-instead-of-class-hierarchies-for-tree-structured-data"></a>Verwenden von Unterscheidungs-Unions statt Klassenhierarchien strukturierten Daten

Baumähnliche Strukturen sind rekursiv definiert. Dies ist ganz einfach mit Vererbung, jedoch mit Unterscheidungs-Unions elegant.

```fsharp
type BST<'T> =
    | Empty
    | Node of 'T * BST<'T> * BST<'T>
```

Darstellen von baumähnliche-Daten mit Unterscheidungs-Unions können Sie auch Exhaustiveness Musterabgleich profitieren.

#### <a name="use-requirequalifiedaccess-on-union-types-whose-case-names-are-not-sufficiently-unique"></a>Verwendung `[<RequireQualifiedAccess>]` auf union-Typen, deren Namen mit Groß-und Kleinschreibung nicht ausreichend eindeutig sind,

Selbst in einer Domäne möglicherweise steht der gleiche Namen auf Namen fest. für unterschiedliche Dinge, wie z. B. Unterscheidungs-Union-Fälle. Sie können `[<RequireQualifiedAccess>]` um Groß-/Kleinschreibung von Namen zu unterscheiden, um zu vermeiden, verwirrend Fehler aufgrund von shadowing abhängig, die Reihenfolge der Auslösung `open` Anweisungen

#### <a name="hide-the-representations-of-discriminated-unions-for-binary-compatible-apis-if-the-design-of-these-types-is-likely-to-evolve"></a>Blenden Sie die Darstellung der Unterscheidungs-Unions für binäre kompatiblen APIs aus, wenn das Design dieser Typen voraussichtlich weiterentwickelt werden

Unions-Typen basieren auf F# Mustervergleichs-Formulare für eine kurze Programmiermodell. Wie bereits erwähnt, sollten Sie konkrete datendarstellungen offenzulegen, wenn das Design dieser Typen voraussichtlich weiterentwickelt wird.

Z. B. die Darstellung einer Unterscheidungs-Union kann ausgeblendet werden, mit einer privaten oder internen-Deklaration, oder indem Sie eine Signaturdatei.

```fsharp
type Union =
    private
    | CaseA of int
    | CaseB of string
```

Wenn Sie eine Unterscheidungs-Unions wahllos anzeigen, es schwierig, Version Ihrer Bibliothek möglicherweise ohne Benutzercode. Erwägen Sie stattdessen eine oder mehrere aktive Muster zum Musterabgleich gegenüber Werte des Typs zulassen offenzulegen.

Aktive Muster stellen eine Alternative zu F# Kunden mit Musterabgleich zugleich Verfügbarmachen von F# Union-Typen direkt.

### <a name="inline-functions-and-member-constraints"></a>Inline-Funktionen und Member-Einschränkungen

#### <a name="define-generic-numeric-algorithms-using-inline-functions-with-implied-member-constraints-and-statically-resolved-generic-types"></a>Definieren von generischen numerischen Algorithmen, die Verwendung von Inlinefunktionen mit impliziten Member-Einschränkungen und statisch aufgelösten generischen Typen

Arithmetische Member und F#-Vergleichs-Einschränkungen sind ein Standard für F#-Programmierung. Beachten Sie z. B. folgenden Code:

```fsharp
let inline highestCommonFactor a b =
    let rec loop a b =
        if a = LanguagePrimitives.GenericZero<_> then b
        elif a < b then loop a (b - a)
        else loop (a - b) b
    loop a b
```

Der Typ dieser Funktion lautet wie folgt aus:

```fsharp
val inline highestCommonFactor : ^T -> ^T -> ^T
                when ^T : (static member Zero : ^T)
                and ^T : (static member ( - ) : ^T * ^T -> ^T)
                and ^T : equality
                and ^T : comparison
```

Dies ist eine passende Funktion für eine öffentliche API in einer mathematischen Bibliothek.

#### <a name="avoid-using-member-constraints-to-simulate-type-classes-and-duck-typing"></a>Vermeiden Sie die Verwendung der Member-Einschränkungen, Klassen und beim Duck-typing zu simulieren

Es ist möglich, mithilfe von "Duck typing" simulieren F# Member-Einschränkungen. Allerdings Elemente, die Stellen verwenden dieses sollte nicht im Allgemeinen in F# verwendet-zu-Entwürfe für F#-Bibliothek. Dies ist, da die Bibliothek-Designs, die basierend auf implizite nicht vertraut sind oder nicht dem standard-Einschränkungen in der Regel dazu führen, dass der Benutzercode unflexibel und an einem bestimmten Framework-Muster gebunden werden.

Darüber hinaus besteht eine hohe Wahrscheinlichkeit, die intensiven Gebrauch von der Membereinschränkungen auf diese Weise sehr lange kompilierzeiten führen kann.

### <a name="operator-definitions"></a>Operatordefinitionen

#### <a name="avoid-defining-custom-symbolic-operators"></a>Vermeiden Sie das Festlegen von benutzerdefinierter symbolische Operatoren

Benutzerdefinierte Operatoren sind in einigen Situationen wichtig und überaus nützliche Schreibweisen Geräte in eine große Menge Code zur Implementierung. Benannte Funktionen sind für neue Benutzer von einer Bibliothek häufig einfacher zu verwenden. Darüber hinaus benutzerdefinierte symbolische Operatoren können schwierig sein, Dokument, und Benutzer finden es schwieriger, um Hilfe für Operatoren, die aufgrund von vorhandenen Einschränkungen in der IDE, und suchen Sie Module zu suchen.

Daher ist es am besten, veröffentlichen Sie Ihre Funktionalität wie die benannten Funktionen und Member, und nur dann, wenn die notationsvorteile überwiegen, Dokumentation und kognitive Kosten für Sie außerdem die Operatoren für diese Funktionalität verfügbar zu machen.

### <a name="units-of-measure"></a>Maßeinheiten

#### <a name="carefully-use-units-of-measure-for-added-type-safety-in-f-code"></a>Maßeinheiten für die hinzugefügte typsicherheit mit Vorsicht verwenden F# Code

Zusätzliche typisierungsinformationen für Einheiten des Measures wird gelöscht, wenn Sie von anderen .NET-Programmiersprachen angezeigt. Denken Sie daran, dass .NET Komponenten, Tools und Reflektion Typen-sans-Einheiten angezeigt werden. C#-Kunden werden angezeigt, z. B. `float` statt `float<kg>`.

### <a name="type-abbreviations"></a>Typabkürzungen

#### <a name="carefully-use-type-abbreviations-to-simplify-f-code"></a>Typabkürzungen sorgfältig zu verwenden, um F#-Code zu vereinfachen

.NET Komponenten, Tools und Reflektion werden nicht abgekürzte Namen für Typen angezeigt. Nennenswerte Nutzung von typabkürzungen kann auch eine Domäne, die angezeigt werden, viel komplexer, als sie tatsächlich ist die könnte Kunden verwirren, vornehmen.

#### <a name="avoid-type-abbreviations-for-public-types-whose-members-and-properties-should-be-intrinsically-different-to-those-available-on-the-type-being-abbreviated"></a>Vermeiden Sie typabkürzungen für öffentliche Typen, deren Elemente und Eigenschaften ganz anderes eingabeparadigma nahe zur Verfügung stehen, für den Typ wird abgekürzt werden soll

In diesem Fall zeigt den abgekürzt werden zu viele Informationen über die Darstellung des aktuellen Typs definiert wird. Stattdessen sollten Sie die Abkürzung in einen Klassentyp oder eine einzelne Fall Unterscheidungs-Union zu umschließen (oder, wenn Leistung wichtig ist, erwägen Sie die Verwendung eines Strukturtyps, umschließen die Abkürzung).

Angenommen, es ist verlockend, definieren Sie eine Zuordnung mit mehreren als Sonderfall von einem F# zuordnen, z.B.:

```fsharp
type MultiMap<'Key,'Value> = Map<'Key,'Value list>
```

Allerdings die logische Punktnotation-Vorgänge für diesen Typ sind nicht identisch mit die Vorgänge auf einer Karte – beispielsweise ist es plausibel, dass die Lookup-Operator zugeordnet. [Schlüssel] Rückgabe der leeren Liste, wenn der Schlüssel nicht in das Wörterbuch, anstatt eine Ausnahme auszulösen.

## <a name="guidelines-for-libraries-for-use-from-other-net-languages"></a>Richtlinien für die Bibliotheken für die Verwendung von anderen .NET-Sprachen

Beim Entwerfen der Bibliotheken für die Verwendung von anderen .NET-Sprachen ist es wichtig, entsprechen die [.NET Klassenbibliotheken – Entwurfsrichtlinien](../../standard/design-guidelines/index.md). In diesem Dokument werden diese Bibliotheken bezeichnet, als einfaches .NET Bibliotheken, im Gegensatz zu F#-Bibliotheken, mit denen F#-facing ohne Einschränkungen erstellt. Entwerfen einfache Bibliotheken für .NET bedeutet, dass vertraut und idiomatische-APIs, die konsistent mit dem Rest des .NET Framework durch minimieren die Verwendung von bereitstellen F#-spezifische Konstrukte in der öffentlichen API. Die Regeln werden in den folgenden Abschnitten erläutert.

### <a name="namespace-and-type-design-for-libraries-for-use-from-other-net-languages"></a>Namespace und Typ-Entwurf (für die Bibliotheken für die Verwendung von anderen .NET-Sprachen)

#### <a name="apply-the-net-naming-conventions-to-the-public-api-of-your-components"></a>Übernehmen Sie die .NET-Namenskonventionen, um die öffentliche API des Ihre Komponenten

Achten Sie besonders auf die Verwendung der abgekürzten Namen und die Groß-/Kleinschreibung-Richtlinien von .NET.

```fsharp
type pCoord = ...
    member this.theta = ...

type PolarCoordinate = ...
    member this.Theta = ...
```

#### <a name="use-namespaces-types-and-members-as-the-primary-organizational-structure-for-your-components"></a>Verwenden von Namespaces, Typen und Membern als die primäre Organisationsstruktur für Ihre Komponenten

Alle Dateien mit öffentlichen Funktionen sollten beginnen mit einer `namespace` Deklaration und die einzigen öffentlichen Entitäten in Namespaces sollten Typen sein. Verwenden Sie keine F# Module.

Verwenden Sie nicht öffentliche Module, um Code zur Implementierung, Hilfsprogramm Typen und Hilfsprogrammfunktionen zu speichern.

Statische Typen sollten bevorzugt werden über Module, sie können für die zukünftige Entwicklung der API zum Überladen von Operatoren und andere .NET API-Entwurfskonzepte verwenden, die nicht innerhalb von verwendet werden kann F# Module.

Beispielsweise anstelle der folgenden öffentlichen API:

```fsharp
module Fabrikam

module Utilities =
    let Name = "Bob"
    let Add2 x y = x + y
    let Add3 x y z = x + y + z
```

Erwägen Sie stattdessen ein:

```fsharp
namespace Fabrikam

[<AbstractClass; Sealed>]
type Utilities =
    static member Name = "Bob"
    static member Add(x,y) = x + y
    static member Add(x,y,z) = x + y + z
```

#### <a name="use-f-record-types-in-vanilla-net-apis-if-the-design-of-the-types-wont-evolve"></a>Verwendung F# Eintragstypen in Vanille .NET APIs, wenn der Entwurf der Typen weiterentwickelt wird nicht

F#Record-Typen, die in einer einfachen .NET Klasse kompiliert werden. Diese sind für einige einfachen, stabile-Typen in APIs geeignet. Erwägen Sie die `[<NoEquality>]` und `[<NoComparison>]` Attribute, um die automatische Generierung von Schnittstellen zu unterdrücken. Außerdem verwenden Sie änderbare Datensatzfelder in Vanille .NET APIs als diese macht ein öffentliches Feld. Berücksichtigen Sie immer, ob es sich bei eine Klasse eine flexiblere Option für die zukünftige Entwicklung der API bieten würde.

Beispielsweise die folgenden F# Code verfügbar macht, die öffentliche API zu einem C# Consumer:

F#:

```fsharp
[<NoEquality; NoComparison>]
type MyRecord =
    { FirstThing: int
        SecondThing: string }
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

#### <a name="hide-the-representation-of-f-union-types-in-vanilla-net-apis"></a>Blenden Sie die Darstellung der F# union-Typen in Vanille .NET APIs

F#-union-Typen nicht dienen meist über komponentenbegrenzungen hinweg, sogar für F#-zu-F#-Programmierung. Sie sind eine ausgezeichnete Implementierung Gerät intern innerhalb der Komponenten und Bibliotheken verwendet.

Beim Entwerfen eines herkömmlichen .NET API sollten Sie die Darstellung eines union-Typs mit einer privaten Deklaration oder eine Signaturdatei ausblenden.

```fsharp
type PropLogic =
    private
    | And of PropLogic * PropLogic
    | Not of PropLogic
    | True
```

Sie können auch Typen erweitern, die intern eine union Darstellung mit Membern verwenden, um eine gewünschte bereitzustellen. NET-Facing-API.

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

Viele verschiedene Frameworks sind in .NET, z. B. WPF, WinForms und ASP.NET verfügbar. Benennen und Design-Konventionen für die einzelnen sollte verwendet werden, wenn Sie Komponenten für die Verwendung in diesen Frameworks entwerfen. Übernehmen Sie für WPF-Programmierung, z. B. WPF-Entwurfsmuster für die Klassen, die Sie entwerfen. Verwenden Sie für die Modelle in der Programmierung der Benutzeroberfläche, Entwurfsmuster, wie Ereignisse und benachrichtigungsbasierte Auflistungen, z. B. unter <xref:System.Collections.ObjectModel>.

### <a name="object-and-member-design-for-libraries-for-use-from-other-net-languages"></a>-Objekt und Element-Entwurf (für die Bibliotheken für die Verwendung von anderen .NET-Sprachen)

#### <a name="use-the-clievent-attribute-to-expose-net-events"></a>Verwenden Sie das CLIEvent-Attribut, Ereignisse verfügbar zu machen

Erstellen einer `DelegateEvent` mit einer bestimmten .NET Delegattyp, der ein Objekt akzeptiert und `EventArgs` (anstelle einer `Event`, die gerade verwendet die `FSharpHandler` standardmäßig Typ), damit die Ereignisse in der vertrauten Verfahren können Sie anderen veröffentlicht werden.

```fsharp
type MyBadType() =
    let myEv = new Event<int>()

    [<CLIEvent>]
    member this.MyEvent = myEv.Publish

type MyEventArgs(x: int) =
    inherit System.EventArgs()
    member this.X = x

    /// A type in a component designed for use from other .NET languages
type MyGoodType() =
    let myEv = new DelegateEvent<EventHandler<MyEventArgs>>()

    [<CLIEvent>]
    member this.MyEvent = myEv.Publish
```

#### <a name="expose-asynchronous-operations-as-methods-which-return-net-tasks"></a>Bereitstellen Sie asynchroner Vorgänge als Methoden, die .NET Aufgaben zurückgeben

Aufgaben sind in .NET verwendet, um aktive asynchrone Berechnungen darzustellen. Aufgaben sind im Allgemeinen weniger als F# kompositionell `Async<T>` Objekte, da sie die Aufgaben "bereits ausgeführt" darstellen und nicht zusammengesetzte zusammen, es gibt Möglichkeiten, parallele Kombination ausführen oder das Ausblenden der Weitergabe von Abbruch signalisiert und andere, kontextbezogene Parameter.

Dennoch sind Methoden, die Aufgaben zurückgeben jedoch die standarddarstellung der asynchronen Programmierung in .NET.

```fsharp
/// A type in a component designed for use from other .NET languages
type MyType() =

    let compute (x: int): Async<int> = async { ... }

    member this.ComputeAsync(x) = compute x |> Async.StartAsTask
```

Sie werden häufig auch als explizites Abbruchtoken akzeptieren möchten:

```fsharp
/// A type in a component designed for use from other .NET languages
type MyType() =
    let compute(x: int): Async<int> = async { ... }
    member this.ComputeAsTask(x, cancellationToken) = Async.StartAsTask(compute x, cancellationToken)
```

#### <a name="use-net-delegate-types-instead-of-f-function-types"></a>Verwenden Sie .NET Delegattypen anstelle von F#-Typen-Funktion

Hier "F# Funktionstypen" bedeutet, dass "Pfeil"-Typen wie `int -> int`.

Statt dies:

```fsharp
member this.Transform(f: int->int) =
    ...
```

Vorgehensweise:

```fsharp
member this.Transform(f: Func<int,int>) =
    ...
```

Die F# Funktionstyp wird als `class FSharpFunc<T,U>` in andere .NET-Sprachen und eignet sich weniger für die Sprachfeatures und Tools, die Delegattypen zu verstehen. Beim Erstellen einer höherer Ordnung-Methode, die für .NET Framework 3.5 oder höher, die `System.Func` und `System.Action` Delegaten sind die richtigen APIs veröffentlichen möchten, .NET Entwickler diese APIs in einer Weise reibungsarme verwenden können. (Bei .NET Framework 2.0 abzielen, sind die vom System definierte Delegattypen mehr beschränkt, erwägen Sie die Verwendung von vordefinierten Delegattypen wie z. B. `System.Converter<T,U>` oder einen bestimmten Delegattyp definieren.)

Auf der Seite kippen .NET Delegaten sind nicht für F# natürliche-Bibliotheken für (finden Sie im nächsten Abschnitt F#-Bibliotheken für). Daher ist eine verbreitete Implementierungsstrategie, bei der Entwicklung von höherer Ordnung-Methoden für einfache Bibliotheken für .NET alle die Implementierung mithilfe von F#-Funktion-Typen zu erstellen, und erstellen Sie die öffentliche API, die mithilfe von Delegaten als thin Fassade auf die tatsächliche F# -Implementierung.

#### <a name="use-the-trygetvalue-pattern-instead-of-returning-f-option-values-and-prefer-method-overloading-to-taking-f-option-values-as-arguments"></a>Verwenden Sie das TryGetValue-Muster, anstatt die Rückgabe von Werten für F#-Option aus, und es vorziehen Sie, Überladen von Methoden mit dem Erstellen von F#-Werte als Argumente

Allgemeine Muster für die Verwendung für die F# Optionstyp APIs sind besser in Vanille implementiert .NET APIs, die mit standardmäßigen .NET entwerfen Techniken. Anstatt einen F#-Wert, erwägen Sie den Rückgabetyp "bool" sowie einen Out-Parameter wie das Muster "TryGetValue". Und anstelle der Instanz F# Optionswerte als Parameter, Überladen von Operatoren oder optionalen Argumenten in Betracht.

```fsharp
member this.ReturnOption() = Some 3

member this.ReturnBoolAndOut(outVal: byref<int>) =
    outVal <- 3
    true

member this.ParamOption(x: int, y: int option) =
    match y with
    | Some y2 -> x + y2
    | None -> x

member this.ParamOverload(x: int) = x

member this.ParamOverload(x: int, y: int) = x + y
```

#### <a name="use-the-net-collection-interface-types-ienumerablet-and-idictionarykeyvalue-for-parameters-and-return-values"></a>Verwenden Sie die .NET sammlungsschnittstelle Typen "IEnumerable"\<T\> und IDictionary\<Schlüssel, Wert\> für Parameter und Rückgabewerte

Vermeiden Sie die Verwendung der konkreten Auflistungstypen, z. B. .NET Arrays `T[]`, F#-Typen `list<T>`, `Map<Key,Value>` und `Set<T>`, und .NET konkreten Auflistungstypen wie z. B. `Dictionary<Key,Value>`. Die .NET Klassenbibliotheken – Entwurfsrichtlinien haben gute Ratschläge in Bezug auf die unterschiedlichen Auflistungstypen, z. B. verwenden `IEnumerable<T>`. Einige verwenden von Arrays (`T[]`) in einigen Fällen aus Gründen, die Leistung akzeptabel ist. Beachten Sie insbesondere, dass `seq<T>` ist nur für die F# alias für `IEnumerable<T>`, und so Seq ist häufig einen geeigneten Typ für eine Vanille .NET API.

Anstelle von F#-Listen:

```fsharp
member this.PrintNames(names: string list) =
    ...
```

Verwendung F# Sequenzen:

```fsharp
member this.PrintNames(names: seq<string>) =
    ...
```

#### <a name="use-the-unit-type-as-the-only-input-type-of-a-method-to-define-a-zero-argument-method-or-as-the-only-return-type-to-define-a-void-returning-method"></a>Verwenden Sie den Typ als einzige Eingabetyp einer Methode so definieren Sie die Methode eine NULL-Argument oder als den einzigen Rückgabetyp auf eine "void" zurückgebende Methode zu definieren

Zu vermeiden Sie anderen Verwendungsmöglichkeiten der den Typ. Dies sind gute:

```fsharp
✔ member this.NoArguments() = 3

✔ member this.ReturnVoid(x: int) = ()
```

Das ist nicht gut:

```fsharp
member this.WrongUnit( x: unit, z: int) = ((), ())
```

#### <a name="check-for-null-values-on-vanilla-net-api-boundaries"></a>Überprüfen Sie null-Werte auf einfaches .NET API-Grenzen

F#Implementierungscode tendenziell weniger null-Werte, aufgrund von unveränderlichen Entwurfsmustern und Einschränkungen bei der Verwendung von null-Literale für F# Typen. Anderen verwenden häufig viel häufiger null als Wert. Aus diesem Grund F# Code, der ein herkömmlichen .NET API verfügbar gemacht wird Überprüfen der Parameter für Null-Zeichen an der API-Grenze, und verhindern, dass diese Werte fließen tiefer in die F# Implementierungscode. Die `isNull` Funktion oder einen Musterabgleich für die `null` Muster kann verwendet werden.

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

Bevorzugen Sie stattdessen die Rückgabe eines benannten Typs, der die aggregierten Daten enthält oder mit dem out-Parameter mehrere Werte zurückgeben. Obwohl Tupel und Strukturieren von Tupeln an, die in .NET vorhanden sind bieten (einschließlich der C#-sprachunterstützung für Tupel, die Struktur), sie meist nicht die ideale und erwartete-API für .NET-Entwickler.

#### <a name="avoid-the-use-of-currying-of-parameters"></a>Vermeiden Sie die Verwendung von currying von Parametern

Verwenden Sie stattdessen .NET Aufrufkonventionen `Method(arg1,arg2,…,argN)`.

```fsharp
member this.TupledArguments(str, num) = String.replicate num str
```

Tipp: Wenn Sie Bibliotheken für die Verwendung von beliebigen entwerfen, dann gibt es keinen Ersatz für die tatsächlich einige experimentelle C# und Visual Basic-Programmierung, um sicherzustellen, dass Ihre Bibliotheken "Verhalten rechts" aus, aus dieser Sprachen. Sie können auch Tools wie z. B. .NET Reflector und den Visual Studio-Objektkatalog verwenden, um sicherzustellen, dass die Bibliotheken und ihrer Dokumentation, wie Entwickler erwartet angezeigt werden.

## <a name="appendix"></a>Anhang

### <a name="end-to-end-example-of-designing-f-code-for-use-by-other-net-languages"></a>End-to-End-Beispiel für das Entwerfen von F#-Code für die Verwendung von anderen .NET-Programmiersprachen

Beachten Sie die folgende Klasse:

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

Der abgeleitete F# Typ diese Klasse ist wie folgt:

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

Sehen wir uns an, wie dies F# Typ angezeigt wird, um ein Programmierer, die mithilfe einer anderen .NET-Sprache. Beispielsweise ist die ungefähre c# "Signatur" wie folgt:

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

Es gibt einige wichtige Punkte zu beachten Sie, dass Informationen F# stellt hier erstellt werden. Zum Beispiel:

* Metadaten wie z. B. den Namen des Funktionsarguments wurde beibehalten.

* F#Methoden, die zwei werden Argumente C# Methoden, die zwei Argumente akzeptieren.

* Funktionen und Listen werden Verweise auf die entsprechenden Typen in der F# Bibliothek.

Der folgende Code zeigt, wie Sie passen Sie diesen Code, um Folgendes zu berücksichtigen.

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

Der abgeleitete F# Typ des Codes lautet wie folgt:

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

Die C#-Signatur sieht jetzt wie folgt aus:

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

Die Korrekturen vorgenommen, um dieser Typ für die Verwendung vorzubereiten, als Teil einer einfachen .NET Bibliothek sind wie folgt:

* Mehrere Namen angepasst: `Point1`, `n`, `l`, und `f` wurde `RadialPoint`, `count`, `factor`, und `transform`bzw.

* Verwendet einen Rückgabetyp von `seq<RadialPoint>` anstelle von `RadialPoint list` durch Ändern der Konstruktion für eine Liste mit `[ ... ]` in eine Sequenz Konstruktion `IEnumerable<RadialPoint>`.

* Verwendet den .NET Delegattyp `System.Func` anstelle eines F#-Funktionstyps.

Dies macht es viel nützlicher in C#-Code nutzen.
