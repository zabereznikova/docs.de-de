---
title: Objektbesitz und Trennung von Benutzer und Schema in SQL Server
description: Erfahren Sie, wie Sie durch die Trennung von Benutzer Schemas Flexibilität beim Verwalten von SQL Server Berechtigungen für Datenbankobjekte Schemas gruppieren Objekte in separaten Namespaces.
ms.date: 03/30/2017
ms.assetid: 242830c1-31b5-4427-828c-cc22ff339f30
ms.openlocfilehash: e92799237a90c502aa4000d8d4027df522aa0d87
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91183142"
---
# <a name="ownership-and-user-schema-separation-in-sql-server"></a><span data-ttu-id="1bf97-104">Objektbesitz und Trennung von Benutzer und Schema in SQL Server</span><span class="sxs-lookup"><span data-stu-id="1bf97-104">Ownership and User-Schema Separation in SQL Server</span></span>

<span data-ttu-id="1bf97-105">Eines der Hauptkonzepte der SQL Server-Sicherheit besteht darin, dass die Besitzer von Objekten unwiderrufbare Berechtigungen für deren Verwaltung besitzen.</span><span class="sxs-lookup"><span data-stu-id="1bf97-105">A core concept of SQL Server security is that owners of objects have irrevocable permissions to administer them.</span></span> <span data-ttu-id="1bf97-106">Es ist nicht möglich, dem Besitzer eines Objekts dessen Privilegien zu entziehen, und Sie können auch keine Besitzer aus der Datenbank entfernen, wenn diese Objekte in der Datenbank besitzen.</span><span class="sxs-lookup"><span data-stu-id="1bf97-106">You cannot remove privileges from an object owner, and you cannot drop users from a database if they own objects in it.</span></span>  
  
## <a name="user-schema-separation"></a><span data-ttu-id="1bf97-107">Trennung von Benutzer und Schema</span><span class="sxs-lookup"><span data-stu-id="1bf97-107">User-Schema Separation</span></span>  

 <span data-ttu-id="1bf97-108">Durch die Trennung von Benutzer und Schema können die Berechtigungen für Datenbankobjekte flexibler verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="1bf97-108">User-schema separation allows for more flexibility in managing database object permissions.</span></span> <span data-ttu-id="1bf97-109">Ein *Schema* ist ein benannter Container für Datenbankobjekte, der es Ihnen ermöglicht, Objekte in separaten Namespaces zu gruppieren.</span><span class="sxs-lookup"><span data-stu-id="1bf97-109">A *schema* is a named container for database objects, which allows you to group objects into separate namespaces.</span></span> <span data-ttu-id="1bf97-110">So enthält die AdventureWorks-Beispieldatenbank z. B. Schemas wie Production, Sales und HumanResources.</span><span class="sxs-lookup"><span data-stu-id="1bf97-110">For example, the AdventureWorks sample database contains schemas for Production, Sales, and HumanResources.</span></span>  
  
 <span data-ttu-id="1bf97-111">Die vierteilige Benennungssyntax zum Verweisen auf Objekte gibt den Schemanamen an.</span><span class="sxs-lookup"><span data-stu-id="1bf97-111">The four-part naming syntax for referring to objects specifies the schema name.</span></span>  
  
```text
Server.Database.DatabaseSchema.DatabaseObject  
```  
  
