---
title: SqlClient-Unterstützung für LocalDB
ms.date: 03/30/2017
ms.assetid: cf796898-5575-46f2-ae6e-21e5aa8c4123
ms.openlocfilehash: 416945964af7fda5ed5aaab2f5aae1bbc8928556
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59204756"
---
# <a name="sqlclient-support-for-localdb"></a><span data-ttu-id="fa3f2-102">SqlClient-Unterstützung für LocalDB</span><span class="sxs-lookup"><span data-stu-id="fa3f2-102">SqlClient Support for LocalDB</span></span>
<span data-ttu-id="fa3f2-103">Ab SQL Server Codename Denali, wird eine einfache Version von SQL Server, dem Namen LocalDB verfügbar sein.</span><span class="sxs-lookup"><span data-stu-id="fa3f2-103">Beginning in SQL Server code name Denali, a lightweight version of SQL Server, called LocalDB, will be available.</span></span> <span data-ttu-id="fa3f2-104">In diesem Thema wird erläutert, wie eine Verbindung mit einer LocalDB-Datenbank hergestellt wird.</span><span class="sxs-lookup"><span data-stu-id="fa3f2-104">This topic discusses how to connect to a LocalDB database.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fa3f2-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fa3f2-105">Remarks</span></span>  
 <span data-ttu-id="fa3f2-106">Weitere Informationen zu LocalDB, einschließlich Informationen zum Installieren von LocalDB und die LocalDB-Instanz konfigurieren, finden in SQL Server-Onlinedokumentation.</span><span class="sxs-lookup"><span data-stu-id="fa3f2-106">For more information about LocalDB, including how to install LocalDB and configure your LocalDB instance, see SQL Server Books Online.</span></span>  
  
 <span data-ttu-id="fa3f2-107">Zusammenfassung der Verwendungsmöglichkeiten für LocalDB:</span><span class="sxs-lookup"><span data-stu-id="fa3f2-107">To summarize what you can do with LocalDB:</span></span>  
  
-   <span data-ttu-id="fa3f2-108">Erstellen und Starten von LocalDB-Instanzen mit der Datei „sqllocaldb.exe“ oder „app.config“.</span><span class="sxs-lookup"><span data-stu-id="fa3f2-108">Create and start LocalDB instances with sqllocaldb.exe or your app.config file.</span></span>  
  
-   <span data-ttu-id="fa3f2-109">Verwenden von „sqlcmd.exe“, um Datenbanken in einer LocalDB-Instanz hinzuzufügen oder zu ändern.</span><span class="sxs-lookup"><span data-stu-id="fa3f2-109">Use sqlcmd.exe to add and modify databases in a LocalDB instance.</span></span> <span data-ttu-id="fa3f2-110">Beispielsweise `sqlcmd -S (localdb)\myinst`.</span><span class="sxs-lookup"><span data-stu-id="fa3f2-110">For example, `sqlcmd -S (localdb)\myinst`.</span></span>  
  
-   <span data-ttu-id="fa3f2-111">Verwenden des `AttachDBFilename` -Schlüsselworts für die Verbindungszeichenfolge, um der LocalDB-Instanz eine Datenbank hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="fa3f2-111">Use the `AttachDBFilename` connection string keyword to add a database to your LocalDB instance.</span></span> <span data-ttu-id="fa3f2-112">Wenn Sie `AttachDBFilename`verwenden und den Namen der Datenbank nicht mit dem `Database` -Schlüsselwort der Verbindungszeichenfolge angeben, wird die Datenbank beim Schließen der Anwendung aus der LocalDB-Instanz entfernt.</span><span class="sxs-lookup"><span data-stu-id="fa3f2-112">When using `AttachDBFilename`, if you do not specify the name of the database with the `Database` connection string keyword, the database will be removed from the LocalDB instance when the application closes.</span></span>  
  
