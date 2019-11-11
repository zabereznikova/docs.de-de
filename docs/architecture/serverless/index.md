---
title: 'Serverlose Apps: Architektur, Muster und Azure-Implementierung'
description: Leitfaden für die serverlose Architektur Erfahren Sie, wann, warum und wie eine serverlose Architektur (im Gegensatz zu Infrastructure-as-a-Service [IaaS] oder Platform as a Service [PaaS]) für Ihre Unternehmensanwendungen implementiert werden kann.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 9dea7dbccb5c9e125f792e6a7287a7dd2fad26f1
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2019
ms.locfileid: "73093537"
---
# <a name="serverless-apps-architecture-patterns-and-azure-implementation"></a>Serverlose Apps: Architektur, Muster und Azure-Implementierung

![Screenshot: Covers des E-Books „Serverless Apps“ (Serverlose Apps)](./media/index/serverless-apps-cover.jpg)

> DOWNLOAD verfügbar unter: <https://aka.ms/serverless-ebook>

VERÖFFENTLICHT VON

Microsoft Developer Division, .NET- und Visual Studio-Produktteams

Eine Abteilung der Microsoft Corporation

One Microsoft Way

Redmond, Washington 98052-6399

Copyright © 2018 by Microsoft Corporation

Alle Rechte vorbehalten. Die Inhalte dieses Buchs dürfen in keiner Form und für keinen Zweck ohne die schriftliche Genehmigung des Herausgebers reproduziert oder übertragen werden.

Dieses Buch wird unverändert bereitgestellt und drückt die Ansichten und Meinungen des Autors aus. Die Ansichten, Meinungen und Informationen, die in diesem Buch zum Ausdruck gebracht werden, einschließlich URLs und anderer Verweise auf Internetwebsites, können ohne vorherige Ankündigung geändert werden.

Einige der hier dargestellten Beispiele dienen nur zu Illustrationszwecken und sind fiktiv. Keinerlei Zuordnung oder Verbindung zu realen Gegebenheiten ist beabsichtigt oder sollte gefolgert werden.

Microsoft und die auf der Webseite „Marken“ unter <https://www.microsoft.com> aufgelisteten Marken sind Marken der Microsoft-Unternehmensgruppe.

Mac und macOS sind Marken von Apple Inc.

Alle anderen Marken und Logos sind Eigentum der jeweiligen Besitzer.

Autor:

