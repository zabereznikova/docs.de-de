---
title: Neuerungen in .NET Core 3.0
description: Informationen zu den neuen Features in .NET Core 3.0.
dev_langs:
- csharp
author: thraka
ms.author: adegeo
ms.date: 01/27/2020
ms.openlocfilehash: 6e85c2c3e796ae59a13f944bd4913e4b7316c56a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79397824"
---
# <a name="whats-new-in-net-core-30"></a>Neuerungen in .NET Core 3.0

In diesem Artikel werden Neuerungen in .NET Core 3.0 beschrieben. Eine der wichtigsten Verbesserungen ist die Unterstützung für Windows-Desktopanwendungen (nur Windows). Mit der .NET Core 3.0 SDK-Komponente Windows Desktop können Sie Ihre Windows Forms- und WPF-Anwendungen (Windows Presentation Foundation) portieren. Die Windows Desktop-Komponente wird ausdrücklich nur für Windows unterstützt und ist nur unter Windows enthalten. Weitere Informationen finden Sie im Abschnitt [Windows-Desktop](#windows-desktop) weiter unten in diesem Artikel.

.NET Core 3.0 bietet Unterstützung für C# 8.0. Es wird dringend empfohlen, [Visual Studio 2019 Version 16.3](https://visualstudio.microsoft.com/vs/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) oder höher, [Visual Studio für Mac 8.3](/visualstudio/mac/install-preview) oder höher oder [Visual Studio Code](https://code.visualstudio.com/) mit der neuesten **C#-Erweiterung** zu verwenden.

[Sie können .NET Core 3.0 jetzt für Windows, macOS oder Linux herunterladen und sofort starten](https://aka.ms/netcore3download).

Weitere Informationen zu diesem Release finden Sie unter [Ankündigung von .NET Core 3.0](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-0/).

.NET Core RC1 wurde von Microsoft als produktionsbereit betrachtet und vollständig unterstützt. Wenn Sie eine Vorschauversion verwenden, müssen Sie für die weitere Unterstützung zur Version RTM wechseln.

## <a name="language-improvements-c-80"></a>Sprachverbesserungen in C# 8.0

C# 8.0 ist ebenfalls Teil dieses Releases, welches das Feature mit [Referenztypen, die NULL-Werte zulassen](../../csharp/tutorials/nullable-reference-types.md), [asynchrone Datenströme](../../csharp/tutorials/generate-consume-asynchronous-stream.md) und [weitere Muster](../../csharp/tutorials/pattern-matching.md) enthält. Weitere Informationen zu Features von C# 8.0 finden Sie unter [Neues in C# 8.0](../../csharp/whats-new/csharp-8.md).

Es wurden Spracherweiterungen hinzugefügt, um die folgenden API-Features zu unterstützen:

- [Bereiche und Indizes](#ranges-and-indices)
- [Asynchrone Datenströme](#async-streams)

## <a name="net-standard-21"></a>.NET Standard 2.1

.NET Core 3.0 implementiert **.NET Standard 2.1**. Dennoch generiert die Standardvorlage `dotnet new classlib` weiterhin ein Projekt für **.NET Standard 2.0**. Ändern Sie für **.NET Standard 2.1** in Ihrer Projektdatei die `TargetFramework`-Eigenschaft in `netstandard2.1`:

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TargetFramework>netstandard2.1</TargetFramework>
  </PropertyGroup>

</Project>
```

Wenn Sie Visual Studio verwenden, benötigen Sie [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019), da Visual Studio 2017 **.NET Standard 2.1** und **.NET Core 3.0** nicht unterstützt.

## <a name="compiledeploy"></a>Kompilieren/bereitstellen

### <a name="default-executables"></a>Standardmäßig ausführbare Dateien

.NET Core erstellt nun standardmäßig [Runtime-abhängige ausführbare Dateien](../deploying/index.md#publish-runtime-dependent). Dieses Verhalten ist neu für Anwendungen, die eine global installierte Version von .NET Core verwenden. Vorher produzierten nur [eigenständige Bereitstellungen](../deploying/index.md#publish-self-contained) eine ausführbare Datei.

Während `dotnet build` oder `dotnet publish` wird eine ausführbare Datei (**appHost**) erstellt, die der Umgebung und Plattform des von Ihnen verwendeten SDKs entspricht. Diese ausführbaren Dateien bieten Ihnen die gleichen Möglichkeiten wie andere native ausführbare Dateien, wie z.B.:

- Sie können die ausführbare Datei doppelklicken.
- Sie können die Anwendung direkt aus einer Eingabeaufforderung starten, z.B. `myapp.exe` unter Windows und `./myapp` unter Linux und MacOS.

### <a name="macos-apphost-and-notarization"></a>macOS-appHost und -Notarisierung

*nur unter macOS*

Ab dem notarisierten .NET Core SDK 3.0 für macOS ist die Einstellung zum Erstellen einer ausführbaren Standarddatei („appHost“) standardmäßig deaktiviert. Weitere Informationen finden Sie unter [macOS Catalina-Notarisierung und die Auswirkungen auf .NET Core-Downloads und -Projekte](../install/macos-notarization-issues.md).

Wenn die appHost-Einstellung aktiviert ist, erzeugt .NET Core eine native ausführbare Mach-O-Datei, wenn Sie einen Build- oder Veröffentlichungsprozess ausführen. Ihre App wird im Kontext von appHost ausgeführt, wenn sie mit dem Befehl `dotnet run` über den Quellcode oder durch direktes Starten der ausführbaren Mach-O-Datei ausgeführt wird.

Ohne die appHost-Datei können Benutzer eine [Runtime-abhängige](../deploying/index.md#publish-runtime-dependent) App nur mit dem Befehl `dotnet <filename.dll>` starten. Es wird immer eine appHost-Datei erstellt, wenn Sie Ihre App [eigenständig](../deploying/index.md#publish-self-contained) veröffentlichen.

Sie können die appHost-Datei entweder auf Projektebene konfigurieren oder für einen spezifischen `dotnet`-Befehl mit dem `-p:UseAppHost`-Parameter aktivieren:

- Projektdatei

  ```xml
  <PropertyGroup>
    <UseAppHost>true</UseAppHost>
  </PropertyGroup>
  ```

- Befehlszeilenparameter

  ```dotnetcli
  dotnet run -p:UseAppHost=true
  ```

Weitere Informationen über die `UseAppHost`-Einstellung finden Sie unter [MSBuild-Eigenschaften für Microsoft.NET.Sdk](../project-sdk/msbuild-props.md#useapphost).

### <a name="single-file-executables"></a>Ausführbare Einzeldateien

Der `dotnet publish`-Befehl unterstützt das Verpacken der App in einer plattformspezifischen ausführbaren Einzeldatei. Die ausführbare Datei ist selbstextrahierend und enthält alle Abhängigkeiten (einschließlich der nativen), die zum Ausführen der App erforderlich sind. Beim ersten Ausführen der App wird die Anwendung in ein Verzeichnis extrahiert, das auf dem Namen und dem Buildbezeichner der App basiert. Der Start ist beim erneuten Ausführen der App schneller. Die Anwendung muss sich nicht selbst ein zweites Mal extrahieren, sofern keine neue Version verwendet wird.

Legen Sie zum Veröffentlichen einer einzelnen ausführbaren Datei `PublishSingleFile` in Ihrem Projekt oder in der Befehlszeile mit dem `dotnet publish`-Befehl fest:

```xml
<PropertyGroup>
  <RuntimeIdentifier>win10-x64</RuntimeIdentifier>
  <PublishSingleFile>true</PublishSingleFile>
</PropertyGroup>
```

- oder -

```dotnetcli
dotnet publish -r win10-x64 -p:PublishSingleFile=true
```

Weitere Informationen zum Veröffentlichen einzelner Dateien finden Sie im [Einzeldatei-Bundler-Entwurfsdokument](https://github.com/dotnet/designs/blob/master/accepted/single-file/design.md).

### <a name="assembly-linking"></a>Verknüpfen von Assemblys

Das.NET Core 3.0 SDK bietet ein Tool, das die Größe von Apps reduzieren kann, indem es IL analysiert und ungenutzte Assemblys trimmt.

Eigenständige Apps enthalten alles, was zum Ausführen Ihres Codes benötigt wird, ohne dass .NET auf dem Hostcomputer installiert sein muss. Allerdings benötigt die App oft nur eine kleine Teilmenge des Frameworks, um zu funktionieren, sodass andere ungenutzte Bibliotheken entfernt werden können.

.NET Core bietet nun eine Einstellung, die das Tool [IL linker](https://github.com/mono/linker) verwendet, um die IL Ihrer App zu untersuchen. Dieses Tool erkennt, welcher Code erforderlich ist, und trimmt dann ungenutzte Bibliotheken. Es kann die Bereitstellungsgröße einiger Apps deutlich reduzieren.

Fügen Sie die Einstellung `<PublishTrimmed>` zu Ihrem Projekt hinzu, und veröffentlichen Sie eine eigenständige App, um dieses Tool zu aktivieren:

```xml
<PropertyGroup>
  <PublishTrimmed>true</PublishTrimmed>
</PropertyGroup>
```

```dotnetcli
dotnet publish -r <rid> -c Release
```

Als Beispiel erreicht die inbegriffene Standardvorlage für neue Konsolenprojekte „hello world“ bei ihrer Veröffentlichung eine Größe von ca.70 MB. Mithilfe von `<PublishTrimmed>` wird diese Größe auf ca. 30 MB reduziert.

Wichtig ist die Tatsache, dass Anwendungen oder Frameworks (einschließlich ASP.NET Core und WPF), die Reflektion oder verwandte dynamische Funktionen verwenden, nach dem Trimmen oft nicht mehr funktionieren. Dies ist der Fall, weil der Linker von diesem dynamischen Verhalten nichts weiß und nicht bestimmen kann, welche Frameworktypen für die Reflektion benötigt werden. Das Tool IL Linker kann so konfiguriert werden, dass es sich dieses Szenarios bewusst ist.

Nach dem Trimmen müssen Sie Ihre App unbedingt testen.

Weitere Informationen zum Tool IL Linker finden Sie in der [Dokumentation](https://aka.ms/dotnet-illink), oder besuchen Sie das Repository [mono/linker]( https://github.com/mono/linker).

### <a name="tiered-compilation"></a>Mehrstufig Kompilierung

Die [mehrstufige Kompilierung](https://github.com/dotnet/runtime/blob/master/docs/design/features/tiered-compilation-guide.md) (Tiered Compilation, TC) ist bei .NET Core 3.0 standardmäßig aktiviert. Dieses Feature ermöglicht der Runtime, den Just-In-Time-Compiler (JIT) adaptiver zu nutzen, um eine bessere Leistung zu erzielen.

Der Hauptvorteil der mehrstufigen Kompilierung (TC, Tiered Compilation) besteht darin, dass sie zwei Methoden zur Just-in-Time-Kompilierung bietet: in einer Stufe mit geringerer Qualität, die aber schneller ist, oder in einer Stufe mit höherer Qualität, die aber langsamer ist. Die Qualität bezieht sich darauf, wie gut die Methode optimiert ist. Die TC verbessert die Leistung einer Anwendung, während sie verschiedene Phasen der Ausführung vom Start bis zum stabilen Zustand durchläuft. Wenn die TC deaktiviert ist, wird jede Methode auf eine einzige Weise kompiliert, die auf eine stabile Leistung gegenüber der Startleistung ausgerichtet ist.

Wenn TC aktiviert ist, gilt beim Start einer App das folgende Verhalten für die Methodenkompilierung:

- Wenn die Methode über AOT-kompilierten Code oder [ReadyToRun](#readytorun-images) verfügt, wird der zuvor generierte Code verwendet.
- Andernfalls wird die Methode mit JIT kompiliert. In der Regel sind diese Methoden Generics über Werttypen.
  - *Quick JIT* erzeugt schneller Code geringerer Qualität (oder weniger optimiert). In .NET Core 3.0 ist Quick JIT standardmäßig für Methoden aktiviert, die keine Schleifen enthalten. Während des Starts wird dies bevorzugt.
  - Die vollständig optimierte Just-In-Time-Kompilierung erzeugt Code höherer Qualität (oder besser optimierten Code), ist aber langsamer. Für Methoden, bei denen die schnelle JIT-Kompilierung nicht verwendet werden würde (beispielsweise dann, wenn die Methode das Attribut <xref:System.Runtime.CompilerServices.MethodImplOptions.AggressiveOptimization?displayProperty=nameWithType> aufweist), wird die vollständig optimierte JIT-Kompilierung verwendet.

Bei häufig aufgerufenen Methoden erzeugt der Just-in-Time-Compiler schließlich vollständig optimierten Code im Hintergrund. Der optimierte Code ersetzt dann den vorkompilierten Code für diese Methode.

Code, der von der schnellen JIT-Kompilierung generiert wurde, wird möglicherweise langsamer ausgeführt, belegt mehr Arbeitsspeicher oder nutzt mehr Stapelspeicher. Wenn es Probleme gibt, können Sie Quick JIT mit dieser MSBuild-Eigenschaft in der Projektdatei deaktivieren:

```xml
<PropertyGroup>
  <TieredCompilationQuickJit>false</TieredCompilationQuickJit>
</PropertyGroup>
```

Verwenden Sie diese MSBuild-Eigenschaft in der Projektdatei, um die TC vollständig zu deaktivieren:

```xml
<PropertyGroup>
  <TieredCompilation>false</TieredCompilation>
</PropertyGroup>
```

> [!TIP]
> Wenn Sie diese Einstellungen in der Projektdatei ändern, müssen Sie möglicherweise einen bereinigten Build durchführen, damit die neuen Einstellungen reflektiert werden. (Löschen Sie die Verzeichnisse `obj` und `bin`, und erstellen Sie diese neu).

Weitere Informationen zum Konfigurieren der Kompilierung zur Laufzeit finden Sie unter [Laufzeitkonfigurationsoptionen für die Kompilierung](../run-time-config/compilation.md).

### <a name="readytorun-images"></a>ReadyToRun-Images

Sie können die Startzeit Ihrer.NET Core-Anwendung beschleunigen, indem Sie Ihre Anwendungsassemblys im R2R-Format (ReadyToRun) kompilieren. R2R ist eine Form der AOT-Kompilierung (Ahead-Of-Time).

R2R-Binärdateien verbessern die Startleistung, indem sie den Arbeitsaufwand des JIT-Compilers (Just-in-time) reduzieren, der anfällt, wenn Ihre Anwendung geladen wird. Die Binärdateien enthalten ähnlichen nativen Code im Vergleich zu dem, was der JIT-Compiler produzieren würde. R2R-Binärdateien sind jedoch größer, da sie sowohl IL-Code (Intermediate Language, Zwischensprache), der für einige Szenarios noch benötigt wird, als auch die native Version des gleichen Codes enthalten. R2R ist nur verfügbar, wenn Sie eine eigenständige Anwendung veröffentlichen, die eine bestimmte Laufzeitumgebung (RID) wie Linux x64 oder Windows x64 als Ziel hat.

Gehen Sie folgendermaßen vor, um Ihr Projekt als „ReadyToRun“ (Bereit zur Ausführung) zu kompilieren:

01. Fügen Sie die `<PublishReadyToRun>`-Einstellung in Ihr Projekt ein.

    ```xml
    <PropertyGroup>
      <PublishReadyToRun>true</PublishReadyToRun>
    </PropertyGroup>
    ```

01. Veröffentlichen Sie eine eigenständige App. Dieser Befehl erstellt beispielsweise eine eigenständige App für die 64-Bit-Version von Windows:

    ```dotnetcli
    dotnet publish -c Release -r win-x64 --self-contained
    ```

#### <a name="cross-platformarchitecture-restrictions"></a>Plattformübergreifende bzw. architekturbezogene Einschränkungen

Der ReadyToRun-Compiler unterstützt derzeit nicht die versionsübergreifende Angabe von Zielen. Die Kompilierung muss für ein bestimmtes Ziel erfolgen. Wenn Sie beispielsweise R2R-Images für Windows x64 benötigen, müssen Sie den Veröffentlichungsbefehl in dieser Umgebung ausführen.

Ausnahmen für die versionsübergreifende Angabe von Zielen:

- Windows x64 kann verwendet werden, um Windows ARM32-, ARM64- und x86-Images zu kompilieren.
- Windows x86 kann verwendet werden, um Windows ARM32-Images zu kompilieren.
- Linux X64 kann verwendet werden, um Linux ARM32- und -ARM64-Images zu kompilieren.

## <a name="runtimesdk"></a>Runtime/SDK

### <a name="major-version-runtime-roll-forward"></a>Runtimerollforward der Hauptversion

Mit .NET Core 3.0 wird ein Aktivierungsfeature eingeführt, das Ihrer App ein Rollforward auf die neueste Hauptversion von .NET Core ermöglicht. Darüber hinaus wurde eine neue Einstellung hinzugefügt, um zu steuern, wie ein Rollforward auf Ihre App angewendet wird. Diese kann folgendermaßen konfiguriert werden:

- Projektdateieigenschaft: `RollForward`
- Eigenschaft der Runtimekonfigurationsdatei: `rollForward`
- Umgebungsvariable: `DOTNET_ROLL_FORWARD`
- Befehlszeilenargument: `--roll-forward`

Einer der folgenden Werte muss angegeben werden. Wenn die Einstellung ausgelassen wird, ist **Minor** die Standardeinstellung.

- **LatestPatch**\
Rollforward zur höchsten Patchversion. Dies deaktiviert ein Rollforward zur Nebenversion.
- **Minor**\
Rollforward zur niedrigsten höheren Nebenversion, wenn die angeforderte Nebenversion nicht vorhanden ist. Wenn die angeforderte Nebenversion vorhanden ist, wird die **LatestPatch**-Richtlinie verwendet.
- **Major**\
Rollforward zur niedrigsten höheren Hauptversion – und niedrigsten Nebenversion, wenn die angeforderte Hauptversion nicht vorhanden ist. Wenn die angeforderte Hauptversion vorhanden ist, wird die **Minor**-Richtlinie verwendet.
- **LatestMinor**\
Rollforward zur höchsten Nebenversion – auch dann, wenn die angeforderte Nebenversion vorhanden ist. Für Komponentenhostingszenarien vorgesehen.
- **LatestMajor**\
Rollforward zur höchsten Hauptversion und höchsten Nebenversion – auch dann, wenn die angeforderte Hauptversion vorhanden ist. Für Komponentenhostingszenarien vorgesehen.
- **Disable**\
Kein Rollforward. Nur Binden an angegebene Version. Diese Richtlinie wird nicht zur allgemeinen Verwendung empfohlen, da sie die Möglichkeit eines Rollforwards zu den neuesten Patches ausschließt. Dieser Wert wird nur zu Testzwecken empfohlen.

Abgesehen von der **Disable**-Einstellung verwenden alle Einstellungen die höchste verfügbare Patchversion.

### <a name="build-copies-dependencies"></a>Build kopiert Abhängigkeiten

Der `dotnet build`-Befehl kopiert jetzt NuGet-Abhängigkeiten für Ihre Anwendung aus dem NuGet-Cache in den Buildausgabeordner. Bisher wurde Abhängigkeiten nur als Teil von `dotnet publish` kopiert.

Es gibt einige Vorgänge, wie das Verlinken und das Veröffentlichen von Razor-Seiten, die noch veröffentlicht werden müssen.

### <a name="local-tools"></a>Lokale Tools

Mit .NET Core 3.0 werden lokale Tools eingeführt. Lokale Tools ähneln [globalen Tools](../tools/global-tools.md), sind aber mit einem bestimmten Speicherort auf dem Datenträger verknüpft. Lokale Tools sind nicht global verfügbar und werden als NuGet-Pakete verteilt.

> [!WARNING]
> Wenn Sie lokale Tools in .NET Core 3.0 Preview 1 ausprobiert haben, z.B. Ausführung von `dotnet tool restore` oder `dotnet tool install`, löschen Sie den Cacheordner der lokalen Tools. Andernfalls funktionieren die lokalen Tools nicht in einem neueren Release. Je nach Betriebssystem werden die Ordnerpfade wie folgt gelöscht:
>
> Unter macOS, Linux: `rm -r $HOME/.dotnet/toolResolverCache`
>
> Windows: `rmdir /s %USERPROFILE%\.dotnet\toolResolverCache`

Lokale Tools basieren auf einer Manifestdatei `dotnet-tools.json` in Ihrem aktuellen Verzeichnis. In dieser Manifestdatei werden die Tools festgelegt, die im Verzeichnis und in den Unterverzeichnissen verfügbar sind. Sie können die Manifestdatei mit dem Code verteilen, um sicherzustellen, dass jeder Benutzer, der mit Ihrem Code arbeitet, dieselben Tools wiederherstellen und verwenden kann.

Für sowohl globale als auch lokale Tools ist eine kompatible Version der Runtime erforderlich. Die meisten Tools führen derzeit NuGet.org target .NET Core Runtime 2.1 aus. Um diese Tools global oder lokal zu installieren, müssten Sie weiterhin die [NET Core 2.1-Runtime](https://dotnet.microsoft.com/download/dotnet-core/2.1) installieren.

### <a name="new-globaljson-options"></a>Neue global.json-Optionen

Die Datei *global.json* verfügt über neue Optionen, die mehr Flexibilität bei der Definition der verwendeten .NET Core SDK-Version bieten. Folgende neue Optionen sind verfügbar:

- `allowPrerelease`: Gibt an, ob der SDK-Resolver bei der Auswahl der zu verwendenden SDK-Version Vorabversionen berücksichtigen soll.
- `rollForward`: Gibt die Rollforwardrichtlinie an, die beim Auswählen einer SDK-Version verwendet werden soll, entweder als Fallback, wenn eine bestimmte SDK-Version fehlt, oder als Anweisung, damit eine höhere Version verwendet wird.

Weitere Informationen zu den Änderungen, einschließlich Standardwerten, unterstützten Werten und neuen Abgleichsregeln, finden Sie unter [global.json: Übersicht](../tools/global-json.md).

### <a name="smaller-garbage-collection-heap-sizes"></a>Kleinere Garbage Collection-Heapgrößen

Die Standardheapgröße des Garbage Collectors wurde reduziert, sodass .NET Core weniger Arbeitsspeicher benötigt. Diese Änderung entspricht eher dem Zuordnungsbudget von Generation 0 mit modernen Prozessorcachegrößen.

### <a name="garbage-collection-large-page-support"></a>Garbage Collection: Unterstützung von „Large Pages“

„Large Pages“ (umfangreiche Seiten, unter Linux auch als „Huge Pages“ bekannt) ist eine Funktion, die dem Betriebssystem ermöglicht, Speicherbereiche einzurichten, die die native Seitengröße (häufig 4KB) überschreiten, um die Leistung der Anwendung zu verbessern, die diese große Seiten anfordert.

Der Garbage Collector kann nun mit der Einstellung **GCLargePages** als Aktivierungsfeature zum Auswählen der Zuordnung großer Seiten auf Windows konfiguriert werden.

## <a name="windows-desktop--com"></a>Windows Desktop und COM

### <a name="net-core-sdk-windows-installer"></a>Windows Installer von .NET Core SDK

Das MSI-Installationsprogramm für Windows wurde ab .NET Core 3.0 geändert. Die SDK-Installer aktualisieren nun vorhandene Releases von SDK-Featuregruppen. Featuregruppen werden in den *Hundertergruppen* des *Patchabschnitts* der Versionsnummer definiert. **3.0._101_** und **3.0._201_** sind beispielsweise Versionen in zwei verschiedenen Featuregruppen, während sich **3.0._101_** und **3.0._199_** in derselben Featuregruppe befinden. Wenn .NET Core SDK **3.0._101_** installiert wird, wird .NET Core SDK **3.0._100_** (sofern vorhanden) vom Computer entfernt. Wenn .NET Core SDK **3.0._200_** auf demselben Computer installiert ist, wird .NET Core SDK **3.0._101_** nicht entfernt.

Weitere Informationen zur Versionsverwaltung finden Sie unter [Übersicht über die .NET Core-Versionsverwaltung](../versions/index.md).

### <a name="windows-desktop"></a>Windows-Desktop

.NET Core 3.0 unterstützt die Windows-Desktopanwendungen mit Windows Presentation Foundation (WPF) und Windows Forms. Diese Frameworks unterstützt auch die Verwendung moderner Steuerelemente und des Fluent-Stils aus der Windows-UI-XAML-Bibliothek (WinUI) über [XAML-Inseln](/windows/uwp/xaml-platform/xaml-host-controls).

Die Windows Desktop-Komponente ist Teil des Windows .NET Core 3.0 SDK.

Mit dem folgenden `dotnet`-Befehl können Sie eine neue WPF- oder Windows Forms-Anwendung erstellen:

```dotnetcli
dotnet new wpf
dotnet new winforms
```

Neu in Visual Studio 2019 sind Vorlagen für die Option **Neues Projekt** für Windows Forms und WPF in .NET Core 3.0.

Weitere Informationen zum Portieren einer vorhandenen .NET Framework-Anwendung finden Sie unter [Portieren von WPF-Projekten](../../desktop-wpf/migration/convert-project-from-net-framework.md) und [Portieren von Windows Forms-Projekten](../porting/winforms.md).

#### <a name="winforms-high-dpi"></a>WinForms mit hohem DPI-Wert

.NET Core-Windows Forms-Anwendungen können den Modus für hohe DPI-Werte mit <xref:System.Windows.Forms.Application.SetHighDpiMode(System.Windows.Forms.HighDpiMode)?displayProperty=nameWithType> festlegen. Die `SetHighDpiMode`-Methode legt den entsprechenden Modus für hohe DPI-Werte fest, sofern er nicht mit anderen Mitteln wie `App.Manifest` oder „P/Invoke“ vor dem `Application.Run` festgelegt wurde.

Die möglichen `highDpiMode`-Werte, wie durch die <xref:System.Windows.Forms.HighDpiMode?displayProperty=nameWithType>-Enumeration ausgedrückt, sind:

- `DpiUnaware`
- `SystemAware`
- `PerMonitor`
- `PerMonitorV2`
- `DpiUnawareGdiScaled`

Weitere Informationen zu hohen DPI-Werten finden Sie unter [Entwicklung von Desktopanwendungen mit hohen DPI-Werten unter Windows](/windows/desktop/hidpi/high-dpi-desktop-application-development-on-windows).

### <a name="create-com-components"></a>Erstellen von COM-Komponenten

Unter Windows können Sie jetzt COM-aufrufbare verwaltete Komponenten erstellen. Diese Funktion ist für die Verwendung von .NET Core mit COM-Add-in-Modellen und auch zur Parität mit .NET Framework wichtig.

Im Gegensatz zu .NET Framework, wo *mscoree.dll* als COM-Server verwendet wurde, fügt .NET Core dem *bin*-Verzeichnis eine native Startprogramm-DLL hinzu, wenn Sie Ihre COM-Komponente erstellen.

Ein Beispiel für das Erstellen einer COM‑Komponente und ihre Verwendung finden Sie in der [COM-Demo](https://github.com/dotnet/samples/tree/master/core/extensions/COMServerDemo).

### <a name="windows-native-interop"></a>Native Windows-Interop-API

Windows stellt eine umfassende native API mit grundlegenden C-APIs (ohne C++-Features), COM und WinRT bereit. Während .NET Core **P/Invoke** unterstützt, fügt .NET Core 3.0 die Fähigkeit zum **CoCreate von COM-APIs** und **Aktivieren von WinRT-APIs** hinzu. Ein Codebeispiel finden Sie in der [Excel-Demo](https://github.com/dotnet/samples/tree/master/core/extensions/ExcelDemo).

### <a name="msix-deployment"></a>MSIX-Bereitstellung

[MSIX](https://docs.microsoft.com/windows/msix/) ist ein neues Windows-Anwendungspaketformat. Es kann zum Bereitstellen von .NET Core 3.0-Desktopanwendungen auf Windows 10 verwendet werden.

In Visual Studio 2019 können mit dem enthaltenen [Paketerstellungsprojekt für Windows-Anwendungen](https://docs.microsoft.com/windows/uwp/porting/desktop-to-uwp-packaging-dot-net) MSIX-Pakete mit [eigenständigen](../deploying/index.md#publish-self-contained) .NET Core-Anwendungen erstellt werden.

Die unterstützten Laufzeiten müssen in der `<RuntimeIdentifiers>`-Eigenschaft der .NET Core-Projektdatei angegeben werden:

```xml
<RuntimeIdentifiers>win-x86;win-x64</RuntimeIdentifiers>
```

## <a name="linux-improvements"></a>Verbesserungen für Linux

### <a name="serialport-for-linux"></a>SerialPort für Linux

.NET Core 3.0 bietet grundlegende Unterstützung für <xref:System.IO.Ports.SerialPort?displayProperty=nameWithType> unter Linux.

Bisher unterstützte .NET Core nur die Verwendung von `SerialPort` auf Windows.

Weitere Informationen zur eingeschränkten Unterstützung für den seriellen Anschluss unter Linux finden Sie unter [GitHub-Issue 33146](https://github.com/dotnet/corefx/issues/33146).

### <a name="docker-and-cgroup-memory-limits"></a>Arbeitsspeicherlimits bei Docker und Cgroup

Die Ausführung von .NET Core 3.0 unter Linux mit Docker funktioniert besser mit Cgroup-Arbeitsspeicherlimits. Das Ausführen eines Docker-Containers mit Arbeitsspeicherlimits, z.B. mit `docker run -m`, ändert das Verhalten von .NET Core.

- Standardmäßige Heapgröße des Garbage Collectors (GC): maximal 20MB oder 75% des Arbeitsspeicherlimits für den Container.
- Die explizite Größe kann als absolute Anzahl oder Prozentsatz des Cgroup-Limits festgelegt werden.
- Die minimale reservierte Segmentgröße pro GC-Heap beträgt 16MB. Diese Größe reduziert die Anzahl der Heaps, die auf Computern erstellt werden.

### <a name="gpio-support-for-raspberry-pi"></a>GPIO-Unterstützung für Raspberry Pi

Über NuGet können nun zwei Pakete für die GPIO-Programmierung bezogen werden:

- [System.Device.Gpio](https://www.nuget.org/packages/System.Device.Gpio)
- [Iot.Device.Bindings](https://www.nuget.org/packages/Iot.Device.Bindings)

Die GPIO-Pakete enthalten APIs für *GPIO*-, *SPI*-, *I2C*- und *PWM*-Geräte. Das IoT-Bindungenpaket enthält Gerätebindungen. Weitere Informationen finden Sie im [GitHub-Repository zu Geräten](https://github.com/dotnet/iot/blob/master/src/devices/).

### <a name="arm64-linux-support"></a>ARM64-Linux-Support

.NET Core 3.0 fügt Unterstützung für ARM64 für Linux hinzu. Der primäre Anwendungsfall für ARM64 sind derzeit IoT-Szenarien. Weitere Informationen finden Sie unter [.NET Core Runtime ARM64 Status](https://github.com/dotnet/announcements/issues/82) (.NET Core-Runtime-ARM64-Status).

[Dockerimages für .NET Core unter ARM64](https://hub.docker.com/r/microsoft/dotnet/) sind für Alpine, Debian und Ubuntu verfügbar.

> [!NOTE]
> **ARM64** wird von Windows noch nicht unterstützt.

## <a name="security"></a>Sicherheit

### <a name="tls-13--openssl-111-on-linux"></a>TLS 1.3 & OpenSSL 1.1.1 auf Linux

.NET Core nutzt nun die Unterstützung von [TLS 1.3 in OpenSSL 1.1.1.1](https://www.openssl.org/blog/blog/2018/09/11/release111/), wenn es in einer bestimmten Umgebung verfügbar ist. Mit TLS 1.3:

- Verbindungszeiten werden durch Reduzierung der erforderlichen Roundtrips zwischen Client und Server verbessert.
- Verbesserte Sicherheit wg. Entfernen verschiedener veralteter und unsicherer kryptografischer Algorithmen.

Sofern verfügbar, verwendet .NET Core 3.0 **OpenSSL 1.1.1**, **OpenSSL 1.1.0** oder **OpenSSL 1.0.2** auf einem Linuxsystem. Wenn **OpenSSL 1.1.1** verfügbar ist, verwendet sowohl der <xref:System.Net.Security.SslStream?displayProperty=nameWithType>- als auch <xref:System.Net.Http.HttpClient?displayProperty=nameWithType>-Typ **TLS 1.3** (vorausgesetzt, dass Client und Server **TLS 1.3** unterstützen).

> [!IMPORTANT]
> Windows und macOS unterstützen **TLS 1.3** noch nicht. .NET Core 3.0 unterstützt **TLS 1.3** auf diesen Betriebssystemen, wenn entsprechender Support verfügbar ist.

Das folgende Beispiel für C# 8.0 veranschaulicht das Herstellen der Verbindung von .NET Core 3.0 auf Ubuntu 18.10 mit <https://www.cloudflare.com>:

[!code-csharp[TLSExample](~/samples/snippets/core/whats-new/whats-new-in-30/cs/TLS.cs#TLS)]

### <a name="cryptography-ciphers"></a>Kryptografieverschlüsselungen

.NET 3.0 fügt Unterstützung für **AES-GCM**- und **AES-CCM-** -Verschlüsselungen hinzu, implementiert mit <xref:System.Security.Cryptography.AesGcm?displayProperty=nameWithType> bzw. <xref:System.Security.Cryptography.AesCcm?displayProperty=nameWithType>. Beide Algorithmen sind [AEAD-Algorithmen (Authenticated Encryption with Association Data)](https://en.wikipedia.org/wiki/Authenticated_encryption).

Der folgende Code veranschaulicht die Verwendung der `AesGcm`-Verschlüsselung zum Verschlüsseln und Entschlüsseln von Zufallsdaten.

[!code-csharp[AesGcm](~/samples/snippets/core/whats-new/whats-new-in-30/cs/Cipher.cs#AesGcm)]

### <a name="cryptographic-key-importexport"></a>Importieren/Exportieren kryptografischer Schlüssel

.NET Core 3.0 unterstützt das Importieren und Exportieren der asymmetrischen öffentlichen und privaten Schlüssel aus den Standardformaten. Sie müssen kein X.509-Zertifikat verwenden.

Alle Schlüsseltypen wie *RSA*, *DSA*, *ECDsa* und *ECDiffieHellman* unterstützen die folgenden Formate:

- **Öffentlicher Schlüssel**
  - X.509 SubjectPublicKeyInfo

- **Privater Schlüssel**
  - PKCS#8 PrivateKeyInfo
  - PKCS#8 EncryptedPrivateKeyInfo

RSA-Schlüsseln unterstützen auch:

- **Öffentlicher Schlüssel**
  - PKCS#1 RSAPublicKey

- **Privater Schlüssel**
  - PKCS#1 RSAPrivateKey

Die Exportmethoden erstellen DER-kodierte Binärdaten, und die Importmethoden erwarten dasselbe. Wenn ein Schlüssel im textfreundlichen PEM-Format gespeichert ist, muss der Anrufer den Inhalt base64-dekodieren, bevor er eine Importmethode aufruft.

[!code-csharp[RSA](~/samples/snippets/core/whats-new/whats-new-in-30/cs/RSA.cs#Rsa)]

**PKCS#8**-Dateien können mit <xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo?displayProperty=nameWithType> überprüft werden, und **PFX/PKCS#12**-Dateien mit <xref:System.Security.Cryptography.Pkcs.Pkcs12Info?displayProperty=nameWithType>. **PFX/PKCS#12**-Dateien können mit <xref:System.Security.Cryptography.Pkcs.Pkcs12Builder?displayProperty=nameWithType> bearbeitet werden.

## <a name="net-core-30-api-changes"></a>Änderungen der .NET Core 3.0-API

### <a name="ranges-and-indices"></a>Bereiche und Indizes

Der neue <xref:System.Index?displayProperty=nameWithType>-Typ kann für die Indizierung verwendet werden. Sie können einen aus einem `int` erstellen, der vom Anfang aus zählt, oder mit einem Präfix-`^`-Operator (C#), der vom Ende aus zählt:

```csharp
Index i1 = 3;  // number 3 from beginning
Index i2 = ^4; // number 4 from end
int[] a = { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 };
Console.WriteLine($"{a[i1]}, {a[i2]}"); // "3, 6"
```

Es gibt auch einen <xref:System.Range?displayProperty=nameWithType>-Typ, der aus zwei `Index`-Werten besteht, einen für den Anfang und einen für das Ende, und mit einem `x..y`-Bereichsausdruck (C#) geschrieben werden kann. Sie können dann mit einem `Range` indizieren, der ein Segment erzeugt:

```csharp
var slice = a[i1..i2]; // { 3, 4, 5 }
```

Weitere Informationen finden Sie im Tutorial [Bereiche und Indizes](../../csharp/tutorials/ranges-indexes.md).

### <a name="async-streams"></a>Asynchrone Datenströme

Die <xref:System.Collections.Generic.IAsyncEnumerable%601>-Typ ist eine neue asynchrone Version von <xref:System.Collections.Generic.IEnumerable%601>. In C# 8.0 können Sie `await foreach` zur Verarbeitung der `IAsyncEnumerable<T>`-Elemente nutzen und anschließend `yield return` zum Erstellen von Elementen verwenden.

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

Weitere Informationen finden Sie im Tutorial [Generieren und Nutzen asynchroner Datenströme mit C# 8.0 und .NET Core 3.0](../../csharp/tutorials/generate-consume-asynchronous-stream.md).

### <a name="ieee-floating-point"></a>IEEE-Gleitkomma

APIs für Gleitkommazahlen werden aktuell der [Revision des Standards IEEE 754-2008](https://en.wikipedia.org/wiki/IEEE_754-2008_revision) angepasst. Ziel dieser Änderungen ist, alle **erforderlichen** Operationen verfügbar zu machen und sicherzustellen, dass sie mit dem in der IEEE-Spezifikation beschriebenen Verhalten kompatibel sind. Weitere Informationen über Gleitkommaverbesserungen finden Sie im Blogbeitrag [Floating-Point Parsing and Formatting improvements in .NET Core 3.0](https://devblogs.microsoft.com/dotnet/floating-point-parsing-and-formatting-improvements-in-net-core-3-0/) (Verbesserungen zu Gleitkommaanalyse und Formatierung in .NET Core 3.0).

Zu den Korrekturen für Analyse und Formatierung zählen:

- Eingaben mit beliebiger Länge werden richtig analysiert und gerundet.
- Die negative Null wird richtig analysiert und formatiert.
- `Infinity`- und `NaN`-Werte werden mithilfe einer Überprüfung, bei der nicht zwischen Groß-/Kleinbuchstaben unterschieden wird, richtig analysiert. Außerdem ist, falls erforderlich, optional das vorangestellte `+`-Zeichen zulässig.

Zu den neuen <xref:System.Math?displayProperty=nameWithType>-APIs zählen:

- <xref:System.Math.BitIncrement(System.Double)> und <xref:System.Math.BitDecrement(System.Double)>\
entspricht den IEEE-Operationen `nextUp` und `nextDown`. Diese geben jeweils die kleinste Gleitkommazahl zurück, die größer oder kleiner als der Eingabewert ist. `Math.BitIncrement(0.0)` gibt beispielsweise `double.Epsilon` zurück.

- <xref:System.Math.MaxMagnitude(System.Double,System.Double)> und <xref:System.Math.MinMagnitude(System.Double,System.Double)>\
entspricht den IEEE-Operationen `maxNumMag` und `minNumMag`. Diese geben für zwei Eingabewerte jeweils den Wert zurück, für den ein größerer oder kleinerer Absolutbetrag ermittelt wird. `Math.MaxMagnitude(2.0, -3.0)` gibt beispielsweise `-3.0` zurück.

- <xref:System.Math.ILogB(System.Double)>\
Entspricht der IEEE-Operation `logB`, die einen integralen Wert zurückgibt. Der Rückgabewert ist der integrale Wert des Logarithmus zur Basis 2 des Eingabeparameters. Diese Methode entspricht im Wesentlichen `floor(log2(x))`, jedoch ist der Rundungsfehler minimal.

- <xref:System.Math.ScaleB(System.Double,System.Int32)>\
Entspricht der IEEE-Operation `scaleB`, der ein integraler Wert übergeben wird. Zurückgegeben wird im Wesentlichen `x * pow(2, n)`, jedoch ist der Rundungsfehler minimal.

- <xref:System.Math.Log2(System.Double)>\
entspricht der IEEE-Operation `log2`, die den Logarithmus zur Basis 2 zurückgibt. Diese Operation minimiert den Rundungsfehler.

- <xref:System.Math.FusedMultiplyAdd(System.Double,System.Double,System.Double)>\
entspricht der IEEE-Operation `fma`, die eine Fused-Multiply-Add-Operation durchführt. Dabei wird `(x * y) + z` als einzelne Operation ausgeführt, wodurch der Rundungsfehler minimiert wird. Ein Beispiel hierfür ist `FusedMultiplyAdd(1e308, 2.0, -1e308)`, diese gibt `1e308` zurück. Die reguläre Operation `(1e308 * 2.0) - 1e308` gibt `double.PositiveInfinity` zurück.

- <xref:System.Math.CopySign(System.Double,System.Double)>\
entspricht der IEEE-Operation `copySign`. Diese gibt den Wert von `x` mit dem Vorzeichen von `y` zurück.

### <a name="net-platform-dependent-intrinsics"></a>Von der .NET-Plattform abhängige systeminterne Funktionen

Mit neuen APIs kann auf bestimmte leistungsorientierte CPU-Anweisungen wie **SIMD** oder **Bit Manipulation Instruction Sets** zugegriffen werden. Diese Anweisungen können in bestimmten Szenarios wie der effizienten parallelen Datenverarbeitung zu deutlichen Leistungssteigerungen führen.

Wo möglich, haben die .NET-Bibliotheken begonnen, mithilfe dieser Anweisungen die Leistung zu verbessern.

Weitere Informationen finden Sie unter [.NET Platform Dependent Intrinsics](https://github.com/dotnet/designs/blob/master/accepted/platform-intrinsics.md) (Von der .NET-Plattform abhängige systeminterne Funktionen).

### <a name="improved-net-core-version-apis"></a>Verbesserte .NET Core-Versions-APIs

Ab .NET Core 3.0 geben die mit .NET Core gelieferten Versions-APIs jetzt die Informationen zurück, die Sie erwarten. Zum Beispiel:

```csharp
System.Console.WriteLine($"Environment.Version: {System.Environment.Version}");

// Old result
//   Environment.Version: 4.0.30319.42000
//
// New result
//   Environment.Version: 3.0.0
```

```csharp
System.Console.WriteLine($"RuntimeInformation.FrameworkDescription: {System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription}");

// Old result
//   RuntimeInformation.FrameworkDescription: .NET Core 4.6.27415.71
//
// New result (notice the value includes any preview release information)
//   RuntimeInformation.FrameworkDescription: .NET Core 3.0.0-preview4-27615-11
```

> [!WARNING]
> Entscheidende Änderung. Dies ist technisch gesehen eine entscheidende Änderung, da das Schema der Versionsverwaltung sich geändert hat.

### <a name="fast-built-in-json-support"></a>Schneller integrierter JSON-Support

.NET-Benutzer haben sich weitgehend auf [Newtonsoft.Json](https://www.newtonsoft.com/json) und andere beliebte JSON-Bibliotheken verlassen, die weiterhin eine gute Wahl sind. `Newtonsoft.Json` verwendet als Basisdatentyp .NET-Zeichenfolgen, die intern in UTF-16 codiert sind.

Die neue integrierte JSON-Unterstützung ist überaus leistungsfähig mit geringer Zuteilung und funktioniert mit UTF-8-codiertem JSON-Text. Weitere Informationen zum Namespace <xref:System.Text.Json> und den Typen finden Sie in den folgenden Artikeln:

* [Übersicht zur JSON-Serialisierung in .NET](../../standard/serialization/system-text-json-overview.md)
* [Serialisieren und Deserialisieren von JSON-Daten in .NET](../../standard/serialization/system-text-json-how-to.md):
* [Migrieren aus Newtonsoft.Json zu System.Text.Json](../../standard/serialization/system-text-json-migrate-from-newtonsoft-how-to.md)

### <a name="http2-support"></a>HTTP/2-Unterstützung

Der <xref:System.Net.Http.HttpClient?displayProperty=nameWithType>-Typ unterstützt das HTTP/2-Protokoll. Wenn HTTP/2 aktiviert ist, wird die HTTP-Protokollversion über TLS/ALPN ausgehandelt, und HTTP/2 wird bei Auswahl durch den Server verwendet.

Das Standardprotokoll bleibt HTTP/1.1, aber HTTP/2 kann auf zwei verschiedene Arten aktiviert werden. Erstens können Sie die HTTP-Anforderungsnachricht so festlegen, dass HTTP/2 verwendet wird:

[!code-csharp[Http2Request](~/samples/snippets/core/whats-new/whats-new-in-30/cs/http.cs#Request)]

Zweitens können Sie <xref:System.Net.Http.HttpClient> so ändern, dass HTTP/2 standardmäßig verwendet wird:

[!code-csharp[Http2Client](~/samples/snippets/core/whats-new/whats-new-in-30/cs/http.cs#Client)]

Oftmals möchten Sie bei der Entwicklung einer Anwendung eine unverschlüsselte Verbindung verwenden. Wenn Sie wissen, dass der Zielendpunkt HTTP/2 verwendet, können Sie unverschlüsselte Verbindungen für HTTP/2 aktivieren. Sie können sie aktivieren, indem Sie die Umgebungsvariable `DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2UNENCRYPTEDSUPPORT` auf `1` festlegen oder sie im App-Kontext aktivieren:

[!code-csharp[Http2Context](~/samples/snippets/core/whats-new/whats-new-in-30/cs/http.cs#AppContext)]

## <a name="next-steps"></a>Nächste Schritte

- [Informationen zu den wichtigsten Unterschieden zwischen .NET Core 2.2 und 3.0](../compatibility/2.2-3.0.md)
- [Überprüfen von Breaking Changes in .NET Core 3.0 für Windows Forms-Apps](../compatibility/winforms.md#net-core-30)
