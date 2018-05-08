---
title: Modernisieren vorhandener .NET-Anwendungen mit Azure Cloud und Windows-Containern
description: Weitere Informationen Sie zu heben und verschieben vorhandene Anwendungen, die Azure-Cloud und der Container mit diesem e-Book.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/26/2017
ms.openlocfilehash: 3109cac1bd64587bb096a057f6f4ae99b055352a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="modernize-existing-net-applications-with-azure-cloud-and-windows-containers-v10"></a>Modernisieren vorhandener .NET-Anwendungen mit Azure Cloud und Windows-Containern (v1.0)

![Titelbild](./media/cover.png)

VERÖFFENTLICHT VON  
Microsoft Press und Microsoft DevDiv  
Geschäftsbereiche der Microsoft Corporation  
One Microsoft Way  
Redmond, Washington 98052-6399  

Copyright © 2017 by Microsoft Corporation  

Alle Rechte vorbehalten. Die Inhalte dieser Veröffentlichung dürfen in keiner Form und für keinen Zweck ohne die schriftliche Genehmigung des Herausgebers reproduziert werden.

Dieses Handbuch steht kostenlos in Form einer elektronischen Buch (e-Book) über mehrere Kanäle bei Microsoft zur Verfügung wie z. B. http://dot.net/architecture.

Wenn Sie Fragen im Zusammenhang mit dieser Veröffentlichung haben, senden Sie eine E-Mail an [dotnet-architecture-ebooks-feedback@service.microsoft.com](mailto:dotnet-architecture-ebooks-feedback@service.microsoft.com?subject=Feedback%20for%20.NET%20Container%20&%20Microservices%20Architecture%20book).

Dieses Buch wird unverändert bereitgestellt und drückt die Ansichten und Meinungen des Autors aus. Ansichten, meinungen und Informationen, ausgedrückt in diesem Buch, einschließlich URLs und anderer Verweise auf Internetwebsites, können ohne vorherige Ankündigung geändert werden.

Einige der hier dargestellten Beispiele dienen nur zu Illustrationszwecken und sind fiktiv. Keinerlei Zuordnung oder Verbindung zu realen Gegebenheiten ist beabsichtigt oder sollte gefolgert werden.

Microsoft und die Marken am http://www.microsoft.com auf der Webseite "Marken" sind Marken der Microsoft-Unternehmensgruppe. Alle anderen Marken sind Eigentum der jeweiligen Besitzer.

Autor:
> **Cesar de la Torre**, Sr. PM, .NET-Produktteam, Microsoft Corp.

Teilnehmer und Prüfer:
> **Scott Hunter**, Partner Director von PM, .NET-Team, Microsoft  
> **Paul Yuknewicz**, Principal PM Manager, Visual Studio-Tools-Team, Microsoft  
> **Claudia Guthrie**, Sr. PM, Visual Studio-Tools-Team, Microsoft  
> **Ankit Asthana**, leitender PM-Manager, .NET-Team, Microsoft  
> **Unai Zorrilla**, leitender Entwickler, einfache Konzepte  
> **Javier Valero**, Chief Operating Officer bei Grupo Solutio  

## <a name="introduction"></a>Einführung

Wenn Sie sich entscheiden, Ihre Webanwendungen zu modernisieren und in die Cloud zu verschieben, müssen Sie Ihre Anwendungen nicht zwangsläufig vollständig neu strukturieren. Die Neustrukturierung einer Anwendung mithilfe eines fortschrittlichen Ansatzes wie Microservices ist aus Kosten- und Zeitgründen nicht immer eine Option. Abhängig von der Art der Anwendung kann es auch sein, dass eine Neustrukturierung einer App nicht notwendig ist. Um die Kosteneffizienz der Cloudmigrationsstrategie Ihres Unternehmens zu optimieren, ist es wichtig, die Bedürfnisse Ihres Unternehmens und die Anforderungen Ihrer Apps zu berücksichtigen. Sie müssen Folgendes ermitteln:

- Welche Apps erfordern eine Transformation oder Neustrukturierung?

- Welche Apps müssen nur teilweise modernisiert werden?

