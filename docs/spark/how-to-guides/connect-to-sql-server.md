---
title: Herstellen einer Verbindung zwischen .NET für Apache Spark und SQL Server
description: Hier erfahren Sie, wie Sie über Ihre .NET für Apache Spark-Anwendung eine Verbindung mit einer SQL Server-Instanz herstellen.
ms.author: nidutta
author: Niharikadutta
ms.date: 10/09/2020
ms.topic: conceptual
ms.custom: mvc,how-to
ms.openlocfilehash: 1fecd796aeefd6c5681c4c2ea623e89f3a5a3c1d
ms.sourcegitcommit: 30a686fd4377fe6472aa04e215c0de711bc1c322
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2020
ms.locfileid: "94439533"
---
# <a name="connect-net-for-apache-spark-to-sql-server"></a><span data-ttu-id="7fdf4-103">Herstellen einer Verbindung zwischen .NET für Apache Spark und SQL Server</span><span class="sxs-lookup"><span data-stu-id="7fdf4-103">Connect .NET for Apache Spark to SQL Server</span></span>

<span data-ttu-id="7fdf4-104">In diesem Artikel erfahren Sie, wie Sie über Ihre [.NET für Apache Spark](https://github.com/dotnet/spark)-Anwendung eine Verbindung mit einer SQL Server-Instanz herstellen.</span><span class="sxs-lookup"><span data-stu-id="7fdf4-104">In this article, you learn how to connect to an SQL server instance from your [.NET for Apache Spark](https://github.com/dotnet/spark) application.</span></span>

## <a name="configure-sql-server-to-grant-your-application-access"></a><span data-ttu-id="7fdf4-105">Konfigurieren von SQL Server für das Gewähren von Zugriff für Ihre Anwendung</span><span class="sxs-lookup"><span data-stu-id="7fdf4-105">Configure SQL Server to grant your application access</span></span>

1. <span data-ttu-id="7fdf4-106">Fügen Sie Ihrer SQL Server-Instanz einen Benutzer und ein Kennwort für die Anmeldung hinzu, und wählen Sie dabei die SQL Server-Authentifizierung aus.</span><span class="sxs-lookup"><span data-stu-id="7fdf4-106">Add a login user and password choosing SQL Server authentication to your SQL Server instance.</span></span>
2. <span data-ttu-id="7fdf4-107">Weisen Sie diesem Anmeldebenutzer die erforderlichen Berechtigungen auf entsprechender Datenbankebene zu. Sehen Sie sich dazu folgendes Beispiel an:</span><span class="sxs-lookup"><span data-stu-id="7fdf4-107">Give that login user necessary permissions at the relevant database level as shown below:</span></span>

    ![SQL Server-Berechtigungen](./media/connect-external-sources/SqlServerAuth.png)

3. <span data-ttu-id="7fdf4-109">Sorgen Sie dafür, dass der Standardport für SQL Server (`1433`) für die Firewall zugelassen ist.</span><span class="sxs-lookup"><span data-stu-id="7fdf4-109">Make sure the default port for SQL Server `1433` is allowed through the firewall.</span></span>
4. <span data-ttu-id="7fdf4-110">Öffnen Sie den Konfigurations-Manager für SQL, um TCP/IP über die Netzwerkkonfiguration zu aktivieren. Sehen Sie sich dazu das Beispiel unten an:</span><span class="sxs-lookup"><span data-stu-id="7fdf4-110">Open SQL configure manager to enable TCP/IP through the network configuration as shown below:</span></span>

    ![Aktivieren von TCP/IP in SQL Server](./media/connect-external-sources/SqlServerTCPIP.png)

    <span data-ttu-id="7fdf4-112">Notieren Sie sich auch den Wert für **Alle überwachen** in obiger Registerkarte unter **Protokoll**.</span><span class="sxs-lookup"><span data-stu-id="7fdf4-112">Also note the value of **Listen All** in above tab under **Protocol**.</span></span>

5. <span data-ttu-id="7fdf4-113">Konfigurieren Sie Port 1433 als TCP/IP-Port für alle erforderlichen IP-Adressen, wenn `Listen All` auf `No` festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="7fdf4-113">Configure the TCP/IP port to 1433 for all required IP addresses if the `Listen All` is set to `No`.</span></span> <span data-ttu-id="7fdf4-114">Legen Sie andernfalls den TCP-Port in IPAll fest.</span><span class="sxs-lookup"><span data-stu-id="7fdf4-114">Otherwise, set the TCP Port in IPAll.</span></span>

    ![TCP/IP-Port in SQL Server](./media/connect-external-sources/SQLServerTCPIIPPort.png)

## <a name="connect-to-sql-server-from-your-application"></a><span data-ttu-id="7fdf4-116">Herstellen einer Verbindung von Ihrer Anwendung zu SQL Server</span><span class="sxs-lookup"><span data-stu-id="7fdf4-116">Connect to SQL Server from your application</span></span>

1. <span data-ttu-id="7fdf4-117">Verwenden Sie den Microsoft JDBC-Treiber für SQL Server, um für Datenbankverbindungen über Ihre Anwendungen zu sorgen. Der Download ist über [diese offizielle Website](/sql/connect/jdbc/download-microsoft-jdbc-driver-for-sql-server?view=sql-server-ver15) möglich.</span><span class="sxs-lookup"><span data-stu-id="7fdf4-117">Use the Microsoft JDBC Driver for SQL Server to provide database connectivity through your application (download from [this official website](/sql/connect/jdbc/download-microsoft-jdbc-driver-for-sql-server?view=sql-server-ver15)).</span></span>
2. <span data-ttu-id="7fdf4-118">Legen Sie die folgenden Konfigurationen fest, um eine Verbindung zur SQL Server-Instanz und zur entsprechenden Datenbank in Ihrer Anwendung herzustellen:</span><span class="sxs-lookup"><span data-stu-id="7fdf4-118">Set the following configurations to connect to the SQL server instance and database from your application:</span></span>
    1. <span data-ttu-id="7fdf4-119">**connection_url:** Hierbei handelt es sich um die URL, die zum Herstellen einer Verbindung zur SQL Server-Instanz bzw. zur entsprechenden Datenbank genutzt wird. Sie weist das folgende Format auf:</span><span class="sxs-lookup"><span data-stu-id="7fdf4-119">**connection_url**: This is the URL used to connect to the SQL server instance/database and has the following format:</span></span>

        ```
        jdbc:sqlserver://<SQL_server_IP_address>:1433;instanceName=<instance_name>;databaseName=<database_name>;
        ```

    2. <span data-ttu-id="7fdf4-120">**dbtable:** Hierbei handelt es sich um den Namen der Tabelle, auf die zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="7fdf4-120">**dbtable**: Name of table being accessed.</span></span>
    3. <span data-ttu-id="7fdf4-121">**user:** Hierbei handelt es sich um den Benutzer für die Anmeldung aus Schritt 1 für die Konfiguration von SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7fdf4-121">**user**: Login user set up in Step 1 of configuring the SQL server.</span></span>
    4. <span data-ttu-id="7fdf4-122">**password:** Hierbei handelt es sich um das Kennwort für die Anmeldung aus Schritt 1 für die Konfiguration von SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7fdf4-122">**password**: Password of user set up in Step 1 of configuring the SQL server.</span></span>
3. <span data-ttu-id="7fdf4-123">Verwenden Sie obige Konfiguration in Ihrem Anwendungscode, um die Daten aus einer Tabelle wie unten gezeigt zu lesen:</span><span class="sxs-lookup"><span data-stu-id="7fdf4-123">Use the above configuration in your application code to read the data from a table as shown below:</span></span>

    ```csharp
    static void Main()
    {
        SparkSession spark = SparkSession
            .Builder()
            .AppName("Connect to SQL Server")
            .GetOrCreate();

        string connection_url = "<URL to connect to SQL server instance>";
        string dbtable = "<database table to access>";
        string user = "<Login user name>";
        string password = "<Login user password>";

        DataFrame jdbcDF = spark.Read()
            .Format("jdbc")
            .Option("driver", "com.microsoft.sqlserver.jdbc.SQLServerDriver")
            .Option("url", connection_url)
            .Option("dbtable", dbtable)
            .Option("user", user)
            .Option("password", password).Load();
        jdbcDF.Show(); // Displays the content of the SQL table as a DataFrame
    }
    ```
