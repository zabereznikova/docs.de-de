---
title: Neuerungen in C# 9.0 – C#-Leitfaden
description: Überblick über die neuen Features von C# 9.0
ms.date: 09/04/2020
ms.openlocfilehash: a8b66d21514b57d8bee3ff54b2a707af391fe7a9
ms.sourcegitcommit: a8730298170b8d96b4272e0c3dfc9819c606947b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2020
ms.locfileid: "90738722"
---
# <a name="whats-new-in-c-90"></a>Neuerungen in C# 9.0

Mit Version 9.0 wird die Sprache C# um die folgenden Features und Verbesserungen erweitert:

- Datensätze
- init-only-Setter
- Top-Level-Anweisungen
- Verbesserungen am Musterabgleich:
- Integerwerte mit nativer Größe
- Funktionszeiger
- Unterdrücken der Ausgabe des Flags „localsinit“
- Zieltypisierte neue Ausdrücke
- Statische anonyme Funktionen
- Bedingter Ausdruck mit Zieltyp
- Kovariante Rückgabetypen
- Unterstützung für die Erweiterung `GetEnumerator` in `foreach`-Schleifen
- Parameter zum Verwerfen von Lambdafunktion
- Attribute in lokalen Funktionen
- Modulinitialisierer
- Neue Features für partielle Methoden

C# 9.0 wird in **.NET 5** unterstützt. Weitere Informationen finden Sie unter [C#-Sprachversionsverwaltung](../language-reference/configure-language-version.md).

## <a name="record-types"></a>Eintragstypen

In C# 9.0 werden ***Datensatztypen*** eingeführt. Hierbei handelt es sich um einen Verweistyp, der synthetisierte Methoden bereitstellt, die mithilfe von Wertsemantik Gleichheitsbeziehungen herstellen. Datensätze sind immer unveränderbar.

Sie vereinfachen die Erstellung von unveränderbaren Verweistypen in .NET. In der Vergangenheit wurden .NET-Typen größtenteils als Verweistypen (einschließlich Klassen und anonyme Typen) und Werttypen (einschließlich Strukturen und Tupeln) klassifiziert. Obwohl unveränderbare Werttypen empfohlen werden, führen veränderbare Werttypen nur selten zu Fehlern. Werttypvariablen speichern Werte, sodass Änderungen an einer Kopie der ursprünglichen Daten vorgenommen werden, wenn Werttypen an Methoden übergeben werden.

Auch unveränderbare Verweistypen weisen viele Vorteile auf. Diese kommen vor allem in gleichzeitig ausgeführten Programmen mit freigegebenen Daten zum Tragen. Bisher mussten Entwickler in C# immer etwas zusätzlichen Code schreiben, um unveränderbare Verweistypen zu erstellen. Dank der Datensätze gibt es nun eine Typdeklaration für unveränderbare Verweistypen, die Gleichheit mithilfe von Wertsemantik herstellt. Für die synthetisierten Methoden, die Gleichheitsbeziehungen und Hashcodes generieren, gelten zwei Datensätze als gleich, wenn alle ihre Eigenschaften übereinstimmen. Sehen Sie sich folgende Definition an:

:::code language="csharp" source="snippets/whats-new-csharp9/RecordsExamples.cs" ID="RecordDefinition":::

Diese Datensatzdefinition erstellt den Typ `Person`, der zwei schreibgeschützte Eigenschaften aufweist: `FirstName` und `LastName`. Bei dem Typ `Person` handelt es sich um einen Verweistyp. Wenn Sie sich die Zwischensprache (Intermediate Language, IL) ansehen, handelt es sich um eine Klasse. Der Typ ist insofern unveränderbar, als dass keine seiner Eigenschaften nach seiner Erstellung geändert werden kann. Wenn Sie einen Datensatztyp definieren, synthetisiert der Compiler verschiedene weitere Methoden für Sie:

- Methoden für wertbasierte Gleichheitsvergleiche
- Überschreibungen für <xref:System.Object.GetHashCode>
- Methoden zum Kopieren und Klonen von Membern
- `PrintMembers` und <xref:System.Object.ToString>
- `Deconstruct`-Methode

Datensätze unterstützen die Vererbung. Ein neuer, von `Person` abgeleiteter Datensatz wird wie folgt deklariert:

:::code language="csharp" source="snippets/whats-new-csharp9/RecordsExamples.cs" ID="InheritedRecord":::

Sie können Datensätze auch versiegeln, um eine weitere Ableitung zu verhindern:

:::code language="csharp" source="snippets/whats-new-csharp9/RecordsExamples.cs" ID="SealedRecord":::

Der Compiler synthetisiert verschiedene Versionen der oben genannten Methoden. Die Methodensignaturen hängen davon ab, ob der Datensatztyp versiegelt ist und ob die direkte Basisklasse „object“ lautet. Datensätze sollten die folgenden Funktionen aufweisen:

- Die Gleichheit ist wertbasiert, und der Datensatz verfügt über eine Überprüfung, die sicherstellt, dass die Typen übereinstimmen. `Student` kann beispielsweise nicht gleich `Person` sein, obwohl beide Datensätze denselben Namen enthalten.
- Für Datensätze wird eine konsistente Zeichenfolgendarstellung für Sie generiert.
- Datensätze unterstützen die Erstellung von Kopien. Bei einer ordnungsgemäßen Erstellung von Kopien müssen Vererbungshierarchien und von Entwicklern hinzugefügte Eigenschaften berücksichtigt werden.
- Datensätze können mit Änderungen kopiert werden. Diese Kopier- und Änderungsvorgänge unterstützen nicht-destruktive Bearbeitungen.
- Alle Datensätze unterstützen die Dekonstruktion.

Zusätzlich zu den bekannten `Equals`-Überladungen, dem `operator ==` sowie dem `operator !=` synthetisiert der Compiler eine neue `EqualityContract`-Eigenschaft. Die Eigenschaft gibt ein `Type`-Objekt zurück, das mit dem Typ des Datensatzes übereinstimmt. Wenn der Basistyp `object` entspricht, lautet die Eigenschaft `virtual`. Wenn der Basistyp einem anderen Datensatztyp entspricht, lautet die Eigenschaft `override`. Wenn der Datensatztyp `sealed` entspricht, lautet die Eigenschaft `sealed`. Die synthetisierte `GetHashCode`-Methode verwendet die `GetHashCode`-Methode aus allen Eigenschaften und Feldern, die im Basis- und im Datensatztyp deklariert wurden. Diese synthetisierten Methoden erzwingen wertbasierte Gleichheitsbeziehungen für eine gesamte Vererbungshierarchie. Dies bedeutet, dass `Student` niemals als identisch mit `Person` gilt, wenn beide den gleichen Namen enthalten. Die Typen sowie auch alle Eigenschaften müssen ebenfalls übereinstimmen, wenn Datensatztypen als gleich gelten sollen.

Datensätze verfügen außerdem über einen synthetisierten Konstruktor und eine „Klonmethode“ zum Erstellen von Kopien. Der synthetisierte Konstruktor verfügt über ein Argument des Datensatztyps. Er generiert einen neuen Datensatz, der für alle Eigenschaften dieselben Werte wie der alte aufweist. Dieser Konstruktor ist privat, wenn der Datensatz versiegelt ist. Andernfalls ist er geschützt. Die synthetisierte „Klonmethode“ unterstützt die Kopieerstellung für Datensatzhierarchien. Der Begriff „klonen“ ist in Anführungszeichen gesetzt, weil der tatsächliche Name vom Compiler generiert wird. Es ist nicht möglich, eine Methode namens `Clone` in einem Datensatztyp zu erstellen. Die synthetisierte „Klonmethode“ gibt den Datensatztyp zurück, der mithilfe der virtuellen Bindung kopiert wird. Der Compiler fügt der „Klonmethode“ je nach Zugriffsmodifizierer des Datensatzes (`record`) verschiedene Modifizierer hinzu:

