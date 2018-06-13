---
title: Schritte in der äußeren Schleife DevOps-Workflow für einen Docker-Anwendung
description: Lebenszyklus von Docker-Containeranwendungen mit der Microsoft-Plattform und Tools
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: 198313c260b36d3f3025606e73e220c361a7ebb8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33579001"
---
# <a name="steps-in-the-outer-loop-devops-workflow-for-a-docker-application"></a>Schritte in der äußeren Schleife DevOps-Workflow für einen Docker-Anwendung

Abbildung 5 – 1 zeigt ein End-to-End-Darstellung der Schritte beinhalten die DevOps äußere Schleife Workflow.

![](./media/image1.png)

Abbildung 5 – 1: DevOps äußere Schleife Workflow für Docker-Anwendungen mit Microsoft-tools

Jetzt sehen wir uns die einzelnen Schritte ausführlicher.

## <a name="step-1-inner-loop-development-workflow"></a>Schritt 1: Inner Loop-Entwicklungsworkflow

Dieser Schritt wird ausführlich in Kapitel 4, aber um Punkte aufzugreifen, sieht die äußere Schleife, dem Moment beginnt an dem ein Entwickler Code vom Quellcodeverwaltungssystem Management (z. B. Git) initiieren von Aktionen für CI-Pipeline schiebt.

## <a name="step-2-source-code-control-integration-and-management-with-visual-studio-team-services-and-git"></a>Schritt 2: Quellcodeverwaltung-Integrations- und verwaltungsmöglichkeiten mit Visual Studio Team Services und Git

In diesem Schritt benötigen Sie ein Versionskontrollsystem eine konsolidierte Version des gesamten Codes, die von den anderen Entwicklern im Team zu sammeln.

Obwohl der Source Code Control (SCC) und Quellcode Verwaltung zweiten Art erscheinen, können die meisten Entwickler, die beim Erstellen von Docker-Anwendungen in einem DevOps-Lebensdauer der Reihe nach ist es wichtig, hervorzuheben, dass Sie nicht die Docker-Images mit der Anwendung senden müssen direkt in der globalen Docker Registrierung (z. B. Azure-Containerregistrierung oder Docker Hub) vom Computer des Entwicklers. Der Docker-Images veröffentlicht und in produktionsumgebungen bereitgestellt werden müssen dagegen ausschließlich auf den Quellcode, der integriert wird in Ihrer globalen Build oder CI-Pipeline, die basierend auf Ihrem Quellcode Repository (z. B. Git) erstellt werden.

Die lokale Bilder, die von den Entwicklern selbst generiert sollte nur von den Entwicklern verwendet werden, beim Testen von ihren eigenen Computern. Deshalb ist es wichtig, dass die DevOps-Pipeline, die aus dem SCC-Code aktiviert ist.

Visual Studio Team Services und Team Foundation Server unterstützt Git- und Team Foundation-Versionskontrolle. Sie können zwischen ihnen auswählen und sie für eine End-to-End-Microsoft-Erfahrung. Sie können jedoch auch können verwalten den Code in externen Repositorys (wie GitHub, lokalen Git-Repositorys oder Subversion) und können weiterhin darauf herstellen und den Code als Ausgangspunkt für Ihre Pipeline DevOps CI abrufen.

## <a name="step-3-build-ci-integrate-and-test-with-visual-studio-team-services-and-docker"></a>Schritt 3: Build, CI, integrieren und Testen mit Visual Studio Team Services und Docker

CI wurde als Standard für moderne Softwaretests und Übermittlung entwickelt. Die Docker-Lösung verwaltet eine klare Abgrenzung der Aspekte zwischen den Entwicklungs- und telefonteams. Die Unveränderlichkeit von Docker-Images wird sichergestellt, dass eine wiederholbare Bereitstellungen zwischen wurde entwickelt, getestet über CI sowie unter Produktionsbedingungen ausführen. Docker-Modul bereitgestellt, über die Entwickler Laptops und Testinfrastruktur wird der Container über Umgebungen hinweg portabel.

