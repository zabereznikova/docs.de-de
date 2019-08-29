---
title: Debuggen einer .NET für Apache Spark-Anwendung unter Windows
description: Erfahren Sie, wie Sie eine .NET für Apache Spark-Anwendung unter Windows debuggen.
ms.date: 08/15/2019
ms.topic: how-to
ms.custom: mvc
ms.openlocfilehash: 08142bd45c475ddd131053213ebdea5f843fa736
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/21/2019
ms.locfileid: "69667668"
---
# <a name="debug-a-net-for-apache-spark-application"></a><span data-ttu-id="1777a-103">Debuggen einer .NET für Apache Spark-Anwendung</span><span class="sxs-lookup"><span data-stu-id="1777a-103">Debug a .NET for Apache Spark application</span></span>

<span data-ttu-id="1777a-104">In diesem Tutorial werden die Befehle beschrieben, die Sie zum Debuggen einer .NET für Apache Spark-Anwendung und von Scala-Code unter Windows ausführen müssen.</span><span class="sxs-lookup"><span data-stu-id="1777a-104">This how-to provides the commands you need to run to debug your .NET for Apache Spark application and Scala code on Windows.</span></span>

## <a name="debug-your-application"></a><span data-ttu-id="1777a-105">Debuggen der Anwendung</span><span class="sxs-lookup"><span data-stu-id="1777a-105">Debug your application</span></span>

<span data-ttu-id="1777a-106">Öffnen Sie ein neues Eingabeaufforderungsfenster, und führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="1777a-106">Open a new command prompt window, run the following:</span></span>

```shell
spark-submit \
  --class org.apache.spark.deploy.dotnet.DotnetRunner \
  --master local \
  <path-to-microsoft-spark-jar> \
  debug
```

<span data-ttu-id="1777a-107">Beim Ausführen des Befehls wird die folgende Ausgabe angezeigt:</span><span class="sxs-lookup"><span data-stu-id="1777a-107">When you run the command, you see the following output:</span></span>

```
***********************************************************************
* .NET Backend running debug mode. Press enter to exit *
***********************************************************************
```

<span data-ttu-id="1777a-108">Im Debugmodus wird die .NET-Anwendung nicht von `DotnetRunner` gestartet. Stattdessen wird gewartet, bis eine Verbindung hergestellt wird.</span><span class="sxs-lookup"><span data-stu-id="1777a-108">In this debug mode, `DotnetRunner` does not launch the .NET application, but it waits for it to connect.</span></span> <span data-ttu-id="1777a-109">Lassen Sie dieses Eingabeaufforderungsfenster geöffnet.</span><span class="sxs-lookup"><span data-stu-id="1777a-109">Leave this command prompt window open.</span></span>

<span data-ttu-id="1777a-110">Nun können Sie Ihre .NET-Anwendung mit einem beliebigen Debugger ausführen, um Ihre Anwendung zu debuggen.</span><span class="sxs-lookup"><span data-stu-id="1777a-110">Now you can run your .NET application with any debugger to debug your application.</span></span>

## <a name="debug-scala-code"></a><span data-ttu-id="1777a-111">Debuggen von Scala-Code</span><span class="sxs-lookup"><span data-stu-id="1777a-111">Debug Scala code</span></span>

<span data-ttu-id="1777a-112">Wenn Sie beispielsweise Scala-Code in `DotnetRunner` oder `DotnetBackendHandler` debuggen müssen, können Sie den folgenden Befehl verwenden:</span><span class="sxs-lookup"><span data-stu-id="1777a-112">If you need to debug the Scala side code, such as `DotnetRunner` or `DotnetBackendHandler`, run the following command:</span></span>

```shell
spark-submit \
  --driver-java-options -agentlib:jdwp=transport=dt_socket,server=y,suspend=n,address=5005 \
  --class org.apache.spark.deploy.dotnet.DotnetRunner \
  --master local \
  <path-to-microsoft-spark-jar> \
  <path-to-your-app-exe> <argument(s)-to-your-app>
```

<span data-ttu-id="1777a-113">Fügen Sie anschließend mit [IntelliJ](https://www.jetbrains.com/help/idea/attaching-to-local-process.html) dem laufenden Prozess einen Debugger an.</span><span class="sxs-lookup"><span data-stu-id="1777a-113">After you run the command, attach a debugger to the running process using [Intellij](https://www.jetbrains.com/help/idea/attaching-to-local-process.html).</span></span>

## <a name="next-steps"></a><span data-ttu-id="1777a-114">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="1777a-114">Next steps</span></span>

* [<span data-ttu-id="1777a-115">Erste Schritte mit .NET für Apache Spark</span><span class="sxs-lookup"><span data-stu-id="1777a-115">Get started with .NET for Apache Spark</span></span>](../tutorials/get-started.md)
* [<span data-ttu-id="1777a-116">Bereitstellen einer .NET für Apache Spark-Anwendung in Azure HDInsight</span><span class="sxs-lookup"><span data-stu-id="1777a-116">Deploy a .NET for Apache Spark application to Azure HDInsight</span></span>](../tutorials/hdinsight-deployment.md)
* [<span data-ttu-id="1777a-117">Bereitstellen einer .NET für Apache Spark-Anwendung in Databricks</span><span class="sxs-lookup"><span data-stu-id="1777a-117">Deploy a .NET for Apache Spark application to Databricks</span></span>](../tutorials/databricks-deployment.md)
* [<span data-ttu-id="1777a-118">Bereitstellen einer .NET für Apache Spark-Anwendung in Amazon EMR Spark</span><span class="sxs-lookup"><span data-stu-id="1777a-118">Deploy a .NET for Apache Spark application to Amazon EMR Spark</span></span>](../tutorials/amazon-emr-spark-deployment.md)