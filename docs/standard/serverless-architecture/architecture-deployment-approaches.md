---
title: Bereitstellung Architekturansätze - serverlose apps
description: Eine Anleitung für verschiedene Arten von Enterprise-Architekturen werden bereitgestellt, in die Cloud, Vergleich zwischen IaaS, PaaS, Container und serverlose.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 6566971d8984ec046b8b5fa2db295c1d48c30b20
ms.sourcegitcommit: 4c158beee818c408d45a9609bfc06f209a523e22
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2018
ms.locfileid: "49369967"
---
# <a name="architecture-deployment-approaches"></a>Architekturansätze-Bereitstellung

Unabhängig von der Architektur abweichen Ansatz zum Entwerfen einer Geschäftsanwendung, die Implementierung und Bereitstellung von Anwendungen verwendet. Unternehmen Hosten von Anwendungen für alles, von der physischen Hardware, serverlosen Funktionen.

## <a name="n-tier-applications"></a>N-Tier-Anwendungen

Die [N-schichtige Architekturmuster](https://docs.microsoft.com/azure/architecture/guide/architecture-styles/n-tier) ist eine ausgereifte Architektur und bezieht sich auf Anwendungen, die verschiedene logische Schichten in separate physische Ebenen zu trennen. N-schichtige Architektur ist eine physische Implementierung der N-Schichten-Architektur. Die am häufigsten verwendete Implementierung dieser Architektur umfasst:

* Eine Präsentationsschicht, z. B. eine Web-app.
* Eine API oder die Daten zugreifen, z. B. eine REST-API-Tarif.
* Eine Datenebene, z. B. eine SQL­Datenbank.

![Architektur mit N Ebenen](./media/n-tier-architecture.png)

N-Tier-Projektmappen weisen folgende Merkmale auf:

* Projekte werden in der Regel mit Ebenen ausgerichtet.
* Testen unter Umständen anders von Ebene berücksichtigt werden.
* Tarife sorgen für Abstraktionsebenen, z. B. die Präsentationsebene die Implementierungsdetails der Datenebene in der Regel ignorieren.
* In der Regel interagieren Ebenen nur mit angrenzenden Ebenen.
* Versionen sind häufig auf das Projekt verwaltet, und daher-Ebene auf. Eine einfache API-Änderung unter Umständen eine neue Version einer gesamten mittleren Ebene.

Dieser Ansatz bietet mehrere Vorteile, einschließlich:

* Isolation der Datenbank (häufig das Front-End keinen direkten Zugriff auf das Back-End).
* Wiederverwenden der API (zum Beispiel, Mobile, Desktop- und Web-app-Clients alle die gleichen APIs verwenden können).
* Fähigkeit, Ebenen, die unabhängig voneinander skalieren.
* Refactoring Isolation: eine Ebene kann ohne Auswirkungen auf andere Ebenen umgestaltet werden.

## <a name="on-premises-and-infrastructure-as-a-service-iaas"></a>Lokale und Infrastructure-as-a-Service (IaaS)

Der herkömmliche Ansatz für das Hosten von Anwendungen erfordert Kauf neuer Hardware und verwalten all der Softwareinstallationen, einschließlich des Betriebssystems. Ursprünglich beteiligt diese teuer Rechenzentren und die physische Hardware. Die Herausforderungen, die im Lieferumfang von physischer Hardware ausgeführt werden viele, einschließlich:

* Muss für "just-in Fall" überschüssige kaufen oder bei Bedarf Szenarios mit spitzenauslastung.
* Sichern physischen Zugriff auf die Hardware.
* Verantwortung für Hardwarefehler (z. B. Fehler auf dem Datenträger).
* Kühlung.
* Konfigurieren von Router und Load balancer.
* Power-Redundanz.
* Sichern des Zugriffs von Software.

![IaaS-Ansatz](./media/iaas-approach.png)

Virtualisierung von Hardware, die über "virtuelle Computer" kann die Infrastruktur als Dienst (IaaS). Hostcomputer sind effektiv zum Bereitstellen von Ressourcen, die Instanzen mit Zuordnungen für ihre eigenen Arbeitsspeicher, CPU und Speicher aufgeteilt. Das Team die erforderlichen virtuellen Computer bereitgestellt und konfiguriert den Zugriff auf Speicher und der zugeordneten Netzwerke.

Weitere Informationen finden Sie unter [VM-Architektur mit N Ebenen Verweis](https://docs.microsoft.com/azure/architecture/reference-architectures/virtual-machines-windows/n-tier).

Obwohl Virtualisierung und Infrastructure-as-a-Service (IaaS) viele Probleme zu lösen, bietet es weiterhin viel Verantwortung an das Infrastruktur-Team. Das Team verwaltet Betriebssystemversionen, gilt der Sicherheitspatches und Drittanbieter-Abhängigkeiten auf den Zielcomputern installiert. Apps werden häufig auf Produktionscomputern im Vergleich zu den Test-Umgebung anders verhalten. Probleme entstehen aufgrund von verschiedenen abhängigkeitsversionen und/oder Betriebssystem-SKU-Ebenen. Obwohl viele Organisationen N-Tier-Anwendungen auf diesen Zielen bereitstellen, viele Unternehmen profitieren, um ein weiteres native Cloud-Modell bereitstellen, z. B. [Plattform als Dienst](#platform-as-a-service-paas). Architekturen mit Microservices sind schwieriger aufgrund der Anforderungen zum horizontalen hochskalieren für Flexibilität und Stabilität.

Weitere Informationen finden Sie unter [VMs](https://docs.microsoft.com/azure/virtual-machines/).

## <a name="platform-as-a-service-paas"></a>Platform-as-a-Service (PaaS)

Plattform konfiguriert wie a-Service (PaaS) bietet, muss der Lösungen, denen Entwickler direkt in eingebunden werden können. PaaS ist ein anderer Ausdruck für die verwaltete hosten. Es entfällt die Notwendigkeit des zugrunde liegenden Betriebssystems zu verwalten, Sicherheit, patches und in vielen Fällen keine Abhängigkeiten von Drittanbietern. Beispiele für Plattformen sind Webanwendungen, Datenbanken und Mobile back-ends.

PaaS die komplexen Herausforderungen für IaaS. PaaS kann der Entwickler den Code und kein Datenbankschema konzentrieren, anstatt wie er bereitgestellt wird. PaaS bietet folgende Vorteile:

* Nutzungsbasierte Bezahlung verwenden Modelle, die den Aufwand für die Investition in den Leerlauf Computern zu vermeiden.
* Direkte Bereitstellung und Optimierung des DevOps, continuous Integration (CI) und Pipelines für continuous Delivery (CD).
* Automatische Upgrades, Updates und Sicherheitspatches.
* Per Knopfdruck horizontales hoch- und zentrales hochskalieren (elastische Skalierung).

Der Hauptnachteil von PaaS wurde anbieterabhängigkeit bisher. Beispielsweise unterstützen einige PaaS-Anbieter nur ASP.NET, Node.js oder andere Sprachen und Plattformen. Produkte wie Azure App Service haben zum Behandeln von mehreren Plattformen und unterstützen eine Vielzahl von Sprachen und Frameworks zum Hosten von Web-apps weiterentwickelt.

![Platform-as-Service-Architektur](./media/paas-architecture.png)

## <a name="software-as-a-service-saas"></a>Software-as-a-Service (SaaS)

Software als Dienst oder SaaS ist zentral gehostet und verfügbar ohne lokale Installation oder Bereitstellung. SaaS wird häufig als Plattform zum Bereitstellen von Software setzt auf PaaS gehostet. SaaS bietet Dienste zum Ausführen und Herstellen einer Verbindung mit vorhandener Software. SaaS ist häufig die Branche und vertikalen spezifische. SaaS ist häufig lizenziert und in der Regel wird ein Client/Server-Modell. Die meisten modernen SaaS-Angebote verwenden webbasierte apps, für den Client. SaaS werden von Unternehmen in der Regel als eine Lösung für lizenzangebote betrachten. Es ist nicht als Aspekt der Architektur für die Skalierbarkeit und verwaltbarkeit einer Anwendung häufig implementiert. Tatsächlich sind die meisten SaaS-Lösungen auf IaaS, PaaS und/oder serverloses Back-Ends aufgebaut.

Weitere Informationen zu SaaS über eine [beispielanwendung](https://docs.microsoft.com/azure/sql-database/saas-tenancy-welcome-wingtip-tickets-app).

## <a name="containers-and-functions-as-a-service-faas"></a>Container und Funktionen als Dienst (FaaS)

Container sind eine interessante Lösung, die PaaS-ähnliche Vorteile ohne den Aufwand für die IaaS-ermöglicht. Ein Container ist im Wesentlichen eine Laufzeit, die die absolut erforderlichen Funktionen benötigt zum Ausführen einer Anwendung eindeutige enthält. Der Kernel oder Core-Teil der Host-Betriebssystem und Dienste wie Storage, werden auf einem Host freigegeben. Freigegebene Kernel kann Container einfach sein (einige sind reine Megabyte groß, im Vergleich zu den GB Größe typische virtuellen Computer). Mit Hosts, die bereits ausgeführt wird können Container schnell gestartet werden, hohen Verfügbarkeit ermöglicht wurde. Die Möglichkeit, Container schnell starten hinaus zusätzliche Ebenen der resilienz. Docker ist eine der beliebtesten Implementierungen von Containern.

Der Container bietet folgende Vorteile:

* Schlanke und portierbare
* Eigenständige daher keine Notwendigkeit, Abhängigkeiten zu installieren
* Geben Sie eine konsistente Umgebung unabhängig vom Host (Ausführung auf einem Laptop identisch wie auf einem Cloudserver)
* Kann schnell für horizontale Skalierung bereitgestellt werden
* Kann schnell neu gestartet, um nach einem Fehler wiederherstellen.

Ein Container, die auf einem containerhost (die wiederum auf einem bare-Metal-Computer oder einen virtuellen Computer ausführen kann) wird ausgeführt. Mehrere Container oder Instanzen der gleichen Container können auf einem Host ausgeführt werden. True, Failover und resilienz müssen die Container über Hosts hinweg skaliert werden.

Weitere Informationen zu Docker-Container, finden Sie unter [docker](../microservices-architecture/container-docker-introduction/docker-defined.md)?

Verwalten von Containern auf Hosts in der Regel erfordert eine Orchestrierung-Tools wie Kubernetes. Konfigurieren und Verwalten von Lösungen für Orchestrierung möglicherweise zusätzlichen Aufwand und Komplexität Projekten hinzufügen. Glücklicherweise bieten viele Cloudanbieter Orchestrierungsdiensten über PaaS-Lösungen zur Vereinfachung der Verwaltung von Containern.

Die folgende Abbildung veranschaulicht ein Beispiel für Kubernetes-Installation. Knoten im Installation Adresse horizontales hochskalieren und das Failover. Sie führen Sie Docker containerinstanzen, die vom Masterserver verwaltet werden. Die *Kubelet* ist der Client, die Befehle von Kubernetes, Docker überträgt.

![Kubernetes](./media/kubernetes-example.png)

Weitere Informationen zu einer Orchestrierung, finden Sie unter [Kubernetes in Azure](https://docs.microsoft.com/azure/aks/intro-kubernetes).

Funktionen als Dienst (FaaS) ist ein spezialisierten Container-Dienst, der serverlosen ähnelt. Eine spezifische Implementierung FaaS, namens [OpenFaaS](https://github.com/openfaas/faas), basiert auf den Container, um serverlose Funktionen bereitzustellen. OpenFaaS enthält Vorlagen, die alle Abhängigkeiten zum Ausführen eines Codeabschnitts Container packen. Mithilfe von Vorlagen vereinfacht den Prozess der Bereitstellung von Code als einer funktionellen Einheit. OpenFaaS zielt auf Architekturen, die Container und orchestratoren bereits enthalten, da sie die vorhandene Infrastruktur verwenden kann. Obwohl sie serverlose Funktionen bereitstellt, müssen speziell Sie Docker und ein Orchestrator verwenden.

## <a name="serverless"></a>Serverlose

Eine serverlose Architektur bietet eine klare Trennung zwischen Code und der hostumgebung. Implementieren Sie den Code in einem *Funktion* , wird aufgerufen, indem eine *Trigger*. Nachdem die Funktion beendet wird, können alle erforderlichen Ressourcen freigegeben werden. Der Trigger möglicherweise manuell, ein zeitlich festgelegtes Prozess, eine HTTP-Anforderung oder eine Datei hoch. Das Ergebnis des Triggers ist die Ausführung von Code. Obwohl serverlose Plattformen unterscheiden zu können, die meisten bieten Sie Zugriff auf vordefinierte APIs und Bindungen für die Optimierung von Aufgaben wie das Schreiben in eine Datenbank oder Message Queueing-Ergebnisse an.

Serverlose Konzepte ist eine Architektur, die sehr basiert auf die hostumgebung auf Code außer acht gelassen. Sie können als betrachtet werden *weniger Server*.

Containerlösungen bieten, dass Entwickler, die vorhandene Skripts zum Veröffentlichen von Code in die serverlose-fähige Images erstellen. Andere Implementierungen verwenden vorhandene PaaS-Lösungen, um eine skalierbare Architektur bereitzustellen.

Die Abstraktion bedeutet, dass das DevOps-Team nicht bereitstellen oder Verwalten von Servern, und bestimmte Container. Der serverlosen Plattform Hosts Code, entweder als Skripts oder App-Pakete ausführbare Dateien mit einer entsprechenden SDK erstellt und weist die erforderlichen Ressourcen für den Code zum Skalieren.

Die folgende Abbildung veranschaulicht die vier serverlose Komponenten. Eine HTTP-Anforderung bewirkt, dass den Checkout API Code ausgeführt wird. Der Checkout-API fügt Code in einer Datenbank, und die Einfügung löst einige andere Funktionen ausführen, um Aufgaben wie Computingaufgaben und Ausführen von der Reihenfolge ausgeführt werden.

![Serverlose Implementierung](./media/serverless-implementation.png)

Die serverlose Funktionen bietet folgende Vorteile:

* **Hohe Dichte.** Viele Instanzen des gleichen serverlose Codes können auf dem gleichen Host im Vergleich zum Container oder virtuellen Computern ausgeführt. Die Instanzen Skalierung über mehrere Hosts horizontales hochskalieren und resilienz.
* **Micro-Abrechnung**. Die meisten serverlose Anbieter Rechnung basierend auf serverlose Ausführungen, die massive kosteneinsparungen in bestimmten Szenarien zu aktivieren.
* **Sofortiges skalieren**. Serverless kann entsprechend von Workloads schnell und automatisch skalieren.
* **Schnellere Markteinführungszeiten** Entwickler sich auf Code konzentrieren und direkt auf der serverlosen Plattform bereitstellen. Komponenten können unabhängig voneinander freigegeben werden.

Serverless wird meist im Kontext von Compute erläutert, aber Sie können auch auf Daten anwenden. Z. B. [Azure SQL](https://docs.microsoft.com/azure/sql-database) und [Cosmos DB](https://docs.microsoft.com/azure/cosmos-db) bieten beide Clouddatenbanken, die Sie zum Konfigurieren von Hostcomputer oder Cluster nicht benötigen. Dieses Buch konzentriert sich auf serverloses Computing.

## <a name="summary"></a>Zusammenfassung

Es gibt ein breites Spektrum an verfügbaren Optionen für die Architektur, einschließlich der einen Hybridansatz. Serverless vereinfacht den Ansatz, Verwaltung und Kosten für die Anwendungsfunktionen auf Kosten der Kontrolle und Portabilität. Allerdings machen viele serverlose Plattformen Konfiguration zum unterstützen die Lösung zu optimieren. Bewährte Programmierverfahren können auch besser portierbaren Code und weniger serverlosen Plattform-Lock-in führen. Die folgende Tabelle zeigt die Architekturansätze nebeneinander an. Wählen Sie die serverlose Ihrer Skalierungsgruppe basierend auf Anforderungen, unabhängig davon, ob die Runtime verwaltet werden sollen und wie gut Sie Ihre Workloads in kleine Komponenten unterteilen können. Sie erfahren über mögliche Herausforderungen bei der serverlosen und andere zu bedenkenden Punkte im nächsten Kapitel.

|         |IaaS     |PaaS     |Container|Serverlose|
|---------|---------|---------|---------|----------|
|**Scale** (Skalieren)|VIRTUELLE COMPUTER       |Instanz |App      |Funktion  |
|**Auszüge aus**|Hardware|Plattform|OS-Server|Laufzeit   |
|**Komponententests** |VIRTUELLE COMPUTER       |Projekt  |Bild    |Code      |
|**Lebensdauer**|Monate|Tage bis Monate|Minuten bis Tage|Millisekunden, die Minuten|
|**Verantwortung**|Anwendungen, Abhängigkeiten, Laufzeit und Betriebssystem|Anwendungen und Abhängigkeiten|Anwendungen, Abhängigkeiten und Laufzeit|Funktion

* **Skalierung** bezieht sich auf die Einheit, die verwendet wird, um die Anwendung zu skalieren
* **Abstrahiert** bezieht sich auf die Ebene, die durch die Implementierung abstrahiert wird
* **Einheit** bezieht sich auf den Bereich der Umfang der Bereitstellung
* **Lebensdauer** bezieht sich auf die typischen Laufzeit einer bestimmten Instanz
* **Verantwortung** bezieht sich auf den Aufwand zu erstellen, bereitstellen und verwalten die Anwendung

Im nächste Kapitel werden konzentrieren, serverlose Architektur, Anwendungsfälle und Entwurfsmuster.

## <a name="recommended-resources"></a>Empfohlene Ressourcen

* [Azure-anwendungsarchitekturleitfaden](https://docs.microsoft.com/azure/architecture/guide/)
* [Azure Cosmos DB](https://docs.microsoft.com/azure/cosmos-db)
* [Azure SQL](https://docs.microsoft.com/azure/sql-database)
* [N-schichtige Architekturmuster](https://docs.microsoft.com/azure/architecture/guide/architecture-styles/n-tier)
* [Kubernetes in Azure](https://docs.microsoft.com/azure/aks/intro-kubernetes)
* [Microservices](https://docs.microsoft.com/azure/architecture/guide/architecture-styles/microservices)
* [VM-N-Tier-Referenzarchitektur](https://docs.microsoft.com/azure/architecture/reference-architectures/virtual-machines-windows/n-tier)
* [Virtuelle Computer](https://docs.microsoft.com/azure/virtual-machines/)
* [What is Docker? (Was ist Docker?)](../microservices-architecture/container-docker-introduction/docker-defined.md)
* [Wingtip Tickets-SaaS-Anwendung](https://docs.microsoft.com/azure/sql-database/saas-tenancy-welcome-wingtip-tickets-app)

>[!div class="step-by-step"]
[Zurück](architecture-approaches.md)
[Weiter](serverless-architecture.md)