- Welche Apps können direkt in die Cloud übertragen und verschoben werden?

## <a name="about-this-guide"></a>Über diesen Leitfaden

Dieser Leitfaden konzentriert sich in erster Linie auf Szenarien vom Typ „Übertragen und Verschieben“ und die anfängliche Modernisierung vorhandener web- oder dienstorientierter Microsoft .NET Framework-Anwendungen. Das Übertragen und Verschieben ist die Aktion, bei der eine Arbeitsauslastung in eine neuere oder modernere Umgebung verlagert wird, ohne den Code und die grundlegende Architektur der Anwendung zu verändern.

In diesem Leitfaden wird beschrieben, wie Sie Ihre vorhandenen .NET Framework-Serveranwendungen direkt in die Cloud verschieben können, indem Sie bestimmte Bereiche modernisieren, ohne dass Sie ganze Anwendungen neu strukturieren oder erneut codieren müssen.

Dieser Leitfaden hebt auch die Vorteile hervor, die sich aus der Verlagerung Ihrer Anwendungen in die Cloud und der teilweisen Modernisierung von Anwendungen durch die Verwendung einer Reihe spezifischer neuer Technologien und Ansätze wie Windows-Container und Orchestratoren in Azure ergeben.

## <a name="path-to-the-cloud-for-existing-net-applications"></a>Pfad in die Cloud für vorhandene .NET-Anwendungen

Unternehmen entscheiden sich in der Regel für den Wechsel in die Cloud, um die Agilität und Geschwindigkeit zu erreichen, die sie für ihre Anwendungen erzielen können. Sie können Tausende von Servern (virtuellen Computern) in der Cloud innerhalb von Minuten einrichten, verglichen mit den Wochen, die normalerweise für die Einrichtung von lokalen Servern benötigt werden.

