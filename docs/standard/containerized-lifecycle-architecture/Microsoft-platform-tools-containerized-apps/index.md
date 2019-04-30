---
title: Einführung in die Microsoft-Plattform und -Tools für Container-Apps
description: Lernen Sie die Microsoft Lösungen zur Unterstützung der Lebenszyklus von Docker-Anwendungen zu kennen.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/15/2019
ms.openlocfilehash: 8536703a520434c0e393c5f46005c2ac02d5d849
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61934659"
---
# <a name="introduction-to-the-microsoft-platform-andtools-for-containerized-apps"></a>Einführung in die Microsoft-Plattform und-Tools für Container-apps

*Vision: Erstellen Sie ein anpassungsfähiger, Unternehmen, Containern Anwendungslebenszyklus, die Ihre Entwicklung, IT-Betrieb und produktionsverwaltung umfasst.*

Abbildung 3-1 zeigt die Hauptpfeiler im Lebenszyklus von Docker-Apps, die nach der Art der von mehreren Teams geleisteten Arbeit klassifiziert sind (App-Entwicklung, DevOps-Infrastrukturprozesse und IT-Verwaltung und -Betrieb). Normalerweise sind im Unternehmen die Profile der „Rollen“, die für jeden Bereich zuständig sind, unterschiedlich. Genau wie ihre Fähigkeiten.

![Microsoft-Tools. Für die arbeitsauslastung zum Entwickeln/entwerfen: Docker-Modul für Windows, Visual Studio und Visual Studio Code, .NET Core, Azure Kubernetes Service. Für den Build/Test/Ship-Workload: Azure DevOps für Team Foundation Server, Docker CLI, Azure Kubernetes-Dienst. Für die Workload ausführen/überwachen/verwalten: Azure Monitor, Azure-Portal Azure Kubernetes-Dienste, Service Fabric, andere orchestratoren.](./media/image1.png)

**Abbildung 3-1.** Hauptpfeiler im Lebenszyklus von Docker-containeranwendungen mit Microsoft-Plattform und-Tools

Ein containerisierten Docker Lebenszyklus-Workflows kann anfangs ausführlichen basierend auf "standardmäßiger Produktauswahl," erleichtert Ihnen die für Entwickler schneller Einstieg ist aber entscheidend, dass im Hintergrund ein offenes Framework ist, damit er kann ein Flexible Workflow kann an die unterschiedlichen Kontexte jeder Organisation oder das Unternehmen anpassen. Die Workflowinfrastruktur (Komponenten und Produkte) muss flexibel genug sein, um die Umgebung abzudecken, die jedes Unternehmen in der Zukunft haben wird, und sie muss sogar in der Lage sein, Entwicklungs- oder DevOps-Produkte gegen andere auszutauschen. Diese Flexibilität, Offenheit und eine breite Auswahl an Technologien in der Plattform und Infrastruktur sind genau die Prioritäten von Microsoft für Docker-Containeranwendungen, wie in den folgenden Kapiteln erläutert wird.

Tabelle 3-1 zeigt, dass die Absicht von Microsoft DevOps für Docker-Containeranwendungen darin besteht, einen offenen DevOps-Workflow bereitzustellen, sodass Sie auswählen können, welche Produkte für jede Phase (Microsoft oder Drittanbieter) verwendet werden sollen, während ein vereinfachter Workflow zur Verfügung steht, der bereits verbundene „standardmäßige Produkte“ bereitstellt. So können Sie schnell mit Ihrem DevOps-Workflow für Docker-Apps auf Unternehmensebene beginnen.

**Tabelle 3-1.** DevOps-Workflows, die an eine beliebige Technologie öffnen

| Host | Microsoft-Technologien | Drittanbieter, in Azure integrierbar |
| ---------------------------| ----------------------------------------------------| --------------------------------------------------------------------------------|
| Plattform für Docker-Apps   | • Microsoft Visual Studio und Visual Studio Code<br /> • .NET<br /> • Microsoft Azure Container Service<br /> • Azure Service Fabric<br /> • Azure Container Registry<br /> | • Beliebiger Code-Editor (z.B. Sublime)<br /> • Beliebige Sprache (Node.js, Java, Go usw.)<br /> • Beliebiger Orchestrator und Scheduler<br /> • Beliebige Docker-Registrierung<br /> |
| DevOps für Docker-Apps     | • Azure DevOps-Dienste<br /> • Microsoft Team Foundation Server<br /> • Azure Container Service<br /> • Azure Service Fabric<br /> | • GitHub, Git, Subversion usw.<br /> • Jenkins, Chef, Puppet, Velocity, CircleCI, TravisCI usw.<br /> • Lokales Docker-Datencenter, Docker Swarm, Mesos DC/OS, Kubernetes usw.<br /> |
| Verwaltung und Überwachung  | • Operations Management Suite<br /> • Applications Insights<br /> | • Marathon, Chronos usw.<br />

Die Microsoft-Plattform und die Tools für containerisierte Docker-Anwendungen, wie in Tabelle 3-1 definiert, bestehen aus den folgenden Komponenten:

