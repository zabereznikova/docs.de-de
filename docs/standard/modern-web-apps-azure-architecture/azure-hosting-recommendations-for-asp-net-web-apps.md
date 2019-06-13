---
title: Empfehlungen für das Hosting mit Azure für ASP.NET Core-Web-Apps
description: Entwerfen moderner Web-Apps mit ASP.NET Core und Azure | Empfehlungen für das Hosting mit Azure für ASP.NET-Web-Apps
author: ardalis
ms.author: wiwagn
ms.date: 06/06/2019
ms.openlocfilehash: 7cfb9ada4f963aa392a41cfb9f1b2df22f542d41
ms.sourcegitcommit: 904b98d8d706f0e2d5ceaa00ce17ffbd92adfb88
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/07/2019
ms.locfileid: "66758656"
---
# <a name="azure-hosting-recommendations-for-aspnet-core-web-apps"></a>Empfehlungen für das Hosting mit Azure für ASP.NET Core-Web-Apps

> "Line-of-Business-Führungskräfte werden überall IT-Abteilungen zum Abrufen von Anwendungen aus der Cloud (auch bekannt als SaaS) umgehen und bezahlen dafür, wie sie magazine-Abonnements. Wenn ein Dienst nicht mehr benötigt wird, kann das Abonnement einfach gekündigt werden, ohne dass hierbei Ressourcen verschwendet werden.“  
> _\- Daryl Plummer, Gartner-Analyst_

Was auch immer Ihre Anwendung die Anforderungen und Architektur, Microsoft Azure stellt Unterstützung für. Ihrer hostinganforderungen können so einfach wie eine statische Website oder eine anspruchsvolle Anwendung, die Dutzende von Diensten besteht sein. Für monolithische Web-Apps und unterstützende Dienste in ASP.NET Core gibt es mehrere bekannte Konfigurationen, die empfohlen werden. Die Empfehlungen in diesem Artikel sind nach der Art der Ressource gruppiert, die gehostet werden soll, z.B. vollständige Anwendungen, individuelle Prozesse oder Daten.

## <a name="web-applications"></a>Webanwendungen

Web-Apps können mit Folgendem gehostet werden:

- App Service-Web-Apps

- Container (verschiedene Optionen)

- Microsoft Azure Virtual Machines

App Service-Web-Apps ist die empfohlene Vorgehensweise für die meisten Szenarien, einschließlich der einfachen Containern basierende apps. Im Fall von Microservicearchitekturen können Sie einen containerbasierten Ansatz verwenden. Wenn Sie mehr Kontrolle über die Computer benötigen, auf denen Ihre Anwendung ausgeführt wird, sollten Sie Azure Virtual Machines in Betracht ziehen.

### <a name="app-service-web-apps"></a>App Service-Web-Apps

App Service-Web-Apps ist eine vollständig verwaltete Plattform, die für das Hosten von Webanwendungen optimiert ist. Es handelt sich dabei um ein PaaS-Angebot (Platform-as-a-Service), mit dem Sie sich auf Ihre Geschäftslogik konzentrieren können, während Azure sich um die erforderliche Infrastruktur für das Ausführen und Skalieren der App kümmert. Einige wesentliche Features von App Service-Web-Apps:

- DevOps-Optimierung (Continuous Integration und Continuous Delivery, mehrere Umgebungen, A/B-Tests, Unterstützung der Skripterstellung)

- Globale Skalierung und Hochverfügbarkeit

- Verbindungen zu SaaS-Plattformen und Ihren lokalen Daten

- Sicherheit und Konformität

- Visual Studio-Integration

