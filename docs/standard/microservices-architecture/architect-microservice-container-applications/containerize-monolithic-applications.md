---
title: Containerizing monolithischen Anwendungen
description: ".NET Microservices Architektur für Datenvolumes .NET-Anwendungen | Containerizing monolithischen Anwendungen"
keywords: Docker, Microservices, ASP.NET, Container
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 11e2c24403b9b61584e424696c844e00e5d34b03
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="containerizing-monolithic-applications"></a>Containerizing monolithischen Anwendungen

Möglicherweise möchten eine einzelne, monolithically bereitgestellte Webanwendung oder einen Dienst zu erstellen und als einen Container bereitstellen. Die Anwendung selbst möglicherweise nicht intern monolithischen, aber strukturiert, wie mehrere Bibliotheken, Komponenten oder sogar Ebenen (Anwendungsschicht, Domänenebene Datenzugriffsschicht, usw.). Extern, allerdings ist es einem einzelnen Container – einem einzelnen Prozess, eine einzelne Webanwendung oder einen einzelnen Dienst.

Um dieses Modell zu verwalten, stellen Sie einen einzelnen Container, um die Anwendung darzustellen. Zum Skalieren, fügen Sie einfach weitere Kopien mit vorangestelltem einen Lastenausgleich hinzu. Die Einfachheit stammen aus eine einzelne Bereitstellung in einem einzelnen Container oder virtuellen Computer verwalten.

![](./media/image1.png)

**Abbildung 4 – 1**. Beispiel für die Architektur einer Datenvolumes monolithischen-Anwendung

Sie können mehrere Komponenten, Bibliotheken oder interne Ebenen in jedem Container einschließen, wie in Abbildung 4 – 1 veranschaulicht. Allerdings dieses monolithischen Muster kann zu Konflikten mit dem Container-Prinzip "ein Container führt eine Aufgabe und wird in einem Prozess", aber möglicherweise werden für einige Fälle ok.

Der Nachteil dieses Ansatzes wird offensichtlich, wenn die Anwendung wächst, erfordern sie zum Skalieren. Wenn die gesamte Anwendung skaliert werden kann, ist es nicht tatsächlich ein Problem aufgetreten. In den meisten Fällen sind jedoch nur einige Teile der Anwendung die Punkte Drossel, Skalierung, erfordern, während andere Komponenten sind kleiner verwendet.

Beispielsweise müssen in einer typischen e-Commerce-Anwendung Sie wahrscheinlich das Produkt Informationen Subsystem skalieren da viele weitere Kunden nach Produkten zu suchen, als sie erwerben. Verwenden Sie die Zahlung Pipeline verwenden mehr Kunden Warenkorb. Weniger Kunden Hinzufügen von Kommentaren oder ihre Bestellung Verlauf anzeigen. Und Sie müssen möglicherweise nur eine Handvoll Mitarbeiter, die den Inhalt und Marketingkampagnen verwalten müssen. Wenn Sie aufgrund eines monolithischen Entwurfs skalieren, wird alle Code für diese verschiedenen Aufgaben mehrmals bereitgestellt und bei der gleichen Grade skaliert.

Es gibt mehrere Möglichkeiten zum Skalieren einer Anwendung – horizontale Duplizierung, Teilen unterschiedliche Bereiche der Anwendung, und der Partitionierung ähnliche Geschäftskonzepte oder der Daten. Jedoch zusätzlich zu das Problem der Skalierung aller Komponenten, Änderungen an einer einzelnen Komponente erfordern vollständige ein erneuter Test die gesamte Anwendung und eine vollständige erneute Bereitstellung von allen Instanzen.

Monolithische Ansatz ist jedoch üblich, ist die Entwicklung der Anwendung anfänglich einfacher als Microservices Ansätze. Viele Organisationen daher entwickeln, verwenden diese Architektur. Während einige Organisationen gut genug Ergebnisse gearbeitet haben, werden andere Grenzwerte erreichen. Viele Organisationen konzipiert, ihre Anwendungen, die dieses Modell verwenden, da Tools und Infrastruktur zu schwierig, zur Erstellung Diensts dienstorientierte Architektur (SOA) Jahren sowie sie nicht die Notwendigkeit vorgenommen, bis die Anwendung vergrößert wurde.

Aus Sicht der Infrastruktur kann jeden Server viele Anwendungen innerhalb desselben Hosts ausführen und eine akzeptable Verhältnis von Effizienz in der Auslastung von Ressourcen, wie in Abbildung 4 – 2 dargestellt.

![](./media/image2.png)

**Abbildung 4 – 2**. Aufgrund eines monolithischen Ansatz: Hosten Ausführen von mehreren apps jede app, die als Container ausgeführt

