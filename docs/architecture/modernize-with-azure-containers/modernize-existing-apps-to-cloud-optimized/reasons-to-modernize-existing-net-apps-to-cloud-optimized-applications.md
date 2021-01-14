---
title: Gründe für die Modernisierung vorhandener .NET-Apps in cloudoptimierte Anwendungen
description: Modernisieren vorhandener .NET-Anwendungen mit Azure Cloud und Windows-Containern | Gründe für die Modernisierung vorhandener .NET-Apps in cloudoptimierte Anwendungen
ms.date: 12/21/2020
ms.openlocfilehash: e9b3ad151cf0591783ada8a1ab87cb0f14423a7e
ms.sourcegitcommit: 5d9cee27d9ffe8f5670e5f663434511e81b8ac38
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2021
ms.locfileid: "98025211"
---
# <a name="reasons-to-modernize-existing-net-apps-to-cloud-optimized-applications"></a>Gründe für die Modernisierung vorhandener .NET-Apps in cloudoptimierte Anwendungen

Mit einer cloudoptimierten Anwendung können Sie Ihren Kunden schnell und wiederholt zuverlässige Anwendungen bereitstellen. Sie erhalten wesentliche Flexibilität und Zuverlässigkeit, indem Sie einen Großteil der Betriebskomplexität Ihrer App auf die Plattform verschieben.

Wenn Sie Ihre Anwendungen nicht schnell auf den Markt bringen können, hat sich der Markt, den Sie als Ziel hatten, zum Zeitpunkt der Auslieferung Ihrer App schon weiterentwickelt. Sie könnten also zu spät kommen, unabhängig davon, wie gut die Anwendung konstruiert oder entwickelt wurde. Möglicherweise wird es ein Fehlschlag, oder Sie schaffen es nicht, Ihr vollständiges Potenzial auszuschöpfen, weil Sie die App-Lieferung nicht mit den Anforderungen des Markt synchronisieren können.

Die Notwendigkeit kontinuierlicher geschäftlicher Innovationen bringt Entwicklungs- und Betriebsteams an ihre Grenzen. Der einzige Weg, die Flexibilität zu erreichen, die Sie für kontinuierliche Geschäftsinnovationen benötigen, ist die Modernisierung Ihrer Anwendungen durch Technologien wie Container und spezifische cloudoptimierte Anwendungsprinzipien.

Das Fazit hieraus ist, dass ein Unternehmen, wenn es Anwendungen entwickelt und verwaltet, die cloudoptimiert sind, Lösungen früher in die Hände der Kunden legen und neue Ideen auf den Markt bringen kann, wenn sie relevant sind.

## <a name="cloud-optimized-application-principles-and-tenets"></a>Cloudoptimierte Anwendungsprinzipien und -grundsätze

Verbesserungen in der Cloud konzentrieren sich größtenteils auf die Erfüllung zweier Ziele: Senken von Kosten und Steigern des Geschäftswachstums durch Verbessern der Flexibilität. Diese Ziele werden erreicht, indem Prozesse vereinfacht und Reibung verringert wird, wenn Sie Anwendungen freigeben und ausliefern.

Ihre Anwendung ist cloudoptimiert, wenn Sie Ihre App auf agile Weise autonom gegenüber anderen lokalen Apps entwickeln und dann in der Cloud veröffentlichen, bereitstellen, automatisch skalieren, überwachen und Probleme damit beheben können.

Der Schlüssel hierbei ist *Agilität* (Flexibilität). Sie können nur agil ausliefern, wenn Sie jegliche Probleme bei der Produktionsbereitstellung und der Entwicklungs-/Testumgebung auf ein absolutes Minimum reduzieren. Container (insbesondere Docker als de facto Standard) und verwaltete Dienste wurden speziell für diesen Zweck entwickelt.

Um Agilität zu erreichen, benötigen Sie außerdem automatisierte DevOps-Prozesse, die auf CI/CD-Pipelines basieren, die auf skalierbaren Plattformen in der Cloud freigeben. CI/CD-Plattformen (wie Azure DevOps Services oder Jenkins), die auf einer skalierbaren und robusten Cloudplattform (wie Azure App Service oder Azure Kubernetes Service) bereitstellen, sind die wichtigsten Technologien zur Erzielung von Agilität in der Cloud.

In der folgenden Liste werden die wichtigsten Grundsätze oder Methoden für cloudoptimierte Anwendungen beschrieben. Beachten Sie, dass Sie alle oder nur einige dieser Prinzipien in einem progressiven oder inkrementellen Ansatz übernehmen können:

- **Container:** Container bieten Ihnen die Möglichkeit, Anwendungsabhängigkeiten mit der Anwendung selbst einzuschließen. Containerisierung reduziert die Anzahl von Problemen signifikant, die auftreten können, wenn Sie in Produktionsumgebungen bereitstellen oder in Stagingumgebungen testen. Letztendlich verbessern Container die Agilität der Anwendungsauslieferung.

- **Robuste und skalierbare Cloud**. Die Cloud bietet eine Plattform, die verwaltet, elastisch, skalierbar und robust ist. Diese Eigenschaften sind von grundlegender Bedeutung, um Kostenverbesserungen zu erzielen und hoch verfügbare und zuverlässige Anwendungen im Rahmen von Continuous Delivery zu liefern. Verwaltete Dienste wie verwaltete Datenbanken, verwalteter Cache-as-a-Service (CaaS) und verwalteter Speicher sind grundlegende Bausteine bei der Senkung der Wartungskosten Ihrer Anwendung.

