---
title: Erstellen Sie resilienter Dienste für die Cloud bereit. Vorübergehende Fehler in der Cloud zu nutzen
description: Aktualisieren von vorhandenen .NET Anwendungen mit Azure-Cloud und Windows-Containern | Erstellen Sie resilienter Dienste für die Cloud bereit. Vorübergehende Fehler in der Cloud zu nutzen
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/30/2018
ms.openlocfilehash: 1df21d0f647b96c315686921276be3526f66bbc8
ms.sourcegitcommit: 88f251b08bf0718ce119f3d7302f514b74895038
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/10/2018
---
# <a name="build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud"></a>Resilienter Dienste bereit, für die Cloud zu erstellen: vorübergehende Fehler in der Cloud zu nutzen

Als Stabilität wird die Fähigkeit zum Wiederherstellen nach Fehlern und zum Fortsetzen der Funktionsweise bezeichnet. Stabilität ist nicht zum Vermeiden von Fehlern, jedoch akzeptiert die Tatsache, dass Fehler auftreten und reagiert dann in einer Weise, die Downtime und Datenverluste vermieden werden. Das Ziel der Stabilität ist, die Anwendung nach einem Fehler wieder in einen voll funktionsfähigen Zustand zu versetzen.

Die Anwendung ist für die Cloud bereit, wenn mindestens ein Modell softwarebasierten resilienzgrad, anstatt eine Hardware-basiertes Modell implementiert. Ihre Cloud-Anwendung muss die teilfehler nutzen, die sicherlich stattfinden. Entwerfen Sie oder gestalten Sie teilweise die Anwendung mit erwarteten teilfehlern Stabilität zu erzielen. Es sollten so entworfen werden, zu bewältigen teilfehler, z. B. vorübergehende Netzwerkausfälle und Knoten oder virtuellen Computern in der Cloud abstürzt. Sogar Container verschoben werden, auf einen anderen Knoten innerhalb eines Clusters Orchestrator können kurze Ausfälle in der Anwendung verursachen.

## <a name="handling-partial-failure"></a>Behandeln von Teilfehlern

In einer Cloud-basierten Anwendung ist eine partielle allgegenwärtigen Ausfallrisiko vorhanden. Z. B. fehlschlagen, eine einzelne Website-Instanz oder einen Container, oder es möglicherweise nicht verfügbar oder nicht reagierenden für kurze Zeit. Alternativ dazu können Sie einen einzelnen virtuellen Computer oder Server stürzt möglicherweise ab.

Da Clients und Dienste separate Vorgänge dar, ein Dienst nicht rechtzeitig auf Anforderung des Clients reagieren möglicherweise. Der Dienst möglicherweise überladen werden und auf Anforderungen langsam reagiert, oder es möglicherweise nicht verfügbar für kurze Zeit aufgrund von Netzwerkproblemen.

Betrachten Sie beispielsweise eine monolithische .NET-Anwendung, die auf eine Datenbank in Azure SQL-Datenbank zugreift. Wenn der Azure SQL-Datenbank oder andere Drittanbieterdienst nicht reagiert für eine kurze Zeit (eine Azure SQL-Datenbank kann an einem anderen Knoten oder Server verschoben werden und werden nicht mehr reagiert für einige Sekunden), wenn der Benutzer versucht, die keine Aktionen ausführen, stürzt die Anwendung und ähnliche w-Ausnahme zum gleichen Zeitpunkt.

Ein ähnliches Szenario kann in einer app auftreten, die HTTP-Dienste verwendet. Das Netzwerk oder der Dienst selbst möglicherweise nicht in der Cloud während einer kurzen, vorübergehende Fehler verfügbar.

Eine robuste Anwendung wie in Abbildung 4-9 sollten Techniken, wie "Wiederholungen mit exponenzieller" implementieren, so erteilen Sie der Anwendung Gelegenheit, vorübergehende Fehler in der Ressourcen zu behandeln. Sie sollten auch "Trennschalter" in Ihren Anwendungen verwenden. Ein Trennschalter wird eine Anwendung versucht, eine Ressource zuzugreifen, wenn es tatsächlich einen langfristigen Fehler wird beendet. Mithilfe von ein Trennschalter vermeidet die Anwendung provozieren einen Denial of Service auf sich selbst.

![Teilweise Ausfälle von Wiederholungen mit exponenzieller behandelt](./media/image9.png)

> **Abbildung 4-9.** Teilweise Ausfälle von Wiederholungen mit exponenzieller behandelt

Sie können diese Techniken in HTTP-Ressourcen und in Database-Ressourcen verwenden. In Abbildung 4-9, basiert die Anwendung auf einer 3-Ebenen-Architektur, daher Sie diese Verfahren auf der Ebene der Dienste (HTTP) und auf der Ebene der Daten (TCP benötigen). In einer monolithischen-Anwendung, die nur eine einzelne app-Ebene zusätzlich zu der Datenbank (ohne zusätzliche Dienste oder Microservices) verwendet, kann Verarbeitung vorübergehender Fehler auf Verbindungsebene Datenbank ausreichend sein. In diesem Szenario ist nur eine bestimmte Konfiguration der Verbindung mit der Datenbank erforderlich.

Bei der Implementierung von robusten Kommunikation, die Sie verwenden auf die Datenbank, abhängig von der Version von .NET zugreifen, kann einfach sein (z. B. [mit Entity Framework 6 oder höher](https://msdn.microsoft.com/library/dn456835(v=vs.113).aspx), es geht nur darum, der Konfiguration der datenbankverbindung). Oder Sie müssen zusätzliche Bibliotheken wie die [vorübergehenden Anwendungsblock zur Behandlung](https://msdn.microsoft.com/library/hh680934(v=pandp.50).aspx) (für frühere Versionen von .NET), oder implementieren Sie sogar eigene Bibliothek.

Beim HTTP-Wiederholungsversuche und Trennschalter implementieren die Empfehlung für .NET ist die Verwendung der [Polly](https://github.com/App-vNext/Polly) -Bibliothek, die Ziel von .NET Framework 4.0, .NET Framework 4.5 und .NET Standard 1.1, die .NET Core-Unterstützung umfasst.

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
