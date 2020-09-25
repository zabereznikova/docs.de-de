---
title: Einführung in die CLR-Integration in SQL Server
description: Die CLR-Integration in SQL Server unterstützt gespeicherte Prozeduren, Trigger, benutzerdefinierte Funktionen, benutzerdefinierte Typen und benutzerdefinierte Aggregate in verwaltetem Code.
ms.date: 03/30/2017
ms.assetid: 551d2290-ed80-49be-b377-44b32444da1c
ms.openlocfilehash: 969afd7dea4aadf88bbb69cbe85d9cd84b233e4f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91194556"
---
# <a name="introduction-to-sql-server-clr-integration"></a><span data-ttu-id="191aa-103">Einführung in die CLR-Integration in SQL Server</span><span class="sxs-lookup"><span data-stu-id="191aa-103">Introduction to SQL Server CLR Integration</span></span>

<span data-ttu-id="191aa-104">CLR (Common Language Runtime) steht im Mittelpunkt von Microsoft .NET Framework und stellt die Ausführungsumgebung für sämtlichen .NET Framework-Code bereit.</span><span class="sxs-lookup"><span data-stu-id="191aa-104">The common language runtime (CLR) is the heart of the Microsoft .NET Framework and provides the execution environment for all .NET Framework code.</span></span> <span data-ttu-id="191aa-105">In CLR geschriebener Code wird als verwalteter Code bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="191aa-105">Code that runs within the CLR is referred to as managed code.</span></span> <span data-ttu-id="191aa-106">CLR stellt verschiedene Funktionen und Dienste für die Programmausführung bereit, unter anderem Just-In-Time-Kompilierung (JIT), Speicherzuordnung und -verwaltung, Erzwingen der Typsicherheit, Ausnahmebehandlung, Threadverwaltung und Sicherheit.</span><span class="sxs-lookup"><span data-stu-id="191aa-106">The CLR provides various functions and services required for program execution, including just-in-time (JIT) compilation, allocating and managing memory, enforcing type safety, exception handling, thread management, and security.</span></span>  
  
 <span data-ttu-id="191aa-107">Mit der von Microsoft SQL Server gehosteten CLR ("CLR-Integration" genannt) können Sie gespeicherte Prozeduren, Trigger, benutzerdefinierte Funktionen, benutzerdefinierte Typen (UDT) und benutzerdefinierte Aggregate in verwaltetem Code erstellen.</span><span class="sxs-lookup"><span data-stu-id="191aa-107">With the CLR hosted in Microsoft SQL Server (called CLR integration), you can author stored procedures, triggers, user-defined functions, user-defined types, and user-defined aggregates in managed code.</span></span> <span data-ttu-id="191aa-108">Da verwalteter Code vor der Ausführung in systemeigenen Code kompiliert wird, können Sie in manchen Fällen einen erheblichen Leistungsanstieg erreichen.</span><span class="sxs-lookup"><span data-stu-id="191aa-108">Because managed code compiles to native code prior to execution, you can achieve significant performance increases in some scenarios.</span></span>  
  
 <span data-ttu-id="191aa-109">Verwalteter Code kann mithilfe von Codezugriffssicherheit (CAS – Code Access Security), Codelinks und Anwendungsdomänen verhindern, dass Assemblys bestimmte Vorgänge ausführen.</span><span class="sxs-lookup"><span data-stu-id="191aa-109">Managed code uses Code Access Security (CAS), code links, and application domains to prevent assemblies from performing certain operations.</span></span> <span data-ttu-id="191aa-110">In SQL Server trägt die Verwendung der Codezugriffssicherheit zur Sicherung des verwalteten Codes und zum Schutz des Betriebssystems und des Datenbankservers vor schädigenden Eingriffen bei.</span><span class="sxs-lookup"><span data-stu-id="191aa-110">SQL Server uses CAS to help secure the managed code and prevent compromise of the operating system or database server.</span></span>  
  
 <span data-ttu-id="191aa-111">In diesem Abschnitt sollen die Informationen bereitgestellt werden, die für den Einstieg in das Programmieren mit der CLR-Integration in SQL Server erforderlich sind. Es ist nicht Ziel dieses Abschnitts, das Thema umfassend abzudecken.</span><span class="sxs-lookup"><span data-stu-id="191aa-111">This section is meant to provide only enough information to get started programming with SQL Server CLR integration, and is not meant to be comprehensive.</span></span> <span data-ttu-id="191aa-112">Weitere ausführliche Informationen finden Sie in der Onlinedokumentation zu SQL Server für die von Ihnen verwendete Version von SQL Server.</span><span class="sxs-lookup"><span data-stu-id="191aa-112">For more detailed information, see the version of SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 <span data-ttu-id="191aa-113">**SQL Server-Dokumentation**</span><span class="sxs-lookup"><span data-stu-id="191aa-113">**SQL Server documentation**</span></span>  
  
