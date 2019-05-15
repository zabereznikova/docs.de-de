---
title: Schritte im Outer-Loop-DevOps-Workflow für eine Docker-Anwendung
description: Lernen Sie die Schritte für die "äußere"Schleife des DevOps-Workflows
ms.date: 02/15/2019
ms.openlocfilehash: 194786a90fc02801211c7614eb632392d67f0109
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65641057"
---
# <a name="steps-in-the-outer-loop-devops-workflow-for-a-docker-application"></a>Schritte im Outer-Loop-DevOps-Workflow für eine Docker-Anwendung

Abbildung 5 – 1 zeigt ein End-to-End-Darstellung der Schritte, die mit der äußeren Schleife DevOps-Workflow.

![Dieses Diagramm zeigt die "äußere Schleife" von DevOps. Wenn Code per Push an das Repository übertragen wird, eine CI-Pipeline wird gestartet und beginnt dann die CD-Pipeline, in dem die Anwendung bereitgestellt wird. Von bereitgestellten Anwendungen gesammelten Metriken werden eingelesen, wieder in der arbeitsauslastung "Entwicklung", die "innere Schleife", wo auftritt, müssen Entwicklungsteams tatsächliche Daten, die auf Benutzer und die geschäftlichen Anforderungen zu reagieren.](./media/image1.png)

**Abbildung 5-1**. Outer-Loop-DevOps-Workflow für Docker-Anwendungen mit Microsoft-tools

Nun sehen wir uns die einzelnen Schritte ausführlicher.

## <a name="step-1-inner-loop-development-workflow"></a>Schritt 1: Innere Schleife-Entwicklungsworkflow

Dadurch werden ausführlich in Kapitel 4, aber Zusammenfassend lässt sich sagen, hier ist die äußere Schleife, dem Moment beginnt an dem ein Entwickler Code auf das Quellcodeverwaltungssystem (z. B. Git) initiieren von Aktionen für CI-Pipeline überträgt.

## <a name="step-2-source-code-control-integration-and-management-with-azure-devops-services-and-git"></a>Schritt 2: Integration der Quellcodeverwaltung und Verwaltung mit Azure DevOps-Services und Git

In diesem Schritt benötigen Sie ein Versionskontrollsystem eine konsolidierte Version des gesamten Codes, die von den anderen Entwicklern im Team zu erfassen.

Auch wenn die quellcodeverwaltung (SCC) und der Quellcode-Management-Blut die meisten Entwickler beim Erstellen von Docker-Anwendungen in einer DevOps-Lebenszyklus durchlaufen scheint, ist es wichtig, hervorzuheben, dass Sie die Docker-Images mit der Anwendung nicht senden müssen direkt in der globalen Docker-Registrierung (z.B. Azure Container Registry oder Docker Hub) aus dem Computer des Entwicklers. Im Gegenteil, müssen der Docker-Images zur Freigabe in produktionsumgebungen bereitgestellte ausschließlich auf den Quellcode, der integriert wird erstellt werden, in Ihrem globalen Build oder die CI-Pipeline, die basierend auf Ihrem Quellcode-Repository (z. B. Git).

Die lokalen Images, die vom Entwickler sollten nur von ihnen verwendet werden, auf ihren eigenen Computern zu testen. Deshalb ist es wichtig, dass die DevOps-Pipeline, die von dem SCC-Code aktiviert ist.

Azure DevOps-Services und Team Foundation Server unterstützt Git- und Team Foundation-Versionskontrolle. Sie können sie auswählen, und es für eine End-to-End-Erfahrung von Microsoft verwenden. Sie können jedoch auch können verwalten Ihren Code in externen Repositorys (z.B. GitHub, lokales Git-Repositorys oder Subversion) und immer noch in der Lage, eine Verbindung herstellen, und erhalten den Code als Ausgangspunkt für Ihre DevOps-CI-Pipeline.

## <a name="step-3-build-ci-integrate-and-test-with-azure-devops-services-and-docker"></a>Schritt 3: Erstellen, Continuous Integration, Integration, und Testen Sie mit Azure DevOps-Dienste und Docker

