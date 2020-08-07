---
title: Formatieren von nur Text
description: 'Erfahren Sie, wie Sie printf und andere Klartext-Formatierungen in F #-Anwendungen und-Skripts verwenden.'
ms.date: 07/22/2020
ms.openlocfilehash: 6b14633e074961757d0f0cd258d1b1667f5fd8ee
ms.sourcegitcommit: c37e8d4642fef647ebab0e1c618ecc29ddfe2a0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2020
ms.locfileid: "87854918"
---
# <a name="plain-text-formatting"></a>Formatieren von nur Text

F # unterstützt die typüberprüfte Formatierung von Klartext mithilfe von `printf` , `printfn` , `sprintf` und verwandten Funktionen.
Ein auf ein Objekt angewendeter

```console
dotnet fsi

> printfn "Hello %s, %d + %d is %d" "world" 2 2 (2+2);;
```

Gibt die Ausgabe an.

```fsharp
Hello world, 2 + 2 is 4
```

Mit F # können auch strukturierte Werte als nur-Text formatiert werden.
Sehen Sie sich z. b. das folgende Beispiel an, in dem die Ausgabe als Matrix ähnliche Anzeige von Tupeln formatiert wird.

```console
dotnet fsi

> printfn "%A" [ for i in 1 .. 5 -> [ for j in 1 .. 5 -> (i, j) ] ];;

[[(1, 1); (1, 2); (1, 3); (1, 4); (1, 5)];
 [(2, 1); (2, 2); (2, 3); (2, 4); (2, 5)];
 [(3, 1); (3, 2); (3, 3); (3, 4); (3, 5)];
 [(4, 1); (4, 2); (4, 3); (4, 4); (4, 5)];
 [(5, 1); (5, 2); (5, 3); (5, 4); (5, 5)]]
```

Die strukturierte Formatierung im Klartext wird aktiviert, wenn Sie das `%A` Format in Formatierungs Zeichenfolgen verwenden `printf` .
Sie wird auch aktiviert, wenn die Ausgabe von Werten in F # Interactive formatiert wird, wobei die Ausgabe zusätzliche Informationen enthält und außerdem anpassbar ist.
Die nur-Text-Formatierung kann auch durch Aufrufe von in `x.ToString()` F #-Union-und-Datensatz-Werten beobachtet werden, einschließlich derjenigen, die implizit beim Debuggen, protokollieren und anderen Tools auftreten.

## <a name="checking-of-printf-format-strings"></a>Überprüfen von Format Zeichenfolgen `printf`

Ein Kompilierzeitfehler wird gemeldet, wenn eine `printf` Formatierungsfunktion mit einem Argument verwendet wird, das nicht mit den printf-Format bezeichmern in der Format Zeichenfolge identisch ist.  Ein auf ein Objekt angewendeter

```fsharp
sprintf "Hello %s" (2+2)
```

Gibt die Ausgabe an.

```console
  sprintf "Hello %s" (2+2)
  ----------------------^

stdin(3,25): error FS0001: The type 'string' does not match the type 'int'
```

Wenn Sie `printf` und andere verwandte Funktionen verwenden, prüft eine spezielle Regel im F #-Compiler das als Format Zeichenfolge übergebenen Zeichenfolgenliteral. Dadurch wird sichergestellt, dass die nachfolgenden Argumente den richtigen Typ aufweisen, um mit den verwendeten Format bezeichnerwerten zu vergleichen.

## <a name="format-specifiers-for-printf"></a>Formatspezifizierer für`printf`

Formatspezifikationen für `printf` Formate sind Zeichen folgen mit `%` Markierungen, die das Format angeben. Format Platzhalter bestehen aus der `%[flags][width][.precision][type]` Art, in der der Typ wie folgt interpretiert wird:

