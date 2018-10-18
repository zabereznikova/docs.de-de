---
title: Serverlose Architektur Überlegungen zum – serverlose apps
description: Verstehen Sie die Herausforderungen beim Entwerfen von serverloser Anwendungen, Zustandsverwaltung und permanenten Speicher zu skalieren, Protokollierung, Ablaufverfolgung und Diagnose.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 5f175351cf42f3d9966add72750d64a4efe14e07
ms.sourcegitcommit: bd4fa78f5a46133efdead1bc692a9aa2811d7868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/23/2018
ms.locfileid: "49370015"
---
# <a name="serverless-architecture-considerations"></a>Überlegungen für eine serverlose Architektur

Einführung einer serverlosen Architektur mit einigen Herausforderungen stammen. In diesem Abschnitt werden einige allgemeinen Überlegungen zu beachten. All diese Herausforderungen bieten Lösungen. Wie bei allen architekturoptionen, sollten die Entscheidung, serverlose Architektur vorgenommen werden, erst nach dem sorgfältig abwägen der vor- und Nachteile. Je nach den Anforderungen Ihrer Anwendung können Sie entscheiden, dass eine serverlose Implementierung die richtige Lösung für bestimmte Komponenten nicht.

## <a name="managing-state"></a>Verwalten des Zustands

Serverlose Funktionen sind wie bei Microservices im Allgemeinen ist standardmäßig zustandslos. Vermeiden Zustand ermöglicht serverlose flüchtig, Skalierung und resilienz, ohne ein zentraler Point of Failure zu gewährleisten. In einigen Fällen erfordern Geschäftsprozesse Zustand. Wenn der Prozess Zustand erfordert, müssen Sie zwei Optionen zur Verfügung. Sie können ein Modell als serverlose übernehmen oder interagieren mit einem separaten Dienst, der Statusinformationen bereitstellt. Hinzufügen eines Status kann erschweren die Lösung schwieriger zu skalieren und möglicherweise erstellen Sie eine einzelne Fehlerquelle. Überlegen Sie, ob Sie Ihre Funktion Steuerelementzustand absolut erforderlich ist. Wenn die Antwort "Ja" lautet, zu bestimmen, ob es weiterhin so implementieren Sie sie mit der serverlosen sinnvoll.

Es gibt mehrere Lösungen Zustand ohne Beeinträchtigung der Vorteile des serverlosen übernehmen. Einige der beliebtesten Lösungen umfassen:

* Verwenden Sie einen temporären Datenspeicher oder verteilten Cache, z. B. Redis
* Store-Status in einer Datenbank wie SQL oder COSMOS DB
* Behandeln des Status über eine Workflow-Engine wie durable functions

Das Fazit ist, dass Sie die Notwendigkeit Zustände verwaltet innerhalb von Prozessen, die Sie darüber nachdenken berücksichtigen sollten, mit der serverlosen implementieren.

## <a name="long-running-processes"></a>Lang andauernde Prozesse

Viele der Vorteile des serverlosen abhängig von der werden kurzlebige Prozesse ab. Kurze Ausführungszeiten erleichtern es, für den serverlosen Anbieter, um Ressourcen freizugeben, wie die End- und -Freigabe-Funktionen über Hosts hinweg funktioniert. Die meisten Cloudanbieter beschränken die Gesamtzeit, die Ihre Funktion auf ca. 10 Minuten ausgeführt werden kann. Wenn der Prozess länger dauern kann, sollten Sie eine alternative Implementierung.

Es gibt einige Ausnahmen und Lösungen. Eine Lösung kann sein, um den Prozess in kleinere Komponenten zu unterbrechen, die einzeln weniger Zeit in Anspruch nehmen. Wenn der Prozess aufgrund von Abhängigkeiten lange ausgeführt wird, können Sie auch einen asynchronen Workflow mit einer Lösung wie durable Functions in Betracht ziehen. Durable Functions anhalten und behalten den Status der der Prozess, beim Warten auf einen externen Prozess, um den Vorgang abzuschließen. Asynchrone Behandlung reduziert die Zeit, die der tatsächliche Prozess ausgeführt wird.

## <a name="startup-time"></a>Startzeit

Ein potenzielles Problem ist mit serverlosen Implementierungen ist die Startzeit. Um Ressourcen zu sparen, erstellen viele serverlose Anbieter-Infrastruktur "bei Nachfrage." Wenn nach einiger Zeit eine serverlose Funktion ausgelöst wird, können die Ressourcen zum Hosten der Funktion erstellt oder neu gestartet werden müssen. In einigen Situationen möglicherweise die Kaltstarts zu Verzögerungen von mehreren Sekunden. Dauer des verbindungsstarts variieren je nach Anbieter und Servicelevels. Es gibt einige Ansätze zur Startzeit für die Adresse ist es wichtig, für den Erfolg der app zu minimieren.

