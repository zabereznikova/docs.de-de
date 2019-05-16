---
title: Monolithische Anwendungen
description: Verstehen Sie die grundlegenden Konzepte für das containerisieren monolithischer Anwendungen.
ms.date: 02/15/2019
ms.openlocfilehash: e577f9a8d9ce4f9d2c8180318b1df181db730e2f
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65641294"
---
# <a name="monolithic-applications"></a>Monolithische Anwendungen

In diesem Szenario sind Sie erstellen eine einfachen und monolithischen Webanwendung oder einen Dienst und als Container bereitstellen. Innerhalb der Anwendung möglicherweise nicht die Struktur monolithische sein; Es kann mehrere Bibliotheken, Komponenten oder sogar Ebenen (Anwendungsebene, Domänenebene, Datenzugriffsebene, usw.) enthalten. Extern, ist es einem einzelnen Container, wie ein einzelner Prozess, einzelne Webanwendung oder einzelnen Dienst.

Stellen Sie einen einzelnen Container bereit, der diese Anwendung darstellt, um dieses Modell zu verwalten. Für die Skalierung, fügen Sie einfach ein paar weitere Kopien mit einem vorangestellten Lastenausgleich hinzu. Die Einfachheit stammt aus der Verwaltung von einer einzelnen Bereitstellung in einem einzelnen Container oder virtuellen Computer (VM).

Ist nach dem Dienstprinzipal, dass ein Container nur eine Sache ist, und wird es in einem Prozess der monolithische Muster in Konflikt. Sie können mehrere Komponenten, Bibliotheken oder interne Schichten in jedem Container einschließen, wie in Abbildung 4-1 dargestellt.

![Eine monolithische app verfügt über alle oder die meisten Funktionen innerhalb einer einzelnen Prozess oder Container, und es gegliedertes in internen Schichten und Bibliotheken.](./media/image1.png)

**Abbildung 4-1.** Ein Beispiel der Architektur der monolithischen Anwendung

Der Nachteil dieses Ansatzes ist, wenn Warnungen oder die Anwendung und skaliert wächst. Wenn die gesamte Anwendung skaliert werden kann, ist dies kein Problem. Allerdings sind in den meisten Fällen einige Teile der Anwendung Engpässe, die erfordern, Skalierung, während andere Komponenten verwendet werden.

Bei Verwendung des typischen e-Commerce-Beispiels, benötigen Sie wahrscheinlich für die Komponente für die Produktinformationen skalieren ist. Viele Kunden suchen Produkte erst und kaufen sie anschließend. Mehr Kunden verwenden Ihren Warenkorb als die Zahlungspipeline. Weniger Kunden fügen Kommentare hinzu oder zeigen ihren Bestellungsverlauf an. Und Sie haben wahrscheinlich nur eine Handvoll Mitarbeiter in einer einzelnen Region, die den Inhalt und die Marketingkampagnen verwalten müssen. Durch das Skalieren des monolithischen Entwurfs der gesamte Code ist mehrmals bereitgestellt.

Zusätzlich zu den "Skalieren – alles, was" Problem erfordern Änderungen einer einzelnen Komponente einen erneuten Test der gesamten Anwendung als auch eine vollständige erneute Bereitstellung aller Instanzen.

Der monolithische Ansatz wird häufig, und viele Organisationen mit dieser Architektur Methode entwickeln. Viele nutzen akzeptable Ergebnisse, gut auf, während andere Einschränkungen auftreten. Viele Anwendungen in diesem Modell entworfen, da Tools und Infrastruktur zum Erstellen dienstorientierter Architekturen zu schwierig waren, und sie nicht die Notwendigkeit sehen, bis die Anwendung gewachsen ist.

Aus Sicht der Infrastruktur kann jeder Server viele Anwendungen auf dem gleichen Host auszuführen und verfügen über ein akzeptables effizienzverhältnis in Ihrer Nutzung von Ressourcen, wie in Abbildung 4-2 dargestellt.

![Ein einzelner Host kann mehrere apps in einem separaten Container ausführen.](./media/image2.png)

**Abbildung 4-2**. Einem mehrere apps/Container-host

Aus Sicht der Verfügbarkeit müssen monolithische Anwendungen schließlich als Ganzes bereitgestellt werden. Dies bedeutet, dass für den Fall, dass Sie müssen *beenden und starten Sie*, alle Funktionen und alle Benutzer werden während des Zeitfensters für die Bereitstellung beeinflusst werden. In bestimmten Situationen die Verwendung von Azure und Container diesen Situationen und verringern die Wahrscheinlichkeit von Ausfallzeiten der Anwendung, wie Sie in Abbildung 4 – 3 sehen können.

