---
title: Neuerungen in .NET Core 3.0
description: Informationen zu den neuen Features in .NET Core 3.0.
dev_langs:
- csharp
- vb
author: thraka
ms.author: adegeo
ms.date: 12/31/2018
ms.openlocfilehash: baaa2676865c475e331ec889e7b10ae326b552fa
ms.sourcegitcommit: b8ace47d839f943f785b89e2fff8092b0bf8f565
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2019
ms.locfileid: "55675087"
---
# <a name="whats-new-in-net-core-30-preview-2"></a>Neuerungen in .NET Core 3.0 (Vorschauversion 2)

In diesem Artikel werden Neuerungen in .NET Core 3.0 (Vorschauversion 2) beschrieben. Eine der wichtigsten Verbesserungen ist die Unterstützung für Windows-Desktopanwendungen (nur Windows). Mit der .NET Core 3.0 SDK-Komponente Windows Desktop können Sie Ihre Windows Forms- und WPF-Anwendungen (Windows Presentation Foundation) portieren. Die Windows Desktop-Komponente wird ausdrücklich nur für Windows unterstützt und ist nur unter Windows enthalten. Weitere Informationen finden Sie unten im Abschnitt [Windows Desktop](#windows-desktop).

.NET Core 3.0 bietet Unterstützung für C# 8.0.

[Sie können die Vorschauversion 2 von .NET Core 3.0 jetzt für Windows, Mac und Linux herunterladen und sofort starten.](https://aka.ms/netcore3download) Alle Details zu diesem Release finden Sie in den [Versionshinweisen zur Vorschauversion 2 von .NET Core 3.0](https://aka.ms/netcore3releasenotes).

Weitere Informationen zu Neuerungen, die in Vorschauversion 1 eingeführt wurden, finden Sie in der [Ankündigung der Vorschauversion 1 von .NET Core 3.0](https://blogs.msdn.microsoft.com/dotnet/2018/12/04/announcing-net-core-3-preview-1-and-open-sourcing-windows-desktop-frameworks/).

Weitere Informationen zu Neuerungen, die in Vorschauversion 2 eingeführt wurden, finden Sie in der [Ankündigung der Vorschauversion 2 von .NET Core 3.0]().

## <a name="c-8"></a>C# 8.0

.NET Core 3.0 unterstützt C# 8.0. Ab der Vorschauversion 2 von NET Core 3.0 werden neue Features unterstützt, die weiter unten aufgeführt sind. Weitere Informationen zu Features von C# 8.0 finden Sie in den folgenden Blogbeiträgen:

- [Do more with patterns in C# 8.0 (Effektivere Verwendung von Mustern in C# 8.0)](https://blogs.msdn.microsoft.com/dotnet/2019/01/24/do-more-with-patterns-in-c-8-0/)
- [Take C# 8.0 for a spin (Neuerungen in C# 8.0)](https://blogs.msdn.microsoft.com/dotnet/2018/12/05/take-c-8-0-for-a-spin/)
- [Building C# 8.0 (Neue Features in C# 8.0)](https://blogs.msdn.microsoft.com/dotnet/2018/11/12/building-c-8-0/)


### <a name="ranges-and-indices"></a>Bereiche und Indizes

Der neue `Index`-Typ kann für die Indizierung verwendet werden. Sie können einen aus einem `int` erstellen, der vom Anfang aus zählt, oder mit einem Präfix-`^`-Operator (C#), der vom Ende aus zählt:

```csharp
Index i1 = 3;  // number 3 from beginning
Index i2 = ^4; // number 4 from end
int[] a = { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 };
Console.WriteLine($"{a[i1]}, {a[i2]}"); // "3, 6"
```

Es gibt auch einen `Range`-Typ, der aus zwei `Index`-Werten besteht, einen für den Anfang und einen für das Ende, und mit einem `x..y`-Bereichsausdruck (C#) geschrieben werden kann. Sie können dann mit einem `Range` indizieren, um einen Slice zu erzeugen:

```csharp
var slice = a[i1..i2]; // { 3, 4, 5 }
```

### <a name="async-streams"></a>Asynchrone Datenströme

Die `IAsyncEnumerable<T>`-Typ ist eine neue asynchrone Version von `IEnumerable<T>`. In C# 8.0 können Sie `await foreach` zur Verarbeitung der `IAsyncEnumerable<T>`-Elemente nutzen und anschließend `yield return` zum Erstellen von Elementen verwenden.

Das folgende Beispiel zeigt sowohl die Produktion als auch die Nutzung von asynchronen Datenströmen. Die `foreach`-Anweisung ist asynchron und verwendet `yield return`, um einen asynchronen Datenstrom für Anrufer zu erstellen. Dieses Muster (mit `yield return`) ist das empfohlene Modell zum Erstellen von asynchronen Datenströmen.

```csharp
async IAsyncEnumerable<int> GetBigResultsAsync()
{
    await foreach (var result in GetResultsAsync())
    {
        if (result > 20) yield return result; 
    }
}
```

Zusätzlich zu `await foreach` können Sie auch asynchrone Iteratoren erstellen, z.B. einen Iterator, der `IAsyncEnumerable/IAsyncEnumerator` zurückgibt, in den Sie sowohl `await` als auch `yield` einfügen können. Für Objekte, die gelöscht werden müssen, können Sie `IAsyncDisposable` verwenden, das von verschiedenen BCL-Typen implementiert wird, wie beispielsweise `Stream` und `Timer`.

>[!NOTE]
>Sie benötigen zur Nutzung asynchroner Datenströme die Vorschauversion 2 von .NET Core 3.0, wenn Sie mit der Vorschauversion 2 von Visual Studio 2019 oder mit der aktuellen Vorschauversion der [C#-Erweiterung für Visual Studio Code](https://github.com/OmniSharp/omnisharp-vscode/releases/tag/v1.18.0-beta5) entwickeln möchten. Wenn Sie die Vorschauversion 2 von .NET Core 3.0 über die Befehlszeile nutzen, entstehen keine Probleme.

### <a name="using-declarations"></a>using-Deklarationen

*using-Deklarationen* sind ein neues Feature, mit dem sichergestellt werden kann, dass ein Objekt wie erwartet verworfen wird. Mit einer *using-Deklaration* wird für das Objekt Speicher belegt, solange es sich im Geltungsbereich befindet. Verlässt das Objekt diesen Bereich, wird es automatisch verworfen. Dadurch müssen weniger geschachtelte *using-Anweisungen* verwendet werden, was zu übersichtlicherem Code führt.

```csharp
static void Main(string[] args)
{
    using var options = Parse(args);
    if (options["verbose"]) { WriteLine("Logging..."); }

} // options disposed here
```

### <a name="switch-expressions"></a>switch-Ausdrücke

*switch-Ausdrücke* stellen eine übersichtlichere Variante von *switch-Anweisungen* dar. Da es sich aber um Ausdrücke handelt, wird ein Wert zurückgegeben. *switch-Ausdrücke* lassen sich außerdem uneingeschränkt mit Musterabgleichen verwenden und nutzen das Ausschussmuster `_` zur Darstellung des `default`-Werts.

Die Syntax von *switch-Ausdrücken* wird im folgenden Beispiel gezeigt:

```csharp
static string Display(object o) => o switch
{
    Point { X: 0, Y: 0 }         => "origin",
    Point { X: var x, Y: var y } => $"({x}, {y})",
    _                            => "unknown"
};
```

In diesem Beispiel werden zwei Muster verwendet. `o` wird für `Point` zuerst mit dem *Typmuster* und anschließend mit dem *Eigenschaftenmuster* innerhalb der *{geschweiften Klammern}* abgeglichen. `_` beschreibt das `discard pattern`, das mit `default` für *switch-Anweisungen* identisch ist.

Mit Mustern können Sie anstelle von prozeduralem Code, in dem Tests für eine Absicht implementiert werden, deklarativen Code schreiben, der diese Absicht direkt erfasst. Die Verantwortung zur Implementierung des prozeduralen Codes wird so dem Compiler übertragen, der diese Aufgabe immer fehlerfrei ausführt.

Es gibt dennoch Fälle, in denen *switch-Anweisungen* weiterhin besser geeignet sind als *switch-Ausdrücke*, und Muster können mit beiden Syntaxstilen verwendet werden.

Weitere Informationen finden Sie unter [Do more with patterns in C# 8.0 (Effektivere Verwendung von Mustern in C# 8.0)](https://blogs.msdn.microsoft.com/dotnet/2019/01/24/do-more-with-patterns-in-c-8-0/).

## <a name="ieee-floating-point-improvements"></a>Verbesserungen bei Gleitkommazahlen gemäß IEEE-Spezifikation

APIs für Gleitkommazahlen werden aktuell an die [Revision des Standards IEEE 754-2008](https://en.wikipedia.org/wiki/IEEE_754-2008_revision) angepasst. Ziel dieser Änderungen ist es, alle „erforderlichen“ Operationen verfügbar zu machen und sicherzustellen, dass sie mit dem in der IEEE-Spezifikation beschriebenen Verhalten kompatibel sind.

Korrekturen bei der Analyse und Formatierung:

* Eingaben mit beliebiger Länge werden richtig analysiert und gerundet.
* Die negative Null wird richtig analysiert und formatiert.
* Unendlichkeits- und NaN-Werte werden mithilfe einer Überprüfung, bei der nicht zwischen Groß-/Kleinbuchstaben unterschieden wird, richtig analysiert. Außerdem ist, falls erforderlich, optional das vorangestellte `+`-Zeichen zulässig.

In den neuen Mathematik-APIs sind folgende Operationen enthalten:

* `BitIncrement/BitDecrement`\
entspricht den IEEE-Operationen `nextUp` und `nextDown`. Diese geben jeweils die kleinste Gleitkommazahl zurück, die größer oder kleiner als der Eingabewert ist. `Math.BitIncrement(0.0)` gibt beispielsweise `double.Epsilon` zurück.

* `MaxMagnitude/MinMagnitude`\
entspricht den IEEE-Operationen `maxNumMag` und `minNumMag`. Diese geben für zwei Eingabewerte jeweils den Wert zurück, für den ein größerer oder kleinerer Absolutbetrag ermittelt wird. `Math.MaxMagnitude(2.0, -3.0)` gibt beispielsweise `-3.0` zurück.

* `ILogB`\
entspricht der IEEE-Operation `logB`, die einen integralen Wert zurückgibt. Der Rückgabewert ist der integrale Wert des Logarithmus zur Basis 2 des Eingabeparameters. Diese Operation entspricht im Wesentlichen `floor(log2(x))`, jedoch ist der Rundungsfehler minimal.

* `ScaleB`\
entspricht der IEEE-Operation `scaleB`, der ein integraler Wert übergeben wird. Zurückgegeben wird im Wesentlichen `x * pow(2, n)`, jedoch ist der Rundungsfehler minimal.

* `Log2`\
entspricht der IEEE-Operation `log2`, die den Logarithmus zur Basis 2 zurückgibt. Diese Operation minimiert den Rundungsfehler.

* `FusedMultiplyAdd`\
entspricht der IEEE-Operation `fma`, die eine Fused-Multiply-Add-Operation durchführt. Dabei wird `(x * y) + z` als einzelne Operation ausgeführt, wodurch der Rundungsfehler minimiert wird. `FusedMultiplyAdd(1e308, 2.0, -1e308)` gibt beispielsweise `1e308` zurück. Die reguläre Operation `(1e308 * 2.0) - 1e308` gibt `double.PositiveInfinity` zurück.

* `CopySign`\
entspricht der IEEE-Operation `copySign`. Diese gibt den Wert von `x` mit dem Vorzeichen von `y` zurück.

## <a name="net-platform-dependent-intrinsics"></a>Intrinsische .NET-plattformabhängige Funktionen

Mit neuen APIs kann auf bestimmte leistungsorientierte CPU-Anweisungen wie **SIMD** oder **Bit Manipulation Instruction Sets** zugegriffen werden. Diese Anweisungen können in bestimmten Szenarios wie der effizienten parallelen Datenverarbeitung zu deutlichen Leistungssteigerungen führen. Diese API-Operationen können nicht nur in eigenen Programmen verwendet werden, sondern werden nun auch von .NET-Bibliotheken zur Leistungssteigerung eingesetzt.

In den folgenden CoreCLR-PRs werden einige intrinsische Funktionen und deren Implementierung oder Verwendung vorgestellt:

* [Implement simple SSE2 hardware intrinsics (Implementieren einfacher intrinsischer SSE2-Hardwarefunktionen)](https://github.com/dotnet/coreclr/pull/15585)
* [Implement the SSE hardware intrinsics (Implementieren intrinsischer SSE2-Hardwarefunktionen)](https://github.com/dotnet/coreclr/pull/15538)
* [Arm64 Base HW Intrinsics (Intrinsische Base-Hardwarefunktionen für ARM64)](https://github.com/dotnet/coreclr/pull/16822)
* [Use TZCNT and LZCNT for Locate{First|Last}Found{Byte|Char} (Verwenden von TZCNT und LZCNT für Locate{First|Last}Found{Byte|Char})](https://github.com/dotnet/coreclr/pull/21073)

Weitere Informationen finden Sie unter [.NET Platform Dependent Intrinsics (Intrinsische .NET-plattformabhängige Funktionen)](https://github.com/dotnet/designs/blob/master/accepted/platform-intrinsics.md). In diesem Artikel wird eine Strategie zum Definieren von intrinsischen Funktionen für eine bestimmte Hardwareinfrastruktur vorgestellt. Dadurch können Microsoft, Chiphersteller oder andere Unternehmen oder Personen Hardware- bzw. Chip-APIs entwerfen, die in .NET-Code verfügbar gemacht werden soll.

## <a name="default-executables"></a>Standardmäßig ausführbare Dateien

.NET Core erstellt die [frameworkabhängigen ausführbaren Dateien](../deploying/index.md#framework-dependent-executables-fde) jetzt standardmäßig. Dies ist neu für Anwendungen, die eine global installierte Version von .NET Core verwenden. Bis jetzt produzierten nur [eigenständige Bereitstellungen](../deploying/index.md#self-contained-deployments-scd) eine ausführbare Datei.

Während `dotnet build` oder `dotnet publish` wird eine ausführbare Datei erstellt, die der Umgebung und Plattform des von Ihnen verwendeten SDKs entspricht. Diese ausführbaren Dateien bieten Ihnen die gleichen Möglichkeiten wie andere native ausführbare Dateien, wie z.B.:

* Sie können die ausführbare Datei doppelklicken.
* Sie können die Anwendung direkt aus einer Eingabeaufforderung starten, z.B. `myapp.exe` unter Windows und `./myapp` unter Linux und MacOS.

## <a name="build-copies-dependencies"></a>Build kopiert Abhängigkeiten

`dotnet build` kopiert jetzt NuGet-Abhängigkeiten für Ihre Anwendung aus dem NuGet-Cache in den Buildausgabeordner. Bisher wurde Abhängigkeiten nur als Teil von `dotnet publish` kopiert. 

Es gibt einige Vorgänge, wie das Verlinken und das Veröffentlichen von Razor-Seiten, die noch veröffentlicht werden müssen.


## <a name="local-dotnet-tools"></a>Lokale dotnet-Tools

>[!WARNING]
>Nach der Vorschauversion 1 von .NET Core 3.0 wurde in Vorschauversion 2 eine Änderung an den lokalen .NET Core-Tools vorgenommen.  Wenn Sie die lokalen Tools in Vorschauversion 1 mit einem Befehl wie `dotnet tool restore` oder `dotnet tool install` verwenden haben, müssen Sie den Cacheordner für die lokalen Tools löschen, da diese andernfalls in Vorschauversion 2 nicht funktionieren. Je nach Betriebssystem werden die Ordnerpfade wie folgt gelöscht:
>
>Mac und Linux: `rm -r $HOME/.dotnet/toolResolverCache`
>
>Windows: `rmdir /s %USERPROFILE%\.dotnet\toolResolverCache`
>
>Wenn Sie diesen Ordner nicht löschen, wird eine Fehlermeldung angezeigt.

.NET Core 2.1 unterstützt globale Tools, .NET Core 3.0 verfügt jetzt über lokale Tools. Lokale Tools ähneln globalen Tools, sind aber mit einem bestimmten Speicherort auf dem Datenträger verknüpft. Dies ermöglicht die Bereitstellung von Tools für einzelne Projekte und Repositorys. Jedes lokal installierte Tool ist nicht global verfügbar. Tools werden als NuGet-Pakete verteilt.

Lokale Tools basieren auf einer Manifestdatei `dotnet-tools.json` in Ihrem aktuellen Verzeichnis. In dieser Manifestdatei werden die Tools festgelegt, die im Verzeichnis und in den Unterverzeichnissen verfügbar sind. Durch die Erstellung dieser Manifestdatei im Stammverzeichnis Ihres Repositorys stellen Sie sicher, dass jeder, der Ihren Code klont, die Tools wiederherstellen und verwenden kann, die für eine erfolgreiche Arbeit mit Ihrem Code erforderlich sind.

Mit dem folgenden Befehl können Sie eine `dotnet-tools.json`-Manifestdatei erstellen:

```console
dotnet new tool-manifest
```

Wenn Sie dem lokalen Manifest ein neues Tool hinzufügen möchten, verwenden Sie den folgenden Befehl:

```console
dotnet tool install <packageId>
```

Mit dem folgenden Befehl können Sie außerdem die Tools im lokalen Manifest auflisten:

```console
dotnet tool list
```

Wenn Sie die global installierten Tools anzeigen möchten, verwenden Sie folgenden Befehl:

```console
dotnet tool list -g
```

Wenn die Manifestdatei für die lokalen Tools verfügbar ist, die im Manifest festgelegten Tools jedoch nicht installiert wurden, verwenden Sie den folgenden Befehl, um sie automatisch herunterzuladen und zu installieren:

```console
dotnet tool restore
```

Führen Sie ein lokales Tool mit dem folgenden Befehl aus:

```console
dotnet tool run <tool-command-name>
```

Wenn ein lokales Tool ausgeführt wird, sucht dotnet nach einer Manifestdatei in der aktuellen Verzeichnisstruktur. Wenn eine Manifestdatei für das Tool gefunden wurde, wird diese nach dem erforderlichen Tool durchsucht. Wenn das Tool im Manifest, aber nicht im Cache gefunden wird, wird dem Benutzer eine Fehlermeldung angezeigt. Dieser muss dann `dotnet tool restore` ausführen.

Wenn Sie ein Tool aus der Manifestdatei für die lokalen Tools entfernen möchten, führen Sie den folgenden Befehl aus:

```console
dotnet tool uninstall <packageId>
```

Die Manifestdatei des Tools ist so konzipiert, dass sie eine manuelle Bearbeitung ermöglicht. Sie müssen die Datei bearbeiten, um die erforderliche Version für die Arbeit mit dem Repository zu aktualisieren. Hier ist ein Beispiel für eine `dotnet-tools.json`-Datei:

```json
{
  "version": 1,
  "isRoot": true,
  "tools": {
    "dotnetsay": {
      "version": "2.1.4",
      "commands": [
        "dotnetsay"
      ]
    },
    "t-rex": {
      "version": "1.0.103",
      "commands": [
        "t-rex"
      ]
    }
  }
}
```

Für sowohl globale als auch lokale Tools ist eine kompatible Version der Runtime erforderlich. Die meisten Tools führen derzeit NuGet.org target .NET Core Runtime 2.1 aus. Um diese global oder lokal zu installieren, müssten Sie weiterhin die [NET Core 2.1-Runtime](https://dotnet.microsoft.com/download/dotnet-core/2.1) installieren.

## <a name="windows-desktop"></a>Windows-Desktop

Ab .NET Core 3.0 Vorschauversion 1 können Sie Windows Desktop-Anwendungen mit WPF und Windows Forms erstellen. Diese Frameworks unterstützt auch die Verwendung moderner Steuerelemente und des Fluent-Stils aus der Windows-UI-XAML-Bibliothek (WinUI) über [XAML-Inseln](/windows/uwp/xaml-platform/xaml-host-controls).

Die Windows Desktop-Komponente ist Teil des Windows .NET Core 3.0 SDK.

Mit dem folgenden `dotnet`-Befehl können Sie eine neue WPF- oder Windows Forms-Anwendung erstellen:

```console
dotnet new wpf
dotnet new winforms
```

Neu in Vorschauversion 2 von Visual Studio 2019 sind Vorlagen für die Option **Neues Projekt** für Windows Forms und WPF in .NET Core 3.0. Designer werden nach wie vor noch nicht unterstützt. Sie können die Projekte in Visual Studio 2019 öffnen, starten und debuggen.

Ab Visual Studio 2017 15.9 ist es möglich, [.NET Core-Vorschauversionen zu aktivieren](https://blogs.msdn.microsoft.com/dotnet/2018/11/13/net-core-tooling-update-for-visual-studio-2017-version-15-9/). Dieses Feature müssen Sie jedoch erst aktivieren, und es handelt sich dabei nicht um ein unterstütztes Szenario.

Die neuen Projekte sind die gleichen wie die bestehenden.NET Core Projekte, mit ein paar Ergänzungen. Hier ist der Vergleich eines einfachen .NET Core-Konsolenprojekts mit einem einfachen Windows Forms- und WPF-Projekt.

In einem .NET Core-Konsolenprojekt verwendet das Projekt das `Microsoft.NET.Sdk` SDK und deklariert eine Abhängigkeit von .NET Core 3.0 über das `netcoreapp3.0`-Zielframework. Um eine Windows Desktop-Anwendung zu erstellen, verwenden Sie das `Microsoft.NET.Sdk.WindowsDesktop` SDK und wählen Sie das zu verwendende UI-Framework:

```diff
-<Project Sdk="Microsoft.NET.Sdk">
+<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp3.0</TargetFramework>
+   <UseWPF>true</UseWPF>
  </PropertyGroup>
</Project>
```

Um Windows Forms und nicht WPF zu wählen, legen Sie `UseWindowsForms` anstelle von `UseWPF` fest:

```diff
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp3.0</TargetFramework>
-   <UseWPF>true</UseWPF>
+   <UseWindowsForms>true</UseWindowsForms>
  </PropertyGroup>
</Project>
```

Sowohl `UseWPF` als auch `UseWindowsForms` können auf `true` festgelegt werden, wenn die Anwendung beide Frameworks verwendet, z.B. wenn ein Windows Forms-Dialogfeld ein WPF-Steuerelement bereitstellt.

Ihr Feedback in den [dotnet/winforms](https://github.com/dotnet/winforms/issues)-, [dotnet/wpf](https://github.com/dotnet/wpf/issues)- und [dotnet/core](https://github.com/dotnet/core/issues)-Repositorys ist jederzeit willkommen.

## <a name="msix-deployment-for-windows-desktop"></a>MSIX-Bereitstellung für Windows Desktop

[MSIX](https://docs.microsoft.com/windows/msix/) ist ein neues Windows-App-Paketformat. Es kann zum Bereitstellen von .NET Core 3.0-Desktopanwendungen auf Windows 10 verwendet werden.

Ab der Vorschauversion 2 von Visual Studio 2019 können mit dem enthaltenen [Paketerstellungsprojekt für Windows-Anwendungen](https://docs.microsoft.com/windows/uwp/porting/desktop-to-uwp-packaging-dot-net) MSIX-Pakete mit [eigenständigen](../deploying/#self-contained-deployments-scd) .NET Core-Anwendungen erstellt werden.

>Hinweis: Die unterstützten Laufzeiten müssen in der `<RuntimeIdentifiers>`-Eigenschaft der .NET Core-Projektdatei angegeben werden:
```xml
<RuntimeIdentifiers>win-x86;win-x64</RuntimeIdentifiers>
```

## <a name="fast-built-in-json-support"></a>Schneller integrierter JSON-Support

Das .NET-Ökosystem basiert auf [**Json.NET**](https://www.newtonsoft.com/json) und anderen beliebten JSON-Bibliotheken, die weiterhin eine gute Wahl sind. **Json.NET** verwendet als Basisdatentyp .NET-Zeichenfolgen, die intern in UTF-16 codiert sind.

Die neue integrierte JSON-Unterstützung ist überaus leistungsfähig und basiert auf `Span<byte>`. Außerdem wird damit nur wenig Speicher belegt. In .NET Core 3.0 wurden dem Namespace `System.Text.Json` drei neue JSON-bezogene Typen hinzugefügt.

### <a name="utf8jsonreader"></a>Utf8JsonReader

`System.Text.Json.Utf8JsonReader` ist ein leistungsstarker, reiner Vorwärtsleser mit geringer Zuordnung für UTF-8-kodierten JSON-Text, der von einem `ReadOnlySpan<byte>` gelesen wird. Der `Utf8JsonReader` ist ein grundlegender, Low-Level-Typ, der zum Erstellen von benutzerdefinierten Parsern und Fehler beim Erstellen des Deserialisierungsprogramms genutzt werden kann. Das Durchlesen einer JSON-Nutzlast mit dem neuen `Utf8JsonReader` ist 2x schneller als mit dem Leser von **Json.NET**. Es wird erst dann zugewiesen, wenn Sie JSON-Token als (UTF-16)-Zeichenfolgen aktualisieren müssen.

Diese neue API umfasst die folgenden Komponenten:

* In Vorschauversion 1: JSON-Reader (sequenzieller Zugriff)
* Geplant: JSON-Writer, DOM (wahlfreier Zugriff), POCO-Serialisierungsprogramm, POCO-Deserialisierungsprogramm

Hier ist eine einfache Leserschleife für den `Utf8JsonReader`, die als Startpunkt verwendet werden kann:

```csharp
using System.Text.Json;

public static void Utf8JsonReaderLoop(ReadOnlySpan<byte> dataUtf8)
{
    var json = new Utf8JsonReader(dataUtf8, isFinalBlock: true, state: default);

    while (json.Read())
    {
        JsonTokenType tokenType = json.TokenType;
        ReadOnlySpan<byte> valueSpan = json.ValueSpan;
        switch (tokenType)
        {
            case JsonTokenType.StartObject:
            case JsonTokenType.EndObject:
                break;
            case JsonTokenType.StartArray:
            case JsonTokenType.EndArray:
                break;
            case JsonTokenType.PropertyName:
                break;
            case JsonTokenType.String:
                string valueString = json.GetStringValue();
                break;
            case JsonTokenType.Number:
                if (!json.TryGetInt32Value(out int valueInteger))
                {
                    throw new FormatException();
                }
                break;
            case JsonTokenType.True:
            case JsonTokenType.False:
                bool valueBool = json.GetBooleanValue();
                break;
            case JsonTokenType.Null:
                break;
            default:
                throw new ArgumentException();
        }
    }

    dataUtf8 = dataUtf8.Slice((int)json.BytesConsumed);
    JsonReaderState state = json.CurrentState;
}
```

### <a name="utf8jsonwriter"></a>Utf8JsonWriter

Mit `System.Text.Json.Utf8JsonWriter` lassen sich in UTF-8 codierte JSON-Texte aus gängigen .NET-Typen wie `String`, `Int32` und `DateTime` schnell, vorwärtsgerichtet und ohne Zwischenspeichern schreiben. Der Writer ist ebenso wie der Reader ein grundlegender Low-Level-Typ, der zum Erstellen von benutzerdefinierten Serialisierungsmodulen verwendet werden kann. Mit der neuen `Utf8JsonWriter`-Klasse werden JSON-Nutzlasten 30 bis 80 % schnell geschrieben als mit dem **Json.NET**-Writer. Außerdem findet keine Speicherbelegung statt.

Das folgende Beispiel enthält für `Utf8JsonWriter` ein Anwendungsszenario, das als Ausgangspunkt verwendet werden kann:

```csharp
static int WriteJson(IBufferWriter<byte> output, long[] extraData)
{
    var json = new Utf8JsonWriter(output, state: default);

    json.WriteStartObject();

    json.WriteNumber("age", 15, escape: false);
    json.WriteString("date", DateTime.Now);
    json.WriteString("first", "John");
    json.WriteString("last", "Smith");

    json.WriteStartArray("phoneNumbers", escape: false);
    json.WriteStringValue("425-000-1212", escape: false);
    json.WriteStringValue("425-000-1213");
    json.WriteEndArray();

    json.WriteStartObject("address");
    json.WriteString("street", "1 Microsoft Way");
    json.WriteString("city", "Redmond");
    json.WriteNumber("zip", 98052);
    json.WriteEndObject();

    json.WriteStartArray("ExtraArray");
    for (var i = 0; i < extraData.Length; i++)
    {
        json.WriteNumberValue(extraData[i]);
    }
    json.WriteEndArray();

    json.WriteEndObject();

    json.Flush(isFinalBlock: true);

    return (int)json.BytesWritten;
}
```

`Utf8JsonWriter` nimmt `IBufferWriter<byte>` als Ausgabespeicherort entgegen, in den die JSON-Daten geschrieben werden. In der aufrufenden Funktion muss eine konkrete Implementierung bereitgestellt werden. Die Plattform umfasst zurzeit keine Implementierung dieser Schnittstelle. Ein Beispiel zu `IBufferWriter<byte>` finden Sie unter [https://gist.github.com/ahsonkhan/c76a1cc4dc7107537c3fdc0079a68b35](https://gist.github.com/ahsonkhan/c76a1cc4dc7107537c3fdc0079a68b35).

### <a name="jsondocument"></a>JsonDocument

`System.Text.Json.JsonDocument` basiert auf `Utf8JsonReader`. Mit `JsonDocument` können JSON-Daten analysiert werden. Zusätzlich kann damit ein schreibgeschütztes Dokumentobjektmodell (DOM) erstellt werden, das zur Unterstützung von zufälligen Zugriffen und Enumerationen abgefragt werden kann. Auf die JSON-Elemente, aus denen sich die Daten zusammensetzen, kann über den Typ `JsonElement` zugegriffen werden, der von `JsonDocument` als `RootElement`-Eigenschaft verfügbar gemacht wird. `JsonElement` enthält das JSON-Array und Objektenumeratoren sowie APIs zum Konvertieren von JSON-Text in gängige .NET-Typen. Die Analyse einer typischen JSON-Nutzlast und der Zugriff auf alle zugehörigen Member mithilfe von `JsonDocument` wird zwei- bis dreimal so schnell durchgeführt wie mit **Json.NET**. Dabei wird für eine überschaubare Datengröße (< 1 MB) nur wenig Speicher belegt.

Das folgende Beispiel enthält für `JsonDocument` und `JsonElement` ein Anwendungsszenario, das als Ausgangspunkt verwendet werden kann:

```csharp
static double ParseJson()
{
    const string json = " [ { \"name\": \"John\" }, [ \"425-000-1212\", 15 ], { \"grades\": [ 90, 80, 100, 75 ] } ]";

    double average = -1;

    using (JsonDocument doc = JsonDocument.Parse(json))
    {
        JsonElement root = doc.RootElement;
        JsonElement info = root[1];

        string phoneNumber = info[0].GetString();
        int age = info[1].GetInt32();

        JsonElement grades = root[2].GetProperty("grades");

        double sum = 0;
        foreach (JsonElement grade in grades.EnumerateArray())
        {
            sum += grade.GetInt32();
        }

        int numberOfCourses = grades.GetArrayLength();
        average = sum / numberOfCourses;
    }

    return average;
}
```

## <a name="assembly-unloadability"></a>Assemblyentladbarkeit

Assemblyentladbarkeit ist eine neue Funktion von `AssemblyLoadContext`. Dieses neue Feature bringt nur wenige neue APIs mit sich und ist daher aus der API-Perspektive gut überschaubar. Mithilfe der Assemblyentladbarkeit kann der Ladeprogrammkontext entladen werden, wodurch sämtlicher Speicher für instanziierte Typen, statische Felder und für die Assembly selbst freigegeben wird. Eine Anwendung sollte mit diesem Mechanismus unbegrenzt lange Assemblys laden und entladen können, ohne dass ein Arbeitsspeicherverlust auftritt.

Diese neue Funktion kann für Szenarios wie die folgenden verwendet werden:

* Plug-In-Szenarios, in denen ein dynamisches Laden und Entladen von Plug-Ins erforderlich ist. 
* Dynamisches Kompilieren und Ausführen von Code sowie Leeren des zugehörigen Speichers. Dies ist beispielsweise für Websites und Skript-Engines nützlich.
* Laden von Assemblys für eine Selbstprüfung (ähnlich wie bei ReflectionOnlyLoad). In vielen Fällen ist [MetadataLoadContext](#type-metadataloadcontext) (veröffentlicht in Vorschauversion 1) jedoch die bessere Wahl.

Weitere Informationen finden Sie unter [Verwenden von Entladbarkeit](https://github.com/dotnet/coreclr/pull/22221).

Beim Entladen von Assemblys muss unbedingt darauf geachtet werden, dass alle außerhalb des Ladeprogrammkontexts vorhandenen Verweise auf verwaltete Objekte nachvollzogen und verwaltet werden. Wenn der Ladeprogrammkontext zum Entladen aufgefordert wird, müssen alle externen Verweise bereits aufgehoben sein, damit der Ladeprogrammkontext ausschließlich mit sich selbst konsistent ist.

Assemblyentladbarkeit wurde im .NET Framework durch Anwendungsdomänen (AppDomains) bereitgestellt, die in .NET Core nicht unterstützt werden. AppDomains hatten verglichen mit diesem neuen Modell sowohl Vor- als auch Nachteile. Das neue Ladeprogrammmodell kann im Vergleich zu AppDomains als flexibler und leistungsfähiger betrachtet werden.

## <a name="windows-native-interop"></a>Native Windows-Interop-API

Windows stellt eine umfassende native API mit grundlegenden C-APIs (ohne C++-Features), COM und WinRT bereit. Seit .NET Core 1.0 wird **P/Invoke** unterstützt. In .NET Core 3.0 besteht nun die Möglichkeit, **mit CoCreate COM-APIs zu erstellen** und **WinRT-APIs zu aktivieren**.

Ein Beispiel zur Verwendung von COM finden Sie im [Quellcode der Excel-Demo](https://github.com/dotnet/samples/tree/master/core/extensions/ExcelDemo).


## <a name="type-sequencereader"></a>Typ: SequenceReader

In .NET Core 3.0 wurde `System.Buffers.SequenceReader` hinzugefügt, der als Leser für `ReadOnlySequence<T>` verwendet werden kann. Dies ermöglicht eine einfache, leistungsstarke Zuteilungsanalyse mit geringer Priorität von `System.IO.Pipelines`-Daten, die mehrere Hintergrundpuffer überwinden können. 

Das folgende Beispiel bricht eine Eingabe-`Sequence` in gültige, durch Trennzeichen getrennte `CR/LF`-Zeilen auf:

```csharp
private static ReadOnlySpan<byte> CRLF => new byte[] { (byte)'\r', (byte)'\n' };

public static void ReadLines(ReadOnlySequence<byte> sequence)
{
    SequenceReader<byte> reader = new SequenceReader<byte>(sequence);

    while (!reader.End)
    {
        if (!reader.TryReadToAny(out ReadOnlySpan<byte> line, CRLF, advancePastDelimiter:false))
        {
            // Couldn't find another delimiter
            // ...
        }

        if (!reader.IsNext(CRLF, advancePast: true))
        {
            // Not a good CR/LF pair
            // ...
        }

        // line is valid, process
        ProcessLine(line);
    }
}
```

## <a name="type-metadataloadcontext"></a>Typ: MetadataLoadContext

Der `MetadataLoadContext`-Typ wurde hinzugefügt, der das Lesen von Assemblymetadaten ermöglicht, ohne die Anwendungsdomäne des Anrufers zu beeinträchtigen. Assemblys werden als Daten gelesen, einschließlich Assemblys, die für andere Architekturen und Plattformen als die aktuelle Runtimeumgebung erstellt wurden. `MetadataLoadContext` überschneidet sich mit <xref:System.Reflection.Assembly.ReflectionOnlyLoad*>, das nur in .NET Framework verfügbar ist.

`MetdataLoadContext` ist im [System.Reflection.MetadataLoadContext-Paket](https://www.nuget.org/packages/System.Reflection.MetadataLoadContext) verfügbar. Es ist ein .NET Standard 2.0-Paket.

Der `MetadataLoadContext` stellt APIs ähnlich dem Typ <xref:System.Runtime.Loader.AssemblyLoadContext> zur Verfügung, basiert aber nicht auf diesem Typ. Ähnlich wie <xref:System.Runtime.Loader.AssemblyLoadContext> ermöglicht der `MetadataLoadContext` das Laden von Assemblys innerhalb einer isolierten Umgebung zum Laden von Assemblys. `MetdataLoadContext`-APIs geben <xref:System.Reflection.Assembly>-Objekte zurück, sodass bekannte Reflektions-APIs verwendet werden können. Ausführungsorientierte APIs, wie [MethodBase.Invoke](https://github.com/dotnet/corefx/blob/master/src/System.Reflection.MetadataLoadContext/src/System/Reflection/TypeLoading/Methods/RoMethod.cs#L127) sind nicht zulässig, und geben „InvalidOperationException“ zurück.

Das folgende Beispiel zeigt, wie Sie den richtigen Typen in einer Assembly findet, die eine bestimmte Schnittstelle implementiert:

```csharp
var paths = new string[] {@"C:\myapp\mscorlib.dll", @"C:\myapp\myapp.dll"};
var resolver = new PathAssemblyResolver(paths);
using (var lc = new MetadataLoadContext(resolver))
{
    Assembly a = lc.LoadFromAssemblyName("myapp");
    Type myInterface = a.GetType("MyApp.IPluginInterface");
    foreach (Type t in a.GetTypes())
    {
        if (t.IsClass && myInterface.IsAssignableFrom(t))
            Console.WriteLine($"Class {t.FullName} implements IPluginInterface");
    }
}
```

Szenarien für `MetadataLoadContext` beinhalten Entwurfszeitfeatures, Buildzeit-Tools und Runtime-Light-Up-Features, die eine Reihe von Assemblys als Daten überprüfen müssen und alle Dateisperren und Speicher freigeben, nachdem die Überprüfung durchgeführt wurde.

Der `MetadataLoadContext` hat eine Resolverklasse, die an dessen Konstruktor übergeben wird. Die Auftrag des Resolvers ist es, eine `Assembly` zu laden, wenn der `AssemblyName` angegeben ist. Die Resolverklasse wird aus der abstrakten `MetadataAssemblyResolver`-Klasse abgeleitet. Die Implementierung des Resolvers für pfadbasierte Szenarien ist durch `PathAssemblyResolver` möglich.

Die [MetadataLoadContext-Tests](https://github.com/dotnet/corefx/tree/master/src/System.Reflection.MetadataLoadContext/tests/src/Tests) zeigen viele Anwendungsfälle. Die [Assemblytests](https://github.com/dotnet/corefx/blob/master/src/System.Reflection.MetadataLoadContext/tests/src/Tests/Assembly/AssemblyTests.cs) sind ein guter Ausgangspunkt.

## <a name="tls-13--openssl-111-on-linux"></a>TLS 1.3 & OpenSSL 1.1.1 auf Linux

.NET Core nutzt nun die Unterstützung von [TLS 1.3 in OpenSSL 1.1.1.1](https://www.openssl.org/blog/blog/2018/09/11/release111/), wenn es in einer bestimmten Umgebung verfügbar ist. Gemäß dem [OpenSSL-Team](https://www.openssl.org/blog/blog/2018/09/11/release111/) hat TLS 1.3 viele Vorteile:

* Verbesserte Verbindungszeiten aufgrund einer Reduzierung der erforderlich Roundtrips zwischen Client und Server.

* Höhere Sicherheit durch das Entfernen verschiedener veralteter und unsicher Kryptografiealgorithmen und die Verschlüsselung von mehr des Verbindungshandshake.

.NET Core 3.0 Vorschauversion 1 kann **OpenSSL 1.1.1**, **OpenSSL 1.1.0** oder **OpenSSL 1.0.2** (was auch immer die geeignete Lösung ist) auf einem Linux-System verwenden.  Wenn **OpenSSL 1.1.1** verfügbar ist, verwenden „SslStream“- und „HttpClient“-Typen **TLS 1.3** bei der Nutzung von `SslProtocols.None` (systemseitige Standardprotokolle), sofern sowohl der Client als auch der Server **TLS 1.3** unterstützen.

Das folgende Beispiel veranschaulicht .NET Core 3.0 Vorschauversion 1 auf Ubuntu 18.10 beim Verbinden mit <https://www.cloudflare.com>:

```csharp
using System;
using System.Net.Security;
using System.Net.Sockets;
using System.Threading.Tasks;

namespace tlstest
{
    class Program
    {
        static async Task Main()
        {
            using (TcpClient tcpClient = new TcpClient())
            {
                string targetHost = "www.cloudflare.com";

                await tcpClient.ConnectAsync(targetHost, 443);

                using (SslStream sslStream = new SslStream(tcpClient.GetStream()))
                {
                    await sslStream.AuthenticateAsClientAsync(targetHost);
                    await Console.Out.WriteLineAsync($"Connected to {targetHost} with {sslStream.SslProtocol}");
                }
            }
        }
    }
}
```

```console
user@comp-ubuntu1810:~/tlstest$ dotnet run
Connected to www.cloudflare.com with Tls13
user@comp-ubuntu1810:~/tlstest$ openssl version
OpenSSL 1.1.1  11 Sep 2018
```

>[!IMPORTANT]
>Windows und macOS unterstützen **TLS 1.3** noch nicht. .NET Core 3.0 unterstützt **TLS 1.3** auf diesen Betriebssystemen, wenn entsprechender Support verfügbar ist.

## <a name="cryptography"></a>Kryptografie

Unterstützung für **AES-GCM**- und **AES-CCM**-Verschlüsselungen wurde hinzugefügt, implementiert über `System.Security.Cryptography.AesGcm` und `System.Security.Cryptography.AesCcm`. Diese Algorithmen sind beide [Authenticated Encryption with Association Data (AEAD)-Algorithmen](https://en.wikipedia.org/wiki/Authenticated_encryption) und die ersten Authenticated Encryption (AE)-Algorithmen, die zu .NET Core hinzugefügt wurden.

Der folgende Code veranschaulicht die Verwendung der **AesGcm**-Verschlüsselung zum Verschlüsseln und Entschlüsseln von Zufallsdaten.

Der Code für **AesCcm** würde fast identisch aussehen (nur der Variablenname der Klasse wäre anders).

```csharp
// key should be: pre-known, derived, or transported via another channel, such as RSA encryption
byte[] key = new byte[16];
RandomNumberGenerator.Fill(key);

byte[] nonce = new byte[12];
RandomNumberGenerator.Fill(nonce);

// normally this would be your data
byte[] dataToEncrypt = new byte[1234];
byte[] associatedData = new byte[333];
RandomNumberGenerator.Fill(dataToEncrypt);
RandomNumberGenerator.Fill(associatedData);

// these will be filled during the encryption
byte[] tag = new byte[16];
byte[] ciphertext = new byte[dataToEncrypt.Length];

using (AesGcm aesGcm = new AesGcm(key))
{
    aesGcm.Encrypt(nonce, dataToEncrypt, ciphertext, tag, associatedData);
}

// tag, nonce, ciphertext, associatedData should be sent to the other part

byte[] decryptedData = new byte[ciphertext.Length];

using (AesGcm aesGcm = new AesGcm(key))
{
    aesGcm.Decrypt(nonce, ciphertext, tag, decryptedData, associatedData);
}

// do something with the data
// this should always print that data is the same
Console.WriteLine($"AES-GCM: Decrypted data is{(dataToEncrypt.SequenceEqual(decryptedData) ? "the same as" : "different than")} original data.");
```

## <a name="cryptographic-key-importexport"></a>Importieren/Exportieren kryptografischer Schlüssel

.NET Core 3.0 Vorschauversion 1 unterstützt das Importieren und Exportieren der asymmetrischen öffentliche und private Schlüssel aus den Standardformaten, ohne dass ein x. 509-Zertifikat verwendet werden muss.

Alle Schlüsseltypen (RSA, DSA, ECDsa, ECDiffieHellman) unterstützten das Format **X.509 SubjectPublicKeyInfo** für öffentliche Schlüssel und die Formate **PKCS#8 PrivateKeyInfo** und **PKCS#8 EncryptedPrivateKeyInfo** für private Schlüssel. RSA unterstützt zudem **PKCS#1 RSAPublicKey** und **PKCS#1 RSAPrivateKey**. Die Exportmethoden erstellen alle DER-kodierte Binärdaten, und die Importmethoden erwarten dasselbe. Wenn ein Schlüssel im textfreundlichen PEM-Format gespeichert ist, muss der Anrufer den Inhalt base64-dekodieren, bevor er eine Importmethode aufruft.

```csharp
using System;
using System.IO;
using System.Security.Cryptography;

namespace rsakeyprint
{
    class Program
    {
        static void Main(string[] args)
        {
            using (RSA rsa = RSA.Create())
            {
                byte[] keyBytes = File.ReadAllBytes(args[0]);
                rsa.ImportRSAPrivateKey(keyBytes, out int bytesRead);
 
                Console.WriteLine($"Read {bytesRead} bytes, {keyBytes.Length-bytesRead} extra byte(s) in file.");
                RSAParameters rsaParameters = rsa.ExportParameters(true);
                Console.WriteLine(BitConverter.ToString(rsaParameters.D));
            }
        }
    }
}
```

```console
user@comp-ubuntu1810:~/rsakeyprint$ echo Making a small key to save on screen space.
Making a small key to save on screen space.
user@comp-ubuntu1810:~/rsakeyprint$ openssl genrsa 768 | openssl rsa -outform der -out rsa.key
Generating RSA private key, 768 bit long modulus (2 primes)
..+++++++
........+++++++
e is 65537 (0x010001)
writing RSA key
user@comp-ubuntu1810:~/rsakeyprint$ dotnet run rsa.key
Read 461 bytes, 0 extra byte(s) in file.
0F-D0-82-34-F8-13-38-4A-7F-C7-52-4A-F6-93-F8-FB-6D-98-7A-6A-04-3B-BC-35-8C-7D-AC-A5-A3-6E-AD-C1-66-30-81-2C-2A-DE-DA-60-03-6A-2C-D9-76-15-7F-61-97-57-
79-E1-6E-45-62-C3-83-04-97-CB-32-EF-C5-17-5F-99-60-92-AE-B6-34-6F-30-06-03-AC-BF-15-24-43-84-EB-83-60-EF-4D-3B-BD-D9-5D-56-26-F0-51-CE-F1
user@comp-ubuntu1810:~/rsakeyprint$ openssl rsa -in rsa.key -inform der -text -noout | grep -A7 private
privateExponent:
    0f:d0:82:34:f8:13:38:4a:7f:c7:52:4a:f6:93:f8:
    fb:6d:98:7a:6a:04:3b:bc:35:8c:7d:ac:a5:a3:6e:
    ad:c1:66:30:81:2c:2a:de:da:60:03:6a:2c:d9:76:
    15:7f:61:97:57:79:e1:6e:45:62:c3:83:04:97:cb:
    32:ef:c5:17:5f:99:60:92:ae:b6:34:6f:30:06:03:
    ac:bf:15:24:43:84:eb:83:60:ef:4d:3b:bd:d9:5d:
    56:26:f0:51:ce:f1
```

PKCS #8-Dateien können mit der `System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo`-Klasse überprüft werden.

PFX/PKCS#12-Dateien können mit `System.Security.Cryptography.Pkcs.Pkcs12Info` oder `System.Security.Cryptography.Pkcs.Pkcs12Builder` überprüft und bearbeitet werden.

## <a name="serialport-for-linux"></a>SerialPort für Linux

.NET Core 3.0 unterstützt jetzt <xref:System.IO.Ports.SerialPort?displayProperty=nameWithType> auf Linux.

Bisher unterstützte .NET Core nur die Verwendung des `SerialPort`-Typs auf Windows.

## <a name="more-bcl-improvements"></a>Weitere BCL-Verbesserungen

Die Typen `Span<T>`, `Memory<T>` und verwandte Typen, die in .NET Core 2.1 eingeführt wurden, wurden in .NET Core 3.0 optimiert. Allgemeine Vorgänge, wie die Bereichserstellung, Slicing, Analyse und Formatierung werden jetzt besser ausgeführt. 

Darüber hinaus haben Typen wie `String` indirekte Verbesserungen, um sie effizienter zu machen, wenn sie als Schlüssel mit `Dictionary<TKey, TValue>` und anderen Sammlungen verwendet werden. Um von diesen Verbesserungen zu profitieren, sind keine Codeänderungen erforderlich.

NET Core 3 Vorschauversion 1 enthält außerdem die folgenden Verbesserungen:

* In HttpClient integrierte Brotli-Unterstützung
* ThreadPool.UnsafeQueueWorkItem(IThreadPoolWorkItem)
* Unsafe.Unbox
* CancellationToken.Unregister
* Komplexe arithmetische Operatoren
* Socket-APIs für TCP-Keep-Alive
* StringBuilder.GetChunks
* IPEndPoint-Analyse
* RandomNumberGenerator.GetInt32

## <a name="tiered-compilation"></a>Mehrstufig Kompilierung

Die [mehrstufig Kompilierung](https://blogs.msdn.microsoft.com/dotnet/2018/08/02/tiered-compilation-preview-in-net-core-2-1/) ist bei .NET Core 3.0 standardmäßig aktiviert. Es ist ein Feature, das es der Runtime ermöglicht, den Just-In-Time (JIT)-Compiler adaptiver zu nutzen, um eine bessere Leistung zu erzielen, sowohl beim Start als auch zur Maximierung des Durchsatzes.

Dieses Feature wurde als abonnierbares Feature für [.NET Core 2.1](https://blogs.msdn.microsoft.com/dotnet/2018/05/30/announcing-net-core-2-1/) hinzugefügt, und anschließend standardmäßig in der [.NET Core 2.2 Vorschauversion 2](https://blogs.msdn.microsoft.com/dotnet/2018/09/12/announcing-net-core-2-2-preview-2/) aktiviert. Anschließend wurde es wieder zurückgesetzt, und ist mit dem Release von .NET Core 2.2 wieder abonnierbar.

## <a name="arm64-linux-support"></a>ARM64-Linux-Support

ARM64 für Linux wird nun unterstützt. Der primäre Anwendungsfall für ARM64 sind derzeit IoT-Szenarien.

Alpine-, Debian- und Ubuntu-[-Dockerimages sind für .NET Core für ARM64 verfügbar](https://hub.docker.com/r/microsoft/dotnet/).

Bitte lesen Sie für weitere Informationen [.NET Core-ARM64-Status](https://github.com/dotnet/announcements/issues/82)

>[!NOTE]
> **ARM64** wird von Windows noch nicht unterstützt.

## <a name="install-net-core-30-previews-on-linux-with-snap"></a>Installieren von .NET Core 3.0-Vorschauversionen unter Linux mit Snap

Snap ist die bevorzugte Methode zum Installieren und Testen von .NET Core-Vorschauversionen unter [Linux-Distributionen, die Snap unterstützen](https://docs.snapcraft.io/installing-snapd/6735).

Führen Sie nach dem Konfigurieren von Snap auf Ihrem System den folgenden Befehl aus, um das [.NET Core SDK 3.0 für die Vorschauversion](https://snapcraft.io/dotnet-sdk) zu installieren.

```console
sudo snap install dotnet-sdk --beta --classic
```
 
Wenn .NET Core mit dem Snap-Paket installiert wird, lautet der Standardbefehl für .NET Core `dotnet-sdk.dotnet` und nicht nur `dotnet`. Der Vorteil des Befehls mit dem Namespace besteht darin, dass keine Konflikte mit möglicherweise global installierten .NET Core-Versionen auftreten. Für diesen Befehl kann der Alias `dotnet` wie folgt erstellt werden:

```console
sudo snap alias dotnet-sdk.dotnet dotnet
```

Bei einigen Distributionen ist ein zusätzlicher Schritt zum Aktivieren des Zugriffs auf das SSL-Zertifikat erforderlich. Details finden Sie im Artikel zur [Einrichtung von Linux](https://github.com/dotnet/core/blob/master/Documentation/linux-setup.md).

## <a name="gpio-support-for-raspberry-pi"></a>GPIO-Unterstützung für Raspberry Pi

Über NuGet können nun zwei neue Pakete für die GPIO-Programmierung bezogen werden:

* [System.Device.Gpio](https://www.nuget.org/packages/System.Device.Gpio/0.1.0-prerelease.19078.2)
* [Iot.Device.Bindings](https://www.nuget.org/packages/Iot.Device.Bindings/0.1.0-prerelease.19078.2)

Die GPIO-Pakete enthalten APIs für GPIO-, SPI-, I2C- und PWM-Geräte. Das IoT-Bindungspaket enthält [Gerätebindungen](https://github.com/dotnet/iot/blob/master/src/devices/README.md) für verschiedene Chips und Sensoren. Dabei handelt es sich um die gleichen Bindungen, die unter [dotnet/iot – src/devices](https://github.com/dotnet/iot/tree/master/src/devices) verfügbar sind.

Die aktualisierten APIs für serielle Anschlüsse, die zusammen mit der Vorschauversion 1 von .NET Core 3.0 angekündigt wurden, sind nicht in diesen Paketen enthalten, stehen jedoch als Teil der .NET Core-Plattform zur Verfügung.


## <a name="platform-support"></a>Plattformunterstützung

.NET Core 3.0 wird auf den folgenden Betriebssystemen unterstützt:

* Windows-Client: 7, 8.1, 10 (1607 und höher)
* Windows Server: 20012 R2 SP1 und höher
* macOS: 10.12 und höher
* RHEL: 6 und höher
* Fedora: 26 und höher
* Ubuntu: 16.04 und höher
* Debian: 9 und höher
* SLES: 12 und höher
* openSUSE: 42.3+
* Alpine: 3.8+

Außerdem werden folgende Chiparchitekturen unterstützt:

* x64 unter Windows, macOS und Linux
* x86 unter Windows
* ARM32 unter Windows und Linux
* ARM64 unter Linux

Für Linux wird ARM32 unter Debian 9 und höher und Ubuntu 16.04 und höher unterstützt. Für ARM64 gilt das Gleiche wie für ARM32, jedoch wird zusätzlich Alpine 3.8 unterstützt. Es handelt sich um die gleichen Versionen der Distributionen, die auch für x64 unterstützt werden.

Docker-Images für .NET Core 3.0 sind unter [microsoft/dotnet im Docker-Hub](https://hub.docker.com/r/microsoft/dotnet/) verfügbar. Microsoft arbeitet aktuell an der Einführung der [Microsoft Container Registry (MCR)](https://cloudblogs.microsoft.com/opensource/2019/01/17/improved-discovery-experience-microsoft-containers-docker-hub/). Die finalen .NET Core 3.0-Images werden voraussichtlich nur dort veröffentlicht.
