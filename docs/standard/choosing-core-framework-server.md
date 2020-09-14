---
title: Wahl zwischen .NET Core und .NET Framework für Server-Apps
description: Ein Leitfaden, der Sie bei der Entscheidung unterstützt, welche Implementierung von .NET bei der Erstellung einer Server-App verwendet werden soll.
author: cartermp
ms.date: 04/28/2020
ms.openlocfilehash: a3c15e8f2198b1bcc4e623a7dc7f5cddca9c83f6
ms.sourcegitcommit: b1f4756120deaecb8b554477bb040620f69a4209
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2020
ms.locfileid: "89415018"
---
# <a name="net-core-vs-net-framework-for-server-apps"></a>.NET Core im Vergleich zur .NET Framework für Server-Apps

Bei der Erstellung von serverseitigen Apps werden zwei .NET-Implementierungen unterstützt: .NET Framework und .NET Core. Beide nutzen viele gemeinsame Komponenten, und bei beiden stimmt ein Teil des Codes überein. Allerdings gibt es auch grundlegende Unterschiede. Daher richtet sich Ihre Entscheidung danach, was Sie erreichen möchten. Dieser Artikel stellt Anleitungen dazu bereit, welche Variante in welchen Fällen verwendet werden sollte.

Verwenden Sie in folgenden Fällen .NET Core für Ihre Serveranwendung:

- Es bestehen plattformübergreifende Anforderungen.
- Sie möchten Microservices erstellen.
- Sie verwenden Docker-Container.
- Sie sind auf skalierbare Hochleistungssysteme angewiesen.
- Sie benötigen pro Anwendung verschiedene parallele .NET-Versionen.

Verwenden Sie in folgenden Fällen .NET Framework für Ihre Serveranwendung:

- Sie verwenden für Ihre Anwendung derzeit .NET Framework (empfohlen wird eine Erweiterung anstelle einer Migration).
- Ihre Anwendung verwendet .NET-Bibliotheken von Drittanbietern oder NuGet-Paketen, die für .NET Core nicht verfügbar sind.
- Ihre Anwendung verwendet .NET-Technologien, die für .NET Core nicht verfügbar sind.
- Ihre Anwendung verwendet eine Plattform, die .NET Core nicht unterstützt. Windows, macOS und Linux unterstützen .NET Core.

## <a name="when-to-choose-net-core"></a>In welchen Fällen sollte .NET Core verwendet werden?

In den folgenden Abschnitten werden die zuvor genannten Gründe für eine Entscheidung für .NET Core ausführlicher erläutert.

### <a name="cross-platform-needs"></a>Plattformübergreifende Anforderungen

Wenn Ihre Anwendung (Web/Dienst) auf mehreren Plattformen ausgeführt werden muss (Windows, Linux und macOS), verwenden Sie .NET Core.

