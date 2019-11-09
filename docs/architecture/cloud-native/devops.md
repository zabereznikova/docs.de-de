---
title: Native Cloud-devops
description: Architektur von Cloud Native .net-apps für Azure | Native Cloud-devops
ms.date: 06/30/2019
ms.openlocfilehash: 2b3dd47eeeb69d63f5ae39705abb9d1d51295645
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73841816"
---
# <a name="cloud-native-devops"></a>Native Cloud-devops

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Das bevorzugte Mantra von Software Beratern besteht darin, die Frage zu beantworten. Dies ist nicht der Fall, weil Software Berater nicht an einer Position beteiligt sind. Das liegt daran, dass es keine echte Antwort auf Fragen in Software gibt. Es gibt keine absolute Rechte und falsche Rechte, sondern vielmehr eine Balance zwischen den Gegensätzen.

Nehmen Sie z. b. die beiden wichtigsten Schulen der Entwicklung von Webanwendungen: Single-Page-Anwendungen (Spas) und serverseitige Anwendungen. Andererseits ist die Benutzerumgebung in den Spas tendenziell besser, und die Menge des Datenverkehrs an den Webserver kann minimiert werden, sodass Sie auf einfache Weise als statisches Hosting gehostet werden kann. Auf der anderen Seite sind die Spas tendenziell langsamer zu entwickeln und schwieriger zu testen. Welches ist die richtige Wahl? Das hängt von ihrer Situation ab.

Native Cloud-Anwendungen sind nicht gegen dieselbe Dichotomie immun. Sie haben deutliche Vorteile hinsichtlich der Geschwindigkeit der Entwicklung, Stabilität und Skalierbarkeit, aber deren Verwaltung kann etwas schwieriger sein.

Vor Jahren war es nicht ungewöhnlich, eine Anwendung von der Entwicklung in die Produktion zu verschieben, um einen Monat oder sogar mehr zu nutzen. Unternehmen haben Software in einem 6-monatigen oder sogar in jedem Jahr veröffentlicht. Sie müssen sich nicht mehr als Microsoft Windows ansehen, um sich einen Überblick über die Kadenz von Releases zu verschaffen, die vor den jemals grünen Tagen von Windows 10 akzeptabel waren. Zwischen Windows XP und Vista sind fünf Jahre vergangen, ein weiteres 3 zwischen Vista und Windows 7.

Es ist nun recht gut festgelegt, dass das schnelle Freigeben von Software schnell verschiebbare Unternehmen einen großen Marktvorteil gegenüber ihren eher langsamsten Wettbewerbern bietet. Der Grund dafür ist, dass die wichtigsten Updates für Windows 10 ungefähr alle sechs Monate durchlaufen werden.

Die Muster und Vorgehensweisen, die schnellere und zuverlässigere Releases zum Bereitstellen von Wert für das Unternehmen ermöglichen, werden zusammen mit devops bezeichnet. Sie bestehen aus einer Vielzahl von Ideen, die den gesamten Lebenszyklus der Softwareentwicklung abdecken, von der Angabe einer Anwendung bis hin zur Bereitstellung und dem Betrieb der Anwendung.

Devops wurde vor der Verwendung von-Diensten entwickelt, und es ist wahrscheinlich, dass die Verschiebung in Bezug auf kleinere, besser geeignete Dienste ohne devops nicht möglich wäre, um die Freigabe und den Betrieb nicht nur für eine Anwendung zu vereinfachen.

![Abbildung 11-0 Suchtrends zeigen, dass das Wachstum in den-Diensten nicht gestartet wird, bis devops eine ziemlich gute Idee ist.](./media/microservices-vs-devops.png)

Mithilfe von guten devops-Verfahren ist es möglich, die Vorteile von cloudbasierten Anwendungen zu realisieren, ohne dass Sie unter einem Arbeitsbereich erstickt werden, der die Anwendungen tatsächlich betreibt.

Es gibt keinen Goldenen Hammer, wenn es um devops geht. Niemand kann eine vollständige und umfassende Lösung für die Veröffentlichung und den Betrieb hochwertiger Anwendungen verkaufen. Dies liegt daran, dass jede Anwendung stark von allen anderen Anwendungen abweicht. Es gibt jedoch Tools, die devops zu einem weitaus weniger beängstigenden Vorschlag machen können. Eines dieser Tools wird als Azure devops bezeichnet.

## <a name="azure-devops"></a>Azure DevOps

Azure devops verfügt über einen langen Stammbaum. Er kann seine Stämme zurückverfolgen, wenn Team Foundation Server zuerst Online verschoben wurde, und durch die verschiedenen Namensänderungen: Visual Studio Online und Visual Studio Team Services. Im Laufe der Jahre ist es jedoch weitaus mehr als seine Vorgänger.

