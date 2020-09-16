---
title: Gewähren zeilenspezifischer Berechtigungen in SQL Server
ms.date: 03/30/2017
ms.assetid: a55aaa12-34ab-41cd-9dec-fd255b29258c
ms.openlocfilehash: 0b34eaee4b66a2be82049816f0a98b9f53012303
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90554852"
---
# <a name="granting-row-level-permissions-in-sql-server"></a><span data-ttu-id="162d5-102">Gewähren zeilenspezifischer Berechtigungen in SQL Server</span><span class="sxs-lookup"><span data-stu-id="162d5-102">Granting Row-Level Permissions in SQL Server</span></span>

<span data-ttu-id="162d5-103">Es gibt Szenarien, in denen der Zugriff auf Daten genauer gesteuert werden muss, als dies durch einfaches Gewähren, Widerrufen oder Ablehnen von Berechtigungen möglich ist.</span><span class="sxs-lookup"><span data-stu-id="162d5-103">In some scenarios, there is a requirement to control access to data at a more granular level than what simply granting, revoking, or denying permissions provides.</span></span> <span data-ttu-id="162d5-104">Eine Anwendung für eine Krankenhausdatenbank kann z. B. für einzelne Ärzte erfordern, dass diese jeweils nur auf Daten der eigenen Patienten zugreifen dürfen.</span><span class="sxs-lookup"><span data-stu-id="162d5-104">For example, a hospital database application may require individual Doctors to be restricted to accessing information related to only their patients.</span></span> <span data-ttu-id="162d5-105">Ähnliche Anforderungen gibt es in vielen Umgebungen, vom Finanzwesen über die Justiz und die Behörden bis hin zum militärischen Bereich.</span><span class="sxs-lookup"><span data-stu-id="162d5-105">Similar requirements exist in many environments, including finance, law, government, and military applications.</span></span> <span data-ttu-id="162d5-106">SQL Server 2016 bietet ein Feature für die [zeilenbasierte Sicherheit](/sql/relational-databases/security/row-level-security) , die die zeilenbasierte Zugriffslogik in einer Sicherheitsrichtlinie vereinfacht und zentralisiert, um diese Szenarien besser zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="162d5-106">To help address these scenarios, SQL Server 2016 provides a [Row-Level Security](/sql/relational-databases/security/row-level-security) feature that simplifies and centralizes row-level access logic in a security policy.</span></span> <span data-ttu-id="162d5-107">Frühere Versionen von SQL Server können mithilfe von Ansichten eine ähnliche Funktionalität erreichen, um die Filterung auf Zeilenebene zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="162d5-107">For earlier versions of SQL Server, similar functionality can be achieved by using views to enact row-level filtering.</span></span>

## <a name="implementing-row-level-filtering"></a><span data-ttu-id="162d5-108">Implementieren der zeilenbasierter Filterung</span><span class="sxs-lookup"><span data-stu-id="162d5-108">Implementing Row-level Filtering</span></span>

<span data-ttu-id="162d5-109">Die zeilenbasierte Filterung wird für Anwendungen verwendet, die Informationen in einer einzelnen Tabelle wie im obigen Krankenhausbeispiel speichern.</span><span class="sxs-lookup"><span data-stu-id="162d5-109">Row-level filtering is used for applications storing information in a single table like in the hospital example above.</span></span> <span data-ttu-id="162d5-110">Um die zeilenbasierte Filterung zu implementieren, besitzt jede Zeile eine Spalte, die ein Unterscheidungsmerkmal (Differenzierungsparameter) definiert, z. B. den Benutzernamen, die Menge oder ein anderes Identifizierungsmerkmal.</span><span class="sxs-lookup"><span data-stu-id="162d5-110">To implement row-level filtering each row has a column that defines a differentiating parameter, such as a user name, label or other identifier.</span></span> <span data-ttu-id="162d5-111">Sie erstellen entweder eine Sicherheitsrichtlinie oder eine Sicht auf die Tabelle, die die Zeilen filtert, auf die der Benutzer zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="162d5-111">You create either a security policy or a view on the table, which filters the rows that the user can access.</span></span> <span data-ttu-id="162d5-112">Sie können dann parametrisierte gespeicherte Prozeduren erstellen, die die Typen von Abfragen steuern, die vom Benutzer ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="162d5-112">You then create parameterized stored procedures, which control the types of queries the user can execute.</span></span>