Zu diesem Zeitpunkt, nachdem Sie ein Versionskontrollsystem mit den richtigen Code übermittelt haben, müssen Sie eine *Builddienst* zum Übernehmen des Codes, und führen Sie den globalen Builds und Tests.

Der interne Workflow für diesen Schritt (CI, Build, test) wird zur Erstellung einer CI-Pipeline besteht aus Ihrem Code-Repository (Git usw.), die Build-Server (Visual Studio Team Services), Docker-Modul und einen Docker-Registrierung.

Sie können Visual Studio Team Services als Grundlage zum Erstellen Ihrer Anwendungen und zum Festlegen der CI-Pipeline und für die Veröffentlichung der integrierten "Elementen" mit einem "Artefakte-Repository," der im nächsten Schritt beschrieben wird.

Bei Verwendung von Docker für die Bereitstellung, die "Letzte Elemente" bereitgestellt werden werden Docker-Images mit Ihrer Anwendung oder Dienste darin eingebettet sind. Diese Bilder abgelegt oder veröffentlicht werden, um eine *Docker Registrierung* (ein privates Repository wie diejenigen in Azure Containerregistrierung lassen oder einen öffentlichen wie Docker Hub-Registrierung, der für die offizielle Basisimages häufig verwendet wird).

Hier wird das grundlegende Konzept: CI Pipeline einen Fehler verursacht und-off durch ein Commit mit einem SCC-Repository wie Git werden wird. Das Commit führt dazu, dass Visual Studio Team Services, führen Sie einen Auftrag erstellen, in einem Docker-Container, und drücken nach erfolgreichem Abschluss dieses Auftrags ein Docker Bild in die Docker-Registrierung, wie in Abbildung 5 – 2 dargestellt.

![](./media/image2.png)

Abbildung 5 – 2: die Schritte im Konfigurationselement

Hier sind die grundlegenden Schritte der CI-Workflow mit Docker und Visual Studio Team Services:

1.  Der Entwickler legt einen Commit mit einem SCC-Repository (Git/Visual Studio Team Services, GitHub, usw.).

2.  Wenn Sie Visual Studio Team Services oder Git verwenden, ist CI bereits integriert, d. h. es so einfach wie das Aktivieren eines Kontrollkästchens in Visual Studio Team Services. Bei Verwendung einer externen SCC (z. B. GitHub), eine *Webhook* Benachrichtigen von Visual Studio Team Services des Updates oder Git/github mithilfe von Push übertragen wird.

3.  Visual Studio Team Services zieht SCC-Repository, einschließlich der dockerfile-Datei, die das Bild als auch für die Anwendung und den Test Code beschreibt.

4.  Visual Studio Team Services ein Docker Bild erstellt und es mit einem Build-Nummer.

5.  Visual Studio Team Services instanziiert den Docker-Container innerhalb der bereitgestellten Docker-Host, und die entsprechende Tests werden ausgeführt.

6.  Wenn die Tests erfolgreich sind, das Bild wird zuerst neu bezeichneten in einen aussagekräftigen Namen, damit Sie wissen, es ist ein "Verbürgtes Build" (z. B. "/ 1.0.0" oder eine andere Bezeichnung), und klicken Sie dann oben auf der Docker-Registrierung (Docker Hub, Azure-Containerregistrierung DTR, usw.) geschoben

### <a name="implementing-the-ci-pipeline-with-visual-studio-team-services-and-the-docker-extension-for-visual-studio-team-services"></a>Implementieren die CI-Pipeline mit Visual Studio Team Services und die Docker-Erweiterung für Visual Studio Team Services