CI hat als Standard für moderne Software testen und Bereitstellung entwickelt. Die Docker-Lösung verwaltet eine klare Trennung von Bereichen zwischen der Entwicklungs- und Betriebsteams. Die Unveränderlichkeit von Docker-Images wird sichergestellt, eine wiederholbare Bereitstellung zwischen Was wurde entwickelt, über CI getestet und in der Produktion ausgeführt wird. Docker-Engine bereitgestellt wird, über die Developer-Laptops und Test-Infrastruktur sind die Container in verschiedenen Umgebungen portabel.

Jetzt, nachdem Sie ein Versionskontrollsystem mit den richtigen Code gesendet haben, müssen Sie eine *Builddienst* wählen Sie den Code, und führen Sie den globalen Builds und Tests.

Der interne Workflow für diesen Schritt (Continuous Integration, Build, test) wird zur Erstellung einer CI-Pipeline, die Ihr coderepository (Git, usw.), bestehend aus dem Buildserver (Azure DevOps-Dienste), Docker-Engine und eine Docker-Registrierung.

Sie können Azure DevOps-Dienste als Grundlage für Ihre Anwendungen erstellen und Festlegen der CI-Pipeline und zum Veröffentlichen der erstellten "Elementen" ein "artefaktrepository" Dies wird im nächsten Schritt beschrieben.

Mithilfe von Docker für die Bereitstellung, der die "finalen Artefakte", die bereitgestellt werden, werden Docker-Images mit Ihrer Anwendung oder Dienste darin eingebettet sind. Diese Images werden mithilfe von Push übertragen oder veröffentlicht in einer *Docker-Registrierung* (einem privaten Repository wie diejenigen, die Sie haben in Azure Container Registry-Instanz oder eine öffentliche wie Docker-Hub-Registrierung, die häufig für offiziellen Basisimages verwendet wird).

Hier ist das grundlegende Konzept: Die CI-Pipeline werden gestartet: deaktiviert ein Commit mit einem SCC-Repository wie Git. Der Commit führt dazu, dass Azure DevOps-Dienste einen buildauftrag in einem Docker-Container ausgeführt werden soll, und nach erfolgreichem Abschluss dieses Auftrags per Push übertragen eines Docker-Images an die Docker-Registrierung, wie in Abbildung 5-2 dargestellt.

![Der erste Teil der äußeren Schleife umfasst die Schritte 1 bis 3, aus dem Code ausführen, Debuggen und zu überprüfen, klicken Sie dann das coderepository bis zu dem Build und Test-CI-Schritt](./media/image2.png)

**Abbildung 5-2**. Die Schritte in CI

Hier sind die grundlegenden Schritte der CI-Workflow mit Docker und Azure DevOps-Dienste:

1. Der Entwickler legt einen Commit mit einem SCC-Repository (Git/Azure DevOps-Services, GitHub usw.).

2. Wenn Sie Azure DevOps-Dienste oder Git verwenden, ist CI integriert, was bedeutet, dass es so einfach wie das Auswählen eines Kontrollkästchens in der Azure DevOps-Dienste ist. Bei Verwendung von einem externen SCC (wie z.B. GitHub), eine `webhook` benachrichtigt Azure DevOps-Dienste des Updates oder zu Git/GitHub übertragen wird.

3. Azure DevOps-Dienste, ruft SCC Repository, einschließlich der dockerfile-Datei, die das Bild als auch der Anwendung und -Code beschreibt.

4. Azure DevOps-Dienste wird ein dockerimage erstellt und es mit einer Nummer bezeichnet.

5. Azure DevOps-Dienste den Docker-Container im Docker-Host bereitgestellten instanziiert und führt die entsprechenden Tests.

6. Wenn die Tests erfolgreich sind, das Bild wird zuerst die Bezeichnung erhalten, einen aussagekräftigen Namen, damit Sie wissen es ist ein "Verbürgtes Build" (z. B. "/ 1.0.0" oder eine beliebige andere Bezeichnung), und klicken Sie dann mithilfe von Push übertragen Sie an Ihre Docker-Registrierung (Docker-Hub, Azure Container Registry, DTR, usw.).

