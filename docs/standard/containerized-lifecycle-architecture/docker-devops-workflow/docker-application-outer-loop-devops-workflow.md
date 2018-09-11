---
title: Schritte in der äußeren Schleife DevOps-Workflow für eine Docker-Anwendung
description: Lebenszyklus von Docker-Containeranwendungen mit der Microsoft-Plattform und Tools
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/10/2018
ms.openlocfilehash: a03853a508cfb3d5dd5fbfe66e4ef484b685faaa
ms.sourcegitcommit: 67de6cb5dd66a19f2180ba7e4d7aecc697f8a963
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2018
ms.locfileid: "44339035"
---
# <a name="steps-in-the-outer-loop-devops-workflow-for-a-docker-application"></a>Schritte in der äußeren Schleife DevOps-Workflow für eine Docker-Anwendung

Abbildung 5 – 1 zeigt ein End-to-End-Darstellung der Schritte, die mit der äußeren Schleife DevOps-Workflow.

![](./media/image1.png)

Abbildung 5-1: DevOps-outer-Loop-Workflow für Docker-Anwendungen mit Microsoft-tools

Nun sehen wir uns die einzelnen Schritte ausführlicher.

## <a name="step-1-inner-loop-development-workflow"></a>Schritt 1: Innere Schleife-Entwicklungsworkflow

Dadurch werden ausführlich in Kapitel 4, aber Zusammenfassend lässt sich sagen, hier ist die äußere Schleife, dem Moment beginnt an dem ein Entwickler Code auf das Quellcodeverwaltungssystem (z. B. Git) initiieren von Aktionen für CI-Pipeline überträgt.

## <a name="step-2-source-code-control-integration-and-management-with-azure-devops-services-and-git"></a>Schritt 2: Integration von Quellcodeverwaltung und Verwaltung mit Azure DevOps-Services und Git

In diesem Schritt benötigen Sie ein Versionskontrollsystem eine konsolidierte Version des gesamten Codes, die von den anderen Entwicklern im Team zu erfassen.

Auch wenn die quellcodeverwaltung (SCC) und der Quellcode-Management-Blut die meisten Entwickler beim Erstellen von Docker-Anwendungen in einer DevOps-Lebenszyklus durchlaufen scheint, ist es wichtig, hervorzuheben, dass Sie die Docker-Images mit der Anwendung nicht senden müssen direkt in der globalen Docker-Registrierung (z.B. Azure Container Registry oder Docker Hub) aus dem Computer des Entwicklers. Im Gegenteil, müssen der Docker-Images zur Freigabe in produktionsumgebungen bereitgestellte ausschließlich auf den Quellcode, der integriert wird erstellt werden, in Ihrem globalen Build oder die CI-Pipeline, die basierend auf Ihrem Quellcode-Repository (z. B. Git).

Die lokalen Images, die durch die Entwickler selbst generiert sollte nur von den Entwicklern verwendet werden, wenn auf ihren eigenen Computern zu testen. Daher ist es wichtig, dass die DevOps-Pipeline, die von dem SCC-Code aktiviert ist.

Azure DevOps-Services und Team Foundation Server unterstützt Git- und Team Foundation-Versionskontrolle. Sie können sie auswählen, und es für eine End-to-End-Erfahrung von Microsoft verwenden. Sie können jedoch auch können verwalten Ihren Code in externen Repositorys (z.B. GitHub, lokales Git-Repositorys oder Subversion) und immer noch in der Lage, eine Verbindung herstellen, und erhalten den Code als Ausgangspunkt für Ihre DevOps-CI-Pipeline.

## <a name="step-3-build-ci-integrate-and-test-with-azure-devops-services-and-docker"></a>Schritt 3: Build, bei der Continuous Integration, Integration und Testen Sie mit Azure DevOps-Dienste und Docker

CI hat als Standard für moderne Software testen und Bereitstellung entwickelt. Die Docker-Lösung verwaltet eine klare Trennung von Bereichen zwischen der Entwicklungs- und Betriebsteams. Die Unveränderlichkeit von Docker-Images wird sichergestellt, eine wiederholbare Bereitstellung zwischen Was wurde entwickelt, über CI getestet und in der Produktion ausgeführt wird. Docker-Engine bereitgestellt wird, über die Developer-Laptops und Test-Infrastruktur sind die Container in verschiedenen Umgebungen portabel.

