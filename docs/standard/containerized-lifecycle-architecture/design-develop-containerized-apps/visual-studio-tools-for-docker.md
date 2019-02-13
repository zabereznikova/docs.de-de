---
title: Visual Studio-Tools für Docker unter Windows
description: Lernen Sie kennen die Docker-Tools in Visual Studio 2017 Version 15.7 und höher verfügbar.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 11/23/2018
ms.custom: vs-dotnet
ms.openlocfilehash: a373a8ebfef605b9845a684d3987355f8841aa1b
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/13/2019
ms.locfileid: "56219541"
---
# <a name="using-visual-studio-tools-for-docker-visual-studio-on-windows"></a>Verwenden von Visual Studio-Tools für Docker (Visual Studio unter Windows)

Visual Studio-Tools für Docker-entwicklungsworkflows ähnelt der Workflow bei Verwendung von Visual Studio Code und Docker-CLI. In der Tat basiert auf der gleichen Docker-CLI, jedoch ist einfacher, um zu beginnen, bietet höhere Produktivität und vereinfacht den Prozess für den Build, ausführen und Tasks erstellen. Ausführen und Debuggen Sie Ihre Container per simple Aktionen wie das **F5** und **STRG**+**F5**. Mit der Unterstützung der Optionaler Container-Orchestrierung, sondern auch zum Ausführen und Debuggen von einem einzelnen Container können Sie ausführen und Debuggen eine Gruppe von Containern (eine gesamte Projektmappe) zur gleichen Zeit.

> [!NOTE]
> In diesem Artikel gilt für Visual Studio unter Windows und nicht in Visual Studio für Mac.

## <a name="configure-your-local-environment"></a>Konfigurieren der lokalen Umgebung