### <a name="implementing-the-ci-pipeline-with-azure-devops-services-and-the-docker-extension-for-azure-devops-services"></a>Implementieren die CI-Pipeline mit Azure DevOps-Dienste und die Docker-Erweiterung für Azure DevOps-Dienste

Visual Studio Azure DevOps-Dienste enthält, Build und Release-Vorlagen, die Sie in Ihre CI/CD-Pipeline verwenden können, mit denen Sie können Docker-Images zu erstellen, Docker-Images an einen authentifizierten Docker-Registrierung per Push zu übertragen, führen Sie Docker-Images oder führen andere Vorgänge, die von Angeboten die Docker-CLI. Es fügt auch eine Docker Compose-Aufgabe, die Sie verwenden können, erstellen, per Push übertragen, und führen Sie Docker-Anwendungen mit mehreren Containern, oder führen andere Vorgänge, die von der Docker Compose-CLI angeboten werden, wie in Abbildung 5-3 gezeigt.

![Browseransicht zur der die Docker-CI-Pipeline in Azure DevOps](./media/image3.png)

**Abbildung 5-3**. Die Docker-CI-Pipeline in Azure DevOps-Dienste, einschließlich Build & Release-Vorlagen und zugeordneten Aufgaben.

Können Sie diese Vorlagen und die Aufgaben zum Erstellen Ihrer CI/CD-Artefakte zum Entwickeln / testen und Bereitstellen in Azure Service Fabric, Azure Kubernetes Service und ähnliche angeboten.

Mit dieser Visual Studio Team Services-Tasks, einen Build Linux-Docker-Host/VM bereitgestellt, in Azure und Ihrer bevorzugten Docker-Registrierung (Azure Container Registry, Docker-Hub, privaten Docker-DTR oder beliebige andere Docker-Registrierung) können Sie Ihre Docker-CI-Pipeline in Zusammenstellen einer sehr einheitlich.

***Anforderungen:***

- Azure DevOps-Dienste oder für lokale Installationen, Team Foundation Server 2015 Update 3 oder höher.

- Ein Azure DevOps-Services-Agent, der die Docker-Binärdateien verfügt.

  Eine einfache Möglichkeit zum Erstellen eines diese Agents werden Docker verwenden, um einen Container basierend auf dem Azure DevOps-Services-Agent Docker-Image ausführen.

> [! Informationen], lesen Sie weitere Informationen zu assemblieren eine Azure DevOps-Dienste-Docker-CI-pipeline und zeigen die exemplarischen Vorgehensweisen finden Sie auf folgenden Websites:
>
> - Ausführen einer Visual Studio Team Services (jetzt Azure DevOps-Services)-Agents als Docker-Container: \
>   <https://hub.docker.com/_/microsoft-azure-pipelines-vsts-agent>
>
> - Erstellen von .NET Core-Linux-Docker-Images mit Azure DevOps-Dienste: \
>   <https://blogs.msdn.microsoft.com/stevelasker/2016/06/13/building-net-core-linux-docker-images-with-visual-studio-team-services/>
>
> - Erstellen einer Linux-basierten Visual Studio Team Service Buildcomputer mit Docker-Unterstützung: \
>   <http://donovanbrown.com/post/2016/06/03/Building-a-Linux-Based-Visual-Studio-Team-Service-Build-Machine-with-Docker-Support>

### <a name="integrate-test-and-validate-multi-container-docker-applications"></a>Integrieren Sie, testen Sie und überprüfen Sie die Docker-Anwendungen mit mehreren Containern

Die meisten Docker-Anwendungen in der Regel bestehen mehrere Container statt von einem einzelnen Container aus. Ein gutes Beispiel ist eine Microservices-orientierte Anwendung, die für die Sie einen Container pro Microservice haben würden. Aber auch ohne strikt befolgen die Muster der Microservices-Ansatz, es ist jedoch wahrscheinlich, dass die Docker-Anwendung aus mehreren Containern oder Diensten bestehen würde.