Azure devops ist in fünf Hauptkomponenten unterteilt:

![Abbildung 11-1 die fünf Hauptbereiche von Azure devops](./media/devops-components.png)

**Azure Boards** : stellt ein Problem und ein Tool zur Nachverfolgung von Arbeitsaufgaben bereit, das den Benutzern die Auswahl der Workflows ermöglicht, die für Sie am besten geeignet sind. Es enthält eine Reihe vorkonfigurierter Vorlagen, einschließlich der für die Unterstützung von Scrum-und Kanban-Entwicklungs Stilen.

**Azure Repos** -Quell Code Verwaltung, die den ehrwürdigen Team Foundation-Versionskontrolle (tfvc) und den Branchen bevorzugten git unterstützt. Pull Requests bieten eine Möglichkeit, Social Coding zu aktivieren, indem Sie die Diskussion über Änderungen fördern, die Sie vorgenommen haben.

**Azure Pipelines** : ein Build-und releaseverwaltungssystem, das eine enge Integration in Azure unterstützt. Builds können auf einer Vielzahl von Plattformen ausgeführt werden, von Windows auf Linux bis hin zu MacOS. Build-Agents können in der Cloud oder lokal bereitgestellt werden.

**Azure Test Plans** : keine QA-Person wird mit der Unterstützung für Test Verwaltung und Explorative Tests, die von der Test Plans-Funktion geboten wird, zurückgelassen.

**Azure Artifacts** : ein artefaktfeed, der es Unternehmen ermöglicht, eigene, interne Versionen von nuget, NPM und anderen zu erstellen. Dies dient dem doppelten Zweck, als Cache von upstreampaketen zu fungieren, wenn ein Fehler bei einem zentralisierten Repository auftritt.