- [<span data-ttu-id="191aa-114">Übersicht über die CLR-Integration (Common Language Runtime)</span><span class="sxs-lookup"><span data-stu-id="191aa-114">Common Language Runtime (CLR) Integration Overview</span></span>](/sql/relational-databases/clr-integration/common-language-runtime-integration-overview)  
  
## <a name="enabling-clr-integration"></a><span data-ttu-id="191aa-115">Aktivieren der CLR-Integration</span><span class="sxs-lookup"><span data-stu-id="191aa-115">Enabling CLR Integration</span></span>  

 <span data-ttu-id="191aa-116">Die Funktion zur Integration der Common Language Runtime (CLR) ist in Microsoft SQL-Server in der Standardeinstellung deaktiviert und muss aktiviert werden, damit die mithilfe der CLR-Integration implementierten Objekte verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="191aa-116">The common language runtime (CLR) integration feature is off by default in Microsoft SQL Server, and must be enabled in order to use objects that are implemented using CLR integration.</span></span> <span data-ttu-id="191aa-117">Um die CLR-Integration mit Transact-SQL zu aktivieren, verwenden Sie Option `clr enabled` der gespeicherten Prozedur `sp_configure` wie folgt:</span><span class="sxs-lookup"><span data-stu-id="191aa-117">To enable CLR integration using Transact-SQL, use the `clr enabled` option of the `sp_configure` stored procedure as shown:</span></span>  
  
```sql  
sp_configure 'clr enabled', 1  
GO  
RECONFIGURE  
GO  
```  
  
 <span data-ttu-id="191aa-118">Sie können die CLR-Integration deaktivieren, indem Sie für die `clr enabled`-Option 0 festlegen.</span><span class="sxs-lookup"><span data-stu-id="191aa-118">You can disable CLR integration by setting the `clr enabled` option to 0.</span></span> <span data-ttu-id="191aa-119">Wenn Sie die CLR-Integration deaktivieren, stoppt SQL Server die Ausführung aller CLR-Routinen und entlädt alle Anwendungsdomänen.</span><span class="sxs-lookup"><span data-stu-id="191aa-119">When you disable CLR integration, SQL Server stops executing all CLR routines and unloads all application domains.</span></span>  
  
 <span data-ttu-id="191aa-120">Weitere ausführliche Informationen finden Sie in der Onlinedokumentation zu SQL Server für die von Ihnen verwendete Version von SQL Server.</span><span class="sxs-lookup"><span data-stu-id="191aa-120">For more detailed information, see the version of SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 <span data-ttu-id="191aa-121">**SQL Server-Dokumentation**</span><span class="sxs-lookup"><span data-stu-id="191aa-121">**SQL Server documentation**</span></span>  
  
- [<span data-ttu-id="191aa-122">Aktivieren der CLR-Integration</span><span class="sxs-lookup"><span data-stu-id="191aa-122">Enabling CLR Integration</span></span>](/sql/relational-databases/clr-integration/clr-integration-enabling)  
  
## <a name="deploying-a-clr-assembly"></a><span data-ttu-id="191aa-123">Bereitstellen einer CLR-Assembly</span><span class="sxs-lookup"><span data-stu-id="191aa-123">Deploying a CLR Assembly</span></span>  

 <span data-ttu-id="191aa-124">Sobald die CLR-Methoden auf dem Testserver getestet und verifiziert wurden, können sie mit einem Bereitstellungsskript auf die Produktionsserver verteilt werden.</span><span class="sxs-lookup"><span data-stu-id="191aa-124">Once the CLR methods have been tested and verified on the test server, they can be distributed to production servers using a deployment script.</span></span> <span data-ttu-id="191aa-125">Das Bereitstellungsskript kann manuell oder mit SQL Server Management Studio generiert werden.</span><span class="sxs-lookup"><span data-stu-id="191aa-125">The deployment script can be generated manually, or by using SQL Server Management Studio.</span></span> <span data-ttu-id="191aa-126">Ausführlichere Informationen finden Sie in der-Version SQL Server Dokumentation für die verwendete Version von SQL Server.</span><span class="sxs-lookup"><span data-stu-id="191aa-126">For more detailed information, see the version of SQL Server documentation for the version of SQL Server you are using.</span></span>  
  
 <span data-ttu-id="191aa-127">**SQL Server-Dokumentation**</span><span class="sxs-lookup"><span data-stu-id="191aa-127">**SQL Server documentation**</span></span>  
  