Die [Visual Studio Team Services-Docker-Erweiterung](https://aka.ms/vstsdockerextension) Fügt einen Task für die CI-Pipeline mit dem Sie können Docker-Images erstellen, Docker-Images an einen authentifizierten Docker-Registrierung weiterleiten, führen Sie Docker-Images oder Ausführen anderer Vorgänge von Angeboten die Docker-Befehlszeilenschnittstelle. Darüber hinaus wird eine Docker Compose-Aufgabe, die Sie verwenden können, erstellen, mithilfe von Push übertragen, und multicontainer Docker-Anwendungen ausführen oder Ausführen anderer Vorgänge, die von der Docker verfassen CLI angeboten, wie in Abbildung 5 – 3 gezeigt hinzugefügt.

![](./media/image3.png)

Abbildung 5 – 3: die Docker-CI-Pipeline in Visual Studio Team Services

Der Docker-Erweiterung können Dienstendpunkte für Docker-Hosts und Container oder Image-Registrierungen. Die Standardeinstellung Aufgaben mit einem lokalen Docker-Host gegebenenfalls (derzeit erfordert dies einen benutzerdefinierte Visual Studio Team Services-Agent); Andernfalls müssen sie, dass Sie keine Docker-Host-Verbindung bereitstellen. Aktionen, die mit einem Docker-Registrierung, z. B. ein Bild Push authentifiziert wird, hängt erfordern, dass Sie ein Docker Registrierung-Verbindung bereitstellen.

Die Visual Studio Team Services-Docker-Erweiterung installiert die folgenden Komponenten in Ihrem Visual Studio Team Services-Konto:

-   Ein Dienstendpunkt für die Verbindung mit einem Docker-Registrierung

-   Ein Dienstendpunkt für die Verbindung mit einem Docker-Container-Host

-   Eine Docker Aufgabe die folgenden Schritte ausführen:

-   Erstellen Sie ein Bild

-   Übertragen Sie ein Bild oder ein Repository mit einer Registrierung mithilfe von Push

-   Führen Sie ein Bild in einem container

-   Führen Sie einen Docker-Befehl

-   Eine Aufgabe Docker Compose einen Docker Compose-Befehl ausführen

Diese Aufgaben Visual Studio Team Services einen Build Linux-Docker-Host/VM bereitgestellt, in Azure und Ihrer bevorzugten Docker-Registrierung (Azure-Containerregistrierung, Docker Hub, private Docker DTR oder anderen Docker-Registrierung) können Ihre Docker CI Pipeline Zusammenstellen einer sehr einheitlich.

***Anforderungen:***

-   Visual Studio Team Services oder bei lokalen Installationen muss Team Foundation Server 2015 Update 3 oder höher.

-   Ein Visual Studio Team Services-Agent, der Docker-Binärdateien verfügt.

Eine einfache Möglichkeit zum Erstellen einer davon ist Docker verwenden, um einen Container, basierend auf dem Visual Studio Team Services-Agent-Docker-Image auszuführen.

**Weitere Informationen** , lesen Weitere Informationen zum Zusammenstellen einer Visual Studio Team Services Docker CI pipeline und Anzeigen von exemplarischen Vorgehensweisen, finden Sie auf den folgenden Websites:

Ausführen eines Visual Studio Team Services-Agents als einen Docker-Container: [ https://hub.docker.com/r/\ Microsoft/Vsts-Agent /](https://hub.docker.com/r/microsoft/vsts-agent/)

VSTS Docker-Erweiterung: <https://aka.ms/vstsdockerextension>

Erstellen von .NET Core-Linux-Docker-Images mit Visual Studio Team Services: <https://blogs.msdn.microsoft.com/stevelasker/2016/06/13/building-net-core-linux-docker-images-with-visual-studio-team-services/>

Erstellen einen Linux-basierten Dienst Visual Studio Team Buildcomputer mit Docker-Unterstützung: <http://donovanbrown.com/post/2016/06/03/Building-a-Linux-Based-Visual-Studio-Team-Service-Build-Machine-with-Docker-Support>

### <a name="integrate-test-and-validate-multicontainer-docker-applications"></a>Integrieren Sie, testen Sie und validieren Sie multicontainer Docker-Anwendungen

In der Regel die meisten Docker Anwendungen mehrere Container anstatt von einem einzelnen Container bestehen. Ein gutes Beispiel ist eine Microservices-orientierten-Anwendung, die für die Sie einen Container pro Microservice verfügen würde. Aber auch ohne streng folgenden Microservices Ansatz Muster, es ist sehr wahrscheinlich, dass die Docker-Anwendung von mehreren Containern oder Diensten zusammengesetzt werden würde.

Aus diesem Grund müssen nach dem Erstellen der Anwendungscontainer in der CI-Pipeline, Sie auch integrieren, bereitstellen und Testen der Anwendung als Ganzes mit alle dessen Container innerhalb einer Integration Docker-Host oder sogar in einem Testcluster, auf das die Container sind verteilt.

Wenn Sie einem Einzelhost verwenden, können Sie Docker-Befehle wie Docker-zum Erstellen und Bereitstellen der zugehörigen Container zum Testen und überprüfen die Docker-Umgebung auf einem einzelnen virtuellen Computer zu erstellen. Aber wenn Sie mit einem Orchestrator-Cluster wie DC/OS, Kubernetes oder Docker Containerhostclustern arbeiten, müssen Sie über einen anderen Mechanismus oder Orchestrator, je nach den ausgewählten Cluster/Planer-Container bereitzustellen.

Es folgen verschiedene Arten von Tests, die für Docker-Container ausgeführt werden können:

-   Komponententests für Docker-Containern

-   Testen die Gruppen von miteinander verwandter Anwendungen oder microservices

-   Testen Sie in Produktions-als auch "Kanarischen" Versionen

Der wichtige Punkt ist, dass bei der Integration und Funktionstests ausgeführt werden, diese Tests von außerhalb der Container ausgeführt werden muss. Tests müssen nicht definiert und innerhalb des Containers, die Sie bereitstellen, ausgeführt werden, da die Container für statische Bilder basieren, die genau sein soll, die Sie in die Produktion bereitstellen möchten.

Sehr möglich beim Testen von komplexeren Szenarien, wie viele Clustern (testen, staging Cluster, und Produktionscluster) testen ist so veröffentlichen Sie die Bilder auf eine Registrierung in verschiedenen Clustern zu testen.

### <a name="push-the-custom-application-docker-image-into-your-global-docker-registry"></a>Mithilfe von Push übertragen Sie die benutzerdefinierte Anwendung Docker Bild in der globalen Docker-Registrierung

Nachdem der Docker-Images getestet und überprüft wurde, sollten Sie kennzeichnen und veröffentlichen Sie sie auf der Docker-Registrierung. Die Docker-Registrierung ist ein wichtiger Teil des Lebenszyklus der Docker-Anwendung, da sie zentraler Ort ist, in dem Sie Ihre benutzerdefinierte Tests (d. h. "Verbürgtes Images") in QA und Produktions-Umgebungen bereitgestellt werden gespeichert.

Ähnlich wie der Anwendungscode in Ihre SCC-Repository (Git usw.) gespeichert Ihre "Source of Truth" ist, wird die Docker-Registrierung die "Source of Truth" für Ihre binäre Anwendung oder die Bits in den Umgebungen QA- oder-produktionsumgebung bereitgestellt werden.

In der Regel sollten Sie Ihre privaten Repositorys bei benutzerdefinierten Images entweder in einem privaten-Repository in der Registrierung für Azure-Container oder in einer lokalen Registrierung wie Docker Trusted Registry oder in einer öffentlichen Cloud-Registrierung mit eingeschränktem Zugriff (z. B. haben Docker Hub), müssen auch in diesem Fall ist der Code nicht als open Source-Sie Sicherheit des Herstellers vertrauen. In beiden Fällen ist die Methode mit der in diesem Fall sehr ähnlich und letztlich basierend auf den Befehl "Docker Push", wie in Abbildung 5-4 dargestellt.

![](./media/image4.png)

Abbildung 5-4: Veröffentlichen benutzerdefinierter Abbilder in Docker-Registrierung

Es sind mehrere Produkte für Docker-Registrierungen von Cloud-Anbieter, wie Azure Containerregistrierung, Amazon Web Services Containerregistrierung, Google Containerregistrierung, Kai Registrierung usw. ein.

Die Visual Studio Team Services-Docker-Erweiterung verwenden, können Sie einen Satz von Bereitstellen von Images von einer Datei Docker compose.yml mehrere Tags dar, eine authentifizierte Docker-Registrierung (z. B. Azure-Containerregistrierung) definiert push, wie in Abbildung 5 – 5 gezeigt.

![](./media/image5.png)

Abbildung 5 – 5: Verwenden von Visual Studio Team Services zum Veröffentlichen benutzerdefinierter Images mit einer Docker-Registrierung

**Weitere Informationen** Weitere Informationen über die Docker-Erweiterung für Visual Studio Team Services, wechseln Sie zu <https://aka.ms/vstsdockerextension>. Wechseln Sie zu, um weitere Informationen zum Azure-Containerregistrierung <https://aka.ms/azurecontainerregistry>.

## <a name="step-4-cd-deploy"></a>Schritt 4: CD, bereitstellen

Die Unveränderlichkeit von Docker-Images wird sichergestellt, dass eine wiederholbare Bereitstellungen mit wurde entwickelt, getestet über CI sowie unter Produktionsbedingungen ausführen. Nachdem Sie die Anwendung Docker-Images, die in der Docker-Registrierung (private oder öffentliche) veröffentlicht haben, können Sie diese bereitstellen, auf die mehrere Umgebungen, die Sie möglicherweise (Produktion, QA, staging usw.) von der CD-Pipeline mit Visual Studio Team Services Pipeline-Vorgänge oder Visual Studio Team Services Release Management.

Allerdings hängt an diesem Punkt welche Art von Docker-Anwendung, die Sie bereitstellen. Bereitstellen einer einfachen Anwendung (aus einer Zusammensetzung und Bereitstellung der Sicht) wie eine monolithischen Anwendung umfasst einige Container oder Dienste und bereitgestellten auf einigen Servern oder virtuellen Computern unterscheidet sich von der Bereitstellung von eine komplexere Anwendung wie eine Microservices dienstorientierten Anwendung mit hyperskalaren-Funktionen. In den folgenden Abschnitten werden diese beiden Szenarien erläutert.

### <a name="deploying-composed-docker-applications-to-multiple-docker-environments"></a>Bereitstellen von Docker-Anwendungen in mehreren Umgebungen von Docker zusammengesetzt

Sehen wir uns zunächst an, die weniger komplexe-Szenario: einfache Docker-Hosts (virtuelle Computer oder Server) in einer einzigen Umgebung oder in mehreren Umgebungen bereitstellen (QA, Staging und Produktion). In diesem Szenario intern die CD-Pipeline können Docker-verfassen (aus der Visual Studio Team Services-Bereitstellungsaufgaben) zum Bereitstellen von Docker-Anwendungen mit einer verwandten Gruppe von Containern oder Diensten, wie in Abbildung 5 bis 6 veranschaulicht.

![](./media/image6.png)

Abbildung 5 – 6: Bereitstellen von Anwendungscontainer für einfache Umgebungen Registrierung des Docker-Hosts

Abbildung 5-7 hebt hervor, wie Sie Ihre Builds CI, QA und testumgebungen über Visual Studio Team Services verbinden können, durch Klicken auf Docker Compose im Dialogfeld Task hinzufügen. Allerdings beim Staging-oder produktionsumgebung bereitstellen, Sie würden normalerweise verwenden Release Management-Funktionen, die Behandlung von Umgebungen mit mehreren (z. B. QA, Staging und Produktion). Wenn Sie auf eine Docker-Host bereitstellen, die Visual Studio Team Services verwendeten Task "Docker Compose" (das ist das Aufrufen der Docker-Befehl hinter den Kulissen verfassen). Wenn Sie Azure-Container-Dienst bereitstellen, verwendet der Docker-Bereitstellungsaufgabe, wie im Abschnitt erläutert, die folgt.

![](./media/image7.png)

Abbildung 5-7: Hinzufügen einer Docker Compose Aufgabe in einer Visual Studio Team Services-pipeline

Beim Erstellen einer Version in Visual Studio Team Services dauert es einen Satz von Eingabedaten Artefakte. Diese sollten unveränderlich während der gesamten Lebensdauer der Version in mehreren Umgebungen verwendet werden. Wenn Sie Container einführen, identifizieren die Eingabe Artefakte Bilder in einer Registrierung bereitstellen. Je nachdem, wie diese identifiziert sind werden sie nicht garantiert bleiben unverändert im Verlauf der Version der offensichtlichste Fall, wenn Sie aus einer Datei Docker-compose "Myimage:latest" verweisen.

Die Docker-Erweiterung für Visual Studio Team Services gibt Ihnen die Möglichkeit, Buildartefakte zu generieren, die spezifischen Registrierungszeichenfolgen-Image enthalten Übersichten, die zur eindeutigen Identifizierung des gleichen Images binäre garantiert werden. Dies sind, was Sie tatsächlich als Eingabe für eine Version verwenden möchten.

### <a name="managing-releases-to-docker-environments-by-using-visual-studio-team-services-release-management"></a>Verwalten von Versionen in Docker-Umgebungen mithilfe von Visual Studio Team Services Release Management

Über die Visual Studio Team Services-Erweiterungen, Sie können ein neues Image erstellen, veröffentlichen einen Docker-Registrierung führen Sie es auf Linux- oder Windows-Hosts und verwenden Sie Befehle wie Docker-zum Bereitstellen von mehreren Containern als eine gesamte Anwendung, über das visuelle Element erstellen Studio Team Services Release Management-Funktionen für mehrere Umgebungen bestimmt, wie in Abbildung 5 bis 8 dargestellt.

![](./media/image8.png)

Abbildung 5 bis 8: Konfigurieren von Visual Studio Team Services Docker Compose Aufgaben von Visual Studio Team Services Release Management

Beachten Sie, dass das Szenario in Abbildung 5 bis 6 dargestellt und in Abbildung 5 bis 8 implementiert ziemlich einfach ist, (er wird bereitgestellt, um einfache Docker-Hosts und virtuellen Computer, und es wird einen einzelnen Container oder eine Instanz pro Bild) und wahrscheinlich nur für Entwicklungs- oder Testserver sc verwendet werden sollte jedoch beibehalten. Enarios. In den meisten Unternehmen Produktionsszenarien sollten damit hohe Verfügbarkeit (HA) und leicht zu verwaltende Skalierbarkeit von Lastenausgleich über mehrere Knoten, Servern und virtuellen Computern sowie "intelligent Failover" daher, die, wenn ein Server oder den Knoten ein Fehler auftritt, seine Dienste und Container werden in einem anderen Server mit dem Host oder virtuellen Computer verschoben. In diesem Fall benötigen Sie komplexere Technologien wie Container Clustern Orchestrators und Planer. Daher ist die Möglichkeit, die für diesen Cluster bereitstellen, genau über die erweiterten Szenarien, die im nächsten Abschnitt erläutert.

### <a name="deploying-complex-docker-applications-to-docker-clusters-dcos-kubernetes-and-docker-swarm"></a>Bereitstellen von komplexen Docker-Anwendungen für Docker-Clustern (DC/OS, Kubernetes und Docker Containerhostclustern)

Die Art der verteilten Anwendung erfordert Serverressourcen, die auch verteilt werden. Zur Produktion Funktionen verfügen, benötigen Sie Funktionen, die hohe Skalierbarkeit bieten clustering und hohe Verfügbarkeit auf der Grundlage von in einem Pool zusammengefasste Ressourcen.

Sie können die Bereitstellung Container manuell zu diesen Clustern von einem CLI-Tool, z. B. Docker Containerhostclustern (z. B. mit [Docker-Dienst erstellen](https://docs.docker.com/engine/swarm/swarm-tutorial/deploy-service/)) oder einer Webbenutzeroberfläche wie z. B. [Mesosphere Marathon](https://mesosphere.github.io/marathon/docs/marathon-ui.html) für DC/OS-Clustern, aber Sie sollten Reservieren Sie, die nur zu Testzwecken punctual Bereitstellung oder zu Verwaltungszwecken wie dezentrale Skalierung oder Überwachungszwecken.

Aus Sicht einer CD, und Visual Studio Team Services insbesondere führen speziell erstellte Bereitstellungsaufgaben aus Ihrer Visual Studio Team Services Release Management-Umgebungen Sie Ihre Sammelartikeleinheit für verteilte Cluster in bereitgestellt wird Containerdienst, wie in Abbildung 5 bis 9 dargestellt.

![](./media/image9.png)

Abbildung 5 – 9: Bereitstellung von verteilten Anwendungen Containerdienst

Zu Beginn beim Bereitstellen auf bestimmte Cluster oder Orchestrators verwenden traditionell bestimmte Bereitstellungsskripts und Mechanismen pro jedes Orchestrator (d. h. Mesosphere DC/OS oder Kubernetes haben unterschiedliche Bereitstellungsmechanismen als Docker als auch Docker Sie Containerhostclustern) anstelle von einfacher und einfach zu bedienenden Docker-verfassen Tool basierend auf den Docker-compose.yml-Definitionsdatei. Allerdings Dank der Microsoft Visual Studio Team Services Docker Deploy-Aufgabe gezeigt in Abbildung 5 bis 10, Sie jetzt auch können bereitstellen, DC-Betriebssystem durch die einfache Verwendung der vertrauten Docker-compose.yml-Datei, da Microsoft diese "Übersetzung" für Sie ausführt (aus der Docker-compose.yml-Datei in andere Formate von DC/OS benötigt).

![](./media/image10.png)

Abbildung 5 bis 10: Hinzufügen der Docker-Bereitstellungstask zu Ihrer Umgebung RM

Abbildung 5 bis 11 wird veranschaulicht, wie Sie den Docker-Bereitstellungstask bearbeiten und geben Sie den Zieltyp (Azure Container Dienst DC/OS, in diesem Fall), die Dockerfile-Datei zu erstellen und die Registrierung der Docker-Verbindung (z. B. Azure-Containerregistrierung oder Docker Hub). Dies ist, in dem der Task kann jetzt zu verwendenden benutzerdefinierten Docker Images als Container im Cluster DC/OS bereitgestellt werden abgerufen werden.

![](./media/image11.png)

Abbildung 5 – 11: Bereitstellen von Docker Aufgabe Definition Bereitstellen von Azure Container Dienst DC/OS

**Weitere Informationen** Weitere Informationen finden Sie Informationen zu CD Pipeline mit Visual Studio Team Services als auch Docker an, auf den folgenden Websites:

Visual Studio Team Services-Erweiterung für Docker und Azure-Container-Dienst: [ https://aka.ms/\ Vstsdockerextension](https://aka.ms/vstsdockerextension)

Azure-Container-Dienst: <https://aka.ms/azurecontainerservice>

Mesosphere DC/OS: <https://mesosphere.com/product/>

## <a name="step-5-run-and-manage"></a>Schritt 5: Ausführen und verwalten

Da ausführen und Verwalten von Anwendungen an Enterprise-Production-Ebene eine Hauptthema in und von sich selbst und aufgrund der Art der Vorgänge und Personen, die auf dieser Ebene (IT-Betrieb) sowie des großen Bereichs dieses Bereichs arbeiten, wir haben die aggregationsverarbeitung verwendet der gesamtes weiter Kapitel verlagern Sie ihn.

## <a name="step-6-monitor-and-diagnose"></a>Schritt 6: Überwachen und zu diagnostizieren

In diesem Thema wird auch im nächsten Kapitel behandelt, als Teil der Aufgaben, die IT-Betrieb in Produktionssystemen führt; Allerdings ist wichtig, markieren Sie, dass die Einsichten, die in diesem Schritt erhaltenen zurück an das Entwicklungsteam feed müssen, damit die Anwendung ständig verbessert wird. Aus dieser Sicht ist es ebenfalls Teil der DevOps, obwohl die Tasks und Vorgänge in der Regel ausgeführt werden IT.

Nur bei der Überwachung und Diagnose zu 100 % in den Bereich des DevOps sind sind die Überwachungsfunktionen Prozesse und Analysen, die vom Entwicklungsteam für Test- oder Beta-Umgebungen ausgeführt. Dies erfolgt durch Ausführen von ladetests oder einfach durch Überwachung Beta oder QA-Umgebungen, in denen Betatester die neuen Versionen versuchen.

>[!div class="step-by-step"]
[Vorherigen] (index.md) [weiter] (.. /Run-Manage-Monitor-docker-Environments/Index.MD)
