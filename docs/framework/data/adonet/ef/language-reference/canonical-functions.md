---
title: Kanonische Funktionen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bbcc9928-36ea-4dff-9e31-96549ffed958
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: da48efc110669c170fc409e22cb8402f471b22e7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="canonical-functions"></a><span data-ttu-id="518a2-102">Kanonische Funktionen</span><span class="sxs-lookup"><span data-stu-id="518a2-102">Canonical Functions</span></span>
<span data-ttu-id="518a2-103">In diesem Abschnitt werden die von allen Datenanbietern unterstützten und in allen Abfragetechnologien verwendbaren kanonischen Funktionen erläutert.</span><span class="sxs-lookup"><span data-stu-id="518a2-103">This section discusses canonical functions that are supported by all data providers, and can be used by all querying technologies.</span></span> <span data-ttu-id="518a2-104">Kanonische Funktionen können von Anbietern nicht erweitert werden.</span><span class="sxs-lookup"><span data-stu-id="518a2-104">Canonical functions cannot be extended by a provider.</span></span>  
  
 <span data-ttu-id="518a2-105">Diese kanonischen Funktionen werden in die entsprechenden Datenquellenfunktionen der Anbieter übersetzt.</span><span class="sxs-lookup"><span data-stu-id="518a2-105">These canonical functions will be translated to the corresponding data source functionality for the provider.</span></span> <span data-ttu-id="518a2-106">Dadurch können Funktionsaufrufe für Datenquellen in einer allgemeinen Form ausgedrückt werden.</span><span class="sxs-lookup"><span data-stu-id="518a2-106">This allows for function invocations expressed in a common form across data sources.</span></span>  
  
 <span data-ttu-id="518a2-107">Da diese kanonischen Funktionen datenquellenunabhängig sind, werden die Argument- und Rückgabetypen kanonischer Funktionen in Form von Typen im konzeptionellen Modell definiert.</span><span class="sxs-lookup"><span data-stu-id="518a2-107">Because these canonical functions are independent of data sources, argument and return types of canonical functions are defined in terms of types in the conceptual model.</span></span> <span data-ttu-id="518a2-108">Jedoch werden von einigen Datenquellen möglicherweise nicht alle Typen im konzeptionellen Modell unterstützt.</span><span class="sxs-lookup"><span data-stu-id="518a2-108">However, some data sources might not support all types in the conceptual model.</span></span>  
  
 <span data-ttu-id="518a2-109">Wenn in einer [!INCLUDE[esql](../../../../../../includes/esql-md.md)]-Abfrage kanonische Funktionen verwendet werden, werden in Datenquellen die entsprechenden Funktionen aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="518a2-109">When canonical functions are used in an [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query, the appropriate function will be called at the data source.</span></span>  
  
 <span data-ttu-id="518a2-110">Für alle kanonischen Funktionen sind das Verhalten bei NULL-Eingaben sowie die Fehlerbedingungen explizit angegeben.</span><span class="sxs-lookup"><span data-stu-id="518a2-110">All canonical functions have both null-input behavior and error conditions explicitly specified.</span></span> <span data-ttu-id="518a2-111">Speicheranbieter sollten diesen Vorgaben entsprechend vorgehen. Dieses Verhalten wird vom [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] jedoch nicht erzwungen.</span><span class="sxs-lookup"><span data-stu-id="518a2-111">Store providers should comply with that behavior, but [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] does not enforce this behavior.</span></span>  
  
 <span data-ttu-id="518a2-112">LINQ-Szenarios, Abfragen für die [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] bei CLR-Methoden den Methoden in der zugrunde liegenden Datenquelle zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="518a2-112">For LINQ scenarios, queries against the [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] involve mapping CLR methods to methods in the underlying data source.</span></span> <span data-ttu-id="518a2-113">Die CLR-Methoden werden kanonischen Funktionen zugeordnet, sodass bestimmte Methoden unabhängig von der Datenquelle ordnungsgemäß zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="518a2-113">The CLR methods map to canonical functions, so that a specific set of methods will correctly map, regardless of the data source.</span></span>  
  
## <a name="canonical-functions-namespace"></a><span data-ttu-id="518a2-114">Namespace kanonischer Funktionen</span><span class="sxs-lookup"><span data-stu-id="518a2-114">Canonical Functions Namespace</span></span>  
 <span data-ttu-id="518a2-115">Der Namespace für kanonische Funktionen ist <xref:System.Data.Metadata.Edm>.</span><span class="sxs-lookup"><span data-stu-id="518a2-115">The namespace for canonical function is <xref:System.Data.Metadata.Edm>.</span></span> <span data-ttu-id="518a2-116">Der <xref:System.Data.Metadata.Edm>-Namespace wird in allen Abfragen automatisch eingebunden.</span><span class="sxs-lookup"><span data-stu-id="518a2-116">The <xref:System.Data.Metadata.Edm> namespace is automatically included in all queries.</span></span> <span data-ttu-id="518a2-117">Wenn jedoch ein anderer Namespace importiert wird, der eine Funktion mit dem gleichen Namen wie eine kanonische Funktion (im <xref:System.Data.Metadata.Edm>-Namespace) enthält, muss der Namespace angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="518a2-117">However, if another namespace is imported that contains a function with the same name as a canonical function (in the <xref:System.Data.Metadata.Edm> namespace), you must specify the namespace.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="518a2-118">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="518a2-118">In This Section</span></span>  
 [<span data-ttu-id="518a2-119">Aggregieren kanonischer Funktionen</span><span class="sxs-lookup"><span data-stu-id="518a2-119">Aggregate Canonical Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/aggregate-canonical-functions.md)  
 <span data-ttu-id="518a2-120">Erläutert die kanonischen Aggregatfunktionen von [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="518a2-120">Discusses aggregate [!INCLUDE[esql](../../../../../../includes/esql-md.md)] canonical functions.</span></span>  
  
 [<span data-ttu-id="518a2-121">Mathematische kanonische Funktionen</span><span class="sxs-lookup"><span data-stu-id="518a2-121">Math Canonical Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/math-canonical-functions.md)  
 <span data-ttu-id="518a2-122">Erläutert die kanonischen mathematischen Funktionen von [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="518a2-122">Discusses math [!INCLUDE[esql](../../../../../../includes/esql-md.md)] canonical functions.</span></span>  
  
 [<span data-ttu-id="518a2-123">Kanonische Zeichenfolgefunktionen</span><span class="sxs-lookup"><span data-stu-id="518a2-123">String Canonical Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)  
 <span data-ttu-id="518a2-124">Erläutert die kanonischen Zeichenfolgenfunktionen von [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="518a2-124">Discusses string [!INCLUDE[esql](../../../../../../includes/esql-md.md)] canonical functions.</span></span>  
  
 [<span data-ttu-id="518a2-125">Kanonische Funktionen für Datum und Zeit</span><span class="sxs-lookup"><span data-stu-id="518a2-125">Date and Time Canonical Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)  
 <span data-ttu-id="518a2-126">Erläutert die kanonischen Datums- und Uhrzeitfunktionen von [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="518a2-126">Discusses date and time [!INCLUDE[esql](../../../../../../includes/esql-md.md)] canonical functions.</span></span>  
  
 [<span data-ttu-id="518a2-127">Bitweise kanonische Funktionen</span><span class="sxs-lookup"><span data-stu-id="518a2-127">Bitwise Canonical Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/bitwise-canonical-functions.md)  
 <span data-ttu-id="518a2-128">Erläutert die kanonischen bitweisen Funktionen von [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="518a2-128">Discusses bitwise [!INCLUDE[esql](../../../../../../includes/esql-md.md)] canonical functions.</span></span>  
  
 [<span data-ttu-id="518a2-129">Räumliche Funktionen</span><span class="sxs-lookup"><span data-stu-id="518a2-129">Spatial Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/spatial-functions.md)  
 <span data-ttu-id="518a2-130">Erläutert die räumlichen kanonischen Funktionen von [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="518a2-130">Discusses Spatial [!INCLUDE[esql](../../../../../../includes/esql-md.md)] canonical functions.</span></span>  
  
 [<span data-ttu-id="518a2-131">Andere kanonische Funktionen</span><span class="sxs-lookup"><span data-stu-id="518a2-131">Other Canonical Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/other-canonical-functions.md)  
 <span data-ttu-id="518a2-132">Erläutert Funktionen, die keine bitweisen Funktionen, Datums- und Uhrzeitfunktionen, Zeichenfolgenfunktionen, mathematische Funktionen oder Aggregatfunktionen sind.</span><span class="sxs-lookup"><span data-stu-id="518a2-132">Discusses functions not classified as bitwise, date/time, string, math, or aggregate.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="518a2-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="518a2-133">See Also</span></span>  
 [<span data-ttu-id="518a2-134">Übersicht über Entity SQL</span><span class="sxs-lookup"><span data-stu-id="518a2-134">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)  
 [<span data-ttu-id="518a2-135">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="518a2-135">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [<span data-ttu-id="518a2-136">Zuordnen von kanonischen Funktionen (konzeptionelles Modell) zu SQL Server-Funktionen</span><span class="sxs-lookup"><span data-stu-id="518a2-136">Conceptual Model Canonical to SQL Server Functions Mapping</span></span>](../../../../../../docs/framework/data/adonet/ef/conceptual-model-canonical-to-sql-server-functions-mapping.md)  
 [<span data-ttu-id="518a2-137">Benutzerdefinierte Funktionen</span><span class="sxs-lookup"><span data-stu-id="518a2-137">User-Defined Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/user-defined-functions-entity-sql.md)
