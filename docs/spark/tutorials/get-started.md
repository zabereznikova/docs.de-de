---
title: Beginnen Sie mit .net für Apache Spark
description: Erfahren Sie, wie Sie mit .net Core unter Windows eine .net für Apache Spark-app ausführen.
ms.date: 06/27/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 7ce7d7aec6c15385d3d797d5a548519eea33b764
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/13/2019
ms.locfileid: "69577007"
---
# <a name="tutorial-get-started-with-net-for-apache-spark"></a>Tutorial: Beginnen Sie mit .net für Apache Spark

In diesem Tutorial erfahren Sie, wie Sie mit .net Core unter Windows eine .net für Apache Spark-app ausführen.

In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:

> [!div class="checklist"]
> * Vorbereiten der Windows-Umgebung für .net für Apache Spark
> * Herunterladen von " **Microsoft. Spark. Worker** "
> * Erstellen und Ausführen einer einfachen .net für Apache Spark-Anwendung

## <a name="prepare-your-environment"></a>Vorbereiten der Umgebung

Bevor Sie beginnen, stellen Sie sicher, dass `dotnet`Sie `java`, `mvn`, `spark-shell` , über die Befehlszeile ausführen können. Wenn Ihre Umgebung bereits vorbereitet ist, können Sie mit dem nächsten Abschnitt fortfahren. Wenn Sie keine oder alle Befehle ausführen können, führen Sie die folgenden Schritte aus.

