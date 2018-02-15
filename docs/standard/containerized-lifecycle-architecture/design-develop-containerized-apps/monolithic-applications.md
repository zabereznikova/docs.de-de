---
title: Aufgrund eines monolithischen Anwendungen
description: Lebenszyklus von Docker-Containeranwendungen mit der Microsoft-Plattform und Tools
keywords: Docker, Microservices, ASP.NET, Container
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 95561aaa8ffccb8eae3fe276192c6648c0819685
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="monolithic-applications"></a>Aufgrund eines monolithischen Anwendungen

In diesem Szenario erstellen eine einzelne und monolithischen Webanwendung oder einen Dienst und als Container bereitstellen. In der Anwendung möglicherweise nicht die Struktur monolithischen sein; Es kann mehrere Bibliotheken, Komponenten oder sogar Ebenen (Anwendungsschicht, Domänenebene Datenzugriffsebene, usw.) umfassen. Extern, ist es einem einzelnen Container, z. B. einen einzelnen Prozess, einzelne Webanwendung oder Einzelgerät.

Um dieses Modell zu verwalten, stellen Sie einen einzelnen Container, um die Anwendung darzustellen. Um sie zu skalieren, fügen Sie einfach ein paar weitere Kopien mit vorangestelltem ein Lastenausgleich hinzu. Die Einfachheit stammen aus eine einzelne Bereitstellung in einem einzelnen Container oder virtuellen Computer (VM) verwalten.

Der Prinzipal ein Container führt nur eine Aufgabe aus, und wird in einem Prozess folgt das monolithische Muster in Konflikt. Sie können mehrere Komponenten-Bibliotheken oder interne Ebenen innerhalb jeder Container einschließen, wie in Abbildung 4 – 1 veranschaulicht.

![](./media/image1.png)

Abbildung 4-1: Beispiel monolithischen Anwendungsarchitektur

Der Nachteil dieses Ansatzes stammen, oder wenn die Anwendung wächst, erfordern sie zum Skalieren. Wenn die gesamte Anwendung skaliert, ist es nicht tatsächlich ein Problem aufgetreten. Allerdings sind in den meisten Fällen einige Teile der Anwendung die Drossel Punkte, die erfordern, Skalierung, während andere Komponenten weniger verwendet werden.

Im typischen eCommerce-Beispiel ist benötigen Sie wahrscheinlich die Informationen Produktkomponente skalieren. Viele weitere Kunden durchsuchen Produkte, als sie erwerben. Verwenden Sie die Zahlung Pipeline verwenden mehr Kunden Warenkorb. Weniger Kunden Hinzufügen von Kommentaren oder ihre Bestellung Verlauf anzeigen. Und Sie haben wahrscheinlich nur eine Handvoll Mitarbeiter in einer einzelnen Region, die den Inhalt und Marketingkampagnen verwalten müssen. Durch zentrales Skalieren der aufgrund eines monolithischen Entwurfs, der gesamte Code ist mehrfach bereitgestellt.

Zusätzlich zu den "Skalierung-alles" Problem, Änderungen an einer einzelnen Komponente erfordern vollständige ein erneuter Test die gesamte Anwendung sowie eine vollständige erneute Bereitstellung aller Instanzen.

Aufgrund eines monolithischen Ansatz ist, und viele Organisationen mit dieser Architektur Methode entwickeln. Viele genießen genügend Ergebnisse gut auf, während andere Grenzwerte auftreten. Viele ihrer Anwendungen in diesem Modell entworfen, daran, dass die Tools und Infrastruktur zu schwierig erstellen dienstorientierter Architekturen wurden, und sie nicht die Notwendigkeit sehen, erst die app vergrößert wurde.

Aus Sicht der Infrastruktur kann jeder Server viele Anwendungen innerhalb desselben Hosts ausführen und eine akzeptable Verhältnis von Effizienz in Ihre Nutzung Ressourcen haben, wie in Abbildung 4 – 2 dargestellt.

![](./media/image2.png)

Abbildung 4 – 2: einem Host, der mit mehreren apps-Container