Aus diesem Grund müssen Sie nach dem Erstellen der Anwendungscontainer in der CI-Pipeline, auch bereitstellen, integrieren und Testen Sie die Anwendung als Ganzes mit allen ihren Container in einem Docker-Host Integration oder sogar in einen Testcluster, Ihre Container werden verteilt.

Wenn Sie einen einzelnen Host verwenden, können Sie Docker-Befehle wie Docker-compose-zum Erstellen und Bereitstellen von verknüpften Container zum Testen und überprüfen Sie die Docker-Umgebung in einem einzelnen virtuellen Computer. Aber wenn Sie mit einem orchestratorcluster wie DC/OS, Kubernetes oder Docker Swarm arbeiten, müssen Sie Ihre Container über einen anderen Mechanismus oder Orchestrator, je nach Ihrer ausgewählten Cluster-Auftragsplaner bereitstellen.

Es folgen verschiedene Arten von Tests, die Sie für Docker-Container ausführen können:

- Komponententests für Docker-Container

- Testen die Gruppen von zusammenhängende oder microservices

- Testen Sie in Produktion und "Canary Release"-Versionen

Der wichtigste Punkt ist, dass bei der Integration und Funktionstests ausgeführt werden, diese Tests von außerhalb der Container ausgeführt werden muss. Tests sind nicht enthalten oder in den Containern, die Sie bereitstellen möchten, die ausgeführt werden, da die Container für statische Bilder basieren, die genau wie sein sollte, die Sie für die Produktion bereitstellen müssen.

Eine praktische Option beim Testen von Szenarien, wie Sie mehrere Cluster (test-Cluster, staging-Cluster und Produktionscluster) einschließlich erweiterte werden die Bilder auf eine Registrierung, veröffentlichen, damit es in verschiedenen Clustern getestet werden kann.

### <a name="push-the-custom-application-docker-image-into-your-global-docker-registry"></a>Schieben Sie das benutzerdefinierte Docker-Image in einer globalen Docker-Registrierung

Nachdem der Docker-Images getestet und überprüft wurde, sollten Sie kennzeichnen und veröffentlichen Sie sie in Ihrer Docker-Registrierung. Die Docker-Registrierung ist eine wesentliche Komponente des Lebenszyklus von Docker-Anwendung, da sie die zentrale ist, in dem Sie den benutzerdefinierten Test (auch bekannt als "Verbürgtes Images") in QA-und produktionsumgebungen bereitgestellt werden gespeichert.

Ähnlich wie Ihre "Source of Truth" von der Anwendungscode, der in Ihrer SCC-Repository (Git, usw.) gespeichert ist, wird die Docker-Registrierung Ihre "Source of Truth" für die binäre Anwendung oder die Bits für die Umgebungen QA- oder-produktionsumgebung bereitgestellt werden.

In der Regel sollten Sie Ihren privaten Repositorys für Ihre benutzerdefinierten Images in einem privaten Repository in Azure Container Registry-Instanz in eine lokale Registrierung wie Docker Trusted Registry oder in einer öffentlichen Cloud-Registrierung mit eingeschränktem Zugriff (z. B. haben Docker-Hub), müssen auch in diesem Fall ist Ihr Code nicht open-Source-Sie des Anbieters Sicherheit vertrauenswürdig. In beiden Fällen die Methode ist ähnlich und basiert auf der `docker push` wie in Abbildung 5-4 gezeigt den Befehl.

![In Schritt 3 zum Erstellen der Integration und testen (CI) können Sie die resultierende Docker-Images an eine private oder öffentliche Registrierung veröffentlichen.](./media/image4.png)

**Abbildung 5-4**. Veröffentlichen von benutzerdefinierten Images in Docker-Registrierung

Es gibt mehrere Angebote von Docker-Registrierungen von cloudanbietern wie Azure Container Registry, Amazon Web Services-Container-Registry, Google Container Registry-Instanz, Kai Registrierung und So weiter.

Sie können mit der Docker-Aufgaben, einen Satz von Abbilder von definierten übertragen einer `docker-compose.yml` -Datei mit mehreren Tags, an einer authentifizierten Docker-Registrierung (z.B. Azure Container Registry), wie in Abbildung 5-5 gezeigt.

