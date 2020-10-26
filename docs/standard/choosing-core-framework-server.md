---
title: .NET 5 im Vergleich zum .NET Framework für Server-Apps
description: Ein Leitfaden, der Sie bei der Entscheidung unterstützt, welche Implementierung von .NET bei der Erstellung einer Server-App verwendet werden soll.
author: cartermp
ms.date: 10/06/2020
ms.openlocfilehash: d9dce0343f9d37e976472b818e896a5b0a661e76
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92160450"
---
# <a name="net-5-vs-net-framework-for-server-apps"></a>.NET 5 für Server-Apps im Vergleich zum .NET Framework

Für die Erstellung von serverseitigen Apps werden zwei .NET-Implementierungen unterstützt: das .NET Framework und .NET 5 (einschließlich .NET Core). Beide nutzen viele gemeinsame Komponenten, und bei beiden stimmt ein Teil des Codes überein. Allerdings gibt es auch grundlegende Unterschiede. Daher richtet sich Ihre Entscheidung danach, was Sie erreichen möchten. Dieser Artikel stellt Anleitungen dazu bereit, welche Variante in welchen Fällen verwendet werden sollte.

Verwenden Sie in den folgenden Fällen .NET 5 für Ihre Serveranwendung:

- Es bestehen plattformübergreifende Anforderungen.
- Sie möchten Microservices erstellen.
- Sie verwenden Docker-Container.
- Sie sind auf skalierbare Hochleistungssysteme angewiesen.
- Sie benötigen pro Anwendung verschiedene parallele .NET-Versionen.

Verwenden Sie in folgenden Fällen .NET Framework für Ihre Serveranwendung:

- Sie verwenden für Ihre Anwendung derzeit .NET Framework (empfohlen wird eine Erweiterung anstelle einer Migration).
- Ihre App verwendet .NET-Bibliotheken von Drittanbietern oder NuGet-Pakete, die für .NET 5 nicht verfügbar sind.
- Ihre App verwendet .NET-Technologien, die für .NET 5 nicht verfügbar sind.
- Ihre Anwendung verwendet eine Plattform, die .NET 5 nicht unterstützt.

## <a name="when-to-choose-net-5"></a>In welchen Fällen sollte .NET 5 verwendet werden?

In den folgenden Abschnitten werden die zuvor genannten Gründe für eine Entscheidung für .NET 5 ausführlicher erläutert.

### <a name="cross-platform-needs"></a>Plattformübergreifende Anforderungen

Wenn Ihre Anwendung (Web/Dienst) auf mehreren Plattformen ausgeführt werden muss (Windows, Linux und macOS), verwenden Sie .NET 5.

