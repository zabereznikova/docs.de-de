---
title: .NET-Glossar
description: "Informationen zu den Bedeutungen der ausgewählten Begriffe, die in der .NET-Dokumentation verwendet werden."
keywords: ".NET-Glossar, .NET-Wörterbuch, .NET-Terminologie, .NET-Plattform, .NET-Framework, .NET-Runtime"
author: tdykstra
ms.author: tdykstra
ms.date: 07/08/2017
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.translationtype: HT
ms.sourcegitcommit: f8cf12317f1f0163028db003ff31604480da5d1c
ms.openlocfilehash: d9a1b1aa2b19e80b885a2da87746667bff04e234
ms.contentlocale: de-de
ms.lasthandoff: 08/21/2017

---

# <a name="net-glossary"></a>.NET-Glossar

Der primäre Zweck dieses Glossars ist die Klärung der Bedeutungen der ausgewählten Begriffe und Akronyme, die häufig ohne Definitionen in der .NET-Dokumentation auftauchen.

## <a name="aot"></a>AOT

Ahead-of-Time-Compiler

Ähnlich wie bei [JIT](#jit) übersetzt dieser Compiler ebenfalls [IL](#il) in Computercode. Im Gegensatz zur JIT-Kompilierung erfolgt die AOT-Kompilierung, bevor die Anwendung ausgeführt wird und wird von einem anderen Computer aus ausgeführt. Da AOT-Toolketten nicht während der Laufzeit kompiliert werden, muss die Zeit, die für das Kompilieren aufgewendet wird, nicht minimiert werden. Das bedeutet, dass mehr Zeit in die Optimierung investiert werden kann. Da die gesamte Anwendung den Kontext der AOT darstellt, führt der AOT-Compiler auch modulübergreifende Verknüpfungen und die Analyse des gesamten Programms aus. Das bedeutet, dass allen Verweisen gefolgt und eine einzige ausführbare Datei generiert wird.

## <a name="aspnet"></a>ASP.NET 

Die ursprüngliche ASP.NET-Implementierung, die im Lieferumfang von .NET Framework enthalten ist.

Bei ASP.NET handelt es sich manchmal um einen Oberbegriff, der sich auf ASP.NET-Implementierungen, einschließlich ASP.NET Core, bezieht. Die Bedeutung des Begriffs in einer bestimmten Instanz wird durch den Kontext festgelegt. 

Siehe [ASP.NET](/aspnet/#pivot=aspnet).

## <a name="aspnet-core"></a>ASP.NET Core

Eine plattformübergreifende, leistungsstarke Open Source-Implementierung von ASP.NET, die auf .NET Core basiert.

Siehe [ASP.NET Core](/aspnet/#pivot=core).

## <a name="assembly"></a>Assembly

Eine *DLL*-Datei, die eine Sammlung von APIs enthält, die von Apps oder anderen Assemblys aufgerufen werden können.

Eine .NET-Assembly ist eine Sammlung von Typen. Eine Assembly enthält Schnittstellen, Klassen, Strukturen, Enumerationen und Delegaten.  Assemblys im Ordner *bin* eines Projekts werden manchmal als *Binärdateien* bezeichnet. Siehe auch [Bibliotheken](#library).

## <a name="clr"></a>CLR

Common Language Runtime

Die genaue Bedeutung hängt vom Kontext ab, normalerweise wird damit jedoch die Runtime des .NET Framework bezeichnet. Die CLR behandelt die Speicherbelegung und -verwaltung. Bei der CLR handelt es sich auch um einen virtuellen Computer, der nicht nur Apps ausführt, sondern auch mithilfe eines JIT-Compilers dynamisch Code generiert und kompiliert. Die aktuelle Microsoft CLR-Implementierung ist nur unter Windows möglich.

## <a name="coreclr"></a>CoreCLR

.NET Core Common Language Runtime

Die CoreCLR basiert auf demselben Code wie die CLR. rsprünglich war CoreCLR die Runtime von Silverlight und wurde entworfen, um auf mehreren Plattformen ausgeführt zu werden, besonders unter Windows und OS X. CoreCLR ist nun Teil von .NET Core und stellt eine vereinfachte Version der CLR dar. Es handelt sich dabei immer noch um eine plattformübergreifende Runtime, die nun viele Linux-Verteilungen unterstützt. CoreCLR ist auch ein virtueller Computer mit JIT und Funktionen für die Codeausführung.

## <a name="corefx"></a>CoreFX

.NET Core-Basisklassenbibliothek (BCL)

Eine Reihe von Bibliotheken, aus denen die Systemnamespaces (und in beschränktem Umfang die Microsoft-Namespaces) bestehen. Bei der BCL handelt es sich um ein allgemeines Framework auf niedriger Ebene, auf dem Anwendungsframeworks auf höherer Ebene, z.B. ASP.NET Core, basieren. Der Quellcode der .NET Core-BCL ist im [CoreFX-Repository](https://github.com/dotnet/corefx) enthalten. Der Großteil der .NET Core-APIs ist jedoch auch im .NET Framework verfügbar, sodass Sie sich CoreFX als einen Fork der .NET Framework-BCL vorstellen können.

## <a name="corert"></a>CoreRT

.NET Core-Runtime

Im Gegensatz zu CLR und CoreCLR handelt es sich bei CoreRT nicht um einen virtuellen Computer. Das bedeutet, dass die Funktionen zum dynamischen Generieren und Ausführen von Code nicht enthalten sind, da kein [JIT](#jit) enthalten ist. Es ist jedoch ein [GC](#gc) enthalten sowie die Möglichkeit zur Identifikation und Reflektion des Laufzeittyps (RTTI). Das Typsystem wurde jedoch so entwickelt, dass keine Metadaten für die Reflektion erforderlich sind. Dadurch wird eine [AOT](#aot)-Toolkette ermöglicht, die die Verknüpfung zu überflüssigen Metadaten aufheben und (was noch wichtiger ist) Code identifizieren kann, der von der App nicht verwendet wird. CoreRT befindet sich in der Entwicklung.

Siehe [Intro to .NET Native and CoreRT (Einführung in .NET Native und CoreRT)](https://github.com/dotnet/corert/blob/master/Documentation/intro-to-corert.md)

## <a name="ecosystem"></a>Umgebung

Jede Laufzeitsoftware und alle Entwicklungstools und Communityressourcen, die zum Erstellen und Ausführen von Anwendungen für eine bestimmte Technologie verwendet werden.

Der Begriff „.NET-Umgebung“ unterscheidet sich von ähnlichen Begriffen wie „.NET-Stapel“ durch seine Einbindung von Apps und Bibliotheken, die von Drittanbietern stammen. Hier ein Beispiel in einem Satz:

- „Die Motivation hinter [.NET Standard](#net-standard) ist das Herstellen einer umfassenderen Einheitlichkeit in der .NET-Umgebung.“ 

## <a name="framework"></a>Framework

Allgemein handelt es sich dabei um eine umfassende Sammlung von APIs, die die Entwicklung und Bereitstellung von Anwendungen erleichtert, die auf einer bestimmten Technologie basieren. Allgemein sind ASP.NET Core und Windows Forms Beispiele für Anwendungsframeworks. Siehe auch [Bibliotheken](#library).

Das Wort „Framework“ hat in den folgenden Begriffen eine spezifischere technische Bedeutung:
* [.NET Framework](#net-framework)
* [Zielframework](#target-framework)
* [TFM (Zielframeworkmoniker)](#tfm)

In der bestehenden Dokumentation bezieht sich „Framework“ manchmal auf eine [Implementierung von .NET](#implementation-of-net). In einem Artikel kann .NET Core beispielsweise als Framework bezeichnet werden. Diese verwirrende Verwendung soll aus der Dokumentation beseitigt werden.

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

Eine Implementierung von .NET umfasst Folgendes:

- Mindestens eine Runtime. Beispiele: CLR, CoreCLR, CoreRT.
- Eine Klassenbibliothek, die eine Version des .NET Standards implementiert und ggf. zusätzliche APIs beinhaltet. Beispiele: .NET Framework-Basisklassenbibliothek, .NET Core-Basisklassenbibliothek.
- Optional mindestens ein Anwendungsframework. Beispiele: ASP.NET, Windows Forms und WPF sind in .NET Framework enthalten.
- Optional Entwicklungstools. Einige Entwicklungstools werden zwischen mehreren Implementierungen freigegeben.

Beispiele für .NET-Implementierungen:

- [.NET Framework](#net-framework)
- [.NET Core](#net-core)
- [Universelle Windows-Plattform (UWP)](#uwp)

## <a name="library"></a>Bibliothek

Eine Sammlung von APIs, die durch Apps oder andere Bibliotheken aufgerufen werden können. Eine .NET-Bibliothek besteht aus einer oder mehreren [Assemblys](#assembly).

Die Wörter „Bibliothek“ und [Framework](#framework) werden häufig synonym verwendet.

## <a name="metapackage"></a>Metapaket

Ein NuGet-Paket, das über keine eigene Bibliothek verfügt, sondern nur eine Liste der Abhängigkeiten darstellt. Die enthaltenen Pakete können optional die API für ein Zielframework erzeugen.

Siehe [Pakete, Metapakete und Frameworks](../core/packages.md).

## <a name="mono"></a>Mono

Eine Open Source-Alternative zu .NET Framework.

Mono wurde etwa zu der Zeit gestartet, als .NET Framework zum ersten Mal veröffentlicht wurde. Da es sich bei .NET Framework nicht um Open Source handelt, musste Mono ganz neu anfangen. Somit handelt es sich um eine komplette Neuimplementierung von .NET Framework und es gibt keinen gemeinsam verwendeten Code.

Als .NET Core unter der MIT-Lizenz veröffentlicht wurde, hat Microsoft ebenfalls einen [großen Teil von .NET Framework unter der MIT-Lizenz](https://github.com/microsoft/referencesource) veröffentlicht. Dadurch wurde es der Mono-Community ermöglicht, den Code von .NET Framework zu verwenden, um Lücken zu schließen und Verhaltensunterschiede zu vermeiden.

Mono wird in erster Linie zum Ausführen von .NET-Anwendungen unter Linux und macOS verwendet. Mono verfügt auch über Ports zu anderen Plattformen, siehe [Mono‘s Supported Platforms (Von Mono unterstützte Plattformen)](http://www.mono-project.com/docs/about-mono/supported-platforms/). Mono verfügt über Implementierungen (die allerdings nicht notwendigerweise vollständig sind) von WinForms, ASP.NET und `System.Drawing`.

## <a name="net"></a>.NET

Der Oberbegriff für [.NET Standard](#net-standard) und alle [.NET-Implementierungen](#implementation-of-net) und Workloads. Immer groß geschrieben, niemals „.Net“.

Siehe [Leitfaden für .NET](index.md).

## <a name="net-core"></a>.NET Core 

Eine plattformübergreifende, leistungsstarke Open Source-Implementierung von .NET. Enthält die Common Language Runtime (CoreCLR), die Core AOT Runtime (CoreRT, in der Entwicklung), die Core-Basisklassenbibliothek und das Core SDK.

Siehe [.NET Core](../core/index.md).

## <a name="net-core-cli"></a>.NET Core-CLI

Eine plattformübergreifende Toolkette zum Entwickeln von .NET Core-Anwendungen.

Siehe [Tools für die .NET Core-Befehlszeilenschnittstelle (CLI)](../core/tools/index.md).

## <a name="net-core-sdk"></a>.NET Core SDK

Eine Sammlung von Bibliotheken und Tools, mit der Entwickler .NET Core-Anwendungen und -Bibliotheken erstellen können. Enthält die [.NET Core-CLI](#net-core-cli) zum Erstellen von Apps, die .NET Core-Bibliotheken und -Runtime zum Erstellen und Ausführen von Apps und die ausführbare dotnet-Datei (*dotnet.exe*), durch die CLI-Befehle und Anwendungen ausgeführt werden.

Siehe [.NET Core SDK – Übersicht](../core/sdk.md).

## <a name="net-framework"></a>.NET Framework

Eine Implementierung von .NET, die nur unter Windows ausgeführt werden kann. Enthält die Common Language Runtime (CLR), die Basisklassenbibliothek und Bibliotheken für Anwendungsframeworks wie ASP.NET, Windows Forms und WPF.

Siehe [Leitfaden für .NET Framework](../framework/index.md).

## <a name="net-native"></a>.NET systemeigen

Eine Compiler-Toolkette, die nativen Code vorzeitig (Ahead-of-Time, AOT) statt rechtzeitig (Just-in-Time, JIT) erzeugt.

Die Kompilierung erfolgt auf dem Computer des Entwicklers und funktioniert ähnlich wie ein C++-Compiler und -Linker. Nicht verwendeter Code wird entfernt und es wird mehr Zeit in die Optimierung des Codes investiert. Es wird Code aus den Bibliotheken extrahiert und in die ausführbare Datei eingefügt. Das Ergebnis ist ein einzelnes Modul, das die gesamte App darstellt.

UWP war das erste Anwendungsframework, das von .NET Native unterstützt wurde. Nun unterstützen wir das Erstellen nativer Konsolen-Apps unter Windows, macOS und Linux.

Siehe [Intro to .NET Native and CoreRT (Einführung in .NET Native und CoreRT)](https://github.com/dotnet/corert/blob/master/Documentation/intro-to-corert.md)

## <a name="net-standard"></a>.NET-Standard

Eine formale Spezifikation der .NET-APIs, die in jeder .NET-Implementierung verfügbar sind.

Die Spezifikation von .NET Standard wird in der Dokumentation manchmal als „Bibliothek“ bezeichnet. Da eine Bibliothek API-Implementierungen enthält und nicht nur Spezifikationen (Schnittstellen), ist es irreführend, .NET Standard als „Bibliothek“ zu bezeichnen. Diese Verwendung soll aus der Dokumentation beseitigt werden. Ausgenommen davon ist der Verweis auf den Namen des .NET Standard-Metapakets (`NETStandard.Library`).

Siehe [.NET Standard](net-standard.md).

## <a name="ngen"></a>NGEN

Native Imagegenerierung

Sie können sich diese Technologie als einen permanenten JIT-Compiler vorstellen. Normalerweise wird der Code auf dem Computer kompiliert, auf dem er ausgeführt wird. Die Kompilierung findet jedoch normalerweise während der Installation statt.

## <a name="package"></a>package

Ein NuGet-Paket &mdash; oder nur ein Paket &mdash; ist eine *ZIP*-Datei mit mindestens einer Assembly, die denselben Namen trägt und zusätzlichen Metadaten, z.B. der Autorenname.

Die *ZIP*-Datei besitzt eine *NUPKG*-Erweiterung und eventuell Ressourcen, z.B. *DLL*- und *XML*-Dateien, für die Verwendung mit mehreren Frameworks und Versionen. Bei der Installation in einer App oder Bibliothek werden die entsprechenden Ressourcen basierend auf dem Zielframework ausgeführt, das von der App oder Bibliothek angegeben wurde. Die Ressourcen, die die Schnittstelle definieren, befinden sich im Ordner *ref*, und die Ressourcen, die die Implementierung definieren, befinden sich im Ordner *lib*.

## <a name="platform"></a>platform

Ein Betriebssystem (z.B. Windows, macOS, Linux, iOS und Android) und die Hardware, auf dem dieses ausgeführt wird.

Hier sind Beispiele für die Verwendung in Sätzen:

- „.NET Core ist eine plattformübergreifende Implementierung von .NET.“ 
- „PCL-Profile stehen für Microsoft-Plattformen, während .NET Standard plattformunabhängig ist.“

Die .NET-Dokumentation verwendet häufig „.NET-Plattform“, um sich entweder auf eine Implementierung von .NET oder den .NET-Stapel, der alle Implementierungen enthält, zu beziehen. Beide dieser Verwendungen werden häufig mit der primären Bedeutung (Betriebssystem/Hardware) verwechselt, sodass wir diese Verwendungen aus der Dokumentation beseitigen werden.

## <a name="runtime"></a>Laufzeit

Die Ausführungsumgebung eines verwalteten Programms.

Das Betriebssystem ist Teil der Laufzeitumgebung, gehört jedoch nicht zur .NET-Runtime. Dies sind einige Beispiele für .NET-Runtimes:

- Common Language Runtime (CLR)
- Core Common Language Runtime (CoreCLR)
- .NET Native (für UWP)
- Mono Runtime

Die .NET-Dokumentation bezeichnet mit „Runtime“ manchmal eine Implementierung von .NET. Beispielsweise sollte „Runtime“ in den folgenden Sätzen durch „Implementierung“ ersetzt werden:

- „Die verschiedenen .NET-Runtimes implementieren bestimmte Versionen von .NET Standard.“
- „Bibliotheken, die auf mehreren Runtimes ausgeführt werden sollen, sollten dieses Framework als Ziel haben.“ (bezogen auf .NET Standard)
- „Die verschiedenen .NET-Runtimes implementieren bestimmte Versionen von .NET Standard. … Jede Version der .NET-Runtime kündigt die höchste Version von .NET Standard an, die sie unterstützt ...“

Diese inkonsistente Verwendung soll beseitigt werden. 

## <a name="stack"></a>Stapel

Eine Reihe von Programmiertechnologien, die zusammen verwendet werden, um Anwendungen zu erstellen und auszuführen.

„Der .NET-Stapel“ bezieht sich auf .NET Standard und alle .NET-Implementierungen. Der Ausdruck „ein .NET-Stapel“ bezieht sich auf eine Implementierung von .NET. 

## <a name="target-framework"></a>Zielframework

Die Sammlung von APIs, auf der eine .NET-App oder -Bibliothek basiert.

Eine App oder Bibliothek kann eine Version von .NET Standard (beispielsweise .NET Standard 2.0) anzielen. Dabei handelt es sich um eine Spezifikation für eine standardisierte Reihe von APIs für alle .NET-Implementierungen. Eine App oder Bibliothek kann auch eine Version einer bestimmten .NET-Implementierung anzielen. In diesem Fall erhält diese Zugriff auf die implementierungsspezifischen APIs. Beispielsweise erhält eine App, die Xamarin iOS anzieht, Zugriff auf die von Xamarin bereitgestellten iOS-API-Wrapper.

Für einige Zielplattformen (z.B. .NET Framework) werden die verfügbaren APIs von den Assemblys definiert, die eine .NET-Implementierung auf einem System installiert, zu denen Anwendungsframework-APIs zählen können (z.B. ASP.NET, WinForms). Für paketbasierte Zielframeworks (z.B. .NET Standard und .NET Core) werden die Framework-APIs von den Paketen definiert, die in der App oder der Bibliothek installiert sind. In diesem Fall gibt das Zielframework implizit ein Metapaket an, das auf alle Pakete verweist, aus denen das Framework besteht.

Siehe [Zielframeworks](frameworks.md).

## <a name="tfm"></a>TFM

Zielframeworkmoniker

Ein standardisiertes Tokenformat zum Angeben des Zielframeworks einer .NET-App oder -Bibliothek. Auf Zielframeworks wird üblicherweise durch einen kurzen Namen verwiesen, z.B. `net462`. Es gibt auch lange TFMs (z.B. .NETFramework, Version = 4.6.2). Diese werden aber im Allgemeinen nicht verwendet, um ein Zielframework anzugeben.

Siehe [Zielframeworks](frameworks.md).

## <a name="uwp"></a>UWP

Universelle Windows-Plattform

Eine Implementierung von .NET, mit der moderne Touchscreen-Windows-Anwendungen und Software für das Internet der Dinge (Internet of Things, IoT) erstellen werden. Sie wurde als einheitliche Plattform entwickelt, um das Programmieren für verschiedene Gerätetypen, von PCs, Tablets, Phablets über Smartphones bis hin zur Xbox, zu ermöglichen. Die UWP bietet viele Dienste, z.B. einen zentralen App Store, eine Ausführungsumgebung (AppContainer) und mehrere Windows-APIs, die anstelle von Win32 (WinRT) verwendet werden. Apps können auf dieser Plattform in C++, C#, VB.NET und JavaScript geschrieben werden. Die .NET-APIs für C# und VB.NET werden von .NET Core bereitgestellt.

## <a name="see-also"></a>Siehe auch

[.NET Guide (Leitfaden für .NET)](index.md)  
[Leitfaden für .NET Framework](../framework/index.md)  
[.NET Core](../core/index.md)  
[ASP.NET Overview (Übersicht über ASP.NET)](/aspnet/index#pivot=aspnet)  
[ASP.NET Core Overview (Übersicht über ASP.NET Core)](/aspnet/index#pivot=core)  


