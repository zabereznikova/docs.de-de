---
title: SqlClient-Unterstützung für LocalDB
ms.date: 03/30/2017
ms.assetid: cf796898-5575-46f2-ae6e-21e5aa8c4123
ms.openlocfilehash: 841c455605b0b32668d26cab16a6207dc1c0f716
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91203422"
---
# <a name="sqlclient-support-for-localdb"></a><span data-ttu-id="c617f-102">SqlClient-Unterstützung für LocalDB</span><span class="sxs-lookup"><span data-stu-id="c617f-102">SqlClient Support for LocalDB</span></span>

<span data-ttu-id="c617f-103">Ab der SQL Server-Version mit dem Codenamen „Denali“ ist eine vereinfachte Version von SQL Server mit dem Namen „LocalDB“ verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c617f-103">Beginning in SQL Server code name Denali, a lightweight version of SQL Server, called LocalDB, will be available.</span></span> <span data-ttu-id="c617f-104">In diesem Artikel wird erläutert, wie Sie eine Verbindung mit einer LocalDB-Datenbank herstellen können.</span><span class="sxs-lookup"><span data-stu-id="c617f-104">This topic discusses how to connect to a LocalDB database.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c617f-105">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="c617f-105">Remarks</span></span>  

 <span data-ttu-id="c617f-106">Weitere Informationen zu LocalDB, einschließlich der Installation von LocalDB und der Konfiguration der LocalDB-Instanz, finden Sie in der SQL Server-Onlinedokumentation.</span><span class="sxs-lookup"><span data-stu-id="c617f-106">For more information about LocalDB, including how to install LocalDB and configure your LocalDB instance, see SQL Server Books Online.</span></span>  
  
 <span data-ttu-id="c617f-107">Sie können LocalDB für Folgendes nutzen:</span><span class="sxs-lookup"><span data-stu-id="c617f-107">To summarize what you can do with LocalDB:</span></span>  
  
- <span data-ttu-id="c617f-108">Erstellen und Starten von LocalDB-Instanzen mit einer sqllocaldb.exe- oder einer app.config-Datei</span><span class="sxs-lookup"><span data-stu-id="c617f-108">Create and start LocalDB instances with sqllocaldb.exe or your app.config file.</span></span>  
  
- <span data-ttu-id="c617f-109">Verwenden Sie „sqlcmd.exe“, um Datenbanken in einer LocalDB-Instanz hinzuzufügen und zu ändern.</span><span class="sxs-lookup"><span data-stu-id="c617f-109">Use sqlcmd.exe to add and modify databases in a LocalDB instance.</span></span> <span data-ttu-id="c617f-110">Beispiel: `sqlcmd -S (localdb)\myinst`.</span><span class="sxs-lookup"><span data-stu-id="c617f-110">For example, `sqlcmd -S (localdb)\myinst`.</span></span>  
  
- <span data-ttu-id="c617f-111">Verwenden des `AttachDBFilename`-Schlüsselworts für eine Verbindungszeichenfolge zum Hinzufügen einer Datenbank zu Ihr LocalDB-Instanz.</span><span class="sxs-lookup"><span data-stu-id="c617f-111">Use the `AttachDBFilename` connection string keyword to add a database to your LocalDB instance.</span></span> <span data-ttu-id="c617f-112">Wenn Sie `AttachDBFilename` verwenden und den Namen der Datenbank nicht mit dem Schlüsselwort der `Database`-Verbindungszeichenfolge angeben, wird die Datenbank aus der LocalDB-Instanz entfernt, wenn die Anwendung geschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="c617f-112">When using `AttachDBFilename`, if you do not specify the name of the database with the `Database` connection string keyword, the database will be removed from the LocalDB instance when the application closes.</span></span>  
  