Sie können mithilfe von dedizierten VMs für jede Instanz monolithische Anwendungen in Azure bereitstellen. Mithilfe von [Azure VM Scale Sets](https://docs.microsoft.com/azure/virtual-machine-scale-sets/), Sie können die VMs problemlos skalieren.

Sie können auch [Azure App Services](https://azure.microsoft.com/services/app-service/) monolithische Anwendungen ausführen und Instanzen problemlos skalieren, ohne die virtuellen Computer verwalten zu müssen. Azure App Services können einzelne Instanzen von Docker-Containern, ausführen, was die Bereitstellung vereinfacht.

Sie können mehrere virtuelle Computer als Docker-Hosts bereitstellen, und führen eine beliebige Anzahl von Containern pro virtuellem Computer. Anschließend können mithilfe von Azure Load Balancer, wie in Abbildung 4: 3, Sie Skalierung verwalten.

![Eine monolithische app kann zu anderen Hosts skalierte werden, in denen jeweils die app im Container ausgeführt wird.](./media/image3.png)

**Abbildung 4-3**. Mehrere Hosts horizontalen Skalieren einer einzelnen Docker-apps/Anwendungscontainer

Sie können die Bereitstellung des Hosts selbst über die herkömmlichen Bereitstellungsverfahren verwalten.

Sie können Docker-Container über die Befehlszeile verwalten, mit Befehlen wie `docker run` und `docker-compose up`, und Sie können auch die in Pipelines für Continuous Delivery (CD) zu automatisieren und Bereitstellen in Docker-Hosts aus Azure DevOps-Dienste, z. B.

## <a name="monolithic-application-deployed-as-a-container"></a>Monolithische Anwendung, die als Container bereitgestellt wird

Es gibt Vorteile bei der Verwendung von Containern zur Verwaltung monolithischer Bereitstellungen. Das Skalieren von Containerinstanzen ist wesentlich schneller und einfacher als die Bereitstellung zusätzlicher VMs.

Die Bereitstellung von Updates, wie Docker-Images, ist wesentlich schneller und effizienter im Netzwerk. Docker-Container starten in der Regel in Sekunden, wodurch Rollouts beschleunigt. Löschen eines Docker-Containers ist so einfach wie das Aufrufen der `docker stop` Befehl aus, in der Regel in weniger als einer Sekunde abgeschlossen.

Da Container entwurfsbedingt grundsätzlich unveränderlich sind, müssen Sie sich nie über beschädigte VMs machen, weil ein Updateskript vergessen haben, um bestimmte Konfigurationen oder Dateien auf dem Datenträger zu berücksichtigen.

Obwohl monolithische apps von Docker profitieren können, sind wir nur die Tipps von den Vorteilen besprochen. Die größere Vorteile der Verwaltung von Containern stammen aus der Bereitstellung mit containerorchestratoren, die die verschiedenen Instanzen und den Lebenszyklus jeder Containerinstanz verwalten. Das Aufteilen der monolithischen Anwendung in Subsysteme, die skaliert, entwickelt und einzeln bereitgestellt werden können, ist Ihr Einstiegspunkt in die Welt der Microservices.

Weitere Informationen zu "lift and shift" monolithische Anwendungen mit Containern und wie Sie Ihre Anwendungen modernisieren können, lesen Sie diese zusätzliche Microsoft-Anleitung, [modernisieren vorhandener .NET-Anwendungen mit Azure-Cloud und Windows-Containern ](../../modernize-with-azure-and-containers/index.md), die Sie können auch als PDF-Datei aus <https://aka.ms/LiftAndShiftWithContainersEbook>.

## <a name="publish-a-single-docker-container-app-to-azure-app-service"></a>Veröffentlichen Sie eine einzelne Docker-Container-app in Azure App Service

Entweder bietet einfach eine einzelner Container-app, Azure App Services, weil eine schnelle Überprüfung eines Containers in Azure bereitgestellten abgerufen werden soll oder die app ist eine hervorragende Möglichkeit, skalierbare einzelner Container Services bereitstellen.

Mit Azure App Service ist intuitiv und die Einrichtung und schnell ausgeführt werden, da sie über gute Git bietet Integration auszuführende Code, erstellen Sie sie in Microsoft Visual Studio, und direkt in Azure bereitstellen. Traditionell (mit keine Docker), ggf. andere Funktionen, Frameworks oder Abhängigkeiten, die in App Services nicht unterstützt werden Sie jedoch erforderlich, um dafür zu warten, bis das Azure-Team diese Abhängigkeiten im Anwendungsdienst aktualisiert oder zu anderen Diensten wie gewechselt Service Fabric, Cloud Services oder sogar VMs, für die Sie verfügen über zusätzliche Kontrolle und können eine erforderliche Komponente oder ein Framework für Ihre Anwendung installieren.

Jetzt aber, wie in Abbildung 4-4 dargestellt kann bei der Verwendung von Visual Studio 2017 docker-Unterstützung in Azure App Service Sie sollen beliebig in Ihrer appumgebung. Wenn Sie eine Abhängigkeit zu Ihrer app hinzugefügt, da Sie es in einem Container ausführen, erhalten Sie die Möglichkeit, diese Abhängigkeiten in Ihrer dockerfile-Datei oder Docker-Image einschließen.

![Überblick über die Visual Studio-Assistenten zum Veröffentlichen in Azure app Service, markieren die Auswahl für die containerregistrierung.](./media/image4.png)

**Abbildung 4-4**. Veröffentlichen Sie einen Container in Azure App Service aus Visual Studio-apps/Container

Abbildung 4-4 zeigt auch, dass es sich bei der veröffentlichungsfluss überträgt ein Bild über eine Containerregistrierung, die möglicherweise die Azure-Containerregistrierung (eine Registrierung in der Nähe Ihrer Bereitstellungen in Azure und von Azure Active Directory-Gruppen und-Konten gesichert werden) oder andere Docker-Registrierungen wie Docker Hub oder in lokalen Registrierungen.

>[!div class="step-by-step"]
>[Zurück](common-container-design-principles.md)
>[Weiter](state-and-data-in-docker-applications.md)
