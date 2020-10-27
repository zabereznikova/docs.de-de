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
# <a name="connect-net-for-apache-spark-to-azure-event-hubs"></a>Herstellen einer Verbindung zwischen .NET für Apache Spark und Azure Event Hubs

In diesem Artikel erfahren Sie, wie Sie eine Verbindung Ihrer [.NET für Apache Spark](https://github.com/dotnet/spark)-Anwendung mit Azure Event Hubs herstellen, um Lese- und Schreibvorgänge für Apache Kafka-Streams durchzuführen.

## <a name="prerequisites"></a>Voraussetzungen

Sie benötigen einen einsatzbereiten Event Hubs-Namespace mit Event Hub. Eine detaillierte Anleitung finden Sie unter [Schnellstart: Erstellen eines Event Hubs mithilfe des Azure-Portals](/azure/event-hubs/event-hubs-create). Achten Sie darauf, den Tarif „Standard“ auszuwählen, wenn Sie den Event Hub-Namespace erstellen.

## <a name="what-is-azure-event-hubs"></a>Was sind Azure Event Hubs?

Bei [Azure Event Hubs](/azure/event-hubs/event-hubs-about) handelt es sich um eine Big-Data-Streamingplattform und einen Ereigniserfassungsdienst. Es handelt sich zudem um ein vollständig verwaltetes PaaS-Angebot (Platform-as-a-Service), das einfach mit [Apache Kafka](https://kafka.apache.org/) integriert werden kann, sodass Sie PaaS-Funktionen von Kafka nutzen können, ohne eigene Cluster verwalten, konfigurieren oder ausführen zu müssen.

## <a name="connect-your-application-to-azure-event-hubs"></a>Herstellen einer Verbindung zwischen Ihrer Anwendung und Azure Event Hubs

1. Rufen Sie die Event Hubs-Verbindungszeichenfolge und den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) zur späteren Verwendung ab. Anweisungen hierzu finden Sie unter [Get an Event Hubs connection string](/azure/event-hubs/event-hubs-get-connection-string) (Abrufen einer Event Hubs-Verbindungszeichenfolge).
2. Legen Sie die folgenden Konfigurationen mit Angaben zu Ihrem Namespace in Ihrem Code fest, um Lesevorgänge für Event Hubs für Kafka zu starten:
    1. Aktualisieren Sie **BOOTSTRAP_SERVERS** und **EH_SASL** in Ihrer Anwendung folgendermaßen:

    ```csharp
    string BOOTSTRAP_SERVERS = "hostname:9093"; // 9093 is the port used to communicate with Event Hubs, see [troubleshooting guide](https://docs.microsoft.com/azure/event-hubs/troubleshooting-guide)
    string EH_SASL = "org.apache.kafka.common.security.plain.PlainLoginModule required username=\"$ConnectionString\" password=\"<CONNECTION_STRING>\";"; // Connection string obtained from Step 1
    ```

## <a name="read-from-azure-event-hub-stream"></a>Lesevorgänge für Event-Hub-Streams in Azure

Sie können nun das Streaming mit Event Hubs genauso starten wie mit Kafka. Unten sehen Sie Beispielcode:

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

## <a name="write-to-azure-event-hub-stream"></a>Schreibvorgänge für Event-Hub-Streams in Azure

Wie unten gezeigt wird, können Sie Schreibvorgänge für Event Hubs auf dieselbe Weise durchführen:

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

## <a name="run-your-application"></a>Ausführen der Anwendung

Zum Ausführen Ihrer .NET für Apache Spark-Anwendung definieren Sie das `spark-sql-kafka-0-10`-Modul als Teil der Builddefinition in Ihrem Spark-Projekt mithilfe von `libraryDependency` in `build.sbt` für sbt-Projekte. Für Spark-Umgebungen wie `spark-submit` (oder `spark-shell`) verwenden Sie die Befehlszeilenoption `--packages` wie folgt:

```bash
spark-shell --packages org.apache.spark:spark-sql-kafka-0-10_2.12:2.4.5
```

> [!NOTE]
> Stellen Sie sicher, dass Sie die Paketversion verwenden, die der ausgeführten Version von Spark entspricht.
