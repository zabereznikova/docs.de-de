---
title: Portieren von .NET Framework zu .NET Core
description: Verstehen Sie den Portiervorgang und entdecken Sie Tools, die Ihnen beim Portieren eines .NET Framework-Projekts zu .NET Core behilflich sein können.
author: cartermp
ms.date: 10/22/2019
ms.openlocfilehash: c206e56e095d1ca068fa2aa6f60e891895f7f999
ms.sourcegitcommit: 4a938327bad8b2e20cabd0f46a9dc50882596f13
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/28/2020
ms.locfileid: "92888573"
---
# <a name="overview-of-porting-from-net-framework-to-net-core"></a>Übersicht über das Portieren von .NET Framework zu .NET Core

Möglicherweise verfügen Sie über Code, der zurzeit im .NET Framework ausgeführt wird und den Sie zu .NET Core portieren möchten. Dieser Artikel enthält:

* Übersicht über den Portiervorgang.
* Eine Liste der Tools, die beim Portieren Ihres Codes zu .NET Core nützlich sein können.

## <a name="overview-of-the-porting-process"></a>Übersicht über den Portiervorgang

Das Portieren zu .NET Core (oder .NET Standard) aus .NET Framework ist für viele Projekte relativ unkompliziert. Es gibt eine Reihe von Änderungen, die erforderlich sind, aber viele von ihnen befolgen die unten beschriebenen Muster. Projekte, bei denen das App-Modell in .NET Core verfügbar ist (z. B. Bibliotheken, Konsolen-Apps und Desktopanwendungen), erfordern in der Regel nur wenige Änderungen. Projekte, für die ein neues App-Modell erforderlich ist, z. B. die Umstellung von ASP.NET auf ASP.NET Core, erfordern etwas mehr Arbeit, aber viele Muster verfügen über analoge Entsprechungen, die während der Konvertierung verwendet werden können. Dieses Dokument sollte bei der Identifizierung der wichtigsten Strategien helfen, die Benutzer angewendet haben, um ihre Codebasen zielgerichtet in .NET Standard oder .NET Core erfolgreich umzuwandeln, und es behandelt dabei die Konvertierung auf zwei Ebenen: projektmappenweit und projektspezifisch. Informationen zu App-modellspezifischen Konvertierungen finden Sie unter den Links am Ende der Anweisungen.

Die folgende Vorgehensweise wird empfohlen, um Ihr Projekt zu .NET Core zu portieren. Mit jedem dieser Schritte werden potenzielle Stellen für Verhaltensänderungen eingeführt, weshalb Sie sicherstellen sollten, dass Sie Ihre Bibliothek oder Anwendung ausreichend testen, bevor Sie mit Folgeschritten fortfahren. In den ersten Schritten wird Ihr Projekt für einen Wechsel zu .NET Standard oder .NET Core vorbereitet. Wenn Sie über Komponententests verfügen, konvertieren Sie diese am besten zuerst, damit Sie mit dem Testen von Änderungen an dem Produkt fortfahren können, an dem Sie gerade arbeiten. Die Portierung auf .NET Core stellt eine erhebliche Änderung Ihrer Codebase dar, deshalb wird dringend empfohlen, Ihre Testprojekte zu portieren. Auf diese Weise können Sie Tests ausführen, wenn Sie Ihren Code portieren. MSTest, xUnit und NUnit funktionieren in .NET Core.

## <a name="getting-started"></a>Erste Schritte

Die folgenden Tools werden im gesamten Prozess verwendet:

