---
title: 'Architektur Ansätze: Server Lose apps'
description: Eine Einführung in die Architektur Ansätze zum Entwickeln von cloudbasierten Unternehmensanwendungen, von N-Tier-Architekturen auf Server lose.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: ee529abd1f6955d4f542464dd9a2380dd663571f
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "69577803"
---
# <a name="architecture-approaches"></a>Architekturansätze

Wenn Sie vorhandene Ansätze zum Entwerfen von Unternehmens-apps verstehen, können Sie die von Server losen Spielen ausgegebene Rolle verdeutlichen. Es gibt viele Ansätze und Muster, die sich über Jahrzehnte der Softwareentwicklung entwickelt haben und alle über eigene vor-und Nachteile verfügen. In vielen Fällen ist es bei der Ultimate-Lösung möglicherweise nicht möglich, einen einzelnen Ansatz zu treffen, sondern mehrere Ansätze zu integrieren. Migrationsszenarien umfassen häufig die Umstellung von einem Architekturansatz auf einen anderen durch einen Hybrid Ansatz.

Dieses Kapitel enthält eine Übersicht über logische und physische Architekturmuster für Unternehmensanwendungen.

## <a name="architecture-patterns"></a>Architekturmuster

Moderne Geschäftsanwendungen befolgen eine Vielzahl von Architekturmustern. Dieser Abschnitt stellt eine Übersicht über allgemeine Muster dar. Die hier aufgeführten Muster sind nicht unbedingt alle bewährten Methoden, sondern veranschaulichen verschiedene Ansätze.

Weitere Informationen finden Sie im [Leitfaden zur Azure-Anwendungsarchitektur](https://docs.microsoft.com/azure/architecture/guide/).

## <a name="monoliths"></a>Monolithen

Viele Geschäftsanwendungen folgen einem monolithischen Muster. Legacy Anwendungen werden häufig als Monolithen implementiert. Im monolithischen Muster sind alle Anwendungsprobleme in einer einzelnen Bereitstellung enthalten. Alles von der Benutzeroberfläche bis hin zu Daten Bank aufrufen ist in derselben CodeBase enthalten.

![Monolithische Architektur](./media/monolith-architecture.png)

Der monolithische Ansatz bietet mehrere Vorteile. Häufig ist es einfach, eine einzelne Codebasis abzurufen und mit der Arbeit zu beginnen. Die Anlaufzeit ist möglicherweise geringer, und das Erstellen von Testumgebungen ist so einfach wie die Bereitstellung einer neuen Kopie. Die monolithische Komponente kann mehrere Komponenten und Anwendungen enthalten.

Leider wird das monolithische Muster tendenziell bei der Skalierung unterbrechen. Zu den wichtigsten Nachteilen des monolithischen Ansatzes gehören:

* Es ist schwierig, parallel in der gleichen Codebasis zu arbeiten.
* Jede Änderung, unabhängig von der Bedeutung, erfordert die Bereitstellung einer neuen Version der gesamten Anwendung.
* Das Refactoring wirkt sich potenziell auf die gesamte Anwendung aus.
* Häufig ist die einzige Lösung, die skaliert werden kann, das Erstellen mehrerer, ressourcenintensiver Kopien der monolithischen.
* Wenn Systeme erweitert oder andere Systeme bezogen werden, kann die Integration schwierig sein.
* Das Testen ist möglicherweise schwierig, da die gesamte monolithische Konfiguration konfiguriert werden muss.
* Die Wiederverwendung von Code ist schwierig, und häufig verfügen andere apps über eigene Code Kopien.

Viele Unternehmen betrachten die Cloud als Gelegenheit zum Migrieren von monolithischen Anwendungen und gestalten Sie gleichzeitig in nützlicheren Mustern um. Es ist üblich, die einzelnen Anwendungen und Komponenten auszuteilen, damit Sie getrennt verwaltet, bereitgestellt und skaliert werden können.

## <a name="n-layer-applications"></a>N-Schicht-Anwendungen

N-schichtige Anwendung partitioniert Anwendungslogik in bestimmte Ebenen. Zu den gängigsten Ebenen gehören:

* Benutzeroberfläche
* Geschäftslogik
* Datenzugriff

Andere Ebenen können Middleware, Batch Verarbeitung und API enthalten. Beachten Sie unbedingt, dass die Ebenen logisch sind. Obwohl Sie isoliert entwickelt wurden, können Sie alle auf der gleichen Zielplattform bereitgestellt werden.

![N-Ebenen-Architektur](./media/n-layer-architecture.png)

Es gibt mehrere Vorteile des N-Ebenen-Ansatzes, einschließlich:

* Refactoring ist auf eine Ebene isoliert.
* Teams können separate Ebenen unabhängig erstellen, testen, bereitstellen und warten.
* Ebenen können ausgetauscht werden, z. b. kann die Datenschicht auf mehrere Datenbanken zugreifen, ohne dass Änderungen an der UI-Schicht erforderlich sind.

Serverless kann verwendet werden, um eine oder mehrere Ebenen zu implementieren.

## <a name="microservices"></a>Microservices

**[Microservicesarchitekturen](https://docs.microsoft.com/azure/architecture/guide/architecture-styles/microservices)** enthalten allgemeine Merkmale, die Folgendes umfassen:

* Anwendungen bestehen aus mehreren kleinen Diensten.
* Jeder Dienst wird in einem eigenen Prozess ausgeführt.
* Dienste werden um Geschäfts Domänen ausgerichtet.
* Dienste kommunizieren über Lightweight-APIs, wobei in der Regel HTTP als Transport verwendet wird.
* Dienste können unabhängig bereitgestellt und aktualisiert werden.
* Dienste sind nicht von einem einzelnen Datenspeicher abhängig.
* Das System ist mit einem Fehler zu tun, und die APP wird möglicherweise weiterhin ausgeführt, auch wenn bestimmte Dienste fehlschlagen.

Microservices müssen sich nicht gegenseitig mit anderen Architektur Ansätzen ausschließen. Beispielsweise kann eine N-Tier-Architektur microservices für die mittlere Ebene verwenden. Es ist auch möglich, auf unterschiedlichste Weise auf der Grundlage von virtuellen Verzeichnissen auf IIS-Hosts in Containern zu implementieren. Die Merkmale von-Diensten machen Sie besonders ideal für Server lose Implementierungen.

![Microservicearchitektur](./media/microservices-architecture.png)

Zu den Profis von microservices-Architekturen gehören:

* Refactoring ist häufig in einem einzelnen Dienst isoliert.
* Dienste können unabhängig voneinander aktualisiert werden.
* Resilienz und Elastizität können auf die Anforderungen einzelner Dienste abgestimmt werden.
* Die Entwicklung kann auf verschiedenen Teams und Plattformen parallel erfolgen.
* Es ist einfacher, umfassende Tests für isolierte Dienste zu schreiben.

Bei der Verwendung von-Diensten gibt es auch die folgenden Herausforderungen:

* Es wird ermittelt, welche Dienste verfügbar sind und wie Sie aufgerufen werden.
* Verwalten des Lebenszyklus von Diensten.
* Es wird erläutert, wie Dienste in der gesamten Anwendung miteinander verknüpft werden.
* Vollständige Systemtests von aufrufen, die über verschiedene Dienste durchgeführt werden.

Letztendlich gibt es Lösungen, um all diese Herausforderungen zu meistern, einschließlich der Vorteile von Server losen, die später besprochen werden.

>[!div class="step-by-step"]
>[Zurück](index.md)
>[Weiter](architecture-deployment-approaches.md)
