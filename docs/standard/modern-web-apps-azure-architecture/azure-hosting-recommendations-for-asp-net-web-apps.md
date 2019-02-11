---
title: Empfehlungen für das Hosting mit Azure für ASP.NET Core-Web-Apps
description: Entwerfen moderner Web-Apps mit ASP.NET Core und Azure | Empfehlungen für das Hosting mit Azure für ASP.NET-Web-Apps
author: ardalis
ms.author: wiwagn
ms.date: 01/30/2019
ms.openlocfilehash: cda4c002c73e2dd0db1b2d5d1fa8bc76903c5c62
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/07/2019
ms.locfileid: "55828383"
---
# <a name="azure-hosting-recommendations-for-aspnet-core-web-apps"></a>Empfehlungen für das Hosting mit Azure für ASP.NET Core-Web-Apps

> „Branchenspezifische Führungskräfte beziehen Anwendungen zunehmend über die Cloud (SaaS) und nicht mehr über ihre IT-Abteilungen. Dabei wird ein Zahlungsmodell genutzt, das an Zeitschriftenabonnements erinnert. Wenn ein Dienst nicht mehr benötigt wird, kann das Abonnement einfach gekündigt werden, ohne dass hierbei Ressourcen verschwendet werden.“  
> _\- Daryl Plummer, Gartner-Analyst_

Windows Azure stellt Unterstützung für sämtliche Anforderungen und die gesamte Architektur Ihrer Anwendung bereit. Ihre Hostinganforderungen können dabei von einfachen statischen Websites bis zu komplexen Anwendungen reichen, die aus zahlreichen Diensten bestehen. Für monolithische Web-Apps und unterstützende Dienste in ASP.NET Core gibt es mehrere bekannte Konfigurationen, die empfohlen werden. Die Empfehlungen in diesem Artikel sind nach der Art der Ressource gruppiert, die gehostet werden soll, z.B. vollständige Anwendungen, individuelle Prozesse oder Daten.

## <a name="web-applications"></a>Webanwendungen

Web-Apps können mit Folgendem gehostet werden:

- App Service-Web-Apps

- Container

- Azure Service Fabric

- Microsoft Azure Virtual Machines

Für die meisten Szenarios werden App Service-Web-Apps empfohlen. Im Fall von Microservicearchitekturen können Sie einen containerbasierten Ansatz oder Service Fabric verwenden. Wenn Sie mehr Kontrolle über die Computer benötigen, auf denen Ihre Anwendung ausgeführt wird, sollten Sie Azure Virtual Machines in Betracht ziehen.

### <a name="app-service-web-apps"></a>App Service-Web-Apps

App Service-Web-Apps ist eine vollständig verwaltete Plattform, die für das Hosten von Webanwendungen optimiert ist. Es handelt sich dabei um ein PaaS-Angebot (Platform-as-a-Service), mit dem Sie sich auf Ihre Geschäftslogik konzentrieren können, während Azure sich um die erforderliche Infrastruktur für das Ausführen und Skalieren der App kümmert. Einige wesentliche Features von App Service-Web-Apps:

- DevOps-Optimierung (Continuous Integration und Continuous Delivery, mehrere Umgebungen, A/B-Tests, Unterstützung der Skripterstellung)

- Globale Skalierung und Hochverfügbarkeit

- Verbindungen zu SaaS-Plattformen und Ihren lokalen Daten

- Sicherheit und Konformität

- Visual Studio-Integration

Für die meisten Web-Apps ist Azure App Service die beste Wahl. Die Bereitstellung und die Verwaltung sind in die Plattform integriert, Websites können zur Bewältigung hoher Datenverkehrsauslastungen schnell skaliert werden, und der integrierte Lastenausgleich sowie der Traffic Manager sorgen für Hochverfügbarkeit. Sie können vorhandene Websites einfach zu Azure App Service mithilfe eines Onlinemigrationstools migrieren, eine Open Source-App aus Web App Gallery verwenden oder eine neue Seite mit einem Framework und mit Tools Ihrer Wahl erstellen. Das WebJobs-Feature vereinfacht die Verarbeitung von Hintergrundaufträgen in Ihrer App Service-Web-App.

### <a name="azure-kubernetes-service"></a>Azure Kubernetes Service

Azure Kubernetes Service (AKS) verwaltet Ihre gehostete Kubernetes-Umgebung. So können Sie sie schnell und einfach Containeranwendungen ohne Kenntnisse in der Containerorchestrierung bereitstellen und verwalten. Dabei entfällt der Aufwand des kontinuierlichen Betriebs und für Wartungen, da Ressourcen nach Bedarf bereitgestellt, upgegradet und skaliert werden, ohne die Anwendungen offline zu schalten.

