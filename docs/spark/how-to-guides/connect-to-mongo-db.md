---
title: Herstellen einer Verbindung zwischen .NET für Apache Spark und MongoDB
description: Hier erfahren Sie, wie Sie über Ihre .NET für Apache Spark-Anwendung eine Verbindung mit einer MongoDB-Instanz herstellen.
ms.author: nidutta
author: Niharikadutta
ms.date: 10/09/2020
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: 945e494e8a027d438bf4659d989da6033a13f6f0
ms.sourcegitcommit: 34968a61e9bac0f6be23ed6ffb837f52d2390c85
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "94687602"
---
# <a name="connect-net-for-apache-spark-to-mongodb"></a>Herstellen einer Verbindung zwischen .NET für Apache Spark und MongoDB

In diesem Artikel erfahren Sie, wie Sie über Ihre .NET für Apache Spark-Anwendung eine Verbindung mit einer MongoDB-Instanz herstellen.

## <a name="prerequisites"></a>Voraussetzungen

1. Sie benötigen einen aktiven MongoDB-Server mit einer [Datenbank und hinzugefügten Sammlungen](https://docs.mongodb.com/manual/core/databases-and-collections/) (Laden Sie [diesen Communityserver](https://www.mongodb.com/try/download/community) für einen lokalen Server herunter oder testen Sie [MongoDB Atlas](https://www.mongodb.com/cloud/atlas) für einen MongoDB-Clouddienst).

## <a name="set-up-your-mongodb-instance"></a>Einrichten Ihrer MongoDB-Instanz

Damit .NET für Apache Spark mit Ihrer MongoDB-Instanz kommunizieren kann, müssen Sie wie folgt sicherstellen, dass sie ordnungsgemäß eingerichtet ist:

1. Erstellen Sie einen Benutzernamen und ein Kennwort für die Verbindung Ihrer Anwendung, und gewähren Sie dem Benutzer die erforderlichen Berechtigungen/Rollen mithilfe des folgenden Befehls über die Mongo-Shell:

    ```bash
    use database
    db.createUser(
      {
        user: "mySparkUser",
        pwd: "<password>",
        roles: [ { role: "userAdminAnyDatabase", db: "admin" }, "readWriteAnyDatabase" ]
      }
    )
    ```

2. Stellen Sie sicher, dass die IP-Adresse des Computers, auf dem Ihre .NET für Apache Spark-Anwendung ausgeführt wird, sich in der Whitelist des MongoDB-Servers befindet, damit die Verbindung hergestellt werden kann. Weitere Informationen hierzu finden Sie in [diesem Leitfaden](https://docs.atlas.mongodb.com/security/add-ip-address-to-list/).

## <a name="configure-your-net-for-apache-spark-application"></a>Konfigurieren Ihrer .NET für Apache Spark-Anwendung

1. Legen Sie die folgenden Variablen zur Konfiguration Ihrer Anwendung fest, damit sie mit der MongoDB-Instanz kommunizieren und aus einer Sammlung lesen kann.
    1. **authURI:** Hierbei handelt es sich um die Verbindungszeichenfolge, die Ihre Anwendung zum Herstellen einer Verbindung mit der erforderlichen MongoDB-Instanz autorisiert. Das Format lautet wie folgt:

        ```
        "mongodb+srv://<username>:<password>@<cluster_address>/<database>.<collection>"
        ```

    2. **username** (Benutzername): Hierbei handelt es sich um den Benutzernamen des Kontos, das Sie in Schritt 1 des vorherigen Abschnitts erstellt haben.
    3. **password** (Kennwort): Hierbei handelt es sich um das Kennwort des erstellten Benutzerkontos.
    4. **cluster_address** (Gruppierte Adresse): Hierbei handelt es sich um den Hostnamen bzw. die Adresse Ihres MongoDB-Clusters.
    5. **database** (Datenbank): Hierbei handelt es sich um die MongoDB-Datenbank, mit der Sie eine Verbindung herstellen möchten.
    6. **collection** (Sammlung): Hierbei handelt es sich um die MongoDB-Sammlung, die Sie lesen möchten. (In diesem Beispiel wird die Standardbeispieldatei [`people.json`](https://github.com/apache/spark/blob/master/examples/src/main/resources/people.json) verwendet, die in jeder Installation von Apache Spark enthalten ist.)

2. Verwenden Sie das Format `spark.Read()` für `com.mongodb.spark.sql.DefaultSource` wie im folgenden Codeausschnitt gezeigt:

    ```csharp
    class Program
    {
        static void Main()
        {
            var authURI = "mongodb+srv://<username>:<password>@<cluster_address>/<database>.<collection>?retryWrites=true&w=majority";
            SparkSession spark = SparkSession
                .Builder()
                .AppName("Connect to Mongo DB example")
                .Config("spark.mongodb.input.uri", authURI)
                .GetOrCreate();

            DataFrame df = spark.Read().Format("com.mongodb.spark.sql.DefaultSource").Load();
            df.PrintSchema();
            df.Show();
            spark.Stop();
        }
    }
    ```

## <a name="run-your-application"></a>Ausführen der Anwendung

Zum Ausführen Ihrer .NET für Apache Spark-Anwendung sollten Sie das `mongo-spark-connector`-Modul als Teil der Builddefinition in Ihrem Spark-Projekt mithilfe von `libraryDependency` in `build.sbt` für sbt-Projekte definieren. Für Spark-Umgebungen wie `spark-submit` (oder `spark-shell`) sollten Sie die Befehlszeilenoption `--packages` wie folgt verwenden:

```bash
spark-submit --master local --packages org.mongodb.spark:mongo-spark-connector_2.12:3.0.0 --class org.apache.spark.deploy.dotnet.DotnetRunner microsoft-spark-<spark_majorversion-spark_minorversion>_<scala_majorversion.scala_minorversion>-<spark_dotnet_version>.jar yourApp.exe
```

> [!NOTE]
> Stellen Sie sicher, dass Sie die Paketversion verwenden, die der ausgeführten Version von Spark entspricht.

Das Ergebnis wird wie im folgenden DataFrame (`df`) angezeigt:

```text
+--------------------+----+-------+
|                 _id| age|   name|
+--------------------+----+-------+
|[5f7c28438029a134...|null|Michael|
|[5f7c287f8029a134...|  30|   Andy|
|[5f7c289a8029a134...|  19| Justin|
+--------------------+----+-------+
```
