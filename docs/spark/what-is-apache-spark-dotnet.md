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
# <a name="what-is-net-for-apache-spark"></a><span data-ttu-id="c59ed-103">Was ist .NET für Apache Spark?</span><span class="sxs-lookup"><span data-stu-id="c59ed-103">What is .NET for Apache Spark?</span></span>

<span data-ttu-id="c59ed-104">[Apache Spark](what-is-spark.md) ist eine verteilte Verarbeitungs-Engine, die universell einsetzbar ist und sich für die Analyse großer Datasets eignet, die üblicherweise mehrere Terabyte oder Petabyte umfassen.</span><span class="sxs-lookup"><span data-stu-id="c59ed-104">[Apache Spark](what-is-spark.md) is a general-purpose distributed processing engine for analytics over large data sets - typically terabytes or petabytes of data.</span></span> <span data-ttu-id="c59ed-105">Mit .NET für Apache Spark, der kostenlosen, plattformübergreifenden Open-Source-.NET-Unterstützung für das beliebte Open-Source-Big Data-Analyseframework, können Sie nun Ihren Big Data-Anwendungen die Leistungsfähigkeit von Apache Spark mithilfe von Sprachen hinzufügen, die Sie bereits kennen.</span><span class="sxs-lookup"><span data-stu-id="c59ed-105">With .NET for Apache Spark, the free, open-source, and cross-platform .NET Support for the popular open-source big data analytics framework, you can now add the power of Apache Spark to your big data applications using languages you already know.</span></span>

## <a name="why-choose-net-for-apache-spark"></a><span data-ttu-id="c59ed-106">Gründe für .NET für Apache Spark</span><span class="sxs-lookup"><span data-stu-id="c59ed-106">Why choose .NET for Apache Spark?</span></span>

<span data-ttu-id="c59ed-107">.NET für Apache Spark ermöglicht Entwicklern mit NET-Erfahrung oder einer .NET-Codebasis den Einstieg in die Welt von Big Data-Analysen.</span><span class="sxs-lookup"><span data-stu-id="c59ed-107">.NET for Apache Spark empowers developers with .NET experience or code bases to participate in the world of big data analytics.</span></span> <span data-ttu-id="c59ed-108">.NET für Apache Spark bietet Hochleistungs-APIs für die Verwendung von Spark in C# und F#.</span><span class="sxs-lookup"><span data-stu-id="c59ed-108">.NET for Apache Spark provides high performance APIs for using Spark from C# and F#.</span></span> <span data-ttu-id="c59ed-109">Mit C# und F# erhalten Sie Zugriff auf Folgendes:</span><span class="sxs-lookup"><span data-stu-id="c59ed-109">With C# and F#, you can access:</span></span>