Für die meisten Web-Apps ist Azure App Service die beste Wahl. Die Bereitstellung und die Verwaltung sind in die Plattform integriert, Websites können zur Bewältigung hoher Datenverkehrsauslastungen schnell skaliert werden, und der integrierte Lastenausgleich sowie der Traffic Manager sorgen für Hochverfügbarkeit. Sie können vorhandene Websites einfach zu Azure App Service mithilfe eines Onlinemigrationstools migrieren, eine Open Source-App aus Web App Gallery verwenden oder eine neue Seite mit einem Framework und mit Tools Ihrer Wahl erstellen. Das WebJobs-Feature vereinfacht die Verarbeitung von Hintergrundaufträgen in Ihrer App Service-Web-App. Wenn Sie haben eine vorhandene ASP.NET-Anwendung auf lokal gehostete mithilfe einer lokalen Datenbank, gibt es ein klaren Weg zum Migrieren von der app zu einer App Service-Web-App mit einer Azure SQL-Datenbank (oder einen sicheren Zugriff auf Ihren lokalen Datenbankserver, wenn Sie dies bevorzugen).

![Empfohlene Migrationsstrategie für lokale .NET apps in Azure App Service](./media/image1-6.png)

Beim Verschieben von einem lokal gehosteten ASP.NET-App auf einer App Service-Web-App in den meisten Fällen ist ein unkomplizierter Prozess. Nur wenig oder gar keinen Änderungen der app selbst erforderlich sein sollte, und sie können schnell beginnen, die vielen Features nutzen, die Azure App Service-Web-Apps bieten.

Zusätzlich zu den apps, die nicht für die Cloud optimiert sind, sind die Azure App Service-Web-Apps eine ausgezeichnete Lösung für viele einfache monolithische (nicht verteilten) Anwendungen, wie viele ASP.NET Core-apps. Bei diesem Ansatz ist die Architektur, basic und einfach zu verstehen und zu verwalten:

![Grundlegende Azure-Architektur](./media/image1-5.png)