1. [<span data-ttu-id="191aa-128">Bereitstellen von CLR-Datenbankobjekten</span><span class="sxs-lookup"><span data-stu-id="191aa-128">Deploying CLR Database Objects</span></span>](/sql/relational-databases/clr-integration/deploying-clr-database-objects)  
  
## <a name="clr-integration-security"></a><span data-ttu-id="191aa-129">Sicherheit der CLR-Integration</span><span class="sxs-lookup"><span data-stu-id="191aa-129">CLR Integration Security</span></span>  

 <span data-ttu-id="191aa-130">Das Sicherheitsmodell der Microsoft SQL Server-Integration in der Common Language Runtime (CLR) von Microsoft .NET Framework verwaltet und sichert den Zugriff zwischen verschiedenen Typen von CLR-Objekten und Nicht-CLR-Objekten, die in SQL Server ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="191aa-130">The security model of the Microsoft SQL Server integration with the Microsoft .NET Framework common language runtime (CLR) manages and secures access between different types of CLR and non-CLR objects running within SQL Server.</span></span> <span data-ttu-id="191aa-131">Diese Objekte können durch eine Transact-SQL-Anweisung oder durch ein anderes, auf dem Server ausgeführtes CLR-Objekt aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="191aa-131">These objects may be called by a Transact-SQL statement or another CLR object running in the server.</span></span>  
  
 <span data-ttu-id="191aa-132">Weitere ausführliche Informationen finden Sie in der Onlinedokumentation zu SQL Server für die von Ihnen verwendete Version von SQL Server.</span><span class="sxs-lookup"><span data-stu-id="191aa-132">For more detailed information, see the version of SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 <span data-ttu-id="191aa-133">**SQL Server-Dokumentation**</span><span class="sxs-lookup"><span data-stu-id="191aa-133">**SQL Server documentation**</span></span>  
  
- [<span data-ttu-id="191aa-134">Sicherheit der CLR-Integration</span><span class="sxs-lookup"><span data-stu-id="191aa-134">CLR Integration Security</span></span>](/sql/relational-databases/clr-integration/security/clr-integration-security)  
  
## <a name="debugging-a-clr-assembly"></a><span data-ttu-id="191aa-135">Debuggen einer CLR-Assembly</span><span class="sxs-lookup"><span data-stu-id="191aa-135">Debugging a CLR Assembly</span></span>  

 <span data-ttu-id="191aa-136">Microsoft SQL Server stellt Unterstützung für das Debuggen von Transact-SQL und CLR-Objekten (Common Language Runtime) in der Datenbank bereit.</span><span class="sxs-lookup"><span data-stu-id="191aa-136">Microsoft SQL Server provides support for debugging Transact-SQL and common language runtime (CLR) objects in the database.</span></span> <span data-ttu-id="191aa-137">Das Debuggen funktioniert sprachübergreifend. Benutzer können problemlos von Transact-SQL zu CLR-Objekten wechseln und umgekehrt.</span><span class="sxs-lookup"><span data-stu-id="191aa-137">Debugging works across languages: users can step seamlessly into CLR objects from Transact-SQL, and vice versa.</span></span>  
  
 <span data-ttu-id="191aa-138">Weitere ausführliche Informationen finden Sie in der Onlinedokumentation zu SQL Server für die von Ihnen verwendete Version von SQL Server.</span><span class="sxs-lookup"><span data-stu-id="191aa-138">For more detailed information, see the version of SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 <span data-ttu-id="191aa-139">**SQL Server-Dokumentation**</span><span class="sxs-lookup"><span data-stu-id="191aa-139">**SQL Server documentation**</span></span>  
  
- [<span data-ttu-id="191aa-140">Debuggen von CLR-Datenbankobjekten</span><span class="sxs-lookup"><span data-stu-id="191aa-140">Debugging CLR Database Objects</span></span>](/sql/relational-databases/clr-integration/debugging-clr-database-objects)  
  
## <a name="see-also"></a><span data-ttu-id="191aa-141">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="191aa-141">See also</span></span>

- [<span data-ttu-id="191aa-142">Codezugriffssicherheit und ADO.NET</span><span class="sxs-lookup"><span data-stu-id="191aa-142">Code Access Security and ADO.NET</span></span>](../code-access-security.md)
- [<span data-ttu-id="191aa-143">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="191aa-143">ADO.NET Overview</span></span>](../ado-net-overview.md)
