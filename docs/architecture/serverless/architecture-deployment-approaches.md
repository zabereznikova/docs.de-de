---
title: 'Ansätze der Architekturbereitstellung: Serverlose Apps'
description: Ein Leitfaden für verschiedene Arten, wie Unternehmensarchitekturen in der Cloud bereitgestellt werden, mit einem Vergleich zwischen IaaS, PaaS, Containern und serverlosen Bereitstellungen.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 7e91412600e8e4e5a0dca2a454f1cb0680c881b2
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91173340"
---
# <a name="architecture-deployment-approaches"></a>Ansätze der Architekturbereitstellung

Unabhängig vom Architekturansatz, der für den Entwurf einer Geschäftsanwendung verwendet wird, kann die Implementierung oder Bereitstellung dieser Anwendungen unterschiedlich sein. Unternehmen hosten Anwendungen auf vielfältige Weise, von physischer Hardware bis hin zu serverlosen Funktionen.

## <a name="n-tier-applications"></a>N-schichtige Anwendungen

Das [n-schichtige Architekturmuster](/azure/architecture/guide/architecture-styles/n-tier) ist eine ausgereifte Architektur und bezieht sich einfach auf Anwendungen, die verschiedene logische Schichten in separate physikalische Schichten trennen. Die n-schichtige Architektur ist eine physische Implementierung der N-Ebenen-Architektur. Die häufigste Implementierung dieser Architektur umfasst Folgendes:

- Eine Präsentationsschicht, z.B. eine Web-App.
- Eine API- oder Datenzugriffsschicht, z.B. eine Rest-API.
- Eine Datenschicht, z.B. eine SQL-Datenbank.

![N-schichtige Architektur](./media/n-tier-architecture.png)

N-schichtige Lösungen weisen die folgenden Merkmale auf:

- Projekte werden in der Regel an Schichten ausgerichtet.
- Tests können je nach Schicht unterschiedlich durchgeführt werden.
- Schichten stellen Abstraktionsebenen bereit, z.B. ist die Präsentationsschicht in der Regel nicht über die Implementierungsdetails der Datenschicht informiert.
- In der Regel interagieren Ebenen nur mit angrenzenden Ebenen.
- Releases werden häufig auf Projekt- und damit auf Schichtebene verwaltet. Eine einfache API-Änderung erfordert möglicherweise ein neues Release einer vollständigen mittleren Schicht.

Diese Vorgehensweise hat einige Vorteile, beispielsweise:

- Isolation der Datenbank (oftmals besitzt das Front-End keinen direkten Zugriff auf das Datenbank-Back-End).
- Wiederverwendung der API (Mobile-, Desktop- und Web-App-Clients können z.B. dieselben APIs wiederverwenden).
- Möglichkeit zum horizontalen Hochskalieren von Schichten.
- Refactoringisolation: Für eine Schicht kann ein Refactoring ausgeführt werden, ohne dass sich dies auf andere Schichten auswirkt.

## <a name="on-premises-and-infrastructure-as-a-service-iaas"></a>Lokale Umgebung und Infrastructure-as-a-Service (IaaS)

Der traditionelle Ansatz für das Hosting von Anwendungen erfordert den Kauf von Hardware und die Verwaltung aller Softwareinstallationen, einschließlich des Betriebssystems. Ursprünglich waren dafür teure Rechenzentren und physische Hardware erforderlich. Zu den Herausforderungen, die beim Betrieb physischen Hardware entstehen, zählen beispielsweise:

- Die Notwendigkeit, zusätzliche Ausstattung für „den Fall der Fälle“ oder Spitzenbedarfsszenarien zu kaufen.
- Sichern des physischen Zugriffs auf die Hardware.
- Verantwortung für Hardwarefehler (z.B. Datenträgerfehler).
- Kühlung.
- Konfigurieren von Routern und Lastenausgleich.
- Bereitstellen von Redundanz.
- Sichern des Zugriffs auf Software.

![IaaS-Ansatz](./media/iaas-approach.png)

