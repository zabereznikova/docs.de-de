---
title: Neuerungen in .NET Core 3.0
description: Informationen zu den neuen Features in .NET Core 3.0.
dev_langs:
- csharp
- vb
author: thraka
ms.author: adegeo
ms.date: 12/04/2018
ms.openlocfilehash: 3ca833031eb8bb0f43a334f833f2e0075842d57d
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53156668"
---
# <a name="whats-new-in-net-core-30-preview-1"></a>Neuerungen in .NET Core 3.0 (Vorschauversion 1)

Dieser Artikel beschreibt die Neuerungen in .NET Core 3.0 (Vorschauversion 1). Eine der wichtigsten Verbesserungen ist die Unterstützung für Windows-Desktopanwendungen (nur Windows). Durch die Verwendung einer .NET Core 3.0-Komponente namens Windows Desktop können Sie Ihre Windows Forms Windows Presentation Foundation (WPF)-Anwendungen portieren. Die Windows Desktop-Komponente wird ausdrücklich nur für Windows unterstützt. Weitere Informationen finden Sie unten im Abschnitt [Windows Desktop](#windows-desktop).

.NET Core 3.0 bietet Unterstützung für C# 8.0.

[Sie können .NET Core 3 Vorschauversion 1 jetzt für Windows, Mac und Linux herunterladen und sofort starte.](https://aka.ms/netcore3download) Alle Details zu diesem Release finden Sie in den [Versionshinweisen zu .NET Core 3 Vorschauversion 1](https://aka.ms/netcore3releasenotes).

Weitere Informationen finden Sie unter [Ankündigung zu .NET Core 3.0 Vorschauversion 1](https://blogs.msdn.microsoft.com/dotnet/2018/12/04/announcing-net-core-3-preview-1-and-open-sourcing-windows-desktop-frameworks/).

## <a name="net-standard-21"></a>.NET Standard 2.1

.NET Core 3.0 implementiert .NET Standard 2.1.

## <a name="default-executables"></a>Standardmäßig ausführbare Dateien

.NET Core erstellt die ausführbaren Dateien jetzt standardmäßig. Dies ist neu für Anwendungen, die eine global installierte Version von .NET Core verwenden. Bis jetzt hatten nur [eigenständige Bereitstellungen](../deploying/index.md#self-contained-deployments-scd) ausführbare Dateien.

Während `dotnet build` oder `dotnet publish` wird eine ausführbare Datei erstellt, die der Umgebung und Plattform des von Ihnen verwendeten SDKs entspricht. Diese ausführbaren Dateien bieten Ihnen die gleichen Möglichkeiten wie andere native ausführbare Dateien, wie z.B.:

* Sie können die ausführbare Datei doppelklicken.
* Sie können die Anwendung direkt aus einer Eingabeaufforderung starten, z.B. `myapp.exe` unter Windows und `./myapp` unter Linux und MacOS.

> [!NOTE]
> Die Angabe einer bestimmten Runtime mit `dotnet publish -r`- oder `dotnet build -r`-Argumenten für andere Runtimeumgebungen wird nicht unterstützt.

## <a name="build-copies-dependencies"></a>Build kopiert Abhängigkeiten

`dotnet build` kopiert jetzt NuGet-Abhängigkeiten für Ihre Anwendung aus dem NuGet-Cache in den Buildausgabeordner. Bisher wurde Abhängigkeiten nur als Teil von `dotnet publish` kopiert. 

Es gibt einige Vorgänge, wie das Verlinken und das Veröffentlichen von Razor-Seiten, die noch veröffentlicht werden müssen.


## <a name="local-dotnet-tools"></a>Lokale dotnet-Tools

.NET Core 2.1 unterstützt globale Tools, .NET Core 3.0 verfügt jetzt über lokale Tools. Lokale Tools ähneln globalen Tools, sind aber mit einem bestimmten Speicherort auf dem Datenträger verknüpft. Dies ermöglicht die Bereitstellung von Tools für einzelne Projekte und Repositorys. Jedes lokal installierte Tool ist nicht global verfügbar.

Lokale Tools basieren auf einer Manifestdatei `dotnet-tools.json` in Ihrem aktuellen Verzeichnis. Diese Manifestdatei definiert die verfügbaren Tools. Durch die Erstellung dieser Manifestdatei im Stammverzeichnis Ihres Repositorys stellen Sie sicher, dass jeder, der Ihren Code klont, die Tools wiederherstellen und verwenden kann, die für eine erfolgreiche Arbeit mit Ihrem Code erforderlich sind.

Wenn die Manifestdatei für lokale Tools verfügbar ist, verwenden Sie den folgenden Befehl, um diese Tools automatisch herunterzuladen und lokal zu installieren:

```console
dotnet tool restore
```

Führen Sie ein lokales Tool mit dem folgenden Befehl aus:

```console
dotnet tool run <tool-command-name>
```

Wenn ein lokales Tool aufgerufen wird, sucht dotnet nach einer Manifestdatei in der Verzeichnisstruktur. Wenn eine Manifestdatei für das Tool gefunden wurde, wird diese nach dem erforderlichen Tool durchsucht. Wenn das Tool gefunden wird, enthält es die Informationen, die benötigt werden, um das Tool am Speicherort der globalen NuGet-Pakete zu finden. 

Wenn das Tool in der Manifestdatei, aber nicht im Cache gefunden wird, erhält der Benutzer eine Fehlermeldung. Diese Meldung wird nach der Vorschauversion 1 verbessert, damit der Benutzer `dotnet tool restore` ausführen muss.

Um lokale Tools zu einem Verzeichnis hinzuzufügen, müssen Sie zuerst die Manifestdatei für das Tool erstellen. Nach der Vorschauversion 1 werden wir einen Mechanismus zum Erstellen von Manifestdateien für das Tool anbieten, wie z.B. eine neue dotnet-Vorlage. Für die Vorschauversion 1 müssen Sie eine Datei mit dem `dotnet-tools.json` und folgendem Inhalt erstellen:

```json
{
  "version": 1,
  "isRoot": true,
  "tools": {}
}
```

Wenn die Manifestdatei erstellt wurde, können Sie folgendermaßen lokale Tools hinzufügen:

```console
dotnet tool install <toolPackageId>
```

Dieser Befehl installiert die neueste Version des Tools, sofern keine andere Version angegeben ist.  Auch wenn die neueste Version automatisch ausgewählt wurde, wird die Version des Tools in die Manifestdatei des Tools geschrieben, damit die korrekte Version des Tools wiederhergestellt oder ausgeführt werden kann.

Die Manifestdatei des Tools ist so konzipiert, dass sie eine manuelle Bearbeitung ermöglicht. Sie müssen die Datei bearbeiten, um die erforderliche Version für die Arbeit mit dem Repository zu aktualisieren.

Hier ist ein Beispiel für eine `dotnet-tools.json`-Datei:

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

Um ein Tool aus der Manifestdatei des Tools zu entfernen, führen Sie den folgenden Befehl aus:

```console
dotnet tool uninstall <toolPackageId>
```

Für sowohl globale als auch lokale Tools ist eine kompatible Version der Runtime erforderlich. Die meisten Tools führen derzeit NuGet.org target .NET Core Runtime 2.1 aus. Um diese global oder lokal zu installieren, müssten Sie weiterhin die [NET Core 2.1-Runtime](https://dotnet.microsoft.com/download/dotnet-core/2.1) installieren.

Weitere Informationen finden Sie unter [Frühe Vorschaudokumentation für lokale Tools](https://github.com/dotnet/cli/issues/10288).

## <a name="windows-desktop"></a>Windows Desktop

Ab .NET Core 3.0 Vorschauversion 1 können Sie Windows Desktop-Anwendungen mit WPF und Windows Forms erstellen. Diese Frameworks unterstützt auch die Verwendung moderner Steuerelemente und des Fluent-Stils aus der Windows-UI-XAML-Bibliothek (WinUI) über [XAML-Inseln](/windows/uwp/xaml-platform/xaml-host-controls).

Die Windows Desktop-Komponente ist Teil des Windows .NET Core 3.0 SDK.

Mit dem folgenden `dotnet`-Befehl können Sie eine neue WPF- oder Windows Forms-Anwendung erstellen:

```console
dotnet new wpf
dotnet new winforms
```

Sie können auch.NET Core 3.0 WPF- und Windows Forms-Projekte in Visual Studio 2019 Vorschauversion 1 öffnen, starten und debuggen. Derzeit können diese Projekte in Visual Studio 2017 15.9 geöffnet werden, das Szenario wird allerdings nicht unterstützt (und Sie müssen [Vorschauversionen aktivieren](https://blogs.msdn.microsoft.com/dotnet/2018/11/13/net-core-tooling-update-for-visual-studio-2017-version-15-9/)).

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

## <a name="fast-built-in-json-support"></a>Schneller integrierter JSON-Support

`System.Text.Json.Utf8JsonReader` ist ein leistungsstarker, reiner Vorwärtsleser mit geringer Zuordnung für UTF-8-kodierten JSON-Text, der von einem `ReadOnlySpan<byte>` gelesen wird. Der `Utf8JsonReader` ist ein grundlegender, Low-Level-Typ, der zum Erstellen von benutzerdefinierten Parsern und Fehler beim Erstellen des Deserialisierungsprogramms genutzt werden kann. Das Durchlesen einer JSON-Nutzlast mit dem neuen `Utf8JsonReader` ist 2x schneller als mit dem Leser von [Json.NET](https://www.newtonsoft.com/json). Es wird erst dann zugewiesen, wenn Sie JSON-Token als (UTF-16)-Zeichenfolgen aktualisieren müssen.

Diese neue API umfasst die folgenden Komponenten:

* In Vorschauversion 1: JSON-Leser (sequenzieller Zugriff)
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

Das .NET-Ökosystem basiert auf [Json.NET](https://www.newtonsoft.com/json) und anderen beliebten JSON-Bibliotheken, die weiterhin eine gute Wahl sind. JSON.NET verwendet .NET-Zeichenfolgen als den Basisdatentyp, die intern UTF-16 sind. 

In .NET Core 2.1 und 3.0 haben wir neue APIs hinzugefügt, die es ermöglichen, JSON-APIs (z.B. `Utf8JsonReader`) zu schreiben, die viel weniger Speicher benötigen, basierend auf der Verwendung von `Span<T>` und UTF-8-Zeichenfolgen, und die die Anforderungen von Anwendungen mit hohem Durchsatz wie Kestrel, ASP.NET Core Webserver besser erfüllen.

## <a name="ranges-and-indices"></a>Bereiche und Indizes

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

> [!NOTE]
> Nur [ C# 8.0](https://blogs.msdn.microsoft.com/dotnet/2018/11/12/building-c-8-0/) unterstützt die Syntax für `Range` und `Index`.

## <a name="async-streams"></a>Asynchrone Datenströme

Die `IAsyncEnumerable<T>`-Typ ist eine neue asynchrone Version von `IEnumerable<T>`. Mit der Sprache können Sie `await foreach` dafür ausführen, um diese Elemente zu verarbeiten, und dann `yield return` verwenden, um Elemente zu erstellen.

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

> [!WARNING]
> Bei .NET Core 3.0 Vorschauversion 1 tritt derzeit ein Fehler bei `await foreach` auf. Verwenden Sie stattdessen `GetEnumerator` und `MoveNext` für die Verarbeitung von Elementen. Weitere Informationen finden Sie unter [roslyn/#31268](https://github.com/dotnet/roslyn/issues/31268).

Zusätzlich zu `await foreach` können Sie auch asynchrone Iteratoren erstellen, z.B. einen Iterator, der `IAsyncEnumerable/IAsyncEnumerator` zurückgibt, in den Sie sowohl `await` als auch `yield` einfügen können. Für Objekte, die gelöscht werden müssen, können Sie `IAsyncDisposable` verwenden, das von verschiedenen BCL-Typen implementiert wird, wie beispielsweise `Stream` und `Timer`.

> [!NOTE]
> Nur [ C# 8.0](https://blogs.msdn.microsoft.com/dotnet/2018/11/12/building-c-8-0/) unterstützt die `await foreach`-Syntax.

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

Mit diesem Release haben wir Support für ARM64 für Linux hinzugefügt. Wir haben den Support für ARM32 für Linux mit .NET Core 2.1 und Windows mit .NET Core 2.2 hinzugefügt. Der primäre Anwendungsfall für ARM64 sind derzeit IoT-Szenarien.

Alpine-, Debian- und Ubuntu-[-Dockerimages sind für .NET Core für ARM64 verfügbar](https://hub.docker.com/r/microsoft/dotnet/).

Bitte lesen Sie für weitere Informationen [.NET Core-ARM64-Status](https://github.com/dotnet/announcements/issues/82)

>[!NOTE]
> **ARM64** wird von Windows noch nicht unterstützt.