- Visual Studio 2019
- Laden Sie [.NET Portability Analyzer](../../standard/analyzers/portability-analyzer.md) herunter.
- _Optional_ Installieren Sie [dotnet try-convert](https://github.com/dotnet/try-convert).

## <a name="porting-a-solution"></a>Portieren einer Projektmappe

Wenn mehrere Projekte in einer Projektmappe enthalten sind, kann die Portierung komplizierter sein, da Sie Projekte in einer bestimmten Reihenfolge verarbeiten müssen. Der Konvertierungsprozess sollte ein Bottom-Up-Ansatz sein, bei dem die Projekte ohne Abhängigkeiten von anderen Projekten in der Projektmappe zuerst konvertiert werden, und der sich dann durch die gesamte Projektmappe fortsetzt.

Um die Reihenfolge festzustellen, in der Projekte migriert werden sollten, können Sie die folgenden Tools verwenden:

- [Abhängigkeitsdiagramme in Visual Studio](/visualstudio/modeling/create-layer-diagrams-from-your-code) können ein gerichtetes Diagramm des Codes in einer Projektmappe erstellen.
- Führen Sie `msbuild _SolutionPath_ /t:GenerateRestoreGraphFile /p:RestoreGraphOutputPath=graph.dg.json` aus, um ein JSON-Dokument zu generieren, das eine Liste der Projektverweise enthält.
- Führen Sie den [.NET Portability Analyzer](../../standard/analyzers/portability-analyzer.md) mit der Option `-r DGML` aus, um ein Abhängigkeitsdiagramm der Assemblys abzurufen. Weitere Informationen finden Sie [hier](../../standard/analyzers/portability-analyzer.md#solution-wide-view).

Sobald Sie über die Abhängigkeitsinformationen verfügen, können Sie diese Informationen zum Starten bei den Blattknoten verwenden und sich die Abhängigkeitsstruktur heraufarbeiten, indem Sie die Schritte des nächsten Abschnitts ausführen.

## <a name="per-project-steps"></a>Schritt pro Projekt

Die folgende Vorgehensweise wird empfohlen, um Ihr Projekt zu .NET Core zu portieren:

1. Konvertieren Sie alle `packages.config`-Abhängigkeiten mit dem [Konvertierungstool in Visual Studio](/nuget/consume-packages/migrate-packages-config-to-package-reference) in das [PackageReference](/nuget/consume-packages/package-references-in-project-files)-Format.

   Zu diesem Schritt gehört auch die Konvertierung von Abhängigkeiten aus dem `packages.config`-Legacyformat. `packages.config` funktioniert in .NET Core nicht, daher ist diese Konvertierung notwendig, wenn Paketabhängigkeiten vorhanden sind. Außerdem sind nur die Abhängigkeiten erforderlich, die Sie direkt in einem Projekt verwenden. Dadurch werden spätere Schritte vereinfacht, da die Anzahl der zu verwaltenden Abhängigkeiten verringert wird.

1. Konvertieren Sie Ihre Projektdatei in die neue SDK-artige Dateistruktur. Sie können neue Projekte für .NET Core erstellen und die Quelldateien kopieren oder versuchen, Ihre vorhandene Projektdatei mithilfe eines Tools zu konvertieren.

   .NET Core verwendet ein einfacheres (und anderes) [Projektdateiformat](../tools/csproj.md) als .NET Framework. Sie müssen Ihre Projektdateien in dieses Format konvertieren, um sie weiter nutzen zu können. Mit diesem Projekttyp können Sie auch auf .NET Framework abzielen, das Sie zu diesem Zeitpunkt auch noch als Ziel haben sollten.

   Sie können versuchen, kleinere Lösungen oder einzelne Projekte mit dem Tool [dotnet try-convert](https://github.com/dotnet/try-convert) in einem einzigen Vorgang in das .NET Core-Projektdateiformat zu portieren. Es kann nicht garantiert werden, dass `dotnet try-convert` für all Ihre Projekte funktioniert, und es kann zu leichten Abweichungen bei Verhalten kommen, das Sie unbedingt benötigen. Verwenden Sie das Tool als _Ausgangspunkt_ , um grundlegende Elemente zu automatisieren, die sich für eine Automatisierung eignen. Dies ist keine garantierte Lösung für die Migration eines Projekts, da es viele Unterschiede bei den Zielen gibt, die von den SDK-artigen Projekten verwendet werden, im Vergleich zu den Projektdateien im alten Stil.

1. Legen Sie für alle zu portierenden Projekte .NET Framework 4.7.2 oder höher als neues Ziel fest.

   Durch diesen Schritt wird sichergestellt, dass Sie API-Alternativen für bestimmte .NET Framework-Ziele verwenden können, falls .NET Core eine bestimmte API nicht unterstützt.

1. Aktualisieren Sie alle Abhängigkeiten auf die neueste Version. Projekte verwenden möglicherweise ältere Versionen von Bibliotheken, die keine Unterstützung für .NET Standard aufweisen. Spätere Versionen unterstützen dies jedoch mithilfe eines einfachen Parameters. Dies erfordert möglicherweise Änderungen am Code, wenn in Bibliotheken Breaking Changes vorliegen.

1. Verwenden Sie den [.NET Portability Analyzer](../../standard/analyzers/portability-analyzer.md), um Ihre Assemblys zu analysieren und zu ermitteln, ob sie zu .NET Core portiert werden können.

   Das .NET Portability Analyzer-Tool analysiert Ihre kompilierten Assemblys und generiert einen Bericht. Dieser Bericht zeigt eine allgemeine Übersicht über die Portierbarkeit und eine Aufschlüsselung nach allen von Ihnen verwendeten APIs, die in .NET Core nicht verfügbar sind. Senden Sie bei Verwendung des Tools nur das einzelne Projekt, das Sie konvertieren, um sich auf die möglicherweise erforderlichen API-Änderungen zu konzentrieren. Viele der APIs verfügen über äquivalente Verfügbarkeit in .NET Core, zu dem Sie wechseln sollten.

   Beim Lesen der von der Analyse generierten Berichte sind die wichtigen Informationen die tatsächlich verwendeten APIs und nicht notwendigerweise die prozentuale Unterstützung für die Zielplattform. Viele APIs verfügen über äquivalente Optionen in .NET Standard/Core, weshalb das Verständnis der Szenarien, für die Ihre Bibliothek oder Anwendung die API benötigt, dabei helfen wird, die Auswirkungen auf die Portabilität zu ermitteln.

   In einigen Fällen sind APIs nicht äquivalent, sodass Sie einige Compilerpräprozessordirektiven (d. h. `#if NET45`) ausführen müssen, um spezielle Anwendungsfälle für die Plattformen zu entwerfen. An diesem Punkt ist Ihr Projekt immer noch ein .NET Framework-Projekt. Für jeden dieser Zielfälle empfiehlt es sich, bekannte Bedingungen zu verwenden, die als ein Szenario verstanden werden können.  Beispielsweise ist die AppDomain-Unterstützung in .NET Core begrenzt, doch für das Laden und Entladen von Assemblys gibt es eine neue API, die in .NET Core nicht verfügbar ist. Eine gängige Methode, um dies im Code zu behandeln, wäre etwa wie folgt:

   ```csharp
   #if FEATURE_APPDOMAIN_LOADING
   // Code that uses appdomains
   #elif FEATURE_ASSEMBLY_LOAD_CONTEXT
   // Code that uses assembly load context
   #else
   #error Unsupported platform
   #endif
   ```

1. Installieren Sie das [.NET API-Analysetool](../../standard/analyzers/api-analyzer.md) in Ihren Projekten, um APIs zu identifizieren, die eine <xref:System.PlatformNotSupportedException> für einige Plattformen auslösen, und um weitere potenzielle Kompatibilitätsprobleme zu ermitteln.

   Dieses Tool ähnelt Portability Analyzer, analysiert jedoch nicht, ob Code in .NET Core kompiliert werden kann, sondern ob Sie eine API auf eine Weise verwenden, die zur Laufzeit eine <xref:System.PlatformNotSupportedException> auslöst. Wenn Sie von .NET Framework 4.7.2 oder höher wechseln, ist dies zwar nicht häufig der Fall, aber eine Überprüfung ist dennoch eine gute Idee. Weitere Informationen zu APIs, die Ausnahmen in .NET Core auslösen, finden Sie unter [APIs, die grundsätzlich Ausnahmen in .NET Core auslösen](../compatibility/unsupported-apis.md).

1. An diesem Punkt können Sie zu .NET Core als Ziel (im Allgemeinen für Anwendungen) oder .NET Standard (für Bibliotheken) wechseln.

   Die Wahl zwischen .NET Core und .NET Standard hängt größtenteils davon ab, wo das Projekt ausgeführt werden soll. Wenn es sich um eine Bibliothek handelt, die von anderen Anwendungen verwendet oder über NuGet verteilt wird, wird in der Regel .NET Standard als Ziel bevorzugt. Es gibt jedoch möglicherweise APIs, die aus Leistungsgründen oder anderen Gründen nur in .NET Core verfügbar sind. Wenn dies der Fall ist, sollte .NET Core möglicherweise mit einem verfügbaren .NET Standard-Build als Ziel sowie mit verringerter Leistung oder Funktionalität verwendet werden. Wenn Sie auf .NET Standard abzielen, ist das Projekt für die Ausführung auf neuen Plattformen (wie WebAssembly) bereit. Wenn das Projekt Abhängigkeiten von bestimmten App-Frameworks (wie ASP.NET Core) aufweist, wird das Ziel durch das, was die Abhängigkeiten unterstützen, eingeschränkt.

   Wenn keine Präprozessordirektiven für die bedingte Kompilierung des Codes für .NET Framework oder .NET Standard vorhanden sind, gestaltet sich dies so einfach, wie das Auffinden der folgenden Elemente in der Projektdatei:

   ```xml
   <TargetFramework>net472</TargetFramework>
   ```

   und wechseln Sie zum gewünschten Framework. Für .NET Core 3.1 wäre dies:

   ```xml
   <TargetFramework>netcoreapp3.1</TargetFramework>
   ```

   Wenn es sich hierbei jedoch um eine Bibliothek handelt, die weiterhin .NET Framework-spezifische Builds unterstützen soll, können Sie [mehrere Ziele](../../standard/library-guidance/cross-platform-targeting.md) verwenden, indem Sie durch Folgendes ersetzen:

   ```xml
   <TargetFrameworks>net472;netstandard2.0</TargetFrameworks>
   ```

   Wenn Sie Windows-spezifische APIs verwenden (z. B. Registrierungszugriff), sollten Sie das [Windows Compatibility Pack](./windows-compat-pack.md) installieren.

## <a name="next-steps"></a>Nächste Schritte

> [!div class="nextstepaction"]
> [Analysieren von Abhängigkeiten](third-party-deps.md)
> [Packen eines NuGet-Pakets](../deploying/creating-nuget-packages.md)

## <a name="see-also"></a>Siehe auch

- [Migration von ASP.NET zu ASP.NET Core](/aspnet/core/migration/proper-to-2x)
- [Migrieren von WPF-Apps zu .NET Core](/dotnet/desktop/wpf/migration/convert-project-from-net-framework)
- [Migrieren einer Windows Forms-App zu .NET Core](winforms.md)
