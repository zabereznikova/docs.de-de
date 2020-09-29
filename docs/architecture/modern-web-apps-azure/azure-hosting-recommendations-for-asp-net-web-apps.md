---
title: Empfehlungen für das Hosting mit Azure für ASP.NET Core-Web-Apps
description: Entwerfen moderner Web-Apps mit ASP.NET Core und Azure | Empfehlungen für das Hosting mit Azure für ASP.NET-Web-Apps
author: ardalis
ms.author: wiwagn
ms.date: 06/06/2019
ms.openlocfilehash: 19626aea07fb26222af575a709b54577ca12589b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91169218"
---
# <a name="azure-hosting-recommendations-for-aspnet-core-web-apps"></a>Empfehlungen für das Hosting mit Azure für ASP.NET Core-Web-Apps

> „Geschäftsbereichsleiter lassen IT-Abteilungen zunehmend außen vor und beziehen Anwendungen über die Cloud (SaaS). Dabei wird ein Zahlungsmodell genutzt, das an Zeitschriftenabonnements erinnert. Wenn ein Dienst nicht mehr benötigt wird, kann das Abonnement einfach gekündigt werden, ohne dass hierbei Ressourcen verschwendet werden.“  
> _\- Daryl Plummer, Gartner-Analyst_

Microsoft Azure stellt Unterstützung für sämtliche Anforderungen und die gesamte Architektur Ihrer Anwendung bereit. Ihre Hostinganforderungen können dabei von einfachen statischen Websites bis zu hochkomplexen Anwendungen reichen, die aus zahlreichen Diensten bestehen. Für monolithische Web-Apps und unterstützende Dienste in ASP.NET Core gibt es mehrere bekannte Konfigurationen, die empfohlen werden. Die Empfehlungen in diesem Artikel sind nach der Art der Ressource gruppiert, die gehostet werden soll, z.B. vollständige Anwendungen, individuelle Prozesse oder Daten.

## <a name="web-applications"></a>Webanwendungen

Web-Apps können mit Folgendem gehostet werden:

- App Service-Web-Apps

- Container (verschiedene Optionen)

- Microsoft Azure Virtual Machines

Für die meisten Szenarien – einschließlich einfacher containerbasierter Apps – bieten sich App Service-Web-Apps an. Im Fall von Microservicearchitekturen können Sie einen containerbasierten Ansatz verwenden. Wenn Sie mehr Kontrolle über die Computer benötigen, auf denen Ihre Anwendung ausgeführt wird, sollten Sie Azure Virtual Machines in Betracht ziehen.

### <a name="app-service-web-apps"></a>App Service-Web-Apps

App Service-Web-Apps ist eine vollständig verwaltete Plattform, die für das Hosten von Webanwendungen optimiert ist. Es handelt sich dabei um ein PaaS-Angebot (Platform-as-a-Service), mit dem Sie sich auf Ihre Geschäftslogik konzentrieren können, während Azure sich um die erforderliche Infrastruktur für das Ausführen und Skalieren der App kümmert. Einige wesentliche Features von App Service-Web-Apps:

- DevOps-Optimierung (Continuous Integration und Continuous Delivery, mehrere Umgebungen, A/B-Tests, Unterstützung der Skripterstellung)

- Globale Skalierung und Hochverfügbarkeit

- Verbindungen zu SaaS-Plattformen und Ihren lokalen Daten

- Sicherheit und Konformität

- Visual Studio-Integration