* Einige Anbieter Benutzern zum Servicelevel bezahlen, die garantieren, dass die Infrastruktur "immer aktiviert" ist.
* Implementieren Sie einen Keep-alive-Mechanismus (Ping den Endpunkt, "aktiv" zu halten).
* Verwenden Sie die Orchestrierung wie Kubernetes mit einem Container ausgeführte Funktion-Ansatz (der Host wird bereits ausgeführt, also Einrichten neuer Instanzen extrem schnelle).

## <a name="database-updates-and-migrations"></a>Datenbank-Updates und Migrationen

Ein Vorteil von serverlosem Code ist, dass Sie neue Funktionen freigeben können, ohne die gesamte Anwendung erneut bereitzustellen. Dieser Vorteil kann ein Nachteil werden, wenn es eine relationale Datenbank beteiligt ist. Änderungen an Datenbankschemas sind schwierig zu mit serverlosen Updates zu synchronisieren. Weitere Herausforderungen werden ausgesetzt, wenn Dinge schief gehen ein, und die Änderungen rückgängig gemacht werden müssen. Integrität der Daten ist einer der Gründe, die eine bewährte Methode für Microservices und serverlose Funktionen, die sie ihre eigenen Daten besitzen. Es ist möglich, Änderungen als eine Einheit von computeressourcen und Daten bereitstellen. Die Realität ist, dass viele Legacysysteme eine große Datenbank für die Back-End-Funktion, die mit der serverlosen Architektur abgestimmt sein müssen.

Ein beliebter Ansatz zur Lösung der versionsverwaltung des Schemas ist, ändern Sie niemals die vorhandenen Eigenschaften und Spalten, sondern stattdessen die neuen Informationen hinzufügen. Betrachten Sie beispielsweise eine Änderung zum Verschieben in einen booleschen Wert "completed" Flag für eine to-Do-Liste für die "Abschlussdatum." Werden anstelle von entfernen das alte Feld ein, der datenbankänderungen aus:

1. Ein neues "Erledigt am" Feld hinzufügen.
1. Transformieren Sie die "Abgeschlossene" boolesche Feld, um eine berechnete-Funktion, die ermittelt, ob das abgeschlossene Datum nach dem aktuellen Datum liegt.
1. Hinzufügen eines Triggers für das aktuelle Datum das Abschlussdatum fest abgeschlossenen der boolesche Wert, wenn festgelegt wird auf "true".

Die Reihenfolge der Änderungen wird sichergestellt, dass es sich bei legacy-Code wird weiterhin "wie besehen" ausgeführt, während neuere serverlose Funktionen des neuen Felds nutzen können.

Weitere Informationen zu Daten in einer serverlosen Architekturen finden Sie unter [Herausforderungen und Lösungen für die verteilte datenverwaltung](../microservices-architecture/architect-microservice-container-applications/distributed-data-management.md).

## <a name="scaling"></a>Skalieren

Es ist ein häufiges Missverständnis, dass mit der serverlosen "wurde kein Server". Es ist tatsächlich "weniger Server." Es ist eine unterstützende Infrastruktur ist wichtig zu verstehen, wenn es auf die Skalierung geht. Die meisten serverlose Plattformen bieten einen Satz von Steuerelementen zu behandeln, wie die Infrastruktur skaliert werden sollen, wenn das Ereignis Dichte zunimmt. Sie können aus einer Vielzahl von Optionen auswählen, aber Ihre Strategie variieren abhängig von der Funktion. Darüber hinaus sind Funktionen in der Regel unter einem entsprechenden Host ausgeführt werden, damit Funktionen auf dem gleichen Host die gleiche Skalierungsoptionen haben. Aus diesem Grund ist es erforderlich, organisieren und skalierungsanforderungen anhand strategiefindung welche Funktionen gehostet werden.

Regeln geben häufig an, wie hochskalieren (Erhöhen der Hostressourcen) und horizontal skalieren (Vergrößern der Anzahl von Instanzen des Hosts) basierend auf verschiedenen Parametern. Trigger für die Skalierungen können Zeitplan, anforderungsraten, CPU-Auslastung und speicherauslastung enthalten. Höhere Leistung oft hat Ihren Preis größer. Die Ansätze kostengünstiger und verbrauchsbasierte können nicht skaliert werden, mit zunehmender schnell Wenn die Anforderungsrate plötzlich. Es muss ein Kompromiss zwischen anmerken "insurance Kosten" im Vergleich zu Bezahlung Zahlen ausschließlich "wie go", und langsamere Antworten aufgrund von einem plötzlichen Anstieg bei Bedarf zu riskieren.

## <a name="monitoring-tracing-and-logging"></a>Überwachung, Ablaufverfolgung und Protokollierung

