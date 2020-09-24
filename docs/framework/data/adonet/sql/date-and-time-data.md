---
title: Datums- und Zeitdaten
description: Informationen zu Datentypen für die Behandlung von Datums-und Uhrzeit Informationen finden Sie in der .NET Framework Datenanbieter für SQL Server.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 6f5ff56a-a57e-49d7-8ae9-bbed697e42e3
ms.openlocfilehash: 6fe047fc672a2b42f886e81dcace91042a552932
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91156315"
---
# <a name="date-and-time-data"></a><span data-ttu-id="7d47d-103">Datums- und Zeitdaten</span><span class="sxs-lookup"><span data-stu-id="7d47d-103">Date and Time Data</span></span>

<span data-ttu-id="7d47d-104">SQL Server 2008 bietet neue Datentypen für Datums- und Uhrzeitinformationen.</span><span class="sxs-lookup"><span data-stu-id="7d47d-104">SQL Server 2008 introduces new data types for handling date and time information.</span></span> <span data-ttu-id="7d47d-105">Die neuen Datentypen umfassen getrennte Typen für Datum und Uhrzeit sowie erweiterte Datentypen mit größerem Umfang, mehr Präzision und besserer Berücksichtigung von Zeitzonen.</span><span class="sxs-lookup"><span data-stu-id="7d47d-105">The new data types include separate types for date and time, and expanded data types with greater range, precision, and time-zone awareness.</span></span> <span data-ttu-id="7d47d-106">Ab .NET Framework Version 3.5 Service Pack (SP) 1 bietet der .NET Framework-Datenanbieter für SQL Server (<xref:System.Data.SqlClient>) vollständige Unterstützung für alle neuen Funktionen der SQL Server 2008-Datenbank-Engine.</span><span class="sxs-lookup"><span data-stu-id="7d47d-106">Starting with the .NET Framework version 3.5 Service Pack (SP) 1, the .NET Framework Data Provider for SQL Server (<xref:System.Data.SqlClient>) provides full support for all the new features of the SQL Server 2008 Database Engine.</span></span> <span data-ttu-id="7d47d-107">Sie müssen .NET Framework 3.5 SP1 (oder höher) installieren, um diese neuen Funktionen mit SqlClient zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="7d47d-107">You must install the .NET Framework 3.5 SP1 (or later) to use these new features with SqlClient.</span></span>  
  
 <span data-ttu-id="7d47d-108">SQL Server-Versionen vor SQL Server 2008 hatten nur zwei Datentypen für das Arbeiten mit Datums- und Uhrzeitwerten: `datetime` und `smalldatetime`.</span><span class="sxs-lookup"><span data-stu-id="7d47d-108">Versions of SQL Server earlier than SQL Server 2008 only had two data types for working with date and time values: `datetime` and `smalldatetime`.</span></span> <span data-ttu-id="7d47d-109">Beide Datentypen enthalten sowohl einen Datumswert als auch einen Uhrzeitwert, wodurch es schwierig ist, nur mit den Datums- oder nur mit den Uhrzeitwerten zu arbeiten.</span><span class="sxs-lookup"><span data-stu-id="7d47d-109">Both of these data types contain both the date value and a time value, which makes it difficult to work with only date or only time values.</span></span> <span data-ttu-id="7d47d-110">Außerdem unterstützen diese Datentypen nur Datumsangaben nach Einführung des gregorianischen Kalenders in England im Jahr 1753.</span><span class="sxs-lookup"><span data-stu-id="7d47d-110">Also, these data types only support dates that occur after the introduction of the Gregorian calendar in England in 1753.</span></span> <span data-ttu-id="7d47d-111">Eine weitere Einschränkung besteht darin, dass diese älteren Datentypen keine Zeitzonen berücksichtigen, was es schwierig macht, mit Daten zu arbeiten, die aus mehreren Zeitzonen stammen.</span><span class="sxs-lookup"><span data-stu-id="7d47d-111">Another limitation is that these older data types are not time-zone aware, which makes it difficult to work with data that originates from multiple time zones.</span></span>  
  
 <span data-ttu-id="7d47d-112">Eine vollständige Dokumentation der SQL Server-Datentypen finden Sie in der SQL Server-Onlinedokumentation.</span><span class="sxs-lookup"><span data-stu-id="7d47d-112">Complete documentation for SQL Server data types is available in SQL Server Books Online.</span></span> <span data-ttu-id="7d47d-113">In der folgenden Tabelle sind die versionsspezifischen Einsteigerthemen für Datums- und Uhrzeitdaten aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="7d47d-113">The following table lists the version-specific entry-level topics for date and time data.</span></span>  
  
 <span data-ttu-id="7d47d-114">**SQL Server-Dokumentation**</span><span class="sxs-lookup"><span data-stu-id="7d47d-114">**SQL Server documentation**</span></span>  
  
1. <span data-ttu-id="7d47d-115">[Verwenden von Datums- und Uhrzeitdaten](/previous-versions/sql/sql-server-2008/ms180878(v=sql.100))</span><span class="sxs-lookup"><span data-stu-id="7d47d-115">[Using Date and Time Data](/previous-versions/sql/sql-server-2008/ms180878(v=sql.100))</span></span>  
  
## <a name="datetime-data-types-introduced-in-sql-server-2008"></a><span data-ttu-id="7d47d-116">Neue Datums-/Uhrzeitdaten in SQL Server 2008</span><span class="sxs-lookup"><span data-stu-id="7d47d-116">Date/Time Data Types Introduced in SQL Server 2008</span></span>  

 <span data-ttu-id="7d47d-117">In der folgenden Tabelle werden die Datums- und Uhrzeit-Datentypen beschrieben.</span><span class="sxs-lookup"><span data-stu-id="7d47d-117">The following table describes the new date and time data types.</span></span>  
  