AKS verringert die Komplexität und den operativen Mehraufwand der Verwaltung eines Kubernetes-Clusters, indem der Großteil der Zuständigkeit dafür an Azure übertragen wird. Als gehosteter Kubernetes-Dienst übernimmt Azure kritische Tasks wie die Sicherheitsüberwachung und die Wartung für Sie. Darüber hinaus zahlen Sie nur für die Agent-Knoten in Ihren Clustern, nicht für die Masterknoten. Als verwalteter Kubernetes-Dienst bietet AKS:

- Automatisierte Kubernetes-Versionsupgrades und -Patches
- Einfache Clusterskalierung
- Selbstheilende gehostete Steuerungsebene (Master)
- Kosteneinsparungen: Zahlen Sie nur für ausgeführte Agentpoolknoten

Da Azure die Knoten im AKS-Cluster verwaltet, müssen Sie keine Aufgaben wie Clusterupgrades mehr manuell ausführen. Da Azure diese wichtigen Wartungsaufgaben übernimmt, stellt AKS keinen direkten Zugriff (z.B. mit SSH) auf den Cluster bereit.

### <a name="azure-service-fabric"></a>Azure Service Fabric

Service Fabric ist eine gute Wahl, wenn Sie eine neue App erstellen oder eine vorhandene App mit dem Ziel neu schreiben, eine Microservicearchitektur zu verwenden. Apps, die in einem freigegebenen Pool von Computern ausgeführt werden, können zu Beginn klein sein, nach einiger Zeit aber eine beachtliche Größe erreichen, wodurch Hunderte oder Tausende Computer benötigt werden. Zustandsbehaftete Dienste erleichtern das konsistente und zuverlässige Speichern des App-Zustands, und Service Fabric verwaltet die Dienstpartitionierung, Skalierung und Verfügbarkeit automatisch für Sie. Service Fabric unterstützt auch die WebAPI mit Open Web Interface for .NET (OWIN) und ASP.NET Core. Im Vergleich zu App Service bietet Service Fabric mehr Kontrolle über bzw. direkten Zugriff auf die zugrunde liegende Infrastruktur. Sie können per Remotezugriff auf Ihre Server zugreifen oder die Startaufgaben des Servers konfigurieren.

### <a name="azure-virtual-machines"></a>Azure Virtual Machines

Wenn Sie über eine Anwendung verfügen, deren Ausführung in App Service oder Service Fabric umfassende Änderungen notwendig machen würde, können Sie sich für Virtual Machines entscheiden, um die Migration zur Cloud zu vereinfachen. Das ordnungsgemäße Konfigurieren, Sichern und Verwalten von Virtual Machines erfordert allerdings deutlich mehr Zeit und IT-Kenntnisse im Vergleich zu Azure App Service und Service Fabric. Wenn Sie Azure Virtual Machines in Betracht ziehen, sollten Sie den ständigen Wartungsaufwand für das Patchen, Aktualisieren und Verwalten der VM-Umgebung beachten. Azure Virtual Machines ist ein IaaS-Angebot (Infrastructure-as-a-Service), während App Service und Service Fabric PaaS-Angebote (Platform-as-a-Service) sind.

#### <a name="feature-comparison"></a>Featurevergleich

| Feature                                                                                    | App Service | Container (AKS) | Service Fabric | Virtueller Computer |
| ------------------------------------------------------------------------------------------ | ----------- | ---------------- | -------------- | --------------- |
| Nahezu sofortige Bereitstellung                                                                    | X           | X                | X              |                 |
| Zentrales Hochskalieren auf größere Computer ohne erneute Bereitstellung                                               | X           | X                | X              |                 |
| Instanzen teilen Inhalte und Konfigurationen – eine erneute Bereitstellung oder Konfiguration wird für die Skalierung nicht benötigt | X           | X                | X              |                 |
| Mehrere Bereitstellungsumgebungen (Produktion, Staging)                                     | X           | X                | X              |                 |
| Automatische Updateverwaltung für Betriebssysteme                                                             | X           | X                |                |                 |
| Nahtloser Wechsel zwischen 32- und 64-Bit-Plattformen                                             | X           | X                |                |                 |
| Bereitstellen von Code mit Git und FTP                                                                  | X           | X                |                | X               |
| Bereitstellen von Code mit WebDeploy                                                                 | X           | X                |                | X               |
| Bereitstellen von Code mit TFS                                                                       | X           | X                | X              | X               |
| Hosten einer Web-/Webdienstebene einer Architektur mit mehreren Ebenen                                    | X           | X                | X              | X               |
| Zugreifen auf Azure-Dienste wie Service Bus, Azure Storage und SQL-Datenbank                              | X           | X                | X              | X               |
| Installieren von benutzerdefinierten MSI                                                                     |             | X                | X              | X               |

