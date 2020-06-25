---
title: .NET Core-RID-Katalog (Runtime Identifier)
description: Erfahren Sie mehr über die Runtime-ID (RID) und wie RIDs in .NET Core verwendet werden.
ms.date: 02/22/2019
ms.openlocfilehash: 903dd9c619008c9e3c6149a471ba814bdc9c97cc
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/17/2020
ms.locfileid: "84903284"
---
# <a name="net-core-rid-catalog"></a>.NET Core-RID-Katalog

RID ist die Kurzform für *Runtime Identifier* (Laufzeitbezeichner). Mithilfe von RID-Werten werden Zielplattformen identifiziert, unter der die Anwendung ausgeführt wird.
Sie werden von .NET-Paketen verwendet, um plattformspezifische Ressourcen in NuGet-Paketen darzustellen. Die folgenden Werte sind Beispiele für RIDs: `linux-x64`, `ubuntu.14.04-x64`, `win7-x64` oder `osx.10.12-x64`.
Für die Pakete mit nativen Abhängigkeiten legt die RID fest, auf welchen Plattformen das Paket wiederhergestellt werden kann.

Eine einzelne RID kann im `<RuntimeIdentifier>`-Element Ihrer Projektdatei festgelegt werden. Mehrere RIDs können als Liste mit Semikolon als Trennzeichen im `<RuntimeIdentifiers>`-Element der Projektdatei definiert werden. Sie können auch über die Option `--runtime` mit den folgenden [.NET Core-CLI-Befehlen](./tools/index.md) verwendet werden:

- [dotnet build](./tools/dotnet-build.md)
- [dotnet clean](./tools/dotnet-clean.md)
- [dotnet pack](./tools/dotnet-pack.md)
- [dotnet publish](./tools/dotnet-publish.md)
- [dotnet restore](./tools/dotnet-restore.md)
- [dotnet run](./tools/dotnet-run.md)
- [dotnet store](./tools/dotnet-store.md)

RIDs, die konkrete Betriebssysteme darstellen, weisen in der Regel folgendes Muster auf: `[os].[version]-[architecture]-[additional qualifiers]`, wobei:

- `[os]` ist der Moniker des Betriebs-/Plattformsystems. Beispielsweise `ubuntu`.

- `[version]` ist die Version des Betriebssystems in Form einer durch Punkte getrennten (`.`) Versionsnummer. Beispielsweise `15.10`.

  - Die Version sollte **keine** Marketingversion sein, da diese häufig mehrere separate Versionen des Betriebssystems mit unterschiedlichen Plattform-API-Oberflächen darstellt.

- `[architecture]` ist die Prozessorarchitektur. Beispielsweise `x86`, `x64`, `arm` oder `arm64`.

- `[additional qualifiers]` differenziert die verschiedenen Plattformen noch stärker. Beispiel: `aot`.

## <a name="rid-graph"></a>RID-Diagramm

