---
title: Verwenden von Visual Studio-Tools für Docker (Visual Studio unter Windows)
description: Lebenszyklus von Docker-Containeranwendungen mit der Microsoft-Plattform und Tools
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/12/2018
ms.custom: vs-dotnet
ms.openlocfilehash: af14c92ab27885deec878dc33e7b94035f43e65b
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2018
ms.locfileid: "46581219"
---
# <a name="using-visual-studio-tools-for-docker-visual-studio-on-windows"></a>Verwenden von Visual Studio-Tools für Docker (Visual Studio unter Windows)

Der Entwicklungsworkflow bei Verwendung von Visual Studio-Tools für Docker ähnelt der Workflow bei Verwendung von Visual Studio Code und Docker-CLI. In der Tat basiert auf der gleichen Docker-CLI, jedoch ist einfacher, um zu beginnen, bietet höhere Produktivität und vereinfacht den Prozess für den Build, ausführen und Tasks erstellen. Es kann auch zum Ausführen und Debuggen Ihre Container per simple Aktionen wie z. B. F5 und STRG + F5 in Visual Studio. Mit der Unterstützung der Optionaler Container-Orchestrierung, sondern auch zum Ausführen und Debuggen von einem einzelnen Container können Sie ausführen und Debuggen eine Gruppe von Containern (eine gesamte Projektmappe) zur gleichen Zeit. Definieren Sie einfach die Container in der gleichen *"Docker-Compose.yml"* Datei auf Projektmappenebene.

## <a name="configuring-your-local-environment"></a>Zum Konfigurieren Ihrer lokalen Umgebung

Docker-Unterstützung ist in Visual Studio 2017 mit der .NET- und .NET Core-Workloads, die installiert enthalten. Installieren Sie Docker für Windows separat an.

Mit den neuesten Versionen von Docker für Windows ist es einfacher, entwickeln jemals auf Docker-Anwendungen, da das Setup einfach ist, wie in den folgenden Referenzen beschrieben.

**Weitere Informationen:** wechseln Sie zu, um weitere Informationen zum Installieren von Docker für Windows <https://docs.docker.com/docker-for-windows/>.

**Weitere Informationen:** finden Sie Anweisungen zum Installieren von Visual Studio [ https://visualstudio.microsoft.com/downloads/ ](https://visualstudio.microsoft.com/downloads/).

Um weitere Informationen zum Installieren von Visual Studio-Tools für Docker anzuzeigen, wechseln Sie zu <http://aka.ms/vstoolsfordocker> und <https://docs.microsoft.com/aspnet/core/host-and-deploy/docker/visual-studio-tools-for-docker>.

## <a name="using-docker-tools-in-visual-studio-2017"></a>Verwenden von Docker-Tools in Visual Studio 2017

Wenn Sie Docker-Unterstützung zu einem Projekt hinzufügen (siehe Abbildung 4-26), fügt Visual Studio eine *dockerfile-Datei* auf das Stammverzeichnis des Projekts.

![Aktivieren der Unterstützung von Docker-Lösung in einem Visual Studio 2017-Projekt](./media/image32.png)

Abbildung 4-26: Aktivieren der Unterstützung von Docker-Lösung in einem Visual Studio 2017-Projekt

 Orchestrierung von containerunterstützung über Docker Compose, wird standardmäßig in Visual Studio 2017, Version 15.7 oder früher hinzugefügt. Orchestrierung von containerunterstützung ist ein optionales Feature in Visual Studio 2017, Versionen 15.8 oder später in diesem Fall Docker Compose und Service Fabric werden unterstützt.

Mit Visual Studio Version 15,8 und höher können Sie Unterstützung für mehrere Projekte in einer Projektmappe hinzufügen, von denen jeder Container zugeordneten. Mit der rechten Maustaste auf den Knoten Projektmappe oder das Projekt im **Projektmappen-Explorer**, und wählen Sie **hinzufügen** > **Orchestrierung von Containerunterstützung**.  Wählen Sie dann **Docker Compose** oder **Service Fabric** um den Container zu verwalten.

Bei der Auswahl **Docker Compose**, fügt Visual Studio einen Abschnitt "Dienst" in der Projektmappe *"Docker-Compose.yml"* -Dateien (oder die Dateien erstellt, sofern nicht vorhanden). Es ist eine einfache Möglichkeit zum Erstellen Ihrer Lösung mit mehreren Containern zu beginnen. Anschließend können Sie öffnen die *"Docker-Compose.yml"* -Dateien und mit zusätzlichen Features aktualisieren.

Diese Aktion fügt die erforderliche Konfiguration Codezeilen auf einer *"Docker-Compose.yml"* auf Projektmappenebene festzulegen.

Sie können auch Docker-Unterstützung aktivieren beim Erstellen eines ASP.NET Core-Projekts in Visual Studio 2017, wie in Abbildung 4-27 dargestellt.

![Aktivieren von Docker-Unterstützung beim Erstellen eines Projekts](./media/image33.png)

Abbildung 4-27: Aktivieren von Docker-Unterstützung beim Erstellen eines Projekts

Nachdem Sie die Projektmappe in Visual Studio Docker-Unterstützung hinzugefügt, außerdem sehen Sie eine neue Knotenstruktur in **Projektmappen-Explorer** mit der hinzugefügten *"Docker-Compose.yml"* -Dateien, wie in Abbildung 4-28 dargestellt.

![Docker-compose.yml-Dateien werden jetzt im Projektmappen-Explorer](./media/image34.PNG)

Abbildung 4-28: Docker-compose.yml-Dateien zeigen jetzt **Projektmappen-Explorer**

Sie können eine app mit mehreren Containern bereitstellen, indem Sie mit einem einzigen *"Docker-Compose.yml"* Datei beim Ausführen von `docker-compose up`jedoch Visual Studio fügt eine Gruppe von Dateien, um die Werte abhängig von der Umgebung (Entwicklung im Vergleich zu überschreiben für die Produktion) und die Ausführung der (Release im Vergleich zu Debug) eingeben. Diese Funktion wird in späteren Kapiteln besser erläutert.

Sie können auch Service Fabric anstelle von Docker Compose verwenden, um mehrere Container zu verwalten. Finden Sie unter [Tutorial: Bereitstellen eine .NET-Anwendung in einem Windows-Container in Azure Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-host-app-in-a-container).

**Weitere Informationen:** finden Sie weitere Informationen zu den Dienste-Implementierung und Verwendung von Visual Studio-Tools für Docker, in den folgenden Artikeln:

Erstellen, Debuggen, aktualisieren und Aktualisieren von apps in einem lokalen Docker-Container: [https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh/](https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh)

Bereitstellen eines ASP.NET Core-Docker-Containers in einer containerregistrierung an: [https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker/](https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker)

>[!div class="step-by-step"]
[Zurück](docker-apps-inner-loop-workflow.md)
[Weiter](set-up-windows-containers-with-powershell.md)
