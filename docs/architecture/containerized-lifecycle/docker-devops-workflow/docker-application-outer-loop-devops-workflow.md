---
title: Schritte im Outer-Loop-DevOps-Workflow für eine Docker-Anwendung
description: Lernen Sie die Schritte für die „äußere Schleife“ des DevOps-Workflows
ms.date: 02/15/2019
ms.openlocfilehash: 44bd73bf88a743e5350e422d3ea000ca075f7383
ms.sourcegitcommit: 465547886a1224a5435c3ac349c805e39ce77706
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "82021302"
---
# <a name="steps-in-the-outer-loop-devops-workflow-for-a-docker-application"></a>Schritte im Outer-Loop-DevOps-Workflow für eine Docker-Anwendung

Abbildung 5–1 zeigt eine End-to-End-Darstellung der Schritte, aus denen der DevOps-Outer-Loop-Workflow besteht. Sie zeigt die „äußere Schleife“ von DevOps. Wenn Code per Push an das Repository übertragen wird, beginnt die CD-Pipeline, in der die Anwendung bereitgestellt wird. Aus bereitgestellten Anwendungen gesammelte Metriken werden in die Entwicklungsworkload rückgekoppelt, in der die „innere Schleife“ stattfindet, sodass die Entwicklungsteams über reale Daten verfügen, mit denen sie auf Benutzer- und Geschäftsanforderungen reagieren können.

![Diagramm, das die 6 Schritte der „äußeren Schleife“ des DevOps-Workflows zeigt.](./media/docker-application-outer-loop-devops-workflow/overview-dev-ops-outter-loop-workflow.png)

**Abbildung 5–1**. DevOps-Outer-Loop-Workflow für Docker-Anwendungen mit Microsoft-Tools

Sehen wir uns die einzelnen Schritte nun ausführlicher an.

## <a name="step-1-inner-loop-development-workflow"></a>Schritt 1: Inner-Loop-Entwicklungsworkflow

Dieser Schritt wird im Detail in Kapitel 4 erläutert, zusammenfassend lässt sich aber sagen, dass diese Stelle den Anfang der äußeren Schleife darstellt, dem Moment, in dem ein Entwickler Code per Push in das Quellcodeverwaltungssystem (wie etwa Git) überträgt und so Aktionen der CI-Pipeline einleitet.

## <a name="step-2-source-code-control-integration-and-management-with-azure-devops-services-and-git"></a>Schritt 2: Integration und Verwaltung der Quellcodeverwaltung mit Azure DevOps Services und Git

In diesem Schritt benötigen Sie ein Versionskontrollsystem, um eine konsolidierte Version des gesamten Codes zu erfassen, der von den verschiedenen Entwicklern im Team kommt.

Auch wenn Quellcodeverwaltung (Source Code Control, SCC) und Quellcodemanagement den meisten Entwicklern in Fleisch und Blut übergegangen sein dürften, beim Erstellen von Docker-Anwendungen in einem DevOps-Lebenszyklus muss unbedingt hervorgehoben werden, dass die Docker-Images mit der Anwendung nicht direkt vom Computer des Entwicklers aus an die globale Docker-Registrierung (etwa die Azure Container Registry oder den Docker Hub) übermittelt werden dürfen. Ganz im Gegenteil müssen die zu veröffentlichenden und in Produktionsumgebungen bereitzustellenden Docker-Images ausschließlich aus dem Quellcode erstellt werden, der auf der Grundlage Ihres Quellcode-Repositorys (z.B. Git) in Ihre globale Build- oder CI-Pipeline integriert wird.

Die von Entwicklern generierten lokalen Images sollte von ihnen nur zum Testen auf ihren eigenen Computern verwendet werden. Deshalb ist es wichtig, dass die DevOps-Pipeline vom SCC-Code aktiviert wird.

Azure DevOps Services und Team Foundation Server unterstützen Git und die Team Foundation-Versionskontrolle. Sie können zwischen ihnen wählen und dies für ein einheitliche Microsoft-End-to-End-Erfahrung nutzen. Sie können Ihren Code jedoch auch in externen Repositorys (wie GitHub, lokalen Git-Repositorys oder Subversion) verwalten und sind dann trotzdem in der Lage, Verbindungen damit herzustellen und Ihren Code als Ausgangspunkt für Ihre DevOps-CI-Pipeline abzurufen.

