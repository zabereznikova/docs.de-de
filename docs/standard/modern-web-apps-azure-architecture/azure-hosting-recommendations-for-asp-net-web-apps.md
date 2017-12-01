---
title: "Azure-hosting Empfehlungen für ASP.NET Core Web-apps"
description: "Innovative Webanwendungen mit ASP.NET Core und Azure Architekt | Azure-hosting Empfehlungen für ASP.NET Web-apps"
author: ardalis
ms.author: wiwagn
ms.date: 10/07/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.openlocfilehash: c361a28321ec9dcbfee1db8036757632a5d81f7c
ms.sourcegitcommit: bbde43da655ae7bea1977f7af7345eb87bd7fd5f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2017
---
# <a name="azure-hosting-recommendations-for-aspnet-core-web-apps"></a>Azure-Hosting Empfehlungen für ASP.NET Core Web-Apps

> "Line-of-Business-Führungskräfte überall sind IT-Abteilungen zum Abrufen von Anwendungen aus der Cloud (aka SaaS) umgehen und wie würden Sie eine Zeitschrift Abonnement bezahlt. Und wenn der Dienst nicht mehr benötigt wird, können sie das Abonnement kündigen, keine Geräte, die Links in der Ecke nicht verwendet."  
> _\-Daryl Plummer, Gartner Analytiker_

## <a name="summary"></a>Zusammenfassung

Alle von Ihnen gewünschten Anforderungen und Architektur der Anwendung, kann Windows Azure unterstützt wird. Ihre Anforderungen kann so einfach wie eine statische Website zu einer sehr komplexe Anwendung setzt sich aus Dutzende von Diensten. Für ASP.NET Core monolithischen Webanwendungen und unterstützende Dienste gibt es mehrere bekannte Konfigurationen, die empfohlen werden. Die folgenden Empfehlungen werden nach der Art der Ressource gehostet werden, ob vollständige Anwendungen, einzelne Prozesse oder Daten gruppiert.

## <a name="web-applications"></a>Webanwendungen

Webanwendungen können mit gehostet werden:

-   App Service-Web-Apps

-   Container

-   Azure Service Fabric

-   Virtuelle Computer (VMs)

Von diesen sind App Service-Web-Apps die empfohlene Vorgehensweise für die meisten Szenarien. Erwägen Sie bei Microservice Architekturen einen Container basierenden Ansatz oder aus einem Service Fabric aus. Wenn Sie mehr Kontrolle über die Computer, die Ihre Anwendung ausführen möchten, sollten Sie die Azure Virtual Machines.

### <a name="app-service-web-apps"></a>App Service-Web-Apps

App Service Web Apps bietet eine vollständig verwaltete Plattform zum Hosten von Webanwendungen optimiert. Es ist ein platform-as-a-service(PaaS) anbieten, können, die Sie auf Ihrer Geschäftslogik konzentrieren, während Azure die Infrastruktur übernimmt, zum Ausführen und skalieren Sie die app erforderlich sind. Einige der wesentlichen Features der App Service-Web-Apps:

-   DevOps-Optimierung (fortlaufende Integration und Übermittlung, mehrere Umgebungen A / B-Tests, die Unterstützung der Skripterstellung)

-   Globale Skalierung und hohe Verfügbarkeit

-   Verbindungen mit SaaS-Plattformen und Ihre lokalen Daten

-   Sicherheit und Kompatibilität

-   Visual Studio-Integration

Azure App Service ist die beste Wahl für die meisten Web-apps. Bereitstellung und Verwaltung sind in der Plattform integriert, und der integrierte laden Lastenausgleich und Traffic Manager hohe Verfügbarkeit bieten Standorte können schnell skalieren, um hohe Datenverkehrsvolumen zu bewältigen. Sie können vorhandene Standorte nach Azure App Service ganz leicht mit einer online-Migrationstool verwenden, eine Open-Source-app aus dem Web App Gallery, oder erstellen Sie einen neuen Standort mithilfe von Framework und Tools Ihrer Wahl verschieben. Die WebJobs-Funktion vereinfacht die Verarbeitung auf Ihre App Service-Web-app Hintergrundauftrag hinzufügen.

### <a name="containers-and-azure-container-service"></a>Container und Azure-Container-Dienst

