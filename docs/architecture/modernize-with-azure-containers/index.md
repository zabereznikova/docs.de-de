---
title: Modernisieren vorhandener .NET-Anwendungen mit Azure Cloud und Windows-Containern
description: Erfahren Sie in diesem E-Book, wie vorhandene Anwendungen in Azure Cloud und Container übertragen, verschoben und modernisiert werden können.
ms.date: 01/07/2021
ms.openlocfilehash: bf6e6dff75c939508947aabeda14955b880f5a89
ms.sourcegitcommit: 5d9cee27d9ffe8f5670e5f663434511e81b8ac38
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2021
ms.locfileid: "98025470"
---
# <a name="modernize-existing-net-applications-with-azure-cloud-and-windows-containers"></a>Modernisieren vorhandener .NET-Anwendungen mit Azure Cloud und Windows-Containern

![Titelbild des Leitfadens zum Modernisieren von .NET-Anwendungen.](./media/index/web-application-guide-cover-image.png)

**EDITION v5.0**

Informationen zu den Buchaktualisierungen und Communitybeiträgen finden Sie im [Änderungsprotokoll](https://aka.ms/modernize-ebook-changelog).

VERÖFFENTLICHT VON DEN Microsoft Press- und Microsoft DevDiv-Geschäftsbereichen der Microsoft Corporation One Microsoft Way Redmond, Washington 98052-6399

Copyright © 2021 by Microsoft Corporation

Alle Rechte vorbehalten. Die Inhalte dieser Veröffentlichung dürfen in keiner Form und für keinen Zweck ohne die schriftliche Genehmigung des Herausgebers reproduziert werden.

Diese Veröffentlichung ist kostenlos in Form eines elektronischen Buchs (E-Book) über mehrere Kanäle bei Microsoft verfügbar, z.B. über <https://dot.net/architecture>.

Wenn Sie Fragen im Zusammenhang mit dieser Veröffentlichung haben, senden Sie eine E-Mail an [dotnet-architecture-ebooks-feedback@service.microsoft.com](mailto:dotnet-architecture-ebooks-feedback@service.microsoft.com?subject=Feedback%20for%20.NET%20Container%20&%20Microservices%20Architecture%20book).

Dieses Buch wird unverändert bereitgestellt und drückt die Ansichten und Meinungen des Autors aus. Die Ansichten, Meinungen und Informationen, die in diesem Buch zum Ausdruck gebracht werden, einschließlich URLs und anderer Verweise auf Internetwebsites, können ohne vorherige Ankündigung geändert werden.

Einige der hier dargestellten Beispiele dienen nur zu Illustrationszwecken und sind fiktiv. Keinerlei Zuordnung oder Verbindung zu realen Gegebenheiten ist beabsichtigt oder sollte gefolgert werden.

Microsoft und die auf der Webseite „Marken“ unter <https://www.microsoft.com> aufgelisteten Marken sind Marken der Microsoft-Unternehmensgruppe. Alle anderen Marken sind Eigentum der jeweiligen Besitzer.

Autor:
> **Cesar de la Torre**, leitender PM, .NET-Produktteam, Microsoft Corp.

Teilnehmer und Prüfer:
> **Scott Hunter**, Partner Director PM, .NET-Team, Microsoft **Paul Yuknewicz**, Principal PM Manager, Visual Studio-Tools-Team, Microsoft **Lisa Guthrie**, Sr. PM, Visual Studio-Tools-Team, Microsoft **Ankit Asthana**, Principal PM Manager, .NET-Team, Microsoft **Unai Zorrilla**, Developer Lead, Plain Concepts **Javier Valero**, Chief Operating Officer bei Grupo Solutio

## <a name="introduction"></a>Einführung

Wenn Sie sich entscheiden, Ihre Webanwendungen oder -dienste zu modernisieren und in die Cloud zu verschieben, müssen Sie Ihre Anwendungen nicht zwangsläufig vollständig neu strukturieren. Die Neustrukturierung einer Anwendung mithilfe eines fortschrittlichen Ansatzes wie Microservices ist aus Kosten- und Zeitgründen nicht immer eine Option. Abhängig von der Art der Anwendung kann es auch sein, dass eine Neustrukturierung einer App nicht notwendig ist. Wenn Sie die Kosteneffizienz der Cloudmigrationsstrategie Ihres Unternehmens optimieren möchten, ist es wichtig, die Bedürfnisse Ihres Unternehmens und die Anforderungen Ihrer Apps zu berücksichtigen. Sie müssen Folgendes ermitteln:

- Welche Apps erfordern eine Transformation oder Neustrukturierung?

- Welche Apps müssen nur teilweise modernisiert werden?

- Welche Apps können direkt in die Cloud übertragen und verschoben werden?

## <a name="about-this-guide"></a>Über diesen Leitfaden

Dieser Leitfaden konzentriert sich in erster Linie auf die anfängliche Modernisierung von vorhandenen Microsoft .NET Framework-Webanwendungen oder dienstorientierten Anwendungen, d. h. auf die Aktion, eine Workload in eine neuere oder modernere Umgebung zu verschieben, ohne den Code und die grundlegende Architektur der Anwendung wesentlich zu verändern.

Dieser Leitfaden hebt auch die Vorteile hervor, die sich aus der Verlagerung Ihrer Anwendungen in die Cloud und der teilweisen Modernisierung von Anwendungen durch die Verwendung einer Reihe spezifischer neuer Technologien und Ansätze ergeben, etwa Windows-Container und verwandte Computeplattformen in Azure, die Windows-Container unterstützen.

## <a name="path-to-the-cloud-for-existing-net-applications"></a>Pfad in die Cloud für vorhandene .NET-Anwendungen

Unternehmen entscheiden sich in der Regel für den Wechsel in die Cloud, um die Agilität und Geschwindigkeit zu erreichen, die sie für ihre Anwendungen erzielen können. Sie können Tausende von Servern (virtuellen Computern) in der Cloud innerhalb von Minuten einrichten, verglichen mit den Wochen, die normalerweise für die Einrichtung von lokalen Servern benötigt werden.

Es gibt keine einheitliche, standardisierte Strategie für die Migration von Anwendungen in die Cloud. Welche Migrationsstrategie für Sie die richtige ist, hängt von den Bedürfnissen und Prioritäten Ihres Unternehmens und der Art der Anwendungen ab, die Sie migrieren. Nicht alle Anwendungen rechtfertigen die Investition in einen Umstieg auf ein [PaaS](https://azure.microsoft.com/overview/what-is-paas/)-Modell (Platform-as-a-Service) oder in die Entwicklung eines [cloudnativen](https://www.gartner.com/doc/3181919/architect-design-cloudnative-applications) Anwendungsmodells. In vielen Fällen können Sie basierend auf Ihren Geschäftsanforderungen einen schrittweisen oder inkrementellen Ansatz wählen, um Ihre Ressourcen in die Cloud zu verschieben.

Für moderne Anwendungen mit der besten langfristigen Agilität und dem besten Wert für die Organisation können Sie von einer Investition in *cloudnative* Anwendungsarchitekturen profitieren. Bei Anwendungen, die bereits vorhandene oder Legacyressourcen sind, kommt es jedoch darauf an, nur minimalen Zeit- und Kostenaufwand zu betreiben (keine Neustrukturierung oder Codeänderungen), um sie in die Cloud zu verschieben, um signifikante Vorteile zu erzielen.

Abbildung 1-1 zeigt die möglichen Pfade, die Sie einschlagen können, wenn Sie vorhandene .NET-Anwendungen in inkrementellen Phasen in die Cloud verschieben.

 ![Modernisierungspfade für vorhandene .NET-Anwendungen und -Dienste](./media/image1-1.png)

**(Abbildung 1-1)** . Modernisierungspfade für vorhandene .NET-Anwendungen und -Dienste

Jeder Migrationsansatz weist unterschiedliche Vorteile und Gründe für seine Anwendung auf. Sie können einen einzelnen Ansatz wählen, wenn Sie Anwendungen in die Cloud migrieren, oder bestimmte Komponenten aus mehreren Ansätzen auswählen. Einzelne Anwendungen sind nicht auf einen Ansatz oder Reifezustand beschränkt. Ein allgemeiner Hybridansatz würde beispielsweise bestimmte lokale Komponenten und andere Komponenten in der Cloud aufweisen.

Die Definition und kurze Erklärung für jede Anwendungsreifestufe sind die folgenden:

**Stufe 1: Bereit für Cloudinfrastruktur**: Bei diesem Migrationsansatz werden Ihre aktuellen lokalen Anwendungen einfach neu gehostet oder zu einer [IaaS](https://azure.microsoft.com/overview/what-is-iaas/)-Plattform (Infrastructure-as-a-Service) migriert. Ihre Apps weisen fast die gleiche Zusammensetzung wie zuvor auf, aber nun stellen Sie sie auf virtuellen Computern in der Cloud bereit.
Dieser einfache Migrationstyp wird in der Branche als „Lift & Shift“ (übertragen und verschieben) bezeichnet.

**Stufe 2: Cloudoptimierte** Anwendungen: Auf dieser Stufe und dennoch ohne Neustrukturierung oder Änderung von signifikantem Code können Sie zusätzliche Vorteile aus der Ausführung Ihrer App in der Cloud mit modernen Technologien wie Containern und zusätzlichen in der Cloud verwalteten Diensten ziehen. Sie verbessern die Agilität Ihrer Anwendungen, um eine schnellere Bereitstellung leisten zu können, indem Sie Ihre DevOps-Prozesse (Enterprise Development Operations) verfeinern. Dies erreichen Sie durch den Einsatz von Technologien wie Windows-Containern, die auf der Docker-Engine basieren. Container beseitigen die Reibung, die durch Anwendungsabhängigkeiten verursacht wird, wenn die Bereitstellung in mehreren Stufen erfolgt. In diesem Reifestufenmodell können Sie Container unter IaaS oder PaaS bereitstellen und gleichzeitig zusätzliche in der Cloud verwaltete Dienste für Datenbanken, Cache-as-a-Service, Überwachung und Pipelines für Continuous Integration/Continuous Deployment (CI/CD) nutzen.

Die dritte Reifestufe ist das ultimative Ziel in der Cloud, aber sie ist für viele Apps optional und stellt nicht der Hauptschwerpunkt dieses Leitfadens dar:

**Stufe 3: Cloudnative** Anwendungen: Dieser Migrationsansatz wird typischerweise von den geschäftlichen Erfordernissen bestimmt und zielt auf die Modernisierung Ihrer unternehmenskritischen Anwendungen ab. Auf dieser Stufe verwenden Sie PaaS-Dienste, um Ihre Apps auf PaaS-Computeplattformen zu verschieben. Sie implementieren [cloudnative](https://www.gartner.com/doc/3181919/architect-design-cloudnative-applications) Anwendungen und Microservicesarchitekturen, um Anwendungen mit langfristiger Agilität zu entwickeln und neue Grenzen für die Skalierung zu entdecken. Diese Art der Modernisierung erfordert in der Regel eine coudspezifische Architektur. Häufig muss neuer Code geschrieben werden, insbesondere, wenn der Übergang auf cloudnative Anwendungs- und auf Microservices basierende Modelle erfolgt. Dieser Ansatz kann Ihnen dabei helfen, Vorteile zu erzielen, die in Ihrer monolithischen und lokalen Anwendungsumgebung nur schwer zu erreichen sind.

Tabelle 1-1 beschreibt die wichtigsten Vorteile und Gründe für die Wahl der einzelnen Migrations- oder Modernisierungsansätze.

| **Bereit für Cloudinfrastruktur** <br /> *Übertragen und verschieben* | **Cloudoptimiert** <br /> *Modernisieren* | **Cloudnativ** <br /> *Modernisieren, Neustrukturieren und Umschreiben* |
|---|---|---|
| **Computeziel der Anwendung** |
| Auf virtuellen Computern in Azure bereitgestellte Anwendungen | Monolithische oder n-schichtige Apps, die in Azure App Service bereitgestellt werden, Azure Container Instance (ACI), VMs mit Containern oder AKS (Azure Kubernetes Service) | Containerisierte Microservices in Azure Kubernetes Service (AKS) und/oder serverlose Microservices, die auf Azure Functions basieren. |
| **Datenziel** |
| SQL- oder eine beliebige relationale Datenbank auf einem virtuellen Computer | Verwaltete Azure SQL-Datenbank-Instanz oder eine andere verwaltete Datenbank in der Cloud. | Differenzierte Datenbanken pro Microservice, basierend auf Azure SQL-Datenbank, Azure Cosmos DB oder einer anderen verwalteten Datenbank in der Cloud |
| **Vorteile**|
| <li>Keine Neustrukturierung, kein neuer Code <li> Geringster Aufwand für eine schnelle Migration. <li> Kleinster gemeinsamen Nenner, der in Azure unterstützt wird. <li> Grundlegende Verfügbarkeitsgarantien. <li> Nach dem Wechsel in die Cloud ist es einfacher, noch mehr zu modernisieren. | <li> Keine Neustrukturierung <li> Minimale Code-/Konfigurationsänderungen <li> Verbesserte Bereitstellung und DevOps-Agilität beim Release aufgrund von Containern. <li> Höhere Dichte und niedrigere Bereitstellungskosten. <li> Portabilität von Apps und Abhängigkeiten. <li> Flexibilität der Hostziele: Paas-Ansätze oder IaaS | <li> Architektur für die Cloud: Sie profitieren von den besten Vorteilen der Cloud, es ist aber neuer Code erforderlich. <li> Cloudnative Microservicesansätze. <li> Moderne unternehmenskritische Anwendungen, cloudrobust, hyperskalierbar <li> Vollständig verwaltete Dienste. <li> Optimiert für die Skalierung. <li> Optimiert für autonome Agilität durch Subsysteme. <li> Basiert auf Bereitstellung und DevOps. |
| **Herausforderungen** |
| <li> Geringerer Cloudwert, abgesehen von der Verlagerung der Betriebskosten oder der Schließung von Rechenzentren <li> Sehr wenig wird verwaltet: Kein Patchen von Betriebssystemen oder Middleware, ggf. werden Infrastrukturlösungen wie Terraform, Spinnaker oder Puppet verwendet. | <li> Containerisierung ist ein zusätzlicher erforderlicher Schritt in der Lernkurve für Entwickler und den IT-Betrieb. <li> DevOps und CI/CD-Pipelines sind bei diesem Ansatz in der Regel ein Muss. Wenn sie zurzeit nicht in der Kultur der Organisation vorhanden sind, stellt dies möglicherweise eine weitere Herausforderung dar.| <li> Erfordert eine Neustrukturierung für cloudnative Apps, Microservicearchitekturen sowie in der Regel erhebliches Refactoring von Code oder ein Neuschreiben bei der Modernisierung (erhöhter Zeitaufwand und Budgetbedarf)|
> **Tabelle 1-1.** Vorteile und Herausforderungen von Modernisierungspfaden für vorhandene .NET-Anwendungen und -Dienste

### <a name="key-technologies-and-architectures-by-maturity-level"></a>Schlüsseltechnologien und -architekturen nach Reifegrad

.NET Framework-Anwendungen begannen ursprünglich mit .NET Framework Version 1.0, die Ende 2001 veröffentlicht wurde. Dann haben Unternehmen neuere Versionen (wie 2.0, 3.5 und .NET Framework 4.x) verwendet. Die meisten dieser Anwendungen wurden unter Windows Server und Internet Information Server (IIS) ausgeführt und verwendeten eine relationale Datenbank (z.B. SQL Server, Oracle, MySQL oder andere RDBMS).

Die meisten vorhandenen .NET-Anwendungen basieren heute auf .NET Framework 4.x oder sogar auf .NET Framework 3.5 und verwenden Webframeworks wie ASP.NET MVC, ASP.NET Web Forms, ASP.NET-Web-API, Windows Communication Foundation (WCF), ASP.NET SignalR oder ASP.NET Web Pages. Diese etablierten .NET Framework-Technologien sind von Windows abhängig. Diese Abhängigkeit muss unbedingt berücksichtigt werden, wenn Sie nur Legacy-Apps migrieren und minimale Änderungen an Ihrer Anwendungsinfrastruktur vornehmen möchten.

Abbildung 1-2 zeigt die primären Technologien und Architekturstile, die bei jedem der drei Cloudreifegrade verwendet werden:

![Primäre Technologien für jeden Reifegrad zur Modernisierung vorhandener .NET-Webanwendungen](./media/image1-2.png)

**Abbildung 1-2.** Primäre Technologien für jeden Reifegrad zur Modernisierung vorhandener .NET-Webanwendungen

Abbildung 1-2 zeigt die gängigsten Szenarien. Es sind aber viele hybride und gemischte Varianten bezüglich der Architektur denkbar. Die Reifegradmodelle gelten beispielsweise nicht nur für monolithische Architekturen in vorhandenen Web-Apps, sondern auch für Dienstorientierung, n-schichtige und andere Architekturstilvarianten. Ein größerer Schwerpunkt auf einem der Architekturtypen und den zugehörigen Technologien (oder ein größerer Prozentsatz) bestimmt die Gesamtreifestufe der Anwendungen.

Jeder Reifegrad im Modernisierungsprozess ist mit den folgenden Schlüsseltechnologien und -ansätzen verbunden:

- **Bereit für Cloudinfrastruktur** (erneutes Hosten oder grundlegendes Übertragen und Verschieben): In einem ersten Schritt möchten viele Organisationen nur schnell eine Cloudmigrationsstrategie ausführen. In diesem Fall werden Anwendungen neu gehostet. Ein Großteil des erneuten Hostens kann automatisiert werden, indem [Azure Migrate](https://aka.ms/azuremigrate) verwendet wird, ein Dienst, der Anleitung, Einblicke und Mechanismen bietet, die benötigt werden, um Sie basierend auf Cloudtools wie [Azure Site Recovery](https://azure.microsoft.com/services/site-recovery/) und [Azure Database Migration Service](https://azure.microsoft.com/campaigns/database-migration/) bei der Migration nach Azure zu unterstützen. Sie können erneutes Hosten auch manuell einrichten, sodass Sie beim Verschieben von Legacy-Apps in die Cloud Infrastrukturdetails über Ihre Ressourcen erfahren können. Beispielsweise können Sie Ihre Anwendungen mit geringen Änderungen auf virtuelle Computer in Azure verschieben (wahrscheinlich mit nur geringen Konfigurationsänderungen). Die Netzwerkfunktionalität ähnelt in diesem Fall einer lokalen Umgebung, insbesondere wenn Sie virtuelle Netzwerke in Azure erstellen.

- **Cloudoptimiert** (verwaltete Dienste und Windows-Container): In diesem Modell geht es darum, einige wichtige Bereitstellungsoptimierungen vorzunehmen, um signifikante Vorteile aus der Cloud zu ziehen, ohne die Kernarchitektur der Anwendung zu verändern. Der grundlegende Schritt hierbei besteht darin, Ihren vorhandenen .NET Framework-Anwendungen Unterstützung für [Windows-Container](/virtualization/windowscontainers/about/) hinzuzufügen. Dieser wichtige Schritt (Containerisierung) erfordert kein Ändern des Codes, sodass der gesamte Übertragungs- und Verschiebeaufwand gering ist. Sie können Tools wie [Image2Docker](https://github.com/docker/communitytools-image2docker-win) oder Visual Studio mit den Tools für [Docker](https://www.docker.com/) verwenden. Visual Studio wählt automatisch intelligente Standardeinstellungen für ASP.NET-Anwendungen und Windows Container-Images aus. Diese Tools bieten sowohl eine schnelle innere Schleife als auch einen schnellen Weg, um die Container in Azure zu übertragen. Ihre Agilität wird verbessert, wenn die Bereitstellung in mehreren Umgebungen erfolgt.
Anschließend können Sie Ihre Windows-Container beim Übergang in die Produktion in [Azure Web App für Container](https://azure.microsoft.com/services/app-service/containers/), [Azure Container Instances (ACI)](https://azure.microsoft.com/services/container-instances/) und in Azure VMs mit Windows Server 2016 und Containern bereitstellen, wenn Sie einen IaaS-Ansatz bevorzugen. Für komplexere Anwendungen mit mehreren Containern sollten Sie Orchestratoren wie [Azure Kubernetes Service (AKS/ACS)](https://azure.microsoft.com/services/container-service/) in Betracht ziehen.

Während dieser ersten Modernisierung können Sie auch Ressourcen aus der Cloud hinzufügen, z.B. Überwachung mit Tools wie [Azure Application Insights](/azure/application-insights/app-insights-overview), CI-/CD-Pipelines für Ihre App-Lebenszyklen mit [Azure DevOps Services](https://azure.microsoft.com/services/devops/) und viele weitere Datenressourcendienste, die in Azure verfügbar sind. Beispielsweise können Sie eine monolithische Web-App., die ursprünglich unter Verwendung von traditionellem [ASP.NET Web Forms](https://www.asp.net/web-forms) oder [ASP.NET MVC](https://www.asp.net/mvc) entwickelt wurde, ändern, aber jetzt stellen Sie sie mit Hilfe von Windows-Containern bereit. Wenn Sie Windows-Container verwenden, sollten Sie Ihre Daten auch zu einer Datenbank in einer [verwalteten Azure SQL-Datenbank-Instanz](/azure/sql-database/) migrieren, ohne die Kernarchitektur Ihrer Anwendung zu verändern.

- **Cloudnativ**: Wie bereits erwähnt, sollten Sie über die Entwicklung von [cloudnativen](https://www.gartner.com/doc/3181919/architect-design-cloudnative-applications) Anwendungen nachdenken, wenn Sie große und komplexe Anwendungen mit mehreren unabhängigen Entwicklungsteams anstreben, die an verschiedenen Microservices arbeiten, die autonom entwickelt und bereitgestellt werden können. Dies gilt auch aufgrund der granularisierten und unabhängigen Skalierbarkeit pro Microservice. Diese Architekturansätze bringen sehr wichtige Herausforderungen und Komplexitäten mit sich, können aber durch den Einsatz von Cloud-PaaS und Orchestratoren wie [Azure Kubernetes Service (AKS/ACS)](https://azure.microsoft.com/services/container-service/) (verwaltete Kubernetes-Dienste) und [Azure Functions](https://azure.microsoft.com/services/functions/) für einen serverlosen Ansatz erheblich vereinfacht werden. Alle diese Ansätze (wie Microservices und serverlose Lösungen) erfordern in der Regel, dass Sie für die Cloud entwickeln und neuen Code schreiben, der an bestimmte PaaS-Plattformen angepasst ist, oder Code, der sich an bestimmte Architekturen wie Microservices anpasst.

Abbildung 1-3 zeigt die internen Technologien, die Sie für jeden Reifegrad verwenden können:

![Interne Technologien für jeden Modernisierungsreifegrad](./media/image1-3.png)

**Abbildung 1-3.** Interne Technologien für jeden Modernisierungsreifegrad

## <a name="lift-and-shift-scenario"></a>Übertragungs- und Verschiebeszenario

Beachten Sie bei der Migration mit Übertragung und Verschiebung, dass Sie in Ihren Anwendungsszenarien viele verschiedene Varianten von Übertragung und Verschiebung verwenden können. Wenn Sie Ihre Anwendung nur neu hosten, liegt möglicherweise ein Szenario wie in Abbildung 1-4 dargestellt vor, in dem Sie virtuelle Computer in der Cloud nur für Ihre Anwendung und für Ihren Datenbankserver verwenden.

![Beispiel für ein reines IaaS-Szenario in der Cloud](./media/image1-4.png)

**Abbildung 1-4.** Beispiel für ein reines IaaS-Szenario in der Cloud

## <a name="modernization-scenarios"></a>Modernisierungsszenarien

Für Modernisierungsszenarien steht Ihnen möglicherweise eine reine cloudoptimierte Anwendung zur Verfügung, die nur Elemente aus dieser Reifestufe verwendet. Sie könnten auch eine Anwendung mit einigen Elementen aus „Bereit für Cloudinfrastruktur“ und anderen Elementen aus „Cloudoptimiert“ einsetzen (ein Auswahl- oder gemischtes Modell), wie in Abbildung 1-5 dargestellt.

![Beispielauswahlszenario mit Datenbank unter IaaS, DevOps und Containerisierung von Ressourcen](./media/image1-5.png)

**Abbildung 1-5.** Beispielauswahlszenario mit Datenbank unter IaaS, DevOps und Containerisierung von Ressourcen

Im nächsten Schritt (als ideales Szenario für die Migration zahlreicher vorhandener .NET Framework-Anwendungen) könnten Sie zu einer cloudoptimierten Anwendung migrieren, um großen Nutzen aus wenig Aufwand zu ziehen. Dieser Ansatz bereitet Sie auch auf cloudnative Lösungen als mögliche Option für die Zukunft vor. Abbildung 1-6 zeigt ein Beispiel.

![Beispielszenario für Apps, die cloudoptimiert sind, mit Windows-Containern und verwalteten Diensten](./media/image1-6.png)

**Abbildung 1-6.** Beispielszenario für Apps, die cloudoptimiert sind, mit Windows-Containern und verwalteten Diensten

Darüber hinaus können Sie Ihre vorhandene cloudoptimierte Anwendung um einige Microservices für bestimmte Szenarien erweitern. Mit diesem Ansatz würden Sie teilweise die Ebene des cloudnativen Modells erreichen, die aber nicht im Mittelpunkt des vorliegenden Leitfadens steht.

## <a name="what-this-guide-does-not-cover"></a>Was in diesem Leitfaden nicht behandelt wird

Dieser Leitfaden behandelt eine bestimmte Teilmenge der in Abbildung 1-7 dargestellten Beispielszenarien. Dieser Leitfaden konzentriert sich ausschließlich auf Übertragungs- und Verschiebungsszenarios und letztlich auf das Modell „Cloudoptimiert“. Im Modell „Cloudoptimiert“ wird eine .NET Framework-Anwendung mithilfe von Windows-Containern und zusätzlichen Komponenten wie Überwachung und CI-/CD-Pipelines modernisiert. Jede Komponente ist wesentlich für die schnellere und flexiblere Bereitstellung von Anwendungen in der Cloud.

![Cloudnative Lösungen werden jedoch nicht in diesem Leitfaden behandelt.](./media/image1-7.png)

**Abbildung 1-7.** Cloudnative Lösungen werden jedoch nicht in diesem Leitfaden behandelt.

Der Schwerpunkt dieses Leitfadens ist spezifisch. Er zeigt Ihnen den Weg, den Sie einschlagen können, um eine Übertragung und Verschiebung Ihrer vorhandenen .NET-Anwendungen zu erreichen, ohne dass Sie die Architektur oder Code ändern müssen. Schließlich zeigt er Ihnen, wie Sie eine Cloudoptimierung Ihrer Anwendung erreichen können.

In diesem Leitfaden wird nicht gezeigt, wie Sie cloudnative Anwendungen erstellen (z.B. die Entwicklung einer Microservicesarchitektur). Um Ihre Anwendungen neu zu strukturieren oder brandneue Anwendungen zu erstellen, die auf Microservices basieren, lesen Sie das E-Book [.NET Microservices: Architektur für containerisierte .NET-Anwendungen](https://aka.ms/microservicesebook).

### <a name="additional-resources"></a>Zusätzliche Ressourcen

- **Containerized Docker Application Lifecycle with Microsoft Platform and Tools (Lebenszyklus von Docker-Containeranwendungen mit der Microsoft-Plattform und Microsoft-Tools)** (E-Book zum Download) \
  <https://aka.ms/dockerlifecycleebook>

- **.NET-Microservices: Architektur für .NET-Containeranwendungen** (E-Book zum Download) \
  <https://aka.ms/microservicesebook>

- **Architektur moderner Webanwendungen mit ASP.NET Core und Azure** (E-Book zum Download) \
  <https://aka.ms/webappebook>

## <a name="who-should-use-this-guide"></a>Zielgruppe dieses Leitfadens

Dieser Leitfaden wurde für Entwickler und Lösungsarchitekten geschrieben, die vorhandene ASP.NET-Webanwendungen oder WCF-Dienste, die auf .NET Framework basieren, modernisieren möchten, um die Flexibilität bei der Auslieferung und dem Release von Anwendungen zu verbessern.

Möglicherweise finden Sie diesen Leitfaden auch nützlich, wenn Sie ein technischer Entscheidungsträger sind (z.B. ein Unternehmensarchitekt oder ein Entwicklungsleiter), der sich nur einen Überblick über die Vorteile verschaffen möchte, die durch die Verwendung von Windows-Containern und die Bereitstellung in der Cloud unter Verwendung von Microsoft Azure erzielt werden können.

## <a name="how-to-use-this-guide"></a>So verwenden Sie diesen Leitfaden

Dieser Leitfaden befasst sich mit dem „Warum“ (warum Sie Ihre vorhandenen Anwendungen modernisieren sollten) und mit den spezifischen Vorteilen, die Ihnen die Verwendung von Windows-Containern bietet, wenn Sie Ihre Apps in die Cloud verschieben. Der Inhalt der ersten Kapitel des Leitfadens richtet sich an Architekten und technische Entscheidungsträger, die sich einen Überblick verschaffen möchten, sich aber nicht auf die Umsetzung und technische Details konzentrieren müssen.

Im letzten Kapitel dieses Leitfadens werden mehrere exemplarische Vorgehensweisen vorgestellt, die sich auf spezifische Bereitstellungsszenarien konzentrieren. Dieser Leitfaden bietet kürzere Versionen der exemplarischen Vorgehensweisen an, um die Szenarien zusammenzufassen und ihre Vorteile aufzuzeigen. Die vollständigen exemplarischen Vorgehensweisen befassen sich ausführlich mit den Einrichtungs- und Implementierungsdetails und werden als eine Gruppe von [Wiki-Beiträgen](https://github.com/dotnet-architecture/eShopModernizing/wiki) in dem gleichen öffentlichen [GitHub Repository](https://github.com/dotnet-architecture/eShopModernizing) veröffentlicht, in dem sich verwandte Beispiel-Apps befinden (siehe nächster Abschnitt). Das letzte Kapitel und die schrittweisen exemplarischen Wiki-Vorgehensweisen auf GitHub werden für Entwickler und Architekten, die sich auf Implementierungsdetails konzentrieren möchten, von größerem Interesse sein.

## <a name="sample-apps-for-modernizing-legacy-apps-eshopmodernizing"></a>Beispiel-Apps für die Modernisierung von Legacy-Apps: eShopModernizing

Das [eShopModernizing](https://github.com/dotnet-architecture/eShopModernizing)-Repository auf GitHub bietet zwei Beispielanwendungen, die monolithische Legacywebanwendungen simulieren. Eine Web-App wird mit ASP.NET MVC entwickelt, die zweite Web-App mit ASP.NET Web Forms, und die dritte App ist eine n-schichtige App mit einer WinForms-Clientdesktop-App, die ein Back-End des WCF-Diensts verwendet. Alle diese Web-Apps basieren auf dem traditionellen .NET Framework. Diese Beispiel-Apps verwenden weder .NET Core noch .NET 5.0 oder ASP.NET Core, da es sich hierbei um vorhandene bzw. veraltete .NET Framework-Anwendungen handelt.

Für diese Beispiel-Apps ist eine zweite Version mit modernisiertem Code verfügbar, die recht einfach ist. Der wichtigste Unterschied zwischen den App-Versionen besteht darin, dass die jeweils zweite Version Windows-Container als Bereitstellungsauswahl verwendet. Es gibt auch einige Ergänzungen zu den zweiten Versionen, wie Azure Storage Blobs für die Verwaltung von Images, Azure Active Directory für die Verwaltung der Sicherheit und Azure Application Insights für die Überwachung und Überprüfung der Anwendungen.

## <a name="send-your-feedback"></a>Senden Sie uns Ihr Feedback

Dieser Leitfaden wurde verfasst, um Ihnen zu helfen, Ihre Möglichkeiten zur Verbesserung und Modernisierung vorhandener .NET-Webanwendungen zu verstehen. Der Leitfaden und die zugehörigen Anwendungsbeispiele werden ständig weiterentwickelt. Ihr Feedback ist uns wichtig! Wenn Sie Anmerkungen dazu haben, wie dieser Leitfaden hilfreicher gestaltet werden könnte, senden Sie diese bitte an [dotnet-architecture-ebooks-feedback@service.microsoft.com](mailto:dotnet-architecture-ebooks-feedback@service.microsoft.com?subject=Feedback%20for%20.NET%20Container%20&%20Microservices%20Architecture%20book).

>[!div class="step-by-step"]
>[Nächste](lift-and-shift-existing-apps-azure-iaas.md) <!-- Next Chapter -->
