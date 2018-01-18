---
title: SQL-Generierung
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0e16aa02-d458-4418-a765-58b42aad9315
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 6b2d4ba925af61f89b47c494f5fb17f5f9f0d995
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2018
---
# <a name="sql-generation"></a><span data-ttu-id="7a5f9-102">SQL-Generierung</span><span class="sxs-lookup"><span data-stu-id="7a5f9-102">SQL Generation</span></span>
<span data-ttu-id="7a5f9-103">Wenn Sie einen Anbieter für [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] schreiben, müssen Sie [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]-Befehlsstrukturen in SQL übersetzen, das eine bestimmte Datenbank verstehen kann, z. B. Transact-SQL für SQL Server oder PL/SQL für Oracle.</span><span class="sxs-lookup"><span data-stu-id="7a5f9-103">When you write a provider for the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)], you must translate [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] command trees into SQL that a specific database can understand, such as Transact-SQL for SQL Server or PL/SQL for Oracle.</span></span> <span data-ttu-id="7a5f9-104">In diesem Abschnitt erfahren Sie, wie eine SQL-Generierungskomponente (für SELECT-Abfragen) für einen [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]-Anbieter entwickelt wird.</span><span class="sxs-lookup"><span data-stu-id="7a5f9-104">In this section, you will learn how to develop a SQL generation component (for SELECT queries) for an [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] provider.</span></span> <span data-ttu-id="7a5f9-105">Informationen, einfügen, aktualisieren und Löschen von Abfragen, finden Sie unter [Generierung von Änderungen in SQL](../../../../../docs/framework/data/adonet/ef/modification-sql-generation.md).</span><span class="sxs-lookup"><span data-stu-id="7a5f9-105">For information about insert, update, and delete queries, see [Modification SQL Generation](../../../../../docs/framework/data/adonet/ef/modification-sql-generation.md).</span></span>  
  
 <span data-ttu-id="7a5f9-106">Um diesen Abschnitt zu verstehen, sollten Sie mit dem [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]- und dem ADO.NET-Anbietermodell vertraut sein.</span><span class="sxs-lookup"><span data-stu-id="7a5f9-106">To understand this section, you should be familiar with the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] and the ADO.NET Provider Model.</span></span> <span data-ttu-id="7a5f9-107">Außerdem sollten Sie Befehlsstrukturen und <xref:System.Data.Common.CommandTrees.DbExpression> verstehen.</span><span class="sxs-lookup"><span data-stu-id="7a5f9-107">You should also understand command trees and <xref:System.Data.Common.CommandTrees.DbExpression>.</span></span>  
  
## <a name="the-role-of-the-sql-generation-module"></a><span data-ttu-id="7a5f9-108">Die Rolle des SQL-Generierungsmoduls</span><span class="sxs-lookup"><span data-stu-id="7a5f9-108">The Role of the SQL Generation Module</span></span>  
 <span data-ttu-id="7a5f9-109">Das SQL-Generierungsmodul eines [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]-Anbieters übersetzt eine angegebene Abfragebefehlsstruktur in eine einzelne SQL SELECT-Anweisung, die für eine SQL:1999-kompatible Datenbank vorgesehen ist.</span><span class="sxs-lookup"><span data-stu-id="7a5f9-109">The SQL generation module of an [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] provider translates a given query command tree into a single SQL SELECT statement that targets a SQL:1999-compliant database.</span></span> <span data-ttu-id="7a5f9-110">Das generierte SQL sollte so wenige geschachtelte Abfragen wie möglich enthalten.</span><span class="sxs-lookup"><span data-stu-id="7a5f9-110">The generated SQL should have as few nested queries as possible.</span></span> <span data-ttu-id="7a5f9-111">Das SQL-Generierungsmodul sollte die Ausgabeabfrage-Befehlsstruktur nicht vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="7a5f9-111">The SQL generation module should not simplify the output query command tree.</span></span> <span data-ttu-id="7a5f9-112">[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] führt dies beispielsweise durch das Eliminieren von Joins und das Reduzieren von aufeinander folgenden Filterknoten aus.</span><span class="sxs-lookup"><span data-stu-id="7a5f9-112">The [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] will do this, for example by eliminating joins and collapsing consecutive filter nodes.</span></span>  
  
 <span data-ttu-id="7a5f9-113">Die <xref:System.Data.Common.DbProviderServices>-Klasse ist der Ausgangspunkt für den Zugriff auf die SQL-Generierungsebene zur Umwandlung von Befehlsstrukturen in <xref:System.Data.Common.DbCommand>.</span><span class="sxs-lookup"><span data-stu-id="7a5f9-113">The <xref:System.Data.Common.DbProviderServices> class is the starting point for accessing the SQL generation layer to convert command trees into <xref:System.Data.Common.DbCommand>.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7a5f9-114">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="7a5f9-114">In This Section</span></span>  
 [<span data-ttu-id="7a5f9-115">Form der Befehlsstrukturen</span><span class="sxs-lookup"><span data-stu-id="7a5f9-115">The Shape of the Command Trees</span></span>](../../../../../docs/framework/data/adonet/ef/the-shape-of-the-command-trees.md)  
  
 [<span data-ttu-id="7a5f9-116">Generieren von SQL aus Befehlsstrukturen: Bewährte Methoden</span><span class="sxs-lookup"><span data-stu-id="7a5f9-116">Generating SQL from Command Trees - Best Practices</span></span>](../../../../../docs/framework/data/adonet/ef/generating-sql-from-command-trees-best-practices.md)  
  
 [<span data-ttu-id="7a5f9-117">SQL-Generierung im Beispielanbieter</span><span class="sxs-lookup"><span data-stu-id="7a5f9-117">SQL Generation in the Sample Provider</span></span>](../../../../../docs/framework/data/adonet/ef/sql-generation-in-the-sample-provider.md)  
  
## <a name="see-also"></a><span data-ttu-id="7a5f9-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7a5f9-118">See Also</span></span>  
 [<span data-ttu-id="7a5f9-119">Schreiben eines Entity Framework-Datenanbieters</span><span class="sxs-lookup"><span data-stu-id="7a5f9-119">Writing an Entity Framework Data Provider</span></span>](../../../../../docs/framework/data/adonet/ef/writing-an-ef-data-provider.md)
