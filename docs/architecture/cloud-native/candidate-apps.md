---
title: Kandidaten-Apps für Cloud native
description: Erfahren Sie, welche Anwendungstypen von einem Cloud-nativen Ansatz profitieren
author: robvet
ms.date: 03/31/2020
ms.openlocfilehash: 8e58f5bd3aa0a4503ea73ab454e42e863eb0bb5d
ms.sourcegitcommit: f87ad41b8e62622da126aa928f7640108c4eff98
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/07/2020
ms.locfileid: "80805612"
---
# <a name="candidate-apps-for-cloud-native"></a>Kandidaten-Apps für Cloud native

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Schauen Sie sich die Apps in Ihrem Portfolio an. Wie viele von ihnen qualifizieren sich für eine Cloud-native Architektur? Alle genannten? Vielleicht einige?

Wenn Sie eine Kosten-Nutzen-Analyse anwenden, besteht eine gute Chance, dass die meisten das saftige Preisschild, das für die Cloud-Native erforderlich ist, nicht unterstützen. Die Kosten für Cloud-Nativ würden den geschäftlichen Wert der Anwendung bei weitem übersteigen.

Welche Art von Anwendung könnte ein Kandidat für Cloud Native sein?

- Ein großes, strategisches Unternehmenssystem, das Geschäftsfähigkeiten/-features ständig weiterentwickeln muss

- Eine Anwendung, die eine hohe Freigabegeschwindigkeit erfordert - mit hoher Sicherheit

- Ein System, bei dem einzelne Funktionen *ohne* vollständige Umschichtung des gesamten Systems freigegeben werden müssen

- Eine Anwendung, die von Teams mit Expertise in verschiedenen Technologie-Stacks entwickelt wurde

- Eine Anwendung mit Komponenten, die unabhängig skaliert werden müssen

Dann gibt es legacy Systeme. Obwohl wir alle gerne neue Anwendungen erstellen möchten, sind wir häufig für die Modernisierung von Legacy-Workloads verantwortlich, die für das Unternehmen von entscheidender Bedeutung sind. Im Laufe der Zeit kann eine Legacyanwendung in Microservices zerlegt, containerisiert und schließlich in eine Cloud-native Architektur "neu platformiert" werden.

### <a name="modernizing-legacy-apps"></a>Modernisierung von Legacy-Apps

