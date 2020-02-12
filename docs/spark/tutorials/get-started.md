---
title: Erste Schritte mit .NET für Apache Spark
description: Informieren Sie sich, wie Sie mit .NET Core unter Windows, macOS und Ubuntu eine .NET für Apache Spark-App ausführen.
ms.date: 01/31/2020
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 018c21804bf942233e07039281d7ec22a6bef763
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2020
ms.locfileid: "77092316"
---
# <a name="tutorial-get-started-with-net-for-apache-spark"></a>Tutorial: Erste Schritte mit .NET für Apache Spark

In diesem Tutorial erfahren Sie, wie Sie mit .NET Core unter Windows, macOS und Ubuntu eine .NET für Apache Spark-App ausführen.

In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:

> [!div class="checklist"]
>
> * Vorbereiten der Umgebung für .NET für Apache Spark
> * Schreiben einer ersten .NET für Apache Spark-Anwendung
> * Erstellen und Ausführen einer einfachen .NET für Apache Spark-Anwendung

## <a name="prepare-your-environment"></a>Vorbereiten der Umgebung

Bevor Sie mit dem Schreiben Ihrer App beginnen, müssen Sie einige grundlegende Abhängigkeiten einrichten. Wenn Sie `dotnet`, `java`, `mvn` und `spark-shell` über die Befehlszeilenumgebung ausführen können, ist Ihre Umgebung bereits vorbereitet, und Sie können mit dem nächsten Abschnitt fortfahren. Führen Sie die folgenden Schritte aus, wenn Sie keine oder nicht alle Befehle ausführen können.

### <a name="1-install-net"></a>1. Installieren von .NET

Sie müssen das .NET SDK (Software Development Kit) herunterladen und installieren, um mit der Entwicklung von .NET-Apps zu beginnen.

