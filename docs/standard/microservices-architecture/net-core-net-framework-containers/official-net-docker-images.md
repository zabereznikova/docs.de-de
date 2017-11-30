---
title: Offizielle .NET Docker-images
description: ".NET Microservices Architektur für Datenvolumes .NET-Anwendungen | Offizielle .NET Docker-images"
keywords: Docker, Microservices, ASP.NET, Container
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 6f14bd0cf55a552f3881d755ebe7389f000975d8
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2017
---
# <a name="official-net-docker-images"></a>Offizielle .NET Docker-images

Die offizielle .NET Docker-Images sind Docker-Images erstellt und optimiert, die von Microsoft. Sie sind in den Microsoft-Repositorys auf öffentlich verfügbare [Docker Hub](https://hub.docker.com/u/microsoft/). Jedes Repository kann mehrere Abbilder, je nach .NET Versionen, und das Betriebssystem und die Versionen (Linux Debian, Alpine Linux, Windows Nano Server, Windows Server Core, usw.) enthalten.

Vision von Microsoft .NET Repositorys besteht darin, eine präzise und konzentriert sich Repositorys haben, wobei ein Repository darstellt, ein bestimmtes Szenario oder eine arbeitsauslastung. Für die Instanz, die [Microsoft/Aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) Bilder sollte verwendet werden, wenn mithilfe von ASP.NET Core auf Docker, da dies der Fall ist der Container bereitgestellt werden diese Bilder ASP.NET Core zusätzliche Optimierungen schneller gestartet werden kann.

Andererseits, beziehen sich die .NET Core-Bilder (Microsoft/Dotnet) Konsolen-apps, die basierend auf .NET Core. Beispielsweise sollten Batchprozessen Azure WebJobs und Weitere Szenarien Konsole .NET Core verwenden. Diese Images enthalten keine ASP.NET Core-Stapel, was zu kleineren Container-Image.

Die meisten Image-Repositorys bieten umfassende kennzeichnen, können Sie nicht nur eine spezifische Framework-Version auszuwählen, sondern auch auf einem Betriebssystem (Linux-Distribution oder Windows-Version).

Weitere Informationen zu den offiziellen .NET Docker-Images, die von Microsoft bereitgestellt werden kann, finden Sie unter der [.NET Docker Images Zusammenfassung](https://aka.ms/dotnetdockerimages).

## <a name="net-core-and-docker-image-optimizations-for-development-versus-production"></a>.NET Core und Docker Bild Optimierungen für die Entwicklung und Produktion

Beim Erstellen von Docker-Images für Entwickler, konzentriert sich Microsoft die folgenden Hauptszenarien:

-   Bildern, mit der *entwickeln* und .NET Core-apps erstellen.

-   Bildern, mit der *ausführen* .NET Core-apps.

Warum mehrere Abbilder? Beim Entwickeln, erstellen und Ausführen von Sammelartikeleinheit, müssen Sie in der Regel unterschiedliche Prioritäten. Indem Sie verschiedene Bilder für diese separaten Vorgänge angeben, hilft Microsoft, der separate Prozesse entwickeln, erstellen und Bereitstellen von apps zu optimieren.

### <a name="during-development-and-build"></a>Während der Entwicklung und build

Während der Entwicklung ist wichtig ist wie schnell Sie Änderungen, und die Fähigkeit zum Debuggen der Änderungen durchlaufen können. Die Größe des Bilds ist nicht so wichtig wie die Möglichkeit, Änderungen am Code vornehmen und schnell die Änderungen anzuzeigen. Einige Tools und "Build-Agent-Container", dient die Entwicklung von ASP.NET Core-Image (Microsoft/Aspnetcore-Build) während der Entwicklung und build-Prozesses. Wenn Sie in einem Docker-Container zu erstellen, sind die wichtigsten Aspekte Elemente, die benötigt werden, um die app zu kompilieren. Dies schließt der Compiler und alle anderen Abhängigkeiten .NET sowie Web Development Abhängigkeiten wie Npm, Gulp und Bower.

Warum ist diese Art von buildabbild wichtig? Dieses Bild bereitgestellt nicht in der produktionsumgebung. Stattdessen wird ein Bild, das Sie verwenden, um den Inhalt, den platzieren Sie Sie, in einer Produktions-Images erstellen. Dieses Image würde in Ihrer Umgebung mit continuous Integration (CI) oder Buildumgebung verwendet werden. Für die Instanz, statt Sie manuell sämtliche anwendungsabhängigkeiten direkt auf einen Build-Agent installieren hosten (z. B. eine VM), der Build-Agent ein .NET Core-Image Build instanziieren würde, mit den Abhängigkeiten, die zum Erstellen der Anwendung erforderlich sind. Der Build-Agent muss nur wissen, wie dieses Docker-Image ausgeführt wird. Dies vereinfacht die CI-Umgebung und erleichtert die wesentlich besser vorhersagbar.

### <a name="in-production"></a>In der Produktion

In der Produktion wichtig ist wie schnell Sie bereitstellen, und starten die Container, basierend auf einer Produktion .NET Core-Image. Aus diesem Grund, das nur das Laufzeitmodul Image basierend auf [Microsoft/Aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) ist klein, damit sie schnell über das Netzwerk aus der Docker-Registrierung, die Docker-Hosts übertragen kann. Die Inhalte sind ausgeführt wird, aktivieren die schnellste Zeit gestartet werden, den Container für die Verarbeitung der Ergebnisse. In das Docker-Modell besteht keine Notwendigkeit für die Kompilierung von C\# code, der als dort ist beim Dotnet Build ausführen Dotnet veröffentlichen, wenn verwenden oder den Container erstellen.

Diese optimierten Images legen Sie nur die Binärdateien und andere Inhalte, die zum Ausführen der Anwendung erforderlich sind. Veröffentlichen Sie der Inhalt von Dotnet erstellt z. B. kompilierte .NET Binärdateien, Bilder, js und CSS-Dateien enthält. Im Laufe der Zeit werden Bilder angezeigt, die JIT-Pakete enthalten.

Obwohl mehrere Versionen der Bilder aus .NET Core und ASP.NET Core verfügbar sind, verwenden sie alle eine oder mehrere Ebenen, einschließlich der grundlegenden Ebene. Aus diesem Grund ist die Menge an Speicherplatz erforderlich, um ein Bild speichern kleine; Es besteht nur das Delta zwischen des benutzerdefinierten Abbilds und die Basis-Image. Das Ergebnis ist, dass es schnell das Image per Pull aus der Registrierung abgerufen werden.

Wenn Sie den .NET Image Repositorys auf Docker Hub durchsuchen, finden Sie mehrere Bildversionen klassifiziert oder mit Tags markiert. Diese Tags helfen um zu entscheiden, welche Sicherung, je nach Version verwenden, die Sie, wie in der folgenden Tabelle aufgeführt benötigen:

-   Microsoft /**Aspnetcore:2.0**

        ASP.NET Core, with runtime only and ASP.NET Core optimizations, on Linux and Windows (multi-arch)

-   Microsoft /**Aspnetcore-Build: 2.0**

        ASP.NET Core, with SDKs included, on Linux and Windows (multi-arch)


>[!div class="step-by-step"]
[Vorherigen] (Net-Container-os-targets.md) [weiter] (.. /Architect-microservice-Container-Applications/Index.MD)