Für die meisten Web-Apps ist Azure App Service die beste Wahl. Die Bereitstellung und die Verwaltung sind in die Plattform integriert, Websites können zur Bewältigung hoher Datenverkehrsauslastungen schnell skaliert werden, und der integrierte Lastenausgleich sowie der Traffic Manager sorgen für Hochverfügbarkeit. Sie können vorhandene Websites einfach zu Azure App Service mithilfe eines Onlinemigrationstools migrieren, eine Open Source-App aus Web App Gallery verwenden oder eine neue Seite mit einem Framework und mit Tools Ihrer Wahl erstellen. Das WebJobs-Feature vereinfacht die Verarbeitung von Hintergrundaufträgen in Ihrer App Service-Web-App. Wenn Sie über eine vorhandene ASP.NET-Anwendung verfügen, die mit einer lokalen Datenbank lokal gehostet wird, existiert ein klar definierter Migrationspfad zu einer App Service-Web-App mit einer Azure SQL-Datenbank (oder sicherem Zugriff auf Ihren lokalen Datenbankserver, wenn Sie dies bevorzugen).

![Empfohlene Strategie für die Migration lokaler .NET-Apps zu Azure App Service](./media/image1-6.png)

In den meisten Fällen ist der Umstieg von einer lokal gehosteten ASP.NET-App auf eine App Service-Web-App unkompliziert. Für die App selbst sind in der Regel keine oder nur geringfügige Änderungen notwendig, und sie profitiert schnell von den vielen Features, die Azure App Service-Web-Apps bieten.

Azure App Service-Web-Apps sind eine hervorragende Lösung nicht nur für Apps, die nicht für die Cloud optimiert sind, sondern auch für viele einfache monolithische (nicht verteilte) Anwendungen, wie z.B. viele ASP.NET Core-Apps. Bei diesem Ansatz ist die Architektur unkompliziert und einfach zu verstehen und zu verwalten:

![Grundlegende Azure-Architektur](./media/image1-5.png)

Zur Verwaltung einer solchen App ist in der Regel eine geringe Anzahl von Ressourcen in einer einzigen Ressourcengruppe ausreichend. Apps, die nicht aus vielen separaten Prozessen bestehen, sondern als eine einzige Einheit bereitgestellt werden, sind üblicherweise gute Kandidaten für diesen [grundlegenden Architekturansatz](/azure/architecture/reference-architectures/app-service-web-app/basic-web-app). Obwohl die Architektur recht einfach ist, ermöglicht es dieser Ansatz dennoch, die gehostete App sowohl zentral (mehr Ressourcen pro Knoten) als auch horizontal (mehr gehostete Knoten) hochzuskalieren, um einen höheren Bedarf zu erfüllen. Mit der Autoskalierung kann die App so konfiguriert werden, dass die Anzahl der Knoten, auf denen die Apps gehostet wird, automatisch basierend auf dem Bedarf und der durchschnittlichen Last auf den Knoten angepasst wird.

### <a name="app-service-web-apps-for-containers"></a>App Service-Web-Apps für Container

