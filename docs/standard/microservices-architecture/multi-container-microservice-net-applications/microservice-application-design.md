---
title: Eine Microservice dienstorientierten Anwendung entwerfen
description: ".NET Microservices Architektur für Datenvolumes .NET-Anwendungen | Eine Microservice dienstorientierten Anwendung entwerfen"
keywords: Docker, Microservices, ASP.NET, Container
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 1e1dc919c7e35580576c86b4cf9872b4f8cea2c2
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2017
---
# <a name="designing-a-microservice-oriented-application"></a>Eine Microservice dienstorientierten Anwendung entwerfen

Dieser Abschnitt konzentriert sich auf das Entwickeln einer hypothetischen serverseitige Enterprise-Anwendung.

## <a name="application-specifications"></a>Spezifikationen der Anwendung

Die hypothetische Anwendung verarbeitet Anforderungen von Geschäftslogik ausführen, den Zugriff auf Datenbanken und Zurückgeben von HTML, JSON oder XML-Antworten. Es wird mitgeteilt, dass die Anwendung eine Vielzahl von Clients, einschließlich Desktopbrowsern mit Single Page Applications (SPAs), herkömmlichen Web-apps, mobile Web-apps und systemeigener mobiler apps unterstützen muss. Die Anwendung möglicherweise auch verfügbar machen eine API für Drittanbieter zu nutzen. Sie sollten auch integrieren Sie ihre Microservices oder externe Anwendungen asynchron ausgeführt wird, kann sein, damit Ansatz Stabilität von der Microservices bei teilfehler hilft.

Die Anwendung wird diese Typen von Komponenten umfassen:

-   Komponenten der Präsentation. Dies sind verantwortlich für die Behandlung von der Benutzeroberflächenautomatisierungs und Nutzung von remote-Diensten.

-   Domäne oder die Geschäftslogik. Dies ist die Domänenlogik der Anwendung.

-   Datenbank-Zugriffslogik. Dies umfasst die Datenzugriffskomponenten ist verantwortlich für den Zugriff auf Datenbanken (SQL oder NoSQL).

-   Integration von Anwendungslogik. Dies schließt einen Messagingkanal, hauptsächlich basierend auf nachrichtenbroker.

Die Anwendung erfordert für hohe Skalierbarkeit und die vertikale Subsysteme autonom, horizontal skalieren lässt, da bestimmte Subsysteme größere Skalierbarkeit als andere benötigen.

Die Anwendung muss in der Lage, in Umgebungen mit mehreren Infrastruktur (mehrere öffentliche Clouds und lokalen) bereitgestellt werden und im Idealfall sollte über Plattformen hinweg, verschieben Sie einfach von Linux zu Windows (oder umgekehrt).

## <a name="development-team-context"></a>Entwicklung Teamprojekt-verwaltungskontext

Außerdem wird vorausgesetzt, Folgendes im Zusammenhang mit den Entwicklungsprozess für die Anwendung:

-   Sie haben mehrere Dev Teams Fokussierung auf bestimmte geschäftliche Bereiche der Anwendung.

-   Neue Teammitglieder müssen schnell produktiv muss, und die Anwendung leicht zu verstehen und zu ändern.

-   Die Anwendung wird eine langfristige Entwicklung und Geschäftsregeln sich stetig ändernden aufweisen.

-   Sie benötigen gute langfristigen Verwaltbarkeit, was bedeutet, dass Flexibilität beim neuen Änderungen in der Zukunft zu implementieren, während mehrere Subsysteme mit minimalen Auswirkungen auf die andere Subsysteme aktualisieren kann.

-   Übung fortlaufende Integration und kontinuierliche Bereitstellung der Anwendung werden sollen.

-   Die Anwendung entwickelt möchten sich entwickelnder Technologie (Frameworks, Programmieren Sprachen, usw.) nutzen. Sie sollten keine vollständigen Migration der Anwendung vornehmen, wenn, neuen Technologien zu verschieben, da die, die zu hohe Kosten und die Vorhersehbarkeit und die Stabilität der Anwendung auswirken würde.

