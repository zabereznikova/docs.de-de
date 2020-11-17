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
# <a name="connect-net-for-apache-spark-to-sql-server"></a>Herstellen einer Verbindung zwischen .NET für Apache Spark und SQL Server

In diesem Artikel erfahren Sie, wie Sie über Ihre [.NET für Apache Spark](https://github.com/dotnet/spark)-Anwendung eine Verbindung mit einer SQL Server-Instanz herstellen.

## <a name="configure-sql-server-to-grant-your-application-access"></a>Konfigurieren von SQL Server für das Gewähren von Zugriff für Ihre Anwendung

1. Fügen Sie Ihrer SQL Server-Instanz einen Benutzer und ein Kennwort für die Anmeldung hinzu, und wählen Sie dabei die SQL Server-Authentifizierung aus.
2. Weisen Sie diesem Anmeldebenutzer die erforderlichen Berechtigungen auf entsprechender Datenbankebene zu. Sehen Sie sich dazu folgendes Beispiel an:

    ![SQL Server-Berechtigungen](./media/connect-external-sources/SqlServerAuth.png)

3. Sorgen Sie dafür, dass der Standardport für SQL Server (`1433`) für die Firewall zugelassen ist.
4. Öffnen Sie den Konfigurations-Manager für SQL, um TCP/IP über die Netzwerkkonfiguration zu aktivieren. Sehen Sie sich dazu das Beispiel unten an:

    ![Aktivieren von TCP/IP in SQL Server](./media/connect-external-sources/SqlServerTCPIP.png)

    Notieren Sie sich auch den Wert für **Alle überwachen** in obiger Registerkarte unter **Protokoll**.

5. Konfigurieren Sie Port 1433 als TCP/IP-Port für alle erforderlichen IP-Adressen, wenn `Listen All` auf `No` festgelegt ist. Legen Sie andernfalls den TCP-Port in IPAll fest.

    ![TCP/IP-Port in SQL Server](./media/connect-external-sources/SQLServerTCPIIPPort.png)

## <a name="connect-to-sql-server-from-your-application"></a>Herstellen einer Verbindung von Ihrer Anwendung zu SQL Server

1. Verwenden Sie den Microsoft JDBC-Treiber für SQL Server, um für Datenbankverbindungen über Ihre Anwendungen zu sorgen. Der Download ist über [diese offizielle Website](/sql/connect/jdbc/download-microsoft-jdbc-driver-for-sql-server?view=sql-server-ver15) möglich.
2. Legen Sie die folgenden Konfigurationen fest, um eine Verbindung zur SQL Server-Instanz und zur entsprechenden Datenbank in Ihrer Anwendung herzustellen:
    1. **connection_url:** Hierbei handelt es sich um die URL, die zum Herstellen einer Verbindung zur SQL Server-Instanz bzw. zur entsprechenden Datenbank genutzt wird. Sie weist das folgende Format auf:

        ```
        jdbc:sqlserver://<SQL_server_IP_address>:1433;instanceName=<instance_name>;databaseName=<database_name>;
        ```

    2. **dbtable:** Hierbei handelt es sich um den Namen der Tabelle, auf die zugegriffen wird.
    3. **user:** Hierbei handelt es sich um den Benutzer für die Anmeldung aus Schritt 1 für die Konfiguration von SQL Server.
    4. **password:** Hierbei handelt es sich um das Kennwort für die Anmeldung aus Schritt 1 für die Konfiguration von SQL Server.
3. Verwenden Sie obige Konfiguration in Ihrem Anwendungscode, um die Daten aus einer Tabelle wie unten gezeigt zu lesen:

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
