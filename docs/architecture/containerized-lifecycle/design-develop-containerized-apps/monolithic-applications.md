---
title: Monolithische Anwendungen
description: Verstehen der grundlegenden Konzepte für das Containerisieren monolithischer Anwendungen.
ms.date: 02/15/2019
ms.openlocfilehash: 8664153ee2e9d1d253164e43ac13105f6dbf476c
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2019
ms.locfileid: "72771035"
---
# <a name="monolithic-applications"></a>Monolithische Anwendungen

In diesem Szenario erstellen Sie eine einzelne, monolithische Webanwendung oder einen Dienst und stellen sie/ihn als Container bereit. Innerhalb der Anwendung ist die Struktur nicht zwangsläufig monolithisch; sie kann z.B. mehrere Bibliotheken, Komponenten oder sogar Schichten umfassen (Anwendungsschicht, Domänenschicht, Datenzugriffsschicht usw.). Extern stellt sie jedoch einen einzelnen Container dar, wie einen einzelnen Prozess, eine einzelne Webanwendung oder einen einzelnen Dienst.

Stellen Sie einen einzelnen Container bereit, der diese Anwendung darstellt, um dieses Modell zu verwalten. Um die Anwendung zu skalieren, fügen Sie einfach ein paar weitere Kopien mit einem davor platzierten Lastenausgleichsmodul hinzu. Die Einfachheit stammt aus der Verwaltung einer einzelnen Bereitstellung in einem einzelnen Container oder virtuellen Computer (VM).

Dem Prinzip folgend, dass ein Container nur eine Aufgabe und das in einem Prozess ausführt, steht das monolithische Muster im Konflikt. Sie können mehrere Komponenten/Bibliotheken oder interne Schichten in jeden Container einschließen, wie in Abbildung 4–1 dargestellt.

![Abbildung, die eine monolithische App zeigt, die durch Klonen der App horizontal hochskaliert wird.](./media/monolithic-applications/monolithic-application-architecture-example.png)

**Abbildung 4-1.** Beispiel für eine monolithische Anwendungsarchitektur

Eine monolithische Anwendung hat ihre Funktionalität ganz oder zum größten Teil innerhalb eines einzelnen Prozesses oder Containers und weist interne Schichten oder Bibliotheken als Komponenten auf. Der Nachteil dieses Ansatzes wird offensichtlich, wenn die Anwendung wächst und skaliert werden muss. Wenn die gesamte Anwendung skaliert werden kann, ist dies kein Problem. In den meisten Fällen sind jedoch nur einige Teile der Anwendung Engpässe, die Skalierung erfordern, während andere Komponente weniger häufig verwendet werden.

Wenn Sie das gewöhnliche eCommerce-Beispiel verwenden, müssen Sie sehr wahrscheinlich die Komponente für die Produktinformationen skalieren. Viele Kunden suchen Produkte erst und kaufen sie anschließend. Mehr Kunden verwenden Ihren Warenkorb als die Zahlungspipeline. Weniger Kunden fügen Kommentare hinzu oder zeigen ihren Bestellungsverlauf an. Und Sie haben möglicherweise nur eine Handvoll Mitarbeiter in einer bestimmten Region, die den Inhalt und die Marketingkampagnen verwalten müssen. Wenn der monolithische Entwurf skaliert wird, wird der gesamte Code mehrmals bereitgestellt.

Zusätzlich zu dem Problem, dass „alle Komponenten skaliert werden müssen“, erfordern Änderungen einer einzelnen Komponente einen erneuten Test der gesamten Anwendung und eine vollständige erneute Bereitstellung aller Instanzen.

