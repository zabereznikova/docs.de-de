---
title: Visual Studio-Tools für Docker unter Windows
description: Lernen Sie die in Visual Studio 2017, Version 15.7 und höher, verfügbaren Docker-Tools kennen.
ms.date: 02/15/2019
ms.custom: vs-dotnet
ms.openlocfilehash: 2b6fdc33f9cf850cf9e52fca4a1a9754cd412567
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "68673877"
---
# <a name="use-docker-tools-in-visual-studio-2017-on-windows"></a>Verwenden von Docker-Tools in Visual Studio 2017 unter Windows

Der Entwicklerworkflow beim Verwenden der in Visual Studio 2017, Version 15.7 und höher, enthaltenen Docker-Tools ist ähnlich wie bei Visual Studio Code und Docker CLI (er basiert tatsächlich auf der gleichen Docker-CLI), der Einstieg ist jedoch leichter, der Prozess ist vereinfacht, und es steht bessere Produktivität für die Erstellungs-, Ausführungs- und Zusammenstellungsaufgaben zur Verfügung. Er ermöglicht außerdem das Ausführen und Debuggen Ihrer Container mithilfe der gewohnten Tasten `F5` und `Ctrl+F5` aus Visual Studio. Sie können sogar eine komplette Projektmappe debuggen, wenn ihre Container in der gleichen `docker-compose.yml`-Datei auf Projektmappenebene definiert sind.

## <a name="configure-your-local-environment"></a>Konfigurieren Ihrer lokalen Umgebung

Mit den neuesten Versionen von Docker für Windows ist es einfacher denn je, Docker-Anwendungen zu entwickeln, da die Einrichtung geradlinig ist, wie in den folgenden Referenzen erläutert wird.

