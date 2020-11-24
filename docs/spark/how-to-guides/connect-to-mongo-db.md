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
# <a name="connect-net-for-apache-spark-to-mongodb"></a><span data-ttu-id="8a243-103">Herstellen einer Verbindung zwischen .NET für Apache Spark und MongoDB</span><span class="sxs-lookup"><span data-stu-id="8a243-103">Connect .NET for Apache Spark to MongoDB</span></span>

<span data-ttu-id="8a243-104">In diesem Artikel erfahren Sie, wie Sie über Ihre .NET für Apache Spark-Anwendung eine Verbindung mit einer MongoDB-Instanz herstellen.</span><span class="sxs-lookup"><span data-stu-id="8a243-104">In this article, you learn how to connect to a MongoDB instance from your .NET for Apache Spark application.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8a243-105">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="8a243-105">Prerequisites</span></span>

1. <span data-ttu-id="8a243-106">Sie benötigen einen aktiven MongoDB-Server mit einer [Datenbank und hinzugefügten Sammlungen](https://docs.mongodb.com/manual/core/databases-and-collections/) (Laden Sie [diesen Communityserver](https://www.mongodb.com/try/download/community) für einen lokalen Server herunter oder testen Sie [MongoDB Atlas](https://www.mongodb.com/cloud/atlas) für einen MongoDB-Clouddienst).</span><span class="sxs-lookup"><span data-stu-id="8a243-106">Have a MongoDB server up and running with a [database and some collection](https://docs.mongodb.com/manual/core/databases-and-collections/) added to it (Download [this community server](https://www.mongodb.com/try/download/community) for a local server or you can try [MongoDB Atlas](https://www.mongodb.com/cloud/atlas) for a cloud MongoDB service.)</span></span>

## <a name="set-up-your-mongodb-instance"></a><span data-ttu-id="8a243-107">Einrichten Ihrer MongoDB-Instanz</span><span class="sxs-lookup"><span data-stu-id="8a243-107">Set up your MongoDB instance</span></span>

<span data-ttu-id="8a243-108">Damit .NET für Apache Spark mit Ihrer MongoDB-Instanz kommunizieren kann, müssen Sie wie folgt sicherstellen, dass sie ordnungsgemäß eingerichtet ist:</span><span class="sxs-lookup"><span data-stu-id="8a243-108">In order to get .NET for Apache Spark to talk to your MongoDB instance you need to make sure it is set up correctly by doing the following:</span></span>

1. <span data-ttu-id="8a243-109">Erstellen Sie einen Benutzernamen und ein Kennwort für die Verbindung Ihrer Anwendung, und gewähren Sie dem Benutzer die erforderlichen Berechtigungen/Rollen mithilfe des folgenden Befehls über die Mongo-Shell:</span><span class="sxs-lookup"><span data-stu-id="8a243-109">Create a username and password for your application to connect through, and give the user the necessary permissions/roles using the following command through mongo shell:</span></span>

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

2. <span data-ttu-id="8a243-110">Stellen Sie sicher, dass die IP-Adresse des Computers, auf dem Ihre .NET für Apache Spark-Anwendung ausgeführt wird, sich in der Whitelist des MongoDB-Servers befindet, damit die Verbindung hergestellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="8a243-110">Make sure the IP address of the machine your .NET for Apache Spark application is running on is whitelisted for the MongoDB server to be able to connect to.</span></span> <span data-ttu-id="8a243-111">Weitere Informationen hierzu finden Sie in [diesem Leitfaden](https://docs.atlas.mongodb.com/security/add-ip-address-to-list/).</span><span class="sxs-lookup"><span data-stu-id="8a243-111">You can refer to [this guide](https://docs.atlas.mongodb.com/security/add-ip-address-to-list/) to learn how to do that.</span></span>

## <a name="configure-your-net-for-apache-spark-application"></a><span data-ttu-id="8a243-112">Konfigurieren Ihrer .NET für Apache Spark-Anwendung</span><span class="sxs-lookup"><span data-stu-id="8a243-112">Configure your .NET for Apache Spark application</span></span>

1. <span data-ttu-id="8a243-113">Legen Sie die folgenden Variablen zur Konfiguration Ihrer Anwendung fest, damit sie mit der MongoDB-Instanz kommunizieren und aus einer Sammlung lesen kann.</span><span class="sxs-lookup"><span data-stu-id="8a243-113">Have the following variables set to configure your application to talk to the MongoDB instance and read from a collection.</span></span>
    1. <span data-ttu-id="8a243-114">**authURI:** Hierbei handelt es sich um die Verbindungszeichenfolge, die Ihre Anwendung zum Herstellen einer Verbindung mit der erforderlichen MongoDB-Instanz autorisiert.</span><span class="sxs-lookup"><span data-stu-id="8a243-114">**authURI**: "Connection string authorizing your application to connect to the required MongoDB instance".</span></span> <span data-ttu-id="8a243-115">Das Format lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="8a243-115">The format for that is as follows:</span></span>

        ```
        "mongodb+srv://<username>:<password>@<cluster_address>/<database>.<collection>"
        ```

    2. <span data-ttu-id="8a243-116">**username** (Benutzername): Hierbei handelt es sich um den Benutzernamen des Kontos, das Sie in Schritt 1 des vorherigen Abschnitts erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="8a243-116">**username**: Username of the account you created in Step 1 of the previous section</span></span>
    3. <span data-ttu-id="8a243-117">**password** (Kennwort): Hierbei handelt es sich um das Kennwort des erstellten Benutzerkontos.</span><span class="sxs-lookup"><span data-stu-id="8a243-117">**password**: Password of the user account created</span></span>
    4. <span data-ttu-id="8a243-118">**cluster_address** (Gruppierte Adresse): Hierbei handelt es sich um den Hostnamen bzw. die Adresse Ihres MongoDB-Clusters.</span><span class="sxs-lookup"><span data-stu-id="8a243-118">**cluster_address**: hostname/address of your MongoDB cluster</span></span>
    5. <span data-ttu-id="8a243-119">**database** (Datenbank): Hierbei handelt es sich um die MongoDB-Datenbank, mit der Sie eine Verbindung herstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="8a243-119">**database**: The MongoDB database you want to connect to</span></span>
    6. <span data-ttu-id="8a243-120">**collection** (Sammlung): Hierbei handelt es sich um die MongoDB-Sammlung, die Sie lesen möchten.</span><span class="sxs-lookup"><span data-stu-id="8a243-120">**collection**: The MongoDB collection you want to read.</span></span> <span data-ttu-id="8a243-121">(In diesem Beispiel wird die Standardbeispieldatei [`people.json`](https://github.com/apache/spark/blob/master/examples/src/main/resources/people.json) verwendet, die in jeder Installation von Apache Spark enthalten ist.)</span><span class="sxs-lookup"><span data-stu-id="8a243-121">(For this example we use the standard [`people.json`](https://github.com/apache/spark/blob/master/examples/src/main/resources/people.json) example file provided with every Apache Spark installation.)</span></span>

2. <span data-ttu-id="8a243-122">Verwenden Sie das Format `spark.Read()` für `com.mongodb.spark.sql.DefaultSource` wie im folgenden Codeausschnitt gezeigt:</span><span class="sxs-lookup"><span data-stu-id="8a243-122">Use the `com.mongodb.spark.sql.DefaultSource` format is `spark.Read()` as shown below in a simple code snippet:</span></span>

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

## <a name="run-your-application"></a><span data-ttu-id="8a243-123">Ausführen der Anwendung</span><span class="sxs-lookup"><span data-stu-id="8a243-123">Run your application</span></span>

<span data-ttu-id="8a243-124">Zum Ausführen Ihrer .NET für Apache Spark-Anwendung sollten Sie das `mongo-spark-connector`-Modul als Teil der Builddefinition in Ihrem Spark-Projekt mithilfe von `libraryDependency` in `build.sbt` für sbt-Projekte definieren.</span><span class="sxs-lookup"><span data-stu-id="8a243-124">In order to run your .NET for Apache Spark application, you should define the `mongo-spark-connector` module as part of the build definition in your Spark project, using `libraryDependency` in `build.sbt` for sbt projects.</span></span> <span data-ttu-id="8a243-125">Für Spark-Umgebungen wie `spark-submit` (oder `spark-shell`) sollten Sie die Befehlszeilenoption `--packages` wie folgt verwenden:</span><span class="sxs-lookup"><span data-stu-id="8a243-125">For Spark environments such as `spark-submit` (or `spark-shell`) you should use the `--packages` command-line option like so:</span></span>

```bash
spark-submit --master local --packages org.mongodb.spark:mongo-spark-connector_2.12:3.0.0 --class org.apache.spark.deploy.dotnet.DotnetRunner microsoft-spark-<spark_majorversion-spark_minorversion>_<scala_majorversion.scala_minorversion>-<spark_dotnet_version>.jar yourApp.exe
```

> [!NOTE]
> <span data-ttu-id="8a243-126">Stellen Sie sicher, dass Sie die Paketversion verwenden, die der ausgeführten Version von Spark entspricht.</span><span class="sxs-lookup"><span data-stu-id="8a243-126">Make sure to include the package version in accordance with the version of Spark being run.</span></span>

<span data-ttu-id="8a243-127">Das Ergebnis wird wie im folgenden DataFrame (`df`) angezeigt:</span><span class="sxs-lookup"><span data-stu-id="8a243-127">The result as displayed is the DataFrame (`df`) as shown below:</span></span>

```text
+--------------------+----+-------+
|                 _id| age|   name|
+--------------------+----+-------+
|[5f7c28438029a134...|null|Michael|
|[5f7c287f8029a134...|  30|   Andy|
|[5f7c289a8029a134...|  19| Justin|
+--------------------+----+-------+
```