Der monolithische Ansatz wird häufig verwendet, und viele Organisationen entwickeln nach dieser Architekturmethode. Viele freuen sich an akzeptablen Ergebnissen, während andere an Grenzen stoßen. Viele Unternehmen haben ihre Anwendungen unter Verwendung dieses Modells entworfen, da Tools und Infrastruktur schon seit Jahren zu komplex für die Erstellung einer SOA (Service-Oriented Architecture) sind. Sie haben die Notwendigkeit nicht erkannt, etwas zu ändern, bis die Anwendung gewachsen ist.

Aus Sicht der Infrastruktur kann jeder Server, wie in Abbildung 4-2 dargestellt, viele Anwendungen innerhalb desselben Hosts ausführen und ein akzeptables Effizienzverhältnis in Ihrer Ressourcenverwendung haben.

![Abbildung, die einen Host mit mehreren Apps in separaten Containern zeigt.](./media/monolithic-applications/host-with-multiple-apps-containers.png)

**Abbildung 4-2**. Ein Host, der mehrere Apps/Container ausführt

Schließlich müssen aus dem Blickwinkel der Verfügbarkeit monolithische Anwendungen als Ganzes bereitgestellt werden; das bedeutet, dass im Fall eines erforderlichen *Beendens und Startens* während des Bereitstellungsfensters die gesamte Funktionalität und alle Benutzer betroffen sind. In bestimmten Situationen kann die Verwendung von Azure und Containern diese Situationen minimieren und die Wahrscheinlichkeit von Ausfallzeiten Ihrer Anwendung verringern, wie in Abbildung 4–3 zu ersehen.