Jetzt, nachdem Sie ein Versionskontrollsystem mit den richtigen Code gesendet haben, müssen Sie eine *Builddienst* wählen Sie den Code, und führen Sie den globalen Builds und Tests.

Der interne Workflow für diesen Schritt (Continuous Integration, Build, test) wird zur Erstellung einer CI-Pipeline, die Ihr coderepository (Git, usw.), bestehend aus dem Buildserver (Azure DevOps-Dienste), Docker-Engine und eine Docker-Registrierung.

Sie können Azure DevOps-Dienste als Grundlage für Ihre Anwendungen erstellen und Festlegen der CI-Pipeline und zum Veröffentlichen der erstellten "Elementen" ein "artefaktrepository" Dies wird im nächsten Schritt beschrieben.

Mithilfe von Docker für die Bereitstellung, der die "finalen Artefakte", die bereitgestellt werden, werden Docker-Images mit Ihrer Anwendung oder Dienste darin eingebettet sind. Diese Images werden mithilfe von Push übertragen oder veröffentlicht in einer *Docker-Registrierung* (einem privaten Repository wie diejenigen, die Sie haben in Azure Container Registry-Instanz oder eine öffentliche wie Docker-Hub-Registrierung, die häufig für offiziellen Basisimages verwendet wird).

Hier ist das grundlegende Konzept: die CI-Pipeline werden gestartet: deaktiviert ein Commit mit einem SCC-Repository wie Git. Der Commit führt dazu, dass Azure DevOps-Dienste einen buildauftrag in einem Docker-Container ausgeführt werden soll, und nach erfolgreichem Abschluss dieses Auftrags per Push übertragen eines Docker-Images an die Docker-Registrierung, wie in Abbildung 5-2 dargestellt.

![](./media/image2.png)

Abbildung 5 – 2: die Schritte in CI

Hier sind die grundlegenden Schritte der CI-Workflow mit Docker und Azure DevOps-Dienste:

1.  Der Entwickler legt einen Commit mit einem SCC-Repository (Git/Azure DevOps-Services, GitHub usw.).

2.  Wenn Sie Azure DevOps-Dienste oder Git verwenden, ist CI integriert, was bedeutet, dass es so einfach wie das Auswählen eines Kontrollkästchens in der Azure DevOps-Dienste ist. Bei Verwendung von einem externen SCC (wie z.B. GitHub), eine *Webhook* benachrichtigt Azure DevOps-Dienste des Updates oder zu Git/GitHub übertragen wird.

3.  Azure DevOps-Dienste, ruft SCC Repository, einschließlich der dockerfile-Datei, die das Bild als auch von der Anwendung und -Code beschreibt.

4.  Azure DevOps-Dienste wird ein dockerimage erstellt und es mit einer Nummer bezeichnet.

5.  Azure DevOps-Dienste den Docker-Container im Docker-Host bereitgestellten instanziiert und führt die entsprechenden Tests.

6.  Wenn die Tests erfolgreich sind, das Bild wird zuerst die Bezeichnung erhalten, einen aussagekräftigen Namen, damit Sie wissen es ist ein "Verbürgtes Build" (z. B. "/ 1.0.0" oder eine beliebige andere Bezeichnung), und klicken Sie dann mithilfe von Push übertragen Sie an Ihre Docker-Registrierung (Docker-Hub, Azure Container Registry, DTR, usw.).

### <a name="implementing-the-ci-pipeline-with-azure-devops-services-and-the-docker-extension-for-azure-devops-services"></a>Implementieren die CI-Pipeline mit Azure DevOps-Dienste und die Docker-Erweiterung für Azure DevOps-Dienste

