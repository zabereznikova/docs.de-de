---
title: Serviceorientierte Architektur
description: Lernen Sie die grundlegenden Unterschiede zwischen Microservices und einer serviceorientierten Architektur (SOA) kennen.
ms.date: 09/20/2018
ms.openlocfilehash: 84786539fbac0e8b38a81a2580232474774cd355
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "68674927"
---
# <a name="service-oriented-architecture"></a>Serviceorientierte Architektur

Der Begriff „serviceorientierte Architektur“ (SOA) wurde zu häufig verwendet und hat daher verschiedene Bedeutungen entwickelt. Der gemeinsame Nenner der Bedeutung von „serviceorientierter Architektur“ ist jedoch, dass die Anwendung strukturiert wird, indem sie in mehrere Dienste zerlegt wird (meistens HTTP-Dienste), die als unterschiedliche Typen klassifiziert werden können, z.B. Subsysteme oder Ebenen.

Diese Dienste können nun als Docker-Container bereitgestellt werden. Dadurch werden Bereitstellungsprobleme gelöst, da alle Abhängigkeiten im Containerimage enthalten sind. Wenn Sie jedoch SOA-Anwendungen zentral hochskalieren müssen, können Probleme mit der Skalierbarkeit und Verfügbarkeit auftreten, falls Sie die Bereitstellung auf Grundlage eines einzelnen Docker-Hosts ausführen. Hier kann Sie Docker-Clusteringsoftware oder ein Orchestrator unterstützen. Dies wird in späteren Abschnitten erläutert, die Ansätze zum Bereitstellen von Microservices thematisieren.

Für herkömmliche serviceorientierte Architekturen und erweiterte Microservicesarchitekturen sind Docker-Container nützlich, jedoch nicht erforderlich.

Microservices werden von serviceorientierten Architekturen abgeleitet, die sich jedoch von Microservicesarchitekturen unterscheiden. Features wie große zentrale Broker, zentrale Orchestratoren auf Organisationsebene und der [Enterprise Service Bus (ESB)](https://en.wikipedia.org/wiki/Enterprise_service_bus) sind typisch für serviceorientierte Architekturen. In den meisten Fällen sind diese Muster in der Microservicescommunity jedoch nicht beliebt. Einige Benutzer argumentieren, dass die Microservicearchitektur die optimale Form der serviceorientierten Architektur sei.

Der Schwerpunkt dieses Handbuchs liegt auf Microservices, da der SOA-Ansatz weniger ausführlich als die Anforderungen und Techniken ist, die in Microservicesarchitekturen verwendet werden. Wenn Sie eine auf Microservices basierte Anwendung erstellen können, können Sie ebenfalls eine einfachere, serviceorientierte Anwendung erstellen.

>[!div class="step-by-step"]
>[Zurück](docker-application-state-data.md)
>[Weiter](microservices-architecture.md)
