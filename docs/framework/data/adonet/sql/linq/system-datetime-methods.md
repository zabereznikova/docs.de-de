---
title: System.DateTime-Methoden
ms.date: 03/30/2017
ms.assetid: 4f80700c-e83f-4ab6-af0f-1c9a606e1133
ms.openlocfilehash: e3bffb1f47c19ccf7ea59151cd3545a15d59f1f2
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91203487"
---
# <a name="systemdatetime-methods"></a><span data-ttu-id="7251f-102">System.DateTime-Methoden</span><span class="sxs-lookup"><span data-stu-id="7251f-102">System.DateTime Methods</span></span>

<span data-ttu-id="7251f-103">Die folgenden LINQ to SQL-unterstützten Methoden, Operatoren und Eigenschaften sind für LINQ to SQL-Abfragen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="7251f-103">The following LINQ to SQL-supported methods, operators, and properties are available to use in LINQ to SQL queries.</span></span> <span data-ttu-id="7251f-104">Wenn eine Methode, ein Operator oder eine Eigenschaft nicht unterstützt wird, kann der Member von LINQ to SQL nicht für die Ausführung auf dem SQL Server übersetzt werden.</span><span class="sxs-lookup"><span data-stu-id="7251f-104">When a method, operator or property is unsupported, LINQ to SQL cannot translate the member for execution on the SQL Server.</span></span> <span data-ttu-id="7251f-105">Diese Member können trotzdem im Code verwendet werden. Sie müssen jedoch ausgewertet werden, bevor die Abfrage in Transact-SQL übersetzt wird oder nachdem die Ergebnisse aus der Datenbank abgerufen wurden.</span><span class="sxs-lookup"><span data-stu-id="7251f-105">You may use these members in your code, however, they must be evaluated before the query is translated to Transact-SQL or after the results have been retrieved from the database.</span></span>  
  
## <a name="supported-systemdatetime-members"></a><span data-ttu-id="7251f-106">Unterstützte 'System.DateTime'-Member</span><span class="sxs-lookup"><span data-stu-id="7251f-106">Supported System.DateTime Members</span></span>  

 <span data-ttu-id="7251f-107">Nach der Zuordnung im Objektmodell oder in der externen Mappingdatei können Sie mit LINQ to SQL die folgenden <xref:System.DateTime?displayProperty=nameWithType>-Member in LINQ to SQL-Abfragen aufrufen.</span><span class="sxs-lookup"><span data-stu-id="7251f-107">Once mapped in the object model or external mapping file, LINQ to SQL allows you to call the following <xref:System.DateTime?displayProperty=nameWithType> members inside LINQ to SQL queries.</span></span>  
  
|<span data-ttu-id="7251f-108">Unterstützte <xref:System.DateTime>-Methoden</span><span class="sxs-lookup"><span data-stu-id="7251f-108">Supported <xref:System.DateTime> Methods</span></span>|<span data-ttu-id="7251f-109">Unterstützte <xref:System.DateTime>-Operatoren</span><span class="sxs-lookup"><span data-stu-id="7251f-109">Supported <xref:System.DateTime> Operators</span></span>|<span data-ttu-id="7251f-110">Unterstützte <xref:System.DateTime>-Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="7251f-110">Supported <xref:System.DateTime> Properties</span></span>|  
|------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.DateTime.Add%2A>|<xref:System.DateTime.op_Addition%2A>|<xref:System.DateTime.Date%2A>|  
|<xref:System.DateTime.AddDays%2A>|<xref:System.DateTime.op_Equality%2A>|<xref:System.DateTime.Day%2A>|  
|<xref:System.DateTime.AddHours%2A>|<xref:System.DateTime.op_GreaterThan%2A>|<xref:System.DateTime.DayOfWeek%2A>|  
|<xref:System.DateTime.AddMilliseconds%2A>|<xref:System.DateTime.op_GreaterThanOrEqual%2A>|<xref:System.DateTime.DayOfYear%2A>|  
|<xref:System.DateTime.AddMinutes%2A>|<xref:System.DateTime.op_Inequality%2A>|<xref:System.DateTime.Hour%2A>|  
|<xref:System.DateTime.AddMonths%2A>|<xref:System.DateTime.op_LessThan%2A>|<xref:System.DateTime.Millisecond%2A>|  
|<xref:System.DateTime.AddSeconds%2A>|<xref:System.DateTime.op_LessThanOrEqual%2A>|<xref:System.DateTime.Minute%2A>|  
|<xref:System.DateTime.AddTicks%2A>|<xref:System.DateTime.op_Subtraction%2A>|<xref:System.DateTime.Month%2A>|  
|<xref:System.DateTime.AddYears%2A>||<xref:System.DateTime.Now%2A>|  
|<xref:System.DateTime.Compare%2A>||<xref:System.DateTime.Second%2A>|  
|<xref:System.DateTime.CompareTo%28System.DateTime%29>||<xref:System.DateTime.TimeOfDay%2A>|  
|<xref:System.DateTime.Equals%28System.DateTime%29>||<xref:System.DateTime.Today%2A>|  
|||<xref:System.DateTime.Year%2A>|  
  
