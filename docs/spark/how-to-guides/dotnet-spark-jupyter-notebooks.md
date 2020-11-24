---
title: Verwenden von Jupyter-Notebooks
titleSuffix: .NET for Apache Spark
description: Verwenden von .NET für Apache Spark in interaktiven Umgebungen wie Jupyter Notebook, Jupyter Lab oder Visual Studio Code (VS Code)
ms.author: luquinta
author: luisquintanilla
ms.date: 10/09/2020
ms.topic: conceptual
ms.custom: mvc, how-to
ms.openlocfilehash: efebaf0a66863eae0f71fbf1158b80260d7469cf
ms.sourcegitcommit: 34968a61e9bac0f6be23ed6ffb837f52d2390c85
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "94688175"
---
# <a name="use-net-for-apache-spark-in-jupyter-notebooks"></a>Verwenden von .NET für Apache Spark in Jupyter Notebook

In diesem Artikel erfahren Sie, wie Sie .NET für Apache Spark-Aufträge interaktiv in Jupyter Notebook und Visual Studio Code (VS Code) mit .NET Interactive ausführen.

## <a name="about-jupyter"></a>Informationen zu Jupyter

[Jupyter](https://jupyter.org/) ist eine plattformübergreifende Open-Source-Computingumgebung, die Benutzern die Möglichkeit bietet, Prototypen und Anwendungen interaktiv zu entwickeln. Sie können über eine Vielzahl von Schnittstellen mit Jupyter interagieren, z. B. Jupyter Notebook, Jupyter Lab und VS Code.

Im Kontext von .NET bietet [.NET Interactive](https://github.com/dotnet/interactive) (ein globales .NET Core-Tool) einen Kernel zum Schreiben von .NET-Code (C#/F#) in interaktiven Computingumgebungen wie Jupyter Notebook.

## <a name="prerequisites"></a>Voraussetzungen

- [.NET Core 3.1 SDK](../../core/install/index.yml)
- [Apache Spark](https://spark.apache.org/downloads.html)
- [Apache Spark .NET-Worker](https://github.com/dotnet/spark/releases)

Weitere Informationen zum Einrichten Ihrer .NET für Apache Spark-Umgebung finden Sie im [Tutorial für die ersten Schritte](../tutorials/get-started.md).

## <a name="prepare-environment"></a>Vorbereiten der Umgebung

Für die Arbeit mit Jupyter Notebook benötigen Sie zwei Dinge.

1. Installieren Sie das [globale .NET-Tool von .NET Interactive](https://github.com/dotnet/interactive/blob/main/docs/NotebooksLocalExperience.md).
1. Laden Sie das NuGet-Paket `Microsoft.Spark` herunter.
    1. Rufen Sie die NuGet-Paketseite [Microsoft.Spark](https://www.nuget.org/packages/Microsoft.Spark/) auf.

        > [!IMPORTANT]
        > Standardmäßig wird die neueste Version des Pakets heruntergeladen. **Stellen Sie sicher, dass die heruntergeladene Version Ihrem Apache Spark .NET-Worker entspricht.**

    1. Klicken Sie im Bereich **Info** auf **Paket herunterladen**, um die neueste Version des Pakets herunterzuladen. Der Name des Pakets ähnelt *microsoft.spark.[PAKETVERSION].nupkg*.
    1. Entpacken Sie das heruntergeladene Paket. Das entpackte Verzeichnis sollte ein Unterverzeichnis namens *jars* enthalten. Notieren Sie sich den Pfad, da Sie ihn später benötigen.

## <a name="start-net-for-apache-spark"></a>Starten von .NET für Apache Spark

Führen Sie den folgenden Befehl aus, um .NET für Apache Spark im Debugmodus zu starten. Dieser `spark-submit`-Befehl startet einen Prozess und wartet auf eine Verbindung von [SparkSession](xref:Microsoft.Spark.Sql.SparkSession). Stellen Sie sicher, dass Sie den entsprechenden Pfad zu `microsoft-spark-<spark_majorversion-spark_minorversion>_<scala_majorversion.scala_minorversion>-<spark_dotnet_version>.jar` für die Version von .NET für Apache Spark angeben, die Sie verwenden.

**Ubuntu**

```bash
spark-submit \
    --class org.apache.spark.deploy.dotnet.DotnetRunner \
    --master local \
    <path-to-microsoft-spark-jar> \
    debug
```

**Windows**

```cmd
spark-submit ^
    --class org.apache.spark.deploy.dotnet.DotnetRunner ^
    --master local ^
    <path-to-microsoft-spark-jar> ^
    debug
```

## <a name="create-a-notebook"></a>Erstellen eines Notebooks

Sie können verschiedene Schnittstellen verwenden, um mit Jupyter zu interagieren. Wenn Sie eine browserbasierte Schnittstelle verwenden möchten, können Sie Jupyter Notebook oder Jupyter Lab verwenden. Wenn Sie einen lokalen Editor verwenden möchten, können Sie VS Code verwenden.

### <a name="jupyter-notebooks--jupyter-lab"></a>Jupyter Notebook & Jupyter Lab

1. Starten Sie Jupyter Notebook oder Jupyter Lab mit einem der folgenden Befehle in einer anderen Eingabeaufforderung:

    **Jupyter Notebook**

    ```bash
    jupyter notebook
    ```

    **Jupyter Lab**

    ```bash
    jupyter lab
    ```

    Mit diesen Befehlen wird ein Browserfenster mit der Jupyter Notebook- oder Jupyter Lab-Schnittstelle gestartet.

1. Erstellen Sie ein neues Notebook im Browser.

    **Jupyter Notebook**

    Klicken Sie auf **Neu > .NET (C#)** oder **Neu > .NET (F#)**

    **Jupyter Lab**

    Klicken Sie im Fenster des Launchers auf **.NET (C#)** oder **.NET (F#)** .

### <a name="visual-studio-code-preview"></a>Visual Studio Code (Vorschau)

> [!IMPORTANT]
> Zum Verwenden von Jupyter Notebook in VS Code müssen Sie Folgendes installieren:
>
>- [VS Code Insiders](https://code.visualstudio.com/insiders/)
>- [.NET Interactive-Notebookerweiterung](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.dotnet-interactive-vscode)

1. Öffnen Sie Visual Studio Code.
1. Öffnen Sie die Befehlspalette **Ansicht > Befehlspalette**.

    Geben Sie den folgenden Befehl ein, wenn die Befehlspalette angezeigt wird, um ein neues .NET Interactive-Notebook zu erstellen.

    ```text
    >.NET Interactive: Create new blank notebook
    ```

    Alternativ können Sie den folgenden Befehl verwenden, wenn Sie ein vorhandenes .NET Interactive Notebook mit der Erweiterung *.ipynb* öffnen möchten.

    ```text
    >.NET Interactive: Open notebook
    ```

## <a name="initialize-a-spark-session"></a>Initialisieren einer Spark-Sitzung

1. Wenn das Notebook geöffnet wird, installieren Sie das NuGet-Paket `Microsoft.Spark`. Stellen Sie sicher, dass die Version, die Sie installieren, mit der Version des .NET-Workers übereinstimmt.

    ```text
    #r "nuget:Microsoft.Spark, 0.12.1"
    ```

1. Fügen Sie die folgende using-Anweisung zum Notebook hinzu.

    ```csharp
    using Microsoft.Spark.Sql;
    ```

1. Initialisieren Sie das Objekt [SparkSession](xref:Microsoft.Spark.Sql.SparkSession).

    ```csharp
    var sparkSession =
    SparkSession
        .Builder()
        .AppName("dotnet-interactive-spark")
        .GetOrCreate();
    ```

Das Notebook sollte dann dem Notebook auf der folgenden Abbildung ähneln. In diesem Beispiel wird VS Code verwendet, jedoch sollten Jupyter Notebook und Jupyter Lab nahezu identisch aussehen.

> [!div class="mx-imgBorder"]
![.NET für Apache Spark mit Jupyter Notebook in VS Code](media/dotnet-spark-jupyter-notebooks/jupyter-notebooks-dotnet-spark-vscode.png)

## <a name="next-steps"></a>Nächste Schritte

- [Erste Schritte mit .NET für Apache Spark](../tutorials/get-started.md)
- [Vorhersagen der Stimmung mit .NET für Apache Spark und ML.NET](../tutorials/ml-sentiment-analysis.md)
- Weitere Informationen über .NET Interactive finden Sie in der [Dokumentation zu .NET Interactive](https://github.com/dotnet/interactive/blob/main/docs/README.md).
