---
title: Einführung in die CLR-Integration in SQL Server
description: Die CLR-Integration in SQL Server unterstützt gespeicherte Prozeduren, Trigger, benutzerdefinierte Funktionen, benutzerdefinierte Typen und benutzerdefinierte Aggregate in verwaltetem Code.
ms.date: 03/30/2017
ms.assetid: 551d2290-ed80-49be-b377-44b32444da1c
ms.openlocfilehash: fa2ef68792d09cf94b3e0680a14bd79f9b593999
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286429"
---
# <a name="introduction-to-sql-server-clr-integration"></a><span data-ttu-id="e38e6-103">Einführung in die CLR-Integration in SQL Server</span><span class="sxs-lookup"><span data-stu-id="e38e6-103">Introduction to SQL Server CLR Integration</span></span>
<span data-ttu-id="e38e6-104">CLR (Common Language Runtime) steht im Mittelpunkt von Microsoft .NET Framework und stellt die Ausführungsumgebung für sämtlichen .NET Framework-Code bereit.</span><span class="sxs-lookup"><span data-stu-id="e38e6-104">The common language runtime (CLR) is the heart of the Microsoft .NET Framework and provides the execution environment for all .NET Framework code.</span></span> <span data-ttu-id="e38e6-105">In CLR geschriebener Code wird als verwalteter Code bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="e38e6-105">Code that runs within the CLR is referred to as managed code.</span></span> <span data-ttu-id="e38e6-106">CLR stellt verschiedene Funktionen und Dienste für die Programmausführung bereit, unter anderem Just-In-Time-Kompilierung (JIT), Speicherzuordnung und -verwaltung, Erzwingen der Typsicherheit, Ausnahmebehandlung, Threadverwaltung und Sicherheit.</span><span class="sxs-lookup"><span data-stu-id="e38e6-106">The CLR provides various functions and services required for program execution, including just-in-time (JIT) compilation, allocating and managing memory, enforcing type safety, exception handling, thread management, and security.</span></span>  
  
 <span data-ttu-id="e38e6-107">Mit der von Microsoft SQL Server gehosteten CLR ("CLR-Integration" genannt) können Sie gespeicherte Prozeduren, Trigger, benutzerdefinierte Funktionen, benutzerdefinierte Typen (UDT) und benutzerdefinierte Aggregate in verwaltetem Code erstellen.</span><span class="sxs-lookup"><span data-stu-id="e38e6-107">With the CLR hosted in Microsoft SQL Server (called CLR integration), you can author stored procedures, triggers, user-defined functions, user-defined types, and user-defined aggregates in managed code.</span></span> <span data-ttu-id="e38e6-108">Da verwalteter Code vor der Ausführung in systemeigenen Code kompiliert wird, können Sie in manchen Fällen einen erheblichen Leistungsanstieg erreichen.</span><span class="sxs-lookup"><span data-stu-id="e38e6-108">Because managed code compiles to native code prior to execution, you can achieve significant performance increases in some scenarios.</span></span>  
  
 <span data-ttu-id="e38e6-109">Verwalteter Code kann mithilfe von Codezugriffssicherheit (CAS – Code Access Security), Codelinks und Anwendungsdomänen verhindern, dass Assemblys bestimmte Vorgänge ausführen.</span><span class="sxs-lookup"><span data-stu-id="e38e6-109">Managed code uses Code Access Security (CAS), code links, and application domains to prevent assemblies from performing certain operations.</span></span> <span data-ttu-id="e38e6-110">In SQL Server trägt die Verwendung der Codezugriffssicherheit zur Sicherung des verwalteten Codes und zum Schutz des Betriebssystems und des Datenbankservers vor schädigenden Eingriffen bei.</span><span class="sxs-lookup"><span data-stu-id="e38e6-110">SQL Server uses CAS to help secure the managed code and prevent compromise of the operating system or database server.</span></span>  
  
 <span data-ttu-id="e38e6-111">In diesem Abschnitt sollen die Informationen bereitgestellt werden, die für den Einstieg in das Programmieren mit der CLR-Integration in SQL Server erforderlich sind. Es ist nicht Ziel dieses Abschnitts, das Thema umfassend abzudecken.</span><span class="sxs-lookup"><span data-stu-id="e38e6-111">This section is meant to provide only enough information to get started programming with SQL Server CLR integration, and is not meant to be comprehensive.</span></span> <span data-ttu-id="e38e6-112">Weitere ausführliche Informationen finden Sie in der Onlinedokumentation zu SQL Server für die von Ihnen verwendete Version von SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e38e6-112">For more detailed information, see the version of SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 <span data-ttu-id="e38e6-113">**Dokumentation zu SQL Server**</span><span class="sxs-lookup"><span data-stu-id="e38e6-113">**SQL Server documentation**</span></span>  
  
