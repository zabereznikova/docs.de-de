---
title: Zusammenfassung
description: Hier finden Sie eine Zusammenfassung der wichtigsten Schlussfolgerungen aus dem Leitfaden zum Entwerfen von Cloud-Native .net-apps für Azure.
ms.date: 05/13/2020
ms.openlocfilehash: b1a195c0c081565c57f5aac2e234411bb904ca08
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83613654"
---
# <a name="summary"></a>Zusammenfassung

Zusammenfassend sind die folgenden wichtigen Schlussfolgerungen in diesem Handbuch aufgeführt:

- **Cloud-Native** ist das Entwerfen moderner Anwendungen, die eine schnelle Änderung, große Skalierbarkeit und Resilienz in modernen, dynamischen Umgebungen wie öffentlichen, privaten und Hybriden Clouds umfassen.

- Die ** [Cloud Native Computing Foundation](https://www.cncf.io/) (cncf)** ist ein einflussreiches Open-Source-Konsortium von über 300 großen Unternehmen. Er ist dafür verantwortlich, die Übernahme von Cloud-Native Computing über Technologie-und cloudstapel hinweg zu fördern.

- **Cncf-Richtlinien** empfehlen, dass cloudnative Anwendungen sechs wichtige Säulen akzeptieren, wie in Abbildung 11-1 dargestellt:

  ![In der Cloud Native grundlegende Säulen](./media/cloud-native-foundational-pillars.png)

  **Abbildung 11-1**. In der Cloud Native grundlegende Säulen

- Diese cloudbasierten Säulen umfassen Folgendes:
  - Die Cloud und das zugrunde liegende Dienstmodell
  - Moderne Entwurfs Prinzipien
  - Microservices
  - Containerisierung und Container Orchestrierung
  - Cloudbasierte Unterstützungsdienste, z. b. Datenbanken und Nachrichten Broker
  - Automatisierung, einschließlich Infrastruktur als Code und Code Bereitstellung

- **Kubernetes** ist die bevorzugte Hostingumgebung für die meisten cloudbasierten Anwendungen. Kleinere, einfache Dienste werden manchmal auf Server losen Plattformen gehostet, wie z. b. Azure Functions. Bei vielen wichtigen Automatisierungs Features bieten beide Umgebungen eine automatische Skalierung, um schwankende workloadvolumes zu verarbeiten.

- Die **Dienst Kommunikation** wird bei der Erstellung einer Cloud-native Anwendung zu einer erheblichen Entwurfs Entscheidung. Anwendungen stellen in der Regel ein API-Gateway zum Verwalten der Front-End-Client Kommunikation bereit. Die Back-End-mikrodienste sind dann bestrebt, miteinander zu kommunizieren, indem asynchrone Kommunikationsmuster implementiert werden.

- **GrpC** ist ein modernes Hochleistungs Framework, das das alte RPC-Protokoll (Remote Procedure callage) weiterentwickelt. Native Cloud-Anwendungen nutzen häufig GrpC, um das Messaging zwischen Back-End-Diensten zu optimieren. GrpC verwendet http/2 für das Transportprotokoll. Es kann bis zu 8-mal schneller als die JSON-Serialisierung mit Nachrichten Größen von 60-80% kleiner sein. GrpC ist Open Source und wird von der Cloud Native Computing Foundation (cncf) verwaltet.

- **Verteilte Daten** sind ein Modell, das häufig von cloudbasierten Anwendungen implementiert wird. Anwendungen trennen Geschäftsfunktionen in kleine, unabhängige microservices. Jeder microservice kapselt seine eigenen Abhängigkeiten, Daten und seinen Zustand. Das klassische Modell für freigegebene Datenbanken wird zu einer von vielen kleineren Datenbanken weiterentwickelt, die jeweils mit einem-Dienst ausgerichtet sind. Wenn der Rauch gelöscht wird, werden wir einen Entwurf mit einem `database-per-microservice` Modell erstellen.

- **Nein-SQL-Datenbanken** beziehen sich auf nicht relationale Datenspeicher mit hoher Leistung. Sie sind in der Benutzerfreundlichkeit, Skalierbarkeit, Resilienz und Verfügbarkeits Merkmalen von Excel. Hohe Volumen Dienste, die eine Antwortzeit der untergeordneten Sekunde erfordern, bevorzugen nosql-Datenspeicher. Die Verbreitung von nosql-Technologien für verteilte cloudnative Systeme kann nicht überschrieben werden.

- **Newsql** ist eine neue Datenbanktechnologie, die die verteilte Skalierbarkeit von nosql und die Acid-Garantien einer relationalen Datenbank kombiniert. Newsql-Datenbanken sind auf Geschäftssysteme ausgerichtet, die große Mengen von Daten in verteilten Umgebungen mit vollständiger Transaktions-/Acid-Konformität verarbeiten müssen. Die Cloud Native Computing Foundation (cncf) umfasst mehrere newsql-Datenbankprojekte.

- **Resilienz** ist die Fähigkeit Ihres Systems, auf Fehler zu reagieren, und bleibt weiterhin funktionsfähig. Cloud-Native Systeme nutzen eine verteilte Architektur, bei der ein Fehler unvermeidlich ist. Anwendungen müssen so erstellt werden, dass Sie elegant auf Fehler reagieren und schnell zu einem voll funktionsfähigen Status zurückkehren.

- **Dienst-Netzen** sind eine konfigurierbare Infrastruktur Schicht mit integrierten Funktionen, um die Dienst Kommunikation und andere übergreifende Herausforderungen zu bewältigen. Sie entkoppeln die übergreifenden Zuständigkeiten von Ihrem Geschäfts Code. Diese Zuständigkeiten wechseln in einen Dienst Proxy. Wird als bezeichnet `Sidecar pattern` , wird der Proxy in einem separaten Prozess bereitgestellt, um die Isolation von Ihrem Geschäfts Code bereitzustellen.

- **Observability** ist ein wichtiger Entwurfs Aspekt bei der Cloud-native Anwendung. Wenn Dienste auf einen Cluster von Knoten verteilt werden, wird die zentralisierte Protokollierung, Überwachung und Warnungen obligatorisch. Azure Monitor ist eine Sammlung von cloudbasierten Tools, die einen Einblick in den Zustand Ihres Systems bieten.

- **Infrastructure as Code** ist eine weit verbreitete Praxis, die die Platt Form Bereitstellung automatisiert. Ihre Infrastruktur und bereit Stellungen sind automatisiert, konsistent und wiederholbar. Tools wie Azure Resource Manager, TERRAFORM und die Azure CLI ermöglichen es Ihnen, deklarativ Skripts für die erforderliche cloudinfrastruktur zu erstellen.

- Die **Code Automatisierung** ist eine Voraussetzung für Native Cloud-Anwendungen. Moderne CI/CD-Systeme helfen dabei, dieses Prinzip zu erfüllen. Sie bieten separate Build-und Bereitstellungs Schritte, die den konsistenten und qualitativ hochwertigen Code sicherstellen. Die Buildphase wandelt den Code in ein binäres artefaktelement um. Die Releasephase übernimmt das binäre artefaktelement, wendet die Konfiguration der externen Umgebung an und stellt Sie in einer angegebenen Umgebung bereit. Azure devops und GitHub sind voll funktionsfähigen devops-Umgebungen.

>[!div class="step-by-step"]
>[Vorherige](application-bundles.md)
