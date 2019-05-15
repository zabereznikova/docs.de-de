---
title: Architekturansätze - serverlose apps
description: Eine Einführung in die Architektur Ansätzen für das Erstellen von Cloud-basierte unternehmensanwendungen, von N-schichtige Architekturen für die serverlose.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: ee529abd1f6955d4f542464dd9a2380dd663571f
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65638841"
---
# <a name="architecture-approaches"></a>Architekturansätze

Grundlegendes zu vorhandenen Ansätze zum Entwerfen von Unternehmens-apps unterstützt, die serverlose Rolle erhalten. Es gibt viele Ansätze und Muster, die sich über mehrere Jahrzehnte bei der Softwareentwicklung entwickelt, und alle haben ihre eigenen vor- und Nachteile. In vielen Fällen die ultimative Lösung kann nicht auf einem einzigen Ansatz entscheiden, umfassen aber möglicherweise mehrere Ansätze integrieren. Migrationsszenarien ist häufig die Umstellung von einem Architekturkonzept, zu einem anderen über ein Hybridansatz erforderlich.

In diesem Kapitel bietet eine Übersicht über beide Muster für die logische und physische Architektur für unternehmensanwendungen.

## <a name="architecture-patterns"></a>Architekturmuster

Moderne Geschäftsanwendungen führen Sie eine Vielzahl von Architekturmuster. Dieser Abschnitt stellt eine Umfrage für allgemeine Muster dar. Die Muster, die hier aufgeführten werden nicht unbedingt alle bewährten Methoden, aber unterschiedliche Ansätze zu veranschaulichen.

Weitere Informationen finden Sie unter [Azure-anwendungsarchitekturleitfaden](https://docs.microsoft.com/azure/architecture/guide/).

## <a name="monoliths"></a>Mehr als Monolithen entwickelt

Viele Geschäftsanwendungen folgen einem Muster für die monolithische Anwendung. Legacy-Anwendungen werden häufig als "Monolithen" implementiert. In der monolithischen Anwendung-Muster sind alle Aspekte der Anwendung in einer einzelnen Bereitstellung enthalten. Angefangen bei der Benutzeroberfläche für die Datenbankaufrufe ist in der gleichen Codebasis enthalten.

![Architektur der monolithischen Anwendung](./media/monolith-architecture.png)

Es gibt mehrere Vorteile, die mit dem monolithischen Ansatz. Häufig ist es einfach zu einer einzigen Codebasis abrufen und mit der Arbeit beginnen. Zeit kann geringer sein, und Erstellen von testumgebungen ist so einfach wie eine neue Kopie bereitstellen. Sollen mehrere Komponenten und Anwendungen, kann die monolithische Anwendung entworfen werden.

Leider die monolithische Anwendung Muster nach Maß zu unterteilen. Gravierenden Nachteile des monolithischen Ansatzes gehören:

* Schwierige parallel in derselben Codebasis arbeiten.
* Alle Änderungen, unabhängig davon, wie einfach ist, muss eine neue Version der gesamten Anwendung bereitgestellt werden.
* Refactoring potenziell wirkt sich auf die gesamte Anwendung aus.
* Die einzige Lösung für die Skalierung häufig ist die Erstellung mehrerer mit großem Ressourcenaufwand Kopien auf die monolithische Anwendung.
* Integration kann schwierig sein, wie Systeme erweitern oder zu anderen Systemen werden abgerufen.
* Es kann schwierig zu testen aufgrund müssen so konfigurieren Sie die gesamte monolithische Anwendung sein.
* Wiederverwendung von Code ist eine Herausforderung darstellen, und andere apps dem mitunter wieder müssen ihre eigenen Kopien von Code.

Viele Unternehmen suchen Sie in der Cloud als eine Möglichkeit zum Migrieren von monolithischen Anwendungen, und wandeln Sie sie gleichzeitig auf mehrere-Muster, verwendet werden. Es ist üblich, die sich die einzelnen Anwendungen und Komponenten, um verwaltet, bereitgestellt und separat skaliert werden zu können.

## <a name="n-layer-applications"></a>N-Schicht-Anwendungen

Anwendung Partition Anwendungslogik in bestimmten Ebenen. Die am häufigsten verwendeten Ebenen sind:

* Benutzeroberfläche
* Geschäftslogik
* Datenzugriff

Andere Ebenen können Middleware, Batchverarbeitung und API enthalten. Es ist wichtig zu beachten, dass die Schichten logisch sind. Obwohl sie isoliert entwickelt haben, können sie alle der gleichen Zielplattform bereitgestellt werden.

![N-Schichten-Architektur](./media/n-layer-architecture.png)

Es gibt mehrere Vorteile, die mit dem Ansatz mit N-Ebene, einschließlich:

* Refactoring wird isoliert auf einer Ebene.
* Teams können unabhängig voneinander erstellen, testen, bereitstellen und Verwalten der verschiedenen Schichten.
* Ebenen können ausgelagert werden, z. B. möglicherweise die Datenschicht mehrere Datenbanken zugreifen, ohne dass Änderungen an der UI-Ebene.

Serverless kann verwendet werden, um eine oder mehrere Ebenen zu implementieren.

## <a name="microservices"></a>Microservices

**[Microservices](https://docs.microsoft.com/azure/architecture/guide/architecture-styles/microservices)**  Architekturen enthalten die allgemeinen Merkmale, die enthalten:

* Anwendungen bestehen aus mehreren kleinen Diensten.
* Jeder Dienst wird in einem eigenen Prozess ausgeführt.
* Dienste werden rund um Geschäftsbereichen ausgerichtet.
* Dienste kommunizieren über einfache APIs, die in der Regel mithilfe von HTTP als Transport.
* Dienste können bereitgestellt und unabhängig voneinander aktualisiert werden.
* Dienste stehen keinen einzigen Datenspeicher abhängt.
* Das System wurde entworfen, mit einem Fehler, denken Sie daran, und die app kann weiterhin ausgeführt, selbst wenn bestimmte Dienste nicht.

Microservices müssen nicht mit anderen Ansätzen Architektur sich gegenseitig ausschließende sein. Beispielsweise kann eine N-schichtige Architektur Microservices für die mittlere Ebene verwenden. Es ist auch möglich, in einer Vielzahl von Möglichkeiten, von der virtuellen Verzeichnisse auf dem IIS-Hosts für Container Microservices zu implementieren. Merkmale von Microservices stellen sie vor allem ideal für serverlose Implementierungen.

![Microservicearchitektur](./media/microservices-architecture.png)

Vorteile der Microservices-Architekturen umfassen:

* Refactoring ist häufig auf einen einzelnen Dienst.
* Dienste können unabhängig voneinander aktualisiert werden.
* Flexibilität und Elastizität können die Anforderungen der einzelnen Dienste optimiert werden.
* Entwicklung möglich parallel auf verschiedenen Teams und Plattformen.
* Es ist einfacher, umfassende Tests für isolierte Dienste zu schreiben.

Microservices verfügen über eigene Herausforderungen, darunter:

* Bestimmen, welche Dienste verfügbar sind und wie sie aufgerufen.
* Der Lebenszyklus der Dienste zu verwalten.
* Verstehen, wie Dienste in der gesamten Anwendung miteinander verbunden sind.
* Vollständige systemüberprüfung der Aufrufe für verschiedene Dienste zu testen.

Letzten Endes sind Lösungen, behandeln all diese Herausforderungen, einschließlich der auf der die Vorteile des serverlosen, die weiter unten erläutert werden.

>[!div class="step-by-step"]
>[Zurück](index.md)
>[Weiter](architecture-deployment-approaches.md)