- [<span data-ttu-id="e38e6-114">Übersicht über die CLR-Integration (Common Language Runtime)</span><span class="sxs-lookup"><span data-stu-id="e38e6-114">Common Language Runtime (CLR) Integration Overview</span></span>](/sql/relational-databases/clr-integration/common-language-runtime-integration-overview)  
  
## <a name="enabling-clr-integration"></a><span data-ttu-id="e38e6-115">Aktivieren der CLR-Integration</span><span class="sxs-lookup"><span data-stu-id="e38e6-115">Enabling CLR Integration</span></span>  
 <span data-ttu-id="e38e6-116">Die Funktion zur Integration der Common Language Runtime (CLR) ist in Microsoft SQL-Server in der Standardeinstellung deaktiviert und muss aktiviert werden, damit die mithilfe der CLR-Integration implementierten Objekte verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="e38e6-116">The common language runtime (CLR) integration feature is off by default in Microsoft SQL Server, and must be enabled in order to use objects that are implemented using CLR integration.</span></span> <span data-ttu-id="e38e6-117">Um die CLR-Integration mit Transact-SQL zu aktivieren, verwenden Sie Option `clr enabled` der gespeicherten Prozedur `sp_configure` wie folgt:</span><span class="sxs-lookup"><span data-stu-id="e38e6-117">To enable CLR integration using Transact-SQL, use the `clr enabled` option of the `sp_configure` stored procedure as shown:</span></span>  
  
```sql  
sp_configure 'clr enabled', 1  
GO  
RECONFIGURE  
GO  
```  
  
 <span data-ttu-id="e38e6-118">Sie können die CLR-Integration deaktivieren, indem Sie für die `clr enabled`-Option 0 festlegen.</span><span class="sxs-lookup"><span data-stu-id="e38e6-118">You can disable CLR integration by setting the `clr enabled` option to 0.</span></span> <span data-ttu-id="e38e6-119">Wenn Sie die CLR-Integration deaktivieren, stoppt SQL Server die Ausführung aller CLR-Routinen und entlädt alle Anwendungsdomänen.</span><span class="sxs-lookup"><span data-stu-id="e38e6-119">When you disable CLR integration, SQL Server stops executing all CLR routines and unloads all application domains.</span></span>  
  
 <span data-ttu-id="e38e6-120">Weitere ausführliche Informationen finden Sie in der Onlinedokumentation zu SQL Server für die von Ihnen verwendete Version von SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e38e6-120">For more detailed information, see the version of SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 <span data-ttu-id="e38e6-121">**Dokumentation zu SQL Server**</span><span class="sxs-lookup"><span data-stu-id="e38e6-121">**SQL Server documentation**</span></span>  
  
- [<span data-ttu-id="e38e6-122">Aktivieren der CLR-Integration</span><span class="sxs-lookup"><span data-stu-id="e38e6-122">Enabling CLR Integration</span></span>](/sql/relational-databases/clr-integration/clr-integration-enabling)  
  
## <a name="deploying-a-clr-assembly"></a><span data-ttu-id="e38e6-123">Bereitstellen einer CLR-Assembly</span><span class="sxs-lookup"><span data-stu-id="e38e6-123">Deploying a CLR Assembly</span></span>  
 <span data-ttu-id="e38e6-124">Sobald die CLR-Methoden auf dem Testserver getestet und verifiziert wurden, können sie mit einem Bereitstellungsskript auf die Produktionsserver verteilt werden.</span><span class="sxs-lookup"><span data-stu-id="e38e6-124">Once the CLR methods have been tested and verified on the test server, they can be distributed to production servers using a deployment script.</span></span> <span data-ttu-id="e38e6-125">Das Bereitstellungsskript kann manuell oder mit SQL Server Management Studio generiert werden.</span><span class="sxs-lookup"><span data-stu-id="e38e6-125">The deployment script can be generated manually, or by using SQL Server Management Studio.</span></span> <span data-ttu-id="e38e6-126">Ausführlichere Informationen finden Sie in der-Version SQL Server Dokumentation für die verwendete Version von SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e38e6-126">For more detailed information, see the version of SQL Server documentation for the version of SQL Server you are using.</span></span>  
  
 <span data-ttu-id="e38e6-127">**Dokumentation zu SQL Server**</span><span class="sxs-lookup"><span data-stu-id="e38e6-127">**SQL Server documentation**</span></span>  
  