- **Überwachung:** Sie können keine zuverlässige Anwendung haben, ohne eine gute Möglichkeit zu besitzen, um Ausnahmen und Probleme bei der Anwendungsleistung zu erkennen und zu diagnostizieren. Sie müssen umsetzbare Erkenntnisse mittels Verwaltung der Anwendungsleistung und Sofortanalysen gewinnen.

- **DevOps-Kultur und Continuous Delivery**. Die Übernahme von DevOps-Methoden erfordert eine Änderung in der Teamkultur dahingehend, dass Teams nicht mehr in unabhängigen Silos arbeiten. CI/CD-Pipelines sind nur möglich, wenn es eine gesteigerte Zusammenarbeit zwischen Entwicklungs- und IT-Betriebsteams gibt, die von Containern und CI/CD-Tools unterstützt werden.

In Abbildung 4-2 werden die wesentlichen optionalen Säulen einer cloudoptimierten Anwendung veranschaulicht. Je mehr Säulen Sie implementieren, desto besser ist Ihre Anwendung vorbereitet, um die Erwartungen Ihrer Kunden zu erfüllen.

![Diagramm, in dem die wesentlichen Säulen einer cloudoptimierten Anwendung benannt werden.](./media/main-pillars-cloud-optimized-application.png)

**Abbildung 4-2**. Wesentliche Säulen einer cloudoptimierten Anwendung

Zusammenfassend lässt sich sagen, dass eine cloudoptimierte Anwendung einen Ansatz zum Entwickeln und Verwalten von Anwendungen darstellt, der das Cloud Computing-Modell ausnutzt und gleichzeitig eine Kombination aus Containern, verwalteter Cloudinfrastruktur, robusten Anwendungsmethoden, Überwachung, Continuous Delivery und DevOps verwendet, ohne dass Ihre vorhandenen Anwendungen neu entworfen und neu programmiert werden müssen.

In Ihrer Organisation können diese Technologien und Ansätze schrittweise übernommen werden. Sie müssen weder alle noch alle gleichzeitig berücksichtigen. Sie können Sie inkrementell übernehmen, abhängig von den Prioritäten und Benutzeranforderungen Ihres Unternehmens.

## <a name="benefits-of-a-cloud-optimized-application"></a>Vorteile einer cloudoptimierten Anwendung

Sie kommen in den Genuss der folgenden Vorteile, wenn Sie eine vorhandene Anwendung in eine cloudoptimierte Anwendung (ohne Neuentwurf oder Neuprogrammierung) umwandeln:

- **Niedrigere Kosten, da die verwaltete Infrastruktur vom Cloudanbieter versorgt wird**. Cloudoptimierte Anwendungen profitieren von den Vorteilen der Cloud, indem sie die bereits vorhandene Elastizität, automatische Skalierbarkeit und Hochverfügbarkeit der Cloud nutzen. Vorteile stehen nicht nur mit den Computefunktionen (VMs und Container) in Zusammenhang, sondern hängen auch von den Ressourcen in der Cloud ab, wie DBaaS, CaaS und jegliche Infrastruktur, die eine Anwendung möglicherweise benötigt.

- **Robuste Anwendung und Infrastruktur**. Wenn Sie zur Cloud migrieren, müssen Sie vorübergehende Ausfälle in Kauf nehmen – Ausfälle, die in der Cloud auftreten. Außerdem sind Cloudinfrastruktur und -hardware „austauschbar“, wodurch sich Möglichkeiten für vorübergehende Ausfallzeiten erhöhen. Gleichzeitig erleichtern die inneren Cloudfunktionen und bestimmte Anwendungsentwicklungsverfahren, die Resilienz implementieren und die Wiederherstellung automatisieren, Ihnen die Wiederherstellung nach unerwarteten Ausfällen in der Cloud erheblich.

- **Tiefere Erkenntnisse über die Anwendungsleistung**. Cloudüberwachungstools wie Azure Application Insights bieten eine Visualisierungen für die Integritätsverwaltung, Protokollierung und Benachrichtigungen. Überwachungsprotokolle erleichtern das Debuggen und Überwachen von Anwendungen, was für eine zuverlässige Cloudanwendung von grundlegender Bedeutung ist.

- **Anwendungsportabilität bei agilen Bereitstellungen**. Container (entweder Linux- oder Windows-Container auf Basis der Docker-Engine) bieten die beste Lösung, um eine in der Cloud gesperrte Anwendung zu vermeiden. Mithilfe von Containern, Docker-Hosts und Multi-Cloud-Orchestratoren können Sie problemlos von einer Umgebung oder Cloud zu einer anderen wechseln. Container beseitigen die Reibung, die in der Regel in Bereitstellungen in einer beliebigen Umgebung (Stage/Test/Produktion) auftritt.

Alle diese Vorteile bieten letztendlich wichtige Kosteneinsparungen für Ihren End-to-End-Anwendungslebenszyklus.

In den folgenden Abschnitten werden diese Vorteile ausführlicher erläutert und mit bestimmten Technologien verknüpft.

>[!div class="step-by-step"]
>[Zurück](index.md)
>[Weiter](microsoft-technologies-in-cloud-optimized-applications.md)