.NET Core unterstützt die zuvor genannten Betriebssysteme für Ihre Entwicklungsarbeitsstation. Visual Studio bietet eine integrierte Entwicklungsumgebung (Integrated Development Environment, IDE) für Windows und macOS. Sie können auch Visual Studio Code verwenden, das unter macOS, Linux und Windows ausgeführt werden kann. Visual Studio Code unterstützt .NET Core, einschließlich IntelliSense und Debugging. Die meisten Editoren von Drittanbietern, wie etwa Sublime, Emacs und VI, funktionieren mit .NET Core. Diese Editoren von Drittanbietern rufen IntelliSense mit [OmniSharp](https://www.omnisharp.net/) ab. Da Sie die [.NET Core-CLI](../core/tools/index.md) direkt verwenden können und diese für alle unterstützten Plattformen zur Verfügung steht, ist ein Code-Editor nicht notwendig.

### <a name="microservices-architecture"></a>Microservicearchitektur

Durch eine Microservicearchitektur ist eine dienstübergreifende Kombination aus Technologien möglich. Diese Kombination aus Technologien ermöglicht eine sukzessive Integration von .NET Core für neue Microservices, die mit anderen Microservices oder Diensten funktionieren. Sie können z.B. Microservices oder Dienste kombinieren, die mit .NET Framework, Java, Ruby oder einer anderen monolithischen Technologie entwickelt wurden.

Es stehen viele verschiedene Infrastrukturplattformen zur Verfügung. [Azure Service Fabric](https://azure.microsoft.com/services/service-fabric/) wurde für große und komplexe Microservicesysteme entwickelt. [Azure App Service](https://azure.microsoft.com/services/app-service/) ist eine gute Wahl bei zustandslosen Microservices. Auf Docker basierende Alternativen zu Microservices sind – wie im Abschnitt [Container](#containers) erläutert – mit allen Arten von Microserviceimplementierungen kompatibel. All diese Plattformen unterstützen .NET Core und eignen sich daher ideal zum Hosten Ihrer Microservices.

Weitere Informationen zur Microservicearchitektur finden Sie unter [ NET Microservices: Architecture for Containerized .NET Applications (.NET Microservices: Architektur für .NET-Containeranwendungen)](../architecture/microservices/index.md).

### <a name="containers"></a>Container

Container werden häufig in Verbindung mit einer Microservicearchitektur verwendet. Container können auch zur Containerisierung von Web-Apps und -Diensten verwendet werden, die einem Architekturmuster folgen. .NET Framework lässt sich auch für Windows-Container verwenden, allerdings ist .NET Core durch seine Modularität und den einfachen Aufbau besser für Container geeignet. Die Imagegröße eines mit .NET Core erstellten und bereitgestellten Containers ist wesentlich kleiner als bei .NET Framework. Aufgrund der plattformübergreifenden Struktur können Sie Server-Apps zum Beispiel in Linux-Docker-Containern bereitstellen.

Docker-Container können in Ihrer Linux- oder Windows-Infrastruktur oder in einem Clouddienst wie [Azure Kubernetes Service](https://azure.microsoft.com/services/kubernetes-service/) gehostet werden. Azure Kubernetes Service kann containerbasierte Anwendungen in der Cloud verwalten, orchestrieren und skalieren.

### <a name="high-performance-and-scalable-systems"></a>Hochleistungssysteme und skalierbare Systeme

Wenn Sie für Ihr System die bestmögliche Leistung und Skalierbarkeit benötigen, sind .NET Core und ASP.NET Core die besten Optionen für Sie. Die leistungsstarke Serverlaufzeit für Windows Server und Linux macht .NET zu einem leistungsfähigen Webframework für [TechEmpower-Benchmarks](https://www.techempower.com/benchmarks/#hw=ph&test=plaintext).

Leistung und Skalierbarkeit sind insbesondere für Microservicearchitekturen relevant, in denen Hunderte von Microservices ausgeführt werden können. Mit ASP.NET Core werden Systeme mit einer deutlich geringeren Zahl an Servern bzw. VMs ausgeführt. Durch die geringere Zahl an Servern bzw. VMs werden Kosten für die Infrastruktur und das Hosten gespart.

### <a name="side-by-side-net-versions-per-application-level"></a>Verschiedene parallele .NET-Versionen pro Anwendungsebene

Für das Installieren von Anwendungen mit Abhängigkeiten von verschiedenen .NET-Versionen wird .NET Core empfohlen. .NET Core unterstützt parallele Installationen verschiedener Versionen der .NET Core-Runtime auf demselben Computer. Diese parallele Installation ermöglicht das Vorhandensein mehrerer Dienste auf demselben Server, wobei jeder seine eigene .NET Core-Version aufweist. Zudem senkt sie Risiken und spart Kosten für Anwendungsupdates und IT-Vorgänge.

Eine parallele Installation ist mit .NET Framework nicht möglich. Dabei handelt es sich um eine Windows-Komponente, und es kann jeweils nur eine Version auf einem Computer vorhanden sein. Jede Version von .NET Framework ersetzt die vorherige Version. Wenn Sie eine neue App installieren, die auf eine neuere Version von .NET Framework abzielt, können Sie vorhandene Apps, die auf dem Computer ausgeführt werden, unterbrechen, da die vorherige Version ersetzt wurde.

## <a name="when-to-choose-net-framework"></a>In welchen Fällen sollte .NET Framework verwendet werden?

.NET Core bietet große Vorteile für neue Anwendungen und Anwendungsmuster. Jedoch bleibt .NET Framework die erste Wahl für viele Szenarios, weshalb .NET Framework nicht für alle Serveranwendungen durch .NET Core ersetzt wurde.

### <a name="current-net-framework-applications"></a>Vorhandene .NET Framework-Anwendungen

In den meisten Fällen müssen Sie Ihre vorhandenen Anwendungen nicht zu .NET Core migrieren. Stattdessen wird die Verwendung von .NET Core empfohlen, wenn Sie eine vorhandene Anwendung erweitern möchten, z.B. durch Schreiben eines neuen Webdiensts in ASP.NET Core.

### <a name="aspnet-core-on-net-framework"></a>ASP.NET Core unter .NET Framework

Informationen zur Unterstützung für ASP.NET Core unter .NET Framework finden Sie in der [.NET Core-Unterstützungsrichtlinie](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).

### <a name="third-party-libraries-or-nuget-packages-not-available-for-net-core"></a>Bibliotheken von Drittanbietern oder NuGet-Paketen nicht für .NET Core verfügbar

Aktuell können Sie die schnelle Integration vom .NET Standard in Bibliotheken beobachten. Mit .NET Standard können Sie Code in allen .NET-Implementierungen einschließlich .NET Core freigeben. Mit .NET Standard 2.0 ist das sogar noch einfacher:

- Die API-Oberfläche ist deutlich größer.
- Der .NET Framework-Kompatibilitätsmodus wurde eingeführt.

  Mit diesem Kompatibilitätsmodus können .NET Standard- und .NET Core-Projekte auf .NET Framework-Bibliotheken verweisen. Im Blogbeitrag [Announcing .NET Standard 2.0 (Ankündigung: .NET Standard 2.0)](https://devblogs.microsoft.com/dotnet/announcing-net-standard-2-0/) finden Sie weitere Informationen zum Kompatibilitätsmodus.

Sie müssen nur dann .NET Framework verwenden, wenn die Bibliotheken oder NuGet-Pakete Technologien verwenden, die nicht in .NET Standard bzw. .NET Core verfügbar sind.

### <a name="net-technologies-not-available-for-net-core"></a>.NET-Technologien, die für .NET Core nicht verfügbar sind

Einige .NET Framework-Technologien sind in .NET Core nicht verfügbar. Möglicherweise werden aber einige in zukünftigen .NET Core-Releases verfügbar gemacht. Andere können jedoch für die neuen Anwendungsmuster, auf die .NET Core abzielt, nicht verwendet werden und werden möglicherweise nie verfügbar sein. Die folgende Liste enthält die häufigsten Technologien, die von .NET Core nicht unterstützt werden:

- ASP.NET Web Forms-Anwendungen: ASP.NET-Web Forms sind nur in .NET Framework verfügbar. ASP.NET Core kann nicht für ASP.NET-Web Forms verwendet werden. Eine Integration von ASP.NET-.Web Forms in .NET Core ist nicht geplant.

- ASP.NET-Web Pages-Anwendungen: ASP.NET Web Pages sind nicht in ASP.NET Core enthalten.

- Implementierung von WCF-Diensten. Auch wenn WCF-Dienste über eine [WCF-Clientbibliothek](https://github.com/dotnet/wcf) von .NET Core genutzt werden, ist die WCF-Serverimplementierung aktuell nur in .NET Framework verfügbar. Dieses Szenario ist nicht Bestandteil der derzeitigen Pläne für .NET Core, wird jedoch für die Zukunft in Betracht gezogen.

- Workflow-bezogene Dienste: Windows Workflow Foundation (WF), die Workflow-Dienste (WCF + WF in einem einzigen Dienst) und WCF Data Services (früher „ADO.NET Data Services“) sind nur in .NET Framework verfügbar. Eine Integration dieser Technologien in .NET Core ist nicht geplant.

- Sprachenunterstützung: Visual Basic und F# werden aktuell in .NET Core unterstützt, allerdings nicht für alle Projekttypen. Eine Liste der unterstützten Projektvorlagen finden Sie im Abschnitt [Vorlagenoptionen für dotnet new](../core/tools/dotnet-new.md#arguments).

### <a name="platform-doesnt-support-net-core"></a>Plattformen, die .NET Core nicht unterstützen

Einige Plattformen von Microsoft oder Drittanbietern unterstützen .NET Core nicht. Einige Azure-Dienste stellen ein SDK bereit, das noch nicht für die Nutzung in .NET Core verfügbar ist. Dies ist allerdings nur vorübergehend der Fall, weil .NET Core von sämtlichen Azure-Diensten verwendet wird. In der Zwischenzeit können Sie anstelle des Client-SDKs die entsprechende REST-API verwenden.

## <a name="see-also"></a>Siehe auch

- [Wählen zwischen ASP.NET und ASP.NET Core](/aspnet/core/choose-aspnet-framework)
- [ASP.NET Core, das .NET Framework anzielt](/aspnet/core/introduction-to-aspnet-core#aspnet-core-targeting-net-framework)
- [Zielframeworks](frameworks.md)
- [Einführung in .NET](../core/introduction.md)
- [Portieren von .NET Framework zu .NET Core](../core/porting/index.md)
- [Einführung in .NET and Docker](../core/docker/introduction.md)
- [.NET-Komponenten – Übersicht](components.md)
- [.NET Microservices. Architecture for Containerized .NET Applications (.NET Microservices: Architektur für .NET-Containeranwendungen)](../architecture/microservices/index.md)