1. [<span data-ttu-id="e38e6-128">Bereitstellen von CLR-Datenbankobjekten</span><span class="sxs-lookup"><span data-stu-id="e38e6-128">Deploying CLR Database Objects</span></span>](/sql/relational-databases/clr-integration/deploying-clr-database-objects)  
  
## <a name="clr-integration-security"></a><span data-ttu-id="e38e6-129">Sicherheit der CLR-Integration</span><span class="sxs-lookup"><span data-stu-id="e38e6-129">CLR Integration Security</span></span>  
 <span data-ttu-id="e38e6-130">Das Sicherheitsmodell der Microsoft SQL Server-Integration in der Common Language Runtime (CLR) von Microsoft .NET Framework verwaltet und sichert den Zugriff zwischen verschiedenen Typen von CLR-Objekten und Nicht-CLR-Objekten, die in SQL Server ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="e38e6-130">The security model of the Microsoft SQL Server integration with the Microsoft .NET Framework common language runtime (CLR) manages and secures access between different types of CLR and non-CLR objects running within SQL Server.</span></span> <span data-ttu-id="e38e6-131">Diese Objekte können durch eine Transact-SQL-Anweisung oder durch ein anderes, auf dem Server ausgeführtes CLR-Objekt aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="e38e6-131">These objects may be called by a Transact-SQL statement or another CLR object running in the server.</span></span>  
  
 <span data-ttu-id="e38e6-132">Weitere ausführliche Informationen finden Sie in der Onlinedokumentation zu SQL Server für die von Ihnen verwendete Version von SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e38e6-132">For more detailed information, see the version of SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 <span data-ttu-id="e38e6-133">**Dokumentation zu SQL Server**</span><span class="sxs-lookup"><span data-stu-id="e38e6-133">**SQL Server documentation**</span></span>  
  
- [<span data-ttu-id="e38e6-134">Sicherheit der CLR-Integration</span><span class="sxs-lookup"><span data-stu-id="e38e6-134">CLR Integration Security</span></span>](/sql/relational-databases/clr-integration/security/clr-integration-security)  
  
## <a name="debugging-a-clr-assembly"></a><span data-ttu-id="e38e6-135">Debuggen einer CLR-Assembly</span><span class="sxs-lookup"><span data-stu-id="e38e6-135">Debugging a CLR Assembly</span></span>  
 <span data-ttu-id="e38e6-136">Microsoft SQL Server stellt Unterstützung für das Debuggen von Transact-SQL und CLR-Objekten (Common Language Runtime) in der Datenbank bereit.</span><span class="sxs-lookup"><span data-stu-id="e38e6-136">Microsoft SQL Server provides support for debugging Transact-SQL and common language runtime (CLR) objects in the database.</span></span> <span data-ttu-id="e38e6-137">Das Debuggen funktioniert sprachübergreifend. Benutzer können problemlos von Transact-SQL zu CLR-Objekten wechseln und umgekehrt.</span><span class="sxs-lookup"><span data-stu-id="e38e6-137">Debugging works across languages: users can step seamlessly into CLR objects from Transact-SQL, and vice versa.</span></span>  
  
 <span data-ttu-id="e38e6-138">Weitere ausführliche Informationen finden Sie in der Onlinedokumentation zu SQL Server für die von Ihnen verwendete Version von SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e38e6-138">For more detailed information, see the version of SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 <span data-ttu-id="e38e6-139">**Dokumentation zu SQL Server**</span><span class="sxs-lookup"><span data-stu-id="e38e6-139">**SQL Server documentation**</span></span>  
  
- [<span data-ttu-id="e38e6-140">Debuggen von CLR-Datenbankobjekten</span><span class="sxs-lookup"><span data-stu-id="e38e6-140">Debugging CLR Database Objects</span></span>](/sql/relational-databases/clr-integration/debugging-clr-database-objects)  
  
## <a name="see-also"></a><span data-ttu-id="e38e6-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e38e6-141">See also</span></span>

- [<span data-ttu-id="e38e6-142">Codezugriffssicherheit und ADO.NET</span><span class="sxs-lookup"><span data-stu-id="e38e6-142">Code Access Security and ADO.NET</span></span>](../code-access-security.md)
- [<span data-ttu-id="e38e6-143">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="e38e6-143">ADO.NET Overview</span></span>](../ado-net-overview.md)
