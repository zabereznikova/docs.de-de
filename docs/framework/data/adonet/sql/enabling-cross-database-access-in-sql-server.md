---
title: Aktivieren des datenbankübergreifenden Zugriffs in SQL Server
ms.date: 03/30/2017
ms.assetid: 10663fb6-434c-4c81-8178-ec894b9cf895
ms.openlocfilehash: 6ea1ed9a6faa39df0a4f9a4a353bf34c7f5ba601
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91156263"
---
# <a name="enabling-cross-database-access-in-sql-server"></a><span data-ttu-id="5b8c8-102">Aktivieren des datenbankübergreifenden Zugriffs in SQL Server</span><span class="sxs-lookup"><span data-stu-id="5b8c8-102">Enabling Cross-Database Access in SQL Server</span></span>

<span data-ttu-id="5b8c8-103">Von einer datenbankübergreifenden Besitzverkettung spricht man, wenn eine Prozedur in einer Datenbank von Objekten in einer anderen Datenbank abhängt.</span><span class="sxs-lookup"><span data-stu-id="5b8c8-103">Cross-database ownership chaining occurs when a procedure in one database depends on objects in another database.</span></span> <span data-ttu-id="5b8c8-104">Eine datenbankübergreifende Besitzkette funktioniert wie die Besitzkette innerhalb einer einzelnen Datenbank – mit dem Unterschied, dass eine durchgängige Besitzkette voraussetzt, dass alle Objektbesitzer demselben Anmeldekonto zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="5b8c8-104">A cross-database ownership chain works in the same way as ownership chaining within a single database, except that an unbroken ownership chain requires that all the object owners are mapped to the same login account.</span></span> <span data-ttu-id="5b8c8-105">Wenn das Quellobjekt in der Quelldatenbank und das Zielobjekt in der Zieldatenbank zu ein und demselben Anmeldekonto gehören, nimmt SQL Server keine Prüfung der Berechtigungen für die Zielobjekte vor.</span><span class="sxs-lookup"><span data-stu-id="5b8c8-105">If the source object in the source database and the target objects in the target databases are owned by the same login account, SQL Server does not check permissions on the target objects.</span></span>  
  
## <a name="off-by-default"></a><span data-ttu-id="5b8c8-106">Standardmäßig deaktiviert</span><span class="sxs-lookup"><span data-stu-id="5b8c8-106">Off By Default</span></span>  

 <span data-ttu-id="5b8c8-107">Die datenbankübergreifende Besitzverkettung ist standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="5b8c8-107">Ownership chaining across databases is turned off by default.</span></span> <span data-ttu-id="5b8c8-108">Microsoft empfiehlt, dass Sie die datenbankübergreifende Besitzverkettung deaktivieren, da Sie sich sonst den folgenden Sicherheitsrisiken aussetzen:</span><span class="sxs-lookup"><span data-stu-id="5b8c8-108">Microsoft recommends that you disable cross-database ownership chaining because it exposes you to the following security risks:</span></span>  
  
- <span data-ttu-id="5b8c8-109">Datenbankbesitzer und Member der `db_ddladmin`-Datenbankrolle bzw. `db_owners` können Objekte erstellen, deren Besitzer andere Benutzer sind.</span><span class="sxs-lookup"><span data-stu-id="5b8c8-109">Database owners and members of the `db_ddladmin` or the `db_owners` database roles can create objects that are owned by other users.</span></span> <span data-ttu-id="5b8c8-110">Diese Objekte können potenziell auf Objekte in anderen Datenbanken zielen.</span><span class="sxs-lookup"><span data-stu-id="5b8c8-110">These objects can potentially target objects in other databases.</span></span> <span data-ttu-id="5b8c8-111">Das bedeutet: Wenn Sie die datenbankübergreifende Besitzverkettung aktivieren, müssen Sie sich dessen bewusst sein, dass diese Benutzer auf die Daten in allen verketteten Datenbanken zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="5b8c8-111">This means that if you enable cross-database ownership chaining, you must fully trust these users with data in all databases.</span></span>  
  
