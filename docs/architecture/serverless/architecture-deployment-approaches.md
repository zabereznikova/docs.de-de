---
title: Architektur Bereitstellung Ansätze-Server Lose apps
description: Eine Anleitung für verschiedene Möglichkeiten, wie Unternehmens Architekturen in der Cloud bereitgestellt werden, mit dem Vergleich zwischen IaaS, Pas, Containern und Server losen.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: c745a4eb1c6f4a00bf139100b02f31cf3327d01e
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2019
ms.locfileid: "72522727"
---
# <a name="architecture-deployment-approaches"></a>Ansätze der Architekturbereitstellung

Unabhängig vom Architekturansatz, der zum Entwerfen einer Geschäftsanwendung verwendet wird, kann die Implementierung oder Bereitstellung dieser Anwendungen variieren. Unternehmen hosten Anwendungen auf allem von physischer Hardware bis Server lose Funktionen.

## <a name="n-tier-applications"></a>N-Tier-Anwendungen

Das [N-schichtige Architekturmuster](https://docs.microsoft.com/azure/architecture/guide/architecture-styles/n-tier) ist eine ausgereifte Architektur und bezieht sich einfach auf Anwendungen, die verschiedene logische Ebenen in separate physische Ebenen aufteilen. Die n-Tier-Architektur ist eine physische Implementierung der n-Ebenen-Architektur. Die häufigste Implementierung dieser Architektur umfasst Folgendes:

- Eine Präsentationsebene, z. b. eine Web-App.
- Eine API-oder Datenzugriffs Ebene, z. b. eine Rest-API.
- Eine Datenebene, z. b. eine SQL-Datenbank.

![N-Tier-Architektur](./media/n-tier-architecture.png)

N-Tier-Lösungen weisen die folgenden Eigenschaften auf:

- Projekte werden in der Regel an Ebenen ausgerichtet.
- Tests können je nach Ebene unterschiedlich durchgeführt werden.
- Ebenen stellen Abstraktions Ebenen bereit, z. b. ist die Präsentationsebene in der Regel nicht von den Implementierungsdetails der Datenebene ignoriert.
- In der Regel interagieren Ebenen nur mit angrenzenden Ebenen.
- Releases werden häufig im Projekt und daher auf Ebene und Ebene verwaltet. Eine einfache API-Änderung erfordert möglicherweise eine neue Version einer vollständigen mittleren Ebene.

Dieser Ansatz bietet mehrere Vorteile:

- Isolation der Datenbank (oftmals hat das Front-End keinen direkten Zugriff auf das Back-End der Datenbank).
- Die Wiederverwendung der API (z. b. Mobile, Desktop-und Web-App-Clients) kann dieselben APIs wieder verwenden.
- Möglichkeit zum horizontalen hochskalieren von Ebenen.
- Refactoringisolation: eine Ebene kann umgestaltet werden, ohne dass sich dies auf andere Ebenen auswirkt.

## <a name="on-premises-and-infrastructure-as-a-service-iaas"></a>Lokale und Infrastructure-as-a-Service (IaaS)

Der herkömmliche Ansatz für das Hosting von Anwendungen erfordert den Kauf von Hardware und die Verwaltung aller Softwareinstallationen, einschließlich des Betriebssystems. Ursprünglich waren diese intensive Rechenzentren und physische Hardware beteiligt. Zu den Herausforderungen, die bei der Betriebs physischen Hardware entstehen, zählen u. a.:

- Die Notwendigkeit, für "nur in Groß-/Kleinschreibung" oder Szenarien mit Spitzenbedarf mehr zu kaufen.
- Sichern des physischen Zugriffs auf die Hardware.
- Verantwortung für Hardwarefehler (z. b. Datenträger Fehler).
- Abzu.
- Konfigurieren von Routern und Lasten Ausgleichs Modulen.
- Strom Redundanz.
- Sichern des Software Zugriffs

![IaaS-Ansatz](./media/iaas-approach.png)

Virtualisierung von Hardware über "virtuelle Computer" ermöglicht Infrastructure-as-a-Service (IaaS). Host Computer werden effektiv partitioniert, um Ressourcen für Instanzen bereitzustellen, die überbelegungen für Ihren eigenen Arbeitsspeicher, CPU und Speicher verfügen. Das Team stellt die erforderlichen VMS bereit und konfiguriert die zugeordneten Netzwerke und den Zugriff auf den Speicher.

Weitere Informationen finden Sie unter [Architektur der N-Ebenen-Referenz für virtuelle Computer](https://docs.microsoft.com/azure/architecture/reference-architectures/virtual-machines-windows/n-tier).

Obwohl die Virtualisierung und IaaS (Infrastructure-as-a-Service) viele Anliegen betreffen, bleibt die Verantwortung des Infrastruktur Teams weiterhin beträchtlich. Das Team verwaltet Betriebssystemversionen, wendet Sicherheitspatches an und installiert Abhängigkeiten von Drittanbietern auf den Ziel Computern. Apps Verhalten sich im Vergleich zur Testumgebung häufig auf Produktions Computern anders. Probleme treten aufgrund von unterschiedlichen Abhängigkeits Versionen und/oder Betriebssystem-SKU-Ebenen auf. Obwohl viele Organisationen N-Tier-Anwendungen für diese Ziele bereitstellen, profitieren viele Unternehmen von der Bereitstellung in einem nativen cloudbasierten Modell wie [Platform-as-a-Service](#platform-as-a-service-paas). Architekturen mit microservices sind aufgrund der Anforderungen zum horizontalen hochskalieren von Elastizität und Resilienz schwieriger.

Weitere Informationen finden Sie unter [Virtual Machines](https://docs.microsoft.com/azure/virtual-machines/).

## <a name="platform-as-a-service-paas"></a>Platform-as-a-Service (PAS)

Platform-as-a-Service (PAS) bietet konfigurierte Lösungen, die Entwickler direkt einbinden können. "Pas" ist ein weiterer Begriff für das verwaltete Hosting. Es entfällt, dass Sie das Basis Betriebssystem, Sicherheitspatches und in vielen Fällen alle Abhängigkeiten von Drittanbietern verwalten müssen. Beispiele für Plattformen sind Webanwendungen, Datenbanken und Mobile Back-Ends.

In der Vergangenheit werden die Herausforderungen von IaaS behandelt. Mit dem Entwickler können sich Entwickler auf den Code oder das Datenbankschema konzentrieren, anstatt darauf zu achten, wie er bereitgestellt wird. Zu den Vorteilen von "Pas" gehören:

- Zahlen Sie für Nutzungsmodelle, die den mehr Aufwand bei der Investition in Computer im Leerlauf vermeiden.
- Direkte Bereitstellung und verbesserte devops-, Continuous Integration-(CI) und Continuous Delivery (CD)-Pipelines.
- Automatische Upgrades, Updates und Sicherheitspatches.
- Horizontale Skalierung und zentrales hochskalieren (elastische Skalierung).

Der Hauptnachteil von einsteigen ist, dass sich die Hersteller Sperre bisher in der Vergangenheit befand. Beispielsweise unterstützen einige Anbieter von Anbieter nur ASP.net, Node. js oder andere spezifische Sprachen und Plattformen. Produkte wie Azure App Service haben sich für mehrere Plattformen entwickelt und unterstützen eine Vielzahl von Sprachen und Frameworks zum Hosting von Web-Apps.

![Platform as a Service-Architektur](./media/paas-architecture.png)

## <a name="software-as-a-service-saas"></a>Software-as-a-Service (SaaS)

Software-as-a-Service oder SaaS ist zentral gehostet und ohne lokale Installation oder Bereitstellung verfügbar. SaaS wird häufig als Plattform für die Bereitstellung von Software als Plattform für die Bereitstellung von Software eingesetzt. Saas bietet Dienste zum Ausführen von und Herstellen einer Verbindung mit vorhandener Software. SaaS ist oft branchenspezifisch und vertikal. SaaS ist oft lizenziert und stellt in der Regel ein Client/Server-Modell bereit. Die meisten modernen SaaS-Angebote verwenden webbasierte Apps für den Client. Unternehmen ziehen Saas in der Regel als Geschäftslösung für Lizenzangebote in Erwägung. Es ist nicht oft als Architektur für die Skalierbarkeit und Verwaltbarkeit einer Anwendung implementiert. Tatsächlich basieren die meisten SaaS-Lösungen auf IaaS-, Pas-und/oder Server losen Back-Ends.

Weitere Informationen zu SaaS finden Sie in einer [Beispielanwendung](https://docs.microsoft.com/azure/sql-database/saas-tenancy-welcome-wingtip-tickets-app).

## <a name="containers-and-functions-as-a-service-faas"></a>Container und functions-as-a-Service (Faas)

Container sind eine interessante Lösung, die die Vorteile von Vorteilen ohne IaaS ermöglicht. Bei einem Container handelt es sich im Wesentlichen um eine Laufzeit, die die notwendigen Grundlagen für die Durchführung einer eindeutigen Anwendung enthält Der Kernel-oder Kernteil des Host Betriebssystems und die Dienste, wie z. b. Speicher, werden auf einem Host freigegeben. Der freigegebene Kernel ermöglicht das einfache Verwenden von Containern (einige sind nur wenige Megabyte groß, verglichen mit der Größe von Gigabyte von typischen virtuellen Computern). Wenn Hosts bereits ausgeführt werden, können Container schnell gestartet werden, um Hochverfügbarkeit zu ermöglichen. Die Möglichkeit zum schnellen Einrichten von Containern bietet auch zusätzliche Ebenen der Resilienz. Docker ist eine der gängigeren Implementierungen von Containern.

Zu den Vorteilen von Containern gehören:

- Einfach und portabel
- In sich selbst enthaltene Abhängigkeiten müssen nicht installiert werden.
- Stellen Sie unabhängig vom Host eine konsistente Umgebung bereit (wird auf einem Laptop genauso wie auf einem cloudserver ausgeführt)
- Kann für horizontales Skalieren schnell bereitgestellt werden
- Kann schnell neu gestartet werden, um nach einem Fehler wiederherzustellen

Ein Container wird auf einem Container Host ausgeführt (der wiederum auf einem Bare-Metal-Computer oder einem virtuellen Computer ausgeführt werden kann). Mehrere Container oder Instanzen desselben Containers können auf einem einzelnen Host ausgeführt werden. Für ein echtes Failover und Resilienz müssen Container zwischen den Hosts skaliert werden.

Weitere Informationen zu docker-Containern finden Sie unter [Was ist docker](../microservices/container-docker-introduction/docker-defined.md)?.

Das Verwalten von Containern auf allen Hosts erfordert in der Regel ein Orchestrierungs Tool wie Kubernetes. Das Konfigurieren und Verwalten von Orchestrierungs Lösungen kann zu weiteren mehr Aufwand und Komplexität von Projekten führen. Glücklicherweise bieten viele cloudanbieter Orchestrierungs Dienste mithilfe von "Pas"-Lösungen, um die Verwaltung von Containern zu vereinfachen.

In der folgenden Abbildung wird ein Beispiel für eine Kubernetes-Installation veranschaulicht. Knoten in der Installations Adresse Scale Out und Failover. Sie führen docker-Container Instanzen aus, die vom Master Server verwaltet werden. Das *kubelet* ist der Client, der Befehle von Kubernetes an docker überträgt.

![Kubernetes](./media/kubernetes-example.png)

Weitere Informationen zur Orchestrierung finden Sie unter [Kubernetes in Azure](https://docs.microsoft.com/azure/aks/intro-kubernetes).

Functions-as-a-Service (Faas) ist ein spezieller Containerdienst, der Server lose ähnelt. Eine spezielle Implementierung von Faas, die als [openfaas](https://github.com/openfaas/faas)bezeichnet wird, liegt auf Containern, um Server lose Funktionen zu bieten. Openfaas stellt Vorlagen bereit, mit denen alle Container Abhängigkeiten, die zum Ausführen eines Code Abschnitts erforderlich sind, verpacken. Die Verwendung von Vorlagen vereinfacht den Prozess der Bereitstellung von Code als Funktionseinheit. Openfaas ist für Architekturen vorgesehen, die bereits Container und orchestratoren enthalten, da die vorhandene Infrastruktur verwendet werden kann. Obwohl es Server lose Funktionen bietet, erfordert es speziell, dass Sie docker und einen Orchestrator verwenden.

## <a name="serverless"></a>Server lose

Eine Server lose Architektur bietet eine klare Trennung zwischen dem Code und der zugehörigen Hostingumgebung. Sie implementieren Code in einer *Funktion* , die von einem- *Triggern*aufgerufen wird. Nachdem diese Funktion beendet wurde, können alle benötigten Ressourcen freigegeben werden. Der-Vorgang ist möglicherweise manuell, ein Zeit gesteuerter Prozess, eine HTTP-Anforderung oder ein Datei Upload. Das Ergebnis des Auslösers ist die Ausführung von Code. Obwohl sich Server lose Plattformen unterscheiden, bieten die meisten Zugriff auf vordefinierte APIs und Bindungen, um Aufgaben wie das Schreiben in eine Datenbank oder die Warteschlangen Ergebnisse zu optimieren.

Serverless ist eine Architektur, die stark davon abhängig ist, die Host Umgebung zu abstrahieren, um sich auf den Code zu konzentrieren. Dies kann sich als *weniger Server*vorstellen.

Container Lösungen bieten Entwicklern vorhandene Buildskripts, mit denen Sie Code für Server lose Images veröffentlichen können. Bei anderen Implementierungen werden vorhandene-Projektmappen verwendet, um eine skalierbare Architektur bereitzustellen.

Die Abstraktion bedeutet, dass das devops-Team weder Server noch bestimmte Container bereitstellen oder verwalten muss. Die Server lose Plattform hostet Code, entweder als Skript oder ausführbare ausführbare Dateien, die mit einem zugehörigen SDK erstellt wurden, und ordnet die erforderlichen Ressourcen zum Skalieren des Codes zu.

In der folgenden Abbildung werden vier Server lose Komponenten dargestellt. Eine HTTP-Anforderung bewirkt, dass der Checkout-API-Code ausgeführt wird. Die Checkout-API fügt Code in eine Datenbank ein, und die Einfügung löst mehrere andere Funktionen aus, die ausgeführt werden, um Aufgaben wie das Berechnen von Aufgaben und das erfüllen der Reihenfolge auszuführen

![Server lose Implementierung](./media/serverless-implementation.png)

Zu den Vorteilen von Server losen gehören:

- **Hohe Dichte.** Viele Instanzen desselben Server losen Codes können im Vergleich zu Containern oder virtuellen Maschinen auf demselben Host ausgeführt werden. Die Instanzen Skalieren auf mehreren Hosts horizontal hoch-und Resilienz.
- **Mikro Abrechnung.** Die meisten Server losen Anbieter werden auf Basis von Server losen Ausführungen abgerechnet, sodass in bestimmten Szenarien massive Kosten eingespart werden können.
- **Sofortige Skalierung.** Serverless kann skaliert werden, um Arbeits Auslastungen automatisch und schnell abzugleichen.
- **Schnellere Markteinführungszeit.** Entwickler konzentrieren sich auf Code und stellen direkt auf der Server losen Plattform bereit. Komponenten können unabhängig voneinander freigegeben werden.

Server lose wird am häufigsten im Kontext von Compute erläutert, kann aber auch auf Daten angewendet werden. Beispielsweise stellen [Azure SQL](https://docs.microsoft.com/azure/sql-database) und [Cosmos DB](https://docs.microsoft.com/azure/cosmos-db) clouddatenbanken bereit, die keine Host Computer oder-Cluster konfigurieren müssen. Dieses Buch konzentriert sich auf Server lose Compute.

## <a name="summary"></a>Zusammenfassung

Es gibt ein breites Spektrum an verfügbaren Optionen für die Architektur, einschließlich eines Hybriden Ansatzes. Serverless vereinfacht den Ansatz, die Verwaltung und die Kosten von Anwendungs Features auf Kosten der Kontrolle und Portabilität. Viele Server lose Plattformen machen jedoch die Konfiguration verfügbar, um die Lösung zu optimieren. Gute Programmierverfahren können auch zu mehr portablen Code und weniger Server lose Platt Form Sperre führen. In der folgenden Tabelle werden die Architektur Ansätze nebeneinander veranschaulicht. Wählen Sie Server lose basierend auf Ihren Skalierungs Anforderungen, unabhängig davon, ob Sie die Laufzeit verwalten möchten, und wie gut Sie Ihre Workloads in kleine Komponenten unterteilen können. Im nächsten Kapitel erfahren Sie mehr über mögliche Herausforderungen bei Server losen und anderen Entscheidungspunkten.

|         |IaaS     |PaaS     |Container|Server lose|
|---------|---------|---------|---------|----------|
|**Scale** (Skalieren)|VM       |Instanz |App      |Funktion  |
|**Ert**|Hardware|Plattform|Betriebssystem Host|Laufzeit   |
|**ATS** |VM       |Projekt  |Bild    |Code      |
|**Lebensdauer**|Monate|Tage bis Monat|Minuten bis Tage|Millisekunden bis Minuten|
|**Dafür**|Anwendungen, Abhängigkeiten, Laufzeit und Betriebssystem|Anwendungen und Abhängigkeiten|Anwendungen, Abhängigkeiten und Laufzeit|Funktion

- **Skala** bezieht sich auf die Einheit, die zum Skalieren der Anwendung verwendet wird.
- **Abstracts** bezieht sich auf die Ebene, die von der Implementierung abstrahiert wird.
- **Unit** bezieht sich auf den Umfang der bereitgestellten Funktionen.
- Die **Lebensdauer** bezieht sich auf die typische Laufzeit einer bestimmten Instanz.
- **Verantwortlichkeit** bezieht sich auf den Aufwand zum Erstellen, bereitstellen und Verwalten der Anwendung.

Im nächsten Kapitel werden die Server lose Architektur, Anwendungsfälle und Entwurfsmuster im Mittelpunkt stehen.

## <a name="recommended-resources"></a>Empfohlene Ressourcen

- [Leitfaden zur Azure-Anwendungsarchitektur](https://docs.microsoft.com/azure/architecture/guide/)
- [Azure Cosmos DB](https://docs.microsoft.com/azure/cosmos-db)
- [Azure SQL](https://docs.microsoft.com/azure/sql-database)
- [N-Tier-Architekturmuster](https://docs.microsoft.com/azure/architecture/guide/architecture-styles/n-tier)
- [Kubernetes in Azure](https://docs.microsoft.com/azure/aks/intro-kubernetes)
- [Microservices](https://docs.microsoft.com/azure/architecture/guide/architecture-styles/microservices)
- [Architektur der N-Ebenen-Referenz für virtuelle Computer](https://docs.microsoft.com/azure/architecture/reference-architectures/virtual-machines-windows/n-tier)
- [Virtuelle Computer](https://docs.microsoft.com/azure/virtual-machines/)
- [What is Docker? (Was ist Docker?)](../microservices/container-docker-introduction/docker-defined.md)
- [Wingtip Tickets SaaS-Anwendung](https://docs.microsoft.com/azure/sql-database/saas-tenancy-welcome-wingtip-tickets-app)

>[!div class="step-by-step"]
>[Zurück](architecture-approaches.md)
>[Weiter](serverless-architecture.md)