- <span data-ttu-id="c617f-113">Geben Sie in der Verbindungszeichenfolge eine LocalDB-Instanz an:</span><span class="sxs-lookup"><span data-stu-id="c617f-113">Specify a LocalDB instance in your connection string.</span></span> <span data-ttu-id="c617f-114">Wenn Ihr Instanzname beispielsweise `myInstance` lautet, enthält die Verbindungszeichenfolge folgende Elemente:</span><span class="sxs-lookup"><span data-stu-id="c617f-114">For example, your instance name is `myInstance`, the connection string would include:</span></span>  
  
    `server=(localdb)\\myInstance`  
  
 <span data-ttu-id="c617f-115">`User Instance=True` ist nicht zulässig, wenn eine Verbindung mit einer LocalDB-Datenbank hergestellt wird.</span><span class="sxs-lookup"><span data-stu-id="c617f-115">`User Instance=True` is not allowed when connecting to a LocalDB database.</span></span>  
  
 <span data-ttu-id="c617f-116">Sie können LocalDB aus dem [Microsoft SQL Server 2012 Feature Pack](https://www.microsoft.com/download/en/details.aspx?id=29065) herunterladen.</span><span class="sxs-lookup"><span data-stu-id="c617f-116">You can download LocalDB from [Microsoft SQL Server 2012 Feature Pack](https://www.microsoft.com/download/en/details.aspx?id=29065).</span></span> <span data-ttu-id="c617f-117">Wenn Sie sqlcmd.exe verwenden, um Daten in der LocalDB-Instanz zu ändern, benötigen Sie sqlcmd von SQ 2012, das auch aus dem SQL Server 2012 Feature Pack abrufbar ist.</span><span class="sxs-lookup"><span data-stu-id="c617f-117">If you will use sqlcmd.exe to modify data in your LocalDB instance, you will need sqlcmd from SQL Server 2012, which you can also get from the SQL Server 2012 Feature Pack.</span></span>  
  
## <a name="programmatically-create-a-named-instance"></a><span data-ttu-id="c617f-118">Programmgesteuertes Erstellen einer benannten Instanz</span><span class="sxs-lookup"><span data-stu-id="c617f-118">Programmatically Create a Named Instance</span></span>  

 <span data-ttu-id="c617f-119">Eine Anwendung kann wie folgt eine benannte Instanz erstellen und eine Datenbank angeben:</span><span class="sxs-lookup"><span data-stu-id="c617f-119">An application can create a named instance and specify a database as follows:</span></span>  
  
- <span data-ttu-id="c617f-120">Geben Sie wie folgt die LocalDB-Instanzen an, die in der Datei „app.config“ erstellt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="c617f-120">Specify the LocalDB instances to create in the app.config file, as follows.</span></span>  <span data-ttu-id="c617f-121">Die Versionsnummer der Instanz sollte mit der Versionsnummer der LocalDB-Installation identisch sein.</span><span class="sxs-lookup"><span data-stu-id="c617f-121">The version number of the instance should be the same as the version number of your LocalDB installation.</span></span>  
  
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
  
- <span data-ttu-id="c617f-122">Geben Sie den Namen der Instanz mithilfe des Schlüsselworts `server` für die Verbindungszeichenfolge an.</span><span class="sxs-lookup"><span data-stu-id="c617f-122">Specify the name of the instance using the `server` connection string keyword.</span></span>  <span data-ttu-id="c617f-123">Der im `server`-Schlüsselwort für die Verbindungszeichenfolge angegebene Instanzname muss mit dem Namen übereinstimmen, der in der Datei app.config angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="c617f-123">The instance name specified in the `server` connection string keyword must match the name specified in the app.config file.</span></span>  
  
- <span data-ttu-id="c617f-124">Verwenden Sie das Schlüsselwort `AttachDBFilename` für die Verbindungszeichenfolge, um die MDF-Datei anzugeben.</span><span class="sxs-lookup"><span data-stu-id="c617f-124">Use the `AttachDBFilename` connection string keyword to specify the .MDF file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c617f-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c617f-125">See also</span></span>

- [<span data-ttu-id="c617f-126">SQL Server Features und ADO.net</span><span class="sxs-lookup"><span data-stu-id="c617f-126">SQL Server Features and ADO.NET</span></span>](sql-server-features-and-adonet.md)
- [<span data-ttu-id="c617f-127">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="c617f-127">ADO.NET Overview</span></span>](../ado-net-overview.md)