## <a name="step-3-build-ci-integrate-and-test-with-azure-devops-services-and-docker"></a>Schritt 3: Erstellen, CI, Integrieren und Testen mit Azure DevOps Services und Docker

CI hat sich als moderner Standard für Softwaretests und -bereitstellungen durchgesetzt. Die Docker-Lösung erhält eine klare Separation of Concerns zwischen den Entwicklungs- und Betriebsteams aufrecht. Die Unveränderlichkeit von Docker-Images stellt eine wiederholbare Bereitstellung zwischen dem sicher, was entwickelt, mithilfe von CI getestet und in der Produktionsumgebung bereitgestellt wird. Durch eine übergreifend auf Entwicklerlaptops bereitgestellte Docker-Engine und Testinfrastruktur werden die Container über Umgebungsgrenzen hinweg portierbar.

Nachdem Sie über ein Versionskontrollsystem mit dem richtigen übermittelten Code verfügen, benötigen Sie einen *Builddienst*, um den Code aufzunehmen und die globalen Builds und Tests auszuführen.

Bei dem internen Workflow für diesen Schritt (CI, Erstellen, Testen) handelt es sich um den Aufbau einer CI-Pipeline, die aus Ihrem Coderepository (Git usw.), Ihrem Buildserver (Azure DevOps Services), der Docker-Engine und einer Docker-Registrierung besteht.

Sie können Azure DevOps Services als Grundlage zum Erstellen Ihrer Anwendungen und Festlegen Ihrer CI-Pipeline sowie zum Veröffentlichen der erstellten „Artefakte“ in einem „Artefaktrepository“ verwenden, wie im nächsten Schritt erläutert.

Bei der Verwendung von Docker für die Bereitstellung sind die „endgültigen Artefakte“, die bereitgestellt werden sollen, Docker-Images, in denen Ihre Anwendung oder Ihre Dienste eingebettet sind. Diese Images werden per Push an eine *Docker-Registrierung* übertragen oder auf ihr veröffentlicht (dabei kann es sich um ein privates Repository in der Art der Azure Container Registry oder um ein öffentliches wie die Docker Hub-Registrierung handeln, die verbreitet für offizielle Basisimages verwendet wird).

Dies ist das grundlegende Konzept: Die CI-Pipeline wird durch einen Commit an ein SCC-Repository wie Git gestartet. Der Commit bewirkt, dass Azure DevOps Services einen Buildauftrag innerhalb eines Docker-Containers ausführen und nach erfolgreichem Abschluss dieses Auftrags ein Docker-Image per Push in die Docker-Registrierung übertragen, wie in Abbildung 5–2 dargestellt. Der erste Teil der äußeren Schleife umfasst die Schritte 1 bis 3, von der Codeerstellung, Ausführung, Debuggen und Validierung, über das Coderepository bis hin zu den CI-Schritten für Erstellen und Testen.

![Diagramm, das die am CI-Workflow beteiligten drei Schritte zeigt.](./media/docker-application-outer-loop-devops-workflow/continuous-integration-steps.png)

**Abbildung 5-2**. Die in CI enthaltenen Schritte

Dies sind die grundlegenden Schritte im CI-Workflow mit Docker und Azure DevOps Services:

1. Der Entwickler übermittelt einen Commit per Push an ein SCC-Repository (Git/Azure DevOps Services, GitHub usw.).

2. Wenn Sie Azure DevOps Services oder Git verwenden, ist CI integriert, was bedeutet, dass Sie einfach nur ein Kontrollkästchen in den Azure DevOps Services aktivieren müssen. Wenn Sie eine externe SCC (wie GitHub) verwenden, benachrichtigt ein `webhook` Azure DevOps Services über das Update oder führt einen Push auf Git/GitHub aus.

3. Azure DevOps Services ruft das SCC-Repository ab, einschließlich des Dockerfiles mit der Beschreibung des Images, sowie den Anwendungs- und Testcode.

4. Azure DevOps Services erstellt ein Docker-Image und bezeichnet es mit einer Buildnummer.

5. Azure DevOps Services instanziiert den Docker-Container innerhalb des bereitgestellten Docker-Hosts und führt die geeigneten Tests aus.