Zusätzlich zur direkten Unterstützung für das Hosten von Web-Apps können [App Service-Web-Apps für Container](https://azure.microsoft.com/services/app-service/containers/) zum Ausführen von containerbasierten Anwendungen unter Windows und Linux verwendet werden. Mit diesem Dienst können Sie ganz einfach containerbasierte Anwendungen bereitstellen und ausführen, die sich mit Ihrem Business skalieren lassen. Die Apps weisen alle oben aufgeführten Features von App Service-Web-Apps auf. Darüber hinaus unterstützen Web-App für Container optimierte CI/CD-Funktionen mit Docker Hub, Azure Container Registry und GitHub. Sie können Azure DevOps verwenden, um Build- und Bereitstellungspipelines zu definieren, die Änderungen in einer Registrierung veröffentlichen. Diese Änderungen können dann in einer Stagingumgebung getestet und über Bereitstellungsslots automatisch in der Produktion bereitgestellt werden – so sind Upgrades ohne jede Ausfallzeit möglich. Ein Rollback zu früheren Versionen lässt sich ebenso einfach ausführen.

Es gibt einige Szenarien, in denen Web-Apps für Container die sinnvollste Lösung sind. Wenn Sie über Apps verfügen, die Sie in Container packen können – Windows- oder Linux-Container –, können Sie diese ganz einfach mithilfe dieses Toolsets hosten. Veröffentlichen Sie einfach Ihren Container, und konfigurieren Sie dann Web-Apps für Container so, dass die neueste Version des Images per Pull aus der Registrierung Ihrer Wahl abgerufen wird. Es handelt sich hier um ein „Lift and Shift“-Verfahren zur Migration von klassischen App-Hostingmodellen zu einem cloudoptimierten Modell.

![Migrieren von lokalen .NET-Anwendungen in Containern zu Azure Web-Apps für Container](./media/image1-8.png)

Dieser Ansatz funktioniert gut, wenn Ihr Entwicklungsteam zu einem containerbasierten Entwicklungsprozess wechseln kann. Die „innere Schleife“ bei der Entwicklung von Apps mit Containern umfasst auch die Erstellung der App mit Containern. Änderungen, die am Code sowie an der Containerkonfiguration vorgenommen werden, werden in die Quellcodeverwaltung gepusht, und ein automatisierter Buildprozess ist dafür zuständig, neue Containerimages in einer Registrierung wie Docker Hub oder Azure Container Registry zu veröffentlichen. Diese Images werden dann als Basis für die weitere Entwicklung sowie zum Verlagern von Bereitstellungen in die Produktion verwendet, wie im folgenden Diagramm gezeigt:

![Vollständiger Docker-DevOps-Lebenszyklusworkflow](./media/image1-7.png)

Die Entwicklung mit Containern bietet viele Vorteile, insbesondere dann, wenn in der Produktion Container verwendet werden. Zum Hosten der App in jeder Umgebung, in der sie ausgeführt wird – vom lokalen Entwicklungscomputer über Build- und Testsysteme bis hin zur Produktion –, wird ein und dieselbe Containerkonfiguration verwendet. Damit sinkt das Risiko von Fehlern, die aus Unterschieden in Computerkonfigurationen oder Softwareversionen resultieren. Entwickler können die Tools verwenden, mit denen sie am produktivsten arbeiten – dies umfasst auch das Betriebssystem –, da Container unter jedem Betriebssystem ausgeführt werden können. In einigen Fällen ist die Ausführung von verteilten Anwendungen mit vielen Containern auf einem einzigen Entwicklungscomputer sehr ressourcenintensiv. In diesem Szenario kann es sinnvoll sein, ein Upgrade durchzuführen und Kubernetes und Azure Dev Spaces einzusetzen. Dies wird im nächsten Abschnitt erläutert.

Da Teile größerer Anwendungen in kleinere, unabhängige *Microservices* aufgeteilt werden, können zusätzliche Entwurfsmuster verwendet werden, um das App-Verhalten zu verbessern. Anstatt direkt mit einzelnen Diensten zu arbeiten, kann ein *API-Gateway* den Zugriff vereinfachen und den Client vom zugehörigen Back-End entkoppeln. Separate Dienst-Back-Ends für verschiedene Front-Ends ermöglichen es Diensten auch, sich in Übereinstimmung mit den jeweiligen Consumern zu entwickeln. Auf gemeinsame Dienste kann über einen separaten *Sidecarcontainer* zugegriffen werden, der über das *Botschafter*-Muster gemeinsame Bibliotheken für die Clientkonnektivität enthalten kann.

![Beispielarchitektur für Microservices mit verschiedenen allgemeinen Entwurfsmustern.](./media/image1-10.png)

[Erfahren Sie mehr über Entwurfsmuster für den Aufbau microservicebasierter Systeme](/azure/architecture/microservices/design/patterns).

### <a name="azure-kubernetes-service"></a>Azure Kubernetes Service

Azure Kubernetes Service (AKS) verwaltet Ihre gehostete Kubernetes-Umgebung. So können Sie sie schnell und einfach Containeranwendungen ohne Kenntnisse in der Containerorchestrierung bereitstellen und verwalten. Dabei entfällt der Aufwand des kontinuierlichen Betriebs und für Wartungen, da Ressourcen nach Bedarf bereitgestellt, upgegradet und skaliert werden, ohne die Anwendungen offline zu schalten.

AKS verringert die Komplexität und den operativen Mehraufwand der Verwaltung eines Kubernetes-Clusters, indem der Großteil der Zuständigkeit dafür an Azure übertragen wird. Als gehosteter Kubernetes-Dienst übernimmt Azure kritische Tasks wie die Sicherheitsüberwachung und die Wartung für Sie. Darüber hinaus zahlen Sie nur für die Agent-Knoten in Ihren Clustern, nicht für die Masterknoten. Als verwalteter Kubernetes-Dienst bietet AKS:

- Automatisierte Kubernetes-Versionsupgrades und -Patches
- Einfache Clusterskalierung
- Selbstheilende gehostete Steuerungsebene (Master)
- Kosteneinsparungen: Zahlen Sie nur für ausgeführte Agentpoolknoten

Da die Verwaltung der Knoten im AKS-Cluster durch Azure erfolgt, müssen Sie viele Aufgaben, z.B. Clusterupgrades, nicht mehr manuell ausführen. Da Azure diese wichtigen Wartungsaufgaben übernimmt, stellt AKS keinen direkten Zugriff (z.B. mit SSH) auf den Cluster bereit.

Teams, die AKS nutzen, können auch von Azure Dev Spaces profitieren. Azure Dev Spaces ermöglicht es Teams, direkt mit der gesamten in AKS ausgeführten Microservicearchitektur oder Anwendung zu arbeiten – so können sich die Teams ganz auf die Entwicklung und schnelle Iteration ihrer Microserviceanwendung konzentrieren. Azure Dev Spaces bietet auch die Möglichkeit, Teile einer Microservicearchitektur unabhängig und isoliert zu aktualisieren, ohne dass dies sich auf den Rest des AKS-Clusters oder andere Entwickler auswirkt.

![Beispiel für Azure Dev Spaces-Workflow](./media/image1-9.gif)

Azure Dev Spaces bietet folgende Vorteile:

- Einrichtungszeit und Ressourcenanforderungen für lokale Computer werden minimiert.
- Teams können Iterationen schneller durchführen.
- Teams benötigen eine geringere Anzahl von Integrationsumgebungen.
- Die Notwendigkeit, bestimmte Dienste in verteilten Systemen zu simulieren, entfällt.

[Weitere Informationen zu Azure Dev Spaces](/azure/dev-spaces/about)

### <a name="azure-virtual-machines"></a>Azure Virtual Machines

Wenn Sie über eine Anwendung verfügen, deren Ausführung in App Service umfassende Änderungen notwendig machen würde, können Sie sich für Virtual Machines entscheiden, um die Migration zur Cloud zu vereinfachen. Das ordnungsgemäße Konfigurieren, Sichern und Verwalten von Virtual Machines erfordert allerdings deutlich mehr Zeit und IT-Kenntnisse im Vergleich zu Azure App Service. Wenn Sie Azure Virtual Machines in Betracht ziehen, sollten Sie den ständigen Wartungsaufwand für das Patchen, Aktualisieren und Verwalten der VM-Umgebung beachten. Azure Virtual Machines ist ein IaaS-Angebot (Infrastructure-as-a-Service), während App Service ein PaaS-Angebot (Platform-as-a-Service) ist. Sie sollten auch überlegen, ob die Bereitstellung Ihrer App als Windows-Container in „Web-App für Container“ eine geeignete Option für Ihr Szenario wäre.

## <a name="logical-processes"></a>Logische Prozesse

Individuelle logische Prozesse, die von der übrigen Anwendung entkoppelt werden können, lassen sich „serverlos“ in Azure Functions bereitstellen. Azure Functions ermöglicht Ihnen, Code für ein bestimmtes Problem zu schreiben, und zwar unabhängig von der Anwendung oder Infrastruktur zum Ausführen dieses Codes. Sie können aus einer Vielzahl von Programmiersprachen wie C\#, F\#, Node.js, Python und PHP die produktivste für die jeweilige Aufgabe auswählen. Wie bei den meisten cloudbasierten Lösungen zahlen Sie nur für den Zeitraum, in dem Sie das Angebot nutzen, und Sie können darauf vertrauen, dass Azure Functions je nach Bedarf eine zentrale Hochskalierung vornimmt.

## <a name="data"></a>Data

Azure bietet ein Vielzahl von Optionen für das Speichern von Daten, sodass Ihre Anwendung den entsprechenden Datenanbieter für die jeweiligen Daten verwenden kann.

Für transaktionale und relationale Daten sind Azure SQL-Datenbanken die beste Option. Eine gute und leistungsfähige Lösung für Daten, auf die überwiegend lesend zugegriffen wird, ist ein Redis-Cache, der von einer Azure SQL-Datenbank unterstützt wird.

Unstrukturierte JSON-Daten können auf verschiedene Weisen gespeichert werden (z. B. als Spalten in einer SQL-Datenbank, Blobs, Tabellen in Azure Storage oder in Azure Cosmos DB). Azure Cosmos DB bietet hierbei die beste Funktionalität für Abfragen und ist die empfohlene Option, wenn Sie mit einer großen Anzahl von JSON-basierten Dokumenten arbeiten, die Abfragen unterstützen müssen.

Für kurzlebige Daten, die im Zusammenhang mit Befehlen und Ereignissen stehen und zur Orchestrierung von Anwendungsverhalten verwendet werden, können Azure Service Bus oder Azure Storage-Warteschlangen verwendet werden. Azure Service Bus bietet mehr Flexibilität und ist der empfohlene Dienst für nicht triviales Messaging innerhalb von und zwischen Anwendungen.

## <a name="architecture-recommendations"></a>Architekturempfehlungen

Die Anforderungen Ihrer Anwendung sollten die Architektur vorgeben. Es sind viele verschiedene Azure-Dienste verfügbar. Die Auswahl des richtigen Diensts ist eine wichtige Entscheidung. Microsoft bietet einen Katalog von Referenzarchitekturen, um dabei zu helfen, typische Architekturen zu identifizieren, die für allgemeine Szenarios optimiert sind. Sie können eine Referenzarchitektur suchen, die den Anforderungen Ihrer Anwendung genau entspricht oder einen Ausgangspunkt darstellt.

Abbildung 11-1 zeigt ein Beispiel einer Referenzarchitektur. Dieses Diagramm beschreibt eine empfohlene Architektur für eine Website, die für Marketingzwecke optimiert ist und ein Content Management-System von Sitecore verwendet.

![Abbildung 11–1](./media/image11-2.png)

**Abbildung 11-1**. Referenzarchitektur der Marketingwebsite mit Sitecore

**Ressourcen: Empfehlungen für das Hosting mit Azure**

- Azure-Lösungsarchitekturen\
  <https://azure.microsoft.com/solutions/architecture/>

- Azure-Architektur für einfache Webanwendungen\
  <https://docs.microsoft.com/azure/architecture/reference-architectures/app-service-web-app/basic-web-app>

- Entwurfsmuster für Microservices\
  <https://docs.microsoft.com/azure/architecture/microservices/design/patterns>

- Entwicklerleitfaden für Microsoft Azure\
  <https://azure.microsoft.com/campaigns/developer-guide/>

- Web-Apps-Übersicht\
  <https://docs.microsoft.com/azure/app-service/app-service-web-overview>

- Web-App für Container\
  <https://azure.microsoft.com/services/app-service/containers/>

- Einführung in Azure Kubernetes Service (AKS)\
  <https://docs.microsoft.com/azure/aks/intro-kubernetes>

>[!div class="step-by-step"]
>[Zurück](development-process-for-azure.md)
