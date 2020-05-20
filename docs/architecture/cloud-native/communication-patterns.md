---
title: Cloudbasierte Kommunikationsmuster
description: Informieren Sie sich über wichtige Probleme bei der Dienst Kommunikation in Cloud-native Anwendungen
author: robvet
ms.date: 05/13/2020
ms.openlocfilehash: 3d678df44b5fef68427846e59f446b7408795625
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614213"
---
# <a name="cloud-native-communication-patterns"></a>Cloudbasierte Kommunikationsmuster

Beim Erstellen eines cloudbasierten Systems wird die Kommunikation zu einer bedeutenden Entwurfs Entscheidung. Wie kommuniziert eine Front-End-Client Anwendung mit einem Back-End-mikroservice? Wie kommunizieren Back-End-mikrodienste miteinander? Welche Prinzipien, Muster und bewährten Methoden müssen bei der Implementierung der Kommunikation in Cloud-native Anwendungen berücksichtigt werden?

## <a name="communication-considerations"></a>Überlegungen zur Kommunikation

In einer monolithischen Anwendung ist die Kommunikation unkompliziert. Die Code Module werden im gleichen ausführbaren Speicherplatz (Prozess) auf einem Server ausgeführt. Diese Vorgehensweise kann sich auf die Leistung auswirken, wenn alles im gemeinsam genutzten Arbeitsspeicher ausgeführt wird. Dies führt jedoch zu einem eng verknüpften Code, der schwer zu warten, zu entwickeln und zu skalieren

Cloud-Native Systeme implementieren eine auf microservices basierende Architektur mit vielen kleinen, unabhängigen microservices. Jeder-mikrodienst wird in einem separaten Prozess ausgeführt und in der Regel in einem Container ausgeführt, der in einem *Cluster*bereitgestellt wird.

Ein Cluster gruppiert einen Pool von virtuellen Computern, um eine hochverfügbare Umgebung zu bilden. Sie werden mit einem Orchestrierungs Tool verwaltet, das für die Bereitstellung und Verwaltung der containerisierten microservices zuständig ist. Abbildung 4-1 zeigt einen [Kubernetes](https://kubernetes.io) -Cluster, der in der Azure-Cloud mit den vollständig verwalteten [Azure Kubernetes-Diensten](https://docs.microsoft.com/azure/aks/intro-kubernetes)bereitgestellt wird.

![Ein Kubernetes-Cluster in Azure](./media/kubernetes-cluster-in-azure.png)

**Abbildung 4-1**. Ein Kubernetes-Cluster in Azure

Im gesamten Cluster kommunizieren die Webdienste über APIs und Messaging Technologien miteinander.

Obwohl Sie viele Vorteile bieten, sind die-Funktionen nicht kostenlos. Lokale Prozess interne Methodenaufrufe zwischen Komponenten werden nun durch Netzwerk Aufrufe ersetzt. Jeder-Dienst muss über ein Netzwerkprotokoll kommunizieren, wodurch die Komplexität Ihres Systems erhöht wird:

- Netzwerk Überlastung, Latenz und vorübergehende Fehler sind ein konstantes Problem.

- Resilienz (d. h. Wiederholungs Versuche für fehlgeschlagene Anforderungen) ist entscheidend.

- Einige Aufrufe müssen [idempotent](https://www.restapitutorial.com/lessons/idempotency.html) sein, um einen konsistenten Zustand zu gewährleisten.

- Jeder-mikrodienst muss Aufrufe authentifizieren und autorisieren.

- Jede Nachricht muss serialisiert und dann deserialisiert werden, was teuer sein kann.

- Die Nachrichten Verschlüsselung/-Entschlüsselung wird wichtig.

Das Buch [.net microservices: Architektur für .NET-Container Anwendungen](https://dotnet.microsoft.com/download/thank-you/microservices-architecture-ebook), die kostenlos von Microsoft zur Verfügung stehen, bietet eine ausführliche Abdeckung der Kommunikationsmuster für microserviceanwendungen. In diesem Kapitel wird eine allgemeine Übersicht über diese Muster sowie die in der Azure-Cloud verfügbaren Implementierungs Optionen bereitgestellt.

In diesem Kapitel befassen wir uns zunächst mit der Kommunikation zwischen Front-End-Anwendungen und Back-End-Webdiensten. Wir sehen uns nun an, dass die Back-End-mikrodienste miteinander kommunizieren. Wir untersuchen die Kommunikationstechnologie "up" und "GrpC". Zum Schluss betrachten wir neue innovative Kommunikationsmuster mithilfe der Service Mesh-Technologie. Wir sehen uns auch an, wie die Azure-Cloud verschiedene Arten von *sicherungsdiensten* zur Unterstützung der cloudbasierten Kommunikation bereitstellt.

>[!div class="step-by-step"]
>[Zurück](other-deployment-options.md)
>[Weiter](front-end-communication.md)
