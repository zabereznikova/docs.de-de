---
title: Erste Schritte mit .NET für Apache Spark
description: Informieren Sie sich, wie Sie mit .NET Core unter Windows, macOS und Ubuntu eine .NET for Apache Spark-App ausführen.
ms.date: 10/09/2020
ms.topic: tutorial
ms.custom: mvc
ms.author: luquinta
author: luisquintanilla
ms.openlocfilehash: 16ccc8f40f290c4bc10f03d1f4d1b296b17f6b11
ms.sourcegitcommit: 34968a61e9bac0f6be23ed6ffb837f52d2390c85
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "94687822"
---
# <a name="tutorial-get-started-with-net-for-apache-spark"></a>Tutorial: Erste Schritte mit .NET für Apache Spark

In diesem Tutorial erfahren Sie, wie Sie mit .NET Core unter Windows, macOS und Ubuntu eine .NET for Apache Spark-App ausführen.

In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:

> [!div class="checklist"]
>
> * Vorbereiten der Umgebung für .NET für Apache Spark
> * Schreiben einer ersten .NET für Apache Spark-Anwendung
> * Erstellen und Ausführen einer .NET für Apache Spark-Anwendung

## <a name="prepare-your-environment"></a>Vorbereiten der Umgebung

Bevor Sie mit dem Schreiben Ihrer App beginnen, müssen Sie einige grundlegende Abhängigkeiten einrichten. Wenn Sie `dotnet`, `java` und `spark-shell` über die Befehlszeilenumgebung ausführen können, ist Ihre Umgebung bereits vorbereitet, und Sie können mit dem nächsten Abschnitt fortfahren. Führen Sie die folgenden Schritte aus, wenn Sie keine oder nicht alle Befehle ausführen können.

### <a name="1-install-net"></a>1. Installieren von .NET

Sie müssen das .NET SDK (Software Development Kit) herunterladen und installieren, um mit der Entwicklung von .NET-Apps zu beginnen.