Die Virtualisierung von Hardware über „virtuelle Computer“ ermöglicht Infrastructure-as-a-Service (IaaS). Hostcomputer werden effektiv partitioniert, um Ressourcen für Instanzen mit Zuteilungen für ihren eigenen Arbeitsspeicher, ihre CPU und ihren Speicher bereitzustellen. Das Team stellt die erforderlichen VMs bereit und konfiguriert die zugeordneten Netzwerke sowie den Zugriff auf Speicher.

Weitere Informationen finden Sie in der [N-schichtigen Referenzarchitektur für virtuelle Computer](/azure/architecture/reference-architectures/virtual-machines-windows/n-tier).

Obwohl Virtualisierung und Infrastructure-as-a-Service (IaaS) viele Probleme lösen, liegt immer noch viel Verantwortung in den Händen des Infrastrukturteams. Das Team verwaltet Betriebssystemversionen, wendet Sicherheitspatches an und installiert Abhängigkeiten von Drittanbietern auf den Zielcomputern. Apps verhalten sich im Vergleich zur Testumgebung auf Produktionscomputern häufig anders. Probleme treten aufgrund von unterschiedlichen Abhängigkeitsversionen und/oder Betriebssystem-SKU-Ebenen auf. Obwohl viele Organisationen n-schichtige Anwendungen für diese Ziele bereitstellen, profitieren viele Unternehmen von der Bereitstellung in einem cloudnativeren Modell, etwa [Platform-as-a-Service](#platform-as-a-service-paas). Architekturen mit Microservices stellen aufgrund der Anforderungen zum horizontalen Hochskalieren, um Elastizität und Resilienz zu erreichen, eine größere Herausforderung dar.

Weitere Informationen finden Sie unter [virtuelle Computer](/azure/virtual-machines/).

## <a name="platform-as-a-service-paas"></a>Platform-as-a-Service (PaaS)

Platform-as-a-Service (PAS) bietet konfigurierte Lösungen, die Entwickler direkt einbinden können. „PaaS“ ist ein anderer Begriff für verwaltetes Hosting. Damit erübrigt sich die Verwaltung des Basisbetriebssystems, der Sicherheitspatches und in vielen Fällen der Abhängigkeiten von Drittanbietern. Beispiele für Plattformen sind Webanwendungen, Datenbanken und mobile Back-Ends.

PaaS behandelt die Herausforderungen, die IaaS mit sich bringt. PaaS ermöglicht es dem Entwickler, sich auf den Code oder das Datenbankschema zu konzentrieren und nicht darauf, wie beides bereitgestellt wird. Zu den Vorteilen von PaaS gehören:

- Modelle mit nutzungsbasierter Bezahlung, die den Aufwand für Investitionen in ungenutzte Computer eliminieren.
- Direkte Bereitstellung und verbesserte DevOps-Funktionen, CI- (Continuous Integration) und CD-Pipelines (Continuous Delivery).
- Automatische Upgrades, Updates und Sicherheitspatches.
- Horizontale Skalierung und zentrales Hochskalieren (elastische Skalierung) auf Knopfdruck.

Der Hauptnachteil von PaaS liegt traditionell in der Herstellerbindung. Einige PaaS-Anbieter unterstützen beispielsweise nur ASP.NET, Node.js oder andere spezifische Sprachen und Plattformen. Produkte wie Azure App Service wurden weiterentwickelt, um mehrere Plattformen und eine Vielzahl von Sprachen und Frameworks für das Hosting von Web-Apps zu unterstützen.

![PaaS- Architektur (Platform-as-a-Service)](./media/paas-architecture.png)

## <a name="software-as-a-service-saas"></a>Software-as-a-Service (SaaS)

Software-as-a-Service oder SaaS wird zentral gehostet und ist ohne lokale Installation oder Bereitstellung verfügbar. SaaS wird häufig über PaaS als Plattform für die Bereitstellung von Software gehostet. Saas bietet Dienste zum Ausführen von und Herstellen einer Verbindung mit vorhandener Software. SaaS ist oft branchenspezifisch und spezialisiert. SaaS wird häufig lizenziert und stellt in der Regel ein Client-/Servermodell bereit. Die meisten modernen SaaS-Angebote verwenden webbasierte Apps für den Client. Unternehmen ziehen SaaS in der Regel als Geschäftslösung für Lizenzangebote in Betracht. SaaS wird nicht oft als Architekturüberlegung für die Skalierbarkeit und Verwaltbarkeit einer Anwendung implementiert. Tatsächlich basieren die meisten SaaS-Lösungen auf IaaS, PaaS und/oder serverlosen Back-Ends.

Erfahren Sie mehr über SaaS anhand einer [Beispielanwendung](/azure/sql-database/saas-tenancy-welcome-wingtip-tickets-app).

## <a name="containers-and-functions-as-a-service-faas"></a>Container und Functions-as-a-Service (FaaS)

Container sind eine interessante Lösung, die PaaS-ähnliche Vorteile ohne den Mehraufwand von IaaS ermöglicht. Ein Container ist im Wesentlichen eine Laufzeit, die die grundlegenden Elemente enthält, die zum Ausführen einer eindeutigen Anwendung erforderlich sind. Der Kernel- oder Kernteil des Hostbetriebssystems und der Dienste (etwa Speicher) werden auf einem Host gemeinsam verwendet. Der gemeinsame Kernel ermöglicht es, dass Container schlank sind (einige sind nur wenige MB groß, verglichen mit mehreren GB großen typischen virtuellen Computern). Wenn Hosts bereits ausgeführt werden, können Container schnell gestartet werden, um Hochverfügbarkeit zu ermöglichen. Die Möglichkeit zum schnellen Starten von Containern bietet auch zusätzliche Ebenen der Resilienz. Docker ist eine der gängigeren Implementierungen von Containern.

Zu den Vorteilen von Containern gehören die folgenden Merkmale:

- Schlank und portabel
- Eigenständig, sodass keine Abhängigkeiten installiert werden müssen
- Bereitstellen einer konsistenten Umgebung unabhängig vom Host (Ausführung auf einem Laptop identisch mit Ausführung auf einem Cloudserver)
- Kann für horizontale Skalierung schnell bereitgestellt werden
- Kann schnell neu gestartet werden, um die Wiederherstellung nach einem Fehler durchzuführen

Ein Container wird auf einem Containerhost ausgeführt (der wiederum auf einem Bare-Metal-Computer oder einem virtuellen Computer ausgeführt werden kann). Mehrere Container oder Instanzen desselben Containers können auf einem einzelnen Host ausgeführt werden. Für ein echtes Failover und Resilienz müssen Container hostübergreifend skaliert werden.

Weitere Informationen zu Docker-Containern finden Sie unter [Was ist Docker?](../microservices/container-docker-introduction/docker-defined.md)

Das hostübergreifende Verwalten von Containern erfordert in der Regel ein Orchestrierungstool wie Kubernetes. Das Konfigurieren und Verwalten von Orchestrierungslösungen kann zu weiterem Mehraufwand und größerer Komplexität von Projekten führen. Glücklicherweise bieten viele Cloudanbieter Orchestrierungsdienste über PaaS-Lösungen an, um die Verwaltung von Containern zu vereinfachen.

Die folgende Abbildung zeigt eine Kubernetes-Beispielinstallation. Knoten in der Installation sind für horizontales Hochskalieren und Failover zuständig. Sie führen Docker-Containerinstanzen aus, die vom Masterserver verwaltet werden. *kubelet* ist der Client, der Befehle von Kubernetes an Docker überträgt.

![Kubernetes](./media/kubernetes-example.png)

Weitere Informationen zur Orchestrierung finden Sie unter [Kubernetes in Azure](/azure/aks/intro-kubernetes).

Functions-as-a-Service (FaaS) ist ein spezieller Containerdienst, der einer serverlosen Lösung ähnelt. Eine spezielle Implementierung von FaaS, die als [OpenFaaS](https://github.com/openfaas/faas) bezeichnet wird, wird über Containern implementiert, um serverlose Funktionen bereitzustellen. OpenFaaS stellt Vorlagen zur Verfügung, die alle Containerabhängigkeiten enthalten, die für die Ausführung eines Codeabschnitts erforderlich sind. Die Verwendung von Vorlagen vereinfacht den Vorgang der Bereitstellung von Code als Funktionseinheit. OpenFaaS ist für Architekturen vorgesehen, die bereits Container und Orchestratoren enthalten, da die vorhandene Infrastruktur verwendet werden kann. Obwohl FaaS serverlose Funktionen bietet, ist es erforderlich, dass Sie Docker und einen Orchestrator verwenden.

## <a name="serverless"></a>Serverlos

Eine serverlose Architektur bietet eine klare Trennung zwischen dem Code und der zugehörigen Hostingumgebung. Sie implementieren Code in einer *Funktion*, die von einem *Trigger* aufgerufen wird. Nachdem diese Funktion beendet wurde, können alle von der Funktion benötigten Ressourcen freigegeben werden. Der Trigger kann manuell, ein zeitgesteuerter Prozess, eine HTTP-Anforderung oder ein Dateiupload sein. Das Ergebnis des Triggers ist die Ausführung von Code. Obwohl sich serverlose Plattformen unterscheiden, bieten die meisten Zugriff auf vordefinierte APIs und Bindungen, um Aufgaben wie das Schreiben in eine Datenbank oder das Einreihen von Ergebnissen in Warteschlangen zu optimieren.

„Serverlos“ ist eine Architektur, die stark davon abhängig ist, die Hostumgebung zu abstrahieren, um sich auf den Code zu konzentrieren. Sie kann als *weniger Server* angesehen werden.

Containerlösungen bieten Entwicklern vorhandene Buildskripts, mit denen sie Code für serverlos-bereite Images veröffentlichen können. Bei anderen Implementierungen werden vorhandene PaaS-Lösungen verwendet, um eine skalierbare Architektur bereitzustellen.

Die Abstraktion bedeutet, dass das DevOps-Team weder Server noch bestimmte Container bereitstellen oder verwalten muss. Die serverlose Plattform hostet Code, entweder als Skript oder als gepackte ausführbare Dateien, die mit einem zugehörigen SDK erstellt wurden, und weist die erforderlichen Ressourcen zum Skalieren des Codes zu.

In der folgenden Abbildung werden vier serverlose Komponenten dargestellt. Eine HTTP-Anforderung bewirkt, dass der Check-Out-API-Code ausgeführt wird. Die Check-Out-API fügt Code in eine Datenbank ein, und diese Einfügung löst die Ausführung mehrerer anderer Funktionen aus, um Aufgaben wie das Berechnen von Tasks und das Erfüllen des Auftrags auszuführen.

![Serverlose Implementierung](./media/serverless-implementation.png)

Zu den Vorteilen von serverloser Implementierung gehören:

- **Hohe Dichte.** Viele Instanzen desselben serverlosen Codes können im Vergleich zu Containern oder virtuellen Computern auf demselben Host ausgeführt werden. Die Instanzen werden über mehrere Hosts hinweg skaliert, und es werden horizontale Hochskalierung und Resilienz bereitgestellt.
- **Microabrechnung.** Die meisten serverlosen Anbieter rechnen auf der Basis von serverlosen Ausführungen ab, sodass in bestimmten Szenarien massiv Kosten eingespart werden können.
- **Sofortige Skalierung.** Serverlose Implementierungen können skaliert werden, um Arbeitsauslastungen automatisch und schnell zu berücksichtigen.
- **Kürzere Zeit bis zur Markreife.** Entwickler konzentrieren sich auf Code und führen die Bereitstellung direkt auf der serverlosen Plattform aus. Komponenten können unabhängig voneinander freigegeben werden.

Serverlose Implementierungen kommen am häufigsten im Kontext von Compute vor, können aber auch auf Daten angewendet werden. Beispielsweise stellen [Azure SQL](/azure/sql-database) und [Cosmos DB](/azure/cosmos-db) Clouddatenbanken bereit, die keine Konfiguration von Hostcomputern oder Clustern erfordern. Dieser Leitfaden konzentriert sich auf serverloses Compute.

## <a name="summary"></a>Zusammenfassung

Für die Architektur steht ein breites Spektrum an Auswahlmöglichkeiten zur Verfügung, darunter ein Hybridansatz. Serverlose Implementierungen vereinfacht den Ansatz, die Verwaltung und die Kosten der Anwendungsfeatures auf Kosten der Kontrolle und Portabilität. Viele serverlose Plattformen stellen jedoch Konfigurationsmöglichkeiten zur Verfügung, um die Lösung zu optimieren. Gute Programmierpraktiken können ebenfalls zu portablerem Code und weniger Bindung an die serverlose Plattform führen. In der folgenden Tabelle werden die Architekturansätze nebeneinander veranschaulicht. Wählen Sie die serverlose Implementierung basierend auf Ihren Skalierungsanforderungen aus, und machen Sie Ihre Entscheidung davon abhängig, ob Sie die Laufzeit verwalten möchten und wie gut Sie Ihre Workloads in kleine Komponenten aufteilen können. Im nächsten Kapitel erfahren Sie mehr über mögliche Herausforderungen bei serverlosen Implementierungen und anderen Entscheidungspunkten.

|         |IaaS     |PaaS     |Container|Serverlos|
|---------|---------|---------|---------|----------|
|**Scale** (Skalieren)|VM       |Instanz |App      |Funktion  |
|**Abstraktion**|Hardware|Plattform|Betriebssystemhost|Laufzeit   |
|**Einheit** |VM       |Projekt  |Bild    |Code      |
|**Lebensdauer**|Monate|Tage bis Monate|Minuten bis Tage|Millisekunden bis Minuten|
|**Verantwortlichkeit**|Anwendungen, Abhängigkeiten, Laufzeit und Betriebssystem|Anwendungen und Abhängigkeiten|Anwendungen, Abhängigkeiten und Laufzeit|Funktion

- **Skalierung** bezieht sich auf die Einheit, die zum Skalieren der Anwendung verwendet wird.
- **Abstraktion** bezieht sich auf die Ebene, die von der Implementierung abstrahiert wird.
- **Einheit** bezieht sich auf den Umfang der Bereitstellung.
- **Lebensdauer** bezieht sich auf die typische Laufzeit einer bestimmten Instanz.
- **Verantwortlichkeit** bezieht sich auf den Mehraufwand zum Erstellen, Bereitstellen und Verwalten der Anwendung.

Im nächsten Kapitel werden serverlose Architektur, Anwendungsfälle und Entwurfsmuster im Mittelpunkt stehen.

## <a name="recommended-resources"></a>Empfohlene Ressourcen

- [Azure-Anwendungsarchitekturleitfaden](/azure/architecture/guide/)
- [Azure Cosmos DB](/azure/cosmos-db)
- [Azure SQL](/azure/sql-database)
- [Architekturmuster n-schichtiger Anwendungen](/azure/architecture/guide/architecture-styles/n-tier)
- [Kubernetes in Azure](/azure/aks/intro-kubernetes)
- [Microservices](/azure/architecture/guide/architecture-styles/microservices)
- [N-schichtigen Referenzarchitektur für virtuelle Computer](/azure/architecture/reference-architectures/virtual-machines-windows/n-tier)
- [Virtuelle Computer](/azure/virtual-machines/)
- [What is Docker? (Was ist Docker?)](../microservices/container-docker-introduction/docker-defined.md)
- [SaaS-Anwendung Wingtip Tickets](/azure/sql-database/saas-tenancy-welcome-wingtip-tickets-app)

>[!div class="step-by-step"]
>[Zurück](architecture-approaches.md)
>[Weiter](serverless-architecture.md)