- <span data-ttu-id="5b8c8-112">Benutzer mit der CREATE DATABASE-Berechtigung können neue Datenbanken erstellen und vorhandene Datenbanken anfügen.</span><span class="sxs-lookup"><span data-stu-id="5b8c8-112">Users with CREATE DATABASE permission can create new databases and attach existing databases.</span></span> <span data-ttu-id="5b8c8-113">Wenn die datenbankübergreifende Besitzverkettung aktiviert ist, können diese Benutzer u. U. auf Objekte in anderen Datenbanken zugreifen, auf die sie von den Datenbanken aus, die sie selbst neu erstellen oder anhängen, keinen Zugriff hätten.</span><span class="sxs-lookup"><span data-stu-id="5b8c8-113">If cross-database ownership chaining is enabled, these users can access objects in other databases that they might not have privileges in from the newly created or attached databases that they create.</span></span>  
  
## <a name="enabling-cross-database-ownership-chaining"></a><span data-ttu-id="5b8c8-114">Aktivieren der datenbankübergreifenden Besitzverkettung</span><span class="sxs-lookup"><span data-stu-id="5b8c8-114">Enabling Cross-database Ownership Chaining</span></span>  

 <span data-ttu-id="5b8c8-115">Die datenbankübergreifende Besitzverkettung sollte nur in Umgebungen aktiviert werden, in denen Sie Benutzern mit weitreichenden Berechtigungen voll vertrauen.</span><span class="sxs-lookup"><span data-stu-id="5b8c8-115">Cross-database ownership chaining should only be enabled in environments where you can fully trust highly-privileged users.</span></span> <span data-ttu-id="5b8c8-116">Sie kann bei der Einrichtung für alle Datenbanken oder mit den Transact-SQL-Befehlen `sp_configure` und `ALTER DATABASE` nur für bestimmte Datenbanken aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="5b8c8-116">It can be configured during setup for all databases, or selectively for specific databases using the Transact-SQL commands `sp_configure` and `ALTER DATABASE`.</span></span>  
  
 <span data-ttu-id="5b8c8-117">Wenn Sie die datenbankübergreifende Besitzverkettung selektiv konfigurieren möchten, deaktivieren Sie sie mithilfe von `sp_configure` für den Server.</span><span class="sxs-lookup"><span data-stu-id="5b8c8-117">To selectively configure cross-database ownership chaining, use `sp_configure` to turn it off for the server.</span></span> <span data-ttu-id="5b8c8-118">Konfigurieren Sie dann mit dem Befehl ALTER DATABASE und mit SET DB_CHAINING ON die datenbankübergreifende Besitzverkettung für die gewünschten Datenbanken.</span><span class="sxs-lookup"><span data-stu-id="5b8c8-118">Then use the ALTER DATABASE command with SET DB_CHAINING ON to configure cross-database ownership chaining for only the databases that require it.</span></span>  
  
 <span data-ttu-id="5b8c8-119">Im folgenden Beispiel wird die datenbankübergreifende Besitzverkettung für alle Datenbanken aktiviert:</span><span class="sxs-lookup"><span data-stu-id="5b8c8-119">The following sample turns on cross-database ownership chaining for all databases:</span></span>  
  
```sql
EXECUTE sp_configure 'show advanced', 1;  
RECONFIGURE;  
EXECUTE sp_configure 'cross db ownership chaining', 1;  
RECONFIGURE;  
```  
  
 <span data-ttu-id="5b8c8-120">Im folgenden Beispiel wird die datenbankübergreifende Besitzverkettung für bestimmte Datenbanken aktiviert:</span><span class="sxs-lookup"><span data-stu-id="5b8c8-120">The following sample turns on cross-database ownership chaining for specific databases:</span></span>  
  
```sql
ALTER DATABASE Database1 SET DB_CHAINING ON;  
ALTER DATABASE Database2 SET DB_CHAINING ON;  
```  
  