![Browseransicht des Schritts, der Bilder in eine Registrierung von Azure DevOps zu veröffentlichen.](./media/image5.png)

**Abbildung 5-5**. Mit Azure DevOps-Services zum Veröffentlichen von benutzerdefinierten Images an eine Docker-Registrierung

> [! Informationen] finden Sie weitere Informationen zu Azure Container Registry, <https://aka.ms/azurecontainerregistry>.

## <a name="step-4-cd-deploy"></a>Schritt 4: CD bereitstellen

Die Unveränderlichkeit von Docker-Images wird sichergestellt, eine wiederholbare Bereitstellung mit Was wurde entwickelt, über CI getestet und in der Produktion ausgeführt wird. Nachdem Sie die Application-Docker-Images in Ihrer Docker-Registrierung (private oder öffentliche) veröffentlicht haben, können Sie sie bereitstellen, auf die mehrere Umgebungen, die möglicherweise (Produktion, QA, staging, usw.) aus Ihrer CD-Pipeline mithilfe von Azure DevOps-Dienste Pipeline-Aufgaben oder Release Management für Azure DevOps Services.

Allerdings hängt an diesem Punkt welche Art von Docker-Anwendung, die Sie bereitstellen möchten. Bereitstellen einer einfachen Anwendung (aus Komposition und Bereitstellung der Sicht) wie eine monolithische Anwendung umfasst einige Container oder Dienste und bereitgestellte wenigen Servern oder VMs unterscheidet sich von der Bereitstellung einer komplexeren Anwendung wie ein Microservices-orientierte Anwendung mit hyperskalierung-Funktionen. Diese beiden Szenarien werden in den folgenden Abschnitten erläutert.

### <a name="deploying-composed-docker-applications-to-multiple-docker-environments"></a>Bereitstellen von Docker-Anwendungen in mehrere Docker-Umgebungen erstellt

Sehen wir uns zunächst an, das weniger komplizierten-Szenario: um einfache Docker-Hosts (VMs oder Server) in einer einzigen Umgebung oder auf mehrere Umgebungen bereitstellen (Qualitätssicherung, Staging und Produktion). In diesem Szenario intern Ihrer CD-Pipeline können Docker-compose (aus Ihrer Azure DevOps-Dienste-Bereitstellungsaufgaben) zum Bereitstellen der Docker-Anwendungen mit einer entsprechenden Gruppe von Containern oder Diensten, wie in Abbildung 5-6 dargestellt.

![Bereitstellen von die CD Schritt (4) kann in verschiedenen Umgebungen, z. B. Fragen veröffentlichen & a, Staging und Produktion.](./media/image6.png)

**Abbildung 5-6**. Bereitstellen von anwendungscontainern in einfachen Docker-Host-Umgebungen-Registrierung

Abbildung 5-7 hebt hervor, wie Sie Ihre Build-CI zu QA-/Test-Umgebungen über das Azure DevOps-Dienste verbinden können, indem Sie auf der Docker Compose im Dialogfeld Task hinzufügen. Allerdings bei der Bereitstellung in Staging-oder produktionsumgebung Sie würde in der Regel verwenden Release Management-Funktionen, die Verarbeitung mehrerer Umgebungen (z. B. QA, Staging und Produktion). Wenn Sie zu einzelnen Docker-Hosts bereitstellen, verwendet es die Azure DevOps-Dienste "Docker-Compose" Task (das ist das Aufrufen der `docker-compose up` Befehl im Hintergrund). Wenn Sie in Azure Container Service bereitstellen, wird die Docker-Bereitstellungsaufgabe verwendet wie im Abschnitt erläutert die folgende.

![Browseransicht eine Docker Compose-Aufgabe hinzufügen.](./media/image7.png)

**Abbildung 5-7**. Hinzufügen einer Docker Compose-Aufgabe in einer Pipeline für Azure DevOps-Dienste

