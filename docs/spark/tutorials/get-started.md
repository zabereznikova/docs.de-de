---
title: Erste Schritte mit .NET für Apache Spark
description: Erfahren Sie, wie Sie mit .NET Core unter Windows eine .NET für Apache Spark-App ausführen.
ms.date: 06/27/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 19efc8412d834d73069c61e1cc1ccd9e5eb8593b
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2019
ms.locfileid: "72774374"
---
# <a name="tutorial-get-started-with-net-for-apache-spark"></a>Tutorial: Erste Schritte mit .NET für Apache Spark

In diesem Tutorial erfahren Sie, wie Sie mit .NET Core unter Windows eine .NET für Apache Spark-App ausführen.

In diesem Tutorial lernen Sie, wie die folgenden Aufgaben ausgeführt werden:

> [!div class="checklist"]
>
> * Vorbereiten der Windows-Umgebung für .NET für Apache Spark
> * Herunterladen von **Microsoft.Spark.Worker**
> * Erstellen und Ausführen einer einfachen .NET für Apache Spark-Anwendung

## <a name="prepare-your-environment"></a>Vorbereiten der Umgebung

Überprüfen Sie zuerst, ob Sie `dotnet`, `java`, `mvn` und `spark-shell` über die Befehlszeile ausführen können. Wenn Sie Ihre Umgebung bereits vorbereitet haben, können Sie mit dem nächsten Abschnitt fortfahren. Wenn Sie keine oder nicht alle Befehle ausführen können, müssen Sie zuerst die folgenden Schritte abarbeiten.

