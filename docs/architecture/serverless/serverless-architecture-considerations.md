---
title: Überlegungen zur Server losen Architektur-Server Lose apps
description: Informieren Sie sich über die Herausforderungen der Architektur von Server losen Anwendungen, von der Zustands Verwaltung und von permanentem Speicher bis hin zu Skalierung, Protokollierung, Ablauf Verfolgung
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: ecbffbbd435b4926608e4def519fdaddddab688d
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "69577433"
---
# <a name="serverless-architecture-considerations"></a>Überlegungen zur serverlosen Architektur

Die Übernahme einer Server losen Architektur bringt bestimmte Herausforderungen mit sich. In diesem Abschnitt werden einige der gängigeren Überlegungen erläutert, die Sie kennen sollten. Alle diese Herausforderungen haben Lösungen. Wie bei allen Architektur Optionen sollte die Entscheidung, die Server lose Entscheidung zu treffen, erst nach der sorgfältigen Betrachtung der vor-und Nachteile getroffen werden. Abhängig von den Anforderungen Ihrer Anwendung können Sie entscheiden, dass eine Server lose Implementierung nicht die richtige Lösung für bestimmte Komponenten ist.

## <a name="managing-state"></a>Verwalten des Zustands

Server lose Funktionen, wie z. b. die allgemeinen Funktionen, sind standardmäßig zustandslos. Durch das vermeiden des Zustands kann Server lose kurzlebig sein, horizontal hochskaliert werden und Resilienz ohne einen zentralen Fehlerpunkt bereitstellen. In einigen Fällen ist für Geschäftsprozesse der Status erforderlich. Wenn Ihr Prozess den Status erfordert, haben Sie zwei Möglichkeiten. Sie können ein anderes Modell als Server lose übernehmen oder mit einem separaten Dienst interagieren, der den Status bereitstellt. Das Hinzufügen des Zustands kann die Lösung erschweren und die Skalierung erschweren und potenziell einen Single Point of Failure erstellen. Überlegen Sie sorgfältig, ob Ihre Funktion den Status absolut erfordert. Wenn die Antwort "Ja" lautet, legen Sie fest, ob es immer noch sinnvoll ist, Sie mit Server less zu implementieren.

Es gibt mehrere Lösungen, um den Status zu übernehmen, ohne die Vorteile von Server losen zu gefährden. Zu den beliebtesten Lösungen gehören:

* Verwenden eines temporären Datenspeichers oder verteilter Caches wie redis
* Speichern des Zustands in einer Datenbank, wie z. b. SQL oder cosmosdb
* Handle des Zustands durch eine Workflow-Engine wie Durable Functions

Die untere Zeile besteht darin, dass Sie die Notwendigkeit einer Zustands Verwaltung in Prozessen beachten sollten, die Sie mit Server losen Implementierung in Erwägung ziehen.

## <a name="long-running-processes"></a>Prozesse mit langer Ausführungszeit

Viele Vorteile von Server lose basieren auf den kurzlebigen Prozessen. Kurze Laufzeiten vereinfachen es dem Server losen Anbieter, Ressourcen freizugeben, wenn Funktionen beendet werden und Funktionen auf allen Hosts freigeben. Die meisten cloudanbieter beschränken die Gesamtzeit, für die die Funktion ausgeführt werden kann, auf ungefähr 10 Minuten. Wenn Ihr Prozess länger dauern kann, können Sie eine alternative Implementierung in Erwägung ziehen.

Es gibt einige Ausnahmen und Lösungen. Eine Lösung kann darin bestehen, den Prozess in kleinere Komponenten zu unterteilen, die für die Ausführung einzeln weniger Zeit in Anspruch nehmen. Wenn Ihr Prozess aufgrund von Abhängigkeiten lange ausgeführt wird, können Sie auch einen asynchronen Workflow mithilfe einer Lösung wie Durable Functions in Erwägung gezogen. Durable Functions hält den Status des Prozesses an und behält ihn bei, während er darauf wartet, dass ein externer Prozess beendet wird. Die asynchrone Behandlung verringert die Zeit, die der tatsächliche Prozess ausgeführt wird.

## <a name="startup-time"></a>Startzeit

Ein mögliches Problem bei Server losen Implementierungen ist die Startzeit. Um Ressourcen zu sparen, erstellen viele Server lose Anbieter die Infrastrukturbedarfs gesteuert. Wenn nach einer bestimmten Zeitspanne eine Server lose Funktion ausgelöst wird, müssen möglicherweise die Ressourcen zum Hosten der Funktion erstellt oder neu gestartet werden. In einigen Fällen kann es zu Verzögerungen bei einem Kaltstart kommen, die mehrere Sekunden dauern. Die Startzeit variiert je nach Anbieter und Dienst Ebene. Es gibt einige Ansätze zum Beheben der Startzeit, wenn es wichtig ist, den Erfolg der APP zu minimieren.