## <a name="choosing-an-architecture"></a>Auswählen einer Architektur

Was muss der Anwendungsarchitektur Bereitstellung? Die Spezifikationen für die Anwendung zusammen mit der Entwicklung Kontext angegeben, wird empfohlen, dass Sie die Anwendung von in autonomen Subsysteme in Form von zusammenarbeitenden Microservices und Container zu zerlegen, wobei ein Microservice Architekt sollten ist ein Container.

Bei diesem Ansatz implementiert jeden Dienst (Container) eine Reihe von zusammenhängenden und eng verwandte Funktionen. Beispielsweise kann eine Anwendung der Dienste, z. B. der Katalogdienst Sortierung Service, Dienst Warenkorb, Benutzerprofildienst usw. bestehen.

Microservices kommunizieren mithilfe der Protokolle wie HTTP (REST), aber auch asynchron (das AMQP) nach Möglichkeit, insbesondere wenn weitergeben aktualisiert mit integrationsereignisse.

Microservices werden entwickelt und als Container unabhängig voneinander bereitgestellt. Dies bedeutet, dass ein Entwicklungsteam entwickeln und Bereitstellen von einem bestimmten Microservice ohne Auswirkungen auf andere Subsysteme werden kann.

Jede Microservice verfügt über eine eigene Datenbank, sodass es vollständig von anderen Microservices entkoppelt werden. Bei Bedarf Konsistenz zwischen Datenbanken von anderen Microservices erfolgt mithilfe auf Anwendungsebene-integrationsereignisse (über einen logischen Ereignisbus), als im Befehl und Abfrage Verantwortung Segregation (CQRS) behandelt. Aus diesem Grund müssen die Einschränkungen Business eventuellen Konsistenz zwischen mehreren Microservices nutzen und zugehörige Datenbanken.

### <a name="eshoponcontainers-a-reference-application-for-net-core-and-microservices-deployed-using-containers"></a>eShopOnContainers: eine Verweis-Anwendung für .NET Core und Microservices bereitgestellt von Containern

