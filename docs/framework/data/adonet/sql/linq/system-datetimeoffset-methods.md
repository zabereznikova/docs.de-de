---
title: System.DateTimeOffset-Methoden
ms.date: 03/30/2017
ms.assetid: 25b3e5c0-7603-4a70-b3e5-2149e3da69a2
ms.openlocfilehash: a638a4fcc156727f734ff480a18b9997bc9d2e34
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69959086"
---
# <a name="systemdatetimeoffset-methods"></a><span data-ttu-id="1476a-102">System.DateTimeOffset-Methoden</span><span class="sxs-lookup"><span data-stu-id="1476a-102">System.DateTimeOffset Methods</span></span>
<span data-ttu-id="1476a-103">Nach der Zuordnung im Objektmodell oder in der externen Zuordnungsdatei können Sie mit LINQ to SQL die meisten der <xref:System.DateTimeOffset?displayProperty=nameWithType>-Methoden, -Operatoren und -Eigenschaften innerhalb Ihrer LINQ to SQL-Abfragen aufrufen.</span><span class="sxs-lookup"><span data-stu-id="1476a-103">Once mapped in the object model or external mapping file, LINQ to SQL allows you to call most of the <xref:System.DateTimeOffset?displayProperty=nameWithType> methods, operators, and properties from within your LINQ to SQL queries.</span></span>  
  
 <span data-ttu-id="1476a-104">Es werden nur die Methoden nicht unterstützt, die von <xref:System.Object?displayProperty=nameWithType> erben und im Kontext von LINQ to SQL-Abfragen keinen Sinn ergeben, z. B. `Finalize`, `GetHashCode`, `GetType` und `MemberwiseClone`.</span><span class="sxs-lookup"><span data-stu-id="1476a-104">The only methods not supported are those inherited from <xref:System.Object?displayProperty=nameWithType> that do not make sense in the context of LINQ to SQL queries, such as: `Finalize`, `GetHashCode`, `GetType`, and `MemberwiseClone`.</span></span> <span data-ttu-id="1476a-105">Diese Methoden werden nicht unterstützt, da sie von LINQ to SQL für die Ausführung auf dem SQL Server nicht übersetzt werden können.</span><span class="sxs-lookup"><span data-stu-id="1476a-105">These methods are not supported because LINQ to SQL cannot translate them for execution on the SQL Server.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1476a-106">Für die <xref:System.DateTimeOffset?displayProperty=nameWithType>-Struktur der Common Language Runtime (CLR) und deren Zuordnung zu einer SQL-`DATETIMEOFFSET`-Spalte mit LINQ to SQL ist .NET Framework 3.5 SP1 oder höher erforderlich.</span><span class="sxs-lookup"><span data-stu-id="1476a-106">The common language runtime (CLR) <xref:System.DateTimeOffset?displayProperty=nameWithType> structure, and the ability to map it to a SQL `DATETIMEOFFSET` column with LINQ to SQL, requires the .NET Framework 3.5 SP1 or beyond.</span></span> <span data-ttu-id="1476a-107">Die SQL-`DATETIMEOFFSET`-Spalte ist nur in Microsoft SQL Server 2008 und höher verfügbar.</span><span class="sxs-lookup"><span data-stu-id="1476a-107">The SQL `DATETIMEOFFSET` column is only available in Microsoft SQL Server 2008 and beyond.</span></span>  
  
## <a name="sqlmethods-date-and-time-methods"></a><span data-ttu-id="1476a-108">Datums- und Uhrzeitmethoden von SQLMethods</span><span class="sxs-lookup"><span data-stu-id="1476a-108">SQLMethods Date and Time Methods</span></span>  
 <span data-ttu-id="1476a-109">Zusätzlich zu den Methoden der <xref:System.DateTimeOffset>-Struktur werden von LINQ to SQL zum Arbeiten mit Datums- und Uhrzeitangaben die in der folgenden Tabelle aufgeführten Methoden der <xref:System.Data.Linq.SqlClient.SqlMethods?displayProperty=nameWithType>-Klasse bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="1476a-109">In addition to the methods offered by the <xref:System.DateTimeOffset> structure, LINQ to SQL offers the methods listed in the following table from the <xref:System.Data.Linq.SqlClient.SqlMethods?displayProperty=nameWithType> class for working with date and time.</span></span>  
  
||||  
|-|-|-|  
|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffDay%2A>|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffMillisecond%2A>|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffNanosecond%2A>|  
|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffHour%2A>|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffMinute%2A>|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffSecond%2A>|  
|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffMicrosecond%2A>|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffMonth%2A>|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffYear%2A>|  
  
## <a name="see-also"></a><span data-ttu-id="1476a-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1476a-110">See also</span></span>

- [<span data-ttu-id="1476a-111">Abfragekonzepte</span><span class="sxs-lookup"><span data-stu-id="1476a-111">Query Concepts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)
- [<span data-ttu-id="1476a-112">Erstellen des Objektmodells</span><span class="sxs-lookup"><span data-stu-id="1476a-112">Creating the Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/creating-the-object-model.md)
- [<span data-ttu-id="1476a-113">SQL-CLR-Typenzuordnung</span><span class="sxs-lookup"><span data-stu-id="1476a-113">SQL-CLR Type Mapping</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md)