| Formatbezeichner   | Typ (e)        | Bemerkungen                      |
|:-------------------|:---------------|:-----------------------------|
| `%b`               | bool      | Formatiert als `true` oder`false`                |
| `%s`               | Zeichenfolge    | Formatiert als Inhalt ohne Escapezeichen         |
| `%c`               | char      | Formatiert als Zeichenliteral  |
| `%d`, `%i`         | ein einfacher ganzzahliger Typ | Formatiert als ganze Dezimalzahl, signiert, wenn der grundlegende ganzzahlige Typ signiert ist. |
| `%u`               | ein einfacher ganzzahliger Typ | Formatiert als ganze Dezimalzahl ohne Vorzeichen   |
| `%x`, `%X`         | ein einfacher ganzzahliger Typ | Formatiert als hexadezimal Zahl ohne Vorzeichen (a-f oder a-f für Hex-Ziffern)  |
|  `%o`              | ein einfacher ganzzahliger Typ | Formatiert als oktale Zahl ohne Vorzeichen |
| `%e`, `%E`         | ein Basistyp für Gleit Komma Zahlen | Wird als Wert mit Vorzeichen formatiert, wobei das Format `[-]d.dddde[sign]ddd` d eine einfache Dezimalzahl ist, dddd eine oder mehrere Dezimalstellen, DDD genau drei Dezimalstellen und Vorzeichen `+` oder`-` |
| `%f`               | ein Basistyp für Gleit Komma Zahlen | Wird als signierter Wert mit dem Format formatiert `[-]dddd.dddd` , wobei `dddd` eine oder mehrere Dezimalstellen sind. Die Anzahl der Ziffern vor dem Dezimaltrennzeichen ist abhängig von der Größe der Zahl, und die Anzahl der Ziffern nach dem Dezimaltrennzeichen ist abhängig von der angeforderten Genauigkeit. |
| `%g`, `%G` | ein Basistyp für Gleit Komma Zahlen |  Formatiert mithilfe von als Wert mit Vorzeichen `%f` im `%e` Format oder, je nachdem, welcher Wert für den angegebenen Wert und die Genauigkeit kompakter ist. |
| `%M` | ein- `System.Decimal` Wert  |    Formatiert mit dem Format Bezeichner `"G"` für`System.Decimal.ToString(format)` |
| `%O` | beliebiger Wert  |   Formatiert durch Boxing des-Objekts und Aufrufen seiner- `System.Object.ToString()` Methode. |
| `%A` | beliebiger Wert  |   Formatiert mit [strukturierter Klartext-Formatierung](plaintext-formatting.md) mit den Standardlayouteinstellungen |
| `%a` | beliebiger Wert  |   Erfordert zwei Argumente: eine Formatierungsfunktion, die einen Kontext Parameter und den Wert akzeptiert, und den zu Druck Ende Wert. |
| `%t` | beliebiger Wert  |   Erfordert ein Argument: eine Formatierungsfunktion, die einen Kontext Parameter annimmt, der den entsprechenden Text entweder ausgibt oder zurückgibt. |

Einfache ganzzahlige Typen sind `byte` ( `System.Byte` ), `sbyte` ( `System.SByte` ), `int16` ( `System.Int16` ), `uint16` ( `System.UInt16` ), `int32` ( `System.Int32` ), (), `uint32` `System.UInt32` `int64` ( `System.Int64` ), `uint64` ( `System.UInt64` ), `nativeint` ( `System.IntPtr` ) und `unativeint` ( `System.UIntPtr` ).
Grundlegende Gleit Komma Typen sind `float` ( `System.Double` ) und `float32` ( `System.Single` ).

Die optionale Breite ist eine ganze Zahl, die die minimale Breite des Ergebnisses angibt. Gibt beispielsweise `%6d` eine ganze Zahl aus, die Leerzeichen vorangestellt ist, um mindestens sechs Zeichen auszufüllen. Wenn Width `*` gleich ist, wird ein zusätzliches ganzzahliges Argument zum Angeben der entsprechenden Breite verwendet.

Gültige Flags sind:

| Flag   | Wirkung        | Bemerkungen                      |
|:-------------------|:---------------|:-----------------------------|
| `0`  | Fügen Sie Nullen anstelle von Leerzeichen hinzu, um die erforderliche Breite zu bilden. |    |
| `-` |  Linksbündig das Ergebnis innerhalb der angegebenen Breite begründen |   |
| `+`  | Fügen Sie ein `+` Zeichen hinzu, wenn die Zahl positiv ist (um einem `-` Vorzeichen für negatives zu entsprechen). |   |
| Leerzeichen | Zusätzlichen Speicherplatz hinzufügen, wenn die Zahl positiv ist (um ein "-"-Zeichen für negative Entsprechung zu finden) |

