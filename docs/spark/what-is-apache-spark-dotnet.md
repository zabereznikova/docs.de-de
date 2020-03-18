---
title: Was ist .NET für Apache Spark?
description: Erfahren Sie mehr über das kostenlose, plattformübergreifende und für Big Data Analytics geeignete Open-Source-Framework .NET für Apache Spark, mit dem Sie Spark für Ihren .NET-Code verwenden können.
author: mamccrea
ms.topic: overview
ms.date: 10/15/2019
ms.openlocfilehash: 12fccd478cedaccf455043feb3afa7b12221bf0e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "73458201"
---
# <a name="what-is-net-for-apache-spark"></a>Was ist .NET für Apache Spark?

[Apache Spark](what-is-spark.md) ist eine verteilte Verarbeitungs-Engine, die universell einsetzbar ist und sich für die Analyse großer Datasets eignet, die üblicherweise mehrere Terabyte oder Petabyte umfassen. Mit .NET für Apache Spark, der kostenlosen, plattformübergreifenden Open-Source-.NET-Unterstützung für das beliebte Open-Source-Big Data-Analyseframework, können Sie nun Ihren Big Data-Anwendungen die Leistungsfähigkeit von Apache Spark mithilfe von Sprachen hinzufügen, die Sie bereits kennen.

## <a name="why-choose-net-for-apache-spark"></a>Gründe für .NET für Apache Spark

.NET für Apache Spark ermöglicht Entwicklern mit NET-Erfahrung oder einer .NET-Codebasis den Einstieg in die Welt von Big Data-Analysen. .NET für Apache Spark bietet Hochleistungs-APIs für die Verwendung von Spark in C# und F#. Mit C# und F# erhalten Sie Zugriff auf Folgendes:

* DataFrames und Spark SQL für die Arbeit mit strukturierten Daten
* Spark Structured Streaming zum Arbeiten mit Streamingdaten
* Spark SQL zum Schreiben von Abfragen mit SQL-Syntax
* Integration von maschinellem Lernen für schnelleres Trainieren und Vorhersagen (d. h. Verwendung von .NET für Apache Spark zusammen mit [ML.NET](https://dot.net/ml))

.NET für Apache Spark ist mit .NET Standard kompatibel, einer formalen Spezifikation von .NET-APIs, die in allen .NET-Implementierungen verwendet werden. Dadurch können Sie .NET für Apache Spark für Ihren .NET-Code verwenden und Ihr Know-how als .NET-Entwickler nutzen sowie Ihren Code und Ihre Bibliotheken weiterverwenden.

.NET für Apache Spark kann unter Windows, Linux und macOS mit .NET Core ausgeführt werden. Unter Windows kann .NET für Apache Spark auch mit dem .NET Framework ausgeführt werden. Sie können Ihre Anwendungen mit den Diensten und Plattformen aller großen Cloudanbieter bereitstellen. Dazu gehören Azure HDInsight Spark, Amazon EMR Spark, Azure Databricks und Databricks auf AWS.

## <a name="net-for-apache-spark-architecture"></a>Architektur von .NET für Apache Spark

Die C#-/F#-Sprachbindung für Spark wurde auf einer neuen Spark-Interoperabilitätsebene geschrieben, die eine einfachere Erweiterbarkeit ermöglicht. Diese neue Ebene der Spark-Interoperabilität wurde anhand bewährter Methoden für die Spracherweiterung geschrieben, Interoperabilität und Leistung zu optimieren. Langfristig kann diese Erweiterbarkeit für das Hinzufügen von Unterstützung für andere Sprachen in Spark verwendet werden.

> [!div class="mx-imgBorder"]
> ![Architektur von .NET für Apache Spark](media/dotnet-spark-architecture.png)

Weitere Informationen zur Interoperabilitätsunterstützung für Spark-Spracherweiterungen finden Sie im [Vorschlag](https://issues.apache.org/jira/browse/SPARK-26257).

## <a name="net-for-apache-spark-performance"></a>Leistung von .NET für Apache Spark

Beim Vergleich mit Python und Scala unter Verwendung der [TPC-H-Benchmarks](http://www.tpc.org/tpch/) ist die Leistung von .NET für Apache Spark in den meisten Fällen gut. Wenn benutzerdefinierte Funktionen besonders wichtig sind, ist die Leistung sogar doppelt so hoch wie bei Python. Die Leistung und Benchmarks werden kontinuierlich verbessert.

Informationen zu eigenen Benchmarktests finden Sie in den verfügbaren Benchmarks auf der [GitHub-Seite für .NET für Apache Spark](https://github.com/dotnet/spark/tree/master/benchmark).

## <a name="net-for-apache-spark-roadmap"></a>Roadmap für .NET für Apache Spark

In der offiziellen [Roadmap für .NET für Apache Spark](https://github.com/dotnet/spark/blob/master/ROADMAP.md) können Sie sich über die kurzfristigen und langfristigen Pläne informieren.

## <a name="net-foundation"></a>.NET Foundation

Das .NET für Apache Spark-Projekt ist Teil der [.NET Foundation](https://www.dotnetfoundation.org/).

## <a name="contributions"></a>Beiträge

Das Team von .NET für Apache Spark freut sich immer über Beiträge in Form von GitHub-Issues und -Pull Requests. Suchen Sie immer zuerst nach einem bereits [vorhandenen Issue](https://github.com/dotnet/spark/issues), bevor Sie ein [neues Issue](https://github.com/dotnet/spark/issues?utf8=%E2%9C%93&q=is%3Aissue+is%3Aopen+) erstellen.

## <a name="next-steps"></a>Nächste Schritte

Testen Sie .NET für Apache Spark.
> [!div class="nextstepaction"]
> [Tutorial: Erste Schritte mit .NET für Apache Spark](./tutorials/get-started.md)
