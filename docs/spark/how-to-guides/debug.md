---
title: Debuggen einer .NET für Apache Spark-Anwendung unter Windows
description: Erfahren Sie, wie Sie eine .NET für Apache Spark-Anwendung unter Windows debuggen.
ms.date: 06/25/2020
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: 9209d5bdec6dd85f6d21a502fb07204effef1934
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617755"
---
# <a name="debug-a-net-for-apache-spark-application"></a>Debuggen einer .NET für Apache Spark-Anwendung

Diese Anleitung zeigt die Schritte, die Sie zum Debuggen einer .NET für Apache Spark-Anwendung unter Windows ausführen müssen.

[!INCLUDE [spark-preview-note](../../../includes/spark-preview-note.md)]

## <a name="debug-your-application"></a>Debuggen einer Anwendung

Öffnen Sie ein neues Eingabeaufforderungsfenster, und führen Sie den folgenden Befehl aus:

```shell
spark-submit \
  --class org.apache.spark.deploy.dotnet.DotnetRunner \
  --master local \
  <path-to-microsoft-spark-jar> \
  debug
```

Beim Ausführen des Befehls wird die folgende Ausgabe angezeigt:

```console
***********************************************************************
* .NET Backend running debug mode. Press enter to exit *
***********************************************************************
```

Im Debugmodus startet DotnetRunner die .NET-Anwendung nicht, sondern wartet darauf, dass Sie diese starten. Lassen Sie die Eingabeaufforderung offen, und starten Sie die .NET-Anwendung über den C#-Debugger, um sie zu debuggen. Starten Sie Ihre .NET-Anwendung mit einem C#-Debugger ([Visual Studio-Debugger für Windows/macOS](https://visualstudio.microsoft.com/vs/) oder [C#-Debuggererweiterung in Visual Studio Code](https://code.visualstudio.com/Docs/editor/debugging)), um sie zu debuggen.

## <a name="debug-a-user-defined-function-udf"></a>Debuggen einer benutzerdefinierten Funktion (User-Defined Function, UDF)

> [!NOTE]
> Benutzerdefinierte Funktionen werden mit dem Visual Studio-Debugger nur unter Windows unterstützt.

Bevor Sie `spark-submit` ausführen, legen Sie die folgende Umgebungsvariable fest:

```bat
set DOTNET_WORKER_DEBUG=1
```

Wenn Sie Ihre Spark-Anwendung ausführen, wird das Fenster `Choose Just-In-Time Debugger` geöffnet. Wählen Sie einen Visual Studio-Debugger aus.

Der Debugger unterbricht die Ausführung in [TaskRunner.cs](https://github.com/dotnet/spark/blob/5e9c08b430b4bc56b5f42252c4b73437377afaed/src/csharp/Microsoft.Spark.Worker/TaskRunner.cs#L52) an der folgenden Stelle:

```csharp
if (EnvironmentUtils.GetEnvironmentVariableAsBool("DOTNET_WORKER_DEBUG"))
{
    Debugger.Launch(); // <-- The debugger will break here.
}
```

Navigieren Sie zu der *.cs*-Datei mit der benutzerdefinierten Funktion, die Sie debuggen möchten, und [legen Sie einen Breakpoint fest](https://docs.microsoft.com/visualstudio/debugger/using-breakpoints?view=vs-2019). Der Breakpoint zeigt die Meldung `The breakpoint will not currently be hit` an, weil der Worker die Assembly mit der benutzerdefinierten Funktion noch nicht geladen hat.

Drücken Sie `F5`, um die Anwendung fortzusetzen. Der Breakpoint wird schließlich erreicht.

> [!NOTE]
> Das Fenster zur Auswahl eines Just-In-Time-Debuggers wird für jeden Task angezeigt. Um eine übermäßige Anzeige von Popupfenstern zu vermeiden, legen Sie eine niedrige Anzahl von Executors fest. Sie können beispielsweise die Option **--master local[1]** für „spark-submit“ verwenden, um die Anzahl von Tasks auf 1 festzulegen. Damit wird eine einzelne Debuggerinstanz gestartet.

## <a name="debug-scala-code"></a>Debuggen von Scala-Code

Wenn Sie den Scala-seitigen Code (`DotnetRunner`, `DotnetBackendHandler` usw.) debuggen müssen, können Sie den folgenden Befehl verwenden und mithilfe von [IntelliJ](https://www.jetbrains.com/help/idea/attaching-to-local-process.html) einen Debugger an den ausgeführten Prozess anfügen:

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
