---
title: Was ist Apache Spark?
description: Erfahren Sie etwas über Apache Spark in Big Data-Szenarien.
ms.date: 10/15/2019
ms.topic: conceptual
ms.custom: mvc
ms.openlocfilehash: 653f355d09a045feabb3dee0f5737cb691cf2dc4
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458178"
---
# <a name="what-is-apache-spark"></a><span data-ttu-id="f878e-103">Was ist Apache Spark?</span><span class="sxs-lookup"><span data-stu-id="f878e-103">What is Apache Spark?</span></span>

<span data-ttu-id="f878e-104">[Apache Spark](https://spark.apache.org/) ist ein Open-Source-Framework für die Parallelverarbeitung, das die arbeitsspeicherinterne Verarbeitung unterstützt, um die Leistung von Anwendungen zur Big Data-Analyse zu steigern.</span><span class="sxs-lookup"><span data-stu-id="f878e-104">[Apache Spark](https://spark.apache.org/) is an open-source parallel processing framework that supports in-memory processing to boost the performance of applications that analyze big data.</span></span> <span data-ttu-id="f878e-105">Big Data-Lösungen sind so konzipiert, dass sie Daten verarbeiten können, die für herkömmliche Datenbanken zu groß oder zu komplex sind.</span><span class="sxs-lookup"><span data-stu-id="f878e-105">Big data solutions are designed to handle data that is too large or complex for traditional databases.</span></span> <span data-ttu-id="f878e-106">Spark verarbeitet große Datenmengen im Arbeitsspeicher, da dies eine erheblich höhere Geschwindigkeit als datenträgerbasierte Alternativen bietet.</span><span class="sxs-lookup"><span data-stu-id="f878e-106">Spark processes large amounts of data in memory, which is much faster than disk-based alternatives.</span></span>

## <a name="common-big-data-scenarios"></a><span data-ttu-id="f878e-107">Allgemeine Big Data-Szenarien</span><span class="sxs-lookup"><span data-stu-id="f878e-107">Common big data scenarios</span></span>

<span data-ttu-id="f878e-108">Sie sollten eine Big Data-Architektur in Erwägung ziehen, wenn Sie große Datenmengen speichern und verarbeiten, unstrukturierte Daten transformieren oder Streamingdaten verarbeiten müssen.</span><span class="sxs-lookup"><span data-stu-id="f878e-108">You might consider a big data architecture if you need to store and process large volumes of data, transform unstructured data, or processes streaming data.</span></span> <span data-ttu-id="f878e-109">Bei Spark handelt es sich um eine allgemeine verteilte Verarbeitungs-Engine, die für verschiedene Big Data-Szenarien verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="f878e-109">Spark is a general-purpose distributed processing engine that can be used for several big data scenarios.</span></span>

### <a name="extract-transform-and-load-etl"></a><span data-ttu-id="f878e-110">Extrahieren, Transformieren und Laden (ETL)</span><span class="sxs-lookup"><span data-stu-id="f878e-110">Extract, transform, and load (ETL)</span></span>

<span data-ttu-id="f878e-111">Beim [Extrahieren, Transformieren und Laden (ETL)](/azure/architecture/data-guide/relational-data/etl) handelt es sich um den Prozess des Erfassens von Daten aus einer oder mehreren Quellen, das Ändern der Daten und das Verschieben der Daten in einen neuen Datenspeicher.</span><span class="sxs-lookup"><span data-stu-id="f878e-111">[Extract, transform, and load (ETL)](/azure/architecture/data-guide/relational-data/etl) is the process of collecting data from one or multiple sources, modifying the data, and moving the data to a new data store.</span></span> <span data-ttu-id="f878e-112">Es gibt mehrere Möglichkeiten zum Transformieren von Daten, darunter:</span><span class="sxs-lookup"><span data-stu-id="f878e-112">There are several ways to transform data, including:</span></span>

* <span data-ttu-id="f878e-113">Filtern</span><span class="sxs-lookup"><span data-stu-id="f878e-113">Filtering</span></span>
* <span data-ttu-id="f878e-114">Sortieren</span><span class="sxs-lookup"><span data-stu-id="f878e-114">Sorting</span></span>
* <span data-ttu-id="f878e-115">Aggregieren</span><span class="sxs-lookup"><span data-stu-id="f878e-115">Aggregating</span></span>
* <span data-ttu-id="f878e-116">Verknüpfen</span><span class="sxs-lookup"><span data-stu-id="f878e-116">Joining</span></span>
* <span data-ttu-id="f878e-117">Bereinigen</span><span class="sxs-lookup"><span data-stu-id="f878e-117">Cleaning</span></span>
* <span data-ttu-id="f878e-118">Deduplizieren</span><span class="sxs-lookup"><span data-stu-id="f878e-118">Deduplicating</span></span>
* <span data-ttu-id="f878e-119">Die Überprüfen erfolgt.</span><span class="sxs-lookup"><span data-stu-id="f878e-119">Validating</span></span>

### <a name="real-time-data-stream-processing"></a><span data-ttu-id="f878e-120">Verarbeiten von Datenströmen in Echtzeit</span><span class="sxs-lookup"><span data-stu-id="f878e-120">Real-time data stream processing</span></span>

<span data-ttu-id="f878e-121">Streaming- oder Echtzeitdaten sind Daten in Bewegung.</span><span class="sxs-lookup"><span data-stu-id="f878e-121">Streaming, or real-time, data is data in motion.</span></span> <span data-ttu-id="f878e-122">Telemetriedaten von IoT-Geräten, Weblogs und Clickstreams sind Beispiele für Streamingdaten.</span><span class="sxs-lookup"><span data-stu-id="f878e-122">Telemetry from IoT devices, weblogs, and clickstreams are all examples of streaming data.</span></span> <span data-ttu-id="f878e-123">Durch die Verarbeitung von Echtzeitdaten können nützliche Informationen gewonnen werden, z. B. für georäumliche Analysen, Remoteüberwachung und Anomalieerkennung.</span><span class="sxs-lookup"><span data-stu-id="f878e-123">Real-time data can be processed to provide useful information, such as geospatial analysis, remote monitoring, and anomaly detection.</span></span> <span data-ttu-id="f878e-124">Ebenso wie bei relationalen Daten können Sie Streamingdaten filtern, aggregieren und vorbereiten, bevor Sie die Daten in eine Ausgabesenke verschieben.</span><span class="sxs-lookup"><span data-stu-id="f878e-124">Just like relational data, you can filter, aggregate, and prepare streaming data before moving the data to an output sink.</span></span> <span data-ttu-id="f878e-125">Apache Spark unterstützt die [Echtzeitverarbeitung von Datenströmen](/azure/architecture/data-guide/big-data/real-time-processing) über [Spark Streaming](https://spark.apache.org/streaming/).</span><span class="sxs-lookup"><span data-stu-id="f878e-125">Apache Spark supports [real-time data stream processing](/azure/architecture/data-guide/big-data/real-time-processing) through [Spark Streaming](https://spark.apache.org/streaming/).</span></span>

### <a name="batch-processing"></a><span data-ttu-id="f878e-126">Batchverarbeitung</span><span class="sxs-lookup"><span data-stu-id="f878e-126">Batch processing</span></span>

<span data-ttu-id="f878e-127">[Batchverarbeitung](/azure/architecture/data-guide/big-data/batch-processing) stellt die Verarbeitung von ruhenden Big Data-Daten dar.</span><span class="sxs-lookup"><span data-stu-id="f878e-127">[Batch processing](/azure/architecture/data-guide/big-data/batch-processing) is the processing of big data at rest.</span></span> <span data-ttu-id="f878e-128">Sie können sehr große Datasets filtern, aggregieren und vorbereiten, indem Sie Aufträge mit langer Ausführungszeit parallel ausführen.</span><span class="sxs-lookup"><span data-stu-id="f878e-128">You can filter, aggregate, and prepare very large datasets using long-running jobs in parallel.</span></span>

### <a name="machine-learning-through-mllib"></a><span data-ttu-id="f878e-129">Maschinelles Lernen über MLlib</span><span class="sxs-lookup"><span data-stu-id="f878e-129">Machine learning through MLlib</span></span>

<span data-ttu-id="f878e-130">Maschinelles Lernen wird für komplexere Analyseprobleme verwendet.</span><span class="sxs-lookup"><span data-stu-id="f878e-130">Machine learning is used for advanced analytical problems.</span></span> <span data-ttu-id="f878e-131">Ihr Computer kann vorhandene Daten verwenden, um zukünftiges Verhalten, Ergebnisse und Trends vorherzusagen.</span><span class="sxs-lookup"><span data-stu-id="f878e-131">Your computer can use existing data to forecast or predict future behaviors, outcomes, and trends.</span></span> <span data-ttu-id="f878e-132">Die Bibliothek für maschinelles Lernen von Apache Spark, [MLlib](https://spark.apache.org/mllib/), enthält mehrere Algorithmen und Hilfsprogramme für maschinelles Lernen.</span><span class="sxs-lookup"><span data-stu-id="f878e-132">Apache Spark's machine learning library, [MLlib](https://spark.apache.org/mllib/), contains several machine learning algorithms and utilities.</span></span>

### <a name="graph-processing-through-graphx"></a><span data-ttu-id="f878e-133">Graphverarbeitung über GraphX</span><span class="sxs-lookup"><span data-stu-id="f878e-133">Graph processing through GraphX</span></span>

<span data-ttu-id="f878e-134">Ein Graph ist eine Sammlung von Knoten, die über Edges verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="f878e-134">A graph is a collection of nodes connected by edges.</span></span> <span data-ttu-id="f878e-135">Sie können eine Graphdatenbank verwenden, wenn Sie über hierarchische Daten oder Daten mit verbundenen Beziehungen verfügen.</span><span class="sxs-lookup"><span data-stu-id="f878e-135">You might use a graph database if you have hierarchial data or data with interconnected relationships.</span></span> <span data-ttu-id="f878e-136">Sie können diese Daten mithilfe der [GraphX-](https://spark.apache.org/graphx/)-API von Apache Spark verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="f878e-136">You can process this data using Apache Spark's [GraphX](https://spark.apache.org/graphx/) API.</span></span>

### <a name="sql-and-structured-data-processing-with-spark-sql"></a><span data-ttu-id="f878e-137">Verarbeiten von SQL- und strukturierten Daten mit Spark SQL</span><span class="sxs-lookup"><span data-stu-id="f878e-137">SQL and structured data processing with Spark SQL</span></span>

<span data-ttu-id="f878e-138">Wenn Sie mit strukturierten (formatierten) Daten arbeiten, können Sie über [Spark SQL](https://spark.apache.org/sql/) in Ihrer Spark-Anwendung SQL-Abfragen verwenden.</span><span class="sxs-lookup"><span data-stu-id="f878e-138">If you're working with structured (formatted) data, you can use SQL queries in your Spark application using [Spark SQL](https://spark.apache.org/sql/).</span></span>

## <a name="apache-spark-architecture"></a><span data-ttu-id="f878e-139">Architektur von Apache Spark</span><span class="sxs-lookup"><span data-stu-id="f878e-139">Apache Spark architecture</span></span>

<span data-ttu-id="f878e-140">Apache Spark nutzt eine Architektur aus Master und Workern mit drei Hauptkomponenten: Treiber, Executors und Cluster-Manager.</span><span class="sxs-lookup"><span data-stu-id="f878e-140">Apache Spark, which uses the master/worker architecture, has three main components: the driver, executors, and cluster manager.</span></span>

![Architektur von Apache Spark](media/spark-architecture.png)

### <a name="driver"></a><span data-ttu-id="f878e-142">Treiber</span><span class="sxs-lookup"><span data-stu-id="f878e-142">Driver</span></span>

<span data-ttu-id="f878e-143">Der Treiber besteht aus Ihrem Programm (z. B. einer C#-Konsolen-App) und einer Spark-Sitzung.</span><span class="sxs-lookup"><span data-stu-id="f878e-143">The driver consists of your program, like a C# console app, and a Spark session.</span></span> <span data-ttu-id="f878e-144">Die Spark-Sitzung übernimmt das Programm und teilt es in kleinere Aufgaben auf, die von den Executors verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="f878e-144">The Spark session takes your program and divides it into smaller tasks that are handled by the executors.</span></span>

### <a name="executors"></a><span data-ttu-id="f878e-145">Ausführer</span><span class="sxs-lookup"><span data-stu-id="f878e-145">Executors</span></span>

<span data-ttu-id="f878e-146">Jeder Executor (oder Workerknoten) empfängt eine Aufgabe vom Treiber und führt diese aus.</span><span class="sxs-lookup"><span data-stu-id="f878e-146">Each executor, or worker node, receives a task from the driver and executes that task.</span></span> <span data-ttu-id="f878e-147">Die Executors befinden sich in einer Entität, die als Cluster bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="f878e-147">The executors reside on an entity known as a cluster.</span></span>

### <a name="cluster-manager"></a><span data-ttu-id="f878e-148">Cluster-Manager</span><span class="sxs-lookup"><span data-stu-id="f878e-148">Cluster manager</span></span>

<span data-ttu-id="f878e-149">Der Cluster-Manager kommuniziert sowohl mit dem Treiber als den Executors, um folgende Aktionen auszuführen:</span><span class="sxs-lookup"><span data-stu-id="f878e-149">The cluster manager communicates with both the driver and the executors to:</span></span>

* <span data-ttu-id="f878e-150">Verwalten der Ressourcenzuordnung</span><span class="sxs-lookup"><span data-stu-id="f878e-150">Manage resource allocation</span></span>
* <span data-ttu-id="f878e-151">Verwalten der Programmaufteilung</span><span class="sxs-lookup"><span data-stu-id="f878e-151">Manage program division</span></span>
* <span data-ttu-id="f878e-152">Verwalten der Programmausführung</span><span class="sxs-lookup"><span data-stu-id="f878e-152">Manage program execution</span></span>

## <a name="language-support"></a><span data-ttu-id="f878e-153">Sprachenunterstützung</span><span class="sxs-lookup"><span data-stu-id="f878e-153">Language support</span></span>

<span data-ttu-id="f878e-154">Die folgenden Programmiersprachen werden von Apache Spark unterstützt:</span><span class="sxs-lookup"><span data-stu-id="f878e-154">Apache Spark supports the following programming languages:</span></span>

* <span data-ttu-id="f878e-155">Scala</span><span class="sxs-lookup"><span data-stu-id="f878e-155">Scala</span></span>
* <span data-ttu-id="f878e-156">Python</span><span class="sxs-lookup"><span data-stu-id="f878e-156">Python</span></span>
* <span data-ttu-id="f878e-157">Java</span><span class="sxs-lookup"><span data-stu-id="f878e-157">Java</span></span>
* <span data-ttu-id="f878e-158">SQL</span><span class="sxs-lookup"><span data-stu-id="f878e-158">SQL</span></span>
* <span data-ttu-id="f878e-159">R</span><span class="sxs-lookup"><span data-stu-id="f878e-159">R</span></span>
* <span data-ttu-id="f878e-160">.NET</span><span class="sxs-lookup"><span data-stu-id="f878e-160">.NET</span></span>

## <a name="spark-apis"></a><span data-ttu-id="f878e-161">Spark-APIs</span><span class="sxs-lookup"><span data-stu-id="f878e-161">Spark APIs</span></span>

<span data-ttu-id="f878e-162">Apache Spark unterstützt die folgenden APIs:</span><span class="sxs-lookup"><span data-stu-id="f878e-162">Apache Spark supports the following APIs:</span></span>

* [<span data-ttu-id="f878e-163">Spark Scala-API</span><span class="sxs-lookup"><span data-stu-id="f878e-163">Spark Scala API</span></span>](https://spark.apache.org/docs/2.2.0/api/scala/index.html)
* [<span data-ttu-id="f878e-164">Spark Java-API</span><span class="sxs-lookup"><span data-stu-id="f878e-164">Spark Java API</span></span>](https://spark.apache.org/docs/2.2.0/api/java/index.html)
* [<span data-ttu-id="f878e-165">Spark Python-API</span><span class="sxs-lookup"><span data-stu-id="f878e-165">Spark Python API</span></span>](https://spark.apache.org/docs/2.2.0/api/python/index.html)
* [<span data-ttu-id="f878e-166">Spark R-API</span><span class="sxs-lookup"><span data-stu-id="f878e-166">Spark R API</span></span>](https://spark.apache.org/docs/2.2.0/api/R/index.html)
* <span data-ttu-id="f878e-167">[Spark SQL](https://spark.apache.org/docs/latest/api/sql/index.html), integrierte Funktionen</span><span class="sxs-lookup"><span data-stu-id="f878e-167">[Spark SQL](https://spark.apache.org/docs/latest/api/sql/index.html), built-in functions</span></span>

## <a name="next-steps"></a><span data-ttu-id="f878e-168">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="f878e-168">Next steps</span></span>

<span data-ttu-id="f878e-169">Erfahren Sie, wie Sie Apache Spark in Ihrer .NET-Anwendung verwenden können.</span><span class="sxs-lookup"><span data-stu-id="f878e-169">Learn how you can use Apache Spark in your .NET application.</span></span> <span data-ttu-id="f878e-170">Mit .NET für Apache Spark können Entwickler mit .NET-Erfahrung und -Geschäftslogik Big Data-Abfragen in C# und F# schreiben.</span><span class="sxs-lookup"><span data-stu-id="f878e-170">With .NET for Apache Spark, developers with .NET experience and business logic can write big data queries in C# and F#.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="f878e-171">Was ist .NET für Apache Spark?</span><span class="sxs-lookup"><span data-stu-id="f878e-171">What is .NET for Apache Spark</span></span>](what-is-apache-spark-dotnet.md)
