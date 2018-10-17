---
title: Cross-Plattform-Ausrichtung
description: Empfehlungen für bewährte Methoden zum Erstellen von plattformübergreifenden .NET Bibliotheken.
author: jamesnk
ms.author: mairaw
ms.date: 10/02/2018
ms.openlocfilehash: 72fa891d5b1054af485a98d89b4efb11d6b0018b
ms.sourcegitcommit: e42d09e5966dd9fd02847d3e7eeb4ec0877069f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2018
ms.locfileid: "49374892"
---
# <a name="cross-platform-targeting"></a>Cross-Plattform-Ausrichtung

Moderne .NET unterstützt mehrere Betriebssysteme und Geräte. Es ist wichtig für .NET Open Source-Bibliotheken, um so viele Entwickler wie möglich zu unterstützen, erstellen sie eine ASP.NET-Website in Azure oder ein .NET-Spiels in Unity gehostet.

## <a name="net-standard"></a>.NET-Standard

.NET standard ist die beste Möglichkeit, plattformübergreifende Unterstützung einer .NET Bibliothek hinzufügen. [.NET standard](../net-standard.md) ist eine Spezifikation von .NET-APIs, die in allen .NET-Implementierungen verfügbar sind. Von .NET Standard können Sie die Bibliotheken zu erstellen, die darauf beschränkt sind, die APIs verwenden, die in einer bestimmten Version von .NET Standard sind. Dies bedeutet, dass er kann verwendet werden von allen Plattformen, die diese Version von .NET Standard zu implementieren.

![.NET Standard](./media/cross-platform-targeting/platforms-netstandard.png ".NET Standard")

Auf .NET Standard abzielen und Ihrem Projekt erfolgreich zu kompilieren garantiert, dass die Bibliothek erfolgreich ausgeführt wird, auf allen Plattformen nicht:

1. Plattformspezifische APIs fehl auf anderen Plattformen. Z. B. <xref:Microsoft.Win32.Registry?displayProperty=nameWithType> erfolgreich auf Windows und löst <xref:System.PlatformNotSupportedException> bei allen anderen Betriebssystemen.
2. APIs können sich unterschiedlich Verhalten. Beispielsweise verfügen über Reflektion APIs unterschiedliche Leistungsmerkmale, wenn eine Anwendung verwendet die ahead-of-Time-Kompilierung auf iOS oder UWP.

> [!TIP]
> Das .NET Team [bietet ein Roslyn-Analysetool](../analyzers/api-analyzer.md) können Sie mögliche Probleme zu ermitteln.

**✔️ FÜHREN** beginnen Sie mit, einschließlich einer `netstandard2.0` Ziel.

> Die meisten Bibliotheken für allgemeine Zwecke sollte die APIs außerhalb von .NET Standard 2.0 nicht erforderlich. .NET standard 2.0 wird von allen modernen Plattformen unterstützt und ist die empfohlene Methode zur Unterstützung mehrerer Plattformen mit einem Ziel.

**❌ Vermeiden** einschließlich einer `netstandard1.x` Ziel.

> .NET standard 1.x als präzise Satz von NuGet-Pakete, die ein großes Paket Abhängigkeitsdiagramm erstellt und führt zu viele Pakete herunterladen, beim Erstellen von Entwicklern verteilt wird. Moderne .NET-Plattformen, einschließlich .NET Framework 4.6.1, UWP und Xamarin unterstützen .NET Standard 2.0. Sie sollten nur .NET Standard abzielen 1.x, wenn Sie explizit eine ältere Plattform müssen.

**✔️ FÜHREN** enthalten eine `netstandard2.0` abzielen, wenn Sie benötigen eine `netstandard1.x` Ziel.

> Alle Plattformen unterstützen .NET Standard 2.0 verwenden die `netstandard2.0` abzielen und davon profitieren, müssen eine kleinere Paketdiagramm während ältere Plattformen werden weiterhin funktionieren und alternative der `netstandard1.x` Ziel.

**❌ NICHT** fügen Sie ein .NET Standard-Ziel aus, wenn die Bibliothek in einem plattformspezifischen app-Modell basiert.

> Beispielsweise ist eine UWP-Steuerelement-Toolkit-Bibliothek auf eine app-Modell, das nur in UWP verfügbar ist. App-Modell-spezifische APIs werden nicht in .NET Standard verfügbar sein.

## <a name="multi-targeting"></a>Festlegung von Zielversionen

Manchmal müssen Sie Framework-spezifische APIs aus Ihren Bibliotheken zuzugreifen. Die beste Möglichkeit, Framework-spezifischen APIs aufzurufen verwendet die Festlegung von Zielversionen, der das Projekt erstellt wurde für viele [Zielframeworks für .NET](../frameworks.md) statt auf nur einen.

