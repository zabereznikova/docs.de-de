---
title: "SqlClient-Unterstützung für LocalDB"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cf796898-5575-46f2-ae6e-21e5aa8c4123
caps.latest.revision: "14"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 99845420549393829582ade11f38b75e3ebff484
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="sqlclient-support-for-localdb"></a><span data-ttu-id="3718d-102">SqlClient-Unterstützung für LocalDB</span><span class="sxs-lookup"><span data-stu-id="3718d-102">SqlClient Support for LocalDB</span></span>
<span data-ttu-id="3718d-103">Ab [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] Codename "Denali" ist eine vereinfachte Version von [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]mit dem Namen LocalDB verfügbar.</span><span class="sxs-lookup"><span data-stu-id="3718d-103">Beginning in [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] code name Denali, a lightweight version of [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)], called LocalDB, will be available.</span></span> <span data-ttu-id="3718d-104">In diesem Thema wird erläutert, wie eine Verbindung mit einer LocalDB-Datenbank hergestellt wird.</span><span class="sxs-lookup"><span data-stu-id="3718d-104">This topic discusses how to connect to a LocalDB database.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3718d-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3718d-105">Remarks</span></span>  
 <span data-ttu-id="3718d-106">Weitere Informationen zu LocalDB, z. B. wie Sie LocalDB installieren und eine LocalDB-Instanz konfigurieren, finden Sie in der [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] -Onlinedokumentation.</span><span class="sxs-lookup"><span data-stu-id="3718d-106">For more information about LocalDB, including how to install LocalDB and configure your LocalDB instance, see [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
 <span data-ttu-id="3718d-107">Zusammenfassung der Verwendungsmöglichkeiten für LocalDB:</span><span class="sxs-lookup"><span data-stu-id="3718d-107">To summarize what you can do with LocalDB:</span></span>  
  
-   <span data-ttu-id="3718d-108">Erstellen und Starten von LocalDB-Instanzen mit der Datei „sqllocaldb.exe“ oder „app.config“.</span><span class="sxs-lookup"><span data-stu-id="3718d-108">Create and start LocalDB instances with sqllocaldb.exe or your app.config file.</span></span>  
  
-   <span data-ttu-id="3718d-109">Verwenden von „sqlcmd.exe“, um Datenbanken in einer LocalDB-Instanz hinzuzufügen oder zu ändern.</span><span class="sxs-lookup"><span data-stu-id="3718d-109">Use sqlcmd.exe to add and modify databases in a LocalDB instance.</span></span> <span data-ttu-id="3718d-110">Beispielsweise `sqlcmd -S (localdb)\myinst`.</span><span class="sxs-lookup"><span data-stu-id="3718d-110">For example, `sqlcmd -S (localdb)\myinst`.</span></span>  
  
-   <span data-ttu-id="3718d-111">Verwenden des `AttachDBFilename` -Schlüsselworts für die Verbindungszeichenfolge, um der LocalDB-Instanz eine Datenbank hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="3718d-111">Use the `AttachDBFilename` connection string keyword to add a database to your LocalDB instance.</span></span> <span data-ttu-id="3718d-112">Wenn Sie `AttachDBFilename`verwenden und den Namen der Datenbank nicht mit dem `Database` -Schlüsselwort der Verbindungszeichenfolge angeben, wird die Datenbank beim Schließen der Anwendung aus der LocalDB-Instanz entfernt.</span><span class="sxs-lookup"><span data-stu-id="3718d-112">When using `AttachDBFilename`, if you do not specify the name of the database with the `Database` connection string keyword, the database will be removed from the LocalDB instance when the application closes.</span></span>  
  
-   <span data-ttu-id="3718d-113">Angeben einer LocalDB-Instanz in der Verbindungszeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="3718d-113">Specify a LocalDB instance in your connection string.</span></span> <span data-ttu-id="3718d-114">Wenn der Instanzname z. B. `myInstance`lautet, könnte die Verbindungszeichenfolge Folgendes enthalten:</span><span class="sxs-lookup"><span data-stu-id="3718d-114">For example, your instance name is `myInstance`, the connection string would include:</span></span>  
  
    ```  
    server=(localdb)\\myInstance  
    ```  
  
 <span data-ttu-id="3718d-115">`User Instance=True` ist bei einer Verbindung mit einer LocalDB-Datenbank nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="3718d-115">`User Instance=True` is not allowed when connecting to a LocalDB database.</span></span>  
  
 <span data-ttu-id="3718d-116">Sie können LocalDB aus dem [Microsoft SQL Server 2012 Feature Pack](http://www.microsoft.com/download/en/details.aspx?id=29065)herunterladen.</span><span class="sxs-lookup"><span data-stu-id="3718d-116">You can download LocalDB from [Microsoft SQL Server 2012 Feature Pack](http://www.microsoft.com/download/en/details.aspx?id=29065).</span></span> <span data-ttu-id="3718d-117">Wenn Sie "sqlcmd.exe" verwenden, um Daten in der LocalDB-Instanz zu ändern, benötigen Sie "sqlcmd" von [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 2012, das auch aus dem [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 2012 Feature Pack abrufbar ist.</span><span class="sxs-lookup"><span data-stu-id="3718d-117">If you will use sqlcmd.exe to modify data in your LocalDB instance, you will need sqlcmd from [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 2012, which you can also get from the [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 2012 Feature Pack.</span></span>  
  
## <a name="programmatically-create-a-named-instance"></a><span data-ttu-id="3718d-118">Programmgesteuertes Erstellen einer benannten Instanz</span><span class="sxs-lookup"><span data-stu-id="3718d-118">Programmatically Create a Named Instance</span></span>  
 <span data-ttu-id="3718d-119">Eine Anwendung kann eine benannte Instanz erstellen und eine Datenbank wie folgt angeben:</span><span class="sxs-lookup"><span data-stu-id="3718d-119">An application can create a named instance and specify a database as follows:</span></span>  
  
-   <span data-ttu-id="3718d-120">Geben Sie die LocalDB-Instanzen, die in der Datei „app.config“ erstellt werden sollen, wie folgt an.</span><span class="sxs-lookup"><span data-stu-id="3718d-120">Specify the LocalDB instances to create in the app.config file, as follows.</span></span>  <span data-ttu-id="3718d-121">Die Versionsnummer der Instanz sollte identisch mit der Versionsnummer der LocalDB-Installation sein.</span><span class="sxs-lookup"><span data-stu-id="3718d-121">The version number of the instance should be the same as the version number of your LocalDB installation.</span></span>  
  
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
  
-   <span data-ttu-id="3718d-122">Geben Sie den Namen der Instanz unter Verwendung des `server` -Schlüsselworts für die Verbindungszeichenfolge an.</span><span class="sxs-lookup"><span data-stu-id="3718d-122">Specify the name of the instance using the `server` connection string keyword.</span></span>  <span data-ttu-id="3718d-123">Der im `server` -Schlüsselwort für die Verbindungszeichenfolge angegebene Instanzname muss mit dem Namen übereinstimmen, der in der Datei „app.config“ angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="3718d-123">The instance name specified in the `server` connection string keyword must match the name specified in the app.config file.</span></span>  
  
-   <span data-ttu-id="3718d-124">Verwenden Sie das `AttachDBFilename` -Schlüsselwort für die Verbindungszeichenfolge, um die MDF-Datei anzugeben.</span><span class="sxs-lookup"><span data-stu-id="3718d-124">Use the `AttachDBFilename` connection string keyword to specify the .MDF file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3718d-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3718d-125">See Also</span></span>  
 [<span data-ttu-id="3718d-126">SQL Server Features and ADO.NET (SQL Server-Features und ADO.NET)</span><span class="sxs-lookup"><span data-stu-id="3718d-126">SQL Server Features and ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-features-and-adonet.md)  
 [<span data-ttu-id="3718d-127">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="3718d-127">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
