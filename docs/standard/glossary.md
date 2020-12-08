---
title: .NET-Glossar
description: Informationen zu den Bedeutungen der ausgewählten Begriffe, die in der .NET-Dokumentation verwendet werden.
ms.date: 11/16/2020
ms.openlocfilehash: 77ed506fb1c5bd4018b5fe0c14cc0bf37cb08113
ms.sourcegitcommit: 721c3e4bdbb1ea0bb420818ec944c538fe5c513a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/01/2020
ms.locfileid: "96438184"
---
# <a name="net-glossary"></a>.NET-Glossar

Der primäre Zweck dieses Glossars ist die Klärung der Bedeutungen der ausgewählten Begriffe und Akronyme, die häufig ohne Definitionen in der .NET-Dokumentation auftauchen.

## <a name="aot"></a>AOT

Ahead-of-Time-Compiler

Ähnlich wie bei [JIT](#jit) übersetzt dieser Compiler ebenfalls [IL](#il) in Computercode. Im Gegensatz zur JIT-Kompilierung erfolgt die AOT-Kompilierung, bevor die Anwendung ausgeführt wird und wird von einem anderen Computer aus ausgeführt. Da AOT-Toolketten nicht während der Laufzeit kompiliert werden, muss die Zeit, die für das Kompilieren aufgewendet wird, nicht minimiert werden. Das bedeutet, dass mehr Zeit in die Optimierung investiert werden kann. Da die gesamte Anwendung den Kontext der AOT darstellt, führt der AOT-Compiler auch modulübergreifende Verknüpfungen und die Analyse des gesamten Programms aus. Das bedeutet, dass allen Verweisen gefolgt und eine einzige ausführbare Datei generiert wird.

Siehe [CoreRT](#corert) und [.NET Native](#net-native).

## <a name="app-model"></a>App-Modell

Hierbei handelt es sich um eine [Workload](#workload)-spezifische API. Im Folgenden finden Sie einige Beispiele:

* ASP.NET
* ASP.NET-Web-API
* Entity Framework (EF)
* Windows Presentation Foundation (WPF)
* Windows Communication Foundation (WCF)
* Windows Workflow Foundation (WF)
* Windows Forms (WinForms)

## <a name="aspnet"></a>ASP.NET

Die ursprüngliche ASP.NET-Implementierung, die im Lieferumfang von .NET Framework enthalten ist.

Bei ASP.NET handelt es sich manchmal um einen Oberbegriff, der sich auf ASP.NET-Implementierungen, einschließlich ASP.NET Core, bezieht. Die Bedeutung des Begriffs in einer bestimmten Instanz wird durch den Kontext festgelegt. Beziehen Sie sich auf ASP.NET 4.x, wenn Sie klarstellen möchten, dass Sie ASP.NET nicht für beide Implementierungen verwenden.

Siehe [ASP.NET-Dokumentation](/aspnet/#pivot=aspnet).

## <a name="aspnet-core"></a>ASP.NET Core

Hierbei handelt es sich um eine plattformübergreifende, leistungsstarke Open-Source-Implementierung von ASP.NET.

Siehe [ASP.NET Core-Dokumentation](/aspnet/#pivot=core).

## <a name="assembly"></a>Assembly

Eine *DLL*/*EXE*-Datei, die eine Sammlung von APIs enthalten kann, die von Anwendungen oder anderen Assemblys aufgerufen werden können.

Eine Assembly kann Typen wie Schnittstellen, Klassen, Strukturen, Enumerationen und Delegaten enthalten. Assemblys im Ordner *bin* eines Projekts werden manchmal als *Binärdateien* bezeichnet. Siehe auch [Bibliotheken](#library).

## <a name="bcl"></a>BCL

Basisklassenbibliothek

Eine Reihe von Bibliotheken, aus denen die Namespaces System.\* (und in beschränktem Umfang Microsoft.\*) bestehen. Bei der BCL handelt es sich um ein allgemeines Framework auf niedriger Ebene, auf dem Anwendungsframeworks auf höherer Ebene, z.B. ASP.NET Core, basieren.

Der Quellcode der Basisklassenbibliothek für [.NET 5 (und .NET Core) und höheren Versionen](#net-5-and-later-versions) befindet sich im [.NET-Runtimerepository](https://github.com/dotnet/runtime). Der Großteil dieser APIs der Basisklassenbibliothek ist auch im .NET Framework verfügbar. Sie können sich diesen Quellcode also als Fork des Quellcodes für die .NET Framework-Basisklassenbibliothek vorstellen.

Die folgenden Begriffe beziehen sich häufig auf dieselbe Sammlung von APIs, auf die sich die BCL bezieht:

- [.NET-Kernbibliotheken](../core/compatibility/corefx.md)
- [Frameworkbibliotheken](#framework-libraries)
- [Runtimebibliotheken](#runtime)
- [Freigegebenes Framework](#shared-framework)

## <a name="clr"></a>CLR

Common Language Runtime

Die genaue Bedeutung hängt vom Kontext ab. Common Language Runtime bezeichnet in der Regel die Runtime von [.NET Framework](#net-framework) oder die Runtime von [.NET 5 (und .NET Core) und höheren Versionen](#net-5-and-later-versions).

Die CLR verarbeitet die Speicherbelegung und -verwaltung. Bei der CLR handelt es sich auch um einen virtuellen Computer, der nicht nur Apps ausführt, sondern auch mithilfe eines [JIT](#jit)-Compilers dynamisch Code generiert und kompiliert.

Die CLR-Implementierung für .NET Framework ist nur für Windows vorgesehen.

Die CLR-Implementierung für .NET 5 und höhere Versionen (auch bekannt als „Core-CLR“) basiert auf derselben Codebasis wie die .NET Framework-CLR. Ursprünglich war die Core-CLR die Runtime von Silverlight und für die Ausführung auf mehreren Plattformen konzipiert, insbesondere Windows und Mac OS X. Sie ist weiterhin eine [plattformübergreifende](#cross-platform) Runtime, die nun viele Linux-Distributionen unterstützt.

Weitere Informationen finden Sie unter [Runtime](#runtime).

## <a name="core-clr"></a>Core-CLR

Hierbei handelt es sich um die Common Language Runtime für [.NET 5 (und .NET Core) und höhere Versionen](#net-5-and-later-versions).

Weitere Informationen finden Sie unter [CLR](#clr).

## <a name="corert"></a>CoreRT

Im Gegensatz zu [CLR](#clr) handelt es sich bei CoreRT nicht um einen virtuellen Computer. Das bedeutet, dass die Funktionen zum dynamischen Generieren und Ausführen von Code nicht enthalten sind, da keine [JIT](#jit)-Kompilierung enthalten ist. Es ist jedoch ein [GC](#gc) enthalten sowie die Möglichkeit zur Identifikation und Reflektion des Laufzeittyps (RTTI). Das Typsystem wurde jedoch so entwickelt, dass keine Metadaten für die Reflektion erforderlich sind. Dies ermöglicht eine [AOT](#aot)-Toolkette, die die Verknüpfung zu überflüssigen Metadaten aufheben und (was noch wichtiger ist) Code identifizieren kann, der von der App nicht verwendet wird. CoreRT befindet sich in der Entwicklung.

Weitere Informationen finden Sie unter [Einführung in .NET Native und CoreRT](https://github.com/dotnet/corert/blob/master/Documentation/intro-to-corert.md).

## <a name="cross-platform"></a>plattformübergreifend

Die Möglichkeit, eine Anwendung zu entwickeln und auszuführen, die unter vielen verschiedenen Betriebssystemen wie Linux, Windows und iOS verwendet werden kann, ohne dass für jedes Betriebssystem Code neu geschrieben werden muss. Dies ermöglicht die Wiederverwendung von Code und Konsistenz zwischen Anwendungen auf verschiedenen Plattformen.

## <a name="ecosystem"></a>Umgebung

Jede Laufzeitsoftware und alle Entwicklungstools und Communityressourcen, die zum Erstellen und Ausführen von Anwendungen für eine bestimmte Technologie verwendet werden.

Der Begriff „.NET-Umgebung“ unterscheidet sich von ähnlichen Begriffen wie „.NET-Stapel“ durch seine Einbindung von Apps und Bibliotheken, die von Drittanbietern stammen. Hier ein Beispiel in einem Satz:

- „Das Ziel von [.NET Standard](#net-standard) ist mehr Einheitlichkeit im .NET-Ökosystem.“

## <a name="framework"></a>Framework

Allgemein handelt es sich dabei um eine umfassende Sammlung von APIs, die die Entwicklung und Bereitstellung von Anwendungen erleichtert, die auf einer bestimmten Technologie basieren. Allgemein sind ASP.NET Core und Windows Forms Beispiele für Anwendungsframeworks. Siehe auch [Bibliotheken](#library).

Das Wort „Framework“ hat in den folgenden Begriffen verschiedene Bedeutungen:

- [Frameworkbibliotheken](#framework-libraries)
- [.NET Framework](#net-framework)
- [Freigegebenes Framework](#shared-framework)
- [Zielframework](#target-framework)
- [TFM (Zielframeworkmoniker)](#tfm)
- [Frameworkabhängige App](../core/deploying/index.md#publish-framework-dependent)

Manchmal bezieht sich „Framework“ auf eine [Implementierung von .NET](#implementation-of-net). Beispielsweise könnte .NET 5 in einem Artikel als Framework bezeichnet werden.

## <a name="framework-libraries"></a>Frameworkbibliotheken

Die Bedeutung hängt vom Kontext ab. Dieser Begriff bezieht sich möglicherweise auf die Frameworkbibliotheken für [.NET 5 (und .NET Core) und höhere Versionen](#net-5-and-later-versions). In diesem Fall bezieht er sich auf dieselben Bibliotheken, auf die sich auch die [BCL](#bcl) bezieht. Er kann sich auch auf die ASP.NET Core-Frameworkbibliotheken beziehen, die auf der BCL basieren und zusätzliche APIs für Web-Apps bereitstellen.

## <a name="gc"></a>GC

Garbage Collector

Der Garbage Collector ist eine Implementierung der automatischen Speicherverwaltung.  Der GC gibt Arbeitsspeicher frei, der durch Objekte belegt ist, die nicht mehr verwendet werden.

Siehe [Garbage Collection](garbage-collection/index.md).

## <a name="il"></a>IL

Zwischensprache

.NET-Sprachen auf höherer Ebene, z.B. C#, werden zu einem hardwareunabhängigen Anweisungssatz kompiliert, der als Zwischensprache (Intermediate Language, IL) bezeichnet wird. IL wird manchmal als MSIL (Microsoft IL) oder CIL (Common IL) bezeichnet.

## <a name="jit"></a>JIT

Just-In-Time-Compiler

Ähnlich wie bei [AOT](#aot) übersetzt dieser Compiler [IL](#il) in einen Computercode, den der Prozessor versteht. Im Gegensatz zu AOT erfolgt die JIT-Kompilierung bei Bedarf und wird vom selben Computer aus ausgeführt, auf dem auch der Code ausgeführt werden soll. Da die JIT-Kompilierung während der Ausführung der Anwendung stattfindet, ist die Kompilierzeit Teil der Laufzeit. Daher müssen JIT-Compiler eine Balance zwischen der Zeit, die in die Optimierung des Codes investiert werden kann, und den Ersparnissen, die der resultierende Code erzeugt, finden. Ein JIT kennt jedoch die tatsächliche Hardware und befreit die Entwickler davon, verschiedene Implementierungen bereitzustellen.

## <a name="implementation-of-net"></a>Implementierung von .NET

Eine Implementierung von .NET umfasst:

- Mindestens eine Runtime. Beispiele: [CLR](#clr) und [CoreRT](#corert).
- Eine Klassenbibliothek, die eine Version von .NET Standard implementiert und ggf. zusätzliche APIs beinhaltet. Beispiele: Die [Basisklassenbibliotheken](#bcl) für [.NET Framework](#net-framework) und [.NET 5 (und .NET Core) und höhere Versionen](#net-5-and-later-versions).
- Optional mindestens ein Anwendungsframework. Beispiele: [ASP.NET](#aspnet), Windows Forms und WPF sind in .NET Framework und .NET 5 enthalten.
- Optional Entwicklungstools. Einige Entwicklungstools werden zwischen mehreren Implementierungen freigegeben.

Beispiele für .NET-Implementierungen:

- [.NET Framework](#net-framework)
- [.NET 5 und höhere Versionen (einschließlich .NET Core 2.1 bis 3.1)](#net-5-and-later-versions)
- [Universelle Windows-Plattform (UWP)](#uwp)
- [Mono](#mono)

## <a name="library"></a>Bibliothek

Eine Sammlung von APIs, die durch Apps oder andere Bibliotheken aufgerufen werden können. Eine .NET-Bibliothek besteht aus einer oder mehreren [Assemblys](#assembly).

Die Wörter „Bibliothek“ und [Framework](#framework) werden häufig synonym verwendet.

## <a name="mono"></a>Mono

Bei Mono handelt es sich um eine [plattformübergreifend](#cross-platform) Open Source-.NET-Implementierung, die in erster Linie verwendet wird, wenn eine kleine Runtime erforderlich ist. Mono ist die Runtime für Xamarin-Anwendungen unter Android, Mac, iOS, tvOS und watchOS und ist hauptsächlich auf Apps mit geringem Ressourcenbedarf ausgelegt.

Außerdem unterstützt Mono alle derzeit veröffentlichten Versionen des .NET Standards.

In der Vergangenheit hat Mono die größere API des .NET Framework implementiert und einige der beliebtesten Funktionen unter Unix emuliert. Manchmal wird es zum Ausführen von .NET-Anwendungen verwendet, die auf diesen Unix-Funktionen basieren.

Mono wird in der Regel mit einem [Just-In-Time-Compiler](#jit) verwendet. Es enthält aber auch einen vollständigen [statischen Compiler (Ahead-of-time-Kompilierung)](#aot), der auf Plattformen wie iOS verwendet wird.

Weitere Informationen finden Sie in der [Mono-Dokumentation](https://www.mono-project.com/docs/).

## <a name="net"></a>.NET

Der Oberbegriff für [.NET Standard](#net-standard) und alle [.NET-Implementierungen](#implementation-of-net) und Workloads. Immer ausschließlich in Großbuchstaben, niemals „.Net“.

Mit dem Release von [.NET 5](#net-5-and-later-versions) (derzeit in der Vorschauphase) wird dies die empfohlene .NET-Implementierung für jegliche neuen .NET-Entwicklungen sein. Daher wird „.NET“ in einigen Kontexten „.NET 5 und höhere Versionen“ implizieren.

Weitere Informationen finden Sie unter [.NET-Grundlagen](../fundamentals/index.yml).

## <a name="net-5-and-later-versions"></a>.NET 5 und höhere Versionen

Eine plattformübergreifende, leistungsstarke Open Source-Implementierung von .NET. Sie umfasst eine Common Language Runtime ([CLR](#clr)), eine [AOT](#aot)-Runtime ([CoreRT](#corert), in der Entwicklung), eine Basisklassenbibliothek ([BCL](#bcl)) und das [.NET SDK](#net-sdk).

Frühere Versionen dieser .NET-Implementierung werden als .NET Core bezeichnet. .NET 5.0 ist die nächste Version nach .NET Core 3.1. Version 4 wurde übersprungen, um eine Verwechslung dieser neuen Implementierung von .NET mit der älteren Implementierung zu vermeiden, die als [.NET Framework](#net-framework) bekannt ist. Die aktuelle Version von .NET Framework ist Version 4.8.

Weitere Informationen finden Sie unter [.NET-Grundlagen](../fundamentals/index.yml).

## <a name="net-cli"></a>.NET CLI

Hierbei handelt es sich um eine plattformübergreifende Toolkette für die Entwicklung von Anwendungen und Bibliotheken für [.NET 5 (und .NET Core) und höhere Versionen](#net-5-and-later-versions). Diese Toolkette ist auch als .NET Core-CLI bekannt.

Weitere Informationen finden Sie unter [.NET-CLI](../core/tools/index.md).

## <a name="net-core"></a>.NET Core

Weitere Informationen finden Sie unter [.NET 5 und höhere Versionen](#net-5-and-later-versions).

## <a name="net-framework"></a>.NET Framework

Eine Implementierung von .NET, die nur unter Windows ausgeführt werden kann. Diese Implementierung enthält die Common Language Runtime ([CLR](#clr)), die Basisklassenbibliothek ([BCL](#bcl)) und Bibliotheken für Anwendungsframeworks wie [ASP.NET](#aspnet), Windows Forms und WPF.

Siehe [Leitfaden für .NET Framework](../framework/index.yml).

## <a name="net-native"></a>.NET systemeigen

Hierbei handelt es sich um eine Compiler-Toolkette, die nativen Code im Voraus (Ahead-of-Time, [AOT](#aot)) erzeugt, anstelle von „rechtzeitig“ (Just-In-Time, [JIT](#jit)).

Die Kompilierung erfolgt auf dem Computer des Entwicklers und funktioniert ähnlich wie ein C++-Compiler und -Linker. Nicht verwendeter Code wird entfernt und es wird mehr Zeit in die Optimierung des Codes investiert. Es wird Code aus den Bibliotheken extrahiert und in die ausführbare Datei eingefügt. Das Ergebnis ist ein einzelnes Modul, das die gesamte App darstellt.

UWP war das erste Anwendungsframework, das von .NET Native unterstützt wurde. Nun unterstützen wir das Erstellen nativer Konsolen-Apps unter Windows, macOS und Linux.

Siehe [Intro to .NET Native and CoreRT (Einführung in .NET Native und CoreRT)](https://github.com/dotnet/corert/blob/master/Documentation/intro-to-corert.md)

## <a name="net-sdk"></a>.NET SDK

Hierbei handelt es sich um eine Reihe von Bibliotheken und Tools, mit denen Entwickler .NET-Anwendungen und Bibliotheken für [.NET 5 (und .NET Core) und höhere Versionen](#net-5-and-later-versions) erstellen können. Dies wird auch als .NET Core SDK bezeichnet.

Darin enthalten sind die [.NET-CLI](#net-cli) zum Erstellen von Apps, die .NET-Bibliotheken und -Runtime zum Erstellen und Ausführen von Apps und die ausführbare dotnet-Datei (*dotnet.exe*), durch die CLI-Befehle und Anwendungen ausgeführt werden.

Weitere Informationen finden Sie in der [Übersicht über .NET SDK](../core/sdk.md).

## <a name="net-standard"></a>.NET Standard

Eine formale Spezifikation der .NET-APIs, die in jeder .NET-Implementierung verfügbar sind.

Die Spezifikation von .NET Standard wird in der Dokumentation manchmal als „Bibliothek“ bezeichnet. Da eine Bibliothek API-Implementierungen enthält und nicht nur Spezifikationen (Schnittstellen), ist es irreführend, .NET Standard als „Bibliothek“ zu bezeichnen.

Siehe [.NET Standard](net-standard.md).

## <a name="ngen"></a>NGEN

Native Imagegenerierung

Sie können sich diese Technologie als einen persistenten [JIT](#jit)-Compiler vorstellen. Normalerweise wird der Code auf dem Computer kompiliert, auf dem er ausgeführt wird. Die Kompilierung findet jedoch normalerweise während der Installation statt.

## <a name="package"></a>package

Ein NuGet-Paket &mdash; oder nur ein Paket &mdash; ist eine *ZIP*-Datei mit mindestens einer Assembly, die denselben Namen trägt und zusätzlichen Metadaten, z.B. der Autorenname.

Die *ZIP*-Datei besitzt eine *NUPKG*-Erweiterung und eventuell Ressourcen, z.B. *DLL*- und *XML*-Dateien, für die Verwendung mit mehreren Zielframeworks und Versionen. Bei der Installation in einer App oder Bibliothek werden die entsprechenden Ressourcen basierend auf dem Zielframework ausgeführt, das von der App oder Bibliothek angegeben wurde. Die Ressourcen, die die Schnittstelle definieren, befinden sich im Ordner *ref*, und die Ressourcen, die die Implementierung definieren, befinden sich im Ordner *lib*.

## <a name="platform"></a>platform

Ein Betriebssystem (z.B. Windows, macOS, Linux, iOS und Android) und die Hardware, auf dem dieses ausgeführt wird.

Hier sind Beispiele für die Verwendung in Sätzen:

- „.NET Core ist eine plattformübergreifende Implementierung von .NET.“
- „PCL-Profile stehen für Microsoft-Plattformen, während .NET Standard plattformagnostisch ist.“

In der Legacydokumentation zu .NET wird manchmal der Begriff „.NET-Plattform“ für eine [Implementierung von .NET](#implementation-of-net) oder den [.NET-Stapel](#stack), einschließlich aller Implementierungen, verwendet. Beide dieser Verwendungsmöglichkeiten werden häufig mit der primären Bedeutung (Betriebssystem/Hardware) verwechselt. Daher werden diese Verwendungen nach Möglichkeit vermieden.

„Plattform“ hat im Begriff „Entwicklerplattform“ eine andere Bedeutung, die sich auf Software bezieht, die Tools und Bibliotheken zum Erstellen und Ausführen von Apps bereitstellt. .NET ist eine plattformübergreifende Open-Source-Entwicklerplattform zum Erstellen vieler verschiedener Arten von Anwendungen.

## <a name="runtime"></a>Laufzeit

Im Allgemeinen handelt es sich hierbei um die Ausführungsumgebung für ein verwaltetes Programm. Das Betriebssystem ist Teil der Laufzeitumgebung, gehört jedoch nicht zur .NET-Runtime. Im Folgenden finden Sie einige Beispiele für .NET-Runtimes, die diese Bedeutung haben:

- Common Language Runtime ([CLR](#clr))
- .NET Native (für UWP)
- Mono Runtime

Das Wort „Runtime“ hat in einigen Kontexten verschiedene Bedeutungen:

* *.NET-Runtime* auf der [.NET 5.0-Downloadseite](https://dotnet.microsoft.com/download/dotnet/5.0)

  Sie können die *.NET-Runtime* oder andere Runtimes wie die *ASP.NET Core-Runtime* herunterladen. *Runtime* steht in diesem Fall für die Komponenten, die auf einem Computer installiert werden müssen, um eine [frameworkabhängige](../core/deploying/index.md#publish-framework-dependent) App auf dem Computer ausführen zu können. Die .NET-Runtime umfasst die [CLR](#clr) und das [freigegebene .NET Framework](#shared-framework), das die [BCL](#bcl) bereitstellt.

* *.NET-Runtimebibliotheken*

  Dies bezieht sich auf die gleichen Bibliotheken, auf die sich die [BCL](#bcl) bezieht. Andere Runtimes (z. B. ASP.NET Core-Runtime) verfügen jedoch über unterschiedliche [freigegebene Frameworks](#shared-framework) mit zusätzlichen Bibliotheken, die auf der BCL basieren.

* [Runtimebezeichner (RID)](../core/rid-catalog.md)

  *Runtime* bezieht sich in diesem Fall auf die Betriebssystemplattform und die CPU-Architektur, auf der eine .NET-App ausgeführt wird (z. B. `linux-x64`).

* Wie in den folgenden Beispielen bezieht sich „Runtime“ manchmal auf die [Implementierung von .NET](#implementation-of-net):

  - „Die verschiedenen .NET-Runtimes implementieren bestimmte Versionen von .NET Standard. … Jede Version der .NET-Runtime kündigt die höchste Version von .NET Standard an, die sie unterstützt ...“
  - „Bibliotheken, die auf mehreren Runtimes ausgeführt werden sollen, sollten dieses Framework als Ziel haben.“ (bezogen auf .NET Standard)

## <a name="shared-framework"></a>Freigegebenes Framework

Die Bedeutung hängt vom Kontext ab. Das *freigegebene .NET-Framework* bezieht sich auf die Bibliotheken in der [.NET-Runtime](#runtime). In diesem Fall bezieht sich das *freigegebene Framework* für [.NET 5 (und .NET Core) und höhere Versionen](#net-5-and-later-versions) auf dieselben Bibliotheken wie die [BCL](#bcl).

Es gibt noch andere freigegebene Frameworks. Das *freigegebene ASP.NET Core-Framework* bezieht sich auf die Bibliotheken in der [ASP.NET Core-Runtime](#runtime), die die BCL und zusätzliche APIs für die Verwendung durch Web-Apps enthält.

Für [frameworkabhängige Apps](../core/deploying/index.md#publish-framework-dependent) besteht das freigegebene Framework aus Bibliotheken, die in Assemblys enthalten sind, die wiederum in einem Ordner auf dem die App ausführenden Computer installiert sind. Für [eigenständige Apps](../core/deploying/index.md#publish-self-contained) sind die freigegebenen Frameworkassemblys in der App enthalten.

Weitere Informationen finden Sie unter [Fundierte Einblicke in .NET Core-Primitiven, Teil 2: Freigegebenes Framework](https://natemcmaster.com/blog/2018/08/29/netcore-primitives-2/).

## <a name="stack"></a>Stapel

Eine Reihe von Programmiertechnologien, die zusammen verwendet werden, um Anwendungen zu erstellen und auszuführen.

Mit dem „.NET-Stapel“ sind .NET Standard und alle .NET-Implementierungen gemeint. Der Ausdruck „ein .NET-Stapel“ bezieht sich auf eine Implementierung von .NET.

## <a name="target-framework"></a>Zielframework

Die Sammlung von APIs, auf der eine .NET-App oder -Bibliothek basiert.

Eine App oder Bibliothek kann auf eine Version von .NET Standard (beispielsweise .NET Standard 2.0) ausgelegt sein. Dabei handelt es sich um eine Spezifikation für eine standardisierte Reihe von APIs für alle .NET-Implementierungen. Eine App oder Bibliothek kann auch eine Version einer bestimmten .NET-Implementierung anzielen. In diesem Fall erhält diese Zugriff auf die implementierungsspezifischen APIs. Beispielsweise erhält eine App, die Xamarin iOS anzieht, Zugriff auf die von Xamarin bereitgestellten iOS-API-Wrapper.

Für einige Zielplattformen (z.B. .NET Framework) werden die verfügbaren APIs von den Assemblys definiert, die eine .NET-Implementierung auf einem System installiert, zu denen Anwendungsframework-APIs zählen können (z.B. ASP.NET, WinForms). Für paketbasierte Zielframeworks (z.B. .NET Standard und .NET Core) werden die Framework-APIs von den Paketen definiert, die in der App oder der Bibliothek installiert sind. In diesem Fall gibt das Zielframework implizit ein Paket an, das auf alle Pakete verweist, aus denen das Framework besteht.

Siehe [Zielframeworks](frameworks.md).

## <a name="tfm"></a>TFM

Zielframeworkmoniker

Ein standardisiertes Tokenformat zum Angeben des Zielframeworks einer .NET-App oder -Bibliothek. Auf Zielframeworks wird üblicherweise durch einen kurzen Namen verwiesen, z.B. `net462`. Es gibt auch lange TFMs (z.B. .NETFramework, Version = 4.6.2). Diese werden aber im Allgemeinen nicht verwendet, um ein Zielframework anzugeben.

Siehe [Zielframeworks](frameworks.md).

## <a name="uwp"></a>UWP

Universelle Windows-Plattform

Eine Implementierung von .NET, mit der moderne Touchscreen-Windows-Anwendungen und Software für das Internet der Dinge (Internet of Things, IoT) erstellen werden. Sie wurde als einheitliche Plattform entwickelt, um das Programmieren für verschiedene Gerätetypen, von PCs, Tablets und Smartphones bis hin zur Xbox, zu ermöglichen. Die UWP bietet viele Dienste, z.B. einen zentralen App Store, eine Ausführungsumgebung (AppContainer) und mehrere Windows-APIs, die anstelle von Win32 (WinRT) verwendet werden. Apps können in C++, C#, Visual Basic und JavaScript geschrieben werden. Bei Verwendung von C# und Visual Basic werden die .NET-APIs von .NET 5 (und .NET Core) und höheren Versionen bereitgestellt.

## <a name="workload"></a>workload

Hierbei handelt es sich um einen App-Typen, der erstellt wird. Eine Workload ist allgemeiner als ein [App-Modell](#app-model). Oben auf jeder Seite der .NET-Dokumentation, einschließlich dieser, finden Sie beispielsweise eine Dropdownliste für **Workloads**, in der Sie die Dokumentation entsprechend der Optionen **Web**, **Mobil**, **Cloud**, **Desktop** und **Machine Learning und Daten** wechseln können.

In manchen Kontexten bezieht sich *Workload* auf eine Featuresammlung in Visual Studio, die Sie installieren können, um einen bestimmten App-Typen zu unterstützen. Ein Beispiel hierfür finden Sie unter [Auswählen einer Workload](../core/install/windows.md#select-a-workload).

## <a name="see-also"></a>Siehe auch

- [.NET-Grundlagen](../fundamentals/index.yml)
- [Leitfaden für .NET Framework](../framework/index.yml)
- [ASP.NET Overview (Übersicht über ASP.NET)](/aspnet/index#pivot=aspnet)
- [ASP.NET Core Overview (Übersicht über ASP.NET Core)](/aspnet/index#pivot=core)