Aufgrund eines monolithischen Anwendungen in Microsoft Azure können mithilfe von dedizierten virtuellen Computern für jede Instanz bereitgestellt werden. Darüber hinaus verwenden [Azure VM-Skalierungsgruppen](https://docs.microsoft.com/azure/virtual-machine-scale-sets/), können Sie die virtuellen Computer problemlos skalieren. [Azure App Service](https://azure.microsoft.com/services/app-service/) auch monolithische Anwendungen ausführen und Instanzen problemlos zu skalieren, ohne dass Sie die virtuellen Computer verwalten können. Seit 2016 können Azure-App-Dienste einzelne Instanzen von Docker-Containern ebenfalls ausführen Vereinfachung der Bereitstellung von.

Als eine QA-Umgebung oder begrenzten produktionsumgebung können Sie mehrere Docker-Host virtuelle Computer bereitstellen und verteilen sie mithilfe der Azure-Lastenausgleich, wie in Abbildung 4 – 3 dargestellt. So können Sie die mit einem Ansatz gröbere skalieren zu verwalten, da die gesamte Anwendung in einem einzelnen Container aktiv ist.

![](./media/image3.png)

**Abbildung 4 – 3**. Beispiel für mehrere Hosts, die Skalierung auf einer einzelnen Container-Anwendung

Bereitstellung für die verschiedenen Hosts kann mit herkömmlichen Bereitstellungsverfahren verwaltet werden. Docker-Hosts verwaltet werden können, mit Befehlen wie `docker run` oder `docker-compose` manuell oder durch die Automatisierung, z. B. Pipelines für fortlaufende Übermittlung (CD) durchgeführt.

## <a name="deploying-a-monolithic-application-as-a-container"></a>Bereitstellen einer monolithischen-Anwendung als container

Es lassen sich Vorteile mit Containern um monolithischen anwendungsbereitstellungen zu verwalten. Skalieren von containerinstanzen ist wesentlich schneller und einfacher als die Bereitstellung zusätzlicher VMs. Selbst bei Verwendung von VM-Skalierungsgruppen Zeit in Anspruch nehmen virtuellen Computer starten. Wenn als herkömmliche Anwendungsinstanzen anstelle von Containern bereitgestellt wird, wird die Konfiguration der Anwendung im Rahmen des virtuellen Computers, verwaltet die ist nicht ideal.

Bereitstellen von Updates, wie Docker-Images ist wesentlich schneller und Netzwerk effizient. Docker-Images beginnen in der Regel in Sekunden an, die Rollouts beschleunigt. Beendet eine Instanz der Docker-Image ist genauso einfach wie das Ausgeben einer `docker stop` Befehl, und in der Regel in weniger als einer Sekunde abgeschlossen ist.

Da Container entwurfsbedingt unveränderlich sind, müssen Sie niemals beschädigte VMs kümmern. Im Gegensatz dazu vergessen Update Skripts für einen virtuellen Computer möglicherweise einige spezifische Konfiguration oder die Datei auf dem Datenträger verbleibenden zu berücksichtigen.

Während der Docker monolithische Anwendungen profitieren können, werden wir nur zu den Vorteilen berühren. Zusätzliche Vorteile der Verwaltung von Containern stammen aus der Bereitstellung mit Container Orchestrators, die die verschiedenen Instanzen und Lebenszyklus jeder Container-Instanz zu verwalten. Aufteilen der monolithischen Anwendung in Subsysteme, die skaliert, entwickelt und einzeln bereitgestellt werden können, ist Ihre Einstiegspunkt außerhalb des Bereichs des Microservices.

## <a name="publishing-a-single-container-based-application-to-azure-app-service"></a>Veröffentlichen einer einzelnen Container-basierenden Anwendung nach Azure App Service

Ob die Überprüfung eines Containers in Azure bereitgestellten abgerufen werden soll, oder wenn eine Anwendung einfach einen einzelnen Container-Anwendung ist, bietet Azure App Service eine hervorragende Möglichkeit, skalierbare Single-Container-basierte Dienste bereitstellen. Mithilfe von Azure App Service ist einfach. Es bietet eine hervorragende Integration mit Git zu vereinfachen, schalten den Code, erstellen Sie sie in Visual Studio und direkt in Azure bereitgestellt.

![](./media/image4.png)

**Abbildung 4-4**. Veröffentlichen einer einzelnen Container-Anwendung nach Azure App Service aus Visual Studio

Ohne Docker ggf. andere Funktionen, Frameworks oder Abhängigkeiten, die in Azure App Service, nicht unterstützt werden mussten Sie warten, bis der Azure-Team diese Abhängigkeiten im App-Dienst aktualisiert. Oder wechseln Sie zu anderen Diensten wie Azure Service Fabric, Azure Cloud Services oder sogar VMs, auf dem Steuerelement mussten weiter und Sie konnte eine erforderliche Komponente oder ein Framework für Ihre Anwendung installieren musste.

Container-Unterstützung in Visual Studio 2017 bietet Ihnen die Möglichkeit, die in Ihrer anwendungsumgebung beliebig enthalten, wie in Abbildung 4-4 dargestellt. Da Sie es in einem Container ausgeführt werden, wenn Sie Ihre Anwendung eine Abhängigkeit hinzufügen, können Sie die Abhängigkeit in Ihrem Image dockerfile-Datei oder Docker einschließen.

Wie auch in Abbildung 4-4 legt der Fluss veröffentlichen ein Bild über den eine containerregistrierung. Dies kann die Azure Containerregistrierung (eine Registrierung auf Ihre Bereitstellungen in Azure zu schließen, und von Azure Active Directory-Gruppen und Konten gesichert werden) oder andere Docker-Registrierung, wie Docker Hub oder eine lokale Registrierung sein.


>[!div class="step-by-step"]
[Vorherigen] (index.md) [weiter] (Docker-Anwendung-Status-data.md)