6. Wenn die Tests erfolgreich sind, wird das Image zuerst mit einem aussagekräftigen Namen neu benannt, damit Sie wissen, dass es sich um einen „verbürgten Build“ (wie etwa „/1.0.0“ oder eine beliebige andere Bezeichnung) handelt, und anschließend per Push in Ihre Docker-Registrierung (Docker Hub, Azure Container Registry, DTR usw.) übertragen.

### <a name="implementing-the-ci-pipeline-with-azure-devops-services-and-the-docker-extension-for-azure-devops-services"></a>Implementieren der CI-Pipeline mit Azure DevOps Services und der Docker-Erweiterung für Azure DevOps Services

Visual Studio Azure DevOps Services enthält Build- und Releasevorlagen, die Sie in Ihrer CI/CD-Pipeline verwenden können. Mithilfe dieser Pipeline können Sie Docker-Images per Push in eine authentifizierte Docker-Registrierung übertragen, Docker-Images ausführen oder andere an der Docker-Eingabeaufforderung verfügbare Vorgänge ausführen. Außerdem wird eine Docker Compose-Aufgabe hinzugefügt, mit der Sie Docker-Anwendungen für mehrere Container erstellen, per Push übertragen und ausführen sowie andere von der Docker Compose-Eingabeaufforderung angebotene Vorgänge ausführen können, wie in Abbildung 5–3 dargestellt.

![Screenshot der Docker CI-Pipeline in Azure DevOps.](./media/docker-application-outer-loop-devops-workflow/docker-ci-pipeline-azure-devops.png)

**Abbildung 5-3**. Die Docker CI-Pipeline in Azure DevOps Services einschließlich Build- und Releasevorlagen und verwandten Aufgaben.

Sie können diese Vorlagen und Aufgaben verwenden, um Ihre CI/CD-Artefakte für das Erstellen/Testen und Bereitstellen in Azure Service Fabric, Azure Kubernetes Service und ähnlichen Angeboten zu erstellen.

Mit diesen Visual Studio Team Services-Aufgaben, einem in Azure bereitgestellten Linux-Docker Host bzw. einer VM und Ihrer bevorzugten Docker-Registrierung (Azure Container Registry, Docker Hub, privatem Docker DTR oder einer beliebigen anderen Docker-Registrierung) können Sie Ihre Docker CI-Pipeline auf sehr konsistente Weise aufbauen.

***Anforderungen:***

- Azure DevOps Services oder Team Foundation Server 2015 Update 3 oder höher für lokale Installationen.

- Ein Azure DevOps Services-Agent, der über die Docker-Binarys verfügt.

  Eine einfache Möglichkeit zum Erstellen eines dieser Agents besteht darin, Docker zum Ausführen eines Containers zu verwenden, der auf dem Docker-Image des Azure DevOps Services-Agent basiert.

> [!INFORMATION] Weitere Informationen zur Zusammenstellung einer Azure DevOps Services Docker CI-Pipeline und eine Möglichkeit zum Anzeigen der exemplarischen Vorgehensweisen finden Sie auf diesen Websites:
>
> - Ausführen eines Visual Studio Team Services-Agents (jetzt Azure DevOps Services) als Docker-Container: \
>   <https://hub.docker.com/_/microsoft-azure-pipelines-vsts-agent>
>
> - Erstellen von .NET Core Linux-Docker-Images mit Azure DevOps Services: \
>   <https://docs.microsoft.com/archive/blogs/stevelasker/building-net-core-linux-docker-images-with-visual-studio-team-services>
>
> - Erstellen eines Linux-basierten Visual Studio Team Service-Buildcomputers mit Docker-Unterstützung: \
>   <http://donovanbrown.com/post/2016/06/03/Building-a-Linux-Based-Visual-Studio-Team-Service-Build-Machine-with-Docker-Support>

### <a name="integrate-test-and-validate-multi-container-docker-applications"></a>Integrieren, Testen und Validieren von Docker-Anwendungen mit mehreren Containern

Die meisten Docker-Anwendungen bestehen normalerweise aus mehreren Containern anstelle eines einzelnen Containers. Ein gutes Beispiel bildet eine an Microservices ausgerichtete Anwendung, für die Sie pro Microservice einen Container verwenden würden. Aber auch ohne strikte Beachtung des Microservice-Ansatzes ist es wahrscheinlich, dass Ihre Docker-Anwendung sich aus mehreren Containern oder Diensten zusammensetzen würde.

