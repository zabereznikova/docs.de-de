---
title: "Zwischenspeichern von Abfrageplänen (Entity SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 90b0c685-5ef2-461b-98b4-c3c0a2b253c7
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 814b4451d5e08d5f9df4d370b2127d971f3fdd1d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="query-plan-caching-entity-sql"></a><span data-ttu-id="a1fb9-102">Zwischenspeichern von Abfrageplänen (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="a1fb9-102">Query Plan Caching (Entity SQL)</span></span>
<span data-ttu-id="a1fb9-103">Bei jeder Ausführung einer Abfrage sucht die Abfragepipeline in ihrem Abfrageplancache, ob genau diese Abfrage bereits kompiliert und verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="a1fb9-103">Whenever an attempt to execute a query is made, the query pipeline looks up its query plan cache to see whether the exact query is already compiled and available.</span></span> <span data-ttu-id="a1fb9-104">Wenn das der Fall ist, wird der zwischengespeicherte Plan erneut verwendet, statt einen neuen Plan zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="a1fb9-104">If so, it reuses the cached plan rather than building a new one.</span></span> <span data-ttu-id="a1fb9-105">Wird keine Übereinstimmung im Abfrageplancache gefunden, wird die Abfrage kompiliert und zwischengespeichert.</span><span class="sxs-lookup"><span data-stu-id="a1fb9-105">If a match is not found in the query plan cache, the query is compiled and cached.</span></span> <span data-ttu-id="a1fb9-106">Eine Abfrage wird durch ihren [!INCLUDE[esql](../../../../../../includes/esql-md.md)]-Text und ihre Parameterauflistung (Namen und Typen) identifiziert.</span><span class="sxs-lookup"><span data-stu-id="a1fb9-106">A query is identified by its [!INCLUDE[esql](../../../../../../includes/esql-md.md)] text and parameter collection (names and types).</span></span> <span data-ttu-id="a1fb9-107">Bei allen Textvergleichen wird die Groß- und Kleinschreibung berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="a1fb9-107">All text comparisons are case-sensitive.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="a1fb9-108">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="a1fb9-108">Configuration</span></span>  
 <span data-ttu-id="a1fb9-109">Das Zwischenspeichern von Abfrageplänen kann über <xref:System.Data.EntityClient.EntityCommand> konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="a1fb9-109">Query plan caching is configurable through the <xref:System.Data.EntityClient.EntityCommand>.</span></span>  
  
 <span data-ttu-id="a1fb9-110">Um das Zwischenspeichern von Abfrageplänen mithilfe von <xref:System.Data.EntityClient.EntityCommand.EnablePlanCaching%2A?displayProperty=nameWithType> zu aktivieren bzw. zu deaktivieren, legen Sie diese Eigenschaft auf `true` bzw. `false` fest.</span><span class="sxs-lookup"><span data-stu-id="a1fb9-110">To enable or disable query plan caching through <xref:System.Data.EntityClient.EntityCommand.EnablePlanCaching%2A?displayProperty=nameWithType>, set this property to `true` or `false`.</span></span> <span data-ttu-id="a1fb9-111">Die Leistung wird verbessert, wenn das Zwischenspeichern des Plans für einzelne dynamische Abfragen, die wahrscheinlich nicht mehr als einmal verwendet werden, deaktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="a1fb9-111">Disabling plan caching for individual dynamic queries that are unlikely to be used more then once improves performance.</span></span>  
  
 <span data-ttu-id="a1fb9-112">Sie können das Zwischenspeichern von Abfrageplänen mittels <xref:System.Data.Objects.ObjectQuery.EnablePlanCaching%2A> aktivieren.</span><span class="sxs-lookup"><span data-stu-id="a1fb9-112">You can enable query plan caching through <xref:System.Data.Objects.ObjectQuery.EnablePlanCaching%2A>.</span></span>  
  
## <a name="recommended-practice"></a><span data-ttu-id="a1fb9-113">Empfohlene Vorgehensweise</span><span class="sxs-lookup"><span data-stu-id="a1fb9-113">Recommended Practice</span></span>  
 <span data-ttu-id="a1fb9-114">Im Allgemeinen sollten dynamische Abfragen vermieden werden.</span><span class="sxs-lookup"><span data-stu-id="a1fb9-114">Dynamic queries should be avoided, in general.</span></span> <span data-ttu-id="a1fb9-115">Das folgende Beispiel einer dynamischen Abfrage ist anfällig für Angriffe durch Einschleusen von SQL-Befehlen, da Benutzereingaben ohne Validierung entgegengenommen werden.</span><span class="sxs-lookup"><span data-stu-id="a1fb9-115">The following dynamic query example is vulnerable to SQL injection attacks, because it takes user input directly without any validation.</span></span>  
  
 `"SELECT sp.SalesYTD FROM AdventureWorksEntities.SalesPerson as sp WHERE sp.EmployeeID = " + employeeTextBox.Text;`  
  
 <span data-ttu-id="a1fb9-116">Wenn Sie dynamisch generierte Abfragen verwenden, erwägen Sie die Deaktivierung der Zwischenspeicherung von Abfrageplänen, um den unnötigen Speicherverbrauch für Cacheeinträge zu vermeiden, die wahrscheinlich nicht wiederverwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a1fb9-116">If you do use dynamically generated queries, consider disabling query plan caching to avoid unnecessary memory consumption for cache entries that are unlikely to be reused.</span></span>  
  
 <span data-ttu-id="a1fb9-117">Das Zwischenspeichern von Abfrageplänen für statische und parametrisierte Abfragen kann Leistungsvorteile bieten.</span><span class="sxs-lookup"><span data-stu-id="a1fb9-117">Query plan caching on static queries and parameterized queries can provide performance benefits.</span></span> <span data-ttu-id="a1fb9-118">Das folgende Beispiel enthält eine statische Abfrage:</span><span class="sxs-lookup"><span data-stu-id="a1fb9-118">The following is an example of a static query:</span></span>  
  
```  
"SELECT sp.SalesYTD FROM AdventureWorksEntities.SalesPerson as sp";  
```  
  
 <span data-ttu-id="a1fb9-119">Damit übereinstimmende Abfragen im Abfrageplancache gefunden werden, sollten sie folgende Anforderungen erfüllen:</span><span class="sxs-lookup"><span data-stu-id="a1fb9-119">For queries to be matched properly by the query plan cache, they should comply with the following requirements:</span></span>  
  
-   <span data-ttu-id="a1fb9-120">Der Abfragetext sollte ein konstantes Muster sein, vorzugsweise eine konstante Zeichenfolge oder eine Ressource.</span><span class="sxs-lookup"><span data-stu-id="a1fb9-120">Query text should be a constant pattern, preferably a constant string or a resource.</span></span>  
  
-   <span data-ttu-id="a1fb9-121"><xref:System.Data.EntityClient.EntityParameter> oder <xref:System.Data.Objects.ObjectParameter> sollte immer dann verwendet werden, wenn ein vom Benutzer bereitgestellter Wert übergeben werden muss.</span><span class="sxs-lookup"><span data-stu-id="a1fb9-121"><xref:System.Data.EntityClient.EntityParameter> or <xref:System.Data.Objects.ObjectParameter> should be used wherever a user-supplied value must be passed.</span></span>  
  
 <span data-ttu-id="a1fb9-122">Sie sollten die folgenden Abfragemuster vermeiden, die unnötigerweise Slots im Abfrageplancache verwenden:</span><span class="sxs-lookup"><span data-stu-id="a1fb9-122">You should avoid the following query patterns, which unnecessarily consume slots in the query plan cache:</span></span>  
  
-   <span data-ttu-id="a1fb9-123">Änderungen an der Schreibweise von Buchstaben im Text.</span><span class="sxs-lookup"><span data-stu-id="a1fb9-123">Changes to letter case in the text.</span></span>  
  
-   <span data-ttu-id="a1fb9-124">Änderungen an Leerzeichen.</span><span class="sxs-lookup"><span data-stu-id="a1fb9-124">Changes to white space.</span></span>  
  
-   <span data-ttu-id="a1fb9-125">Änderungen an Literalwerten.</span><span class="sxs-lookup"><span data-stu-id="a1fb9-125">Changes to literal values.</span></span>  
  
-   <span data-ttu-id="a1fb9-126">Änderungen an Text in Kommentaren.</span><span class="sxs-lookup"><span data-stu-id="a1fb9-126">Changes to text inside comments.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1fb9-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a1fb9-127">See Also</span></span>  
 [<span data-ttu-id="a1fb9-128">Übersicht über Entity SQL</span><span class="sxs-lookup"><span data-stu-id="a1fb9-128">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
