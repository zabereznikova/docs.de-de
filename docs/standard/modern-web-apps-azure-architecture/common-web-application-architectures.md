---
title: Allgemeine Web-Anwendungsarchitektur
description: Innovative Webanwendungen mit ASP.NET Core und Microsoft Azure konzipiert | Allgemeine Web-Anwendungsarchitektur
author: ardalis
ms.author: wiwagn
ms.date: 10/06/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.openlocfilehash: b6236cfab290211f930d6a1987075abeade4fd6d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
#<a name="common-web-application-architectures"></a>Allgemeine Web-Anwendungsarchitektur

> "Wenn Sie, dass guten Architektur aufwändig ist glauben, wiederholen Sie den fehlerhaften Architektur."  
> _-Brian Agenturen Foote und Joseph Yoder_

## <a name="summary"></a>Zusammenfassung

Den meisten herkömmliche-.NET-Anwendungen bereitgestellt werden als einzelne Einheiten, die für eine ausführbare Datei oder eine einzelne Webanwendung, die in einer einzelnen IIS-Appdomain ausgeführt wird. Dies ist das einfachste Bereitstellungsmodell und viele interne und kleinere öffentliche Anwendungen sehr gut dient. Allerdings vorteilhaft, selbst wenn dieser Einheit der Bereitstellung, die meisten nicht-trivialen Geschäftsanwendungen eine logische Trennung in mehreren Ebenen.

## <a name="what-is-a-monolithic-application"></a>Was ist eine Anwendung aufgrund eines monolithischen?

Eine Anwendung aufgrund eines monolithischen ist vollständig eigenständige, im Hinblick auf das Verhalten ist. Es möglicherweise mit anderen Diensten oder Datenspeichern im Verlauf seiner Vorgänge interagieren, aber der Kern des Verhaltens in einem eigenen Prozess ausgeführt wird, und die gesamte Anwendung in der Regel als einzelne Einheit bereitgestellt wird. Wenn eine solche Anwendung horizontal skalieren muss, wird die gesamte Anwendung in der Regel auf mehreren Servern oder virtuellen Computern dupliziert werden.

## <a name="all-in-one-applications"></a>: 1-Anwendungen

Der kleinste darstellbare Zahl von Projekten für eine Anwendungsarchitektur ist eine. In dieser Architektur ist die gesamte Logik der Anwendung in einem einzelnen Projekt enthalten sind, in einer einzelnen Assembly kompiliert und als einzelne Einheit bereitgestellt.

Ein neues Projekt für ASP.NET Core beginnt, ob in Visual Studio oder über die Befehlszeile erstellt als eine einfache "all-in-One" Monolith. Er enthält alle des Verhaltens der Anwendung, einschließlich der Präsentations-, Geschäftslogik- und Data Access-Logik. Abbildung 5 – 1 zeigt die Dateistruktur Einzelprojekt--App.

**Abbildung 5 – 1.** Ein einzelnes Projekt ASP.NET Core-app

![](./media/image5-1.png)

In einem einzelnen Projekt Szenario erfolgt die Abgrenzung von Problemen durch die Verwendung von Ordnern. Die Standardvorlage enthält separate Ordner für MVC-Muster Aufgaben der Modelle, Ansichten und Controllern sowie zusätzliche Ordner für Daten und Dienste. In dieser Anordnung Präsentation Details in den Ordner Views so weit wie möglich eingeschränkt sein, und Data Access-Implementierungsdetails sollte auf Klassen, die im Ordner "Daten" beibehalten beschränkt sein. Geschäftslogik muss sich im Dienste und Klassen im Ordner Models befinden.

