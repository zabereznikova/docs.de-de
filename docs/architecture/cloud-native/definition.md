---
title: Definition von cloudbasiert
description: Erfahren Sie mehr über die Grundpfeiler, die das Fundament für Cloud-native Systeme bilden
author: robvet
ms.date: 08/20/2019
ms.openlocfilehash: 756a2565bd77fcef19a5f15579987836ff0e75a4
ms.sourcegitcommit: e3cbf26d67f7e9286c7108a2752804050762d02d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2020
ms.locfileid: "80989089"
---
# <a name="defining-cloud-native"></a>Definieren der Cloud nativ

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Stoppen Sie, was Sie tun, und schreiben Sie zehn Ihrer Kollegen. Bitten Sie sie, den Begriff "Cloud Native" zu definieren. Gute Chance, dass Sie acht verschiedene Antworten erhalten.

Bei Cloud Native geht es darum, die Art und Weise zu ändern, wie wir über die Entwicklung kritischer Geschäftssysteme nachdenken.

Cloud-native Systeme wurden entwickelt, um schnelle Veränderungen, große Mengen und Widerstandsfähigkeit zu nutzen.

Die Cloud Native Computing Foundation bietet eine [offizielle Definition:](https://github.com/cncf/foundation/blob/master/charter.md)

> *Cloud-native Technologien ermöglichen es Unternehmen, skalierbare Anwendungen in modernen, dynamischen Umgebungen wie öffentlichen, privaten und hybriden Clouds zu erstellen und auszuführen. Container, Dienstnetze, Microservices, unveränderliche Infrastruktur und deklarative APIs veranschaulichen diesen Ansatz.*

> *Diese Techniken ermöglichen lose gekoppelte Systeme, die belastbar, überschaubar und beobachtbar sind. In Kombination mit robuster Automatisierung ermöglichen sie es Ingenieuren, häufig und vorhersehbar mit minimaler Arbeit stark wirkende Änderungen vorzunehmen.*

Anwendungen werden immer komplexer, und die Benutzer fordern immer mehr. Benutzer erwarten schnelle Reaktionsfähigkeit, innovative Funktionen und keine Ausfallzeiten. Leistungsprobleme, wiederkehrende Fehler und die Unfähigkeit, sich schnell zu bewegen, sind nicht länger akzeptabel. Sie werden leicht zu Ihrem Konkurrenten bewegen.

Cloud native ist viel über *Geschwindigkeit* und *Agilität*. Geschäftssysteme entwickeln sich von der Ermöglichung von Geschäftsfähigkeiten zu Waffen strategischer Transformation, die geschäftsgeschwindigkeit und Wachstum beschleunigen. Es ist unerlässlich, Ideen sofort auf den Markt zu bringen.

Hier sind einige Unternehmen, die diese Techniken implementiert haben. Denken Sie an die Geschwindigkeit, Agilität und Skalierbarkeit, die sie erreicht haben.

| Company | Benutzererfahrung |
| :-------- | :-------- |
| [Netflix](https://www.infoq.com/news/2013/06/netflix/) | Hat mehr als 600 Dienstleistungen in der Produktion. Stellt hundertmal pro Tag bereit. |
| [Uber](https://eng.uber.com/micro-deploy/) | Hat mehr als 1.000 Dienstleistungen in der Produktion gespeichert. Stellt mehrere tausend Builds pro Woche bereit. |
| [WeChat](https://www.cs.columbia.edu/~ruigu/papers/socc18-final100.pdf) | Hat mehr als 300 Dienstleistungen in der Produktion. Macht fast 1.000 Änderungen pro Tag. |

Wie Sie sehen können, zeigen Netflix, Uber und WeChat Systeme, die aus Hunderten von unabhängigen Microservices bestehen. Dieser architektonische Stil ermöglicht es ihnen, schnell auf die Marktbedingungen zu reagieren. Sie können kleine Bereiche einer live, komplexen Anwendung sofort aktualisieren und diese Bereiche nach Bedarf individuell skalieren.

Die Geschwindigkeit und Agilität von Cloud Native ist auf eine Reihe von Faktoren zurückzuführen. An erster Stelle steht die Cloud-Infrastruktur. Fünf weitere Grundpfeiler, die in Abbildung 1-3 dargestellt sind, bilden auch das Fundament für Cloud-native Systeme.

![Cloud-native Grundsäulen](./media/cloud-native-foundational-pillars.png)

**Abbildung 1-3**. Cloud-native Grundsäulen

Nehmen wir uns etwas Zeit, um die Bedeutung der einzelnen Pfeiler besser zu verstehen.

## <a name="the-cloud"></a>Die Wolke...

Cloud-native Systeme nutzen das Cloud-Service-Modell voll aus.

Diese Systeme wurden entwickelt, um in einer dynamischen, virtualisierten Cloud-Umgebung zu gedeihen, und nutzen [die Platform as a Service (PaaS)-Computeinfrastruktur](https://azure.microsoft.com/overview/what-is-paas/) und Managed Services umfassend. Sie behandeln die zugrunde liegende Infrastruktur als *Einweg* - in Wenigen Minuten bereitgestellt und in der Größe angepasst, skaliert, bewegt oder bei Bedarf zerstört - über Automatisierung.

Betrachten Sie das weithin akzeptierte DevOps-Konzept von [Pets vs. Cattle](https://medium.com/@Joachim8675309/devops-concepts-pets-vs-cattle-2380b5aab313). In einem herkömmlichen Rechenzentrum werden Server wie *Haustiere*behandelt: eine physische Maschine, die einen aussagekräftigen Namen erhält und gepflegt wird. Sie skalieren, indem Sie dem gleichen Computer weitere Ressourcen hinzufügen (skalieren). Wenn der Server krank wird, pflegen Sie ihn wieder gesund. Sollte der Server nicht mehr verfügbar sein, merkt es jeder.

Das *Rinderservicemodell* ist anders. Sie stellen jede Instanz als virtuelle Maschine oder Container zur Verfügung. Sie sind identisch und haben eine Systemkennung wie Service-01, Service-02 usw. zugewiesen. Sie skalieren, indem Sie mehr davon erstellen (horizontal ausskalieren). Wenn man nicht mehr verfügbar ist, merkt es niemand.

Das Rindermodell umfasst *eine unveränderliche Infrastruktur.* Server werden nicht repariert oder geändert. Wenn einer ausfällt oder aktualisiert werden muss, wird es zerstört und ein neues bereitgestellt – alles über Automatisierung.

Cloud-native Systeme umfassen das Cattle-Servicemodell. Sie laufen weiterhin, wenn die Infrastruktur ohne Rücksicht auf die Maschinen, auf denen sie ausgeführt werden, skaliert wird.

Die Azure Cloud-Plattform unterstützt diese Art hochelastischer Infrastruktur mit automatischen Skalierungs-, Selbstheilungs- und Überwachungsfunktionen.

## <a name="modern-design"></a>Modernes Design

Wie würden Sie eine Cloud-native App entwerfen? Wie würde Ihre Architektur aussehen? An welche Grundsätze, Muster und Best Practices würden Sie sich halten? Welche Infrastruktur- und Betriebsbedenken wären wichtig?

### <a name="the-twelve-factor-application"></a>Die Zwölf-Faktor-Anwendung

Eine weithin akzeptierte Methode zum Erstellen cloudbasierter Anwendungen ist die [Zwölf-Faktor-Anwendung](https://12factor.net/). Es beschreibt eine Reihe von Prinzipien und Vorgehensweisen, die Entwickler befolgen, um Anwendungen zu erstellen, die für moderne Cloud-Umgebungen optimiert sind. Besonderes Augenmerk wird auf die Portabilität über Umgebungen und deklarative Automatisierung.

Obwohl sie für jede webbasierte Anwendung anwendbar ist, betrachten viele Praktiker sie als solide Grundlage für die Erstellung cloud-nativer Apps. Systeme, die auf diesen Prinzipien aufbauen, können schnell bereitgestellt und skaliert werden und Funktionen hinzufügen, um schnell auf Marktänderungen reagieren zu können.

Die folgende Tabelle hebt die Zwölf-Faktor-Methodik hervor:

|    |  Faktor | Erklärung  |
| :-------- | :-------- | :-------- |
| 1 | Codebasis | Eine einzige Codebasis für jeden Microservice, die in einem eigenen Repository gespeichert ist. Nachverfolgt mit Versionskontrolle kann es in mehreren Umgebungen (QA, Staging, Production) bereitgestellt werden. |
| 2 | Abhängigkeiten | Jeder Microservice isoliert und verpackt seine eigenen Abhängigkeiten, wobei Änderungen berücksichtigt werden, ohne das gesamte System zu beeinträchtigen. |
| 3 | Configurations  | Konfigurationsinformationen werden aus dem Microservice verschoben und über ein Konfigurationsverwaltungstool außerhalb des Codes externisiert. Dieselbe Bereitstellung kann sich über Umgebungen hinweg ausbreiten, wobei die richtige Konfiguration angewendet wird.  |
| 4 | Backing Services | Zusätzliche Ressourcen (Datenspeicher, Caches, Nachrichtenbroker) sollten über eine adressierbare URL verfügbar gemacht werden. Dadurch wird die Ressource von der Anwendung entkoppelt, sodass sie austauschbar ist.  |
| 5 | Erstellen, Freigeben, Ausführen | Jede Version muss eine strikte Trennung über die Build-, Release- und Ausführungsphasen erzwingen. Jeder sollte mit einer eindeutigen ID markiert werden und die Möglichkeit zum Rollback unterstützen. Moderne CI/CD-Systeme helfen dabei, dieses Prinzip zu erfüllen. |
| 6 | Prozesse | Jeder Microservice sollte in seinem eigenen Prozess ausgeführt werden, isoliert von anderen ausgeführten Diensten. Externalisieren Des erforderlichen Status für einen Sicherungsdienst, z. B. einen verteilten Cache oder Datenspeicher. |
| 7 | Portbindung | Jeder Microservice sollte mit seinen Schnittstellen und Funktionen, die auf einem eigenen Port verfügbar gemacht werden, in sich geschlossen sein. Dies ermöglicht die Isolierung von anderen Microservices. |
| 8 | Parallelität | Die Dienste werden über eine große Anzahl kleiner identischer Prozesse (Kopien) skaliert, anstatt eine einzelne große Instanz auf dem leistungsstärksten verfügbaren Computer zu skalieren. |
| 9 | Verfügbarkeit | Dienstinstanzen sollten verfügbar sein, schnelle Startmöglichkeiten bevorzugen, um Skalierbarkeitsmöglichkeiten zu erhöhen, und ordnungsgemäße Herunterfahren, um das System in einem korrekten Zustand zu belassen. Docker-Container zusammen mit einem Orchestrator erfüllen diese Anforderung inhärent. |
| 10 | Dev/Prod Parität | Halten Sie Umgebungen über den gesamten Anwendungslebenszyklus hinweg so ähnlich wie möglich, um kostspielige Verknüpfungen zu vermeiden. Hier kann die Einführung von Containern durch die Förderung der gleichen Ausführungsumgebung einen großen Beitrag leisten. |
| 11 | Protokollierung | Behandeln Sie Protokolle, die von Microservices generiert werden, als Ereignisstreams. Verarbeiten Sie sie mit einem Ereignisaggregator, und übertragen Sie die Daten an Data-Mining-/Log-Verwaltungstools wie Azure Monitor oder Splunk und schließlich an langfristige Archivierung. |
| 12 | Admin-Prozesse | Führen Sie Verwaltungs-/Verwaltungsaufgaben als einmalige Prozesse aus. Zu den Aufgaben können die Datenbereinigung und das Abrufen von Analysen für einen Bericht gehören. Tools, die diese Aufgaben ausführen, sollten aus der Produktionsumgebung aufgerufen werden, jedoch getrennt von der Anwendung. |

In dem Buch [Beyond the Twelve-Factor App](https://content.pivotal.io/blog/beyond-the-twelve-factor-app)beschreibt Autor Kevin Hoffman jeden der ursprünglichen 12 Faktoren (geschrieben 2011). Darüber hinaus bietet das Buch drei weitere Faktoren, die das moderne Cloud-Anwendungsdesign von heute widerspiegeln.

|    |  Neuer Faktor | Erklärung  |
| :-------- | :-------- | :-------- |
| 13 | API First | Machen Sie alles zu einem Service. Angenommen, Ihr Code wird von einem Front-End-Client, Gateway oder einem anderen Dienst verwendet. |
| 14 | Telemetrie | Auf einer Arbeitsstation haben Sie einen tiefen Einblick in Ihre Anwendung und ihr Verhalten. In der Cloud nicht. Stellen Sie sicher, dass Ihr Entwurf die Sammlung von Überwachungs-, domänenspezifischen und Integritäts-/Systemdaten umfasst. |
| 15 | Authentifizierung/Autorisierung  | Implementieren Sie die Identität von Anfang an. Betrachten Sie [RBAC-Funktionen (role-based Access Control),](https://docs.microsoft.com/azure/role-based-access-control/overview) die in öffentlichen Clouds verfügbar sind.  |

Wir werden auf viele der 12+ Faktoren in diesem Kapitel und im gesamten Buch verweisen.

### <a name="critical-design-considerations"></a>Kritische Entwurfsüberlegungen

Abgesehen von den Anleitungen aus der Zwölf-Faktor-Methodik gibt es mehrere wichtige Entwurfsentscheidungen, die Sie beim Erstellen verteilter Systeme treffen müssen.

*Kommunikation*

Wie kommunizieren Front-End-Clientanwendungen mit Unterstützten Kerndiensten? Werden Sie eine direkte Kommunikation zulassen? Oder können Sie die Back-End-Dienste mit einer Gateway-Fassade abstrahieren, die Flexibilität, Kontrolle und Sicherheit bietet?

Wie kommunizieren Back-End-Kerndienste miteinander? Werden Sie direkte HTTP-Aufrufe zulassen, die zu Kopplung und Auswirkungen auf Leistung und Agilität führen? Oder sollten Sie die Entkoppere von Messaging mit Warteschlangen- und Thementechnologien in Betracht ziehen?

Die Kommunikation wird ausführlich behandelt Kapitel 4, *Cloud-Native Communication Patterns*.

*Resilienz*

Eine Microservices-Architektur verschiebt Ihr System von der in-Process- zur Netzwerkkommunikation. Was tun Sie in einer verteilten Umgebung, wenn Dienst B nicht auf einen Anruf von Dienst A reagiert? Was geschieht, wenn Dienst C vorübergehend nicht mehr verfügbar ist und andere Dienste, die ihn aufrufen, stacken und die Systemleistung beeinträchtigen?

Die Resilienz wird im Detail behandelt Kapitel 6, *Cloud-Native Resiliency*.

*Verteilte Daten*

Jeder Microservice kapselt seine eigenen Daten und stellt Vorgänge über seine öffentliche Schnittstelle frei. Wenn ja, wie können Sie Daten abfragen oder eine Transaktion über mehrere Dienste hinweg implementieren?

Verteilte Daten werden im Detail behandelt Kapitel 5, *Cloud-Native Data Patterns*.

*Identität*

Wie wird Ihr Dienst ermitteln, wer darauf zugreift und über welche Berechtigungen er verfügt?

Die Identität wird im Detail behandelt Kapitel 8, *Identität*.

## <a name="microservices"></a>Microservices

Cloud-native Systeme umfassen Microservices, einen beliebten Architekturstil für die Erstellung moderner Anwendungen.

Microservices wurden als verteilter Satz kleiner, unabhängiger Dienste entwickelt, die über eine gemeinsam genutzte Fabric interagieren, und haben die folgenden Merkmale:

- Jeder implementiert eine bestimmte Geschäftsfunktion in einem größeren Domänenkontext.

- Jeder wird autonom entwickelt und kann unabhängig voneinander eingesetzt werden.

- Jedes ist in sich geschlossen und kapselt seine eigene Datenspeichertechnologie (SQL, NoSQL) und Programmierplattform.

- Jeder wird in einem eigenen Prozess ausgeführt und kommuniziert mit anderen über Standardkommunikationsprotokolle wie HTTP/HTTPS, WebSockets oder [AMQP](https://en.wikipedia.org/wiki/Advanced_Message_Queuing_Protocol).

- Sie komponieren zusammen, um eine Anwendung zu bilden.

Abbildung 1-4 kontrastiert einen monolithischen Anwendungsansatz mit einem Microservices-Ansatz. Beachten Sie, wie der Monolith aus einer mehrschichtigen Architektur besteht, die in einem einzigen Prozess ausgeführt wird. In der Regel wird eine relationale Datenbank verwendet. Der Microservice-Ansatz unterteilt jedoch Die Funktionalität in unabhängige Dienste, die Logik und Daten enthalten. Jeder Microservice hostet einen eigenen Datenspeicher.

![Monolithische Bereitstellung im Vergleich zu Microservices](./media/monolithic-vs-microservices.png)

**Abbildung 1-4.** Monolithische Bereitstellung im Vergleich zu Microservices

Beachten Sie, wie Microservices das Prinzip "One Codebase, One Application" aus der [Zwölf-Faktor-Anwendung](https://12factor.net/)fördern, die weiter oben im Kapitel besprochen wurde.

> *Faktor \#1 gibt "Eine einzelne Codebasis für jeden Microservice an, der in einem eigenen Repository gespeichert ist. Mit Versionskontrolle verfolgt, kann es in mehreren Umgebungen bereitgestellt werden."*

### <a name="why-microservices"></a>Gründe für die Verwendung von Microservices

Microservices bieten Agilität.

Früher im Kapitel haben wir eine eCommerce-Anwendung, die als Monolith erstellt wurde, mit Microservices verglichen. Im Beispiel haben wir einige klare Vorteile gesehen:

- Jeder Microservice verfügt über einen autonomen Lebenszyklus und kann sich unabhängig entwickeln und häufig bereitstellen. Sie müssen nicht auf eine vierteljährliche Version warten, um neue Features oder Updates bereitzustellen. Sie können einen kleinen Bereich einer komplexen Anwendung aktualisieren, ohne das Risiko, das gesamte System zu stören.

- Jeder Microservice kann unabhängig skaliert werden. Anstatt die gesamte Anwendung als eine Einheit zu skalieren, skalieren Sie nur die Dienste, die mehr Rechenleistung oder Netzwerkbandbreite benötigen. Dieser feinkörnige Skalierungsansatz ermöglicht eine bessere Kontrolle Ihres Systems und trägt dazu bei, die Gesamtkosten zu senken, wenn Sie Teile Ihres Systems skalieren, nicht alles.

Ein ausgezeichneter Referenzleitfaden für das Verständnis von Microservices ist [.NET Microservices: Architecture for Containerized .NET Applications](https://docs.microsoft.com/dotnet/standard/microservices-architecture/). Das Buch taucht tief in Microservices Design und Architektur ein. Es ist ein Begleiter für eine [Full-Stack-Microservice-Referenzarchitektur,](https://github.com/dotnet-architecture/eShopOnContainers) die als kostenloser Download von Microsoft zur Verfügung steht.

### <a name="developing-microservices"></a>Entwicklung von Microservices

Microservices können mit jeder modernen Entwicklungsplattform erstellt werden.

Die Microsoft .NET Core-Plattform ist eine ausgezeichnete Wahl. Frei und Open Source, hat es viele integrierte Funktionen, um die Entwicklung von Microservice zu vereinfachen. .NET Core ist plattformübergreifend. Anwendungen können unter Windows, macOS und den meisten Linux-Varianten erstellt und ausgeführt werden.

.NET Core ist sehr leistungsstark und hat im Vergleich zu Node.js und anderen konkurrierenden Plattformen gut abgeschnitten. Interessanterweise führte [TechEmpower](https://www.techempower.com/) eine umfangreiche Reihe von [Performance-Benchmarks](https://www.techempower.com/benchmarks/#section=data-r17&hw=ph&test=plaintext) auf vielen Webanwendungsplattformen und Frameworks durch. .NET Core punktete in den Top 10 - deutlich über Node.js und anderen konkurrierenden Plattformen.

.NET Core wird von Microsoft und der .NET-Community auf GitHub verwaltet.

## <a name="containers"></a>Container

Heutzutage ist es natürlich, den Begriff *Container* in jedem Gespräch über *Cloud native*erwähnt zu hören. In dem Buch [Cloud Native Patterns](https://www.manning.com/books/cloud-native-patterns)bemerkt Autorin Cornelia Davis: "Container sind ein großartiger Ermöglicher cloudnativer Software." Die Cloud Native Computing Foundation stellt die Microservice-Containerisierung als ersten Schritt in ihrer [Cloud-Native Trail Map](https://raw.githubusercontent.com/cncf/trailmap/master/CNCF_TrailMap_latest.png) - Anleitung für Unternehmen, die ihre Cloud-native Reise beginnen.

Die Containerisierung eines Microservices ist einfach und unkompliziert. Der Code, seine Abhängigkeiten und die Laufzeit werden in eine Binärdatei mit dem Namen [Containerabbild](https://docs.docker.com/glossary/?term=image)gepackt. Bilder werden in einer [Containerregistrierung](https://caylent.com/container-registries/)gespeichert, die als Repository oder Bibliothek für Bilder fungiert. Eine Registrierung kann sich auf Ihrem Entwicklungscomputer, in Ihrem Rechenzentrum oder in einer öffentlichen Cloud befinden. Docker selbst unterhält eine öffentliche Registrierung über [Docker Hub](https://hub.docker.com/). Die Azure-Cloud verfügt über eine [Containerregistrierung](https://azure.microsoft.com/services/container-registry/) zum Speichern von Containerabbildern in der Nähe der Cloudanwendungen, die sie ausführen.

Bei Bedarf transformieren Sie das Bild in eine laufende Containerinstanz. Die Instanz wird auf jedem Computer ausgeführt, auf dem ein [Container-Laufzeitmodul](https://kubernetes.io/docs/setup/production-environment/container-runtimes/) installiert ist. Sie können beaufststehend über den Containerdienst verfügen, wie erforderlich.

Abbildung 1-5 zeigt drei verschiedene Microservices, die jeweils in einem eigenen Container ausgeführt werden und auf einem einzelnen Host ausgeführt werden.

![Mehrere Container, die auf einem Containerhost ausgeführt werden](./media/hosting-mulitple-containers.png)

**Abbildung 1-5**. Mehrere Container, die auf einem Containerhost ausgeführt werden

Beachten Sie, dass jeder Container einen eigenen Satz von Abhängigkeiten und Laufzeiten verwaltet, die unterschiedlich sein können. Hier sehen wir verschiedene Versionen des Product Microservice, die auf demselben Host ausgeführt werden. Jeder Container teilt ein Segment des zugrunde liegenden Hostbetriebssystems, Arbeitsspeichers und Prozessors, ist jedoch voneinander isoliert.

Beachten Sie, wie gut das Containermodell das Prinzip "Abhängigkeiten" aus der [Zwölf-Faktor-Anwendung](https://12factor.net/)umfasst.

> *Faktor \#2 gibt an, dass "jeder Microservice seine eigenen Abhängigkeiten isoliert und verpackt, wobei Änderungen berücksichtigt werden, ohne das gesamte System zu beeinträchtigen."*

Container unterstützen sowohl Linux- als auch Windows-Workloads. Die Azure-Cloud umfasst offen beides. Interessanterweise ist es Linux, nicht Windows Server, das zum beliebtesten Betriebssystem in Azure geworden ist.

Während es mehrere Container-Anbieter gibt, hat Docker den Löwenanteil des Marktes erobert. Das Unternehmen hat die Software-Container-Bewegung vorangetrieben. Es ist zum De-facto-Standard für das Verpacken, Bereitstellen und Ausführen von Cloud-nativen Anwendungen geworden.

### <a name="why-containers"></a>Warum Container?

Container bieten Portabilität und garantieren Konsistenz über Umgebungen hinweg. Indem Sie alles in einem einzigen Paket kapseln, *isolieren* Sie den Microservice und seine Abhängigkeiten von der zugrunde liegenden Infrastruktur.

Sie können denselben Container in jeder Umgebung bereitstellen, die über das Docker-Laufzeitmodul verfügt. Containerisierte Workloads eliminieren auch die Kosten für die Vorkonfiguration jeder Umgebung mit Frameworks, Softwarebibliotheken und Laufzeitmodulen.

Durch die gemeinsame Nutzung des zugrunde liegenden Betriebssystems und der Hostressourcen haben Container einen viel geringeren Platzbedarf als eine vollständige virtuelle Maschine. Die kleinere Größe erhöht die *Dichte*oder Anzahl der Microservices, die ein bestimmter Host gleichzeitig ausführen kann.

### <a name="container-orchestration"></a>Containerorchestrierung

Während Tools wie Docker Images erstellen und Container ausführen, benötigen Sie auch Tools, um sie zu verwalten. Die Containerverwaltung erfolgt mit einem speziellen Softwareprogramm namens Containerorchestrator. Bei einem Skalenbetrieb ist die Containerorchestrierung unerlässlich.

Abbildung 1-6 zeigt Verwaltungsaufgaben, die Container-Orchestratoren bereitstellen.

![Was Container-Orchestratoren tun](./media/what-container-orchestrators-do.png)

**Abbildung 1-6**. Was Container-Orchestratoren tun

In der folgenden Tabelle werden allgemeine Orchestrierungsaufgaben beschrieben.

|  Aufgaben | Erklärung  |
| :-------- | :-------- |
| Scheduling | Automatische Bereitstellung von Containerinstanzen.|
| Affinität/Anti-Affinität | Bereitstellung von Containern in der Nähe oder weit voneinander entfernt, um Verfügbarkeit und Leistung zu unterstützen. |
| Systemüberwachung | AutomatischeErkennung und Korrektur von Fehlern.|
| Failover | Automatische erneute Bereitstellung fehlgeschlagener Instanz enden auf fehlerfreien Computern.|
| Skalierung | Automatisches Hinzufügen oder Entfernen der Containerinstanz, um den Bedarf zu decken.|
| Netzwerk | Verwalten Sie ein Netzwerk-Overlay für die Containerkommunikation.|
| Dienstsuche | Aktivieren Sie Container, um sich gegenseitig zu lokalisieren.|
| Parallele Upgrades | Koordinieren Sie inkrementelle Upgrades mit einer Bereitstellung ohne Ausfallzeiten. Automatisches Rollback problematischer Änderungen.|

Beachten Sie, wie Die Orchestratoren die Grundsätze der Disponierbarkeit und Parallelität aus der [Zwölf-Faktor-Anwendung](https://12factor.net/)übernehmen, die weiter oben im Kapitel behandelt wurde.

> *Faktor \#9 gibt an, dass "Dienstinstanzen verfügbar sein sollten, und schnelle Startmöglichkeiten bevorzugen, um Skalierbarkeitsmöglichkeiten zu erhöhen, und ordnungsgemäße Herunterschaltungen, um das System in einem korrekten Zustand zu belassen. Docker-Container zusammen mit einem Orchestrator erfüllen diese Anforderung von Natur aus."*

> *Faktor \#8 gibt an, dass "Dienste über eine große Anzahl kleiner identischer Prozesse (Kopien) skaliert werden, anstatt eine einzelne große Instanz auf dem leistungsstärksten verfügbaren Computer zu skalieren."*

Während es mehrere Container-Orchestratoren gibt, ist [Kubernetes](https://kubernetes.io/docs/concepts/overview/what-is-kubernetes/) zum De-facto-Standard für die Cloud-native Welt geworden. Es handelt sich um eine portable, erweiterbare Open-Source-Plattform für die Verwaltung containerisierter Workloads.

Sie könnten Ihre eigene Instanz von Kubernetes hosten, aber dann wären Sie für die Bereitstellung und Verwaltung seiner Ressourcen verantwortlich - was komplex sein kann. Die Azure-Cloud verfügt über Kubernetes als verwalteten Dienst, [Azure Kubernetes Service (AKS)](https://azure.microsoft.com/services/kubernetes-service/). Ein verwalteter Dienst ermöglicht es Ihnen, seine Funktionen vollständig zu nutzen, ohne sie installieren und warten zu müssen.

Azure Kubernetes Services wird ausführlich behandelt Kapitel 2, *Scaling Cloud-Native Applications*.

## <a name="backing-services"></a>Backing Services

Cloud-native Systeme hängen von vielen verschiedenen Nebenressourcen ab, z. B. Datenspeichern, Nachrichtenbrokern, Überwachungs- und Identitätsdiensten. Diese Dienste werden als [Sicherungsdienste](https://12factor.net/backing-services)bezeichnet.

 Abbildung 1-7 zeigt viele gängige Unterstützungsdienste, die Cloud-native Systeme nutzen.

![Gemeinsame Unterstützungsdienste](./media/common-backing-services.png)

**Abbildung 1-7**. Gemeinsame Unterstützungsdienste

Unterstützungsdienste fördern das Prinzip der "Staatenlosigkeit" aus der [Zwölf-Faktor-Anwendung](https://12factor.net/), die weiter oben im Kapitel erörtert wurde.

>*Faktor \#6* gibt an: "Jeder Microservice sollte in seinem eigenen Prozess ausgeführt werden, isoliert von anderen ausgeführten Diensten. Externalisieren des erforderlichen Status für einen Sicherungsdienst, z. B. einen verteilten Cache oder Datenspeicher."

Sie können Ihre eigenen Sicherungsdienste hosten, aber dann sind Sie für die Lizenzierung, Bereitstellung und Verwaltung dieser Ressourcen verantwortlich.

Cloud-Anbieter bieten eine reiche Auswahl an *Managed Backing Services.* Anstatt den Dienst zu besitzen, konsumieren Sie ihn einfach. Der Anbieter betreibt die Ressource in großem Maßstab und trägt die Verantwortung für Leistung, Sicherheit und Wartung. Überwachung, Redundanz und Verfügbarkeit sind in den Dienst integriert. Anbieter unterstützen ihre Managed Services voll um, öffnen Sie ein Ticket und beheben Sie Ihr Problem.

Cloud-native Systeme bevorzugen managed backing services von Cloud-Anbietern. Die Zeit- und Arbeitsersparnis ist groß. Das operationelle Risiko, eigene Hosting und Probleme zu haben, kann schnell teuer werden.

Es wird eine bewährte Methode darin besteht, einen Sicherungsdienst als *angefügte Ressource*zu behandeln, die dynamisch an einen Microservice mit Informationen (einer URL und Anmeldeinformationen) gebunden ist, die in einer externen Konfiguration gespeichert sind. Diese Anleitung ist in der [Zwölf-Faktor-Anwendung](https://12factor.net/)dargelegt, die weiter oben im Kapitel erörtert wurde.

>*Faktor \#4* gibt an, dass Sicherungsdienste "über eine adressierbare URL verfügbar gemacht werden sollten. Dadurch wird die Ressource von der Anwendung entkoppelt, sodass sie austauschbar ist."

>*Faktor \#3* gibt an, dass "Konfigurationsinformationen aus dem Microservice verschoben und über ein Konfigurationsverwaltungstool außerhalb des Codes externisiert werden."

Bei diesem Muster kann ein Sicherungsdienst ohne Codeänderungen angefügt und getrennt werden. Sie können einen Microservice von der Qualitätssicherung in eine Stagingumgebung heraufstufen. Sie aktualisieren die Microservice-Konfiguration, um auf die Sicherungsdienste in der Staging-Station zu verweisen, und fügen die Einstellungen über eine Umgebungsvariable in den Container ein.

Cloud-Anbieter stellen APIs für die Kommunikation mit ihren proprietären Backing-Services bereit. Diese Bibliotheken kapseln die Installation und Komplexität. Wenn Sie direkt mit diesen APIs kommunizieren, wird Ihr Code eng mit dem Sicherungsdienst verzahnt. Es ist eine bessere Methode, die Implementierungsdetails der Hersteller-API zu isolieren. Führen Sie eine Intermediationsschicht oder Zwischen-API ein, um generische Vorgänge für Ihren Dienstcode zu verwenden. Mit dieser lose Kopplung können Sie einen Sicherungsdienst gegen einen anderen austauschen oder Den Code in eine andere öffentliche Cloud verschieben, ohne Änderungen am Hauptdienstcode vornehmen zu müssen.

Sicherungsdienste werden ausführlich behandelt Kapitel 5, *Cloud-Native Data Patterns*und Kapitel 4, *Cloud-Native Communication Patterns*.

## <a name="automation"></a>Automation

Wie Sie gesehen haben, umfassen Cloud-native Systeme Microservices, Container und modernes Systemdesign, um Geschwindigkeit und Agilität zu erreichen. Aber das ist nur ein Teil der Geschichte. Wie stellen Sie die Cloud-Umgebungen bereit, in denen diese Systeme ausgeführt werden? Wie können Sie App-Funktionen und -Updates schnell bereitstellen? Wie runden Sie das Gesamtbild ab?

Geben Sie die weithin akzeptierte Praxis [infrastruktur als Code](https://docs.microsoft.com/azure/devops/learn/what-is-infrastructure-as-code)oder IaC ein.

Mit IaC automatisieren Sie die Bereitstellung von Plattformen und die Anwendungsbereitstellung. Sie wenden im Wesentlichen Software-Engineering-Praktiken wie Testen und Versionieren auf Ihre DevOps-Praktiken an. Ihre Infrastruktur und Ihre Bereitstellungen sind automatisiert, konsistent und wiederholbar.

### <a name="automating-infrastructure"></a>Automatisierung der Infrastruktur

Tools wie [Azure Resource Manager](https://azure.microsoft.com/documentation/articles/resource-group-overview/), Terraform und die Azure [CLI](https://docs.microsoft.com/cli/azure/)ermöglichen es Ihnen, deklarativ skripten die Cloudinfrastruktur, die Sie benötigen. Ressourcennamen, Standorte, Kapazitäten und Geheimnisse sind parametrisiert und dynamisch. Das Skript wird als Artefakt Ihres Projekts versioniert und in die Quellcodeverwaltung eingecheckt. Sie rufen das Skript auf, um eine konsistente und wiederholbare Infrastruktur für alle Systemumgebungen bereitzustellen, z. B. QS, Staging und Produktion.

Unter der Haube ist IaC idempotent, was bedeutet, dass Sie das gleiche Skript immer und immer wieder ohne Nebenwirkungen ausführen können. Wenn das Team eine Änderung vornehmen muss, bearbeitet und führt es das Skript erneut aus. Nur die aktualisierten Ressourcen sind betroffen.

In dem Artikel [What is Infrastructure as Code](https://docs.microsoft.com/azure/devops/learn/what-is-infrastructure-as-code)beschreibt Autor Sam Guckenheimer, wie "Teams, die IaC implementieren, stabile Umgebungen schnell und in großem Maßstab bereitstellen können. Teams vermeiden die manuelle Konfiguration von Umgebungen und erzwingen Konsistenz, indem sie den gewünschten Zustand ihrer Umgebungen über Code darstellen. Infrastrukturbereitstellungen mit IaC sind wiederholbar und verhindern Laufzeitprobleme, die durch Konfigurationsdrift oder fehlende Abhängigkeiten verursacht werden. DevOps-Teams können mit einer einheitlichen Reihe von Verfahren und Tools zusammenarbeiten, um Anwendungen und ihre unterstützende Infrastruktur schnell, zuverlässig und in großem Maßstab bereitzustellen."

### <a name="automating-deployments"></a>Automatisieren von Bereitstellungen

Die [zwölfstufige Anwendung](https://12factor.net/), die zuvor erörtert wurde, erfordert separate Schritte beim Transformieren von abgeschlossenem Code in eine ausgeführte Anwendung.

> *Faktor \#5* gibt an, dass "jede Version eine strikte Trennung über die Build-, Release- und Ausführungsphasen erzwingen muss. Jeder sollte mit einer eindeutigen ID versehen werden und die Möglichkeit unterstützen, einen Rollback zurückzufahren."

Moderne CI/CD-Systeme helfen dabei, dieses Prinzip zu erfüllen. Sie bieten separate Bereitstellungsschritte und helfen dabei, konsistenten und qualitativ hochwertigen Code sicherzustellen, der Benutzern problemlos zur Verfügung steht.

Abbildung 1-8 zeigt die Trennung über den Bereitstellungsprozess hinweg.

![Bereitstellungsschritte in DER CI/CD-Pipeline](./media/build-release-run-pipeline.png)

**Abbildung 1-8**. Bereitstellungsschritte in einer CI/CD-Pipeline

Achten Sie in der vorherigen Abbildung besonders auf die Aufgabentrennung.

Der Entwickler erstellt ein Feature in seiner Entwicklungsumgebung und durchläuft die so genannte "innere Schleife" von Code, Ausführung und Debuggen. Nach Abschluss wird dieser Code in ein Code-Repository wie GitHub, Azure DevOps oder BitBucket *übertragen.*

Der Push löst eine Buildphase aus, die den Code in ein binäres Artefakt umwandelt. Die Arbeit wird mit einer [Continuous Integration (CI)-Pipeline](https://martinfowler.com/articles/continuousIntegration.html) durchgeführt. Es erstellt, testet und verpackt die Anwendung automatisch.

Die Release-Phase nimmt das binäre Artefakt auf, wendet externe Anwendungs- und Umgebungskonfigurationsinformationen an und erzeugt eine unveränderliche Version. Die Version wird in einer angegebenen Umgebung bereitgestellt. Die Arbeit wird mit einer [Continuous Delivery(CD)-Pipeline](https://martinfowler.com/bliki/ContinuousDelivery.html) implementiert. Jede Version sollte identifizierbar sein. Sie können sagen: "Diese Bereitstellung führt Release 2.1.1 der Anwendung aus."

Schließlich wird die freigegebene Funktion in der Zielausführungsumgebung ausgeführt. Releases sind unveränderlich, was bedeutet, dass jede Änderung eine neue Version erstellen muss.

Mit diesen Praktiken haben Organisationen die Art und Weise, wie sie Software versenden, radikal weiterentwickelt. Viele haben sich von vierteljährlichen Versionen zu On-Demand-Updates bewegt. Das Ziel ist es, Probleme früh im Entwicklungszyklus zu fangen, wenn sie weniger teuer zu beheben sind. Je länger die Dauer zwischen den Integrationen, desto teurer werden Probleme zu lösen.  Mit der Konsistenz im Integrationsprozess können Teams Codeänderungen häufiger übertragen, was zu einer besseren Zusammenarbeit und Softwarequalität führt.

### <a name="azure-pipelines"></a>Azure Pipelines

Die Azure-Cloud enthält einen neuen CI/CD-Dienst mit dem Titel [Azure Pipelines](https://azure.microsoft.com/services/devops/pipelines/), der Teil des [Azure DevOps-Angebots](https://azure.microsoft.com/services/devops/) in Abbildung 1-9 ist.

![Azure-Pipelines in DevOps](./media/devops-components.png)

**Abbildung 1-9**. Azure DevOps-Angebote

Azure Pipelines ist ein Clouddienst, der kontinuierliche Integration (Continuous Integration, CI) und Continuous Delivery (CD) kombiniert. Sie können Ihren Code automatisch testen, erstellen und an jedes beliebige Ziel senden.

Sie definieren Ihre Pipeline in Code in einer YAML-Datei zusammen mit dem Rest des Codes für Ihre App.

- Die Pipeline wird mit Ihrem Code versioniert und folgt derselben Verzweigungsstruktur.
- Sie erhalten eine Validierung Ihrer Änderungen durch Codeüberprüfungen in Pull-Anforderungen und Zweigstellenbuildrichtlinien.
- Jeder Zweig, den Sie verwenden, kann die Buildrichtlinie anpassen, indem die Datei azure-pipelines.yml geändert wird.
- Die Pipelinedatei wird in die Versionskontrolle eingecheckt und kann bei einem Problem untersucht werden.

Der Azure-Pipelinesdienst unterstützt die meisten Git-Anbieter und kann Bereitstellungspipelines für Anwendungen generieren, die auf Linux-, macOS- oder Windows-Plattformen geschrieben wurden. Es enthält Unterstützung für Java, .NET, JavaScript, Python, PHP, Go, XCode und C++.

>[!div class="step-by-step"]
>[Zurück](introduction.md)
>[Weiter](candidate-apps.md)
