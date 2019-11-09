---
title: Nutzen von serverlosen Funktionen
description: Nutzen von Server losen und Azure Functions in cloudbasierten Anwendungen
ms.date: 06/30/2019
ms.openlocfilehash: 77ddef0eb8844ea1b55cd2fc5ec8aa12593c8631
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73841744"
---
# <a name="leveraging-serverless-functions"></a>Nutzen von serverlosen Funktionen

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Im Bereich der Verwaltung von vollständigen Computern und Betriebssystemen in Bezug auf die Nutzung von cloudfunktionen Leben Server lose am äußersten Ende, bei dem Sie nur für Ihren Code zuständig sind, und Sie zahlen nur, wenn Ihr Code ausgeführt wird. Azure Functions bietet eine Möglichkeit, Server lose Funktionen in Ihren Anwendungen zu erstellen.

## <a name="what-is-serverless"></a>Was ist Server Los?

Das Server lose Computing bedeutet nicht, dass kein Server an der Ausführung Ihrer Anwendung beteiligt ist. der Code wird immer noch auf einem Server ausgeführt. Der Unterschied besteht darin, dass das Anwendungs Entwicklungsteam sich nicht mehr mit der Verwaltung der Serverinfrastruktur befassen muss. Server lose Computing-Lösungen wie Azure Functions helfen Teams, Ihre Produktivität zu steigern, und Unternehmen können Ihre Ressourcen optimieren und sich auf die Bereitstellung von Lösungen konzentrieren.

Beim Server losen Computing werden von Ereignissen ausgelöste Zustands lose Container verwendet, um Ihre Anwendung oder einen Teil Ihrer Anwendung zu hosten. Server lose Plattformen können horizontal hoch-und herunterskaliert werden, um die Nachfrage nach Bedarf zu erfüllen. Plattformen wie Azure Functions haben einfachen direkten Zugriff auf andere Azure-Dienste wie Warteschlangen, Ereignisse und Speicher.

## <a name="what-challenges-are-solved-by-serverless"></a>Welche Herausforderungen werden durch Server lose gelöst?

Serverless ist die ultimative Abstraktion von der Ausführung ihrer eigenen Hardware. Entwickler können sich ausschließlich auf das Schreiben von Code konzentrieren, um Geschäftsprobleme zu lösen, ohne dass Sie sich auf die folgenden Aufgaben beziehen müssen, die möglicherweise beim Hosten Ihrer eigenen Server erforderlich waren:

- Erwerben von Computern und Softwarelizenzen
- Betreiben, sichern, konfigurieren und Verwalten der Computer und ihrer Netzwerk-, Leistungs-und A/C-Anforderungen
- Patchen und Upgraden von Betriebssystemen und Software
- Konfigurieren von Webservern oder Computerdiensten zum Hosten von Anwendungssoftware
- Konfigurieren von Anwendungssoftware innerhalb Ihrer Plattform

Viele Unternehmen nutzen Dutzende von Mitarbeiter Mitgliedern und weisen große Budgets zu, um diese Probleme mit der Hardware Infrastruktur zu unterstützen. Die Umstellung auf die Cloud beseitigt einige dieser Aspekte: Wenn Sie Anwendungen auf Server lose Weise verlagern, wird der Rest ausgeschlossen.

## <a name="what-scenarios-are-appropriate-for-serverless"></a>Welche Szenarien sind für Server lose geeignet?

Serverless verwendet einzelne Funktionen mit kurzer Laufzeit, die als Reaktion auf einen-Auslösers aufgerufen werden. Dies macht Sie ideal für die Verarbeitung von Hintergrundaufgaben.

