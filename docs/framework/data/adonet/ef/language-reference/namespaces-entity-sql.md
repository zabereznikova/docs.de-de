---
title: Namespaces (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 83991c21-60db-4af9-aca3-b416f6cae98e
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 1f97b28bce20fa71f82942fa5f123d7c2ac6616a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="namespaces-entity-sql"></a><span data-ttu-id="6ebd9-102">Namespaces (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="6ebd9-102">Namespaces (Entity SQL)</span></span>
[!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="6ebd9-103"> vermeidet Namenskonflikte bei globalen Bezeichnern wie Typnamen, Entitätenmengen, Funktionen usw. mithilfe von Namespaces.</span><span class="sxs-lookup"><span data-stu-id="6ebd9-103"> introduces namespaces to avoid name conflicts for global identifiers such as type names, entity sets, functions, and so on.</span></span> <span data-ttu-id="6ebd9-104">Unterstützung von Namespaces in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] ähnelt die Namespaceunterstützung in den [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6ebd9-104">The namespace support in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] is similar to the namespace support in the [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)].</span></span>  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="6ebd9-105"> stellt, wie in folgendem Beispiel veranschaulicht, zwei Arten der USING-Klausel zur Verfügung: qualifizierte Namespaces (wobei ein kürzerer Alias für den Namespace bereitgestellt wird) und unqualifizierte Namespaces:</span><span class="sxs-lookup"><span data-stu-id="6ebd9-105"> provides two forms of the USING clause: qualified namespaces (where a shorter alias is provided for the namespace), and unqualified namespaces, as illustrated in the following example:</span></span>  
  
 `USING System.Data;`  
  
 `USING tsql = System.Data;`  
  
## <a name="name-resolution-rules"></a><span data-ttu-id="6ebd9-106">Regeln zur Namensauflösung</span><span class="sxs-lookup"><span data-stu-id="6ebd9-106">Name Resolution Rules</span></span>  
 <span data-ttu-id="6ebd9-107">Wenn ein Bezeichner in den lokalen Bereichen aufgelöst werden kann [!INCLUDE[esql](../../../../../../includes/esql-md.md)] versucht, den Namen in den globalen Bereichen (den Namespaces) gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="6ebd9-107">If an identifier cannot be resolved in the local scopes, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] tries to locate the name in the global scopes (the namespaces).</span></span> [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="6ebd9-108"> vergleicht zunächst den Bezeichner (Präfix) mit einem der qualifizierten Namespaces.</span><span class="sxs-lookup"><span data-stu-id="6ebd9-108"> first tries to match the identifier (prefix) with one of the qualified namespaces.</span></span> <span data-ttu-id="6ebd9-109">Wenn eine Übereinstimmung besteht, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] versucht, den Rest des Bezeichners im angegebenen Namespace aufzulösen.</span><span class="sxs-lookup"><span data-stu-id="6ebd9-109">If there is a match, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] tries to resolve the rest of the identifier in the specified namespace.</span></span> <span data-ttu-id="6ebd9-110">Wenn keine Übereinstimmung festgestellt werden kann, wird eine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="6ebd9-110">If no match is found, an exception is thrown.</span></span>  
  
 <span data-ttu-id="6ebd9-111">Als Nächstes [!INCLUDE[esql](../../../../../../includes/esql-md.md)] versucht, die allen unqualifizierten Namespaces (die im Prolog angegeben) für den Bezeichner zu suchen.</span><span class="sxs-lookup"><span data-stu-id="6ebd9-111">Next, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] tries to search all unqualified namespaces (specified in the prolog) for the identifier.</span></span> <span data-ttu-id="6ebd9-112">Wird der Bezeichner in genau einem Namespace gefunden, wird dieser Bereich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="6ebd9-112">If the identifier can be located in exactly one namespace, that location is returned.</span></span> <span data-ttu-id="6ebd9-113">Wenn dem Bezeichner mehrere Namespaces entsprechen, wird eine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="6ebd9-113">If more than one namespace has a match for that identifier, an exception is thrown.</span></span> <span data-ttu-id="6ebd9-114">Für den Bezeichner kein Namespace angegeben werden kann [!INCLUDE[esql](../../../../../../includes/esql-md.md)] übergibt den Namen auf den nächsten äußeren Bereich (das <xref:System.Data.Common.DbCommand> oder <xref:System.Data.Common.DbConnection> Objekt), wie im folgenden Beispiel veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="6ebd9-114">If no namespace can be identified for the identifier, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] passes the name onto the next outward scope (the <xref:System.Data.Common.DbCommand> or <xref:System.Data.Common.DbConnection> object), as illustrated in the following example:</span></span>  
  
```  
SELECT TREAT(p AS NamespaceName.Employee)  
FROM ContainerName.Person AS p  
WHERE p IS OF (NamespaceName.Employee)  
```  
  
## <a name="differences-from-the-net-framework"></a><span data-ttu-id="6ebd9-115">Unterschiede zum .NET Framework</span><span class="sxs-lookup"><span data-stu-id="6ebd9-115">Differences from the .NET Framework</span></span>  
 <span data-ttu-id="6ebd9-116">In [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)] können teilweise qualifizierte Namespaces verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="6ebd9-116">In the [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)], you can use partially qualified namespaces.</span></span> <span data-ttu-id="6ebd9-117">Mit [!INCLUDE[esql](../../../../../../includes/esql-md.md)] ist dies nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="6ebd9-117">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] does not allow this.</span></span>  
  
## <a name="adonet-usage"></a><span data-ttu-id="6ebd9-118">Verwendung von ADO.NET</span><span class="sxs-lookup"><span data-stu-id="6ebd9-118">ADO.NET Usage</span></span>  
 <span data-ttu-id="6ebd9-119">Abfragen werden mit ADO.NET-<xref:System.Data.Common.DbCommand>-Objekten ausgedrückt.</span><span class="sxs-lookup"><span data-stu-id="6ebd9-119">Queries are expressed through ADO.NET <xref:System.Data.Common.DbCommand> objects.</span></span> <span data-ttu-id="6ebd9-120"><xref:System.Data.Common.DbCommand>-Objekte werden über <xref:System.Data.Common.DbConnection>-Objekte erstellt.</span><span class="sxs-lookup"><span data-stu-id="6ebd9-120"><xref:System.Data.Common.DbCommand> objects can be built over <xref:System.Data.Common.DbConnection> objects.</span></span> <span data-ttu-id="6ebd9-121">Namespaces können außerdem als Teil der <xref:System.Data.Common.DbCommand>- und <xref:System.Data.Common.DbConnection>-Objekte spezifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="6ebd9-121">Namespaces can also be specified as part of the <xref:System.Data.Common.DbCommand> and <xref:System.Data.Common.DbConnection> objects.</span></span> <span data-ttu-id="6ebd9-122">Wenn [!INCLUDE[esql](../../../../../../includes/esql-md.md)] ein Bezeichners kann nicht aufgelöst werden innerhalb der Abfrage selbst, werden die externen Namespaces (nach ähnlichen Regeln) überprüft.</span><span class="sxs-lookup"><span data-stu-id="6ebd9-122">If [!INCLUDE[esql](../../../../../../includes/esql-md.md)] cannot resolve an identifier within the query itself, the external namespaces are probed (based on similar rules).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ebd9-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6ebd9-123">See Also</span></span>  
 [<span data-ttu-id="6ebd9-124">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="6ebd9-124">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [<span data-ttu-id="6ebd9-125">Übersicht über Entity SQL</span><span class="sxs-lookup"><span data-stu-id="6ebd9-125">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
