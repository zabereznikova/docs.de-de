---
title: "Mithilfe von Visual Studio-Tools für Docker (Visual Studio unter Windows)"
description: Lebenszyklus von Datenvolumes Docker-Anwendung mit Microsoft-Webplattform und Tools
keywords: Docker, Microservices, ASP.NET, Container
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: d7a24633f5857bc5b72ebab42020627c645f4302
ms.sourcegitcommit: 6f49c973f62855ffd6c4a322903e7dd50c5c1b50
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2017
---
# <a name="using-visual-studio-tools-for-docker-visual-studio-on-windows"></a>Mithilfe von Visual Studio-Tools für Docker (Visual Studio unter Windows)

Der Workflow Entwickler bei Verwendung von Visual Studio-Tools für Docker ähnlich wie der Workflow wird bei Verwendung von Visual Studio-Code und Docker-Befehlszeilenschnittstelle (in der Tat basiert auf der gleichen Docker-Befehlszeilenschnittstelle), aber es ist einfacher, um zu beginnen, vereinfacht den Prozess und höhere Steigerung der Produktivität für den Build ausführen und Aufgaben zusammenstellen. Es kann auch zum Ausführen und Debuggen der Container über einfache Aktionen wie z. B. F5 bzw. STRG + F5 in Visual Studio. Sogar noch stärker mit Visual Studio 2017 und zum Ausführen und Debuggen von einem einzelnen Container kann zusätzlich dazu können auch ausführen und Debuggen eine Gruppe von Containern (betreffender) zur gleichen Zeit, wenn sie in der gleichen Docker compose.yml-Datei auf Projektmappenebene definiert sind.

## <a name="configuring-your-local-environment"></a>Konfigurieren der lokalen Umgebung

Mit den neuesten Versionen von Docker für Windows ist es einfacher, die jemals zum Docker-Anwendungen entwickeln, da das Setup einfach ist, ist, wie in den folgenden Ressourcen beschrieben.

**Weitere Informationen:** wechseln Sie zu, um weitere Informationen zum Installieren von Docker für Windows <https://docs.docker.com/docker-for-windows/>.

Wenn Sie Visual Studio 2015 verwenden, müssen Sie Update 3 oder höher sowie Visual Studio-Tools für Docker verfügen.

**Weitere Informationen:** finden Sie Anweisungen zum Installieren von Visual Studio [https://www.visualstudio.com/ \ Produkte/Visual Studio-2015-Produkt-Editionen](https://www.visualstudio.com/products/vs-2015-product-editions).

Um weitere Informationen zum Installieren von Visual Studio-Tools für Docker anzuzeigen, wechseln Sie zu <http://aka.ms/vstoolsfordocker> und <https://docs.microsoft.com/dotnet/articles/core/docker/visual-studio-tools-for-docker>.

Wenn Sie Visual Studio 2017 verwenden, wird Unterstützung für Docker bereits verwendet.

## <a name="using-docker-tools-in-visual-studio-2015"></a>Mithilfe von Docker-Tools in Visual Studio 2015

Visual Studio-Tools für Docker bietet eine einheitliche Methode zum Entwickeln und überprüfen Sie lokal die Docker-Container für Linux in einem Linux-Docker-Host oder virtuellen Computer oder Ihrer Windows-Container direkt unter Windows.

Wenn Sie einen einzelnen Container verwenden, werden im ersten Schritt müssen Sie beginnen Docker-Unterstützung in Ihr Projekt .NET Core zu aktivieren. Zu diesem Zweck das Kontextmenü der Projektdatei, wie in Abbildung 4-25 dargestellt.

![https://i1.visualstudiogallery.msdn.s-msft.com/0f5b2caa-ea00-41c8-b8a2-058c7da0b3e4/Image/File/205468/1/Add-docker-Support.PNG](./media/image31.png)

Abbildung 4-25: das Aktivieren der Docker-Unterstützung für Visual Studio-Projekts

## <a name="using-docker-tools-in-visual-studio-2017"></a>Verwenden von Docker-Tools in Visual Studio 2017

Beim Hinzufügen Docker-Unterstützung zu einem Service-Projekt in der Projektmappe (siehe Abbildung 4-26), Visual Studio ist nicht einfach eine DockerFile-Datei dem Projekt hinzufügen, es ist auch ein Abschnitt "Dienst" in der Projektmappe Docker compose.yml-Dateien (oder erstellen die Dateien aus, wenn sie nicht hinzufügen vorhanden sein). Es ist eine einfache Möglichkeit zum Verfassen von multicontainer Projektmappe zu beginnen. Anschließend können Sie die Docker-compose.yml-Dateien öffnen und mit zusätzlichen Funktionen zu aktualisieren.

![](./media/image32.png)

Abbildung 4-26: das Aktivieren der Unterstützung von Docker-Lösung in einem 2017 von Visual Studio-Projekt

Die dockerfile-Datei von dieser Aktion nicht nur dem Projekt hinzugefügt, werden außerdem die erforderliche Konfiguration Codezeilen hinzugefügt, um eine globale Docker compose.yml auf Projektmappenebene festgelegt.

Sie können auch Docker-Unterstützung aktivieren beim Erstellen einer ASP.NET Core-Projekts in Visual Studio-2017, wie in Abbildung 4-27 dargestellt.

![](./media/image33.png)

Abbildung 4-27: das Aktivieren der Docker Unterstützung beim Erstellen eines Projekts

Nachdem Sie die Projektmappe in Visual Studio Docker-Unterstützung hinzugefügt haben, sehen Sie auch mit den hinzugefügten Docker-compose.yml-Dateien im Projektmappen-Explorer eine neue Knotenstruktur, wie in Abbildung 4-28 dargestellt.

![](./media/image34.PNG)

Abbildung 4-28: Docker compose.yml Dateien zeigen jetzt im Projektmappen-Explorer

Sie können die Bereitstellung einer Multicontainer-Anwendung unter Verwendung einer einzelnen Docker-compose.yml beim Ausführen von Docker ergeben. Allerdings fügt Visual Studio eine Gruppe, damit Sie, abhängig von der Umgebung (Entwicklung im Vergleich zur Produktion) und die Ausführung der überschreiben können Typ (Version im Vergleich zu Debug). Diese Funktion wird in den Kapiteln besser erklärt werden.

**Weitere Informationen:** Detailinformationen zu den Dienste-Implementierung und Verwendung von Visual Studio-Tools für Docker, lesen Sie die folgenden Artikeln:

Erstellen, Debuggen, aktualisieren und Aktualisieren von apps in einem lokalen Docker-Container: [https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh/](https://docs.microsoft.com/azure/vs-azure-tools-docker-edit-and-refresh)

Stellen Sie einen ASP.NET Container bereit, mit einem Docker-Remotehost: [https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker/](https://docs.microsoft.com/azure/vs-azure-tools-docker-hosting-web-apps-in-docker)


>[!div class="step-by-step"]
[Vorherigen] (Docker-apps-Inner-Schleife-workflow.md) [weiter] (Set-up-windows-containers-with-powershell.md)