Das printf `#` -Flag ist ungültig, und es wird ein Kompilierzeitfehler gemeldet, wenn es verwendet wird.

Werte werden mithilfe der invarianten Kultur formatiert. Kultur Einstellungen sind für `printf` die Formatierung unerheblich, es sei denn, Sie wirken sich auf die Ergebnisse der Formatierung `%O` und aus `%A` . Weitere Informationen finden Sie unter [strukturierte Klartext-Formatierung](plaintext-formatting.md).

## <a name="a-formatting"></a>`%A`ert

Der `%A` Format Bezeichner wird verwendet, um Werte auf lesbare Weise zu formatieren, und kann auch hilfreich sein, um Diagnoseinformationen zu melden.

### <a name="primitive-values"></a>Primitive Werte

Beim Formatieren von Klartext mit dem `%A` Spezifizierer werden numerische F #-Werte mit Ihrem Suffix und der invarianten Kultur formatiert. Gleit Komma Werte werden mithilfe von 10 Stellen der Gleit Komma Genauigkeit formatiert. Ein auf ein Objekt angewendeter

```fsharp
printfn "%A" (1L, 3n, 5u, 7, 4.03f, 5.000000001, 5.0000000001)
```

Ergebnissen

```console
(1L, 3n, 5u, 7, 4.03000021f, 5.000000001, 5.0)
```

Wenn Sie den- `%A` Spezifizierer verwenden, werden Zeichen folgen mit Anführungszeichen formatiert. Escapecodes werden nicht hinzugefügt, und stattdessen werden die Rohzeichen gedruckt. Ein auf ein Objekt angewendeter

```fsharp
printfn "%A" ("abc", "a\tb\nc\"d")

```

Ergebnissen

```console
("abc", "a      b
c"d")
```

### <a name="net-values"></a>.Net-Werte

Beim Formatieren von nur-Text mit dem `%A` -Spezifizierer werden nicht-F #-.NET-Objekte mithilfe `x.ToString()` der Standardeinstellungen von .net formatiert, die von und angegeben werden `System.Globalization.CultureInfo.CurrentCulture` `System.Globalization.CultureInfo.CurrentUICulture` .  Ein auf ein Objekt angewendeter

```fsharp
open System.Globalization

let date = System.DateTime(1999, 12, 31)

CultureInfo.CurrentCulture <- CultureInfo.GetCultureInfo("de-DE")
printfn "Culture 1: %A" date

CultureInfo.CurrentCulture <- CultureInfo.GetCultureInfo("en-US")
printfn "Culture 2: %A" date
```

Ergebnissen

```console
Culture 1: 31.12.1999 00:00:00
Culture 2: 12/31/1999 12:00:00 AM
```

### <a name="structured-values"></a>Strukturierte Werte

Beim Formatieren von nur-Text mit dem- `%A` Spezifizierer wird der Block Einzug für F #-Listen und-Tupel verwendet. Dies wird im vorherigen Beispiel gezeigt.
Die Struktur von Arrays wird ebenfalls verwendet, einschließlich mehrdimensionaler Arrays.  Eindimensionale Arrays werden mit Syntax angezeigt `[| ... |]` . Ein auf ein Objekt angewendeter

```fsharp
printfn "%A" [| for i in 1 .. 20 -> (i, i*i) |]
```

Ergebnissen

```console
[|(1, 1); (2, 4); (3, 9); (4, 16); (5, 25); (6, 36); (7, 49); (8, 64); (9, 81);
  (10, 100); (11, 121); (12, 144); (13, 169); (14, 196); (15, 225); (16, 256);
  (17, 289); (18, 324); (19, 361); (20, 400)|]
```

Die Standarddruck Breite ist 80.  Diese Breite kann mit einer Druckbreite im Format Bezeichner angepasst werden. Ein auf ein Objekt angewendeter

```fsharp
printfn "%10A" [| for i in 1 .. 5 -> (i, i*i) |]

printfn "%20A" [| for i in 1 .. 5 -> (i, i*i) |]

printfn "%50A" [| for i in 1 .. 5 -> (i, i*i) |]
```

Ergebnissen

```console
[|(1, 1);
  (2, 4);
  (3, 9);
  (4, 16);
  (5, 25)|]
[|(1, 1); (2, 4);
  (3, 9); (4, 16);
  (5, 25)|]
[|(1, 1); (2, 4); (3, 9); (4, 16); (5, 25)|]
```