Daher müssen Sie nach dem Erstellen der Anwendungscontainer in der CI-Pipeline die gesamte Anwendung mit allen ihren Containern in einem Docker-Integrationshost oder sogar auf einem Testcluster, an den Sie Ihre Container verteilen, bereitstellen, integrieren und testen.

Wenn Sie einen einzelnen Host verwenden, können Sie Docker-Befehle wie „docker-compose“ zum Erstellen und Bereitstellen von zugehörigen Containern zum Testen und Überprüfen der Docker-Umgebung auf einem einzelnen virtuellen Computer verwenden. Wenn Sie aber mit einem Orchestratorcluster wie DC/OS, Kubernetes oder Docker Swarm arbeiten, müssen Sie Ihre Container mithilfe eines anderen Mechanismus oder Orchestrators bereitstellen, abhängig von dem gewählten Cluster/Scheduler.

Im Folgenden finden Sie verschiedene Arten von Tests, die Sie für Docker-Container ausführen können:

- Komponententests für Docker-Container

- Testen von Gruppen von aufeinander bezogenen Anwendungen oder Microservices

- Tests in der Produktion und "Canary Release"-Versionen

Der wichtige Punkt ist hier, dass Integrations- und Funktionstests von außerhalb der Container ausgeführt werden müssen. Die Tests sind nicht in den von Ihnen bereitgestellten Containern enthalten und werden nicht in ihnen ausgeführt, da die Container auf statischen Images basieren, die exakt mit denen übereinstimmen sollten, die Sie in der Produktionsumgebung bereitstellen.

Eine praktische Option beim Testen komplexerer Szenarien, etwa solcher, die mehrere Cluster beinhalten (Testcluster, Stagingcluster und Produktionscluster), besteht darin, die Images in einer Registrierung zu veröffentlichen, damit sie in verschiedenen Clustern getestet werden können.

### <a name="push-the-custom-application-docker-image-into-your-global-docker-registry"></a>Übertragen Sie das benutzerdefinierte Docker-Anwendungsimage per Push in Ihre globale Docker-Registrierung

Nachdem die Docker-Images getestet und validiert wurden, ist es sinnvoll, sie zu kennzeichnen und in Ihrer Docker-Registrierung zu veröffentlichen. Die Docker-Registrierung stellt eine wesentliche Komponente im Lebenszyklus von Docker-Anwendungen dar, da sie der zentrale Ort ist, an dem Sie Ihren benutzerdefinierten Test (auch als „verbürgtes Image“ bezeichnet) für die Bereitstellung in den QA- und Produktionsumgebungen speichern.

In ähnlicher Weise, wie der in Ihrem SSC-Repository (Git usw.) gespeicherte Anwendungscode Ihre SSOT (Single Source of Truth) ist, stellt die Docker-Registrierung Ihre SSOT für Ihre binäre Anwendung oder für die in der QA- oder Produktionsumgebung bereitzustellenden Anwendungsteile dar.

Normalerweise ist es sinnvoll, private Repositorys für Ihre benutzerdefinierten Images entweder in einem privaten Repository in der Azure Container Registry, in einer lokalen Registrierung wie der Docker Trusted Registry oder in einer öffentlichen Cloudregistrierung mit eingeschränktem Zugriff (wie Docker Hub) aufzubewahren, mit der Einschränkung, dass Sie im letzten Fall der Sicherheit des Anbieters vertrauen müssen, falls Ihr Code nicht Open Source ist. Die eingesetzten Methoden sind in allen Fällen ähnlich und basieren auf dem `docker push`-Befehl, wie in Abbildung 5–4 dargestellt.

![Diagramm, das den Pushvorgang benutzerdefinierter Images in eine Containerregistrierung zeigt.](./media/docker-application-outer-loop-devops-workflow/docker-push-custom-images.png)

**Abbildung 5-4**. Veröffentlichen von benutzerdefinierten Images in der Docker-Registrierung

Zum Aufbau der Integration und zum Testen (CI) in Schritt 3 können Sie die resultierenden Docker-Images in einer privaten oder öffentlichen Registrierung veröffentlichen. Es gibt viele Angebote für Docker-Registrierungen von Cloudanbietern, wie Azure Container Registry, Amazon Web Services Container Registry, Google Container Registry, Quay Registry usw.