> [!TIP]
> Weitere Informationen zum Installieren von Docker für Windows finden Sie unter (<https://docs.docker.com/docker-for-windows/>).

## <a name="docker-support-in-visual-studio-2017"></a>Docker-Unterstützung in Visual Studio 2017

Es gibt zwei Ebenen von Docker-Unterstützung, die Sie einem Projekt hinzufügen können. In ASP.NET Core-Projekten können Sie dem Projekt einfach eine `Dockerfile`-Datei hinzufügen, indem Sie Docker-Unterstützung aktivieren. Die nächste Ebene ist die Orchestrierungsunterstützung für Container, die dem Projekt ein `Dockerfile` (wenn dort noch keins vorhanden ist) und eine `docker-compose.yml`-Datei auf Projektmappenebene hinzufügt. Orchstrierungsunterstützung für Container mithilfe von Docker Compose wird in Visual Studio 2017, Versionen 15.0 bis 15.7, standardmäßig hinzugefügt. Orchestrierungsunterstützung für Container ist eine optionale Funktion in Visual Studio 2017, Version 15.8 oder höher. Version 15.8 und höher unterstützen Docker Compose und Service Fabric.

Die Befehle **Hinzufügen > Docker-Unterstützung** und **Hinzufügen > Unterstützung für Containerorchestrator** befinden sich im  **Projektmappen-Explorer** im Kontextmenü des Projektknotens für ein ASP.NET Core-Projekt wie in Abbildung 4–31 gezeigt:

![Menüoption „Hinzufügen > Docker-Unterstützung“ in Visual Studio](./media/add-docker-support-menu.png)

**Abbildung 4-31**. Hinzufügen von Docker-Unterstützung zu einem Visual Studio 2017-Projekt

### <a name="add-docker-support"></a>Hinzufügen von Docker-Unterstützung

Sie können die Docker-Unterstützung einem vorhandenen ASP.NET Core-Projekt hinzufügen, indem Sie im **Projektmappen-Explorer** die Option **Hinzufügen** > **Docker-Unterstützung** auswählen. Ferner können Sie die Docker-Unterstützung während der Projekterstellung aktivieren, indem Sie im Dialogfeld **Neue ASP.NET Core-Webanwendung**, das geöffnet wird, nachdem Sie im Dialogfeld **Neues Projekt** auf **OK** klicken, **Docker-Unterstützung aktivieren** auswählen, wie in Abbildung 4–32 gezeigt.

![Aktivieren der Docker-Unterstützung für neue ASP.NET Core-Web-App in Visual Studio](./media/enable-docker-support-visual-studio.png)

**Abbildung 4-32**. Aktivieren der Docker-Unterstützung während der Projekterstellung in Visual Studio 2017

Wenn Sie Docker-Unterstützung hinzufügen oder aktivieren, fügt Visual Studio dem Projekt eine *Dockerfile*-Datei hinzu.

> [!NOTE]
> Wenn Sie die Docker Compose-Unterstützung während der Projekterstellung für ein ASP.NET-Projekt (.NET Framework, kein .NET Core-Projekt) aktivieren, wie in Abbildung 4–33 gezeigt, wird auch die Unterstützung der Containerorchestrierung hinzugefügt.

![Aktivieren der Docker Compose-Unterstützung für ein ASP.NET-Projekt](media/enable-docker-compose-support.png)

**Abbildung 4-33**. Aktivieren der Docker Compose-Unterstützung für ein ASP.NET-Projekt in Visual Studio 2017

### <a name="add-container-orchestration-support"></a>Hinzufügen von Orchestrierungsunterstützung für Container

Wenn Sie eine Projektmappe mit mehreren Containern erstellen möchten, fügen Sie Ihren Projekten die Unterstützung der Containerorchestrierung hinzu. Dadurch können Sie eine Gruppe von Containern (eine gesamte Projektmappe) gleichzeitig ausführen und debuggen, wenn diese in derselben *docker-compose.yml*-Datei definiert sind.

Um die Unterstützung der Containerorchestrierung hinzuzufügen, klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf die Projektmappe oder den Projektknoten, und wählen Sie **Hinzufügen > Unterstützung für Containerorchestrator** aus. Wählen Sie anschließend **Docker Compose** oder **Service Fabric** aus, um die Container zu verwalten.

Nachdem Sie Ihrem Projekt Orchestrierungsunterstützung für Container hinzugefügt haben, sehen Sie im **Projektmappen-Explorer**, dass Ihrem Projekt ein Dockerfile und der Projektmappe ein Ordner **docker-compose** hinzugefügt wurden, wie in Abbildung 4–34 dargestellt:

![Docker-Dateien im Projektmappen-Explorer in Visual Studio](media/docker-support-solution-explorer.png)

**Abbildung 4–34**. Docker-Dateien im Projektmappen-Explorer in Visual Studio 2017

Wenn *docker-compose.yml* bereits vorhanden ist, fügt Visual Studio nur die erforderlichen Zeilen zum Konfigurationscode hinzu.

## <a name="configure-docker-tools"></a>Konfigurieren von Docker-Tools

Wählen Sie im Hauptmenü **Extras > Optionen** aus, und klappen Sie **Containertools > Einstellungen** auf. Die Einstellungen der Containertools werden angezeigt.

![Optionen für Visual Studio Docker-Tools mit diesen Elementen: „Erforderliche Docker-Images beim Laden des Projekts automatisch abrufen“, „Container im Hintergrund automatisch starten“, „Beim Schließen der Lösung Container automatisch beenden“ und „Nicht nach Vertrauenswürdigkeit von SSL-Zertifikaten fragen“.](./media/visual-studio-docker-tools-options.png)

**Abbildung 4–35**. Optionen für Docker-Tools

Die folgende Tabelle hilft Ihnen möglicherweise beim Festlegen dieser Optionen.

| name | Standardeinstellung | Gilt für | Beschreibung |
| -----|:---------------:|:----------:| ----------- |
| Erforderliche Docker-Images beim Laden des Projekts automatisch abrufen | Ein | Docker Compose | Zum Steigern der Leistung beim Laden von Projekten beginnt Visual Studio einen Docker-Pull-Vorgang im Hintergrund, sodass das Image bereits heruntergeladen ist oder heruntergeladen wird, wenn Sie zur Ausführung Ihres Codes bereit sind. Wenn Sie lediglich Projekte laden und Code durchsuchen, können Sie dies ausschalten, um das Herunterladen von Containerimages zu vermeiden, die Sie nicht benötigen. |
| Container im Hintergrund automatisch starten | Ein | Docker Compose | Ebenfalls zum Steigern der Leistung erstellt Visual Studio einen Container mit Volumeeinbindungen, die bereit stehen, wenn Sie Ihren Container erstellen und ausführen. Wenn Sie steuern möchten, wann Ihr Container erstellt wird, deaktivieren Sie diese Option. |
| Beim Schließen der Lösung Container automatisch beenden | Ein | Docker Compose | Deaktivieren Sie diese Option, wenn Container für Ihre Projektmappe nach dem Schließen von Projektmappe oder Visual Studio weiter ausgeführt werden sollen. |
| Nicht nach Vertrauenswürdigkeit des localhost-SSL-Zertifikats fragen | Aus | ASP.NET Core 2.2-Projekte | Wenn das localhost-SSL-Zertifikat nicht vertrauenswürdig ist, benachrichtigt Visual Studio Sie bei jeder Ausführung Ihres Projekts, sofern dieses Kontrollkästchen nicht aktiviert ist. |

> [!WARNING]
> Wenn das localhost-SSL-Zertifikat nicht vertrauenswürdig ist und Sie das Kontrollkästchen aktivieren, um die Benachrichtigung zu unterdrücken, treten in Ihrer App oder Ihrem Dienst bei HTTPS-Webanforderungen zur Laufzeit möglicherweise Fehler auf. Deaktivieren Sie in diesem Fall das **Nicht fragen**-Kontrollkästchen, führen Sie Ihr Projekt aus, und drücken Sie bei der Aufforderung Ihr Vertrauen aus.

> [!TIP]
> Weitere Informationen zur Implementierung der Dienste und Verwendung von Visual Studio-Tools für Docker finden Sie in den folgenden Artikeln:
>
>Debuggen von Apps in einem lokalen Docker-Container: <https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh>
>
>Bereitstellen eines ASP.NET-Containers in einer Containerregistrierung mithilfe von Visual Studio: <https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker>

>[!div class="step-by-step"]
>[Zurück](docker-apps-inner-loop-workflow.md)
>[Weiter](set-up-windows-containers-with-powershell.md)
