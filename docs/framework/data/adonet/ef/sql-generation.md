---
title: SQL-Generierung
ms.date: 03/30/2017
ms.assetid: 0e16aa02-d458-4418-a765-58b42aad9315
ms.openlocfilehash: 9c5301d3f4d5bc2e0db4a138c6d8ceb06d3a7845
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854352"
---
# <a name="sql-generation"></a><span data-ttu-id="52507-102">SQL-Generierung</span><span class="sxs-lookup"><span data-stu-id="52507-102">SQL Generation</span></span>
<span data-ttu-id="52507-103">Wenn Sie einen Anbieter für das Entity Framework schreiben, müssen Sie Entity Framework Befehlsstrukturen in SQL übersetzen, die von einer bestimmten Datenbank verstanden werden können, z. b. Transact-SQL für SQL Server oder PL/SQL für Oracle.</span><span class="sxs-lookup"><span data-stu-id="52507-103">When you write a provider for the Entity Framework, you must translate Entity Framework command trees into SQL that a specific database can understand, such as Transact-SQL for SQL Server or PL/SQL for Oracle.</span></span> <span data-ttu-id="52507-104">In diesem Abschnitt erfahren Sie, wie Sie eine SQL-Generierungs Komponente (für SELECT-Abfragen) für einen Entity Framework-Anbieter entwickeln.</span><span class="sxs-lookup"><span data-stu-id="52507-104">In this section, you will learn how to develop a SQL generation component (for SELECT queries) for an Entity Framework provider.</span></span> <span data-ttu-id="52507-105">Weitere Informationen zu INSERT-, Update-und DELETE-Abfragen finden Sie unter [Ändern der SQL-Generierung](modification-sql-generation.md).</span><span class="sxs-lookup"><span data-stu-id="52507-105">For information about insert, update, and delete queries, see [Modification SQL Generation](modification-sql-generation.md).</span></span>  
  
 <span data-ttu-id="52507-106">Um diesen Abschnitt zu verstehen, sollten Sie mit dem Entity Framework und dem ADO.NET-Anbieter Modell vertraut sein.</span><span class="sxs-lookup"><span data-stu-id="52507-106">To understand this section, you should be familiar with the Entity Framework and the ADO.NET Provider Model.</span></span> <span data-ttu-id="52507-107">Außerdem sollten Sie Befehlsstrukturen und <xref:System.Data.Common.CommandTrees.DbExpression> verstehen.</span><span class="sxs-lookup"><span data-stu-id="52507-107">You should also understand command trees and <xref:System.Data.Common.CommandTrees.DbExpression>.</span></span>  
  
## <a name="the-role-of-the-sql-generation-module"></a><span data-ttu-id="52507-108">Die Rolle des SQL-Generierungsmoduls</span><span class="sxs-lookup"><span data-stu-id="52507-108">The Role of the SQL Generation Module</span></span>  
 <span data-ttu-id="52507-109">Das SQL-Generierungs Modul eines Entity Framework Anbieters übersetzt eine angegebene Abfrage Befehlsstruktur in eine einzelne SQL SELECT-Anweisung, die auf eine SQL: 1999-kompatible Datenbank abzielt.</span><span class="sxs-lookup"><span data-stu-id="52507-109">The SQL generation module of an Entity Framework provider translates a given query command tree into a single SQL SELECT statement that targets a SQL:1999-compliant database.</span></span> <span data-ttu-id="52507-110">Das generierte SQL sollte so wenige geschachtelte Abfragen wie möglich enthalten.</span><span class="sxs-lookup"><span data-stu-id="52507-110">The generated SQL should have as few nested queries as possible.</span></span> <span data-ttu-id="52507-111">Das SQL-Generierungsmodul sollte die Ausgabeabfrage-Befehlsstruktur nicht vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="52507-111">The SQL generation module should not simplify the output query command tree.</span></span> <span data-ttu-id="52507-112">Dies wird durch den Entity Framework erfolgt, beispielsweise durch das Eliminieren von Joins und das reduzieren aufeinander folgender Filter Knoten.</span><span class="sxs-lookup"><span data-stu-id="52507-112">The Entity Framework will do this, for example by eliminating joins and collapsing consecutive filter nodes.</span></span>  
  
 <span data-ttu-id="52507-113">Die <xref:System.Data.Common.DbProviderServices>-Klasse ist der Ausgangspunkt für den Zugriff auf die SQL-Generierungsebene zur Umwandlung von Befehlsstrukturen in <xref:System.Data.Common.DbCommand>.</span><span class="sxs-lookup"><span data-stu-id="52507-113">The <xref:System.Data.Common.DbProviderServices> class is the starting point for accessing the SQL generation layer to convert command trees into <xref:System.Data.Common.DbCommand>.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="52507-114">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="52507-114">In This Section</span></span>  
 [<span data-ttu-id="52507-115">Form der Befehlsstrukturen</span><span class="sxs-lookup"><span data-stu-id="52507-115">The Shape of the Command Trees</span></span>](the-shape-of-the-command-trees.md)  
  
 [<span data-ttu-id="52507-116">Generieren von SQL aus Befehlsstrukturen: Bewährte Methoden</span><span class="sxs-lookup"><span data-stu-id="52507-116">Generating SQL from Command Trees - Best Practices</span></span>](generating-sql-from-command-trees-best-practices.md)  
  
 [<span data-ttu-id="52507-117">SQL-Generierung im Beispielanbieter</span><span class="sxs-lookup"><span data-stu-id="52507-117">SQL Generation in the Sample Provider</span></span>](sql-generation-in-the-sample-provider.md)  
  
## <a name="see-also"></a><span data-ttu-id="52507-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="52507-118">See also</span></span>

- [<span data-ttu-id="52507-119">Schreiben eines Entity Framework-Datenanbieters</span><span class="sxs-lookup"><span data-stu-id="52507-119">Writing an Entity Framework Data Provider</span></span>](writing-an-ef-data-provider.md)