- Wenn der Datensatztyp `abstract` ist, ist auch die „Klonmethode“ `abstract`. Wenn der Basistyp nicht `object` entspricht, ist die Methode ebenfalls `override`.
- Für Datensatztypen, die nicht `abstract` sind, wenn der Basistyp `object` lautet, gilt:
  - Wenn der Datensatz `sealed` ist, werden der „Klonmethode“ keine weiteren Modifizierer hinzugefügt (was bedeutet, dass sie nicht `virtual` ist).
  - Wenn der Datensatztyp nicht `sealed` ist, ist die „Klonmethode“ `virtual`.
- Für Datensatztypen, die nicht `abstract` sind, wenn der Basistyp nicht `object` lautet, gilt:
  - Wenn der Datensatz `sealed` ist, ist auch die „Klonmethode“ `sealed`.
  - Wenn der Datensatztyp nicht `sealed` ist, ist die „Klonmethode“ `override`.

Diese Regeln führen dazu, dass Gleichheit in jeder Hierarchie von Datensatztypen konsistent implementiert wird. Zwei Datensätze sind gleich, wenn ihre Eigenschaften gleich sind und ihre Typen übereinstimmen. Dies wird im folgenden Beispiel veranschaulicht:

:::code language="csharp" source="snippets/whats-new-csharp9/RecordsExamples.cs" ID="RecordsEquality":::

Der Compiler synthetisiert zwei Methoden, die eine Druck- oder Bildschirmausgabe unterstützen: eine <xref:System.Object.ToString>-Überschreibung und die Methode `PrintMembers`. `PrintMembers` nimmt <xref:System.Text.StringBuilder?displayProperty=nameWithType> als Argument. Die Methode fügt eine durch Trennzeichen getrennte Liste von Eigenschaftsnamen und -werten für alle Eigenschaften im Datensatztyp an. `PrintMembers` ruft die Basisimplementierung aller Datensätze ab, die von anderen Datensätzen abgeleitet wurden. Die <xref:System.Object.ToString>-Überschreibung gibt die Zeichenfolge in geschweiften Klammern (`{` und `}`) zurück, die von `PrintMembers` erzeugt wurde. Die Methode <xref:System.Object.ToString> für `Student` gibt beispielsweise eine Zeichenfolge (`string`) wie im folgenden Beispielcode zurück:

```csharp
"Student { LastName = Wagner, FirstName = Bill, Level = 11 }"
```

In den bisher gezeigten Beispielen wird eine herkömmliche Syntax für die Deklaration von Eigenschaften verwendet. Es gibt eine prägnantere Lösung namens ***positionelle Datensätze***.  Nachstehend finden Sie die drei Datensatztypen, die zuvor als positionelle Datensätze definiert wurden:

:::code language="csharp" source="snippets/whats-new-csharp9/PositionalRecords.cs" ID="PositionalRecords":::

Diese Deklarationen erstellen die gleiche Funktionalität wie die frühere Version (mit einigen zusätzlichen Features, die im folgenden Abschnitt behandelt werden). Diese Deklarationen enden mit einem Semikolon anstelle von Klammern, da diese Datensätze keine zusätzlichen Methoden hinzufügen. Sie können einen Körper und beliebige zusätzliche Methoden einfügen:

:::code language="csharp" source="snippets/whats-new-csharp9/PositionalRecords.cs" ID="RecordsWithMethods":::

Der Compiler erstellt eine `Deconstruct`-Methode für positionelle Datensätze. Die `Deconstruct`-Methode verfügt über Parameter, die mit den Namen aller öffentlichen Eigenschaften im Datensatztyp übereinstimmen. Mithilfe der `Deconstruct`-Methode kann der Datensatz in seine Komponenteneigenschaften dekonstruiert werden:

:::code language="csharp" source="snippets/whats-new-csharp9/PositionalRecords.cs" ID="DeconstructRecord":::