### <a name="schema-owners-and-permissions"></a><span data-ttu-id="1bf97-112">Schemabesitzer und Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="1bf97-112">Schema Owners and Permissions</span></span>  

 <span data-ttu-id="1bf97-113">Schemas können jedem beliebigen Datenbankprinzipal gehören, und ein einzelner Prinzipal kann Besitzer mehrerer Schemas sein.</span><span class="sxs-lookup"><span data-stu-id="1bf97-113">Schemas can be owned by any database principal, and a single principal can own multiple schemas.</span></span> <span data-ttu-id="1bf97-114">Sie können Sicherheitsregeln auf ein Schema anwenden, die dann von allen Objekten im Schema geerbt werden.</span><span class="sxs-lookup"><span data-stu-id="1bf97-114">You can apply security rules to a schema, which are inherited by all objects in the schema.</span></span> <span data-ttu-id="1bf97-115">Wenn Sie die Zugriffsberechtigungen für ein Schema eingerichtet haben, werden diese Berechtigungen automatisch auf alle neuen Objekte angewendet, die dem Schema hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="1bf97-115">Once you set up access permissions for a schema, those permissions are automatically applied as new objects are added to the schema.</span></span> <span data-ttu-id="1bf97-116">Benutzer können einem Standardschema zugewiesen werden, und mehrere Datenbankbenutzer können gemeinsam dasselbe Schema verwenden.</span><span class="sxs-lookup"><span data-stu-id="1bf97-116">Users can be assigned a default schema, and multiple database users can share the same schema.</span></span>  
  
 <span data-ttu-id="1bf97-117">Wenn Entwickler Objekte in einem Schema erstellen, gehen diese Objekte standardmäßig nicht in den Besitz des Entwicklers über, sondern in den Besitz des Sicherheitsprinzipals, dem das Schema gehört.</span><span class="sxs-lookup"><span data-stu-id="1bf97-117">By default, when developers create objects in a schema, the objects are owned by the security principal that owns the schema, not the developer.</span></span> <span data-ttu-id="1bf97-118">Der Objektbesitz kann mit der Transact-SQL-ALTER AUTHORIZATION-Anweisung übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="1bf97-118">Object ownership can be transferred with ALTER AUTHORIZATION Transact-SQL statement.</span></span> <span data-ttu-id="1bf97-119">Ein Schema kann auch Objekte enthalten, die unterschiedlichen Besitzern gehören und im Vergleich zu den dem Schema zugewiesenen Berechtigungen detailliertere Berechtigungen besitzen. Eine solche Strukturierung wird jedoch nicht empfohlen, da sie die Verwaltung der Berechtigungen erschwert.</span><span class="sxs-lookup"><span data-stu-id="1bf97-119">A schema can also contain objects that are owned by different users and have more granular permissions than those assigned to the schema, although this is not recommended because it adds complexity to managing permissions.</span></span> <span data-ttu-id="1bf97-120">Objekte können zwischen Schemas verschoben werden, und der Schemabesitz kann zwischen den Prinzipalen übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="1bf97-120">Objects can be moved between schemas, and schema ownership can be transferred between principals.</span></span> <span data-ttu-id="1bf97-121">Datenbankbenutzer lassen sich löschen, ohne dass sich dies auf die Schemas auswirkt.</span><span class="sxs-lookup"><span data-stu-id="1bf97-121">Database users can be dropped without affecting schemas.</span></span>  
  
### <a name="built-in-schemas"></a><span data-ttu-id="1bf97-122">Integrierte Schemas</span><span class="sxs-lookup"><span data-stu-id="1bf97-122">Built-In Schemas</span></span>  

 <span data-ttu-id="1bf97-123">SQL Server enthält zehn vordefinierte Schemas, deren Namen mit den integrierten Datenbankbenutzern und Rollen übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="1bf97-123">SQL Server ships with ten pre-defined schemas that have the same names as the built-in database users and roles.</span></span> <span data-ttu-id="1bf97-124">Diese Schemas wurden hauptsächlich aus Gründen der Abwärtskompatibilität bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="1bf97-124">These exist mainly for backward compatibility.</span></span> <span data-ttu-id="1bf97-125">Sie können die Schemas, die denselben Namen wie die festen Datenbankrollen haben, löschen, wenn Sie sie nicht benötigen.</span><span class="sxs-lookup"><span data-stu-id="1bf97-125">You can drop the schemas that have the same names as the fixed database roles if you do not need them.</span></span> <span data-ttu-id="1bf97-126">Die folgenden Schemas können nicht gelöscht werden:</span><span class="sxs-lookup"><span data-stu-id="1bf97-126">You cannot drop the following schemas:</span></span>  
  
- `dbo`  
  
- `guest`  
  
- `sys`  
  
- `INFORMATION_SCHEMA`  
  
 <span data-ttu-id="1bf97-127">Wenn Sie sie aus der Modelldatenbank entfernen, werden sie in neuen Datenbanken nicht mehr angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1bf97-127">If you drop them from the model database, they will not appear in new databases.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1bf97-128">Die Schemas `sys` und `INFORMATION_SCHEMA` sind für Systemobjekte reserviert.</span><span class="sxs-lookup"><span data-stu-id="1bf97-128">The `sys` and `INFORMATION_SCHEMA` schemas are reserved for system objects.</span></span> <span data-ttu-id="1bf97-129">Sie können in diesen Schemas keine Objekte erstellen, und Sie können die Schemas nicht löschen.</span><span class="sxs-lookup"><span data-stu-id="1bf97-129">You cannot create objects in these schemas and you cannot drop them.</span></span>  
  