Ein häufig vernachlässigter Aspekt der DevOps überwacht Anwendungen, die nach der Bereitstellung. Es ist wichtig, eine Strategie zum Überwachen von serverloser Funktionen. Die größte Herausforderung ist häufig auf, Korrelation oder erkant werden, wenn ein Benutzer mehrere Funktionen als Teil der gleichen Aktivität aufruft. Die meisten serverlose Plattformen zulassen, dass die Konsolenoptionen zur Protokollanzeige, die in Drittanbieter-Tools importiert werden kann. Es gibt auch Optionen zum Automatisieren der Erfassung von Telemetriedaten, generieren und Nachverfolgen von Korrelations-IDs und überwachen bestimmte Aktionen, um detaillierte Einblicke zu bieten. Azure bietet erweiterten [Application Insights-Plattform](https://docs.microsoft.com/azure/azure-functions/functions-monitoring) für Überwachung und Analyse.

## <a name="inter-service-dependencies"></a>Kommunikation zwischen Diensten Abhängigkeiten

Eine serverlose Architektur kann Funktionen enthalten, die auf andere Funktionen basieren. In der Tat ist es nicht ungewöhnlich, dass in einer serverlosen Architektur, die mehrere Dienste im Rahmen einer Interaktion oder verteilte Transaktion gegenseitig aufrufen. Um starke Kopplung zu vermeiden, empfiehlt es sich, dass Dienste nicht direkt auf miteinander verweisen. Wenn der Endpunkt für einen Dienst geändert werden muss, können direkte Verweise zu wichtigen refactoring führen. Eine empfohlene Lösung ist, einen dienstermittlungsmechanismus, z. B. einer Registrierung bereitzustellen, die den entsprechenden Endpunkt für einen Anforderungstyp bereitstellt. Eine andere Lösung besteht darin, messaging-Dienste wie Warteschlangen oder Themen für die Kommunikation zwischen Diensten zu nutzen.

## <a name="managing-failure-and-providing-resiliency"></a>Fehler beim Verwalten und resilienz bereitstellen

Es ist auch wichtig zu berücksichtigen die *Circuit-Breaker-Muster*: Wenn Sie aus irgendeinem Grund, weiterhin ein Dienst ein Fehler auftritt, ist es nicht ratsam, diesen Dienst wiederholt aufrufen. Stattdessen wird ein alternativer Dienst aufgerufen wird, oder eine Meldung zurückgegeben, bis die Integrität der abhängige Dienst wiederhergestellt ist. Die serverlose Architektur muss die Strategie zum Auflösen von, und Verwalten von dienstübergreifende Abhängigkeiten berücksichtigen.

Zum Fortsetzen des Vorgangs des Trennschalter Musters müssen Dienste Fehlertoleranz und stabil sein. Fehlertoleranz bezeichnet die Fähigkeit Ihrer Anwendung weiter ausgeführt wird, auch nach dem unerwarteten Ausnahmen oder ungültige Zuständen auftreten. Fehlertoleranz ist in der Regel an eine Funktion des Codes selbst und wie es geschrieben hat, um Ausnahmen zu behandeln. Stabilität bezieht sich auf wie die app auf die Wiederherstellung bei Fehlern kann. Resilienz wird häufig durch die serverlose Plattform verwaltet werden. Die Plattform sollte in der Lage, um eine neue Instanz der serverlosen Funktion zu starten, wenn der vorhandenen Dateigruppe nicht. Die Plattform sollte auch intelligent genug sind, so einrichten neuer Instanzen beenden, wenn es sich bei jeder neuen-Instanz ein Fehler auftritt.

Weitere Informationen finden Sie unter [Implementieren des trennschaltermusters](../microservices-architecture/implement-resilient-applications/implement-circuit-breaker-pattern.md).

## <a name="versioning-and-greenblue-deployments"></a>Versionsverwaltung und Grün/Blau-Bereitstellungen

Ein großer Vorteil von serverlosen ist die Möglichkeit, eine bestimmte Funktion aktualisieren, ohne dass die gesamte Anwendung erneut bereitstellen. Für Upgrades erfolgreich ist müssen Funktionen mit Versionsangabe sein, damit die richtige Version des Codes die aufrufenden Dienste gedrosselt, weitergeleitet werden. Eine Strategie für das Bereitstellen neuer Versionen ist auch wichtig. Eine gängige Methode ist die Verwendung von "Bereitstellungen Grün/Blau." Die grüne Bereitstellung ist die aktuelle Funktion. Eine neue Version für "blaue" ist in der produktionsumgebung bereitgestellt und getestet. Beim Testen von Pass werden die grünen und blauen Versionen ausgetauscht, damit die neue Version live stammt. Wenn Probleme auftreten, können sie wieder ausgetauscht werden. Unterstützung der versionsverwaltung und Grün/Blau-Bereitstellungen erfordert eine Kombination von Funktionen zur Aufnahme von Änderungen an der Typsystemversion erstellen und Arbeiten mit der serverlosen Plattform Bereitstellungen verarbeiten. Ein möglicher Ansatz ist die Verwendung von Proxys, die in beschrieben werden die [serverlose Azure-Plattform](azure-functions.md#proxies) Kapitel.

>[!div class="step-by-step"]
[Zurück](serverless-architecture.md)
[Weiter](serverless-design-examples.md)