## <a name="members-not-supported-by-linq-to-sql"></a><span data-ttu-id="7251f-111">Von LINQ to SQL nicht unterstützte Member</span><span class="sxs-lookup"><span data-stu-id="7251f-111">Members Not Supported by LINQ to SQL</span></span>  

 <span data-ttu-id="7251f-112">Die folgenden Member werden in LINQ to SQL-Abfragen nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="7251f-112">The following members are not supported inside LINQ to SQL queries.</span></span>  
  
|||  
|-|-|  
|<xref:System.DateTime.IsDaylightSavingTime%2A>|<xref:System.DateTime.IsLeapYear%2A>|  
|<xref:System.DateTime.DaysInMonth%2A>|<xref:System.DateTime.ToBinary%2A>|  
|<xref:System.DateTime.ToFileTime%2A>|<xref:System.DateTime.ToFileTimeUtc%2A>|  
|<xref:System.DateTime.ToLongDateString%2A>|<xref:System.DateTime.ToLongTimeString%2A>|  
|<xref:System.DateTime.ToOADate%2A>|<xref:System.DateTime.ToShortDateString%2A>|  
|<xref:System.DateTime.ToShortTimeString%2A>|<xref:System.DateTime.ToUniversalTime%2A>|  
|<xref:System.DateTime.FromBinary%2A>|<xref:System.DateTime.UtcNow%2A>|  
|<xref:System.DateTime.FromFileTime%2A>|<xref:System.DateTime.FromFileTimeUtc%2A>|  
|<xref:System.DateTime.FromOADate%2A>|<xref:System.DateTime.GetDateTimeFormats%2A>|  
  
## <a name="method-translation-example"></a><span data-ttu-id="7251f-113">Beispiel für die Methodenübersetzung</span><span class="sxs-lookup"><span data-stu-id="7251f-113">Method Translation Example</span></span>  

 <span data-ttu-id="7251f-114">Alle von LINQ to SQL unterstützten Methoden werden in Transact-SQL übersetzt, bevor sie an SQL Server gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="7251f-114">All methods supported by LINQ to SQL are translated to Transact-SQL before they are sent to   SQL Server.</span></span> <span data-ttu-id="7251f-115">Beachten Sie beispielsweise das folgende Muster.</span><span class="sxs-lookup"><span data-stu-id="7251f-115">For example, consider the following pattern.</span></span>  
  
 `(dateTime1 – dateTime2).{Days, Hours, Milliseconds, Minutes, Months, Seconds, Years}`  
  
 <span data-ttu-id="7251f-116">Wenn es erkannt wird, wird es wie folgt in einen direkten Aufruf der `DATEDIFF`-Funktion von SQL Server übersetzt:</span><span class="sxs-lookup"><span data-stu-id="7251f-116">When it is recognized, it is translated into a direct call to the SQL Server `DATEDIFF` function, as follows:</span></span>  
  
 `DATEDIFF({DatePart}, @dateTime1, @dateTime2)`  
  
## <a name="sqlmethods-date-and-time-methods"></a><span data-ttu-id="7251f-117">Datums- und Uhrzeitmethoden von SQLMethods</span><span class="sxs-lookup"><span data-stu-id="7251f-117">SQLMethods Date and Time Methods</span></span>  

 <span data-ttu-id="7251f-118">Zusätzlich zu den Methoden der <xref:System.DateTime>-Struktur werden von LINQ to SQL zum Arbeiten mit Datums- und Uhrzeitangaben die in der folgenden Tabelle aufgeführten Methoden der <xref:System.Data.Linq.SqlClient.SqlMethods?displayProperty=nameWithType>-Klasse bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="7251f-118">In addition to the methods offered by the <xref:System.DateTime> structure, LINQ to SQL offers the methods listed in the following table from the <xref:System.Data.Linq.SqlClient.SqlMethods?displayProperty=nameWithType> class for working with date and time.</span></span>  
  
||||  
|-|-|-|  
|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffDay%2A>|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffMillisecond%2A>|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffNanosecond%2A>|  
|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffHour%2A>|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffMinute%2A>|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffSecond%2A>|  
|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffMicrosecond%2A>|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffMonth%2A>|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffYear%2A>|  
  
## <a name="see-also"></a><span data-ttu-id="7251f-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7251f-119">See also</span></span>

- [<span data-ttu-id="7251f-120">Abfragekonzepte</span><span class="sxs-lookup"><span data-stu-id="7251f-120">Query Concepts</span></span>](query-concepts.md)
- [<span data-ttu-id="7251f-121">Erstellen des Objektmodells</span><span class="sxs-lookup"><span data-stu-id="7251f-121">Creating the Object Model</span></span>](creating-the-object-model.md)
- [<span data-ttu-id="7251f-122">SQL-CLR-Typenzuordnung</span><span class="sxs-lookup"><span data-stu-id="7251f-122">SQL-CLR Type Mapping</span></span>](sql-clr-type-mapping.md)
- [<span data-ttu-id="7251f-123">Datentypen und Funktionen</span><span class="sxs-lookup"><span data-stu-id="7251f-123">Data Types and Functions</span></span>](data-types-and-functions.md)
