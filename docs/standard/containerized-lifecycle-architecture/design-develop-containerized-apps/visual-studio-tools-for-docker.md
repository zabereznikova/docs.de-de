---
title: Visual Studio-Tools für Docker unter Windows
description: Lebenszyklus von Docker-Containeranwendungen mit der Microsoft-Plattform und Tools
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/12/2018
ms.custom: vs-dotnet
ms.openlocfilehash: cd140c12ef4a0187cce096e013937d5c98cd4b39
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2018
ms.locfileid: "47170794"
---
# <a name="using-visual-studio-tools-for-docker-visual-studio-on-windows"></a>Verwenden von Visual Studio-Tools für Docker (Visual Studio unter Windows)

Visual Studio-Tools für Docker-Entwicklungsworkflow ist vergleichbar mit der Verwendung von Visual Studio Code und Docker-CLI (er die gleichen Docker-Befehlszeilenschnittstelle basiert auf). Visual Studio-Tools für Docker es auch erleichtert für den Einstieg, den Prozess vereinfacht und höhere Produktivität für den Build bietet, führen, und Verfassen von Aufgaben. Ausführen und Debuggen Sie Ihre Container per simple Aktionen wie das **F5** und **STRG**+**F5**.

> [!NOTE]
> In diesem Artikel gilt für Visual Studio unter Windows und nicht in Visual Studio für Mac.

## <a name="configure-your-local-environment"></a>Konfigurieren der lokalen Umgebung

Mit den neuesten Versionen von Docker für Windows ([https://docs.docker.com/docker-for-windows/](https://docs.docker.com/docker-for-windows/)), die einfache Einrichtung erleichtert Ihnen die Docker-Anwendungen zu entwickeln.

Docker-Unterstützung ist in Visual Studio 2017 enthalten. Visual Studio 2017 hier herunterladen: [https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs)

## <a name="use-docker-tools-in-visual-studio-2017"></a>Verwenden von Docker-Tools in Visual Studio 2017

Es gibt zwei Ebenen der Docker-Unterstützung, die Sie einem Projekt hinzufügen können. Sie können einfach hinzufügen, in .NET Core-Web-app-Projekten, eine *dockerfile-Datei* Datei in das Projekt durch Aktivieren der Docker-Unterstützung. Die nächste Ebene ist die Unterstützung für containerorchestrator, der hinzufügt eine *dockerfile-Datei* auf das Projekt (sofern nicht bereits vorhanden) und ein *"Docker-Compose.yml"* Datei auf Projektmappenebene.

Die **hinzufügen** > **Docker-Unterstützung** und **hinzufügen** > **Unterstützung für Containerorchestrator** Befehle sind befindet sich auf der rechten Maustaste (oder Kontextmenü) des Projektknotens für eine Web-app-Projekt im **Projektmappen-Explorer**, wie in Abbildung 4-26 veranschaulicht:

![Menüoption für Docker-Unterstützung in Visual Studio hinzufügen](media/add-docker-support-menu.png)

Abbildung 4-26: Hinzufügen von Docker-Unterstützung zu einem Visual Studio 2017-Projekt

### <a name="add-docker-support"></a>Docker-Unterstützung hinzufügen

Sie können Docker-Unterstützung zu einem vorhandenen .NET Core Web-app-Projekt hinzufügen, indem Sie die Auswahl **hinzufügen** > **Docker-Unterstützung** in **Projektmappen-Explorer**. Sie können auch Docker-Unterstützung während der projekterstellung aktivieren, indem Sie auswählen **Aktivieren der Unterstützung für Docker** in die **neue ASP.NET Core-Webanwendung** geöffnet, nachdem Sie auf **OK** in die **neues Projekt** Dialogfeld wie in Abbildung 4-27 dargestellt.

![Aktivieren von Docker-Unterstützung für neue ASP.NET Core-Web-app in Visual Studio](./media/enable-docker-support-visual-studio.png)

Abbildung 4-27: Aktivieren von Docker-Unterstützung während der projekterstellung in Visual Studio 2017

Wenn Sie hinzufügen oder Docker-Unterstützung aktivieren, fügt Visual Studio eine *dockerfile-Datei* Datei zum Projekt.

> [!NOTE]
> Wenn Sie Docker Compose-Unterstützung während der projekterstellung für ein .NET Framework Web-app-Projekt (kein .NET Core Web-app-Projekt) aktivieren, wie in Abbildung 4-28 dargestellt, wird auch Unterstützung für containerorchestrator hinzugefügt.
>
> ![Aktivieren von Docker compose-Unterstützung für ein .NET Framework-Web-app-Projekt](media/enable-docker-compose-support.png)

> Abbildung 4-28: Aktivieren der Unterstützung für Docker Compose auf eine .NET Framework-Web-app-Projekt in Visual Studio 2017

### <a name="add-container-orchestrator-support"></a>Unterstützung für containerorchestrator hinzufügen

Wenn Sie eine Lösung mit mehreren Containern erstellen möchten, fügen Sie Unterstützung für containerorchestrator zu Ihren Projekten hinzu. Wenn Sie Unterstützung für containerorchestrator hinzufügen, fügt Visual Studio eine *dockerfile-Datei* zum Projekt (sofern nicht bereits vorhanden) und eine globale *"Docker-Compose.yml"* Datei auf Projektmappenebene. Dadurch können Sie die ausführen und Debuggen eine Gruppe von Containern (eine gesamte Projektmappe) zur gleichen Zeit, wenn sie in der gleichen definiert *"Docker-Compose.yml"* Datei. Wenn *"Docker-Compose.yml"* bereits vorhanden ist, Visual Studio fügt nur die erforderlichen Zeilen Konfigurationscode hinzu.

Nachdem Sie die Orchestrierung von containerunterstützung zu Ihrem Projekt hinzufügen, werden Sie sehen eine dockerfile-Datei dem Projekt hinzugefügt und ein **Docker-compose-** hinzugefügt, um die Projektmappe im Ordner **Projektmappen-Explorer**, wie in Abbildung 4-29 dargestellt:

![Docker-Dateien im Projektmappen-Explorer in Visual Studio](media/docker-support-solution-explorer.png)

Abbildung 4-29: Docker-Dateien im Projektmappen-Explorer in Visual Studio 2017

**Weitere Informationen:** finden Sie weitere Informationen zu den Dienste-Implementierung und Verwendung von Visual Studio-Tools für Docker, in den folgenden Artikeln:

Erstellen, Debuggen, aktualisieren und Aktualisieren von apps in einem lokalen Docker-Container: [https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh/](https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh)

Bereitstellen eines ASP.NET Core-Docker-Containers in einer containerregistrierung an: [https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker/](https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker)

>[!div class="step-by-step"]
[Zurück](docker-apps-inner-loop-workflow.md)
[Weiter](set-up-windows-containers-with-powershell.md)