Azure Containerdienst erleichtert das Erstellen, konfigurieren und Verwalten eines Clusters von virtuellen Computern, die zum Ausführen von Sammelartikeleinheit vorkonfiguriert werden. Es wird eine optimierte Konfiguration der beliebten Open Source-Planung und Orchestrierung Tools verwendet. Dadurch können Sie Ihre vorhandenen Kenntnisse, oder eine große und wachsende Hauptteil Kenntnisse der Community, zur Bereitstellung und Verwaltung der Container-basierte Anwendungen in Microsoft Azure zu zeichnen.

Azure Containerdienst erleichtert das Erstellen, konfigurieren und Verwalten eines Clusters von virtuellen Computern, die zum Ausführen von Sammelartikeleinheit vorkonfiguriert werden. Es wird eine optimierte Konfiguration der beliebten Open Source-Planung und Orchestrierung Tools verwendet. Dadurch können Sie Ihre vorhandenen Kenntnisse, oder eine große und wachsende Hauptteil Kenntnisse der Community, zur Bereitstellung und Verwaltung der Container-basierte Anwendungen in Microsoft Azure zu zeichnen.

Eines der Ziele von Azure-Container-Dienst ist eine Container-Hostingumgebung mit Open Source-Tools und Technologien aufgeführt, die von Microsoft Kunden heute ebenfalls sind angeben. Zu diesem Zweck stellt Azure Containerdienst die standard-API-Endpunkte für die ausgewählte Orchestrator (DC/OS, Docker Containerhostclustern oder Kubernetes). Mit diesen Endpunkten, können Sie keine Software nutzen, die der Kommunikation mit diesen Endpunkten kann. Beispielsweise im Fall der Endpunkt Docker Containerhostclustern können Sie die Docker-Befehlszeilenschnittstelle (CLI) zu verwenden. DC/OS können Sie die DCOS CLI auswählen. Bei Kubernetes können Sie Kubectl entscheiden. Abbildung 11 – 1 zeigt an, wie Sie diese Endpunkte verwenden würden, um Ihre Cluster Container zu verwalten.

![](./media/image11-1.png)

**Abbildung 11 – 1.** Azure Containerdienst-Verwaltung mit Docker, Kubernetes oder DC/OS-Endpunkten.

### <a name="azure-service-fabric"></a>Azure Service Fabric

Service Fabric ist eine gute Wahl, wenn Sie eine neue app erstellen oder eine vorhandene Anwendung aus, um eine Microservice-Architektur verwenden umschreiben zu müssen. Apps, die auf einen freigegebenen Pool von Computern ausführen, können klein anzufangen und massive Skalierung mit Hunderten oder Tausenden von Computern nach Bedarf wachsen. Zustandsbehaftete Dienste erleichtern das zum Speichern von app-Status, zuverlässig und konsistent und Service Fabric verwaltet automatisch Dienst Partitionierung, Skalierung und Verfügbarkeit für Sie. Service Fabric unterstützt auch WebAPI mit Open Web-Schnittstelle für .NET (OWIN) und ASP.NET Core. Im Vergleich zu App Service, bietet Service Fabric auch mehr Kontrolle über oder direkten Zugriff auf die zugrunde liegende Infrastruktur. Sie können per Remotezugriff auf Ihren Servern oder Startaufgaben Server konfigurieren.

### <a name="azure-virtual-machines"></a>Azure Virtual Machines

Wenn Sie eine vorhandene Anwendung, die beträchtliche Änderungen führen Sie im App-Dienst oder die Service Fabric erfordern verfügen, können Sie virtuelle Computer auswählen, um die Migration zur Cloud zu vereinfachen. Ordnungsgemäß erfordert konfigurieren, Sichern und Verwalten von virtuellen Computern jedoch deutlich mehr Zeit und IT-Kenntnisse, die im Vergleich zu Azure App Service und Service Fabric. Wenn Sie virtuelle Computer in Azure in Betracht ziehen, stellen Sie sicher, dass Sie berücksichtigen, die laufende Wartung leichter gepatcht, aktualisieren und verwalten Ihre Umgebung mit virtuellen Computern. Virtuelle Computer in Azure ist Infrastructure-as-a-Service (IaaS) verwenden, während der App Services und Service Fabric Platform-as-a-Service (Paas) sind.

#### <a name="feature-comparison"></a>Featurevergleich zwischen "

