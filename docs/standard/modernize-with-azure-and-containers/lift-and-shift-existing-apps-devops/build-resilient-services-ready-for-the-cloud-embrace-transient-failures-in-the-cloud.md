---
title: "Erstellen Sie resilienter Dienste für die Cloud bereit. Vorübergehende Fehler in der Cloud zu nutzen"
description: ".NET Microservices Architektur für Datenvolumes .NET-Anwendungen | Erstellen Sie resilienter Dienste für die Cloud bereit. Vorübergehende Fehler in der Cloud zu nutzen"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/26/2017
ms.prod: .net
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: df452c9fbf1c16603efcec40844b55810bd5d2d4
ms.sourcegitcommit: d3cfda0943364aaf6ccd574f55f584576c8a4fee
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/08/2018
---
# <a name="build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud"></a>Resilienter Dienste bereit, für die Cloud zu erstellen: vorübergehende Fehler in der Cloud zu nutzen

Als Stabilität wird die Fähigkeit zum Wiederherstellen nach Fehlern und zum Fortsetzen der Funktionsweise bezeichnet. Stabilität ist nicht zum Vermeiden von Fehlern, jedoch akzeptiert die Tatsache, dass Fehler auftreten und reagiert dann in einer Weise, die Downtime und Datenverluste vermieden werden. Das Ziel der Stabilität ist, die Anwendung nach einem Fehler wieder in einen voll funktionsfähigen Zustand zu versetzen.

Die Anwendung ist für die Cloud bereit, wenn mindestens ein Modell softwarebasierten resilienzgrad, anstatt eine Hardware-basiertes Modell implementiert. Ihre Cloud-Anwendung muss die teilfehler nutzen, die sicherlich stattfinden. Sie müssen zum Entwerfen, oder gestalten Sie teilweise die Anwendung auf, wenn Sie Stabilität bei erwarteten teilfehler erzielen möchten. Es sollten so entworfen werden, zu bewältigen teilfehler, z. B. vorübergehende Netzwerkausfälle und Knoten oder virtuellen Computern in der Cloud abstürzt. Sogar Container verschoben werden, auf einen anderen Knoten innerhalb eines Clusters Orchestrator können kurze Ausfälle in der Anwendung verursachen.

## <a name="handling-partial-failure"></a>Behandeln von Teilfehlern

In einer Cloud-basierten Anwendung ist eine partielle allgegenwärtigen Ausfallrisiko vorhanden. Z. B. fehlschlagen, eine einzelne Website-Instanz oder einen Container, oder es möglicherweise nicht verfügbar oder nicht reagierenden für kurze Zeit. Alternativ dazu können Sie einen einzelnen virtuellen Computer oder Server stürzt möglicherweise ab.

Da Clients und Dienste separate Vorgänge dar, ein Dienst nicht rechtzeitig auf Anforderung des Clients reagieren möglicherweise. Der Dienst möglicherweise überladen werden und auf Anforderungen extrem langsam reagiert, oder es einfach möglicherweise nicht verfügbar für kurze Zeit aufgrund von Netzwerkproblemen.

Betrachten Sie beispielsweise eine monolithische .NET-Anwendung, die auf eine Datenbank in Azure SQL-Datenbank zugreift. Wenn der Azure SQL-Datenbank oder andere Drittanbieterdienst nicht reagiert für eine kurze Zeit (eine Azure SQL-Datenbank kann an einem anderen Knoten oder Server verschoben werden und werden nicht mehr reagiert für einige Sekunden), wenn der Benutzer versucht, die keine Aktionen ausführen, stürzt die Anwendung und ähnliche eine Ausnahme im Moment selbe w.

Ein ähnliches Szenario kann in einer app auftreten, die HTTP-Dienste verwendet. Das Netzwerk oder der Dienst selbst möglicherweise nicht in der Cloud während einer kurzen, vorübergehende Fehler verfügbar.

Eine robuste Anwendung wie in Abbildung 4-9 sollten Techniken, wie "Wiederholungen mit exponenzieller" implementieren, so erteilen Sie der Anwendung Gelegenheit, vorübergehende Fehler in der Ressourcen zu behandeln. Sie sollten auch "Trennschalter" in Ihren Anwendungen verwenden. Ein Trennschalter wird eine Anwendung versucht, eine Ressource zuzugreifen, wenn es tatsächlich einen langfristigen Fehler wird beendet. Mithilfe von ein Trennschalter vermeidet die Anwendung provozieren einen Denial of Service auf sich selbst.

![Teilweise Ausfälle von Wiederholungen mit exponenzieller behandelt](./media/image9.png)

> **Abbildung 4-9.** Teilweise Ausfälle von Wiederholungen mit exponenzieller behandelt

Sie können diese Techniken in HTTP-Ressourcen und in Database-Ressourcen verwenden. In Abbildung 4-9, basiert die Anwendung auf einer 3-Ebenen-Architektur, daher Sie diese Verfahren auf der Ebene der Dienste (HTTP) und auf der Ebene der Daten (TCP benötigen). In einer monolithischen-Anwendung, die nur eine einzelne app-Ebene zusätzlich zu der Datenbank (ohne zusätzliche Dienste oder Microservices) verwendet, kann Verarbeitung vorübergehender Fehler auf Verbindungsebene Datenbank ausreichend sein. In diesem Szenario ist in der Regel nur eine bestimmte Konfiguration der Verbindung mit der Datenbank erforderlich.

Wenn robuste Kommunikation zu implementieren, die die Datenbank, abhängig von der Version von .NET zugreifen, Sie verwenden, kann es sehr einfach sein (z. B. [mit Entity Framework 6 oder höher](https://msdn.microsoft.com/library/dn456835(v=vs.113).aspx), es geht nur darum, der Konfiguration der datenbankverbindung). Oder Sie müssen zusätzliche Bibliotheken wie die [vorübergehenden Anwendungsblock zur Behandlung](https://msdn.microsoft.com/library/hh680934(v=pandp.50).aspx) (für frühere Versionen von .NET), oder implementieren Sie sogar eigene Bibliothek.

Beim HTTP-Wiederholungsversuche und Trennschalter implementieren die Empfehlung für .NET ist die Verwendung der [Polly](https://github.com/App-vNext/Polly) -Bibliothek, die Ziel von .NET 4.0, .NET 4.5 und .NET Standard 1.1, die .NET Core-Unterstützung umfasst.

Gewusst wie: Implementieren von Strategien für die Behandlung von teilfehler in der Cloud finden Sie unter den folgenden Ressourcen.

### <a name="additional-resources"></a>Zusätzliche Ressourcen

-   **Implementieren robusten Kommunikation zum partiellen Fehler behandeln**

    [https://docs.microsoft.com/dotnet/standard/microservices-architecture/implement-resilient-applications/partial-failure-strategies](../../microservices-architecture/implement-resilient-applications/partial-failure-strategies.md)

-   **Entity Framework Connection Resiliency und Wiederholungslogik (Version 6 und höher)**

    [https://msdn.microsoft.com/library/dn456835(v=vs.113).aspx](https://msdn.microsoft.com/library/dn456835(v=vs.113).aspx)

-   **Der Anwendungsblock für die Behandlung vorübergehender Fehler**

-   [https://msdn.microsoft.com/library/hh680934(v=pandp.50).aspx](https://msdn.microsoft.com/library/hh680934(v=pandp.50).aspx)

-   **Polly-Bibliothek für robusten HTTP-Kommunikation**

    https://github.com/App-vNext/Polly

>[!div class="step-by-step"]
[Zurück](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
[Weiter](modernize-your-apps-with-monitoring-and-telemetry.md)
