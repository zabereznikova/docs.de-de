---
title: SqlClient-Unterstützung für LocalDB
ms.date: 03/30/2017
ms.assetid: cf796898-5575-46f2-ae6e-21e5aa8c4123
ms.openlocfilehash: 55ab1346de6f5c14f15d01344a984c18edf30e02
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94824479"
---
# <a name="sqlclient-support-for-localdb"></a><span data-ttu-id="82e5f-102">SqlClient-Unterstützung für LocalDB</span><span class="sxs-lookup"><span data-stu-id="82e5f-102">SqlClient Support for LocalDB</span></span>

<span data-ttu-id="82e5f-103">In diesem Artikel wird erläutert, wie eine Verbindung mit einer localdb-Datenbank hergestellt wird.</span><span class="sxs-lookup"><span data-stu-id="82e5f-103">This article discusses how to connect to a LocalDB database.</span></span> <span data-ttu-id="82e5f-104">Localdb ist eine vereinfachte Version von SQL Server.</span><span class="sxs-lookup"><span data-stu-id="82e5f-104">LocalDB is a lightweight version of SQL Server.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="82e5f-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="82e5f-105">Remarks</span></span>
  
 <span data-ttu-id="82e5f-106">Sie können LocalDB für Folgendes nutzen:</span><span class="sxs-lookup"><span data-stu-id="82e5f-106">To summarize what you can do with LocalDB:</span></span>  
  
- <span data-ttu-id="82e5f-107">Erstellen und Starten von LocalDB-Instanzen mit einer sqllocaldb.exe- oder einer app.config-Datei</span><span class="sxs-lookup"><span data-stu-id="82e5f-107">Create and start LocalDB instances with sqllocaldb.exe or your app.config file.</span></span>  
  
- <span data-ttu-id="82e5f-108">Verwenden Sie „sqlcmd.exe“, um Datenbanken in einer LocalDB-Instanz hinzuzufügen und zu ändern.</span><span class="sxs-lookup"><span data-stu-id="82e5f-108">Use sqlcmd.exe to add and modify databases in a LocalDB instance.</span></span> <span data-ttu-id="82e5f-109">Beispiel: `sqlcmd -S (localdb)\myinst`.</span><span class="sxs-lookup"><span data-stu-id="82e5f-109">For example, `sqlcmd -S (localdb)\myinst`.</span></span>  
  
- <span data-ttu-id="82e5f-110">Verwenden des `AttachDBFilename`-Schlüsselworts für eine Verbindungszeichenfolge zum Hinzufügen einer Datenbank zu Ihr LocalDB-Instanz.</span><span class="sxs-lookup"><span data-stu-id="82e5f-110">Use the `AttachDBFilename` connection string keyword to add a database to your LocalDB instance.</span></span> <span data-ttu-id="82e5f-111">Wenn Sie `AttachDBFilename` verwenden und den Namen der Datenbank nicht mit dem Schlüsselwort der `Database`-Verbindungszeichenfolge angeben, wird die Datenbank aus der LocalDB-Instanz entfernt, wenn die Anwendung geschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="82e5f-111">When using `AttachDBFilename`, if you do not specify the name of the database with the `Database` connection string keyword, the database will be removed from the LocalDB instance when the application closes.</span></span>  
  
- <span data-ttu-id="82e5f-112">Geben Sie in der Verbindungszeichenfolge eine LocalDB-Instanz an:</span><span class="sxs-lookup"><span data-stu-id="82e5f-112">Specify a LocalDB instance in your connection string.</span></span> <span data-ttu-id="82e5f-113">Wenn Ihr Instanzname beispielsweise `myInstance` lautet, enthält die Verbindungszeichenfolge folgende Elemente:</span><span class="sxs-lookup"><span data-stu-id="82e5f-113">For example, your instance name is `myInstance`, the connection string would include:</span></span>  
  
    `server=(localdb)\\myInstance`  
  
 <span data-ttu-id="82e5f-114">`User Instance=True` ist nicht zulässig, wenn eine Verbindung mit einer LocalDB-Datenbank hergestellt wird.</span><span class="sxs-lookup"><span data-stu-id="82e5f-114">`User Instance=True` is not allowed when connecting to a LocalDB database.</span></span>  
  
<span data-ttu-id="82e5f-115">Weitere Informationen zum Installieren von localdb finden Sie unter [SQL Server Express localdb](/sql/database-engine/configure-windows/sql-server-express-localdb).</span><span class="sxs-lookup"><span data-stu-id="82e5f-115">For information about installing LocalDB, see [SQL Server Express LocalDB](/sql/database-engine/configure-windows/sql-server-express-localdb).</span></span>
  
## <a name="programmatically-create-a-named-instance"></a><span data-ttu-id="82e5f-116">Programmgesteuertes Erstellen einer benannten Instanz</span><span class="sxs-lookup"><span data-stu-id="82e5f-116">Programmatically Create a Named Instance</span></span>  

 <span data-ttu-id="82e5f-117">Eine Anwendung kann wie folgt eine benannte Instanz erstellen und eine Datenbank angeben:</span><span class="sxs-lookup"><span data-stu-id="82e5f-117">An application can create a named instance and specify a database as follows:</span></span>  
  
- <span data-ttu-id="82e5f-118">Geben Sie wie folgt die LocalDB-Instanzen an, die in der Datei „app.config“ erstellt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="82e5f-118">Specify the LocalDB instances to create in the app.config file, as follows.</span></span>  <span data-ttu-id="82e5f-119">Die Versionsnummer der Instanz sollte mit der Versionsnummer der LocalDB-Installation identisch sein.</span><span class="sxs-lookup"><span data-stu-id="82e5f-119">The version number of the instance should be the same as the version number of your LocalDB installation.</span></span>  
  
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
  
- <span data-ttu-id="82e5f-120">Geben Sie den Namen der Instanz mithilfe des Schlüsselworts `server` für die Verbindungszeichenfolge an.</span><span class="sxs-lookup"><span data-stu-id="82e5f-120">Specify the name of the instance using the `server` connection string keyword.</span></span>  <span data-ttu-id="82e5f-121">Der im `server`-Schlüsselwort für die Verbindungszeichenfolge angegebene Instanzname muss mit dem Namen übereinstimmen, der in der Datei app.config angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="82e5f-121">The instance name specified in the `server` connection string keyword must match the name specified in the app.config file.</span></span>  
  
- <span data-ttu-id="82e5f-122">Verwenden Sie das Schlüsselwort `AttachDBFilename` für die Verbindungszeichenfolge, um die MDF-Datei anzugeben.</span><span class="sxs-lookup"><span data-stu-id="82e5f-122">Use the `AttachDBFilename` connection string keyword to specify the .MDF file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82e5f-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="82e5f-123">See also</span></span>

- [<span data-ttu-id="82e5f-124">SQL Server-Funktionen und ADO.NET</span><span class="sxs-lookup"><span data-stu-id="82e5f-124">SQL Server Features and ADO.NET</span></span>](sql-server-features-and-adonet.md)
- [<span data-ttu-id="82e5f-125">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="82e5f-125">ADO.NET Overview</span></span>](../ado-net-overview.md)
