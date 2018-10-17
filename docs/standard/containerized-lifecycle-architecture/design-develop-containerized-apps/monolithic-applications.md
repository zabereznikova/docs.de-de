---
title: Monolithische Anwendungen
description: Lebenszyklus von Docker-Containeranwendungen mit der Microsoft-Plattform und Tools
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: a2fe2c325377ec49f89199ad2e36c950ebab6a24
ms.sourcegitcommit: e42d09e5966dd9fd02847d3e7eeb4ec0877069f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2018
ms.locfileid: "49374702"
---
# <a name="monolithic-applications"></a>Monolithische Anwendungen

Sie sind in diesem Szenario erstellen eine einzelne und monolithischen Webanwendung oder einen Dienst und als Container bereitstellen. Innerhalb der Anwendung möglicherweise nicht die Struktur monolithische sein; Es kann mehrere Bibliotheken, Komponenten oder sogar Ebenen (Anwendungsebene, Domänenebene, Datenzugriffsebene, usw.) enthalten. Extern, ist es einem einzelnen Container, wie ein einzelner Prozess, einzelne Webanwendung oder einzelnen Dienst.

Stellen Sie einen einzelnen Container bereit, der diese Anwendung darstellt, um dieses Modell zu verwalten. Für die Skalierung, fügen Sie einfach ein paar weitere Kopien mit einem vorangestellten Lastenausgleich hinzu. Die Einfachheit stammt aus der Verwaltung von einer einzelnen Bereitstellung in einem einzelnen Container oder virtuellen Computer (VM).

Ist nach dem Dienstprinzipal, dass ein Container nur eine Sache ist, und wird es in einem Prozess der monolithische Muster in Konflikt. Sie können mehrere Komponenten, Bibliotheken oder interne Schichten in jedem Container einschließen, wie in Abbildung 4-1 dargestellt.

![](./media/image1.png)

Abbildung 4-1: ein Beispiel der Architektur der monolithischen Anwendung

Der Nachteil dieses Ansatzes ist, wenn Warnungen oder die Anwendung und skaliert wächst. Wenn die gesamte Anwendung skaliert werden kann, ist dies kein Problem. Allerdings sind in den meisten Fällen einige Teile der Anwendung Engpässe, die erfordern, Skalierung, während andere Komponenten verwendet werden.

Bei Verwendung des typischen e-Commerce-Beispiels, benötigen Sie wahrscheinlich für die Komponente für die Produktinformationen skalieren ist. Viele Kunden suchen Produkte erst und kaufen sie anschließend. Mehr Kunden verwenden Ihren Warenkorb als die Zahlungspipeline. Weniger Kunden fügen Kommentare hinzu oder zeigen ihren Bestellungsverlauf an. Und Sie haben wahrscheinlich nur eine Handvoll Mitarbeiter in einer einzelnen Region, die den Inhalt und die Marketingkampagnen verwalten müssen. Durch das Skalieren des monolithischen Entwurfs der gesamte Code ist mehrmals bereitgestellt.

Zusätzlich zu den "Skalieren – alles, was" Problem erfordern Änderungen einer einzelnen Komponente einen erneuten Test der gesamten Anwendung als auch eine vollständige erneute Bereitstellung aller Instanzen.

Der monolithische Ansatz wird häufig, und viele Organisationen mit dieser Architektur Methode entwickeln. Viele nutzen akzeptable Ergebnisse, gut auf, während andere Einschränkungen auftreten. Viele Anwendungen in diesem Modell entworfen, da Tools und Infrastruktur zum Erstellen dienstorientierter Architekturen zu schwierig waren, und sie nicht die Notwendigkeit sehen, bis die Anwendung gewachsen ist.

Aus Sicht der Infrastruktur kann jeder Server viele Anwendungen auf dem gleichen Host auszuführen und verfügen über ein akzeptables effizienzverhältnis in Ihrer Nutzung von Ressourcen, wie in Abbildung 4-2 dargestellt.

![](./media/image2.png)

Abbildung 4-2: einem Host Ausführen mehrerer apps/Container