#### <a name="the-dbo-schema"></a><span data-ttu-id="1bf97-130">Das "dbo"-Schema</span><span class="sxs-lookup"><span data-stu-id="1bf97-130">The dbo Schema</span></span>  

 <span data-ttu-id="1bf97-131">Das `dbo`-Schema ist das Standardschema für neu erstellte Datenbanken.</span><span class="sxs-lookup"><span data-stu-id="1bf97-131">The `dbo` schema is the default schema for a newly created database.</span></span> <span data-ttu-id="1bf97-132">Das `dbo`-Schema gehört dem `dbo`-Benutzerkonto.</span><span class="sxs-lookup"><span data-stu-id="1bf97-132">The `dbo` schema is owned by the `dbo` user account.</span></span> <span data-ttu-id="1bf97-133">Für Benutzer, die mit dem Transact-SQL-CREATE USER-Befehl erstellt werden, ist `dbo` standardmäßig das Standardschema.</span><span class="sxs-lookup"><span data-stu-id="1bf97-133">By default, users created with the CREATE USER Transact-SQL command have `dbo` as their default schema.</span></span>  
  
 <span data-ttu-id="1bf97-134">Benutzer, denen das `dbo`-Schema zugewiesen ist, erben nicht die Berechtigungen des `dbo`-Benutzerkontos.</span><span class="sxs-lookup"><span data-stu-id="1bf97-134">Users who are assigned the `dbo` schema do not inherit the permissions of the `dbo` user account.</span></span> <span data-ttu-id="1bf97-135">Es werden keine Berechtigungen aus einem Schema an die Benutzer vererbt; die Schemaberechtigungen werden von den im Schema enthaltenen Datenbankobjekten geerbt.</span><span class="sxs-lookup"><span data-stu-id="1bf97-135">No permissions are inherited from a schema by users; schema permissions are inherited by the database objects contained in the schema.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1bf97-136">Wenn mit einem einteiligen Namen auf Datenbankobjekte verwiesen wird, durchsucht SQL Server zunächst das Standardschema des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="1bf97-136">When database objects are referenced by using a one-part name, SQL Server first looks in the user's default schema.</span></span> <span data-ttu-id="1bf97-137">Wenn das Objekt dort nicht gefunden wird, sucht SQL Server als Nächstes im `dbo`-Schema.</span><span class="sxs-lookup"><span data-stu-id="1bf97-137">If the object is not found there, SQL Server looks next in the `dbo` schema.</span></span> <span data-ttu-id="1bf97-138">Wenn sich das Objekt nicht im `dbo`-Schema befindet, wird eine Fehlermeldung zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="1bf97-138">If the object is not in the `dbo` schema, an error is returned.</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="1bf97-139">Externe Ressourcen</span><span class="sxs-lookup"><span data-stu-id="1bf97-139">External Resources</span></span>  

 <span data-ttu-id="1bf97-140">Weitere Informationen zu Objektbesitz und Schemas finden Sie in den folgenden Ressourcen:</span><span class="sxs-lookup"><span data-stu-id="1bf97-140">For more information on object ownership and schemas, see the following resources.</span></span>  
  
|<span data-ttu-id="1bf97-141">Resource</span><span class="sxs-lookup"><span data-stu-id="1bf97-141">Resource</span></span>|<span data-ttu-id="1bf97-142">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1bf97-142">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="1bf97-143">[Trennung von Benutzer und Schema](/previous-versions/sql/sql-server-2008-r2/ms190387(v=sql.105))</span><span class="sxs-lookup"><span data-stu-id="1bf97-143">[User-Schema Separation](/previous-versions/sql/sql-server-2008-r2/ms190387(v=sql.105))</span></span>|<span data-ttu-id="1bf97-144">Beschreibt die Änderungen, die die Trennung von Benutzer und Schema zur Folge hat.</span><span class="sxs-lookup"><span data-stu-id="1bf97-144">Describes the changes introduced by user-schema separation.</span></span> <span data-ttu-id="1bf97-145">Enthält Informationen zum neuen Verhalten, seinen Auswirkungen auf den Objektbesitz, zu Katalogsichten und zu Berechtigungen.</span><span class="sxs-lookup"><span data-stu-id="1bf97-145">Includes new behavior, its impact on ownership, catalog views, and permissions.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1bf97-146">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1bf97-146">See also</span></span>

- [<span data-ttu-id="1bf97-147">Sichern von ADO.NET-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="1bf97-147">Securing ADO.NET Applications</span></span>](../securing-ado-net-applications.md)
- [<span data-ttu-id="1bf97-148">Anwendungssicherheitsszenarios in SQL Server</span><span class="sxs-lookup"><span data-stu-id="1bf97-148">Application Security Scenarios in SQL Server</span></span>](application-security-scenarios-in-sql-server.md)
- [<span data-ttu-id="1bf97-149">Authentifizierung in SQL Server</span><span class="sxs-lookup"><span data-stu-id="1bf97-149">Authentication in SQL Server</span></span>](authentication-in-sql-server.md)
- [<span data-ttu-id="1bf97-150">Server- und Datenbankrollen in SQL Server</span><span class="sxs-lookup"><span data-stu-id="1bf97-150">Server and Database Roles in SQL Server</span></span>](server-and-database-roles-in-sql-server.md)
- [<span data-ttu-id="1bf97-151">Autorisierung und Berechtigungen in SQL Server</span><span class="sxs-lookup"><span data-stu-id="1bf97-151">Authorization and Permissions in SQL Server</span></span>](authorization-and-permissions-in-sql-server.md)
- [<span data-ttu-id="1bf97-152">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="1bf97-152">ADO.NET Overview</span></span>](../ado-net-overview.md)
