---
title: Weitere Informationen zu .NET Core
description: Erfahren Sie mehr zu .NET Core.
ms.date: 09/17/2019
ms.openlocfilehash: 89740b67b294650f78cf36361548c2fe24ac80cb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79147359"
---
# <a name="about-net-core"></a>Weitere Informationen zu .NET Core

.NET Core weist folgende Merkmale auf:

- **Plattformübergreifend:** Ist unter den [Betriebssystemen](https://github.com/dotnet/core/blob/master/os-lifecycle-policy.md) Windows, macOS und Linux lauffähig.
- **Architekturübergreifende Konsistenz:** Führt Ihren Code in unterschiedlichen Architekturen (z.B. x64, x86 und ARM) mit demselben Verhalten aus.
- **Befehlszeilentools:**  Umfasst benutzerfreundliche Befehlszeilentools, mit denen Sie lokal und in Continuous Integration-Szenarios entwickeln können.
- **Flexible Bereitstellung:** Kann in Ihre App eingebunden oder parallel installiert werden (benutzer- oder systemweite Installation). Kann mit [Docker-Containern](docker/introduction.md) verwendet werden.
- **Kompatibel:** .NET Core ist über [.NET Standard](../standard/net-standard.md) mit .NET Framework, Xamarin und Mono kompatibel.
- **Open Source:** Die .NET Core-Plattform ist eine Open Source-Plattform, die MIT- und Apache 2-Lizenzen verwendet. .NET Core ist ein [.NET Foundation](https://dotnetfoundation.org/)-Projekt.
- **Von Microsoft unterstützt:** .NET Core wird entsprechend den Richtlinien unter [.NET Support Policy (Richtlinien für die .NET-Unterstützung)](https://dotnet.microsoft.com/platform/support/policy) von Microsoft unterstützt.

## <a name="languages"></a>Sprachen

C#, Visual Basic und F# können verwendet werden, um Anwendungen und Bibliotheken für .NET Core zu schreiben. Diese Sprachen können Sie in Ihren bevorzugten Text-Editoren oder integrierten Entwicklungsumgebungen (IDE, Integrated Development Environment) wie den folgenden verwenden:

- [Visual Studio](https://visualstudio.microsoft.com/vs/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link)
- [Visual Studio Code](https://code.visualstudio.com/download)
- Sublime Text
- Vim

Diese Integration wird teilweise dank der Mitwirkenden von [OmniSharp](https://www.omnisharp.net/) und [Ionide](http://ionide.io) bereitgestellt.

## <a name="apis"></a>APIs

.NET Core stellt vielseitige APIs bereit, u.a. die folgenden:

- Primitive Typen wie <xref:System.Boolean?displayProperty=nameWithType> und <xref:System.Int32?displayProperty=nameWithType>.
- Sammlungen, z.B. <xref:System.Collections.Generic.List%601?displayProperty=nameWithType> und <xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWithType>.
- Hilfstypen, z.B. <xref:System.Net.Http.HttpClient?displayProperty=nameWithType> und <xref:System.IO.FileStream?displayProperty=nameWithType>.
- Datentypen, z.B. <xref:System.Data.DataSet?displayProperty=nameWithType> und [DbSet](https://www.nuget.org/packages/Microsoft.EntityFrameworkCore/).
- Hochleistungstypen, z. B. <xref:System.Numerics.Vector?displayProperty=nameWithType> und [Pipelines](../standard/io/pipelines.md).

Durch die Implementierung der [.NET Standard](../standard/net-standard.md)-Spezifikation ist .NET Core mit .NET Framework und Mono-APIs kompatibel.

## <a name="frameworks"></a>Frameworks

Mehrere Frameworks wurden basierend auf .NET Core entwickelt:

- [ASP.NET Core](/aspnet/core/)
- [Windows 10 Universelle Windows-Plattform (UWP)](https://developer.microsoft.com/windows)
- [Tizen](https://developer.tizen.org/development/training/.net-application)

## <a name="composition"></a>Aufbau

.NET Core umfasst folgende Bestandteile:

- Eine [.NET Core-Runtime](https://github.com/dotnet/runtime/tree/master/src/coreclr), die ein Typsystem, eine Funktion zum Laden von Assemblys, einen Garbage Collector, natives Interop und andere grundlegende Dienste bereitstellt. [.NET Core-Frameworkbibliotheken](https://github.com/dotnet/runtime/tree/master/src/libraries) stellen primitive Datentypen, Typen zur Anwendungsgestaltung und grundlegende Hilfsprogramme bereit.
- Die [ASP.NET Core-Runtime](https://github.com/dotnet/aspnetcore), die ein Framework zum Erstellen moderner, cloudbasierter Anwendungen mit Internetverbindung, wie etwa Web-Apps, IoT-Apps und mobile Back-Ends, bietet.
- Das [.NET Core SDK](https://github.com/dotnet/sdk) und die Sprachcompiler ([Roslyn](https://github.com/dotnet/roslyn) und [F#](https://github.com/microsoft/visualfsharp)), die Funktionen für .NET Core-Entwickler bereitstellen.
- Der [dotnet-Befehl](./tools/dotnet.md), der zum Starten von .NET Core-Anwendungen und CLI-Befehlen verwendet wird. Er wählt und hostet die Runtime, stellt eine Richtlinie zum Laden der Assembly bereit und startet die Anwendungen und Tools.

Die Komponenten sind wie folgt verfügbar:

- [.NET Core-Runtime:](https://dotnet.microsoft.com/download) enthält die .NET Core-Runtime und -Frameworkbibliotheken.
- [ASP.NET Core-Runtime:](https://dotnet.microsoft.com/download) enthält die ASP.NET Core-Runtime sowie die .NET Core-Runtime und -Frameworkbibliotheken.
- [.NET Core SDK:](https://dotnet.microsoft.com/download) enthält die .NET Core-CLI, die ASP.NET Core-Runtime, die .NET Core-Runtime und das .NET Core-Framework.

### <a name="open-source"></a>Quelle öffnen

[.NET Core](https://github.com/dotnet/core) ist eine Open Source-Plattform ([MIT-Lizenz](https://github.com/dotnet/core/blob/master/LICENSE.TXT)) und wurde von Microsoft im Jahr 2014 zur [.NET Foundation](https://dotnetfoundation.org) hinzugefügt. Es ist jetzt eines der aktivsten .NET-Foundation-Projekte. Es kann von Einzelpersonen und Unternehmen für persönliche, wissenschaftliche oder kommerzielle Zwecke verwendet werden. Mehrere Unternehmen verwenden .NET Core als Teil von Anwendungen, Tools, neuen Plattformen und Hostingdiensten. Einige dieser Unternehmen leisten auf GitHub bedeutende Beiträge zu .NET Core, und bieten eine Anleitung für die Produktentwicklung als Teil der [.NET Foundation Technical Steering Group](https://dotnetfoundation.org/blog/tsg-welcome) (Technische Steuerungsgruppe).

### <a name="designed-for-adaptability"></a>Konzipiert für Anpassungsfähigkeit

.NET Core wurde als ähnliches, aber auch einzigartiges Produkt im Vergleich zu anderen .NET-Produkten erstellt. Das Produkt wurde entwickelt, um eine umfassende Anpassung an neue Plattformen und Arbeitsauslastungen zu ermöglichen. Es verfügt über mehrere Betriebssysteme und CPU-Ports (und kann auf viele weitere portiert werden).

Das Produkt ist in mehrere Teile aufgeteilt, und die verschiedenen Teile können zu unterschiedlichen Zeitpunkten an neue Plattformen angepasst werden. Die Laufzeit und grundlegende plattformspezifische Bibliotheken müssen als eine Einheit portiert werden. Plattformagnostische Bibliotheken sollten wie vorhanden von der Konstruktion auf allen Plattformen funktionieren. Es gibt eine Projektverschiebung zur Verminderung der plattformspezifischen Implementierungen, um die Effizienz der Entwickler zu erhöhen. Wenn ein Algorithmus oder API so vollständig oder teilweise implementiert werden kann, wird ein plattformneutraler C#-Code bevorzugt.

Häufig wird die Frage gestellt, wie .NET Core so implementiert wird, dass mehrere Betriebssysteme unterstützt werden können. Dabei wird meistens gefragt, ob es separate Implementierungen gibt oder die [bedingte Kompilierung](https://en.wikipedia.org/wiki/Conditional_compilation) verwendet wird. Die Antwort lautet: Beide Ansätze werden eingesetzt, aber der Schwerpunkt liegt eindeutig auf der bedingten Kompilierung.

Im folgenden Diagramm sehen Sie, dass die große Mehrheit der [.NET Core-Bibliotheken](https://github.com/dotnet/runtime/tree/master/src/libraries) plattformneutralen Code enthalten, der auf allen Plattformen gemeinsam genutzt wird. Ein plattformneutraler Code kann als einzelne, tragbare Assembly implementiert werden, die auf allen Plattformen verwendet wird.

![CoreFX: Codezeilen pro Plattform](../images/corefx-platforms-loc.png)

Windows- und Unix-Implementierungen haben eine ähnliche Größe. Windows verfügt über eine größere Implementierung, da .NET Core-Bibliotheken einige auf Windows beschränkte Funktionen implementieren, z. B. [Microsoft.Win32.Registry](https://github.com/dotnet/runtime/tree/master/src/libraries/Microsoft.Win32.Registry), jedoch noch nicht viele auf UNIX beschränkte Konzepte. Außerdem sehen Sie, dass die Mehrheit der Linux- und Mac OS-Implementierungen für mehrere Unix-Implementierungen verwendet werden, während die spezifischen Linux- und Mac OS-Implementierungen ungefähr gleich groß sind.

Es gibt eine Mischung aus plattformspezifischen und plattformneutralen Bibliotheken in .NET Core. Sie können das Muster in einigen Beispielen sehen:

- [CoreCLR](https://github.com/dotnet/runtime/tree/master/src/coreclr) ist plattformspezifisch. Es baut auf Subsystemen des Betriebssystems auf, z.B. auf dem Speicher-Manager und dem Threadplaner.
- [System.IO](https://github.com/dotnet/runtime/tree/master/src/libraries/System.IO) und [System.Security.Cryptography.Algorithms](https://github.com/dotnet/runtime/tree/master/src/libraries/System.Security.Cryptography.Algorithms) sind plattformspezifisch, angesichts der Tatsache, dass sich Speicher- und Kryptografie-APIs je nach Betriebssystem voneinander unterscheiden.
- [System.Collections](https://github.com/dotnet/runtime/tree/master/src/libraries/System.Collections) und [System.Linq](https://github.com/dotnet/runtime/tree/master/src/libraries/System.Linq) sind plattformneutral, angesichts der Tatsache, dass sie Datenstrukturen erstellen und verwenden.

## <a name="comparisons-to-other-net-implementations"></a>Vergleiche mit anderen .NET- Implementierungen

Es ist wohl am einfachsten, die Größe und Form von .NET Core durch einen Vergleich mit vorhandenen .NET-Implementierungen zu verstehen.

### <a name="comparison-with-net-framework"></a>Vergleich mit .NET- Framework

.NET wurde erstmals in 2000 von Microsoft angekündigt, und hat sich dann von dort aus entwickelt. Das .NET Framework war in den letzten zwei Jahrzehnten die primäre .NET-Implementierung von Microsoft.

Die Hauptunterschiede zwischen .NET Core und dem .NET Framework:

- **App-Modelle:** .NET Core unterstützt nicht alle .NET Framework-App-Modelle. Insbesondere unterstützt es weder ASP.NET Web Forms noch ASP.NET MVC, aber es unterstützt ASP.NET Core MVC. Ab .NET Core 3.0 unterstützt .NET Core auch WPF und Windows Forms, jedoch nur unter Windows.
- **APIs:** .NET Core enthält viele .NET Framework-Basisklassenbibliotheken mit unterschiedlicher Verarbeitung (die Assemblynamen unterscheiden sich; in Typen bereitgestellte Members unterscheiden sich in wichtigen Fällen). Diese Unterschiede erfordern gelegentlich Änderungen der Portquelle von .NET Core. Weitere Informationen finden Sie unter [.NET Portability Analyzer](../standard/analyzers/portability-analyzer.md). .NET Core implementiert die [.NET-Standard](../standard/net-standard.md)-API-Spezifikation.
- **Subsysteme**: .NET Core implementiert eine Teilmenge der Subsysteme in .NET Framework, mit dem Ziel einer einfacheren Implementierung und einem einfacheren Programmiermodell. Code Access Security (CAS) wird z. B. nicht unterstützt, während Reflektion unterstützt wird.
- **Plattformen**: .NET Framework unterstützt Windows und Windows-Server- während .NET Core auch Mac OS und Linux unterstützt.
- **Open Source**: .NET Core ist Open Source, während eine [schreibgeschützte Teilmenge von .NET Framework](https://github.com/microsoft/referencesource) Open Source ist.

Obwohl .NET Core einzigartig ist und sich erheblich vom .NET Framework und anderen .NET-Implementierungen unterscheidet, ist es dennoch unkompliziert, den gleichen Code in diesen Implementierungen zu verwenden. Dazu können Sie Quell- oder Binärfreigabeverfahren verwenden.

Da .NET Core die parallele Installation unterstützt und die Runtime vollständig unabhängig vom .NET Framework ist, kann .NET Core ohne Probleme auf Computern installiert werden, auf denen .NET Framework installiert ist.

### <a name="comparison-with-mono"></a>Vergleich mit Mono

[Mono](https://www.mono-project.com/) ist die ursprüngliche plattformübergreifende Implementierung von .NET. Sie wurde zunächst als [Open-Source-](https://github.com/mono/mono)-Alternative zu .NET Framework angeboten und mit zunehmender Beliebtheit von iOS- und Android-Geräten an mobile Geräte angepasst. Sie kann als Community-Klon des .NET Frameworks betrachtet werden. Das Mono-Projektteam griff auf die offenen [.NET-Standards](https://github.com/dotnet/runtime/blob/master/docs/project/dotnet-standards.md) (insbesondere ECMA 335) zurück, die von Microsoft veröffentlicht wurden, um eine kompatible Implementierung bereitzustellen.

Die Hauptunterschiede zwischen .NET Core und Mono:

- **Anwendungsmodelle**: Mono unterstützt eine Teilmenge der .NET Framework-Anwendungsmodelle (z. B. Windows Forms) und einige zusätzliche für die mobile Entwicklung (z. B. [Xamarin.iOS](https://www.xamarin.com/platform)) über das Xamarin-Produkt. Xamarin wird von .NET Core nicht unterstützt.
- **APIs**: Mono unterstützt eine [große Teilmenge](http://docs.go-mono.com/?link=root%3a%2fclasslib) der .NET Framework-APIs, die die gleichen Assemblynamen und Fakturierung verwenden.
- **Plattformen**: Mono unterstützt zahlreiche Plattformen und CPUs.
- **Open Source**: Mono und .NET Core verwenden beide die MIT-Lizenz und sind .NET Foundation-Projekte.
- **Fokus**: In den letzten Jahren lag der primäre Fokus von Mono auf mobilen Plattformen, während sich .NET Core auf Cloud- und Desktopworkloads konzentriert hat.

## <a name="the-future"></a>Die Zukunft

Es wurde angekündigt, dass .NET 5 das nächste Release von .NET Core sein wird und eine Vereinheitlichung der Plattform darstellt. Mit dem Projekt soll .NET in einigen wesentlichen Punkten verbessert werden:

- Erstellung einer zentralen .NET-Runtime und eines Frameworks, das überall verwendet werden kann, ein einheitliches Laufzeitverhalten aufweist und eine einheitliche Entwicklerumgebung bereitstellt
- Erweiterung der Funktionen von .NET um die besten Funktionen von .NET Core, .NET Framework, Xamarin und Mono
- Entwicklung dieses Produkts aus einer einzigen Codebasis, die Entwickler (Microsoft und die Community) gemeinsam bearbeiten und erweitern können und die zu einer Verbesserung aller Szenarios beiträgt

Weitere Informationen zu den Plänen für .NET 5 finden Sie unter [Einführung in .NET 5](https://devblogs.microsoft.com/dotnet/introducing-net-5/).
