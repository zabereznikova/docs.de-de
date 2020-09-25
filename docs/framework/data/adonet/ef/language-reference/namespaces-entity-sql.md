---
title: Namespaces (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 83991c21-60db-4af9-aca3-b416f6cae98e
ms.openlocfilehash: 7a53f8e7e70dbc9fa505f7f8619af10a0e44c331
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91197806"
---
# <a name="namespaces-entity-sql"></a><span data-ttu-id="b51af-102">Namespaces (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="b51af-102">Namespaces (Entity SQL)</span></span>

[!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="b51af-103">vermeidet Namenskonflikte bei globalen Bezeichnern wie Typnamen, Entitätenmengen, Funktionen usw. mithilfe von Namespaces.</span><span class="sxs-lookup"><span data-stu-id="b51af-103">introduces namespaces to avoid name conflicts for global identifiers such as type names, entity sets, functions, and so on.</span></span> <span data-ttu-id="b51af-104">Die Namespace Unterstützung in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] ähnelt der Namespace Unterstützung in der .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b51af-104">The namespace support in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] is similar to the namespace support in the .NET Framework.</span></span>  
  
 <span data-ttu-id="b51af-105"> stellt, wie in folgendem Beispiel veranschaulicht, zwei Arten der USING-Klausel zur Verfügung: qualifizierte Namespaces (wobei ein kürzerer Alias für den Namespace bereitgestellt wird) und unqualifizierte Namespaces:</span><span class="sxs-lookup"><span data-stu-id="b51af-105">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] provides two forms of the USING clause: qualified namespaces (where a shorter alias is provided for the namespace), and unqualified namespaces, as illustrated in the following example:</span></span>  
  
 `USING System.Data;`  
  
 `USING tsql = System.Data;`  
  
## <a name="name-resolution-rules"></a><span data-ttu-id="b51af-106">Regeln zur Namensauflösung</span><span class="sxs-lookup"><span data-stu-id="b51af-106">Name Resolution Rules</span></span>  

 <span data-ttu-id="b51af-107">Wenn ein Bezeichner nicht in den lokalen Bereichen aufgelöst werden kann, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] versucht, den Namen in den globalen Bereichen (den Namespaces) zu finden.</span><span class="sxs-lookup"><span data-stu-id="b51af-107">If an identifier cannot be resolved in the local scopes, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] tries to locate the name in the global scopes (the namespaces).</span></span> [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="b51af-108">vergleicht zunächst den Bezeichner (Präfix) mit einem der qualifizierten Namespaces.</span><span class="sxs-lookup"><span data-stu-id="b51af-108">first tries to match the identifier (prefix) with one of the qualified namespaces.</span></span> <span data-ttu-id="b51af-109">Wenn eine Entsprechung vorliegt, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] versucht, den Rest des Bezeichners im angegebenen Namespace aufzulösen.</span><span class="sxs-lookup"><span data-stu-id="b51af-109">If there is a match, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] tries to resolve the rest of the identifier in the specified namespace.</span></span> <span data-ttu-id="b51af-110">Wenn keine Übereinstimmung festgestellt werden kann, wird eine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="b51af-110">If no match is found, an exception is thrown.</span></span>  
  
 <span data-ttu-id="b51af-111">Anschließend [!INCLUDE[esql](../../../../../../includes/esql-md.md)] versucht, alle nicht qualifizierten Namespaces (die im Prolog angegeben sind) für den Bezeichner zu durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="b51af-111">Next, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] tries to search all unqualified namespaces (specified in the prolog) for the identifier.</span></span> <span data-ttu-id="b51af-112">Wird der Bezeichner in genau einem Namespace gefunden, wird dieser Bereich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="b51af-112">If the identifier can be located in exactly one namespace, that location is returned.</span></span> <span data-ttu-id="b51af-113">Wenn dem Bezeichner mehrere Namespaces entsprechen, wird eine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="b51af-113">If more than one namespace has a match for that identifier, an exception is thrown.</span></span> <span data-ttu-id="b51af-114">Wenn für den Bezeichner kein Namespace identifiziert werden kann, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] übergibt den Namen an den nächsten äußeren Bereich (das- <xref:System.Data.Common.DbCommand> Objekt oder das- <xref:System.Data.Common.DbConnection> Objekt), wie im folgenden Beispiel veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="b51af-114">If no namespace can be identified for the identifier, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] passes the name onto the next outward scope (the <xref:System.Data.Common.DbCommand> or <xref:System.Data.Common.DbConnection> object), as illustrated in the following example:</span></span>  
  
```sql  
SELECT TREAT(p AS NamespaceName.Employee)  
FROM ContainerName.Person AS p  
WHERE p IS OF (NamespaceName.Employee)  
```  
  
## <a name="differences-from-the-net-framework"></a><span data-ttu-id="b51af-115">Unterschiede zum .NET Framework</span><span class="sxs-lookup"><span data-stu-id="b51af-115">Differences from the .NET Framework</span></span>  

 <span data-ttu-id="b51af-116">In der .NET Framework können Sie teilweise qualifizierte Namespaces verwenden.</span><span class="sxs-lookup"><span data-stu-id="b51af-116">In the .NET Framework, you can use partially qualified namespaces.</span></span> <span data-ttu-id="b51af-117">Mit [!INCLUDE[esql](../../../../../../includes/esql-md.md)] ist dies nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="b51af-117">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] does not allow this.</span></span>  
  
## <a name="adonet-usage"></a><span data-ttu-id="b51af-118">Verwendung von ADO.NET</span><span class="sxs-lookup"><span data-stu-id="b51af-118">ADO.NET Usage</span></span>  

 <span data-ttu-id="b51af-119">Abfragen werden mit ADO.NET-<xref:System.Data.Common.DbCommand>-Objekten ausgedrückt.</span><span class="sxs-lookup"><span data-stu-id="b51af-119">Queries are expressed through ADO.NET <xref:System.Data.Common.DbCommand> objects.</span></span> <span data-ttu-id="b51af-120"><xref:System.Data.Common.DbCommand>-Objekte werden über <xref:System.Data.Common.DbConnection>-Objekte erstellt.</span><span class="sxs-lookup"><span data-stu-id="b51af-120"><xref:System.Data.Common.DbCommand> objects can be built over <xref:System.Data.Common.DbConnection> objects.</span></span> <span data-ttu-id="b51af-121">Namespaces können außerdem als Teil der <xref:System.Data.Common.DbCommand>- und <xref:System.Data.Common.DbConnection>-Objekte spezifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="b51af-121">Namespaces can also be specified as part of the <xref:System.Data.Common.DbCommand> and <xref:System.Data.Common.DbConnection> objects.</span></span> <span data-ttu-id="b51af-122">Wenn [!INCLUDE[esql](../../../../../../includes/esql-md.md)] ein Bezeichner in der Abfrage nicht auflösen kann, werden die externen Namespaces (basierend auf ähnlichen Regeln) geprüft.</span><span class="sxs-lookup"><span data-stu-id="b51af-122">If [!INCLUDE[esql](../../../../../../includes/esql-md.md)] cannot resolve an identifier within the query itself, the external namespaces are probed (based on similar rules).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b51af-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b51af-123">See also</span></span>

- [<span data-ttu-id="b51af-124">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="b51af-124">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="b51af-125">Übersicht über Entity SQL</span><span class="sxs-lookup"><span data-stu-id="b51af-125">Entity SQL Overview</span></span>](entity-sql-overview.md)
