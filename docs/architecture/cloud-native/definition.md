---
title: Definition von cloudbasiert
description: Erfahren Sie mehr über die grundlegenden Säulen, die das Fundament für Native cloudsysteme bereitstellen.
author: robvet
ms.date: 05/13/2020
ms.openlocfilehash: dce8da57b90519880e322a26de403d8e7cb718c2
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91160904"
---
# <a name="defining-cloud-native"></a>Definieren von Cloud Native

Nehmen Sie an, was Sie tun, und Text zehn Ihrer Kollegen. Bitten Sie ihn, den Begriff "Cloud Native" zu definieren. Eine gute Chance ist, dass Sie zehn verschiedene Antworten erhalten.

Bei der nativen Cloud geht es um das Ändern der Art und Weise, wie Sie mit der Erstellung wichtiger Geschäftssysteme

Cloud-Native Systeme sind für schnelle Änderungen, große Skalierbarkeit und Resilienz konzipiert.

Die Cloud Native Computing Foundation bietet eine [offizielle Definition](https://github.com/cncf/foundation/blob/master/charter.md):

> *Cloudnative Technologien ermöglichen Organisationen das Erstellen und ausführen skalierbarer Anwendungen in modernen, dynamischen Umgebungen wie öffentlichen, privaten und Hybriden Clouds. Diese Vorgehensweise wird durch Container, Service Meshes, microservices, eine unveränderliche Infrastruktur und deklarative APIs veranschaulicht.*

> *Diese Techniken ermöglichen lose gekoppelte Systeme, die robust, verwaltbar und observabel sind. In Kombination mit robuster Automatisierung ermöglichen Sie Entwicklern das häufige und vorhersagbare ändern von Änderungen mit minimaler Beeinträchtigung.*

Anwendungen sind immer komplexer geworden, und Benutzer fordern mehr und mehr an. Benutzer erwarten schnelle Reaktionsfähigkeit, innovative Features und keine Ausfallzeiten. Leistungsprobleme, wiederkehrende Fehler und die Unfähigkeit, schnell zu verschieben, sind nicht mehr akzeptabel. Sie können problemlos zu ihrem Mitbewerber wechseln.

Cloud Native ist viel über *Geschwindigkeit* und *Agilität*. Geschäftssysteme werden von der Unterstützung von Geschäftsfunktionen bis hin zu einer strategischen Transformation entwickelt und beschleunigen die Geschäfts Geschwindigkeit und das Wachstum. Es ist zwingend erforderlich, dass Sie sofort Ideen in den Markt bringen.

Im folgenden finden Sie einige Unternehmen, die diese Techniken implementiert haben. Berücksichtigen Sie die Geschwindigkeit, Agilität und Skalierbarkeit, die Sie erreicht haben.

| Company | Erfahrung |
| :-------- | :-------- |
| [Netflix](https://www.infoq.com/news/2013/06/netflix/) | Umfasst 600 Dienste in der Produktionsumgebung. Wird hundert Mal pro Tag bereitgestellt. |
| [Uber](https://eng.uber.com/micro-deploy/) | Hat in der Produktion 1000 Dienste. Stellt mehrere tausend Male pro Woche bereit. |
| [WeChat](https://www.cs.columbia.edu/~ruigu/papers/socc18-final100.pdf) | Verfügt über 3000 Dienste in der Produktionsumgebung. Stellt 1.000 Mal täglich bereit. |

Wie Sie sehen, machen Netflix, uber und WeChat Systeme verfügbar, die aus Hunderten von unabhängigen mikrodiensten bestehen. Dieser Architekturstil ermöglicht es Ihnen, schnell auf Marktbedingungen zu reagieren. Sie können kleine Bereiche einer aktiven, komplexen Anwendung sofort aktualisieren und diese Bereiche bei Bedarf einzeln skalieren.

Die Geschwindigkeit und Agilität von Cloud Native ist von einer Reihe von Faktoren abhängig. Vor allem ist die cloudinfrastruktur Fünf weitere grundlegende Säulen, die in Abbildung 1-3 dargestellt werden, stellen auch das Fundament für Native cloudsysteme dar.

![In der Cloud Native grundlegende Säulen](./media/cloud-native-foundational-pillars.png)

**Abbildung 1–3**. In der Cloud Native grundlegende Säulen

Nehmen wir etwas Zeit, um die Bedeutung der einzelnen Säulen besser zu verstehen.

## <a name="the-cloud"></a>Die Cloud...

Cloud-Native Systeme nutzen das clouddienstmodell vollständig.

Diese Systeme sind so konzipiert, dass Sie in einer dynamischen, virtualisierten cloudumgebung eingesetzt werden, indem Sie die Compute-Infrastruktur von [Platform-as-a-Service (PAS)](https://azure.microsoft.com/overview/what-is-paas/) und verwaltete Dienste umfassend nutzen Die zugrunde liegende Infrastruktur wird in wenigen *Minuten als in* wenigen Minuten bereitgestellt und in der Größe geändert, skaliert, verschoben oder zerstört – über Automation.

Sehen Sie sich das weithin akzeptierte devops-Konzept von [Haustieren und Rindern](https://medium.com/@Joachim8675309/devops-concepts-pets-vs-cattle-2380b5aab313)an. In einem herkömmlichen Rechenzentrum werden Server als *Haustiere*behandelt: ein physischer Computer, bei dem ein sinnvoller Name angegeben ist und der behandelt wird. Skalieren Sie durch Hinzufügen von weiteren Ressourcen zum gleichen Computer (zentrales hochskalieren). Wenn der Server krank wird, können Sie ihn wieder in die Integrität unter Rücken. Wenn der Server nicht mehr verfügbar ist, wird jeder bemerkt.

Das *Rinder* Dienstmodell unterscheidet sich. Sie stellen jede Instanz als einen virtuellen Computer oder Container bereit. Sie sind identisch und haben einen System Bezeichner wie Service-01, Service-02 usw. zugewiesen. Skalieren Sie, indem Sie mehr von Ihnen erstellen (horizontal hochskalieren). Wenn eine solche nicht verfügbar ist, wird niemand bemerkt.

Das Rinder Modell umfasst eine *unveränderliche Infrastruktur*. Server werden nicht repariert oder geändert. Wenn ein Fehler auftritt oder aktualisiert werden muss, wird er zerstört und eine neue bereitgestellt – alles über Automation.

Cloud-Native Systeme nehmen das Vieh Dienstmodell in Betrieb. Sie werden weiterhin ausgeführt, wenn die Infrastruktur in Bezug auf die Computer, auf denen Sie ausgeführt werden, horizontal hoch-oder herunterskaliert wird.

Die Azure-cloudplattform unterstützt diese Art von hochelastischer Infrastruktur mit automatischer Skalierung, Selbstreparatur und Überwachungsfunktionen.

## <a name="modern-design"></a>Modernes Design

Wie würden Sie eine Cloud-Native App entwerfen? Wie sieht Ihre Architektur aus? Welchen Prinzipien, Mustern und bewährten Methoden entsprechen Sie? Welche Infrastruktur und welche betrieblichen Probleme sind wichtig?

### <a name="the-twelve-factor-application"></a>Die zwölfstufige Anwendung

Eine weit verbreitete Methode zum Erstellen von cloudbasierten Anwendungen ist die [zwölfstufige Anwendung](https://12factor.net/). Es beschreibt eine Reihe von Prinzipien und Vorgehensweisen, die Entwickler befolgen, um Anwendungen zu erstellen, die für moderne cloudumgebungen optimiert sind. Besondere Aufmerksamkeit ist für die Portabilität in Umgebungen und deklarative Automatisierung.

Wenngleich auf webbasierte Anwendungen anwendbar ist, sehen viele Fachleute als eine solide Grundlage für die Entwicklung von cloudbasierten apps. Systeme, die auf diesen Prinzipien basieren, können schnell bereitstellen und skalieren und Features hinzufügen, um schnell auf Markt Änderungen zu reagieren.

In der folgenden Tabelle wird die zwölfstufige Methodik hervorgehoben:

|    |  Faktor | Erklärung  |
| :-------- | :-------- | :-------- |
| 1 | Codebasis | Eine einzelne Codebasis für jeden in einem eigenen Repository gespeicherten mikrodienst. Die Nachverfolgung mit der Versionskontrolle kann in mehreren Umgebungen (QA, Staging, Produktion) bereitgestellt werden. |
| 2 | Abhängigkeiten | Jeder-mikrodienst isoliert und packt seine eigenen Abhängigkeiten und übernimmt Änderungen, ohne dass sich dies auf das gesamte System auswirkt. |
| 3 | Configurations  | Konfigurationsinformationen werden aus dem-Unternehmens Dienst verschoben und durch ein Konfigurations Verwaltungs Tool außerhalb des Codes extern ausgelagert. Dieselbe Bereitstellung kann über Umgebungen hinweg verteilt werden, auf die die korrekte Konfiguration angewendet wird.  |
| 4 | Sichern von Diensten | Hilfdressourcen (Datenspeicher, Caches, Nachrichten Broker) sollten über eine adressierbare URL verfügbar gemacht werden. Dadurch wird die Ressource von der Anwendung entkoppelt, sodass Sie austauschbar ist.  |
| 5 | Build, Release, Run | Jede Version muss eine strikte Trennung in den Build-, Release-und Lauf Phasen erzwingen. Jede sollte mit einer eindeutigen ID gekennzeichnet werden und die Möglichkeit des Rollbacks unterstützen. Moderne CI/CD-Systeme helfen dabei, dieses Prinzip zu erfüllen. |
| 6 | Prozesse | Jeder-mikrodienst sollte in einem eigenen Prozess ausgeführt werden, isoliert von anderen ausgelaufenden Diensten. Externalisieren Sie den erforderlichen Zustand zu einem Sicherungsdienst, z. b. einem verteilten Cache oder einem Datenspeicher. |
| 7 | Portbindung | Jeder-mikrodienst sollte eigenständig sein und seine Schnittstellen und Funktionen, die auf seinem eigenen Port verfügbar gemacht werden. Dadurch wird die Isolation von anderen-Diensten ermöglicht. |
| 8 | Parallelität | Dienste können über eine große Anzahl von kleinen identischen Prozessen (Kopien) horizontal hochskaliert werden, anstatt eine einzelne große Instanz auf dem leistungsstärksten verfügbaren Computer zentral hochzuskalieren. |
| 9 | Disposability | Dienst Instanzen sollten verworfen werden können, um schnelle Startups zu verbessern, um Skalierbarkeits Chancen und ordnungsgemäße Herunterfahr Vorgänge zu verbessern, um das System in einem korrekten Zustand zu belassen Docker-Container zusammen mit einem Orchestrator erfüllen diese Anforderung von Natur aus. |
| 10 | Dev/Prod-Parität | Sorgen Sie dafür, dass Umgebungen im gesamten Anwendungslebenszyklus so ähnlich wie möglich sind Hier kann die Übernahme von Containern durch herauf Stufen derselben Ausführungsumgebung erheblich beitragen. |
| 11 | Protokollierung | Behandeln Sie von-Webdiensten generierte Protokolle als Ereignisdaten Ströme. Verarbeiten Sie Sie mit einem Ereignisaggregator, und übertragen Sie die Daten an Data Mining/Log-Verwaltungs Tools wie Azure Monitor oder Splunk und schließlich über eine langfristige Archivierung. |
| 12 | Verwaltungsprozesse | Ausführen von Verwaltungs-und Verwaltungsaufgaben als einmalige Prozesse. Tasks können Datencleanup und Pull Analytics für einen Bericht einschließen. Tools, die diese Aufgaben ausführen, sollten aus der Produktionsumgebung, aber getrennt von der Anwendung aufgerufen werden. |

Im Buch [über die zwölfstufige App hinaus](https://content.pivotal.io/blog/beyond-the-twelve-factor-app)erläutert Autor Kevin Hoffman jeden der ursprünglichen 12 Faktoren (geschrieben in 2011). Außerdem erläutert er drei weitere Faktoren, die den heutigen modernen cloudanwendungsentwurf widerspiegeln.

|    |  Neuer Faktor | Erklärung  |
| :-------- | :-------- | :-------- |
| 13 | API First | Machen Sie alles als Dienst. Nehmen Sie an, dass Ihr Code von einem Front-End-Client,-Gateway oder einem anderen Dienst verwendet wird. |
| 14 | Telemetrie | Auf einer Arbeitsstation haben Sie umfassende Einblicke in Ihre Anwendung und ihr Verhalten. In der Cloud ist das nicht der einzige. Stellen Sie sicher, dass Ihr Entwurf die Erfassung von Überwachungs-, domänenspezifischen und Integritäts-/Systemdaten umfasst. |
| 15 | Authentifizierung/Autorisierung  | Implementieren Sie die Identität von Anfang an. Beachten Sie die [RBAC-Features (rollenbasierte Zugriffs Steuerung)](/azure/role-based-access-control/overview) , die in öffentlichen Clouds verfügbar sind.  |

Wir verweisen auf viele der 12 +-Faktoren in diesem Kapitel und im Buch.

### <a name="critical-design-considerations"></a>Wichtige Überlegungen zum Entwurf

Neben den Anleitungen der zwölfstufigen Methodik gibt es einige wichtige Entwurfsentscheidungen, die Sie beim Erstellen verteilter Systeme treffen müssen.

*Kommunikation*

Wie werden Front-End-Client Anwendungen mit gesicherten End-Kerndiensten kommunizieren? Wird die direkte Kommunikation zugelassen? Oder können Sie die Back-End-Dienste mit einer gatewayfassade abstrahieren, die Flexibilität, Kontrolle und Sicherheit bietet?

Wie werden Back-End-Kerndienste miteinander kommunizieren? Können Sie direkte http-Aufrufe zulassen, die zu einer Kopplung führen und die Leistung und Agilität beeinträchtigen? Oder sollten Sie entkoppelte Messaging mit Warteschlangen-und Themen Technologien in Erwägung gezogen haben?

Die Kommunikation wird im Detail Kapitel 4, in der *Cloud Native Kommunikationsmuster*behandelt.

*Resilienz*

Eine microservices-Architektur verlagert das System von Prozess zu Prozess-und prozessübergreifende Netzwerkkommunikation. Was geschieht in einer verteilten Architektur, wenn Dienst B nicht auf einen Netzwerkdienst von Dienst a antwortet? Oder was geschieht, wenn Dienst C vorübergehend nicht verfügbar ist und andere Dienste, die ihn aufrufen, blockiert werden?

Die Resilienz wird im Detail Kapitel 6, *Cloud-Native Resilienz*behandelt.

*Verteilte Daten*

In der Entwurfs Umgebung kapselt jeder microservice seine eigenen Daten, wodurch Vorgänge über seine öffentliche Schnittstelle verfügbar gemacht werden. Wenn dies der Fall ist, wie können Sie Daten Abfragen oder eine Transaktion über mehrere Dienste hinweg implementieren?

Verteilte Daten werden in Kapitel 5, in der *Cloud Native Datenmuster*, ausführlich behandelt.

*Identität*

Wie wird Ihr Dienst ermitteln, wer auf ihn zugreift und welche Berechtigungen er hat?

Die Identität wird im Detail Kapitel 8, *Identity*, behandelt.

## <a name="microservices"></a>Microservices

In der Cloud Native Systeme sind für die Erstellung moderner Anwendungen ein beliebter Architekturstil zum Erstellen moderner Anwendungen.

Bei der Erstellung eines verteilten Satzes von kleinen, unabhängigen Diensten, die über ein gemeinsam genutztes Fabric interagieren, verfügen die folgenden Eigenschaften über die folgenden Eigenschaften:

- Jede implementiert eine bestimmte Geschäftsfunktion innerhalb eines größeren Domänen Kontexts.

- Jede wird autonom entwickelt und kann unabhängig bereitgestellt werden.

- Jede ist eigenständig und umfasst eine eigene Daten Speicherungs Technologie (SQL, nosql) und eine Programmierplattform.

- Jede wird in einem eigenen Prozess ausgeführt und kommuniziert über Standard Kommunikationsprotokolle wie http/https, websockets oder [AMQP](https://en.wikipedia.org/wiki/Advanced_Message_Queuing_Protocol)mit anderen.

- Sie werden zusammengeführt, um eine Anwendung zu bilden.

In Abbildung 1-4 wird der Ansatz einer monolithischen Anwendung mit einem microservices-Ansatz gegen überstehen. Beachten Sie, dass die monolithische Struktur aus einer geschichteten Architektur besteht, die in einem einzelnen Prozess ausgeführt wird. Normalerweise wird eine relationale Datenbank verwendet. Der microservice-Ansatz trennt jedoch die Funktionalität in unabhängige Dienste, die Logik und Daten enthalten. Jeder-mikrodienst hostet seinen eigenen Datenspeicher.

![Monolithische Bereitstellung im Vergleich zu mikroservices](./media/monolithic-vs-microservices.png)

**Abbildung 1-4.** Monolithische Bereitstellung im Vergleich zu mikroservices

Beachten Sie, wie von den-und-Diensten das "One CodeBase, ONE Application"-Prinzip aus der [zwölfstufigen Anwendung](https://12factor.net/)herauf gestuft wird, das weiter oben im Kapitel erläutert wurde.

> *Faktor \# 1 gibt "eine einzelne Codebasis für jeden in einem eigenen Repository gespeicherten mikrodienst an. Mit der Versionskontrolle nachverfolgt, kann es in mehreren Umgebungen bereitgestellt werden. "*

### <a name="why-microservices"></a>Gründe für die Verwendung von Microservices

Mit der-Dienst Flexibilität können Sie Agilität

An früherer Stelle in diesem Kapitel haben wir eine eCommerce-Anwendung, die als monolithische Anwendung erstellt wurde, mit den-Diensten verglichen. In diesem Beispiel haben wir einige deutliche Vorteile gesehen:

- Jeder-Dienst verfügt über einen autonomen Lebenszyklus und kann unabhängig voneinander entwickelt und häufig bereitgestellt werden. Sie müssen nicht auf eine vierteljährliche Version warten, um neue Features oder Updates bereitzustellen. Sie können einen kleinen Bereich einer komplexen Anwendung aktualisieren, wobei das Risiko verringert wird, das gesamte System zu stören.

- Jeder-mikrodienst kann unabhängig voneinander skaliert werden. Anstatt die gesamte Anwendung als einzelne Einheit zu skalieren, Skalieren Sie nur die Dienste hoch, die eine höhere Verarbeitungsleistung oder Netzwerkbandbreite erfordern. Diese differenzierte Skalierungs Methode bietet eine bessere Kontrolle über Ihr System und hilft, die Gesamtkosten zu reduzieren, wenn Sie Teile Ihres Systems skalieren und nicht alles.

Eine hervorragende Referenzanleitung zum Verständnis von microservices sind [.net-microservices: Architektur für .NET-Container Anwendungen](https://dotnet.microsoft.com/download/thank-you/microservices-architecture-ebook). Das Buch geht tief in microservices Design und Architektur über. Es ist eine Ergänzung für eine [vollständige microservice-Referenzarchitektur](https://github.com/dotnet-architecture/eShopOnContainers) , die als kostenloser Download von Microsoft zur Verfügung steht.

### <a name="developing-microservices"></a>Entwickeln von mikroservices

Sie können mit jeder modernen Entwicklungsplattform erstellt werden.

Die Microsoft .net Core-Plattform ist eine hervorragende Wahl. Kostenlos und Open Source verfügt über viele integrierte Features zur Vereinfachung der Entwicklung von Webdiensten. .Net Core ist plattformübergreifend. Anwendungen können unter Windows, macOS und den meisten Linux-Versionen erstellt und ausgeführt werden.

.Net Core ist äußerst leistungsfähig und wurde im Vergleich zu Node.js und anderen konkurrierenden Plattformen gut bewertet. Interessanterweise hat [techperformance](https://www.techempower.com/) einen umfangreichen Satz von [Leistungs Benchmarks](https://www.techempower.com/benchmarks/#section=data-r17&hw=ph&test=plaintext) für viele Webanwendungs Plattformen und-Frameworks durchgeführt. .Net Core wurde in den ersten 10 über Node.js und anderen konkurrierenden Plattformen bewertet.

.Net Core wird von Microsoft und der .net-Community auf GitHub verwaltet.

## <a name="containers"></a>Container

Heutzutage ist es natürlich, dass der Begriff *Container* zu hören ist, der in einer beliebigen Konversation in Bezug auf die *Cloud Native* Im Buch " [Cloud Native Patterns](https://www.manning.com/books/cloud-native-patterns)" wird der Autor Cornelia Davis feststellen, dass "Container eine gute Lösung für cloudnative Software" sind. Die Cloud Native Computing Foundation stellt die microservice-Containerisierung als ersten Schritt in Ihre [cloudnative Pfad](https://raw.githubusercontent.com/cncf/trailmap/master/CNCF_TrailMap_latest.png) Zuordnung dar und Unternehmen, die mit ihrer cloudbasierten Migration beginnen.

Das containerialisieren eines microservice ist einfach und unkompliziert. Der Code, seine Abhängigkeiten und die Laufzeit werden in eine Binärdatei gepackt, die als [Container Image](https://docs.docker.com/glossary/?term=image)bezeichnet wird. Bilder werden in einer [Container Registrierung](https://caylent.com/container-registries/)gespeichert, die als Repository oder Bibliothek für Images fungiert. Eine Registrierung kann sich auf dem Entwicklungs Computer, in Ihrem Rechenzentrum oder in einer Public Cloud befinden. Docker selbst verwaltet eine öffentliche Registrierung über [docker Hub](https://hub.docker.com/). Die Azure-Cloud verfügt über eine [Container Registrierung](https://azure.microsoft.com/services/container-registry/) zum Speichern von Container Images in der Nähe der cloudanwendungen, von denen Sie ausgeführt werden.

Bei Bedarf wandeln Sie das Bild in eine Container Instanz um, die ausgeführt wird. Die-Instanz wird auf allen Computern ausgeführt, auf denen ein [Container-Lauf](https://kubernetes.io/docs/setup/production-environment/container-runtimes/) Zeit Modul installiert ist. Sie können beliebig viele Instanzen des containerisierten Dienstanbieter haben.

In Abbildung 1-5 werden drei verschiedene mikrodienste angezeigt, die sich jeweils in einem eigenen Container befinden und auf einem einzelnen Host ausgeführt werden.

![Mehrere Container, die auf einem Containerhost ausgeführt werden](./media/hosting-mulitple-containers.png)

**Abbildung 1-5**. Mehrere Container, die auf einem Containerhost ausgeführt werden

Beachten Sie, wie jeder Container seinen eigenen Satz an Abhängigkeiten und Laufzeit beibehält. Dies kann unterschiedlich sein. Hier sehen wir verschiedene Versionen des produkterebugdiensts, die auf demselben Host ausgeführt werden. Jeder Container teilt sich einen Slice des zugrunde liegenden Host Betriebssystems, Arbeitsspeichers und Prozessors, ist aber voneinander isoliert.

Beachten Sie, wie gut das Container Modell das "Abhängigkeiten"-Prinzip von der [zwölfstufigen Anwendung](https://12factor.net/)einnimmt.

> *Faktor \# 2 gibt an, dass "jeder-mikrodienst seine eigenen Abhängigkeiten isoliert und packt, ohne dass das gesamte System beeinträchtigt wird."*

Container unterstützen sowohl Linux-als auch Windows-Workloads. Die Azure-Cloud nimmt beides offen. Interessanterweise ist es Linux, nicht Windows Server, das am beliebtesten Betriebssystem in Azure geworden ist.

Obwohl mehrere containerhersteller vorhanden sind, hat docker den Marktanteil des Landes erfasst. Das Unternehmen hat die Software Container Bewegung vorangetrieben. Es ist der de-facto-Standard für das Verpacken, bereitstellen und Ausführen von cloudbasierten Anwendungen.

### <a name="why-containers"></a>Warum Container?

Container bieten Portabilität und gewährleisten die Konsistenz zwischen Umgebungen. Indem Sie alles in ein einzelnes Paket Kapseln, *isolieren* Sie den microservice und seine Abhängigkeiten von der zugrunde liegenden Infrastruktur.

Sie können denselben Container in jeder Umgebung bereitstellen, die über das docker-Lauf Zeit Modul verfügt. Durch containerisierte Workloads entfällt auch der Aufwand für die Vorkonfigurierung der einzelnen Umgebungen mit Frameworks, Software Bibliotheken und Lauf Zeit Modulen.

Durch die gemeinsame Nutzung des zugrunde liegenden Betriebssystems und der Host Ressourcen haben Container viel geringeren Speicherbedarf als ein vollständiger virtueller Computer. Die geringere Größe erhöht die *Dichte*bzw. die Anzahl von mikrodiensten, die ein bestimmter Host gleichzeitig ausführen kann.

### <a name="container-orchestration"></a>Containerorchestrierung

Während Tools wie docker Images erstellen und Container ausführen, benötigen Sie auch Tools, um Sie zu verwalten. Die Container Verwaltung erfolgt mit einem speziellen Softwareprogramm, das als containerorchestrator bezeichnet wird. Bei einem skalierbaren Betrieb ist die Container Orchestrierung unverzichtbar.

Abbildung 1-6 zeigt Verwaltungsaufgaben, die von containerorchestratoren bereitgestellt werden.

![Was containerorchestratoren tun](./media/what-container-orchestrators-do.png)

**Abbildung 1-6**. Was containerorchestratoren tun

In der folgenden Tabelle werden allgemeine Orchestrierungs Aufgaben beschrieben.

|  Aufgaben | Erklärung  |
| :-------- | :-------- |
| Scheduling | Automatisches Bereitstellen von Container Instanzen.|
| Affinität/antiaffinität | Stellen Sie Container bereit, die sich nahe beieinander befinden, und unterstützen Sie die Verfügbarkeit und Leistung. |
| Systemüberwachung | Automatisches Erkennen und korrigieren von Fehlern.|
| Failover | Fehler beim automatischen erneuten Bereitstellen fehlerhafter Computer.|
| Skalierung | Fügen Sie Container Instanzen automatisch hinzu, um die Anforderung zu erfüllen.|
| Netzwerk | Verwalten Sie eine Netzwerk Überlagerung für die Container Kommunikation.|
| Dienstsuche | Aktivieren Sie Container, um sich gegenseitig zu suchen.|
| Parallele Upgrades | Inkrementelle Upgrades ohne Ausfallzeiten Bereitstellung koordinieren. Automatisches Rollback von problematischen Änderungen.|

Beachten Sie, wie orchestratoren die disposability-und Parallelitäts Prinzipien der [12-stufigen Anwendung](https://12factor.net/)akzeptieren, die weiter oben in diesem Kapitel erläutert wurden.

> *Faktor \# 9 gibt an, dass Dienst Instanzen verworfen werden sollten. Dadurch werden schnelle Startups bevorzugt, um Skalierbarkeits Chancen und ordnungsgemäße Herunterfahr Vorgänge zu verbessern, um das System in einem ordnungsgemäßen Zustand zu belassen. Docker-Container zusammen mit einem Orchestrator erfüllen diese Anforderung von Natur aus. "*

> *Faktor \# 8 gibt an, dass "Dienste für eine große Anzahl von kleinen identischen Prozessen (Kopien) horizontal hochskaliert werden, anstatt eine einzelne große Instanz auf dem leistungsstärksten verfügbaren Computer zentral hochzuskalieren."*

Obwohl mehrere containerorchestratoren vorhanden sind, ist [Kubernetes](https://kubernetes.io/docs/concepts/overview/what-is-kubernetes/) der de-facto-Standard für die Cloud-Native Welt. Es ist eine Portable, erweiterbare Open-Source-Plattform für die Verwaltung von Workloads in Containern.

Sie könnten eine eigene Instanz von Kubernetes hosten, aber dann sind Sie für die Bereitstellung und Verwaltung der Ressourcen zuständig, die komplex sein können. Die Azure-Cloud-Features Kubernetes als verwalteter Dienst, [Azure Kubernetes Service (AKS)](https://azure.microsoft.com/services/kubernetes-service/). Ein verwalteter Dienst ermöglicht es Ihnen, seine Features vollständig zu nutzen, ohne dass er installiert und gewartet werden muss.

Azure Kubernetes Services finden Sie im Detail Kapitel 2: *Skalieren von cloudbasierten Anwendungen*.

## <a name="backing-services"></a>Sichern von Diensten

Cloud-Native Systeme sind von vielen unterschiedlichen Ressourcen abhängig, z. b. Daten speichern, Nachrichten Brokern, Überwachung und Identitäts Diensten. Diese Dienste werden als [Sicherungsdienste](https://12factor.net/backing-services)bezeichnet.

 In Abbildung 1-7 werden viele gängige Unterstützungsdienste gezeigt, die von cloudbasierten Systemen genutzt werden.

![Allgemeine Unterstützungsdienste](./media/common-backing-services.png)

**Abbildung 1-7**. Allgemeine Unterstützungsdienste

Unterstützungsdienste Stufen das Prinzip der "Status Freiheit" der [zwölfstufigen Anwendung](https://12factor.net/)herauf, das weiter oben in diesem Kapitel erläutert wurde.

>*Faktor \# 6* gibt an, dass "jeder mikrodienst in einem eigenen Prozess ausgeführt werden soll, isoliert von anderen ausgelaufenden Diensten. Externalisieren Sie den erforderlichen Zustand zu einem Sicherungsdienst, z. b. einem verteilten Cache oder einem Datenspeicher.

Sie können Ihre eigenen Sicherungsdienste hosten, aber dann sind Sie für die Lizenzierung, Bereitstellung und Verwaltung dieser Ressourcen verantwortlich.

Cloudanbieter bieten eine umfangreiche Palette *verwalteter Sicherungsdienste.* Anstatt den Dienst zu besitzen, verwenden Sie ihn einfach. Der Anbieter betreibt die Ressource in der Skala und übernimmt die Verantwortung für Leistung, Sicherheit und Wartung. Überwachung, Redundanz und Verfügbarkeit sind in den Dienst integriert. Anbieter unterstützen Ihre verwalteten Dienste vollständig. Öffnen Sie ein Ticket, und beheben Sie das Problem.

Native cloudsysteme bevorzugen verwaltete Unterstützungsdienste von cloudanbietern. Die Einsparungen in Zeit und Arbeit sind hervorragend. Das Betriebsrisiko des Hostings ihrer eigenen und Probleme kann teuer werden.

Eine bewährte Vorgehensweise besteht darin, einen Sicherungsdienst als *angefügte Ressource*zu behandeln, die dynamisch an einen-Dienst mit Informationen (URL und Anmelde Informationen) gebunden ist, die in einer externen Konfiguration gespeichert sind. Dieser Leitfaden ist in der [zwölfstufigen Anwendung](https://12factor.net/)beschrieben, die weiter oben in diesem Kapitel erläutert wurde.

>*Faktor \# 4* gibt an, dass Unterstützungsdienste über eine adressierbare URL verfügbar gemacht werden sollen. Dadurch wird die Ressource von der Anwendung entkoppelt, sodass Sie austauschbar sein kann. "

>*Faktor \# 3* gibt an, dass "Konfigurationsinformationen aus dem-Unternehmens Dienst verschoben und durch ein Konfigurations Verwaltungs Tool außerhalb des Codes extern ausgelagert werden."

Bei diesem Muster kann ein Unterstützungsdienst ohne Codeänderungen angefügt und getrennt werden. Sie können einen-mikrodienst von QA in eine Stagingumgebung herauf Stufen. Sie aktualisieren die Konfiguration des-Webdiensts so, dass Sie auf die Unterstützungsdienste in der Stagingumgebung verweist, und fügen die Einstellungen über eine Umgebungsvariable in ihren Container

Cloudanbieter stellen APIs bereit, mit denen Sie mit ihren proprietären Unterstützungsdiensten kommunizieren können. Diese Bibliotheken Kapseln die Grundlagen und die Komplexität. Wenn Sie direkt mit diesen APIs kommunizieren, werden Sie Ihren Code eng mit dem Unterstützungsdienst verknüpfen. Es empfiehlt sich, die Implementierungsdetails der Anbieter-API zu isolieren. Stellen Sie eine Vermittlungs Schicht oder eine zwischen-API bereit, die generische Vorgänge für Ihren Dienst Code verfügbar macht. Diese lose Kopplung ermöglicht das Austauschen eines Sicherungs Dienstanbieter für einen anderen oder das Verschieben des Codes in einen anderen Public Cloud, ohne Änderungen am Haupt-Dienst Code vornehmen zu müssen.

Unterstützende Dienste werden in Kapitel 5, in der *Cloud Native Datenmuster*und in Kapitel 4, in der *Cloud Native Kommunikationsmuster*erläutert.

## <a name="automation"></a>Automation

Wie Sie gesehen haben, sind in der Cloud Native Systeme zum Erreichen von Geschwindigkeit und Agilität für die Entwicklung von Funktionen, Containern und modernen System Entwürfen konzipiert. Aber das ist nur ein Teil der Story. Wie stellen Sie die cloudumgebungen bereit, auf denen diese Systeme ausgeführt werden? Wie werden App-Features und Updates schnell bereitgestellt? Wie wird das vollständige Bild abgerundet?

Geben Sie die allgemein akzeptierte [Infrastruktur als Code](/azure/devops/learn/what-is-infrastructure-as-code)oder IAC ein.

Mit IAC automatisieren Sie die Platt Form Bereitstellung und die Anwendungs Bereitstellung. Sie wenden im Wesentlichen Software Entwicklungsverfahren wie Tests und Versionsverwaltung auf Ihre devops-Verfahren an. Ihre Infrastruktur und bereit Stellungen sind automatisiert, konsistent und wiederholbar.

### <a name="automating-infrastructure"></a>Automatisieren der Infrastruktur

Tools wie [Azure Resource Manager](/azure/azure-resource-manager/management/overview), TERRAFORM und die [Azure CLI](/cli/azure/)ermöglichen es Ihnen, deklarativ Skripts für die erforderliche cloudinfrastruktur zu erstellen. Ressourcennamen, Speicherorte, Kapazitäten und Geheimnisse sind parametrisiert und dynamisch. Das Skript wird mit Versions Angabe versehen und als Element des Projekts in die Quell Code Verwaltung eingecheckt. Sie rufen das Skript auf, um eine konsistente und wiederholbare Infrastruktur in Systemumgebungen bereitzustellen, wie z. b. QA, Staging und Produktion.

Im Hintergrund ist IAC idempotent, d. h., Sie können das gleiche Skript immer wieder ausführen, ohne Nebeneffekte zu haben. Wenn das Team eine Änderung vornehmen muss, wird das Skript bearbeitet und erneut ausgeführt. Nur die aktualisierten Ressourcen sind betroffen.

Im Artikel [Was ist Infrastructure as Code, wird](/azure/devops/learn/what-is-infrastructure-as-code)der Autor Sam Guckenheimer beschrieben, wie "Teams, die IAC implementieren, schnelle und skalierbare Umgebungen bereitstellt. Teams vermeiden die manuelle Konfiguration von Umgebungen und erzwingen Konsistenz, indem Sie den gewünschten Zustand ihrer Umgebungen über Code darstellen. Infrastruktur Bereitstellungen mit IAC sind wiederholbar und verhindern Lauf Zeit Probleme, die durch Konfigurations Abweichung oder fehlende Abhängigkeiten verursacht werden. Devops-Teams können mit einem einheitlichen Satz von Methoden und Tools zusammenarbeiten, um Anwendungen und deren unterstützende Infrastruktur schnell, zuverlässig und skalierbar bereitzustellen. "

### <a name="automating-deployments"></a>Automatisieren von bereit Stellungen

Die zuvor beschriebene [12-stufige Anwendung](https://12factor.net/)erfordert separate Schritte, wenn Sie abgeschlossenen Code in eine laufende Anwendung umwandeln.

> *Faktor \# 5* gibt an, dass "jedes Release eine strikte Trennung in den Build-, Release-und Lauf Phasen erzwingen muss. Jede sollte mit einer eindeutigen ID gekennzeichnet werden und die Möglichkeit des Rollbacks unterstützen. "

Moderne CI/CD-Systeme helfen dabei, dieses Prinzip zu erfüllen. Sie bieten separate Bereitstellungs Schritte und sorgen für konsistenten und qualitativ hochwertigen Code, der Benutzern problemlos zur Verfügung steht.

In Abbildung 1-8 wird die Trennung für den gesamten Bereitstellungs Prozess veranschaulicht.

![Schritte zur Bereitstellung in der CI/CD-Pipeline](./media/build-release-run-pipeline.png)

**Abbildung 1-8**. Bereitstellungs Schritte in einer CI/CD-Pipeline

Achten Sie in der vorherigen Abbildung besonders auf die Trennung von Aufgaben.

Der Entwickler erstellt ein Feature in der Entwicklungsumgebung und durchläuft dabei den sogenannten "inneren Schleifen Code", "ausführen" und "Debuggen". *Nach Abschluss* des Vorgangs wird dieser Code in ein Coderepository, wie z. b. GitHub, Azure devops oder Bitbucket, übermittelt.

Der Push löst eine Buildphase aus, die den Code in ein binäres artefaktelement umwandelt. Die Arbeit wird mit einer CI-Pipeline [(Continuous Integration)](https://martinfowler.com/articles/continuousIntegration.html) implementiert. Die Anwendung wird automatisch erstellt, getestet und verpackt.

Die Releasephase übernimmt das binäre artefaktelement, wendet externe Anwendungs-und Umgebungs Konfigurationsinformationen an und erzeugt eine unveränderliche Version. Das Release wird in einer bestimmten Umgebung bereitgestellt. Die Arbeit wird mit einer CD-Pipeline [(Continuous Delivery)](https://martinfowler.com/bliki/ContinuousDelivery.html) implementiert. Jedes Release sollte identifizierbar sein. Sie können Folgendes sagen: "diese Bereitstellung führt Release 2.1.1 der Anwendung aus."

Schließlich wird die freigegebene Funktion in der Ziel Ausführungsumgebung ausgeführt. Releases sind unveränderlich, was bedeutet, dass jede Änderung eine neue Version erstellen muss.

Wenn Sie diese Vorgehensweisen anwenden, haben Organisationen die Art und Weise entwickelt, wie Sie Software liefern Viele wurden von vierteljährlichen Releases zu bedarfsgesteuerten Updates verschoben. Das Ziel besteht darin, Probleme früh im Entwicklungszeitraum abzufangen, wenn diese kostengünstiger behoben werden. Wenn die Dauer zwischen Integrationen länger ist, werden die Kosten kostspieliger.  Aufgrund der Konsistenz im Integrationsprozess können Teams Codeänderungen häufiger durchführen, was zu einer besseren Zusammenarbeit und Software Qualität führt.

### <a name="azure-pipelines"></a>Azure Pipelines

Die Azure-Cloud enthält einen neuen CI/CD-Dienst mit dem Titel [Azure Pipelines](https://azure.microsoft.com/services/devops/pipelines/), der Teil des [Azure devops](https://azure.microsoft.com/services/devops/) -Angebots in Abbildung 1-9 ist.

![Azure Pipelines in devops](./media/devops-components.png)

**Abbildung 1-9**. Azure devops-Angebote

Azure Pipelines ist ein clouddienst, der Continuous Integration (CI) und Continuous Delivery (CD) kombiniert. Sie können Ihren Code automatisch testen, erstellen und an ein beliebiges Ziel senden.

Sie definieren die Pipeline im Code in einer YAML-Datei neben dem Rest des Codes für Ihre APP.

- Die Pipeline wird mit dem Code versioniert und folgt derselben Verzweigungs Struktur.
- Eine Überprüfung Ihrer Änderungen erzielen Sie durch Code Reviews in Pull Requests und Brancherstellungsrichtlinien.
- Jede Verzweigung, die Sie verwenden, kann die Buildrichtlinie durch Ändern der Datei Azure-Pipelines. yml anpassen.
- Die Pipeline Datei wird in die Versionskontrolle eingecheckt und kann bei einem Problem untersucht werden.

Der Azure Pipelines-Dienst unterstützt die meisten git-Anbieter und kann Bereitstellungs Pipelines für Anwendungen generieren, die auf den Plattformen Linux, macOS oder Windows geschrieben sind. Sie enthält Unterstützung für Java, .net, JavaScript, Python, PHP, go, Xcode und C++.

>[!div class="step-by-step"]
>[Zurück](introduction.md)
>[Weiter](candidate-apps.md)