.NET 5 unterstützt die zuvor genannten Betriebssysteme für Ihre Entwicklungsarbeitsstation. Visual Studio bietet eine integrierte Entwicklungsumgebung (Integrated Development Environment, IDE) für Windows und macOS. Sie können auch Visual Studio Code verwenden, das unter macOS, Linux und Windows ausgeführt werden kann. Visual Studio Code unterstützt .NET 5, einschließlich IntelliSense und Debugging. Die meisten Editoren von Drittanbietern funktionieren mit .NET 5, z. B. Sublime, Emacs und VI. Diese Editoren von Drittanbietern rufen IntelliSense mit [OmniSharp](https://www.omnisharp.net/) ab. Da Sie die [.NET Core-CLI](../core/tools/index.md) direkt verwenden können und diese für alle unterstützten Plattformen zur Verfügung steht, ist ein Code-Editor nicht notwendig.

### <a name="microservices-architecture"></a>Microservicearchitektur

Durch eine Microservicearchitektur ist eine dienstübergreifende Kombination aus Technologien möglich. Diese Kombination aus Technologien ermöglicht eine sukzessive Integration von .NET 5 für neue Microservices, die mit anderen Microservices oder Diensten funktionieren. Sie können z.B. Microservices oder Dienste kombinieren, die mit .NET Framework, Java, Ruby oder einer anderen monolithischen Technologie entwickelt wurden.

Es stehen viele verschiedene Infrastrukturplattformen zur Verfügung. [Azure Service Fabric](https://azure.microsoft.com/services/service-fabric/) wurde für große und komplexe Microservicesysteme entwickelt. [Azure App Service](https://azure.microsoft.com/services/app-service/) ist eine gute Wahl bei zustandslosen Microservices. Auf Docker basierende Alternativen zu Microservices sind – wie im Abschnitt [Container](#containers) erläutert – mit allen Arten von Microserviceimplementierungen kompatibel. All diese Plattformen unterstützen .NET 5 und eignen sich daher ideal zum Hosten Ihrer Microservices.

Weitere Informationen zur Microservicearchitektur finden Sie unter [ NET Microservices: Architecture for Containerized .NET Applications (.NET Microservices: Architektur für .NET-Containeranwendungen)](../architecture/microservices/index.md).

### <a name="containers"></a>Container

Container werden häufig in Verbindung mit einer Microservicearchitektur verwendet. Container können auch zur Containerisierung von Web-Apps und -Diensten verwendet werden, die einem Architekturmuster folgen. Das .NET Framework lässt sich auch für Windows-Container verwenden, allerdings ist .NET 5 durch seine Modularität und den einfachen Aufbau besser für Container geeignet. Die Imagegröße eines mit .NET 5 erstellten und bereitgestellten Containers ist wesentlich kleiner als beim .NET Framework. Aufgrund der plattformübergreifenden Struktur können Sie Server-Apps zum Beispiel in Linux-Docker-Containern bereitstellen.

Docker-Container können in Ihrer Linux- oder Windows-Infrastruktur oder in einem Clouddienst wie [Azure Kubernetes Service](https://azure.microsoft.com/services/kubernetes-service/) gehostet werden. Azure Kubernetes Service kann containerbasierte Anwendungen in der Cloud verwalten, orchestrieren und skalieren.

### <a name="high-performance-and-scalable-systems"></a>Hochleistungssysteme und skalierbare Systeme

Wenn Ihr System die bestmögliche Leistung und Skalierbarkeit erfordert, eignen sich .NET 5 und ASP.NET Core am besten. Die leistungsstarke Serverlaufzeit für Windows Server und Linux macht .NET zu einem leistungsfähigen Webframework für [TechEmpower-Benchmarks](https://www.techempower.com/benchmarks/#hw=ph&test=plaintext).

Leistung und Skalierbarkeit sind insbesondere für Microservicearchitekturen relevant, in denen Hunderte von Microservices ausgeführt werden können. Mit ASP.NET Core werden Systeme mit einer deutlich geringeren Zahl an Servern bzw. VMs ausgeführt. Durch die geringere Zahl an Servern bzw. VMs werden Kosten für die Infrastruktur und das Hosten gespart.

### <a name="side-by-side-net-versions-per-application-level"></a>Verschiedene parallele .NET-Versionen pro Anwendungsebene

Für das Installieren von Anwendungen mit Abhängigkeiten von verschiedenen .NET-Versionen wird .NET 5 empfohlen. .NET 5 unterstützt parallele Installationen verschiedener Versionen der .NET 5-Runtime auf demselben Computer. Durch diese parallele Installation können mehrerer Dienste auf demselben Server ausgeführt werden, wobei jeder seine eigene .NET 5-Version (.NET Core 2.1 oder 3.1) aufweist. Zudem senkt sie Risiken und spart Kosten für Anwendungsupdates und IT-Vorgänge.

Eine parallele Installation ist mit dem .NET Framework nicht möglich. Es handelt sich hierbei um eine Windows-Komponente, und es kann jeweils nur eine Version auf einem Computer vorhanden sein. Jede Version von .NET Framework ersetzt die vorherige Version. Wenn Sie eine neue App installieren, die auf eine neuere Version von .NET Framework abzielt, können Sie vorhandene Apps, die auf dem Computer ausgeführt werden, unterbrechen, da die vorherige Version ersetzt wurde.

## <a name="when-to-choose-net-framework"></a>In welchen Fällen sollte .NET Framework verwendet werden?

.NET 5 bietet große Vorteile für neue Anwendungen und Anwendungsmuster. Allerdings bleibt das .NET Framework die erste Wahl für viele Szenarios, weshalb es nicht für alle Serveranwendungen durch .NET 5 ersetzt wurde.

### <a name="current-net-framework-applications"></a>Vorhandene .NET Framework-Anwendungen

In den meisten Fällen müssen Sie Ihre vorhandenen Anwendungen nicht zu .NET 5 migrieren. Stattdessen wird die Verwendung von .NET 5 empfohlen, wenn Sie eine vorhandene Anwendung erweitern möchten, z. B. durch Schreiben eines neuen Webdiensts in ASP.NET Core.

### <a name="third-party-libraries-or-nuget-packages-not-available-for-net-5"></a>Bibliotheken von Drittanbietern oder NuGet-Paketen sind nicht für .NET 5 verfügbar

Mit .NET Standard können Sie Code in allen .NET-Implementierungen einschließlich .NET 5 freigeben. Für .NET Standard 2.0 ermöglicht ein Kompatibilitätsmodus, dass .NET Standard- und .NET 5-Projekte auf .NET Framework-Bibliotheken verweisen können. Weitere Informationen finden Sie unter [Unterstützung für .NET Framework-Bibliotheken](whats-new/whats-new-in-dotnet-standard.md#support-for-net-framework-libraries).

Sie müssen nur dann das .NET Framework verwenden, wenn die Bibliotheken oder NuGet-Pakete Technologien verwenden, die nicht in .NET Standard bzw. .NET 5 verfügbar sind.

### <a name="net-technologies-not-available-for-net-5"></a>.NET-Technologien, die für .NET 5 nicht verfügbar sind

Einige .NET Framework-Technologien sind in .NET 5 nicht verfügbar. Die folgende Liste enthält die häufigsten Technologien, die von .NET 5 nicht unterstützt werden:

- ASP.NET Web Forms-Anwendungen: ASP.NET-Web Forms sind nur in .NET Framework verfügbar. ASP.NET Core kann nicht für ASP.NET-Web Forms verwendet werden.

- ASP.NET-Web Pages-Anwendungen: ASP.NET Web Pages sind nicht in ASP.NET Core enthalten.

- Implementierung von WCF-Diensten. Auch wenn WCF-Dienste über eine [WCF-Clientbibliothek](https://github.com/dotnet/wcf) von .NET 5 genutzt werden, ist die WCF-Serverimplementierung aktuell nur im .NET Framework verfügbar.

- Workflow-bezogene Dienste: Windows Workflow Foundation (WF), die Workflow-Dienste (WCF + WF in einem einzigen Dienst) und WCF Data Services (früher „ADO.NET Data Services“) sind nur in .NET Framework verfügbar.

- Sprachenunterstützung: Visual Basic und F# werden aktuell in .NET 5 unterstützt, allerdings nicht für alle Projekttypen. Eine Liste der unterstützten Projektvorlagen finden Sie im Abschnitt [Vorlagenoptionen für dotnet new](../core/tools/dotnet-new.md#arguments).

Weitere Informationen finden Sie unter [.NET Framework-Technologien, die in .NET 5 nicht verfügbar sind](../core/porting/net-framework-tech-unavailable.md).

### <a name="platform-doesnt-support-net-5"></a>Plattform unterstützt .NET 5 nicht

Einige Plattformen von Microsoft oder Drittanbietern unterstützen .NET 5 nicht. Einige Azure-Dienste stellen ein SDK bereit, das noch nicht für die Nutzung in .NET 5 verfügbar ist. In solchen Fällen können Sie anstelle des Client-SDKs die entsprechende REST-API verwenden.

## <a name="see-also"></a>Siehe auch

- [Wählen zwischen ASP.NET und ASP.NET Core](/aspnet/core/choose-aspnet-framework)
- [ASP.NET Core, das .NET Framework anzielt](/aspnet/core/introduction-to-aspnet-core?view=aspnetcore-2.2&preserve-view=true#aspnet-core-targeting-net-framework)
- [Zielframeworks](frameworks.md)
- [Einführung in .NET](../core/introduction.md)
- [Portieren vom .NET Framework zu .NET 5](../core/porting/index.md)
- [Einführung in .NET and Docker](../core/docker/introduction.md)
- [.NET-Komponenten – Übersicht](components.md)
- [.NET Microservices. Architecture for Containerized .NET Applications (.NET Microservices: Architektur für .NET-Containeranwendungen)](../architecture/microservices/index.md)
