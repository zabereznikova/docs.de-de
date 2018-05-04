---
title: Offizielle .NET-Docker-Images
description: .NET-Microservicesarchitektur für .NET-Containeranwendungen | Offizielle .NET-Docker-Images
keywords: Docker, Microservices, ASP.NET, Container
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: adbe63a2d2f93819b5b29c6dd8d8089cd35ad2f3
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="official-net-docker-images"></a>Offizielle .NET-Docker-Images

Die offiziellen .NET-Docker-Images sind Docker-Images, die von Microsoft erstellt und optimiert werden. Sie sind öffentlich in den Microsoft-Repositorys im [Docker-Hub](https://hub.docker.com/u/microsoft/) verfügbar. Jedes Repository kann je nach .NET-Version und der Version des Betriebssystems mehrere Images enthalten (Linux Debian, Alpine Linux, Windows Nano Server, Windows Server Core usw.).

.NET-Repositorys wurden von Microsoft entworfen, um spezialisierte Repositorys bereitzustellen, falls sie ein bestimmtes Szenario oder eine bestimmte Workload darstellen. Die [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/)-Images sollten z.B. verwendet werden, wenn ASP.NET Core auf Docker verwendet wird, da ASP.NET Core-Images zusätzliche Optimierungen bereitstellen, sodass Container schneller gestartet werden können.

Die .NET Core-Images (microsoft/dotnet) hingegen wurden für Konsolen-Apps konzipiert, die auf .NET Core basieren. Beispielsweise sollten Batchprozesse, Azure WebJobs und andere Konsolenszenarios .NET Core verwenden. Diese Images enthalten nicht den ASP.NET Core-Stapel, was zu einem kleineren Containerimage führt.

Die meisten Image-Repositorys stellen umfangreiche Taggingfunktionen bereit, die Sie nicht nur bei der Auswahl einer bestimmten Frameworkversion unterstützen, sondern auch bei der des Betriebssystems (Linux-Distribution oder Windows-Version).

Weitere Informationen zu den offiziellen .NET-Docker-Images, die von Microsoft bereitgestellt werden, finden Sie unter der [Zusammenfassung zu .NET-Docker-Images](https://aka.ms/dotnetdockerimages).

## <a name="net-core-and-docker-image-optimizations-for-development-versus-production"></a>.NET Core- und Docker-Imageoptimierungen für die Entwicklung und die Produktion

Beim Erstellen von Docker-Images für Entwickler standen für Microsoft die folgenden wichtigen Szenarios im Mittelpunkt:

-   Images zum *Entwickeln* und Erstellen von .NET Core-Apps

-   Images zum *Ausführen* von .NET Core-Apps

Warum mehrere Images? Beim Entwickeln, Erstellen und Ausführen von Containeranwendungen gibt es üblicherweise unterschiedliche Prioritäten. Durch das Bereitstellen verschiedener Images leistet Microsoft einen Beitrag zur Optimierung der separaten Prozesse des Entwickelns, Erstellens und Bereitstellens von Apps.

### <a name="during-development-and-build"></a>Während der Entwicklung und Erstellung

In der Entwicklungsphase zählt, wie schnell Sie Änderungen durchlaufen und Änderungen debuggen können. Die Größe des Images ist nicht so entscheidend wie die Fähigkeit, Änderungen am Code vorzunehmen und schnell anzuzeigen. Einige Tools und „Build-Agent-Container“ verwenden das ASP.NET Core-Entwicklungsimage (microsoft/aspnetcore-build) während der Entwicklung und des Buildprozesses. Wenn Sie innerhalb eines Docker-Containers programmieren, sind die Elemente, die zum Kompilieren der App benötigt werden, das Wichtigste. Das schließt den Compiler und alle anderen .NET-Abhängigkeiten sowie Webentwicklungsabhängigkeiten wie npm, Gulp und Bower mit ein.

Warum ist diese Art von Buildimage wichtig? Dieses Image wird nie in einer Produktionsumgebung bereitgestellt. Damit wird ausschließlich der Inhalt erstellt, den Sie in einem Produktionsimage platzieren. Dieses Image wird dann in der Continuous Integration- oder Buildumgebung verwendet. Anstatt alle Anwendungsabhängigkeiten z.B. manuell direkt auf einem Build-Agent zu installieren (z.B. einer VM), instanziiert der Build-Agent beispielsweise ein .NET Core-Buildimage mit allen Abhängigkeiten, die zum Erstellen der App erforderlich sind. Der Build-Agent muss nur wissen, wie dieses Docker-Image ausgeführt wird. Dies vereinfacht die CI-Umgebung und macht sie wesentlich vorhersagbarer.

### <a name="in-production"></a>In einer Produktionsumgebung

In der Produktion ist wichtig, wie schnell Sie bereitstellen und die Container basierend auf einem Produktions-.NET Core-Image starten können. Das Image, das auf [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) basiert und nur die Runtime enthält, ist aus diesem Grund klein: damit es von der Docker-Registrierung schnell über das Netzwerk an die Docker-Hosts übertragen werden kann. Die Inhalte sind bereit zur Ausführung und ermöglichen eine minimale Zeitspanne zwischen dem Start des Containers und dem Verarbeiten der Ergebnisse. Anders als bei „dotnet build“ oder „dotnet publish“ beim Verwenden des Buildcontainers besteht im Docker-Modell keine Notwendigkeit, C\#-Code zu kompilieren.

In diesem optimierten Image werden nur die Binärdateien und andere Inhalte platziert, die zum Ausführen der Anwendung erforderlich sind. Der von „dotnet publish“ erstellte Inhalt enthält z.B. nur die kompilierten .NET-Binärdateien, Images sowie JS- und CSS-Dateien. Im Laufe der Zeit sehen Sie Images, die JIT-kompilierte Pakete enthalten.

Obwohl mehrere Versionen der .NET Core- und ASP.NET Core-Images verfügbar sind, haben sie alle mindestens eine Ebene gemeinsam, einschließlich der Grundebene. Aus diesem Grund ist wenig Speicherplatz erforderlich, um ein Image zu speichern, denn es besteht nur aus dem Delta zwischen dem benutzerdefinierten Image und dem Basis-Image. So können Sie das Image schnell aus der Registrierung abrufen.

Wenn Sie sich die .NET-Image-Repositorys im Docker-Hub ansehen, werden Sie mehrere Imageversionen finden, die klassifiziert oder mit Tags versehen sind. Diese Tags helfen dabei, je nach benötigter Version zu entscheiden, welches Image verwendet werden sollte, so wie in der folgenden Tabelle:

-   microsoft/**aspnetcore:2.0**

        ASP.NET Core, with runtime only and ASP.NET Core optimizations, on Linux and Windows (multi-arch)

-   microsoft/**aspnetcore-build:2.0**

        ASP.NET Core, with SDKs included, on Linux and Windows (multi-arch)


>[!div class="step-by-step"]
[Zurück] (net-container-os-targets.md) [Weiter] (../architect-microservice-container-applications/index.md)
