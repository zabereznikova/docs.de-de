---
title: Containerisieren monolithischer Anwendungen
description: Das Containerisieren monolithischer Anwendungen bietet zwar nicht alle Vorteile der Microservicearchitektur, dafür jedoch wichtige Vorteile beim Bereitstellen, von denen Sie direkt profitieren können.
ms.date: 01/30/2020
ms.openlocfilehash: 0e6f7504a91d2b1a89193471746168fc34f50956
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503285"
---
# <a name="containerizing-monolithic-applications"></a>Containerisieren monolithischer Anwendungen

Sie sollten eine einzelne, monolithisch bereitgestellte Webanwendung oder einen Webdienst erstellen und als Container bereitstellen. Die Anwendung selbst ist möglicherweise nicht intern monolithisch, aber in mehrere Bibliotheken, Komponenten oder sogar Ebenen strukturiert (Anwendungsebene, Domänenebene, Datenzugriffsebene, usw.). Extern ist sie allerdings ein einzelner Container – ein einzelner Prozess, eine einzelne Webanwendung oder ein einzelner Dienst.

Stellen Sie einen einzelnen Container bereit, der diese Anwendung darstellt, um dieses Modell zu verwalten. Führen Sie Erweiterungen aus, um die Kapazität zu erhöhen. Fügen Sie dazu weitere Exemplare mit einem Lastenausgleich davor hinzu. Die Einfachheit stammt aus der Verwaltung einer einzelnen Bereitstellung in einem einzelnen Container oder virtuellen Computer.

![Diagramm, das die Komponenten einer monolithischen Containeranwendung darstellt.](./media/containerize-monolithic-applications/monolithic-containerized-application.png)

**Abbildung 4-1**. Beispiel für die Architektur einer containerisierten monolithischen Anwendung

Sie können, wie in Abbildung 4-1 veranschaulicht, mehrere Komponenten, Bibliotheken oder interne Ebenen in jedem Container einschließen. Die meisten Funktionen einer monolithischen Containeranwendung befinden sich innerhalb eines einzelnen Containers, der interne Ebenen oder Bibliotheken hat. Die Anwendung führt Erweiterungen durch Klonen des Containers auf mehrere Server/VMs aus. Allerdings kann dieses monolithische Muster zu einem Konflikt mit dem Containerprinzip „ein Container führt eine Aufgabe in einem Prozess aus“ führen. In einigen Fällen kommt es jedoch nicht zum Konflikt.

Der Nachteil dieses Ansatzes wird offensichtlich, wenn die Anwendung wächst und skaliert werden muss. Wenn die gesamte Anwendung skaliert werden kann, ist es kein Problem. In den meisten Fällen sind jedoch nur einige Teile der Anwendung Engpässe, die Skalierung erfordern, während andere Komponente weniger häufig verwendet werden.

Beispielsweise müssen Sie in einer typischen E-Commerceanwendung mit höherer Wahrscheinlichkeit das Subsystem der Produktinformationen skalieren, da viel mehr Kunden nach Produkten suchen, als Kunden Produkte erwerben. Mehr Kunden verwenden Ihren Warenkorb als die Zahlungspipeline. Weniger Kunden fügen Kommentare hinzu oder zeigen ihren Bestellungsverlauf an. Zudem haben Sie möglicherweise nur eine Handvoll Mitarbeiter, die den Inhalt und die Marketingkampagnen verwalten müssen. Wenn Sie den monolithischen Entwurf skalieren, wird der gesamte Code für diese verschiedenen Aufgaben mehrmals bereitgestellt und zum gleichen Grad skaliert.

Es gibt mehrere Möglichkeiten zum Skalieren einer Anwendung – horizontale Duplizierung, Teilen unterschiedlicher Bereiche der Anwendung und die Partitionierung ähnlicher Geschäftskonzepte oder -daten. Zusätzlich zu den Problemen der Skalierung aller Komponenten erfordern Änderungen einer einzelnen Komponente einen erneuten Test der gesamten Anwendung und eine vollständig neue Bereitstellung aller Instanzen.

Der monolithische Ansatz ist jedoch üblich, da die Entwicklung der Anwendung anfänglich einfacher ist als bei Microservicesansätzen. Daher führen viele Unternehmen Entwicklungen mit diesem Architekturansatz aus. Während einige Unternehmen gute Ergebnisse erzielen, stoßen andere an Grenzen. Viele Unternehmen haben ihre Anwendungen unter Verwendung dieses Modells entworfen, da Tools und Infrastruktur schon seit Jahren zu komplex für die Erstellung von serviceorientierter Architektur (SOA) sind. Sie haben die Notwendigkeit nicht erkannt – bis die Anwendung gewachsen ist.

Aus Sicht der Infrastruktur kann jeder Server, wie in Abbildung 4-2 dargestellt, viele Anwendungen innerhalb desselben Hosts ausführen und ein akzeptables Effizienzverhältnis in der Ressourcenverwendung haben.

![Diagramm, das einen Host zeigt, der viele Apps in Containern ausführt.](./media/containerize-monolithic-applications/host-multiple-apps-containers.png)

**Abbildung 4-2**. Monolithischer Ansatz: Der Host führt mehrere Anwendungen aus, jede Anwendung wird als Container ausgeführt

