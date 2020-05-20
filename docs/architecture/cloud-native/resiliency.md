---
title: Cloudbasierte Resilienz
description: Architektur von Cloud Native .net-apps für Azure | Native Cloud-Resilienz
author: robvet
ms.date: 05/13/2020
ms.openlocfilehash: f3aa89e3ae21b13a31f65013b59636b3f931553c
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83613771"
---
# <a name="cloud-native-resiliency"></a>Cloudbasierte Resilienz

Resilienz ist die Fähigkeit Ihres Systems, auf Fehler zu reagieren, und bleibt weiterhin funktionsfähig. Es geht nicht um das Vermeiden von Fehlern, aber das akzeptieren von Fehlern und das Erstellen Ihrer cloudbasierten Dienste, um darauf zu reagieren. Sie möchten schnell wie möglich in den Status "voll funktionsfähig" zurückkehren.

Im Gegensatz zu herkömmlichen monolithischen Anwendungen, bei denen alles in einem einzelnen Prozess ausgeführt wird, nutzen cloudnative Systeme eine verteilte Architektur, wie in Abbildung 6-1 dargestellt:

![Verteilte, cloudbasierte Umgebung](./media/distributed-cloud-native-environment.png)

**Abbildung 6-1.** Verteilte, cloudbasierte Umgebung

In der obigen Abbildung werden die einzelnen und cloudbasierten [Unterstützungsdienste](https://12factor.net/backing-services) in einem separaten Prozess ausgeführt, der über die Serverinfrastruktur hinweg kommuniziert und über netzwerkbasierte Aufrufe kommuniziert.

In dieser Umgebung muss ein Dienst für viele verschiedene Herausforderungen sensibel sein:

- Unerwartete Netzwerk Latenz: die Zeit für die Übertragung einer Service Request zum Empfänger und zurück.

- [Vorübergehende Fehler](https://docs.microsoft.com/azure/architecture/best-practices/transient-faults) : kurzlebige Netzwerkverbindungsfehler.

- Blockage durch einen synchronen Vorgang mit langer Laufzeit.

- Ein Host Prozess, der abgestürzt ist und neu gestartet oder verschoben wird.

- Ein überladener-mikrodienst, der für kurze Zeit nicht antworten kann.

- Einen laufenden Orchestrator-Vorgang, z. b. ein paralleles Upgrade oder das Verschieben eines Dienstanbieter von einem Knoten zu einem anderen.

- Hardware Fehler.

Cloudplattformen können viele dieser Infrastrukturprobleme erkennen und mindern. Der Dienst kann neu gestartet, horizontal hochskaliert und sogar auf einen anderen Knoten verteilt werden.  Um den integrierten Schutz in vollem Umfang nutzen zu können, müssen Sie jedoch ihre Dienste so entwerfen, dass Sie darauf reagieren und in dieser dynamischen Umgebung gedeihen.

In den folgenden Abschnitten werden die von Ihrem Dienst und den verwalteten cloudressourcen verwendeten Verteidigungstechniken erläutert, um Ausfallzeiten und Unterbrechungen zu minimieren.

>[!div class="step-by-step"]
>[Zurück](elastic-search-in-azure.md)
>[Weiter](application-resiliency-patterns.md)
