---
title: Visual Studio-Tools für Docker unter Windows
description: Lernen Sie die in Visual Studio 2017, Version 15.7 und höher, verfügbaren Docker-Tools kennen.
ms.date: 08/06/2020
ms.custom: vs-dotnet
ms.openlocfilehash: ae20ebf7c3c27d7f2ebe51c33719b82048f86241
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032189"
---
# <a name="use-docker-tools-in-visual-studio-on-windows"></a>Verwenden von Docker-Tools in Visual Studio unter Windows

Der Entwicklerworkflow beim Verwenden der in Visual Studio 2017, Version 15.7 und höher, enthaltenen Docker-Tools ist ähnlich wie bei Visual Studio Code und Docker CLI (er basiert tatsächlich auf der gleichen Docker-CLI), der Einstieg ist jedoch leichter, der Prozess ist vereinfacht, und es steht bessere Produktivität für die Erstellungs-, Ausführungs- und Zusammenstellungsaufgaben zur Verfügung. Er ermöglicht außerdem das Ausführen und Debuggen Ihrer Container mithilfe der gewohnten Tasten `F5` und `Ctrl+F5` aus Visual Studio. Sie können sogar eine komplette Projektmappe debuggen, wenn ihre Container in der gleichen `docker-compose.yml`-Datei auf Projektmappenebene definiert sind.

## <a name="configure-your-local-environment"></a>Konfigurieren Ihrer lokalen Umgebung

Mit den neuesten Versionen von Docker für Windows ist es einfacher denn je, Docker-Anwendungen zu entwickeln, da die Einrichtung geradlinig ist, wie in den folgenden Referenzen erläutert wird.