> **[Jeremy Likness](https://twitter.com/jeremylikness)** , Senior Cloud Advocate, Microsoft Corp.

Mitwirkender:

> **[Cecil Phillip](https://twitter.com/cecilphillip)** , Senior Cloud Advocate, Microsoft Corp.

Editoren:

> **[Bill Wagner](https://twitter.com/billwagner)** , Senior Content Developer, Microsoft Corp.

> **[Maira Wenzel](https://twitter.com/mairacw)** , Senior Content Developer, Microsoft Corp.

Teilnehmer und Prüfer:

> **[Steve Smith](https://twitter.com/ardalis)** , Owner, Ardalis Services.

## <a name="introduction"></a>Einführung

Durch die [serverlose Architektur](https://azure.microsoft.com/solutions/serverless/) entwickeln sich Cloudplattformen in Richtung von cloudnativem Code weiter. Dadurch kommen Entwickler der Geschäftslogik näher, während sie diese von Infrastrukturproblemen isolieren. Dieses Muster impliziert nicht, dass kein Server mehr vorhanden ist, sondern dass weniger Server vorhanden sind. Serverloser Code ist ereignisgesteuert. Code kann beispielsweise von einer HTTP-Webanforderung für einen Timer oder vom Ergebnis eines Dateiuploads ausgelöst werden. Mithilfe der serverlosen Architektur kann eine sofortige Skalierung durchgeführt werden, um elastischen Anforderungen nachzukommen. Außerdem bietet sie Microbilling, sodass Sie nur das bezahlen, was Sie auch nutzen. Die serverlose Architektur erfordert eine neue Denkweise und Herangehensweise bei der Anwendungserstellung. Sie ist aber keineswegs die Universallösung für jedes Problem. Als Entwickler müssen Sie Folgendes entscheiden:

- Was sind die Vor- und Nachteile der serverlosen Architektur?
- Warum sollten Sie die serverlose Architektur für Ihre eigenen Anwendungen in Betracht ziehen?
- Wie können Sie Ihren serverlosen Code erstellen, testen, bereitstellen und verwalten?
- Wo ergibt es Sinn, Code in vorhandenen Anwendungen zu einer serverlosen Architektur zu migrieren, und wie können Sie diesen Umstieg am besten durchführen?

## <a name="about-this-guide"></a>Über diesen Leitfaden

Dieser Leitfaden konzentriert sich auf die cloudnative Entwicklung von Anwendungen mit serverloser Architektur. In diesem E-Book wird besonders auf die Vorteile der serverlosen Architektur eingegangen. Gleichzeitig werden aber auch potentielle Nachteile bei der Entwicklung serverloser Apps aufgezeigt und ein Überblick über die serverlose Architektur gegeben. Sie erhalten einen Einblick in Beispiele für die Verwendung der serverlosen Architektur sowie in Entwurfsmuster serverloser Architekturen.

In diesem Leitfaden werden die Komponenten der serverlosen Azure-Plattform erläutert. Dabei liegt der Fokus besonders auf der Implementierung der serverlosen Architektur mithilfe von [Azure Functions](https://docs.microsoft.com/azure/azure-functions/functions-overview). Sie lernen alles zu Triggern und Bindungen und wie serverlose zustandsbehaftete Apps implementiert werden. Zuletzt erhalten Sie durch Beispiele aus dem Geschäftsbereich und durch Fallstudien Bezugspunkte und Kontext, damit Sie bestimmen können, ob die serverlose Architektur der richtige Ansatz für Ihre Projekte ist.

## <a name="evolution-of-cloud-platforms"></a>Entwicklung der Cloudplattformen

Die serverlose Architektur ist der krönende Abschluss der Iterationen von Cloudplattformen. Die Entwicklung begann mit physischen Serverschränken in Rechenzentren und führte dann über IaaS und PaaS hin zur serverlosen Architektur.

![Entwicklung von lokal zu serverlos](./media/serverless-evolution-iaas-paas.png)

Vor der Cloud gab es eine deutliche Grenze zwischen der Entwicklung und dem Betrieb. Die Bereitstellung und Anwendungen erforderten die Beantwortung unzähliger Fragen, wie z.B.:

- Welche Hardware soll installiert werden?
- Wie wird der physische Zugriff auf den Computer geschützt?
- Erfordert das Rechenzentrum eine unterbrechungsfreie Stromversorgung?
- Wohin werden Sicherungskopien des Arbeitsspeichers gesendet?
- Sollte redundante Stromversorgung vorhanden sein?

Das ist nur eine Auswahl der Fragen, die im Vorhinein geklärt werden mussten. Der Aufwand war einfach enorm. IT-Abteilungen mussten oft sehr viel Verschwendung in Kauf nehmen. Diese entstand z.B. durch die Zuweisung von unverhältnismäßig vielen Servern als Sicherungsserver für die Notfallwiederherstellung und als Standbyserver, um die horizontale Skalierung zu ermöglichen. Die Einführung der Virtualisierungstechnologie (z.B. [Hyper-V](/virtualization/hyper-v-on-windows/about/)) mit virtuellen Computern (VMs) hat dann jedoch den Weg für Infrastructure-as-a-Service (IaaS) geebnet. Durch die virtuelle Infrastruktur konnte die Betriebsabteilung Standardserver als Backbone einrichten, wodurch eine flexible Umgebung ermöglicht wurde, die „bedarfsgesteuert“ eindeutige Server bereitstellen konnte. Darüber hinaus war die Virtualisierung die Grundlage für die Verwendung der Cloud und ermöglichte so die Bereitstellung virtueller Computer „as-a-Service“. Unternehmen mussten sich von da an keine Sorgen mehr um die redundante Stromversorgung oder um physische Computer machen. Stattdessen konnten sie sich auf die virtuelle Umgebung konzentrieren.

Für IaaS ist noch immer ein hoher Aufwand erforderlich, da der Betrieb noch immer für unterschiedliche Aufgaben verantwortlich ist. Diese Aufgaben sind:

- Das Patchen und die Sicherungen von Servern
- Das Installieren von Paketen
- Das Betriebssystem auf dem neuesten Stand halten
- Die Überwachung der Anwendung

Im nächsten Schritt wurde der Aufwand durch Bereitstellung von Platform-as-a-Service (PaaS) reduziert. Mit PaaS kann der Cloudanbieter Betriebssysteme, Sicherheitspatches und sogar die erforderlichen Pakete bereistellen, um eine bestimmte Plattform zu unterstützen. Statt der Erstellung einer VM und dem anschließenden Konfigurieren von .NET Framework und der Verwendung der Internetinformationsdienste (IIS) wählen Entwickler ganz einfach ein „Plattformziel“ aus, z.B. „Webanwendung“ oder „API-Endpunkt“, und stellen den Code direkt bereit. Die Fragen zur Infrastruktur sind nun weniger geworden:

- Wie groß müssen die Dienste sein?
- Wie können die Dienste horizontal hochskaliert werden (bzw. wie können mehr Server oder Knoten hinzugefügt werden)?
- Wie werden die Dienste zentral hochskaliert (wie kann die Kapazität von Hostingservern oder -knoten erhöht werden)?

Der serverlose Code abstrahiert die Server weiter durch Konzentration auf den ereignisgesteuerten Code. Statt auf Plattformen können sich Entwickler nun auf einen Microservice konzentrieren, der nur einen Vorgang ausführt. Die beiden wichtigsten Fragen zum Erstellen des serverlosen Codes sind:

- Was löst den Code aus?
- Was macht dieser Code?

Mit serverlosem Code wird die Infrastruktur abstrahiert. In einigen Fällen muss sich der Entwickler überhaupt keine Sorgen mehr über den Host machen. Der Entwickler konzentriert sich auf einen HTTP-Trigger, egal ob für die Verwaltung einer Webanforderungen eine IIS-, Kestrel- oder Apache-Instanz oder ein ganz anderer Webserver ausgeführt wird. Der Trigger stellt die standardmäßige plattformübergreifende Nutzlast für die Anforderung bereit. Die Nutzlast vereinfacht nicht nur den Bereitstellungsvorgang, sondern vereinfacht auch in einigen Fällen das Testen, wodurch Code einfach plattformübergreifend portierbar ist.

Microbilling ist ein weiteres Feature der serverlosen Architektur. Es ist üblich, das Webanwendungen Web-API-Endpunkte hosten. In traditionellen Bare-Metal-, IaaS- und sogar PaaS-Implementierungen werden Ressourcen für das Hosten der API ununterbrochen gezahlt. Das heißt, dass Sie dafür zahlen, die Endpunkte zu hosten, auch wenn gar nicht auf diese zugegriffen wird. Oft wird eine API öfter als andere aufgerufen. Also wird das gesamte System so skaliert, dass es die beliebten Endpunkte unterstützen kann. Durch die serverlose Architektur können Sie jeden Endpunkt unabhängig skalieren, und Sie zahlen nur für das, was Sie benutzen. Es entstehen also keine Kosten, wenn die APIs nicht aufgerufen werden. Eine Migration kann in vielen Situationen die laufenden Kosten für die Endpunktunterstützung erheblich verringern.

## <a name="what-this-guide-doesnt-cover"></a>Was in diesem Leitfaden nicht behandelt wird

In diesem Leitfaden wird auf die Architekturansätze und Entwurfsmuster eingegangen. Er bietet keinen tiefgehenden Einblick in die Implementierungsdetails von Azure Functions, [Logic Apps](https://docs.microsoft.com/azure/logic-apps/logic-apps-what-are-logic-apps) oder von anderen serverlosen Plattformen. Es werden beispielsweise keine erweiterten Workflows mit Logic Apps oder Features von Azure Functions behandelt, wie etwa die Konfiguration von Cross-Origin Resource Sharing (CORS), die Anwendung benutzerdefinierter Domänen oder das Hochladen von SSL-Zertifikaten. Informationen dazu sind online in der [Dokumentation zu Azure Functions](https://docs.microsoft.com/azure/azure-functions/functions-reference) verfügbar.

### <a name="additional-resources"></a>Zusätzliche Ressourcen

- [Azure Architecture Center](https://docs.microsoft.com/azure/architecture/)
- [Bewährte Methode für Cloudanwendungen](https://docs.microsoft.com/azure/architecture/best-practices/api-design)

## <a name="who-should-use-the-guide"></a>Zielgruppe dieses Leitfadens

Dieser Leitfaden wurde für Entwickler und Lösungsarchitekten verfasst, die Unternehmensanwendungen mit .NET erstellen möchten, welche serverlose Komponentenlokal oder in der Cloud verwenden können. Er ist hilfreich für Entwickler, Architekten und technische Entscheidungsträger, die an Folgendem interessiert sind:

- Vor- und Nachteile der serverlosen Entwicklung
- Entwerfen einer serverlosen Architektur
- Beispielimplementierungen von serverlosen Apps

## <a name="how-to-use-the-guide"></a>So verwenden Sie diesen Leitfaden

Der erste Teil dieses Leitfadens befasst sich damit, warum die serverlose Architektur eine sinnvolle Option für Sie darstellen kann, indem mehrere unterschiedliche Architekturansätze miteinander verglichen werden. Es werden jeweils der Technologie- und der Entwicklungslebenszyklus verglichen, da alle Aspekte der Softwareentwicklung von Architekturentscheidungen betroffen sind. Im Leitfaden werden anschließend die Anwendungsfälle und Entwurfsmuster untersucht. Außerdem werden Referenzimplementierungen mit Azure Functions vorgestellt. Jeder Abschnitt enthält zusätzliche Ressourcen, damit Sie mehr zu einem bestimmten Bereich erfahren können. Der Leitfaden endet mit exemplarischen Vorgehensweisen und praktischen Übungen zur serverlosen Implementierung.

## <a name="send-your-feedback"></a>Senden Sie uns Ihr Feedback

Dieser Leitfaden und die dazugehörigen Beispiele werden ständig weiterentwickelt, deshalb freuen wir uns über Ihr Feedback. Wenn Sie Anmerkungen zur Verbesserung dieses Leitfadens haben, nutzen Sie den Feedbackabschnitt, der unten auf jeder Seite zu finden ist und über den [GitHub-Issues](https://github.com/dotnet/docs/issues) erstellt werden.

>[!div class="step-by-step"]
>[Nächste](architecture-approaches.md)
