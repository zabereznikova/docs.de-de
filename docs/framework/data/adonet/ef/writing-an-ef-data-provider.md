---
title: Schreiben eines Entity Framework-Datenanbieters
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 092e88c4-a301-453a-b5c3-5740c6575a9f
caps.latest.revision: 3
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: cb969589afd4474d9bdfa3a475d8325c1717ab13
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="writing-an-entity-framework-data-provider"></a><span data-ttu-id="e645b-102">Schreiben eines Entity Framework-Datenanbieters</span><span class="sxs-lookup"><span data-stu-id="e645b-102">Writing an Entity Framework Data Provider</span></span>
<span data-ttu-id="e645b-103">In diesem Abschnitt wird erläutert, wie zum Schreiben einer [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] -Anbieter zur Unterstützung einer Datenquelle als SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e645b-103">This section discusses how to write an [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] provider to support a data source other than SQL Server.</span></span> <span data-ttu-id="e645b-104">Die [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] umfasst einen Anbieter, die SQL Server unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e645b-104">The [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] includes a provider that supports SQL Server.</span></span>  
  
## <a name="introducing-the-entity-framework-provider-model"></a><span data-ttu-id="e645b-105">Einführung in das Entity Framework-Anbietermodell</span><span class="sxs-lookup"><span data-stu-id="e645b-105">Introducing the Entity Framework Provider Model</span></span>  
 <span data-ttu-id="e645b-106">[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] ist Datenbank-unabhängig. Sie können mit dem ADO.NET-Anbietermodell einen Anbieter schreiben, um eine Verbindung mit verschiedenen Datenquellen herzustellen.</span><span class="sxs-lookup"><span data-stu-id="e645b-106">The [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] is database independent, and you can write a provider by using the ADO.NET Provider Model to connect to a diverse set of data sources.</span></span>  
  
 <span data-ttu-id="e645b-107">Der mit dem ADO.NET-Datenanbietermodell erstellte Entity Framework-Datenanbieter führt die folgenden Funktionen aus:</span><span class="sxs-lookup"><span data-stu-id="e645b-107">The Entity Framework data provider (built using the ADO.NET Data Provider model) performs the following functions:</span></span>  
  
-   <span data-ttu-id="e645b-108">Zuordnen von primitiven Typen des Entity Data Model (EDM) zu Anbietertypen.</span><span class="sxs-lookup"><span data-stu-id="e645b-108">Maps Entity Data Model (EDM) primitive types to provider types.</span></span>  
  
-   <span data-ttu-id="e645b-109">Bereitstellen von anbieterspezifischen Funktionen.</span><span class="sxs-lookup"><span data-stu-id="e645b-109">Exposes provider-specific functions.</span></span>  
  
-   <span data-ttu-id="e645b-110">Generieren von anbieterspezifischen Befehlen für einen angegebenen DbQueryCommandTree zur Unterstützung von [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]-Abfragen.</span><span class="sxs-lookup"><span data-stu-id="e645b-110">Generates provider-specific commands for a given DbQueryCommandTree to support [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] queries.</span></span>  
  
-   <span data-ttu-id="e645b-111">Generieren von anbieterspezifischen Updatebefehlen für einen angegebenen DbModificationCommandTree zur Unterstützung von Updates durch den [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e645b-111">Generates provider-specific update commands for a given DbModificationCommandTree to support updates through the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span></span>  
  
-   <span data-ttu-id="e645b-112">Bereitstellen von Zuordnungsdateien für die Speicherschemadefinition zur Unterstützung der Generierung eines Modells auf Grundlage einer Datenbank.</span><span class="sxs-lookup"><span data-stu-id="e645b-112">Exposes mapping files for the store schema definition, to support generation of a model based on a database.</span></span>  
  
-   <span data-ttu-id="e645b-113">Bereitstellen von Metadaten (z. B. Tabellen und Sichten) über ein konzeptionelles Modell.</span><span class="sxs-lookup"><span data-stu-id="e645b-113">Exposes metadata (tables and views, for example) via a conceptual model.</span></span>  
  
 <span data-ttu-id="e645b-114">![b42a7a5c&#45;0ac0&#45;4911&#45;86be&#45;0460a78760ba](../../../../../docs/framework/data/adonet/ef/media/b42a7a5c-0ac0-4911-86be-0460a78760ba.gif "b42a7a5c-0ac0-4911-86be-0460a78760ba")</span><span class="sxs-lookup"><span data-stu-id="e645b-114">![b42a7a5c&#45;0ac0&#45;4911&#45;86be&#45;0460a78760ba](../../../../../docs/framework/data/adonet/ef/media/b42a7a5c-0ac0-4911-86be-0460a78760ba.gif "b42a7a5c-0ac0-4911-86be-0460a78760ba")</span></span>  
  
## <a name="sample"></a><span data-ttu-id="e645b-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e645b-115">Sample</span></span>  
 <span data-ttu-id="e645b-116">Finden Sie unter der [Entity Framework-Beispielanbieter](http://go.microsoft.com/fwlink/?LinkId=180616) ein Beispiel für eine [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] Anbieter, der eine Datenquelle als SQL Server unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e645b-116">See the [Entity Framework Sample Provider](http://go.microsoft.com/fwlink/?LinkId=180616) for a sample of an [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] provider that supports a data source other than SQL Server.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e645b-117">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="e645b-117">In This Section</span></span>  
 [<span data-ttu-id="e645b-118">SQL-Generierung</span><span class="sxs-lookup"><span data-stu-id="e645b-118">SQL Generation</span></span>](../../../../../docs/framework/data/adonet/ef/sql-generation.md)  
  
 [<span data-ttu-id="e645b-119">Generierung von Änderungen in SQL</span><span class="sxs-lookup"><span data-stu-id="e645b-119">Modification SQL Generation</span></span>](../../../../../docs/framework/data/adonet/ef/modification-sql-generation.md)  
  
 [<span data-ttu-id="e645b-120">Anbietermanifestspezifikation</span><span class="sxs-lookup"><span data-stu-id="e645b-120">Provider Manifest Specification</span></span>](../../../../../docs/framework/data/adonet/ef/provider-manifest-specification.md)  
  
## <a name="see-also"></a><span data-ttu-id="e645b-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e645b-121">See Also</span></span>  
 [<span data-ttu-id="e645b-122">Arbeiten mit Datenanbietern</span><span class="sxs-lookup"><span data-stu-id="e645b-122">Working with Data Providers</span></span>](../../../../../docs/framework/data/adonet/ef/working-with-data-providers.md)
