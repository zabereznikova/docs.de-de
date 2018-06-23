---
title: Aktualisieren von vorhandenen .NET Anwendungen mit Azure Cloud und Windows-Container (2. Edition)
description: Informationen Sie zum Heben und verschieben und modernisieren bestehende Anwendungen in die Azure-Cloud und der Container mit diesem e-Book.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 4/28/2018
ms.openlocfilehash: 10af3a8ce1b9f501d7b646c8d49fcecab29af821
ms.sourcegitcommit: c217b067985905cb21eafc5dd9a83568d7ff4e45
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/22/2018
ms.locfileid: "36314798"
---
# <a name="modernize-existing-net-applications-with-azure-cloud-and-windows-containers-2nd-edition"></a>Aktualisieren von vorhandenen .NET Anwendungen mit Azure-Cloud und Windows-Container (2. Edition)

![Titelbild](./media/cover.png)

VERÖFFENTLICHT VON  
Microsoft Press und Microsoft DevDiv  
Geschäftsbereiche der Microsoft Corporation  
One Microsoft Way  
Redmond, Washington 98052-6399  

Copyright © 2018 by Microsoft Corporation  

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

Wenn Sie entscheiden, Ihre Webanwendungen oder Dienste zu aktualisieren, und verschieben Sie sie in der Cloud, müssen Sie unbedingt Ihre apps vollständig neu entwerfe. Eine Anwendung mit einem erweiterten Ansatz wie Microservices Neuentwurf nicht immer eine Option aufgrund von Kosten und Zeit-Einschränkungen. Je nach Art der Anwendung kann eine app Neuentwurf auch nicht erforderlich sein. Um die Kosteneffizienz der Cloudmigrationsstrategie Ihres Unternehmens zu optimieren, ist es wichtig, die Bedürfnisse Ihres Unternehmens und die Anforderungen Ihrer Apps zu berücksichtigen. Sie müssen Folgendes ermitteln:

- Welche apps setzen eine Umwandlung oder Neuentwurf.

- Welche Apps müssen nur teilweise modernisiert werden?

- Welche Apps können direkt in die Cloud übertragen und verschoben werden?

## <a name="about-this-guide"></a>Über diesen Leitfaden

Dieses Handbuch konzentriert sich hauptsächlich auf anfängliche Modernisierung von vorhandenen Microsoft .NET Framework-Web- oder dienstorientierten Anwendungen bedeutet die Aktion eine arbeitsauslastung in einer neueren oder modernere verschieben, ohne den Code der Anwendung erheblich zu ändern und die grundlegende Architektur. 

Dieses Handbuch wird auch die Vorteile von apps in die Cloud verschieben und teilweise Modernisierung apps mit einem bestimmten Satz von neue Technologien und Ansätze, wie Windows-Containern und verwandte Compute-Plattformen in Azure unterstützen die Windows-Containern hervorgehoben.

## <a name="path-to-the-cloud-for-existing-net-applications"></a>Pfad in die Cloud für vorhandene .NET-Anwendungen

Unternehmen entscheiden sich in der Regel für den Wechsel in die Cloud, um die Agilität und Geschwindigkeit zu erreichen, die sie für ihre Anwendungen erzielen können. Sie können Tausende von Servern (virtuellen Computern) in der Cloud innerhalb von Minuten einrichten, verglichen mit den Wochen, die normalerweise für die Einrichtung von lokalen Servern benötigt werden.