Mithilfe der Docker-Aufgaben können Sie eine Reihe von Dienstimages, die durch eine `docker-compose.yml`-Datei definiert sind, mit mehreren Tags per Push an eine authentifizierte Docker-Registrierung (wie die Container Registry) übertragen, wie in Abbildung 5–5 dargestellt.

![Screenshot, der den Schritt zum Veröffentlichen von Images in einer Registrierung zeigt.](./media/docker-application-outer-loop-devops-workflow/publish-custom-image-to-docker-registry.png)

**Abbildung 5-5**. Verwenden von Azure DevOps Services zum Veröffentlichen benutzerdefinierter Images in einer Docker-Registrierung

> [!INFORMATION] Weitere Informationen zur Azure Container Registry finden Sie unter <https://aka.ms/azurecontainerregistry>.

## <a name="step-4-cd-deploy"></a>Schritt 4: CD, Bereitstellen

Die Unveränderlichkeit von Docker-Images stellt eine wiederholbare Bereitstellung von dem sicher, was entwickelt, mithilfe von CI getestet und in der Produktionsumgebung bereitgestellt wird. Nachdem Sie die Docker-Anwendungsimages in Ihrer Docker-Registrierung (privat oder öffentlich) veröffentlicht haben, können Sie sie aus Ihrer CD-Pipeline mithilfe von Azure DevOps Services-Pipelineaufgaben oder Azure DevOps Services Release Management in Ihren verschiedenen Umgebungen (Produktion, QA, Staging usw.) bereitstellen.

Allerdings hängt es an diesem Punkt davon ab, welche Art Docker-Anwendung Sie bereitstellen. Das Bereitstellen einer einfachen Anwendung (unter den Gesichtspunkten von Zusammensetzung und Bereitstellung) wie einer monolithischen Anwendung, die ein paar Container oder Dienste umfasst und auf ein paar Servern oder VMs bereitgestellt wird, unterscheidet sich vom Bereitstellen komplexerer Anwendungen, wie einer an Microservices orientierten Anwendung mit Hyperskalierung. Diese zwei Szenarien werden in den folgenden Abschnitten erläutert.

### <a name="deploying-composed-docker-applications-to-multiple-docker-environments"></a>Bereitstellen von zusammengesetzten Docker-Anwendungen in mehreren Docker-Umgebungen

Sehen wir uns zunächst das weniger komplizierte Szenario an: das Bereitstellen auf einfachen Docker-Hosts (VMs oder Servern) in einer einzelnen Umgebung oder mehreren Umgebungen (QA, Staging und Produktion). In diesem Szenario kann Ihre CD-Pipeline intern docker-compose (aus Ihren Azure DevOps Services-Bereitstellungsaufgaben) verwenden, um die Docker-Anwendungen mit ihrem zugehörigen Satz von Containern oder Diensten bereitzustellen, wie in Abbildung 5–6 dargestellt.

![Diagramm, das den Schritt für die CD-Bereitstellung in drei Umgebungen zeigt.](./media/docker-application-outer-loop-devops-workflow/deploy-app-containers-to-docker-host-environments.png)

**Abbildung 5–6**. Bereitstellen von Anwendungscontainern in einer Registrierung für einfache Docker-Hostumgebungen

Abbildung 5–7 hebt hervor, wie Sie Ihre Build-CI mithilfe von Azure DevOps Services mit QA-/Testumgebungen verbinden können, indem Sie im Dialogfeld „Aufgabe hinzufügen“ auf „Docker Compose“ klicken. Beim Bereitstellen in Staging- oder Produktionsumgebungen würden jedoch normalerweise Funktionen der Releaseverwaltung zum Einsatz kommen, die mehrere Umgebungen (wie QA, Staging und Produktion) behandeln. Wenn Sie auf einzelnen Docker-Hosts bereitstellen, wird die Aufgabe „Docker Compose“ von Azure DevOps Services verwendet (die hinter den Kulissen den `docker-compose up`-Befehl aufruft). Wenn Sie in Azure Kubernetes Service (AKS) bereitstellen, wird die Docker-Bereitstellungsaufgabe verwendet, wie im anschließenden Abschnitt erläutert.

![Screenshot, der das Dialogfeld „Aufgaben hinzufügen“ der Docker Compose-Aufgabe zeigt.](./media/docker-application-outer-loop-devops-workflow/add-tasks-docker-compose.png)

