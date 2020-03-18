---
title: Was ist Apache Spark?
description: Erfahren Sie etwas über Apache Spark in Big Data-Szenarien.
ms.date: 10/15/2019
ms.topic: conceptual
ms.custom: mvc
ms.openlocfilehash: 653f355d09a045feabb3dee0f5737cb691cf2dc4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "73458178"
---
# <a name="what-is-apache-spark"></a>Was ist Apache Spark?

[Apache Spark](https://spark.apache.org/) ist ein Open-Source-Framework für die Parallelverarbeitung, das die arbeitsspeicherinterne Verarbeitung unterstützt, um die Leistung von Anwendungen zur Big Data-Analyse zu steigern. Big Data-Lösungen sind so konzipiert, dass sie Daten verarbeiten können, die für herkömmliche Datenbanken zu groß oder zu komplex sind. Spark verarbeitet große Datenmengen im Arbeitsspeicher, da dies eine erheblich höhere Geschwindigkeit als datenträgerbasierte Alternativen bietet.

## <a name="common-big-data-scenarios"></a>Allgemeine Big Data-Szenarien

Sie sollten eine Big Data-Architektur in Erwägung ziehen, wenn Sie große Datenmengen speichern und verarbeiten, unstrukturierte Daten transformieren oder Streamingdaten verarbeiten müssen. Bei Spark handelt es sich um eine allgemeine verteilte Verarbeitungs-Engine, die für verschiedene Big Data-Szenarien verwendet werden kann.

### <a name="extract-transform-and-load-etl"></a>Extrahieren, Transformieren und Laden (ETL)

Beim [Extrahieren, Transformieren und Laden (ETL)](/azure/architecture/data-guide/relational-data/etl) handelt es sich um den Prozess des Erfassens von Daten aus einer oder mehreren Quellen, das Ändern der Daten und das Verschieben der Daten in einen neuen Datenspeicher. Es gibt mehrere Möglichkeiten zum Transformieren von Daten, darunter:

* Filterung
* Sortieren
* Aggregieren
* Verknüpfen
* Bereinigen
* Deduplizieren
* Die Überprüfen erfolgt.

### <a name="real-time-data-stream-processing"></a>Verarbeiten von Datenströmen in Echtzeit

Streaming- oder Echtzeitdaten sind Daten in Bewegung. Telemetriedaten von IoT-Geräten, Weblogs und Clickstreams sind Beispiele für Streamingdaten. Durch die Verarbeitung von Echtzeitdaten können nützliche Informationen gewonnen werden, z. B. für georäumliche Analysen, Remoteüberwachung und Anomalieerkennung. Ebenso wie bei relationalen Daten können Sie Streamingdaten filtern, aggregieren und vorbereiten, bevor Sie die Daten in eine Ausgabesenke verschieben. Apache Spark unterstützt die [Echtzeitverarbeitung von Datenströmen](/azure/architecture/data-guide/big-data/real-time-processing) über [Spark Streaming](https://spark.apache.org/streaming/).

### <a name="batch-processing"></a>Batchverarbeitung

[Batchverarbeitung](/azure/architecture/data-guide/big-data/batch-processing) stellt die Verarbeitung von ruhenden Big Data-Daten dar. Sie können sehr große Datasets filtern, aggregieren und vorbereiten, indem Sie Aufträge mit langer Ausführungszeit parallel ausführen.

### <a name="machine-learning-through-mllib"></a>Maschinelles Lernen über MLlib

Maschinelles Lernen wird für komplexere Analyseprobleme verwendet. Ihr Computer kann vorhandene Daten verwenden, um zukünftiges Verhalten, Ergebnisse und Trends vorherzusagen. Die Bibliothek für maschinelles Lernen von Apache Spark, [MLlib](https://spark.apache.org/mllib/), enthält mehrere Algorithmen und Hilfsprogramme für maschinelles Lernen.

### <a name="graph-processing-through-graphx"></a>Graphverarbeitung über GraphX

Ein Graph ist eine Sammlung von Knoten, die über Edges verbunden sind. Sie können eine Graphdatenbank verwenden, wenn Sie über hierarchische Daten oder Daten mit verbundenen Beziehungen verfügen. Sie können diese Daten mithilfe der [GraphX-](https://spark.apache.org/graphx/)-API von Apache Spark verarbeiten.

### <a name="sql-and-structured-data-processing-with-spark-sql"></a>Verarbeiten von SQL- und strukturierten Daten mit Spark SQL

Wenn Sie mit strukturierten (formatierten) Daten arbeiten, können Sie über [Spark SQL](https://spark.apache.org/sql/) in Ihrer Spark-Anwendung SQL-Abfragen verwenden.

## <a name="apache-spark-architecture"></a>Architektur von Apache Spark

Apache Spark nutzt eine Architektur aus Master und Workern mit drei Hauptkomponenten: Treiber, Executors und Cluster-Manager.

![Architektur von Apache Spark](media/spark-architecture.png)

### <a name="driver"></a>Treiber

Der Treiber besteht aus Ihrem Programm (z. B. einer C#-Konsolen-App) und einer Spark-Sitzung. Die Spark-Sitzung übernimmt das Programm und teilt es in kleinere Aufgaben auf, die von den Executors verarbeitet werden.

### <a name="executors"></a>Ausführer

Jeder Executor (oder Workerknoten) empfängt eine Aufgabe vom Treiber und führt diese aus. Die Executors befinden sich in einer Entität, die als Cluster bezeichnet wird.

### <a name="cluster-manager"></a>Cluster-Manager

Der Cluster-Manager kommuniziert sowohl mit dem Treiber als den Executors, um folgende Aktionen auszuführen:

* Verwalten der Ressourcenzuordnung
* Verwalten der Programmaufteilung
* Verwalten der Programmausführung

## <a name="language-support"></a>Sprachunterstützung

Die folgenden Programmiersprachen werden von Apache Spark unterstützt:

* Scala
* Python
* Java
* SQL
* R
* .NET

## <a name="spark-apis"></a>Spark-APIs

Apache Spark unterstützt die folgenden APIs:

* [Spark Scala-API](https://spark.apache.org/docs/2.2.0/api/scala/index.html)
* [Spark Java-API](https://spark.apache.org/docs/2.2.0/api/java/index.html)
* [Spark Python-API](https://spark.apache.org/docs/2.2.0/api/python/index.html)
* [Spark R-API](https://spark.apache.org/docs/2.2.0/api/R/index.html)
* [Spark SQL](https://spark.apache.org/docs/latest/api/sql/index.html), integrierte Funktionen

## <a name="next-steps"></a>Nächste Schritte

Erfahren Sie, wie Sie Apache Spark in Ihrer .NET-Anwendung verwenden können. Mit .NET für Apache Spark können Entwickler mit .NET-Erfahrung und -Geschäftslogik Big Data-Abfragen in C# und F# schreiben.
> [!div class="nextstepaction"]
> [Was ist .NET für Apache Spark?](what-is-apache-spark-dotnet.md)