Datensätze unterstützen auch ***with-Ausdrücke***. Ein ***with-Ausdruck*** weist den Compiler an, eine Kopie eines Datensatzes *mit* (engl.: „with“) bestimmten geänderten Eigenschaften zu erstellen:

:::code language="csharp" source="snippets/whats-new-csharp9/PositionalRecords.cs" ID="Wither":::

In der obigen Zeile wird ein neuer `Person`-Datensatz erstellt, bei dem die `LastName`-Eigenschaft eine Kopie von `person` ist und `FirstName` „Paul“ entspricht. Sie können in with-Ausdrücken eine beliebige Anzahl von Eigenschaften festlegen.  Jeder dieser synthetisierten Member, außer der „Klonmethode“, kann von Ihnen selbst geschrieben werden. Wenn ein Datensatztyp über eine Methode verfügt, die mit der Signatur einer beliebigen synthetisierten Methode übereinstimmt, wird diese Methode vom Compiler nicht synthetisiert. Der zuvor verwendete Beispieldatensatz `Dog` enthält eine manuell geschriebene <xref:System.String.ToString>-Methode als Beispiel.

## <a name="init-only-setters"></a>init-only-Setter

***Nur-init-Setter*** bieten eine konsistente Syntax zum Initialisieren von Objektmembern. Eigenschafteninitialisierer verdeutlichen, welcher Wert welche Eigenschaft festlegt. Der Nachteil ist, dass diese Eigenschaften festlegbar sein müssen. Ab C# 9.0 können Sie `init`-Zugriffsmethoden anstelle von `set`-Zugriffsmethoden für Eigenschaften und Indexer erstellen. Aufrufer können diese Werte mithilfe der Syntax von Eigenschafteninitialisierern in Erstellungsausdrücken festlegen. Diese Eigenschaften sind jedoch nach Abschluss der Erstellung schreibgeschützt. Nur-init-Setter bieten Ihnen die Möglichkeit, den Zustand innerhalb eines bestimmten Zeitfensters zu ändern. Dieses Zeitfenster schließt sich nach Abschluss der Konstruktionsphase. Die Konstruktionsphase endet effektiv, nachdem die gesamte Initialisierung, einschließlich aller Eigenschafteninitialisierer und with-Ausdrücke, abgeschlossen wurde.

Im vorherigen Beispiel für positionelle Datensätze wurde veranschaulicht, wie eine Eigenschaft mithilfe eines Nur-init-Setters in einem with-Ausdruck festgelegt wird. Sie können Nur-init-Setter in einem jedem Typ deklarieren, den Sie schreiben. Die folgende Struktur definiert z. B. eine Struktur zur Wetterbeobachtung:

:::code language="csharp" source="snippets/whats-new-csharp9/WeatherObservation.cs" ID="DeclareWeatherObservation":::

Aufrufer können die Werte mithilfe der Syntax von Eigenschafteninitialisierern festlegen und gleichzeitig die Unveränderlichkeit wahren:

:::code language="csharp" source="snippets/whats-new-csharp9/WeatherObservation.cs" ID="UseWeatherObservation":::

Die Änderung einer Beobachtung nach der Initialisierung führt jedoch zu einem Fehler, da eine Nur-init-Eigenschaft außerhalb der Initialisierung zugewiesen wird:

```csharp
// Error! CS8852.
now.TemperatureInCelsius = 18;
```

Nur-init-Setter können nützlich sein, um Basisklasseneigenschaften von abgeleiteten Klassen festzulegen. Sie können auch mithilfe von Hilfsprogrammen abgeleitete Eigenschaften in einer Basisklasse festlegen. Positionelle Datensätze deklarieren Eigenschaften mithilfe von Nur-init-Settern. Diese Setter werden in with-Ausdrücken verwendet. Sie können Nur-init-Setter für alle Klassen (`class`) oder Strukturen (`struct`) deklarieren, die Sie definieren.

## <a name="top-level-statements"></a>Top-Level-Anweisungen

Mithilfe von ***allgemeinen Anweisungen*** lässt sich der Code in vielen Anwendungen stark verkürzen. Dies ist das kanonische Hallo-Welt-Programm („Hello World“):