|<span data-ttu-id="7d47d-118">SQL Server-Datentyp</span><span class="sxs-lookup"><span data-stu-id="7d47d-118">SQL Server data type</span></span>|<span data-ttu-id="7d47d-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7d47d-119">Description</span></span>|  
|--------------------------|-----------------|  
|`date`|<span data-ttu-id="7d47d-120">Der Bereich der gültigen Werte für den `date`-Datentyp reicht vom 1. Januar 0001 bis zum 31. Dezember 9999 mit einer Genauigkeit von einem Tag.</span><span class="sxs-lookup"><span data-stu-id="7d47d-120">The `date` data type has a range of January 1, 01 through December 31, 9999 with an accuracy of 1 day.</span></span> <span data-ttu-id="7d47d-121">Der Standardwert ist der 1. Januar 1900.</span><span class="sxs-lookup"><span data-stu-id="7d47d-121">The default value is January 1, 1900.</span></span> <span data-ttu-id="7d47d-122">Die Speichergröße beträgt 3 Byte.</span><span class="sxs-lookup"><span data-stu-id="7d47d-122">The storage size is 3 bytes.</span></span>|  
|`time`|<span data-ttu-id="7d47d-123">Der `time`-Datentyp speichert reine Uhrzeitwerte im 24-Stunden-Format.</span><span class="sxs-lookup"><span data-stu-id="7d47d-123">The `time` data type stores time values only, based on a 24-hour clock.</span></span> <span data-ttu-id="7d47d-124">Der `time`-Datentyp hat einen Bereich von 00:00:00.0000000 bis 23:59:59.9999999 mit einer Genauigkeit von 100 Nanosekunden.</span><span class="sxs-lookup"><span data-stu-id="7d47d-124">The `time` data type has a range of 00:00:00.0000000 through 23:59:59.9999999 with an accuracy of 100 nanoseconds.</span></span> <span data-ttu-id="7d47d-125">Der Standardwert ist 00:00:00.0000000 (Mitternacht).</span><span class="sxs-lookup"><span data-stu-id="7d47d-125">The default value is 00:00:00.0000000 (midnight).</span></span> <span data-ttu-id="7d47d-126">Der `time`-Datentyp unterstützt benutzerdefinierte Sekundenbruchteilgenauigkeit, und die Speichergröße variiert je nach angegebener Genauigkeit zwischen 3 und 6 Bytes.</span><span class="sxs-lookup"><span data-stu-id="7d47d-126">The `time` data type supports user-defined fractional second precision, and the storage size varies from 3 to 6 bytes, based on the precision specified.</span></span>|  
|`datetime2`|<span data-ttu-id="7d47d-127">Der Datentyp `datetime2` kombiniert den Bereich und die Genauigkeit der Datentypen `date` und `time` zu einem einzelnen Datentyp.</span><span class="sxs-lookup"><span data-stu-id="7d47d-127">The `datetime2` data type combines the range and precision of the `date` and `time` data types into a single data type.</span></span><br /><br /> <span data-ttu-id="7d47d-128">Die Standardwerte und Formate für Zeichenfolgenliterale sind identisch mit denen, die in den Datentypen `date` und `time` definiert sind.</span><span class="sxs-lookup"><span data-stu-id="7d47d-128">The default values and string literal formats are the same as those defined in the `date` and `time` data types.</span></span>|  
|`datetimeoffset`|<span data-ttu-id="7d47d-129">Der `datetimeoffset`-Datentyp besitzt alle Funktionen von `datetime2`, verfügt darüber hinaus aber auch über eine als Abweichung (Offset) von der koordinierten Weltzeit angegebene Zeitzonenangabe.</span><span class="sxs-lookup"><span data-stu-id="7d47d-129">The `datetimeoffset` data type has all the features of `datetime2` with an additional time zone offset.</span></span> <span data-ttu-id="7d47d-130">Der Zeitzonenoffset wird wie folgt dargestellt: [+&#124;-] HH:MM.</span><span class="sxs-lookup"><span data-stu-id="7d47d-130">The time zone offset is represented as [+&#124;-] HH:MM.</span></span> <span data-ttu-id="7d47d-131">Bei HH handelt es sich um zwei Ziffern im Bereich von 00 bis 24, die die Anzahl der Stunden im Zeitzonenoffset darstellen.</span><span class="sxs-lookup"><span data-stu-id="7d47d-131">HH is 2 digits ranging from 00 to 14 that represent the number of hours in the time zone offset.</span></span> <span data-ttu-id="7d47d-132">Bei MM handelt es sich um zwei Ziffern im Bereich von 00 bis 59, die die Anzahl der zusätzlichen Minuten im Zeitzonenoffset darstellen.</span><span class="sxs-lookup"><span data-stu-id="7d47d-132">MM is 2 digits ranging from 00 to 59 that represent the number of additional minutes in the time zone offset.</span></span> <span data-ttu-id="7d47d-133">Uhrzeitformate werden mit einer Genauigkeit von bis zu 100 Nanosekunden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="7d47d-133">Time formats are supported to 100 nanoseconds.</span></span> <span data-ttu-id="7d47d-134">Das obligatorische Plus- oder Minuszeichen gibt an, ob der Zeitzonenoffset von der UTC (Universal Time Coordinate oder Greenwich Mean Time) addiert oder subtrahiert wird, um die Ortszeit zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="7d47d-134">The mandatory + or - sign indicates whether the time zone offset is added or subtracted from UTC (Universal Time Coordinate or Greenwich Mean Time) to obtain the local time.</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="7d47d-135">Weitere Informationen über die Verwendung des `Type System Version`-Schlüsselworts finden Sie unter <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A>.</span><span class="sxs-lookup"><span data-stu-id="7d47d-135">For more information about using the `Type System Version` keyword, see <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A>.</span></span>  
  
## <a name="date-format-and-date-order"></a><span data-ttu-id="7d47d-136">Datumsformat und Datumsreihenfolge</span><span class="sxs-lookup"><span data-stu-id="7d47d-136">Date Format and Date Order</span></span>  

 <span data-ttu-id="7d47d-137">Wie SQL Server Datums- und Uhrzeitwerte analysiert, hängt nicht nur von der Typsystem- und Serverversion ab, sondern auch von der Standardsprache und den Formateinstellungen des Servers.</span><span class="sxs-lookup"><span data-stu-id="7d47d-137">How SQL Server parses date and time values depends not only on the type system version and server version, but also on the server's default language and format settings.</span></span> <span data-ttu-id="7d47d-138">Eine Datumszeichenfolge, die für die Datumsformate einer Sprache funktioniert, wird möglicherweise nicht erkannt, wenn die Abfrage über eine Verbindung erfolgt, die eine andere Sprach- und Datumsformateinstellung verwendet.</span><span class="sxs-lookup"><span data-stu-id="7d47d-138">A date string that works for the date formats of one language might be unrecognizable if the query is executed by a connection that uses a different language and date format setting.</span></span>  
  
 <span data-ttu-id="7d47d-139">Die Transact-SQL-Anweisung SET LANGUAGE legt implizit das DATEFORMAT fest, das die Reihenfolge der Datumsteile bestimmt.</span><span class="sxs-lookup"><span data-stu-id="7d47d-139">The Transact-SQL SET LANGUAGE statement implicitly sets the DATEFORMAT that determines the order of the date parts.</span></span> <span data-ttu-id="7d47d-140">Sie können die Transact-SQL-Anweisung SET DATEFORMAT für eine Verbindung verwenden, um Datumswerte eindeutig zu bestimmen, indem Sie die Datumsteile in der Reihenfolge MTJ, TMJ, JMT, JTM, MJT oder TJM sortieren.</span><span class="sxs-lookup"><span data-stu-id="7d47d-140">You can use the SET DATEFORMAT Transact-SQL statement on a connection to disambiguate date values by ordering the date parts in MDY, DMY, YMD, YDM, MYD, or DYM order.</span></span>  
  
 <span data-ttu-id="7d47d-141">Wenn Sie kein DATEFORMAT für die Verbindung angeben, verwendet SQL Server die der Verbindung zugeordnete Standardsprache.</span><span class="sxs-lookup"><span data-stu-id="7d47d-141">If you do not specify any DATEFORMAT for the connection, SQL Server uses the default language associated with the connection.</span></span> <span data-ttu-id="7d47d-142">Beispiel: Die Datumszeichenfolge 01/02/03 würde auf einem Server mit der Spracheinstellung „Englisch (USA)“ als MTJ (Januar 2, 2003) und auf einem Server mit der Spracheinstellung „Englisch (UK)“ als TMJ (1. Februar 2003) interpretiert.</span><span class="sxs-lookup"><span data-stu-id="7d47d-142">For example, a date string of '01/02/03' would be interpreted as MDY (January 2, 2003) on a server with a language setting of United States English, and as DMY (February 1, 2003) on a server with a language setting of British English.</span></span> <span data-ttu-id="7d47d-143">Das Jahr wird mithilfe der SQL Server-Regel für das Umstellungsjahr bestimmt, die das Umstellungsdatum für die Zuweisung des Jahrhundertwerts definiert.</span><span class="sxs-lookup"><span data-stu-id="7d47d-143">The year is determined by using SQL Server's cutoff year rule, which defines the cutoff date for assigning the century value.</span></span> <span data-ttu-id="7d47d-144">Weitere Informationen finden Sie unter Option "Umstellungs Jahr für Angaben mit [zwei Ziffern](/sql/database-engine/configure-windows/configure-the-two-digit-year-cutoff-server-configuration-option)".</span><span class="sxs-lookup"><span data-stu-id="7d47d-144">For more information, see [two digit year cutoff Option](/sql/database-engine/configure-windows/configure-the-two-digit-year-cutoff-server-configuration-option).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7d47d-145">Das Datumsformat JTM wird bei der Konvertierung aus einem Zeichenfolgenformat in `date`, `time`, `datetime2` oder `datetimeoffset` nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="7d47d-145">The YDM date format is not supported when converting from a string format to `date`, `time`, `datetime2`, or `datetimeoffset`.</span></span>  
  
 <span data-ttu-id="7d47d-146">Weitere Informationen zum Interpretieren von Datums-und uhrzeitanzeit SQL Server finden [Sie unter Verwenden von Datums-und Uhrzeit Daten](/previous-versions/sql/sql-server-2008/ms180878(v=sql.100)).</span><span class="sxs-lookup"><span data-stu-id="7d47d-146">For more information about how SQL Server interprets date and time data, see [Using Date and Time Data](/previous-versions/sql/sql-server-2008/ms180878(v=sql.100)).</span></span>  
  
## <a name="datetime-data-types-and-parameters"></a><span data-ttu-id="7d47d-147">Datentypen und Parameter zur Angabe von Datum und Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="7d47d-147">Date/Time Data Types and Parameters</span></span>  

 <span data-ttu-id="7d47d-148">Die folgenden Enumerationen wurden <xref:System.Data.SqlDbType> hinzugefügt, um die neuen Datums- und Uhrzeitdatentypen zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="7d47d-148">The following enumerations have been added to <xref:System.Data.SqlDbType> to support the new date and time data types.</span></span>  
  
- `SqlDbType.Date`  
  
- `SqlDbType.Time`  
  
- `SqlDbType.DateTime2`  
  
- `SqlDbType.DateTimeOffSet`  

<span data-ttu-id="7d47d-149">Sie können den Datentyp eines <xref:System.Data.SqlClient.SqlParameter> mithilfe einer der voranstehenden <xref:System.Data.SqlDbType>-Enumerationen angeben.</span><span class="sxs-lookup"><span data-stu-id="7d47d-149">You can specify the data type of a <xref:System.Data.SqlClient.SqlParameter> by using one of the preceding <xref:System.Data.SqlDbType> enumerations.</span></span>

> [!NOTE]
> <span data-ttu-id="7d47d-150">Sie können die `DbType`-Eigenschaft von `SqlParameter` nicht auf `SqlDbType.Date` festlegen.</span><span class="sxs-lookup"><span data-stu-id="7d47d-150">You cannot set the `DbType` property of a `SqlParameter` to `SqlDbType.Date`.</span></span>

 <span data-ttu-id="7d47d-151">Der Typ eines <xref:System.Data.SqlClient.SqlParameter> kann auch generisch angegeben werden, indem die <xref:System.Data.SqlClient.SqlParameter.DbType%2A>-Eigenschaft eines `SqlParameter`-Objekts auf einen bestimmten <xref:System.Data.DbType>-Enumerationswert festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="7d47d-151">You can also specify the type of a <xref:System.Data.SqlClient.SqlParameter> generically by setting the <xref:System.Data.SqlClient.SqlParameter.DbType%2A> property of a `SqlParameter` object to a particular <xref:System.Data.DbType> enumeration value.</span></span> <span data-ttu-id="7d47d-152">Zur Unterstützung der Datentypen `datetime2` und `datetimeoffset` wurden <xref:System.Data.DbType> die im Folgenden aufgeführten Enumerationswerte hinzugefügt:</span><span class="sxs-lookup"><span data-stu-id="7d47d-152">The following enumeration values have been added to <xref:System.Data.DbType> to support the `datetime2` and `datetimeoffset` data types:</span></span>  
  
- <span data-ttu-id="7d47d-153">DbType.DateTime2</span><span class="sxs-lookup"><span data-stu-id="7d47d-153">DbType.DateTime2</span></span>  
  
- <span data-ttu-id="7d47d-154">DbType.DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="7d47d-154">DbType.DateTimeOffset</span></span>  
  
 <span data-ttu-id="7d47d-155">Diese neuen Enumerationen ergänzen die Enumerationen `Date`, `Time` und `DateTime`, die bereits in früheren .NET Framework-Versionen vorhanden waren.</span><span class="sxs-lookup"><span data-stu-id="7d47d-155">These new enumerations supplement the `Date`, `Time`, and `DateTime` enumerations, which existed in earlier versions of the .NET Framework.</span></span>  
  
 <span data-ttu-id="7d47d-156">Der .NET Framework-Datenanbietertyp eines Parameterobjekts wird vom .NET Framework-Typ des Werts des Parameterobjekts oder vom `DbType` des Parameterobjekts hergeleitet.</span><span class="sxs-lookup"><span data-stu-id="7d47d-156">The .NET Framework data provider type of a parameter object is inferred from the .NET Framework type of the value of the parameter object, or from the `DbType` of the parameter object.</span></span> <span data-ttu-id="7d47d-157">Es wurden keine neuen <xref:System.Data.SqlTypes>-Datentypen eingeführt, um die neuen Datums- und Uhrzeitdatentypen zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="7d47d-157">No new <xref:System.Data.SqlTypes> data types have been introduced to support the new date and time data types.</span></span> <span data-ttu-id="7d47d-158">In der folgenden Tabelle werden die Zuordnungen zwischen den Datums- und Uhrzeitdatentypen von SQL Server 2008 und den CLR-Datentypen beschrieben.</span><span class="sxs-lookup"><span data-stu-id="7d47d-158">The following table describes the mappings between the SQL Server 2008 date and time data types and the CLR data types.</span></span>  
  
|<span data-ttu-id="7d47d-159">SQL Server-Datentyp</span><span class="sxs-lookup"><span data-stu-id="7d47d-159">SQL Server data type</span></span>|<span data-ttu-id="7d47d-160">.NET Framework-Typ</span><span class="sxs-lookup"><span data-stu-id="7d47d-160">.NET Framework type</span></span>|<span data-ttu-id="7d47d-161">System.Data.SqlDbType</span><span class="sxs-lookup"><span data-stu-id="7d47d-161">System.Data.SqlDbType</span></span>|<span data-ttu-id="7d47d-162">System.Data.DbType</span><span class="sxs-lookup"><span data-stu-id="7d47d-162">System.Data.DbType</span></span>|  
|--------------------------|-------------------------|---------------------------|------------------------|  
|<span data-ttu-id="7d47d-163">date</span><span class="sxs-lookup"><span data-stu-id="7d47d-163">date</span></span>|<span data-ttu-id="7d47d-164">System.DateTime</span><span class="sxs-lookup"><span data-stu-id="7d47d-164">System.DateTime</span></span>|<span data-ttu-id="7d47d-165">Date</span><span class="sxs-lookup"><span data-stu-id="7d47d-165">Date</span></span>|<span data-ttu-id="7d47d-166">Date</span><span class="sxs-lookup"><span data-stu-id="7d47d-166">Date</span></span>|  
|<span data-ttu-id="7d47d-167">time</span><span class="sxs-lookup"><span data-stu-id="7d47d-167">time</span></span>|<span data-ttu-id="7d47d-168">System.TimeSpan</span><span class="sxs-lookup"><span data-stu-id="7d47d-168">System.TimeSpan</span></span>|<span data-ttu-id="7d47d-169">Time</span><span class="sxs-lookup"><span data-stu-id="7d47d-169">Time</span></span>|<span data-ttu-id="7d47d-170">Time</span><span class="sxs-lookup"><span data-stu-id="7d47d-170">Time</span></span>|  
|<span data-ttu-id="7d47d-171">datetime2</span><span class="sxs-lookup"><span data-stu-id="7d47d-171">datetime2</span></span>|<span data-ttu-id="7d47d-172">System.DateTime</span><span class="sxs-lookup"><span data-stu-id="7d47d-172">System.DateTime</span></span>|<span data-ttu-id="7d47d-173">DateTime2</span><span class="sxs-lookup"><span data-stu-id="7d47d-173">DateTime2</span></span>|<span data-ttu-id="7d47d-174">DateTime2</span><span class="sxs-lookup"><span data-stu-id="7d47d-174">DateTime2</span></span>|  
|<span data-ttu-id="7d47d-175">datetimeoffset</span><span class="sxs-lookup"><span data-stu-id="7d47d-175">datetimeoffset</span></span>|<span data-ttu-id="7d47d-176">System.DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="7d47d-176">System.DateTimeOffset</span></span>|<span data-ttu-id="7d47d-177">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="7d47d-177">DateTimeOffset</span></span>|<span data-ttu-id="7d47d-178">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="7d47d-178">DateTimeOffset</span></span>|  
|<span data-ttu-id="7d47d-179">datetime</span><span class="sxs-lookup"><span data-stu-id="7d47d-179">datetime</span></span>|<span data-ttu-id="7d47d-180">System.DateTime</span><span class="sxs-lookup"><span data-stu-id="7d47d-180">System.DateTime</span></span>|<span data-ttu-id="7d47d-181">Datetime</span><span class="sxs-lookup"><span data-stu-id="7d47d-181">DateTime</span></span>|<span data-ttu-id="7d47d-182">Datetime</span><span class="sxs-lookup"><span data-stu-id="7d47d-182">DateTime</span></span>|  
|<span data-ttu-id="7d47d-183">smalldatetime</span><span class="sxs-lookup"><span data-stu-id="7d47d-183">smalldatetime</span></span>|<span data-ttu-id="7d47d-184">System.DateTime</span><span class="sxs-lookup"><span data-stu-id="7d47d-184">System.DateTime</span></span>|<span data-ttu-id="7d47d-185">Datetime</span><span class="sxs-lookup"><span data-stu-id="7d47d-185">DateTime</span></span>|<span data-ttu-id="7d47d-186">Datetime</span><span class="sxs-lookup"><span data-stu-id="7d47d-186">DateTime</span></span>|  
  
### <a name="sqlparameter-properties"></a><span data-ttu-id="7d47d-187">SqlParameter-Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="7d47d-187">SqlParameter Properties</span></span>  

 <span data-ttu-id="7d47d-188">In der folgenden Tabelle werden `SqlParameter`-Eigenschaften beschrieben, die für Datums- und Uhrzeitdatentypen relevant sind.</span><span class="sxs-lookup"><span data-stu-id="7d47d-188">The following table describes `SqlParameter` properties that are relevant to date and time data types.</span></span>  
  
|<span data-ttu-id="7d47d-189">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="7d47d-189">Property</span></span>|<span data-ttu-id="7d47d-190">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7d47d-190">Description</span></span>|  
|--------------|-----------------|  
|<xref:System.Data.SqlClient.SqlParameter.IsNullable%2A>|<span data-ttu-id="7d47d-191">Ruft ab oder legt fest, ob ein Wert NULL sein kann.</span><span class="sxs-lookup"><span data-stu-id="7d47d-191">Gets or sets whether a value is nullable.</span></span> <span data-ttu-id="7d47d-192">Wenn Sie den Parameterwert NULL an den Server senden, müssen Sie <xref:System.DBNull> anstelle von `null` (`Nothing` in Visual Basic) angeben.</span><span class="sxs-lookup"><span data-stu-id="7d47d-192">When you send a null parameter value to the server, you must specify <xref:System.DBNull>, rather than `null` (`Nothing` in Visual Basic).</span></span> <span data-ttu-id="7d47d-193">Weitere Informationen zu Daten Bank Nullen finden Sie unter [Behandeln von NULL-Werten](handling-null-values.md).</span><span class="sxs-lookup"><span data-stu-id="7d47d-193">For more information about database nulls, see [Handling Null Values](handling-null-values.md).</span></span>|  
|<xref:System.Data.SqlClient.SqlParameter.Precision%2A>|<span data-ttu-id="7d47d-194">Ruft die maximale Anzahl von Stellen ab, die verwendet werden, um den Wert darzustellen, oder legt diese fest.</span><span class="sxs-lookup"><span data-stu-id="7d47d-194">Gets or sets the maximum number of digits used to represent the value.</span></span> <span data-ttu-id="7d47d-195">Diese Einstellung wird für Datums -und Uhrzeitdatentypen ignoriert.</span><span class="sxs-lookup"><span data-stu-id="7d47d-195">This setting is ignored for date and time data types.</span></span>|  
|<xref:System.Data.SqlClient.SqlParameter.Scale%2A>|<span data-ttu-id="7d47d-196">Ruft die Anzahl der Dezimalstellen für die Auflösung des Uhrzeitteils des Werts für `Time`, `DateTime2` und `DateTimeOffset` ab, oder legt diese fest.</span><span class="sxs-lookup"><span data-stu-id="7d47d-196">Gets or sets the number of decimal places to which the time portion of the value is resolved for `Time`, `DateTime2`,and `DateTimeOffset`.</span></span> <span data-ttu-id="7d47d-197">Der Standardwert ist 0, was bedeutet, dass die tatsächliche Skala vom Wert hergeleitet und an den Server gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="7d47d-197">The default value is 0, which means that the actual scale is inferred from the value and sent to the server.</span></span>|  
|<xref:System.Data.SqlClient.SqlParameter.Size%2A>|<span data-ttu-id="7d47d-198">Wird für Datums -und Uhrzeitdatentypen ignoriert.</span><span class="sxs-lookup"><span data-stu-id="7d47d-198">Ignored for date and time data types.</span></span>|  
|<xref:System.Data.SqlClient.SqlParameter.Value%2A>|<span data-ttu-id="7d47d-199">Ruft den Parameterwert ab oder legt ihn fest.</span><span class="sxs-lookup"><span data-stu-id="7d47d-199">Gets or sets the parameter value.</span></span>|  
|<xref:System.Data.SqlClient.SqlParameter.SqlValue%2A>|<span data-ttu-id="7d47d-200">Ruft den Parameterwert ab oder legt ihn fest.</span><span class="sxs-lookup"><span data-stu-id="7d47d-200">Gets or sets the parameter value.</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="7d47d-201">Uhrzeitwerte, die kleiner als 0 oder größer oder gleich 24 Stunden sind, lösen eine <xref:System.ArgumentException> aus.</span><span class="sxs-lookup"><span data-stu-id="7d47d-201">Time values that are less than zero or greater than or equal to 24 hours will throw an <xref:System.ArgumentException>.</span></span>  
  
### <a name="creating-parameters"></a><span data-ttu-id="7d47d-202">Erstellen von Parametern</span><span class="sxs-lookup"><span data-stu-id="7d47d-202">Creating Parameters</span></span>  

 <span data-ttu-id="7d47d-203">Sie können ein <xref:System.Data.SqlClient.SqlParameter>-Objekt erstellen, indem Sie dessen Konstruktor verwenden, oder Sie fügen es zu einer <xref:System.Data.SqlClient.SqlCommand><xref:System.Data.SqlClient.SqlCommand.Parameters%2A>-Auflistung hinzu, indem Sie die `Add`-Methode der <xref:System.Data.SqlClient.SqlParameterCollection> aufrufen.</span><span class="sxs-lookup"><span data-stu-id="7d47d-203">You can create a <xref:System.Data.SqlClient.SqlParameter> object by using its constructor, or by adding it to a <xref:System.Data.SqlClient.SqlCommand><xref:System.Data.SqlClient.SqlCommand.Parameters%2A> collection by calling the `Add` method of the <xref:System.Data.SqlClient.SqlParameterCollection>.</span></span> <span data-ttu-id="7d47d-204">Die `Add`-Methode verwendet als Eingabe entweder Konstruktorargumente oder ein vorhandenes Parameterobjekt.</span><span class="sxs-lookup"><span data-stu-id="7d47d-204">The `Add` method will take as input either constructor arguments or an existing parameter object.</span></span>  
  
 <span data-ttu-id="7d47d-205">Die nächsten Abschnitte in diesem Thema enthalten Beispiele zum Angeben von Datums- und Uhrzeitparametern.</span><span class="sxs-lookup"><span data-stu-id="7d47d-205">The next sections in this topic provide examples of how to specify date and time parameters.</span></span> <span data-ttu-id="7d47d-206">Weitere Beispiele für das Arbeiten mit Parametern finden Sie unter [Konfigurieren von Parametern und Parameter Datentypen](../configuring-parameters-and-parameter-data-types.md) und [DataAdapter-Parametern](../dataadapter-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="7d47d-206">For additional examples of working with parameters, see [Configuring Parameters and Parameter Data Types](../configuring-parameters-and-parameter-data-types.md) and [DataAdapter Parameters](../dataadapter-parameters.md).</span></span>  
  
### <a name="date-example"></a><span data-ttu-id="7d47d-207">Datumsbeispiel</span><span class="sxs-lookup"><span data-stu-id="7d47d-207">Date Example</span></span>  

 <span data-ttu-id="7d47d-208">Das folgende Codefragment zeigt, wie ein `date`-Parameter angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="7d47d-208">The following code fragment demonstrates how to specify a `date` parameter.</span></span>  
  
```csharp  
SqlParameter parameter = new SqlParameter();  
parameter.ParameterName = "@Date";  
parameter.SqlDbType = SqlDbType.Date;  
parameter.Value = "2007/12/1";  
```  
  
```vb  
Dim parameter As New SqlParameter()  
parameter.ParameterName = "@Date"  
parameter.SqlDbType = SqlDbType.Date  
parameter.Value = "2007/12/1"  
```  
  
### <a name="time-example"></a><span data-ttu-id="7d47d-209">Uhrzeitbeispiel</span><span class="sxs-lookup"><span data-stu-id="7d47d-209">Time Example</span></span>  

 <span data-ttu-id="7d47d-210">Das folgende Codefragment zeigt, wie ein `time`-Parameter angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="7d47d-210">The following code fragment demonstrates how to specify a `time` parameter.</span></span>  
  
```csharp  
SqlParameter parameter = new SqlParameter();  
parameter.ParameterName = "@time";  
parameter.SqlDbType = SqlDbType.Time;  
parameter.Value = DateTime.Parse("23:59:59").TimeOfDay;  
```  
  
```vb  
Dim parameter As New SqlParameter()  
parameter.ParameterName = "@Time"  
parameter.SqlDbType = SqlDbType.Time  
parameter.Value = DateTime.Parse("23:59:59").TimeOfDay;  
```  
  
### <a name="datetime2-example"></a><span data-ttu-id="7d47d-211">Datetime2-Beispiel</span><span class="sxs-lookup"><span data-stu-id="7d47d-211">Datetime2 Example</span></span>  

 <span data-ttu-id="7d47d-212">Das folgende Codefragment zeigt, wie ein `datetime2`-Parameter mit Datums- und Uhrzeitteilen angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="7d47d-212">The following code fragment demonstrates how to specify a `datetime2` parameter with both the date and time parts.</span></span>  
  
```csharp  
SqlParameter parameter = new SqlParameter();  
parameter.ParameterName = "@Datetime2";  
parameter.SqlDbType = SqlDbType.DateTime2;  
parameter.Value = DateTime.Parse("1666-09-02 1:00:00");  
```  
  
```vb  
Dim parameter As New SqlParameter()  
parameter.ParameterName = "@Datetime2"  
parameter.SqlDbType = SqlDbType.DateTime2  
parameter.Value = DateTime.Parse("1666-09-02 1:00:00");  
```  
  
### <a name="datetimeoffset-example"></a><span data-ttu-id="7d47d-213">DateTimeOffSet-Beispiel</span><span class="sxs-lookup"><span data-stu-id="7d47d-213">DateTimeOffSet Example</span></span>  

 <span data-ttu-id="7d47d-214">Das folgende Codefragment zeigt, wie ein `DateTimeOffSet`-Parameter mit einem Datum, einer Uhrzeit und dem Zeitzonenoffset 0 angegeben werden kann.</span><span class="sxs-lookup"><span data-stu-id="7d47d-214">The following code fragment demonstrates how to specify a `DateTimeOffSet` parameter with a date, a time, and a time zone offset of 0.</span></span>  
  
```csharp  
SqlParameter parameter = new SqlParameter();  
parameter.ParameterName = "@DateTimeOffSet";  
parameter.SqlDbType = SqlDbType.DateTimeOffSet;  
parameter.Value = DateTimeOffset.Parse("1666-09-02 1:00:00+0");  
```  
  
```vb  
Dim parameter As New SqlParameter()  
parameter.ParameterName = "@DateTimeOffSet"  
parameter.SqlDbType = SqlDbType.DateTimeOffSet  
parameter.Value = DateTimeOffset.Parse("1666-09-02 1:00:00+0");  
```  
  
### <a name="addwithvalue"></a><span data-ttu-id="7d47d-215">AddWithValue</span><span class="sxs-lookup"><span data-stu-id="7d47d-215">AddWithValue</span></span>  

 <span data-ttu-id="7d47d-216">Sie können Parameter auch mithilfe der `AddWithValue`-Methode von <xref:System.Data.SqlClient.SqlCommand> angeben, wie im folgenden Codefragment gezeigt.</span><span class="sxs-lookup"><span data-stu-id="7d47d-216">You can also supply parameters by using the `AddWithValue` method of a <xref:System.Data.SqlClient.SqlCommand>, as shown in the following code fragment.</span></span> <span data-ttu-id="7d47d-217">Die `AddWithValue`-Methode ermöglicht jedoch nicht, <xref:System.Data.SqlClient.SqlParameter.DbType%2A> oder <xref:System.Data.SqlClient.SqlParameter.SqlDbType%2A> für den Parameter anzugeben.</span><span class="sxs-lookup"><span data-stu-id="7d47d-217">However, the `AddWithValue` method does not allow you to specify the <xref:System.Data.SqlClient.SqlParameter.DbType%2A> or <xref:System.Data.SqlClient.SqlParameter.SqlDbType%2A> for the parameter.</span></span>  
  
```csharp  
command.Parameters.AddWithValue(
    "@date", DateTimeOffset.Parse("16660902"));  
```  
  
```vb  
command.Parameters.AddWithValue( _  
    "@date", DateTimeOffset.Parse("16660902"))  
```  
  
 <span data-ttu-id="7d47d-218">Der `@date`-Parameter kann den Datentypen `date`, `datetime` oder `datetime2` auf dem Server zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="7d47d-218">The `@date` parameter could map to a `date`, `datetime`, or `datetime2` data type on the server.</span></span> <span data-ttu-id="7d47d-219">Wenn Sie mit den neuen `datetime`-Datentypen arbeiten, müssen Sie die <xref:System.Data.SqlDbType>-Eigenschaft des Parameters explizit auf den Datentyp der Instanz festlegen.</span><span class="sxs-lookup"><span data-stu-id="7d47d-219">When working with the new `datetime` data types, you must explicitly set the parameter's <xref:System.Data.SqlDbType> property to the data type of the instance.</span></span> <span data-ttu-id="7d47d-220">Das Verwenden von <xref:System.Data.SqlDbType.Variant> oder implizite Bereitstellen von Parameterwerten kann zu Problemen bei der Abwärtskompatibilität der Datentypen `datetime` und `smalldatetime` führen.</span><span class="sxs-lookup"><span data-stu-id="7d47d-220">Using <xref:System.Data.SqlDbType.Variant> or implicitly supplying parameter values can cause problems with backward compatibility with the `datetime` and `smalldatetime` data types.</span></span>  
  
 <span data-ttu-id="7d47d-221">Die folgende Tabelle zeigt, welche `SqlDbTypes` von welchen CLR-Typen abgeleitet werden:</span><span class="sxs-lookup"><span data-stu-id="7d47d-221">The following table shows which `SqlDbTypes` are inferred from which CLR types:</span></span>  
  
|<span data-ttu-id="7d47d-222">CLR-Typ</span><span class="sxs-lookup"><span data-stu-id="7d47d-222">CLR type</span></span>|<span data-ttu-id="7d47d-223">Abgeleiteter SqlDbType</span><span class="sxs-lookup"><span data-stu-id="7d47d-223">Inferred SqlDbType</span></span>|  
|--------------|------------------------|  
|<span data-ttu-id="7d47d-224">Datetime</span><span class="sxs-lookup"><span data-stu-id="7d47d-224">DateTime</span></span>|<span data-ttu-id="7d47d-225">SqlDbType.DateTime</span><span class="sxs-lookup"><span data-stu-id="7d47d-225">SqlDbType.DateTime</span></span>|  
|<span data-ttu-id="7d47d-226">TimeSpan</span><span class="sxs-lookup"><span data-stu-id="7d47d-226">TimeSpan</span></span>|<span data-ttu-id="7d47d-227">SqlDbType.Time</span><span class="sxs-lookup"><span data-stu-id="7d47d-227">SqlDbType.Time</span></span>|  
|<span data-ttu-id="7d47d-228">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="7d47d-228">DateTimeOffset</span></span>|<span data-ttu-id="7d47d-229">SqlDbType.DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="7d47d-229">SqlDbType.DateTimeOffset</span></span>|  
  
## <a name="retrieving-date-and-time-data"></a><span data-ttu-id="7d47d-230">Abrufen von Datums- und Uhrzeitdaten</span><span class="sxs-lookup"><span data-stu-id="7d47d-230">Retrieving Date and Time Data</span></span>  

 <span data-ttu-id="7d47d-231">In der folgenden Tabelle werden die Methoden zum Abrufen von Datums- und Uhrzeitwerten in SQL Server 2008 beschrieben.</span><span class="sxs-lookup"><span data-stu-id="7d47d-231">The following table describes methods that are used to retrieve SQL Server 2008 date and time values.</span></span>  
  
|<span data-ttu-id="7d47d-232">SqlClient-Methode</span><span class="sxs-lookup"><span data-stu-id="7d47d-232">SqlClient method</span></span>|<span data-ttu-id="7d47d-233">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7d47d-233">Description</span></span>|  
|----------------------|-----------------|  
|<xref:System.Data.SqlClient.SqlDataReader.GetDateTime%2A>|<span data-ttu-id="7d47d-234">Ruft den angegebenen Spaltenwert als <xref:System.DateTime>-Struktur ab.</span><span class="sxs-lookup"><span data-stu-id="7d47d-234">Retrieves the specified column value as a <xref:System.DateTime> structure.</span></span>|  
|<xref:System.Data.SqlClient.SqlDataReader.GetDateTimeOffset%2A>|<span data-ttu-id="7d47d-235">Ruft den angegebenen Spaltenwert als <xref:System.DateTimeOffset>-Struktur ab.</span><span class="sxs-lookup"><span data-stu-id="7d47d-235">Retrieves the specified column value as a <xref:System.DateTimeOffset> structure.</span></span>|  
|<xref:System.Data.SqlClient.SqlDataReader.GetProviderSpecificFieldType%2A>|<span data-ttu-id="7d47d-236">Gibt den Typ zurück, der der zugrunde liegende anbieterspezifische Typ des Felds ist.</span><span class="sxs-lookup"><span data-stu-id="7d47d-236">Returns the type that is the underlying provider-specific type for the field.</span></span> <span data-ttu-id="7d47d-237">Gibt für neue Datums- und Uhrzeittypen die gleichen Typen wie `GetFieldType` zurück.</span><span class="sxs-lookup"><span data-stu-id="7d47d-237">Returns the same types as `GetFieldType` for new date and time types.</span></span>|  
|<xref:System.Data.SqlClient.SqlDataReader.GetProviderSpecificValue%2A>|<span data-ttu-id="7d47d-238">Ruft den Wert der angegebenen Spalte ab.</span><span class="sxs-lookup"><span data-stu-id="7d47d-238">Retrieves the value of the specified column.</span></span> <span data-ttu-id="7d47d-239">Gibt für die neuen Datums- und Uhrzeittypen die gleichen Typen wie `GetValue` zurück.</span><span class="sxs-lookup"><span data-stu-id="7d47d-239">Returns the same types as `GetValue` for the new date and time types.</span></span>|  
|<xref:System.Data.SqlClient.SqlDataReader.GetProviderSpecificValues%2A>|<span data-ttu-id="7d47d-240">Ruft die Werte im angegebenen Array ab.</span><span class="sxs-lookup"><span data-stu-id="7d47d-240">Retrieves the values in the specified array.</span></span>|  
|<xref:System.Data.SqlClient.SqlDataReader.GetSqlString%2A>|<span data-ttu-id="7d47d-241">Ruft den Spaltenwert als <xref:System.Data.SqlTypes.SqlString> ab.</span><span class="sxs-lookup"><span data-stu-id="7d47d-241">Retrieves the column value as a <xref:System.Data.SqlTypes.SqlString>.</span></span> <span data-ttu-id="7d47d-242">Eine <xref:System.InvalidCastException> tritt auf, wenn die Daten nicht als `SqlString` ausgedrückt werden können.</span><span class="sxs-lookup"><span data-stu-id="7d47d-242">An <xref:System.InvalidCastException> occurs if the data cannot be expressed as a `SqlString`.</span></span>|  
|<xref:System.Data.SqlClient.SqlDataReader.GetSqlValue%2A>|<span data-ttu-id="7d47d-243">Ruft Spaltendaten als ihren standardmäßigen `SqlDbType` ab.</span><span class="sxs-lookup"><span data-stu-id="7d47d-243">Retrieves column data as its default `SqlDbType`.</span></span> <span data-ttu-id="7d47d-244">Gibt für die neuen Datums- und Uhrzeittypen die gleichen Typen wie `GetValue` zurück.</span><span class="sxs-lookup"><span data-stu-id="7d47d-244">Returns the same types as `GetValue` for the new date and time types.</span></span>|  
|<xref:System.Data.SqlClient.SqlDataReader.GetSqlValues%2A>|<span data-ttu-id="7d47d-245">Ruft die Werte im angegebenen Array ab.</span><span class="sxs-lookup"><span data-stu-id="7d47d-245">Retrieves the values in the specified array.</span></span>|  
|<xref:System.Data.SqlClient.SqlDataReader.GetString%2A>|<span data-ttu-id="7d47d-246">Ruft den Spaltenwert als Zeichenfolge ab, wenn „Type System Version“ auf SQL Server 2005 festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="7d47d-246">Retrieves the column value as a string if the Type System Version is set to SQL Server 2005.</span></span> <span data-ttu-id="7d47d-247">Eine <xref:System.InvalidCastException> tritt auf, wenn die Daten nicht als Zeichenfolge ausgedrückt werden können.</span><span class="sxs-lookup"><span data-stu-id="7d47d-247">An <xref:System.InvalidCastException> occurs if the data cannot be expressed as a string.</span></span>|  
|<xref:System.Data.SqlClient.SqlDataReader.GetTimeSpan%2A>|<span data-ttu-id="7d47d-248">Ruft den angegebenen Spaltenwert als <xref:System.TimeSpan>-Struktur ab.</span><span class="sxs-lookup"><span data-stu-id="7d47d-248">Retrieves the specified column value as a <xref:System.TimeSpan> structure.</span></span>|  
|<xref:System.Data.SqlClient.SqlDataReader.GetValue%2A>|<span data-ttu-id="7d47d-249">Ruft den angegebenen Spaltenwert als zugrunde liegenden CLR-Typ ab.</span><span class="sxs-lookup"><span data-stu-id="7d47d-249">Retrieves the specified column value as its underlying CLR type.</span></span>|  
|<xref:System.Data.SqlClient.SqlDataReader.GetValues%2A>|<span data-ttu-id="7d47d-250">Ruft Spaltenwerte in einem Array ab.</span><span class="sxs-lookup"><span data-stu-id="7d47d-250">Retrieves column values in an array.</span></span>|  
|<xref:System.Data.SqlClient.SqlDataReader.GetSchemaTable%2A>|<span data-ttu-id="7d47d-251">Gibt eine <xref:System.Data.DataTable> zurück, die die Metadaten des Resultsets beschreibt.</span><span class="sxs-lookup"><span data-stu-id="7d47d-251">Returns a <xref:System.Data.DataTable> that describes the metadata of the result set.</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="7d47d-252">Die neue Datums- und Uhrzeitwerte für `SqlDbTypes` werden nicht für Code unterstützt, der in SQL Server prozessintern ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="7d47d-252">The new date and time `SqlDbTypes` are not supported for code that is executing in-process in SQL Server.</span></span> <span data-ttu-id="7d47d-253">Eine Ausnahme wird ausgelöst, wenn einer dieser Typen an den Server übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="7d47d-253">An exception will be raised if one of these types is passed to the server.</span></span>  
  
## <a name="specifying-date-and-time-values-as-literals"></a><span data-ttu-id="7d47d-254">Angeben von Datums- und Uhrzeitwerten als Literale</span><span class="sxs-lookup"><span data-stu-id="7d47d-254">Specifying Date and Time Values as Literals</span></span>  

 <span data-ttu-id="7d47d-255">Sie können Datums- und Uhrzeitdatentypen angeben, indem Sie eine Vielzahl verschiedener Formate für Literalzeichenfolgen verwenden, die SQL Server dann zur Laufzeit auswertet und in interne Datums-/Uhrzeitstrukturen konvertiert.</span><span class="sxs-lookup"><span data-stu-id="7d47d-255">You can specify date and time data types by using a variety of different literal string formats, which SQL Server then evaluates at run time, converting them to internal date/time structures.</span></span> <span data-ttu-id="7d47d-256">SQL Server erkennt Datums- und Uhrzeitdaten, die in einfache Anführungszeichen (') eingeschlossen sind.</span><span class="sxs-lookup"><span data-stu-id="7d47d-256">SQL Server recognizes date and time data that is enclosed in single quotation marks (').</span></span> <span data-ttu-id="7d47d-257">Die folgenden Beispiele veranschaulichen einige Formate:</span><span class="sxs-lookup"><span data-stu-id="7d47d-257">The following examples demonstrate some formats:</span></span>  
  
- <span data-ttu-id="7d47d-258">Alphabetische Datumsformate wie `'October 15, 2006'`.</span><span class="sxs-lookup"><span data-stu-id="7d47d-258">Alphabetic date formats, such as `'October 15, 2006'`.</span></span>  
  
- <span data-ttu-id="7d47d-259">Numerische Datumsformate wie `'10/15/2006'`.</span><span class="sxs-lookup"><span data-stu-id="7d47d-259">Numeric date formats, such as `'10/15/2006'`.</span></span>  
  
- <span data-ttu-id="7d47d-260">Ungetrennte Zeichenfolgenformate wie `'20061015'`, die als 15. Oktober 2006 interpretiert werden, wenn Sie das ISO-Standarddatumsformat verwenden.</span><span class="sxs-lookup"><span data-stu-id="7d47d-260">Unseparated string formats, such as `'20061015'`, which would be interpreted as October 15, 2006 if you are using the ISO standard date format.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7d47d-261">Sie finden die vollständige Dokumentation aller Formate von Literalzeichenfolgen und anderer Features der Datums- und Uhrzeitdatentypen in der SQL Server-Onlinedokumentation.</span><span class="sxs-lookup"><span data-stu-id="7d47d-261">You can find complete documentation for all of the literal string formats and other features of the date and time data types in SQL Server Books Online.</span></span>  
  
 <span data-ttu-id="7d47d-262">Uhrzeitwerte, die kleiner als 0 oder größer oder gleich 24 Stunden sind, lösen eine <xref:System.ArgumentException> aus.</span><span class="sxs-lookup"><span data-stu-id="7d47d-262">Time values that are less than zero or greater than or equal to 24 hours will throw an <xref:System.ArgumentException>.</span></span>  
  
## <a name="resources-in-sql-server-books-online"></a><span data-ttu-id="7d47d-263">Ressourcen in der SQL Server-Onlinedokumentation</span><span class="sxs-lookup"><span data-stu-id="7d47d-263">Resources in SQL Server Books Online</span></span>  

 <span data-ttu-id="7d47d-264">Weitere Informationen zum Arbeiten mit Datums-und Uhrzeitwerten in SQL Server finden Sie in den folgenden Ressourcen in SQL Server-Onlinedokumentation.</span><span class="sxs-lookup"><span data-stu-id="7d47d-264">For more information about working with date and time values in SQL Server, see the following resources in SQL Server Books Online.</span></span>  
  
|<span data-ttu-id="7d47d-265">Thema</span><span class="sxs-lookup"><span data-stu-id="7d47d-265">Topic</span></span>|<span data-ttu-id="7d47d-266">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7d47d-266">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="7d47d-267">Datums- und Uhrzeitdatentypen und zugehörige Funktionen (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="7d47d-267">Date and Time Data Types and Functions (Transact-SQL)</span></span>](/sql/t-sql/functions/date-and-time-data-types-and-functions-transact-sql)|<span data-ttu-id="7d47d-268">Bietet eine Übersicht über alle Transact-SQL-Datentypen und -Funktionen zur Angabe des Datums und der Uhrzeit.</span><span class="sxs-lookup"><span data-stu-id="7d47d-268">Provides an overview of all Transact-SQL date and time data types and functions.</span></span>|  
|<span data-ttu-id="7d47d-269">[Verwenden von Datums- und Uhrzeitdaten](/previous-versions/sql/sql-server-2008/ms180878(v=sql.100))</span><span class="sxs-lookup"><span data-stu-id="7d47d-269">[Using Date and Time Data](/previous-versions/sql/sql-server-2008/ms180878(v=sql.100))</span></span>|<span data-ttu-id="7d47d-270">Stellt Informationen zu den Datentypen und Funktionen zur Angabe des Datums und der Uhrzeit sowie Beispiele für deren Verwendung bereit.</span><span class="sxs-lookup"><span data-stu-id="7d47d-270">Provides information about the date and time data types and functions, and examples of using them.</span></span>|  
|[<span data-ttu-id="7d47d-271">Datentypen (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="7d47d-271">Data Types (Transact-SQL)</span></span>](/sql/t-sql/data-types/data-types-transact-sql)|<span data-ttu-id="7d47d-272">Beschreibt System Datentypen in SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7d47d-272">Describes system data types in SQL Server.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7d47d-273">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7d47d-273">See also</span></span>

- [<span data-ttu-id="7d47d-274">SQL Server-Datentypzuordnungen</span><span class="sxs-lookup"><span data-stu-id="7d47d-274">SQL Server Data Type Mappings</span></span>](../sql-server-data-type-mappings.md)
- [<span data-ttu-id="7d47d-275">Konfigurieren von Parametern und Parameterdatentypen</span><span class="sxs-lookup"><span data-stu-id="7d47d-275">Configuring Parameters and Parameter Data Types</span></span>](../configuring-parameters-and-parameter-data-types.md)
- [<span data-ttu-id="7d47d-276">SQL Server-Datentypen und ADO.NET</span><span class="sxs-lookup"><span data-stu-id="7d47d-276">SQL Server Data Types and ADO.NET</span></span>](sql-server-data-types.md)
- [<span data-ttu-id="7d47d-277">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="7d47d-277">ADO.NET Overview</span></span>](../ado-net-overview.md)