Damit Sie sich die Architektur und den Technologien statt darum geht, eine hypothetic Business-Domäne, die Sie möglicherweise nicht bekannt konzentrieren können, haben wir eine bekannte Business-Domäne ausgewählt, nämlich eine vereinfachte eCommerce (e-Shop)-Anwendung, die stellt einen Katalog mit Produkte, die Bestellungen von Kunden verwendet, Bestand überprüft und führt andere Geschäftsfunktionen. Dieser Container-basierte Anwendungsquellcode steht in der [eShopOnContainers](http://aka.ms/MicroservicesArchitecture) GitHub-Repository.

Die Anwendung besteht aus mehreren Subsysteme, einschließlich mehrere Store UI-Front-Ends (eine Webanwendung und eine systemeigene mobile app), zusammen mit den Back-End-Microservices und Container für alle erforderlichen serverseitige Vorgänge. Abbildung 8 – 1 zeigt die Architektur der Anwendung Verweis.

![](./media/image1.png)

**Abbildung 8 – 1**. Die eShopOnContainers verweisen auf die Anwendung, die eine direkte Kommunikation von Client-zu-Microservice und den-Ereignisbus anzeigt

**Hostingumgebung**. In Abbildung 8 – 1, sehen Sie mehrere Container in einem einzelnen Docker-Host bereitgestellt. Das wäre die Groß-/Kleinschreibung bei der Bereitstellung für einen einzelnen Docker-Host mit der Docker-Befehl zu erstellen. Allerdings Domänenmodus unter Verwendung einer Orchestrator oder Container-Cluster, jeder Container in einen anderen Host (Knoten) ausgeführt werden konnte und einen beliebigen Knoten kann eine beliebige Anzahl von Containern, wie wir zuvor im Abschnitt Architektur erklärt ausgeführt werden.

**Kommunikationsarchitektur**. Die Anwendung eShopOnContainers verwendet zwei Kommunikationstypen, abhängig von der Art der funktionalen Aktion (Abfragen im Vergleich zu Updates und Transaktionen):

-   Direkte Kommunikation von Client-zu-Microservice. Für Abfragen und wird verwendet, wenn Update oder transaktionsbefehlen, die über die Client-apps zu akzeptieren.

-   Asynchrone Kommunikation, die ereignisbasierten. Dies erfolgt über eine Ereignisbus Updates über Microservices weitergegeben oder mit externen Anwendungen zu integrieren. Alle messaging-Broker-Infrastruktur-Technologie wie RabbitMQ oder mit höherer Service Bus wie Azure Service Bus, NServiceBus, MassTransit oder Brighter kann der-Ereignisbus implementiert werden.

Die Anwendung wird als eine Reihe von Microservices in Form von Containern bereitgestellt. Client-apps können mit diesen Containern kommunizieren sowie der Kommunikation zwischen Microservices. Wie bereits erwähnt, wird diese anfängliche Architektur eine direkte Kommunikation von Client-Microservice-Architektur verwendet, was bedeutet, dass eine Clientanwendung Anforderungen direkt an jede der Microservices ausführen kann. Jede Microservice verfügt über einen öffentlichen Endpunkt wie https://servicename.applicationname.companyname. Falls erforderlich, können jede Microservice einen anderen TCP-Port. In der Produktion, die URL der Microservices Lastenausgleich zugeordnet würde die Anforderungen auf die verfügbaren Microservice-Instanzen verteilt.

**Wichtiger Hinweis auf Vs-API-Gateway. Direkte Kommunikation in eShopOnContainers.** Wie im Abschnitt "Architektur" dieses Handbuchs erläutert, kann die direkte Kommunikation von Client-zu-Microservice Architektur Nachteile aufweisen, wenn Sie eine große und komplexe Microservice-basierte Anwendung erstellen. Doch kann dies ausreichend Platz für eine kleine Anwendung, z. B. in der eShopOnContainers, die zum Ziel hat eine einfachere erste konzentrieren Docker Container-basierte Anwendung Anwendungsstart, und möchten wir aber nicht um ein einzelnes monolithischen-API-Gateway zu erstellen, die auswirken kann die Microservices Entwicklung Autonomie.

Aber wenn Sie vorhaben, eine große Microservice-basierte Anwendung mit Dutzenden von Microservices entwerfen, es wird dringend empfohlen, die Sie berücksichtigen, dass die API-Gateway-Muster, wie wir im Architektur-Abschnitt erläutert.
Diese Entscheidung hinsichtlich der Architektur konnte umgestaltet werden soll, sobald zu produktionfertiges Anwendungen und Fassaden speziell vorgenommen Betrachtung der Remoteclients. Müssen mehrere benutzerdefinierte API-Gateways, abhängig von den Clientanwendungen Formfaktor Vorteile hinsichtlich der verschiedenen Datenaggregation pro Client-app bereitstellen kann, sowie können interne Microservices oder die APIs an den Client-apps ausblenden und dieser einzelnen Ebene zu autorisieren. 

Beachten Sie jedoch und wie bereits erwähnt, für große und monolithischen-API-Gateways, die Ihre Microservices Entwicklung Autonomie kill kann.

### <a name="data-sovereignty-per-microservice"></a>Daten Hoheit pro microservice

In der beispielanwendung jedes Microservice besitzt eine eigene Datenbank oder Daten von Quell- und jede Datenbank, oder -Datenquelle als einen anderen Container bereitgestellt wird. Diese Entscheidung wurde versucht, nur für Entwickler von GitHub den Code abrufen, Klonen Sie sie aus, und öffnen es in Visual Studio oder Visual Studio Code erleichtern. Oder alternativ erleichtert, Kompilieren die benutzerdefinierten Docker-Images, die mithilfe von .NET Core-CLI und dem Docker-Befehlszeilenschnittstelle und bereitstellen, und führen Sie sie in einer Entwicklungsumgebung Docker. In beiden Fällen Datenquellen Container für Daten mit können Entwickler erstellen und in wenigen Minuten bereitstellen, ohne Sie zur Bereitstellung einer externen Datenbank oder eine beliebige andere Datenquelle mit harte Abhängigkeiten auf Infrastruktur (Cloud oder lokal).

In einer realen produktionsumgebung für hohe Verfügbarkeit und Skalierbarkeit sollte die Datenbanken auf Datenbankservern in der Cloud oder lokal, aber nicht in Container basieren.

Aus diesem Grund die Zeiten der Bereitstellung für Microservices (und sogar für Datenbanken in dieser Anwendung) werden in Docker-Containern, und der Verweis-Anwendung wird von Multi-Container, die Microservices Prinzipien Verwaltungsteam.

### <a name="additional-resources"></a>Zusätzliche Ressourcen

-   **eShopOnContainers GitHub-Repository. Quellcode für die Anwendung Verweis**
    *https://aka.ms/eShopOnContainers/*

## <a name="benefits-of-a-microservice-based-solution"></a>Vorteile einer Microservice-basierten Lösung

Eine Microservice basierend Lösung wie folgt hat viele Vorteile:

**Jede Microservice ist relativ klein – einfach verwalten und entwickeln**. Dies gilt insbesondere in folgenden Fällen:

-   Es ist einfach ein Entwickler zu verstehen und raschen Einstieg in gute Produktivität.

-   Container starten schnelle, wodurch Entwickler produktiver.

-   Eine IDE wie Visual Studio kann kleinere Projekte schnell geladen werden Entwickler produktiver zu machen.

-   Jede Microservice kann entworfen, entwickelt und bereitgestellt werden, unabhängig von anderen Microservices, die Flexibilität bietet, da neue Versionen des Microservices häufig Bereitstellen einfacher ist.

**Es ist möglich, Dezentrales Skalieren einzelne Bereiche der Anwendung**. Z. B. möglicherweise die Catalog-Dienst oder die Warenkorb-Dienst, aber nicht der Bestellvorgang skaliert werden müssen. Eine Infrastruktur Microservices wird im Hinblick auf die Ressourcen verwendet, wenn out Skalierung, als wäre eine monolithische Architektur wesentlich effizienter sein.

**Sie können die Entwicklungsarbeit zwischen mehreren Teams aufteilen**. Jeder Dienst kann von einem einzelnen Entwicklungsteam im Besitz eines. Jedes Team kann verwalten, entwickeln, bereitstellen und skalieren ihren Dienst unabhängig von der Rest des Teams.

**Probleme sind stärker isolierte**. Wenn ein Problem in einem Dienst vorhanden ist, nur diesen Dienst wird anfänglich (außer wenn das falsche Design mit direkter Abhängigkeiten zwischen Microservices verwendet wird,) beeinträchtigt, und andere Dienste können weiterhin Anforderungen zu verarbeiten. Im Gegensatz dazu kann eine Gestörte Komponente in einer Bereitstellungsarchitektur mit monolithisch das gesamte System beenden insbesondere, wenn sie Ressourcen, z. B. einen Speicherverlust umfasst. Wenn ein Problem in einer Microservice aufgelöst wird, können Sie darüber hinaus nur die betroffenen Microservice bereitstellen, ohne den Rest der Anwendung beeinträchtigen.

**Sie können die neuesten Technologien**. Da Sie starten die Entwicklung von Diensten unabhängig und parallel verwendet werden (danken Container und .NET Core) ausführen können, können Sie beginnen, anstelle der neuesten Technologien und Frameworks ist auf einem älteren Stapel oder Framework für den gesamten hängen die Anwendung.

## <a name="downsides-of-a-microservice-based-solution"></a>Nachteile einer Microservice-basierten Lösung

Eine Microservice-basierten Lösung wie folgt hat auch einige Nachteile:

**Verteilte Anwendung**. Erhöht die Komplexität die Anwendung verteilen für Entwickler beim Entwerfen und erstellen die Dienste. Beispielsweise müssen Entwickler interservice Kommunikation mithilfe von Protokollen wie HTTP oder AMPQ, wodurch Komplexität für das Testen und Ausnahmebehandlung hinzugefügt implementieren. Darüber hinaus wird Latenz hinzugefügt, mit dem System.

**Bereitstellung komplexer**. Eine Anwendung, die Dutzende von Microservices Typen und hohe Skalierbarkeit (sie muss in der Lage, das viele Instanzen pro Dienst erstellen und Ausgleichen von diesen Diensten über viele Hosts) bedeutet, dass ein hohes Maß an Komplexität der Bereitstellung für IT-Betrieb und Verwaltung. Wenn Sie eine Microservice-orientierten-Infrastruktur (z. B. ein Orchestrator und Scheduler) nicht verwenden, kann zusätzliche Komplexität jedoch weitaus höher Entwicklungsarbeiten als Business-Anwendung selbst ist erforderlich.

**Atomarische Transaktionen**. Atomarische Transaktionen zwischen mehreren Microservices in der Regel sind nicht möglich. Die geschäftsanforderungen müssen eventuelle Konsistenz zwischen mehreren Microservices zu nutzen.

**Globale Ressourcenverbrauch erhöht** (Gesamter Arbeitsspeicher, Laufwerke und Netzwerkressourcen für alle Server oder Hosts). In vielen Fällen wird beim Ersetzen einer monolithischen-Anwendung mit einem Ansatz Microservices wird globale Ressourcen, die erforderlich sind, durch die neue Microservice-basierte Anwendung größer als die Infrastruktur Anforderungen der ursprünglichen Anwendung aufgrund eines monolithischen Verarbeitungsaufwand erforderlich. Dies ist, da die höhere Grad an Granularität und verteilte Dienste eher globale und Ressourcen benötigt. Wenn Sie die niedrigen Kosten von Ressourcen im Allgemeinen sowie über den Vorteil, dass die Möglichkeit, nur bestimmte Bereiche der Anwendung im Vergleich zur langfristigen Kosten bei monolithischen Anwendungen zu erweitern, die verbesserte Verwendung von Ressourcen ist jedoch normalerweise einen guten Kompromiss für große, Langfristige Anwendungen.

**Probleme bei der direkten Client‑to‑microservice Kommunikation**. Wenn die Anwendung mit Dutzenden von Microservices sehr lang ist, sind Probleme und Einschränkungen, wenn die Anwendung erfordert, dass die direkte Kommunikation von Client-zu-Microservice. Ein Problem ist ein potenziellen Konflikt zwischen den Anforderungen des Clients und die APIs, die von jeder der Microservices verfügbar gemacht werden. In bestimmten Fällen kann die Clientanwendung müssen viele separate Anforderungen, die Benutzeroberfläche zu verfassen kann über das Internet ineffizient sein und über eine mobile Netzwerk wäre unpraktisch. Aus diesem Grund sollte die Anforderungen von der Clientanwendung an das Back-End-System minimiert werden.

Ein anderes Problem direkte Client-zu-Microservice unterworfen ist, dass einige Microservices Protokolle verwendet werden kann, die nicht webfreundlichen sind. Ein Dienst kann einen binären Protokolls verwenden, während ein anderer Dienst AMQP-messaging verwenden kann. Diese Protokolle sind nicht Firewall‑friendly und intern verwendet werden. In der Regel sollte eine Anwendung Protokolle wie HTTP und WebSockets für die Kommunikation außerhalb der Firewall verwenden.

Noch ist ein weiterer Nachteil bei dieser Vorgehensweise direkten Client‑to‑service an, dass sie die Verträge für diese Microservices Umgestalten erschwert. Mit der Zeit sollten Entwickler ändern, wie das System in Dienste partitioniert wird. Sie können z. B. Zusammenführen von zwei Diensten oder einen Dienst in zwei oder mehrere Dienste unterteilt. Jedoch wenn Clients direkt mit den Diensten kommunizieren, kann diese Art der Umgestaltung ausführen Kompatibilität mit Client-apps unterbrechen.

Wie in der Architektur Abschnitt beim Entwerfen und Erstellen einer komplexen Anwendung, die basierend auf Microservices erwähnt, sollten Sie die Verwendung von mehreren differenzierte API-Gateways anstelle der direkten Client‑to‑microservice Kommunikation einfacher.

**Partitionieren der Microservices**. Schließlich wird eine weitere Herausforderung unabhängig davon, welchen Ansatz Sie Ihre Microservice-Architektur ausgeführt werden soll, wie eine End-to-End-Anwendung in mehrere Microservices partitioniert entscheiden. Wie im Abschnitt "Architektur" des Handbuchs erwähnt, gibt es verschiedene Techniken und Ansätze, die Sie ergreifen können. Im Wesentlichen müssen Sie Bereiche der Anwendung, die aus anderen Bereichen entkoppelt werden und bei denen eine geringe Anzahl von harte Abhängigkeiten, zu identifizieren. In vielen Fällen ist dies ausgerichtet Partitionierung Services durch die Groß-/Kleinschreibung verwenden. In der vorliegenden Anwendung e-Shop haben wir z. B. einen Sortierung Dienst, der für alle im Zusammenhang mit der Auftragsprozess Geschäftslogik zuständig ist. Wir haben auch die Catalog-Dienst und dem Warenkorb-Dienst, die andere Funktionen zu implementieren. Idealerweise sollte jeder Dienst nur eine kleine Gruppe von Aufgaben verfügen. Dieser Vorgang ähnelt einzelne Prinzip der Verantwortung (Policies, SRP) angewendet auf Klassen, das angibt, dass ein Grund für das Ändern von eine Klasse nur haben soll. In diesem Fall ist jedoch zu Microservices, sodass der Bereich größer als eine einzelne Klasse ausgeführt wird. Am häufigsten daran, verfügt über ein Microservice, vollständig autonome, End-to-End einschließlich Verantwortung für die eigene Datenquellen zu erhalten.

## <a name="external-versus-internal-architecture-and-design-patterns"></a>Externe und interne Architektur und Entwurf-Muster

Die externe Architektur ist die Microservice-Architektur, die von mehreren Dienst, befolgen im Abschnitt "Architektur" dieses Handbuchs beschriebenen Grundsätze zusammengesetzt. Je nach Art der einzelnen Microservice und unabhängig von der allgemeinen Microservice-Architektur, die Sie auswählen, es ist jedoch häufig und in einigen Fällen sinnvoll, verschiedene interne Architekturen haben, jeweils basieren auf unterschiedliche Muster für verschiedene Microservices. Die Microservices können auch verschiedene Technologien und Programmiersprachen. Abbildung 8 – 2 veranschaulicht diese Vielfalt an.

![](./media/image2.png)

**Abbildung 8-2**. Externe und interne Architektur und Entwurf

Z. B. in unserer *eShopOnContainers* Beispiel, den Katalog Basket und Benutzer Profil Microservices werden einfache (im Wesentlichen CRUD-Subsysteme). Ihre interne Architektur und Entwurf ist einfach. Allerdings könnte Sie andere Microservices, z. B. die Sortierung Microservice verfügen, die komplexer ist und sich stetig ändernden Geschäftsregeln mit einem hohen Grad an Komplexität der Domäne darstellt. In solchen Fällen sollten zum Implementieren von komplexeren Mustern in einer bestimmten Microservice, wie Sie sind mit Ansätze zum Domain driven Design (DDD) definiert, wie wir auf diese Weise werden der *eShopOnContainers* Sortierung Microservice. (Überprüfen wir diese DDD Muster im Abschnitt weiter unten, die die Implementierung von erklärt die *eShopOnContainers* Sortierung Microservice.)

Ein weiterer Grund für eine andere Technologie pro Microservice kann die Art der einzelnen Microservice sein. Beispielsweise ist es möglicherweise eher die Verwendung einen funktionalen Programmiersprache Ihrer Wahl, z. B. F\#, oder sogar eine anderen Sprache wie R aus, wenn AI und Machine learning-Domänen, anstelle einer stärker objektorientierten Programmiersprache wie C anvisierten\#.

Entscheidend ist, dass jede Microservice eine andere interne Architektur, die auf Grundlage der Design-Muster aufweisen kann. Nicht alle Microservices sollten implementiert werden, mithilfe von erweiterten DDD-Muster, da, die diese stark engineering werden würde. Auf ähnliche Weise komplexe Microservices mit Geschäftslogik sich stetig ändernden sollten nicht als CRUD-Komponenten implementiert werden, oder mit geringer Qualität Code annehmen kann.



## <a name="the-new-world-multiple-architectural-patterns-and-polyglot-microservices"></a>Die neue Welt: mehrere architektonische Muster und polyglot Microservices

Es gibt viele architektonische Muster von Softwarearchitekten und Entwickler verwendet. Im folgenden sind einige (Mischen Architektur Formatvorlagen und Architekturmuster):

-   Einfache CRUD, ein-Ebenen, Single-Ebene.

-   [Herkömmliche N-Ebenen](https://msdn.microsoft.com/en-us/library/ee658109.aspx#Layers).

-   [Domain-Driven Design N-Ebenen](https://blogs.msdn.microsoft.com/cesardelatorre/2011/07/03/published-first-alpha-version-of-domain-oriented-n-layered-architecture-v2-0/).

-   [Bereinigen der Architektur](https://8thlight.com/blog/uncle-bob/2012/08/13/the-clean-architecture.html) (wie in [eShopOnWeb](http://aka.ms/WebAppArchitecture))

-   [Befehls- und Abfragen Responsibility Segregation](https://martinfowler.com/bliki/CQRS.html) (CQRS).

-   [Ereignisgesteuerte Architektur](https://en.wikipedia.org/wiki/Event-driven_architecture) (EDA).

Sie können auch mit vielen Technologien und Sprachen, z. B. ASP.NET Core Web-APIs, NancyFx, ASP.NET Core SignalR (verfügbar mit .NET Core 2), F Microservices erstellen\#, Node.js, Python, Java, C++, GoLang und vieles mehr.

Der wichtige Punkt ist, dass keine bestimmte Architekturmuster oder Stil noch auf eine bestimmte Technologie für alle Situationen geeignet ist. Abbildung 8 – 3 zeigt einige Ansätze und -Technologien (jedoch nicht in einer bestimmten Reihenfolge), die in verschiedenen Microservices verwendet werden konnte.

![](./media/image3.png)

**Abbildung 8 – 3**. Mit mehreren architektonische Muster und die polyglot Microservices Welt

Siehe besteht Abbildung 8 – 3, in Anwendungen viele Microservices (begrenzt Kontexten in Domain driven Design Terminologie oder einfach "Subsysteme" als autonome Microservices) jeder Microservice auf andere Weise implementiert werden kann. Jede möglicherweise haben eine andere Architekturmuster und andere Sprachen und Datenbanken je nach der Anwendungsverzeichnis ist, geschäftlichen Anforderungen und Prioritäten verwenden. In einigen Fällen kann die Microservices ähnlich sein. Aber das ist nicht in der Regel der Fall, da jedes Subsystem Kontextgrenze und Anforderungen in der Regel unterschiedlich sind.

Z. B. möglicherweise für eine einfache Anwendung der CRUD-Wartung, es nicht sinnvoll, Entwerfen und implementieren DDD-Muster. Für Ihre Domäne Core oder Kerngeschäft, müssen Sie jedoch möglicherweise anzuwendende komplexere Mustern um Business Komplexität mit sich stetig ändernden Geschäftsregeln konfigurieren.

Insbesondere, wenn Sie mit großen Anwendungen aus, das mehrere Subsysteme arbeiten, sollten Sie ein Architektur für einmaliges auf oberster Ebene basierend auf einem einzelnen Architekturmuster nicht anwenden. Z. B. CQRS nicht als eine der obersten Ebene Architektur für eine gesamte Anwendung angewendet werden soll, aber für eine bestimmte Gruppe von Diensten nützlich sein.

Es ist kein Allheilmittel oder ein Muster richtigen Architektur für jeden angegebenen Fall. Sie können nicht "eine Architektur Muster zum Regel" alle "." verwenden. Je nach Prioritäten der einzelnen Microservice müssen Sie einen anderen Ansatz für jede, auswählen, wie in den folgenden Abschnitten erläutert.


>[!div class="step-by-step"]
[Vorherigen] (index.md) [weiter] (Data-driven-Crud-microservice.md)