```csharp
using System;

namespace HelloWorld
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Hello World!");
        }
    }
}
```

Nur eine der Codezeilen ruft eine Aktion hervor. Mit allgemeinen Anweisungen können Sie all diese Codebausteine durch die `using`-Anweisung und die eine Zeile ersetzen, die die Aktion verursacht:

:::code language="csharp" source="snippets/whats-new-csharp9/Program.cs" ID="TopLevelStatements":::

Wenn Sie ein einzeiliges Programm schreiben möchten, können Sie die `using`-Anweisung auch entfernen und den vollqualifizierten Typnamen verwenden:

```csharp
System.Console.WriteLine("Hello World!");
```

Allgemeine Anweisungen dürfen nur einer Anwendungsdatei eingesetzt werden. Wenn der Compiler in mehreren Quelldateien allgemeine Anweisungen findet, führt dies zu einem Fehler. Ein Fehler wird ebenfalls zurückgegeben, wenn Sie allgemeine Anweisungen mit einer deklarierten Einstiegspunktmethode des Programms kombinieren (in der Regel eine `Main`-Methode). Sie können sich dies vorstellen, als ob eine Datei die Anweisungen enthält, die normalerweise in die `Main`-Methode einer `Program`-Klasse geschrieben werden.  

Einer der häufigsten Anwendungsfälle für dieses Feature ist die Erstellung von Lehrmaterial. Angehende C#-Entwickler können die kanonische Hallo-Welt-Anwendung in einer oder zwei Codezeilen schreiben. Keiner der zusätzlichen Codebausteine ist erforderlich. Aber auch erfahrene Entwickler werden viele Verwendungsmöglichkeiten für dieses Feature finden. Allgemeine Anweisungen bieten skriptähnliche Experimentierfunktionen, ähnlich wie Jupyter Notebook-Instanzen. Allgemeine Anweisungen eignen sich auch hervorragend für kleine Konsolenprogramme und Hilfsprogramme. Azure-Funktionen sind ein idealer Anwendungsfall für allgemeine Anweisungen.

Vor allem schränken allgemeine Anweisungen weder den Umfang noch die Komplexität einer Anwendung ein. Diese Anweisungen können auf jede beliebige .NET-Klasse zugreifen oder diese verwenden. Außerdem schränken sie nicht die Verwendung von Befehlszeilenargumenten oder Rückgabewerten ein. Allgemeine Anweisungen können auf ein Zeichenfolgenarray namens „args“ zugreifen. Wenn allgemeine Anweisungen einen ganzzahligen Wert zurückgeben, wird dieser Wert zum ganzzahligen Rückgabecode einer synthetisierten `Main`-Methode. Allgemeine Anweisungen können async-Ausdrücke enthalten. In diesem Fall gibt der synthetisierte Einstiegspunkt `Task` oder `Task<int>` zurück.

## <a name="pattern-matching-enhancements"></a>Verbesserungen am Musterabgleich:

C# 9 enthält neue Verbesserungen am Musterabgleich:

- ***Typmuster*** gleichen eine Variable mit einem Typ ab.
- ***In Klammern gesetzte Muster*** erzwingen den Vorrang von Musterkombinationen oder heben diesen hervor.
- In ***konjunktiven `and`-Mustern*** müssen beide Muster übereinstimmen.
- In ***disjunktiven `or`-Mustern*** muss eines von beiden Mustern übereinstimmen.
- In ***negierten `not`-Mustern*** darf ein Muster nicht übereinstimmen.
- In ***relationalen Mustern*** muss die Eingabe kleiner als, größer als, kleiner gleich oder größer gleich einer angegebenen Konstante sein.

Diese Muster erweitern die Mustersyntax. Sehen Sie sich die folgenden Beispiele an:

:::code language="csharp" source="snippets/whats-new-csharp9/PatternUtilities.cs" ID="IsLetterPattern":::

Dies ist eine alternative Schreibweise mit optionalen Klammern, die verdeutlichen, dass `and` Vorrang vor `or` hat:

:::code language="csharp" source="snippets/whats-new-csharp9/PatternUtilities.cs" ID="IsLetterOrSeparatorPattern":::

Einer der gängigsten Anwendungsfälle ist eine neue Syntax für NULL-Überprüfungen:

```csharp
if (e is not null)
{
    // ...
}
```

Jedes dieser Muster kann in jedem Kontext verwendet werden, in dem Muster zulässig sind: `is`-Musterausdrücke, `switch`-Ausdrücke, geschachtelte Muster und das Muster einer `case`-Bezeichnung einer `switch`-Anweisung.

## <a name="performance-and-interop"></a>Leistung und Interop

Diese drei neuen Features verbessern die Unterstützung für die native Interop und spezifische Bibliotheken, die eine hohe Leistung erfordern: ganze Zahlen mit nativer Größe, Funktionszeiger und das Auslassen des `localsinit`-Flags.

Ganze Zahlen mit nativer Größe, `nint` und `nuint`, sind ganzzahlige Typen. Sie werden durch die zugrunde liegenden Typen <xref:System.IntPtr?displayProperty=nameWithType> und <xref:System.UIntPtr?displayProperty=nameWithType> ausgedrückt. Der Compiler gibt zusätzliche Konvertierungen und Vorgänge für diese Typen als native ganze Zahlen aus. Ganze Zahlen mit nativer Größe haben keine Konstanten für `MaxValue` oder `MinValue`, mit Ausnahme von `nuint.MinValue`. Hier entspricht `MinValue` dem Wert `0`. Andere Werte können nicht als Konstanten ausgedrückt werden, da sie von der nativen Größe einer ganzen Zahl auf dem Zielcomputer abhängen. Konstantenwerte können für `nint` in folgendem Bereich verwendet werden: [`int.MinValue` ... `int.MaxValue`]. Konstantenwerte können für `nuint` in folgendem Bereich verwendet werden: [`uint.MinValue` ... `uint.MaxValue`]. Der Compiler führt eine konstante Faltung aller unären und binären Operatoren mithilfe der Typen <xref:System.Int32?displayProperty=nameWithType> und <xref:System.UInt32?displayProperty=nameWithType> durch. Wenn das Ergebnis nicht in 32 Bit passt, wird der Vorgang zur Laufzeit ausgeführt und nicht als Konstante angesehen. Ganze Zahlen mit nativer Größe können die Leistung in Szenarios steigern, in denen ganzzahlige Mathematik intensiv angewendet und die schnellstmögliche Leistung benötigt wird.

Funktionszeiger bieten eine einfache Syntax für den Zugriff auf die IL-Opcodes `ldftn` und `calli`. Sie können Funktionszeiger mithilfe der neuen `delegate*`-Syntax deklarieren. Ein `delegate*`-Typ ist ein Typ von Zeiger. Bei einem Aufruf des `delegate*`-Typs wird `calli` verwendet. Dies ist ein Unterschied zu einem Delegaten, der `callvirt` für die `Invoke()`-Methode verwendet. Syntaktisch sind die Aufrufe identisch. Bei Aufrufen von Funktionszeigern wird die `managed`-Aufrufkonvention verwendet. Wenn Sie deklarieren möchten, dass Sie die `unmanaged`-Aufrufkonvention benötigen, müssen Sie nach der `delegate*`-Syntax das Schlüsselwort `unmanaged` einfügen. Andere Aufrufkonventionen können mithilfe von Attributen in der `delegate*`-Deklaration angegeben werden.

