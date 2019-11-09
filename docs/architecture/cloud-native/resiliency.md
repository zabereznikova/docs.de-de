---
title: Cloudbasierte Resilienz
description: Architektur von Cloud Native .net-apps für Azure | Native Cloud-Resilienz
ms.date: 06/30/2019
ms.openlocfilehash: 680542abc5d8c43c577321d5ae834f0a13290da3
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2019
ms.locfileid: "73841042"
---
# <a name="cloud-native-resiliency"></a>Cloudbasierte Resilienz

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Resilienz ist die Fähigkeit Ihres Systems, auf Fehler zu reagieren, und bleibt weiterhin funktionsfähig. Es geht nicht um das Vermeiden von Fehlern. Es ist jedoch zu akzeptieren, dass ein Fehler in cloudbasierten Systemen unvermeidlich ist, und die Anwendung so zu entwickeln, dass Sie darauf antwortet. Das Ziel der Resilienz besteht darin, die Anwendung nach einem Fehler wieder in einen voll funktionsfähigen Zustand zu bringen.

Im Gegensatz zu herkömmlichen monolithischen Anwendungen, bei denen alles in einem einzelnen Prozess ausgeführt wird, nutzen cloudnative Systeme die verteilte Architektur, wie in Abbildung 6-1 dargestellt:

![Verteilte, cloudbasierte Umgebung](./media/distributed-cloud-native-environment.png)

**Abbildung 6–1**. Verteilte, cloudbasierte Umgebung

Beachten Sie in der obigen Abbildung, wie jeder Client, der-Dienst und der cloudbasierte [Unterstützungsdienst](https://12factor.net/backing-services) als separater Prozess ausgeführt wird, der auf verschiedenen Servern ausgeführt wird und alle über netzwerkbasierte Aufrufe kommuniziert.

Was könnte also schief gehen?

- Unerwartete [Netzwerk Latenz](https://www.techopedia.com/definition/8553/network-latency).
- [Vorübergehende Fehler](https://docs.microsoft.com/azure/architecture/best-practices/transient-faults) (temporäre Netzwerkkonnektivitätsprobleme).
- Blockierung durch einen synchronen Vorgang mit langer Laufzeit.
- Ein Host Prozess, der abgestürzt ist und neu gestartet oder verschoben wird.
- Ein überladener-mikrodienst, der für kurze Zeit nicht antworten kann.
- Ein aktiver devops-Vorgang, z. b. ein Aktualisierungs-oder Skalierungs Vorgang.
- Ein Orchestrator-Vorgang, z. b. das Verschieben eines Dienstes von einem Knoten zu einem anderen.
- Hardwarefehler von der Ware Hardware.

Bei der Bereitstellung verteilter Dienste in einer cloudbasierten Infrastruktur werden die Faktoren aus der vorherigen Liste sehr real, und Sie müssen für Sie in der Praxis einen Architekten entwickeln und entwickeln.

Bei einem kleinen verteilten System ist der Ausfall seltener, aber wenn das System horizontal hoch-und herunterskaliert wird, können Sie davon ausgehen, dass Sie mehr von diesen Problemen bis zu einem Punkt erleben, an dem Teil Fehler normal werden.

Daher müssen Ihre Anwendung und Infrastruktur robust sein. In den folgenden Abschnitten werden die Verteidigungstechniken erläutert, die Sie Ihrer Anwendung hinzufügen können, sowie integrierte cloudanwendungen, die Sie nutzen können, um die Benutzeroberflächen zu unterstützen.

>[!div class="step-by-step"]
>[Zurück](azure-data-storage.md)
>[Weiter](application-resiliency-patterns.md)