-   <span data-ttu-id="fa3f2-113">Angeben einer LocalDB-Instanz in der Verbindungszeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="fa3f2-113">Specify a LocalDB instance in your connection string.</span></span> <span data-ttu-id="fa3f2-114">Wenn der Instanzname z. B. `myInstance`lautet, könnte die Verbindungszeichenfolge Folgendes enthalten:</span><span class="sxs-lookup"><span data-stu-id="fa3f2-114">For example, your instance name is `myInstance`, the connection string would include:</span></span>  
  
    ```  
    server=(localdb)\\myInstance  
    ```  
  
 `User Instance=True` <span data-ttu-id="fa3f2-115">ist nicht zulässig, wenn die Verbindung mit einer LocalDB-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="fa3f2-115">is not allowed when connecting to a LocalDB database.</span></span>  
  
 <span data-ttu-id="fa3f2-116">Sie können LocalDB aus dem [Microsoft SQL Server 2012 Feature Pack](https://www.microsoft.com/download/en/details.aspx?id=29065)herunterladen.</span><span class="sxs-lookup"><span data-stu-id="fa3f2-116">You can download LocalDB from [Microsoft SQL Server 2012 Feature Pack](https://www.microsoft.com/download/en/details.aspx?id=29065).</span></span> <span data-ttu-id="fa3f2-117">Wenn Sie sqlcmd.exe verwenden möchten, um Daten in der LocalDB-Instanz ändern, benötigen Sie Sqlcmd von SQL Server 2012, die Sie auch über die SQL Server 2012 Feature Pack abrufen können.</span><span class="sxs-lookup"><span data-stu-id="fa3f2-117">If you will use sqlcmd.exe to modify data in your LocalDB instance, you will need sqlcmd from SQL Server 2012, which you can also get from the SQL Server 2012 Feature Pack.</span></span>  
  
## <a name="programmatically-create-a-named-instance"></a><span data-ttu-id="fa3f2-118">Programmgesteuertes Erstellen einer benannten Instanz</span><span class="sxs-lookup"><span data-stu-id="fa3f2-118">Programmatically Create a Named Instance</span></span>  
 <span data-ttu-id="fa3f2-119">Eine Anwendung kann eine benannte Instanz erstellen und eine Datenbank wie folgt angeben:</span><span class="sxs-lookup"><span data-stu-id="fa3f2-119">An application can create a named instance and specify a database as follows:</span></span>  
  
-   <span data-ttu-id="fa3f2-120">Geben Sie die LocalDB-Instanzen, die in der Datei „app.config“ erstellt werden sollen, wie folgt an.</span><span class="sxs-lookup"><span data-stu-id="fa3f2-120">Specify the LocalDB instances to create in the app.config file, as follows.</span></span>  <span data-ttu-id="fa3f2-121">Die Versionsnummer der Instanz sollte identisch mit der Versionsnummer der LocalDB-Installation sein.</span><span class="sxs-lookup"><span data-stu-id="fa3f2-121">The version number of the instance should be the same as the version number of your LocalDB installation.</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <configuration>  
      <configSections>  
        <section  
        name="system.data.localdb"  
        type="System.Data.LocalDBConfigurationSection,System.Data,Version=4.0.0.0,Culture=neutral,PublicKeyToken=b77a5c561934e089"/>  
      </configSections>  
      <system.data.localdb>  
        <localdbinstances>  
          <add name="myInstance" version="11.0" />  
        </localdbinstances>  
      </system.data.localdb>  
    </configuration>  
    ```  
  
-   <span data-ttu-id="fa3f2-122">Geben Sie den Namen der Instanz unter Verwendung des `server` -Schlüsselworts für die Verbindungszeichenfolge an.</span><span class="sxs-lookup"><span data-stu-id="fa3f2-122">Specify the name of the instance using the `server` connection string keyword.</span></span>  <span data-ttu-id="fa3f2-123">Der im `server` -Schlüsselwort für die Verbindungszeichenfolge angegebene Instanzname muss mit dem Namen übereinstimmen, der in der Datei „app.config“ angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="fa3f2-123">The instance name specified in the `server` connection string keyword must match the name specified in the app.config file.</span></span>  
  
-   <span data-ttu-id="fa3f2-124">Verwenden Sie das `AttachDBFilename` -Schlüsselwort für die Verbindungszeichenfolge, um die MDF-Datei anzugeben.</span><span class="sxs-lookup"><span data-stu-id="fa3f2-124">Use the `AttachDBFilename` connection string keyword to specify the .MDF file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa3f2-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fa3f2-125">See also</span></span>

- [<span data-ttu-id="fa3f2-126">SQL Server-Funktionen und ADO.NET</span><span class="sxs-lookup"><span data-stu-id="fa3f2-126">SQL Server Features and ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-features-and-adonet.md)
- [<span data-ttu-id="fa3f2-127">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="fa3f2-127">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
