---
title: .NET-Produkte
description: .NET-Produkte
keywords: .NET, .NET Core
author: richlander
manager: wpickett
ms.date: 06/23/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 2e38e9d9-8284-46ee-a15f-199adc4f26f4
translationtype: Human Translation
ms.sourcegitcommit: 15c55a87beb64f265a164db918c7721c7690fadf
ms.openlocfilehash: 90deb1903eea6ae1336326ca91f1e7863485dfd1

---

# <a name="net-products"></a>.NET-Produkte

.NET ist eine sehr flexible, naturgemäß plattformübergreifende [Spezifikation](https://github.com/dotnet/coreclr/blob/master/Documentation/project-docs/dotnet-standards.md) für allgemeine Zwecke zum Erstellen von Entwicklerprodukten. Es wird für alle gängigen App-Kategorien eingesetzt: Desktop, Mobilgeräte, Cloud, Spiele und IoT.

In diesem Dokument werden zwei leicht unterschiedliche Begriffe verwendet:

- .NET-Produkt: Ermöglicht Ihnen das Erstellen einer App für eine oder mehrere Zielplattformen.
- .NET-Implementierung: Kombination aus Runtime, Framework und Tools, die den „.NET-Code“ ausführen können, auf dem die Produkte basieren.

## <a name="product-categories"></a>Produktkategorien

.NET-Produkte sind für jede der folgenden Produktkategorien verfügbar.

### <a name="desktop"></a>Desktop

Sie können Desktop-Apps für Windows und macOS erstellen.

- [Universelle Windows-Apps](https://developer.microsoft.com/windows) mit [.NET Native](#net-native)
- [Windows Presentation Foundation (WPF)](https://msdn.microsoft.com/library/ms754130.aspx) für Windows mit dem [.NET Framework](#net-framework)
- [Windows Forms](https://msdn.microsoft.com/library/dd30h2yb.aspx) für Windows mit dem [.NET Framework](#net-framework)
- Cocoa für macOS mit [Xamarin](#xamarin-sdk)
- [Electron](http://electron.atom.io/) für plattformübergreifende Desktops mit [electron-edge](https://github.com/kexplo/electron-edge)

### <a name="games"></a>Spiele

Sie können Spiele für viele Desktop-, Mobil-, Konsolen- und Virtual/Augmented Reality-Geräte erstellen.

- [CRYENGINE](http://docs.cryengine.com/display/CEPROG/CE%23+Programming) mit [Mono](#mono)
- [MonoGame](http://www.monogame.net/documentation/?page=main) mit [Mono](#mono)
- [Unity](http://docs.unity3d.com/Manual/index.html) mit [Mono](#mono)

### <a name="iot"></a>Internet der Dinge

Sie können IoT-Apps (Internet of Things, Internet der Dinge) für Windows 10 IoT Core erstellen, einschließlich Raspberry Pi 2/3.

- [Windows 10 IoT Core](https://developer.microsoft.com/windows/iot) mit [.NET Native](#net-native)

### <a name="mobile"></a>Mobil

Sie können mobile Apps für iOS, Android und Windows erstellen.

- iOS-App mit [Xamarin](#xamarin-sdk)
- Android-App mit [Xamarin](#xamarin-sdk)
- [Universelle Windows-App](https://developer.microsoft.com/windows) mit [.NET Native](#net-native)

### <a name="web-and-cloud"></a>Web und Cloud

Sie können Web- und Cloud-Apps für Windows und Linux erstellen.

- [ASP.NET](http://www.asp.net/) für Windows mit dem [.NET Framework](#net-framework)
- [ASP.NET Core](http://docs.asp.net/) für Windows, macOS und Linux mit [.NET Core](#net-core)

## <a name="net-implementations"></a>.NET-Implementierungen

Größere kommerzielle und Open Source-Implementierungen von .NET werden unten in alphabetischer Reihenfolge aufgeführt.

### <a name="net-core"></a>.NET Core

.NET Core wird verwendet, um Geräte-, Web-, Cloud- und eingebettete/IoT-Apps zu erstellen. Es ist [Open Source](https://github.com/dotnet/core) und plattformübergreifend mit Unterstützung für Windows, macOS und Linux. [ASP.NET Core](http://docs.asp.net/) ist die am häufigsten verwendete Arbeitsauslastung für .NET Core. Sie können damit Web-Apps und Dienste zur lokalen Bereitstellung und zur Bereitstellung in der Cloud erstellen. Zudem können Sie mit .NET Core auch Tools, Hilfsprogramme und Cloudworker-Apps erstellen.

- Weitere Informationen zu [.NET Core](../core/index.md)
- Weitere Informationen zu [ASP.NET Core](http://docs.asp.net/)
- [.NET Core herunterladen](http://dot.net/core)

Im Folgenden sind die wesentlichen Merkmale von .NET Core aufgeführt:

**Plattformübergreifend** – .NET Core unterstützt drei Betriebssystemfamilien: Linux, Windows und macOS. .NET Core-Apps sind standardmäßig plattformübergreifend. Sie können Apps und Bibliotheken schreiben, die über unterstützte Betriebssysteme hinweg unverändert ausgeführt werden.

**Open Source** - [.NET Core](https://github.com/dotnet/core) steht auf GitHub zur Verfügung, lizenziert mit [MIT](https://github.com/dotnet/coreclr/blob/master/LICENSE.TXT)- und [Apache 2](https://github.com/dotnet/roslyn/blob/master/License.txt)-Lizenzen (Lizenzierung pro Komponente). Die Dokumentation ist [CC-BY](https://github.com/dotnet/docs/blob/master/license.txt). .NET Core nutzt außerdem eine erhebliche Anzahl von Open Source-Branchenabhängigkeiten, die in den [.NET Core-Anmerkungen zur Version](https://github.com/dotnet/core/releases) aufgeführt sind. 

**Natürlicher Erwerb** – .NET Core wird in unterschiedlicher Form bereitgestellt, um den jeweiligen Entwickleranforderungen gerecht zu werden. Sie erhalten .NET Core über den Installer (oder ZIP-Dateien) des [.NET Core SDK](https://dot.net/core) oder über betriebssystemspezifische Paket-Manager wie z.B. APT und Yum. [Offizielle .NET Core Docker-Images](https://hub.docker.com/r/microsoft/dotnet/) stehen auf Docker Hub zur Verfügung. Allgemeinere Frameworkbibliotheken und das größere Ökosystem der .NET-Bibliothek sind auf [NuGet](http://www.nuget.org/) verfügbar. 

**Modulare Plattform** – .NET Core basiert auf einem modularen Design, sodass Anwendungen nur die benötigten .NET Core-Bibliotheken und -Abhängigkeiten einbeziehen müssen. Jede Anwendung trifft ihre eigene .NET Core-Versionsauswahl, um Konflikte mit gemeinsam verwendeten Komponenten zu vermeiden. Dieser Ansatz entspricht dem Trend der Softwareentwicklung mithilfe von Containertechnologien wie Docker.

### <a name="net-framework"></a>.NET Framework

Das .NET Framework wird zum Erstellen von Apps für Windows und Windows Server verwendet. Sie können es zum Erstellen umfassender Benutzeroberflächen mit Windows Presentation Framework (WPF) und Windows Forms verwenden. Es unterstützt außerdem das Erstellen von Server-Apps mit ASP.NET Web Forms, ASP.NET MVC und Windows Communication Framework (WCF). Visual Studio bietet umfassende Designerfunktionen für das .NET Framework, damit Sie mit Leichtigkeit sowohl Client- als auch Server-Apps erstellen können. Die ideale Wahl für das Schreiben von Windows-Apps.

- Informationen zum [.NET Framework](https://msdn.microsoft.com/library/w0x726c2.aspx)
- [.NET Framework herunterladen](https://dot.net)

Mit [Windows Forms](https://msdn.microsoft.com/library/dd30h2yb.aspx) können Sie schneller als mit jeder anderen Technologie eine Desktopoberfläche nach dem Prinzip „Forms over Data“ erstellen. Es verwendet einen Designer, in dem Sie Benutzeroberflächen- und andere Steuerelemente per Drag & Drop ziehen und ablegen können, sodass die meisten Entwicklungsaufgaben sich auf eine einzige Aktion und ein konzeptionelles Modell reduzieren.

[Windows Presentation Foundation (WPF)](https://msdn.microsoft.com/library/ms754130.aspx) trennt Aspekte von Code und Benutzeroberfläche, indem die Benutzeroberfläche mithilfe der [XAML](https://msdn.microsoft.com/library/ms752059.aspx)-Markupsprache beschrieben wird. WPF ist sehr flexibel und wird häufig für Benutzeroberflächen eingesetzt, die ein komplexeres Benutzermodell oder eine elegantere Darstellung erfordern.

[Windows Communication Foundation (WCF)](https://msdn.microsoft.com/library/ms731082.aspx) ist ein Satz von Bibliotheken für SOAP-Webdienste. WCF ermöglicht Ihnen das Erstellen von Diensten, die über verschiedene unterstützte Protokolle unter Verwendung verschiedener Datenformate kommunizieren und in einem beliebigen von Ihnen gewählten Prozess gehostet werden können. Damit ergibt sich eines der wesentlichen Features von WCF: Ihre Dienste sind nicht an eine bestimmte Hostingstrategie oder an einen bestimmten Ansatz gebunden.

[ASP.NET](http://www.asp.net/) ist ein Webframework. Es setzt sich aus mehreren einzelnen Teilen zusammen, die zum Erstellen moderner und hochleistungsfähiger Webanwendungen verwendet werden. 

- Mit [ASP.NET Web Forms](http://www.asp.net/web-forms) können Sie schneller als mit den meisten anderen Webtechnologien eine Benutzeroberfläche nach dem Prinzip „Forms over Data“ erstellen – mit einem Designer, der das Ziehen und Ablegen (Drag & Drop) von Websteuerelementen ermöglicht. 
- [ASP.NET MVC](http://www.asp.net/mvc) verleiht Ihnen größere Kontrolle über die gesamte Webpipeline, von der HTTP-Ebene bis hin zur Benutzeroberfläche. 
- [ASP.NET WebAPI](http://www.asp.net/web-api) ist ein auf Konventionen basierendes Framework zum Erstellen von REST-Diensten. 
- Über [SignalR](http://www.asp.net/signalr) können Sie Ihren Webanwendungen eine Push-basierte Kommunikation über das [WebSocket](https://en.wikipedia.org/wiki/WebSocket)-Protokoll bereitstellen.

### <a name="net-native"></a>.NET Native

.NET Native ist ein Satz nativer Buildtools für .NET Core. .NET Native ist eine AOT-Toolchain (Ahead-of-Time), die native Anwendungen durch das Kompilieren von IL-Bytecode in nativen Code erstellt. Die daraus resultierende Binärdatei ist demnach das, was vom Betriebssystem ausgeführt wird. Es gibt keine JIT-Kompilierung zur Laufzeit. Dies führt zu einer besseren Startleistung und zu Sicherheitsvorteilen.

.NET Native wird hauptsächlich von .NET-[UWP](https://msdn.microsoft.com/library/windows/apps/dn726767.aspx)-Anwendungen (Universelle Windows-Plattform) verwendet.

### <a name="mono"></a>Mono

[Mono](http://www.mono-project.com/docs/about-mono/) ist die ursprüngliche Open Source- und plattformübergreifende Implementierung von .NET von der Community [Mono-Projekt](http://mono-project.com). Sie wird jetzt von Microsoft gesponsert. Man kann sich darunter eine offene und plattformübergreifende Version von .NET Framework vorstellen. Die APIs entsprechen den Vorgängen von .NET Framework, nicht von .NET Core.

Mono besteht aus mehreren Komponenten:

**C#-Compiler** – Der C#-Compiler von Mono umfasst sämtliche Features für C# 6.

**Mono-Runtime** – Die Runtime implementiert die ECMA-CLI (Common Language Infrastructure). Die Runtime umfasst einen JIT-Compiler (Just-in-Time), einen AOT-Compiler (Ahead-of-Time), ein Bibliotheksladeprogramm, den Garbage Collector, ein Threadingsystem und Interoperabilitätsfunktionen.

**Basisklassenbibliothek** – Die Mono-Plattform bietet einen umfassenden Satz von Klassen, die eine stabile Grundlage für die Erstellung von Anwendungen bereitstellen. Diese Klassen sind kompatibel mit den Microsoft .NET Framework-Klassen.

**Mono-Klassenbibliothek** – Mono bietet außerdem viele Klassen, die über die Basisklassenbibliothek von .NET Framework hinaus gehen. Diese bieten zusätzliche Funktionalität, die insbesondere beim Erstellen von Linux-Anwendungen hilfreich ist. Beispiele hierfür sind Klassen für GTK+, ZIP-Dateien, LDAP, OpenGL, Cairo, POSIX usw.

### <a name="xamarin-sdk"></a>Xamarin SDK

Das [Xamarin SDK](http://open.xamarin.com) dient zum Erstellen nativer mobiler Apps und Geräte-Apps, in erster Linie für Apple- und Google-Ökosysteme. Es basiert auf Mono und ist Open Source mit MIT-Lizenz. Sie können damit iOS- und Android-Apps für Telefone, Tablets und Uhren erstellen. [Xamarin.Forms](https://www.xamarin.com/forms) ist eine beliebte Möglichkeit zum Schreiben wiederverwendbarer Benutzeroberflächen für Apple-, Google- und Windows-Apps.

- Informationen zum [Xamarin-SDK](https://developer.xamarin.com/)
- [Xamarin herunterladen](https://www.xamarin.com/platform)



<!--HONumber=Nov16_HO1-->


