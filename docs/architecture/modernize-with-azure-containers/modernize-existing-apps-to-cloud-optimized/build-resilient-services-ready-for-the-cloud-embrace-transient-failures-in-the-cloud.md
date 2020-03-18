---
title: Erstellen robuster Clouddienste. Beheben vorübergehender Fehler in der Cloud
description: Modernisieren vorhandener .NET-Anwendungen mit Azure Cloud und Windows-Containern | Erstellen robuster Clouddienste. Beheben vorübergehender Fehler in der Cloud
ms.date: 04/30/2018
ms.openlocfilehash: e516dc675ceb8def25c6d676bced0ea7f253b2d5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "74711248"
---
# <a name="build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud"></a>Erstellen robuster Clouddienste: Beheben vorübergehender Fehler in der Cloud

Als Stabilität wird die Fähigkeit zum Wiederherstellen nach Fehlern und zum Fortsetzen der Funktionsweise bezeichnet. Bei Stabilität geht es nicht um das Vermeiden von Fehlern, sondern um das Akzeptieren der Tatsache, dass Fehler passieren und um eine angemessene Reaktion auf diese, um Ausfallzeiten und Datenverluste zu vermeiden. Das Ziel der Stabilität ist, die Anwendung nach einem Fehler wieder in einen voll funktionsfähigen Zustand zu versetzen.

Ihre Anwendung ist für die Cloud bereit, wenn sie mindestens ein softwarebasiertes Modell für Stabilität (Resilienz) implementiert, anstatt ein hardwarebasiertes Modell. Ihre Cloudanwendung muss die Teilfehler umfassen, die sicher auftreten werden. Entwerfen oder gestalten Sie ihre Anwendung teilweise um, um Resilienz gegenüber erwarteten Teilfehlern zu erzielen. Sie sollte dafür entworfen sein, mit Teilfehlern wie vorübergehenden Netzwerkausfällen und Knoten oder virtuellen Computern, die in der Cloud abstürzen, umzugehen. Sogar Container, die innerhalb eines Orchestratorclusters auf einen anderen Knoten verschoben werden, können zeitweilig kurze Fehler in der Anwendung verursachen.

## <a name="handling-partial-failure"></a>Behandeln von Teilfehlern

In einer cloudbasierten Anwendung gibt es ein allgegenwärtiges Risiko für Teilfehler. Beispielsweise können eine einzelne Websiteinstanz oder ein Container fehlschlagen, oder sie/er ist möglicherweise für kurze Zeit nicht verfügbar oder reagiert nicht. Oder ein einzelner virtueller Computer oder Server kann abstürzen.

Da Clients und Dienste separate Vorgänge sind, kann ein Dienst möglicherweise nicht schnell genug auf die Anforderung eines Clients reagieren. Der Dienst ist möglicherweise überlastet und antwortet langsam auf Anforderungen, oder er ist aufgrund von Netzwerkproblemen vorübergehend nicht verfügbar.

Stellen Sie sich beispielsweise eine monolithische .NET-Anwendung vor, die auf eine Datenbank in Azure SQL-Datenbank zugreift. Wenn die Azure SQL-Datenbank oder ein anderer Drittanbieterdienst für einen kurzen Zeitraum nicht reagiert (eine Azure SQL-Datenbank wird möglicherweise auf einen anderen Knoten oder Server verschoben, und reagiert einige Sekunden lang nicht), wenn der Benutzer versucht, eine Aktion durchzuführen, stürzt die Anwendung möglicherweise ab und gibt gleichzeitig eine Ausnahme aus.

Ein ähnliches Szenario kann in einer App auftreten, die HTTP-Dienste nutzt. Das Netzwerk oder der Dienst selbst ist möglicherweise während eines kurzen vorübergehenden Fehlers in der Cloud nicht verfügbar.

