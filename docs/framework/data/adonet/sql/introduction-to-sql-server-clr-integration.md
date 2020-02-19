---
title: Einführung in die CLR-Integration in SQL Server
ms.date: 03/30/2017
ms.assetid: 551d2290-ed80-49be-b377-44b32444da1c
ms.openlocfilehash: 41dd89af4f45c673cf6b7283fc39aaf91fd9963c
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452408"
---
# <a name="introduction-to-sql-server-clr-integration"></a><span data-ttu-id="70ea9-102">Einführung in die CLR-Integration in SQL Server</span><span class="sxs-lookup"><span data-stu-id="70ea9-102">Introduction to SQL Server CLR Integration</span></span>
<span data-ttu-id="70ea9-103">CLR (Common Language Runtime) steht im Mittelpunkt von Microsoft .NET Framework und stellt die Ausführungsumgebung für sämtlichen .NET Framework-Code bereit.</span><span class="sxs-lookup"><span data-stu-id="70ea9-103">The common language runtime (CLR) is the heart of the Microsoft .NET Framework and provides the execution environment for all .NET Framework code.</span></span> <span data-ttu-id="70ea9-104">In CLR geschriebener Code wird als verwalteter Code bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="70ea9-104">Code that runs within the CLR is referred to as managed code.</span></span> <span data-ttu-id="70ea9-105">CLR stellt verschiedene Funktionen und Dienste für die Programmausführung bereit, unter anderem Just-In-Time-Kompilierung (JIT), Speicherzuordnung und -verwaltung, Erzwingen der Typsicherheit, Ausnahmebehandlung, Threadverwaltung und Sicherheit.</span><span class="sxs-lookup"><span data-stu-id="70ea9-105">The CLR provides various functions and services required for program execution, including just-in-time (JIT) compilation, allocating and managing memory, enforcing type safety, exception handling, thread management, and security.</span></span>  
  
 <span data-ttu-id="70ea9-106">Mit der von Microsoft SQL Server gehosteten CLR ("CLR-Integration" genannt) können Sie gespeicherte Prozeduren, Trigger, benutzerdefinierte Funktionen, benutzerdefinierte Typen (UDT) und benutzerdefinierte Aggregate in verwaltetem Code erstellen.</span><span class="sxs-lookup"><span data-stu-id="70ea9-106">With the CLR hosted in Microsoft SQL Server (called CLR integration), you can author stored procedures, triggers, user-defined functions, user-defined types, and user-defined aggregates in managed code.</span></span> <span data-ttu-id="70ea9-107">Da verwalteter Code vor der Ausführung in systemeigenen Code kompiliert wird, können Sie in manchen Fällen einen erheblichen Leistungsanstieg erreichen.</span><span class="sxs-lookup"><span data-stu-id="70ea9-107">Because managed code compiles to native code prior to execution, you can achieve significant performance increases in some scenarios.</span></span>  
  
 <span data-ttu-id="70ea9-108">Verwalteter Code kann mithilfe von Codezugriffssicherheit (CAS – Code Access Security), Codelinks und Anwendungsdomänen verhindern, dass Assemblys bestimmte Vorgänge ausführen.</span><span class="sxs-lookup"><span data-stu-id="70ea9-108">Managed code uses Code Access Security (CAS), code links, and application domains to prevent assemblies from performing certain operations.</span></span> <span data-ttu-id="70ea9-109">In SQL Server trägt die Verwendung der Codezugriffssicherheit zur Sicherung des verwalteten Codes und zum Schutz des Betriebssystems und des Datenbankservers vor schädigenden Eingriffen bei.</span><span class="sxs-lookup"><span data-stu-id="70ea9-109">SQL Server uses CAS to help secure the managed code and prevent compromise of the operating system or database server.</span></span>  
  
 <span data-ttu-id="70ea9-110">In diesem Abschnitt sollen die Informationen bereitgestellt werden, die für den Einstieg in das Programmieren mit der CLR-Integration in SQL Server erforderlich sind. Es ist nicht Ziel dieses Abschnitts, das Thema umfassend abzudecken.</span><span class="sxs-lookup"><span data-stu-id="70ea9-110">This section is meant to provide only enough information to get started programming with SQL Server CLR integration, and is not meant to be comprehensive.</span></span> <span data-ttu-id="70ea9-111">Weitere ausführliche Informationen finden Sie in der Onlinedokumentation zu SQL Server für die von Ihnen verwendete Version von SQL Server.</span><span class="sxs-lookup"><span data-stu-id="70ea9-111">For more detailed information, see the version of SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 <span data-ttu-id="70ea9-112">**SQL Server-Dokumentation**</span><span class="sxs-lookup"><span data-stu-id="70ea9-112">**SQL Server documentation**</span></span>  
  