Wenn eine Druckbreite von 0 angegeben wird, wird keine Druckbreite verwendet. Eine einzelne Textzeile wird angezeigt, außer wenn eingebettete Zeichen folgen in der Ausgabezeilen Umbrüche enthalten.  Beispiel:

```fsharp
printfn "%0A" [| for i in 1 .. 5 -> (i, i*i) |]

printfn "%0A" [| for i in 1 .. 5 -> "abc\ndef" |]
```

Ergebnissen

```console
[|(1, 1); (2, 4); (3, 9); (4, 16); (5, 25)|]
[|"abc
def"; "abc
def"; "abc
def"; "abc
def"; "abc
def"|]
```

Ein tiefen Limit von 4 wird für Sequenzwerte ( `IEnumerable` ) verwendet, die als angezeigt werden `seq { ...}` . Für Listen-und Array Werte wird eine Tiefe Grenze von 100 verwendet.
Ein auf ein Objekt angewendeter

```fsharp
printfn "%A" (seq { for i in 1 .. 10 -> (i, i*i) })
```

Ergebnissen

```console
seq [(1, 1); (2, 4); (3, 9); (4, 16); ...]
```

Der Block Einzug wird auch für die Struktur öffentlicher Daten Satz-und Union-Werte verwendet. Ein auf ein Objekt angewendeter

```fsharp
type R = { X : int list; Y : string list }

printfn "%A" { X =  [ 1;2;3 ]; Y = ["one"; "two"; "three"] }
```

Ergebnissen

```console
{ X = [1; 2; 3]
  Y = ["one"; "two"; "three"] }
```

Wenn `%+A` verwendet wird, wird die private Struktur von Datensätzen und Unions auch mithilfe von Reflektion offengelegt. Beispiel:

```fsharp
type internal R =
    { X : int list; Y : string list }
    override _.ToString() = "R"

let internal data = { X = [ 1;2;3 ]; Y = ["one"; "two"; "three"] }

printfn "external view:\n%A" data

printfn "internal view:\n%+A" data

```

Ergebnissen

```console
external view:
R

internal view:
{ X = [1; 2; 3]
  Y = ["one"; "two"; "three"] }
```

### <a name="large-cyclic-or-deeply-nested-values"></a>Große, zyklische oder tief geschachtelte Werte

Große strukturierte Werte werden mit einer maximalen Gesamtzahl von Objekt Knoten von 10000 formatiert.
Tief geschachtelte Werte werden mit einer Tiefe von 100 formatiert.  In beiden Fällen `...` wird verwendet, um einen Teil der Ausgabe zu entfernen.  Ein auf ein Objekt angewendeter

```fsharp
type Tree =
    | Tip
    | Node of Tree * Tree

let rec make n =
    if n = 0 then
        Tip
    else
        Node(Tip, make (n-1))

printfn "%A" (make 1000)
```

erzeugt eine große Ausgabe mit einigen Teilen:

```console
Node(Tip, Node(Tip, ....Node (..., ...)...))
```

Zyklen werden in den Objekt Diagrammen erkannt und `...` an Stellen verwendet, an denen Zyklen erkannt werden. Beispiel:

```fsharp
type R = { mutable Links: R list }
let r = { Links = [] }
r.Links <- [r]
printfn "%A" r
```

Ergebnissen

```console
{ Links = [...] }
```

### <a name="lazy-null-and-function-values"></a>Werte für Lazy, NULL und Function

Verzögerte Werte werden als `Value is not created` oder entsprechender Text gedruckt, wenn der Wert noch nicht ausgewertet wurde.

NULL-Werte werden als gedruckt `null` , es sei denn, der statische Typ des Werts wird als Union-Typ festgelegt, wobei `null` eine zugelassene Darstellung ist.

F #-Funktions Werte werden als Ihr intern generierter Schließungs Name gedruckt, z `<fun:it@43-7>` . b..

### <a name="customize-plain-text-formatting-with-structuredformatdisplay"></a>Anpassen der nur-Text-Formatierung mit`StructuredFormatDisplay`