Die [Azure DevOps-Dienste-Docker-Erweiterung](https://aka.ms/vstsdockerextension) Fügt eine Aufgabe auf Ihrem CI-Pipeline mit dem Sie können Docker-Images zu erstellen, Docker-Images an einen authentifizierten Docker-Registrierung per Push zu übertragen, führen Sie Docker-Images oder führen andere Vorgänge, die von Docker angeboten werden CLI. Es fügt auch eine Docker Compose-Aufgabe, die Sie verwenden können, erstellen, per Push übertragen, und führen Sie Docker-Anwendungen mit mehreren Containern, oder führen andere Vorgänge, die von der Docker Compose-CLI angeboten werden, wie in Abbildung 5-3 gezeigt.

![](./media/image3.png)

Abbildung 5 – 3: die Docker-CI-Pipeline in Azure DevOps-Dienste

Die Docker-Erweiterung können Sie Dienstendpunkte für Docker-Hosts und -Container oder imageregistrierungen verwenden. Der Standardwert Aufgaben mit einem lokalen Docker-Host gegebenenfalls (Dies erfordert derzeit einen benutzerdefinierten Azure DevOps-Services-Agent); Andernfalls benötigen sie, dass Sie eine Docker-hostverbindung angeben. Aktionen, die mit einer Docker-Registrierung, z. B. mithilfe von Push übertragen ein Bild, authentifizierenden abhängig erfordern, dass Sie ein Docker-registrierungsverbindung angeben.

Die Azure DevOps-Dienste-Docker-Erweiterung installiert die folgenden Komponenten in Ihrem Azure DevOps-Services-Konto an:

-   Ein Dienstendpunkt, für die Verbindung mit einer Docker-Registrierung

-   Ein Dienstendpunkt, für die Verbindung mit einem Docker-Container-Host

-   Ein Docker-Aufgabe, die folgenden Schritte ausführen:

-   Erstellen Sie ein image

-   Übertragen Sie ein Bild oder ein Repository mit einer Registrierung mithilfe von Push

-   Führen Sie ein Bild in einem container

-   Führen Sie einen Docker-Befehl

-   Eine Docker Compose-Aufgabe zum Ausführen eines Befehls Docker Compose

Bei diesen Aufgaben Azure DevOps-Dienste einen Build Linux-Docker-Host/VM bereitgestellt, in Azure und Ihrer bevorzugten Docker-Registrierung (Azure Container Registry, Docker-Hub, privaten Docker-DTR oder beliebige andere Docker-Registrierung) können Sie Ihre Docker-CI-Pipeline in Zusammenstellen einer sehr konsistente Weise.

***Anforderungen:***

-   Azure DevOps-Dienste oder für lokale Installationen, Team Foundation Server 2015 Update 3 oder höher.

-   Ein Azure DevOps-Services-Agent, der die Docker-Binärdateien verfügt.

Eine einfache Möglichkeit zum Erstellen dieser werden Docker verwenden, um einen Container basierend auf dem Azure DevOps-Services-Agent Docker-Image ausführen.

**Weitere Informationen** , lesen Weitere Informationen zum Zusammenstellen von einer Azure DevOps-Dienste-Docker-CI-pipeline und anzuzeigenden Exemplarische Vorgehensweisen finden Sie unter den folgenden Websites:

Ausführen eines Azure DevOps-Services-Agents als Docker-Container: [ https://hub.docker.com/r/\ Microsoft/Vsts-Agent /](https://hub.docker.com/r/microsoft/vsts-agent/)

Azure DevOps-Dienste-Docker-Erweiterung: <https://aka.ms/vstsdockerextension>

Erstellen von .NET Core-Linux-Docker-Images mit Azure DevOps-Dienste: <https://blogs.msdn.microsoft.com/stevelasker/2016/06/13/building-net-core-linux-docker-images-with-visual-studio-team-services/>

Erstellen einen Linux-basierten Visual Studio Team Service-Buildcomputer mit Docker-Unterstützung: <http://donovanbrown.com/post/2016/06/03/Building-a-Linux-Based-Visual-Studio-Team-Service-Build-Machine-with-Docker-Support>

### <a name="integrate-test-and-validate-multicontainer-docker-applications"></a>Integrieren Sie, testen Sie und überprüfen Sie die Docker-Anwendungen mit mehreren Containern

Die meisten Docker-Anwendungen in der Regel bestehen mehrere Container statt von einem einzelnen Container aus. Ein gutes Beispiel ist eine Microservices-orientierte Anwendung, die für die Sie einen Container pro Microservice haben würden. Aber auch ohne strikt befolgen die Muster der Microservices-Ansatz, es ist sehr wahrscheinlich, dass die Docker-Anwendung aus mehreren Containern oder Diensten bestehen würde.

Aus diesem Grund müssen Sie nach dem Erstellen der Anwendungscontainer in der CI-Pipeline, auch bereitstellen, integrieren und Testen Sie die Anwendung als Ganzes mit allen ihren Container in einem Docker-Host Integration oder sogar in einen Testcluster, Ihre Container werden verteilt.

Wenn Sie einen einzelnen Host verwenden, können Sie Docker-Befehle wie Docker-compose-zum Erstellen und Bereitstellen von verknüpften Container zum Testen und überprüfen Sie die Docker-Umgebung in einem einzelnen virtuellen Computer. Aber wenn Sie mit einem orchestratorcluster wie DC/OS, Kubernetes oder Docker Swarm arbeiten, müssen Sie Ihre Container über einen anderen Mechanismus oder Orchestrator, je nach Ihrer ausgewählten Cluster-Auftragsplaner bereitstellen.

Es folgen verschiedene Arten von Tests, die Sie für Docker-Container ausführen können:

-   Komponententests für Docker-Container

-   Testen die Gruppen von zusammenhängende oder microservices

-   Testen Sie in Produktion und "Canary Release"-Versionen

Der wichtigste Punkt ist, dass bei der Integration und Funktionstests ausgeführt werden, diese Tests von außerhalb der Container ausgeführt werden muss. Tests müssen nicht definiert und in die Container, die Sie bereitstellen, ausgeführt werden, da die Container für statische Bilder basieren, die genau wie sein soll, die Sie in der Produktion bereitstellen möchten.

Sehr möglich beim Testen von komplexeren Szenarien, wie Sie mehrere Cluster (test-Cluster, staging-Cluster und Produktionscluster) testing ist die Bilder in eine Registrierung zum Testen in verschiedenen Clustern zu veröffentlichen.

### <a name="push-the-custom-application-docker-image-into-your-global-docker-registry"></a>Schieben Sie das benutzerdefinierte Docker-Image in einer globalen Docker-Registrierung

Nachdem der Docker-Images getestet und überprüft wurde, sollten Sie kennzeichnen und veröffentlichen Sie sie in Ihrer Docker-Registrierung. Die Docker-Registrierung ist eine wesentliche Komponente des Lebenszyklus von Docker-Anwendung, da sie die zentrale ist, in dem Sie den benutzerdefinierten Test (auch bekannt als "Verbürgtes Images") in QA-und produktionsumgebungen bereitgestellt werden gespeichert.

Ähnlich wie Ihre "Source of Truth" von der Anwendungscode, der in Ihrer SCC-Repository (Git, usw.) gespeichert ist, wird die Docker-Registrierung Ihre "Source of Truth" für die binäre Anwendung oder die Bits für die Umgebungen QA- oder-produktionsumgebung bereitgestellt werden.

In der Regel sollten Sie Ihren privaten Repositorys für Ihre benutzerdefinierten Images in einem privaten Repository in Azure Container Registry-Instanz in eine lokale Registrierung wie Docker Trusted Registry oder in einer öffentlichen Cloud-Registrierung mit eingeschränktem Zugriff (z. B. haben Docker-Hub), müssen auch in diesem Fall ist Ihr Code nicht open-Source-Sie des Anbieters Sicherheit vertrauenswürdig. In beiden Fällen ist die Methode, die mit der Sie dies tun, sehr ähnlich und letztlich basiert auf der Docker-Push-Befehl, wie in Abbildung 5-4 dargestellt.

![](./media/image4.png)

Abbildung 5-4: Veröffentlichen von benutzerdefinierten Images in Docker-Registrierung

Es gibt mehrere Angebote von Docker-Registrierungen von cloudanbietern wie Azure Container Registry, Amazon Web Services-Container-Registry, Google Container Registry-Instanz, Kai Registrierung und So weiter.

Die Azure DevOps-Dienste-Docker-Erweiterung verwenden, können Sie einen Satz von Bereitstellen von Images von einer Datei "Docker-Compose.yml" mit mehreren Tags, an einer authentifizierten Docker-Registrierung (z.B. Azure Container Registry), definiert pushen, wie in Abbildung 5-5 gezeigt.

![](./media/image5.png)

Abbildung 5-5: Verwenden von Azure DevOps-Dienste zum Veröffentlichen von benutzerdefinierten Images an eine Docker-Registrierung

**Weitere Informationen** Weitere Informationen über die Docker-Erweiterung für Azure DevOps-Dienste, wechseln Sie zu <https://aka.ms/vstsdockerextension>. Wechseln Sie zu, um weitere Informationen zu Azure Container Registry <https://aka.ms/azurecontainerregistry>.

## <a name="step-4-cd-deploy"></a>Schritt 4: CD bereitstellen

Die Unveränderlichkeit von Docker-Images wird sichergestellt, eine wiederholbare Bereitstellung mit Was wurde entwickelt, über CI getestet und in der Produktion ausgeführt wird. Nachdem Sie die Application-Docker-Images in Ihrer Docker-Registrierung (private oder öffentliche) veröffentlicht haben, können Sie sie bereitstellen, auf die mehrere Umgebungen, die möglicherweise (Produktion, QA, staging, usw.) aus Ihrer CD-Pipeline mithilfe von Azure DevOps-Dienste Pipeline-Aufgaben oder Release Management für Azure DevOps Services.

Allerdings hängt an diesem Punkt welche Art von Docker-Anwendung, die Sie bereitstellen möchten. Bereitstellen einer einfachen Anwendung (aus Komposition und Bereitstellung der Sicht) wie eine monolithische Anwendung umfasst einige Container oder Dienste und bereitgestellte wenigen Servern oder VMs unterscheidet sich von der Bereitstellung einer komplexeren Anwendung wie ein Microservices-orientierte Anwendung mit hyperskalierung-Funktionen. Diese beiden Szenarien werden in den folgenden Abschnitten erläutert.

### <a name="deploying-composed-docker-applications-to-multiple-docker-environments"></a>Bereitstellen von Docker-Anwendungen in mehrere Docker-Umgebungen erstellt

Sehen wir uns zunächst an, das weniger komplizierten-Szenario: um einfache Docker-Hosts (VMs oder Server) in einer einzigen Umgebung oder auf mehrere Umgebungen bereitstellen (Qualitätssicherung, Staging und Produktion). In diesem Szenario intern Ihrer CD-Pipeline können Docker-compose (aus Ihrer Azure DevOps-Dienste-Bereitstellungsaufgaben) zum Bereitstellen der Docker-Anwendungen mit einer entsprechenden Gruppe von Containern oder Diensten, wie in Abbildung 5-6 dargestellt.

![](./media/image6.png)

Abbildung 5: 6: Bereitstellen von Anwendungscontainer an einfache Docker-Host-Umgebungen-Registrierung

Abbildung 5-7 hebt hervor, wie Sie Ihre Build-CI zu QA-/Test-Umgebungen über das Azure DevOps-Dienste verbinden können, indem Sie auf der Docker Compose im Dialogfeld Task hinzufügen. Allerdings bei der Bereitstellung in Staging-oder produktionsumgebung Sie würde in der Regel verwenden Release Management-Funktionen, die Verarbeitung mehrerer Umgebungen (z. B. QA, Staging und Produktion). Wenn Sie zu einzelnen Docker-Hosts bereitstellen, ist das Azure DevOps-Dienste verwendet "Docker-Compose" Aufgabe (das ist das Aufrufen der Docker-compose-Befehl im Hintergrund). Wenn Sie in Azure Container Service bereitstellen, wird die Docker-Bereitstellungsaufgabe verwendet wie im Abschnitt erläutert die folgende.

![](./media/image7.png)

Abbildung 5-7: Hinzufügen einer Docker Compose-Aufgabe in einer Pipeline für Azure DevOps-Dienste

Wenn Sie ein Release in Azure DevOps-Dienste erstellen, dauert es eine Reihe von Eingabe-Elemente. Diese sollen während der gesamten Lebensdauer des Releases unveränderlich sein, über mehrere Umgebungen hinweg. Wenn Sie Container einführen, identifizieren die Eingabe Artefakte Bilder in einer Registrierung bereitstellen. Je nachdem, wie diese identifiziert sind werden sie nicht unbedingt bleibt während der Dauer von der Version der offensichtlichste Fall wird, wenn Sie auf "Myimage:latest" aus einer docker-Compose-Datei verweisen.

Die Docker-Erweiterung für Azure DevOps-Dienste bietet Ihnen, die Möglichkeit, Build-Artefakte zu generieren, die spezifischen Registrierungszeichenfolgen-Bild enthalten aufnimmt, die garantiert das gleiche Image binäre eindeutig zu identifizieren. Dies sind, was Sie wirklich als Eingabe für ein Release verwenden möchten.

### <a name="managing-releases-to-docker-environments-by-using-azure-devops-services-release-management"></a>Verwalten von Releases fest, die Docker-Umgebungen mithilfe von Release Management für Azure DevOps Services

Über das Azure DevOps-Services-Erweiterungen, Sie können ein neues Image zu erstellen, veröffentlichen es in einer Docker-Registrierung, führen Sie es auf Linux oder Windows-Hosts an und verwenden Sie Befehle wie Docker-compose-zum Bereitstellen von mehreren Containern als eine gesamte Anwendung, über das Azure DevOps Services Release Management-Funktionen, die für mehrere Umgebungen vorgesehen, wie in Abbildung 5-8 dargestellt.

![](./media/image8.png)

Abbildung 5 bis 8: Konfigurieren von Azure DevOps-Dienste Docker Compose-Aufgaben in der Releaseverwaltung für Azure DevOps-Dienste

Beachten Sie, dass das Szenario in Abbildung 5-6 dargestellt und in Abbildung 5-8 implementiert, ziemlich einfach ist ist (es wird einfach Docker-Hosts und virtuellen Computern bereitgestellt und fallen in einem einzelnen Container oder eine Instanz pro Bild), und wahrscheinlich werden, nur für Entwicklungs- oder testumgebung sc verwendet sollte jedoch beibehalten. Enarios. In den meisten Unternehmen Produktionsszenarien soll hohe Verfügbarkeit (HA) verfügen und einfach zu verwaltende Skalierbarkeit von Lastenausgleich über mehrere Knoten, Servern und virtuellen Computern sowie "intelligent Failover" also, wenn ein Server oder den Knoten ein Fehler auftritt, seine Dienste und Container werden zu einem anderen Hostserver oder virtuellen Computer verschoben. In diesem Fall benötigen Sie erweiterte Technologien wie containercluster und orchestratoren Zeitplanungsmodule. Daher ist die Möglichkeit, die mit diesen Clustern bereitstellen, genau über die erweiterten Szenarios, die im nächsten Abschnitt erläutert.

### <a name="deploying-complex-docker-applications-to-docker-clusters-dcos-kubernetes-and-docker-swarm"></a>Bereitstellen von komplexen Docker-Anwendungen in Docker-Cluster (DC/OS, Kubernetes und Docker Swarm)

Die Art der verteilten Anwendungen erfordert die Compute-Ressourcen, die auch verteilt werden. Um-produktionsmandanten und Funktionen zu erhalten, benötigen Sie Funktionen, die hohen Skalierbarkeit bieten clustering und hohe Verfügbarkeit auf der Grundlage von in einem Pool zusammengefasste Ressourcen.

Sie können Container manuell bereitstellen mit diesen Clustern von einem CLI-Tool, z. B. Docker Swarm (wie die Verwendung von [Docker-Dienst erstellen](https://docs.docker.com/engine/swarm/swarm-tutorial/deploy-service/)) oder eine Web-Benutzeroberfläche wie z. B. [Mesosphere Marathon](https://mesosphere.github.io/marathon/docs/marathon-ui.html) für DC/OS-Cluster, aber Sie sollten zu reservieren, die nur zu Testzwecken punctual Bereitstellung oder zu Verwaltungszwecken wie dezentrale Skalierung oder Überwachungszwecken.

Aus Sicht einer CD und Azure DevOps-Dienste insbesondere führen speziell vorgenommen Bereitstellungsaufgaben aus Ihren Release-Management für Azure DevOps-Services-Umgebungen Sie Ihre containeranwendungen in verteilten Cluster in Container bereitgestellt wird Dienst, wie in Abbildung 5-9 dargestellt.

![](./media/image9.png)

Abbildung 5-9: Bereitstellung von verteilten Anwendungen in Container Service

Zunächst bei der Bereitstellung in bestimmten Cluster oder orchestratoren verwenden üblicherweise bestimmte Bereitstellungsskripts und Mechanismen pro jeden Orchestrator (d. h. Mesosphere DC/OS oder Kubernetes haben verschiedene Mechanismen als Docker und Docker Sie Swarm) statt einfacher und leicht zu bedienende Docker-compose-Tool basierend auf der "Docker-Compose.yml"-Definitionsdatei. Dank der Microsoft Azure DevOps-Dienste Docker Deploy-Task, dargestellt in Abbildung 5 bis 10, Sie jedoch jetzt auch können Bereitstellen in DC/OS einfach mit der vertrauten Docker-compose.yml-Datei, da Microsoft diese "Übersetzung" für Sie ausführt (aus Ihrem Docker-compose.yml-Datei in andere Formate, die von DC/OS benötigt).

![](./media/image10.png)

Abbildung 5 bis 10: Hinzufügen der Docker-Deploy-Task zu der Ressourcen-Manager-Umgebung

Abbildung 5-11 zeigt, wie Sie bearbeite die Aufgabe mit Docker bereitstellen können, und geben Sie den Zieltyp (Azure Container Service-DC/OS, in diesem Fall), Ihre Docker-Compose-Datei und die Docker-registrierungsverbindung (z.B. Azure Container Registry oder Docker Hub). Dies ist, in dem die Aufgabe Ihre bereit zu verwendenden benutzerdefinierten Docker-Images als Container in DC/OS-Cluster bereitgestellt werden abgerufen werden.

![](./media/image11.png)

Abbildung 5-11: Bereitstellen von Docker Aufgabe Definition bereitstellen, Azure Container Service DC/OS

**Weitere Informationen** Weitere Informationen finden Sie Informationen zu den CD-Pipeline mit Azure DevOps-Dienste und Docker auf den folgenden Websites:

Azure DevOps-Dienste-Erweiterung für Docker und Azure Container Service: [ https://aka.ms/\ Vstsdockerextension](https://aka.ms/vstsdockerextension)

Azure Container Service: <https://aka.ms/azurecontainerservice>

Mesosphere DC/OS: <https://mesosphere.com/product/>

## <a name="step-5-run-and-manage"></a>Schritt 5: Ausführen und verwalten

Da ausführen und Verwalten von Anwendungen auf Enterprise für die Produktion ist ein Hauptthema in sich selbst und aufgrund der Art der Vorgänge und Personen, die auf dieser Ebene (IT-Betrieb) sowie den großen Bereich dieses Bereichs arbeiten, wir haben die aggregationsverarbeitung verwendet des gesamtes neben die Kapitel, erklärt es.

## <a name="step-6-monitor-and-diagnose"></a>Schritt 6: Überwachen und diagnostizieren

In diesem Thema wird auch im nächsten Kapitel behandelt, als Teil der Aufgaben, die IT-Vorgänge in Produktionssystemen; Sie ist jedoch wichtig, hervorzuheben, dass die Einblicke erhalten in diesem Schritt an das Entwicklungsteam feed müssen, damit die Anwendung ständig verbessert wird. Aus dieser Sicht ist es ebenfalls Teil des DevOps, obwohl die Tasks und Vorgänge in der Regel von ausgeführt werden IT.

Sind Sie nur bei der Überwachung und Diagnose zu 100 Prozent in den Bereich von DevOps sind die Prozesse und Analysen, die vom Entwicklungsteam für Tests oder Beta-Umgebungen ausgeführt. Dies erfolgt entweder durch das Durchführen von Auslastungstests oder einfach durch Überwachung, Beta- oder QA-Umgebungen, in denen die neuen Versionen Beta-Tester versuchen, sind.

>[!div class="step-by-step"]
[Zurück](index.md)
[Weiter](../run-manage-monitor-docker-environments/index.md)
