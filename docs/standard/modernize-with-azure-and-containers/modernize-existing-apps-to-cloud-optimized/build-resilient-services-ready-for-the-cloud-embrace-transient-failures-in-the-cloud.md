---
title: Erstellen Sie belastbarer Dienste, die für die Cloud bereit. Verstehen Sie vorübergehender Fehler in der cloud
description: Modernisieren vorhandener .NET-Anwendungen mit Azure-Cloud und Windows-Containern | Erstellen Sie belastbarer Dienste, die für die Cloud bereit. Verstehen Sie vorübergehender Fehler in der cloud
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/30/2018
ms.openlocfilehash: 16228321cc788b381603513213130415eb73a95c
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53128855"
---
# <a name="build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud"></a>Erstellen Sie belastbarer Dienste, die für die Cloud bereit: Verstehen Sie vorübergehender Fehler in der cloud

Als Stabilität wird die Fähigkeit zum Wiederherstellen nach Fehlern und zum Fortsetzen der Funktionsweise bezeichnet. Resilienz ist nicht zum Vermeiden von Fehlern, aber akzeptieren der Tatsache, dass Fehler auftreten, und klicken Sie dann die Antwort auf diese in einer Weise, die Ausfallzeiten oder Datenverluste zu vermeiden. Das Ziel der Stabilität ist, die Anwendung nach einem Fehler wieder in einen voll funktionsfähigen Zustand zu versetzen.

Ihre Anwendung ist bereit für die Cloud, wenn mindestens ein Software-basiertes Modell der resilienz, anstatt eine Hardware-basierte Modell implementiert. Ihre Cloud-Anwendung muss die teilfehler umfassen, die sicherlich auftreten. Entwerfen Sie oder Umgestalten Sie teilweise Ihrer Anwendung zur Erreichung von resilienz mit erwarteten teilfehlern. Es sollten so entworfen werden, mit teilfehlern wie vorübergehende Netzwerkausfälle und Knoten oder virtuellen Computern in der Cloud abstürzen zu bewältigen. Sogar Container verschoben werden, auf einen anderen Knoten in einem orchestratorcluster können zeitweilig kurze Fehler in der Anwendung verursachen.

## <a name="handling-partial-failure"></a>Behandeln von Teilfehlern

In einer Cloud-basierten Anwendung müssen Sie es ein allgegenwärtiges Risiko für teilfehler ist. Z. B. eine einzelne Website-Instanz eines Containers unter Umständen nicht erfolgreich, oder es möglicherweise nicht verfügbar oder für eine kurze Zeit nicht reagiert. Alternativ dazu können Sie eine einzelne VM oder Server stürzt möglicherweise ab.

Da Clients und Dienste separate Vorgänge sind, möglicherweise ein Dienst nicht rechtzeitig auf die Anforderung eines Clients zu reagieren. Der Dienst möglicherweise überladen werden und nur langsam auf Anforderungen reagiert, oder es möglicherweise nicht zugegriffen werden für kurze Zeit aufgrund von Netzwerkproblemen.

Betrachten Sie beispielsweise eine monolithische .NET-Anwendung, die auf eine Datenbank in Azure SQL-Datenbank zugreift. Wenn Azure SQL-Datenbank oder einen anderen Drittanbieter-Dienst nicht reagiert für eine kurze Zeit (Azure SQL-Datenbank möglicherweise zu einem anderen Knoten oder Server verschoben und werden ein paar Sekunden lang nicht mehr reagiert), wenn der Benutzer versucht, die keine Aktionen ausführen, stürzt die Anwendung und anzeigen w-Ausnahme zum gleichen Zeitpunkt.

Ein ähnliches Szenario kann in einer app auftreten, die HTTP-Dienste verwendet. Das Netzwerk oder den Dienst selbst kann in der Cloud bei einem kurzen, vorübergehende Fehler nicht verfügbar.

