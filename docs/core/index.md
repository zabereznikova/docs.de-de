---
title: .NET Core
description: .NET Core
keywords: .NET, .NET Core
author: richlander
ms.author: mairaw
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: f2b312cb-f80c-4b0d-9101-93908f06a6fa
ms.translationtype: Human Translation
ms.sourcegitcommit: d97a1501ad25b683cbb5d7fbd8bd1b137f7f4046
ms.openlocfilehash: 132551673f97142a90513d43d7690867c3d00295
ms.contentlocale: de-de
ms.lasthandoff: 04/10/2017

---

# <a name="net-core"></a>.NET Core

> Sehen Sie sich die [Lernprogramme „Erste Schritte“](getting-started.md) an, und lernen Sie, wie Sie eine einfache .NET Core-Anwendung erstellen können. Es dauert nur wenige Minuten bis Ihre erste App funktioniert und ausgeführt wird.

.NET Core ist eine allgemeine Entwicklungsplattform, die von Microsoft und der .NET-Community auf [GitHub](https://github.com/dotnet/core) verwaltet wird. Sie ist plattformübergreifend, wird von Windows, Mac OS und Linux unterstützt, und kann auf Geräten, in der Cloud und in eingebetteten/IoT-Szenarios verwendet werden. 

Die folgenden Merkmale definieren .NET Core am besten:

- **Flexible Bereitstellung:** Kann in Ihre App integriert oder parallel Benutzer - oder Computerweit installiert werden.
- **Plattformübergreifend:** Wird auf Windows, macOS und Linux ausgeführt, und kann auf andere Betriebssystemen portiert werden. Die [unterstützten Betriebssysteme (BS)](https://github.com/dotnet/core/blob/master/roadmap.md), CPUs und Anwendungsszenarios wachsen im Laufe der Zeit, und werden von Microsoft, anderen Unternehmen oder Einzelpersonen bereitgestellt.
- **Befehlszeilen-Tools:** Alle Produkt-Szenarios können in der Befehlszeile ausgeführt werden. 
- **Kompatibel:** .NET Core ist über die [.NET Standardbibliothek](../standard/library.md) mit .NET Framework, Xamarin und Mono kompatibel.
- **Open Source:** Die .NET Core-Plattform ist eine Open Source-Plattform, die MIT- und Apache 2-Lizenzen verwendet. Dokumentation ist lizenziert unter [CC-BY](https://creativecommons.org/licenses/by/4.0/). .NET Core ist ein [.NET Foundation](https://dotnetfoundation.org/)-Projekt.
- **Von Microsoft unterstützt:** .NET Core wird per [.NET Core-Unterstützung](https://www.microsoft.com/net/core/support/) von Microsoft unterstützt

## <a name="composition"></a>Komposition

.NET Core besteht aus den folgenden Teilen:

- Eine [.NET-Laufzeit](https://github.com/dotnet/coreclr), die ein Typsystem, das Laden einer Assembly, einen Garbage Collector, ein systemeigenes Interop und andere grundlegende Dienste bereitstellt. 
- Eine Reihe von [Framework-Bibliotheken](https://github.com/dotnet/corefx), die primitive Datentypen, Anwendungskompositionstypen und grundlegende Hilfsprogramme bereitstellen. 
- Ein [Satz von SDK-Tools](https://github.com/dotnet/cli) und [Sprachcompiler](https://github.com/dotnet/roslyn), die die grundlegende Entwicklererfahrung ermöglichen, sind in der [.NET Core SDK](sdk.md) verfügbar.
- Der „Dotnet“-Anwendungs-Host, der zum Starten von .NET Core-Anwendungen verwendet wird. Er wählt und hostet die Laufzeit, stellt eine Richtlinie zum Laden der Assembly bereit und startet die Anwendung. Der gleiche Host startet auch SDK-Tools auf die gleiche Weise.

### <a name="languages"></a>Sprachen

C#- und F#-Sprachen (Visual Basic kommt demnächst) können verwendet werden, um Anwendungen und Bibliotheken für .NET Core zu schreiben. Die Compiler werden auf .NET Core ausgeführt, und ermöglichen es Ihnen, .NET Core dort zu entwickeln, wo es ausgeführt wird. In der Regel verwenden Sie die Compiler nicht direkt, sondern indirekt durch die SDK-Tools.

Die C#- und F#-Compiler und die .NET Core-Tools werden oder können in mehrere Text-Editoren und IDEs, einschließlich Visual Studio, [Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp), Sublime Text und Vim integriert werden. .NET Core ist somit eine Option in Ihrer bevorzugten Programmierumgebung und im Betriebssystem. Diese Integration wird teilweise von den Leuten vom [OmniSharp-Projekt](http://www.omnisharp.net/) bereitgestellt.

### <a name="net-apis-and-compatibility"></a>.NET-APIs und Kompatibilität

.NET Core kann als plattformübergreifende Version von .NET Framework, auf der Ebene der .NET Framework Base Class Libraries (BCL) angesehen werden. Es implementiert die [.NET-Standardbibliothek](../standard/library.md)-Spezifikation. .NET Core bietet eine Teilmenge der APIs, die im .NET Framework oder in Mono/Xamarin verfügbar sind. In einigen Fällen sind die Typen nicht vollständig implementiert (einige Mitglieder sind nicht verfügbar oder wurden verschoben).

Sehen Sie sich die [.NET Core Roadmap](https://github.com/dotnet/core/blob/master/roadmap.md) an, um mehr über die .NET Core-API-Roadmap zu erfahren.

### <a name="relationship-to-the-net-standard-library"></a>Beziehung mit der .NET-Standardbibliothek

Die [.NET-Standardbibliothek](../standard/library.md) ist eine API-Spezifikation, die den konsistenten Satz von .NET-APIs beschreibt, die Entwickler in jeder .NET-Implementierung erwarten können. .NET-Implementierungen müssen diese Spezifikationen implementieren, um als konform mit .NET-Standardbibliotheken eingestuft zu werden und Bibliotheken zu unterstützen, die auf .NET-Standardbibliothek abzielen. 

.NET Core implementiert die .NET-Standardbibliothek und unterstützt daher .NET-Standardbibliotheken.

### <a name="workloads"></a>Arbeitslasten

.NET Core selbst beinhaltet ein einziges Anwendungsmodell ‒ Konsolenanwendungen ‒ die für Tools, lokale Dienste und textbasierte Spiele nützlich sind. Weitere Anwendungsmodelle wurden zusätzlich zu .NET Core erstellt, um die Funktionalitäten zu erweitern, z.B.:

- [ASP.NET Core](https://docs.microsoft.com/aspnet/core/)
- [Windows 10 Universelle Windows-Plattform (UWP)](https://developer.microsoft.com/windows)
- [Xamarin.Forms](https://www.xamarin.com/forms)

### <a name="open-source"></a>Open Source

[.NET Core](https://github.com/dotnet/core) ist Open Source (MIT-Lizenz) und wurde von Microsoft im Jahr 2014 zur [.NET Foundation](https://dotnetfoundation.org) hinzugefügt. Es ist jetzt eines der aktivsten .NET-Foundation-Projekte. Es kann kostenlos von Einzelpersonen und Unternehmen, einschließlich persönlicher, wissenschaftlicher oder kommerzieller Zwecke übernommen werden. Mehrere Unternehmen verwenden .NET Core als Teil von Anwendungen, Tools, neuen Plattformen und Hostingdiensten. Einige dieser Unternehmen leisten auf GitHub bedeutende Beiträge zu .NET Core, und bieten eine Anleitung für die Produktentwicklung als Teil der [.NET Foundation Technical Steering Group](https://dotnetfoundation.org/blog/tsg-welcome) (Technische Steuerungsgruppe).

## <a name="acquisition"></a>Erwerb

.NET Core wird auf zwei Arten verteilt: als Pakete auf NuGet.org und als eigenständige Verteilungen.

### <a name="distributions"></a>Verteilungen

Sie können .NET Core auf der Seite [.NET Core Erste Schritte](https://www.microsoft.com/net/core) herunterladen.

- Die Verteilung *Microsoft .NET Core* enthält die CoreCLR-Runtime, zugehörige Bibliotheken, einen Konsolenanwendungshost und den Anwendungsstarter `dotnet`. Sie wird durch die [`Microsoft.NETCore.App`](https://www.nuget.org/packages/Microsoft.NETCore.App)-Metapakete beschrieben.
- Die Verteilung *Microsoft .NET Core-SDK* enthält .NET Core und eine Reihe von Tools zum Wiederherstellen von NuGet-Paketen und Kompilieren und Erstellen von Anwendungen. 

In der Regel installieren Sie zunächst .NET Core-SDK und beginnen dann mit der .NET Core-Entwicklung. Sie können zusätzliche .NET Core (möglicherweise Vorabversion)-Builds installieren.

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

Es wird häufig gefragt, wie .NET Core implementiert wird, um mehrere Betriebssysteme zu unterstützen. In der Regel wird gefragt, ob es separate Implementierungen gibt oder [bedingte Kompilierung](https://en.wikipedia.org/wiki/Conditional_compilation) verwendet wird. Beides wird mit starkem Bias für bedingte Kompilierung durchgeführt.

Sie sehen im Diagramm unten, dass die große Mehrheit der [CoreFX](https://github.com/dotnet/corefx) aus plattformneutralem Code sind, der auf allen Plattformen gemeinsam genutzt wird. Ein plattformneutraler Code kann als einzelne, tragbare Assembly implementiert werden, die auf allen Plattformen verwendet wird.

![CoreFX: Zeilen-Code pro Plattform](../images/corefx-platforms-loc.png)

Windows- und Unix-Implementierungen haben eine ähnliche Größe. Windows verfügt über eine größere Implementierung, da CoreFX einige Funktionen nur für Windows implementiert, wie z.B. [Microsoft.Win32.Registry](https://github.com/dotnet/corefx/tree/master/src/Microsoft.Win32.Registry), jedoch noch keine Konzepte nur für Unix implementiert. Außerdem sehen Sie, dass die Mehrheit der Linux- und Mac OS-Implementierungen für mehrere Unix-Implementierungen verwendet werden, während die spezifischen Linux- und Mac OS-Implementierungen ungefähr gleich groß sind.


Es gibt eine Mischung aus plattformspezifischen und plattformneutralen Bibliotheken in .NET Core. Sie können das Muster in einigen Beispielen sehen:

- [CoreCLR](https://github.com/dotnet/coreclr) ist plattformspezifisch. Es ist in C/C++ erstellt, und ist von der Konstruktion plattformspezifisch.
- [System.IO](https://github.com/dotnet/corefx/tree/master/src/System.IO) und [System.Security.Cryptography.Algorithms](https://github.com/dotnet/corefx/tree/master/src/System.Security.Cryptography.Algorithms) sind plattformspezifisch, angesichts der Tatsache, dass sich die Speicherung und Kryptografie-APIs je nach Betriebssystem stark voneinander unterscheiden. 
- [System.Collections](https://github.com/dotnet/corefx/tree/master/src/System.Collections) und [System.Linq](https://github.com/dotnet/corefx/tree/master/src/System.Linq) sind plattformneutral, angesichts der Tatsache, dass sie Datenstrukturen erstellen und verwenden.

## <a name="comparisons-to-other-net-platforms"></a>Vergleiche mit anderen .NET- Plattformen

Möglicherweise ist es am einfachsten, die Größe und Form von .NET Core durch einen Vergleich mit vorhandenen .NET-Plattformen zu verstehen. 

### <a name="comparison-with-net-framework"></a>Vergleich mit .NET- Framework

Die .NET-Plattform wurde erstmals in 2000 von Microsoft angekündigt, und hat sich dann von dort aus entwickelt. Das .NET Framework war in den 15 Jahren und mehr seither das primäre .NET-Produkt von Microsoft. 

Die Hauptunterschiede zwischen .NET Core und dem .NET Framework: 

- **Anwendungsmodelle** ‒ .NET Core unterstützt nicht alle Anwendungsmodelle für .NET Framework. Teilweise liegt das daran, da viele von ihnen auf Windows-Technologien, wie z.B. WPF (basierend auf DirectX) erstellt werden. Die Konsole und ASP.NET Core-Anwendungsmodelle werden von .NET Core und .NET Framework unterstützt. 
- **APIs** ‒ .NET Core enthält viele der gleichen, aber weniger APIs als .NET Framework und mit einer anderen Verarbeitung (Assemblynamen sind unterschiedlich; Typform unterscheidet sich in wichtigen Fällen). Diese Unterschiede erfordern derzeit in der Regel Änderungen der Portquelle von .NET Core. .NET Core implementiert die [.NET-Standardbibliothek](../standard/library.md)-API, die ausgeweitet wird, um mit der Zeit mehr BCL-API von .NET Framework zu enthalten.
- **Subsysteme** ‒ .NET Core implementiert eine Teilmenge der Subsysteme in .NET Framework, mit dem Ziel einer einfacheren Implementierung und einem einfacheren Programmiermodell. Code Access Security (CAS) wird z.B. nicht unterstützt, während Reflektion unterstützt wird.
- **Plattformen** ‒ .NET Framework unterstützt Windows und Windows-Server- während .NET Core auch Mac OS und Linux unterstützt.
- **Open Source** ‒ .NET Core ist Open Source, während eine [schreibgeschützte Teilmenge von .NET Framework](https://github.com/microsoft/referencesource) Open Source ist.

Während .NET Core einzigartig ist und sich erheblich von .NET Framework und anderen .NET-Plattformen unterscheidet, ist es einfach, Code entweder mit der Quell. oder Binärdatei- Freigabeverfahren freizugeben. 

### <a name="comparison-with-mono"></a>Vergleich mit Mono

[Mono](http://www.mono-project.com/) ist die ursprüngliche plattformübergreifende und [Open Source](https://github.com/mono/mono) .NET-Implementierung, die erstmals im Jahr 2004 versendet wurde. Sie kann als Community-Klon des .NET Frameworks betrachtet werden. Das Mono-Projektteam griff auf die offenen [.NET-Standards](https://github.com/dotnet/coreclr/blob/master/Documentation/project-docs/dotnet-standards.md) (insbesondere ECMA 335) zurück, die von Microsoft veröffentlicht wurden, um eine kompatible Implementierung bereitzustellen.

Die Hauptunterschiede zwischen .NET Core und Mono:

- **Anwendungsmodelle** ‒ Mono unterstützt eine Teilmenge der .NET Framework-Anwendungsmodelle (z.B. Windows Forms) und einige zusätzliche (z.B. [Xamarin.iOS](https://www.xamarin.com/platform)) über das Xamarin-Produkt. .NET Core unterstützt diese nicht.
- **APIs** ‒ Mono unterstützt eine [große Teilmenge](http://docs.go-mono.com/?link=root%3a%2fclasslib) der .NET Framework-APIs, die die gleichen Assemblynamen und Fakturierung verwenden.
- **Plattformen** ‒ Mono unterstützt zahlreiche Plattformen und CPUs.
- **Open Source** ‒ Mono und .NET Core verwenden beide die MIT-Lizenz und sind .NET Foundation-Projekte.
- **Fokus** ‒ Der primäre Fokus von Mono in den letzten Jahren waren die mobilen Plattformen, während sich .NET Core auf Cloud-Arbeitslasten konzentriert.

