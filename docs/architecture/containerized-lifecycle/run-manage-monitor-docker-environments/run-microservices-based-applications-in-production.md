---
title: Ausführen von zusammengesetzten und auf Microservices basierenden Anwendungen in Produktionsumgebungen
description: Lernen Sie die wichtigsten Komponenten zum Ausführen containerbasierter Anwendungen in Produktionsumgebungen kennen
ms.date: 02/15/2019
ms.openlocfilehash: 69df3d39a00b91cbe59c96e5fcab841a60943bcc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "68672917"
---
# <a name="run-composed-and-microservices-based-applications-in-production-environments"></a>Ausführen von zusammengesetzten und auf Microservices basierenden Anwendungen in Produktionsumgebungen

Aus mehreren Microservices zusammengesetzte Anwendungen müssen in Orchestratorclustern bereitgestellt werden, um die Komplexität der Bereitstellung zu vereinfachen und aus der IT-Perspektive umsetzbar zu machen. Ohne einen Orchestratorcluster wäre es schwierig, eine komplexe Microserviceanwendung bereitzustellen und zu skalieren.

## <a name="introduction-to-orchestrators-schedulers-and-container-clusters"></a>Einführung in Orchestratoren, Planer und Containercluster

Früher in diesem E-Book wurden *Cluster* und *Planer* im Rahmen der Diskussion zu Softwarearchitektur und Entwicklung eingeführt. Kubernetes und Service Fabric sind Beispiele für Docker-Cluster. Beide Orchestratoren können als Teil der von Microsoft Azure Kubernetes Service bereitgestellten Infrastruktur ausgeführt werden.

Wenn Anwendungen über mehrere Hostsysteme skaliert werden, wird die Möglichkeit attraktiv, jedes Hostsystem zu verwalten und die Komplexität der zugrunde liegenden Plattform durch Abstraktion auszublenden. Das ist genau der Beitrag von Orchestratoren und Planern. Sehen wir sie uns hier kurz an:

- **Planer.** „Planung“ bezeichnet die Möglichkeit eines Administrators, eine Dienstdatei auf ein Hostsystem hochzuladen, die festlegt, wie ein bestimmter Container ausgeführt werden soll. Das Starten von Containern in einem Docker-Cluster wird häufig als „Planung“ bezeichnet. Zwar bezieht sich Planen auf den spezifischen Vorgang des Ladens der Dienstdefinition, in einem allgemeineren Sinn sind Planer aber für das Einhängen in das init-System eines Hosts zuständig, um Dienste in jeder erforderlichen Hinsicht zu verwalten.

   Ein Clusterplaner hat mehrere Ziele: effiziente Verwendung der Clusterressourcen, Arbeiten mit vom Benutzer festgelegten Platzierungseinschränkungen, schnelles Planen von Anwendungen, um sie nicht einem ausstehenden Zustand zu belassen, ein gewisses Maß an „Fairness“ aufzubringen, robust gegenüber Fehlern und immer verfügbar zu sein.

- **Orchestratoren**. Plattformen weiten Funktionen zur Lebenszyklusverwaltung auf komplexe, mehrere Container umfassende Workloads aus, die auf einem Cluster aus Hosts bereitgestellt sind. Durch Abstrahieren der Hostinfrastruktur geben Orchestrierungstools Benutzern die Möglichkeit, den gesamten Cluster als ein einzelnes Bereitstellungsziel zu behandeln.

   Der Prozess der Orchestrierung beinhaltet Tools und eine Plattform, die alle Aspekte der Anwendungsverwaltung umfassen, von der anfänglichen Platzierung oder Bereitstellung pro Container, dem Verschieben von Containern auf andere Hosts abhängig von Status oder Leistung des Hosts, Versionsverwaltung und rollierende Updates bis zu Funktionen zur Integritätsüberwachung, Skalierung und Failover und noch vielem mehr.

   Orchestrierung ist ein breit gefasster Begriff, der sich auf Containerplanung, Clusterverwaltung und möglicherweise die Bereitstellung zusätzlicher Hosts bezieht.

Die von Orchestratoren und Planern bereitgestellten Funktionen sind komplex, wenn sie von Grund auf entwickelt und erstellt werden, daher werden Sie normalerweise von Herstellern angebotene Orchestrierungslösungen verwenden.

>[!div class="step-by-step"]
>[Zurück](index.md)
>[Weiter](manage-production-docker-environments.md)
