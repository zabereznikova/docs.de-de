---
title: Debuggen einer .NET für Apache Spark-Anwendung unter Windows
description: Erfahren Sie, wie Sie eine .NET für Apache Spark-Anwendung unter Windows debuggen.
ms.date: 08/15/2019
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: dcaca96f6eb871c15a37adc18190b073c63c8e93
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/31/2019
ms.locfileid: "70206143"
---
# <a name="debug-a-net-for-apache-spark-application"></a>Debuggen einer .NET für Apache Spark-Anwendung

In diesem Tutorial werden die Befehle beschrieben, die Sie zum Debuggen einer .NET für Apache Spark-Anwendung und von Scala-Code unter Windows ausführen müssen.

## <a name="debug-your-application"></a>Debuggen der Anwendung

Öffnen Sie ein neues Eingabeaufforderungsfenster, und führen Sie den folgenden Befehl aus:

```shell
spark-submit \
  --class org.apache.spark.deploy.dotnet.DotnetRunner \
  --master local \
  <path-to-microsoft-spark-jar> \
  debug
```

Beim Ausführen des Befehls wird die folgende Ausgabe angezeigt:

```
***********************************************************************
* .NET Backend running debug mode. Press enter to exit *
***********************************************************************
```

Im Debugmodus wird die .NET-Anwendung nicht von `DotnetRunner` gestartet. Stattdessen wird gewartet, bis eine Verbindung hergestellt wird. Lassen Sie dieses Eingabeaufforderungsfenster geöffnet.

Nun können Sie Ihre .NET-Anwendung mit einem beliebigen Debugger ausführen, um Ihre Anwendung zu debuggen.

## <a name="debug-scala-code"></a>Debuggen von Scala-Code

Wenn Sie beispielsweise Scala-Code in `DotnetRunner` oder `DotnetBackendHandler` debuggen müssen, können Sie den folgenden Befehl verwenden:

```shell
spark-submit \
  --driver-java-options -agentlib:jdwp=transport=dt_socket,server=y,suspend=n,address=5005 \
  --class org.apache.spark.deploy.dotnet.DotnetRunner \
  --master local \
  <path-to-microsoft-spark-jar> \
  <path-to-your-app-exe> <argument(s)-to-your-app>
```

Fügen Sie anschließend mit [IntelliJ](https://www.jetbrains.com/help/idea/attaching-to-local-process.html) dem laufenden Prozess einen Debugger an.

## <a name="next-steps"></a>Nächste Schritte

* [Erste Schritte mit .NET für Apache Spark](../tutorials/get-started.md)
* [Bereitstellen einer .NET für Apache Spark-Anwendung in Azure HDInsight](../tutorials/hdinsight-deployment.md)
* [Bereitstellen einer .NET für Apache Spark-Anwendung in Databricks](../tutorials/databricks-deployment.md)
* [Bereitstellen einer .NET für Apache Spark-Anwendung in Amazon EMR Spark](../tutorials/amazon-emr-spark-deployment.md)