1. Laden Sie das [.net Core 2.1 x SDK](https://dotnet.microsoft.com/download/dotnet-core/2.1)herunter, und installieren Sie es. Wenn Sie das SDK installieren `dotnet` , wird die Toolkette dem Pfad hinzugefügt. Verwenden Sie den PowerShell `dotnet --version` -Befehl, um die Installation zu überprüfen.

2. Installieren Sie [Visual Studio 2017](https://www.visualstudio.com/downloads/) oder [Visual Studio 2019](https://visualstudio.microsoft.com/vs/preview/) mit den neuesten Updates. Sie können Community, Professional oder Enterprise verwenden. Die Community-Version ist kostenlos.

   Wählen Sie während der Installation die folgenden Workloads aus:
      * .NET-Desktopentwicklung
          * Alle erforderlichen Komponenten
          * .NET Framework 4.6.1-Entwicklungs Tools
      * Plattformübergreifende .NET Core-Entwicklung
          * Alle erforderlichen Komponenten

3. Installieren Sie [Java 1,8](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html).

    * Wählen Sie die für Ihr Betriebssystem geeignete Version aus. Wählen Sie z. b. **JDK-8u201-Windows-x64. exe** für einen Windows x64-Computer aus.
    * Verwenden Sie den PowerShell `java -version` -Befehl, um die Installation zu überprüfen.

4. Installieren Sie [Apache Maven 3.6.0 +](https://maven.apache.org/download.cgi).
    * Laden Sie [Apache Maven 3.6.0](http://mirror.metrocast.net/apache/maven/maven-3/3.6.0/binaries/apache-maven-3.6.0-bin.zip)herunter.
    * In ein lokales Verzeichnis extrahieren. Beispielsweise `c:\bin\apache-maven-3.6.0\`.
    * Fügen Sie Apache Maven Ihrer [PATH-Umgebungsvariablen](https://www.java.com/en/download/help/path.xml)hinzu. Wenn Sie in `c:\bin\apache-maven-3.6.0\`extrahiert haben, würden Sie `c:\bin\apache-maven-3.6.0\bin` zu Ihrem Pfad hinzufügen.
    * Verwenden Sie den PowerShell `mvn -version` -Befehl, um die Installation zu überprüfen.

5. Installieren Sie [Apache Spark 2.3 +](https://spark.apache.org/downloads.html). Apache Spark 2.4 und höher wird nicht unterstützt.
    * Laden Sie [Apache Spark 2.3](https://spark.apache.org/downloads.html) und höher herunter, und extrahieren Sie Sie mithilfe eines Tools wie [7-Zip](https://www.7-zip.org/) oder [WinZip](https://www.winzip.com/)in einen lokalen Ordner. Beispielsweise können Sie Sie in `c:\bin\spark-2.3.2-bin-hadoop2.7\`extrahieren.
    * Fügen Sie Apache Spark Ihrer [PATH-Umgebungsvariablen](https://www.java.com/en/download/help/path.xml)hinzu. Wenn Sie in `c:\bin\spark-2.3.2-bin-hadoop2.7\`extrahiert haben, würden Sie `c:\bin\spark-2.3.2-bin-hadoop2.7\bin` zu Ihrem Pfad hinzufügen.
    * Fügen Sie eine [neue Umgebungsvariable](https://www.java.com/en/download/help/path.xml) mit dem Namen `SPARK_HOME`hinzu. Wenn Sie in `C:\bin\spark-2.3.2-bin-hadoop2.7\`extrahiert haben, `C:\bin\spark-2.3.2-bin-hadoop2.7\` verwenden Sie für den **Variablen Wert**.
    * Vergewissern Sie sich, dass Sie `spark-shell` in der Befehlszeile ausführen können.

6. Einrichten von [winutils](https://github.com/steveloughran/winutils).
    * Laden Sie die Binärdatei **winutils. exe** aus dem [winutils-Repository](https://github.com/steveloughran/winutils)herunter. Wählen Sie die Version von Hadoop aus, mit der die Spark-Distribution kompiliert wurde. Beispielsweise verwenden Sie **Hadoop-2.7.1** für **Spark 2.3.2**. Die Hadoop-Version wird am Ende Ihres Spark-Installationsordner namens mit Anmerkungen versehen.
    * Speichern Sie die Binärdatei " **winutils. exe** " in einem Verzeichnis Ihrer Wahl. Beispielsweise `c:\hadoop\bin`.
    * Legen `HADOOP_HOME` Sie fest, um das Verzeichnis mit **winutils. exe** ohne `bin`zu reflektieren. Beispielsweise `c:\hadoop`.
    * Legen Sie die Umgebungsvariable PATH auf `%HADOOP_HOME%\bin`include fest.

Überprüfen Sie, ob Sie `dotnet` `mvn`, `java`,, `spark-shell` über die Befehlszeile ausführen können, bevor Sie mit dem nächsten Abschnitt fortfahren.

## <a name="download-the-microsoftsparkworker-release"></a>Herunterladen der Microsoft. Spark. Worker-Version

1. Laden Sie die [Microsoft. Spark. Worker](https://github.com/dotnet/spark/releases) -Version von der .net for Apache Spark GitHub Releases-Seite auf Ihren lokalen Computer herunter. Beispielsweise können Sie die Datei in den Pfad `c:\bin\Microsoft.Spark.Worker\`herunterladen.

2. Erstellen Sie eine [neue Umgebungsvariable](https://www.java.com/en/download/help/path.xml) mit dem Namen `DotnetWorkerPath` , und legen Sie Sie auf das Verzeichnis fest, in das Sie **Microsoft. Spark. Worker**heruntergeladen und extrahiert haben. Beispielsweise `c:\bin\Microsoft.Spark.Worker`.

## <a name="clone-the-net-for-apache-spark-github-repo"></a>Klonen von .net für Apache Spark GitHub-Repository

Verwenden Sie den folgenden [gitbash](https://gitforwindows.org/) -Befehl, um .net für Apache Spark Repository auf Ihrem Computer zu klonen.

```bash
git clone https://github.com/dotnet/spark.git c:\github\dotnet-spark
```

## <a name="write-a-net-for-apache-spark-app"></a>.Net für Apache Spark-app schreiben

1. Öffnen Sie **Visual Studio** , und navigieren Sie zu **Datei > Erstellen Sie ein neues Projekt > Konsolen-app (.net Core)** . Nennen Sie die Anwendung **hellospark**.

2. Installieren Sie das [nuget-Paket Microsoft. Spark](https://www.nuget.org/profiles/spark). Weitere Informationen zum Installieren von nuget-Paketen finden [Sie unter verschiedene Möglichkeiten zum Installieren eines nuget-Pakets](https://docs.microsoft.com/nuget/consume-packages/ways-to-install-a-package).

3. ÖffnenSie in Projektmappen-Explorer **Program.cs** , und schreiben Sie C# den folgenden Code:

   ```csharp
     var spark = SparkSession.Builder().GetOrCreate();
     var df = spark.Read().Json("people.json");
     df.Show();
   ```

4. Erstellen Sie die Projektmappe.

## <a name="run-your-net-for-apache-spark-app"></a>Ausführen der .net für Apache Spark-App

1. Öffnen Sie **PowerShell** , und ändern Sie das Verzeichnis in den Ordner, in dem Ihre APP gespeichert ist.

   ```powershell
   cd <your-app-output-directory>
   ```

2. Erstellen Sie eine Datei namens **People. JSON** mit folgendem Inhalt:

   ```json
   {"name":"Michael"}
   {"name":"Andy", "age":30}
   {"name":"Justin", "age":19}
   ```

3. Verwenden Sie den folgenden PowerShell-Befehl, um die APP auszuführen:

   ```powershell
    spark-submit `
    --class org.apache.spark.deploy.dotnet.DotnetRunner `
    --master local `
    microsoft-spark-2.4.x-<version>.jar `
    dotnet HelloSpark.dll
    ```

Herzlichen Glückwunsch! Sie haben .net für Apache Spark-App erfolgreich erstellt und ausgeführt.

## <a name="next-steps"></a>Nächste Schritte

In diesem Tutorial haben Sie gelernt, wie die folgenden Aufgaben ausgeführt werden:
> [!div class="checklist"]
> * Vorbereiten der Windows-Umgebung für .net für Apache Spark
> * Herunterladen von " **Microsoft. Spark. Worker** "
> * Erstellen und Ausführen einer einfachen .net für Apache Spark-Anwendung

Weitere Informationen finden Sie auf der Ressourcenseite.
> [!div class="nextstepaction"]
> [.Net für Apache Spark-Ressourcen](../resources/index.md)