Wenn Sie den- `%A` Spezifizierer verwenden, wird das vorhanden sein des- `StructuredFormatDisplay` Attributs für Typdeklarationen beachtet.  Dies kann verwendet werden, um den Ersatztext und die Eigenschaft anzugeben, um einen Wert anzuzeigen. Beispiel:

```fsharp
[<StructuredFormatDisplay("Counts({Clicks})")>]
type Counts = { Clicks:int list}

printfn "%20A" {Clicks=[0..20]}
```

Ergebnissen

```console
Counts([0; 1; 2; 3;
        4; 5; 6; 7;
        8; 9; 10; 11;
        12; 13; 14;
        15; 16; 17;
        18; 19; 20])
```

### <a name="customize-plain-text-formatting-by-overriding-tostring"></a>Einfache Textformatierung durch Überschreiben anpassen`ToString`

Die Standard Implementierung von `ToString` ist in der F #-Programmierung Observable. Häufig sind die Standard Ergebnisse nicht für die Verwendung in der programmierseitigen Informationsanzeige oder bei der Benutzer Ausgabe geeignet. Folglich ist es üblich, die Standard Implementierung zu überschreiben.  

Standardmäßig überschreiben F #-Datensatz-und Union-Typen die Implementierung von `ToString` mit einer-Implementierung, die verwendet `sprintf "%+A"` .  Ein auf ein Objekt angewendeter

```fsharp
type Counts = { Clicks:int list }

printfn "%s" ({Clicks=[0..10]}.ToString())
```

Ergebnissen

```console
{ Clicks = [0; 1; 2; 3; 4; 5; 6; 7; 8; 9; 10] }
```

Bei Klassentypen wird keine Standard Implementierung von `ToString` bereitgestellt, und der .NET-Standard wird verwendet, der den Namen des Typs meldet. Ein auf ein Objekt angewendeter

```fsharp
type MyClassType(clicks: int list) =
   member _.Clicks = clicks

let data = [ MyClassType([1..5]); MyClassType([1..5]) ]
printfn "Default structured print gives this:\n%A" data
printfn "Default ToString gives:\n%s" (data.ToString())
```

Ergebnissen

```console
Default structured print gives this:
[MyClassType; MyClassType]
Default ToString gives:
[MyClassType; MyClassType]
```

Das Hinzufügen einer außer Kraft setzung für `ToString` kann eine bessere Formatierung bieten.

```fsharp
type MyClassType(clicks: int list) =
   member _.Clicks = clicks
   override _.ToString() = sprintf "MyClassType(%0A)" clicks

let data = [ MyClassType([1..5]); MyClassType([1..5]) ]
printfn "Now structured print gives this:\n%A" data
printfn "Now ToString gives:\n%s" (data.ToString())
```

Ergebnissen

```console
Now structured print gives this:
[MyClassType([1; 2; 3; 4; 5]); MyClassType([1; 2; 3; 4; 5])]
Now ToString gives:
[MyClassType([1; 2; 3; 4; 5]); MyClassType([1; 2; 3; 4; 5])]
```

## <a name="f-interactive-structured-printing"></a>F# Interactive strukturierter Druck

F# Interactive ( `dotnet fsi` ) verwendet eine erweiterte Version der strukturierten Klartext-Formatierung, um Werte zu melden, und ermöglicht zusätzliche Anpassungsmöglichkeiten. Weitere Informationen finden Sie unter [F# Interactive](fsharp-interactive-options.md).

## <a name="customize-debug-displays"></a>Anpassen der debuganzeige

Debugger für .net berücksichtigen die Verwendung von Attributen, wie z `DebuggerDisplay` `DebuggerTypeProxy` . b. und, und diese beeinflussen die strukturierte Anzeige von Objekten in debuggerinspektions-Fenstern.
Der F #-Compiler hat diese Attribute automatisch für Unterscheidungs-Union-und Daten Satz Typen generiert, aber nicht für Klassen-, Schnittstellen-oder Strukturtypen.

Diese Attribute werden bei der Klartext-Formatierung in F # ignoriert, aber es kann nützlich sein, diese Methoden zu implementieren, um die Anzeige beim Debuggen von F #-Typen zu verbessern

## <a name="see-also"></a>Siehe auch

- [Zeichenfolgen](strings.md)
- [Best](records.md)
- [Unterscheidungs-Unions](discriminated-unions.md)
- [F# Interactive](fsharp-interactive-options.md)
