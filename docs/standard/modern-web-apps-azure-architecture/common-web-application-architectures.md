---
title: Häufig verwendete Webanwendungsarchitekturen
description: Entwerfen moderner Webanwendungen mit ASP.NET Core und Microsoft Azure | Häufig verwendete Webanwendungsarchitekturen
author: ardalis
ms.author: wiwagn
ms.date: 10/06/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: dc5580d38ac29a5e923a4b7d84f9d7e077d5cdb2
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
#<a name="common-web-application-architectures"></a>Häufig verwendete Webanwendungsarchitekturen

> „Wenn Sie denken, dass eine gute Architektur viel Geld kostet, dann haben Sie noch nicht mit einer schlechten gearbeitet.“  
> _– Brian Foote und Joseph Yoder_

## <a name="summary"></a>Zusammenfassung

Die meisten herkömmlichen .NET-Anwendungen werden als einzelne Einheiten bereitgestellt, die einer ausführbaren Datei oder einer Webanwendung entsprechen, die innerhalb einer IIS-Anwendungsdomäne ausgeführt wird. Dabei handelt es sich um das wohl einfachste Bereitstellungsmodell, das sich gut für interne und kleinere öffentliche Anwendungen eignet. Allerdings eignet sich für die meisten wichtigen Geschäftsanwendungen sogar mit dieser einzelnen Bereitstellungseinheit die logische Unterteilung in mehrere Schichten.

## <a name="what-is-a-monolithic-application"></a>Was sind monolithische Anwendungen?

Monolithische Anwendungen sind in Bezug auf ihr Verhalten vollkommen unabhängig. Sie interagieren zwar möglichweise mit anderen Diensten oder Datenspeichern, während sie Vorgänge ausführen, aber der Hauptbestandteil ihres Verhaltens liegt in ihren eigenen Prozessen, und die gesamte Anwendung wird in der Regel als einzelne Einheit bereitgestellt. Wenn eine solche Anwendung eine horizontale Skalierung vornehmen muss, wird in der Regel die gesamte Anwendung auf mehreren Servern oder virtuellen Computern dupliziert.

## <a name="all-in-one-applications"></a>All-in-One-Anwendungen

Jede Anwendungsarchitektur muss mindestens ein Projekt umfassen. In dieser Architektur ist die gesamte Logik der Anwendung in nur einem Projekt enthalten. Außerdem wird sie in nur eine Assembly kompiliert und als einzelne Einheit bereitgestellt.

Wenn ein neues ASP.NET Core-Projekt erstellt wird, stellt dieses anfangs immer einen All-in-One-Monolith dar. Dabei macht es keinen Unterschied, ob es über Visual Studio oder die Befehlszeile erstellt wird. Dieser Monolith enthält das gesamte Verhalten der Anwendung, einschließlich der Darstellungs-, Geschäfts- und Datenzugriffslogik. In Abbildung 5-1 wird die Dateistruktur einer App dargestellt, die aus einem Projekt besteht.

**Abbildung 5-1.** Eine ASP.NET Core-App, die nur aus einem Projekt besteht

![](./media/image5-1.png)

Wenn eine App nur aus einem Projekt besteht, wird das Prinzip „Separation of Concerns“ durch die Verwendung von Ordnern unterstützt. Die Standardvorlage enthält separate Ordner für Verantwortlichkeiten von MVC-Mustern für Modelle, Ansichten und Controller sowie zusätzliche Ordner für Daten und Dienste. Wenn Sie diese Vorlage verwenden, sollten Darstellunsgdetails weitestgehend auf den Ansichtenordner (Views) beschränkt sein, und Implementierungsdetails zum Datenzugriff sollten auf Klassen beschränkt sein, die im Datenordner (Data) gespeichert werden. Die Geschäftslogik sollte in Diensten und Klassen gespeichert sein, die im Modellordner (Models) enthalten sind.