Monolithische Anwendungen in Microsoft Azure können mithilfe von dedizierten VMs für jede Instanz bereitgestellt werden. Außerdem können Sie die VMs problemlos mit [Azure-VM-Skalierungsgruppen](https://azure.microsoft.com/documentation/services/virtual-machine-scale-sets/) skalieren. [Azure App Service](https://azure.microsoft.com/services/app-service/) kann auch monolithische Anwendungen ausführen und Instanzen problemlos skalieren, ohne dass Sie die VMs verwalten müssen. Seit 2016 kann Azure App Services ebenfalls einzelne Instanzen von Docker-Containern ausführen, was die Bereitstellung vereinfacht.

Als QA-Umgebung oder begrenzte Produktionsumgebung können Sie mehrere Docker-Host-VMs bereitstellen und Sie, wie in Abbildung 4-3 dargestellt, mithilfe des Azure-Lastenausgleichs ausgleichen. So können Sie die Skalierung mit einem gröberen Ansatz verwalten, da die gesamte Anwendung in einem einzelnen Container aktiv ist.

![Diagramm, das mehrere Hosts zeigt, die die monolithischen App-Container ausführen.](./media/containerize-monolithic-applications/docker-infrastructure-monolithic-application.png)

**Abbildung 4-3**. Beispiel für die Skalierung einer einzelnen Containeranwendung durch mehrere Hosts

Die Bereitstellung auf den verschiedenen Hosts kann mit herkömmlichen Bereitstellungsverfahren verwaltet werden. Docker-Hosts können mit manuellen Befehlen wie `docker run` oder `docker-compose` oder durch die Automatisierung, z.B. Pipelines für Continuous Delivery (CD), verwaltet werden.

## <a name="deploying-a-monolithic-application-as-a-container"></a>Bereitstellen einer monolithischen Anwendung als Container

Das Verwenden von Containern zur Verwaltung monolithischer Anwendungsbereitstellungen hat Vorteile. Das Skalieren von Containerinstanzen ist wesentlich schneller und einfacher als die Bereitstellung zusätzlicher VMs. Selbst wenn Sie VM-Skalierungsgruppen verwenden, benötigt der Start der VMs Zeit. Bei der Bereitstellung als herkömmliche Anwendungsinstanzen anstelle von Containern wird die Konfiguration der Anwendung im Rahmen der VM verwaltet. Das ist nicht ideal.

Die Bereitstellung von Updates, wie Docker-Images, ist wesentlich schneller und effizienter im Netzwerk. Docker-Images starten in der Regel in Sekunden, was Rollouts beschleunigt. Das Löschen einer Instanz eines Docker-Images ist genauso einfach wie das Ausgeben eines `docker stop`-Befehls, und in der Regel in weniger als einer Sekunde abgeschlossen.

Da Container entwurfsbedingt unveränderlich sind, müssen Sie sich keine Sorgen um beschädigte VMs machen. Im Gegensatz dazu vergessen Updateskripts für eine VM möglicherweise einige spezifische Konfigurationen oder Dateien auf dem Datenträger.

Während monolithische Anwendungen von Docker profitieren können, werden hier nur die Vorteile besprochen. Zusätzliche Vorteile für die Verwaltung von Containern stammen aus der Bereitstellung mit Containerorchestratoren, die die verschiedenen Instanzen und den Lebenszyklus jeder Containerinstanz verwalten. Das Aufteilen der monolithischen Anwendung in Subsysteme, die skaliert, entwickelt und einzeln bereitgestellt werden können, ist Ihr Einstiegspunkt in die Welt der Microservices.

## <a name="publishing-a-single-container-based-application-to-azure-app-service"></a>Veröffentlichen einer einzelnen Containeranwendung in Azure App Service

Ob Sie einen in Azure bereitgestellten Container überprüfen möchten, oder wenn eine Anwendung einfach eine einzelnen Containeranwendung ist, Azure App Service bietet hervorragende, skalierbare Dienste auf Grundlage einzelner Containeranwendungen. Die Verwendung von Azure App Service ist einfach. Der Dienst bietet eine hervorragende Integration mit Git, um die Vorgehensweise für das Verwenden und Erstellen von Code in Visual Studio und die direkte Bereitstellung in Azure zu vereinfachen.

![Screenshot des Dialogfelds „App Service erstellen“ mit einer Containerregistrierung.](./media/containerize-monolithic-applications/publish-azure-app-service-container.png)

**Abbildung 4-4**. Veröffentlichen einer einzelnen Containeranwendung in Azure App Service aus Visual Studio 2019

Wenn Sie ohne Docker andere Funktionen, Frameworks oder Abhängigkeiten benötigten, die in Azure App Service nicht unterstützt werden, mussten Sie warten, bis das Azure-Team diese Abhängigkeiten im Anwendungsdienst aktualisiert. Oder Sie mussten zu anderen Diensten wie Azure Service Fabric oder zu VMs wechseln. Dort hatten Sie mehr Kontrolle und konnten eine erforderliche Komponente oder ein Framework für Ihre Anwendung installieren.

Die Containerunterstützung in Visual Studio 2017 bietet Ihnen, wie in Abbildung 4-4 dargestellt, die Möglichkeit, beliebige Elemente in Ihre Anwendungsumgebung einzuschließen. Da Sie sie in einem Container ausführen, können Sie die Abhängigkeit in Ihrem Dockerfile oder Ihrem Docker-Image einschließen, wenn Sie Ihrer Anwendung eine Abhängigkeit hinzufügen.

Abbildung 4-4 zeigt auch, wie der Veröffentlichungsfluss ein Image über eine Containerregistrierung überträgt. Hierbei handelt es sich um eine Azure-Containerregistrierung (eine Registrierung in der Nähe Ihrer Bereitstellungen in Azure, die von Azure Active Directory-Gruppen und -Konten gesichert wird) oder andere Docker-Registrierungen wie Docker-Hub oder eine lokale Registrierung.

>[!div class="step-by-step"]
>[Zurück](index.md)
>[Weiter](docker-application-state-data.md)