* Einige Anbieter ermöglichen es Benutzern, Service Levels zu zahlen, die die Infrastruktur "Always on" garantieren.
* Implementieren Sie einen Keep-Alive-Mechanismus (Pingen Sie den Endpunkt, um die Sicherheit zu gewährleisten).
* Verwenden Sie eine Orchestrierung wie Kubernetes mit einem Ansatz für eine containerisierte Funktion (der Host wird bereits ausgeführt, sodass das Einrichten neuer Instanzen äußerst schnell ist).

## <a name="database-updates-and-migrations"></a>Datenbankaktualisierungen und-Migrationen

Ein Vorteil von Server losem Code besteht darin, dass Sie neue Funktionen freigeben können, ohne die gesamte Anwendung erneut bereitstellen zu müssen. Dieser Vorteil kann zu einem Nachteil werden, wenn eine relationale Datenbank beteiligt ist. Änderungen an Datenbankschemas sind schwer zu synchronisieren und Server lose Updates. Weitere Herausforderungen werden ausgelöst, wenn ein Fehler auftritt und für die Änderungen ein Rollback ausgeführt werden muss. Die Datenintegrität ist ein Grund dafür, dass eine bewährte Vorgehensweise für Funktionen von-und Server losen Funktionen darin besteht, dass Sie Ihre eigenen Daten besitzen. Es ist möglich, Änderungen als eine einzelne Einheit von COMPUTE-und-Daten bereitzustellen. Die Realität ist, dass viele Legacy Systeme eine große Back-End-Datenbank aufweisen, die mit der Server losen Architektur abgestimmt werden muss.

Ein beliebter Ansatz zum Lösen der Schema Versionsverwaltung besteht darin, niemals vorhandene Eigenschaften und Spalten zu ändern, sondern stattdessen neue Informationen hinzuzufügen. Nehmen Sie beispielsweise an, dass eine Änderung von einem booleschen "abgeschlossenen" Flag für eine TODO-Liste zu einem "abgeschlossenen Datum" verschoben wird. Anstatt das alte Feld zu entfernen, wird die Daten Bank Änderung wie folgt durchführt:

1. Fügen Sie ein neues Feld "abgeschlossene Datumsangaben" hinzu.
1. Wandelt das "Abgeschlossene" boolesche Feld in eine berechnete Funktion um, die auswertet, ob das abgeschlossene Datum nach dem aktuellen Datum liegt.
1. Fügen Sie einen-Vorgang hinzu, um das abgeschlossene Datum auf das aktuelle Datum festzulegen, an dem der abgeschlossene boolesche Wert auf true festgelegt ist.

Die Abfolge der Änderungen stellt sicher, dass der Legacy Code weiterhin unverändert ausgeführt wird, während neuere Server lose Funktionen das neue Feld nutzen können.

Weitere Informationen zu Daten in Server losen Architekturen finden Sie unter [Herausforderungen und Lösungen für die Verwaltung verteilter Daten](../microservices/architect-microservice-container-applications/distributed-data-management.md).

## <a name="scaling"></a>Skalieren

Es ist ein gängiges Missverständnis, dass Server lose "kein Server" bedeutet. Es ist tatsächlich "less Server". Die Tatsache, dass es eine Sicherungs Infrastruktur gibt, ist wichtig zu verstehen, wenn es um die Skalierung geht. Die meisten Server losen Plattformen stellen eine Reihe von Steuerelementen bereit, mit denen Sie die Skalierung der Infrastruktur bei steigender Ereignis Dichte Steuern Sie können aus einer Vielzahl von Optionen auswählen, aber ihre Strategie kann je nach Funktion variieren. Außerdem werden Funktionen in der Regel unter einem verknüpften Host ausgeführt, sodass Funktionen auf demselben Host über die gleichen Skalierungs Optionen verfügen. Daher ist es erforderlich, die Funktionen zu organisieren und zu überprüfen, die auf der Grundlage der Skalierungs Anforderungen gehostet werden.

Regeln geben häufig an, wie Sie das zentrale hochskalieren (erhöhen der Host Ressourcen) und das horizontale hochskalieren (erhöhen der Anzahl der Host Instanzen) basierend auf verschiedenen Parametern festlegen. Trigger für Skalen können Zeitplan, Anforderungs Raten, CPU-Auslastung und Speicherauslastung umfassen. Eine höhere Leistung ist oft kostengünstiger. Die kostengünstigeren, Verbrauchs basierten Ansatz können nicht so schnell skaliert werden, wenn sich die Anforderungs Rate plötzlich erhöht. Es gibt einen Kompromiss zwischen dem bezahlen der Kosten für "Versicherungskosten" im Vergleich zu "bei Bedarf" und dem Risiko langsamer Antworten aufgrund von plötzlichen Anstieg der Nachfrage.

## <a name="monitoring-tracing-and-logging"></a>Überwachung, Ablauf Verfolgung und Protokollierung

