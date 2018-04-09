---
title: Leitfaden für .NET Core
description: .NET Core ist eine modulare, hochleistungsfähige Implementierung von .NET zur Erstellung von Windows-, Linux- und Mac-Apps. Erfahren Sie mehr über .NET Core, und legen Sie los.
keywords: .NET, .NET Core
author: richlander
ms.author: mairaw
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: f2b312cb-f80c-4b0d-9101-93908f06a6fa
ms.workload:
- dotnetcore
ms.openlocfilehash: de71e043533d7a7d3d7d3fd3af0a8530c0e145b6
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="net-core-guide"></a>Leitfaden für .NET Core

> Sehen Sie sich die [Einsteigertutorials](get-started.md) an. Dort erfahren Sie, wie Sie eine einfache .NET Core-Anwendung erstellen. Es dauert nur wenige Minuten, bis Ihre erste App einsatzbereit ist.

.NET Core ist eine universelle Entwicklungsplattform, die von Microsoft und der .NET-Community auf [GitHub](https://github.com/dotnet/core) gepflegt wird. Sie ist plattformübergreifend, d.h., sie unterstützt Windows, macOS und Linux und kann lokal, in der Cloud und in Einbettungs- und IoT-Szenarios verwendet werden. 

Die folgenden Merkmale definieren .NET Core am besten:

- **Flexible Bereitstellung:** Kann in Ihre App eingebunden oder parallel zu ihr installiert werden – auf Benutzer- oder Computerbasis.
- **Plattformübergreifend:** Ist unter Windows, macOS und Linux lauffähig und kann auf andere Betriebssystemen portiert werden. Die Bandbreite [unterstützter Betriebssysteme](https://github.com/dotnet/core/blob/master/roadmap.md), CPUs und Anwendungsszenarios wird sich im Laufe der Zeit erweitern. Die Bereitstellung erfolgt dabei durch Microsoft, weitere Unternehmen oder Einzelpersonen.
- **Befehlszeilen-Tools:** Alle Produktszenarios können auf der Befehlszeile geübt werden. 
- **Kompatibel:** .NET Core ist über die [.NET Standardbibliothek](../standard/net-standard.md) mit .NET Framework, Xamarin und Mono kompatibel.
- **Open Source:** Die .NET Core-Plattform ist eine Open Source-Plattform, die MIT- und Apache 2-Lizenzen verwendet. Dokumentation ist lizenziert unter [CC-BY](https://creativecommons.org/licenses/by/4.0/). .NET Core ist ein [.NET Foundation](https://dotnetfoundation.org/)-Projekt.
- **Von Microsoft unterstützt:** .NET Core wird per [.NET Core-Unterstützung](https://www.microsoft.com/net/core/support/) von Microsoft unterstützt

## <a name="composition"></a>Aufbau

.NET Core umfasst folgende Bestandteile:

- Eine [.NET-Laufzeit](https://github.com/dotnet/coreclr), die ein Typsystem, eine Funktion zum Laden von Assemblys, einen Garbage Collector, natives Interop und andere grundlegende Dienste bereitstellt. 
- Verschiedene [Frameworkbibliotheken](https://github.com/dotnet/corefx), die primitive Datentypen, Typen zur Anwendungsgestaltung und grundlegende Hilfsprogramme bereitstellen. 
- Eine Anzahl [SDK-Tools](https://github.com/dotnet/cli) und [Sprachcompiler](https://github.com/dotnet/roslyn), zur Implementierung der grundlegenden Entwicklungsfunktionen über das [.NET Core SDK](sdk.md).
- Der „Dotnet“-App-Host, der zum Starten von .NET Core-Anwendungen verwendet wird. Er wählt und hostet die Laufzeit, stellt eine Richtlinie zum Laden der Assembly bereit und startet die Anwendung. Der gleiche Host startet auch SDK-Tools auf die gleiche Weise.

### <a name="languages"></a>Sprachen

C#-, Visual Basic- und F#-Sprachen können verwendet werden, um Anwendungen und Bibliotheken für .NET Core zu schreiben. Die Compiler werden auf .NET Core ausgeführt, und ermöglichen es Ihnen, .NET Core dort zu entwickeln, wo es ausgeführt wird. In der Regel verwenden Sie die Compiler nicht direkt, sondern indirekt durch die SDK-Tools.

Die C#-, Visual Basic- und F#-Compiler und die .NET Core-Tools sind integriert bzw. können in mehrere Text-Editoren und IDEs, einschließlich Visual Studio, [Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp), Sublime Text und Vim integriert werden. .NET Core ist somit eine Option in Ihrer bevorzugten Programmierumgebung und im Betriebssystem. Diese Integration wird teilweise von den Leuten vom [OmniSharp-Projekt](http://www.omnisharp.net/) bereitgestellt.

### <a name="net-apis-and-compatibility"></a>.NET-APIs und Kompatibilität

.NET Core kann als plattformübergreifende Version von .NET Framework, auf der Ebene der .NET Framework Base Class Libraries (BCL) angesehen werden. Es implementiert die [.NET-Standard](../standard/net-standard.md)-Spezifikation. .NET Core bietet eine Teilmenge der APIs, die im .NET Framework oder in Mono/Xamarin verfügbar sind. In einigen Fällen sind die Typen nicht vollständig implementiert (einige Mitglieder sind nicht verfügbar oder wurden verschoben).

Sehen Sie sich die [.NET Core Roadmap](https://github.com/dotnet/core/blob/master/roadmap.md) an, um mehr über die .NET Core-API-Roadmap zu erfahren.

### <a name="relationship-to-net-standard"></a>Beziehung zu .NET-Standard

[.NET-Standard](../standard/net-standard.md) ist eine API-Spezifikation, die den konsistenten Satz von .NET-APIs beschreibt, die Entwickler in jeder .NET-Implementierung erwarten können. .NET-Implementierungen müssen diese Spezifikationen implementieren, um als konform mit .NET-Standard eingestuft zu werden und Bibliotheken zu unterstützen, die auf .NET-Standard abzielen. 

.NET Core implementiert .NET-Standard und unterstützt daher .NET-Standardbibliotheken.

### <a name="workloads"></a>Arbeitslasten

.NET Core selbst beinhaltet ein einziges Anwendungsmodell ‒ Konsolenanwendungen ‒ die für Tools, lokale Dienste und textbasierte Spiele nützlich sind. Weitere Anwendungsmodelle wurden zusätzlich zu .NET Core erstellt, um die Funktionalitäten zu erweitern, z.B.:

- [ASP.NET Core](/aspnet/core/)
- [Windows 10 Universelle Windows-Plattform (UWP)](https://developer.microsoft.com/windows)
- [Xamarin.Forms für UWP](https://www.xamarin.com/forms)

### <a name="open-source"></a>Open Source

[.NET Core](https://github.com/dotnet/core) ist Open Source (MIT-Lizenz) und wurde von Microsoft im Jahr 2014 zur [.NET Foundation](https://dotnetfoundation.org) hinzugefügt. Es ist jetzt eines der aktivsten .NET-Foundation-Projekte. Es kann kostenlos von Einzelpersonen und Unternehmen, einschließlich persönlicher, wissenschaftlicher oder kommerzieller Zwecke übernommen werden. Mehrere Unternehmen verwenden .NET Core als Teil von Anwendungen, Tools, neuen Plattformen und Hostingdiensten. Einige dieser Unternehmen leisten auf GitHub bedeutende Beiträge zu .NET Core, und bieten eine Anleitung für die Produktentwicklung als Teil der [.NET Foundation Technical Steering Group](https://dotnetfoundation.org/blog/tsg-welcome) (Technische Steuerungsgruppe).

## <a name="acquisition"></a>Erwerb

.NET Core wird auf zwei Arten verteilt: als Pakete auf NuGet.org und als eigenständige Verteilungen.

### <a name="distributions"></a>Verteilungen

Sie können .NET Core auf der Seite [.NET Core Erste Schritte](https://www.microsoft.com/net/core) herunterladen.

- Die Verteilung *Microsoft .NET Core* enthält die CoreCLR-Runtime, zugehörige Bibliotheken, einen Konsolenanwendungshost und den Anwendungsstarter `dotnet`. Sie wird durch die [`Microsoft.NETCore.App`](https://www.nuget.org/packages/Microsoft.NETCore.App)-Metapakete beschrieben.
- Die Verteilung *Microsoft .NET Core SDK* enthält .NET Core und eine Reihe von Tools zum Wiederherstellen von NuGet-Paketen und Kompilieren und Erstellen von Anwendungen. 

In der Regel installieren Sie zunächst .NET Core SDK und beginnen dann mit der .NET Core-Entwicklung. Sie können zusätzliche .NET Core-Builds (möglicherweise in der Vorabversion) installieren.

### <a name="packages"></a>Pakete

- [.NET Core-Pakete](packages.md) enthalten die .NET Core Runtime und -Bibliotheken (Verweisassemblys und Implementierungen). Beispielsweise [System.Net.Http](https://www.nuget.org/packages/System.Net.Http/).
- [.NET Core-Metapakete](packages.md) beschreiben verschiedene Ebenen und Anwendungsmodelle, indem sie auf die entsprechenden versionsspezifischen Bibliothekspakete verweisen.

## <a name="architecture"></a>Architektur

.NET Core ist eine plattformübergreifende .NET-Implementierung. Die primären, für .NET Core einzigartigen architektonischen Fragen beziehen sich auf die Erstellung von plattformspezifischen Implementierungen für unterstützte Plattformen.

### <a name="environments"></a>Umgebungen

.NET Core wird von Microsoft auf Windows, Mac OS und Linux unterstützt. Auf Linux unterstützt Microsoft hauptsächlich .NET Core, das auf Red Hat Enterprise Linux (RHEL) und Debian Distributionsfamilien ausgeführt wird.

.NET Core unterstützt derzeit X64 CPUs. Auf Windows wird X86 ebenfalls unterstützt. ARM64 und ARM32 werden durchgeführt.

Die [.NET Core Roadmap](https://github.com/dotnet/core/blob/master/roadmap.md) enthält ausführlichere Informationen zur Arbeitsauslastung, CPU-Umgebung, zum Betriebssystem und zu Plänen.

Andere Gruppen oder Unternehmen unterstützen .NET Core möglicherweise für andere Anwendungstypen und Anwendungsumgebungen.

### <a name="designed-for-adaptability"></a>Für Anpassungsfähigkeit entworfen

.NET Core wurde als sehr ähnliches, aber auch einzigartiges Produkt im Vergleich zu anderen .NET-Produkten erstellt. Es wurde entwickelt, um umfassende Anpassungsfähigkeit auf neuen Plattformen zu aktivieren, für neue Arbeitsbelastungen und mit neuen Compiler-Toolchains. Es verfügt über mehrere Betriebssysteme und CPU-Ports und kann an vielen anderen portiert werden. Ein Beispiel ist das [LLILC](https://github.com/dotnet/llilc)-Projekt, das ein früher Prototyp systeminterner Kompilierung für .NET Core über die [LLVM](http://llvm.org/)-Compiler ist.

Das Produkt wird in mehrere Stücke aufgeteilt, und die verschiedenen Teile können an neue Plattformen auf unterschiedlichen Zeitplänen angepasst werden. Die Laufzeit und grundlegende plattformspezifische Bibliotheken müssen als eine Einheit portiert werden. Plattformagnostische Bibliotheken sollten wie vorhanden von der Konstruktion auf allen Plattformen funktionieren. Es gibt eine Projektverschiebung zur Verminderung der plattformspezifischen Implementierungen, um die Effizienz der Entwickler zu erhöhen. Wenn ein Algorithmus oder API so vollständig oder teilweise implementiert werden kann, wird ein plattformneutraler C#-Code bevorzugt.

Häufig wird die Frage gestellt, wie .NET Core so implementiert wird, dass mehrere Betriebssysteme unterstützt werden können. Dabei wird meistens gefragt, ob es separate Implementierungen gibt oder die [bedingte Kompilierung](https://en.wikipedia.org/wiki/Conditional_compilation) verwendet wird. Die Antwort lautet: Beide Ansätze werden eingesetzt, aber der Schwerpunkt liegt eindeutig auf der bedingten Kompilierung.

Sie sehen im Diagramm unten, dass die große Mehrheit der [CoreFX](https://github.com/dotnet/corefx) aus plattformneutralem Code sind, der auf allen Plattformen gemeinsam genutzt wird. Ein plattformneutraler Code kann als einzelne, tragbare Assembly implementiert werden, die auf allen Plattformen verwendet wird.

![CoreFX: Zeilen-Code pro Plattform](../images/corefx-platforms-loc.png)

Windows- und Unix-Implementierungen haben eine ähnliche Größe. Windows verfügt über eine größere Implementierung, da CoreFX einige Funktionen nur für Windows implementiert, wie z.B. [Microsoft.Win32.Registry](https://github.com/dotnet/corefx/tree/master/src/Microsoft.Win32.Registry), jedoch noch keine Konzepte nur für Unix implementiert. Außerdem sehen Sie, dass die Mehrheit der Linux- und Mac OS-Implementierungen für mehrere Unix-Implementierungen verwendet werden, während die spezifischen Linux- und Mac OS-Implementierungen ungefähr gleich groß sind.


Es gibt eine Mischung aus plattformspezifischen und plattformneutralen Bibliotheken in .NET Core. Sie können das Muster in einigen Beispielen sehen:

- [CoreCLR](https://github.com/dotnet/coreclr) ist plattformspezifisch. Es ist in C/C++ erstellt, und ist von der Konstruktion plattformspezifisch.
- [System.IO](https://github.com/dotnet/corefx/tree/master/src/System.IO) und [System.Security.Cryptography.Algorithms](https://github.com/dotnet/corefx/tree/master/src/System.Security.Cryptography.Algorithms) sind plattformspezifisch, angesichts der Tatsache, dass sich die Speicherung und Kryptografie-APIs je nach Betriebssystem stark voneinander unterscheiden. 
- [System.Collections](https://github.com/dotnet/corefx/tree/master/src/System.Collections) und [System.Linq](https://github.com/dotnet/corefx/tree/master/src/System.Linq) sind plattformneutral, angesichts der Tatsache, dass sie Datenstrukturen erstellen und verwenden.

## <a name="comparisons-to-other-net-implementations"></a>Vergleiche mit anderen .NET- Implementierungen

Möglicherweise ist es am einfachsten, die Größe und Form von .NET Core durch einen Vergleich mit vorhandenen .NET-Implementierungen zu verstehen. 

### <a name="comparison-with-net-framework"></a>Vergleich mit .NET- Framework

.NET wurde erstmals in 2000 von Microsoft angekündigt, und hat sich dann von dort aus entwickelt. Das .NET Framework war in den 15 Jahren und mehr seither die primäre .NET-Implementierung von Microsoft. 

Die Hauptunterschiede zwischen .NET Core und dem .NET Framework: 

- **Anwendungsmodelle**: .NET Core unterstützt nicht alle Anwendungsmodelle für .NET Framework. Teilweise liegt das daran, da viele von ihnen auf Windows-Technologien, wie z.B. WPF (basierend auf DirectX) erstellt werden. Die Konsole und ASP.NET Core-Anwendungsmodelle werden von .NET Core und .NET Framework unterstützt. 
- **APIs**: .NET Core enthält viele der gleichen, aber weniger APIs als .NET Framework und mit einer anderen Verarbeitung (Assemblynamen sind unterschiedlich; Typform unterscheidet sich in wichtigen Fällen). Diese Unterschiede erfordern derzeit in der Regel Änderungen der Portquelle von .NET Core. .NET Core implementiert die [.NET-Standard](../standard/net-standard.md)-API, die ausgeweitet wird, um mit der Zeit mehr BCL-API von .NET Framework zu enthalten.
- **Subsysteme**: .NET Core implementiert eine Teilmenge der Subsysteme in .NET Framework, mit dem Ziel einer einfacheren Implementierung und einem einfacheren Programmiermodell. Code Access Security (CAS) wird z.B. nicht unterstützt, während Reflektion unterstützt wird.
- **Plattformen**: .NET Framework unterstützt Windows und Windows-Server- während .NET Core auch Mac OS und Linux unterstützt.
- **Open Source**: .NET Core ist Open Source, während eine [schreibgeschützte Teilmenge von .NET Framework](https://github.com/microsoft/referencesource) Open Source ist.

Während .NET Core einzigartig ist und sich erheblich von .NET Framework und anderen .NET-Implementierungen unterscheidet, ist es einfach, Code entweder mit der Quell. oder Binärdatei- Freigabeverfahren freizugeben. 

### <a name="comparison-with-mono"></a>Vergleich mit Mono

[Mono](http://www.mono-project.com/) ist die ursprüngliche plattformübergreifende und [Open Source](https://github.com/mono/mono) .NET-Implementierung, die erstmals im Jahr 2004 versendet wurde. Sie kann als Community-Klon des .NET Frameworks betrachtet werden. Das Mono-Projektteam griff auf die offenen [.NET-Standards](https://github.com/dotnet/coreclr/blob/master/Documentation/project-docs/dotnet-standards.md) (insbesondere ECMA 335) zurück, die von Microsoft veröffentlicht wurden, um eine kompatible Implementierung bereitzustellen.

Die Hauptunterschiede zwischen .NET Core und Mono:

- **Anwendungsmodelle**: Mono unterstützt eine Teilmenge der .NET Framework-Anwendungsmodelle (z.B. Windows Forms) und einige zusätzliche (z.B. [Xamarin.iOS](https://www.xamarin.com/platform)) über das Xamarin-Produkt. .NET Core unterstützt diese nicht.
- **APIs**: Mono unterstützt eine [große Teilmenge](http://docs.go-mono.com/?link=root%3a%2fclasslib) der .NET Framework-APIs, die die gleichen Assemblynamen und Fakturierung verwenden.
- **Plattformen**: Mono unterstützt zahlreiche Plattformen und CPUs.
- **Open Source**: Mono und .NET Core verwenden beide die MIT-Lizenz und sind .NET Foundation-Projekte.
- **Fokus**: Der primäre Fokus von Mono in den letzten Jahren waren die mobilen Plattformen, während sich .NET Core auf Cloud-Arbeitslasten konzentriert.