Es gibt keine einheitliche, standardisierte Strategie für die Migration von Anwendungen in die Cloud. Welche Migrationsstrategie für Sie die richtige ist, hängt von den Bedürfnissen und Prioritäten Ihres Unternehmens und der Art der Anwendungen ab, die Sie migrieren. Nicht alle Anwendungen rechtfertigen die Investition in einen Umstieg auf ein [PaaS](https://azure.microsoft.com/overview/what-is-paas/)-Modell (Platform-as-a-Service) oder in die Entwicklung eines [cloudnativen](https://www.gartner.com/doc/3181919/architect-design-cloudnative-applications) Anwendungsmodells. In vielen Fällen können Sie basierend auf Ihren Geschäftsanforderungen einen schrittweisen oder inkrementellen Ansatz wählen, um Ihre Ressourcen in die Cloud zu verschieben.

Für moderne Anwendungen mit der besten langfristigen Agilität und dem besten Wert für die Organisation können Sie von einer Investition in *cloudoptimierte* und  *cloudnative* Anwendungsarchitekturen profitieren. Bei Anwendungen, die bereits vorhandene oder Legacyressourcen sind, kommt es jedoch darauf an, nur minimalen Zeit- und Kostenaufwand zu betreiben (keine Neustrukturierung oder Codeänderungen), um sie in die Cloud zu verschieben, um signifikante Vorteile zu erzielen.

Abbildung 1-1 zeigt die möglichen Pfade, die Sie einschlagen können, wenn Sie vorhandene .NET-Anwendungen in inkrementellen Phasen in die Cloud verschieben.

 ![Modernisierungspfade für vorhandene .NET-Anwendungen und -Dienste](./media/image1-1.png)

> **(Abbildung 1-1)**. Modernisierungspfade für vorhandene .NET-Anwendungen und -Dienste

Jeder Migrationsansatz weist unterschiedliche Vorteile und Gründe für seine Anwendung auf. Sie können einen einzelnen Ansatz wählen, wenn Sie Anwendungen in die Cloud migrieren, oder bestimmte Komponenten aus mehreren Ansätzen auswählen. Einzelne Anwendungen sind nicht auf einen Ansatz oder Reifezustand beschränkt. Ein allgemeiner Hybridansatz würde beispielsweise bestimmte lokale Komponenten und andere Komponenten in der Cloud aufweisen.

Auf den ersten beiden Migrationsstufen können Sie Ihre Anwendungen einfach übertragen und verschieben:

**Stufe 1: Bereit für die Cloudinfrastruktur**: Bei diesem Migrationsansatz werden Ihre aktuellen lokalen Anwendungen einfach neu gehostet oder auf eine [IaaS](https://azure.microsoft.com/overview/what-is-iaas/)-Plattform (Infrastructure-as-a-Service) verschoben. Ihre Apps weisen fast die gleiche Zusammensetzung wie zuvor auf, aber nun stellen Sie sie auf virtuellen Computern in der Cloud bereit.

**Stufe 2: Bereit für Cloud-DevOps**: Auf dieser Stufe können Sie nach einem anfänglichen Übertragen und Verschieben (und immer noch ohne Neustrukturierung oder Änderung des Codes) noch mehr Vorteile aus dem Ausführen Ihrer App in der Cloud ziehen. Sie verbessern die Agilität Ihrer Anwendungen, um eine schnellere Bereitstellung leisten zu können, indem Sie Ihre DevOps-Prozesse (Enterprise Development Operations) verfeinern. Dies erreichen Sie durch den Einsatz einer Technologie wie Windows-Container, die auf dem Docker-Modul basiert. Container beseitigen die Reibung, die durch Anwendungsabhängigkeiten verursacht wird, wenn die Bereitstellung in mehreren Stufen erfolgt. Container verwenden auch zusätzliche Cloud-verwalteten Dienste im Zusammenhang mit Daten, Überwachung und fortlaufende Integration/fortlaufende Bereitstellung (CI/CD)-Pipelines.

Die dritte Reifestufe ist das ultimative Ziel in der Cloud, aber sie ist für viele Apps optional und stellt nicht der Hauptschwerpunkt dieses Leitfadens dar:

**Stufe 3: Cloudoptimiert**: Dieser Migrationsansatz wird typischerweise von den geschäftlichen Erfordernissen bestimmt und zielt auf die Modernisierung Ihrer geschäftskritischen Anwendungen ab. Auf dieser Stufe verwenden Sie PaaS-Dienste, um Ihre Apps auf PaaS-Computeplattformen zu verschieben. Sie implementieren [cloudnative](https://www.gartner.com/doc/3181919/architect-design-cloudnative-applications) Anwendungen und Microservicesarchitekturen, um Anwendungen mit langfristiger Agilität zu entwickeln und neue Grenzen für die Skalierung zu entdecken. Diese Art der Modernisierung erfordert in der Regel eine coudspezifische Architektur. Häufig muss neuer Code geschrieben werden, insbesondere, wenn der Übergang auf cloudnative Anwendungs- und auf Microservices basierende Modelle erfolgt. Dieser Ansatz kann Ihnen dabei helfen, Vorteile zu erzielen, die in Ihrer monolithischen und lokalen Anwendungsumgebung nur schwer zu erreichen sind.

Tabelle 1-1 beschreibt die wichtigsten Vorteile und Gründe für die Wahl der einzelnen Migrations- oder Modernisierungsansätze.

| **Bereit für Cloudinfrastruktur** <br /> *Übertragen und verschieben* | **Bereit für Cloud-DevOps** <br /> *Übertragen und verschieben* | **Cloudoptimiert** *Modernisieren/Refactoring/neu schreiben* |
|---|---|---|
| **Computeziel der Anwendung** |
| Auf virtuellen Computern in Azure bereitgestellte Anwendungen | Containerisierte monolithische oder n-schichtige Anwendungen. Sie werden für virtuelle Computer, unter Azure Service Fabric oder Azure Container Service (d.h. Kubernetes) bereitgestellt. | Containerisierte Microservices oder reguläre Anwendungen basierend auf PaaS unter Azure App Service, Azure Service Fabric, Azure Container Service (d.h. Kubernetes). |
| **Datenziel** |
| SQL- oder eine beliebige relationale Datenbank auf einem virtuellen Computer | Verwaltete Azure SQL-Datenbank-Instanz | Azure SQL-Datenbank, Azure Cosmos DB und andere NoSQL-Datenbanken |
| **Vorteile**|
| <li>Keine Neustrukturierung, kein neuer Code. <li> Geringster Aufwand für eine schnelle Migration. <li> Kleinster gemeinsamen Nenner, der in Azure unterstützt wird. <li> Grundlegende Verfügbarkeitsgarantien. <li> Nach dem Wechsel in die Cloud ist es einfacher, noch mehr zu modernisieren. | <li>Keine Neustrukturierung, kein neuer Code. <li> Container bieten einen geringen inkrementellen Aufwand im Vergleich zu virtuellen Computern. <li> Verbesserte Bereitstellung und DevOps-Agilität beim Release aufgrund von Containern. <li> Höhere Dichte und niedrigere Bereitstellungskosten. <li> Portabilität von Apps und Abhängigkeiten. <li> Bietet mit Azure Container Service (oder Kubernetes) und Azure Service Fabric Hochverfügbarkeit und Orchestrierung. <li> Knoten-/VM-Patches in Service Fabric. <li> Flexibilität der Host-Ziele: Azure-VMs oder VM Skala festlegt, Dienst für Azure-Container (oder Kubernetes) Service Fabric und zukünftige Container-basierte Optionen | <li>Architektur für die Cloud, Refactoring, neuer Code erforderlich. <li> Cloudnative Microservicesansätze. <li> Neue Web-Apps, monolithisch, n-schichtig, cloudrobust und cloudoptimiert. <li> Vollständig verwaltete Dienste. <li> Automatische Patches. <li> Optimiert für die Skalierung. <li> Optimiert für autonome Agilität durch Subsysteme. <li> Basiert auf Bereitstellung und DevOps. <li> Verbesserte DevOps, z.B. Slots und Bereitstellungsstrategien <li> PaaS- und Orchestratorziele: Azure App Service, Azure Container Service (oder Kubernetes), Azure Service Fabric und zukünftiges containerbasiertes PaaS |
| **Herausforderungen** |
| <li> Geringerer Cloudwert, abgesehen von der Verschiebung der Betriebskosten oder der Schließung von Datencentern. <li> Es wird sehr wenig verwaltet: kein Patchen von Betriebssystemen oder Middleware, ggf. Infrastrukturlösungen wie Terraform, Spinnaker oder Puppet. | <li> Containerisierung ist ein zusätzlicher erforderlicher Schritt in der Lernkurve. | <li> Erfordert ggf. erhebliches Coderefactoring oder Neuerstellung (erhöhter Zeit- und Kostenaufwand). |
> **Tabelle 1-1.** Vorteile und Herausforderungen von Modernisierungspfaden für vorhandene .NET-Anwendungen und -Dienste

### <a name="key-technologies-and-architectures-by-maturity-level"></a>Schlüsseltechnologien und -architekturen nach Reifegrad

.NET Framework-Anwendungen begannen ursprünglich mit .NET Framework Version 1.0, die Ende 2001 veröffentlicht wurde. Dann haben Unternehmen neuere Versionen (wie 2.0, 3.5 und .NET 4.x) verwendet. Die meisten dieser Anwendungen auf Windows Server und Internet Information Server (IIS) ausgeführt, und eine relationale Datenbank, wie SQL Server, Oracle, MySQL oder eine beliebige andere RDBMS verwendet.

Die meisten vorhandenen .NET-Anwendungen basieren heute auf .NET Framework 4.x oder sogar auf .NET Framework 3.5 und verwenden Webframeworks wie ASP.NET MVC, ASP.NET Web Forms, ASP.NET-Web-API, Windows Communication Foundation (WCF), ASP.NET SignalR oder ASP.NET Web Pages. Diese etablierten .NET Framework-Technologien sind von Windows abhängig. Diese Abhängigkeit muss unbedingt berücksichtigt werden, wenn Sie nur Legacy-Apps migrieren und minimale Änderungen an Ihrer Anwendungsinfrastruktur vornehmen möchten.

Abbildung 1-2 zeigt die primären Technologien und Architekturstile, die bei jedem der drei Cloudreifegrade verwendet werden:

![Primäre Technologien für jeden Reifegrad zur Modernisierung vorhandener .NET-Webanwendungen](./media/image1-2.png)

> **Abbildung 1-2.** Primäre Technologien für jeden Reifegrad zur Modernisierung vorhandener .NET-Webanwendungen

Abbildung 1-2 zeigt die gängigsten Szenarien. Es sind aber viele hybride und gemischte Varianten bezüglich der Architektur denkbar. Die Reifegradmodelle gelten beispielsweise nicht nur für monolithische Architekturen in vorhandenen Web-Apps, sondern auch für Dienstorientierung, n-schichtige und andere Architekturstilvarianten.

Jeder Reifegrad im Modernisierungsprozess ist mit den folgenden Schlüsseltechnologien und -ansätzen verbunden:

- **Bereit für Cloudinfrastruktur** (erneutes Hosten oder grundlegendes Übertragen und Verschieben): In einem ersten Schritt möchten viele Organisationen nur schnell eine Cloudmigrationsstrategie ausführen. In diesem Fall werden Anwendungen einfach neu gehostet. Ein Großteil des erneuten Hostens kann automatisiert werden, indem [Azure Migrate](https://aka.ms/azuremigrate) verwendet wird, ein Dienst, der Anleitung, Einblicke und Mechanismen bietet, die benötigt werden, um Sie basierend auf Cloudtools wie [Azure Site Recovery](https://azure.microsoft.com/services/site-recovery/) und [Azure Database Migration Service](https://azure.microsoft.com/campaigns/database-migration/) bei der Migration nach Azure zu unterstützen. Sie können erneutes Hosten auch manuell einrichten, sodass Sie beim Verschieben von Legacy-Apps in die Cloud Infrastrukturdetails über Ihre Ressourcen erfahren können. Beispielsweise können Sie Ihre Anwendungen mit sehr geringen Änderungen auf virtuelle Computer in Azure verschieben (wahrscheinlich mit nur geringen Konfigurationsänderungen). Die Netzwerkfunktionalität ähnelt in diesem Fall einer lokalen Umgebung, insbesondere wenn Sie virtuelle Netzwerke in Azure erstellen.

- **Bereit für Cloud-DevOps** (verbessertes Übertragen und Verschieben): In diesem Modell geht es darum, einige wichtige Bereitstellungsoptimierungen vorzunehmen, um signifikante Vorteile aus der Cloud zu ziehen, ohne die Kernarchitektur der Anwendung zu verändern. Der grundlegende Schritt hierbei besteht darin, Ihren vorhandenen .NET Framework-Anwendungen Unterstützung für [Windows-Container](https://docs.microsoft.com/virtualization/windowscontainers/about/) hinzuzufügen. Dieser wichtige Schritt (Containerisierung) erfordert kein Ändern des Codes, sodass der gesamte Übertragungs- und Verschiebeaufwand sehr gering ist. Sie können Tools wie [Image2Docker](https://github.com/docker/communitytools-image2docker-win) oder Visual Studio mit den Tools für [Docker](https://www.docker.com/) verwenden. Visual Studio wählt automatisch intelligente Standardeinstellungen für ASP.NET-Anwendungen und Windows Container-Images aus. Diese Tools bieten sowohl eine schnelle innere Schleife als auch einen schnellen Weg, um die Container in Azure zu übertragen. Ihre Agilität wird verbessert, wenn die Bereitstellung in mehreren Umgebungen erfolgt. Wenn Sie dann in die Produktion übergehen, können Sie Ihre Windows-Container für Orchestratoren wie [Azure Service Fabric](https://azure.microsoft.com/services/service-fabric/) oder [Azure Container Service](https://azure.microsoft.com/services/container-service/) (Kubernetes, DC/OS oder Swarm) bereitstellen. Während dieser ersten Modernisierung können Sie auch Ressourcen aus der Cloud hinzufügen, z.B. Überwachung mit Tools wie [Azure Application Insights](https://docs.microsoft.com/azure/application-insights/app-insights-overview), CI-/CD-Pipelines für Ihre App-Lebenszyklen mit [Visual Studio Team Services](https://www.visualstudio.com/team-services/) und viele weitere Datenressourcendienste, die in Azure verfügbar sind. Beispielsweise können Sie eine monolithische Web-App., die ursprünglich unter Verwendung von traditionellem [ASP.NET Web Forms](https://www.asp.net/web-forms) oder [ASP.NET MVC](https://www.asp.net/mvc) entwickelt wurde, ändern, aber jetzt stellen Sie sie mit Hilfe von Windows-Containern bereit. Wenn Sie Windows-Container verwenden, sollten Sie Ihre Daten auch zu einer Datenbank in einer [verwalteten Azure SQL-Datenbank-Instanz](https://docs.microsoft.com/azure/sql-database/) migrieren, ohne die Kernarchitektur Ihrer Anwendung zu verändern.

- **Cloudoptimiert**: Wie bereits erwähnt, ist das ultimative Ziel bei der Modernisierung von Anwendungen in der Cloud, Ihr System auf PaaS-Plattformen wie [Azure App Service](https://azure.microsoft.com/services/app-service/) aufzubauen. PaaS-Plattformen konzentrieren sich auf moderne Webanwendungen und erweitern Ihre Anwendungen um neue Dienste auf der Basis von [serverlosem Computing](https://azure.microsoft.com/overview/serverless-computing/) und Plattformen wie [Azure Functions](https://azure.microsoft.com/services/functions/). Das zweite und weiter fortgeschrittene Szenario in diesem Reifegradmodell befasst sich mit Mikroservicesarchitekturen und [cloudnativen](https://www.gartner.com/doc/3181919/architect-design-cloudnative-applications) Anwendungen, die typischerweise Orchestratoren wie [Azure Service Fabric](https://azure.microsoft.com/services/service-fabric/) oder [Azure Container Service](https://azure.microsoft.com/services/container-service/) (Kubernetes, DC/OS oder Swarm) verwenden. Diese Orchestratoren sind speziell für Microservices und Multicontaineranwendungen konzipiert. Alle diese Ansätze (wie Microservices und PaaS) erfordern in der Regel, dass Sie neuen Code schreiben, der an bestimmte PaaS-Plattformen angepasst ist, oder Code, der sich an bestimmte Architekturen wie Microservices anpasst.

Abbildung 1-3 zeigt die internen Technologien, die Sie für jeden Reifegrad verwenden können:

![Interne Technologien für jeden Modernisierungsreifegrad](./media/image1-3.png)

> **Abbildung 1-3.** Interne Technologien für jeden Modernisierungsreifegrad

## <a name="lift-and-shift-scenarios"></a>Übertragungs- und Verschiebeszenarien

Beachten Sie bei der Migration mit Übertragung und Verschiebung, dass Sie in Ihren Anwendungsszenarien viele verschiedene Varianten von Übertragung und Verschiebung verwenden können. Wenn Sie Ihre Anwendung nur neu hosten, liegt möglicherweise ein Szenario wie in Abbildung 1-4 dargestellt vor, in dem Sie virtuelle Computer in der Cloud nur für Ihre Anwendung und für Ihren Datenbankserver verwenden.

![Beispiel für ein reines IaaS-Szenario in der Cloud](./media/image1-4.png)

> **Abbildung 1-4.** Beispiel für ein reines IaaS-Szenario in der Cloud

In Zukunft könnten Sie eine reine DevOps-fähige Cloudanwendung einsetzen, die nur Elemente aus diesem Reifegrad verwendet. Sie könnten auch eine Anwendung mit einigen Elementen aus „Bereit für Cloudinfrastruktur“ und anderen Elementen aus „Bereit für Cloud-DevOps“ einsetzen (ein Auswahl- oder gemischtes Modell), wie in Abbildung 1-5 dargestellt.

![Beispielauswahlszenario mit Datenbank unter IaaS, DevOps und Containerisierung von Ressourcen](./media/image1-5.png)

> **Abbildung 1-5.** Beispielauswahlszenario mit Datenbank unter IaaS, DevOps und Containerisierung von Ressourcen

Als Nächstes als idealerweise für viele vorhandene .NET Framework-Anwendungen zu migrieren, konnte Sie an eine Cloudfähige DevOps-Anwendung so wenig Arbeit bedeutende Vorteile ab migriert werden. Dieser Ansatz bereitet Sie auch auf die Cloudoptimierung als Option für die Zukunft vor. Abbildung 1-6 zeigt ein Beispiel.

![Beispielszenario für Apps, die „Bereit für Cloud-DevOps“ sind, mit Windows-Containern und verwalteten Diensten](./media/image1-6.png)

> **Abbildung 1-6.** Beispielszenario für Apps, die „Bereit für Cloud-DevOps“ sind, mit Windows-Containern und verwalteten Diensten

Darüber hinaus können Sie Ihre vorhandene Anwendung, die „Bereit für Cloud-DevOps“ ist, um einige Microservices für bestimmte Szenarien erweitern. Damit würden Sie teilweise die Ebene des cloudnativen „cloudoptimierten“ Modells erreichen, die aber nicht im Mittelpunkt der vorliegenden Anleitung steht.


## <a name="what-this-guide-does-not-cover"></a>Was in diesem Leitfaden nicht behandelt wird

Dieser Leitfaden behandelt eine bestimmte Teilmenge der in Abbildung 1-7 dargestellten Beispielszenarien. Dieser Leitfaden konzentriert sich ausschließlich auf Szenarien mit Übertragung und Verschiebung und letztlich auf das Modell „Bereit für Cloud-DevOps“. Im Modell „Bereit für Cloud-DevOps“ wird eine .NET Framework-Anwendung mithilfe von Windows-Containern und zusätzlichen Komponenten wie Überwachung und CI-/CD-Pipelines modernisiert. Jede Komponente ist wesentlich für die schnellere und flexiblere Bereitstellung von Anwendungen in der Cloud.

![Übertragen und Verschieben und Anfangsmodernisierung in Anwendungen, die „Bereit für Cloud-DevOps“ sind](./media/image1-7.png)

> **Abbildung 1-7.** Übertragen und Verschieben und Anfangsmodernisierung in Anwendungen, die „Bereit für Cloud-DevOps“ sind

Der Schwerpunkt dieses Leitfadens ist spezifisch. Hier erfahren Sie den Pfad ein, den Sie ergreifen können, um eine Lift- and -Shift mit Ihren vorhandenen .NET Anwendungen ohne Architektur und ohne codeänderungen zu erzielen. Letztlich gezeigt, wie Ihre Anwendung DevOps Cloudfähige vornehmen.

Dieses Handbuch ist nicht zum Arbeiten mit systemeigenen Cloud-Anwendungen, z. B. wie auf eine Architektur Microservices weiterentwickelt anzeigen Um Ihre Anwendungen neu zu strukturieren oder brandneue Anwendungen zu erstellen, die auf Microservices basieren, lesen Sie das E-Book [.NET Microservices: Architektur für containerisierte .NET-Anwendungen](https://aka.ms/microservicesebook).

### <a name="additional-resources"></a>Zusätzliche Ressourcen

- **Lebenszyklus der Docker-Anwendung mit Microsoft-Webplattform und Tools in Containern** (herunterladbares e-Book): [*https://aka.ms/dockerlifecycleebook*](https://aka.ms/dockerlifecycleebook)

- **.NET Microservices: Architektur für .NET Sammelartikeleinheit** (herunterladbares e-Book): [*https://aka.ms/microservicesebook*](https://aka.ms/microservicesebook)

- **Innovative Webanwendungen mit ASP.NET Core und Azure Architektur** (herunterladbares e-Book): [*https://aka.ms/webappebook*](https://aka.ms/webappebook)

## <a name="who-should-use-this-guide"></a>Zielgruppe dieses Leitfadens

Dieses Handbuch wurde für Entwicklern und Lösungsarchitekten vorhandene ASP.NET-Anwendungen modernisieren, die auf .NET Framework, für die verbesserte Flexibilität bei den Protokollversand und Anwendungen freigeben möchte geschrieben.

Möglicherweise finden Sie diesen Leitfaden auch nützlich, wenn Sie ein technischer Entscheidungsträger sind (z.B. ein Unternehmensarchitekt oder ein Entwicklungsleiter), der sich nur einen Überblick über die Vorteile verschaffen möchte, die durch die Verwendung von Windows-Containern und die Bereitstellung in der Cloud unter Verwendung von Microsoft Azure erzielt werden können.

## <a name="how-to-use-this-guide"></a>So verwenden Sie diesen Leitfaden

Dieser Leitfaden befasst sich mit dem „Warum“ (warum Sie Ihre vorhandenen Anwendungen modernisieren sollten) und mit den spezifischen Vorteilen, die Ihnen die Verwendung von Windows-Containern bietet, wenn Sie Ihre Apps in die Cloud verschieben. Der Inhalt der ersten Kapitel des Leitfadens richtet sich an Architekten und technische Entscheidungsträger, die sich einen Überblick verschaffen möchten, sich aber nicht auf die Umsetzung und technische Details konzentrieren müssen.

Im letzten Kapitel dieses Leitfadens werden mehrere exemplarische Vorgehensweisen vorgestellt, die sich auf spezifische Bereitstellungsszenarien konzentrieren. Dieses Handbuch bietet kürzere Versionen der exemplarischen Vorgehensweisen, um Szenarien zusammenzufassen und deren Vorteile zu markieren. Die vollständigen exemplarischen Vorgehensweisen befassen sich ausführlich mit den Einrichtungs- und Implementierungsdetails und werden als eine Gruppe von [Wiki-Beiträgen](https://github.com/dotnet-architecture/eShopModernizing/wiki) in dem gleichen öffentlichen [GitHub Repository](https://github.com/dotnet-architecture/eShopModernizing) veröffentlicht, in dem sich verwandte Beispiel-Apps befinden (siehe nächster Abschnitt). Das letzte Kapitel und die schrittweisen exemplarischen Wiki-Vorgehensweisen auf GitHub werden für Entwickler und Architekten, die sich auf Implementierungsdetails konzentrieren möchten, von größerem Interesse sein.

## <a name="sample-apps-for-modernizing-legacy-apps-eshopmodernizing"></a>Beispiel-Apps für die Modernisierung von Legacy-Apps: eShopModernizing

Das [eShopModernizing](https://github.com/dotnet-architecture/eShopModernizing)-Repository auf GitHub bietet zwei Beispielanwendungen, die monolithische Legacywebanwendungen simulieren. Eine Web-App wird unter Verwendung von ASP.NET MVC entwickelt, die zweite Web-App unter Verwendung von ASP.NET Web Forms. Beide Web-Apps basieren auf dem traditionellen .NET Framework. Diese Beispiel-Apps verwenden nicht .NET Core oder ASP.NET Core, da es sich dabei um vorhandene bzw. zu modernisierende .NET Framework-Anwendungen handelt.

Für beide Beispiel-Apps ist eine zweite Version mit modernisiertem Code verfügbar, die recht einfach ist. Der wichtigste Unterschied zwischen den App-Versionen besteht darin, dass die jeweils zweite Version Windows-Container als Bereitstellungsauswahl verwendet. Es gibt auch einige Ergänzungen zu den zweiten Versionen, wie Azure Storage Blobs für die Verwaltung von Images, Azure Active Directory für die Verwaltung der Sicherheit und Azure Application Insights für die Überwachung und Überprüfung der Anwendungen.

## <a name="send-your-feedback"></a>Senden Sie Ihr feedback

Dieses Handbuch wurde geschrieben, um die Optionen für die Verbesserung und Modernisierung .NET in vorhandene Webanwendungen zu verstehen. Der Leitfaden und die zugehörigen Anwendungsbeispiele werden ständig weiterentwickelt. Ihr Feedback ist Willkommen! Wenn Sie Anmerkungen dazu haben, wie dieser Leitfaden hilfreicher gestaltet werden könnte, senden Sie diese bitte an [dotnet-architecture-ebooks-feedback@service.microsoft.com](mailto:dotnet-architecture-ebooks-feedback@service.microsoft.com?subject=Feedback%20for%20.NET%20Container%20&%20Microservices%20Architecture%20book).

>[!div class="step-by-step"]
[Nächste](lift-and-shift-existing-apps-azure-iaas.md)