<span data-ttu-id="162d5-113">Das folgende Beispiel beschreibt, wie die zeilenbasierte Filterung auf der Grundlage eines Benutzer- oder Anmeldenamens konfiguriert werden kann.</span><span class="sxs-lookup"><span data-stu-id="162d5-113">The following example describes how to configure row-level filtering based on a user or login name:</span></span>

- <span data-ttu-id="162d5-114">Erstellen Sie die Tabelle, und fügen Sie eine Spalte zum Speichern des Namens hinzu.</span><span class="sxs-lookup"><span data-stu-id="162d5-114">Create the table, adding a column to store the name.</span></span>

- <span data-ttu-id="162d5-115">Aktivieren der zeilenbasierten Filterung:</span><span class="sxs-lookup"><span data-stu-id="162d5-115">Enable row-level filtering:</span></span>

  - <span data-ttu-id="162d5-116">Bei Verwendung von SQL Server 2016 oder höher oder [Azure SQL-Datenbank](/azure/sql-database/)erstellen Sie eine Sicherheitsrichtlinie, die der Tabelle ein Prädikat hinzufügt, das die Zeilen auf diejenigen einschränkt, die entweder mit dem aktuellen Datenbankbenutzer (mithilfe der integrierten CURRENT_USER()-Funktion) oder mit dem aktuellen Anmeldenamen (mithilfe der integrierten SUSER_SNAME()-Funktion) übereinstimmen:</span><span class="sxs-lookup"><span data-stu-id="162d5-116">If you are using SQL Server 2016 or higher, or [Azure SQL Database](/azure/sql-database/), create a security policy that adds a predicate on the table restricting the rows returned to those that match either the current database user (using the CURRENT_USER() built-in function) or the current login name (using the SUSER_SNAME() built-in function):</span></span>

      ```sql
      CREATE SCHEMA Security
      GO

      CREATE FUNCTION Security.userAccessPredicate(@UserName sysname)
          RETURNS TABLE
          WITH SCHEMABINDING
      AS
          RETURN SELECT 1 AS accessResult
          WHERE @UserName = SUSER_SNAME()
      GO

      CREATE SECURITY POLICY Security.userAccessPolicy
          ADD FILTER PREDICATE Security.userAccessPredicate(UserName) ON dbo.MyTable,
          ADD BLOCK PREDICATE Security.userAccessPredicate(UserName) ON dbo.MyTable
      GO
      ```

  - <span data-ttu-id="162d5-117">Wenn Sie eine Vorgängerversion von SQL Server 2016 verwenden, können Sie eine ähnliche Funktionalität mithilfe einer Sicht erzielen:</span><span class="sxs-lookup"><span data-stu-id="162d5-117">If you are using a version of SQL Server prior to 2016, you can achieve similar functionality using a view:</span></span>

      ```sql
      CREATE VIEW vw_MyTable
      AS
          RETURN SELECT * FROM MyTable
          WHERE UserName = SUSER_SNAME()
      GO
      ```

- <span data-ttu-id="162d5-118">Erstellen Sie gespeicherte Prozeduren, um Daten auszuwählen, einzufügen, zu aktualisieren und zu löschen.</span><span class="sxs-lookup"><span data-stu-id="162d5-118">Create stored procedures to select, insert, update, and delete data.</span></span> <span data-ttu-id="162d5-119">Wenn die Filterung mithilfe einer Sicherheitsrichtlinie durchgeführt wird, sollten die gespeicherten Prozeduren diese Vorgänge direkt mit der Basistabelle durchführen. Wenn die Filterung mithilfe einer Sicht durchgeführt wird, sollten die gespeicherten Prozeduren stattdessen mit der Sicht arbeiten.</span><span class="sxs-lookup"><span data-stu-id="162d5-119">If the filtering is enacted by a security policy, the stored procedures should perform these operations on the base table directly; otherwise, if the filtering is enacted by a view, the stored procedures should instead operate against the view.</span></span> <span data-ttu-id="162d5-120">Die Sicherheitsrichtlinie oder Sicht filtert die durch Benutzerabfragen zurückgegebenen oder geänderten Zeilen automatisch, und die gespeicherte Prozedur bietet eine stärkere Sicherheitsgrenze, um zu verhindern, dass Benutzer mit direktem Zugriff auf die Abfragen erfolgreich Abfragen ausführen, die die Existenz gefilterter Daten ableiten können.</span><span class="sxs-lookup"><span data-stu-id="162d5-120">The security policy or view will automatically filter the rows returned or modified by user queries, and the stored procedure will provide a harder security boundary to prevent users with direct query access from successfully running queries that can infer the existence of filtered data.</span></span>