Beispielsweise muss eine Anwendung möglicherweise im Rahmen der Verarbeitung einer Anforderung eine e-Mail senden. Anstatt die e-Mail als Teil der Verarbeitung der Webanforderung zu senden, können die Details der e-Mail in eine Warteschlange gestellt werden, und eine Azure-Funktion kann verwendet werden, um die Nachricht zu übernehmen und die e-Mail zu senden. Viele verschiedene Teile der Anwendung oder sogar viele Anwendungen können dieselbe Azure-Funktion nutzen, um die Leistung und Skalierbarkeit der Anwendungen zu verbessern und den [Warteschlangen basierten Lasten](https://docs.microsoft.com/azure/architecture/patterns/queue-based-load-leveling) Ausgleich zu vermeiden, um Engpässe im Zusammenhang mit dem Senden von e-Mails zu vermeiden.

Obwohl es sich bei einem [Verleger-](https://docs.microsoft.com/azure/architecture/patterns/publisher-subscriber) /Abonnementen zwischen Anwendungen und Azure Functions um das gängigste Muster handelt, sind andere Muster möglich. Azure Functions können von anderen Ereignissen ausgelöst werden, z. b. Änderungen an Azure BLOB Storage. Eine Anwendung, die Image Uploads unterstützt, kann über eine Azure-Funktion verfügen, die für das Erstellen von Miniaturbildern oder das Ändern der Größe von hochgeladenen Bildern zu konsistenten Dimensionen oder die Optimierung der All diese Funktionen können direkt durch Einfügungen in Azure BLOB Storage ausgelöst werden, sodass die Komplexität und die Arbeitsauslastung nicht mehr von der Anwendung selbst übernommen werden.

Viele Anwendungen verfügen über Prozesse mit langer Ausführungsdauer im Rahmen ihrer Workflows. Häufig werden diese Aufgaben im Rahmen der Interaktion des Benutzers mit der Anwendung ausgeführt, sodass der Benutzer das warten und negative Auswirkungen auf seine Benutzerinteraktion erzwingt. Das Server lose Computing bietet eine hervorragend Möglichkeit zum Ausführen langsamer Aufgaben außerhalb der Benutzer Interaktions Schleife. diese Aufgaben können problemlos mit Bedarf skaliert werden, ohne dass die gesamte Anwendung skaliert werden muss.

## <a name="when-should-you-avoid-serverless"></a>Wann sollten Sie Server lose vermeiden?

Server Loses Computing eignet sich am besten für Aufgaben, die die Benutzeroberfläche nicht blockieren. Dies bedeutet, dass Sie nicht ideal zum direkten Hosting von Webanwendungen oder Web-APIs sind. Der Hauptgrund dafür ist, dass Server lose Lösungen bereitgestellt und Bedarfs gesteuert skaliert werden. Wenn eine neue Instanz einer Funktion benötigt wird, die als *Kaltstart*bezeichnet wird, dauert es eine Weile, bis die Bereitstellung erfolgt ist. Diese Zeit ist in der Regel ein paar Sekunden, kann jedoch je nach verschiedenen Faktoren länger sein. Eine einzelne Instanz kann häufig unbegrenzt aufrechterhalten werden (z. a. durch regelmäßiges Ausführen einer Anforderung), aber das Problem beim Kaltstart bleibt bestehen, wenn die Anzahl der Instanzen jemals zentral hochskaliert werden muss.

![kalt im Vergleich zu warmem Start](./media/cold-start-warm-start.png)
**Abbildung 3-10**. Kaltstart im Vergleich zum warmen Start.

Wenn Sie einen vollständigen Kaltstart vermeiden müssen, können Sie von einem [Verbrauchs Plan zu einem dedizierten Plan](https://azure.microsoft.com/blog/understanding-serverless-cold-start/)wechseln. Sie können auch [eine oder mehrere vorerwärmte Instanzen](https://docs.microsoft.com/azure/azure-functions/functions-premium-plan#pre-warmed-instances) mit dem Premium-Plan konfigurieren. Wenn Sie also eine weitere Instanz hinzufügen müssen, ist Sie bereits einsatzbereit. Diese Optionen können eines der Hauptprobleme im Zusammenhang mit dem Server losen Computing mindern.

Sie sollten in der Regel auch Server lose Aufgaben für Aufgaben mit langer Ausführungszeit vermeiden. Sie eignen sich am besten für kleine Teile der Arbeit, die schnell abgeschlossen werden können. Die meisten Server losen Plattformen erfordern, dass einzelne Funktionen innerhalb weniger Minuten abgeschlossen werden. Azure Functions ist standardmäßig auf einen Zeitraum von 5 Minuten eingestellt (kann bis zu 10 Minuten konfiguriert werden). Der Plan "Azure Functions Premium" kann dieses Problem ebenfalls mindern, das Timeout auf 30 Minuten beschränkt und das Konfigurieren einer ungebundenen höheren Grenze ermöglicht.

Wenn Sie die Server lose Nutzung für bestimmte Aufgaben innerhalb Ihrer Anwendung nutzen, wird die Komplexität erhöht. Häufig empfiehlt es sich, Ihre Anwendung zunächst in einer modularen, locker gekoppelten Weise zu entwerfen und dann festzustellen, ob es Vorteile gibt, die Server lose anbieten würde, was die zusätzliche Komplexität lohnt. Viele kleinere Anwendungen können in einer einzelnen monolithischen Bereitstellung perfekt ausgeführt werden, ohne dass für die Architektur verteilter Anwendungen ein Server Loses Computing erforderlich ist.

## <a name="references"></a>Verweise

- [Grundlegendes zum Server losen Kaltstart](https://azure.microsoft.com/blog/understanding-serverless-cold-start/)
- [Vorwärmte Azure Functions Instanzen](https://docs.microsoft.com/azure/azure-functions/functions-premium-plan#pre-warmed-instances)
- [Erstellen einer Funktion unter Linux mithilfe eines benutzerdefinierten Images](https://docs.microsoft.com/azure/azure-functions/functions-create-function-linux-custom-image)

>[!div class="step-by-step"]
>[Zurück](leverage-containers-orchestrators.md)
>[Weiter](combine-containers-serverless-approaches.md)
