---
title: Erstellen Sie robuste Dienste, die für die Cloud bereit sind. Beheben vorübergehender Fehler in der Cloud
description: Modernisieren vorhandener .NET-Anwendungen mit Azure Cloud und Windows-Containern | Erstellen Sie robuste Dienste, die für die Cloud bereit sind. Beheben vorübergehender Fehler in der Cloud
ms.date: 04/30/2018
ms.openlocfilehash: e6fae8140b55cb0308dca9f4b77e961501b41f8f
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2019
ms.locfileid: "73739394"
---
# <a name="build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud"></a>Erstellen robuster Dienste, die für die Cloud bereit sind: vorübergehende Ausfälle in der Cloud

Als Stabilität wird die Fähigkeit zum Wiederherstellen nach Fehlern und zum Fortsetzen der Funktionsweise bezeichnet. Bei der Resilienz geht es nicht darum, Ausfälle zu vermeiden, sondern die Tatsache zu akzeptieren, dass Fehler auftreten, und dann auf eine Weise darauf zu reagieren, dass Ausfallzeiten oder Datenverluste vermieden werden. Das Ziel der Stabilität ist, die Anwendung nach einem Fehler wieder in einen voll funktionsfähigen Zustand zu versetzen.

Die Anwendung ist für die Cloud bereit, wenn Sie mindestens ein softwarebasiertes Modell der Resilienz implementiert, anstatt ein Hardware basiertes Modell. Ihre cloudanwendung muss die Teil Fehler, die auf jeden Fall auftreten, berücksichtigen. Entwerfen oder partielles Umgestalten ihrer Anwendung, um Resilienz bei erwarteten Teil Fehlern zu erzielen. Sie sollte so entworfen werden, dass Sie mit partiellen Fehlern wie vorübergehenden Netzwerkausfällen und Knoten oder VMS in der Cloud zurechtkommt. Selbst Container, die auf einen anderen Knoten innerhalb eines Orchestrator-Clusters verschoben werden, können zu vorübergehenden kurzen Fehlern innerhalb der Anwendung führen.

## <a name="handling-partial-failure"></a>Behandeln von Teilfehlern

In einer cloudbasierten Anwendung gibt es ein immer vorhandenes Risiko eines Teil Fehlers. Beispielsweise kann eine einzelne Website Instanz oder ein Container fehlschlagen, oder Sie ist möglicherweise nicht verfügbar oder reagiert für kurze Zeit nicht. Oder ein einzelner virtueller Computer oder Server stürzt ab.

Da es sich bei Clients und Diensten um separate Prozesse handelt, kann ein Dienst möglicherweise nicht rechtzeitig auf die Anforderung eines Clients reagieren. Der Dienst ist möglicherweise überlastet und reagiert langsam auf Anforderungen, oder er ist aufgrund von Netzwerkproblemen möglicherweise für kurze Zeit nicht verfügbar.

Stellen Sie sich beispielsweise eine monolithische .NET-Anwendung vor, die auf eine Datenbank in Azure SQL-Datenbank zugreift. Wenn die Azure SQL-Datenbank oder ein anderer Drittanbieter Dienst für einen kurzen Zeitraum nicht reagiert (eine Azure SQL-Datenbank wird möglicherweise auf einen anderen Knoten oder Server verschoben, und die Reaktionszeit dauert einige Sekunden nicht.), wenn der Benutzer versucht, eine Aktion durchzuführen, stürzt die Anwendung möglicherweise ab. eine Ausnahme gleichzeitig.

Ein ähnliches Szenario kann in einer APP auftreten, die HTTP-Dienste nutzt. Das Netzwerk oder der Dienst selbst ist in der Cloud möglicherweise nicht während eines kurzen vorübergehenden Fehlers verfügbar.

Eine robuste Anwendung, wie die in Abbildung 4-9 gezeigt, sollte Verfahren wie "Wiederholungs Versuche mit exponentiellem Backoff" implementieren, um der Anwendung die Möglichkeit zu geben, vorübergehende Fehler in Ressourcen zu verarbeiten. Sie sollten auch "Trennschalter" in Ihren Anwendungen verwenden. Ein Trennschalter hindert eine Anwendung daran, auf eine Ressource zuzugreifen, wenn es sich um einen langfristigen Fehler handelt. Durch die Verwendung eines Trenn Schalters vermeidet die Anwendung einen Denial-of-Service-Angriff auf sich selbst.

![Diagramm der Teil Fehler, die von Wiederholungen mit exponentiellem Backoff behandelt werden.](./media/build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud/retry-partial-failures.png)

**Abbildung 4-9.** Teil Fehler, die von Wiederholungen mit exponentiellem Backoff behandelt werden

Sie können diese Techniken sowohl in http-Ressourcen als auch in Datenbankressourcen verwenden. In Abbildung 4-9 basiert die Anwendung auf einer 3-Ebenen-Architektur, sodass Sie diese Techniken auf der Dienst Ebene (http) und auf Ebene der Datenebene (TCP) benötigen. In einer monolithischen Anwendung, die zusätzlich zur-Datenbank nur eine einzelne APP-Ebene verwendet (keine zusätzlichen Dienste oder-Dienste), kann das behandeln vorübergehender Fehler auf der Daten bankverbindungs Ebene ausreichen. In diesem Szenario ist nur eine bestimmte Konfiguration der Datenbankverbindung erforderlich.

Bei der Implementierung robuster Kommunikationen, die auf die Datenbank zugreifen, kann dies abhängig von der verwendeten .NET-Version (z. b. [mit Entity Framework 6 oder](/ef/ef6/fundamentals/connection-resiliency/retry-logic)höher) unkompliziert erfolgen. Es ist nur eine Frage der Konfiguration der Datenbankverbindung. Oder Sie müssen möglicherweise zusätzliche Bibliotheken wie den [Anwendungs Block zur Behandlung vorübergehender Fehler](https://docs.microsoft.com/previous-versions/msp-n-p/hh680934(v=pandp.50)) (für frühere Versionen von .net) verwenden oder sogar Ihre eigene Bibliothek implementieren.

Bei der Implementierung von http-Wiederholungen und Schutz Schaltern empfiehlt es sich, die [Polly](https://github.com/App-vNext/Polly) -Bibliothek zu verwenden, die .NET Framework 4,0, .NET Framework 4,5 und .NET Standard 1,1 verwendet, einschließlich der .net Core-Unterstützung.

Informationen zum Implementieren von Strategien für die Behandlung von Teil Fehlern in der Cloud finden Sie in den folgenden Referenzen.

### <a name="additional-resources"></a>Zusätzliche Ressourcen

- **Implementieren robuster Kommunikation zur Behandlung von Teil Fehlern**

    [https://docs.microsoft.com/dotnet/architecture/microservices/implement-resilient-applications/partial-failure-strategies](../../microservices/implement-resilient-applications/partial-failure-strategies.md)

- **Entity Framework verbindungsresilienz und Wiederholungs Logik (Version 6 und höher)**

    [https://docs.microsoft.com/ef/ef6/fundamentals/connection-resiliency/retry-logic](/ef/ef6/fundamentals/connection-resiliency/retry-logic)

- **Anwendungs Block zur Behandlung vorübergehender Fehler**

- <https://docs.microsoft.com/previous-versions/msp-n-p/hh680934(v=pandp.50)>

- **Polly Library für robuste HTTP-Kommunikation**

    https://github.com/App-vNext/Polly

>[!div class="step-by-step"]
>[Zurück](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
>[Weiter](modernize-your-apps-with-monitoring-and-telemetry.md)
