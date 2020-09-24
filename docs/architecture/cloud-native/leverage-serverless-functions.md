---
title: Nutzen von serverlosen Funktionen
description: Nutzen von Server losen und Azure Functions in cloudbasierten Anwendungen
ms.date: 05/13/2020
ms.openlocfilehash: 8e5c60d29cd8d635f79f42c232b33f060949e2b5
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91155366"
---
# <a name="leveraging-serverless-functions"></a>Nutzen von serverlosen Funktionen

Im Bereich von der Verwaltung physischer Computer bis hin zur Nutzung von cloudfunktionen Leben Server lose Server lose Systeme am äußersten Ende. Ihre einzige Verantwortung ist Ihr Code, und Sie zahlen nur, wenn Ihr Code ausgeführt wird. Azure Functions bietet eine Möglichkeit, Server lose Funktionen in Ihre cloudbasierten Anwendungen zu erstellen.

## <a name="what-is-serverless"></a>Was bedeutet serverlos?

Serverless ist ein relativ neues Dienstmodell von Cloud Computing. Dies bedeutet nicht, dass Server optional sind. Ihr Code wird immer noch auf einem Server ausgeführt. Der Unterschied besteht darin, dass das Anwendungsteam sich nicht mehr mit der Verwaltung der Serverinfrastruktur beschäftigt. Stattdessen ist der cloudhersteller für diese Aufgabe zuständig. Das Entwicklungsteam steigert seine Produktivität durch die Bereitstellung von Unternehmenslösungen für Kunden, nicht für die Einrichtung.

Beim Server losen Computing werden vom Ereignis ausgelöste Zustands lose Container zum Hosten Ihrer Dienste verwendet. Sie können horizontal hoch-und herunterskaliert werden, um die Nachfrage nach Bedarf zu erfüllen. Server lose Plattformen wie Azure Functions sind eng in andere Azure-Dienste wie Warteschlangen, Ereignisse und Speicher integriert.

## <a name="what-challenges-are-solved-by-serverless"></a>Welche Herausforderungen werden durch Server lose gelöst?

Server lose Plattformen erfüllen viele zeitaufwändige und kostspielige Probleme:

- Erwerben von Computern und Softwarelizenzen
- Betreiben, sichern, konfigurieren und Verwalten der Computer und ihrer Netzwerk-, Leistungs-und A/C-Anforderungen
- Patchen und Upgraden von Betriebssystemen und Software
- Konfigurieren von Webservern oder Computerdiensten zum Hosten von Anwendungssoftware
- Konfigurieren von Anwendungssoftware innerhalb Ihrer Plattform

Viele Unternehmen weisen große Budgets zu, um Hardware Infrastrukturprobleme zu unterstützen. Die Umstellung auf die Cloud kann Ihnen helfen, diese Kosten zu reduzieren. Wenn Sie Anwendungen auf Server lose Anwendungen verschieben, können Sie diese vermeiden.

## <a name="what-is-the-difference-between-a-microservice-and-a-serverless-function"></a>Worin besteht der Unterschied zwischen einem mikrodienst und einer Server losen Funktion?

In der Regel kapselt ein microservice eine Geschäftsfunktion, z. b. einen Warenkorb für eine Online-e-Commerce-Website. Es macht mehrere Vorgänge verfügbar, mit denen ein Benutzer seine Einkaufsmöglichkeiten verwalten kann. Eine Funktion ist jedoch ein kleiner, einfacher Codeblock, der als Reaktion auf ein Ereignis einen Vorgang mit nur einem Zweck ausführt.
In der Regel werden in der Regel von einer Schnittstelle auf Anforderungen reagiert. Anforderungen können http-Rest-oder GrpC-basiert sein. Server lose Dienste reagieren auf Ereignisse. Die ereignisgesteuerte Architektur eignet sich ideal für die Verarbeitung von Aufgaben mit kurzer Laufzeit, Hintergrundaufgaben.

## <a name="what-scenarios-are-appropriate-for-serverless"></a>Welche Szenarien sind für Server lose geeignet?

Server lose macht einzelne Funktionen mit kurzer Laufzeit verfügbar, die als Reaktion auf einen-ausgelöst aufgerufen werden. Dies macht Sie ideal für die Verarbeitung von Hintergrundaufgaben.

Möglicherweise muss eine Anwendung eine e-Mail als Schritt in einem Workflow senden. Anstatt die Benachrichtigung als Teil einer Anforderung eines-Webdiensts zu senden, platzieren Sie die Nachrichten Details in eine Warteschlange. Eine Azure-Funktion kann die Nachricht aus der Warteschlange entfernen und Sie asynchron senden. Dies könnte die Leistung und Skalierbarkeit des-Dienstanbieter verbessern. [Warteschlangen basierter Lasten](/azure/architecture/patterns/queue-based-load-leveling) Ausgleich kann implementiert werden, um Engpässe im Zusammenhang mit dem Senden der e-Mails zu vermeiden. Außerdem kann dieser eigenständige Dienst als Dienstprogramm für viele verschiedene Anwendungen wieder verwendet werden.

