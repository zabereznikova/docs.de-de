---
title: Kanonische Funktionen
ms.date: 03/30/2017
ms.assetid: bbcc9928-36ea-4dff-9e31-96549ffed958
ms.openlocfilehash: 11e22d527c4266f45ea5d26f2ec95926ebe46332
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91185241"
---
# <a name="canonical-functions"></a><span data-ttu-id="31900-102">Kanonische Funktionen</span><span class="sxs-lookup"><span data-stu-id="31900-102">Canonical Functions</span></span>

<span data-ttu-id="31900-103">In diesem Abschnitt werden die von allen Datenanbietern unterstützten und in allen Abfragetechnologien verwendbaren kanonischen Funktionen erläutert.</span><span class="sxs-lookup"><span data-stu-id="31900-103">This section discusses canonical functions that are supported by all data providers, and can be used by all querying technologies.</span></span> <span data-ttu-id="31900-104">Kanonische Funktionen können von Anbietern nicht erweitert werden.</span><span class="sxs-lookup"><span data-stu-id="31900-104">Canonical functions cannot be extended by a provider.</span></span>  
  
 <span data-ttu-id="31900-105">Diese kanonischen Funktionen werden in die entsprechenden Datenquellenfunktionen der Anbieter übersetzt.</span><span class="sxs-lookup"><span data-stu-id="31900-105">These canonical functions will be translated to the corresponding data source functionality for the provider.</span></span> <span data-ttu-id="31900-106">Dadurch können Funktionsaufrufe für Datenquellen in einer allgemeinen Form ausgedrückt werden.</span><span class="sxs-lookup"><span data-stu-id="31900-106">This allows for function invocations expressed in a common form across data sources.</span></span>  
  
 <span data-ttu-id="31900-107">Da diese kanonischen Funktionen datenquellenunabhängig sind, werden die Argument- und Rückgabetypen kanonischer Funktionen in Form von Typen im konzeptionellen Modell definiert.</span><span class="sxs-lookup"><span data-stu-id="31900-107">Because these canonical functions are independent of data sources, argument and return types of canonical functions are defined in terms of types in the conceptual model.</span></span> <span data-ttu-id="31900-108">Jedoch werden von einigen Datenquellen möglicherweise nicht alle Typen im konzeptionellen Modell unterstützt.</span><span class="sxs-lookup"><span data-stu-id="31900-108">However, some data sources might not support all types in the conceptual model.</span></span>  
  
 <span data-ttu-id="31900-109">Wenn in einer [!INCLUDE[esql](../../../../../../includes/esql-md.md)]-Abfrage kanonische Funktionen verwendet werden, werden in Datenquellen die entsprechenden Funktionen aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="31900-109">When canonical functions are used in an [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query, the appropriate function will be called at the data source.</span></span>  
  
 <span data-ttu-id="31900-110">Für alle kanonischen Funktionen sind das Verhalten bei NULL-Eingaben sowie die Fehlerbedingungen explizit angegeben.</span><span class="sxs-lookup"><span data-stu-id="31900-110">All canonical functions have both null-input behavior and error conditions explicitly specified.</span></span> <span data-ttu-id="31900-111">Speicher Anbieter sollten dieses Verhalten einhalten, Entity Framework jedoch dieses Verhalten nicht erzwingt.</span><span class="sxs-lookup"><span data-stu-id="31900-111">Store providers should comply with that behavior, but Entity Framework does not enforce this behavior.</span></span>  
  
 <span data-ttu-id="31900-112">Bei LINQ-Szenarios müssen bei Abfragen für die Entity Framework CLR-Methoden zu Methoden in der zugrunde liegenden Datenquelle Mapping werden.</span><span class="sxs-lookup"><span data-stu-id="31900-112">For LINQ scenarios, queries against the Entity Framework involve mapping CLR methods to methods in the underlying data source.</span></span> <span data-ttu-id="31900-113">Die CLR-Methoden werden kanonischen Funktionen zugeordnet, sodass bestimmte Methoden unabhängig von der Datenquelle ordnungsgemäß zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="31900-113">The CLR methods map to canonical functions, so that a specific set of methods will correctly map, regardless of the data source.</span></span>  
  
## <a name="canonical-functions-namespace"></a><span data-ttu-id="31900-114">Namespace kanonischer Funktionen</span><span class="sxs-lookup"><span data-stu-id="31900-114">Canonical Functions Namespace</span></span>  

 <span data-ttu-id="31900-115">Der Namespace für kanonische Funktionen ist <xref:System.Data.Metadata.Edm>.</span><span class="sxs-lookup"><span data-stu-id="31900-115">The namespace for canonical function is <xref:System.Data.Metadata.Edm>.</span></span> <span data-ttu-id="31900-116">Der <xref:System.Data.Metadata.Edm>-Namespace wird in allen Abfragen automatisch eingebunden.</span><span class="sxs-lookup"><span data-stu-id="31900-116">The <xref:System.Data.Metadata.Edm> namespace is automatically included in all queries.</span></span> <span data-ttu-id="31900-117">Wenn jedoch ein anderer Namespace importiert wird, der eine Funktion mit dem gleichen Namen wie eine kanonische Funktion (im <xref:System.Data.Metadata.Edm>-Namespace) enthält, muss der Namespace angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="31900-117">However, if another namespace is imported that contains a function with the same name as a canonical function (in the <xref:System.Data.Metadata.Edm> namespace), you must specify the namespace.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="31900-118">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="31900-118">In This Section</span></span>  

 [<span data-ttu-id="31900-119">Aggregieren kanonischer Funktionen</span><span class="sxs-lookup"><span data-stu-id="31900-119">Aggregate Canonical Functions</span></span>](aggregate-canonical-functions.md)  
 <span data-ttu-id="31900-120">Erläutert die kanonischen Aggregatfunktionen von [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="31900-120">Discusses aggregate [!INCLUDE[esql](../../../../../../includes/esql-md.md)] canonical functions.</span></span>  
  
 [<span data-ttu-id="31900-121">Kanonische Mathematikfunktionen</span><span class="sxs-lookup"><span data-stu-id="31900-121">Math Canonical Functions</span></span>](math-canonical-functions.md)  
 <span data-ttu-id="31900-122">Erläutert die kanonischen mathematischen Funktionen von [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="31900-122">Discusses math [!INCLUDE[esql](../../../../../../includes/esql-md.md)] canonical functions.</span></span>  
  
 [<span data-ttu-id="31900-123">Kanonische Zeichenfolgefunktionen</span><span class="sxs-lookup"><span data-stu-id="31900-123">String Canonical Functions</span></span>](string-canonical-functions.md)  
 <span data-ttu-id="31900-124">Erläutert die kanonischen Zeichenfolgenfunktionen von [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="31900-124">Discusses string [!INCLUDE[esql](../../../../../../includes/esql-md.md)] canonical functions.</span></span>  
  
 [<span data-ttu-id="31900-125">Kanonische Funktionen für Datum und Zeit</span><span class="sxs-lookup"><span data-stu-id="31900-125">Date and Time Canonical Functions</span></span>](date-and-time-canonical-functions.md)  
 <span data-ttu-id="31900-126">Erläutert die kanonischen Datums- und Uhrzeitfunktionen von [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="31900-126">Discusses date and time [!INCLUDE[esql](../../../../../../includes/esql-md.md)] canonical functions.</span></span>  
  
 [<span data-ttu-id="31900-127">Bitweise kanonische Funktionen</span><span class="sxs-lookup"><span data-stu-id="31900-127">Bitwise Canonical Functions</span></span>](bitwise-canonical-functions.md)  
 <span data-ttu-id="31900-128">Erläutert die kanonischen bitweisen Funktionen von [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="31900-128">Discusses bitwise [!INCLUDE[esql](../../../../../../includes/esql-md.md)] canonical functions.</span></span>  
  
 [<span data-ttu-id="31900-129">Räumliche Funktionen</span><span class="sxs-lookup"><span data-stu-id="31900-129">Spatial Functions</span></span>](spatial-functions.md)  
 <span data-ttu-id="31900-130">Erläutert die räumlichen kanonischen Funktionen von [!INCLUDE[esql](../../../../../../includes/esql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="31900-130">Discusses Spatial [!INCLUDE[esql](../../../../../../includes/esql-md.md)] canonical functions.</span></span>  
  
 [<span data-ttu-id="31900-131">Andere kanonische Funktionen</span><span class="sxs-lookup"><span data-stu-id="31900-131">Other Canonical Functions</span></span>](other-canonical-functions.md)  
 <span data-ttu-id="31900-132">Erläutert Funktionen, die keine bitweisen Funktionen, Datums- und Uhrzeitfunktionen, Zeichenfolgenfunktionen, mathematische Funktionen oder Aggregatfunktionen sind.</span><span class="sxs-lookup"><span data-stu-id="31900-132">Discusses functions not classified as bitwise, date/time, string, math, or aggregate.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31900-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="31900-133">See also</span></span>

- [<span data-ttu-id="31900-134">Übersicht über Entity SQL</span><span class="sxs-lookup"><span data-stu-id="31900-134">Entity SQL Overview</span></span>](entity-sql-overview.md)
- [<span data-ttu-id="31900-135">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="31900-135">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="31900-136">Zuordnen von kanonischen Funktionen (konzeptionelles Modell) zu SQL Server-Funktionen</span><span class="sxs-lookup"><span data-stu-id="31900-136">Conceptual Model Canonical to SQL Server Functions Mapping</span></span>](../conceptual-model-canonical-to-sql-server-functions-mapping.md)
- [<span data-ttu-id="31900-137">Benutzerdefinierte Funktionen</span><span class="sxs-lookup"><span data-stu-id="31900-137">User-Defined Functions</span></span>](user-defined-functions-entity-sql.md)