Sie können mithilfe von dedizierten VMs für jede Instanz monolithische Anwendungen in Azure bereitstellen. Mithilfe von [Azure VM Scale Sets](https://docs.microsoft.com/azure/virtual-machine-scale-sets/), Sie können die VMs problemlos skalieren. [Azure App Service](https://azure.microsoft.com/services/app-service/) kann auch monolithische Anwendungen ausführen und Instanzen problemlos skalieren, ohne dass die VMs verwaltet werden müssen. Seit 2016 kann Azure App Services einzelne Instanzen von Docker-Container auch ausführen, vereinfachen die Bereitstellung. Und mit Docker können Sie eine einzelne VM als Docker-Host bereitstellen und ausführen können mehrere Instanzen. Verwenden den Azure Balancer aus, wie in Abbildung 4: 3 dargestellt, können Sie die Skalierung verwalten.

![](./media/image3.png)

Abbildung 4 – 3: mehrere Hosts horizontalen Skalieren einer einzelnen Docker-apps/Anwendungscontainer

Sie können die Bereitstellung auf den verschiedenen Hosts über die herkömmlichen Bereitstellungsverfahren verwalten. Sie können Docker-Hosts verwalten, mit Befehlen wie `docker run` manuell über die Automatisierung, z.B. Pipelines für Continuous Delivery (CD), die wir weiter unten in diesem e-Book zu erklären.

## <a name="monolithic-application-deployed-as-a-container"></a>Monolithische Anwendung, die als Container bereitgestellt wird

Es gibt Vorteile bei der Verwendung von Containern zur Verwaltung monolithischer Bereitstellungen. Das Skalieren von Containerinstanzen ist wesentlich schneller und einfacher als die Bereitstellung zusätzlicher VMs. Auch wenn VM-Skalierungsgruppen sind eine großartige Funktion zum Skalieren von virtuellen Computern, die zum Hosten der Docker-Container erforderlich sind, dauern diese einrichten. Wenn die App-Konfiguration als App-Instanz bereitgestellt wird, wird diese als Teil der VM verwaltet.

Die Bereitstellung von Updates, wie Docker-Images, ist wesentlich schneller und effizienter im Netzwerk. Die Vn-Instanzen können auf den gleichen Hosts wie Ihre Vn-1-Instanzen, Eliminieren von Kosten durch zusätzliche virtuelle Computer eingerichtet werden. Docker-Images starten in der Regel in Sekunden, wodurch Rollouts beschleunigt. Löschen einer Docker-Instanz ist so einfach wie das Aufrufen der `docker stop` Befehl aus, in der Regel in weniger als einer Sekunde abgeschlossen.

Da Container entwurfsbedingt grundsätzlich unveränderlich sind, müssen Sie sich nie über beschädigte VMs machen, weil ein Updateskript vergessen haben, um bestimmte Konfigurationen oder Dateien auf dem Datenträger zu berücksichtigen.

Obwohl monolithische apps von Docker profitieren können, sind wir nur die Tipps von den Vorteilen besprochen. Bereitstellung mit containerorchestratoren, die die verschiedenen Instanzen und den Lebenszyklus jeder Containerinstanz verwalten, ist die größere Vorteile der Verwaltung von Containern stammen. Das Aufteilen der monolithischen Anwendung in Subsysteme, die skaliert, entwickelt und einzeln bereitgestellt werden können, ist Ihr Einstiegspunkt in die Welt der Microservices.

## <a name="publishing-a-single-docker-container-app-to-azure-app-service"></a>Veröffentlichen eine einzelne Docker-Container-app in Azure App Service

Entweder bietet einfach eine einzelner Container-app, Azure App Services, weil eine schnelle Überprüfung eines Containers in Azure bereitgestellten abgerufen werden soll oder die app ist eine hervorragende Möglichkeit, skalierbare einzelner Container Services bereitstellen.

Mit Azure App Service ist intuitiv und die Einrichtung und schnell ausgeführt werden, da sie über gute Git bietet Integration auszuführende Code, erstellen Sie sie in Microsoft Visual Studio, und direkt in Azure bereitstellen. Traditionell (mit keine Docker), ggf. andere Funktionen, Frameworks oder Abhängigkeiten, die in App Services nicht unterstützt werden Sie jedoch erforderlich, um dafür zu warten, bis das Azure-Team diese Abhängigkeiten im Anwendungsdienst aktualisiert oder zu anderen Diensten wie gewechselt Service Fabric, Cloud Services oder sogar VMs, für die Sie verfügen über zusätzliche Kontrolle und können eine erforderliche Komponente oder ein Framework für Ihre Anwendung installieren.

Jetzt hingegen (auf der Microsoft Connect 2016 im November 2016 angekündigt) und wie in Abbildung 4‑4, angezeigt, wenn es sich bei Visual Studio 2017 verwenden, Unterstützung von Containern in Azure App Service bietet Ihnen die Möglichkeit, enthalten beliebig in Ihrer appumgebung. Wenn Sie eine Abhängigkeit zu Ihrer app hinzugefügt, da es in einem Container ausgeführt wird, erhalten Sie die Möglichkeit, diese Abhängigkeiten in Ihrer dockerfile-Datei oder Docker-Image einschließen.

![](./media/image4.png)

Abbildung 4-4: Veröffentlichen eines Containers in Azure App Service aus Visual Studio-apps/Container

Abbildung 4-4 zeigt auch, dass es sich bei der veröffentlichungsfluss überträgt ein Bild über eine Containerregistrierung, die möglicherweise die Azure-Containerregistrierung (eine Registrierung in der Nähe Ihrer Bereitstellungen in Azure und von Azure Active Directory-Gruppen und-Konten gesichert werden) oder andere Docker-Registrierungen wie Docker Hub oder in lokalen Registrierungen.


>[!div class="step-by-step"]
[Zurück](common-container-design-principles.md)
[Weiter](state-and-data-in-docker-applications.md)