Eine kleine Anzahl von Ressourcen in einer einzigen Ressourcengruppe ist in der Regel ausreichend, um eine solche Anwendung zu verwalten. Apps, die in der Regel als einzelne Einheit bereitgestellt werden, anstatt diese apps, die viele separate Prozesse bestehen eignen sich gut für diesen [grundlegende Architekturansatz](https://docs.microsoft.com/azure/architecture/reference-architectures/app-service-web-app/basic-web-app). Dieser Ansatz ermöglicht aber architektonisch einfach weiterhin die gehostete app zu beiden (Weitere Ressourcen pro Knoten) skalieren (mehr gehostete Knoten) kein Anstieg bei Bedarf zu erfüllen. Mit der automatischen Skalierung kann die app konfiguriert werden, um die Anzahl von Knoten zum Hosten der app, die basierend auf der Nachfrage und durchschnittliche Last für die Knoten automatisch angepasst.

### <a name="app-service-web-apps-for-containers"></a>App Service-Web-Apps für Container

Neben der Unterstützung für das Hosten von Web-apps direkt [App Service-Web-Apps für Container](https://azure.microsoft.com/services/app-service/containers/) können zum Ausführen von Anwendungen in Container unter Windows und Linux verwendet werden. Über diesen Dienst können Sie ganz einfach bereitstellen und Ausführen von Anwendungen in Containern, die mit Ihrem Geschäft skaliert werden können. Die apps verfügen über alle Funktionen von App Service Web Apps, die oben aufgeführten. Darüber hinaus optimiert, Web-Apps für die Unterstützung von Containern CI/CD mit Docker-Hub, Azure Container Registry und GitHub. Sie können Azure DevOps verwenden, um Build- und bereitstellungspipelines zu definieren, die Änderungen an einer Registrierung zu veröffentlichen. Diese Änderungen können dann in einer Stagingumgebung getestet und automatisch bereitgestellt, in der Produktion mithilfe von bereitstellungsslots, Upgrades ohne Ausfallzeiten ermöglicht werden. Rollback zu früheren Versionen kann ebenso einfach durchgeführt werden.

Es gibt einige Szenarien, in dem Web-Apps für Container am sinnvollsten sind. Wenn Sie vorhandene apps, die Sie containerize können, in Windows oder Linux-Container verfügen, können Sie diese ganz einfach mit diesem Toolset hosten. Veröffentlichen Sie einfach Ihren Container ein, und konfigurieren Sie Web-Apps für Container, um die neueste Version des Images aus der Registrierung Ihrer Wahl abrufen. Dies ist ein "Lift and Shift"-Ansatz zum Migrieren von klassischen app zum Hosten der Modelle, um ein Modell Cloud optimiert.

![Migrieren Sie Container lokal .NET-Anwendung zum Azure-Web-Apps für Container](./media/image1-8.png)

Dieser Ansatz funktioniert auch gut, wenn Ihr Entwicklungsteam an einen Prozess containerbasierte Entwicklung verschieben kann. Die "innere Schleife" der Entwicklung von apps mit Containern umfasst das Erstellen der app mit Containern. Änderungen an den Code auch hinsichtlich der Konfiguration des Containers werden in die quellcodeverwaltung verschoben, und ein automatisierter Build ist verantwortlich für die Veröffentlichung von neuen Container-Images in einer Registrierung wie Docker Hub oder Azure Container Registry. Diese Abbilder werden dann als Grundlage für die weitere Entwicklung sowie für Bereitstellungen für die Produktion verwendet wie im folgenden Diagramm dargestellt:

![End-to-End-Docker DevOps-Lebenszyklus-Workflows](./media/image1-7.png)

Entwickeln mit Containern bietet viele Vorteile, insbesondere wenn der Container in der Produktion verwendet werden. Die gleiche Konfiguration des Containers ist zum Hosten der app in jeder Umgebung, in dem er ausgeführt aus dem lokalen Entwicklungscomputer erstellen und Testsysteme bis zur Produktion wird, verwendet. Daher sinkt die Wahrscheinlichkeit von Fehlern, die aufgrund der Unterschiede in der Konfiguration des Computers oder Softwareversionen. Entwickler können sich auch auf andere geeignete Tools sind am Produktivität, einschließlich Betriebssystem, da der Container unter jedem Betriebssystem ausgeführt werden können. In einigen Fällen möglicherweise verteilte Anwendungen, die im Zusammenhang mit viele Container sehr ressourcenintensiv auf einem einzelnen Entwicklungscomputer ausführen. In diesem Szenario kann es sinnvoll, ein upgrade auf Kubernetes mit Azure Dev Leerzeichen im nächsten Abschnitt behandelt.

Wie Teile von größeren Anwendungen in ihren eigenen kleiner, unabhängige unterteilt werden *Microservices*, zusätzliche Entwurfsmuster können verwendet werden, um das Verhalten der app zu verbessern. Anstatt direkt mit einzelnen Dienste zu arbeiten ein *-API-Gateway* können vereinfachen des Zugriffs und den Client über die Back-End zu entkoppeln. Mit separaten Dienst-back-Ends für die verschiedenen Front-Ends kann auch Dienste zusammen mit den Kunden weiter. Gemeinsame Dienste können auf das über eine Separate *Sidecar* Container, der allgemeine Clientbibliotheken für Verbindungen mit enthalten möglicherweise die *botschafter* Muster.

![Microservices-Beispiel-Architektur mit mehrere gängige Entwurfsmuster notiert haben.](./media/image1-10.png)

[Weitere Informationen finden Sie Informationen zu Entwurfsmustern, bei der Erstellung von Microservice-basierte Systeme zu berücksichtigen.](https://docs.microsoft.com/azure/architecture/microservices/design/patterns)

### <a name="azure-kubernetes-service"></a>Azure Kubernetes Service

Azure Kubernetes Service (AKS) verwaltet Ihre gehostete Kubernetes-Umgebung. So können Sie sie schnell und einfach Containeranwendungen ohne Kenntnisse in der Containerorchestrierung bereitstellen und verwalten. Dabei entfällt der Aufwand des kontinuierlichen Betriebs und für Wartungen, da Ressourcen nach Bedarf bereitgestellt, upgegradet und skaliert werden, ohne die Anwendungen offline zu schalten.

AKS verringert die Komplexität und den operativen Mehraufwand der Verwaltung eines Kubernetes-Clusters, indem der Großteil der Zuständigkeit dafür an Azure übertragen wird. Als gehosteter Kubernetes-Dienst übernimmt Azure kritische Tasks wie die Sicherheitsüberwachung und die Wartung für Sie. Darüber hinaus zahlen Sie nur für die Agent-Knoten in Ihren Clustern, nicht für die Masterknoten. Als verwalteter Kubernetes-Dienst bietet AKS:

- Automatisierte Kubernetes-Versionsupgrades und -Patches
- Einfache Clusterskalierung
- Selbstheilende gehostete Steuerungsebene (Master)
- Kosteneinsparungen: Zahlen Sie nur für ausgeführte Agentpoolknoten

Da Azure die Knoten im AKS-Cluster verwaltet, müssen Sie keine Aufgaben wie Clusterupgrades mehr manuell ausführen. Da Azure diese wichtigen Wartungsaufgaben übernimmt, stellt AKS keinen direkten Zugriff (z.B. mit SSH) auf den Cluster bereit.

Teams, die ACS nutzen können auch Azure Dev Speicherplätze nutzen. Azure Dev Leerzeichen können Teams für die Entwicklung und schnelle Iterationen ihrer microservices-Anwendung zu konzentrieren, indem es ermöglicht Teams arbeiten direkt mit ihren gesamten Microservices-Architektur oder einer Anwendung, die in AKS ausgeführte. Azure Dev Leerzeichen bietet auch eine Möglichkeit, Teile Ihrer Microservices-Architektur isoliert unabhängig voneinander aktualisieren, ohne den Rest des AKS-Cluster oder andere Entwickler.

![Beispiel für Azure Dev Speicherplätze-workflow](./media/image1-9.gif)

Azure Developer-Speicherplätze:

- Minimieren Sie Zeit und Ressourcen Installationsanforderungen des lokalen Computers
- Können Sie Teams schneller durchlaufen.
- Reduzieren Sie die Anzahl der Integration-Umgebungen, die vom Team erforderlich
- Entfernen müssen, um bestimmte Dienste in verteilten System zu simulieren, beim Entwickeln/testen

[Erfahren Sie mehr über Azure Dev Leerzeichen](https://docs.microsoft.com/azure/dev-spaces/about)

### <a name="azure-virtual-machines"></a>Azure Virtual Machines

Wenn Sie über eine Anwendung verfügen, deren Ausführung in App Service umfassende Änderungen notwendig machen würde, können Sie sich für Virtual Machines entscheiden, um die Migration zur Cloud zu vereinfachen. Das ordnungsgemäße Konfigurieren, Sichern und Verwalten von Virtual Machines erfordert allerdings deutlich mehr Zeit und IT-Kenntnisse im Vergleich zu Azure App Service. Wenn Sie Azure Virtual Machines in Betracht ziehen, sollten Sie den ständigen Wartungsaufwand für das Patchen, Aktualisieren und Verwalten der VM-Umgebung beachten. Azure Virtual Machines ist ein IaaS-Angebot (Infrastructure-as-a-Service), während App Service ein PaaS-Angebot (Platform-as-a-Service) ist. Sie sollten auch überlegen, ob die Bereitstellung Ihrer App als Windows-Container in „Web-App für Container“ eine geeignete Option für Ihr Szenario wäre.

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

- Architecture\ für grundlegende Azure-Web-Anwendung
  <https://docs.microsoft.com/azure/architecture/reference-architectures/app-service-web-app/basic-web-app>

- Entwurfsmuster für Microservices\
  <https://docs.microsoft.com/azure/architecture/microservices/design/patterns>

- Entwicklerleitfaden für Microsoft Azure
  <https://azure.microsoft.com/campaigns/developer-guide/>

- Web-Apps-Übersicht
  <https://docs.microsoft.com/azure/app-service/app-service-web-overview>

- Web-App für Container
  <https://azure.microsoft.com/services/app-service/containers/>

- Einführung in Azure Kubernetes Service (AKS)
  <https://docs.microsoft.com/azure/aks/intro-kubernetes>

>[!div class="step-by-step"]
>[Vorherige](development-process-for-azure.md)