Bei einer stabilen Anwendung wie in Abbildung 4-9 sollten Techniken wie z. B. "Wiederholungen mit exponentiellem Backoff" implementieren, um der Anwendung eine Möglichkeit zur Behandlung vorübergehender Fehler in den Ressourcen zu gewähren. Sie sollten auch "Trennschalter" in Ihren Anwendungen verwenden. Ein Trennschalter beendet eine Anwendung versucht, die auf eine Ressource zuzugreifen, wenn es tatsächlich einen langfristigen Fehler ist. Verwenden eines schutzschalters, wird die Anwendung Geschäftsperspektiven zeigen einen Denial of Service zu sich selbst vermieden.

![Teilweise Ausfälle von Wiederholungen mit exponentiellem Backoff verarbeitet](./media/image9.png)

> **Abbildung 4-9.** Teilweise Ausfälle von Wiederholungen mit exponentiellem Backoff verarbeitet

Sie können diese Techniken in HTTP-Ressourcen und in der Datenbank-Ressourcen verwenden. In Abbildung 4-9, basiert die Anwendung auf einer 3-Ebenen-Architektur, weshalb Sie diese Techniken auf der Ebene der Dienste (HTTP) und auf der Ebene der Daten (TCP). In einer monolithischen Anwendung, die nur eine einzelne app-Ebene zusätzlich zu der Datenbank (ohne zusätzliche Dienste oder Microservices) verwendet, möglicherweise Behandlung von vorübergehenden Fehlern auf der Datenbankebene für die Verbindung ausreichen. In diesem Szenario ist nur eine bestimmte Konfiguration der Verbindung mit der Datenbank erforderlich.

Bei der Implementierung von robuster Kommunikation, die auf die Datenbank, abhängig von der Version von .NET zugreifen, Sie verwenden, können sie einfach sein (z. B. [mit Entity Framework 6 oder höher](https://msdn.microsoft.com/library/dn456835(v=vs.113).aspx), es ist nur eine Frage der Konfiguration der datenbankverbindung). Oder Sie müssen zusätzliche Bibliotheken wie dem [Transient Fault Handling Application Block](https://msdn.microsoft.com/library/hh680934(v=pandp.50).aspx) (für frühere Versionen von .NET), oder sogar Ihre eigene Bibliothek implementieren.

Beim Implementieren von Wiederholungen von HTTP und der Schutzschalter die Empfehlung für .NET ist die Verwendung der [Polly](https://github.com/App-vNext/Polly) , das auf .NET Framework 4.0 und .NET Framework 4.5, .NET Standard 1.1, einschließlich Unterstützung für .NET Core-Bibliothek.

Gewusst wie: Implementieren Sie Strategien zum Beheben von teilfehlern in der Cloud finden Sie unter den folgenden Referenzen.

### <a name="additional-resources"></a>Zusätzliche Ressourcen

-   **Implementieren robuste Kommunikation zum Behandeln von teilfehlern**

    [https://docs.microsoft.com/dotnet/standard/microservices-architecture/implement-resilient-applications/partial-failure-strategies](../../microservices-architecture/implement-resilient-applications/partial-failure-strategies.md)

-   **Entity Framework datenbankverbindungsresilienz und Wiederholungslogik Verbindungslogik (Version 6 und höher)**

    [https://msdn.microsoft.com/library/dn456835(v=vs.113).aspx](https://msdn.microsoft.com/library/dn456835(v=vs.113).aspx)

-   **Der Anwendungsblock für die Behandlung vorübergehender Fehler**

-   [https://msdn.microsoft.com/library/hh680934(v=pandp.50).aspx](https://msdn.microsoft.com/library/hh680934(v=pandp.50).aspx)

-   **Polly-Bibliothek für robuste HTTP-Kommunikation**

    https://github.com/App-vNext/Polly

>[!div class="step-by-step"]
>[Zurück](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
>[Weiter](modernize-your-apps-with-monitoring-and-telemetry.md)