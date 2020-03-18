---
title: Bereitstellen des .NET für Apache Spark-Workers und für benutzerdefinierte Funktionsbinärdateien
description: Erfahren Sie, wie Sie den .NET für Apache Spark-Worker und benutzerdefinierte Funktionsbinärdateien bereitstellen.
ms.date: 01/21/2019
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: f373ccee398149adcadeac91f02d9896214706b0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "79187598"
---
# <a name="deploy-net-for-apache-spark-worker-and-user-defined-function-binaries"></a>Bereitstellen des .NET für Apache Spark-Workers und für benutzerdefinierte Funktionsbinärdateien

Diese Anleitung enthält allgemeine Anweisungen für die Bereitstellung des .NET für Apache Spark-Workers und für benutzerdefinierte Funktionsbinärdateien. Sie lernen, welche Umgebungsvariablen eingerichtet werden müssen, sowie einige häufig verwendete Parameter zum Starten von Anwendungen mit `spark-submit`.

## <a name="configurations"></a>Konfigurationen
Die Konfigurationen zeigen die allgemeinen Umgebungsvariablen und Parametereinstellungen, um den .NET für Apache Spark-Worker und benutzerdefinierte Funktionsbinärdateien bereitzustellen.

### <a name="environment-variables"></a>Umgebungsvariablen
Bei der Bereitstellung von Workern und dem Schreiben von UDFs gibt es einige häufig verwendete Umgebungsvariablen, die Sie möglicherweise festlegen müssen:

| Umgebungsvariable         | Beschreibung
| :--------------------------- | :----------
| DOTNET_WORKER_DIR            | Hierbei handelt es sich um den Pfad, in dem die <code>Microsoft.Spark.Worker</code>-Binärdatei generiert wurde.</br>Dieser wird vom Spark-Treiber verwendet und wird an die Spark-Executors weitergeleitet. Wenn diese Variable nicht eingerichtet ist, suchen die Spark-Executors den in der <code>PATH</code>-Umgebungsvariablen angegebenen Pfad.</br>_z. B. "C:\bin\Microsoft.Spark.Worker"_
| DOTNET_ASSEMBLY_SEARCH_PATHS | Hierbei handelt es sich um durch Trennzeichen getrennte Pfade, in denen <code>Microsoft.Spark.Worker</code> Assemblys lädt.</br>Beachten Sie, dass, wenn ein Pfad mit "." beginnt, das Arbeitsverzeichnis vorangestellt wird. Im **YARN-Modus** würde "." das Arbeitsverzeichnis des Containers darstellen.</br>_z. B. "C:\Users\\&lt;Benutzername&gt;\\&lt;mysparkapp&gt;\bin\Debug\\&lt;dotnet-Version&gt;"_
| DOTNET_WORKER_DEBUG          | Wenn Sie <a href="https://github.com/dotnet/spark/blob/master/docs/developer-guide.md#debugging-user-defined-function-udf">ein UDF debuggen</a> wollen, legen Sie diese Umgebungsvariable auf <code>1</code> fest, bevor Sie <code>spark-submit</code> ausführen.