Diese monolithische Projektmappe, die aus nur einem Projekt besteht, ist zwar sehr einfach strukturiert, weist aber auch einige Nachteile auf. Wenn der Umfang des Projekts ausgeweitet wird, entstehen auch immer mehr Dateien und Ordner. Elemente, die die Benutzeroberfläche betreffen (z.B. Modelle, Ansichten und Controller), sind in unterschiedlichen Ordnern gespeichert, die nicht gemeinsam in alphabetischer Reihenfolge sortiert sind. Dieses Problem wird noch größer, wenn zusätzliche Konstrukte auf Benutzeroberflächenebene wie Filter oder ModelBinders-Elemente zu ihren jeweiligen Ordnern hinzugefügt werden. Die Geschäftslogik ist auf die Modell- und Dienstordner (Models und Services) aufgeteilt, und es gibt keinen Anhaltspunkt dafür, welche Klassen in welchen Ordnern von welchen anderen Elementen abhängig sein sollen. Dadurch, dass auf Projektebene keine Sortierung vorgenommen wird, wird der Code häufig unübersichtlich, und es entsteht sogenannter [Spaghetticode](http://deviq.com/spaghetti-code/).

Um diese Probleme zu umgehen, greifen Entwickler häufig auf die Möglichkeit zurück, Anwendungen in Projektmappen mit mehreren Projekten auszuweiten. In diesen Projektmappen ist dann jedes Projekt auf einer bestimmten *Schicht* einer Anwendung gespeichert.

## <a name="what-are-layers"></a>Was sind Schichten?

Wenn eine Anwendung immer komplexer wird, können Sie dagegen vorgehen, indem Sie sie anhand ihrer Zuständigkeiten und Aufgaben aufteilen. Dieses Prinzip wird als „Separation of Concerns“ (Trennung von Belangen“ bezeichnet und hilft Ihnen dabei, die Codebasis zu ordnen, damit Sie problemlos feststellen können, an welcher Stelle bestimmte Funktionen implementiert wurden. Die Strukturierung Ihres Codes ist aber nicht der einzige Vorteil einer aus Schichten bestehenden Architektur.

Wenn Sie Code in Schichten unterteilen, können häufig verwendete grundlegende Funktionen in der gesamten Anwendung wiederverwendet werden. Dies hat den Vorteil, dass Sie weniger Code schreiben müssen und die Anwendung für eine Implementierung standardisiert wird, was dem Don‘t Repeat Yourself-Prinzip entspricht.

Wenn eine Architektur aus Schichten besteht, können Anwendungen Einschränkungen für die Kommunikation zwischen den einzelnen Schichten erzwingen. Dies erleichtert die Kapselung. Wenn eine Schicht geändert oder ersetzt wird, sollten nur die Schichten betroffen sein, die mit dieser zusammenarbeiten. Wenn Sie einschränken, welche Schichten voneinander abhängig sind, können die Auswirkungen von Änderungen verringert werden, sodass eine einzige Änderung nicht die gesamte Anwendung betrifft.

Schichten (und die Kapselung) vereinfachen das Ersetzen von Funktionen innerhalb der Anwendung. Möglicherweise verwendet z.B. eine Anwendung anfangs ihre eigene SQL Server-Datenbank als Persistenzspeicher. Sie können sich dann später aber immer noch dafür entscheiden, eine cloudbasierte Persistenzstrategie oder eine Web-API zu verwenden. Wenn die Anwendungen ihre Persistenzimplementierungen innerhalb einer logischen Schicht kapseln, kann diese SQL Server-spezifische Schicht durch eine neue Implementierung derselben öffentlichen Schnittstelle ersetzt werden.

Neben der Möglichkeit, Implementierungen auszutauschen, um möglichen zukünftigen Änderungen von Anforderungen vorzubeugen, können diese mithilfe von Anwendungsschichten auch zu Testzwecken ausgetauscht werden. Die Schichten können während der Tests durch falsche Implementierungen ersetzt werden, die bekannte Antworten auf Anforderungen bereitstellen, sodass Sie keine Tests mehr schreiben müssen, die mit der echten Daten- oder Benutzeroberflächenschicht der Anwendung arbeiten. Dadurch können Tests einfacher geschrieben und im Vergleich zu Tests der echten Infrastruktur der Anwendung schneller ausgeführt werden.

Das Erstellen logischer Schichten ist eine häufig verwendete Technik zum Verbessern der Strukturierung von Code in Unternehmensanwendungen. Es gibt mehrere Möglichkeiten, Code in Schichten zu strukturieren.

> [!NOTE]
> *Schichten* stellen eine logische Unterteilung aller Bestandteile einer App dar. Wenn die Anwendungslogik physisch auf separate Server oder Prozesse verteilt wird, werden diese separaten Bereitstellunsgsziele als *Ebenen* bezeichnet. Die Verwendung einer Anwendung mit mehreren Schichten, die für eine einzelne Schicht bereitgestellt wird, ist möglich und wird häufig angewandt.

## <a name="traditional-n-layer-architecture-applications"></a>Traditionelle Architektur einer Anwendung mit mehreren Schichten

In Abbildung 5-2 wird die am häufigsten verwendete Unterteilung einer Anwendungslogik in Schichten dargestellt.

**Abbildung 5-2.** Typische Anwendungsschichten

![](./media/image5-2.png)

Diese Schichten werden häufig mit den englischen Abkürzungen UI für User Interface (Benutzeroberfläche), BLL für Business Logic Layer (Schicht der Geschäftslogik) und DAL für Data Access Layer (Schicht für den Datenzugriff) bezeichnet. Wenn diese Architektur verwendet wird, senden Benutzer Anforderungen über die Benutzeroberflächenschicht, die nur mit der BLL interagiert. Die BLL kann wiederum die DAL für Anforderungen hinsichtlich des Datenzugriffs aufrufen. Die UI-Schicht sollte keine direkten Anforderungen an die DAL senden oder direkt mithilfe anderer Methoden mit der Persistenz interagieren. Gleichzeitig sollte die BLL nur über die DAL mit der Persistenz interagieren. Auf diese Weise wird jeder Schicht eine individuelle bekannte Verantwortlichkeit zugewiesen.

Dieser traditionelle Ansatz zum Erstellen von Schichten hat allerdings den Nachteil, dass Abhängigkeiten zur Kompilierzeit von oben nach unten ausgeführt werden. Das heißt, die UI-Schicht ist von der BLL abhängig, die wiederum von der DAL abhängig ist. Das wiederum bedeutet, dass die BLL, die in der Regel die wichtigste Logik innerhalb der Anwendung aufweist, von den Implementierungsdetails zum Datenzugriff abhängig ist (und dadurch häufig auch eine Datenbank benötigt). Das Testen einer Geschäftslogik in einer Architektur wie dieser gestaltet sich häufig als schwierig und erfordert eine Testdatenbank. Sie können dieses Problem wie im nächsten Abschnitt beschrieben mit dem Dependency Inversion-Prinzip angehen.

In Abbildung 5-3 wird eine Projektmappe als Beispiel dargestellt, in der die Anwendung anhand von Zuständigkeiten bzw. Schichten in drei Projekte unterteilt wird.

**Abbildung 5-3.** Eine einfache monolithische Anwendung mit drei Projekten

![](./media/image5-3.png)

Obwohl diese Anwendung aus Strukturierungsgründen mehrere Projekte verwendet, wird sie als einzelne Einheit bereitgestellt und ihre Clients interagieren mit ihr wie mit einer einzelnen Web-App. Dies vereinfacht die Bereitstellung. In Abbildung 5-4 wird dargestellt, wie eine solche App unter Verwendung von Windows Azure gehostet werden kann.

![](./media/image5-4.png)

**Abbildung 5-4.** Einfache Bereitstellung einer Azure-Web-App

Wenn die Anforderungen an eine App höher werden, ist möglicherweise eine komplexere und robustere Bereitstellungslösung erforderlich. In Abbildung 5-5 ist ein Beispiel einer komplexeren Bereitstellung dargestellt, die mehrere zusätzliche Funktionen unterstützt.

![](./media/image5-5.png)

**Abbildung 5-5.** Bereitstellen einer Web-App in Azure App Service

Innerhalb der Anwendung verbessert diese Unterteilung in mehrere Projekte anhand von Zuständigkeiten deren Verwaltbarkeit.

Diese Einheit kann zentral oder horizontal hochskaliert werden, um die cloudbasierte bedarfsgesteuerte Skalierbarkeit zu nutzen. Beim zentralen Hochskalieren werden zusätzliche CPU, zusätzlicher Arbeitsspeicher, zusätzlicher Speicherplatz auf dem Datenträger oder andere Ressourcen zu dem Server bzw. den Servern hinzugefügt, der bzw. die Ihre App hosten. Beim horizontalen Hochskalieren werden zusätzliche Instanzen der Server hinzugefügt. Dabei macht es keinen Unterschied, ob es sich um physische Server oder virtuelle Computer handelt. Wenn Ihre App auf mehreren Instanzen gehostet wird, wird ein Lastenausgleich vorgenommen, um individuellen App-Instanzen Anforderungen zuzuweisen.

Der einfachste Ansatz zum Skalieren einer Webanwendung in Azure ist das manuelle Konfigurieren einer Skalierung im App Service-Plan der Anwendung. In Abbildung 5-6 wird die Anzeige des Azure-Dashboards dargestellt, über die Sie konfigurieren können, wie viele Instanzen einer App zugrunde liegen.

![](./media/image5-6.png)

**Abbildung 5-6.** Skalieren des App Service-Plans in Azure

## <a name="clean-architecture"></a>Clean Architecture

Anwendungen, die den Prinzipien Dependency Inversion und Domain-Driven Design (DDD) folgen, weisen alle eine ähnliche Architektur auf. Diese Architektur wurde in den vergangenen Jahren unterschiedlich benannt. Zuerst wurde diese Architektur als „Hexagonal Architecture“ bezeichnet. Darauf folgte der Begriff „Ports-and-Adapters“. Heutzutage spricht man aber eher von [Onion Architecture](http://jeffreypalermo.com/blog/the-onion-architecture-part-1/) bzw. [Clean Architecture](https://8thlight.com/blog/uncle-bob/2012/08/13/the-clean-architecture.html). In diesem E-Book wird der Begriff „Clean Architecture“ als Grundlage zum Beschreiben dieser Architektur verwendet.

> [!NOTE]
> Die Clean Architecture kann sowohl für Anwendungen erstellt werden, die dem DDD-Prinzip folgen, als auch für Anwendungen, die diesem nicht entsprechen. Wenn das DDD-Prinzip angewendet wird, kann die Architektur als „Clean DDD Architecture“ bezeichnet werden.

In der Clean Architecture sind die Geschäftslogik und das Anwendungsmodell im Kern der Anwendung enthalten. Es wird dann das Prinzip Dependency Inversion angewendet, bei dem die Geschäftslogik nicht mehr vom Datenzugriff oder anderen Aufgaben, die die Infrastruktur betreffen, abhängig ist. Stattdessen sind die Informationen zur Infrastruktur und Implementierung vom Anwendungskern abhängig. Dafür werden Abstraktionen oder Schnittstellen im Anwendungskern definiert und anschließend anhand von Typen implementiert, die in der Infrastrukturschicht definiert werden. Diese Architektur wird häufig in Kreisringen dargestellt, die dem Aufbau einer Zwiebel ähneln. In Abbildung 5-X wird ein Beispiel dargestellt, mit dem die Architektur dargestellt werden kann.

![](./media/image5-7.png)

**Abbildung 5-7.** Clean Architecture: „Zwiebelansicht“

In diesem Diagramm beziehen sich alle Abhängigkeiten auf den inneren Kreisring, also auf den Anwendungskern. Der Anwendungskern verfügt also nicht über Abhängigkeiten von anderen Anwendungsschichten. Die Entitäten und Schnittstellen der Anwendung stehen im Mittelpunkt. Domänendienste, die in der Regel Schnittstellen implementieren, die im inneren Kreisring definiert sind, befinden sich am äußeren Rand des Anwendungskerns. Außerhalb des Anwendungskerns sind sowohl die Benutzeroberfläche als auch die Infrastrukturschichten zwar vom Anwendungskern, aber nicht (unbedingt) voneinander abhängig.

In Abbildung 5-X wird ein herkömmlicheres horizontales Schichtendiagramm dargestellt, das die Abhängigkeit zwischen Benutzeroberfläche und anderen Schichten besser darstellt.

![](./media/image5-8.png)

**Abbildung 5-8.** Clean Architecture: Ansicht mit horizontalen Schichten

Beachten Sie, dass die Pfeile mit durchgezogener Linie Abhängigkeiten zur Kompilierzeit darstellen. Die Pfeile mit gestrichelten Linien stellen Abhängigkeiten dar, die nur zur Laufzeit bestehen. Unter Verwendung der Clean Architecture funktioniert die UI-Schicht nur mit Schnittstellen, die zur Kompilierzeit im Anwendungskern definiert werden. Im Idealfall sollten diese außerdem nicht über Informationen zu den in der Infrastrukturschicht definierten Implementierungstypen verfügen. Zur Laufzeit sind diese Implementierungstypen jedoch erforderlich, damit die App ausgeführt werden kann. Daher müssen Sie definiert und über Dependency Injection mit den Schnittstellen des Anwendungskerns verbunden sein.

In Abbildung 5-9 wird eine detailliertere Ansicht der Architektur einer ASP.NET Core-Anwendung dargestellt, die anhand dieser Empfehlungen erstellt wurde.

![ASP.NET Core-Architektur](./media/image5-9.png)

**Abbildung 5-9.** Diagramm der ASP.NET Core-Architektur, die dem Prinzip der Clean Architecture folgt

Da der Anwendungskern nicht von der Infrastrukturschicht abhängig ist, ist es leicht, automatisierte Komponententests für diese Schicht zu schreiben. In den Abbildungen 5-10 und 5-11 wird dargestellt, wie Tests mit dieser Architektur in Einklang gebracht werden können.

![UnitTestCore](./media/image5-10.png)

**Abbildung 5-10.** Isolierter Komponententest des Anwendungskerns

![IntegrationTests](./media/image5-11.png)

**Abbildung 5-11.** Integrationstest von Infrastrukturimplementierungen mit externen Abhängigkeiten

Da die UI-Schicht nicht über direkte Abhängigkeiten von im Infrastrukturprojekt definierten Typen verfügt, können Implementierungen leicht ausgetauscht werden. Dadurch kann das Testen vereinfacht werden, oder sich ändernde Anwendungsanforderungen lassen sich leichter umsetzen. Durch die in ASP.NET Core integrierte Verwendung von und Unterstützung für Dependency Injection eignet sich diese Architektur besonders gut zum Strukturieren wichtiger monolithischer Anwendungen.

Bei monolithischen Anwendungen werden Projekte für den Anwendungskern, die Infrastruktur und die Benutzeroberfläche als eine einzelne Anwendung ausgeführt. Die Anwendungsarchitektur zur Laufzeit sieht in etwa wie in Abbildung 5-12 dargestellt aus.

![ASP.NET Core-Architektur 2](./media/image5-12.png)

**Abbildung 5-12.** Beispiel für die Laufzeitarchitektur einer ASP.NET Core-App

### <a name="organizing-code-in-clean-architecture"></a>Strukturieren von Code anhand des Clean Architecture-Prinzips

In einer gemäß der Clean Architecture erstellten Projektmappe verfügt jedes Projekt über klare Zuständigkeiten. Daher gehören zu jedem Projekt bestimmte Typen, und häufig entsprechen Ordner im jeweiligen Projekt diesen Typen.

Der Anwendungskern enthält das Geschäftsmodell, das wiederum Entitäten, Dienste und Schnittstellen umfasst. Diese Schnittstellen umfassen Abstraktionen für Vorgänge, die unter Verwendung der Infrastruktur ausgeführt werden. Damit sind z.B. der Datenzugriff, der Zugriff auf Dateisysteme und Netzwerkaufrufe gemeint. Gelegentlich müssen für diese Schicht installierte Dienste und Schnittstellen mit Typen zusammenarbeiten, bei denen es sich nicht um Entitäten handelt und die nicht von der Benutzeroberfläche oder der Infrastruktur abhängig sind. Diese Dienste und Schnittstellen können als einfache Datentransferobjekte (Data Transfer Objects, DTOs) definiert sein.

> ### <a name="application-core-types"></a>Typen des Anwendungskerns
> -   Entitäten (Klassen von Geschäftsmodellen, die dauerhaft gespeichert werden)
> -   Schnittstellen
> -   Dienste
> -   DTOs

Das Infrastrukturprojekt umfasst in der Regel Implementierungen für den Datenzugriff. In einer herkömmlichen ASP.NET Core-Webanwendung umfasst dies die Entity Framework-DbContext-Klasse, jegliche EF Core-Migrationen, die definiert wurden, und Klassen für Implementierungen des Datenzugriffs. Die beste Möglichkeit, Implementierungscode für den Datenzugriff zu implementieren, stellt das [Entwurfsmuster Repository](http://deviq.com/repository-pattern/) dar.

Das Infrastrukturprojekt sollte neben Implementierungen für den Datenzugriff Implementierungen von Diensten enthalten, die mit verschiedenen Bestandteilen der Infrastruktur interagieren. Diese Dienste sollten im Anwendungskern definierte Schnittstellen implementierten. Daher sollte im Infrastrukturprojekt ein Verweis auf das Anwendungskernprojekt enthalten sein.

> ### <a name="infrastructure-types"></a>Typen der Infrastruktur
> -   EF Core-Typen (DbContext, Migrationen)
> -   Implementierungstypen für den Datenzugriff (Repositorys)
> -   Infrastrukturspezifische Dienste (FileLogger, SmtpNotifier etc.)

Die UI-Schicht in einer ASP.NET Core MVC-Anwendung stellt den Einstiegspunkt für die Anwendung dar und fungiert als ein ASP.NET Core MVC-Projekt. Dieses Projekt sollte auf das Anwendungskernprojekt verweisen, und dessen Typen sollten ausschließlich über im Anwendungskern definierte Schnittstellen mit der Infrastruktur interagieren. In der UI-Schicht sollten keine direkte Instanziierung oder statische Aufrufe von Typen von Infrastrukturschichten zugelassen werden.

> ### <a name="ui-layer-types"></a>Typen der UI-Schicht
> -   Controller
> -   Filter
> -   Ansichten
> -   ViewModels
> -   Startup

Die Startup-Klasse ist für das Konfigurieren von Anwendungen und für das Verknüpfen von Implementierungstypen mit Schnittstellen zuständig. Dadurch kann zur Laufzeit erfolgreich Dependency Injection angewendet werden.

> [!NOTE]
> Wenn Sie Dependency Injection in ConfigureServices in der Startup.cs-Datei des UI-Projekts durchführen möchten, muss das Projekt möglicherweise auf das Infrastrukturprojekt verweisen. Diese Abhängigkeit kann problemlos mithilfe eines benutzerdefinierten Dependency Injection-Containers entfernt werden. Im Hinblick auf das hier aufgeführte Beispiel ist es die einfachste Lösung, wenn Sie zulassen, dass das UI-Projekt auf das Infrastrukturprojekt verweist.

## <a name="monolithic-applications-and-containers"></a>Monolithische Anwendungen und Container 

Sie können eine einzelne, monolithisch bereitgestellte Webanwendung oder einen Webdienst erstellen und als Container bereitstellen. Die Anwendung ist in ihrem Inneren möglicherweise nicht monolithisch strukturiert, sondern in mehrere Bibliotheken, Komponenten oder Schichten unterteilt. Extern ist sie ein einzelner Container – z.B. ein einzelner Prozess, eine einzelne Webanwendung oder ein einzelner Dienst.

Stellen Sie einen einzelnen Container bereit, der diese Anwendung darstellt, um dieses Modell zu verwalten. Fügen Sie zum Skalieren einfach weitere Kopien mit einem vorangestellten Lastenausgleich hinzu. Die Einfachheit stammt aus der Verwaltung einer einzelnen Bereitstellung in einem einzelnen Container oder virtuellen Computer.

![](./media/image5-13.png)

Sie können, wie in Abbildung 5-X veranschaulicht, mehrere Komponenten, Bibliotheken oder interne Schichten in jeden Container einschließen. Allerdings kann dieses monolithische Muster zu einem Konflikt mit dem Containerprinzip *Jeder Container hat nur eine Aufgabe, die er in einem Prozess ausführt* führen.

Der Nachteil dieses Ansatzes wird offensichtlich, wenn die Anwendung wächst und skaliert werden muss. Wenn die gesamte Anwendung skaliert werden kann, ist dies kein Problem. In den meisten Fällen stellen jedoch nur einige Teile der Anwendung Engpässe dar, die eine Skalierung erfordern, während andere Komponente weniger häufig verwendet werden.

Wenn Sie das gewöhnliche eCommerce-Beispiel verwenden, müssen Sie sehr wahrscheinlich die Komponente für die Produktinformationen skalieren. Viele Kunden suchen Produkte erst und kaufen sie anschließend. Mehr Kunden verwenden Ihren Warenkorb als die Zahlungspipeline. Weniger Kunden fügen Kommentare hinzu oder zeigen ihren Bestellungsverlauf an. Und Sie haben möglicherweise nur eine Handvoll Mitarbeiter in einer bestimmten Region, die den Inhalt und die Marketingkampagnen verwalten müssen. Wenn der monolithische Entwurf skaliert wird, wird der gesamte Code mehrmals bereitgestellt.

Zusätzlich zu dem Problem, dass alle Komponenten skaliert werden müssen, erfordern Änderungen einer einzelnen Komponente einen erneuten Test der gesamten Anwendung und eine vollständige erneute Bereitstellung aller Instanzen.

Der monolithische Ansatz wird häufig verwendet, und viele Organisationen arbeiten mit dieser Architektur. Viele von ihnen erzielen damit akzeptable Ergebnisse, aber andere stoßen an ihre Grenzen. Viele Unternehmen haben ihre Anwendungen unter Verwendung dieses Modells entworfen, da Tools und Infrastruktur schon seit Jahren zu komplex für die Erstellung einer dienstorientierten Architektur (SOA) sind. Sie haben die Notwendigkeit nicht erkannt, etwas zu ändern — bis die Anwendung gewachsen ist. Wenn Sie an die Grenzen des monolithischen Ansatzes stoßen, ist der nächste logische Schritt das Aufteilen der App, damit diese Container und Microservices besser nutzen kann.

![](./media/image5-14.png)

Monolithische Anwendungen in Microsoft Azure können mithilfe von dedizierten VMs für jede Instanz bereitgestellt werden. Sie können die VMs problemlos skalieren, wenn Sie [Azure VM Scale Sets](https://docs.microsoft.com/azure/virtual-machine-scale-sets/) verwenden. [Azure App Service](https://azure.microsoft.com/services/app-service/) kann auch monolithische Anwendungen ausführen und Instanzen problemlos skalieren, ohne dass die VMs verwaltet werden müssen. Azure App Services kann ebenfalls einzelne Instanzen von Docker-Containern ausführen, was die Bereitstellung vereinfacht. Wenn Sie Docker verwenden, können Sie eine einzelne VM als Docker-Host bereitstellen und mehrere Instanzen ausführen. Wenn Sie wie in Abbildung 5-14 dargestellt den Azure Balancer verwenden, können Sie die Skalierung verwalten.

Die Bereitstellung auf den verschiedenen Hosts kann mit herkömmlichen Bereitstellungsverfahren verwaltet werden. Docker-Hosts können manuell mit Befehlen wie **docker run** oder durch Automatisierung, z.B. Pipelines für Continuous Delivery (CD), verwaltet werden.

### <a name="monolithic-application-deployed-as-a-container"></a>Monolithische Anwendung, die als Container bereitgestellt wird

Das Verwenden von Containern zur Verwaltung monolithischer Anwendungsbereitstellungen hat einige Vorteile. Das Skalieren von Containerinstanzen ist wesentlich schneller und einfacher als die Bereitstellung zusätzlicher VMs. Auch wenn VM Scale Sets verwendet wird, um VMs zu skalieren, nimmt deren Instanziierung viel Zeit in Anspruch. Wenn die App-Konfiguration als App-Instanz bereitgestellt wird, wird diese als Teil der VM verwaltet.

Die Bereitstellung von Updates, wie Docker-Images, ist wesentlich schneller und effizienter im Netzwerk. Docker-Images starten in der Regel in Sekunden, wodurch Rollouts beschleunigt werden. Das Löschen einer Docker-Instanz ist genauso einfach wie das Ausführen eines **docker stop**-Befehls und in der Regel in weniger als einer Sekunde abgeschlossen.

Da Container unveränderlich sind, müssen Sie sich keine Gedanken über beschädigte VMs machen. Es kann allerdings vorkommen, das Updateskripts bestimmte Konfigurationen oder restliche Dateien auf einem Datenträger erfassen.

Docker kann sich im Hinblick auf monolithische Apps zwar als sinnvoll erweisen. Wenn aber die monolithische Anwendung in Subsysteme unterteilt wird, die skaliert, entwickelt und einzeln bereitgestellt werden können, lohnt es sich möglicherweise, wenn Sie sich mit Microservices vertraut machen.

> ### <a name="references--common-web-architectures"></a>Ressourcen: Häufig verwendete Webarchitekturen
> - **Clean Architecture**  
> <https://8thlight.com/blog/uncle-bob/2012/08/13/the-clean-architecture.html>
> - **Onion Architecture**  
> <http://jeffreypalermo.com/blog/the-onion-architecture-part-1/>
> - **The Repository Pattern (Das Muster „Repository“)**  
> <http://deviq.com/repository-pattern/>
> - **Clean Architecture Solution Sample (Projektmappenbeispiel unter Verwendung von Clean Architecture)**  
> <https://github.com/ardalis/cleanarchitecture>
> - **E-Book zum Entwerfen von Microservices** <http://aka.ms/MicroservicesEbook>

>[!div class="step-by-step"]
[Zurück] (architectural-principles.md) [Weiter] (common-client-side-web-technologies.md)