Schließlich können Sie <xref:System.Runtime.CompilerServices.SkipLocalsInitAttribute?displayProperty=nameWithType> hinzufügen, um den Compiler anzuweisen, das `localsinit`-Flag nicht auszugeben. Dieses Flag weist die Common Language Runtime an, alle lokalen Variablen mit 0 (Null) zu initialisieren. Das `localsinit`-Flag ist das Standardverhalten von C# seit Version 1.0. Die zusätzliche Nullinitialisierung kann jedoch in einigen Szenarios zu nachweisbaren Leistungseinbußen führen, insbesondere wenn Sie `stackalloc` verwenden. In diesen Fällen können Sie <xref:System.Runtime.CompilerServices.SkipLocalsInitAttribute> hinzufügen. Sie können die Klasse einer einzelnen Methode oder Eigenschaft, zu `class`/`struct`/`interface` oder sogar zu einem Modul hinzufügen. Dieses Attribut hat keine Auswirkung auf `abstract`-Methoden. Es beeinflusst den für die Implementierung generierten Code.

Diese Features können die Leistung in einigen Szenarios verbessern. Sie sollten jedoch nur nach einem sorgfältigen Leistungsvergleich vor und nach der Einführung eingesetzt werden. Code, der ganze Zahlen in nativer Größe enthält, muss auf mehreren Zielplattformen mit unterschiedlichen Größen von ganzen Zahlen getestet werden. Die anderen Features erfordern unsicheren Code.

## <a name="fit-and-finish-features"></a>Anpassen und Fertigstellen von Features

Viele der anderen Features helfen Ihnen, Code effizienter zu schreiben. In C# 9.0 können Sie den Typ in einem neuen Ausdruck weglassen, wenn der Typ des erstellten Objekts bereits bekannt ist. Die häufigste Anwendungsfall hierfür sind Felddeklarationen:

:::code language="csharp" source="snippets/whats-new-csharp9/FitAndFinish.cs" ID="WeatherStationField":::

Der Zieltyp „new“ kann auch verwendet werden, wenn Sie ein neues Objekt erstellen müssen, das als Parameter an eine Methode übergeben werden soll. In diesem Fall können Sie eine `ForecastFor()`-Methode mit der folgenden Signatur implementieren:

:::code language="csharp" source="snippets/whats-new-csharp9/FitAndFinish.cs" ID="ForecastSignature":::

Sie können sie wie folgt aufrufen:

:::code language="csharp" source="snippets/whats-new-csharp9/FitAndFinish.cs" ID="TargetTypeNewArgument":::

Ein weiterer nützlicher Anwendungsfall für dieses Feature ist die Kombination mit Nur-init-Eigenschaften, um ein neues Objekt zu initialisieren:

:::code language="csharp" source="snippets/whats-new-csharp9/FitAndFinish.cs" ID="InitWeatherStation":::

Mithilfe eines `return new();`-Ausdrucks können Sie eine Instanz zurückgeben, die vom Standardkonstruktor erstellt wurde.

Ein ähnliches Feature verbessert die Zieltypauflösung von bedingten Ausdrücken. Aufgrund dieser Änderung müssen die beiden Ausdrücke keine implizite Konvertierung von einem in den anderen aufweisen, sondern können beide über implizite Konvertierungen in einen Zieltyp verfügen. Diese Änderung wird Ihnen wahrscheinlich nicht auffallen. Was Sie bemerken werden, ist, dass einige bedingte Ausdrücke, die zuvor eine Umwandlung erforderten oder nicht kompiliert werden konnten, jetzt funktionieren.

Ab C# 9.0 können Sie Lambdaausdrücken oder anonymen Methoden den Modifizierer `static` hinzufügen. Statische Lambdaausdrücke entsprechen den lokalen `static`-Funktionen: statische Lambdafunktionen oder anonyme Funktionen weder lokale Variablen noch den Instanzzustand erfassen. Der Modifizierer `static` verhindert, dass versehentlich andere Variablen erfasst werden.

Kovariante Rückgabetypen flexibilisieren die Rückgabetypen von überschriebenen Funktionen. Eine überschriebene virtuelle Funktion kann einen Typ zurückgeben, der von dem in der Basisklassenmethode deklarierten Rückgabetyp abgeleitet wird. Dies kann nicht nur für Datensätze nützlich sein, sondern auch für andere Typen, die virtuelle Klon- oder Factorymethoden unterstützen.

