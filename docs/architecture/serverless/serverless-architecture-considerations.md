---
title: 'Überlegungen zur serverlosen Architektur: Serverlose Apps'
description: Verstehen der Herausforderungen der Architektur von serverlosen Anwendungen, von Zustandsverwaltung und persistentem Speicher über Skalierung, Protokollierung, Ablaufverfolgung bis hin zu Diagnose.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 04/06/2020
ms.openlocfilehash: 3c07e1149e6af41a6b9a9317238e5c71015d2c4e
ms.sourcegitcommit: 8b02d42f93adda304246a47f49f6449fc74a3af4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/24/2020
ms.locfileid: "82135671"
---
# <a name="serverless-architecture-considerations"></a>Überlegungen zur serverlosen Architektur

Die Nutzung einer serverlosen Architektur bringt bestimmte Herausforderungen mit sich. In diesem Abschnitt werden einige der gängigeren Überlegungen erläutert, die Sie kennen sollten. Für alle diese Herausforderungen gibt es Lösungen. Wie bei allen Architekturoptionen sollte die Entscheidung, eine serverlose Implementierung zu verwenden, erst nach sorgfältiger Untersuchung der Vor- und Nachteile getroffen werden. Abhängig von den Anforderungen Ihrer Anwendung können Sie die Erkenntnis gewinnen, dass eine serverlose Implementierung nicht die richtige Lösung für bestimmte Komponenten ist.

## <a name="managing-state"></a>Verwalten des Zustands

Serverlose Funktionen sind (wie Microservices allgemein) standardmäßig zustandslos. Durch das Vermeiden des Zustands kann eine serverlose Bereitstellung kurzlebig sein, horizontal hochskaliert werden und Resilienz ohne einen zentralen Fehlerpunkt bereitstellen. In einigen Fällen ist für Geschäftsprozesse ein Zustand erforderlich. Wenn Ihr Prozess einen Zustand erfordert, haben Sie zwei Möglichkeiten. Sie können ein anderes Modell als eine serverlose Bereitstellung verwenden oder mit einem separaten Dienst interagieren, der einen Zustand bereitstellt. Das Hinzufügen eines Zustands kann die Lösung komplizierter gestalten, die Skalierung erschweren und potenziell zu einem Single Point of Failure führen. Überlegen Sie sorgfältig, ob Ihre Funktion unbedingt einen Zustand erfordert. Wenn die Antwort „Ja“ lautet, überlegen Sie, ob es immer noch sinnvoll ist, eine serverlose Lösung zu implementieren.

Es gibt mehrere Lösungen, die einen Zustand bereitstellen, ohne die Vorteile einer serverlosen Implementierung zu gefährden. Zu den beliebtesten Lösungen gehören:

- Verwenden eines temporären Datenspeichers oder verteilten Caches wie Redis
- Speichern des Zustands in einer Datenbank, z.B. SQL oder CosmosDB
- Verarbeiten des Zustands durch eine Workflow-Engine wie [Durable Functions](https://docs.microsoft.com/azure/azure-functions/durable/durable-functions-overview)

Fazit: Sie sollten die Notwendigkeit einer Zustandsverwaltung in Prozessen beachten, für die Sie eine serverlose Implementierung in Erwägung ziehen.

## <a name="long-running-processes"></a>Prozesse mit langer Ausführungszeit

Viele Vorteile von serverlosen Lösungen basieren auf kurzlebigen Prozessen. Kurze Ausführungszeiten vereinfachen es dem Anbieter einer serverlosen Lösung, Ressourcen freizugeben, wenn Funktionen beendet werden, und Funktionen hostübergreifend gemeinsam zu verwenden. Die meisten Cloudanbieter beschränken die Gesamtausführungsdauer Ihrer Funktion auf ungefähr 10 Minuten. Wenn Ihr Prozess mehr Zeit in Anspruch nimmt, können Sie eine alternative Implementierung in Erwägung ziehen.

Es gibt einige Ausnahmen und Lösungen. Eine Lösung kann darin bestehen, den Prozess in kleinere Komponenten zu unterteilen, deren einzelne Ausführung weniger Zeit in Anspruch nimmt. Wenn Ihr Prozess aufgrund von Abhängigkeiten zur einer langen Ausführungszeit führt, können Sie auch einen asynchronen Workflow mithilfe einer Lösung wie Durable Functions in Erwägung ziehen. Durable Functions werden angehalten und behalten den Zustand des Prozesses bei, während darauf gewartet wird, dass ein externer Prozess beendet wird. Die asynchrone Verarbeitung verringert die Zeit, die der tatsächliche Prozess ausgeführt wird.

## <a name="startup-time"></a>Startzeit

Ein mögliches Problem bei serverlosen Implementierungen ist die Startzeit. Um Ressourcen zu sparen, erstellen viele Anbieter von serverlosen Lösungen die Infrastruktur „bei Bedarf“. Wenn eine serverlose Funktion nach einer gewissen Zeit ausgelöst wird, müssen möglicherweise die Ressourcen zum Hosten der Funktion erstellt oder neu gestartet werden. In einigen Fällen kann es zu Verzögerungen bei einem Kaltstart kommen, die mehrere Sekunden dauern. Die Startzeit variiert je nach Anbieter und Dienstebene. Es gibt einige Ansätze, um die Startzeit zu verkürzen, wenn dies für den Erfolg der App wichtig ist.

- Einige Anbieter ermöglichen es Benutzern, für Dienstebenen zu zahlen, die eine Infrastruktur garantieren, die „immer aktiv“ ist.
- Implementieren Sie einen Keep-Alive-Mechanismus (pingen Sie den Endpunkt, um seine „Aktivität“ zu gewährleisten).
- Verwenden Sie eine Orchestrierung wie Kubernetes mit einem Ansatz für eine containerisierte Funktion (der Host wird bereits ausgeführt, sodass das Einrichten neuer Instanzen äußerst schnell erfolgt).

## <a name="database-updates-and-migrations"></a>Datenbankaktualisierungen und -migrationen

Ein Vorteil von serverlosem Code besteht darin, dass Sie neue Funktionen freigeben können, ohne die gesamte Anwendung erneut bereitstellen zu müssen. Dieser Vorteil kann zu einem Nachteil werden, wenn eine relationale Datenbank beteiligt ist. Änderungen an Datenbankschemas sind schwer mit serverlosen Aktualisierungen zu synchronisieren. Weitere Herausforderungen ergeben sich, wenn ein Fehler auftritt und für die Änderungen ein Rollback ausgeführt werden muss. Datenintegrität ist ein Grund dafür, dass eine bewährte Methode für Microservices und serverlose Funktionen darin besteht, dass sie Besitzer ihrer eigenen Daten sind. Es ist möglich, Änderungen als eine einzelne Einheit von Compute und Daten bereitzustellen. Die Realität sieht so aus, dass viele Legacysysteme über eine große Back-End-Datenbank verfügen, die mit der serverlosen Architektur abgestimmt werden muss.

Ein beliebter Ansatz zum Lösen der Schemaversionsverwaltung besteht darin, niemals vorhandene Eigenschaften und Spalten zu ändern, sondern stattdessen neue Informationen hinzuzufügen. Nehmen Sie beispielsweise eine Änderung an, bei der von einem booleschen Flag „Abgeschlossen“ für eine Aufgabenliste zu einem „Abschlussdatum“ gewechselt wird. Anstatt das alte Feld zu entfernen, wird die Datenbankänderung wie folgt durchführt:

1. Fügen Sie ein neues Feld „Abschlussdatum“ hinzu.
1. Transformieren Sie das boolesche Feld „Abgeschlossen“ in eine berechnete Funktion, die auswertet, ob das Abschlussdatum nach dem aktuellen Datum liegt.
1. Fügen Sie einen Trigger hinzu, um das Abschlussdatum auf das aktuelle Datum festzulegen, wenn der boolesche Wert „Abgeschlossen“ auf TRUE festgelegt wird.

Die Sequenz der Änderungen stellt sicher, dass der Legacycode weiterhin „unverändert“ ausgeführt wird, während neuere serverlose Funktionen das neue Feld nutzen können.

Weitere Informationen zu Daten in serverlosen Architekturen finden Sie unter [Herausforderungen und Lösungen für verteilte Datenverwaltung](../microservices/architect-microservice-container-applications/distributed-data-management.md).

## <a name="scaling"></a>Skalieren

Es ist ein gängiges Missverständnis, dass serverlos „kein Server“ bedeutet. Tatsächlich geht es um „weniger Server“. Die Tatsache, dass es eine unterstützende Infrastruktur gibt, ist wichtig zu verstehen, wenn es um Skalierung geht. Die meisten serverlosen Plattformen bieten eine Reihe von Steuermöglichkeiten, wie die Infrastruktur bei zunehmender Ereignisdichte skaliert werden soll. Sie können aus einer Vielzahl von Optionen auswählen, aber ihre Strategie kann je nach Funktion unterschiedlich sein. Außerdem werden Funktionen in der Regel auf einem verwandten Host ausgeführt, sodass Funktionen auf demselben Host über die gleichen Skalierungsoptionen verfügen. Daher ist es erforderlich, zu organisieren und strategisch festzulegen, welche Funktionen aufgrund von Skalierungsanforderungen gemeinsam gehostet werden.

Regeln geben häufig an, wie das zentrale Hochskalieren (Erhöhen der Hostressourcen) und die horizontale Skalierung (Erhöhen der Anzahl der Hostinstanzen) basierend auf verschiedenen Parametern erfolgen soll. Trigger für Skalierungen können einen Zeitplan, Anforderungsraten, die CPU-Auslastung und die Speicherauslastung umfassen. Höhere Leistung ist häufig mit höheren Kosten verbunden. Die kostengünstigeren, verbrauchsbasierten Ansätze können ggf. nicht so schnell skaliert werden, wenn sich die Anforderungsrate plötzlich erhöht. Es gibt einen Kompromiss zwischen der Zahlung von „Versicherungskosten“ im Voraus und der strikten „nutzungsbasierten“ Zahlung mit der Gefahr, dass Reaktionen aufgrund plötzlich steigender Nachfrage langsamer werden.

## <a name="monitoring-tracing-and-logging"></a>Überwachung, Ablaufverfolgung und Protokollierung

Ein häufig übersehener Aspekt von DevOps ist die Überwachung von Anwendungen nach der Bereitstellung. Es ist wichtig, dass Sie über eine Strategie zum Überwachen von serverlosen Funktionen verfügen. Die größte Herausforderung besteht häufig in der Korrelation oder dem Erkennen, wenn ein Benutzer mehrere Funktionen als Teil derselben Interaktion aufruft. Die meisten serverlosen Plattformen ermöglichen Konsolenprotokollierung, die in Tools von Drittanbietern importiert werden kann. Es gibt auch Optionen zum Automatisieren der Erfassung von Telemetriedaten, Generieren und Nachverfolgen von Korrelations-IDs und Überwachen spezifischer Aktionen, um detaillierte Einblicke zu erhalten. Azure bietet die erweiterte [Application Insights-Plattform](https://docs.microsoft.com/azure/azure-functions/functions-monitoring) für Überwachung und Analysen.

## <a name="inter-service-dependencies"></a>Abhängigkeiten zwischen Diensten

Eine serverlose Architektur kann Funktionen enthalten, die von anderen Funktionen abhängen. Tatsächlich ist es in einer serverlosen Architektur nicht ungewöhnlich, dass mehrere Dienste einander als Teil einer Interaktion oder verteilten Transaktion aufrufen. Um eine starke Kopplung zu vermeiden, wird empfohlen, dass Dienste nicht direkt aufeinander verweisen. Wenn sich der Endpunkt für einen Dienst ändern muss, können direkte Verweise zu umfangreichem Refactoring führen. Eine vorgeschlagene Lösung besteht darin, einen Dienstermittlungsmechanismus (z.B. eine Registrierung) bereitzustellen, der den entsprechenden Endpunkt für einen Anforderungstyp bereitstellt. Eine weitere Lösung besteht darin, Messagingdienste wie Warteschlangen oder Themen für die Kommunikation zwischen Diensten zu nutzen.

## <a name="managing-failure-and-providing-resiliency"></a>Verwalten von Fehlern und Bereitstellen von Resilienz

Es ist auch wichtig, das *Sicherungsmuster* zu berücksichtigen: Wenn ein Dienst aus irgendeinem Grund wiederholt ausfällt, empfiehlt es sich nicht, diesen Dienst wiederholt aufzurufen. Stattdessen wird ein alternativer Dienst aufgerufen, oder es wird eine Nachricht zurückgegeben, bis die Integrität des abhängigen Diensts wiederhergestellt ist. Die serverlose Architektur muss eine Strategie zum Auflösen und Verwalten von Abhängigkeiten zwischen Diensten berücksichtigen.

Um das Sicherungsmuster fortzusetzen, müssen Dienste fehlertolerant und robust sein. Fehlertoleranz bezieht sich auf die Fähigkeit Ihrer Anwendung, weiterhin ausgeführt zu werden, auch wenn unerwartete Ausnahmen oder ungültige Zustände aufgetreten sind. Fehlertoleranz ist in der Regel eine Funktion des Codes selbst und hängt davon ab, wie er geschrieben wurde, um Ausnahmen zu behandeln. Resilienz bezieht sich darauf, wie leistungsfähig die App bei der Wiederherstellung nach Fehlern ist. Resilienz wird häufig von der serverlosen Plattform verwaltet. Die Plattform sollte in der Lage sein, eine neue Instanz der serverlosen Funktion zu starten, wenn in der vorhandenen Instanz ein Fehler auftritt. Die Plattform sollte auch intelligent genug sein, um das Einrichten neuer Instanzen zu beenden, wenn für jede neue Instanz ein Fehler auftritt.

Weitere Informationen finden Sie unter [Implementieren des Sicherungsmusters](../microservices/implement-resilient-applications/implement-circuit-breaker-pattern.md).

## <a name="versioning-and-greenblue-deployments"></a>Versionsverwaltung und grüne/blaue Bereitstellungen

Ein großer Vorteil von serverlosen Bereitstellungen ist die Möglichkeit, eine bestimmte Funktion zu aktualisieren, ohne die gesamte Anwendung erneut bereitstellen zu müssen. Damit Upgrades erfolgreich sind, muss auf Funktionen Versionsverwaltung angewendet werden, damit Dienste, die sie aufrufen, an die richtige Version des Codes weitergeleitet werden. Eine Strategie für die Bereitstellung neuer Versionen ist ebenfalls wichtig. Eine gängige Methode ist die Verwendung von „grünen/blauen Bereitstellungen“. Die grüne Bereitstellung ist die aktuelle Funktion. Eine neue „blaue“ Version wird in der Produktionsumgebung bereitgestellt und getestet. Wenn die Tests bestanden werden, werden die grünen und blauen Versionen ausgetauscht, sodass die neue Version online geschaltet wird. Wenn Probleme auftreten, können die Versionen zurückgetauscht werden. Die Unterstützung der Versionsverwaltung und der grünen/blauen Bereitstellungen erfordert eine Kombination aus der Erstellung der Funktionen, um Versionsänderungen zu unterstützen, und dem Arbeiten mit der serverlosen Plattform zum Verarbeiten von Bereitstellungen.

>[!div class="step-by-step"]
>[Zurück](serverless-architecture.md)
>[Weiter](serverless-design-examples.md)
