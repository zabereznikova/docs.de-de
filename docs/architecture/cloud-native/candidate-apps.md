---
title: Kandidaten-Apps für die native Cloud
description: Erfahren Sie, welche Arten von Anwendungen von einem cloudbasierten Ansatz profitieren.
author: robvet
ms.date: 05/14/2020
ms.openlocfilehash: b907a17b2351bc4ffe49fd6eb6f5963b209d00db
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614239"
---
# <a name="candidate-apps-for-cloud-native"></a>Kandidaten-Apps für die native Cloud

Sehen Sie sich die apps in Ihrem Portfolio an. Wie viele von Ihnen sind für eine Cloud-Native Architektur qualifiziert? Alle genannten? Vielleicht etwas?

Wenn Sie eine Kosten-/Nutzungsanalyse durch nehmen, besteht die Möglichkeit, dass die meisten nicht das heftige Preis Kennzeichen unterstützen, das in der Cloud System eigen sein muss. Die Kosten für eine native Cloud würden den Geschäftswert der Anwendung weit überschreiten.

Welche Art von Anwendung ist möglicherweise ein Kandidat für die native Cloud?

- Strategisches Unternehmenssystem, das ständig Geschäftsfunktionen/-Features entwickeln muss

- Eine Anwendung, die eine hohe releasegeschwindigkeit erfordert, mit hohem Vertrauen

- Ein System, in dem einzelne Features *ohne* vollständige erneute Bereitstellung des gesamten Systems freigegeben werden müssen

- Eine Anwendung, die von Teams mit Fachkenntnissen in verschiedenen Technologie Stapeln entwickelt wurde

- Eine Anwendung mit Komponenten, die unabhängig voneinander skaliert werden müssen

Dann gibt es ältere Systeme. Wir möchten zwar neue Anwendungen erstellen, aber wir sind häufig dafür verantwortlich, ältere Workloads zu modernisieren, die für das Unternehmen von entscheidender Bedeutung sind. Im Laufe der Zeit könnte eine Legacy Anwendung in microservices, containerisiert und letztendlich "replatgeformt" in eine cloudbasierte Architektur zerlegt werden.

### <a name="modernizing-legacy-apps"></a>Modernialisieren von Legacy-apps