Zum schützen Ihre Kunden für die einzelnen Frameworks erstellen müssen, sollten Sie sich bemühen, um eine .NET Standard-Ausgabe und eine oder mehrere frameworkspezifische Ausgaben zu erhalten. Mit der Festlegung von Zielversionen werden alle Assemblys in einem einzelnen NuGet-Paket verpackt. Kunden können dann das gleiche Paket verweisen, und wählt NuGet die entsprechende Implementierung. .NET Standard-Bibliothek fungiert, wie die fallback-Bibliothek, die überall, mit Ausnahme der Fälle, in denen Ihr NuGet-Paket für eine Framework-spezifische Implementierung bietet. Festlegung von Zielversionen, können Sie für die bedingte Kompilierung in Ihrem Code verwenden und frameworkspezifische-APIs aufrufen.

![NuGet-Paket mit mehreren Assemblys](./media/cross-platform-targeting/nuget-package-multiple-assemblies.png "NuGet-Paket mit mehreren Assemblys")

**✔️ GGF.** für Implementierungen von .NET zusätzlich zu .NET Standard.

> Implementierungen von .NET Zielframework ist, können Sie plattformspezifische APIs aufrufen, die außerhalb von .NET Standard sind.
>
> Unterstützung für .NET Standard kann nicht gelöscht werden, wenn Sie dies tun. Stattdessen lösen Sie, die von der Implementierung und bieten Sie die Möglichkeit, APIs. Auf diese Weise Ihre Bibliothek kann überall verwendet werden und unterstützt die Common Language Runtime-Light-Up Features.

**❌ Vermeiden** mit Festlegung von Zielversionen mit .NET Standard, wenn Sie Ihren Quellcode, die für alle Ziele identisch ist.

> Die .NET Standard-Assembly wird automatisch von NuGet verwendet werden. Ziel der einzelnen Implementierungen von .NET steigt die `*.nupkg` für keinen Vorteil.

**✔️ GGF.** Hinzufügen eines Ziels für `net461` bieten Sie bei einem `netstandard2.0` Ziel. 

> Mit .NET Standard 2.0 von .NET Framework weist einige Probleme, die in .NET Framework 4.7.2 behoben wurden. Sie können die Oberfläche für Entwickler verbessern, die auf .NET Framework 4.6.1 – 4.7.1, indem sie eine Binärdatei, die für .NET Framework 4.6.1 basiert anbieten.

**Führen Sie ✔️** Ihre Bibliothek mithilfe von NuGet-Paket verteilen.

> NuGet wird wählen Sie das beste Ziel für den Entwickler und geschützt werden, müssen Sie die entsprechende Implementierung auswählen.

**Führen Sie ✔️** verwenden eine Projektdatei `TargetFrameworks` -Eigenschaft bei der Festlegung von Zielversionen.

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <!-- This project will output netstandard2.0 and net461 assemblies -->
    <TargetFrameworks>netstandard2.0;net461</TargetFrameworks>
  </PropertyGroup>
</Project>
```

**✔️ GGF.** mit [MSBuild.Sdk.Extras](https://github.com/onovotny/MSBuildSdkExtras) bei der Festlegung von Zielversionen für UWP und Xamarin, wie sie Ihre Projektdatei vereinfacht.

## <a name="older-targets"></a>Ältere Ziele

.NET unterstützt die Zielgruppenadressierung anhand bestimmter Versionen von .NET Framework, die sind lange Out-of-Support als auch für Plattformen, die nicht mehr häufig verwendet werden. Während bei der Erstellung Ihrer Bibliothek Arbeit auf wie viele Ziele wie möglich erfolgt, müssen zur Umgehung fehlender APIs hinzufügen können erheblichen Aufwand Wert vorhanden ist. Wir glauben sicher, dass Frameworks nicht mehr lohnt, abzielen, sind in Betracht ziehen, ihre Reichweite und Einschränkungen.

**❌ NICHT** fügen Sie ein Ziel für die Portable Klassenbibliothek (PCL). Beispielsweise `portable-net45+win8+wpa81+wp8`.

> .NET standard ist die moderne Möglichkeit zur Unterstützung von Cross-Platform-Bibliotheken für .NET und ersetzt PCLs.

**❌ NICHT** schließt Ziele für .NET-Plattformen, die nicht mehr unterstützt werden. Platzhalter in einer derartigen Schreibweise sind z.B. `SL4` und `WP`.

>[!div class="step-by-step"]
[Zurück](./get-started.md)
[Weiter](./strong-naming.md)