Wenn Sie ein Release in Azure DevOps-Dienste erstellen, dauert es eine Reihe von Eingabe-Elemente. Diese Artefakte werden für die Lebensdauer von der Version in allen Umgebungen unveränderlich sein soll. Wenn Sie Container einführen, identifizieren die Eingabe Artefakte Bilder in einer Registrierung bereitstellen. Je nachdem, wie diese Bilder identifiziert werden, sie werden nicht unbedingt bleibt während der Dauer der Version, die offensichtlichste Groß-/Kleinschreibung wird beim Verweisen auf `myimage:latest` aus einem `docker-compose` Datei.

Die Vorlagen des Azure DevOps-Dienste geben Ihnen, die Möglichkeit, Build-Artefakte zu generieren, die spezifischen Registrierungszeichenfolgen-Bild enthalten aufnimmt, die garantiert das gleiche Image binäre eindeutig zu identifizieren. Dies sind, was Sie wirklich als Eingabe für ein Release verwenden möchten.

### <a name="managing-releases-to-docker-environments-by-using-azure-devops-services-release-management"></a>Verwalten von Releases fest, die Docker-Umgebungen mithilfe von Release Management für Azure DevOps Services

Über das Azure DevOps-Services-Vorlagen, Sie können ein neues Image zu erstellen, veröffentlichen es in einer Docker-Registrierung, führen Sie es auf Linux oder Windows-Hosts an und verwenden Sie Befehle wie z. B. `docker-compose` mehrere Container als eine gesamte Anwendung, über das Azure DevOps bereitstellen Services Release Management-Funktionen, die für mehrere Umgebungen vorgesehen, wie in Abbildung 5-8 dargestellt.

![Browseransicht der Azure DevOps, Konfigurieren von Docker-compose-Versionen.](./media/image8.png)

**Abbildung 5-8**. Konfigurieren von Azure DevOps-Dienste Docker Compose-Tasks in der Releaseverwaltung für Azure DevOps-Dienste

Aber Bedenken Sie, dass das Szenario in Abbildung 5-6 dargestellt und in Abbildung 5-8 implementiert ein einfaches Beispiel ist (es einzelnen Docker-Hosts und virtuellen Computern bereitstellt und einen einzelnen Container oder eine Instanz pro Image vorhanden sein wird) und sollte wahrscheinlich nur für Entwicklungs- oder testumgebung Sce verwendet werden Narios. In den meisten Unternehmen Produktionsszenarien sollten Sie zum Lastenausgleich über mehrere Knoten, Servern und virtuellen Computern sowie "intelligent Failover" hohe Verfügbarkeit (HA) und einfach zu verwaltende Skalierbarkeit haben, wenn ein Server oder Knoten ausfällt, Diensten und Containern wird in einem anderen Hostserver oder virtuellen Computer verschoben werden. In diesem Fall benötigen Sie die erweiterte Technologien wie z. B. containercluster und orchestratoren Zeitplanungsmodule. Daher wird die Möglichkeit, die mit diesen Clustern bereitstellen, indem Sie die erweiterten Szenarios behandeln im nächsten Abschnitt erläutert.

### <a name="deploying-docker-applications-to-docker-clusters"></a>Bereitstellen von Docker-Anwendungen in Docker-Cluster

Die Art der verteilten Anwendungen erfordert die Compute-Ressourcen, die auch verteilt werden. Um-produktionsmandanten und Funktionen zu erhalten, benötigen Sie Funktionen, die hohe Skalierbarkeit und hohe Verfügbarkeit, die basierend auf in einem Pool zusammengefasste Ressourcen bereitstellen.

Sie konnte manuelles Bereitstellen von Containern mit diesen Clustern aus einem CLI-Tool oder eine Web-Benutzeroberfläche, jedoch sollten Sie diese Art von manueller Arbeit zum Erkennen der Bereitstellung reservieren oder Verwaltungszwecke wie dezentrale Skalierung oder Überwachung.

Aus Sicht einer CD und Azure DevOps-Dienste können insbesondere speziell vorgenommen Bereitstellungsaufgaben aus Ihren Release-Management für Azure DevOps-Services-Umgebungen ausführen, die Ihre containeranwendungen in verteilten Cluster in Container bereitgestellt wird Dienst, wie in Abbildung 5-9 dargestellt.