### <a name="dynamic-sql"></a><span data-ttu-id="5b8c8-121">Dynamische SQL-Anweisungen</span><span class="sxs-lookup"><span data-stu-id="5b8c8-121">Dynamic SQL</span></span>  

 <span data-ttu-id="5b8c8-122">Die datenbankübergreifende Besitzverkettung funktioniert nicht, wenn dynamisch erstellte SQL-Anweisungen ausgeführt werden, sofern derselbe Benutzer nicht in beiden Datenbanken vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="5b8c8-122">Cross-database ownership chaining does not work in cases where dynamically created SQL statements are executed unless the same user exists in both databases.</span></span> <span data-ttu-id="5b8c8-123">Dieses Problem können Sie in SQL Server umgehen, indem Sie eine gespeicherte Prozedur erstellen, die auf die Daten in einer anderen Datenbank zugreift, und die Prozedur mit einem Zertifikat signieren, das in beiden Datenbanken vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="5b8c8-123">You can work around this in SQL Server by creating a stored procedure that accesses data in another database and signing the procedure with a certificate that exists in both databases.</span></span> <span data-ttu-id="5b8c8-124">Dadurch erhalten Benutzer Zugriff auf die von der Prozedur verwendeten Datenbankressourcen, ohne dass ihnen Datenbankzugriff gewährt wird oder Berechtigungen erteilt werden.</span><span class="sxs-lookup"><span data-stu-id="5b8c8-124">This gives users access to the database resources used by the procedure without granting them database access or permissions.</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="5b8c8-125">Externe Ressourcen</span><span class="sxs-lookup"><span data-stu-id="5b8c8-125">External Resources</span></span>  

 <span data-ttu-id="5b8c8-126">Weitere Informationen finden Sie in den folgenden Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="5b8c8-126">For more information, see the following resources.</span></span>  
  
|<span data-ttu-id="5b8c8-127">Resource</span><span class="sxs-lookup"><span data-stu-id="5b8c8-127">Resource</span></span>|<span data-ttu-id="5b8c8-128">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5b8c8-128">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="5b8c8-129">[Erweitern des Daten Bank Identitäts Wechsels mithilfe der Option EXECUTE AS](/previous-versions/sql/sql-server-2008-r2/ms188304(v=sql.105)) und [Cross DB Ownership Chaining](/sql/database-engine/configure-windows/cross-db-ownership-chaining-server-configuration-option).</span><span class="sxs-lookup"><span data-stu-id="5b8c8-129">[Extending Database Impersonation by Using EXECUTE AS](/previous-versions/sql/sql-server-2008-r2/ms188304(v=sql.105)) and [Cross DB Ownership Chaining Option](/sql/database-engine/configure-windows/cross-db-ownership-chaining-server-configuration-option).</span></span>|<span data-ttu-id="5b8c8-130">In den Artikeln wird beschrieben, wie die datenbankübergreifende Besitz Verkettung für eine Instanz von SQL Server konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="5b8c8-130">Articles describe how to configure cross-database ownership chaining for an instance of SQL Server.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5b8c8-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5b8c8-131">See also</span></span>

- [<span data-ttu-id="5b8c8-132">Sichern von ADO.NET-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="5b8c8-132">Securing ADO.NET Applications</span></span>](../securing-ado-net-applications.md)
- [<span data-ttu-id="5b8c8-133">Übersicht über die SQL Server-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="5b8c8-133">Overview of SQL Server Security</span></span>](overview-of-sql-server-security.md)
- [<span data-ttu-id="5b8c8-134">Verwalten von Berechtigungen mit gespeicherten Prozeduren in SQL Server</span><span class="sxs-lookup"><span data-stu-id="5b8c8-134">Managing Permissions with Stored Procedures in SQL Server</span></span>](managing-permissions-with-stored-procedures-in-sql-server.md)
- [<span data-ttu-id="5b8c8-135">Schreiben von sicherem dynamischem SQL in SQL Server</span><span class="sxs-lookup"><span data-stu-id="5b8c8-135">Writing Secure Dynamic SQL in SQL Server</span></span>](writing-secure-dynamic-sql-in-sql-server.md)
- [<span data-ttu-id="5b8c8-136">Signieren von gespeicherten Prozeduren in SQL Server</span><span class="sxs-lookup"><span data-stu-id="5b8c8-136">Signing Stored Procedures in SQL Server</span></span>](signing-stored-procedures-in-sql-server.md)
- [<span data-ttu-id="5b8c8-137">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="5b8c8-137">ADO.NET Overview</span></span>](../ado-net-overview.md)