Die monolithische Einzelprojekt--Lösung umfasst einige Nachteile, zwar einfach. Mit zunehmender Größe und Komplexität des Projekts wird die Anzahl der Dateien und Ordner sowie vergrößert werden fortgesetzt. UI-Probleme (Modelle, Ansichten, Controller) befinden sich in mehrere Ordner, in denen nicht in alphabetischer Reihenfolge gruppiert werden. Dieses Problem schlimmer nur, wenn zusätzliche Konstrukte für den UI-Ebene, z. B. Filter oder ModelBinders, in die eigenen Ordner hinzugefügt werden. Geschäftslogik wird zwischen Ordnern Modelle und Dienste verschoben, und es gibt keine deutlich wird, welche die Klassen, in welchen Ordnern auf welche anderen abhängen sollten. Diese mangelnde Organisation auf Projektebene führt häufig zu [Spaghetti Code](http://deviq.com/spaghetti-code/).

Um diese Probleme zu beheben, Anwendungen häufig weiterentwickelt in Projektmappen mit mehreren Projekten, in dem jedes Projekt in einer bestimmten befinden gilt *Ebene* der Anwendung.

## <a name="what-are-layers"></a>Welche Ebenen sind?

Eine Möglichkeit zum Verwalten dieser Komplexität werden wie Anwendungen Komplexität zunehmen, die Anwendung gemäß seiner Zuständigkeiten oder Bedenken zusammensetzen. Dies folgt die Trennung von Anliegen-Prinzip und gewährleisten eine wachsende Codebasis organisiert, sodass Entwickler leicht finden können, in denen bestimmte Funktionen implementiert wird. Mehrschicht-Architektur bietet eine Reihe von Vorteilen außerhalb der Organisation nur Code, jedoch an.

Indem Code in Ebenen organisiert, kann die allgemeine Low-Level-Funktionen in der gesamten Anwendung wiederverwendet werden. Die Wiederverwendung ist nützlich, da es bedeutet, dass weniger Code geschrieben werden muss und es der Anwendung auf eine einzelne Implementierung, befolgen das Prinzip TROCKENEN standardisieren ermöglichen kann.

Mit einer mehrstufigen Architektur können Anwendungen Einschränkungen erzwingen, für die Ebenen mit anderen Ebenen kommunizieren können. Dadurch wird um die Kapselung zu erzielen. Wenn eine Ebene geändert oder ersetzt wird, sollte nur diese Ebenen, die Arbeit mit beeinträchtigt werden. Durch die Begrenzung der abhängen Ebenen an, auf denen andere Ebenen, die Auswirkungen von Änderungen gemindert werden können, sodass eine einzelne Änderung keine Auswirkungen auf die gesamte Anwendung hat.

Ebenen (und Kapselung) erleichtern Funktionen innerhalb der Anwendung zu ersetzen. Z. B. eine Anwendung möglicherweise zunächst eine eigene SQL Server-Datenbank für Persistenz verwenden, sondern kann später zu einer Strategie für die Cloud-basierten Persistenz, hinter einer Web-API verwenden, oder auswählen. Wenn die Anwendung ordnungsgemäß seine dauerhaftigkeitsimplementierung innerhalb einer logischen Ebene gekapselt ist, könnte, dass bestimmte SQL Server-Ebene durch eine neue Implementierung der gleichen öffentlichen Schnittstelle ersetzt werden.

Zusätzlich zu das Potenzial der Auslagerung Implementierungen als Antwort auf zukünftige Änderungen der Anforderungen erleichtern Anwendungsebenen auch Implementierungen für Testzwecke austauschen. Anstatt Tests schreiben, die für die Ebene um echte Daten bzw. den UI-Ebene der Anwendung ausgeführt werden, können diese Ebenen zum Zeitpunkt der Test mit gefälschten Implementierungen ersetzt werden, die bekannte Antworten auf Anforderungen zu bieten. In der Regel dadurch Tests viel einfacher schreiben und viel schneller ausführen, Vergleich für die Ausführung der tests erneut real Anwendungsinfrastruktur.

Logische Anordnung ist ein gängiges Verfahren zum Verbessern der Organisation des Codes im Enterprise-softwareanwendungen, und es gibt mehrere Möglichkeiten, die in denen Code in Ebenen organisiert werden kann.

> [!NOTE]
> *Ebenen* logische Trennung innerhalb der Anwendung darstellen. Falls bei der Anwendungslogik physisch separaten Servern oder Prozesse verteilt wird, diese separaten physischen Bereitstellungsziele bezeichnet als *Ebenen*. Es ist möglich und recht häufig vorkommt, damit eine N-Ebenen-Anwendung, die auf einer einzelnen Ebene bereitgestellt wird.

## <a name="traditional-n-layer-architecture-applications"></a>Herkömmliche "N-Ebene" Architektur Anwendungen

Die am häufigsten verwendete Organisation der Anwendungslogik in Ebenen er die in Abbildung 5 – 2 dargestellt.

**Abbildung 5-2.** Typische Anwendungsebenen.

![](./media/image5-2.png)

Diese Ebenen werden als Benutzeroberfläche, häufig abgekürzt BLL (Business Logic Layer) und Datenzugriffsschicht (Data Access Layer). Mit dieser Architektur, stellen Benutzer Anforderungen über die Benutzeroberfläche der Ebene nur mit der BLL interagiert. Die BLL kann wiederum die DAL für zugriffsanforderungen Daten aufrufen. Die Benutzeroberflächenebene nicht nehmen alle Anforderungen an die DAL direkt, noch sollte sie interagieren mit Persistenz direkt über andere Mittel. Entsprechend sollte die BLL nur Persistenz interagieren mit der DAL durchlaufen. Auf diese Weise ist jede Ebene einen eigenen bekannten verantwortlich.

Ein Nachteil dieses Ansatzes herkömmlichen Strukturlayout ist, dass die Kompilierung Abhängigkeiten von oben nach unten ausgeführt. D. h. hängt die Benutzeroberflächenebene die BLL, abhängig von der DAL. Dies bedeutet, dass die BLL, der in der Regel die wichtigste Programmlogik in der Anwendung enthält, abhängige auf "Details" Data Access-Implementierung (und häufig auf das Vorhandensein einer Datenbank). Testen von Geschäftslogik in einer solchen Architektur ist häufig schwierig ist, erfordern eine Testdatenbank. Das Prinzip der Abhängigkeit Umkehrung kann verwendet werden, um dieses Problem zu beheben, wie Sie im nächsten Abschnitt sehen.

Abbildung 5 – 3 zeigt eine beispiellösung, die Unterbrechung von der Anwendung in drei Projekte durch Verantwortung (oder Ebene).

**Abbildung 5-3.** Eine einfache monolithischen Anwendung mit drei Projekte.

![](./media/image5-3.png)

Obwohl diese Anwendung mehrere Projekte zu organisatorischen Zwecken verwendet wird, wird weiterhin als einzelne Einheit bereitgestellt und seinen Clients als eine einzelne Web-app mit ihm interagieren. Dies ermöglicht sehr einfachen Bereitstellungsverfahrens. Abbildung 5-4 zeigt, wie eine solche Anwendung möglicherweise mit Windows Azure gehostet.

![](./media/image5-4.png)

**Abbildung 5-4.** Einfache Bereitstellung von Azure-Web-App

Wie die Anwendung muss wachsen, möglicherweise komplexen und robusten bereitstellungslösungen erforderlich. Abbildung 5 – 5 zeigt ein Beispiel für eine komplexere Bereitstellungsplan, der zusätzliche Funktionen unterstützt.

![](./media/image5-5.png)

**Abbildung 5 bis 5.** Bereitstellen von einer Web-app in Azure App Service

Intern wird dieses Projekt Organisation in mehrere Projekte, die basierend auf Verantwortung die Verwaltbarkeit der Anwendung verbessert.

Diese Einheit kann Skalierbarkeit für Cloud-basierte bei Bedarf nutzen oder skalieren skaliert werden. Zentrales Skalieren bedeutet das Hinzufügen von zusätzlichen CPU, Arbeitsspeicher, Speicherplatz auf dem Datenträger oder andere Ressourcen auf den Servern, hosten Ihre app. Horizontales Skalieren bedeutet, ob diese physische oder virtuelle Computer sind solche Server zusätzliche Instanzen hinzufügen. Wenn Ihre app über mehrere Instanzen gehostet wird, ist ein Lastenausgleich zum Zuweisen von Anforderungen auf individuellen app-Instanzen verwendet.

Die einfachste Vorgehensweise zum Skalieren einer Webanwendung in Azure besteht darin, in der Anwendungsverzeichnis App Service-Plan manuell skalieren zu konfigurieren. Abbildung 5 bis 6 zeigen den entsprechenden Azure-Dashboard-Bildschirm, um konfigurieren, wie viele Instanzen eine app betreuen.

![](./media/image5-6.png)

**Abbildung 5 bis 6.** Skalierung in Azure App Service-Plan.

## <a name="clean-architecture"></a>Bereinigen der Architektur

Anwendungen, die die Abhängigkeit Umkehrung Prinzip sowie Driven Design (DDD) Prinzipien folgen tendenziell eine ähnliche Architektur ankommen. Diese Architektur ist im Laufe der Jahre viele Namen. Einer der ersten Namen wurde Sechseckige Architektur verteilter Transaktionen, gefolgt von Ports und Adaptern. Udate wird als genannten wurden die [Onion Architektur](http://jeffreypalermo.com/blog/the-onion-architecture-part-1/) oder [bereinigen Architektur](https://8thlight.com/blog/uncle-bob/2012/08/13/the-clean-architecture.html). Es ist dieser Nachname Clean-Architektur, die als Grundlage zum Beschreiben der in diesem e-Book-Architektur verwendet wird.

> [!NOTE]
> Der Begriff, den bereinigen Architektur auf Anwendungen angewendet werden können, die mit DDD Prinzipien auch auf solche, die nicht erstellt werden, mit DDD erstellt werden. Im Fall der erste Wert diese Kombination kann bezeichnet werden als "Clean DDD Architecture".

Clean-Architektur setzt das Geschäftsmodell Logik und die Anwendung in der Mitte der Anwendung. Anstatt von Geschäftslogik, die Datenzugriff oder Bedenken Infrastruktur abhängig sind, wird diese Abhängigkeit invertiert: Infrastruktur und die Implementierung richten sich nach den Kern der Anwendung. Dies erfolgt durch die Definition von Abstraktionen oder Schnittstellen, in der Anwendung, die dann durch die in die Infrastrukturebene definierten Typen implementiert werden. Eine gängige Methode der Visualisierung dieser Architektur ist eine Reihe von konzentrische Kreise, ähnlich wie eine Onion verwenden. Abbildung 5 X zeigt ein Beispiel für diese Art der Darstellung von Architektur.

![](./media/image5-7.png)

**Abbildung 5-7.** Bereinigen Sie die Architektur; Onion anzeigen

In diesem Diagramm bedroht werden Abhängigkeiten in Richtung der innersten Kreis. Daher sehen Sie sich, dass der Anwendung-Core (die den Namen aus seiner Position im Kern dieses Diagramm annimmt) keine anderen Anwendungsebenen abhängt. Sind Sie sehr zentriert Entitäten und die Schnittstellen der Anwendungsverzeichnis aus. Nur außerhalb, jedoch noch in der Anwendung Core sind Domänendienste, die in der Regel in der inneren Kreis definierte Schnittstellen implementieren. Außerhalb der Anwendung Core richten sich die Benutzeroberfläche und den infrastrukturschichten auf Anwendung Core, jedoch nicht auf anderen (unbedingt).

Abbildung 5 X herkömmlicheren horizontale Ebenendiagramm, die die Abhängigkeit zwischen der Benutzeroberfläche und anderen Ebenen besser wiedergibt.

![](./media/image5-8.png)

**Abbildung 5 bis 8.** Bereinigen Sie die Architektur; horizontale Ebene anzeigen

Beachten Sie, dass das ausgefüllte Pfeile Kompilierzeit Abhängigkeiten darstellen, während der gestrichelte Pfeil stellt eine Abhängigkeit nur das Laufzeitmodul dar. Verwenden die clean-Architektur, die Benutzeroberflächenebene funktioniert mit Schnittstellen, die in der Anwendung zum Zeitpunkt der Kompilierung definiert und im Idealfall sollte kein Kenntnis von den Implementierungstypen definiertes in die Infrastrukturebene. Zur Laufzeit jedoch werden diese Implementierungstypen für die app ausgeführt wird, benötigt, damit er vorhanden und bis zu der Anwendung Core Schnittstellen über Abhängigkeitsinjektion kabelgebundenen sein muss.

Abbildung 5 – 9 zeigt eine ausführlichere Ansicht eines ASP.NET Core der Architektur einer Anwendung nach dieser Empfehlungen erstellt.

![ASPNET Kernarchitektur](./media/image5-9.png)

**Abbildung 5 bis 9.** ASP.NET Core-Architekturdiagramm bereinigen Architektur befolgen.

Da das Kernstück der Anwendung nicht von Infrastruktur abhängig ist, ist es sehr einfach, automatisierte Komponententests für diese Ebene zu schreiben. Zahlen 5 bis 10 und 5 bis 11 zeigen an, wie die Tests in dieser Architektur passen.

![UnitTestCore](./media/image5-10.png)

**Abbildung 5 bis 10.** UnitTests Application Core isoliert.

![IntegrationTests](./media/image5-11.png)

**Abbildung 5-11.** Integrationstests Infrastruktur Implementierungen mit externen Abhängigkeiten.

Da die Benutzeroberflächenebene für Typen, die in der Infrastructure-Projekt definiert direkte Abhängigkeit besitzt, ist es ebenso sehr einfach out Implementierungen, entweder testen zu vereinfachen oder als Reaktion auf die sich ändernden anwendungsanforderungen ausgetauscht werden.. ASP.NET Core des integrierten Verwendung von und Unterstützung für Abhängigkeitsinjektion macht diese Architektur die am besten geeignete Möglichkeit, die Struktur nicht triviale monolithischen Anwendungen.

Für monolithischen Anwendungen werden alle Projekte Anwendung Kern, der Infrastruktur und der Benutzeroberfläche als eine einzelne Anwendung ausgeführt. Die Common Language Runtime-Anwendungsarchitektur sieht möglicherweise etwas wie Abbildung 5 – 12.

![ASPNET Kernarchitektur 2](./media/image5-12.png)

**Abbildung 5 – 12.** Ein Beispiel ASP.NET Core-app-Runtime-Architektur.

### <a name="organizing-code-in-clean-architecture"></a>Organisieren von Code in Clean-Architektur

In einer Projektmappe bereinigen Architektur hat jedes Projekt löschen Aufgaben. Als solche in jedem Projekt angelegt werden, bestimmte Typen gehören, und finden Sie häufig Ordnern, die auf diese Typen in das entsprechende Projekt entspricht.

Den Kern der Anwendung enthält die Geschäftsmodell, das Entitäten, Diensten und Schnittstellen enthält. Zu diesen Schnittstellen gehören Abstraktionen für Vorgänge, die anhand von Infrastruktur, z. B. den Datenzugriff, Dateisystemzugriff, Netzwerkaufrufe usw. gesucht werden soll. In einigen Fällen müssen Diensten oder Schnittstellen definiert, die auf dieser Ebene mit nicht-Entitätstypen arbeiten, die keine Abhängigkeiten auf der Benutzeroberfläche oder Infrastruktur haben. Diese können als einfache Daten übertragen Objekte (DTOs) definiert werden.

> ### <a name="application-core-types"></a>Core Anwendungstypen
> -   Entitäten (Business Modellklassen, die beibehalten werden)
> -   Schnittstellen
> -   Dienste
> -   DTOs

Infrastructure-Projekt enthält in der Regel Data Access-Implementierungen. In einer typischen Webanwendung ASP.NET Core umfasst dies Entity Framework DbContext, alle EF-Core-Migrationen, die definiert wurden und Datenzugriffsklassen-Implementierung. Die gängigste Methode zum abstrahieren Datenzugriffscode Implementierung wird durch Verwendung von der [Repository Entwurfsmuster](http://deviq.com/repository-pattern/).

Zusätzlich zu den Data Access-Implementierungen sollte das Infrastruktur-Projekt Implementierungen von Diensten enthalten, die mit der Infrastruktur Bedenken interagieren muss. Diese Dienste sollten in den Kern der Anwendung definierte Schnittstellen implementieren und haben deshalb Infrastruktur sollte einen Verweis auf das Projekt Application Core.

> ### <a name="infrastructure-types"></a>Infrastrukturtypen
> -   EF Core Typen ("DbContext", "Migration")
> -   Datenzugriff Implementierungstypen (Repositorys)
> -   Infrastruktur-spezifische Dienste ("FileLogger", SmtpNotifier usw.).

Die Benutzeroberflächenebene in einer ASP.NET-MVC-Anwendung Core werden den Einstiegspunkt für die Anwendung, und es werden ein ASP.NET Core MVC-Projekt. Dieses Projekt sollte die Anwendung Core-Projekt verweist, und die Typen sollten mit Infrastruktur ausschließlich über Schnittstellen, die in der Anwendung Core definiert interagieren. Keine direkte Instanziierung von (oder statische Aufrufe) Ebene Infrastrukturtypen in der Benutzeroberflächenebene zugelassen werden sollte.

> ### <a name="ui-layer-types"></a>Benutzeroberflächentypen-Ebene
> -   Domänencontroller
> -   Filter
> -   Ansichten
> -   ViewModels
> -   Start

Die Startklasse ist verantwortlich für das Konfigurieren der Anwendung und verknüpft Implementierungstypen zu Schnittstellen, sodass Abhängigkeitsinjektion zur Laufzeit ordnungsgemäß funktioniert.

> [!NOTE]
> Damit die Abhängigkeitsinjektion in ConfigureServices in der Startup.cs-Datei des Projekts Benutzeroberfläche zu verknüpfen, müssen das Projekt ggf. Infrastructure-Projekt zu verweisen. Diese Abhängigkeit kann am einfachsten mithilfe eines benutzerdefinierten DI-Containers entfernt werden. Der einfachste Ansatz werden im Rahmen dieses Beispiels können die UI-Projekt, in das Infrastruktur-Projekt zu verweisen.

## <a name="monolithic-applications-and-containers"></a>Aufgrund eines monolithischen Anwendungen und Container 

Sie können einen einfachen und monolithischen Bereitstellung-basierten Web-Anwendung oder Dienst erstellen und als einen Container bereitstellen. In der Anwendung möglicherweise nicht aufgrund eines monolithischen jedoch in mehrere Bibliotheken, Komponenten oder Ebenen organisiert werden. Extern ist es einem einzelnen Container wie einen einzelnen Prozess, einzelne Webanwendung oder einzelnen Dienst.

Um dieses Modell zu verwalten, stellen Sie einen einzelnen Container, um die Anwendung darzustellen. Wenn skaliert werden sollen, fügen Sie einfach zusätzliche Kopien mit vorangestelltem einen Lastenausgleich hinzu. Die Einfachheit stammen aus eine einzelne Bereitstellung in einem einzelnen Container oder virtuellen Computer verwalten.

![](./media/image5-13.png)

Sie können mehrere Komponenten-Bibliotheken oder interne Ebenen innerhalb jeder Container einschließen, wie in Abbildung 5 X dargestellt. Folgt jedoch die Container-Prinzip des *"ein Container ist dabei, ein und in einem Prozess*", das monolithische Muster ist möglicherweise ein Konflikt.

Der Nachteil dieses Ansatzes stammen, wenn/die Anwendung wächst, erfordern sie skalieren. Wenn die gesamte Anwendung skaliert, ist es nicht tatsächlich ein Problem aufgetreten. In den meisten Fällen sind jedoch einige Teile der Anwendung, dass die Drossel Punkte, Skalierung, erfordern, während andere Komponenten sind kleiner verwendet.

Verwenden Sie das Standard-e-Commerce-Beispiel; Was müssen Sie wahrscheinlich skalieren ist die Komponente der Informationen. Viele weitere Kunden durchsuchen Produkte, als sie erwerben. Verwenden Sie die Zahlung Pipeline verwenden mehr Kunden Warenkorb. Weniger Kunden Hinzufügen von Kommentaren oder ihre Bestellung Verlauf anzeigen. Und Sie wahrscheinlich nur eine Handvoll Mitarbeiter in einer einzelnen Region, die den Inhalt und Marketingkampagnen verwalten müssen. Durch zentrales Skalieren der aufgrund eines monolithischen Entwurfs, wird der gesamte Code mehrmals bereitgestellt.

Zusätzlich zu der Skala erfordern alles Problem, Änderungen an einer einzelnen Komponente vollständige ein erneuter Test die gesamte Anwendung und eine vollständige erneute Bereitstellung aller Instanzen.

Aufgrund eines monolithischen Ansatz ist, und viele Organisationen mit dieser Architektur Ansatz entwickeln. Viele haben genügend Ergebnisse gut anzumelden, während andere Grenzwerte aktiviert sind. Viele entwickelt ihre Anwendungen in diesem Modell, da die Tools und Infrastruktur für Waren zu schwierig dienstorientierte Architektur (SOA) zu erstellen, und sie die Notwendigkeit - sehen haben nicht, bis vergrößert die app wurde. Wenn Sie, dass Sie die Grenzwerte des monolithischen Ansatzes auftreten feststellen, kann die Aufteilung der app auf Container und Microservices besser genutzt werden, damit ein logischen als Nächstes sein.

![](./media/image5-14.png)

Bereitstellen von monolithischen Anwendungen in Microsoft Azure kann mithilfe von dedizierten virtuellen Computern für jede Instanz erreicht werden. Mit [Azure VM-Skalierungsgruppen](https://docs.microsoft.com/azure/virtual-machine-scale-sets/), können Sie die virtuellen Computer problemlos skalieren. [Azure App-Dienste](https://azure.microsoft.com/services/app-service/) monolithische Anwendungen ausführen können, und Instanzen problemlos zu skalieren, ohne den VMs verwalten zu müssen. Azure App-Dienste können einzelne Instanzen von Docker-Containern ebenfalls ausführen, Vereinfachung der Bereitstellungsstatus. Mit Docker, können Sie eine einzelne virtuelle Maschine als Docker-Host bereitstellen und Ausführen mehrerer Instanzen. Der Azure-Lastenausgleich, können wie in Abbildung 5-14 gezeigt, Sie Skalierung verwalten.

Mit herkömmlichen Bereitstellung Techniken kann die Bereitstellung für die verschiedenen Hosts verwaltet werden. Die Docker-Hosts verwaltet werden können, mit Befehlen wie **"Docker run"** manuell oder durch die Automatisierung ausgeführt, z. B. pipelines Continuous Delivery (CD).

### <a name="monolithic-application-deployed-as-a-container"></a>Aufgrund eines monolithischen Anwendung, die als Container bereitgestellt

Es sind Vorteile der Verwendung von Containern monolithischen anwendungsbereitstellungen zu verwalten. Skalieren die Instanzen von Containern ist wesentlich schneller und einfacher als die Bereitstellung zusätzlicher VMs. Selbst wenn die VM-Skalierungsgruppen verwenden, um virtuelle Computer zu skalieren, Zeit dauern, bis diese Instanz. Wenn als app-Instanzen bereitgestellt wird, wird die Konfiguration der app im Rahmen des virtuellen Computers verwaltet.

Bereitstellen von Updates, wie Docker-Images ist wesentlich schneller und Netzwerk effizient. Docker-Images beginnen in der Regel in Sekunden, die Befehlseingabe Rollouts. Beendet eine Instanz der Docker ist genauso einfach wie das Ausgeben einer **Docker Stop** Befehl ein, in der Regel in weniger als einer Sekunde abschließen.

Wie Container entwurfsbedingt grundsätzlich unveränderlich sind, müssen Sie nie fehlerhafte VMs zu kümmern, während der Update-Skripts vergessen haben möglicherweise für einige bestimmte Konfiguration oder die Datei Links auf dem Datenträger zu berücksichtigen.

Während monolithischen apps von Docker in Sub-Systeme, die skaliert werden kann die aufgrund eines monolithischen Anwendung unterbrechen profitieren können, entwickelt und einzeln bereitgestellt werden möglicherweise Ihre Einstiegspunkt außerhalb des Bereichs des Microservices.

> ### <a name="references--common-web-architectures"></a>Verweise – allgemeine Web-Architekturen
> - **Die Clean-Architektur**  
> <https://8thlight.com/Blog/Uncle-Bob/2012/08/13/the-Clean-Architecture.HTML>
> - **Die Onion-Architektur**  
> <http://jeffreypalermo.com/Blog/the-Onion-Architecture-Part-1/>
> - **Das Repositorymuster**  
> <http://deviq.com/Repository-Pattern/>
> - **Bereinigen der Architektur Lösung-Beispiel**  
> <https://github.com/ardalis/cleanarchitecture>
> - **Architektur Microservices e-Book** <http://aka.ms/MicroservicesEbook>

>[!div class="step-by-step"]
[Vorherigen] (architektonische principles.md) [weiter] (Common-Client-Side-Web-technologies.md)