| Feature der App Service | Service Fabric | Virtueller Computer |
|---------|----------|----------|
| Nahezu sofortige Bereitstellung | X | X | |
| Vertikales Skalieren Sie auf leistungsfähigere Computer ohne erneute Bereitstellung | X | X | |
| Instanzen Freigabe von Inhalt und Konfiguration; muss nicht erneut bereitstellen oder Reconfigure beim Skalieren | X | X | |
| Mehrere bereitstellungsumgebungen (Produktion, Staging) | X | X | |
| Automatische Betriebssystems updateverwaltung | X | | |
| Nahtlosen Wechsel zwischen 32/64-Bit-Plattformen | X | | |
| Bereitstellen von Code mit Git, FTP | X | | X |
| Bereitstellen von Code mit WebDeploy | X | | X |
| Bereitstellen von Code mit TFS | X | X | X |
| Host-Website oder Web-Dienstebene der Multi-Tier-Architektur | X | X | X |
| Zugriff auf Azure-Diensten wie Storage, Service Bus-SQL-Datenbank | X | X | X |
| Installieren Sie alle benutzerdefinierten MSI-Datei | | X | X |

## <a name="logical-processes"></a>Logische Prozesse

Einzelne logische Prozesse, die von der Rest der Anwendung entkoppelt werden, können möglicherweise unabhängig auf Azure-Funktionen in einer "serverlose" Weise bereitgestellt werden. Azure-Funktionen können Sie gerade schreiben den Code, den Sie für ein bestimmtes Problem benötigen, unabhängig von der Anwendung oder Infrastruktur, um es auszuführen. Sie können auswählen, aus einer Vielzahl von Programmiersprachen, einschließlich C\#, F\#, Node.js, Python und PHP, und Sie können die produktivste Sprache für den Task zur hand auswählen. Wie die meisten Cloud-basierten Lösungen Sie Zahlen nur für den Zeitraum, Ihre Verwendung und Azure-Funktionen, um nach Bedarf skalieren können Sie vertrauen.

## <a name="data"></a>Daten

Azure bietet eine Vielzahl von Speicheroptionen für die Daten, damit Ihre Anwendung den entsprechenden Datenanbieter für die betreffenden Daten verwenden können.

Für Transaktions-, relationale Daten werden Azure SQL-Datenbanken die beste Option. Für hohe Leistung überwiegend schreibgeschützten Daten ist ein Redis-Cache von Azure SQL-Datenbanken unterstützt eine gute Lösung.

Unstrukturierte JSON-Daten können in einer Vielzahl von Möglichkeiten in DocumentDB, aus SQL-Datenbank-Spalten auf Blobs oder Tabellen im Azure-Speicher gespeichert werden. Von diesen DocumentDB bietet die beste-Abfragefunktionalität und ist die empfohlene Option für eine große Anzahl von JSON-basierte Dokumente, die Abfragen unterstützen muss.

Vorübergehender Befehl oder Ereignis-basierten Daten verwendet, um das Verhalten der Anwendung zu orchestrieren können Azure Service Bus oder Azure-Speicher-Warteschlangen verwenden. Azure Storage-Bus bietet mehr Flexibilität und ist der empfohlene Dienst für nicht triviale messaging innerhalb und zwischen Anwendungen.

## <a name="architecture-recommendations"></a>Architektur-Empfehlungen

Anforderungen der Anwendung sollte die Architektur diktieren. Viele andere Azure-Dienste sind verfügbar, auswählen, dass eine wichtige Entscheidung richtig ist. Microsoft bietet einen Katalog von Verweis Architekturen zur Identifizierung der typische Architekturen für allgemeine Szenarien optimiert. Sie können eine Referenzarchitektur Maps eng mit den Anforderungen der Anwendung oder an mindestens einen Ausgangspunkt bietet binden.

Abbildung 11 – 2 zeigt ein Beispiel-Referenzarchitektur. Dieses Diagramm wird einen Ansatz empfohlene Architektur für eine für Marketing optimiert Sitecore Content Management System-Website beschrieben.

![](./media/image11-2.png)

**Abbildung 11-2.** Sitecore marketing-Website-Referenzarchitektur.

**Verweise – Azure Hosten von Empfehlungen**

-   Azure-Lösung Architectures\
    <https://Azure.Microsoft.com/Solutions/Architecture/>

-   Azure-Entwickler Konventionen\
    <https://Azure.Microsoft.com/Campaigns/Developer-Guide/>

-   Was ist, dass Azure App Service? \
    <https://docs.Microsoft.com/Azure/App-Service/App-Service-Value-Prop-What-is>

-   Azure App Service, Virtual Machines, Service Fabric und Cloud Services Comparison\
    <https://docs.Microsoft.com/Azure/App-Service-Web/Choose-Web-Site-Cloud-Service-VM>

>[!div class="step-by-step"]
[Vorherigen] (Development-Prozess-für-azure.md)
