---
title: "Beim Auswählen von .NET Framework für Docker-Containern"
description: ".NET Microservices Architektur für Datenvolumes .NET-Anwendungen | Beim Auswählen von .NET Framework für Docker-Containern"
keywords: Docker, Microservices, ASP.NET, Container
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 1bf1f055f040e7f3dc575b7a04140ebf0c599f98
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2017
---
# <a name="when-to-choose-net-framework-for-docker-containers"></a>Beim Auswählen von .NET Framework für Docker-Containern

.NET Core bedeutende Vorteile für neue Anwendungen und Anwendungsmuster bietet, ist .NET Framework weiterhin eine gute Wahl für viele vorhandene Szenarien.

## <a name="migrating-existing-applications-directly-to-a-windows-server-container"></a>Migrieren von vorhandenen Anwendungen direkt zu einem Windows Server-container

Möglicherweise möchten die Docker-Containern zu verwenden, nur zur Vereinfachung der Bereitstellung, auch wenn Sie keine Microservices erstellt werden. Beispielsweise vielleicht Sie möchten den DevOps-Workflow mit Docker zu verbessern – Container bieten eine bessere Leistung isolierten testumgebungen und kann auch entfallen Bereitstellungsproblemen durch fehlende Abhängigkeiten verursacht werden, wenn Sie in einer produktionsumgebung verschieben. Auch wenn Sie eine monolithische Anwendung bereitstellen möchten, ist es in solchen Fällen sinnvoll Docker und Windows-Container für den aktuellen .NET Framework-Anwendungen verwendet.

In den meisten Fällen für dieses Szenario müssen Sie nicht Ihre vorhandenen Anwendungen zu .NET Core zu migrieren. Sie können Docker-Containern, die herkömmliche .NET Framework enthalten. Allerdings ist eine empfohlene Vorgehensweise .NET Core verwenden, wie Sie eine vorhandene Anwendung wie dem Schreiben eines neuen Diensts in ASP.NET Core erweitern.

## <a name="using-third-party-net-libraries-or-nuget-packages-not-available-for-net-core"></a>Mithilfe von .NET Bibliotheken von Drittanbietern oder NuGet-Pakete nicht verfügbar für .NET Core