Asynchrones Messaging aus Warteschlangen und Themen ist ein gängiges Muster, um Server lose Funktionen zu initiieren. Azure Functions können jedoch durch andere Ereignisse ausgelöst werden, z. b. Änderungen an Azure BLOB Storage. Ein Dienst, der Bild Uploads unterstützt, kann über eine Azure-Funktion verfügen, die für die Optimierung der Image Größe zuständig Die-Funktion kann direkt durch Einfügungen in Azure BLOB Storage ausgelöst werden, sodass die Komplexität der Vorgänge im-Betrieb gewahrt bleibt.

Viele Dienste weisen Prozesse mit langer Ausführungszeit als Teil ihrer Workflows auf. Häufig werden diese Aufgaben im Rahmen der Interaktion des Benutzers mit der Anwendung ausgeführt. Diese Aufgaben können den Benutzer zwingen, zu warten, was sich negativ auf die Benutzeroberflächen auswirkt. Das Server lose Computing bietet eine hervorragend Möglichkeit zum Verschieben langsamer Aufgaben außerhalb der Benutzer Interaktions Schleife. Diese Aufgaben können mit Bedarf skaliert werden, ohne dass die gesamte Anwendung skaliert werden muss.

## <a name="when-should-you-avoid-serverless"></a>Wann sollten Sie Server lose vermeiden?

Server lose Lösungen stellen Bedarfs gesteuert bereit und Skalieren Sie. Wenn eine neue Instanz aufgerufen wird, sind Kaltstarts ein häufiges Problem. Ein Kaltstart ist die Zeitspanne, die für die Bereitstellung dieser Instanz benötigt wird. Diese Verzögerung kann normalerweise einige Sekunden dauern, kann jedoch je nach den verschiedenen Faktoren länger sein. Nach der Bereitstellung wird eine einzelne Instanz aufrechterhalten, solange Sie periodische Anforderungen empfängt. Wenn ein Dienst aber seltener aufgerufen wird, kann Azure ihn aus dem Arbeitsspeicher entfernen und einen Kaltstart bei der Neuerstellung erfordern. Kaltstarts sind auch erforderlich, wenn eine Funktion auf eine neue Instanz horizontal hochskaliert wird.

In Abbildung 3-10 wird ein kalt Start Muster gezeigt. Beachten Sie die zusätzlichen Schritte, die erforderlich sind, wenn die APP kalt ist.

![Kalt und warm Start ](./media/cold-start-warm-start.png)
 **Abbildung 3-10**. Kaltstart im Vergleich zum warmen Start.

Um zu vermeiden, dass Kaltstarts vollständig ausgeführt werden, können Sie von einem [Verbrauchs Plan zu einem dedizierten Plan](https://azure.microsoft.com/blog/understanding-serverless-cold-start/)wechseln. Sie können auch eine oder mehrere [vorerwärmte Instanzen](/azure/azure-functions/functions-premium-plan#pre-warmed-instances) mit der Premium-Plan Aktualisierung konfigurieren. Wenn Sie in diesen Fällen eine weitere Instanz hinzufügen müssen, ist Sie bereits einsatzbereit. Diese Optionen können dabei helfen, das Problem mit dem Kaltstart bei Server losem Computing zu verringern.

Die Abrechnung von cloudanbietern basierend auf der computeausführungszeit und dem verbrauchten Arbeitsspeicher. Vorgänge mit langer Ausführungsdauer oder Arbeits Auslastungen mit hohem Arbeitsspeicher sind nicht immer die besten Kandidaten für Server lose. Server lose Funktionen bevorzugen kleine Arbeitsblöcke, die schnell ausgeführt werden können. Die meisten Server losen Plattformen erfordern, dass einzelne Funktionen innerhalb weniger Minuten abgeschlossen werden. Azure Functions ist standardmäßig auf eine Dauer von 5 Minuten festgelegt, die bis zu 10 Minuten konfiguriert werden kann. Der Plan "Azure Functions Premium" kann dieses Problem ebenfalls mindern, wobei Timeouts auf 30 Minuten festgelegt werden, wobei eine unbegrenzte Grenze erreicht wird, die konfiguriert werden kann. Die COMPUTE-Zeit ist keine Kalenderzeit. Erweiterte Funktionen mit [Azure Durable Functions Framework](/azure/azure-functions/durable/durable-functions-overview?tabs=csharp) können die Ausführung über mehrere Tage anhalten. Die Abrechnung basiert auf der tatsächlichen Ausführungszeit, wenn die Funktion aktiviert wird und die Verarbeitung fortgesetzt wird.

Wenn Sie Azure Functions für Anwendungsaufgaben nutzen, wird die Komplexität erhöht. Es ist ratsam, die Anwendung zunächst mit einem modularen, locker gekoppelten Design zu erstellen. Stellen Sie dann fest, ob die Vorteile von Server losen angeboten werden, die die zusätzliche Komplexität rechtfertigen würden.

>[!div class="step-by-step"]
>[Zurück](leverage-containers-orchestrators.md)
>[Weiter](combine-containers-serverless-approaches.md)
