---
title: 'Architekturansätze: Serverlose Apps'
description: Eine Einführung in Architekturansätze für das Erstellen von cloudbasierten Unternehmensanwendungen, von n-schichtigen Architekturen bis hin zu serverlosen Lösungen.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 74de96bef48f16ced4adf82855a740aa0afcdf1d
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2019
ms.locfileid: "72522898"
---
# <a name="architecture-approaches"></a>Architekturansätze

Das Verständnis vorhandener Ansätze zur Architektur von Unternehmensanwendungen hilft, die Rolle von serverlosen Lösungen zu verdeutlichen. Es gibt viele Ansätze und Muster, die sich über Jahrzehnte der Softwareentwicklung herauskristallisiert haben, und alle haben ihre eigenen Vor- und Nachteile. In vielen Fällen kann die ultimative Lösung nicht darin bestehen, sich für einen einzigen Ansatz zu entscheiden, sondern mehrere Ansätze zu integrieren. Migrationsszenarien beinhalten oft den Wechsel von einem Architekturansatz zu einem anderen mithilfe eines Hybridansatzes.

Dieses Kapitel enthält eine Übersicht über logische und physische Architekturmuster für Unternehmensanwendungen.

## <a name="architecture-patterns"></a>Architekturmuster

Moderne Geschäftsanwendungen folgen einer Vielzahl von Architekturmustern. Dieser Abschnitt bietet eine Übersicht über allgemeine Muster. Die hier aufgeführten Muster sind nicht unbedingt alle bewährten Methoden, veranschaulichen aber verschiedene Ansätze.

Weitere Informationen finden Sie unter [Leitfaden für die Azure-Anwendungsarchitektur](https://docs.microsoft.com/azure/architecture/guide/).

## <a name="monoliths"></a>Monolithische Anwendungen

Viele Geschäftsanwendungen folgen einem monolithischen Muster. Legacyanwendungen werden häufig als monolithische Anwendungen implementiert. Im monolithischen Muster sind alle Anwendungsprobleme in einer einzelnen Bereitstellung enthalten. Alles von der Benutzeroberfläche bis hin zu Datenbankaufrufen ist in derselben Codebasis enthalten.

![Monolithische Architektur](./media/monolith-architecture.png)

Der monolithische Ansatz bietet mehrere Vorteile: Häufig ist es einfach, eine einzelne Codebasis abzurufen und mit der Arbeit zu beginnen. Die Anlaufzeit ist möglicherweise geringer, und das Erstellen von Testumgebungen ist so einfach wie die Bereitstellung einer neuen Kopie. Die monolithische Anwendung kann mehrere Komponenten und Anwendungen enthalten.

Leider versagt das monolithische Muster tendenziell bei der Skalierung. Zu den wichtigsten Nachteilen des monolithischen Ansatzes gehören:

- Es ist schwierig, parallel in der gleichen Codebasis zu arbeiten.
- Jede noch so geringfügige Änderung erfordert die Bereitstellung einer neuen Version der gesamten Anwendung.
- Ein Refactoring wirkt sich potenziell auf die gesamte Anwendung aus.
- Oft ist die einzige Lösung zur Skalierung die Erstellung mehrerer, ressourcenintensiver Kopien der monolithischen Anwendung.
- Wenn Systeme erweitert oder andere Systeme eingesetzt werden, kann die Integration schwierig sein.
- Das Testen ist möglicherweise schwierig, da die gesamte monolithische Anwendung konfiguriert werden muss.
- Die Wiederverwendung von Code stellt eine Herausforderung dar, und häufig verfügen andere Apps letztendlich über eigene Kopien des Codes.

Viele Unternehmen betrachten die Cloud als eine Möglichkeit, monolithische Anwendungen zu migrieren und sie gleichzeitig in besser nutzbare Muster umzugestalten. Es ist üblich, die einzelnen Anwendungen und Komponenten herauszubrechen, damit Sie getrennt verwaltet, bereitgestellt und skaliert werden können.

## <a name="n-layer-applications"></a>N-schichtige Anwendungen

N-schichtige Anwendungen partitionieren Anwendungslogik in bestimmte Schichten. Zu den häufigsten Schichten zählen:

- Benutzeroberfläche
- Geschäftslogik
- Datenzugriff

Andere Schichten können Middleware, Batchverarbeitung und APIs enthalten. Beachten Sie unbedingt, dass die Schichten logisch sind. Obwohl Sie isoliert entwickelt werden, können sie alle auf der gleichen Zielplattform bereitgestellt werden.

![N-schichtige Architektur](./media/n-layer-architecture.png)

Der n-schichtige Ansatz bietet mehrere Vorteile:

- Refactoring ist in einer Schicht isoliert.
- Teams können separate Schichten unabhängig voneinander erstellen, testen, bereitstellen und verwalten.
- Schichten können ausgewechselt werden, z.B. kann die Datenschicht auf mehrere Datenbanken zugreifen, ohne dass Änderungen an der UI-Schicht erforderlich sind.

Das serverlose Modell kann verwendet werden, um mindestens eine Schicht zu implementieren.

## <a name="microservices"></a>Microservices

**[Microservices](https://docs.microsoft.com/azure/architecture/guide/architecture-styles/microservices)** architekturen weisen allgemeine Merkmale auf, z.B. die folgenden:

- Anwendungen bestehen aus mehreren kleinen Diensten.
- Jeder Dienst wird in einem eigenen Prozess ausgeführt.
- Dienste werden auf Geschäftsfelder ausgerichtet.
- Dienste kommunizieren über schlanke APIs, wobei in der Regel HTTP als Transport verwendet wird.
- Dienste können unabhängig voneinander bereitgestellt und aktualisiert werden.
- Dienste sind nicht von einem einzelnen Datenspeicher abhängig.
- Das System ist auf Fehler ausgelegt, und die App kann auch dann noch ausgeführt werden, wenn bestimmte Dienste ausfallen.

Microservices müssen nicht alle anderen Architekturansätze ausschließen. Beispielsweise kann eine n-schichtige Architektur Microservices für die mittlere Schicht verwenden. Es ist auch möglich, Microservices auf verschiedene Weise zu implementieren, von virtuellen Verzeichnissen auf IIS-Hosts bis hin zu Containern. Die Merkmale von Microservices machen sie besonders geeignet für serverlose Implementierungen.

![Microservicearchitektur](./media/microservices-architecture.png)

Zu den Vorteilen von Microservicesarchitekturen gehören:

- Refactoring ist häufig auf einen einzelnen Dienst beschränkt.
- Dienste können unabhängig voneinander aktualisiert werden.
- Resilienz und Elastizität können auf die Anforderungen einzelner Dienste abgestimmt werden.
- Die Entwicklung kann in verschiedenen Teams und auf verschiedenen Plattformen parallel erfolgen.
- Es ist einfacher, umfassende Tests für isolierte Dienste zu schreiben.

Microservices stellen Sie vor ihre eigenen Herausforderungen, darunter:

- Ermitteln, welche Dienste verfügbar sind und wie sie aufgerufen werden.
- Verwalten des Lebenszyklus von Diensten.
- Verstehen, wie Dienste in der Gesamtanwendung zusammenpassen.
- Vollständige Systemtests von Aufrufen, die über verschiedene Dienste erfolgen.

Letztendlich gibt es Lösungen für all diese Herausforderungen, einschließlich der Nutzung der Vorteile von serverlosen Ansätzen, die später behandelt werden.

>[!div class="step-by-step"]
>[Zurück](index.md)
>[Weiter](architecture-deployment-approaches.md)