Das kostenlose Microsoft-E-Book [Modernisieren vorhandener .NET-Anwendungen mit Azure-Cloud und Windows-Containern](https://dotnet.microsoft.com/download/thank-you/modernizing-existing-net-apps-ebook) bietet Anleitungen für die Migration lokaler Workloads in die Cloud. Abbildung 1-10 zeigt, dass es keine einzige Einheitsstrategie für die Modernisierung älterer Anwendungen gibt.

![Strategien für die Migration von Legacy-Workloads](./media/strategies-for-migrating-legacy-workloads.png)

**Abbildung 1-10**. Strategien für die Migration von Legacy-Workloads

Monolithische Apps, die nicht kritisch sind, profitieren größtenteils von einer schnellen Migration mit["Cloud Infrastructure-Ready "Cloud Infrastructure".](../modernize-with-azure-containers/lift-and-shift-existing-apps-azure-iaas.md) Hier wird die lokale Workload ohne Änderungen auf einer cloudbasierten VM wieder gehostet. Bei diesem Ansatz wird das [IaaS-Modell (Infrastructure as a Service) verwendet.](https://azure.microsoft.com/overview/what-is-iaas/) Azure enthält mehrere Tools wie [Azure Migrate](https://azure.microsoft.com/services/azure-migrate/), Azure [Site Recovery](https://azure.microsoft.com/services/site-recovery/)und Azure Database [Migration Service,](https://azure.microsoft.com/campaigns/database-migration/) um eine solche Verschiebung zu vereinfachen. Obwohl diese Strategie einige Kosteneinsparungen bringen kann, wurden solche Anwendungen in der Regel nicht entwickelt, um die Vorteile des Cloud Computing freizuschalten und zu nutzen.

Monolithische Apps, die für das Unternehmen von entscheidender Bedeutung sind, profitieren häufig von einer verbesserten Migration mit Lift-and-Shift (*Cloud Optimized*). Dieser Ansatz umfasst Bereitstellungsoptimierungen, die wichtige Clouddienste ermöglichen , ohne die Kernarchitektur der Anwendung zu ändern. Sie können die Anwendung z. B. [containerisieren](https://docs.microsoft.com/virtualization/windowscontainers/about/) und in einem Containerorchestrator bereitstellen, z. B. [Azure Kubernetes Services](https://azure.microsoft.com/services/kubernetes-service/), der weiter unten in diesem Buch erläutert wird. Einmal in der Cloud, kann die Anwendung andere Clouddienste wie Datenbanken, Nachrichtenwarteschlangen, Überwachung und verteiltes Zwischenspeichern nutzen.

Schließlich könnten monolithische Apps, die strategische Unternehmensfunktionen ausführen, am besten von einem *Cloud-Native-Ansatz* profitieren, der Gegenstand dieses Buches ist. Dieser Ansatz bietet Agilität und Geschwindigkeit. Aber es kostet die Neu-, Neuarchitektur und das Umschreiben von Code.

Wenn Sie und Ihr Team einen Cloud-nativen Ansatz für angemessen halten, müssen Sie die Entscheidung mit Ihrer Organisation rationalisieren. Was genau ist das Geschäftsproblem, das ein Cloud-nativer Ansatz lösen wird? Wie würde sie sich an den geschäftlichen Bedürfnissen orientieren?

- Schnelle Veröffentlichungen von Funktionen mit erhöhtem Selbstvertrauen?

- Feinkörnige Skalierbarkeit - effizientere Nutzung von Ressourcen?

- Verbesserte Systemresilienz?

- Verbesserte Systemleistung?

- Mehr Einblick in Vorgänge?

- Verschmelzen Sie Entwicklungsplattformen und Datenspeicher, um das beste Tool für den Job zu finden?

- Zukunftssichere Anwendungsinvestition?

Die richtige Migrationsstrategie hängt von den organisatorischen Prioritäten und den Systemen ab, auf die Sie abzielen. Für viele kann es kostengünstiger sein, eine monolithische Anwendung in der Cloud zu optimieren oder einer N-Tier-App grobkörnige Dienste hinzuzufügen. In diesen Fällen können Sie weiterhin die Cloud-PaaS-Funktionen, wie sie von Azure App Service angeboten werden, voll ausschöpfen.

## <a name="summary"></a>Zusammenfassung

In diesem Kapitel haben wir Cloud-Native Computing eingeführt. Wir haben eine Definition zusammen mit den wichtigsten Funktionen bereitgestellt, die eine cloudnative Anwendung antreiben. Wir haben uns die Arten von Anwendungen angesehen, die diese Investition und diesen Aufwand rechtfertigen könnten.

Mit der Einführung im Rücken tauchen wir nun in einen viel detaillierteren Blick auf Cloud Native ein.

### <a name="references"></a>References

- [Cloud Native Computing Foundation](https://www.cncf.io/)

- [.NET Microservices: Architektur für containerisierte .NET-Anwendungen](https://dotnet.microsoft.com/download/thank-you/microservices-architecture-ebook)

- [Modernisieren vorhandener .NET-Anwendungen mit Azure Cloud und Windows Containers](https://dotnet.microsoft.com/download/thank-you/modernizing-existing-net-apps-ebook)

- [Cloud Native Patterns von Cornelia Davis](https://www.manning.com/books/cloud-native-patterns)

- [Jenseits der Zwölf-Faktor-Anwendung](https://content.pivotal.io/blog/beyond-the-twelve-factor-app)

- [Was ist Infrastruktur als Code](https://docs.microsoft.com/azure/devops/learn/what-is-infrastructure-as-code)

- [Micro Deploy von Uber Engineering: Täglich mit Zuversicht bereitstellen](https://eng.uber.com/micro-deploy/)

- [Wie Netflix Code bereitstellt](https://www.infoq.com/news/2013/06/netflix/)

- [Überlaststeuerung für die Skalierung von WeChat Microservices](https://www.cs.columbia.edu/~ruigu/papers/socc18-final100.pdf)

>[!div class="step-by-step"]
>[Zurück](definition.md)
>[Weiter](introduce-eshoponcontainers-reference-app.md)