- [<span data-ttu-id="70ea9-113">Übersicht über die CLR-Integration (Common Language Runtime)</span><span class="sxs-lookup"><span data-stu-id="70ea9-113">Common Language Runtime (CLR) Integration Overview</span></span>](/sql/relational-databases/clr-integration/common-language-runtime-integration-overview)  
  
## <a name="enabling-clr-integration"></a><span data-ttu-id="70ea9-114">Aktivieren der CLR-Integration</span><span class="sxs-lookup"><span data-stu-id="70ea9-114">Enabling CLR Integration</span></span>  
 <span data-ttu-id="70ea9-115">Die Funktion zur Integration der Common Language Runtime (CLR) ist in Microsoft SQL-Server in der Standardeinstellung deaktiviert und muss aktiviert werden, damit die mithilfe der CLR-Integration implementierten Objekte verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="70ea9-115">The common language runtime (CLR) integration feature is off by default in Microsoft SQL Server, and must be enabled in order to use objects that are implemented using CLR integration.</span></span> <span data-ttu-id="70ea9-116">Um die CLR-Integration mit Transact-SQL zu aktivieren, verwenden Sie Option `clr enabled` der gespeicherten Prozedur `sp_configure` wie folgt:</span><span class="sxs-lookup"><span data-stu-id="70ea9-116">To enable CLR integration using Transact-SQL, use the `clr enabled` option of the `sp_configure` stored procedure as shown:</span></span>  
  
```sql  
sp_configure 'clr enabled', 1  
GO  
RECONFIGURE  
GO  
```  
  
 <span data-ttu-id="70ea9-117">Sie können die CLR-Integration deaktivieren, indem Sie für die `clr enabled`-Option 0 festlegen.</span><span class="sxs-lookup"><span data-stu-id="70ea9-117">You can disable CLR integration by setting the `clr enabled` option to 0.</span></span> <span data-ttu-id="70ea9-118">Wenn Sie die CLR-Integration deaktivieren, stoppt SQL Server die Ausführung aller CLR-Routinen und entlädt alle Anwendungsdomänen.</span><span class="sxs-lookup"><span data-stu-id="70ea9-118">When you disable CLR integration, SQL Server stops executing all CLR routines and unloads all application domains.</span></span>  
  
 <span data-ttu-id="70ea9-119">Weitere ausführliche Informationen finden Sie in der Onlinedokumentation zu SQL Server für die von Ihnen verwendete Version von SQL Server.</span><span class="sxs-lookup"><span data-stu-id="70ea9-119">For more detailed information, see the version of SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 <span data-ttu-id="70ea9-120">**SQL Server-Dokumentation**</span><span class="sxs-lookup"><span data-stu-id="70ea9-120">**SQL Server documentation**</span></span>  
  
- [<span data-ttu-id="70ea9-121">Aktivieren der CLR-Integration</span><span class="sxs-lookup"><span data-stu-id="70ea9-121">Enabling CLR Integration</span></span>](/sql/relational-databases/clr-integration/clr-integration-enabling)  
  
## <a name="deploying-a-clr-assembly"></a><span data-ttu-id="70ea9-122">Bereitstellen einer CLR-Assembly</span><span class="sxs-lookup"><span data-stu-id="70ea9-122">Deploying a CLR Assembly</span></span>  
 <span data-ttu-id="70ea9-123">Sobald die CLR-Methoden auf dem Testserver getestet und verifiziert wurden, können sie mit einem Bereitstellungsskript auf die Produktionsserver verteilt werden.</span><span class="sxs-lookup"><span data-stu-id="70ea9-123">Once the CLR methods have been tested and verified on the test server, they can be distributed to production servers using a deployment script.</span></span> <span data-ttu-id="70ea9-124">Das Bereitstellungsskript kann manuell oder mit SQL Server Management Studio generiert werden.</span><span class="sxs-lookup"><span data-stu-id="70ea9-124">The deployment script can be generated manually, or by using SQL Server Management Studio.</span></span> <span data-ttu-id="70ea9-125">Ausführlichere Informationen finden Sie in der-Version SQL Server Dokumentation für die verwendete Version von SQL Server.</span><span class="sxs-lookup"><span data-stu-id="70ea9-125">For more detailed information, see the version of SQL Server documentation for the version of SQL Server you are using.</span></span>  
  
 <span data-ttu-id="70ea9-126">**SQL Server-Dokumentation**</span><span class="sxs-lookup"><span data-stu-id="70ea9-126">**SQL Server documentation**</span></span>  
  