**Abbildung 5-7**. Hinzufügen einer Docker Compose-Aufgabe in einer Azure DevOps Services-Pipeline

Wenn Sie ein Release in Azure DevOps Services erstellen, wird ein Satz Eingabeartefakte benötigt. Diese Artefakte sollen für die Lebensdauer des Release für alle Umgebungen unveränderlich sein. Wenn Sie Container einführen, bezeichnen die Eingabeartefakte bereitzustellende Images in einer Registrierung. Je nachdem, wie diese Images identifiziert werden, besteht keine Garantie, dass sie über die Dauer des Release gleich bleiben – der offensichtlichste Fall ist der Verweis auf `myimage:latest` aus einer `docker-compose`-Datei.

Die Azure DevOps Services-Vorlagen geben Ihnen die Möglichkeit, Buildartefakte zu generieren, die bestimmte Registrierungsimagedigests enthalten, die die gleiche Imagebinärdatei garantiert eindeutig identifizieren. Das ist die Art Eingabe, die Sie sich wirklich als Grundlage eines Release wünschen.

### <a name="managing-releases-to-docker-environments-by-using-azure-devops-services-release-management"></a>Verwalten von Releases in Docker-Umgebungen mithilfe von Azure DevOps Services Release Management

Mithilfe der Azure DevOps Services-Vorlagen können Sie ein neues Image erstellen, es in einer Docker-Registrierung veröffentlichen, es auf Linux- oder Windows-Hosts ausführen und Befehle wie `docker-compose` verwenden, um mehrere Container als vollständige Anwendung bereitzustellen, all das mithilfe der Funktionen von Azure DevOps Services Release Management, die für mehrere Umgebungen bestimmt sind, wie in Abbildung 5–8 dargestellt.

![Screenshot, der die Konfiguration von Docker Compose-Releases zeigt.](./media/docker-application-outer-loop-devops-workflow/configure-docker-compose-release.png)

**Abbildung 5-8**. Konfigurieren von Azure DevOps Services Docker Compose-Aufgaben in Azure DevOps Services Release Management

Bedenken Sie jedoch, dass es sich bei dem in Abbildung 5–6 gezeigten und in Abbildung 5–8 implementierten Szenario um ein einfaches handelt (es wird auf einzelnen Docker-Hosts und VMs bereitgestellt, und es gibt einen einzelnen Container bzw. eine einzelne Instanz pro Image), das wahrscheinlich nur für Entwicklungs- und Testszenarien verwendet wird. In den meisten Produktionsszenarien in Unternehmen würden Sie wohl Hochverfügbarkeit (High Availability, HA) und komfortabel zu verwaltende Skalierbarkeit mithilfe von Lastenausgleich über mehrere Knoten, Server und VMs hinweg und zuzüglich „intelligentes Failover“ fordern, sodass beim Ausfall eines Servers oder Knotens dessen Dienste und Container auf einen anderen Hostserver oder in eine andere VM verschoben würden. In diesem Fall benötigen Sie weiter fortgeschrittene Technologien, wie Containercluster, Orchestratoren und Scheduler. Das Verfahren zum Bereitstellen auf solchen Clustern beruht daher in der Beherrschung der fortgeschrittenen Szenarien, die im nächsten Abschnitt erläutert werden.

### <a name="deploying-docker-applications-to-docker-clusters"></a>Bereitstellen von Docker-Anwendungen auf Docker-Clustern

Verteilte Anwendungen erfordern ihrem Wesen nach Computeressourcen, die ebenfalls verteilt sind. Für Funktionalität im Produktionsmaßstab benötigen Sie Clusterfunktionen, die hohe Skalierbarkeit und Hochverfügbarkeit auf der Grundlage gepoolter Ressourcen zur Verfügung stellen.

Sie könnten aus einem CLI-Tool oder von einer Webbenutzeroberfläche aus Container manuell auf diesen Clustern bereitstellen, aber Sie sollten diese Art von manueller Arbeit für Spotchecks bei der Bereitstellung oder Verwaltungszwecke wie horizontales Skalieren oder Überwachung reservieren.

Unter CD-Gesichtspunkten und insbesondere im Hinblick auf Azure DevOps Services können Sie speziell erstellte Bereitstellungsaufgaben aus Ihren Azure DevOps Services Release Management-Umgebungen ausführen, die Ihre in Containern verpackten Anwendungen im Containerdienst auf verteilten Clustern bereitstellen, wie in Abbildung 5–9 veranschaulicht.