- <span data-ttu-id="162d5-121">Erfassen Sie bei gespeicherten Prozeduren, die Daten einfügen, den Benutzernamen mit der in der Sicherheitsrichtlinie oder Sicht angegebenen Funktion, und fügen Sie diesen Wert in die Spalte „UserName“ ein.</span><span class="sxs-lookup"><span data-stu-id="162d5-121">For stored procedures that insert data, capture the user name using the same function specified in the security policy or view, and insert that value into the UserName column.</span></span>

- <span data-ttu-id="162d5-122">Verweigern Sie der Rolle `public` alle Berechtigungen für die Tabellen (und Sichten, falls zutreffend).</span><span class="sxs-lookup"><span data-stu-id="162d5-122">Deny all permissions on the tables (and views, if applicable) to the `public` role.</span></span> <span data-ttu-id="162d5-123">Die Benutzer können keine Berechtigungen aus anderen Datenbankrollen erben, weil das Filterprädikat nicht auf Rollen, sondern auf Benutzer- oder Anmeldenamen basiert.</span><span class="sxs-lookup"><span data-stu-id="162d5-123">Users will not be able to inherit permissions from other database roles, because the filter predicate is based on user or login names, not on roles.</span></span>

- <span data-ttu-id="162d5-124">Gewähren Sie den Datenbankrollen die Berechtigung EXECUTE für die gespeicherten Prozeduren.</span><span class="sxs-lookup"><span data-stu-id="162d5-124">Grant EXECUTE on the stored procedures to database roles.</span></span> <span data-ttu-id="162d5-125">Die Benutzer können nur auf Daten zugreifen, die über die gespeicherten Prozeduren bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="162d5-125">Users can only access data through the stored procedures provided.</span></span>

## <a name="see-also"></a><span data-ttu-id="162d5-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="162d5-126">See also</span></span>

- [<span data-ttu-id="162d5-127">Sicherheit auf Zeilenebene</span><span class="sxs-lookup"><span data-stu-id="162d5-127">Row-Level Security</span></span>](/sql/relational-databases/security/row-level-security)
- [<span data-ttu-id="162d5-128">Sichern von ADO.NET-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="162d5-128">Securing ADO.NET Applications</span></span>](../securing-ado-net-applications.md)
- [<span data-ttu-id="162d5-129">Übersicht über die SQL Server-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="162d5-129">Overview of SQL Server Security</span></span>](overview-of-sql-server-security.md)
- [<span data-ttu-id="162d5-130">Anwendungssicherheitsszenarios in SQL Server</span><span class="sxs-lookup"><span data-stu-id="162d5-130">Application Security Scenarios in SQL Server</span></span>](application-security-scenarios-in-sql-server.md)
- [<span data-ttu-id="162d5-131">Verwalten von Berechtigungen mit gespeicherten Prozeduren in SQL Server</span><span class="sxs-lookup"><span data-stu-id="162d5-131">Managing Permissions with Stored Procedures in SQL Server</span></span>](managing-permissions-with-stored-procedures-in-sql-server.md)
- [<span data-ttu-id="162d5-132">Schreiben von sicherem dynamischem SQL in SQL Server</span><span class="sxs-lookup"><span data-stu-id="162d5-132">Writing Secure Dynamic SQL in SQL Server</span></span>](writing-secure-dynamic-sql-in-sql-server.md)
- [<span data-ttu-id="162d5-133">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="162d5-133">ADO.NET Overview</span></span>](../ado-net-overview.md)
