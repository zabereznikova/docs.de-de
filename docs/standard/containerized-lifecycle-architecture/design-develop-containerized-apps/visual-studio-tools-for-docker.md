---
title: Visual Studio-Tools für Docker unter Windows
description: Lernen Sie kennen die Docker-Tools in Visual Studio 2017 Version 15.7 und höher verfügbar.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/15/2019
ms.custom: vs-dotnet
ms.openlocfilehash: 431a0f34ba913c18c35e28ca45660495403bf688
ms.sourcegitcommit: 69bf8b719d4c289eec7b45336d0b933dd7927841
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57844248"
---
# <a name="use-docker-tools-in-visual-studio-2017-on-windows"></a>Verwenden von Docker-Tools in Visual Studio 2017 unter Windows

Der Developer-Workflow bei Verwendung der Docker-Tools in Visual Studio 2017 Version 15.7 und höher, enthalten ist vergleichbar mit der Verwendung von Visual Studio Code und Docker-CLI (in der Tat es basiert auf der gleichen Docker-CLI), aber es ist einfacher, für den Einstieg, vereinfacht den Prozess, und bietet höhere Produktivität für den Build, ausführen und Tasks erstellen. Es auch ausführen und Debuggen Sie Ihre Container über den üblichen `F5` und `Ctrl+F5` Schlüssel aus Visual Studio. Können Sie auch Debuggen eine gesamte Projektmappe seine Container definiert sind, in der gleichen `docker-compose.yml` Datei auf Projektmappenebene.

## <a name="configure-your-local-environment"></a>Konfigurieren der lokalen Umgebung

Mit den neuesten Versionen von Docker für Windows ist es einfacher, entwickeln jemals auf Docker-Anwendungen, da das Setup einfach ist, wie in den folgenden Referenzen beschrieben.