1. [<span data-ttu-id="70ea9-127">Bereitstellen von CLR-Datenbankobjekten</span><span class="sxs-lookup"><span data-stu-id="70ea9-127">Deploying CLR Database Objects</span></span>](/sql/relational-databases/clr-integration/deploying-clr-database-objects)  
  
## <a name="clr-integration-security"></a><span data-ttu-id="70ea9-128">Sicherheit der CLR-Integration</span><span class="sxs-lookup"><span data-stu-id="70ea9-128">CLR Integration Security</span></span>  
 <span data-ttu-id="70ea9-129">Das Sicherheitsmodell der Microsoft SQL Server-Integration in der Common Language Runtime (CLR) von Microsoft .NET Framework verwaltet und sichert den Zugriff zwischen verschiedenen Typen von CLR-Objekten und Nicht-CLR-Objekten, die in SQL Server ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="70ea9-129">The security model of the Microsoft SQL Server integration with the Microsoft .NET Framework common language runtime (CLR) manages and secures access between different types of CLR and non-CLR objects running within SQL Server.</span></span> <span data-ttu-id="70ea9-130">Diese Objekte können durch eine Transact-SQL-Anweisung oder durch ein anderes, auf dem Server ausgeführtes CLR-Objekt aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="70ea9-130">These objects may be called by a Transact-SQL statement or another CLR object running in the server.</span></span>  
  
 <span data-ttu-id="70ea9-131">Weitere ausführliche Informationen finden Sie in der Onlinedokumentation zu SQL Server für die von Ihnen verwendete Version von SQL Server.</span><span class="sxs-lookup"><span data-stu-id="70ea9-131">For more detailed information, see the version of SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 <span data-ttu-id="70ea9-132">**SQL Server-Dokumentation**</span><span class="sxs-lookup"><span data-stu-id="70ea9-132">**SQL Server documentation**</span></span>  
  
- [<span data-ttu-id="70ea9-133">Sicherheit der CLR-Integration</span><span class="sxs-lookup"><span data-stu-id="70ea9-133">CLR Integration Security</span></span>](/sql/relational-databases/clr-integration/security/clr-integration-security)  
  
## <a name="debugging-a-clr-assembly"></a><span data-ttu-id="70ea9-134">Debuggen einer CLR-Assembly</span><span class="sxs-lookup"><span data-stu-id="70ea9-134">Debugging a CLR Assembly</span></span>  
 <span data-ttu-id="70ea9-135">Microsoft SQL Server stellt Unterstützung für das Debuggen von Transact-SQL und CLR-Objekten (Common Language Runtime) in der Datenbank bereit.</span><span class="sxs-lookup"><span data-stu-id="70ea9-135">Microsoft SQL Server provides support for debugging Transact-SQL and common language runtime (CLR) objects in the database.</span></span> <span data-ttu-id="70ea9-136">Das Debuggen funktioniert sprachübergreifend. Benutzer können problemlos von Transact-SQL zu CLR-Objekten wechseln und umgekehrt.</span><span class="sxs-lookup"><span data-stu-id="70ea9-136">Debugging works across languages: users can step seamlessly into CLR objects from Transact-SQL, and vice versa.</span></span>  
  
 <span data-ttu-id="70ea9-137">Weitere ausführliche Informationen finden Sie in der Onlinedokumentation zu SQL Server für die von Ihnen verwendete Version von SQL Server.</span><span class="sxs-lookup"><span data-stu-id="70ea9-137">For more detailed information, see the version of SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 <span data-ttu-id="70ea9-138">**SQL Server-Dokumentation**</span><span class="sxs-lookup"><span data-stu-id="70ea9-138">**SQL Server documentation**</span></span>  
  
- [<span data-ttu-id="70ea9-139">Debuggen von CLR-Datenbankobjekten</span><span class="sxs-lookup"><span data-stu-id="70ea9-139">Debugging CLR Database Objects</span></span>](/sql/relational-databases/clr-integration/debugging-clr-database-objects)  
  
## <a name="see-also"></a><span data-ttu-id="70ea9-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="70ea9-140">See also</span></span>

- [<span data-ttu-id="70ea9-141">Codezugriffssicherheit und ADO.NET</span><span class="sxs-lookup"><span data-stu-id="70ea9-141">Code Access Security and ADO.NET</span></span>](../code-access-security.md)
- [<span data-ttu-id="70ea9-142">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="70ea9-142">ADO.NET Overview</span></span>](../ado-net-overview.md)