> [!TIP]
> Weitere Informationen zum Installieren von Docker für Windows finden Sie unter (<https://docs.docker.com/docker-for-windows/>).

## <a name="docker-support-in-visual-studio"></a>Docker-Unterstützung in Visual Studio

Es gibt zwei Ebenen von Docker-Unterstützung, die Sie einem Projekt hinzufügen können. In ASP.NET Core-Projekten können Sie dem Projekt einfach eine `Dockerfile`-Datei hinzufügen, indem Sie Docker-Unterstützung aktivieren. Die nächste Ebene ist die Orchestrierungsunterstützung für Container, die dem Projekt ein `Dockerfile` (wenn dort noch keins vorhanden ist) und eine `docker-compose.yml`-Datei auf Projektmappenebene hinzufügt. Orchstrierungsunterstützung für Container mithilfe von Docker Compose wird in Visual Studio 2017, Versionen 15.0 bis 15.7, standardmäßig hinzugefügt. Orchestrierungsunterstützung für Container ist eine optionale Funktion in Visual Studio 2017, Version 15.8 oder höher. Visual Studio 2019 oder höher unterstützt auch **Kubernetes-/Helm-** -Bereitstellungen.

Die Befehle **Hinzufügen > Docker-Unterstützung** und **Hinzufügen > Unterstützung für Containerorchestrator** befinden sich im **Projektmappen-Explorer** im Kontextmenü des Projektknotens für ein ASP.NET Core-Projekt wie in Abbildung 4–31 gezeigt:

![Menüoption „Hinzufügen > Docker-Unterstützung“ in Visual Studio](media/add-docker-support-menu.png)

**Abbildung 4-31**. Hinzufügen von Docker-Unterstützung zu einem Visual Studio 2019-Projekt

### <a name="add-docker-support"></a>Hinzufügen der Docker-Unterstützung

Neben der Option zum Hinzufügen der Docker-Unterstützung zu einer vorhandenen Anwendung, wie im vorigen Abschnitt gezeigt, können Sie die Docker-Unterstützung während der Projekterstellung aktivieren, indem Sie im Dialogfeld **Neue ASP.NET Core-Webanwendung**, das geöffnet wird, nachdem Sie im Dialogfeld **Neues Projekt** auf **OK** klicken, **Docker-Unterstützung aktivieren** auswählen, wie in Abbildung 4-32 gezeigt.

![Aktivieren der Docker-Unterstützung für neue ASP.NET Core-Web-App in Visual Studio](media/enable-docker-support-visual-studio.png)

**Abbildung 4-32**. Aktivieren von Docker-Unterstützung während der Projekterstellung in Visual Studio 2019

Wenn Sie Docker-Unterstützung hinzufügen oder aktivieren, fügt Visual Studio dem Projekt eine _Dockerfile_-Datei hinzu, die Verweise auf alle erforderlichen Projekte aus der Projektmappe enthält.

### <a name="add-container-orchestration-support"></a>Hinzufügen von Orchestrierungsunterstützung für Container

Wenn Sie eine Projektmappe mit mehreren Containern erstellen möchten, fügen Sie Ihren Projekten die Unterstützung der Containerorchestrierung hinzu. Dadurch können Sie eine Gruppe von Containern (eine gesamte Projektmappe) gleichzeitig ausführen und debuggen, wenn diese in derselben _docker-compose.yml_-Datei definiert sind.

Um die Unterstützung der Containerorchestrierung hinzuzufügen, klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf die Projektmappe oder den Projektknoten, und wählen Sie **Hinzufügen > Unterstützung für Containerorchestrator** aus. Wählen Sie dann **Kubernetes/Helm** oder **Docker Compose** aus, um die Container zu verwalten.

Nachdem Sie Ihrem Projekt Orchestrierungsunterstützung für Container hinzugefügt haben, sehen Sie im **Projektmappen-Explorer**, dass Ihrem Projekt ein Dockerfile und der Projektmappe ein Ordner **docker-compose** hinzugefügt wurden, wie in Abbildung 4-33 gezeigt:

![Docker-Dateien im Projektmappen-Explorer in Visual Studio](media/docker-support-solution-explorer.png)

**Abbildung 4-33**. Docker-Dateien im Projektmappen-Explorer in Visual Studio 2019

Wenn _docker-compose.yml_ bereits vorhanden ist, fügt Visual Studio nur die erforderlichen Zeilen zum Konfigurationscode hinzu.

## <a name="configure-docker-tools"></a>Konfigurieren von Docker-Tools

Wählen Sie im Hauptmenü **Extras > Optionen** aus, und klappen Sie **Containertools > Einstellungen** auf. Die Einstellungen der Containertools werden angezeigt.

![Optionen für Visual Studio Docker-Tools, die drei Seiten anzeigen: „Allgemein“, „Einzelnes Projekt“ und „Docker Compose“. Details dazu finden Sie im Artikeltext.](media/visual-studio-docker-tools-options.png)

**Abbildung 4–34**. Optionen für Docker-Tools

Die folgende Tabelle hilft Ihnen möglicherweise beim Festlegen dieser Optionen.

| Seite/Einstellung                                |  Standardeinstellung   | BESCHREIBUNG                                                                                                                                                                                                                                                                                                                                                                                                           |
| ------------------------------------------- | :----------------: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Seite „Allgemein“**                            |
| Installieren Sie bei Bedarf Docker für Windows            |     Aufforderung      |
| Starten Sie bei Bedarf Docker Desktop.              |     Aufforderung      |
| ASP.NET Core-SSL-Zertifikat als vertrauenswürdig einstufen          |     Aufforderung      | Wenn das localhost-SSL-Zertifikat nicht als vertrauenswürdig markiert wurde (mit `dotnet dev-certs https --trust`), zeigt Visual Studio jedes Mal, wenn Sie Ihr Projekt ausführen, eine Eingabeaufforderung an.                                                                                                                                                                                                                                                    |
| **Seite „Einzelnes Projekt“**                     |
| Erforderliche Docker-Images beim Öffnen des Projekts mithilfe von Pull übertragen |        True        | Zum Steigern der Leistung beim Ausführen von Projekten beginnt Visual Studio einen Docker-Pull-Vorgang im Hintergrund, sodass das Image bereits heruntergeladen ist oder heruntergeladen wird, wenn Sie zur Ausführung Ihres Codes bereit sind. Wenn Sie lediglich Projekte laden und Code durchsuchen, können Sie dies ausschalten, um das Herunterladen von Containerimages zu vermeiden, die Sie nicht benötigen. Dies kann die Benutzerfreundlichkeit beim Öffnen von Projekten verlangsamen. |
| Aktualisierte Docker-Images beim Laden des Projekts pullen  | .NET Core-Projekte | Pullen Sie Updates für vorhandene Images, um beim Öffnen des Projekts die neuesten Updates zu verwenden. Dies kann die Benutzerfreundlichkeit beim Öffnen von Projekten verlangsamen.                                                                                                                                                                                                                                                                                          |
| Entfernen von Containern beim Schließen des Projekts          |        True        | Bereinigung beim Schließen des Projekts. Dies kann die Benutzerfreundlichkeit beim Schließen von Projekten verlangsamen, ist aber in der Regel trotzdem schnell.                                                                                                                                                                                                                                                                                                            |
| Container beim Öffnen des Projekts ausführen              |        True        | Um bei der Ausführung des Projekts eine bessere Leistung zu erzielen, startet Visual Studio alle Container in der Projektmappe. Dies kann die Benutzerfreundlichkeit beim Öffnen von Projekten verlangsamen.                                                                                                                                                                                                                                                        |
| **Docker Compose**                          |                    | Die Seite „Docker Compose“ enthält die gleichen Einstellungen wie die Seite „Einzelnes Projekt“, diese gelten aber für Lösungen mit mehreren Containern.                                                                                                                                                                                                                                                                                           |

> [!WARNING]
> Wenn das localhost-SSL-Zertifikat nicht vertrauenswürdig ist und Sie die Option auf **Nie** festlegen, treten in Ihrer App oder Ihrem Dienst bei HTTPS-Webanforderungen zur Laufzeit möglicherweise Fehler auf. Legen Sie in diesem Fall den Wert erneut auf **Aufforderung** fest, oder (besser noch) vertrauen Sie den Zertifikaten auf Ihrem Entwicklungscomputer, indem Sie den Befehl `dotnet dev-certs https --trust` verwenden.

> [!TIP]
> Weitere Informationen zur Implementierung der Dienste und Verwendung von Visual Studio-Tools für Docker finden Sie in den folgenden Artikeln:
>
> Debuggen von Apps in einem lokalen Docker-Container: <https://docs.microsoft.com/visualstudio/containers/edit-and-refresh>
>
> Bereitstellen eines ASP.NET-Containers in einer Containerregistrierung mithilfe von Visual Studio: <https://docs.microsoft.com/visualstudio/containers/hosting-web-apps-in-docker>

> [!div class="step-by-step"]
> [Zurück](docker-apps-inner-loop-workflow.md)
> [Weiter](set-up-windows-containers-with-powershell.md)