Sie können monolithische Anwendungen in Azure mithilfe dedizierter VMs für die einzelnen Instanzen bereitstellen. Mithilfe von [Azure VM Scale Sets](https://docs.microsoft.com/azure/virtual-machine-scale-sets/) lassen sich die VMs komfortabel skalieren.

Sie können auch [Azure App Services](https://azure.microsoft.com/services/app-service/) verwenden, um monolithische Anwendungen auszuführen und Instanzen problemlos zu skalieren, ohne dass die VMs verwaltet werden müssen. Azure App Services kann ebenfalls einzelne Instanzen von Docker-Containern ausführen, was die Bereitstellung vereinfacht.

Sie können mehrere VMs als Docker-Hosts bereitstellen und eine beliebige Anzahl von Containern pro VM ausführen. Dann können Sie mithilfe eines Azure Load Balancers die Skalierung verwalten, wie in Abbildung 4–3 dargestellt.

![Abbildung, die eine monolithische App zeigt, die auf verschiedene Hosts horizontal hochskaliert ist.](./media/monolithic-applications/multiple-hosts-from-single-docker-container.png)

**Abbildung 4-3**. Mehrere Hosts, die eine einzelne Docker-Anwendung horizontal hochskalieren

Die Verwaltung der Hosts selbst kann mithilfe herkömmlicher Bereitstellungsverfahren erfolgen.

Sie können Docker-Container auf der Befehlszeile verwalten, indem Sie Befehle wie `docker run` und `docker-compose up` verwenden, und Sie können dies auch in CD-Pipelines (Continuous Delivery) automatisieren und beispielsweise aus Azure DevOps Services heraus auf Docker-Hosts bereitstellen.

## <a name="monolithic-application-deployed-as-a-container"></a>Monolithische Anwendung, die als Container bereitgestellt wird

Das Verwenden von Containern zur Verwaltung monolithischer Bereitstellungen hat Vorteile. Das Skalieren von Containerinstanzen ist wesentlich schneller und einfacher als die Bereitstellung zusätzlicher VMs.

Die Bereitstellung von Updates, wie Docker-Images, ist wesentlich schneller und effizienter im Netzwerk. Docker-Container starten in der Regel in Sekunden, wodurch Rollouts beschleunigt werden. Das Löschen eines Docker-Containers erschöpft sich im Aufrufen des `docker stop`-Befehls und ist in der Regel in weniger als einer Sekunde abgeschlossen.

Da Container unveränderlich sind, müssen Sie sich keine Gedanken über beschädigte VMs machen, etwa weil ein Updateskript bestimmte Konfigurationen oder restliche Dateien auf einem Datenträger nicht erfasst hat.

Zwar können monolithische Apps von Docker profitieren, wir behandeln hier aber gerade einmal die offenkundigsten Vorteile. Die größeren Vorteile für die Verwaltung von Containern stammen aus der Bereitstellung mit Containerorchestratoren, die die verschiedenen Instanzen und den Lebenszyklus jeder Containerinstanz verwalten. Das Aufteilen der monolithischen Anwendung in Subsysteme, die skaliert, entwickelt und einzeln bereitgestellt werden können, ist Ihr Einstiegspunkt in die Welt der Microservices.

Informationen zum Lift-and-Shift monolithischer Anwendungen mithilfe von Containern und zum Modernisieren Ihrer Anwendungen finden Sie in diesem zusätzlichen Microsoft-Leitfaden [Modernisieren vorhandener .NET-Anwendungen mit Azure Cloud und Windows-Containern](../../modernize-with-azure-containers/index.md), den Sie hier <https://aka.ms/LiftAndShiftWithContainersEbook> auch als PDF-Datei herunterladen können.

## <a name="publish-a-single-docker-container-app-to-azure-app-service"></a>Veröffentlichen einer einzelnen Docker-Container-App in Azure App Service

Ob Sie eine schnelle Überprüfung eines in Azure bereitgestellten Containers wünschen oder die App einfach eine in einem Container bereitzustellende App ist, Azure App Services stellt eine hervorragende Möglichkeit dar, skalierbare Dienste auf der Grundlage einzelner Container bereitzustellen.

Die Verwendung von Azure App Service ist intuitiv, und Sie sind aufgrund der hervorragenden Git-Integration zur Annahme Ihres Codes, seiner Erstellung in Microsoft Visual Studio und der direkten Bereitstellung in Azure schnell betriebsbereit. Aber wenn Sie bei herkömmlicher Bereitstellung (also ohne Docker) andere Funktionen, Frameworks oder Abhängigkeiten benötigten, die in App Services nicht unterstützt werden, mussten Sie warten, bis das Azure-Team ein Update dieser Abhängigkeiten in App Service vornahm oder zu anderen Diensten wechseln, wie Service Fabric, Cloud Services – eventuell sogar zu einfachen VMs, bei denen Sie mehr Kontrolle haben und eine erforderliche Komponente oder ein erforderliches Framework für Ihre Anwendung installieren können.

Jetzt haben Sie, wie in Abbildung 4–4 dargestellt, bei der Verwendung von Visual Studio 2017 dank der Containerunterstützung in Azure App Service die Möglichkeit, Ihre App-Umgebung um beliebige Zusätze zu erweitern. Wenn Sie Ihrer App eine Abhängigkeit hinzugefügt haben, haben Sie die Möglichkeit, diese Abhängigkeiten in Ihr Dockerfile oder Ihr Docker-Image einzuschließen, da Sie Ihre App in einem Container ausführen.

![Screenshot des Dialogfelds „App Service erstellen“ mit einer Containerregistrierung.](./media/monolithic-applications/publish-azure-app-service-container.png)

**Abbildung 4-4**. Veröffentlichen eines Containers in Azure App Service aus Visual Studio-Apps/Containern

Abbildung 4–4 zeigt außerdem, dass ein Image vom Veröffentlichungsfluss durch eine Containerregistrierung übertragen wird, wobei es sich um eine Azure-Containerregistrierung (eine Registrierung in der Nähe Ihrer Bereitstellungen in Azure, die von Azure Active Directory-Gruppen und -Konten gesichert wird) oder andere Docker-Registrierungen wie Docker Hub oder eine lokale Registrierung handeln kann.

>[!div class="step-by-step"]
>[Zurück](common-container-design-principles.md)
>[Weiter](state-and-data-in-docker-applications.md)