- **Plattform für die Entwicklung von Docker Apps**: Die Entwicklung eines Diensts oder einer Sammlung von Diensten, aus denen sich eine „App“ zusammensetzt. Die Entwicklungsplattform stellt alle Aufgaben bereit, die Entwickler benötigen, bevor sie ihren Code in ein gemeinsames Coderepository mithilfe von Push verschieben. Entwicklung von Diensten, die als Container bereitgestellt sind vergleichbar mit der Entwicklung derselben Anwendungen oder Dienste ohne Docker. Sie weiterhin Ihre bevorzugte Sprache (.NET, Node.js, Go usw.) und den bevorzugten Editor oder die IDE wie Visual Studio oder Visual Studio Code verwenden. Anstatt Docker jedoch als Bereitstellungsziel zu betrachten, entwickeln Sie Ihre Dienste in der Docker-Umgebung. Die Erstellung, das Ausführen und Testen sowie das Debuggen Ihres Codes erfolgt lokal in Containern, und Sie stellen die Zielumgebung zur Entwicklungszeit zur Verfügung. Indem sie die Zielumgebung lokal bereitstellen, richten Docker-Container eine Umgebung ein, die Sie erheblich dabei unterstützen wird, Ihren DevOps-Lebenszyklus zu optimieren. Visual Studio und Visual Studio Code verfügen über Erweiterungen für die Integration von Docker-Containern in Ihren Entwicklungsprozess.

- **DevOps für Docker-Apps** können Entwickler, die Docker-Anwendungen erstellen [Azure DevOps-Dienste](https://azure.microsoft.com/services/devops/) oder einem anderen Drittanbieter-Produkt, wie Jenkins, um eine umfassende automatisierte Anwendungslebenszyklus erstellen Management (ALM).

  Mit Azure DevOps-Dienste können Entwickler erstellen, Container ausgerichtete DevOps für einen schnellen, iterativen Prozess, der Quellcode-abdeckt, Steuern von jedem beliebigen Standort (Azure DevOps-Services-Git, GitHub, alle Git-Remoterepository oder Subversion), Continuous Integration (CI) , interne Komponententests, Integrationstests Kommunikation zwischen-container/Dienste, Continuous Delivery (CD) und releaseverwaltung (RM). Entwickler können auch ihre Docker-Anwendungsreleases in Azure Container Service automatisieren: von der Entwicklung bis hin zu Staging und Produktionsumgebungen.

- **Verwaltung und Überwachung** IT verwalten und Überwachen von Produktionsanwendungen und-Dienste auf unterschiedliche Weise beider Sichtweisen in einer konsolidierten Benutzeroberfläche integrieren können.

  - **Azure-Portal** , wenn Sie Open Source-orchestratoren verwenden, Azure Kubernetes Service (AKS), Service Fabric und andere orchestratoren helfen Ihnen beim Einrichten und Verwalten Ihrer Docker-Umgebungen. Wenn Sie Azure Service Fabric verwenden, ermöglicht Ihnen das Tool Service Fabric Explorer die Visualisierung und Konfiguration Ihres Clusters.

  - **Docker-Tools** : Sie können Ihre Containeranwendungen mit vertrauten Tools verwalten. Es besteht keine Notwendigkeit, Ihre vorhandenen Docker-Verwaltungsverfahren zu ändern, um Containerworkloads in die Cloud zu verschieben. Nutzen Sie die Ihnen bereits vertrauten Anwendungsverwaltungstools, und verbinden Sie sich über die API-Standardendpunkte mit dem Orchestrator Ihrer Wahl. Sie können auch andere Tools von Drittanbietern verwenden, um Ihre Docker-Anwendungen zu verwalten, z.B. Docker Datacenter oder sogar CLI-Tools von Docker. 

    Auch wenn Sie mit Linux-Befehlen vertraut sind, können Sie Ihre containeranwendungen mit Microsoft Windows und PowerShell mit einer Linux-Subsystem-Befehlszeile und die Produkte (Docker, Kubernetes,...)-Clients auf diese Funktion für die Linux-Subsystem unter verwalten. Sie erfahren mehr zur Verwendung dieser Tools unter Linux-Subsystem, die mit Ihrem bevorzugten Microsoft-Windows-Betriebssystem weiter unten in diesem Buch.

  - **Open-Source-Tools** da AKS stellt die API-Standardendpunkte für die Orchestrierungs-Engine, die beliebtesten Tools mit ACS kompatibel sind und in den meisten Fällen funktionieren sofort – einschließlich Visualisierung, Überwachung und Befehlszeilentools und sogar zukünftige Tools, sobald diese verfügbar werden.

  - **Azure Monitor** wird von Azure-Lösung für jeden Winkel der produktionsumgebung zu überwachen. Sie können Docker-Produktionsanwendungen überwachen, indem Sie einfach deren SDK in Ihre Dienste einrichten, damit Sie vom System generierte Daten von den Anwendungen abrufen können.

Damit stellt Microsoft eine vollständige Grundlage für einen End-to-End-Lebenszyklus von Docker-Containeranwendungen breit. Es ist jedoch *eine Auflistung von Produkten und Technologien, mit denen Sie optional auswählen und integrieren in vorhandene tools und Prozesse*. Die Flexibilität durch einen umfassenden Ansatz und die Stärke der tiefgreifenden Funktionen versetzen Microsoft in eine starke Position für die Entwicklung von Docker-Containeranwendungen.

>[!div class="step-by-step"]
>[Zurück](../Docker-application-lifecycle/containers-foundation-for-devops-collaboration.md)
>[Weiter](../design-develop-containerized-apps/index.md)