1. Laden Sie das [.NET Core 2.1x SDK](https://dotnet.microsoft.com/download/dotnet-core/2.1) herunter, und installieren Sie es. Dadurch wird die `dotnet`-Toolkette der PATH-Umgebungsvariable hinzugefügt. Verwenden Sie den PowerShell-Befehl `dotnet --version`, um die Installation zu überprüfen.

2. Installieren Sie [Visual Studio 2017](https://www.visualstudio.com/downloads/) oder [Visual Studio 2019](https://visualstudio.microsoft.com/vs/preview/) mit den neuesten Updates. Sie können die Versionen Community, Professional oder Enterprise verwenden. Die Community-Version ist kostenlos.

   Wählen Sie während der Installation die folgenden Workloads aus:
      * .NET-Desktopentwicklung
          * Alle erforderlichen Komponenten
          * .NET Framework 4.6.1-Entwicklungstools
      * Plattformübergreifende .NET Core-Entwicklung
          * Alle erforderlichen Komponenten

3. Installieren Sie [Java 1.8](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html).

    * Wählen Sie die für Ihr Betriebssystem geeignete Version aus. Für einen Windows-Computer mit x64-Architektur wählen Sie beispielsweise **jdk-8u201-windows-x64.exe** aus.
    * Verwenden Sie den PowerShell-Befehl `java -version`, um die Installation zu überprüfen.

4. Installieren Sie [Apache Maven 3.6.0 oder höher](https://maven.apache.org/download.cgi).
    * Laden Sie [Apache Maven 3.6.2](http://mirror.metrocast.net/apache/maven/maven-3/3.6.2/binaries/apache-maven-3.6.2-bin.zip) herunter.
    * Extrahieren Sie die Datei in ein lokales Verzeichnis. Beispielsweise `c:\bin\apache-maven-3.6.2\`.
    * Fügen Sie Ihrer [PATH-Umgebungsvariable](https://www.java.com/en/download/help/path.xml) Apache Maven hinzu. Wenn Sie bei der Extraktion `c:\bin\apache-maven-3.6.2\` als Zielverzeichnis angegeben haben, fügen Sie PATH `c:\bin\apache-maven-3.6.2\bin` hinzu.
    * Verwenden Sie den PowerShell-Befehl `mvn -version`, um die Installation zu überprüfen.

5. Installieren Sie [Apache Spark 2.3 oder höher](https://spark.apache.org/downloads.html). Apache Spark 2.4 und höher wird nicht unterstützt.
    * Laden Sie [Apache Spark 2.3 oder höher](https://spark.apache.org/downloads.html) herunter, und extrahieren Sie die Datei mit einem Tool wie [7-Zip](https://www.7-zip.org/) oder [WinZip](https://www.winzip.com/) in einen lokalen Ordner. Sie können beispielsweise `c:\bin\spark-2.3.2-bin-hadoop2.7\` als Extraktionsverzeichnis verwenden.
    * Fügen Sie Ihrer [PATH-Umgebungsvariable](https://www.java.com/en/download/help/path.xml) Apache Spark hinzu. Wenn Sie bei der Extraktion `c:\bin\spark-2.3.2-bin-hadoop2.7\` als Zielverzeichnis angegeben haben, fügen Sie PATH `c:\bin\spark-2.3.2-bin-hadoop2.7\bin` hinzu.
    * Fügen Sie [eine neue Umgebungsvariable](https://www.java.com/en/download/help/path.xml) mit dem Namen `SPARK_HOME` hinzu. Wenn Sie bei der Extraktion `C:\bin\spark-2.3.2-bin-hadoop2.7\` als Zielverzeichnis angegeben haben, legen Sie `C:\bin\spark-2.3.2-bin-hadoop2.7\` als **Variablenwert** fest.
    * Überprüfen Sie, ob Sie `spark-shell` über die Befehlszeile ausführen können.

6. Richten Sie [WinUtils](https://github.com/steveloughran/winutils) ein.
    * Laden Sie die Binärdatei **winutils.exe** aus dem [WinUtils-Repository](https://github.com/steveloughran/winutils) herunter. Wählen Sie die Hadoop-Version aus, mit der die Spark-Distribution kompiliert wurde. Für **Spark 2.3.2** verwenden Sie beispielsweise **hadoop-2.7.1**. Die Hadoop-Version ist abschließend in der Bezeichnung des Spark-Installationsordners enthalten.
    * Speichern Sie die Binärdatei **winutils.exe** in einem beliebigen Verzeichnis. Beispielsweise `c:\hadoop\bin`.
    * Legen Sie für `HADOOP_HOME` das Verzeichnis fest, in dem sich **winutils.exe** befindet, und lassen Sie dabei `bin` weg. Beispielsweise `c:\hadoop`.
    * Fügen Sie der PATH-Umgebungsvariable `%HADOOP_HOME%\bin` hinzu.

Überprüfen Sie, ob Sie `dotnet`, `java`, `mvn` und `spark-shell` über die Befehlszeile ausführen können, bevor Sie mit dem nächsten Abschnitt fortfahren.

## <a name="download-the-microsoftsparkworker-release"></a>Herunterladen des Microsoft.Spark.Worker-Release

1. Laden Sie das [Microsoft.Spark.Worker](https://github.com/dotnet/spark/releases)-Release von der GitHub-Releaseseite für .NET für Apache Spark auf Ihren lokalen Computer herunter. Beispielsweise können Sie für den Download der Datei den Pfad `c:\bin\Microsoft.Spark.Worker\` verwenden.

2. Erstellen Sie eine [neue Umgebungsvariable](https://www.java.com/en/download/help/path.xml) mit dem Namen `DOTNET_WORKER_DIR`, und legen Sie diese auf das Verzeichnis fest, in dem sich die heruntergeladene und extrahierte **Microsoft.Spark.Worker**-Datei befindet. Beispielsweise `c:\bin\Microsoft.Spark.Worker`.

## <a name="clone-the-net-for-apache-spark-github-repo"></a>Klonen des GitHub-Repositorys von .NET für Apache Spark

Verwenden Sie den folgenden [GitBash](https://gitforwindows.org/)-Befehl, um das .NET für Apache Spark-Repository auf Ihrem Computer zu klonen.

```bash
git clone https://github.com/dotnet/spark.git c:\github\dotnet-spark
```

## <a name="write-a-net-for-apache-spark-app"></a>Programmieren einer .NET für Apache Spark-App

1. Öffnen Sie **Visual Studio**, und navigieren Sie zu **Datei > Neues Projekt erstellen > Konsolen-App (.NET Core)** . Nennen Sie die Anwendung **HelloSpark**.

2. Installieren Sie das [NuGet-Paket Microsoft.Spark](https://www.nuget.org/profiles/spark). Weitere Informationen zum Installieren von NuGet-Paketen finden Sie unter [Installationsmöglichkeiten für NuGet-Pakete](https://docs.microsoft.com/nuget/consume-packages/ways-to-install-a-package).

3. Öffnen Sie im **Projektmappen-Explorer** die Datei **Program.cs**, und fügen Sie den folgenden C#-Code ein:

   ```csharp
     var spark = SparkSession.Builder().GetOrCreate();
     var df = spark.Read().Json("people.json");
     df.Show();
   ```

4. Erstellen Sie die Projektmappe.

## <a name="run-your-net-for-apache-spark-app"></a>Ausführen der .NET für Apache Spark-App

1. Öffnen Sie **PowerShell**, und legen Sie für das Verzeichnis den Ordner fest, in dem Ihre App gespeichert ist.

   ```powershell
   cd <your-app-output-directory>
   ```

2. Erstellen Sie eine Datei mit dem Namen **project.json** und dem folgendem Inhalt:

   ```json
   {"name":"Michael"}
   {"name":"Andy", "age":30}
   {"name":"Justin", "age":19}
   ```

3. Verwenden Sie den folgenden PowerShell-Befehl, um die App auszuführen:

   ```powershell
    spark-submit `
    --class org.apache.spark.deploy.dotnet.DotnetRunner `
    --master local `
    microsoft-spark-2.4.x-<version>.jar `
    dotnet HelloSpark.dll
    ```

Herzlichen Glückwunsch! Sie haben eine .NET für Apache Spark-App erfolgreich erstellt und ausgeführt.

## <a name="next-steps"></a>Nächste Schritte

In diesem Tutorial haben Sie gelernt, wie die folgenden Aufgaben ausgeführt werden:
> [!div class="checklist"]
>
> * Vorbereiten der Windows-Umgebung für .NET für Apache Spark
> * Herunterladen von **Microsoft.Spark.Worker**
> * Erstellen und Ausführen einer einfachen .NET für Apache Spark-Anwendung

Weitere Informationen finden Sie auf der Ressourcenseite.
> [!div class="nextstepaction"]
> [Ressourcen für .NET für Apache Spark](../resources/index.md)