Das kostenlose e-Book von Microsoft zur [Modernisierung vorhandener .NET-Anwendungen mit Azure Cloud und Windows-Containern](https://dotnet.microsoft.com/download/thank-you/modernizing-existing-net-apps-ebook) bietet Anleitungen zum Migrieren von lokalen Workloads in die Cloud. In Abbildung 1-10 sehen Sie, dass es für die Modernisierung älterer Anwendungen keine einzige, eindimensionale Strategie gibt.

![Strategien zum Migrieren von Legacy-Workloads](./media/strategies-for-migrating-legacy-workloads.png)

**Abbildung 1-10**. Strategien zum Migrieren von Legacy-Workloads

Monolithische apps, die nicht schwerwiegend sind, profitieren größtenteils von einer schnellen Lift-and-Shift-Migration ([cloudinfrastructure-Ready](../modernize-with-azure-containers/lift-and-shift-existing-apps-azure-iaas.md)). Hier wird die lokale Arbeitsauslastung ohne Änderungen erneut auf einem cloudbasierten virtuellen Computer gehostet. Bei diesem Ansatz wird das [IaaS-Modell (Infrastructure-as-a-Service)](https://azure.microsoft.com/overview/what-is-iaas/)verwendet. Azure umfasst mehrere Tools, wie z. b. [Azure migrate](https://azure.microsoft.com/services/azure-migrate/), [Azure Site Recovery](https://azure.microsoft.com/services/site-recovery/)und [Azure Database Migration Service](https://azure.microsoft.com/campaigns/database-migration/) , um eine solche Verschiebung zu vereinfachen. Wenngleich diese Strategie zu Kosteneinsparungen führen kann, sind solche Anwendungen in der Regel nicht so entworfen, dass Sie die Vorteile von Cloud Computing entsperren und nutzen können.

Monolithische apps, die für das Unternehmen von entscheidender Bedeutung sind, profitieren von einer verbesserten Lift-and-Shift-Migration (*cloudoptimiert*). Diese Vorgehensweise umfasst Bereitstellungs Optimierungen, die wichtige Clouddienste ermöglichen, ohne die Kernarchitektur der Anwendung zu ändern. Beispielsweise können Sie die Anwendung [containerisieren](https://docs.microsoft.com/virtualization/windowscontainers/about/) und in einem containerorchestrator wie [Azure Kubernetes Services bereitstellen](https://azure.microsoft.com/services/kubernetes-service/), der weiter unten in diesem Buch erläutert wird. In der Cloud kann die Anwendung andere Clouddienste nutzen, wie z. b. Datenbanken, Nachrichten Warteschlangen, Überwachung und verteiltes Zwischenspeichern.

Schließlich können monolithische apps, die strategische Unternehmensfunktionen durchführen, am besten von einem *cloudbasierten* Ansatz profitieren, dem Betreff dieses Buchs. Dieser Ansatz bietet Agilität und Geschwindigkeit. Allerdings entstehen Kosten für die Neuplatzierung, Umgestaltung und Neuerstellung von Code.

Wenn Sie und Ihr Team der Meinung sind, dass ein cloudbasierter Ansatz geeignet ist, sollten Sie die Entscheidung mit Ihrer Organisation rationalisieren. Was genau ist das Geschäftsproblem, das ein cloudbasierter Ansatz lösen wird? Wie sieht es mit den geschäftlichen Anforderungen aus?

- Schnelle Versionen von Features mit mehr Vertrauen?

- Differenzierte Skalierbarkeit: effizientere Nutzung von Ressourcen?

- Verbesserte Resilienz des Systems?

- Verbesserte Systemleistung?

- Mehr Transparenz in Betrieb?

- Entwickeln Sie Entwicklungsplattformen und Datenspeicher, um das beste Tool für den Auftrag zu erreichen?

- Zukunftssichere Anwendungs Investition?

Die richtige Migrationsstrategie hängt von den Organisations Prioritäten und den Systemen ab, auf die Sie abzielen. Für viele ist es möglicherweise kostengünstiger, eine monolithische Anwendung in der Cloud zu optimieren oder einer N-Tier-App grobe Dienste hinzuzufügen. In diesen Fällen können Sie die Cloud-Funktionen wie die von Azure App Service bereitgestellten Funktionen weiterhin vollständig nutzen.

## <a name="summary"></a>Zusammenfassung

In diesem Kapitel haben wir das Native Cloud-Computing eingeführt. Wir haben eine Definition zusammen mit den wichtigsten Funktionen bereitgestellt, die eine in der Cloud native Anwendung fördern. Wir haben uns mit den Anwendungs Typen beschäftigt, die diese Investition und den Aufwand rechtfertigen können.

Mit der Einführung hinter sehen wir uns nun einen ausführlicheren Überblick über die Cloud Native an.

### <a name="references"></a>Referenzen

- [Cloud Native Computing Foundation](https://www.cncf.io/)

- [.Net-microservices: Architektur für .NET-Container Anwendungen](https://dotnet.microsoft.com/download/thank-you/microservices-architecture-ebook)

- [Modernisieren vorhandener .NET-Anwendungen mit Azure Cloud und Windows-Containern](https://dotnet.microsoft.com/download/thank-you/modernizing-existing-net-apps-ebook)

- [Native Cloud-Muster von Cornelia Davis](https://www.manning.com/books/cloud-native-patterns)

- [Über die zwölfstufige Anwendung hinaus](https://content.pivotal.io/blog/beyond-the-twelve-factor-app)

- [Was ist Infrastructure als Code?](https://docs.microsoft.com/azure/devops/learn/what-is-infrastructure-as-code)

- [Microbereitstellung von uber Engineering: tägliche Bereitstellung mit Vertrauen](https://eng.uber.com/micro-deploy/)

- [Bereitstellen von Code durch Netflix](https://www.infoq.com/news/2013/06/netflix/)

- [Überladungs Steuerelement zum Skalieren von WeChat-mikrodiensten](https://www.cs.columbia.edu/~ruigu/papers/socc18-final100.pdf)

>[!div class="step-by-step"]
>[Zurück](definition.md)
>[Weiter](introduce-eshoponcontainers-reference-app.md)