![Diagramm, das den Schritt für die CD-Bereitstellung in Orchestratoren zeigt.](./media/docker-application-outer-loop-devops-workflow/cd-deploy-to-orchestrators.png)

**Abbildung 5-9**. Bereitstellen von verteilten Anwendungen im Containerdienst

Beim Bereitstellen auf bestimmten Clustern oder Orchestratoren würden Sie traditionell von spezifischen Bereitstellungsskripts und für jeden Orchestrator spezifischen Mechanismen ausgehen (d.h. die Bereitstellungsmechanismen von Kubernetes und Service Fabric unterscheiden sich), statt das einfachere und komfortable `docker-compose`-Tool zu verwenden, das auf der `docker-compose.yml`-Definitionsdatei basiert. Aufgrund der Docker-Bereitstellungsaufgabe von Azure DevOps Services, die in Abbildung 5–10 dargestellt ist, können Sie jetzt auch auf den unterstützten Orchestratoren bereitstellen, indem Sie einfach Ihre vertraute `docker-compose.yml`-Datei verwenden, da das Tool die erforderliche „Übersetzung“ für Sie vornimmt (von Ihrer `docker-compose.yml`-Datei in das für den Orchestrator erforderliche Format).

![Screenshot, der die Aufgabe „In Kubernetes bereitstellen“ zeigt.](./media/docker-application-outer-loop-devops-workflow/add-deploy-to-kubernetes-task.png)

**Abbildung 5-10**. Hinzufügen der Aufgabe zum Bereitstellen in Kubernetes zu Ihrer Umgebung

Abbildung 5–11 veranschaulicht, wie Sie die Aufgabe „Für Kubernetes bereitstellen“ mit den zur Konfiguration verfügbaren Abschnitten bearbeiten können. Dies ist die Aufgabe, die Ihre verwendungsbereiten benutzerdefinierten Docker-Images für die Bereitstellung als Container im Cluster abruft.

![Screenshot, der die Konfiguration der Aufgabe „In Kubernetes bereitstellen“ zeigt.](./media/docker-application-outer-loop-devops-workflow/edit-deploy-to-kubernetes-task.png)

**Abbildung 5-11**. Definition der Docker-Bereitstellungsaufgabe bei der Bereitstellung für ACS DC/OS

> [!INFORMATION] Weitere Informationen zur CD-Pipeline mit Azure DevOps Services und Docker finden Sie unter <https://azure.microsoft.com/services/devops/pipelines>

## <a name="step-5-run-and-manage"></a>Schritt 5: Ausführen und Verwalten

Da das Ausführen und Verwalten von Anwendungen in Produktionsumgebungen auf Unternehmensniveau ein eigenes, wichtiges Thema ist und aufgrund der Art der Vorgänge und Personen, die auf dieser Ebene (IT-Operations) arbeiten sowie dem großen Umfang dieses Gebiets, ist ihm das gesamte nächste Kapitel gewidmet.

## <a name="step-6-monitor-and-diagnose"></a>Schritt 6: Überwachen und Diagnostizieren

Dieses Thema wird ebenfalls im nächsten Kapitel als Teil der Aufgaben behandelt, die IT in Produktionssystemen ausführt. Es muss aber hervorgehoben werden, dass die in diesem Schritt erhaltenen Erkenntnisse an das Entwicklungsteam rückgekoppelt werden müssen, sodass die Anwendung fortlaufend verbessert wird. Unter diesem Blickwinkel ist es ebenfalls Teil von DevOps, obwohl die Aufgaben und Betriebsvorgänge normalerweise von der IT-Abteilung durchgeführt werden.

Nur wenn Überwachung und Diagnose zu 100 % im Zugriffsbereich von DevOps liegen, werden die vom Entwicklungsteam durchgeführten Überwachungsprozesse und Analysen in Test- oder Betaumgebungen ausgeführt. Dies erfolgt entweder in Form von Auslastungstests oder durch Überwachen von Beta- oder QA-Umgebungen, in denen Betatester die neuen Versionen ausprobieren.

>[!div class="step-by-step"]
>[Zurück](index.md)
>[Weiter](create-ci-cd-pipelines-azure-devops-services-aspnetcore-kubernetes.md)
