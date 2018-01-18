---
title: System.DateTimeOffset-Methoden
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 25b3e5c0-7603-4a70-b3e5-2149e3da69a2
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 23fab531e127e26f1a4fb9fc8f644b903188f60a
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2018
---
# <a name="systemdatetimeoffset-methods"></a><span data-ttu-id="115c2-102">System.DateTimeOffset-Methoden</span><span class="sxs-lookup"><span data-stu-id="115c2-102">System.DateTimeOffset Methods</span></span>
<span data-ttu-id="115c2-103">Nach der Zuordnung im Objektmodell oder in der externen Zuordnungsdatei können Sie mit LINQ to SQL die meisten der <xref:System.DateTimeOffset?displayProperty=nameWithType>-Methoden, -Operatoren und -Eigenschaften innerhalb Ihrer LINQ to SQL-Abfragen aufrufen.</span><span class="sxs-lookup"><span data-stu-id="115c2-103">Once mapped in the object model or external mapping file, LINQ to SQL allows you to call most of the <xref:System.DateTimeOffset?displayProperty=nameWithType> methods, operators, and properties from within your LINQ to SQL queries.</span></span>  
  
 <span data-ttu-id="115c2-104">Es werden nur die Methoden nicht unterstützt, die von <xref:System.Object?displayProperty=nameWithType> erben und im Kontext von LINQ to SQL-Abfragen keinen Sinn ergeben, z. B. `Finalize`, `GetHashCode`, `GetType` und `MemberwiseClone`.</span><span class="sxs-lookup"><span data-stu-id="115c2-104">The only methods not supported are those inherited from <xref:System.Object?displayProperty=nameWithType> that do not make sense in the context of LINQ to SQL queries, such as: `Finalize`, `GetHashCode`, `GetType`, and `MemberwiseClone`.</span></span> <span data-ttu-id="115c2-105">Diese Methoden werden nicht unterstützt, da sie von LINQ to SQL für die Ausführung auf dem SQL Server nicht übersetzt werden können.</span><span class="sxs-lookup"><span data-stu-id="115c2-105">These methods are not supported because LINQ to SQL cannot translate them for execution on the SQL Server.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="115c2-106">Für die <xref:System.DateTimeOffset?displayProperty=nameWithType>-Struktur der Common Language Runtime (CLR) und deren Zuordnung zu einer SQL-`DATETIMEOFFSET`-Spalte mit LINQ to SQL ist .NET Framework 3.5 SP1 oder höher erforderlich.</span><span class="sxs-lookup"><span data-stu-id="115c2-106">The common language runtime (CLR) <xref:System.DateTimeOffset?displayProperty=nameWithType> structure, and the ability to map it to a SQL `DATETIMEOFFSET` column with LINQ to SQL, requires the .NET Framework 3.5 SP1 or beyond.</span></span> <span data-ttu-id="115c2-107">Die SQL-`DATETIMEOFFSET`-Spalte ist nur in Microsoft SQL Server 2008 und höher verfügbar.</span><span class="sxs-lookup"><span data-stu-id="115c2-107">The SQL `DATETIMEOFFSET` column is only available in Microsoft SQL Server 2008 and beyond.</span></span>  
  
## <a name="sqlmethods-date-and-time-methods"></a><span data-ttu-id="115c2-108">Datums- und Uhrzeitmethoden von SQLMethods</span><span class="sxs-lookup"><span data-stu-id="115c2-108">SQLMethods Date and Time Methods</span></span>  
 <span data-ttu-id="115c2-109">Zusätzlich zu den Methoden der <xref:System.DateTimeOffset>-Struktur werden von LINQ to SQL zum Arbeiten mit Datums- und Uhrzeitangaben die in der folgenden Tabelle aufgeführten Methoden der <xref:System.Data.Linq.SqlClient.SqlMethods?displayProperty=nameWithType>-Klasse bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="115c2-109">In addition to the methods offered by the <xref:System.DateTimeOffset> structure, LINQ to SQL offers the methods listed in the following table from the <xref:System.Data.Linq.SqlClient.SqlMethods?displayProperty=nameWithType> class for working with date and time.</span></span>  
  
||||  
|-|-|-|  
|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffDay%2A>|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffMillisecond%2A>|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffNanosecond%2A>|  
|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffHour%2A>|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffMinute%2A>|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffSecond%2A>|  
|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffMicrosecond%2A>|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffMonth%2A>|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffYear%2A>|  
  
## <a name="see-also"></a><span data-ttu-id="115c2-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="115c2-110">See Also</span></span>  
 [<span data-ttu-id="115c2-111">Abfragekonzepte</span><span class="sxs-lookup"><span data-stu-id="115c2-111">Query Concepts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)  
 [<span data-ttu-id="115c2-112">Erstellen des Objektmodells</span><span class="sxs-lookup"><span data-stu-id="115c2-112">Creating the Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/creating-the-object-model.md)  
 [<span data-ttu-id="115c2-113">SQL-CLR-Typenzuordnung</span><span class="sxs-lookup"><span data-stu-id="115c2-113">SQL-CLR Type Mapping</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md)