Ein häufig übermittelter Aspekt von devops ist die Überwachung von Anwendungen nach der Bereitstellung. Es ist wichtig, dass Sie über eine Strategie zum Überwachen von Server losen Funktionen verfügen. Die größte Herausforderung besteht häufig in der Korrelation oder dem erkennen, wenn ein Benutzer mehrere Funktionen als Teil derselben Interaktion aufruft. Die meisten Server losen Plattformen ermöglichen die Konsolen Protokollierung, die in Tools von Drittanbietern importiert werden kann. Es gibt auch Optionen zum Automatisieren der Erfassung von Telemetriedaten, generieren und Nachverfolgen von Korrelations-IDs und überwachen spezifischer Aktionen, um detaillierte Einblicke zu erhalten. Azure bietet die erweiterte [Application Insights Plattform](https://docs.microsoft.com/azure/azure-functions/functions-monitoring) für Überwachung und Analyse.

## <a name="inter-service-dependencies"></a>Abhängigkeiten zwischen Diensten

Eine Server lose Architektur kann Funktionen enthalten, die von anderen Funktionen abhängen. Tatsächlich ist es in einer Server losen Architektur nicht ungewöhnlich, dass mehrere Dienste einander als Teil einer Interaktion oder verteilten Transaktion aufruft. Um eine sichere Kopplung zu vermeiden, wird empfohlen, dass Dienste nicht direkt aufeinander verweisen. Wenn sich der Endpunkt für einen Dienst ändern muss, können direkte Verweise zu einem umfangreichen Refactoring führen. Eine vorgeschlagene Lösung besteht darin, einen Dienst Ermittlungs Mechanismus (z. b. eine Registrierung) bereitzustellen, der den entsprechenden Endpunkt für einen Anforderungstyp bereitstellt. Eine weitere Lösung besteht darin, Messaging Dienste wie Warteschlangen oder Themen für die Kommunikation zwischen Diensten zu nutzen.

## <a name="managing-failure-and-providing-resiliency"></a>Verwalten von Fehlern und Bereitstellen von Resilienz

Es ist auch wichtig, das Trenn *Schalter-Muster*zu beachten: Wenn ein Dienst aus irgendeinem Grund weiterhin ausfällt, empfiehlt es sich nicht, diesen Dienst wiederholt aufzurufen. Stattdessen wird ein alternativer Dienst aufgerufen, oder es wird eine Nachricht zurückgegeben, bis die Integrität des abhängigen Dienstanbieter wieder hergestellt wird. Die Server lose Architektur muss die Strategie zum Auflösen und Verwalten von Abhängigkeiten zwischen Diensten berücksichtigen.

Um das Trennschalter-Muster fortzusetzen, müssen Dienste fehlertolerant und robust sein. Die Fehlertoleranz bezieht sich auf die Fähigkeit Ihrer Anwendung, weiter ausgeführt zu werden, auch wenn unerwartete Ausnahmen oder ungültige Zustände aufgetreten sind. Die Fehlertoleranz ist in der Regel eine Funktion des Codes selbst und deren Schreibweise, um Ausnahmen zu behandeln. Resilienz bezieht sich darauf, wie sich die APP nach Fehlern wiederherstellen kann. Die Resilienz wird häufig von der Server losen Plattform verwaltet. Die Plattform sollte in der Lage sein, eine neue Server lose Funktions Instanz zu starten, wenn die vorhandene nicht erfolgreich ist. Die Plattform sollte auch intelligent genug sein, um das Einrichten neuer Instanzen zu beenden, wenn jede neue Instanz ausfällt.

Weitere Informationen finden Sie unter [Implementieren des Trennschalter-Musters](../microservices/implement-resilient-applications/implement-circuit-breaker-pattern.md).

## <a name="versioning-and-greenblue-deployments"></a>Versionierung und grüne/blaue bereit Stellungen

Ein großer Vorteil von Server losen ist die Möglichkeit, eine bestimmte Funktion zu aktualisieren, ohne die gesamte Anwendung erneut bereitstellen zu müssen. Damit Upgrades erfolgreich sind, müssen Funktionen versioniert werden, damit Dienste, die Sie aufrufen, an die richtige Version des Codes weitergeleitet werden. Eine Strategie für die Bereitstellung neuer Versionen ist ebenfalls wichtig. Eine gängige Methode ist die Verwendung von "grünen/blauen bereit Stellungen". Die grüne Bereitstellung ist die aktuelle Funktion. Eine neue "Blaue" Version wird in der Produktionsumgebung bereitgestellt und getestet. Wenn die Tests durchlaufen werden, werden die grünen und blauen Versionen ausgetauscht, sodass die neue Version online geschaltet wird. Wenn Probleme auftreten, können Sie zurück getauscht werden. Die Unterstützung der Versionsverwaltung und der grünen/blauen bereit Stellungen erfordert eine Kombination aus der Erstellung der Funktionen, um Versionsänderungen zu unterstützen und mit der Server losen Plattform zum Verarbeiten von bereit Stellungen zu arbeiten. Ein möglicher Ansatz besteht darin, Proxys zu verwenden, die im Kapitel [Azure Server lose Plattform](azure-functions.md#proxies) beschrieben werden.

>[!div class="step-by-step"]
>[Zurück](serverless-architecture.md)
>[Weiter](serverless-design-examples.md)