## <a name="logical-processes"></a>Logische Prozesse

Individuelle logische Prozesse, die von der übrigen Anwendung entkoppelt werden können, lassen sich „serverlos“ in Azure Functions bereitstellen. Azure Functions ermöglicht Ihnen, Code für ein bestimmtes Problem zu schreiben, und zwar unabhängig von der Anwendung oder Infrastruktur zum Ausführen dieses Codes. Sie können aus einer Vielzahl von Programmiersprachen wie C\#, F\#, Node.js, Python und PHP die produktivste für die jeweilige Aufgabe auswählen. Wie bei den meisten cloudbasierten Lösungen zahlen Sie nur für den Zeitraum, in dem Sie das Angebot nutzen, und Sie können darauf vertrauen, dass Azure Functions je nach Bedarf eine zentrale Hochskalierung vornimmt.

## <a name="data"></a>Daten

Azure bietet ein Vielzahl von Optionen für das Speichern von Daten, sodass Ihre Anwendung den entsprechenden Datenanbieter für die jeweiligen Daten verwenden kann.

Für transaktionale und relationale Daten sind Azure SQL-Datenbanken die beste Option. Eine gute und leistungsfähige Lösung für Daten, auf die überwiegend lesend zugegriffen wird, ist ein Redis-Cache, der von einer Azure SQL-Datenbank unterstützt wird.

Unstrukturierte JSON-Daten können auf verschiedene Weisen gespeichert werden, z.B. als Spalten in einer SQL-Datenbank , Blobs, Tabellen in Azure Storage oder in Cosmos DB. Cosmos DB bietet hierbei die beste Funktionalität für Abfragen und ist die empfohlene Option, wenn Sie mit einer großen Anzahl von JSON-basierten Dokumenten arbeiten, die Abfragen unterstützen müssen.

Für kurzlebige Daten, die im Zusammenhang mit Befehlen und Ereignissen stehen und zur Orchestrierung von Anwendungsverhalten verwendet werden, können Azure Service Bus oder Azure Storage-Warteschlangen verwendet werden. Azure Storage Bus bietet mehr Flexibilität und ist der empfohlene Dienst für nicht triviales Messaging innerhalb von und zwischen Anwendungen.

## <a name="architecture-recommendations"></a>Architekturempfehlungen

Die Anforderungen Ihrer Anwendung sollten die Architektur vorgeben. Es sind viele verschiedene Azure-Dienste verfügbar. Die Auswahl des richtigen Diensts ist eine wichtige Entscheidung. Microsoft bietet einen Katalog von Referenzarchitekturen, um dabei zu helfen, typische Architekturen zu identifizieren, die für allgemeine Szenarios optimiert sind. Sie können eine Referenzarchitektur suchen, die den Anforderungen Ihrer Anwendung genau entspricht oder einen Ausgangspunkt darstellt.

Abbildung 11-2 zeigt ein Beispiel einer Referenzarchitektur. Dieses Diagramm beschreibt eine empfohlene Architektur für eine Website, die für Marketingzwecke optimiert ist und ein Content Management-System von Sitecore verwendet.

![](./media/image11-2.png)

**Abbildung 11-1**. Referenzarchitektur der Marketingwebsite mit Sitecore

**Ressourcen: Empfehlungen für das Hosting mit Azure**

- Azure-Lösungsarchitekturen
  <https://azure.microsoft.com/solutions/architecture/>

- Entwicklerleitfaden für Microsoft Azure
  <https://azure.microsoft.com/campaigns/developer-guide/>

- Web-Apps-Übersicht
  <https://docs.microsoft.com/azure/app-service/app-service-web-overview>

- Azure App Service, Azure Virtual Machines, Service Fabric und Azure Cloud Services im Vergleich
  <https://docs.microsoft.com/azure/app-service-web/choose-web-site-cloud-service-vm>

- Einführung in Azure Kubernetes Service (AKS)
  <https://docs.microsoft.com/azure/aks/intro-kubernetes>

>[!div class="step-by-step"]
>[Vorherige](development-process-for-azure.md)