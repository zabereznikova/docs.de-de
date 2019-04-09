---
title: Modernisieren von vorhandenen .NET Anwendungen mit Azure Cloud und Windows-Container (2. Auflage)
description: Informationen Sie zum übertragen und verschieben und modernisieren vorhandene Anwendungen zu Azure Cloud und Container mit diesem e-Book.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/28/2018
ms.openlocfilehash: ed291309d04e3e5bfed6c73cdf8a67b79431a363
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59156389"
---
# <a name="modernize-existing-net-applications-with-azure-cloud-and-windows-containers-2nd-edition"></a>Modernisieren vorhandener .NET-Anwendungen mit Azure-Cloud und Windows-Containern (2. Auflage)

![Titelbild der Leitfaden für .NET modernisieren Sie Anwendungen.](./media/index/web-application-guide-cover-image.png)

VERÖFFENTLICHT VON  
Microsoft Press und Microsoft DevDiv  
Geschäftsbereiche der Microsoft Corporation  
One Microsoft Way  
Redmond, Washington 98052-6399  

Copyright © 2018 by Microsoft Corporation  

Alle Rechte vorbehalten. Die Inhalte dieser Veröffentlichung dürfen in keiner Form und für keinen Zweck ohne die schriftliche Genehmigung des Herausgebers reproduziert werden.

Dieses Buch ist kostenlos in Form eines elektronischen Buchs (e-Book) über mehrere Kanäle bei Microsoft zur Verfügung wie z. B. <https://dot.net/architecture>.

Wenn Sie Fragen im Zusammenhang mit dieser Veröffentlichung haben, senden Sie eine E-Mail an [dotnet-architecture-ebooks-feedback@service.microsoft.com](mailto:dotnet-architecture-ebooks-feedback@service.microsoft.com?subject=Feedback%20for%20.NET%20Container%20&%20Microservices%20Architecture%20book).

Dieses Buch wird unverändert bereitgestellt und drückt die Ansichten und Meinungen des Autors aus. Die Ansichten, meinungen und Informationen, ausgedrückt in diesem Buch, einschließlich URLs und anderer Verweise auf Internetwebsites, können ohne vorherige Ankündigung geändert werden.

Einige der hier dargestellten Beispiele dienen nur zu Illustrationszwecken und sind fiktiv. Keinerlei Zuordnung oder Verbindung zu realen Gegebenheiten ist beabsichtigt oder sollte gefolgert werden.

Microsoft und die auf der Webseite „Marken“ unter <https://www.microsoft.com> aufgelisteten Marken sind Marken der Microsoft-Unternehmensgruppe. Alle anderen Marken sind Eigentum der jeweiligen Besitzer.

Autor:
> **Cesar De La Torre**, Senior PM, .NET Produkt .NET-Produktteam, Microsoft Corp.

Teilnehmer und Prüfer:
> **Scott Hunter**, Partner Director von PM, .NET-Team, Microsoft  
> **Paul Yuknewicz**, Principal PM Manager, Visual Studio-Tools-Team, Microsoft  
> **Lisa Guthrie**, Senior PM, Visual Studio-Tools-Team, Microsoft  
> **Ankit Asthana**, leitender PM-Manager, .NET-Team, Microsoft  
> **Unai Zorrilla**, leitender Entwickler, einfache Konzepte  
> **Javier Valero**, Chief Operating Officer bei Grupo Solutio  

## <a name="introduction"></a>Einführung

Wenn Sie modernisieren Sie Ihre Webanwendungen oder Dienste, und sie in die Cloud verschieben möchten, müssen Sie unbedingt vollständig auf Ihre apps überarbeiten. Neuentwurf von einer Anwendungs mithilfe eines fortschrittlichen Ansatzes wie Microservices ist nicht immer eine Option aufgrund der Kosten- und Zeitgründen. Je nach Art der Anwendung kann eine app überarbeiten auch nicht erforderlich sein. Um die Kosteneffizienz der Cloudmigrationsstrategie Ihres Unternehmens zu optimieren, ist es wichtig, die Bedürfnisse Ihres Unternehmens und die Anforderungen Ihrer Apps zu berücksichtigen. Sie müssen Folgendes ermitteln:

- Welche apps erfordern eine Transformation oder überarbeiten.

- Welche Apps müssen nur teilweise modernisiert werden?

- Welche Apps können direkt in die Cloud übertragen und verschoben werden?

## <a name="about-this-guide"></a>Über diesen Leitfaden

Dieser Leitfaden konzentriert sich hauptsächlich auf die anfängliche Modernisierung vorhandener Microsoft .NET Framework-Web- oder dienstorientierter Anwendungen, d. h. die Aktion eine Workload auf eine neuere oder modernere Umgebung verschieben, ohne den Code der Anwendung erheblich zu ändern und die grundlegende Architektur. 

Dieser Leitfaden erläutert auch die Vorteile der Verlagerung Ihrer Anwendungen in der Cloud und teilweise Modernisierung von Anwendungen durch einen bestimmten Satz von neuen Technologien und Ansätze wie Windows-Container und die zugehörigen Compute-Plattformen in Windows-Containern mit Unterstützung für Azure verwenden.

## <a name="path-to-the-cloud-for-existing-net-applications"></a>Pfad in die Cloud für vorhandene .NET-Anwendungen

Unternehmen entscheiden sich in der Regel für den Wechsel in die Cloud, um die Agilität und Geschwindigkeit zu erreichen, die sie für ihre Anwendungen erzielen können. Sie können Tausende von Servern (virtuellen Computern) in der Cloud innerhalb von Minuten einrichten, verglichen mit den Wochen, die normalerweise für die Einrichtung von lokalen Servern benötigt werden.