Laden Sie das [.NET Core SDK](https://dotnet.microsoft.com/download/dotnet-core/3.1) herunter, und installieren Sie es. Dadurch wird die `dotnet`-Toolkette der PATH-Umgebungsvariable hinzugefügt.

Nachdem Sie das .NET Core SDK installiert haben, öffnen Sie eine neue Eingabeaufforderung oder ein Terminal, und führen Sie `dotnet` aus.

Wenn der Befehl ausgeführt wird und Informationen zur Verwendung von dotnet ausgibt, können Sie mit dem nächsten Schritt fortfahren. Stellen Sie sicher, dass Sie vor dem Ausführen des Befehls eine **neue** Eingabeaufforderung oder ein Terminal geöffnet haben, wenn Sie einen `'dotnet' is not recognized as an internal or external command`-Fehler erhalten.

### <a name="2-install-java"></a>2. Installieren von Java

Installieren Sie [Java 8.1](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html) für Windows und macOS oder [OpenJDK 8](https://openjdk.java.net/install/) für Ubuntu.

Wählen Sie die für Ihr Betriebssystem geeignete Version aus. Wählen Sie beispielsweise **jdk-8u201-windows-x64.exe** für einen Windows x64-Computer (wie unten gezeigt) oder **jdk-8u231-macosx-x64.dmg** für macOS aus. Verwenden Sie dann den Befehl `java`, um die Installation zu überprüfen.

![Java-Download](https://dotnet.microsoft.com/static/images/java-jdk-downloads-windows.png?v=6BbJHoNyDO-PyYVciImr5wzh2AW_YHNcyb3p093AwPA)

### <a name="3-install-compression-software"></a>3. Installieren von Komprimierungssoftware

Apache Spark wird als komprimierte TGZ-Datei heruntergeladen. Verwenden Sie ein Extraktionsprogramm wie [7-Zip](https://www.7-zip.org/) oder [WinZip](https://www.winzip.com/), um die Datei zu extrahieren.

### <a name="4-install-apache-spark"></a>4. Installieren von Apache Spark

[Laden Sie Apache Spark herunter, und installieren Sie es](https://spark.apache.org/downloads.html). Sie müssen aus den Versionen 2.3.* oder 2.4.0, 2.4.1, 2.4.3 oder 2.4.4 auswählen (.NET für Apache Spark ist mit anderen Versionen von Apache Spark nicht kompatibel).

Anhand der in den folgenden Schritten verwendeten Befehle wird davon ausgegangen, dass Sie [Apache Spark 2.4.1 heruntergeladen und installiert](https://archive.apache.org/dist/spark/spark-2.4.1/spark-2.4.1-bin-hadoop2.7.tgz) haben. Wenn Sie eine andere Version verwenden möchten, ersetzen Sie **2.4.1** durch die entsprechende Versionsnummer. Extrahieren Sie anschließend die **TAR**-Datei und die Apache Spark-Dateien.

So extrahieren Sie die **TAR**-Datei:

* Suchen Sie die Datei **spark-2.4.1-bin-hadoop2.7.tgz**, die Sie heruntergeladen haben.
* Klicken Sie mit der rechten Maustaste auf die Datei, und wählen Sie **7-Zip -> Extract here** (7-Zip -> Hier extrahieren) aus.
* **spark-2.4.1-bin-hadoop2.7.tar** wird zusammen mit der **TGZ**-Datei erstellt, die Sie heruntergeladen haben.

So extrahieren Sie die Apache Spark-Dateien:

* Klicken Sie mit der rechten Maustaste auf **spark-2.4.1-bin-hadoop2.7.tar**, und wählen Sie **7-Zip -> Extract files...** (7-Zip-> Dateien extrahieren...) aus.
* Geben Sie **C:\bin** in das Feld **Extrahieren nach** ein.
* Deaktivieren Sie das Kontrollkästchen unterhalb des Felds **Extrahieren nach**.
* Klicken Sie auf **OK**.
* Die Apache Spark-Dateien werden nach C:\bin\spark-2.4.1-bin-hadoop2.7\ extrahiert.

![Spark-Installation](https://dotnet.microsoft.com/static/images/spark-extract-with-7-zip.png?v=YvjUv54LIxI9FbALPC3h8zSQdyMtK2-NKbFOliG-f8M)

Führen Sie die folgenden Befehle aus, um die Umgebungsvariablen für die Suche nach Apache Spark unter **Windows** festzulegen:

```console
setx HADOOP_HOME C:\bin\spark-2.4.1-bin-hadoop2.7\
setx SPARK_HOME C:\bin\spark-2.4.1-bin-hadoop2.7\
```

Führen Sie die folgenden Befehle aus, um die Umgebungsvariablen für die Suche nach Apache Spark unter **macOS** und **Ubuntu** festzulegen:

```bash
export SPARK_HOME=~/bin/spark-2.4.1-bin-hadoop2.7/
export PATH="$SPARK_HOME/bin:$PATH"
source ~/.bashrc
```

Nachdem Sie alles installiert und die Umgebungsvariablen festgelegt haben, öffnen Sie eine **neue** Eingabeaufforderung oder ein Terminal, und führen Sie den folgenden Befehl aus:

`%SPARK_HOME%\bin\spark-submit --version`

Wenn der Befehl ausgeführt wird und Versionsinformationen ausgibt, können Sie mit dem nächsten Schritt fortfahren.

Wenn Sie einen `'spark-submit' is not recognized as an internal or external command`-Fehler erhalten, stellen Sie sicher, dass Sie eine **neue** Eingabeaufforderung geöffnet haben.

### <a name="5-install-net-for-apache-spark"></a>5. Installieren von .NET für Apache Spark

Laden Sie das [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases)-Release von GitHub für .NET für Apache Spark herunter. Wenn Sie beispielsweise einen Windows-Computer nutzen und die Verwendung von .NET Core planen, [laden Sie das Windows x64 netcoreapp3.1-Release herunter](https://github.com/dotnet/spark/releases/download/v0.8.0/Microsoft.Spark.Worker.netcoreapp3.1.win-x64-0.8.0.zip).

So extrahieren Sie Microsoft.Spark.Worker:

* Suchen Sie die Datei **Microsoft.Spark.Worker.netcoreapp3.1.win-x64-0.8.0.zip**, die Sie heruntergeladen haben.
* Klicken Sie mit der rechten Maustaste, und wählen Sie **7-Zip -> Extract files...** (7-Zip-> Dateien extrahieren...) aus.
* Geben Sie **C:\bin** in das Feld **Extrahieren nach** ein.
* Deaktivieren Sie das Kontrollkästchen unterhalb des Felds **Extrahieren nach**.
* Klicken Sie auf **OK**.

![.NET Spark-Installation](https://dotnet.microsoft.com/static/images/dotnet-for-spark-extract-with-7-zip.png?v=jwCyum9mL0mGIi4V5zC7yuvLfcj1_nL-QFFD8TClhZk)

### <a name="6-install-winutils-windows-only"></a>6. Installieren von WinUtils (nur Windows)

.NET für Apache Spark erfordert die Installation von WinUtils neben Apache Spark. [Laden Sie die winutils.exe-Datei herunter](https://github.com/steveloughran/winutils/blob/master/hadoop-2.7.1/bin/winutils.exe). Kopieren Sie dann WinUtils in **C:\bin\spark-2.4.1-bin-hadoop2.7\bin**.

> [!NOTE]
> Wenn Sie eine andere Version von Hadoop verwenden (dies ist am Ende des Namens Ihres Spark-Installationsordner angemerkt), [wählen Sie die Version von WinUtils aus](https://github.com/steveloughran/winutils), die mit Ihrer Version von Hadoop kompatibel ist.

### <a name="7-set-dotnet_worker_dir-and-check-dependencies"></a>7. Festlegen von DOTNET_WORKER_DIR und Überprüfen von Abhängigkeiten

Führen Sie einen der folgenden Befehle aus, um die Umgebungsvariable `DOTNET_WORKER_DIR` festzulegen, die von .NET-Apps für die Suche nach Apache Spark verwendet wird.

Erstellen Sie unter **Windows** die [neue Umgebungsvariable](https://www.java.com/en/download/help/path.xml) `DOTNET_WORKER_DIR`, und legen Sie diese auf das Verzeichnis fest, in dem sich die heruntergeladene und extrahierte Microsoft.Spark.Worker-Datei befindet (z. B. `C:\bin\Microsoft.Spark.Worker\`).

Erstellen Sie unter **macOS** mithilfe von `export DOTNET_WORKER_DIR <your_path>` eine neue Umgebungsvariable, und legen Sie diese auf das Verzeichnis fest, in dem sich die heruntergeladene und extrahierte Microsoft.Spark.Worker-Datei befindet (z. B. *~/bin/Microsoft.Spark.Worker/* ). 

Erstellen Sie unter **Ubuntu** die [neue Umgebungsvariable](https://help.ubuntu.com/community/EnvironmentVariables) `DOTNET_WORKER_DIR`, und legen Sie diese auf das Verzeichnis fest, in dem sich die heruntergeladene und extrahierte Microsoft.Spark.Worker-Datei befindet (z. B. *~/bin/Microsoft.Spark.Worker*).

Überprüfen Sie abschließend, ob Sie `dotnet`, `java`, `mvn` und `spark-shell` über die Befehlszeile ausführen können, bevor Sie mit dem nächsten Abschnitt fortfahren.

## <a name="write-a-net-for-apache-spark-app"></a>Programmieren einer .NET für Apache Spark-App

### <a name="1-create-a-console-app"></a>1. Erstellen einer Konsolenanwendung

Führen Sie in der Eingabeaufforderung oder im Terminal die folgenden Befehle aus, um eine neue Konsolenanwendung zu erstellen:

```dotnetcli
dotnet new console -o mySparkApp
cd mySparkApp
```

Der `dotnet`-Befehl erstellt für Sie eine `new`-Anwendung des Typs `console`. Der `-o`-Parameter erstellt ein Verzeichnis namens *mySparkApp*, in dem Ihre App gespeichert wird, und füllt es mit den erforderlichen Dateien auf. Mit dem Befehl `cd mySparkApp` wird das Verzeichnis in das soeben erstellte App-Verzeichnis geändert.

### <a name="2-install-nuget-package"></a>2. Installieren des NuGet-Pakets

Wenn Sie .NET für Apache Spark in einer App verwenden möchten, installieren Sie das Microsoft.Spark-Paket. Führen Sie in der Eingabeaufforderung oder im Terminal den folgenden Befehl aus:

`dotnet add package Microsoft.Spark --version 0.8.0`

### <a name="3-code-your-app"></a>3. Programmieren Ihrer App

Öffnen Sie *Program.cs* in Visual Studio Code oder in einem beliebigen Text-Editor, und ersetzen Sie den gesamten Code durch Folgendes:

```csharp
using Microsoft.Spark.Sql;

namespace MySparkApp
{
    class Program
    {
        static void Main(string[] args)
        {
            // Create a Spark session.
            SparkSession spark = SparkSession
                .Builder()
                .AppName("word_count_sample")
                .GetOrCreate();

            // Create initial DataFrame.
            DataFrame dataFrame = spark.Read().Text("input.txt");

            // Count words.
            DataFrame words = dataFrame
                .Select(Functions.Split(Functions.Col("value"), " ").Alias("words"))
                .Select(Functions.Explode(Functions.Col("words"))
                .Alias("word"))
                .GroupBy("word")
                .Count()
                .OrderBy(Functions.Col("count").Desc());

            // Show results.
            words.Show();

            // Stop Spark session.
            spark.Stop();
        }
    }
}
```

### <a name="4-create-and-add-a-data-file"></a>4. Erstellen und Hinzufügen einer Datendatei

Öffnen Sie die Eingabeaufforderung oder ein Terminal, und navigieren Sie zu Ihrem App-Ordner.

```bash
cd <your-app-output-directory>
```

Ihre App verarbeitet eine Datei mit Textzeilen. Erstellen Sie eine *input.txt*-Datei in Ihrem *mySparkApp*-Verzeichnis, die den folgenden Text enthält:

```text
Hello World
This .NET app uses .NET for Apache Spark
This .NET app counts words with Apache Spark
```

## <a name="run-your-net-for-apache-spark-app"></a>Ausführen der .NET für Apache Spark-App

1. Führen Sie den folgenden Befehl aus, um die Anwendung zu erstellen:

   ```dotnetcli
   dotnet build
   ```

2. Führen Sie den folgenden Befehl aus, um Ihre Anwendung für die Ausführung auf Apache Spark zu übermitteln:

   ```console
   spark-submit \
   --class org.apache.spark.deploy.dotnet.DotnetRunner \
   --master local \
   microsoft-spark-2.4.x-<version>.jar \
   dotnet HelloSpark.dll
   ```

   > [!NOTE]
   > Bei diesem Befehl wird davon ausgegangen, dass Sie Apache Spark heruntergeladen und der Umgebungsvariablen „PATH“ hinzugefügt haben, damit `spark-submit` verwendet werden kann. Andernfalls müssten Sie den vollständigen Pfad (z. B. *C:\bin\apache-spark\bin\spark-submit* oder *~/spark/bin/spark-submit*) verwenden.

3. Wenn Ihre App ausgeführt wird, werden die Wortzähldaten der Datei *Input.txt* in die Konsole geschrieben.

Herzlichen Glückwunsch! Sie haben eine .NET für Apache Spark-App erfolgreich erstellt und ausgeführt.

## <a name="next-steps"></a>Nächste Schritte

In diesem Tutorial haben Sie gelernt, wie die folgenden Aufgaben ausgeführt werden:
> [!div class="checklist"]
>
> * Vorbereiten der Windows-Umgebung für .NET für Apache Spark
> * Schreiben einer ersten .NET für Apache Spark-Anwendung
> * Erstellen und Ausführen einer einfachen .NET für Apache Spark-Anwendung

Ein Video, in dem die obigen Schritte erläutert werden, finden Sie in der [Videoserie zu .NET für Apache Spark 101](https://channel9.msdn.com/Series/NET-for-Apache-Spark-101/Run-Your-First-NET-for-Apache-Spark-App).

Weitere Informationen finden Sie auf der Ressourcenseite.
> [!div class="nextstepaction"]
> [Ressourcen für .NET für Apache Spark](../resources/index.md)