Mit den neuesten Versionen von Docker für Windows ([https://docs.docker.com/docker-for-windows/](https://docs.docker.com/docker-for-windows/)), die einfache Einrichtung erleichtert Ihnen die Docker-Anwendungen zu entwickeln.

Docker-Unterstützung ist in Visual Studio 2017 enthalten. Visual Studio 2017 hier herunterladen: [https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs)

## <a name="use-docker-tools-in-visual-studio-2017"></a>Verwenden von Docker-Tools in Visual Studio 2017

Es gibt zwei Ebenen der Docker-Unterstützung, die Sie einem Projekt hinzufügen können. Sie können einfach hinzufügen, in .NET Core-Web-app-Projekten, eine *dockerfile-Datei* Datei in das Projekt durch Aktivieren der Docker-Unterstützung. Die nächste Ebene ist die Orchestrierung die containerunterstützung, das hinzufügt eine *dockerfile-Datei* auf das Projekt (sofern nicht bereits vorhanden) und ein *"Docker-Compose.yml"* Datei auf Projektmappenebene. Orchestrierung von containerunterstützung über Docker Compose, wird standardmäßig in Visual Studio 2017, Version 15.7 oder früher hinzugefügt. Orchestrierung von containerunterstützung ist ein optionales Feature in Visual Studio 2017, Versionen 15.8 oder später in diesem Fall Docker Compose und Service Fabric werden unterstützt.

Die **hinzufügen** > **Docker-Unterstützung** und **hinzufügen** > **containerorchestrierung Unterstützung** Befehle sind befindet sich auf der rechten Maustaste (oder Kontextmenü) des Projektknotens für eine Web-app-Projekt im **Projektmappen-Explorer**, wie in Abbildung 4-26 veranschaulicht:

![Menüoption für Docker-Unterstützung in Visual Studio hinzufügen](media/add-docker-support-menu.png)

Abbildung 4-26: Hinzufügen von Docker-Unterstützung zu einem Visual Studio 2017-Projekt

### <a name="add-docker-support"></a>Docker-Unterstützung hinzufügen

Sie können Docker-Unterstützung zu einem vorhandenen .NET Core Web-app-Projekt hinzufügen, indem Sie die Auswahl **hinzufügen** > **Docker-Unterstützung** in **Projektmappen-Explorer**. Sie können auch Docker-Unterstützung während der projekterstellung aktivieren, indem Sie auswählen **Aktivieren der Unterstützung für Docker** in die **neue ASP.NET Core-Webanwendung** geöffnet, nachdem Sie auf **OK** in die **neues Projekt** Dialogfeld wie in Abbildung 4-27 dargestellt.

![Aktivieren von Docker-Unterstützung für neue ASP.NET Core-Web-app in Visual Studio](./media/enable-docker-support-visual-studio.png)

Abbildung 4-27: Aktivieren Sie Docker-Unterstützung, während der projekterstellung in Visual Studio 2017

Wenn Sie hinzufügen oder Docker-Unterstützung aktivieren, fügt Visual Studio eine *dockerfile-Datei* Datei zum Projekt.

> [!NOTE]
> Wenn Sie Docker Compose-Unterstützung während der projekterstellung für ein .NET Framework Web-app-Projekt (kein .NET Core Web-app-Projekt) aktivieren, wie in Abbildung 4-28 dargestellt, wird die Orchestrierung von containerunterstützung ebenfalls hinzugefügt.
>
> ![Aktivieren von Docker compose-Unterstützung für ein .NET Framework-Web-app-Projekt](media/enable-docker-compose-support.png)

> Abbildung 4-28: Aktivieren der Unterstützung für Docker Compose auf eine .NET Framework-Web-app-Projekt in Visual Studio 2017

### <a name="add-container-orchestration-support"></a>Hinzufügen von Unterstützung für die Orchestrierung von Containern

Wenn Sie eine Lösung mit mehreren Containern erstellen möchten, fügen Sie Unterstützung für die Orchestrierung von Containern zu Ihren Projekten hinzu. Dadurch können Sie die ausführen und Debuggen eine Gruppe von Containern (eine gesamte Projektmappe) zur gleichen Zeit, wenn sie in der gleichen definiert *"Docker-Compose.yml"* Datei.

Zum Hinzufügen von Unterstützung für die Orchestrierung von Containern mit der Maustaste, klicken Sie auf den Knoten Projektmappe oder das Projekt im **Projektmappen-Explorer**, und wählen Sie **hinzufügen** > **Container Orchestrierung unterstützt**. Wählen Sie dann **Docker Compose** oder **Service Fabric** um den Container zu verwalten.

Nachdem Sie die Orchestrierung von containerunterstützung zu Ihrem Projekt hinzufügen, werden Sie sehen eine dockerfile-Datei dem Projekt hinzugefügt und ein **Docker-compose-** hinzugefügt, um die Projektmappe im Ordner **Projektmappen-Explorer**, wie in Abbildung 4-29 dargestellt:

![Docker-Dateien im Projektmappen-Explorer in Visual Studio](media/docker-support-solution-explorer.png)

Abbildung 4-29: Docker-Dateien im Projektmappen-Explorer in Visual Studio 2017

Wenn *"Docker-Compose.yml"* bereits vorhanden ist, Visual Studio fügt nur die erforderlichen Zeilen Konfigurationscode hinzu.

## <a name="configure-docker-tools"></a>Konfigurieren von Docker-tools

Wählen Sie im Hauptmenü **Tools** > **Optionen**, und erweitern Sie **Containertools** > **Einstellungen**. Die Einstellungen der Container-Tools angezeigt werden.

![](./media/visual-studio-docker-tools-options.png)

Abbildung 4-30: Optionen für Docker-Tools

In der folgende Tabelle können Sie entscheiden, wie Sie diese Optionen festlegen können.

| name | Standardeinstellung | Gilt für | Beschreibung |
| -----|:---------------:|:----------:| ----------- |
| Ziehen Sie erforderlichen Docker-Images automatisch beim Laden von Projekten | Ein | Docker Compose | Zur Steigerung der Leistung beim Laden von Projekten wird Visual Studio einen Docker Pull-Vorgang im Hintergrund starten, damit das Bild, wenn Sie bereit zum Ausführen des Codes sind, bereits heruntergeladen wurde oder gerade heruntergeladen werden. Wenn Sie nur Projekte laden und Durchsuchen von Code, können Sie diese deaktivieren, um zu vermeiden, Herunterladen von containerimages, die Sie nicht benötigen. |
| Container im Hintergrund automatisch starten | Ein | Docker Compose | Erneut zur Steigerung der Leistung Visual Studio erstellt einen Container mit volumebereitstellungen bereit für die beim Erstellen und Ausführen Ihrer Container. Wenn Sie möchten steuern, wenn Ihr Container erstellt wird, deaktivieren Sie diese Option aus. |
| Kill Lösung Container schließen automatisch | Ein | Docker Compose | Deaktivieren Sie diese Option, wenn Sie Container für Ihre Lösung, um anzugeben, dass nach dem Schließen der Projektmappe oder das Schließen von Visual Studio ausführen möchten. |
| Fordert nicht zur vertrauenden Localhost-SSL-Zertifikat | Aus | ASP.NET Core 2.1-Projekten | Wenn die Localhost-SSL-Zertifikat nicht vertrauenswürdig ist, wird ein Visual Studio aufgefordert, jedes Mal, wenn Sie das Projekt auszuführen, wenn dieses Kontrollkästchen aktiviert ist. |

> [!WARNING]
> Wenn die Localhost-SSL-Zertifikat nicht vertrauenswürdig ist, und Sie das Kontrollkästchen zum Unterdrücken der eingabeaufforderungen, können der HTTPS-webanforderungen zur Laufzeit in Ihrer app oder Ihres Diensts fehlschlagen. In diesem Fall deaktivieren Sie die **keine Aufforderung** aktiviert, führen Sie das Projekt, und vertrauen an der Eingabeaufforderung angeben.

**Weitere Informationen:** finden Sie weitere Informationen zu den Dienste-Implementierung und Verwendung von Visual Studio-Tools für Docker, in den folgenden Artikeln:

Erstellen, Debuggen, aktualisieren und Aktualisieren von apps in einem lokalen Docker-Container: [https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh/](https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh)

Bereitstellen eines ASP.NET Core-Docker-Containers in einer containerregistrierung an: [https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker/](https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker)

>[!div class="step-by-step"]
>[Zurück](docker-apps-inner-loop-workflow.md)
>[Weiter](set-up-windows-containers-with-powershell.md)