Drittanbieter-Bibliotheken sind schnell Übernahme der [.NET Standard](https://docs.microsoft.com/dotnet/standard/net-standard), wodurch Code für alle .NET-Konfigurationen, einschließlich .NET Core freigegeben. .NET Version 2.0 Standard-Bibliothek und darüber hinaus die API-Oberfläche Kompatibilität über verschiedene Frameworks geworden ist wesentlich umfangreicher und in .NET Core 2.0 Anwendungen können auch direkt verweisen auf vorhandene .NET Framework-Bibliotheken (finden Sie unter  [ /Compat Shim](https://github.com/dotnet/standard/blob/master/docs/faq.md#how-does-net-standard-versioning-work)).

Allerdings auch bei diesem außergewöhnlichen Progression seit .NET Standard 2.0 und .NET Core 2.0 möglicherweise Fälle, bei denen bestimmte NuGet-Pakete zum Ausführen von Windows und .NET Core möglicherweise nicht unterstützt. Wenn diese Pakete für die Anwendung von entscheidender Bedeutung sind, müssen Sie .NET Framework auf Windows-Container zu verwenden.

## <a name="usingnet-technologies-not-available-for-net-core"></a>Nicht verfügbar für .NET Core frameworkneutrale-Technologien 

Einige .NET Framework-Technologien sind nicht in der aktuellen Version von .NET Core (Version 2.0 Verfassung dieses Dokuments) verfügbar. Einige von ihnen stehen dann in späteren Versionen von .NET Core (.NET Core 2.x), aber andere gelten nicht für die neue Anwendung Muster auf die .NET Core und möglicherweise nie zur Verfügung steht.

Die folgende Liste enthält die meisten der Technologien, die in .NET Core 2.0 nicht verfügbar sind:

-   ASP.NET Web Forms. Diese Technologie ist nur verfügbar, auf .NET Framework. Eine Integration von ASP.NET Web Forms in .NET Core ist zurzeit nicht geplant.

-   WCF-Dienste. Selbst wenn eine [WCF-Clientbibliothek](https://github.com/dotnet/wcf) für die Nutzung von WCF-Dienste von .NET Core verfügbar ist. Seit Mitte 2017 ist die WCF-Implementierung nur für .NET Framework verfügbar. Dieses Szenario kann für zukünftige Versionen von .NET Core als angesehen werden.

-   Workflow-bezogene Dienste. Windows Workflow Foundation (WF), Workflowdienste (WCF und WF in einem einzigen Dienst) und WCF Data Services (früher bekannt als ADO.NET Data Services) sind nur in .NET Framework verfügbar. Es gibt derzeit keine Pläne, die sie in der .NET Core zu bringen.

Zusätzlich zu den Technologien aufgeführt, in den offiziellen [Roadmap für die .NET Core](https://github.com/aspnet/Home/wiki/Roadmap), andere Funktionen möglicherweise zu .NET Core portiert werden. Betrachten Sie eine vollständige Liste der Elemente, die als [Port und Kern](https://github.com/dotnet/corefx/issues?q=is%3Aopen+is%3Aissue+label%3Aport-to-core) auf CoreFX GitHub-Website. Beachten Sie, dass diese Liste keine Verpflichtung von Microsoft, schalten Sie diese Komponenten zu .NET Core darstellt, die Elemente einfach Anforderungen aus der Community zu erfassen. Wenn Sie keines der oben aufgelisteten Komponenten interessieren, sollten Sie die Teilnahme an der Diskussionen auf GitHub, damit Ihre Stimme gehört werden kann. Wenn Ihrer Ansicht nach noch etwas fehlt, [eröffnen Sie im CoreFX Repository ein neues „Issue“](https://github.com/dotnet/corefx/issues/new).

## <a name="using-a-platform-or-api-that-does-not-support-net-core"></a>Verwenden eine Plattform oder der API, die .NET Core nicht unterstützt

Einige Microsoft oder Drittanbieter-Plattformen unterstützt .NET Core nicht. Einige Azure-Dienste bieten z. B. eine SDK, die noch nicht für die Verwendung auf .NET Core verfügbar ist. Dies ist temporär, da alle Azure-Dienste schließlich .NET Core verwendet werden. Z. B. die [Azure DocumentDB-SDK für .NET Core](https://www.nuget.org/packages/Microsoft.Azure.DocumentDB.Core/1.2.1) als Vorschau auf 16 November 2016 freigegeben wurde, aber es ist jetzt allgemein verfügbar (GA) als eine stabile Version.

Wenn jeder Plattform oder der Dienst in Azure weiterhin .NET Core mit der Client-API nicht unterstützt, können Sie in der Zwischenzeit können die entsprechende REST-API aus dem Azure-Dienst oder Client-SDK auf .NET Framework verwenden.

### <a name="additional-resources"></a>Zusätzliche Ressourcen

-   **Handbuch für die .NET Core**
    [*https://docs.microsoft.com/dotnet/core/index*](https://docs.microsoft.com/dotnet/core/index)

-   **Portieren von .NET Framework zu .NET Core**
    [*https://docs.microsoft.com/dotnet/core/porting/index*](https://docs.microsoft.com/dotnet/core/porting/index)

-   **.NET Framework auf Docker Handbuch**
    [*https://docs.microsoft.com/dotnet/framework/docker/*](https://docs.microsoft.com/dotnet/framework/docker/)

-   **Übersicht über die Komponenten von .NET**
    [*https://docs.microsoft.com/dotnet/standard/components*](https://docs.microsoft.com/dotnet/standard/components)




>[!div class="step-by-step"]
[Vorherigen] (Net-Core-Container-scenarios.md) [weiter] (Container-Framework-Choice-factors.md)