> [!TIP]
> Wechseln Sie zu, um weitere Informationen zum Installieren von Docker für Windows (<https://docs.docker.com/docker-for-windows/>).

## <a name="docker-support-in-visual-studio-2017"></a>Docker-Unterstützung in Visual Studio 2017

Es gibt zwei Ebenen der Docker-Unterstützung, die Sie einem Projekt hinzufügen können. Sie können einfach hinzufügen, in ASP.NET Core-Projekten eine `Dockerfile` Datei in das Projekt durch Aktivieren der Docker-Unterstützung. Die nächste Ebene ist die Orchestrierung die containerunterstützung, das hinzufügt eine `Dockerfile` auf das Projekt (sofern nicht bereits vorhanden) und ein `docker-compose.yml` Datei auf Projektmappenebene. Orchestrierung von containerunterstützung über Docker Compose, wird standardmäßig in Visual Studio 2017, Versionen 15.0, 15.7 hinzugefügt. Orchestrierung von containerunterstützung ist ein optionales Feature in Visual Studio 2017, Versionen 15,8 oder höher. Version 15.8 ein später Docker Compose und Service Fabric zu unterstützen.

Die **hinzufügen > Docker-Unterstützung** und **hinzufügen > Unterstützung für Containerorchestrator** Befehle befinden sich auf der rechten Maustaste (oder im Kontextmenü) des Projektknotens für ein ASP.NET Core-Projekt im  **Projektmappen-Explorer**, wie in Abbildung 4-31 gezeigt:

![Menüoption für Docker-Unterstützung in Visual Studio hinzufügen](./media/add-docker-support-menu.png)

**Abbildung 4-31**. Hinzufügen von Docker-Unterstützung zu einem Visual Studio 2017-Projekt

### <a name="add-docker-support"></a>Docker-Unterstützung hinzufügen

Sie können Docker-Unterstützung zu einem vorhandenen ASP.NET Core-Projekt hinzufügen, indem Sie die Auswahl **hinzufügen** > **Docker-Unterstützung** in **Projektmappen-Explorer**. Sie können auch Docker-Unterstützung während der projekterstellung aktivieren, indem Sie auswählen **Aktivieren der Unterstützung für Docker** in die **neue ASP.NET Core-Webanwendung** geöffnet, nachdem Sie auf **OK** in die **neues Projekt** Dialogfeld wie in Abbildung 4 – 32 gezeigt.

![Aktivieren von Docker-Unterstützung für neue ASP.NET Core-Web-app in Visual Studio](./media/enable-docker-support-visual-studio.png)

**Abbildung 4-32**. Aktivieren Sie Docker-Unterstützung, während der projekterstellung in Visual Studio 2017

Wenn Sie hinzufügen oder Docker-Unterstützung aktivieren, fügt Visual Studio eine *dockerfile-Datei* Datei zum Projekt.

> [!NOTE]
> Wenn Sie Docker Compose-Unterstützung während der projekterstellung für ein ASP.NET-Projekt (.NET Framework, nicht in einem .NET Core-Projekt) aktivieren, wie in Abbildung 4-33 gezeigt, wird die Orchestrierung von containerunterstützung ebenfalls hinzugefügt.

![Aktivieren von Docker compose-Unterstützung für ein ASP.NET-Projekt](media/enable-docker-compose-support.png)

**Abbildung 4-33**. Aktivieren der Unterstützung für ein ASP.NET-Projekt in Visual Studio 2017 für Docker Compose

### <a name="add-container-orchestration-support"></a>Hinzufügen von Unterstützung für die Orchestrierung von Containern

Wenn Sie eine Lösung mit mehreren Containern erstellen möchten, fügen Sie Unterstützung für die Orchestrierung von Containern zu Ihren Projekten hinzu. Dadurch können Sie die ausführen und Debuggen eine Gruppe von Containern (eine gesamte Projektmappe) zur gleichen Zeit, wenn sie in der gleichen definiert *"Docker-Compose.yml"* Datei.

Zum Hinzufügen von Unterstützung für die Orchestrierung von Containern mit der Maustaste, klicken Sie auf den Knoten Projektmappe oder das Projekt im **Projektmappen-Explorer**, und wählen Sie **hinzufügen > Container Orchestrierung unterstützt**. Wählen Sie dann **Docker Compose** oder **Service Fabric** um den Container zu verwalten.

Nachdem Sie die Orchestrierung von containerunterstützung zu Ihrem Projekt hinzufügen, werden Sie sehen eine dockerfile-Datei dem Projekt hinzugefügt und ein **Docker-compose-** hinzugefügt, um die Projektmappe im Ordner **Projektmappen-Explorer**, wie in Abbildung 4-34 gezeigt:

![Docker-Dateien im Projektmappen-Explorer in Visual Studio](media/docker-support-solution-explorer.png)

**Abbildung 4-34**. Docker-Dateien im Projektmappen-Explorer in Visual Studio 2017

Wenn *"Docker-Compose.yml"* bereits vorhanden ist, Visual Studio fügt nur die erforderlichen Zeilen Konfigurationscode hinzu.

## <a name="configure-docker-tools"></a>Konfigurieren von Docker-tools

Wählen Sie im Hauptmenü **Tools > Optionen**, und erweitern Sie **Container Tools > Einstellungen**. Die Einstellungen der Container-Tools angezeigt werden.

![Visual Studio-Docker-tools-Optionen angezeigt: Automatisch die erforderliche Docker-Images beim Laden von Projekten abrufen, Container im Hintergrund automatisch starten, schließen Lösung Container automatisch zu beenden und nicht vertrauenswürdige SSL-Zertifikat aufgefordert.](./media/visual-studio-docker-tools-options.png)

**Abbildung 4: 35**. Optionen für Docker-Tools

In der folgende Tabelle können Sie entscheiden, wie Sie diese Optionen festlegen können.

| name | Standardeinstellung | Gilt für | Beschreibung |
| -----|:---------------:|:----------:| ----------- |
| Ziehen Sie erforderlichen Docker-Images automatisch beim Laden von Projekten | Ein | Docker Compose | Zur Steigerung der Leistung beim Laden von Projekten von startet Visual Studio einen Docker Pull-Vorgang im Hintergrund, damit das Bild, wenn Sie bereit zum Ausführen des Codes sind, bereits heruntergeladen wurde oder gerade heruntergeladen. Wenn Sie nur Projekte laden und Durchsuchen von Code, können Sie diese deaktivieren, um zu vermeiden, Herunterladen von containerimages, die Sie nicht benötigen. |
| Container im Hintergrund automatisch starten | Ein | Docker Compose | Erneut zur Steigerung der Leistung Visual Studio erstellt einen Container mit volumebereitstellungen bereit für die beim Erstellen und Ausführen Ihrer Container. Wenn Sie möchten steuern, wenn Ihr Container erstellt wird, deaktivieren Sie diese Option aus. |
| Kill Lösung Container schließen automatisch | Ein | Docker Compose | Deaktivieren Sie diese Option, wenn Sie Container für Ihre Lösung, um anzugeben, dass nach dem Schließen der Projektmappe oder das Schließen von Visual Studio ausführen möchten. |
| Fordert nicht zur vertrauenden Localhost-SSL-Zertifikat | Aus | ASP.NET Core 2.1-Projekten | Wenn die Localhost-SSL-Zertifikat nicht vertrauenswürdig ist, wird ein Visual Studio aufgefordert, jedes Mal, wenn Sie das Projekt auszuführen, wenn dieses Kontrollkästchen aktiviert ist. |

> [!WARNING]
> Wenn die Localhost-SSL-Zertifikat nicht vertrauenswürdig ist, und Sie das Kontrollkästchen zum Unterdrücken der eingabeaufforderungen, können der HTTPS-webanforderungen zur Laufzeit in Ihrer app oder Ihres Diensts fehlschlagen. In diesem Fall deaktivieren Sie die **keine Aufforderung** aktiviert, führen Sie das Projekt, und vertrauen an der Eingabeaufforderung angeben.

> [!TIP]
> Weitere Informationen zu den Dienste-Implementierung und Verwendung von Visual Studio-Tools für Docker lesen Sie die folgenden Artikeln:
>
>Debuggen von apps in einem lokalen Docker-Container: <https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh>
>
>Bereitstellen eines ASP.NET-Containers an eine containerregistrierung mithilfe von Visual Studio: <https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker>

>[!div class="step-by-step"]
>[Zurück](docker-apps-inner-loop-workflow.md)
>[Weiter](set-up-windows-containers-with-powershell.md)