Außerdem erkennen und verwenden `foreach`-Schleifen eine `GetEnumerator`-Erweiterungsmethode, die ansonsten das `foreach`-Muster erfüllt. Diese Änderung bedeutet, dass `foreach` mit anderen musterbasierten Konstruktionen, z. B. mit dem async-Muster, sowie der musterbasierten Dekonstruktion konsistent ist. In der Praxis bedeutet diese Änderung, dass Sie jedem Typ `foreach`-Unterstützung hinzufügen können. Sie sollten die Verwendung von „foreach“ jedoch auf die Fälle beschränken, in denen die Enumeration eines Objekts in Ihrem Softwareentwurf sinnvoll ist.

Sie können auch Ausschussvariablen als Parameter für Lambdaausdrücke verwenden. So müssen Sie das Argument nicht mehr benennen, und der Compiler muss es unter Umständen gar nicht verwenden. Sie nutzen einfach `_` für alle Argumente.

Schließlich haben Sie nun die Möglichkeit, Attribute auf lokale Funktionen anzuwenden. Sie können beispielsweise Nullwerte zulassende Attributanmerkungen auf lokale Funktionen anwenden.

## <a name="support-for-code-generators"></a>Unterstützung für Code-Generatoren

Die beiden letzten Features dienen der Unterstützung von C#-Code-Generatoren. C#-Code-Generatoren sind eine Komponente, die Sie selbst schreiben können und die einem Roslyn-Analysetool oder einem Codefix ähnelt. Der Unterschied besteht darin, dass Code-Generatoren Code analysieren und im Rahmen der Kompilierung neue Quellcodedateien schreiben. Ein typischer Code-Generator durchsucht Code nach Attributen oder weiteren Konventionen.

Ein Code-Generator liest Attribute oder andere Codeelemente mithilfe der Roslyn-Analyse-APIs. Auf Grundlage dieser Informationen fügt er der Kompilierung neuen Code hinzu. Quell-Generatoren können nur Code hinzufügen. Sie sind nicht berechtigt, vorhandenen Code während der Kompilierung zu ändern.

Bei den beiden Features für Code-Generatoren sind handelt es sich um Erweiterungen für die ***partielle Methodensyntax*** und für ***Modulinitialisierer***. Zuerst zu den Änderungen an partiellen Methoden: Vor C# 9.0 waren partielle Methoden privat (`private`) und konnten weder einen Zugriffsmodifizierer angeben noch über eine leere Rückgabe (`void`) oder `out`-Parameter verfügen. Diese Einschränkungen führten dazu, dass der Compiler alle Aufrufe von partiellen Methoden entfernte, wenn keine Methodenimplementierung bereitgestellt wurde. In C# 9.0 werden diese Einschränkungen behoben. Deklarationen von partiellen Methoden müssen jetzt jedoch implementiert werden. Code-Generatoren können diese Implementierung bereitstellen. Damit kein Breaking Change eingeführt wird, befolgt der Compiler bei jeder partiellen Methode, die keinen Zugriffsmodifizierer aufweist, die alten Regeln. Wenn die partielle Methode den Zugriffsmodifizierer `private` enthält, unterliegt die partielle Methode den neuen Regeln.

Das zweite neue Feature für Code-Generatoren sind ***Modulinitialisierer***. Modulinitialisierer sind Methoden, an die das Attribut <xref:System.Runtime.CompilerServices.ModuleInitializerAttribute> angefügt wurde. Diese Methoden werden von der Runtime aufgerufen, wenn die Assembly geladen wird. Ein Modulinitialisierer:

- muss statisch sein
- muss parameterlos sein
- muss eine leere Rückgabe („void“) zurückgeben
- darf keine generische Methode sein
- darf nicht in einer generischen Klasse enthalten sein
- muss für das Modul zugänglich sein, in dem er enthalten ist

Der letzte Aufzählungspunkt bedeutet, dass die Methode und die Klasse, in der die Methode enthalten ist, intern oder öffentlich sein müssen. Diese Methode darf keine lokale Funktion sein.
