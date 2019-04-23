---
title: .NET Core und Open-Source
ms.date: 03/30/2017
ms.assetid: e6bd4655-ce37-4003-8462-468a6fe2c40f
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5eeef28f9a1d81ffa6328bfa5f2a8ed5295b47aa
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59163422"
---
# <a name="net-core-and-open-source"></a>.NET Core und Open-Source
Dieses Thema enthält einen kurzen Überblick über .NET Core und zeigt, wie Sie weitere Informationen erhalten können. Die vollständige Liste der Themen für .NET Core finden Sie im [Leitfaden für .NET Core](../../core/index.md).
  
<a name="BKMK_WhatisNETCore"></a>   
## <a name="what-is-net-core"></a>Was ist .NET Core?  
 .NET Core ist eine allgemeine, modulare, plattformübergreifende Open Source-Implementierung der .NET-Standards. Sie enthält viele derselben APIs wie das .NET Framework (aber .NET Core umfasst eine kleinere Gruppe) und umfasst Runtime-, Framework-, Compiler- und Toolkomponenten, die eine Vielzahl von Betriebssystemen und Prozessorzielen unterstützt. Die .NET Core-Implementierung wurde in erster Linie durch die ASP.NET Core-Arbeitsauslastungen gesteuert, aber auch durch die Notwendigkeit und den Wunsch nach einer moderneren Implementierung. Sie kann in Geräte-, Cloud- und eingebetteten/IoT-Szenarien verwendet werden.  
  
 Besuchen Sie für die ersten Schritte mit .NET Core die [.NET Core-Homepage](https://www.microsoft.com/net/core).  
  
 Im Folgenden sind die wesentlichen Merkmale von .NET Core aufgeführt:  
  
-   **Plattformübergreifend:** .NET Core stellt Hauptfunktionen zur Implementierung der erforderlichen App-Funktionen bereit sowie zur Wiederverwendung dieses Codes unabhängig von Ihrer Zielplattform. Derzeit werden die drei Hauptbetriebssysteme unterstützt: Windows, Linux und macOS. Sie können Apps und Bibliotheken schreiben, die über unterstützte Betriebssysteme hinweg unverändert ausgeführt werden. Die Liste der unterstützten Betriebssysteme finden Sie unter [.NET Core Roadmap](https://github.com/dotnet/core/blob/master/roadmap.md).
  
-   **Open Source:** .NET Core ist eines der vielen Projekten unter der Leitung der [.NET Foundation](https://www.dotnetfoundation.org/) und ist auf [GitHub](https://github.com/) verfügbar.  Die Entwicklung von .NET Core als Open Source-Projekt fördert einen transparenteren Entwicklungsprozess sowie eine aktive und engagierte Community.  
  
-   **Flexible Bereitstellung:** Es gibt zwei Hauptmethoden zum Bereitstellen Ihrer App: Frameworkabhängige oder eigenständige Bereitstellung. Bei der frameworkabhängigen Bereitstellung werden nur Ihre App und Abhängigkeiten von Drittanbietern installiert. Zudem hängt Ihre App von der Verfügbarkeit einer systemweiten Version von .NET Core ab.  Bei der eigenständigen Bereitstellung wird die .NET Core-Version, die zum Erstellen der Anwendung verwendet wird, auch zusammen mit Ihrer App und Abhängigkeiten von Drittanbietern bereitgestellt. Sie kann auch parallel mit anderen Versionen ausgeführt werden.    Weitere Informationen finden Sie unter [.NET Core Anwendungsbereitstellung](../../core/deploying/index.md).

-   **Modular:** .NET Core ist modular aufgebaut, weil es über NuGet in kleineren Assemblypaketen veröffentlicht wird. Statt in einer großen Assembly, die die meisten der Kernfunktionalitäten enthält, wird .NET Core in kleineren, funktionsorientierten Pakete zur Verfügung gestellt. Dies ermöglicht uns ein flexibleres Entwicklungsmodell und gestattet es Ihnen, Ihre App zu optimieren, um nur die erforderlichen NuGet-Pakete einzubeziehen. Die Vorteile eines kleineren App-Oberflächenbereichs umfassen straffere Sicherheit, verringerte Wartungsarbeiten, verbesserte Leistung und niedrigere Kosten bei einem Modell mit nutzungsabhängiger Preisgestaltung.  
  
## <a name="the-net-core-platform"></a>.NET Core-Plattform  
 Die .NET Core-Plattform besteht aus mehreren Komponenten, die den verwalteten Compiler, die Runtime, die Basisklassenbibliotheken sowie zahlreiche Anwendungsmodelle wie ASP.NET Core umfassen. Weitere Informationen zu den verschiedenen Komponenten finden Sie in den folgenden [GitHub](https://github.com/)-Repositorys:  
  
-   [.NET Core](https://github.com/dotnet/core)  
  
-   [CoreFX – Grundlegende .NET Core-Bibliotheken](https://github.com/dotnet/corefx)  
  
-   [CoreCLR – .NET Core-Runtime](https://github.com/dotnet/coreclr)  
  
-   [CLI – Tools für die .NET Core-Befehlszeile](https://github.com/dotnet/cli)  
  
-   [Roslyn – .NET-Compilerplattform](https://github.com/dotnet/roslyn)  
  
-   [ASP.NET Core](https://github.com/aspnet/home)  
  
## <a name="see-also"></a>Siehe auch

- [.NET Core-Homepage](https://www.microsoft.com/net/core)
- [Leitfaden für .NET Core](../../core/index.md)
- [ASP.NET Core-Dokumentation](/aspnet/core/)
