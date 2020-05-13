---
title: Entwurfsrichtlinien für eine F#-Komponente
description: 'Erfahren Sie mehr über die Richtlinien zum Schreiben von F #-Komponenten, die von anderen Aufrufern für'
ms.date: 05/14/2018
ms.openlocfilehash: 590bda0660d54ea73c590d31e694f3d499e0fd9f
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209135"
---
# <a name="f-component-design-guidelines"></a>Entwurfsrichtlinien für eine F#-Komponente

Dieses Dokument ist eine Reihe von Richtlinien zum Entwerfen von Komponenten für die f #-Programmierung, die auf den f #-Komponenten Entwurfs Richtlinien, v14, Microsoft Research und einer Version basiert, die ursprünglich von der f #-Software Foundation eingerichtet und verwaltet wurde.

Dieses Dokument setzt voraus, dass Sie mit der F #-Programmierung vertraut sind. Vielen Dank an die F #-Community für Ihre Beiträge und nützliches Feedback zu verschiedenen Versionen dieses Handbuchs.

## <a name="overview"></a>Übersicht

In diesem Dokument werden einige der Probleme im Zusammenhang mit dem Entwurf und der Codierung von F #-Komponenten behandelt. Eine Komponente kann Folgendes bedeuten:

* Eine Ebene im F #-Projekt, die über externe Consumer innerhalb dieses Projekts verfügt.
* Eine Bibliothek, die von F #-Code über assemblygrenzen hinweg genutzt werden soll.
* Eine Bibliothek, die von einer beliebigen .NET-Sprache über assemblygrenzen hinweg benötigt wird.
* Eine Bibliothek, die über ein Paketrepository (z. b. [nuget](https://nuget.org)) zur Verteilung vorgesehen ist

Die in diesem Artikel beschriebenen Verfahren folgen den [fünf Prinzipien von gutem F #-Code](index.md#five-principles-of-good-f-code)und verwenden daher die funktionale und die Objekt Programmierung entsprechend.

Unabhängig von der Methodik sind der Komponenten-und Bibliotheks-Designer bei dem Versuch, eine API zu erstellen, die am einfachsten von Entwicklern verwendet werden kann, mit einigen praktischen und prosaischen Problemen konfrontiert. Die [Entwurfs Richtlinien für die Entwurfs Richtlinien von .NET-Bibliotheken](../../standard/design-guidelines/index.md) führen Sie zur Erstellung eines konsistenten Satzes von APIs, die für Sie von Nutzen sind.

## <a name="general-guidelines"></a>Allgemeine Richtlinien

Es gibt ein paar universelle Richtlinien, die für F #-Bibliotheken gelten, unabhängig von der Zielgruppe für die Bibliothek.

### <a name="learn-the-net-library-design-guidelines"></a>Erlernen der Entwurfs Richtlinien für .NET-Bibliotheken

Unabhängig davon, welche Art von F #-Codierung Sie durchgeführt haben, ist es von Vorteil, dass Sie über Kenntnisse der [Entwurfs Richtlinien für .NET-Bibliotheken](../../standard/design-guidelines/index.md)verfügen. Die meisten anderen F #-und .NET-Programmierer sind mit diesen Richtlinien vertraut und erwarten, dass .NET-Code Ihnen entspricht.

Die Entwurfs Richtlinien für .NET-Bibliotheken bieten allgemeine Anleitungen für die Benennung, das Entwerfen von Klassen und Schnittstellen, das Entwerfen von Elementen (Eigenschaften, Methoden, Ereignisse usw.) und vieles mehr. Sie sind ein nützlicher erster Bezugspunkt für eine Vielzahl von Entwurfs Anleitungen.

### <a name="add-xml-documentation-comments-to-your-code"></a>Hinzufügen von XML-Dokumentations Kommentaren zum Code

Die XML-Dokumentation zu öffentlichen APIs stellt sicher, dass Benutzer bei der Verwendung dieser Typen und Member großartige IntelliSense-und QuickInfo-Informationen erhalten und die Erstellung von Dokumentationsdateien für die Bibliothek aktivieren können. Informationen zu verschiedenen XML-Tags, die für zusätzliches Markup in xmlDoc--Kommentaren verwendet werden können, finden Sie in der [XML-Dokumentation](../language-reference/xml-documentation.md) .

```fsharp
/// A class for representing (x,y) coordinates
type Point =

    /// Computes the distance between this point and another
    member DistanceTo: otherPoint:Point -> float
```

Sie können entweder die Kurzform-XML-Kommentare ( `/// comment` ) oder XML-Standard Kommentare ( `///<summary>comment</summary>` ) verwenden.

### <a name="consider-using-explicit-signature-files-fsi-for-stable-library-and-component-apis"></a>Verwenden Sie explizite Signatur Dateien (FSI) für stabile Bibliothek-und Komponenten-APIs.

Die Verwendung von expliziten Signaturen in einer F #-Bibliothek bietet eine kurze Zusammenfassung der öffentlichen API, mit der Sie sicherstellen können, dass Sie die vollständige öffentliche Oberfläche der Bibliothek kennen, und eine saubere Trennung zwischen der öffentlichen Dokumentation und den internen Implementierungsdetails bietet. Signatur Dateien fügen eine Reibung zum Ändern der öffentlichen API hinzu, indem Änderungen an der Implementierungs-und der Signatur Datei vorgenommen werden müssen. Folglich sollten Signatur Dateien in der Regel nur dann eingefügt werden, wenn eine API gefestigt wird und sich nicht mehr in erheblichem Umfang ändert.

### <a name="always-follow-best-practices-for-using-strings-in-net"></a>Befolgen Sie stets die bewährten Methoden für die Verwendung von Zeichen folgen in .net

Befolgen Sie die [bewährten Methoden zum Verwenden von Zeichen folgen in .net](../../standard/base-types/best-practices-strings.md) -Anleitungen. Insbesondere ist die *Kultur Absicht* beim Konvertieren und Vergleichen von Zeichen folgen immer explizit.

## <a name="guidelines-for-f-facing-libraries"></a>Richtlinien für Bibliotheken mit F #

In diesem Abschnitt finden Sie Empfehlungen für die Entwicklung von öffentlichen F-Bibliotheken. Das heißt, Bibliotheken, die öffentliche APIs verfügbar machen, die von F #-Entwicklern verwendet werden sollen. Es gibt eine Reihe von Bibliotheks Entwurfs Empfehlungen, die speziell für F # gelten. Wenn keine spezifischen Empfehlungen befolgt werden, sind die Entwurfs Richtlinien für .NET-Bibliotheken die Ausweich Anleitung.

### <a name="naming-conventions"></a>Benennungskonventionen

#### <a name="use-net-naming-and-capitalization-conventions"></a>.Net-Benennungs-und-groß Schreibung

In der folgenden Tabelle sind die .net-Benennungs-und-groß Schreibung Es gibt kleine Ergänzungen, die auch F #-Konstrukte enthalten.

| Konstrukt | Fall | Teil | Beispiele | Hinweise |
|-----------|------|------|----------|-------|
| Konkrete Typen | PascalCase | Substantiv/Adjektiv | List, Double, Complex | Konkrete Typen sind Strukturen, Klassen, Enumerationen, Delegaten, Datensätze und Unions. Obwohl Typnamen in ocaml traditionell klein geschrieben werden, hat F # das .net-Benennungs Schema für-Typen übernommen.
| DLLs           | PascalCase |                 | Fabrikam. Core. dll |  |
| Union-Tags     | PascalCase | Nomen | Einige, hinzufügen, Erfolg | Verwenden Sie kein Präfix in öffentlichen APIs. Optional ein Präfix verwenden, z. b.`type Teams = TAlpha | TBeta | TDelta.` |
| Ereignis          | PascalCase | Verb | ValueChanged/valuechanging |  |
| Ausnahmen     | PascalCase |      | WebException | Der Name muss auf "Exception" enden. |
| Feld          | PascalCase | Nomen | Currentname  | |
| Schnittstellentypen |  PascalCase | Substantiv/Adjektiv | IDisposable | Der Name sollte mit "I" beginnen. |
| Methode |  PascalCase |  Verb | ToString | |
| Namespace | PascalCase | | Microsoft. FSharp. Core | Verwenden Sie in der Regel, wenn die `<Organization>.<Technology>[.<Subnamespace>]` Organisation unabhängig von der Organisation ist. |
| Parameter | CamelCase | Nomen |  Typname, Transformation, Bereich | |
| Let-Werte (intern) | CamelCase oder PascalCase | Substantiv/Verb |  GetValue, myTable |
| Werte zulassen (extern) | CamelCase oder PascalCase | Substantiv/Verb  | List. map, dates. heute | Let-gebundene Werte sind häufig öffentlich, wenn Sie herkömmliche funktionale Entwurfsmuster befolgen. Verwenden Sie in der Regel jedoch PascalCase, wenn der Bezeichner von anderen .NET-Sprachen verwendet werden kann. |
| Eigenschaft  | PascalCase  | Substantiv/Adjektiv  | Isendoffile, BackColor  | Boolesche Eigenschaften werden in der Regel verwendet, und es kann und sein, wie in isendoffile, nicht isnotendoffile.

#### <a name="avoid-abbreviations"></a>Abkürzungen vermeiden

Die .NET-Richtlinien verhindern die Verwendung von Abkürzungen (z. b `OnButtonClick` . "Use anstelle `OnBtnClick` "). Allgemeine Abkürzungen, wie z `Async` . b. für "asynchron", werden toleriert. Diese Richtlinie wird manchmal bei der funktionalen Programmierung ignoriert. Beispielsweise wird von `List.iter` eine Abkürzung für "Iterate" verwendet. Aus diesem Grund wird die Verwendung von Abkürzungen tendenziell in größerem Umfang in der f #-zu-F #-Programmierung toleriert, sollte jedoch im Entwurf der öffentlichen Komponente immer noch vermieden werden.

#### <a name="avoid-casing-name-collisions"></a>Vermeiden von Namenskonflikten in Großbuchstaben

Die .NET-Richtlinien sagen, dass die Groß-/Kleinschreibung allein nicht verwendet werden kann, um Namenskonflikte eindeutig zu machen, da bei einigen Client Sprachen (z. b. Visual Basic) die Groß-/Kleinschreibung

#### <a name="use-acronyms-where-appropriate"></a>Verwenden Sie ggf. acronyme.

Akronyme, z. b. XML, sind keine Abkürzungen und werden häufig in .NET-Bibliotheken in nicht Großbuchstaben (XML) verwendet. Es sollten nur bekannte, allgemein erkannte Akronyme verwendet werden.

#### <a name="use-pascalcase-for-generic-parameter-names"></a>Verwenden von PascalCase für generische Parameternamen

Verwenden Sie PascalCase für generische Parameternamen in öffentlichen APIs, z. b. für Bibliotheken mit F #. Verwenden Sie insbesondere Namen wie `T` , `U` , `T1` `T2` für beliebige generische Parameter, und wenn bestimmte Namen sinnvoll sind, verwenden Sie für mit F # ausgerichtete Bibliotheken Namen wie,, `Key` `Value` `Arg` (aber nicht beispielsweise `TKey` ).

#### <a name="use-either-pascalcase-or-camelcase-for-public-functions-and-values-in-f-modules"></a>Verwenden Sie entweder PascalCase oder CamelCase für öffentliche Funktionen und Werte in F #-Modulen.

CamelCase wird für öffentliche Funktionen verwendet, die für die Verwendung als nicht qualifiziert konzipiert sind (z. b. `invalidArg` ), und für die "Standard Auflistungs Funktionen" (z. b. List. map). In beiden Fällen agieren die Funktionsnamen ähnlich wie Schlüsselwörter in der Sprache.

### <a name="object-type-and-module-design"></a>Objekt-, Typ-und Modul Entwurf

#### <a name="use-namespaces-or-modules-to-contain-your-types-and-modules"></a>Verwenden von Namespaces oder Modulen zum enthalten von Typen und Modulen

Jede F #-Datei in einer Komponente sollte entweder mit einer Namespace Deklaration oder einer Modul Deklaration beginnen.

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

Die Unterschiede zwischen der Verwendung von Modulen und Namespaces zum Organisieren von Code auf oberster Ebene lauten wie folgt:

* Namespaces können mehrere Dateien umfassen.
* Namespaces dürfen keine F #-Funktionen enthalten, es sei denn, Sie befinden sich in einem inneren Modul
* Der Code für ein bestimmtes Modul muss in einer einzelnen Datei enthalten sein.
* Module der obersten Ebene können F #-Funktionen enthalten, ohne dass ein internes Modul erforderlich ist.

Die Wahl zwischen einem Namespace oder Modul der obersten Ebene wirkt sich auf die kompilierte Form des Codes aus und wirkt sich daher auf die Ansicht von anderen .NET-Sprachen aus, wenn Ihre API schließlich außerhalb von F #-Code verwendet werden soll.

#### <a name="use-methods-and-properties-for-operations-intrinsic-to-object-types"></a>Verwenden von Methoden und Eigenschaften für systeminterne Vorgänge in Objekttypen

Beim Arbeiten mit-Objekten ist es am besten, sicherzustellen, dass die verwendbare Funktionalität als Methoden und Eigenschaften für diesen Typ implementiert wird.

```fsharp
type HardwareDevice() =

    member this.ID = ...

    member this.SupportedProtocols = ...

type HashTable<'Key,'Value>(comparer: IEqualityComparer<'Key>) =

    member this.Add(key, value) = ...

    member this.ContainsKey(key) = ...

    member this.ContainsValue(value) = ...
```

Der Großteil der Funktionalität für ein bestimmtes Element muss nicht notwendigerweise in diesem Member implementiert werden, aber der nutzbare Teil dieser Funktionalität sollte sein.

#### <a name="use-classes-to-encapsulate-mutable-state"></a>Verwenden von Klassen zum Kapseln des änderbaren Zustands

In F # muss dies nur erfolgen, wenn dieser Zustand nicht bereits von einem anderen Sprachkonstrukt gekapselt ist, wie z. b. ein Abschluss, ein Sequenz Ausdruck oder eine asynchrone Berechnung.

```fsharp
type Counter() =
    // let-bound values are private in classes.
    let mutable count = 0

    member this.Next() =
        count <- count + 1
        count
```

#### <a name="use-interfaces-to-group-related-operations"></a>Verwenden von Schnittstellen zum Gruppieren verwandter Vorgänge

Verwenden Sie Schnittstellentypen, um einen Satz von Vorgängen darzustellen. Dies wird für andere Optionen bevorzugt, wie z. b. Tupel von Funktionen oder Daten Satz Funktionen.

```fsharp
type Serializer =
    abstract Serialize<'T>: preserveRefEq: bool -> value: 'T -> string
    abstract Deserialize<'T>: preserveRefEq: bool -> pickle: string -> 'T
```

Vor:

```fsharp
type Serializer<'T> = {
    Serialize: bool -> 'T -> string
    Deserialize: bool -> string -> 'T
}
```

Schnittstellen sind erstklassige Konzepte in .net, die Sie verwenden können, um zu erreichen, welche Funktoren Sie normalerweise erhalten. Darüber hinaus können Sie verwendet werden, um existentielle Typen in Ihrem Programm zu codieren, die Datensätze von Funktionen nicht haben.

#### <a name="use-a-module-to-group-functions-that-act-on-collections"></a>Verwenden eines Moduls zum Gruppieren von Funktionen, die auf Auflistungen reagieren

Wenn Sie einen Sammlungstyp definieren, sollten Sie die Bereitstellung eines Standardsatzes von Vorgängen wie `CollectionType.map` und `CollectionType.iter` ) für neue Sammlungs Typen in Erwägung gezogen.

```fsharp
module CollectionType =
    let map f c =
        ...
    let iter f c =
        ...
```

Wenn Sie ein solches Modul einschließen, befolgen Sie die Standard Benennungs Konventionen für Funktionen, die in FSharp. Core gefunden werden.

#### <a name="use-a-module-to-group-functions-for-common-canonical-functions-especially-in-math-and-dsl-libraries"></a>Verwenden eines Moduls zum Gruppieren von Funktionen für allgemeine, kanonische Funktionen, insbesondere in mathematischen und DSL-Bibliotheken

Beispielsweise `Microsoft.FSharp.Core.Operators` ist eine automatisch geöffnete Auflistung von Funktionen der obersten Ebene (wie `abs` und), die `sin` von FSharp. Core. dll bereitgestellt werden.

Ebenso kann eine Statistik Bibliothek ein Modul mit Funktionen und enthalten `erf` `erfc` , bei denen dieses Modul explizit oder automatisch geöffnet werden soll.

#### <a name="consider-using-requirequalifiedaccess-and-carefully-apply-autoopen-attributes"></a>Ziehen Sie die Verwendung von "Requirements qualifiedaccess" in Erwägung, und wenden Sie die

Das Hinzufügen des- `[<RequireQualifiedAccess>]` Attributs zu einem Modul gibt an, dass das Modul möglicherweise nicht geöffnet wird und dass Verweise auf die Elemente des Moduls einen expliziten qualifizierten Zugriff erfordern. Beispielsweise verfügt das `Microsoft.FSharp.Collections.List` Modul über dieses Attribut.

Dies ist nützlich, wenn Funktionen und Werte im Modulnamen haben, die mit den Namen in anderen Modulen wahrscheinlich in Konflikt stehen. Wenn qualifizierter Zugriff erforderlich ist, kann die langfristige Wartbarkeit und die Entwicklung einer Bibliothek erheblich gesteigert werden.

Das Hinzufügen des- `[<AutoOpen>]` Attributs zu einem Modul bedeutet, dass das Modul geöffnet wird, wenn der enthaltende Namespace geöffnet wird. Das- `[<AutoOpen>]` Attribut kann auch auf eine Assembly angewendet werden, um ein Modul anzugeben, das automatisch geöffnet wird, wenn auf die Assembly verwiesen wird.

Beispielsweise kann eine Statistik Bibliothek **mathsheaven. Statistics** eine `module MathsHeaven.Statistics.Operators` enthaltende Funktion `erf` und enthalten `erfc` . Es ist sinnvoll, dieses Modul als zu markieren `[<AutoOpen>]` . Dies bedeutet, dass `open MathsHeaven.Statistics` auch dieses Modul geöffnet und die Namen `erf` und in den Gültigkeitsbereich gebracht werden `erfc` . Eine weitere gute Verwendung von `[<AutoOpen>]` ist für Module, die Erweiterungs Methoden enthalten.

Die übermäßige Verwendung von `[<AutoOpen>]` führt zu verschmutzten Namespaces, und das Attribut sollte mit Bedacht verwendet werden. Für bestimmte Bibliotheken in bestimmten Domänen kann die durch die Verwendung von eine `[<AutoOpen>]` bessere Benutzerfreundlichkeit führen.

#### <a name="consider-defining-operator-members-on-classes-where-using-well-known-operators-is-appropriate"></a>Es empfiehlt sich, Operator Member für Klassen zu definieren, in denen bekannte Operatoren geeignet sind.

Manchmal werden Klassen verwendet, um mathematische Konstrukte zu modellieren, z. b. Vektoren. Wenn die zu modellierende Domäne über bekannte Operatoren verfügt, ist es hilfreich, Sie als intrinsische Elemente für die Klasse zu definieren.

```fsharp
type Vector(x: float) =

    member v.X = x

    static member (*) (vector: Vector, scalar: float) = Vector(vector.X * scalar)

    static member (+) (vector1: Vector, vector2: Vector) = Vector(vector1.X + vector2.X)

let v = Vector(5.0)

let u = v * 10.0
```

Diese Anleitung entspricht allgemeinen .net-Anleitungen für diese Typen. Dies kann jedoch in F #-Codierungen von Bedeutung sein, da diese Typen in Verbindung mit f #-Funktionen und-Methoden mit Element Einschränkungen, z. b. List. sumBy, verwendet werden können.

#### <a name="consider-using-compiledname-to-provide-a-net-friendly-name-for-other-net-language-consumers"></a>Verwenden Sie CompiledName, um einen bereitzustellen. Netzwerk freundlicher Name für andere .NET-Sprachen

In manchen Fällen möchten Sie möglicherweise etwas in einem Stil für F #-Consumer benennen (z. b. ein statisches Element in Kleinbuchstaben, sodass es so aussieht, als ob es sich um eine Modul gebundene Funktion handelt), aber einen anderen Stil für den Namen haben, wenn es in eine Assembly kompiliert wird. Sie können das- `[<CompiledName>]` Attribut verwenden, um einen anderen Stil für nicht F #-Code bereitzustellen, der die Assembly verwendet.

```fsharp
type Vector(x:float, y:float) =

    member v.X = x
    member v.Y = y

    [<CompiledName("Create")>]
    static member create x y = Vector (x, y)

let v = Vector.create 5.0 3.0
```

Mithilfe von `[<CompiledName>]` können Sie .net-Benennungs Konventionen für nicht-F #-Consumer der Assembly verwenden.

#### <a name="use-method-overloading-for-member-functions-if-doing-so-provides-a-simpler-api"></a>Verwenden Sie das Überladen von Methoden für Member-Funktionen, wenn dies eine einfachere API bereitstellt.

Das Überladen von Methoden ist ein leistungsfähiges Tool zum Vereinfachen einer API, die möglicherweise eine ähnliche Funktionalität ausführen muss, aber mit unterschiedlichen Optionen oder Argumenten.

```fsharp
type Logger() =

    member this.Log(message) =
        ...
    member this.Log(message, retryPolicy) =
        ...
```

In F # ist es häufiger, eine Überladung für die Anzahl von Argumenten anstelle von Argument Typen zu überlasten.

#### <a name="hide-the-representations-of-record-and-union-types-if-the-design-of-these-types-is-likely-to-evolve"></a>Blenden Sie die Darstellungen von Daten Satz-und Union-Typen aus, wenn sich der Entwurf dieser Typen wahrscheinlich weiterentwickelt.

Vermeiden Sie es, konkrete Darstellungen von Objekten offenzulegen. Beispielsweise wird die konkrete Darstellung von <xref:System.DateTime> Werten nicht von der externen öffentlichen API des Entwurfs der .NET-Bibliothek offengelegt. Zur Laufzeit kennt die Common Language Runtime die implementiertes Implementierung, die während der Ausführung verwendet wird. Allerdings übernimmt der kompilierte Code nicht selbst Abhängigkeiten von der konkreten Darstellung.

#### <a name="avoid-the-use-of-implementation-inheritance-for-extensibility"></a>Vermeiden Sie die Verwendung der Implementierungs Vererbung für die Erweiterbarkeit.

In F # wird die Implementierungsvererbung selten verwendet. Außerdem sind Vererbungs Hierarchien häufig komplex und schwer zu ändern, wenn neue Anforderungen eingehen. Die Vererbungs Implementierung ist in f # weiterhin für Kompatibilität und in seltenen Fällen vorhanden, in denen es sich um die beste Lösung für ein Problem handelt, aber alternative Techniken bei der Entwicklung von Polymorphie, wie z. b. der Schnittstellen Implementierung, in ihren f #-Programmen.

### <a name="function-and-member-signatures"></a>Funktions-und Element Signaturen

#### <a name="use-tuples-for-return-values-when-returning-a-small-number-of-multiple-unrelated-values"></a>Verwenden Sie Tupel für Rückgabewerte, wenn Sie eine kleine Anzahl von mehreren nicht verknüpften Werten zurückgeben.

Im folgenden finden Sie ein gutes Beispiel für die Verwendung eines Tupels in einem Rückgabetyp:

```fsharp
val divrem: BigInteger -> BigInteger -> BigInteger * BigInteger
```

Verwenden Sie für Rückgabe Typen, die viele Komponenten enthalten oder für die die Komponenten mit einer einzelnen identifizierbaren Entität verknüpft sind, einen benannten Typ anstelle eines Tupels.

#### <a name="use-asynct-for-async-programming-at-f-api-boundaries"></a>Verwendung für die asynchrone `Async<T>` Programmierung in F #-API-Grenzen

Wenn ein entsprechender synchroner Vorgang mit dem Namen vorhanden ist `Operation` , der einen zurückgibt `T` , sollte der asynchrone Vorgang bei Rückgabe von oder zurückgegeben werden `AsyncOperation` `Async<T>` `OperationAsync` `Task<T>` . Für häufig verwendete .NET-Typen, die Begin/End-Methoden verfügbar machen, empfiehlt es sich, mithilfe `Async.FromBeginEnd` von Erweiterungs Methoden als Fassade zu schreiben, um diese .NET-APIs mit dem asynchronen F #-Programmiermodell bereitzustellen

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

Weitere Informationen zur geeigneten Verwendung von Ausnahmen, Ergebnissen und Optionen finden Sie unter [Fehler Verwaltung](conventions.md#error-management) .

### <a name="extension-members"></a>Erweiterungsmember

#### <a name="carefully-apply-f-extension-members-in-f-to-f-components"></a>Sorgfältiges Anwenden von f #-Erweiterungs Membern in f #-zu-f #-Komponenten

F #-Erweiterungs Elemente sollten in der Regel nur für Vorgänge verwendet werden, die bei der Schließung von systeminternen Vorgängen verwendet werden, die einem Typ in den meisten Verwendungs Modi zugeordnet sind. Eine häufige Verwendung besteht darin, APIs bereitzustellen, die mehr idiomatisch in F # für verschiedene .NET-Typen sind:

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

#### <a name="use-discriminated-unions-instead-of-class-hierarchies-for-tree-structured-data"></a>Verwenden von Unterscheidungs-Unions anstelle von Klassenhierarchien für Struktur strukturierte Daten

Struktur ähnliche Strukturen werden rekursiv definiert. Dies ist mit Vererbung, aber elegant mit Unterscheidungs-Unions sehr umständlich.

```fsharp
type BST<'T> =
    | Empty
    | Node of 'T * BST<'T> * BST<'T>
```

Das darstellen von Struktur ähnlichen Daten mit Unterscheidungs-Unions ermöglicht Ihnen außerdem, von der Erschöpfung bei der Muster Übereinstimmung profitieren zu können.

#### <a name="use-requirequalifiedaccess-on-union-types-whose-case-names-are-not-sufficiently-unique"></a>Verwendung `[<RequireQualifiedAccess>]` für Union-Typen, deren Groß-/Kleinschreibung nicht ausreichend eindeutig ist

Sie können sich in einer Domäne befinden, in der derselbe Name der beste Name für verschiedene Dinge ist, wie z. b. diskriminierte Union-Fälle. Sie können verwenden `[<RequireQualifiedAccess>]` , um Case-Namen eindeutig zu machen, um zu vermeiden, dass verwirrende Fehler ausgelöst werden, da shadodown von der Reihenfolge der Anweisungen abhängig ist. `open`

#### <a name="hide-the-representations-of-discriminated-unions-for-binary-compatible-apis-if-the-design-of-these-types-is-likely-to-evolve"></a>Verbergen der Darstellungen von Unterscheidungs-Unions für Binär kompatible APIs, wenn sich der Entwurf dieser Typen wahrscheinlich weiterentwickelt

Unions-Typen basieren auf F #-Muster Vergleichs Formularen für ein präct-Programmiermodell. Wie bereits erwähnt, sollten Sie das Offenlegen konkreter Daten Darstellungen vermeiden, wenn sich der Entwurf dieser Typen wahrscheinlich weiterentwickelt.

Beispielsweise kann die Darstellung einer Unterscheidungs-Union mit einer privaten oder internen Deklaration oder mithilfe einer Signatur Datei ausgeblendet werden.

```fsharp
type Union =
    private
    | CaseA of int
    | CaseB of string
```

Wenn Sie Unterscheidungs Unions willkürlich offenlegen, ist es möglicherweise schwierig, Ihre Bibliothek zu versidieren, ohne den Benutzercode zu unterbrechen. Verwenden Sie stattdessen ein oder mehrere aktive Muster, um eine Muster Übereinstimmung für Werte des Typs zuzulassen.

Aktive Muster bieten eine alternative Möglichkeit, f #-Consumer mit Muster Übereinstimmungen bereitzustellen und gleichzeitig die direkte Bereitstellung von f #-Union-Typen

### <a name="inline-functions-and-member-constraints"></a>Inline Funktionen und Element Einschränkungen

#### <a name="define-generic-numeric-algorithms-using-inline-functions-with-implied-member-constraints-and-statically-resolved-generic-types"></a>Definieren von generischen numerischen Algorithmen mithilfe von Inline Funktionen mit impliziten Element Einschränkungen und statisch aufgelösten generischen Typen

Arithmetische Member-Einschränkungen und f #-Vergleichs Einschränkungen sind ein Standard für die f #-Programmierung. Beachten Sie z. B. folgenden Code:

```fsharp
let inline highestCommonFactor a b =
    let rec loop a b =
        if a = LanguagePrimitives.GenericZero<_> then b
        elif a < b then loop a (b - a)
        else loop (a - b) b
    loop a b
```

Der Typ dieser Funktion ist wie folgt:

```fsharp
val inline highestCommonFactor : ^T -> ^T -> ^T
                when ^T : (static member Zero : ^T)
                and ^T : (static member ( - ) : ^T * ^T -> ^T)
                and ^T : equality
                and ^T : comparison
```

Dies ist eine geeignete Funktion für eine öffentliche API in einer mathematischen Bibliothek.

#### <a name="avoid-using-member-constraints-to-simulate-type-classes-and-duck-typing"></a>Vermeiden Sie die Verwendung von Element Einschränkungen zum Simulieren von Typklassen und der Typisierung

Es ist möglich, "ententypisierung" mithilfe von F #-Member-Einschränkungen zu simulieren. Member, die diese verwenden, sollten jedoch nicht im Allgemeinen in f #-zu-f #-Bibliotheks Entwürfen verwendet werden. Dies liegt daran, dass Bibliotheks Entwürfe, die auf unbekannten oder nicht standardmäßigen impliziten Einschränkungen basieren, dazu führen, dass Benutzercode unflexibel und an ein bestimmtes Framework-Muster gebunden wird.

Außerdem gibt es eine gute Wahrscheinlichkeit, dass Element Einschränkungen auf diese Weise sehr lange kompiliert werden können.

### <a name="operator-definitions"></a>Operator Definitionen

#### <a name="avoid-defining-custom-symbolic-operators"></a>Vermeiden der Definition benutzerdefinierter symbolischer Operatoren

Benutzerdefinierte Operatoren sind in einigen Situationen unverzichtbar und sind sehr nützliche notationgeräte innerhalb eines großen Texts von Implementierungs Code. Für neue Benutzer einer Bibliothek sind benannte Funktionen häufig einfacher zu verwenden. Außerdem können benutzerdefinierte symbolische Operatoren schwer zu dokumentieren sein, und Benutzer können aufgrund vorhandener Einschränkungen in IDE-und Suchmaschinen die Suche nach Hilfe zu Operatoren erschweren.

Daher ist es am besten, ihre Funktionalität als benannte Funktionen und Member zu veröffentlichen, und zusätzlich Operatoren für diese Funktionalität nur verfügbar zu machen, wenn die notalisierungsvorteile die Dokumentation und die kognitiven Kosten Ihrer IT überwiegen.

### <a name="units-of-measure"></a>Maßeinheiten

#### <a name="carefully-use-units-of-measure-for-added-type-safety-in-f-code"></a>Sorgfältige Verwendung von Maßeinheiten für die hinzugefügte Typsicherheit in F #-Code

Zusätzliche Typisierungs Informationen für Maßeinheiten werden gelöscht, wenn Sie von anderen .NET-Sprachen angezeigt werden. Beachten Sie, dass .NET-Komponenten,-Tools und-Reflektion Typen-Sans-Units sehen werden. Beispielsweise sehen c#-Consumer `float` anstelle von `float<kg>` .

### <a name="type-abbreviations"></a>Typabkürzungen

#### <a name="carefully-use-type-abbreviations-to-simplify-f-code"></a>Sorgfältige Verwendung von typabkürzungen zum Vereinfachen von F #-Code

Für .NET-Komponenten,-Tools und-Reflektion werden keine abgekürzten Namen für-Typen angezeigt. Eine bedeutende Verwendung von typabkürzungen kann auch dazu führen, dass eine Domäne komplexer erscheint, als Sie tatsächlich ist, was den Consumer verwirren könnte.

#### <a name="avoid-type-abbreviations-for-public-types-whose-members-and-properties-should-be-intrinsically-different-to-those-available-on-the-type-being-abbreviated"></a>Vermeiden Sie typabkürzungen für öffentliche Typen, deren Member und Eigenschaften sich intrinsisch von denen unterscheiden, die für den Typ verfügbar sind, der abgekürzt wird.

In diesem Fall wird der Typ, der abgekürzt wird, zu viel über die Darstellung des tatsächlichen Typs angezeigt, der definiert wird. Stattdessen sollten Sie die Abkürzung in einen Klassentyp oder eine Unterscheidungs-Union einschließen (oder wenn die Leistung unverzichtbar ist, sollten Sie einen Strukturtyp verwenden, um die Abkürzung zu umschließen).

Beispielsweise ist es verlockend, eine mehrfach Zuordnung als Sonderfall einer F #-Karte zu definieren, beispielsweise:

```fsharp
type MultiMap<'Key,'Value> = Map<'Key,'Value list>
```

Allerdings sind die logischen Punkt Schreibvorgänge für diesen Typ nicht mit den Vorgängen auf einer Zuordnung identisch – beispielsweise ist es sinnvoll, dass der Such Operator zugeordnet ist. [key] gibt die leere Liste zurück, wenn der Schlüssel nicht im Wörterbuch enthalten ist, anstatt eine Ausnahme zu erhöhen.

## <a name="guidelines-for-libraries-for-use-from-other-net-languages"></a>Richtlinien für Bibliotheken zur Verwendung in anderen .NET-Sprachen

Beim Entwerfen von Bibliotheken für die Verwendung in anderen .NET-Sprachen ist es wichtig, die [Entwurfs Richtlinien für .net](../../standard/design-guidelines/index.md)-Bibliotheken einzuhalten. In diesem Dokument werden diese Bibliotheken als "Vanille .NET-Bibliotheken" bezeichnet, im Gegensatz zu f #-orientierten Bibliotheken, die f #-Konstrukte ohne Einschränkung verwenden. Das Entwerfen von Vanille-.NET-Bibliotheken bedeutet, dass vertraute und idiomatische APIs konsistent mit dem Rest der .NET Framework sind, indem die Verwendung von F #-spezifischen Konstrukten in der öffentlichen API minimiert wird. Die Regeln werden in den folgenden Abschnitten erläutert.

### <a name="namespace-and-type-design-for-libraries-for-use-from-other-net-languages"></a>Namespace und typentwurf (für Bibliotheken zur Verwendung in anderen .NET-Sprachen)

#### <a name="apply-the-net-naming-conventions-to-the-public-api-of-your-components"></a>Anwenden der .net-Benennungs Konventionen auf die öffentliche API ihrer Komponenten

Achten Sie besonders auf die Verwendung von abgekürzten Namen und den .NET-Richtlinien für die Groß Schreibung

```fsharp
type pCoord = ...
    member this.theta = ...

type PolarCoordinate = ...
    member this.Theta = ...
```

#### <a name="use-namespaces-types-and-members-as-the-primary-organizational-structure-for-your-components"></a>Verwenden von Namespaces, Typen und Membern als primäre Organisationsstruktur für Ihre Komponenten

Alle Dateien, die die öffentliche Funktionalität enthalten, müssen mit einer `namespace` -Deklaration beginnen, und die einzigen öffentlich ausgerichteten Entitäten in Namespaces sollten-Typen sein. Verwenden Sie keine F #-Module.

Verwenden Sie nicht öffentliche Module zum Speichern von Implementierungs Code, hilfsprogrammtypen und Hilfsprogrammfunktionen.

Statische Typen sollten gegenüber Modulen bevorzugt werden, da Sie für zukünftige Entwicklungen der API die Verwendung von überladen und anderen .NET-API-Entwurfskonzepten ermöglichen, die nicht in F #-Modulen verwendet werden können.

Beispielsweise anstelle der folgenden öffentlichen API:

```fsharp
module Fabrikam

module Utilities =
    let Name = "Bob"
    let Add2 x y = x + y
    let Add3 x y z = x + y + z
```

Verwenden Sie stattdessen Folgendes:

```fsharp
namespace Fabrikam

[<AbstractClass; Sealed>]
type Utilities =
    static member Name = "Bob"
    static member Add(x,y) = x + y
    static member Add(x,y,z) = x + y + z
```

#### <a name="use-f-record-types-in-vanilla-net-apis-if-the-design-of-the-types-wont-evolve"></a>Verwenden von F #-Daten Satz Typen in Vanille-.NET-APIs, wenn der Entwurf der Typen nicht weiterentwickelt wird

F #-Daten Satz Typen werden in eine einfache .NET-Klasse kompiliert. Diese sind für einige einfache, stabile Typen in APIs geeignet. Verwenden Sie die `[<NoEquality>]` `[<NoComparison>]` Attribute und, um die automatische Generierung von Schnittstellen zu unterdrücken. Vermeiden Sie außerdem die Verwendung änderbarer Daten Satz Felder in den .NET-APIs von Vanille, da diese ein öffentliches Feld verfügbar machen Denken Sie immer daran, ob eine Klasse eine flexiblere Option zur zukünftigen Entwicklung der API bereitstellen würde.

Beispielsweise macht der folgende F #-Code die öffentliche API für einen c#-Consumer verfügbar:

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

#### <a name="hide-the-representation-of-f-union-types-in-vanilla-net-apis"></a>Ausblenden der Darstellung von F #-Union-Typen in Vanille-. NET-APIs

F #-Union-Typen werden nicht häufig über Komponenten Grenzen hinweg verwendet, auch bei f #-zu-f #-Codierungen. Sie sind ein ausgezeichnetes Implementierungs Gerät, wenn es intern innerhalb von Komponenten und Bibliotheken verwendet wird.

Beim Entwerfen einer .NET-API für Vanille sollten Sie die Darstellung eines Union-Typs in Erwägung gezogen, indem Sie entweder eine private oder eine Signatur Datei verwenden.

```fsharp
type PropLogic =
    private
    | And of PropLogic * PropLogic
    | Not of PropLogic
    | True
```

Sie können auch Typen erweitern, die eine Union-Darstellung intern mit Membern verwenden, um ein gewünschtes bereitzustellen. NET-API.

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

#### <a name="design-gui-and-other-components-using-the-design-patterns-of-the-framework"></a>Entwerfen von GUI und anderen Komponenten mithilfe der Entwurfsmuster des Frameworks

In .net stehen viele verschiedene Frameworks zur Verfügung, z. b. WinForms, WPF und ASP.net. Benennungs-und Entwurfs Konventionen sollten verwendet werden, wenn Sie Komponenten für die Verwendung in diesen Frameworks entwerfen. Nehmen Sie z. b. für die WPF-Programmierung WPF-Entwurfsmuster für die Klassen an, die Sie entwerfen. Verwenden Sie für Modelle in der Programmierung von Benutzeroberflächen Entwurfsmuster wie z. b. Ereignisse und Benachrichtigungs basierte Auflistungen, z. b. die in <xref:System.Collections.ObjectModel> .

### <a name="object-and-member-design-for-libraries-for-use-from-other-net-languages"></a>Objekt-und Element Entwurf (für Bibliotheken zur Verwendung in anderen .NET-Sprachen)

#### <a name="use-the-clievent-attribute-to-expose-net-events"></a>Verwenden des clievent-Attributs zum verfügbar machen von .NET-Ereignissen

Erstellen `DelegateEvent` Sie ein-Objekt mit einem bestimmten .net-Delegattyp, der ein-Objekt und `EventArgs` (anstelle eines `Event` verwendet, das `FSharpHandler` standardmäßig den-Typ verwendet), sodass die Ereignisse auf vertraute Weise in anderen .NET-Sprachen veröffentlicht werden.

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

#### <a name="expose-asynchronous-operations-as-methods-that-return-net-tasks"></a>Verfügbar machen asynchroner Vorgänge als Methoden, die .net-Tasks zurückgeben

Tasks werden in .NET verwendet, um aktive asynchrone Berechnungen darzustellen. Aufgaben sind im Allgemeinen weniger festgesetzt als F # `Async<T>` -Objekte, da Sie "bereits ausgeführte" Aufgaben darstellen und nicht in einer Weise zusammengesetzt werden können, die eine parallele Komposition durchführt oder die Propagierung von Abbruch Signalen und anderen Kontext Parametern ausblenden.

Dennoch sind Methoden, die Aufgaben zurückgeben, die Standarddarstellung der asynchronen Programmierung in .net.

```fsharp
/// A type in a component designed for use from other .NET languages
type MyType() =

    let compute (x: int): Async<int> = async { ... }

    member this.ComputeAsync(x) = compute x |> Async.StartAsTask
```

Sie möchten häufig auch ein explizites Abbruch Token akzeptieren:

```fsharp
/// A type in a component designed for use from other .NET languages
type MyType() =
    let compute(x: int): Async<int> = async { ... }
    member this.ComputeAsTask(x, cancellationToken) = Async.StartAsTask(compute x, cancellationToken)
```

#### <a name="use-net-delegate-types-instead-of-f-function-types"></a>Verwenden von .net-Delegattypen anstelle von F #-Funktionstypen

Hier sind "F #-Funktionstypen", "Pfeil"-Typen wie `int -> int` .

Anstelle von:

```fsharp
member this.Transform(f: int->int) =
    ...
```

Gehen Sie folgendermaßen vor:

```fsharp
member this.Transform(f: Func<int,int>) =
    ...
```

Der F #-Funktionstyp `class FSharpFunc<T,U>` wird als zu anderen .NET-Sprachen angezeigt und ist weniger geeignet für sprach Features und Tools, die Delegattypen verstehen. Beim Erstellen einer höherwertigen Methode, die auf .NET Framework 3,5 oder höher ausgerichtet ist, sind die Delegaten `System.Func` und `System.Action` die richtigen APIs für die Veröffentlichung, damit .NET-Entwickler diese APIs auf wenig reibungslose Weise nutzen können. (Bei .NET Framework 2,0 werden die System definierten Delegattypen eingeschränkt. verwenden Sie ggf. vordefinierte Delegattypen, z `System.Converter<T,U>` . b., oder definieren Sie einen bestimmten Delegattyp.)

Auf der Flip-Seite sind .net-Delegaten bei f #-orientierten Bibliotheken nicht von Belang (Weitere Informationen finden Sie im nächsten Abschnitt zu f #-orientierten Bibliotheken). Daher besteht eine gängige Implementierungsstrategie beim Entwickeln von Methoden höherer Ordnung für die Verwendung von .NET-Bibliotheken darin, die gesamte Implementierung mithilfe von f #-Funktionstypen zu verfassen und dann die öffentliche API mithilfe von Delegaten als schlanke Fassade auf der eigentlichen f #-Implementierung zu erstellen.

#### <a name="use-the-trygetvalue-pattern-instead-of-returning-f-option-values-and-prefer-method-overloading-to-taking-f-option-values-as-arguments"></a>Verwenden Sie das TryGetValue-Muster anstelle der Rückgabe von f #-Options Werten, und bevorzugen Sie Methoden Überladung, um f #-Optionswerte als Argumente zu verwenden.

Gängige Verwendungs Muster für den F #-Optionstyp in APIs sind in den .NET-APIs von .NET mithilfe von .NET-Standard Entwurfs Techniken besser implementiert. Anstatt einen F #-Optionswert zurückzugeben, sollten Sie den booleschen Rückgabetyp plus einen out-Parameter wie im "TryGetValue"-Muster verwenden. Anstatt die F #-Optionswerte als Parameter zu verwenden, sollten Sie die Verwendung von Methoden Überladungen oder optionalen Argumenten in Erwägung ziehen.

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

#### <a name="use-the-net-collection-interface-types-ienumerablet-and-idictionarykeyvalue-for-parameters-and-return-values"></a>Verwenden Sie die .net-Auflistungs Schnittstellentypen IEnumerable \< T \> und IDictionary \< Key, Wert \> für Parameter und Rückgabewerte.

Vermeiden Sie die Verwendung von konkreten Auflistungs Typen wie .NET-Arrays `T[]` , F #-Typen und und konkreten Auflistungs `list<T>` Typen von .net, `Map<Key,Value>` `Set<T>` wie z `Dictionary<Key,Value>` . b.. Die Entwurfs Richtlinien für .NET-Bibliotheken bieten gute Ratschläge hinsichtlich der Verwendung verschiedener Sammlungs Typen wie `IEnumerable<T>` . Die Verwendung von Arrays ( `T[]` ) ist unter bestimmten Umständen in Leistungsgründen akzeptabel. Beachten Sie insbesondere, dass `seq<T>` es sich bei nur um den F #-Alias für handelt und dass es sich bei der `IEnumerable<T>` .NET-API oft um einen geeigneten Typ handelt.

Anstelle von F #-Listen:

```fsharp
member this.PrintNames(names: string list) =
    ...
```

F #-Sequenzen verwenden:

```fsharp
member this.PrintNames(names: seq<string>) =
    ...
```

#### <a name="use-the-unit-type-as-the-only-input-type-of-a-method-to-define-a-zero-argument-method-or-as-the-only-return-type-to-define-a-void-returning-method"></a>Verwenden Sie den Unit-Typ als einzigen Eingabetyp einer Methode, um eine Methode mit 0 (null) zu definieren, oder als einzigen Rückgabetyp, um eine Methode mit void-Rückgabe zu definieren.

Vermeiden Sie andere Verwendungsmöglichkeiten des Einheits Typs. Diese sind gut geeignet:

```fsharp
✔ member this.NoArguments() = 3

✔ member this.ReturnVoid(x: int) = ()
```

Dies ist schlecht:

```fsharp
member this.WrongUnit( x: unit, z: int) = ((), ())
```

#### <a name="check-for-null-values-on-vanilla-net-api-boundaries"></a>Überprüfen auf NULL-Werte in den Grenzen der .NET-API

F #-Implementierungs Code verfügt tendenziell über weniger NULL-Werte, da unveränderliche Entwurfsmuster und Einschränkungen bei der Verwendung von NULL-literalen für F #-Typen vorliegen. Bei anderen .NET-Sprachen wird häufig NULL als Wert verwendet. Aus diesem Grund sollte F #-Code, der eine Vanille-. NET-API verfügbar macht, die Parameter auf NULL an der API-Grenze überprüfen und verhindern, dass diese Werte tiefer in den F #-Implementierungs Code fließen. Die `isNull` Funktions-oder Muster Übereinstimmung für das `null` Muster kann verwendet werden.

```fsharp
let checkNonNull argName (arg: obj) =
    match arg with
    | null -> nullArg argName
    | _ -> ()

let checkNonNull` argName (arg: obj) =
    if isNull arg then nullArg argName
    else ()
```

#### <a name="avoid-using-tuples-as-return-values"></a>Vermeiden der Verwendung von Tupeln als Rückgabewerte

Stattdessen sollten Sie lieber einen benannten Typ zurückgeben, der die aggregierten Daten enthält, oder out-Parameter verwenden, um mehrere Werte zurückzugeben. Obwohl Tupel und strukturtupel in .net vorhanden sind (einschließlich der c#-Sprachunterstützung für strukturtupel), stellen Sie am häufigsten nicht die ideale und erwartete API für .NET-Entwickler bereit.

#### <a name="avoid-the-use-of-currying-of-parameters"></a>Vermeiden Sie die Verwendung von Parametern.

Verwenden Sie stattdessen .net-Aufruf Konventionen `Method(arg1,arg2,…,argN)` .

```fsharp
member this.TupledArguments(str, num) = String.replicate num str
```

Tipp: Wenn Sie Bibliotheken für die Verwendung in einer beliebigen .NET-Sprache entwerfen, gibt es keinen Ersatz für die eigentliche Durchführung von experimentellen c#-und Visual Basic Programmierung, um sicherzustellen, dass Ihre Bibliotheken in den folgenden Sprachen richtig aussehen. Sie können auch Tools wie .net Reflektor und die Visual Studio-Objektkatalog verwenden, um sicherzustellen, dass Bibliotheken und deren Dokumentation Entwicklern erwartungsgemäß angezeigt werden.

## <a name="appendix"></a>Anhang

### <a name="end-to-end-example-of-designing-f-code-for-use-by-other-net-languages"></a>End-to-End-Beispiel für das Entwerfen von F #-Code für die Verwendung durch andere .NET-Sprachen

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

Der abherleitet F #-Typ dieser Klasse lautet wie folgt:

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

Sehen wir uns nun an, wie dieser F #-Typ einem Programmierer mit einer anderen .NET-Sprache erscheint. Die ungefähre c#-Signatur lautet z. b. wie folgt:

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

Es gibt einige wichtige Punkte zu beachten, wie F # hier Konstrukte repräsentiert. Zum Beispiel:

* Metadaten, wie z. b. Argument Namen, wurden beibehalten.

* F #-Methoden, die zwei Argumente annehmen, werden zu c#-Methoden, die zwei Argumente annehmen.

* Funktionen und Listen werden zu verweisen auf die entsprechenden Typen in der F #-Bibliothek.

Der folgende Code zeigt, wie Sie diesen Code anpassen können, um diese Aspekte zu berücksichtigen.

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

Der abherleitet F #-Typ des Codes lautet wie folgt:

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

Die c#-Signatur lautet nun wie folgt:

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

Die zur Vorbereitung dieses Typs für die Verwendung als Teil einer Vanille .NET-Bibliothek erstellten Korrekturen lauten wie folgt:

* Mehrere Namen wurden angepasst: `Point1` , `n` , und `l` `f` wurden `RadialPoint` , `count` , `factor` `transform` bzw..

* Hat einen Rückgabetyp von `seq<RadialPoint>` anstelle von verwendet `RadialPoint list` , indem eine Listen Konstruktion mithilfe von `[ ... ]` in eine Sequenz Konstruktion geändert wird `IEnumerable<RadialPoint>` .

* Verwendet den .net-Delegattyp `System.Func` anstelle eines F #-Funktions Typs.

Dies macht es viel leichter, in c#-Code zu verwenden.