### <a name="parameter-options"></a>Parameteroptionen
Sobald die Spark-Anwendung [gebündelt](https://spark.apache.org/docs/latest/submitting-applications.html#bundling-your-applications-dependencies) ist, können Sie diese mit `spark-submit` starten. In der folgenden Tabelle werden einige der häufig verwendeten Optionen aufgeführt:

| Parametername        | Beschreibung
| :---------------------| :----------
| --class               | Dies ist der Einstiegspunkt für Ihre Anwendung.</br>_z. B. org.apache.spark.deploy.dotnet.DotnetRunner_
| --master              | Dies ist die <a href="https://spark.apache.org/docs/latest/submitting-applications.html#master-urls">master-URL</a> für den Cluster.</br>_z. B. YARN_
| --deploy-mode         | Dieser Parameter gibt an, ob Ihr Treiber auf den Workerknoten (<code>cluster</code>) oder lokal als externer Client (<code>client</code>) bereitgestellt werden soll.</br>Standardwert: <code>client</code>
| --conf                | Dies ist eine beliebige Spark-Konfigurationseigenschaft im <code>key=value</code>-Format.</br>_z. B. spark.yarn.appMasterEnv.DOTNET_WORKER_DIR=.\worker\Microsoft.Spark.Worker_
| --files               | Dies ist eine durch Trennzeichen getrennte Liste von Dateien, die im Arbeitsverzeichnis jedes Executors platziert werden sollen.<br/><ul><li>Bitte beachten Sie, dass diese Option nur für den YARN-Modus anwendbar ist.</li><li>Diese unterstützt ähnlich wie bei Hadoop die Angabe von Dateinamen mit #.</br></ul>_z. B. <code>myLocalSparkApp.dll#appSeen.dll</code>. Ihre Anwendung sollte den Namen als <code>appSeen.dll</code> verwenden, um auf <code>myLocalSparkApp.dll</code> zu verweisen, wenn sie unter YARN ausgeführt wird._</li>
| --archives          | Dies ist eine durch Trennzeichen getrennte Liste von Archiven, die im Arbeitsverzeichnis jedes Executors extrahiert werden sollen.</br><ul><li>Bitte beachten Sie, dass diese Option nur für den YARN-Modus anwendbar ist.</li><li>Diese unterstützt ähnlich wie bei Hadoop die Angabe von Dateinamen mit #.</br></ul>_z. B. <code>hdfs://&lt;path to your worker file&gt;/Microsoft.Spark.Worker.zip#worker</code>. Hiermit wird die ZIP-Datei in den <code>worker</code>-Ordner kopiert und extrahiert._</li>
| application-jar       | Dies ist der Pfad zu einer gebündelten JAR-Datei mit Ihrer Anwendung und allen Abhängigkeiten.</br>_z. B. hdfs://&lt;Pfad-zu-Ihrer-JAR-Datei&gt;/microsoft-spark-&lt;Version&gt;.jar_
| application-arguments | Dies sind Argumente, die an die Hauptmethode Ihrer Hauptklasse übergeben werden, falls diese vorhanden sind.</br>_z. B. hdfs://&lt;Pfad-zu-Ihrer-App&gt;/&lt;Ihre-App&gt;.zip &lt;Ihr-App-Name&gt; &lt;App-Argumente&gt;_

> [!NOTE]
> Geben Sie beim Start von Anwendungen mit `spark-submit` alle `--options`-Parameter vor `application-jar` an, sonst werden sie ignoriert. Weitere Informationen finden Sie unter [`spark-submit`-Optionen](https://spark.apache.org/docs/latest/submitting-applications.html) und [Details zur Ausführung von Spark unter YARN](https://spark.apache.org/docs/latest/running-on-yarn.html).

## <a name="frequently-asked-questions"></a>Häufig gestellte Fragen
### <a name="when-i-run-a-spark-app-with-udfs-i-get-a-filenotfoundexception-error-what-should-i-do"></a>Wenn ich eine Spark-App mit UDFs ausführe, erhalte ich den Fehler `FileNotFoundException'. Wie sollte ich vorgehen?
> **Fehler:** [Error] [TaskRunner] [0] ProcessStream() mit Ausnahme fehlgeschlagen: System.IO.FileNotFoundException: Assembly 'mySparkApp, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null' Datei nicht gefunden: 'mySparkApp.dll'

**Antwort:** Überprüfen Sie, ob die `DOTNET_ASSEMBLY_SEARCH_PATHS`-Umgebungsvariable korrekt festgelegt ist. Diese sollte der Pfad sein, der `mySparkApp.dll` enthält.

### <a name="after-i-upgraded-my-net-for-apache-spark-version-and-reset-the-dotnet_worker_dir-environment-variable-why-do-i-still-get-the-following-ioexception-error"></a>Nachdem ich die .NET für Apache Spark-Version aktualisiert und die `DOTNET_WORKER_DIR`-Umgebungsvariable zurückgesetzt habe, erhalte ich immer noch die folgende `IOException`-Fehlermeldung. Warum?
> **Fehler:** Lost task 0.0 in stage 11.0 (TID 24, Localhost, Executor Treiber): java.io.IOException: Programm kann nicht ausgeführt werden "Microsoft.Spark.Worker.exe": CreateProcess error=2, Das System kann die angegebene Datei nicht finden.

**Antwort:** Versuchen Sie zuerst, Ihr PowerShell-Fenster (oder andere Befehlsfenster) neu zu starten, damit es die neuesten Werte der Umgebungsvariablen annehmen kann. Starten Sie dann Ihr Programm.

### <a name="after-submitting-my-spark-application-i-get-the-error-systemtypeloadexception-could-not-load-type-systemruntimeremotingcontextscontext"></a>Nachdem ich meine Spark-Anwendung übermittelt habe, erhalte ich die Fehlermeldung `System.TypeLoadException: Could not load type 'System.Runtime.Remoting.Contexts.Context'`.
> **Fehler:** [Error] [TaskRunner] [0] ProcessStream() mit Ausnahme fehlgeschlagen: System.TypeLoadException: Der Typ konnte nicht geladen werden 'System.Runtime.Remoting.Contexts.Context' from assembly 'mscorlib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=...'.

**Antwort:** Überprüfen Sie die `Microsoft.Spark.Worker`-Version, die Sie verwenden. Es gibt zwei Versionen: **.NET Framework 4.6.1** und **.NET Core 2.1.x**. In diesem Fall sollte `Microsoft.Spark.Worker.net461.win-x64-<version>` (zum [Herunterladen](https://github.com/dotnet/spark/releases)) verwendet werden, da `System.Runtime.Remoting.Contexts.Context` nur für .NET Framework gilt.

### <a name="how-do-i-run-my-spark-application-with-udfs-on-yarn-which-environment-variables-and-parameters-should-i-use"></a>Wie führe ich meine Spark-Anwendung mit UDFs unter YARN aus? Welche Umgebungsvariablen und Parameter sollte ich verwenden?

**Antwort:** Die Umgebungsvariablen sollten als `spark.yarn.appMasterEnv.[EnvironmentVariableName]` angegeben werden, um die Spark-Anwendung auf YARN zu starten. Weiteres finden Sie unten im Beispiel, in dem `spark-submit` verwendet wird:

```powershell
spark-submit \
--class org.apache.spark.deploy.dotnet.DotnetRunner \
--master yarn \
--deploy-mode cluster \
--conf spark.yarn.appMasterEnv.DOTNET_WORKER_DIR=./worker/Microsoft.Spark.Worker-<version> \
--conf spark.yarn.appMasterEnv.DOTNET_ASSEMBLY_SEARCH_PATHS=./udfs \
--archives hdfs://<path to your files>/Microsoft.Spark.Worker.net461.win-x64-<version>.zip#worker,hdfs://<path to your files>/mySparkApp.zip#udfs \
hdfs://<path to jar file>/microsoft-spark-2.4.x-<version>.jar \
hdfs://<path to your files>/mySparkApp.zip mySparkApp
```

## <a name="next-steps"></a>Nächste Schritte

* [Erste Schritte mit .NET für Apache Spark](../tutorials/get-started.md)
* [Debuggen einer .NET für Apache Spark-Anwendung unter Windows](../how-to-guides/debug.md)
