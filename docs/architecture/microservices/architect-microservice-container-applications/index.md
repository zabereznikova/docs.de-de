---
title: Architekturentwurf von Container- und auf Microservice basierende Anwendungen
description: Der Architekturentwurf von Container- und Microservice-basierten Anwendungen ist keine Kleinigkeit und sollte nicht auf die leichte Schulter genommen werden. Machen Sie sich in diesem Kapitel mit den Kernkonzepten vertraut.
ms.date: 01/13/2021
ms.openlocfilehash: d87633b6c5073a9098c34c1192bcca1abad00e5c
ms.sourcegitcommit: a4cecb7389f02c27e412b743f9189bd2a6dea4d6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/14/2021
ms.locfileid: "98189485"
---
# <a name="architecting-container-and-microservice-based-applications"></a>Architekturentwurf von Container- und auf Microservice basierende Anwendungen

*Microservices bieten zahlreiche Vorteile, stellen aber auch große neue Herausforderungen dar. Microservice-Architekturmuster sind eine Grundvoraussetzung für das Erstellen einer auf Microservice basierenden Anwendung.*

In diesem Leitfaden haben Sie bereits die grundlegenden Konzepte für Container und Docker gelernt. Dabei handelt es sich um die mindestens erforderlichen Informationen, die Sie für die ersten Schritte mit Containern benötigen. Wenngleich Container nützlich und besonders für Microservices geeignet sind, sind sie für eine Microservicearchitektur nicht erforderlich. Auch viele architektonische Konzepte in diesem Abschnitt zur Architektur können ohne Container angewendet werden. Der Schwerpunkt dieses Leitfadens liegt jedoch auf der Schnittmenge beider Methoden, da die Wichtigkeit der Container bereits eingeführt wurde.

Unternehmensanwendungen können komplex sein. Oft bestehen sie aus mehreren Diensten statt aus einer einzelnen, dienstbasierten Anwendungen. Für diese Fälle müssen Sie mit weiteren architektonischen Ansätzen vertraut sein, z. B. Microservices, bestimmte DDD-Mustern (Domain-Driven Design) und Orchestrierungskonzepten für Container. Beachten Sie, dass dieses Kapitel nicht nur Microservices auf Containern, sondern auch Containeranwendungen beschreibt.

## <a name="container-design-principles"></a>Richtlinien für das Containerdesign

Im Containermodell stellt eine Instanz eines Containerimages einen einzelnen Prozess dar. Indem ein Containerimage als Prozessgrenze definiert wird, können Sie Grundtypen erstellen, die zum Skalieren oder Stapeln des Prozesses verwendet werden können.

Wenn Sie ein Containerimage entworfen haben, wird Ihnen die Definition [ENTRYPOINT](https://docs.docker.com/engine/reference/builder/#entrypoint) in der Dockerfile angezeigt. Mit dieser wird der Prozess definiert, dessen Lebensdauer die Lebensdauer des Containers steuert. Wenn der Prozess abgeschlossen ist, endet der Lebenszyklus des Containers. Container können langlebige Prozesse wie Webserver, aber auch kurzlebige Prozesse wie Batchaufträge (früher als Azure [WebJobs](https://github.com/Azure/azure-webjobs-sdk/wiki) implementiert) darstellen.

Wenn der Prozess fehlschlägt, wird der Container angehalten und der Orchestrator übernimmt seinen Platz. Wenn der Orchestrator dafür konfiguriert wurde, fünf Instanzen auszuführen und eine davon fehlschlägt, erstellt der Orchestrator eine andere Containerinstanz, um den fehlgeschlagenen Prozess zu ersetzen. In einem Batchauftrag wird der Prozess mit Parametern gestartet. Wenn der Prozess abgeschlossen ist, ist die Arbeit abgeschlossen. Dieser Leitfaden geht zu einem späteren Zeitpunkt ausführlich auf Orchestratoren ein.

Es gibt Szenarios, in denen mehrere Prozesse in einem einzigen Container ausgeführt werden sollen. Da es nur einen Einstiegspunkt pro Container geben kann, können Sie für dieses Szenario ein Skript innerhalb des Containers ausführen, das so viele Programme wie benötigt startet. Sie können beispielsweise [Supervisor](http://supervisord.org/) oder ein ähnliches Tool verwenden, um mehrere Prozesse innerhalb eines einzigen Containers zu starten. Auch wenn es Architekturen gibt, die mehrere Prozesse pro Container enthalten können, ist dieser Ansatz eher unüblich.

>[!div class="step-by-step"]
>[Zurück](../net-core-net-framework-containers/official-net-docker-images.md)
>[Weiter](containerize-monolithic-applications.md)