Es gibt keine einheitliche, standardisierte Strategie für die Migration von Anwendungen in die Cloud. Welche Migrationsstrategie für Sie die richtige ist, hängt von den Bedürfnissen und Prioritäten Ihres Unternehmens und der Art der Anwendungen ab, die Sie migrieren. Nicht alle Anwendungen rechtfertigen die Investition in einen Umstieg auf ein [PaaS](https://azure.microsoft.com/overview/what-is-paas/)-Modell (Platform-as-a-Service) oder in die Entwicklung eines [cloudnativen](https://www.gartner.com/doc/3181919/architect-design-cloudnative-applications) Anwendungsmodells. In vielen Fällen können Sie basierend auf Ihren Geschäftsanforderungen einen schrittweisen oder inkrementellen Ansatz wählen, um Ihre Ressourcen in die Cloud zu verschieben.

Für moderne Anwendungen mit dem am besten langfristigen Flexibilität und der Wert für die Organisation, profitieren Sie möglicherweise in investieren *Cloud systemeigenen* Anwendungsarchitektur. Allerdings ist der Schlüssel für Anwendungen, die vorhanden sind oder ältere Bestand, kürzester Zeit und Geld (keine Änderung Neuentwurf oder Code) ausgeben, während Sie sie in der Cloud bedeutende Vorteile realisieren verschieben.

Abbildung 1-1 zeigt die möglichen Pfade, die Sie einschlagen können, wenn Sie vorhandene .NET-Anwendungen in inkrementellen Phasen in die Cloud verschieben.

 ![Modernisierungspfade für vorhandene .NET-Anwendungen und -Dienste](./media/image1-1.png)

> **(Abbildung 1-1)**. Modernisierungspfade für vorhandene .NET-Anwendungen und -Dienste

Jeder Migrationsansatz weist unterschiedliche Vorteile und Gründe für seine Anwendung auf. Sie können einen einzelnen Ansatz wählen, wenn Sie Anwendungen in die Cloud migrieren, oder bestimmte Komponenten aus mehreren Ansätzen auswählen. Einzelne Anwendungen sind nicht auf einen Ansatz oder Reifezustand beschränkt. Ein allgemeiner Hybridansatz würde beispielsweise bestimmte lokale Komponenten und andere Komponenten in der Cloud aufweisen.

Die Definition und eine kurze Erklärung für jede Anwendung Reifegrad lauten wie folgt:

**Ebene 1: Cloud-Infrastruktur bereit** Anwendungen: Bei dieser Vorgehensweise Migration Sie einfach migrieren oder zum erneuten Hosten Ihrer aktuellen auf lokaler Anwendungen unter Verwendung einer Infrastruktur als Dienst ([IaaS](https://azure.microsoft.com/overview/what-is-iaas/)) Plattform. Ihre Apps weisen fast die gleiche Zusammensetzung wie zuvor auf, aber nun stellen Sie sie auf virtuellen Computern in der Cloud bereit.
Mit diesem einfachen Typ der Migration wird in der Regel in der Branche als "Lift & verschieben." bezeichnet.

**Ebene 2: Cloud optimierte** Anwendungen: auf dieser Ebene und weiterhin ohne Neuentwurf oder erhebliche Code ändern, erhalten Sie zusätzliche Vorteile aus Ihrer app in der Cloud mit modernen Technologien wie Container und zusätzliche ausgeführt Cloud-verwalteten Dienste. Sie verbessern die Agilität Ihrer Anwendungen, um eine schnellere Bereitstellung leisten zu können, indem Sie Ihre DevOps-Prozesse (Enterprise Development Operations) verfeinern. Sie erreichen dies durch Verwendung von Technologien wie Windows-Container, basierend auf den Docker-Modul. Entfernen Sie die Unstimmigkeiten, die von der anwendungsabhängigkeiten verursacht wird, während der Bereitstellung in mehreren Phasen Container. In diesem Reifegradmodell können Sie Container unter IaaS bereitstellen, oder PaaS bei der Verwendung zusätzliche Cloud-verwalteten Dienste im Zusammenhang mit Datenbanken, als ein Dienst, Überwachung und fortlaufende Integration/dauerhafte Bereitstellung-Pipelines (CI/CD) zwischenspeichern.

Die dritte Reifestufe ist das ultimative Ziel in der Cloud, aber sie ist für viele Apps optional und stellt nicht der Hauptschwerpunkt dieses Leitfadens dar:

**Ebene 3: Cloud systemeigenen** Anwendungen: Diese Vorgehensweise bei der Migration wird in der Regel durch die Anforderungen Ihres Unternehmens und Ziele, die Ihre unternehmenswichtigen Anwendungen Modernisierung gesteuert. Auf dieser Stufe verwenden Sie PaaS-Dienste, um Ihre Apps auf PaaS-Computeplattformen zu verschieben. Sie implementieren [cloudnative](https://www.gartner.com/doc/3181919/architect-design-cloudnative-applications) Anwendungen und Microservicesarchitekturen, um Anwendungen mit langfristiger Agilität zu entwickeln und neue Grenzen für die Skalierung zu entdecken. Diese Art der Modernisierung erfordert in der Regel eine coudspezifische Architektur. Häufig muss neuer Code geschrieben werden, insbesondere, wenn der Übergang auf cloudnative Anwendungs- und auf Microservices basierende Modelle erfolgt. Dieser Ansatz kann Ihnen dabei helfen, Vorteile zu erzielen, die in Ihrer monolithischen und lokalen Anwendungsumgebung nur schwer zu erreichen sind.

Tabelle 1-1 beschreibt die wichtigsten Vorteile und Gründe für die Wahl der einzelnen Migrations- oder Modernisierungsansätze.

| **Bereit für Cloudinfrastruktur** <br /> *Übertragen und verschieben* | **Cloud optimierten-** <br /> *Modernisieren* | **Cloud-systemeigen** <br /> *Modernisieren, neu entwerfe und Schreiben* |
|---|---|---|
| **Computeziel der Anwendung** |
| Auf virtuellen Computern in Azure bereitgestellte Anwendungen | Aufgrund eines monolithischen oder N-Tier-apps, die Azure App Service, Azure-Container-Instanz (ACI), virtuelle Computer bereitgestellt wird, mit der Container, Azure Service Fabric oder so (Azure-Kubernetes-Dienst) | Datenvolumes Microservices Azure Kubernetes Service (so), Service Fabric und/oder serverlose Microservices basierend auf Azure-Funktionen. |
| **Datenziel** |
| SQL- oder eine beliebige relationale Datenbank auf einem virtuellen Computer | Azure SQL-Datenbank verwaltete Instanz oder eine andere verwaltete Datenbank in der Cloud. | Verlangt Körnung Datenbanken pro Microservice, basierend auf Azure SQL-Datenbank, Azure-Cosmos-Datenbank oder eine andere verwaltete Datenbank in der cloud |
| **Vorteile**|
| <li>Kein Neuentwurf, werden keine neuen code <li> Geringster Aufwand für eine schnelle Migration. <li> Kleinster gemeinsamen Nenner, der in Azure unterstützt wird. <li> Grundlegende Verfügbarkeitsgarantien. <li> Nach dem Wechsel in die Cloud ist es einfacher, noch mehr zu modernisieren. | <li> Keine Neuentwurf <li> Minimale Code/Config-Änderungen <li> Verbesserte Bereitstellung und DevOps-Agilität beim Release aufgrund von Containern. <li> Höhere Dichte und niedrigere Bereitstellungskosten. <li> Portabilität von Apps und Abhängigkeiten. <li> Flexibilität der Host-Ziele: PaaS Vorgehensweisen oder IaaS | <li> Architekt für die Cloud erhalten Sie die beste Vorteile aus der Cloud jedoch neue Code ist erforderlich. <li> Cloudnative Microservicesansätze. <li> Moderne unternehmenswichtige Anwendungen Cloud robusten hyper skalierbar <li> Vollständig verwaltete Dienste. <li> Optimiert für die Skalierung. <li> Optimiert für autonome Agilität durch Subsysteme. <li> Basiert auf Bereitstellung und DevOps. |
| **Herausforderungen** |
| <li> Geringerer Cloudwert, abgesehen von der Verschiebung der Betriebskosten oder der Schließung von Datencentern. <li> Nur wenig verwaltet wird: keine Betriebssystem- oder Middleware Patchen; möglicherweise-infrastrukturlösungen, wie Terraform, Spinnaker oder Puppet verwenden | <li> Containerizing stellt einen zusätzlichen Schritt in den Lernaufwand für Entwickler und IT-Betrieb <li> DevOps und CI-CD-Pipelines ist in der Regel "erforderlich" für diesen Ansatz. Wenn dies nicht der momentan in der Kultur der Organisation vorhanden, ist es möglicherweise eine weitere Herausforderung| <li> Erfordert eine Reihe für Cloud-apps, systemeigene und Microservice Architekturen und in der Regel erfordert erhebliche Code Umgestalten, oder wenn Modernisierung umschreiben (mehr Zeit und Geld) <li> DevOps und CI-CD-Pipelines ist in der Regel "erforderlich" für diesen Ansatz. Wenn dies nicht der momentan in der Kultur der Organisation vorhanden, ist es möglicherweise eine weitere Herausforderung|
> **Tabelle 1-1.** Vorteile und Herausforderungen von Modernisierungspfaden für vorhandene .NET-Anwendungen und -Dienste

### <a name="key-technologies-and-architectures-by-maturity-level"></a>Schlüsseltechnologien und -architekturen nach Reifegrad

.NET Framework-Anwendungen begannen ursprünglich mit .NET Framework Version 1.0, die Ende 2001 veröffentlicht wurde. Dann haben Unternehmen neuere Versionen (wie 2.0, 3.5 und .NET 4.x) verwendet. Die meisten dieser Anwendungen auf Windows Server und Internet Information Server (IIS) ausgeführt, und eine relationale Datenbank, wie SQL Server, Oracle, MySQL oder eine beliebige andere RDBMS verwendet.

Die meisten vorhandenen .NET-Anwendungen basieren heute auf .NET Framework 4.x oder sogar auf .NET Framework 3.5 und verwenden Webframeworks wie ASP.NET MVC, ASP.NET Web Forms, ASP.NET-Web-API, Windows Communication Foundation (WCF), ASP.NET SignalR oder ASP.NET Web Pages. Diese etablierten .NET Framework-Technologien sind von Windows abhängig. Diese Abhängigkeit muss unbedingt berücksichtigt werden, wenn Sie nur Legacy-Apps migrieren und minimale Änderungen an Ihrer Anwendungsinfrastruktur vornehmen möchten.

Abbildung 1-2 zeigt die primären Technologien und Architekturstile, die bei jedem der drei Cloudreifegrade verwendet werden:

![Primäre Technologien für jeden Reifegrad zur Modernisierung vorhandener .NET-Webanwendungen](./media/image1-2.png)

> **Abbildung 1-2.** Primäre Technologien für jeden Reifegrad zur Modernisierung vorhandener .NET-Webanwendungen

Abbildung 1-2 zeigt die gängigsten Szenarien. Es sind aber viele hybride und gemischte Varianten bezüglich der Architektur denkbar. Die Reifegradmodelle gelten beispielsweise nicht nur für monolithische Architekturen in vorhandenen Web-Apps, sondern auch für Dienstorientierung, n-schichtige und andere Architekturstilvarianten. Die höhere Fokus oder den Prozentsatz für einen oder eine andere Architektur und verwandten Technologien bestimmt insgesamt Entwicklungsstands Ihrer Anwendungen.

Jeder Reifegrad im Modernisierungsprozess ist mit den folgenden Schlüsseltechnologien und -ansätzen verbunden:

- **Cloud-Infrastruktur einsatzfähige** (zum erneuten Hosten oder Basic lift & verschieben): als ersten Schritt viele Organisationen möchten nur eine Migrationsstrategie für Cloud schnell ausgeführt werden. In diesem Fall werden Anwendungen neu gehostet. Ein Großteil des erneuten Hostens kann automatisiert werden, indem [Azure Migrate](https://aka.ms/azuremigrate) verwendet wird, ein Dienst, der Anleitung, Einblicke und Mechanismen bietet, die benötigt werden, um Sie basierend auf Cloudtools wie [Azure Site Recovery](https://azure.microsoft.com/services/site-recovery/) und [Azure Database Migration Service](https://azure.microsoft.com/campaigns/database-migration/) bei der Migration nach Azure zu unterstützen. Sie können erneutes Hosten auch manuell einrichten, sodass Sie beim Verschieben von Legacy-Apps in die Cloud Infrastrukturdetails über Ihre Ressourcen erfahren können. Sie können z. B. Ihre Anwendungen auf virtuellen Computern in Azure verschieben, mit einem geringen Änderung-wahrscheinlich mit nur geringfügigen Änderungen. Die Netzwerkfunktionalität ähnelt in diesem Fall einer lokalen Umgebung, insbesondere wenn Sie virtuelle Netzwerke in Azure erstellen.

- **Cloud-optimierten** (Managed Services und Windows-Container): Dieses Modell ist, stellt einige wichtige Bereitstellung Optimierungen, einige bedeutende Vorteile aus der Cloud ohne Änderung der Kernarchitektur von der Anwendung zu erhalten. Der grundlegende Schritt hierbei besteht darin, Ihren vorhandenen .NET Framework-Anwendungen Unterstützung für [Windows-Container](https://docs.microsoft.com/virtualization/windowscontainers/about/) hinzuzufügen. Berühren den Code, damit die gesamte Lift- and -Shift-Aufwand leuchtet erfordert diesen wichtige Schritt (Containerization). Sie können Tools wie [Image2Docker](https://github.com/docker/communitytools-image2docker-win) oder Visual Studio mit den Tools für [Docker](https://www.docker.com/) verwenden. Visual Studio wählt automatisch intelligente Standardeinstellungen für ASP.NET-Anwendungen und Windows Container-Images aus. Diese Tools bieten sowohl eine schnelle innere Schleife als auch einen schnellen Weg, um die Container in Azure zu übertragen. Ihre Agilität wird verbessert, wenn die Bereitstellung in mehreren Umgebungen erfolgt. Klicken Sie dann, bis hin zur Produktion verschieben, können Sie bereitstellen Ihrer Windows-Containern zu [Azure-Web-App für Container](https://azure.microsoft.com/en-us/services/app-service/containers/), [Azure-Container-Instanzen (ACI) und Azure virtuelle Computer mit Windows Server 2016 und Container, wenn Sie einen IaaS-Ansatz bevorzugen. Für etwas komplexer Multi containeranwendungen in Orchestrators wie [Azure Service Fabric](https://azure.microsoft.com/services/service-fabric/) oder [Azure Kubernetes Service (so/ACS)](https://azure.microsoft.com/en-us/services/container-service/). Während dieser ersten Modernisierung können Sie auch Ressourcen aus der Cloud hinzufügen, z.B. Überwachung mit Tools wie [Azure Application Insights](https://docs.microsoft.com/azure/application-insights/app-insights-overview), CI-/CD-Pipelines für Ihre App-Lebenszyklen mit [Visual Studio Team Services](https://visualstudio.microsoft.com/team-services/) und viele weitere Datenressourcendienste, die in Azure verfügbar sind. Beispielsweise können Sie eine monolithische Web-App., die ursprünglich unter Verwendung von traditionellem [ASP.NET Web Forms](https://www.asp.net/web-forms) oder [ASP.NET MVC](https://www.asp.net/mvc) entwickelt wurde, ändern, aber jetzt stellen Sie sie mit Hilfe von Windows-Containern bereit. Wenn Sie Windows-Container verwenden, sollten Sie Ihre Daten auch zu einer Datenbank in einer [verwalteten Azure SQL-Datenbank-Instanz](https://docs.microsoft.com/azure/sql-database/) migrieren, ohne die Kernarchitektur Ihrer Anwendung zu verändern.

- **Cloud-systemeigenen**: wie eingeführt, sollten Sie sich vorstellen Architektur [Cloud systemeigenen](https://www.gartner.com/doc/3181919/architect-design-cloudnative-applications) Anwendungen durch, wenn große und komplexe Anwendungen mit mehrere unabhängige Entwicklungsteams arbeiten auf das Ziel verschiedene Microservices, die entwickelt und autonom bereitgestellt werden können. Darüber hinaus aufgrund granularized und unabhängige Skalierbarkeit pro Microservice. Diese Architektur Ansätze sind sehr wichtig Herausforderungen und die Komplexität, aber mithilfe cloudbasierter PaaS erheblich vereinfacht werden und Orchestrators wie [Azure Kubernetes Service (so/ACS)](https://azure.microsoft.com/en-us/services/container-service/) (verwaltete Kubernetes), [Azure-Dienst Fabric, und [Azure Funktionen](https://azure.microsoft.com/services/functions/) serverlose vor. Alle diese Ansätze (z. B. Microservices und serverlose) in der Regel müssen Sie für die Cloud zu entwickeln und Schreiben von Code: Code, der für bestimmte PaaS-Plattformen angepasst ist, oder Code, der bestimmte Architekturen, wie etwa Microservices entspricht.

Abbildung 1-3 zeigt die internen Technologien, die Sie für jeden Reifegrad verwenden können:

![Interne Technologien für jeden Modernisierungsreifegrad](./media/image1-3.png)

> **Abbildung 1-3.** Interne Technologien für jeden Modernisierungsreifegrad

## <a name="lift-and-shift-scenario"></a>Lift- and -shift-Szenario

Beachten Sie bei der Migration mit Übertragung und Verschiebung, dass Sie in Ihren Anwendungsszenarien viele verschiedene Varianten von Übertragung und Verschiebung verwenden können. Wenn Sie Ihre Anwendung nur neu hosten, liegt möglicherweise ein Szenario wie in Abbildung 1-4 dargestellt vor, in dem Sie virtuelle Computer in der Cloud nur für Ihre Anwendung und für Ihren Datenbankserver verwenden.

![Beispiel für ein reines IaaS-Szenario in der Cloud](./media/image1-4.png)

> **Abbildung 1-4.** Beispiel für ein reines IaaS-Szenario in der Cloud

## <a name="modernization-scenarios"></a>Modernisierung-Szenarien

Bei Modernisierung-Szenarien müssen Sie gegebenenfalls eine reine Cloud-optimierten Anwendung, die nur von diesem Reifegrad Elemente verwendet. Oder Sie müssen möglicherweise eine Intermediate-Status-Anwendung mit einigen Elementen aus der Cloud-Infrastruktur bereit und andere Elemente aus der Cloud-optimierte (einen "auswählen" oder ein gemischtes Modell), wie in Abbildung 1 bis 5.

![Beispielauswahlszenario mit Datenbank unter IaaS, DevOps und Containerisierung von Ressourcen](./media/image1-5.png)

> **Abbildung 1-5.** Beispielauswahlszenario mit Datenbank unter IaaS, DevOps und Containerisierung von Ressourcen

Als Nächstes als idealerweise für viele vorhandene .NET Framework-Anwendungen zu migrieren, konnte Sie einer Cloud-optimierten-Anwendung so wenig Arbeit bedeutende Vorteile ab migriert werden. Dieser Ansatz legt außerdem Sie für Cloud-systemeigen als eine mögliche künftige Entwicklung. Abbildung 1-6 zeigt ein Beispiel.

![Cloud-optimierten apps von Beispielszenario mit Windows-Containern und verwaltete Dienste](./media/image1-6.png)

> **Abbildung 1-6.** Cloud-optimierten apps von Beispielszenario mit Windows-Containern und verwaltete Dienste

Gehen noch weiter, konnte Sie eine vorhandene Cloud-optimierten Anwendung durch Hinzufügen von wenigen Microservices für bestimmte Szenarien erweitern. Dies würden Sie teilweise auf die Ebene der systemeigenen Cloud-Modell, Verschieben der nicht das Hauptaugenmerk der Anleitung vorhanden ist.


## <a name="what-this-guide-does-not-cover"></a>Was in diesem Leitfaden nicht behandelt wird

Dieser Leitfaden behandelt eine bestimmte Teilmenge der in Abbildung 1-7 dargestellten Beispielszenarien. Dieses Handbuch konzentriert sich nur auf Lift- and -Shift-Szenarien und schließlich auf dem Cloud-optimierten-Modell. Im Modell Cloudoptimiertes ist eine .NET Framework-Anwendung mithilfe von Windows-Container sowie zusätzliche Komponenten wie Überwachung modernisiert und pipelines CI-CD. Jede Komponente ist wesentlich für die schnellere und flexiblere Bereitstellung von Anwendungen in der Cloud.

![Cloud-systemeigenen ist in diesem Handbuch nicht behandelt.](./media/image1-7.png)

> **Abbildung 1-7.** Cloud-systemeigenen ist in diesem Handbuch nicht behandelt.

Der Schwerpunkt dieses Leitfadens ist spezifisch. Hier erfahren Sie den Pfad ein, den Sie ergreifen können, um eine Lift- and -Shift mit Ihren vorhandenen .NET Anwendungen ohne Neuentwurf und ohne codeänderungen zu erreichen. Letztlich er zeigt, wie eine Anwendung die Cloud optimierten.

Dieses Handbuch ist nicht zum Erstellen von systemeigenen Cloud-Anwendungen, z. B. wie auf eine Architektur Microservices weiterentwickelt anzeigen Um Ihre Anwendungen neu entwerfe oder völlig neue Anwendungen erstellen, die auf Microservices basieren, finden Sie unter der e-Book [.NET Microservices: Architektur für .NET Sammelartikeleinheit](https://aka.ms/microservicesebook).

### <a name="additional-resources"></a>Zusätzliche Ressourcen

- **Lebenszyklus der Docker-Anwendung mit Microsoft-Webplattform und Tools in Containern** (herunterladbares e-Book): [*https://aka.ms/dockerlifecycleebook*](https://aka.ms/dockerlifecycleebook)

- **.NET Microservices: Architektur für .NET Sammelartikeleinheit** (herunterladbares e-Book): [*https://aka.ms/microservicesebook*](https://aka.ms/microservicesebook)

- **Innovative Webanwendungen mit ASP.NET Core und Azure Architektur** (herunterladbares e-Book): [*https://aka.ms/webappebook*](https://aka.ms/webappebook)

## <a name="who-should-use-this-guide"></a>Zielgruppe dieses Leitfadens

Dieses Handbuch wurde für Entwicklern und Lösungsarchitekten modernisieren vorhandenen ASP.NET-Webanwendungen oder WCF-Dienste, die auf .NET Framework, für die verbesserte Flexibilität im für den Vertrieb und Freigeben von Anwendungen basieren möchte geschrieben.

Möglicherweise finden Sie diesen Leitfaden auch nützlich, wenn Sie ein technischer Entscheidungsträger sind (z.B. ein Unternehmensarchitekt oder ein Entwicklungsleiter), der sich nur einen Überblick über die Vorteile verschaffen möchte, die durch die Verwendung von Windows-Containern und die Bereitstellung in der Cloud unter Verwendung von Microsoft Azure erzielt werden können.

## <a name="how-to-use-this-guide"></a>So verwenden Sie diesen Leitfaden

Dieser Leitfaden befasst sich mit dem „Warum“ (warum Sie Ihre vorhandenen Anwendungen modernisieren sollten) und mit den spezifischen Vorteilen, die Ihnen die Verwendung von Windows-Containern bietet, wenn Sie Ihre Apps in die Cloud verschieben. Der Inhalt der ersten Kapitel des Leitfadens richtet sich an Architekten und technische Entscheidungsträger, die sich einen Überblick verschaffen möchten, sich aber nicht auf die Umsetzung und technische Details konzentrieren müssen.

Im letzten Kapitel dieses Leitfadens werden mehrere exemplarische Vorgehensweisen vorgestellt, die sich auf spezifische Bereitstellungsszenarien konzentrieren. Dieses Handbuch bietet kürzere Versionen der exemplarischen Vorgehensweisen, um Szenarien zusammenzufassen und deren Vorteile zu markieren. Die vollständigen exemplarischen Vorgehensweisen befassen sich ausführlich mit den Einrichtungs- und Implementierungsdetails und werden als eine Gruppe von [Wiki-Beiträgen](https://github.com/dotnet-architecture/eShopModernizing/wiki) in dem gleichen öffentlichen [GitHub Repository](https://github.com/dotnet-architecture/eShopModernizing) veröffentlicht, in dem sich verwandte Beispiel-Apps befinden (siehe nächster Abschnitt). Das letzte Kapitel und die schrittweisen exemplarischen Wiki-Vorgehensweisen auf GitHub werden für Entwickler und Architekten, die sich auf Implementierungsdetails konzentrieren möchten, von größerem Interesse sein.

## <a name="sample-apps-for-modernizing-legacy-apps-eshopmodernizing"></a>Beispiel-Apps für die Modernisierung von Legacy-Apps: eShopModernizing

Das [eShopModernizing](https://github.com/dotnet-architecture/eShopModernizing)-Repository auf GitHub bietet zwei Beispielanwendungen, die monolithische Legacywebanwendungen simulieren. Eine Web-app wird mithilfe von ASP.NET MVC entwickelt; die zweite Web-app mithilfe von ASP.NET Web Forms entwickelt, und die dritte app ist eine N-Tier-Anwendung mit einer WinForms Client desktop-app nutzen eines WCF-Dienst Back-Ends. Alle diese apps basieren auf herkömmliche .NET Framework. Diese Beispiel-Apps verwenden nicht .NET Core oder ASP.NET Core, da es sich dabei um vorhandene bzw. zu modernisierende .NET Framework-Anwendungen handelt.

Diese Beispiel-apps eine zweite Version, mit der moderneres Code und dem Recht einfach. Der wichtigste Unterschied zwischen den App-Versionen besteht darin, dass die jeweils zweite Version Windows-Container als Bereitstellungsauswahl verwendet. Es gibt auch einige Ergänzungen zu den zweiten Versionen, wie Azure Storage Blobs für die Verwaltung von Images, Azure Active Directory für die Verwaltung der Sicherheit und Azure Application Insights für die Überwachung und Überprüfung der Anwendungen.

## <a name="send-your-feedback"></a>Senden Sie Ihr feedback

Dieses Handbuch wurde geschrieben, um die Optionen für die Verbesserung und Modernisierung .NET in vorhandene Webanwendungen zu verstehen. Der Leitfaden und die zugehörigen Anwendungsbeispiele werden ständig weiterentwickelt. Ihr Feedback ist Willkommen! Wenn Sie Anmerkungen dazu haben, wie dieser Leitfaden hilfreicher gestaltet werden könnte, senden Sie diese bitte an [dotnet-architecture-ebooks-feedback@service.microsoft.com](mailto:dotnet-architecture-ebooks-feedback@service.microsoft.com?subject=Feedback%20for%20.NET%20Container%20&%20Microservices%20Architecture%20book).

>[!div class="step-by-step"]
[Nächste](lift-and-shift-existing-apps-azure-iaas.md)