Die Organisationseinheit der obersten Ebene in Azure devops wird als Projekt bezeichnet. Innerhalb jedes Projekts können die verschiedenen Komponenten, z. b. Azure Artifacts, aktiviert und deaktiviert werden. Wenn Benutzer Ihren Quellcode in GitHub verwalten möchten, aber weiterhin Azure Pipelines nutzen möchten, ist dies durchaus möglich. Tatsächlich nutzen viele Open-Source-Projekte die [kostenlosen Builds](https://azure.microsoft.com/blog/announcing-azure-pipelines-with-unlimited-ci-cd-minutes-for-open-source/) , die von Azure devops angeboten werden, während der Quellcode auf GitHub aufbewahrt wird. Einige bedeutende Open Source-Projekte, wie z. b. [Visual Studio Code](https://code.visualstudio.com/), [Yarn](https://yarnpkg.com/en/), [Gulp](https://gulpjs.com/)und [numpy](https://www.numpy.org/) , haben den Übergang vorgenommen.

Jede dieser Komponenten bietet einige Vorteile für cloudanwendungen, aber die drei nützlichsten sind die Quell Code Verwaltung, Boards und Pipelines.  

## <a name="source-control"></a>Quellcodeverwaltung

Die Organisation des Codes für eine native Cloud-Anwendung kann eine Herausforderung darstellen. Anstatt einer einzigen riesigen Anwendung bestehen die cloudbasierten Anwendungen tendenziell aus einem Web kleinerer Anwendungen, die miteinander kommunizieren. Wie alle Aspekte beim Computing, ist die beste Code Ordnung eine offene Frage. Es gibt Beispiele für erfolgreiche Anwendungen, die unterschiedliche Arten von Layouts verwenden, aber zwei Varianten scheinen die meiste Beliebtheit zu haben.

Bevor Sie in die eigentliche Quell Code Verwaltung einsteigen, sollten Sie sich wahrscheinlich entscheiden, wie viele Projekte geeignet sind. Innerhalb eines einzelnen Projekts werden mehrere Depots und buildpipelines unterstützt. Boards sind etwas komplizierter, aber es kann auch sein, dass die Aufgaben problemlos mehreren Teams innerhalb eines einzelnen Projekts zugewiesen werden können. Es ist sicherlich möglich, Hunderte, sogar Tausende von Entwicklern, von einem einzelnen Azure devops-Projekt zu unterstützen. Dies ist wahrscheinlich die beste Vorgehensweise, da Sie für alle Entwickler von einem zentralen Ort aus arbeiten und die Verwirrung der Suche nach einer Anwendung verringert, wenn Entwickler nicht sicher sind, in welchem Projekt Sie sich befindet.

Das Aufteilen von Code für die im Azure devops-Projekt enthaltenen mikrodienste kann etwas schwieriger sein.

![Abbildung 11-2 Single im Vergleich zu mehreren Depots](./media/single-repository-vs-multiple.png)

### <a name="repository-per-microservice"></a>Repository pro mikroservice

Auf den ersten Blick scheint dies der logischste Ansatz für das Aufteilen des Quellcodes für microservices. Jedes Repository kann den Code enthalten, der zum Erstellen des One-mikroservice benötigt wird. Die Vorteile dieses Ansatzes sind leicht sichtbar:

1. Anweisungen zum entwickeln und Verwalten der Anwendung können einer Infodatei im Stammverzeichnis jedes Repository hinzugefügt werden. Beim Kippen durch die Depots ist es einfach, diese Anweisungen zu finden, um die Zeit für Entwickler zu verkürzen.
2. Jeder Dienst befindet sich an einer logischen Stelle und kann leicht gefunden werden, indem er den Namen des dienstanens kennt.
3. Builds können problemlos so eingerichtet werden, dass Sie nur ausgelöst werden, wenn eine Änderung am besitzenden Repository vorgenommen wird.
4. Die Anzahl der in einem Repository kommenden Änderungen ist auf die kleine Anzahl von Entwicklern beschränkt, die an dem Projekt arbeiten.
5. Die Einrichtung der Sicherheit ist einfach, indem die Depots eingeschränkt werden, für die Entwickler über Lese-und Schreibberechtigungen verfügen.
6. Einstellungen auf der Repository-Ebene können vom zuständigen Team mit einer minimalen Diskussion mit anderen Personen geändert werden.

Eines der wichtigsten Ideen hinter den mikrodiensten besteht darin, dass Dienste von einander getrennt und voneinander getrennt werden müssen. Wenn Sie den Domänen gestützten Entwurf verwenden, um die Grenzen für Dienste zu bestimmen, fungieren die Dienste als Transaktionsgrenzen. Datenbankupdates dürfen nicht mehrere Dienste umfassen. Diese Auflistung verwandter Daten wird als begrenzter Kontext bezeichnet.  Diese Idee wird durch die Isolierung von Daten von einem Datenbanksystem zu einer separaten und autonomen Datenbank von den restlichen Diensten reflektiert. Es ist sehr sinnvoll, diese Idee vollständig zum Quellcode zu bringen.

Dieser Ansatz ist jedoch nicht ohne Probleme. Zu den komplexeren Entwicklungsproblemen unserer Zeit zählt die Verwaltung von Abhängigkeiten. Sehen Sie sich die Anzahl der Dateien an, aus denen sich die durchschnittlichen `node_modules` Verzeichnisse richten. Eine Neuinstallation von etwas wie `create-react-app` wird wahrscheinlich Tausende von Paketen mit sich bringen. Die Frage, wie diese Abhängigkeiten verwaltet werden, ist schwierig.

Wenn eine Abhängigkeit aktualisiert wird, muss diese Abhängigkeit von downstreampaketen ebenfalls aktualisiert werden. Leider ist die Entwicklung so, dass das `node_modules`-Verzeichnis immer mehrere Versionen eines einzelnen Pakets verwendet, von denen jedes eine Abhängigkeit von einem anderen Paket ist, das in einem etwas anderen Rhythmus versioniert ist. Welche Version einer Abhängigkeit sollte beim Bereitstellen einer Anwendung verwendet werden? Die Version, die sich derzeit in der Produktionsumgebung befindet? Die Version, die sich zurzeit in der Beta Version befindet, aber wahrscheinlich in der Produktion ist, wenn der Consumer Sie in die Produktion bringt? Schwierige Probleme, die nicht durch die Verwendung von mikroservices gelöst werden.

Es gibt Bibliotheken, die von einer Vielzahl von Projekten abhängen. Durch die Aufteilung der mikrodienste in jedem Repository können die internen Abhängigkeiten am besten mithilfe des internen Repository Azure Artifacts aufgelöst werden. Builds für Bibliotheken verschieben ihre neuesten Versionen in Azure Artifacts für die interne Nutzung. Das downstreamprojekt muss weiterhin manuell aktualisiert werden, um eine Abhängigkeit von den neu aktualisierten Paketen zu übernehmen.

Ein weiterer Nachteil ist das Verschieben von Code zwischen Diensten. Obwohl es sinnvoll wäre, zu glauben, dass die erste Division einer Anwendung in die mikrodienste 100% richtig ist, ist die Realität, dass wir so gut wie möglich sind, um keine Fehler in der Dienst Division zu machen. Daher muss die Funktionalität und der Code, der Sie steuert, von Dienst zu Dienst: Repository in Repository verschoben werden. Beim springen von einem Repository zu einem anderen verliert der Code den Verlauf. Es gibt viele Fälle, insbesondere im Fall einer Überwachung, bei der die vollständige Versionsgeschichte für einen Code Abschnitt von großer Bedeutung ist.

Der endgültige und möglicherweise wichtigste Nachteil ist die Koordinierung von Änderungen. In einer echten mikroservicesanwendung sollten keine Bereitstellungs Abhängigkeiten zwischen Diensten vorhanden sein. Es sollte möglich sein, die Dienste A, B und C in beliebiger Reihenfolge bereitzustellen, da Sie eine lose Kopplung aufweisen. In der Praxis gibt es jedoch Zeiten, in denen es wünschenswert ist, eine Änderung vorzunehmen, die mehrere Depots gleichzeitig überschreitet. Beispiele hierfür sind das Aktualisieren einer Bibliothek, um eine Sicherheitslücke zu schließen oder ein Kommunikationsprotokoll zu ändern, das von allen Diensten verwendet wird.

Zum Durchführen einer übergreifenden Änderung muss ein Commit für jedes Repository nacheinander durchgeführt werden. Jede Änderung in jedem Repository muss per Pull angefordert und separat überprüft werden. Dies kann schwierig zu koordinieren und im allgemeinen ärgerlich sein.

Eine Alternative zur Verwendung vieler Depots besteht darin, den gesamten Quellcode in einem Riesen, allen wissen, einem einzelnen Repository hinzuzufügen.

### <a name="single-repository"></a>Einzelnes Repository

Bei diesem Ansatz, der manchmal auch als [monorepository](https://danluu.com/monorepo/)bezeichnet wird, wird der gesamte Quellcode für jeden Dienst in dasselbe Repository eingefügt. Zunächst scheint dies eine schreckliche Idee zu sein, die den Umgang mit dem Quellcode schwer zu machen hat. Es gibt jedoch einige markierte Vorteile, um auf diese Weise zu arbeiten.

Der erste Vorteil besteht darin, dass es einfacher ist, Abhängigkeiten zwischen Projekten zu verwalten. Anstatt sich auf einen externen artefaktfeed zu verlassen, können Projekte einen anderen direkt importieren. Dies bedeutet, dass Updates sofort und in Konflikt stehende Versionen zur Kompilierzeit auf der Arbeitsstation des Entwicklers gefunden werden. Tatsächlich werden einige der Integrationstests nach links verschoben.

Wenn Sie Code zwischen Projekten verschieben, ist es jetzt einfacher, den Verlauf beizubehalten, da die Dateien als verschoben erkannt werden, anstatt neu geschrieben zu werden.

Ein weiterer Vorteil besteht darin, dass umfangreiche Änderungen, die über Dienst Grenzen hinweg durchgeführt werden können, in einem einzelnen Commit vorgenommen werden Dadurch wird der Aufwand verringert, bei dem möglicherweise Dutzende von Änderungen einzeln überprüft werden.

Es gibt viele Tools, die eine statische Analyse des Codes durchführen können, um unsichere Programmiermethoden oder die problematische Verwendung von APIs zu erkennen. In einer Welt mit mehreren Repository muss jedes Repository durchlaufen werden, um die darin auftretenden Probleme zu finden. Das einzige Repository ermöglicht das Ausführen der Analyse an einem Ort.

Es gibt auch viele Nachteile des einzelnen Repository-Ansatzes. Eine der beunruhigendsten Aspekte besteht darin, dass ein einzelnes Repository Sicherheitsprobleme auslöst. Wenn der Inhalt eines Repository in einem Repository pro Dienstmodell kompromittiert wird, ist die Menge des verlorenen Codes minimal. Mit einem einzelnen Repository könnte alles, was das Unternehmen besitzt, verloren gehen. In der Vergangenheit gab es viele Beispiele, die die gesamte Spieleentwicklung Unternehmen konnten. Das vorhanden sein mehrerer Depots macht weniger Oberfläche verfügbar, was in den meisten Sicherheitsverfahren ein sehr wünschenswert ist.

Die Größe des einzelnen Repository ist wahrscheinlich schnell nicht mehr verwaltbar. Dies stellt einige interessante Auswirkungen auf die Leistung dar. Es kann erforderlich sein, spezielle Tools zu verwenden, wie z. b. das [virtuelle Datei System für git](https://vfsforgit.org/), das ursprünglich entwickelt wurde, um Entwickler im Windows-Team zu verbessern.

Häufig wird das Argument für die Verwendung eines einzelnen Repository auf ein Argument heruntergefahren, das Facebook oder Google diese Methode für die Quell Code Anordnung verwendet. Wenn der Ansatz für diese Unternehmen gut genug ist, dann ist es sicherlich der richtige Ansatz für alle Unternehmen. Die Wahrheit besteht darin, dass nur wenige Unternehmen mit der Skalierung von Facebook oder Google arbeiten. Die Probleme, die bei diesen Skalierungen auftreten, unterscheiden sich von den meisten Entwicklern. Was für die Goose geeignet ist, ist für den Gander möglicherweise nicht gut geeignet.

Am Ende kann eine der beiden Lösungen zum Hosten des Quellcodes für die-Dienste verwendet werden. In den meisten Fällen ist der Verwaltungs-und Engineering-Aufwand, der in einem einzelnen Repository betrieben wird, jedoch nicht für die Vorteile von Vorteilen. Das Aufteilen von Code in mehreren Depots fördert die Trennung von Bereichen und fördert die Autonomie zwischen Entwicklungsteams.  

### <a name="standard-directory-structure"></a>Standard Verzeichnisstruktur

Unabhängig von der Diskussion mit einzelnen und mehreren Depots hat jeder Dienst ein eigenes Verzeichnis. Eine der besten Optimierungen, die es Entwicklern ermöglichen, schnell zwischen Projekten zu überarbeiten, besteht darin, eine Standardverzeichnis Struktur zu verwalten.

![Abbildung 11-3 eine Standardverzeichnis Struktur für die e-Mail-und Anmelde Dienste](./media/dir-struct.png)

Wenn ein neues Projekt erstellt wird, sollte eine Vorlage verwendet werden, die die richtige Struktur einfügt. Diese Vorlage kann auch nützliche Elemente als Skeleton-Infodatei und eine `azure-pipelines.yml`enthalten. In jeder microservice-Architektur führt ein hohes Maß an Varianz zwischen Projekten zu einer schwierigeren Ausführung von Massen Vorgängen für die Dienste.

Es gibt viele Tools, die Vorlagen für ein gesamtes Verzeichnis bereitstellen können, das mehrere Quell Code Verzeichnisse enthält. [Yeoman](https://yeoman.io/) ist in der JavaScript-Welt beliebt, und GitHub hat vor kurzem [Repository-Vorlagen](https://github.blog/2019-06-06-generate-new-repositories-with-repository-templates/)veröffentlicht, die viele der gleichen Funktionen bereitstellen.

## <a name="task-management"></a>Task Verwaltung

Das Verwalten von Aufgaben in Projekten kann schwierig sein. Im Vorfeld sind unzählige Fragen über die Art der Workflows zu beantworten, um die optimale Produktivität von Entwicklern sicherzustellen.

Native cloudanwendungen sind tendenziell kleiner als herkömmliche Softwareprodukte, oder Sie sind zumindest in kleinere Dienste unterteilt. Die Nachverfolgung von Problemen oder Tasks im Zusammenhang mit diesen Diensten bleibt ebenso wichtig wie bei allen anderen Softwareprojekten. Niemand möchte den Überblick über ein Arbeits Element verlieren oder einem Kunden erklären, dass das Problem nicht ordnungsgemäß protokolliert wurde. Boards werden auf Projektebene konfiguriert, aber in jedem Projekt können Bereiche definiert werden. Diese ermöglichen das Aufteilen von Problemen über mehrere Komponenten hinweg. Der Vorteil, dass alle Aufgaben für die gesamte Anwendung an einem Ort aufbewahrt werden, besteht darin, dass es einfach ist, Arbeitselemente von einem Team auf ein anderes zu verschieben, da Sie besser verstanden werden.

Azure devops enthält eine Reihe von gängigen vorkonfigurierten Vorlagen. In der grundlegendsten Konfiguration müssen Sie lediglich wissen, was im Rückstand liegt, von welchen Personen Sie arbeiten und was erledigt ist. Es ist wichtig, dass Sie diese Einblicke in den Prozess der Software Erstellung haben, sodass die Arbeit priorisiert und abgeschlossene Aufgaben an den Kunden gesendet werden kann. Natürlich bleiben nur wenige Softwareprojekte so einfach wie `to do`, `doing`und `done`. Es dauert nicht lange, bis die Benutzer mit dem Hinzufügen von Schritten wie `QA` oder `Detailed Specification` zum Prozess beginnen.

Einer der wichtigsten Bestandteile von Agile-Methoden ist die selbstgeh Aufnahme in regelmäßigen Abständen. Diese Überprüfungen sollen Aufschluss darüber geben, welche Probleme das Team hat und wie Sie verbessert werden können. Häufig bedeutet dies, dass der Fluss von Problemen und Features durch den Entwicklungsprozess geändert wird. Daher ist es ganz problemlos, die Layouts der Boards mit zusätzlichen Stufen zu erweitern.

Die Phasen in den Boards sind nicht das einzige Organisations Tool. Abhängig von der Konfiguration des Boards gibt es eine Hierarchie von Arbeits Elementen. Das differenzierteste Element, das auf einem Board angezeigt werden kann, ist eine Aufgabe. Standardmäßig enthält eine Aufgabe Felder für einen Titel, eine Beschreibung, eine Priorität, eine Schätzung der verbleibenden Arbeit und die Möglichkeit, eine Verknüpfung zu anderen Arbeits Elementen oder Entwicklungs Elementen (branches, Commits, Pull Requests, Builds usw.) zu erstellen. Arbeitselemente können in verschiedene Bereiche der Anwendung und verschiedene Iterationen (Sprints) klassifiziert werden, um die Suche zu vereinfachen.

![Abbildung 11-4 eine Beispiel Aufgabe in Azure devops](./media/task-details.png)

Das Beschreibungsfeld unterstützt die normalen Formate, die Sie erwarten (Fett, kursiv und durchgestrichen), sowie die Möglichkeit zum Einfügen von Bildern. Dies ist ein sehr leistungsfähiges Tool zur Verwendung bei der Angabe von Arbeit oder Fehlern.

Aufgaben können in Funktionen eingeführt werden, die eine größere Arbeitseinheit definieren. Funktionen können wiederum in [EPICS hoch](https://docs.microsoft.com/azure/devops/boards/backlogs/define-features-epics?view=azure-devops)Gefahren werden. Durch die Klassifizierung von Aufgaben in dieser Hierarchie wird deutlich leichter zu verstehen, wie das Rollout eines großen Features das Rollout ermöglicht.

![Abbildung 11-5 standardmäßig konfigurierte Arbeits Elementtypen in der grundlegenden Prozess Vorlage](./media/board-issue-types.png)

Es gibt unterschiedliche Arten von Ansichten zu den Problemen in Azure Boards. Elemente, die noch nicht geplant sind, werden im Rückstand angezeigt. Von dort aus können Sie einem Sprint zugewiesen werden. Bei einem Sprint handelt es sich um ein Zeitfenster, in dem erwartet wird, dass eine Menge Arbeit abgeschlossen wird. Diese Arbeit kann Tasks, aber auch die Auflösung von Tickets umfassen. Anschließend kann der gesamte Sprint über den Abschnitt Sprint Board verwaltet werden. Diese Ansicht zeigt, wie die Arbeit fortschreitet, und enthält ein Dropdown Diagramm, das eine aktualisierbare Schätzung anzeigt, wenn der Sprint erfolgreich sein wird.

![Abbildung 11-6 ein Board mit definiertem Sprint](./media/sprint-board.png)

Mittlerweile ist es offensichtlich, dass die Boards in Azure devops eine große Menge an Leistungsfähigkeit aufweisen. Für Entwickler gibt es einfache Sichten, was bearbeitet wird. Für Projektmanager-Ansichten anstehende Arbeit und eine Übersicht über die vorhandene Arbeit. Für Manager gibt es viele Berichte über die Beschaffung und Kapazität. Leider gibt es keine magischen cloudbasierten Anwendungen, die das Nachverfolgen der Arbeit ausschließen. Wenn Sie jedoch die Arbeit nachverfolgen müssen, gibt es einige Orte, an denen die Umgebung besser als in Azure devops ist.

## <a name="cicd-pipelines"></a>CI/CD-Pipelines

Fast keine Änderung im Lebenszyklus der Softwareentwicklung war so revolutionär wie die Einführung von Continuous Integration (CI) und Continuous Delivery (CD). Das entwickeln und Ausführen automatisierter Tests für den Quellcode eines Projekts, sobald eine Änderung aktiviert ist, fängt Fehler frühzeitig ab. Vor der Einführung von Continuous Integration Builds wäre es nicht ungewöhnlich, Code aus dem Repository zu übertragen und festzustellen, dass er keine Tests bestanden hat oder überhaupt nicht erstellt werden konnte. Dies führte zu einer großen Nachverfolgung der Quelle des Bruchs.

Die Lieferung von Software an die Produktionsumgebung erforderte in der Regel eine umfassende Dokumentation und eine Liste von Schritten. Jeder dieser Schritte muss in einem sehr fehleranfälligen Prozess manuell abgeschlossen werden.

![Abbildung 11-7 A Checkliste](./media/checklist.png)

Die Schwester von Continuous Integration wird Continuous Delivery, in der die neu erstellten Pakete in einer Umgebung bereitgestellt werden. Der manuelle Prozess kann nicht entsprechend der Entwicklungsgeschwindigkeit skaliert werden, sodass die Automatisierung wichtiger wird. Checklisten werden durch Skripts ersetzt, die die gleichen Aufgaben schneller und präziser ausführen können als alle menschlichen.

Die Umgebung, in der Continuous Delivery bereitstellt, ist möglicherweise eine Testumgebung oder, wie von vielen großen Technologieunternehmen, möglicherweise die Produktionsumgebung. Letzteres erfordert eine Investition in hochwertige Tests, die sicher sein können, dass eine Änderung die Produktion für Benutzer nicht unterbricht. Auf dieselbe Weise, wie Continuous Integration Probleme im Code früh abgefangen Continuous Delivery, fängt Probleme im Bereitstellungs Prozess frühzeitig ab.

Die Automatisierung des Erstellungs-und Übermittlungs Prozesses wird durch Native Cloud-Anwendungen verstärkt. Bereit Stellungen werden häufiger und in mehr Umgebungen ausgeführt, sodass Rahmen nicht potenziell manuell bereitgestellt werden.

### <a name="azure-builds"></a>Azure-Builds

Azure devops bietet eine Reihe von Tools, um Continuous Integration und die Bereitstellung einfacher als je zuvor zu gestalten. Diese Tools befinden sich unter Azure Pipelines. Der erste Vorgang ist Azure-Builds, bei dem es sich um ein Tool zum horizontalen Ausführen von YAML-basierten Builddefinitionen handelt. Benutzer können entweder Ihre eigenen Buildcomputer verwenden (hervorragend für den Build, wenn der Build eine sorgfältige Einrichtung erfordert) oder einen Computer aus einem ständig aktualisierten Pool von in Azure gehosteten virtuellen Computern verwenden. Diese gehosteten Build-Agents werden mit einer Vielzahl von Entwicklungs Tools installiert, die nicht nur die .net-Entwicklung, sondern auch alles von der Java-zu-python-bis iPhone-Entwicklung unterliegen.

Devops enthält eine breite Palette von Standard-Builddefinitionen, die für jeden Build angepasst werden können. Die Builddefinitionen werden in einer Datei namens `azure-pipelines.yml` definiert und in das Repository eingecheckt, damit Sie zusammen mit dem Quellcode versioniert werden können. Dies erleichtert es, Änderungen an der Buildpipeline in einer Verzweigung vorzunehmen, da die Änderungen nur in dieser Verzweigung eingecheckt werden können. Ein Beispiel `azure-pipelines.yml` zum Aufbauen einer ASP.NET-Webanwendung im vollständigen Framework finden Sie in Abbildung 11-8.

```yml
name: $(rev:r)

variables:
  version: 9.2.0.$(Build.BuildNumber)
  solution: Portals.sln
  artifactName: drop
  buildPlatform: any cpu
  buildConfiguration: release
  
pool:
  name: Hosted VS2017
  demands:
  - msbuild
  - visualstudio
  - vstest

steps:
- task: NuGetToolInstaller@0
  displayName: 'Use NuGet 4.4.1'
  inputs:
    versionSpec: 4.4.1

- task: NuGetCommand@2
  displayName: 'NuGet restore'
  inputs:
    restoreSolution: '$(solution)'

- task: VSBuild@1
  displayName: 'Build solution'
  inputs:
    solution: '$(solution)'
    msbuildArgs: '-p:DeployOnBuild=true -p:WebPublishMethod=Package -p:PackageAsSingleFile=true -p:SkipInvalidConfigurations=true -p:PackageLocation="$(build.artifactstagingdirectory)\\"'
    platform: '$(buildPlatform)'
    configuration: '$(buildConfiguration)'

- task: VSTest@2
  displayName: 'Test Assemblies'
  inputs:
    testAssemblyVer2: |
     **\$(buildConfiguration)\**\*test*.dll
     !**\obj\**
     !**\*testadapter.dll
    platform: '$(buildPlatform)'
    configuration: '$(buildConfiguration)'

- task: CopyFiles@2
  displayName: 'Copy UI Test Files to: $(build.artifactstagingdirectory)'
  inputs:
    SourceFolder: UITests
    TargetFolder: '$(build.artifactstagingdirectory)/uitests'

- task: PublishBuildArtifacts@1
  displayName: 'Publish Artifact'
  inputs:
    PathtoPublish: '$(build.artifactstagingdirectory)'
    ArtifactName: '$(artifactName)'
  condition: succeededOrFailed()
```

**Abbildung 11-8** -Beispiel Azure-Pipelines. yml

Diese Builddefinition verwendet eine Reihe integrierter Aufgaben, die das Erstellen von Builds so einfach gestalten wie das Erstellen eines LEGO-Satzes (einfacher als der Giant Millennium-Falcon). Beispielsweise stellt die nuget-Aufgabe nuget-Pakete wieder her, während die vsbuild-Aufgabe die Visual Studio-Buildtools aufruft, um die tatsächliche Kompilierung auszuführen. Es gibt Hunderte verschiedener Aufgaben in Azure devops, von denen Tausende von der Community verwaltet werden. Es ist wahrscheinlich, dass Sie unabhängig von den Buildaufgaben, die Sie ausführen möchten, bereits eine erstellt haben.

Builds können manuell, durch einen Eincheck Vorgang, nach einem Zeitplan oder nach dem Abschluss eines anderen Builds ausgelöst werden. In den meisten Fällen ist das entwickeln bei jedem Einchecken wünschenswert. Builds können so gefiltert werden, dass unterschiedliche Builds für verschiedene Teile des Repository oder für verschiedene Verzweigungen ausgeführt werden. Dies ermöglicht Szenarien wie das Ausführen von schnellen Builds mit reduzierten Tests für Pull Requests und das Ausführen einer vollständigen Regressions Suite für den trunk in einer Nacht.

Das Endergebnis eines Builds ist eine Auflistung von Dateien, die als buildartefakte bezeichnet werden. Diese Artefakte können an den nächsten Schritt im Buildprozess weitergegeben oder einem Azure-artefaktfeed hinzugefügt werden, sodass Sie von anderen Builds verwendet werden können.

### <a name="azure-devops-releases"></a>Azure devops-Releases

Builds übernehmen die Kompilierung der Software in ein abrechenbares Paket, aber die Artefakte müssen nach wie vor in eine Testumgebung übermittelt werden, um Continuous Delivery abzuschließen. Hierfür verwendet Azure devops ein separates Tool namens Releases. Releases verwenden die Bibliothek derselben Aufgaben, die für den Build verfügbar waren, aber ein Konzept von "Stufen" darstellen. Eine Stufe ist eine isolierte Umgebung, in der das Paket installiert wird. Beispielsweise kann ein Produkt eine Entwicklungs-, QA-und Produktionsumgebung verwenden. Der Code wird kontinuierlich in der Entwicklungsumgebung bereitgestellt, in der automatisierte Tests ausgeführt werden können. Wenn diese Tests bestanden wurden, werden die Releases für manuelle Tests in die QA-Umgebung verschoben. Schließlich wird der Code in die Produktion übermittelt, wo er für alle sichtbar ist.

![Abbildung 11-9 eine Beispiel-releasepipeline mit Entwicklungs-, QA-und Produktionsphasen](./media/release-pipeline.png)

Jede Phase im Build kann automatisch durch den Abschluss der vorherigen Phase ausgelöst werden. In vielen Fällen ist dies jedoch nicht wünschenswert. Das Verschieben von Code in die Produktion erfordert möglicherweise eine Genehmigung von einem anderen Releases unterstützen dies, indem genehmigende Personen in jedem Schritt der releasepipeline zugelassen werden. Regeln können so eingerichtet werden, dass eine bestimmte Person oder Gruppe von Personen sich bei einem Release anmelden muss, bevor es in der Produktion erfolgt. Diese Gates ermöglichen manuelle Qualitätsprüfungen sowie die Einhaltung gesetzlicher Bestimmungen, die Steuern, was in die Produktion übergeht.

### <a name="everybody-gets-a-build-pipeline"></a>Jeder erhält eine Buildpipeline.

Es fallen keine Kosten für die Konfiguration vieler buildpipelines an, daher ist es vorteilhaft, mindestens eine Buildpipeline pro mikroservice zu erstellen. Im Idealfall können Sie in jeder Umgebung unabhängig voneinander bereitgestellt werden, sodass jedes einzelne über seine eigene Pipeline freigegeben werden kann, ohne dass eine Menge nicht verknüpfter Codes freigegeben werden kann. Jede Pipeline kann über einen eigenen Satz von Genehmigungen verfügen, die Variationen des Buildprozesses für jeden Dienst ermöglichen.

### <a name="versioning-releases"></a>Versionierung von Releases

Ein Nachteil bei der Verwendung der Releases-Funktionalität besteht darin, dass Sie nicht in einem eingecheckten `azure-pipelines.yml` Datei definiert werden kann. Es gibt viele Gründe, aus denen Sie herausfinden können, dass Sie in der Projektvorlage Verzweigungs Definitionen mit freiverzweigungen hinzufügen möchten. Glücklicherweise wird die Arbeit fortlaufend durchgeführt, um einige der Stufen Unterstützung in die Buildkomponente zu verlagern. Dies wird als mehrstufiger Build bezeichnet, und die [erste Version ist jetzt verfügbar](https://devblogs.microsoft.com/devops/whats-new-with-azure-pipelines/)!

>[!div class="step-by-step"]
>[Zurück](azure-security.md)
>[Weiter](infrastructure-as-code.md)