Es gibt keine einheitliche, standardisierte Strategie für die Migration von Anwendungen in die Cloud. Welche Migrationsstrategie für Sie die richtige ist, hängt von den Bedürfnissen und Prioritäten Ihres Unternehmens und der Art der Anwendungen ab, die Sie migrieren. Nicht alle Anwendungen rechtfertigen die Investition in einen Umstieg auf ein [PaaS](https://azure.microsoft.com/overview/what-is-paas/)-Modell (Platform-as-a-Service) oder in die Entwicklung eines [cloudnativen](https://www.gartner.com/doc/3181919/architect-design-cloudnative-applications) Anwendungsmodells. In vielen Fällen können Sie basierend auf Ihren Geschäftsanforderungen einen schrittweisen oder inkrementellen Ansatz wählen, um Ihre Ressourcen in die Cloud zu verschieben.

Für moderne Anwendungen mit den am besten geeignete langfristige Flexibilität und den Wert für die Organisation, können Sie profitieren von einer Investition in *cloudnative* Anwendungsarchitekturen. Allerdings ist der Schlüssel für Anwendungen, die bereits vorhandene sind oder Legacyressourcen nur sehr wenig Zeit und Geld (keine Änderung Neuentwurf oder Code) ausgeben, beim Verschieben sie in der Cloud, um signifikante Vorteile zu erzielen.

Abbildung 1-1 zeigt die möglichen Pfade, die Sie einschlagen können, wenn Sie vorhandene .NET-Anwendungen in inkrementellen Phasen in die Cloud verschieben.

 ![Modernisierungspfade für vorhandene .NET-Anwendungen und -Dienste](./media/image1-1.png)

> **(Abbildung 1-1)**. Modernisierungspfade für vorhandene .NET-Anwendungen und -Dienste

Jeder Migrationsansatz weist unterschiedliche Vorteile und Gründe für seine Anwendung auf. Sie können einen einzelnen Ansatz wählen, wenn Sie Anwendungen in die Cloud migrieren, oder bestimmte Komponenten aus mehreren Ansätzen auswählen. Einzelne Anwendungen sind nicht auf einen Ansatz oder Reifezustand beschränkt. Ein allgemeiner Hybridansatz würde beispielsweise bestimmte lokale Komponenten und andere Komponenten in der Cloud aufweisen.

Die Definition und kurzen Erklärung für jeden Reifegrad Anwendung lauten wie folgt:

**Ebene 1: Bereit für Cloudinfrastruktur** Anwendungen: Bei diesem Migrationsansatz einfach zu migrieren oder hosten Sie Ihre aktuellen lokalen Anwendungen zu einer Infrastruktur als Dienst ([IaaS](https://azure.microsoft.com/overview/what-is-iaas/)) Plattform. Ihre Apps weisen fast die gleiche Zusammensetzung wie zuvor auf, aber nun stellen Sie sie auf virtuellen Computern in der Cloud bereit.
Dieser einfache Typ einer Migration wird in der Regel in der Branche als "Lift & Shift." bezeichnet.

**Ebene 2: Cloud optimiert** Anwendungen: Auf dieser Ebene und weiterhin ohne Neuentwurf oder erhebliche Code ändern zu können erhalten Sie zusätzliche Vorteile aus Ihrer app in der Cloud mit modernen Technologien wie Container und zusätzliche in der Cloud verwaltete Dienste ausgeführt. Sie verbessern die Agilität Ihrer Anwendungen, um eine schnellere Bereitstellung leisten zu können, indem Sie Ihre DevOps-Prozesse (Enterprise Development Operations) verfeinern. Dies erreichen Sie mithilfe von Technologien wie Windows-Container, die Docker-Engine basiert. Container entfernen Sie die Reibung, die durch anwendungsabhängigkeiten verursacht wird, bei der Bereitstellung in mehreren Phasen. In diesem Reifegradmodell können Sie Container in IaaS oder PaaS bei der Verwendung von zusätzlichen als a-Service, Überwachung und continuous Integration/continuous Deployment-Pipelines (CI/CD) Zwischenspeichern in der Cloud verwaltete Dienste im Zusammenhang mit der Datenbanken.

Die dritte Reifestufe ist das ultimative Ziel in der Cloud, aber sie ist für viele Apps optional und stellt nicht der Hauptschwerpunkt dieses Leitfadens dar:

**Ebene 3: Cloudnative** Anwendungen: Diese Vorgehensweise bei der Migration wird in der Regel von geschäftlichen Erfordernissen bestimmt und zielt auf die Modernisierung Ihrer geschäftskritischen Anwendungen gesteuert werden. Auf dieser Stufe verwenden Sie PaaS-Dienste, um Ihre Apps auf PaaS-Computeplattformen zu verschieben. Sie implementieren [cloudnative](https://www.gartner.com/doc/3181919/architect-design-cloudnative-applications) Anwendungen und Microservicesarchitekturen, um Anwendungen mit langfristiger Agilität zu entwickeln und neue Grenzen für die Skalierung zu entdecken. Diese Art der Modernisierung erfordert in der Regel eine coudspezifische Architektur. Häufig muss neuer Code geschrieben werden, insbesondere, wenn der Übergang auf cloudnative Anwendungs- und auf Microservices basierende Modelle erfolgt. Dieser Ansatz kann Ihnen dabei helfen, Vorteile zu erzielen, die in Ihrer monolithischen und lokalen Anwendungsumgebung nur schwer zu erreichen sind.

Tabelle 1-1 beschreibt die wichtigsten Vorteile und Gründe für die Wahl der einzelnen Migrations- oder Modernisierungsansätze.

| **Bereit für Cloudinfrastruktur** <br /> *Lift & shift* | **Cloud-Optimized** <br /> *Modernisieren* | **Cloud-Native** <br /> *Modernisieren, überarbeiten und Schreiben* |
|---|---|---|
| **Computeziel der Anwendung** |
| Auf virtuellen Computern in Azure bereitgestellte Anwendungen | Monolithisch oder N-Tier-apps, die für Azure App Service, Azure Container-Instanz (ACI), virtuelle Computer bereitgestellt wird, mit dem Container, Azure Service Fabric oder AKS (Azure Kubernetes Service) | Microservices in Containern in Azure Kubernetes Service (AKS), Service Fabric und/oder serverlose Microservices, die basierend auf der Azure Functions. |
| **Datenziel** |
| SQL- oder eine beliebige relationale Datenbank auf einem virtuellen Computer | Verwaltete Azure SQL-Datenbankinstanz oder eine andere verwaltete Datenbank in der Cloud. | Strafzahlungen differenziertere Datenbanken pro Microservice, basierend auf Azure SQL-Datenbank, Azure Cosmos DB oder eine andere verwaltete Datenbank in der cloud |
| **Vorteile**|
| <li>Kein Code überarbeiten, werden keine neuen <li> Geringster Aufwand für eine schnelle Migration. <li> Kleinster gemeinsamen Nenner, der in Azure unterstützt wird. <li> Grundlegende Verfügbarkeitsgarantien. <li> Nach dem Wechsel in die Cloud ist es einfacher, noch mehr zu modernisieren. | <li> Keine Neuentwurf <li> Änderungen der minimalen Code-Konfiguration <li> Verbesserte Bereitstellung und DevOps-Agilität beim Release aufgrund von Containern. <li> Höhere Dichte und niedrigere Bereitstellungskosten. <li> Portabilität von Apps und Abhängigkeiten. <li> Die Flexibilität der hostziele: Methoden für PaaS oder IaaS | <li> Architekt für die Cloud, erhalten Sie die größten Vorteile aus der Cloud, aber neuer Code ist erforderlich. <li> Cloudnative Microservicesansätze. <li> Moderne unternehmenskritische Anwendungen, cloudrobust überaus skalierbarer <li> Vollständig verwaltete Dienste. <li> Optimiert für die Skalierung. <li> Optimiert für autonome Agilität durch Subsysteme. <li> Basiert auf Bereitstellung und DevOps. |
| **Herausforderungen** |
| <li> Geringerer Cloudwert, abgesehen von der Verschiebung der Betriebskosten oder der Schließung von Datencentern. <li> Wenig verwaltet wird: Ohne Betriebssystem oder Middleware Patchen; ggf. infrastrukturlösungen wie Terraform, Spinnaker oder Puppet verwenden werden. | <li> Das containerisieren ist ein zusätzlicher Schritt in der Lernkurve für Entwickler und IT-Betrieb <li> DevOps und CI/CD-Pipelines ist, in der Regel "muss" für diesen Ansatz. Wenn dies nicht der derzeit in der die Kultur der Organisation, möglicherweise eine zusätzliche Herausforderung| <li> Erfordert eine Neugestaltung für native Cloud-apps und Microservice-Architekturen und in der Regel erfordert erhebliche Code coderefactoring oder Neuerstellung beim modernisieren (erhöhter Zeit- und Kostenaufwand) <li> DevOps und CI/CD-Pipelines ist, in der Regel "muss" für diesen Ansatz. Wenn dies nicht der derzeit in der die Kultur der Organisation, möglicherweise eine zusätzliche Herausforderung|
> **Tabelle 1-1.** Vorteile und Herausforderungen von Modernisierungspfaden für vorhandene .NET-Anwendungen und -Dienste

### <a name="key-technologies-and-architectures-by-maturity-level"></a>Schlüsseltechnologien und -architekturen nach Reifegrad

.NET Framework-Anwendungen begannen ursprünglich mit .NET Framework Version 1.0, die Ende 2001 veröffentlicht wurde. Dann haben Unternehmen neuere Versionen (wie 2.0, 3.5 und .NET 4.x) verwendet. Die meisten dieser Anwendungen auf Windows Server und Internet Information Server (IIS) ausgeführt und verwendet eine relationale Datenbank, wie SQL Server, Oracle, MySQL oder beliebigen anderen RDBMS erfolgen.

Die meisten vorhandenen .NET-Anwendungen basieren heute auf .NET Framework 4.x oder sogar auf .NET Framework 3.5 und verwenden Webframeworks wie ASP.NET MVC, ASP.NET Web Forms, ASP.NET-Web-API, Windows Communication Foundation (WCF), ASP.NET SignalR oder ASP.NET Web Pages. Diese etablierten .NET Framework-Technologien sind von Windows abhängig. Diese Abhängigkeit muss unbedingt berücksichtigt werden, wenn Sie nur Legacy-Apps migrieren und minimale Änderungen an Ihrer Anwendungsinfrastruktur vornehmen möchten.

Abbildung 1-2 zeigt die primären Technologien und Architekturstile, die bei jedem der drei Cloudreifegrade verwendet werden:

![Primäre Technologien für jeden Reifegrad zur Modernisierung vorhandener .NET-Webanwendungen](./media/image1-2.png)

> **Abbildung 1 – 2.** Primäre Technologien für jeden Reifegrad zur Modernisierung vorhandener .NET-Webanwendungen

Abbildung 1-2 zeigt die gängigsten Szenarien. Es sind aber viele hybride und gemischte Varianten bezüglich der Architektur denkbar. Die Reifegradmodelle gelten beispielsweise nicht nur für monolithische Architekturen in vorhandenen Web-Apps, sondern auch für Dienstorientierung, n-schichtige und andere Architekturstilvarianten. Die höhere Fokus oder Prozent in eine oder andere Architekturtyp und verwandten Technologien bestimmt die allgemeine Reife Ihrer Anwendungen.

Jeder Reifegrad im Modernisierungsprozess ist mit den folgenden Schlüsseltechnologien und -ansätzen verbunden:

- **Bereit für Cloudinfrastruktur** ("zum erneuten Hosten" oder "Basic" lift & shift "): Als ersten Schritt möchten viele Organisationen nur schnell eine cloudmigrationsstrategie ausführen. In diesem Fall werden Anwendungen neu gehostet. Ein Großteil des erneuten Hostens kann automatisiert werden, indem [Azure Migrate](https://aka.ms/azuremigrate) verwendet wird, ein Dienst, der Anleitung, Einblicke und Mechanismen bietet, die benötigt werden, um Sie basierend auf Cloudtools wie [Azure Site Recovery](https://azure.microsoft.com/services/site-recovery/) und [Azure Database Migration Service](https://azure.microsoft.com/campaigns/database-migration/) bei der Migration nach Azure zu unterstützen. Sie können erneutes Hosten auch manuell einrichten, sodass Sie beim Verschieben von Legacy-Apps in die Cloud Infrastrukturdetails über Ihre Ressourcen erfahren können. Sie können z. B. Ihre Anwendungen für virtuelle Computer in Azure verschieben, mit nur wenig Änderungen wahrscheinlich mit nur geringen konfigurationsänderungen. Die Netzwerkfunktionalität ähnelt in diesem Fall einer lokalen Umgebung, insbesondere wenn Sie virtuelle Netzwerke in Azure erstellen.

- **Cloudoptimiert** (verwalteten Diensten und Windows-Containern): Dieses Modell geht es darum einige wichtige bereitstellungsoptimierungen um signifikante Vorteile aus der Cloud zu erhalten, ohne die Kernarchitektur der Anwendung ändern zu müssen. Der grundlegende Schritt hierbei besteht darin, Ihren vorhandenen .NET Framework-Anwendungen Unterstützung für [Windows-Container](https://docs.microsoft.com/virtualization/windowscontainers/about/) hinzuzufügen. Dieser wichtige Schritt (containerisierung) erfordert keine, berühren den Code, damit der gesamte übertragungs- und verschiebeaufwand gering ist. Sie können Tools wie [Image2Docker](https://github.com/docker/communitytools-image2docker-win) oder Visual Studio mit den Tools für [Docker](https://www.docker.com/) verwenden. Visual Studio wählt automatisch intelligente Standardeinstellungen für ASP.NET-Anwendungen und Windows Container-Images aus. Diese Tools bieten sowohl eine schnelle innere Schleife als auch einen schnellen Weg, um die Container in Azure zu übertragen. Ihre Agilität wird verbessert, wenn die Bereitstellung in mehreren Umgebungen erfolgt. Klicken Sie dann in die produktionsumgebung verschoben werden, Sie können Bereitstellen Ihrer Windows-Container [Azure-Web-App für Container](https://azure.microsoft.com/services/app-service/containers/), [Azure Container Instances (ACI) und Azure-VMs mit Windows Server 2016 und Container, wenn Sie einen IaaS-Ansatz bevorzugen. Für etwas komplexere Anwendungen mit mehreren Containern, in orchestratoren wie [Azure Service Fabric](https://azure.microsoft.com/services/service-fabric/) oder [Azure Kubernetes Service (AKS/ACS)](https://azure.microsoft.com/services/container-service/). Sie können während dieser ersten Modernisierung, auch Ressourcen hinzufügen, aus der Cloud, z.B. Überwachung mit Tools wie [Azure Application Insights](https://docs.microsoft.com/azure/application-insights/app-insights-overview); CI/CD-Pipelines für Ihre app-Lebenszyklen mit [Azure DevOps-Dienste](https://visualstudio.microsoft.com/team-services/); und viele weitere datenressourcendienste, die in Azure verfügbar sind. Beispielsweise können Sie eine monolithische Web-App., die ursprünglich unter Verwendung von traditionellem [ASP.NET Web Forms](https://www.asp.net/web-forms) oder [ASP.NET MVC](https://www.asp.net/mvc) entwickelt wurde, ändern, aber jetzt stellen Sie sie mit Hilfe von Windows-Containern bereit. Wenn Sie Windows-Container verwenden, sollten Sie Ihre Daten auch zu einer Datenbank in einer [verwalteten Azure SQL-Datenbank-Instanz](https://docs.microsoft.com/azure/sql-database/) migrieren, ohne die Kernarchitektur Ihrer Anwendung zu verändern.

- **Cloud-Native**: Wie eingeführt, sollten Sie sich vorstellen Informationen über die Architektur [cloudnative](https://www.gartner.com/doc/3181919/architect-design-cloudnative-applications) -Anwendungen, wenn Sie große und komplexe Anwendungen mit mehreren unabhängige Entwicklungsteams arbeiten, die auf verschiedene Microservices, die sein können, verwenden möchten entwickelt und unabhängig bereitgestellt. Darüber hinaus aufgrund granularized und unabhängige Skalierbarkeit pro Microservice. Diese Architekturansätze stehen vor sehr wichtig, Herausforderungen und Komplexität aber Cloudplattform mit erheblich vereinfacht werden und orchestratoren wie [Azure Kubernetes Service (AKS/ACS)](https://azure.microsoft.com/services/container-service/) (verwalteter kubernetes-Cluster), [Azure-Dienst Fabric und [Azure Functions](https://azure.microsoft.com/services/functions/) für eines serverlosen Ansatzes. Alle diese Ansätze (wie Microservices und serverlose) in der Regel müssen Sie sich für die Cloud entwerfen und Schreiben von neuem Code – Code, der an bestimmte PaaS-Plattformen angepasst ist, oder Code, der bestimmte Architekturen wie Microservices ausgerichtet ist.

Abbildung 1-3 zeigt die internen Technologien, die Sie für jeden Reifegrad verwenden können:

![Interne Technologien für jeden Modernisierungsreifegrad](./media/image1-3.png)

> **Abbildung 1 – 3.** Interne Technologien für jeden Modernisierungsreifegrad

## <a name="lift-and-shift-scenario"></a>Lift & Shift-Szenario

Beachten Sie bei der Migration mit Übertragung und Verschiebung, dass Sie in Ihren Anwendungsszenarien viele verschiedene Varianten von Übertragung und Verschiebung verwenden können. Wenn Sie Ihre Anwendung nur neu hosten, liegt möglicherweise ein Szenario wie in Abbildung 1-4 dargestellt vor, in dem Sie virtuelle Computer in der Cloud nur für Ihre Anwendung und für Ihren Datenbankserver verwenden.

![Beispiel für ein reines IaaS-Szenario in der Cloud](./media/image1-4.png)

> **Abbildung 1-4.** Beispiel für ein reines IaaS-Szenario in der Cloud

## <a name="modernization-scenarios"></a>Modernisierung-Szenarien

Modernisierung Szenarien müssen Sie eine reine Cloud optimierte Anwendung möglicherweise, die Elemente nur aus diesem Reifegrad verwendet. Möglicherweise verfügen Sie über eine Anwendung mit einigen Elementen aus der bereit für Cloud-Infrastruktur und andere Elemente in die Cloud optimierte (ein "auswählen" oder gemischtes Modell), wie in Abbildung 1 bis 5.

![Beispielauswahlszenario mit Datenbank unter IaaS, DevOps und Containerisierung von Ressourcen](./media/image1-5.png)

> **Abbildung 1 bis 5.** Beispielauswahlszenario mit Datenbank unter IaaS, DevOps und Containerisierung von Ressourcen

Als Nächstes als ideales Szenario für viele vorhandene .NET Framework-Anwendungen zu migrieren, könnten Sie einer Anwendung Cloudoptimierte abzurufenden bedeutende Vorteile aus wenig Aufwand migrieren. Dieser Ansatz wird Sie als eine mögliche zukünftige Entwicklung auch für Native Cloud. Abbildung 1-6 zeigt ein Beispiel.

![Beispiel-apps Cloudoptimierte-Szenario mit Windows-Containern und verwalteten Diensten](./media/image1-6.png)

> **Abbildung 1 bis 6.** Beispiel-apps Cloudoptimierte-Szenario mit Windows-Containern und verwalteten Diensten

Darüber hinaus können Sie Ihre vorhandene Cloud optimierte Anwendung durch einige microservices für bestimmte Szenarien erweitern. Dies würden Sie teilweise auf der Ebene des Cloudnativen Modell verschieben handelt es sich nicht im Mittelpunkt der vorliegenden Anleitung steht.

## <a name="what-this-guide-does-not-cover"></a>Was in diesem Leitfaden nicht behandelt wird

Dieser Leitfaden behandelt eine bestimmte Teilmenge der in Abbildung 1-7 dargestellten Beispielszenarien. Dieser Leitfaden konzentriert sich nur auf Lift & Shift-Szenarios und schließlich auf die Cloud optimierte Modell. Eine .NET Framework-Anwendung mithilfe von Windows-Containern und zusätzlichen Komponenten wie die Überwachung der modernisiert und CI/CD-pipelines, in die Cloud optimierte Modell. Jede Komponente ist wesentlich für die schnellere und flexiblere Bereitstellung von Anwendungen in der Cloud.

![Cloudnative wird in diesem Handbuch nicht behandelt.](./media/image1-7.png)

> **Abbildung 1 bis 7.** Cloudnative wird in diesem Handbuch nicht behandelt.

Der Schwerpunkt dieses Leitfadens ist spezifisch. Erfahren Sie, den Pfad an, die, den Sie ergreifen können, um eine Übertragung und Verschiebung Ihrer vorhandenen .NET-Anwendungen verwenden können, ohne Neuentwurf und ohne codeänderungen zu erzielen. Letzten Endes es erfahren Sie, wie Sie Ihre Anwendung Cloud optimiert.

Diesem Leitfaden können nicht Sie Gewusst wie: Erstellen Sie Native Cloudanwendungen, wie eine Microservices-Architektur weiterentwickeln. Um Ihre Anwendungen überarbeiten oder brandneue Anwendungen zu erstellen, die auf Microservices basieren, finden Sie im e-Book [.NET Microservices: Architektur für containerisierte .NET-Anwendungen](https://aka.ms/microservicesebook).

### <a name="additional-resources"></a>Zusätzliche Ressourcen

- **Containerisierter Docker-Anwendungslebenszyklus mit Microsoft-Plattform und-Tools** (herunterladbares e-Book) \
  [https://aka.ms/dockerlifecycleebook](https://aka.ms/dockerlifecycleebook)

- **.NET-Microservices: Architektur für containerisierte .NET-Anwendungen** (herunterladbares e-Book) \
  [https://aka.ms/microservicesebook](https://aka.ms/microservicesebook)

- **Entwerfen moderner Webanwendungen mit ASP.NET Core und Azure** (herunterladbares e-Book) \
  [https://aka.ms/webappebook](https://aka.ms/webappebook)

## <a name="who-should-use-this-guide"></a>Zielgruppe dieses Leitfadens

Dieses Handbuch wurde für Entwickler und Lösungsarchitekten, die zu modernisieren, vorhandene Webanwendungen in ASP.NET oder WCF-Diensten, die auf .NET Framework, für größere Flexibilität bei der Auslieferung und Freigeben von Anwendungen beruhen geschrieben.

Möglicherweise finden Sie diesen Leitfaden auch nützlich, wenn Sie ein technischer Entscheidungsträger sind (z.B. ein Unternehmensarchitekt oder ein Entwicklungsleiter), der sich nur einen Überblick über die Vorteile verschaffen möchte, die durch die Verwendung von Windows-Containern und die Bereitstellung in der Cloud unter Verwendung von Microsoft Azure erzielt werden können.

## <a name="how-to-use-this-guide"></a>So verwenden Sie diesen Leitfaden

Dieser Leitfaden befasst sich mit dem „Warum“ (warum Sie Ihre vorhandenen Anwendungen modernisieren sollten) und mit den spezifischen Vorteilen, die Ihnen die Verwendung von Windows-Containern bietet, wenn Sie Ihre Apps in die Cloud verschieben. Der Inhalt der ersten Kapitel des Leitfadens richtet sich an Architekten und technische Entscheidungsträger, die sich einen Überblick verschaffen möchten, sich aber nicht auf die Umsetzung und technische Details konzentrieren müssen.

Im letzten Kapitel dieses Leitfadens werden mehrere exemplarische Vorgehensweisen vorgestellt, die sich auf spezifische Bereitstellungsszenarien konzentrieren. Dieses Handbuch bietet kürzere Versionen der exemplarischen Vorgehensweisen, um die Szenarien zusammenzufassen und ihre Vorteile aufzuzeigen. Die vollständigen exemplarischen Vorgehensweisen befassen sich ausführlich mit den Einrichtungs- und Implementierungsdetails und werden als eine Gruppe von [Wiki-Beiträgen](https://github.com/dotnet-architecture/eShopModernizing/wiki) in dem gleichen öffentlichen [GitHub Repository](https://github.com/dotnet-architecture/eShopModernizing) veröffentlicht, in dem sich verwandte Beispiel-Apps befinden (siehe nächster Abschnitt). Das letzte Kapitel und die schrittweisen exemplarischen Wiki-Vorgehensweisen auf GitHub werden für Entwickler und Architekten, die sich auf Implementierungsdetails konzentrieren möchten, von größerem Interesse sein.

## <a name="sample-apps-for-modernizing-legacy-apps-eshopmodernizing"></a>Beispiel-Apps für die Modernisierung von Legacy-Apps: eShopModernizing

Das [eShopModernizing](https://github.com/dotnet-architecture/eShopModernizing)-Repository auf GitHub bietet zwei Beispielanwendungen, die monolithische Legacywebanwendungen simulieren. Eine Web-app wird mit ASP.NET MVC entwickelt; die zweite Web-app mit ASP.NET Web Forms entwickelt, und die dritte app ist eine N-Tier-app mit einer WinForms Client desktop-app eine WCF-Dienst-Back-End verwenden. Alle diese apps basieren auf dem herkömmlichen .NET Framework. Diese Beispiel-Apps verwenden nicht .NET Core oder ASP.NET Core, da es sich dabei um vorhandene bzw. zu modernisierende .NET Framework-Anwendungen handelt.

Diese Beispiel-apps ist eine zweite Version mit modernisiertem Code verfügbar, und das sind ziemlich einfach. Der wichtigste Unterschied zwischen den App-Versionen besteht darin, dass die jeweils zweite Version Windows-Container als Bereitstellungsauswahl verwendet. Es gibt auch einige Ergänzungen zu den zweiten Versionen, wie Azure Storage Blobs für die Verwaltung von Images, Azure Active Directory für die Verwaltung der Sicherheit und Azure Application Insights für die Überwachung und Überprüfung der Anwendungen.

## <a name="send-your-feedback"></a>Senden Sie uns Ihr Feedback

Dieses Handbuch wurde geschrieben, können Sie Ihre Möglichkeiten zur Verbesserung und Modernisierung vorhandene Webanwendungen für .NET zu verstehen. Der Leitfaden und die zugehörigen Anwendungsbeispiele werden ständig weiterentwickelt. Ihr Feedback ist Willkommen! Wenn Sie Anmerkungen dazu haben, wie dieser Leitfaden hilfreicher gestaltet werden könnte, senden Sie diese bitte an [dotnet-architecture-ebooks-feedback@service.microsoft.com](mailto:dotnet-architecture-ebooks-feedback@service.microsoft.com?subject=Feedback%20for%20.NET%20Container%20&%20Microservices%20Architecture%20book).

>[!div class="step-by-step"]
>[Weiter](lift-and-shift-existing-apps-azure-iaas.md)