Sie können aufgrund eines monolithischen Anwendungen in Azure mithilfe von dedizierten virtuellen Computern für jede Instanz bereitstellen. Mit [Azure VM-Skalierungsgruppen](https://docs.microsoft.com/azure/virtual-machine-scale-sets/), können Sie die virtuellen Computer problemlos skalieren. [Azure App-Dienste](https://azure.microsoft.com/en-us/services/app-service/) monolithische Anwendungen ausführen können, und Instanzen problemlos zu skalieren, ohne den VMs verwalten zu müssen. Seit 2016 können Azure-App-Dienste einzelne Instanzen von Docker-Containern ebenfalls ausführen Vereinfachung der Bereitstellungsstatus. Und mit Docker, können Sie eine einzelne virtuelle Maschine als Docker-Host bereitstellen und Ausführen mehrerer Instanzen. Der Azure-Lastenausgleich, können wie in Abbildung 4 – 3 gezeigt, Sie Skalierung verwalten.

![](./media/image3.png)

Abbildung 4 – 3: mehrere Hosts dezentrale Skalierung einer einzelnen Docker apps/Anwendungscontainer

Sie können die Bereitstellung für die verschiedenen Hosts über herkömmliche Bereitstellungsverfahren verwalten. Verwalten von Docker-Hosts können mithilfe der Befehle wie `docker run` manuell, durch die Automatisierung, z. B. Continuous Delivery (CD)-Pipelines, die erläutern wir weiter unten in diesem e-Book.

## <a name="monolithic-application-deployed-as-a-container"></a>Aufgrund eines monolithischen Anwendung, die als Container bereitgestellt

Es lassen sich Vorteile mit Containern um monolithische Bereitstellungen zu verwalten. Skalieren die Instanzen von Containern ist wesentlich schneller und einfacher als die Bereitstellung zusätzlicher VMs. Obwohl die VM-Skalierungsgruppen sind eine hervorragende Funktion Skalieren von VMs, die erforderlich sind, um den Docker-Containern zu hosten, Zeit in Anspruch nehmen sie einrichten. Wenn als app-Instanzen bereitgestellt wird, wird die Konfiguration der app im Rahmen des virtuellen Computers verwaltet.

Bereitstellen von Updates, wie Docker-Images ist wesentlich schneller und Netzwerk effizient. Die Vn-Instanzen können auf den gleichen Hosts wie der Vn-1-Instanzen, entfernen Sie zusätzliche Kosten, die infolge zusätzlicher VMs eingerichtet werden. Docker-Images beginnen in der Regel in Sekunden, die Befehlseingabe Rollouts. Beendet eine Instanz der Docker ist genauso einfach wie das Aufrufen der `docker stop` Befehl ein, in der Regel in weniger als einer Sekunde abschließen.

Da Container entwurfsbedingt grundsätzlich unveränderlich sind, müssen Sie niemals beschädigte VMs kümmern, da ein Updateskript vergessen haben, um einige spezifische Konfiguration oder die Datei auf dem Datenträger verbleibenden zu berücksichtigen.

Obwohl monolithischen apps von Docker profitieren können, sind wir auf nur die Tipps zu den Vorteilen berühren. Die größere Vorteile der Verwaltung von Containern stammt Bereitstellen mit Orchestrators Container, die die verschiedenen Instanzen und Lebenszyklus jeder Container-Instanz zu verwalten. Aufteilen der monolithischen Anwendung in Subsysteme, die skaliert, entwickelt und einzeln bereitgestellt werden können, ist Ihre Einstiegspunkt außerhalb des Bereichs des Microservices.

## <a name="publishing-a-single-docker-container-app-to-azure-app-service"></a>Veröffentlichen eine einzelne Docker-Container-app in Azure App Service

Entweder enthält einfach eine einzelnen Container-app, Azure App-Dienste, da eine schnelle Überprüfung eines Containers in Azure bereitgestellten abgerufen werden soll oder die app ist eine hervorragende Möglichkeit, skalierbare einzelnen Container-Dienstleistungen.

Mithilfe von Azure App Service ist intuitiv können und Sie und schnell ausgeführt werden, da er hervorragende Git bietet Integration auszuführenden Code, erstellen Sie sie in Microsoft Visual Studio, und direkt in Azure bereitgestellt. Traditionell (mit keinen Docker), ggf. andere Funktionen, Frameworks oder Abhängigkeiten, die in App-Dienste nicht unterstützt werden Sie jedoch erforderlich, um dafür warten Sie, bis das Azure-Team diese Abhängigkeiten in der App Service aktualisiert oder von anderen Diensten wie übernommen Service Fabric, Cloud-Dienste oder auch nur virtuelle Computer, für die weiteren Kontrolle haben, und eine erforderliche Komponente oder ein Framework für Ihre Anwendung installieren können.

Jetzt jedoch (auf der Microsoft Connect 2016 im November 2016 vorgestellt) wie in Abbildung 4‑4, angezeigt, wenn mithilfe von Visual Studio 2017, Container-Unterstützung in Azure App Service bietet Ihnen die Möglichkeit, beliebig in Ihrer appumgebung enthalten. Wenn Sie eine Abhängigkeit zu Ihrer app hinzugefügt, da es in einem Container ausgeführt wird, erhalten Sie die Möglichkeit, einschließlich solcher Abhängigkeiten in Ihrem Image dockerfile-Datei oder Docker.

![](./media/image4.png)

Abbildung 4-4: Veröffentlichen eines Containers in Azure App Service aus Visual Studio apps/Containern

Abbildung 4-4 zeigt auch, dass der Ablauf veröffentlichen ein Bild über den eine Containerregistrierung, der sein kann der Azure-Container-Registrierung schiebt (eine Registrierung in der Nähe auf Ihre Bereitstellungen in Azure und von Azure Active Directory-Gruppen und Konten gesichert werden) oder andere Docker-Registrierung wie Docker Hub oder lokal Registrierungen.


>[!div class="step-by-step"]
[Vorherigen] (Allgemeine-Container-Design-principles.md) [weiter] (State-and-data-in-docker-applications.md)