Eine robuste Anwendung, wie die in Abbildung 4-9 gezeigte, sollte Verfahren wie „Wiederholungsversuche mit exponentiellem Backoff“ implementieren, um der Anwendung die Möglichkeit zu geben, vorübergehende Fehler in Ressourcen zu verarbeiten. Sie sollten auch „Trennschalter“ in Ihren Anwendungen verwenden. Ein Trennschalter beendet die Versuche einer Anwendung, auf eine Ressource zuzugreifen, wenn es sich tatsächlich um einen langfristigen Fehler handelt. Durch die Verwendung eines Trennschalters vermeidet die Anwendung einen Denial-of-Service-Angriff auf sich selbst.

![Diagramm der von Wiederholungsversuchen mit exponentiellem Backoff behandelten Teilfehler.](./media/retry-partial-failures.png)

**Abbildung 4–9.** Von Wiederholungsversuchen mit exponentiellem Backoff behandelte Teilfehler

Sie können diese Verfahren sowohl in HTTP-Ressourcen als auch in Datenbankressourcen verwenden. In Abbildung 4-9 basiert die Anwendung auf einer 3-schichtigen Architektur, sodass Sie diese Verfahren auf der Dienstebene (HTPP) und auf der Datenschichtebene (TCP) benötigen. In einer monolithischen Anwendung, die zusätzlich zur Datenbank nur eine einzelne App-Ebene verwendet (keine zusätzlichen Dienste oder Microservices), kann das behandeln vorübergehender Fehler auf Datenbankverbindungsebene ausreichen. In diesem Szenario ist nur eine bestimmte Konfiguration der Datenbankverbindung erforderlich.

Bei der Implementierung robuster Kommunikationen, die auf die Datenbank zugreifen, kann dies je nach verwendeter .NET-Version unkompliziert sein (z. B. [mit Entity Framework 6 oder höher](/ef/ef6/fundamentals/connection-resiliency/retry-logic). Es ist nur eine Frage der Konfiguration der Datenbankverbindung.). Oder Sie müssen möglicherweise zusätzliche Bibliotheken verwenden, wie z. B. den [Anwendungsblock zur Handhabung von vorübergehenden Fehlern](https://docs.microsoft.com/previous-versions/msp-n-p/hh680934(v=pandp.50)) (Transient Fault Handling Application Block; für frühere Versionen von .NET), oder sogar Ihre eigene Bibliothek implementieren.

Bei der Implementierung von HTTP-Wiederholungsversuchen und Trennschaltern empfiehlt es sich bei .NET, die [Polly](https://github.com/App-vNext/Polly)-Bibliothek zu verwenden, die auf .NET Framework 4.0, .NET Framework 4.5 und .NET Standard 1.1 abzielt, was die Unterstützung von .NET Core umfasst.

Informationen zum Implementieren von Strategien für die Handhabung von Teilfehlern in der Cloud finden Sie in den folgenden Referenzen.

### <a name="additional-resources"></a>Zusätzliche Ressourcen

- **Implementieren robuster Kommunikation zur Handhabung von Teilfehlern**

    [https://docs.microsoft.com/dotnet/architecture/microservices/implement-resilient-applications/partial-failure-strategies](../../microservices/implement-resilient-applications/partial-failure-strategies.md)

- **Entity Framework-Verbindungsresilienz und -wiederholungslogik (Version 6 und höher)**

    [https://docs.microsoft.com/ef/ef6/fundamentals/connection-resiliency/retry-logic](/ef/ef6/fundamentals/connection-resiliency/retry-logic)

- **Anwendungsblock zum Behandeln vorübergehender Fehler**

- <https://docs.microsoft.com/previous-versions/msp-n-p/hh680934(v=pandp.50)>

- **Polly-Bibliothek für robuste HTTP-Kommunikation**

    https://github.com/App-vNext/Polly

>[!div class="step-by-step"]
>[Zurück](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
>[Weiter](modernize-your-apps-with-monitoring-and-telemetry.md)