Laden Sie das [.NET Core SDK](https://dotnet.microsoft.com/download/dotnet-core/3.1) herunter, und installieren Sie es. Dadurch wird die `dotnet`-Toolkette der PATH-Umgebungsvariable hinzugefügt.

Nachdem Sie das .NET Core SDK installiert haben, öffnen Sie eine neue Eingabeaufforderung oder ein Terminal, und führen Sie `dotnet` aus.

Wenn der Befehl ausgeführt wird und Informationen zur Verwendung von dotnet ausgibt, können Sie mit dem nächsten Schritt fortfahren. Stellen Sie sicher, dass Sie vor dem Ausführen des Befehls eine **neue** Eingabeaufforderung oder ein Terminal geöffnet haben, wenn Sie einen `'dotnet' is not recognized as an internal or external command`-Fehler erhalten.

### <a name="2-install-java"></a>2. Installieren von Java

Installieren Sie [Java 8.1](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html) für Windows und macOS oder [OpenJDK 8](https://openjdk.java.net/install/) für Ubuntu.

Wählen Sie die für Ihr Betriebssystem geeignete Version aus. Wählen Sie beispielsweise **jdk-8u201-windows-x64.exe** für einen Windows-x64-Computer (wie unten gezeigt) oder **jdk-8u231-macosx-x64.dmg** für macOS aus. Verwenden Sie dann den Befehl `java`, um die Installation zu überprüfen.

![Java-Download](https://dotnet.microsoft.com/static/images/java-jdk-downloads-windows.png?v=6BbJHoNyDO-PyYVciImr5wzh2AW_YHNcyb3p093AwPA)

### <a name="3-install-compression-software"></a>3. Installieren von Komprimierungssoftware

Apache Spark wird als komprimierte TGZ-Datei heruntergeladen. Verwenden Sie ein Extraktionsprogramm wie [7-Zip](https://www.7-zip.org/) oder [WinZip](https://www.winzip.com/), um die Datei zu extrahieren.

### <a name="4-install-apache-spark"></a>4. Installieren von Apache Spark

[Laden Sie Apache Spark herunter, und installieren Sie es](https://spark.apache.org/downloads.html). Sie müssen aus den Versionen 2.3.* oder 2.4.0, 2.4.1, 2.4.3, 2.4.4, 2.4.5, 2.4.6, 2.4.7, 3.0.0 oder 3.0.1. auswählen (.NET für Apache Spark ist mit anderen Versionen von Apache Spark nicht kompatibel).

Anhand der in den folgenden Schritten verwendeten Befehle wird davon ausgegangen, dass Sie [Apache Spark 3.0.1 heruntergeladen und installiert](https://spark.apache.org/downloads.html) haben. Wenn Sie eine andere Version verwenden möchten, ersetzen Sie **3.0.1** durch die entsprechende Versionsnummer. Extrahieren Sie anschließend die **TAR**-Datei und die Apache Spark-Dateien.

So extrahieren Sie die **TAR**-Datei:

* Suchen Sie die Datei **spark-3.0.1-bin-hadoop2.7.tgz**, die Sie heruntergeladen haben.
* Klicken Sie mit der rechten Maustaste auf die Datei, und wählen Sie **7-Zip -> Extract here** (7-Zip -> Hier extrahieren) aus.
* **spark-3.0.1-bin-hadoop2.7.tar** wird zusammen mit der **TGZ**-Datei erstellt, die Sie heruntergeladen haben.

So extrahieren Sie die Apache Spark-Dateien:

* Klicken Sie mit der rechten Maustaste auf **spark-3.0.1-bin-hadoop2.7.tar**, und klicken Sie auf **7-Zip > Extract files** (7-Zip > Dateien extrahieren).
* Geben Sie **C:\bin** in das Feld **Extrahieren nach** ein.
* Deaktivieren Sie das Kontrollkästchen unterhalb des Felds **Extrahieren nach**.
* Klicken Sie auf **OK**.
* Die Apache Spark-Dateien werden nach C:\bin\spark-3.0.1-bin-hadoop2.7\ extrahiert.

![Spark-Installation](./media/spark-extract-with-7-zip.png)

Führen Sie die folgenden Befehle aus, um die Umgebungsvariablen für die Suche nach Apache Spark festzulegen. Stellen Sie unter Windows sicher, dass Sie die Eingabeaufforderung im Administratormodus ausführen.

#### <a name="windows"></a>[Windows](#tab/windows)

```console
setx /M HADOOP_HOME C:\bin\spark-3.0.1-bin-hadoop2.7\
setx /M SPARK_HOME C:\bin\spark-3.0.1-bin-hadoop2.7\
setx /M PATH "%PATH%;%HADOOP_HOME%;%SPARK_HOME%\bin"
```

#### <a name="maclinux"></a>[Mac/Linux](#tab/linux)

```bash
export SPARK_HOME=~/bin/spark-3.0.1-bin-hadoop2.7/
export PATH="$SPARK_HOME/bin:$PATH"
source ~/.bashrc
```

---

Nachdem Sie alles installiert und die Umgebungsvariablen festgelegt haben, öffnen Sie eine **neue** Eingabeaufforderung oder ein Terminal, und führen Sie den folgenden Befehl aus:

```text
spark-submit --version
```

Wenn der Befehl ausgeführt wird und Versionsinformationen ausgibt, können Sie mit dem nächsten Schritt fortfahren.

Wenn Sie einen `'spark-submit' is not recognized as an internal or external command`-Fehler erhalten, stellen Sie sicher, dass Sie eine **neue** Eingabeaufforderung geöffnet haben.

### <a name="5-install-net-for-apache-spark"></a>5. Installieren von .NET für Apache Spark

Laden Sie das [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases)-Release von GitHub für .NET für Apache Spark herunter. Wenn Sie beispielsweise einen Windows-Computer nutzen und die Verwendung von .NET Core planen, [laden Sie das Windows x64 netcoreapp3.1-Release herunter](https://github.com/dotnet/spark/releases).

So extrahieren Sie Microsoft.Spark.Worker:

* Suchen Sie die Datei **Microsoft.Spark.Worker.netcoreapp3.1.win-x64-1.0.0.zip**, die Sie heruntergeladen haben.
* Klicken Sie mit der rechten Maustaste, und wählen Sie **7-Zip > Extract files** (7-Zip > Dateien extrahieren) aus.
* Geben Sie **C:\bin** in das Feld **Extrahieren nach** ein.
* Deaktivieren Sie das Kontrollkästchen unterhalb des Felds **Extrahieren nach**.
* Klicken Sie auf **OK**.

### <a name="6-install-winutils-windows-only"></a>6. Installieren von WinUtils (nur Windows)

.NET für Apache Spark erfordert die Installation von WinUtils neben Apache Spark. [Laden Sie die winutils.exe-Datei herunter](https://github.com/steveloughran/winutils/blob/master/hadoop-2.7.1/bin/winutils.exe). Kopieren Sie dann WinUtils in **C:\bin\spark-3.0.1-bin-hadoop2.7\bin**.

> [!NOTE]
> Wenn Sie eine andere Version von Hadoop verwenden (dies ist am Ende des Namens Ihres Spark-Installationsordner angemerkt), [wählen Sie die Version von WinUtils aus](https://github.com/steveloughran/winutils), die mit Ihrer Version von Hadoop kompatibel ist.

### <a name="7-set-dotnet_worker_dir-and-check-dependencies"></a>7. Festlegen von DOTNET_WORKER_DIR und Überprüfen von Abhängigkeiten

Führen Sie einen der folgenden Befehle aus, um die Umgebungsvariable `DOTNET_WORKER_DIR` festzulegen, die von .NET-Apps für die Suche nach Workerbinärdateien für .NET für Apache Spark verwendet wird. Stellen Sie sicher, dass Sie `<PATH-DOTNET_WORKER_DIR>` durch das Verzeichnis ersetzen, in das Sie `Microsoft.Spark.Worker` heruntergeladen und extrahiert haben. Stellen Sie unter Windows sicher, dass Sie die Eingabeaufforderung im Administratormodus ausführen.

#### <a name="windows"></a>[Windows](#tab/windows)

```console
setx /M DOTNET_WORKER_DIR <PATH-DOTNET-WORKER-DIR>
```

#### <a name="maclinux"></a>[Mac/Linux](#tab/linux)

```bash
export DOTNET_WORKER_DIR=<PATH-DOTNET-WORKER-DIR>
```

---

Überprüfen Sie abschließend, ob Sie `dotnet`, `java` und `spark-shell` über die Befehlszeile ausführen können, bevor Sie mit dem nächsten Abschnitt fortfahren.

## <a name="write-a-net-for-apache-spark-app"></a>Programmieren einer .NET für Apache Spark-App

### <a name="1-create-a-console-app"></a>1. Erstellen einer Konsolenanwendung

Führen Sie in der Eingabeaufforderung oder im Terminal die folgenden Befehle aus, um eine neue Konsolenanwendung zu erstellen:

```dotnetcli
dotnet new console -o MySparkApp
cd MySparkApp
```

Der `dotnet`-Befehl erstellt für Sie eine `new`-Anwendung des Typs `console`. Der `-o`-Parameter erstellt ein Verzeichnis namens *MySparkApp*, in dem Ihre App gespeichert wird, und füllt es mit den erforderlichen Dateien auf. Mit dem Befehl `cd MySparkApp` wird das Verzeichnis in das erstellte App-Verzeichnis geändert.

### <a name="2-install-nuget-package"></a>2. Installieren des NuGet-Pakets

Wenn Sie .NET für Apache Spark in einer App verwenden möchten, installieren Sie das Microsoft.Spark-Paket. Führen Sie in der Eingabeaufforderung oder im Terminal den folgenden Befehl aus:

```dotnetcli
dotnet add package Microsoft.Spark
```

> [!NOTE]
> In diesem Tutorial wird die neueste Version des NuGet-Pakets `Microsoft.Spark` verwendet, sofern nicht anders angegeben.

### <a name="3-write-your-app"></a>3. Schreiben der App

Öffnen Sie *Program.cs* in Visual Studio Code oder in einem beliebigen Text-Editor, und ersetzen Sie den gesamten Code durch Folgendes:

```csharp
using Microsoft.Spark.Sql;
using static Microsoft.Spark.Sql.Functions;

namespace MySparkApp
{
    class Program
    {
        static void Main(string[] args)
        {
            // Create Spark session
            SparkSession spark =
                SparkSession
                    .Builder()
                    .AppName("word_count_sample")
                    .GetOrCreate();

            // Create initial DataFrame
            string filePath = args[0];
            DataFrame dataFrame = spark.Read().Text(filePath);

            //Count words
            DataFrame words =
                dataFrame
                    .Select(Split(Col("value")," ").Alias("words"))
                    .Select(Explode(Col("words")).Alias("word"))
                    .GroupBy("word")
                    .Count()
                    .OrderBy(Col("count").Desc());

            // Display results
            words.Show();

            // Stop Spark session
            spark.Stop();
        }
    }
}
```

[SparkSession](xref:Microsoft.Spark.Sql.SparkSession) ist der Einstiegspunkt von Apache Spark-Anwendungen, der den Kontext und Informationen zu Ihrer Anwendung verwaltet. Mithilfe der [Text](xref:Microsoft.Spark.Sql.DataFrameReader.Text%2A)-Methode werden die Textdaten aus der Datei, die durch `filePath` angegeben wird, in einen [DataFrame](xref:Microsoft.Spark.Sql.DataFrame) gelesen. Ein DataFrame ist eine Möglichkeit zum Organisieren von Daten in eine Gruppe von benannten Spalten. Anschließend wird eine Reihe von Transformationen angewendet, um die Sätze in der Datei aufzuteilen, die einzelnen Wörter zu gruppieren, sie zu zählen und in absteigender Reihenfolge zu sortieren. Das Ergebnis dieser Vorgänge wird in einem anderen DataFrame gespeichert. Beachten Sie, dass zu diesem Zeitpunkt keine Vorgänge stattgefunden haben, da .NET für Apache Spark die Daten verzögert auswertet. Erst wenn die [Show](xref:Microsoft.Spark.Sql.DataFrame.Show%2A)-Methode aufgerufen wird, um den Inhalt des transformierten `words`-DataFrame in der Konsole anzuzeigen, werden die Vorgänge, die in den Zeilen oben definiert wurden, ausgeführt. Wenn Sie die Spark-Sitzung nicht mehr benötigen, verwenden Sie die [Stop](xref:Microsoft.Spark.Sql.SparkSession.Stop%2A)-Methode zum Beenden der Sitzung.

### <a name="4-create-data-file"></a>4. Erstellen der Datendatei

Ihre App verarbeitet eine Datei mit Textzeilen. Erstellen Sie eine Datei *input.txt* in Ihrem Verzeichnis *MySparkApp*, die den folgenden Text enthält:

```text
Hello World
This .NET app uses .NET for Apache Spark
This .NET app counts words with Apache Spark
```

Speichern Sie die Änderungen, und schließen Sie die Datei.

## <a name="run-your-net-for-apache-spark-app"></a>Ausführen der .NET für Apache Spark-App

Führen Sie den folgenden Befehl aus, um die Anwendung zu erstellen:

```dotnetcli
dotnet build
```

Navigieren Sie zum Buildausgabeverzeichnis, und verwenden Sie den `spark-submit`-Befehl, um Ihre Anwendung für die Ausführung unter Apache Spark zu übermitteln. Stellen Sie sicher, dass Sie `<version>` durch die Version des .NET-Workers und `<path-of-input.txt>` durch den Pfad der Datei *input.txt* ersetzen.

### <a name="windows"></a>[Windows](#tab/windows)

```console
spark-submit ^
--class org.apache.spark.deploy.dotnet.DotnetRunner ^
--master local ^
microsoft-spark-3-0_2.12-<version>.jar ^
dotnet MySparkApp.dll <path-of-input.txt>
```

### <a name="maclinux"></a>[Mac/Linux](#tab/linux)

```bash
spark-submit \
--class org.apache.spark.deploy.dotnet.DotnetRunner \
--master local \
microsoft-spark-3-0_2.12-<version>.jar \
dotnet MySparkApp.dll <path-of-input.txt>
```

---

> [!NOTE]
> Bei diesem Befehl wird davon ausgegangen, dass Sie Apache Spark heruntergeladen und der Umgebungsvariablen „PATH“ hinzugefügt haben, damit `spark-submit` verwendet werden kann. Andernfalls müssten Sie den vollständigen Pfad (z. B. *C:\bin\apache-spark\bin\spark-submit* oder *~/spark/bin/spark-submit*) verwenden.

Wenn Ihre App ausgeführt wird, werden die Wortzähldaten der Datei *Input.txt* in die Konsole geschrieben.

```console
+------+-----+
|  word|count|
+------+-----+
|  .NET|    3|
|Apache|    2|
|   app|    2|
|  This|    2|
| Spark|    2|
| World|    1|
|counts|    1|
|   for|    1|
| words|    1|
|  with|    1|
| Hello|    1|
|  uses|    1|
+------+-----+
```

Herzlichen Glückwunsch! Sie haben eine .NET für Apache Spark-App erfolgreich erstellt und ausgeführt.

## <a name="next-steps"></a>Nächste Schritte

In diesem Tutorial haben Sie Folgendes gelernt:
> [!div class="checklist"]
>
> * Vorbereiten der Umgebung für .NET für Apache Spark
> * Schreiben einer ersten .NET für Apache Spark-Anwendung
> * Erstellen und Ausführen einer .NET für Apache Spark-Anwendung

Ein Video, in dem die oben aufgeführten Schritte erläutert werden, finden Sie in der [Videoserie zu .NET für Apache Spark 101](https://channel9.msdn.com/Series/NET-for-Apache-Spark-101/Run-Your-First-NET-for-Apache-Spark-App).

Weitere Informationen finden Sie auf der Ressourcenseite.
> [!div class="nextstepaction"]
> [Ressourcen für .NET für Apache Spark](../resources/index.md)