Das RID-Diagramm oder Runtimefallbackdiagramm ist eine Liste von RIDs, die miteinander kompatibel sind. Die RIDs werden im Paket [Microsoft.NETCore.Platforms](https://www.nuget.org/packages/Microsoft.NETCore.Platforms/) definiert. Die Liste der unterstützten RIDs und das RID-Diagramm finden Sie in der Datei [*runtime.json*](https://github.com/dotnet/runtime/blob/master/src/libraries/pkg/Microsoft.NETCore.Platforms/runtime.json) im `dotnet/runtime`-Repository. In dieser Datei können Sie sehen, dass alle RIDs außer der Basis-RID eine `"#import"`-Anweisung enthalten. Diese Anweisungen geben kompatible RIDs an.

Bei NuGet-Wiederherstellungspaketen wird versucht, eine genaue Übereinstimmung für die angegebene Runtime zu finden.
Wenn keine genaue Übereinstimmung gefunden wird, durchläuft das NuGet erneut das Diagramm, bis es das System mit der größten Kompatibilität gemäß dem RID-Diagramm findet.

Im Folgenden wird ein Beispiel für den tatsächlichen Eintrag für die `osx.10.12-x64`-RID vorgestellt:

```json
"osx.10.12-x64": {
    "#import": [ "osx.10.12", "osx.10.11-x64" ]
}
```

Die oben genannte RID gibt an, dass `osx.10.12-x64``osx.10.11-x64` importiert. Bei NuGet-Wiederherstellungspaketen wird daher versucht, eine genaue Übereinstimmung für `osx.10.12-x64` im Paket zu finden. Wenn das NuGet die angegebene Runtime nicht finden kann, kann es beispielsweise Wiederherstellungspakete mit den Runtimes `osx.10.11-x64` finden.

Das folgende Beispiel zeigt, wie ein etwas größeres RID-Diagramm auch in der Datei *runtime.json* definiert wird:

```
    win7-x64    win7-x86
       |   \   /    |
       |   win7     |
       |     |      |
    win-x64  |  win-x86
          \  |  /
            win
             |
            any
```

Alle RIDs bilden schließlich wieder den Stamm `any`-RID ab.

Es gibt einige Aspekte zu RIDs, die Sie bei der Verwendung bedenken müssen:

- RIDs sind **opake Zeichenfolgen** und sollten als Blackboxes behandelt werden.
- Erstellen Sie RIDs nicht programmgesteuert.
- Verwenden Sie RIDs, die bereits für die Plattform definiert sind.
- Die RIDs müssen spezifisch sein. Leiten Sie daher keine Annahmen anhand des tatsächlichen RID-Werts ab.

## <a name="using-rids"></a>Die Verwendung von RIDs

Um RIDs verwenden zu können, müssen Sie wissen, welche RIDs es gibt. Zur Plattform werden regelmäßig neue Werte hinzugefügt.
Prüfen Sie die Datei [runtime.json](https://github.com/dotnet/runtime/blob/master/src/libraries/pkg/Microsoft.NETCore.Platforms/runtime.json) im `dotnet/runtime`-Repository auf die neueste und vollständige Version.

Mit dem .NET Core 2.0 SDK wird das Konzept von portablen RIDs eingeführt. Dabei handelt es sich um neue zum RID-Diagramm hinzugefügte Werte, die nicht an eine bestimmte Version oder Betriebssystemverteilung gebunden und die bevorzugte Wahl bei der Verwendung von .NET Core 2.0 und höher sind. Sie sind besonders nützlich beim Umgang mit mehreren Linux-Distributionen, da die meisten Distributions-RIDs portable RIDs sind.

Die folgende Liste enthält eine kleine Untergruppe der am häufigsten verwendeten RIDs für jedes Betriebssystem.

## <a name="windows-rids"></a>RIDs für Windows

Nur allgemeine Werte werden aufgeführt. Prüfen Sie die Datei [runtime.json](https://github.com/dotnet/runtime/blob/master/src/libraries/pkg/Microsoft.NETCore.Platforms/runtime.json) im `dotnet/runtime`-Repository auf die neueste und vollständige Version.

- Portabel (.NET Core 2.0 oder höher)
  - `win-x64`
  - `win-x86`
  - `win-arm`
  - `win-arm64`
- Windows 7 / Windows Server 2008 R2
  - `win7-x64`
  - `win7-x86`
- Windows 8.1 / Windows Server 2012 R2
  - `win81-x64`
  - `win81-x86`
  - `win81-arm`
- Windows 10 / Windows Server 2016
  - `win10-x64`
  - `win10-x86`
  - `win10-arm`
  - `win10-arm64`

Weitere Informationen finden Sie unter [.NET Core-Abhängigkeiten und -Anforderungen](install/dependencies.md?pivots=os-windows).

## <a name="linux-rids"></a>RIDs für Linux

Nur allgemeine Werte werden aufgeführt. Prüfen Sie die Datei [runtime.json](https://github.com/dotnet/runtime/blob/master/src/libraries/pkg/Microsoft.NETCore.Platforms/runtime.json) im `dotnet/runtime`-Repository auf die neueste und vollständige Version. Geräte, die unter einer nicht aufgeführten Distribution ausgeführt werden, funktionieren möglicherweise mit einem der portablen RIDs. Beispielsweise können Raspberry Pi-Geräte, die unter einer nicht aufgeführten Linux-Distribution ausgeführt werden, mit `linux-arm` erreicht werden.

- Portabel (.NET Core 2.0 oder höher)
  - `linux-x64` (Die meisten Desktopdistributionen wie CentOS, Debian, Fedora, Ubuntu und Ableitungen)
  - `linux-musl-x64` (Einfache Distributionen mit [musl](https://wiki.musl-libc.org/projects-using-musl.html) wie Alpine Linux)
  - `linux-arm` (Linux-Distributionen, die auf ARM ausgeführt werden, wie Raspbian auf Raspberry Pi, Modell 2+)
  - `linux-arm64` (Linux-Distributionen, die auf 64-Bit-ARM ausgeführt werden, wie Ubuntu Server, 64-Bit, auf Raspberry Pi, Modell 3+)
- Red Hat Enterprise Linux
  - `rhel-x64` (Ersetzt durch `linux-x64` für RHEL ab Version 6)
  - `rhel.6-x64` (.NET Core 2.0 oder höher)
- Tizen (.NET Core 2.0 oder höher)
  - `tizen`
  - `tizen.4.0.0`
  - `tizen.5.0.0`

Weitere Informationen finden Sie unter [.NET Core-Abhängigkeiten und -Anforderungen](install/dependencies.md?pivots=os-linux).

## <a name="macos-rids"></a>Relative IDs für macOS

Relative IDs für macOS verwenden das ältere Branding „OSX“. Nur allgemeine Werte werden aufgeführt. Prüfen Sie die Datei [runtime.json](https://github.com/dotnet/runtime/blob/master/src/libraries/pkg/Microsoft.NETCore.Platforms/runtime.json) im `dotnet/runtime`-Repository auf die neueste und vollständige Version.

- Portabel (.NET Core 2.0 oder höher)
  - `osx-x64` (Mindestversion des Betriebssystems ist macOS 10.12 Sierra)
- macOS 10.10  Yosemite
  - `osx.10.10-x64`
- macOS 10.11 El Capitan
  - `osx.10.11-x64`
- macOS 10.12 Sierra (.NET Core 1.1 oder höher)
  - `osx.10.12-x64`
- macOS 10.13 Sierra (.NET Core 1.1 oder höher)
  - `osx.10.13-x64`
- macOS 10.14 Mojave (.NET Core 1.1 oder höher)
  - `osx.10.14-x64`

Weitere Informationen finden Sie unter [.NET Core-Abhängigkeiten und -Anforderungen](install/dependencies.md?pivots=os-macos).

## <a name="see-also"></a>Siehe auch

- [Runtime-IDs](https://github.com/dotnet/runtime/blob/master/src/libraries/pkg/Microsoft.NETCore.Platforms/readme.md)