![Bereitstellen von die CD Schritt (4) kann auch zu einem Cluster über orchestratoren veröffentlichen.](./media/image9.png)

**Abbildung 5-9**. Bereitstellung von verteilten Anwendungen in Container Service

Zunächst bei der Bereitstellung in bestimmten Cluster oder orchestratoren verwenden üblicherweise bestimmte Bereitstellungsskripts und Mechanismen pro jeden Orchestrator (d.h. Kubernetes und Service Fabric haben verschiedene Mechanismen) anstelle der einfacheren Sie und leicht zu bedienende `docker-compose` Tool basierend auf den `docker-compose.yml` -Definitionsdatei. Dank der in Abbildung 5-10 dargestellt, die Bereitstellung von Azure DevOps-Dienste Docker-Aufgabe Sie jedoch jetzt auch können bereitstellen, die unterstützten orchestratoren einfach mit Ihrer bevorzugten `docker-compose.yml` -Datei, da das Tool diese "Übersetzung" führt für Sie (über Ihre `docker-compose.yml`Datei in das Format, die vom Orchestrator erforderlich).

![Bereitstellungstask für den Browseransicht der aufgabenkatalog in Azure DevOps mit Docker.](./media/image10.png)

**Abbildung 5-10**. Hinzufügen der Docker-Deploy-Task, der Ressourcen-Manager-Umgebung

Abbildung 5-11 zeigt, wie Sie bearbeite die Aufgabe mit Docker bereitstellen können, und geben Sie den Zieltyp (Azure Container Service-DC/OS, in diesem Fall), Ihre Docker-Compose-Datei und die Docker-registrierungsverbindung (z.B. Azure Container Registry oder Docker Hub). Dies ist die Aufgabe, die Ihre bereit zu verwendenden benutzerdefinierten Docker-Images als Container im Cluster bereitgestellt werden, abgerufen werden.

![Browseransicht der Azure DevOps, stellen Sie in Orchestrator Aufgabendefinition.](./media/image11.png)

**Abbildung 5-11**. Docker bereitstellen Aufgabe Definition bereitstellen, Azure Container Service DC/OS

> [! Informationen] Weitere Informationen finden Sie Informationen zu den CD-Pipeline mit Azure DevOps-Dienste und Docker auf <https://azure.microsoft.com/services/devops/pipelines>

## <a name="step-5-run-and-manage"></a>Schritt 5: Ausführen und verwalten

Da ausführen und Verwalten von Anwendungen auf Enterprise für die Produktion ist ein Hauptthema in sich selbst und aufgrund der Art der Vorgänge und Personen, die auf dieser Ebene (IT-Betrieb) sowie den großen Bereich dieses Bereichs arbeiten, die gesamte im nächste Kapitel geht es um Erläutern es aus.

## <a name="step-6-monitor-and-diagnose"></a>Schritt 6: Überwachen und diagnostizieren

In diesem Thema wird auch in den nächsten behandelt Kapitel als Teil der Aufgaben, dass die IT führt in Produktionssystemen; Sie ist jedoch wichtig, hervorzuheben, dass die Einblicke erhalten in diesem Schritt an das Entwicklungsteam feed müssen, damit die Anwendung ständig verbessert wird. Aus dieser Sicht ist es ebenfalls Teil des DevOps, obwohl die Tasks und Vorgänge von häufig ausgeführt werden IT.

Nur bei der Überwachung und Diagnose 100 % in den Bereich von DevOps sind sind die Prozesse und Analysen, die vom Entwicklungsteam für Tests oder Beta-Umgebungen ausgeführt. Dies erfolgt entweder durch Durchführen von Auslastungstests oder durch die Überwachung, Beta- oder QA-Umgebungen, in denen die neuen Versionen Beta-Tester versuchen, sind.

>[!div class="step-by-step"]
>[Zurück](index.md)
>[Weiter](create-ci-cd-pipelines-azure-devops-services-aspnetcore-kubernetes.md)
