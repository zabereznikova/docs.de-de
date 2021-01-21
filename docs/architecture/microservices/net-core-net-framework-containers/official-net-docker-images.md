---
title: Offizielle .NET-Docker-Images
description: .NET-Microservicesarchitektur für .NET-Containeranwendungen | Offizielle .NET-Docker-Images
ms.date: 01/13/2021
ms.openlocfilehash: 3f4b58b2775c4e80b69cbd707396ebe98ccfe29c
ms.sourcegitcommit: a4cecb7389f02c27e412b743f9189bd2a6dea4d6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/14/2021
ms.locfileid: "98188620"
---
# <a name="official-net-docker-images"></a>Offizielle .NET-Docker-Images

Die offiziellen .NET-Docker-Images sind Docker-Images, die von Microsoft erstellt und optimiert werden. Sie sind öffentlich in den Microsoft-Repositorys im [Docker-Hub](https://hub.docker.com/u/microsoft/) verfügbar. Jedes Repository kann je nach .NET-Version und der Version des Betriebssystems mehrere Images enthalten (Linux Debian, Alpine Linux, Windows Nano Server, Windows Server Core usw.).

Seit .NET Core 2.1 stehen alle .NET Core-Images (auch für ASP.NET Core) auf Docker Hub im .NET-Imagerepository zur Verfügung: <https://hub.docker.com/_/microsoft-dotnet/>.

Seit Mai 2018 werden Microsoft-Images [in der Microsoft Container Registry syndiziert](https://azure.microsoft.com/blog/microsoft-syndicates-container-catalog/). Der offizielle Katalog ist nach wie vor nur in Docker Hub verfügbar, und dort finden Sie die aktualisierte Adresse zum Pullen des Images.

Die meisten Repositorys für Images bieten umfangreiche Taggingfunktionen, die Sie nicht nur bei der Wahl einer bestimmten Frameworkversion unterstützen, sondern auch bei der des Betriebssystems (Linux-Distribution oder Windows-Version).

## <a name="net-and-docker-image-optimizations-for-development-versus-production"></a>.NET- und Docker-Imageoptimierungen für die Entwicklung und die Produktion im Vergleich

Beim Erstellen von Docker-Images für Entwickler standen für Microsoft die folgenden wichtigen Szenarios im Mittelpunkt:

- Images zum *Entwickeln* und Erstellen von .NET-Apps

- Images zum *Ausführen* von .NET-Apps

Warum mehrere Images? Beim Entwickeln, Erstellen und Ausführen von Containeranwendungen gibt es üblicherweise unterschiedliche Prioritäten. Durch das Bereitstellen verschiedener Images leistet Microsoft einen Beitrag zur Optimierung der separaten Prozesse des Entwickelns, Erstellens und Bereitstellens von Apps.

### <a name="during-development-and-build"></a>Während der Entwicklung und Erstellung

In der Entwicklungsphase zählt, wie schnell Sie Änderungen durchlaufen und Änderungen debuggen können. Die Größe des Images ist nicht so entscheidend wie die Fähigkeit, Änderungen am Code schnell vorzunehmen und anzuzeigen. Einige Tools und Build-Agent-Container verwenden während des Entwicklungs- und Buildprozesses das .NET-Entwicklungsimage (*mcr.microsoft.com/dotnet/sdk:5.0*). Wenn Sie Builds innerhalb eines Docker-Containers erstellen, sind die Elemente, die zum Kompilieren der App benötigt werden, das Wichtigste. Das schließt den Compiler und alle anderen .NET-Abhängigkeiten ein.

Warum ist diese Art von Buildimage wichtig? Sie stellen dieses Image nicht in der Produktion bereit. Damit wird ausschließlich der Inhalt erstellt, den Sie in einem Produktionsimage platzieren. Dieses Image wird dann bei Verwendung mehrstufiger Docker-Builds in der Continuous Integration- oder Buildumgebung verwendet.

### <a name="in-production"></a>In einer Produktionsumgebung

In der Produktion ist wichtig, wie schnell Sie Container basierend auf einem .NET-Produktionsimage bereitstellen und starten können. Das Image, das auf *mcr.microsoft.com/dotnet/aspnet:5.0* basiert und nur die Runtime enthält, ist daher klein, damit es von der Docker-Registrierung schnell über das Netzwerk an die Docker-Hosts übertragen werden kann. Die Inhalte sind bereit zur Ausführung und ermöglichen eine minimale Zeitspanne zwischen dem Start des Containers und dem Verarbeiten der Ergebnisse. Anders als bei „dotnet build“ oder „dotnet publish“ beim Verwenden des Buildcontainers besteht im Docker-Modell keine Notwendigkeit, C\#-Code zu kompilieren.

In diesem optimierten Image werden nur die Binärdateien und andere Inhalte platziert, die zum Ausführen der Anwendung erforderlich sind. Der von `dotnet publish` erstellte Inhalt enthält z. B. nur die kompilierten .NET-Binärdateien, Images sowie JS- und CSS-Dateien. Im Lauf der Zeit werden Sie Images bemerken, die vorab JIT-kompiliert wurden (die Kompilierung von IL zu nativ, die zur Laufzeit erfolgt).

Obwohl mehrere Versionen der .NET- und ASP.NET Core-Images verfügbar sind, haben sie alle mindestens eine Schicht gemeinsam, einschließlich der Basisschicht. Aus diesem Grund ist wenig Speicherplatz erforderlich, um ein Image zu speichern, denn es besteht nur aus dem Delta zwischen dem benutzerdefinierten Image und dem Basis-Image. So können Sie das Image schnell aus der Registrierung abrufen.

Wenn Sie sich die .NET-Image-Repositorys im Docker-Hub ansehen, werden Sie mehrere Imageversionen finden, die klassifiziert oder mit Tags versehen sind. Diese Tags helfen dabei, je nach benötigter Version zu entscheiden, welches Image verwendet werden sollte, so wie in der folgenden Tabelle:

| Bild | Kommentare |
|-------|----------|
| mcr.microsoft.com/dotnet/aspnet:**5.0** | ASP.NET Core mit Optimierungen nur für die Runtime und ASP.NET Core unter Linux und Windows (Mehrfacharchitektur) |
| mcr.microsoft.com/dotnet/sdk:**5.01** | .NET 5 mit enthaltenen SDKs unter Linux und Windows (Mehrfacharchitektur) |

> [!div class="step-by-step"]
> [Zurück](net-container-os-targets.md)
> [Weiter](../architect-microservice-container-applications/index.md)