* <span data-ttu-id="c59ed-110">DataFrames und Spark SQL für die Arbeit mit strukturierten Daten</span><span class="sxs-lookup"><span data-stu-id="c59ed-110">DataFrame and SparkSQL for working with structured data.</span></span>
* <span data-ttu-id="c59ed-111">Spark Structured Streaming zum Arbeiten mit Streamingdaten</span><span class="sxs-lookup"><span data-stu-id="c59ed-111">Spark Structured Streaming for working with streaming data.</span></span>
* <span data-ttu-id="c59ed-112">Spark SQL zum Schreiben von Abfragen mit SQL-Syntax</span><span class="sxs-lookup"><span data-stu-id="c59ed-112">Spark SQL for writing queries with SQL syntax.</span></span>
* <span data-ttu-id="c59ed-113">Integration von maschinellem Lernen für schnelleres Trainieren und Vorhersagen (d. h. Verwendung von .NET für Apache Spark zusammen mit [ML.NET](https://dot.net/ml))</span><span class="sxs-lookup"><span data-stu-id="c59ed-113">Machine learning integration for faster training and prediction (that is, use .NET for Apache Spark alongside [ML.NET](https://dot.net/ml)).</span></span>

<span data-ttu-id="c59ed-114">.NET für Apache Spark ist mit .NET Standard kompatibel, einer formalen Spezifikation von .NET-APIs, die in allen .NET-Implementierungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c59ed-114">.NET for Apache Spark is compliant with .NET Standard, a formal specification of .NET APIs that are common across .NET implementations.</span></span> <span data-ttu-id="c59ed-115">Dadurch können Sie .NET für Apache Spark für Ihren .NET-Code verwenden und Ihr Know-how als .NET-Entwickler nutzen sowie Ihren Code und Ihre Bibliotheken weiterverwenden.</span><span class="sxs-lookup"><span data-stu-id="c59ed-115">This means you can use .NET for Apache Spark anywhere you write .NET code allowing you to reuse all the knowledge, skills, code, and libraries you already have as a .NET developer.</span></span>

<span data-ttu-id="c59ed-116">.NET für Apache Spark kann unter Windows, Linux und macOS mit .NET Core ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="c59ed-116">.NET for Apache Spark runs on Windows, Linux, and macOS using .NET Core.</span></span> <span data-ttu-id="c59ed-117">Unter Windows kann .NET für Apache Spark auch mit dem .NET Framework ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="c59ed-117">It also runs on Windows using .NET Framework.</span></span> <span data-ttu-id="c59ed-118">Sie können Ihre Anwendungen mit den Diensten und Plattformen aller großen Cloudanbieter bereitstellen. Dazu gehören Azure HDInsight Spark, Amazon EMR Spark, Azure Databricks und Databricks auf AWS.</span><span class="sxs-lookup"><span data-stu-id="c59ed-118">You can deploy your applications to all major cloud providers including Azure HDInsight Spark, Amazon EMR Spark, Azure Databricks, and Databricks on AWS.</span></span>

## <a name="net-for-apache-spark-architecture"></a><span data-ttu-id="c59ed-119">Architektur von .NET für Apache Spark</span><span class="sxs-lookup"><span data-stu-id="c59ed-119">.NET for Apache Spark architecture</span></span>

<span data-ttu-id="c59ed-120">Die C#-/F#-Sprachbindung für Spark wurde auf einer neuen Spark-Interoperabilitätsebene geschrieben, die eine einfachere Erweiterbarkeit ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="c59ed-120">The C#/ F# language binding to Spark is written on a new Spark interop layer which offers easier extensibility.</span></span> <span data-ttu-id="c59ed-121">Diese neue Ebene der Spark-Interoperabilität wurde anhand bewährter Methoden für die Spracherweiterung geschrieben, Interoperabilität und Leistung zu optimieren.</span><span class="sxs-lookup"><span data-stu-id="c59ed-121">This new layer of Spark interop was written using the best practices for language extension and optimizes for interop and performance.</span></span> <span data-ttu-id="c59ed-122">Langfristig kann diese Erweiterbarkeit für das Hinzufügen von Unterstützung für andere Sprachen in Spark verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c59ed-122">Long term, this extensibility can be used for adding support for other languages in Spark.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c59ed-123">![Architektur von .NET für Apache Spark](media/dotnet-spark-architecture.png)</span><span class="sxs-lookup"><span data-stu-id="c59ed-123">![.NET for Apache Spark architecture](media/dotnet-spark-architecture.png)</span></span>

<span data-ttu-id="c59ed-124">Weitere Informationen zur Interoperabilitätsunterstützung für Spark-Spracherweiterungen finden Sie im [Vorschlag](https://issues.apache.org/jira/browse/SPARK-26257).</span><span class="sxs-lookup"><span data-stu-id="c59ed-124">You can learn about interop support for Spark language extensions from [the proposal](https://issues.apache.org/jira/browse/SPARK-26257).</span></span>

## <a name="net-for-apache-spark-performance"></a><span data-ttu-id="c59ed-125">Leistung von .NET für Apache Spark</span><span class="sxs-lookup"><span data-stu-id="c59ed-125">.NET for Apache Spark performance</span></span>

<span data-ttu-id="c59ed-126">Beim Vergleich mit Python und Scala unter Verwendung der [TPC-H-Benchmarks](http://www.tpc.org/tpch/) ist die Leistung von .NET für Apache Spark in den meisten Fällen gut. Wenn benutzerdefinierte Funktionen besonders wichtig sind, ist die Leistung sogar doppelt so hoch wie bei Python.</span><span class="sxs-lookup"><span data-stu-id="c59ed-126">When compared against Python and Scala using the [TPC-H benchmark](http://www.tpc.org/tpch/), .NET for Apache Spark performs well in most cases and is 2x faster than Python when user-defined function performance is critical.</span></span> <span data-ttu-id="c59ed-127">Die Leistung und Benchmarks werden kontinuierlich verbessert.</span><span class="sxs-lookup"><span data-stu-id="c59ed-127">There is an ongoing effort to improve and benchmark performance.</span></span>

<span data-ttu-id="c59ed-128">Informationen zu eigenen Benchmarktests finden Sie in den verfügbaren Benchmarks auf der [GitHub-Seite für .NET für Apache Spark](https://github.com/dotnet/spark/tree/master/benchmark).</span><span class="sxs-lookup"><span data-stu-id="c59ed-128">To do your own benchmarking, see the benchmarks available on the [.NET for Apache Spark GitHub](https://github.com/dotnet/spark/tree/master/benchmark).</span></span>

## <a name="net-for-apache-spark-roadmap"></a><span data-ttu-id="c59ed-129">Roadmap für .NET für Apache Spark</span><span class="sxs-lookup"><span data-stu-id="c59ed-129">.NET for Apache Spark roadmap</span></span>

<span data-ttu-id="c59ed-130">In der offiziellen [Roadmap für .NET für Apache Spark](https://github.com/dotnet/spark/blob/master/ROADMAP.md) können Sie sich über die kurzfristigen und langfristigen Pläne informieren.</span><span class="sxs-lookup"><span data-stu-id="c59ed-130">Learn about short term and long term plans from the official [.NET for Apache Spark roadmap](https://github.com/dotnet/spark/blob/master/ROADMAP.md).</span></span>

## <a name="net-foundation"></a><span data-ttu-id="c59ed-131">.NET Foundation</span><span class="sxs-lookup"><span data-stu-id="c59ed-131">.NET Foundation</span></span>

<span data-ttu-id="c59ed-132">Das .NET für Apache Spark-Projekt ist Teil der [.NET Foundation](https://www.dotnetfoundation.org/).</span><span class="sxs-lookup"><span data-stu-id="c59ed-132">The .NET for Apache Spark project is part of the [.NET Foundation](https://www.dotnetfoundation.org/).</span></span>

## <a name="contributions"></a><span data-ttu-id="c59ed-133">Beiträge</span><span class="sxs-lookup"><span data-stu-id="c59ed-133">Contributions</span></span>

<span data-ttu-id="c59ed-134">Das Team von .NET für Apache Spark freut sich immer über Beiträge in Form von GitHub-Issues und -Pull Requests.</span><span class="sxs-lookup"><span data-stu-id="c59ed-134">The .NET for Apache Spark team encourages contributions, both GitHub issues and pull requests.</span></span> <span data-ttu-id="c59ed-135">Suchen Sie immer zuerst nach einem bereits [vorhandenen Issue](https://github.com/dotnet/spark/issues),</span><span class="sxs-lookup"><span data-stu-id="c59ed-135">First, look for an [existing issue](https://github.com/dotnet/spark/issues).</span></span> <span data-ttu-id="c59ed-136">bevor Sie ein [neues Issue](https://github.com/dotnet/spark/issues?utf8=%E2%9C%93&q=is%3Aissue+is%3Aopen+) erstellen.</span><span class="sxs-lookup"><span data-stu-id="c59ed-136">If you can't find an existing issue, [open a new issue](https://github.com/dotnet/spark/issues?utf8=%E2%9C%93&q=is%3Aissue+is%3Aopen+).</span></span>

## <a name="next-steps"></a><span data-ttu-id="c59ed-137">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="c59ed-137">Next steps</span></span>

<span data-ttu-id="c59ed-138">Testen Sie .NET für Apache Spark.</span><span class="sxs-lookup"><span data-stu-id="c59ed-138">Try .NET for Apache Spark.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="c59ed-139">Tutorial: Erste Schritte mit .NET für Apache Spark</span><span class="sxs-lookup"><span data-stu-id="c59ed-139">Tutorial: Get started with .NET for Apache Spark</span></span>](./tutorials/get-started.md)
