---
title: Herstellen einer Verbindung zwischen .NET für Apache Spark und Azure Event Hubs
description: Hier erfahren Sie, wie Sie eine Verbindung zu Azure Event Hubs von einer lokalen .NET für Apache Spark-Instanz herstellen.
ms.author: nidutta
author: Niharikadutta
ms.date: 10/09/2020
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: c8fd10992e63674032af4148e0673a5330d9086c
ms.sourcegitcommit: 67ebdb695fd017d79d9f1f7f35d145042d5a37f7
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/20/2020
ms.locfileid: "92223957"
---
# <a name="connect-net-for-apache-spark-to-azure-event-hubs"></a><span data-ttu-id="38efd-103">Herstellen einer Verbindung zwischen .NET für Apache Spark und Azure Event Hubs</span><span class="sxs-lookup"><span data-stu-id="38efd-103">Connect .NET for Apache Spark to Azure Event Hubs</span></span>

<span data-ttu-id="38efd-104">In diesem Artikel erfahren Sie, wie Sie eine Verbindung Ihrer [.NET für Apache Spark](https://github.com/dotnet/spark)-Anwendung mit Azure Event Hubs herstellen, um Lese- und Schreibvorgänge für Apache Kafka-Streams durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="38efd-104">In this article, you will learn how to connect your [.NET for Apache Spark](https://github.com/dotnet/spark) application with Azure Event Hubs to read and write Apache Kafka streams.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="38efd-105">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="38efd-105">Prerequisites</span></span>

<span data-ttu-id="38efd-106">Sie benötigen einen einsatzbereiten Event Hubs-Namespace mit Event Hub.</span><span class="sxs-lookup"><span data-stu-id="38efd-106">Have an Event Hubs Namespace ready with an event hub.</span></span> <span data-ttu-id="38efd-107">Eine detaillierte Anleitung finden Sie unter [Schnellstart: Erstellen eines Event Hubs mithilfe des Azure-Portals](/azure/event-hubs/event-hubs-create).</span><span class="sxs-lookup"><span data-stu-id="38efd-107">For a step-by-step guide, refer to [Quickstart: Create an event hub using Azure portal](/azure/event-hubs/event-hubs-create).</span></span> <span data-ttu-id="38efd-108">Achten Sie darauf, den Tarif „Standard“ auszuwählen, wenn Sie den Event Hub-Namespace erstellen.</span><span class="sxs-lookup"><span data-stu-id="38efd-108">Make sure to select the Standard Pricing tier while creating the Event Hub Namespace.</span></span>

## <a name="what-is-azure-event-hubs"></a><span data-ttu-id="38efd-109">Was sind Azure Event Hubs?</span><span class="sxs-lookup"><span data-stu-id="38efd-109">What is Azure Event Hubs</span></span>

<span data-ttu-id="38efd-110">Bei [Azure Event Hubs](/azure/event-hubs/event-hubs-about) handelt es sich um eine Big-Data-Streamingplattform und einen Ereigniserfassungsdienst.</span><span class="sxs-lookup"><span data-stu-id="38efd-110">[Azure Event Hubs](/azure/event-hubs/event-hubs-about) is a big-data streaming platform and event-ingestion service.</span></span> <span data-ttu-id="38efd-111">Es handelt sich zudem um ein vollständig verwaltetes PaaS-Angebot (Platform-as-a-Service), das einfach mit [Apache Kafka](https://kafka.apache.org/) integriert werden kann, sodass Sie PaaS-Funktionen von Kafka nutzen können, ohne eigene Cluster verwalten, konfigurieren oder ausführen zu müssen.</span><span class="sxs-lookup"><span data-stu-id="38efd-111">It is a fully managed Platform-as-a-Service (PaaS) that can easily integrate with [Apache Kafka](https://kafka.apache.org/) to give you the PaaS Kafka experience without having to manage, configure, or run your own clusters.</span></span>

## <a name="connect-your-application-to-azure-event-hubs"></a><span data-ttu-id="38efd-112">Herstellen einer Verbindung zwischen Ihrer Anwendung und Azure Event Hubs</span><span class="sxs-lookup"><span data-stu-id="38efd-112">Connect your application to Azure Event Hubs</span></span>

1. <span data-ttu-id="38efd-113">Rufen Sie die Event Hubs-Verbindungszeichenfolge und den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) zur späteren Verwendung ab.</span><span class="sxs-lookup"><span data-stu-id="38efd-113">Get the Event Hubs connection string and fully qualified domain name (FQDN) for later use.</span></span> <span data-ttu-id="38efd-114">Anweisungen hierzu finden Sie unter [Get an Event Hubs connection string](/azure/event-hubs/event-hubs-get-connection-string) (Abrufen einer Event Hubs-Verbindungszeichenfolge).</span><span class="sxs-lookup"><span data-stu-id="38efd-114">For instructions, see [Get an Event Hubs connection string](/azure/event-hubs/event-hubs-get-connection-string).</span></span>
2. <span data-ttu-id="38efd-115">Legen Sie die folgenden Konfigurationen mit Angaben zu Ihrem Namespace in Ihrem Code fest, um Lesevorgänge für Event Hubs für Kafka zu starten:</span><span class="sxs-lookup"><span data-stu-id="38efd-115">Set the following configurations with details from your namespace in your code to start reading from Event Hubs for Kafka:</span></span>
    1. <span data-ttu-id="38efd-116">Aktualisieren Sie **BOOTSTRAP_SERVERS** und **EH_SASL** in Ihrer Anwendung folgendermaßen:</span><span class="sxs-lookup"><span data-stu-id="38efd-116">Update **BOOTSTRAP_SERVERS** and **EH_SASL** in your application like so:</span></span>

    ```csharp
    string BOOTSTRAP_SERVERS = "hostname:9093"; // 9093 is the port used to communicate with Event Hubs, see [troubleshooting guide](https://docs.microsoft.com/azure/event-hubs/troubleshooting-guide)
    string EH_SASL = "org.apache.kafka.common.security.plain.PlainLoginModule required username=\"$ConnectionString\" password=\"<CONNECTION_STRING>\";"; // Connection string obtained from Step 1
    ```

## <a name="read-from-azure-event-hub-stream"></a><span data-ttu-id="38efd-117">Lesevorgänge für Event-Hub-Streams in Azure</span><span class="sxs-lookup"><span data-stu-id="38efd-117">Read from Azure Event Hub stream</span></span>

<span data-ttu-id="38efd-118">Sie können nun das Streaming mit Event Hubs genauso starten wie mit Kafka.</span><span class="sxs-lookup"><span data-stu-id="38efd-118">You can now start streaming with Event Hubs as you would with Kafka.</span></span> <span data-ttu-id="38efd-119">Unten sehen Sie Beispielcode:</span><span class="sxs-lookup"><span data-stu-id="38efd-119">Sample code as shown below:</span></span>

```csharp
SparkSession spark = SparkSession
    .Builder()
    .AppName("Connect Event Hub")
    .GetOrCreate();

DataFrame df = spark
    .ReadStream()
    .Format("kafka")
    .Option("kafka.bootstrap.servers", BOOTSTRAP_SERVERS)
    .Option("subscribe", "spark-test")
    .Option("kafka.sasl.mechanism", "PLAIN")
    .Option("kafka.security.protocol", "SASL_SSL")
    .Option("kafka.sasl.jaas.config", EH_SASL)
    .Option("kafka.request.timeout.ms", "60000")
    .Option("kafka.session.timeout.ms", "60000")
    .Option("failOnDataLoss", "false")
    .Load();

DataFrame dfWrite = df
    .WriteStream()
    .OutputMode("append")
    .Format("console")
    .Start();
```

## <a name="write-to-azure-event-hub-stream"></a><span data-ttu-id="38efd-120">Schreibvorgänge für Event-Hub-Streams in Azure</span><span class="sxs-lookup"><span data-stu-id="38efd-120">Write to Azure Event Hub stream</span></span>

<span data-ttu-id="38efd-121">Wie unten gezeigt wird, können Sie Schreibvorgänge für Event Hubs auf dieselbe Weise durchführen:</span><span class="sxs-lookup"><span data-stu-id="38efd-121">You can also write to Event Hubs in the same way, as shown below:</span></span>

```csharp
// df is the DataFrame to write

df.WriteStream()
    .Format("kafka")
    .Option("topic", topics)
    .Option("kafka.bootstrap.servers", BOOTSTRAP_SERVERS)
    .Option("kafka.sasl.mechanism", "PLAIN")
    .Option("kafka.security.protocol", "SASL_SSL")
    .Option("kafka.sasl.jaas.config", EH_SASL)
    .Option("checkpointLocation", "./checkpoint")
    .Start();
```

## <a name="run-your-application"></a><span data-ttu-id="38efd-122">Ausführen der Anwendung</span><span class="sxs-lookup"><span data-stu-id="38efd-122">Run your application</span></span>

<span data-ttu-id="38efd-123">Zum Ausführen Ihrer .NET für Apache Spark-Anwendung definieren Sie das `spark-sql-kafka-0-10`-Modul als Teil der Builddefinition in Ihrem Spark-Projekt mithilfe von `libraryDependency` in `build.sbt` für sbt-Projekte.</span><span class="sxs-lookup"><span data-stu-id="38efd-123">In order to run your .NET for Apache Spark application, define the `spark-sql-kafka-0-10` module as part of the build definition in your Spark project, using `libraryDependency` in `build.sbt` for sbt projects.</span></span> <span data-ttu-id="38efd-124">Für Spark-Umgebungen wie `spark-submit` (oder `spark-shell`) verwenden Sie die Befehlszeilenoption `--packages` wie folgt:</span><span class="sxs-lookup"><span data-stu-id="38efd-124">For Spark environments such as `spark-submit` (or `spark-shell`), use the `--packages` command-line option like so:</span></span>

```bash
spark-shell --packages org.apache.spark:spark-sql-kafka-0-10_2.12:2.4.5
```

> [!NOTE]
> <span data-ttu-id="38efd-125">Stellen Sie sicher, dass Sie die Paketversion verwenden, die der ausgeführten Version von Spark entspricht.</span><span class="sxs-lookup"><span data-stu-id="38efd-125">Make sure to include the package version in accordance with the version of Spark being run.</span></span>
