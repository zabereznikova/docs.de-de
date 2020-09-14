---
title: .NET Core und Open-Source
description: .NET Core ist eine allgemeine, modulare, plattformübergreifende Open-Source-Implementierung von .NET Standard.
ms.date: 03/30/2017
ms.assetid: e6bd4655-ce37-4003-8462-468a6fe2c40f
ms.openlocfilehash: 4627d4cc1bf45f3a7ad3f269279384b4a303f00d
ms.sourcegitcommit: b1f4756120deaecb8b554477bb040620f69a4209
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2020
ms.locfileid: "89414915"
---
# <a name="net-core-and-open-source"></a>.NET Core und Open-Source

Dieser Artikel enthält einen kurzen Überblick über .NET Core und zeigt, wie Sie weitere Informationen erhalten können.

## <a name="what-is-net-core"></a>Was ist .NET Core?  

.NET Core ist eine allgemeine, modulare, plattformübergreifende Open Source-Implementierung des .NET-Standards. Sie enthält viele derselben APIs wie das .NET Framework (aber .NET Core umfasst eine kleinere Gruppe) und umfasst Runtime-, Framework-, Compiler- und Toolkomponenten, die eine Vielzahl von Betriebssystemen und Prozessorzielen unterstützen. Die .NET Core-Implementierung wurde in erster Linie durch die ASP.NET Core-Arbeitsauslastungen gesteuert, aber auch durch die Notwendigkeit und den Wunsch nach einer moderneren Implementierung. Sie kann in Geräte-, Cloud- und eingebetteten/IoT-Szenarien verwendet werden.  
  
Informationen zu den ersten Schritten mit .NET Core finden Sie im .NET-Tutorial [Hallo Welt in zehn Minuten](https://dotnet.microsoft.com/learn/dotnet/hello-world-tutorial/intro).  
  
.NET Core weist die folgenden wesentlichen Merkmale auf:
  
- **Plattformübergreifend:** .NET Core stellt Hauptfunktionen zur Implementierung der erforderlichen App-Funktionen bereit sowie zur Wiederverwendung dieses Codes unabhängig von Ihrer Zielplattform. Derzeit werden die drei Hauptbetriebssysteme unterstützt: Windows, Linux und macOS Sie können Apps und Bibliotheken schreiben, die über unterstützte Betriebssysteme hinweg unverändert ausgeführt werden. Die Liste der unterstützten Betriebssysteme finden Sie unter [.NET Core Roadmap](https://github.com/dotnet/core/blob/master/roadmap.md).
  
- **Open Source:** .NET Core ist eines der vielen Projekten unter der Leitung der [.NET Foundation](https://www.dotnetfoundation.org/) und ist auf [GitHub](https://github.com/) verfügbar. Als Open-Source-Projekt fördert .NET Core einen transparenteren Entwicklungsprozess und aktive und engagierte Community.  
  
- **Flexible Bereitstellung:** Es gibt zwei Hauptmethoden zum Bereitstellen Ihrer App: Frameworkabhängige oder eigenständige Bereitstellung. Bei der frameworkabhängigen Bereitstellung werden nur Ihre App und Abhängigkeiten von Drittanbietern installiert. Zudem hängt Ihre App von der Verfügbarkeit einer systemweiten Version von .NET Core ab. Bei der eigenständigen Bereitstellung wird die .NET Core-Version, die zum Erstellen der Anwendung verwendet wird, auch zusammen mit Ihrer App und Abhängigkeiten von Drittanbietern bereitgestellt. Sie kann auch parallel mit anderen Versionen ausgeführt werden. Weitere Informationen finden Sie unter [.NET Core Anwendungsbereitstellung](../../core/deploying/index.md).

- **Modular:** .NET Core ist modular aufgebaut, weil es über NuGet in kleineren Assemblypaketen veröffentlicht wird. Statt in einer großen Assembly, die die meisten der Kernfunktionalitäten enthält, wird .NET Core in kleineren, funktionsorientierten Paketen zur Verfügung gestellt. Diese Modularität ermöglicht uns ein flexibleres Entwicklungsmodell und gestattet es Ihnen, Ihre App zu optimieren, um nur die erforderlichen NuGet-Pakete einzubeziehen. Die Vorteile eines kleineren App-Oberflächenbereichs umfassen straffere Sicherheit, verringerte Wartungsarbeiten, verbesserte Leistung und niedrigere Kosten bei einem Modell mit nutzungsabhängiger Preisgestaltung.  
  
## <a name="the-net-core-platform"></a>Die .NET Core-Plattform
  
Die .NET Core-Plattform besteht aus mehreren Komponenten, die den verwalteten Compiler, die Runtime, die Basisklassenbibliotheken sowie zahlreiche Anwendungsmodelle wie ASP.NET Core umfassen. Weitere Informationen zu den verschiedenen Komponenten finden Sie in den folgenden [GitHub](https://github.com/)-Repositorys:  
  
- [.NET Core Home](https://github.com/dotnet/core)  
  
- [Runtime: .NET Core-Plattform und -Laufzeit](https://github.com/dotnet/runtime)  
  
- [CLI – Tools für die .NET Core-Befehlszeile](https://github.com/dotnet/cli)  
  
- [Roslyn – .NET-Compilerplattform](https://github.com/dotnet/roslyn)  
  
- [ASP.NET Core](https://github.com/dotnet/aspnetcore)  
  
## <a name="see-also"></a>Siehe auch

- [.NET-Tutorial: Hallo Welt in zehn Minuten](https://dotnet.microsoft.com/learn/dotnet/hello-world-tutorial/intro)
- [Einführung in .NET](../../core/introduction.md)
- [Dokumentation zu ASP.NET Core](/aspnet/core/)
