---
title: Anbieterstatistiken für SQL Server
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 429c9d09-92ac-46ec-829a-fbff0a9575a2
ms.openlocfilehash: d52c6bfdadf0a53ac4c5f62c37f1056c6702a82c
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2018
ms.locfileid: "46706423"
---
# <a name="provider-statistics-for-sql-server"></a><span data-ttu-id="08cff-102">Anbieterstatistiken für SQL Server</span><span class="sxs-lookup"><span data-stu-id="08cff-102">Provider Statistics for SQL Server</span></span>
<span data-ttu-id="08cff-103">Ab .NET Framework Version 2.0 unterstützt der .NET Framework-Datenanbieter für SQL Server Laufzeitstatistiken.</span><span class="sxs-lookup"><span data-stu-id="08cff-103">Starting with the .NET Framework version 2.0, the .NET Framework Data Provider for SQL Server supports run-time statistics.</span></span> <span data-ttu-id="08cff-104">Sie müssen die Statistik aktivieren, indem Sie nach dem Erstellen eines gültigen Verbindungsobjekts die <xref:System.Data.SqlClient.SqlConnection.StatisticsEnabled%2A>-Eigenschaft des <xref:System.Data.SqlClient.SqlConnection>-Objekts auf `True` festlegen.</span><span class="sxs-lookup"><span data-stu-id="08cff-104">You must enable statistics by setting the <xref:System.Data.SqlClient.SqlConnection.StatisticsEnabled%2A> property of the <xref:System.Data.SqlClient.SqlConnection> object to `True` after you have a valid connection object created.</span></span> <span data-ttu-id="08cff-105">Nach dem Aktivieren der Statistik können Sie sie als "Momentaufnahme" betrachten, indem Sie einen <xref:System.Collections.IDictionary>-Verweis über die <xref:System.Data.SqlClient.SqlConnection.RetrieveStatistics%2A>-Methode des <xref:System.Data.SqlClient.SqlConnection>-Objekts abrufen.</span><span class="sxs-lookup"><span data-stu-id="08cff-105">After statistics are enabled, you can review them as a "snapshot in time" by retrieving an <xref:System.Collections.IDictionary> reference via the <xref:System.Data.SqlClient.SqlConnection.RetrieveStatistics%2A> method of the <xref:System.Data.SqlClient.SqlConnection> object.</span></span> <span data-ttu-id="08cff-106">Blättern Sie durch die Liste wie durch Wörterbucheinträge mit Name-Wert-Paaren.</span><span class="sxs-lookup"><span data-stu-id="08cff-106">You enumerate through the list as a set of name/value pair dictionary entries.</span></span> <span data-ttu-id="08cff-107">Diese Name-Wert-Paare sind nicht sortiert.</span><span class="sxs-lookup"><span data-stu-id="08cff-107">These name/value pairs are unordered.</span></span> <span data-ttu-id="08cff-108">Sie können jederzeit die <xref:System.Data.SqlClient.SqlConnection.ResetStatistics%2A>-Methode des <xref:System.Data.SqlClient.SqlConnection>-Objekts aufrufen, um die Zähler zurückzusetzen.</span><span class="sxs-lookup"><span data-stu-id="08cff-108">At any time, you can call the <xref:System.Data.SqlClient.SqlConnection.ResetStatistics%2A> method of the <xref:System.Data.SqlClient.SqlConnection> object to reset the counters.</span></span> <span data-ttu-id="08cff-109">Wenn das Erfassen der Statistik nicht aktiviert wurde, wird keine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="08cff-109">If statistic gathering has not been enabled, an exception is not generated.</span></span> <span data-ttu-id="08cff-110">Wenn <xref:System.Data.SqlClient.SqlConnection.RetrieveStatistics%2A> aufgerufen wird, ohne vorher <xref:System.Data.SqlClient.SqlConnection.StatisticsEnabled%2A> aufzurufen, stellen die abgerufenen Werte die Anfangswerte für die einzelnen Einträge dar.</span><span class="sxs-lookup"><span data-stu-id="08cff-110">In addition, if <xref:System.Data.SqlClient.SqlConnection.RetrieveStatistics%2A> is called without <xref:System.Data.SqlClient.SqlConnection.StatisticsEnabled%2A> having been called first, the values retrieved are the initial values for each entry.</span></span> <span data-ttu-id="08cff-111">Wenn Sie die Statistik aktivieren, die Anwendung für eine gewisse Zeit ausführen und dann die Statistik wieder deaktivieren, entsprechen die abgerufenen Werte den Werten, die bis zu dem Zeitpunkt erfasst wurden, an dem die Statistik deaktiviert wurde.</span><span class="sxs-lookup"><span data-stu-id="08cff-111">If you enable statistics, run your application for a while, and then disable statistics, the values retrieved will reflect the values collected up to the point where statistics were disabled.</span></span> <span data-ttu-id="08cff-112">Alle statistischen Werte werden auf der Basis einzelner Verbindungen erfasst.</span><span class="sxs-lookup"><span data-stu-id="08cff-112">All statistical values gathered are on a per-connection basis.</span></span>  
  
## <a name="statistical-values-available"></a><span data-ttu-id="08cff-113">Verfügbare statistische Werte</span><span class="sxs-lookup"><span data-stu-id="08cff-113">Statistical Values Available</span></span>  
 <span data-ttu-id="08cff-114">Gegenwärtig sind vom Anbieter Microsoft SQL Server 18 verschiedene Elemente verfügbar.</span><span class="sxs-lookup"><span data-stu-id="08cff-114">Currently there are 18 different items available from the Microsoft SQL Server provider.</span></span> <span data-ttu-id="08cff-115">Die Anzahl der verfügbaren Elemente zugegriffen werden kann, über die **Anzahl** Eigenschaft der <xref:System.Collections.IDictionary> Schnittstellenreferenz zurückgegebenes <xref:System.Data.SqlClient.SqlConnection.RetrieveStatistics%2A>.</span><span class="sxs-lookup"><span data-stu-id="08cff-115">The number of items available can be accessed via the **Count** property of the <xref:System.Collections.IDictionary> interface reference returned by <xref:System.Data.SqlClient.SqlConnection.RetrieveStatistics%2A>.</span></span> <span data-ttu-id="08cff-116">Alle Zähler für Anbieterstatistiken verwenden die common Language Runtime <xref:System.Int64> Typ (**lange** in c# und Visual Basic), d.h. 64 Bits breit.</span><span class="sxs-lookup"><span data-stu-id="08cff-116">All of the counters for provider statistics use the common language runtime <xref:System.Int64> type (**long** in C# and Visual Basic), which is 64 bits wide.</span></span> <span data-ttu-id="08cff-117">Der maximale Wert, der die **int64** -Datentyp, gemäß der **int64. MaxValue** Feld, ((2^63)-1)).</span><span class="sxs-lookup"><span data-stu-id="08cff-117">The maximum value of the **int64** data type, as defined by the **int64.MaxValue** field, is ((2^63)-1)).</span></span> <span data-ttu-id="08cff-118">Wenn die Werte für die Zähler diesen Maximalwert erreichen, können sie nicht mehr als korrekt bezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="08cff-118">When the values for the counters reach this maximum value, they should no longer be considered accurate.</span></span> <span data-ttu-id="08cff-119">Dies bedeutet, dass **int64. MaxValue**-1((2^63)-2) ist tatsächlich der größte gültige Wert für alle Statistiken.</span><span class="sxs-lookup"><span data-stu-id="08cff-119">This means that **int64.MaxValue**-1((2^63)-2) is effectively the greatest valid value for any statistic.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="08cff-120">Für die zurückgegebene Anbieterstatistik wird ein Wörterbuch verwendet, da sich die Anzahl, die Namen und die Reihenfolge der zurückgegebenen Statistiken zukünftig ändern können.</span><span class="sxs-lookup"><span data-stu-id="08cff-120">A dictionary is used for returning provider statistics because the number, names and order of the returned statistics may change in the future.</span></span> <span data-ttu-id="08cff-121">Anwendungen sollten sich nicht darauf verlassen, dass ein bestimmter Wert in einem Wörterbuch gefunden wird, sondern stattdessen überprüfen, ob der Wert vorhanden ist, und entsprechend verzweigen.</span><span class="sxs-lookup"><span data-stu-id="08cff-121">Applications should not rely on a specific value being found in the dictionary, but should instead check whether the value is there and branch accordingly.</span></span>  
  
 <span data-ttu-id="08cff-122">In der folgenden Tabelle werden die aktuell verfügbaren statistischen Werte beschrieben.</span><span class="sxs-lookup"><span data-stu-id="08cff-122">The following table describes the current statistical values available.</span></span> <span data-ttu-id="08cff-123">Beachten Sie, dass die Schlüsselnamen für die einzelnen Werte für regionale Versionen von Microsoft .NET Framework nicht lokalisiert werden.</span><span class="sxs-lookup"><span data-stu-id="08cff-123">Note that the key names for the individual values are not localized across regional versions of the Microsoft .NET Framework.</span></span>  
  
|<span data-ttu-id="08cff-124">Schlüsselname</span><span class="sxs-lookup"><span data-stu-id="08cff-124">Key Name</span></span>|<span data-ttu-id="08cff-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="08cff-125">Description</span></span>|  
|--------------|-----------------|  
|`BuffersReceived`|<span data-ttu-id="08cff-126">Gibt die Anzahl der TDS-Pakete (Tabular Data Stream) zurück, die vom Anbieter von SQL Server empfangen wurden, seitdem die Anwendung den Anbieter verwendet und die Statistik aktiviert hat.</span><span class="sxs-lookup"><span data-stu-id="08cff-126">Returns the number of tabular data stream (TDS) packets received by the provider from SQL Server after the application has started using the provider and has enabled statistics.</span></span>|  
|`BuffersSent`|<span data-ttu-id="08cff-127">Gibt die Anzahl der TDS-Pakete zurück, die vom Anbieter an SQL Server gesendet wurden, seit die Statistik aktiviert wurde.</span><span class="sxs-lookup"><span data-stu-id="08cff-127">Returns the number of TDS packets sent to SQL Server by the provider after statistics have been enabled.</span></span> <span data-ttu-id="08cff-128">Für umfangreiche Befehle sind möglicherweise mehrere Puffer erforderlich.</span><span class="sxs-lookup"><span data-stu-id="08cff-128">Large commands can require multiple buffers.</span></span> <span data-ttu-id="08cff-129">Wenn z. B. ein großer Befehl an der Server gesendet wurde und 6 Pakete erfordert, wird `ServerRoundtrips` um 1 vergrößert und `BuffersSent` um 6 vergrößert.</span><span class="sxs-lookup"><span data-stu-id="08cff-129">For example, if a large command is sent to the server and it requires six packets, `ServerRoundtrips` is incremented by one and `BuffersSent` is incremented by six.</span></span>|  
|`BytesReceived`|<span data-ttu-id="08cff-130">Gibt die Anzahl der Bytes der Daten in TDS-Paketen zurück, die vom Anbieter von SQL Server empfangen wurden, seitdem die Anwendung den Anbieter verwendet und die Statistik aktiviert hat.</span><span class="sxs-lookup"><span data-stu-id="08cff-130">Returns the number of bytes of data in the TDS packets received by the provider from SQL Server once the application has started using the provider and has enabled statistics.</span></span>|  
|`BytesSent`|<span data-ttu-id="08cff-131">Gibt die Anzahl der Bytes der Daten zurück, die in TDS-Paketen an SQL Server gesendet wurden, seitdem die Anwendung den Anbieter verwendet und die Statistik aktiviert hat.</span><span class="sxs-lookup"><span data-stu-id="08cff-131">Returns the number of bytes of data sent to SQL Server in TDS packets after the application has started using the provider and has enabled statistics.</span></span>|  
|`ConnectionTime`|<span data-ttu-id="08cff-132">Die Zeitspanne (in Millisekunden), die die Verbindung nach dem Aktivieren der Statistik geöffnet war (die Gesamtverbindungszeit, wenn die Statistik vor dem Öffnen der Verbindung aktiviert wurde).</span><span class="sxs-lookup"><span data-stu-id="08cff-132">The amount of time (in milliseconds) that the connection has been opened after statistics have been enabled (total connection time if statistics were enabled before opening the connection).</span></span>|  
|`CursorOpens`|<span data-ttu-id="08cff-133">Gibt zurück, wie oft während der Verbindung ein Cursor geöffnet war, seitdem die Anwendung den Anbieter verwendet und die Statistik aktiviert hat.</span><span class="sxs-lookup"><span data-stu-id="08cff-133">Returns the number of times a cursor was open through the connection once the application has started using the provider and has enabled statistics.</span></span><br /><br /> <span data-ttu-id="08cff-134">Beachten Sie, dass schreibgeschützte Vorwärtsergebnisse, die von SELECT-Anweisungen zurückgegeben wurden, nicht als Cursor betrachtet werden und deshalb diesen Zähler nicht beeinflussen.</span><span class="sxs-lookup"><span data-stu-id="08cff-134">Note that read-only/forward-only results returned by SELECT statements are not considered cursors and thus do not affect this counter.</span></span>|  
|`ExecutionTime`|<span data-ttu-id="08cff-135">Gibt die Gesamtzeitspanne (in Millisekunden) zurück, die der Anbieter seit dem Aktivieren der Statistik mit der Verarbeitung verbracht hat, einschließlich der Zeit zum Warten auf Antworten vom Server und zum Ausführen von Code im Anbieter selbst.</span><span class="sxs-lookup"><span data-stu-id="08cff-135">Returns the cumulative amount of time (in milliseconds) that the provider has spent processing once statistics have been enabled, including the time spent waiting for replies from the server as well as the time spent executing code in the provider itself.</span></span><br /><br /> <span data-ttu-id="08cff-136">Folgende Klassen enthalten Zeiterfassungscode:</span><span class="sxs-lookup"><span data-stu-id="08cff-136">The classes that include timing code are:</span></span><br /><br /> <span data-ttu-id="08cff-137">SqlConnection</span><span class="sxs-lookup"><span data-stu-id="08cff-137">SqlConnection</span></span><br /><br /> <span data-ttu-id="08cff-138">SqlCommand</span><span class="sxs-lookup"><span data-stu-id="08cff-138">SqlCommand</span></span><br /><br /> <span data-ttu-id="08cff-139">SqlDataReader</span><span class="sxs-lookup"><span data-stu-id="08cff-139">SqlDataReader</span></span><br /><br /> <span data-ttu-id="08cff-140">SqlDataAdapter</span><span class="sxs-lookup"><span data-stu-id="08cff-140">SqlDataAdapter</span></span><br /><br /> <span data-ttu-id="08cff-141">SqlTransaction</span><span class="sxs-lookup"><span data-stu-id="08cff-141">SqlTransaction</span></span><br /><br /> <span data-ttu-id="08cff-142">SqlCommandBuilder</span><span class="sxs-lookup"><span data-stu-id="08cff-142">SqlCommandBuilder</span></span><br /><br /> <span data-ttu-id="08cff-143">Um leistungswichtige Member so klein wie möglich zu halten, erfolgt für die folgenden Member keine Zeiterfassung:</span><span class="sxs-lookup"><span data-stu-id="08cff-143">To keep performance-critical members as small as possible, the following members are not timed:</span></span><br /><br /> <span data-ttu-id="08cff-144">SqlDataReader</span><span class="sxs-lookup"><span data-stu-id="08cff-144">SqlDataReader</span></span><br /><br /> <span data-ttu-id="08cff-145">this[]-Operator (alle Überladungen)</span><span class="sxs-lookup"><span data-stu-id="08cff-145">this[] operator (all overloads)</span></span><br /><br /> <span data-ttu-id="08cff-146">GetBoolean</span><span class="sxs-lookup"><span data-stu-id="08cff-146">GetBoolean</span></span><br /><br /> <span data-ttu-id="08cff-147">GetChar</span><span class="sxs-lookup"><span data-stu-id="08cff-147">GetChar</span></span><br /><br /> <span data-ttu-id="08cff-148">GetDateTime</span><span class="sxs-lookup"><span data-stu-id="08cff-148">GetDateTime</span></span><br /><br /> <span data-ttu-id="08cff-149">GetDecimal</span><span class="sxs-lookup"><span data-stu-id="08cff-149">GetDecimal</span></span><br /><br /> <span data-ttu-id="08cff-150">GetDouble</span><span class="sxs-lookup"><span data-stu-id="08cff-150">GetDouble</span></span><br /><br /> <span data-ttu-id="08cff-151">GetFloat</span><span class="sxs-lookup"><span data-stu-id="08cff-151">GetFloat</span></span><br /><br /> <span data-ttu-id="08cff-152">GetGuid</span><span class="sxs-lookup"><span data-stu-id="08cff-152">GetGuid</span></span><br /><br /> <span data-ttu-id="08cff-153">GetInt16</span><span class="sxs-lookup"><span data-stu-id="08cff-153">GetInt16</span></span><br /><br /> <span data-ttu-id="08cff-154">GetInt32</span><span class="sxs-lookup"><span data-stu-id="08cff-154">GetInt32</span></span><br /><br /> <span data-ttu-id="08cff-155">GetInt64</span><span class="sxs-lookup"><span data-stu-id="08cff-155">GetInt64</span></span><br /><br /> <span data-ttu-id="08cff-156">GetName</span><span class="sxs-lookup"><span data-stu-id="08cff-156">GetName</span></span><br /><br /> <span data-ttu-id="08cff-157">GetOrdinal</span><span class="sxs-lookup"><span data-stu-id="08cff-157">GetOrdinal</span></span><br /><br /> <span data-ttu-id="08cff-158">GetSqlBinary</span><span class="sxs-lookup"><span data-stu-id="08cff-158">GetSqlBinary</span></span><br /><br /> <span data-ttu-id="08cff-159">GetSqlBoolean </span><span class="sxs-lookup"><span data-stu-id="08cff-159">GetSqlBoolean</span></span><br /><br /> <span data-ttu-id="08cff-160">GetSqlByte </span><span class="sxs-lookup"><span data-stu-id="08cff-160">GetSqlByte</span></span><br /><br /> <span data-ttu-id="08cff-161">GetSqlDateTime </span><span class="sxs-lookup"><span data-stu-id="08cff-161">GetSqlDateTime</span></span><br /><br /> <span data-ttu-id="08cff-162">GetSqlDecimal </span><span class="sxs-lookup"><span data-stu-id="08cff-162">GetSqlDecimal</span></span><br /><br /> <span data-ttu-id="08cff-163">GetSqlDouble </span><span class="sxs-lookup"><span data-stu-id="08cff-163">GetSqlDouble</span></span><br /><br /> <span data-ttu-id="08cff-164">GetSqlGuid </span><span class="sxs-lookup"><span data-stu-id="08cff-164">GetSqlGuid</span></span><br /><br /> <span data-ttu-id="08cff-165">GetSqlInt16 </span><span class="sxs-lookup"><span data-stu-id="08cff-165">GetSqlInt16</span></span><br /><br /> <span data-ttu-id="08cff-166">GetSqlInt32 </span><span class="sxs-lookup"><span data-stu-id="08cff-166">GetSqlInt32</span></span><br /><br /> <span data-ttu-id="08cff-167">GetSqlInt64 </span><span class="sxs-lookup"><span data-stu-id="08cff-167">GetSqlInt64</span></span><br /><br /> <span data-ttu-id="08cff-168">GetSqlMoney </span><span class="sxs-lookup"><span data-stu-id="08cff-168">GetSqlMoney</span></span><br /><br /> <span data-ttu-id="08cff-169">GetSqlSingle </span><span class="sxs-lookup"><span data-stu-id="08cff-169">GetSqlSingle</span></span><br /><br /> <span data-ttu-id="08cff-170">GetSqlString </span><span class="sxs-lookup"><span data-stu-id="08cff-170">GetSqlString</span></span><br /><br /> <span data-ttu-id="08cff-171">GetString</span><span class="sxs-lookup"><span data-stu-id="08cff-171">GetString</span></span><br /><br /> <span data-ttu-id="08cff-172">IsDBNull</span><span class="sxs-lookup"><span data-stu-id="08cff-172">IsDBNull</span></span>|  
|`IduCount`|<span data-ttu-id="08cff-173">Gibt die gesamte Anzahl der über die Verbindung ausgeführten INSERT-, DELETE- und UPDATE-Anweisungen zurück, seitdem die Anwendung den Anbieter verwendet und die Statistik aktiviert hat.</span><span class="sxs-lookup"><span data-stu-id="08cff-173">Returns the total number of INSERT, DELETE, and UPDATE statements executed through the connection once the application has started using the provider and has enabled statistics.</span></span>|  
|`IduRows`|<span data-ttu-id="08cff-174">Gibt die gesamte Anzahl der Zeilen zurück, die von über die Verbindung ausgeführten INSERT-, DELETE- und UPDATE-Anweisungen beeinflusst wurden, seitdem die Anwendung den Anbieter verwendet und die Statistik aktiviert hat.</span><span class="sxs-lookup"><span data-stu-id="08cff-174">Returns the total number of rows affected by INSERT, DELETE, and UPDATE statements executed through the connection once the application has started using the provider and has enabled statistics.</span></span>|  
|`NetworkServerTime`|<span data-ttu-id="08cff-175">Gibt die Gesamtzeitspanne (in Millisekunden) zurück, die der Anbieter zum Warten auf Antworten vom Server aufgewendet hat, seit die Anwendung den Anbieter verwendet und die Statistik aktiviert hat.</span><span class="sxs-lookup"><span data-stu-id="08cff-175">Returns the cumulative amount of time (in milliseconds) that the provider spent waiting for replies from the server once the application has started using the provider and has enabled statistics.</span></span>|  
|`PreparedExecs`|<span data-ttu-id="08cff-176">Gibt die Anzahl vorbereiteter Befehle zurück, die über die Verbindung ausgeführt wurden, seitdem die Anwendung den Anbieter verwendet und die Statistik aktiviert hat.</span><span class="sxs-lookup"><span data-stu-id="08cff-176">Returns the number of prepared commands executed through the connection once the application has started using the provider and has enabled statistics.</span></span>|  
|`Prepares`|<span data-ttu-id="08cff-177">Gibt die Anzahl der über die Verbindung vorbereiteten Anweisungen zurück, seitdem die Anwendung den Anbieter verwendet und die Statistik aktiviert hat.</span><span class="sxs-lookup"><span data-stu-id="08cff-177">Returns the number of statements prepared through the connection once the application has started using the provider and has enabled statistics.</span></span>|  
|`SelectCount`|<span data-ttu-id="08cff-178">Gibt die Anzahl von SELECT-Anweisungen zurück, die über die Verbindung ausgeführt wurden, seitdem die Anwendung den Anbieter verwendet und die Statistik aktiviert hat.</span><span class="sxs-lookup"><span data-stu-id="08cff-178">Returns the number of SELECT statements executed through the connection once the application has started using the provider and has enabled statistics.</span></span> <span data-ttu-id="08cff-179">Darin sind FETCH-Anweisungen zum Abrufen von Zeilen von Cursors enthalten, und die Anzahl von SELECT-Anweisungen wird aktualisiert, wenn das Ende eines <xref:System.Data.SqlClient.SqlDataReader> erreicht wird.</span><span class="sxs-lookup"><span data-stu-id="08cff-179">This includes FETCH statements to retrieve rows from cursors, and the count for SELECT statements is updated when the end of a <xref:System.Data.SqlClient.SqlDataReader> is reached.</span></span>|  
|`SelectRows`|<span data-ttu-id="08cff-180">Gibt die Anzahl der Zeilen zurück, die ausgewählt wurden, seitdem die Anwendung den Anbieter verwendet und die Statistik aktiviert hat.</span><span class="sxs-lookup"><span data-stu-id="08cff-180">Returns the number of rows selected once the application has started using the provider and has enabled statistics.</span></span> <span data-ttu-id="08cff-181">Dieser Zähler gibt alle Zeilen wieder, die durch SQL-Anweisungen erstellt wurden, darunter auch die, die vom Aufrufer nicht verarbeitet wurden.</span><span class="sxs-lookup"><span data-stu-id="08cff-181">This counter reflects all the rows generated by SQL statements, even those that were not actually consumed by the caller.</span></span> <span data-ttu-id="08cff-182">Das Schließen eines Datenreaders vor dem vollständigen Lesen des Ergebnisses beeinflusst z. B. die Zählung nicht.</span><span class="sxs-lookup"><span data-stu-id="08cff-182">For example, closing a data reader before reading the entire result set would not affect the count.</span></span> <span data-ttu-id="08cff-183">Dies gilt auch für Zeilen, die über FETCH-Anwendungen von Cursors abgerufen wurden.</span><span class="sxs-lookup"><span data-stu-id="08cff-183">This includes the rows retrieved from cursors through FETCH statements.</span></span>|  
|`ServerRoundtrips`|<span data-ttu-id="08cff-184">Gibt an, wie oft die Verbindung Befehle zum Server gesendet und eine Antwort erhalten hat, seitdem die Anwendung den Anbieter verwendet und die Statistik aktiviert hat.</span><span class="sxs-lookup"><span data-stu-id="08cff-184">Returns the number of times the connection sent commands to the server and got a reply back once the application has started using the provider and has enabled statistics.</span></span>|  
|`SumResultSets`|<span data-ttu-id="08cff-185">Gibt die Anzahl der verwendeten Resultsets zurück, seitdem die Anwendung den Anbieter verwendet und die Statistik aktiviert hat.</span><span class="sxs-lookup"><span data-stu-id="08cff-185">Returns the number of result sets that have been used once the application has started using the provider and has enabled statistics.</span></span> <span data-ttu-id="08cff-186">Dies umfasst z. B. Resultsets, die zum Client zurückgegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="08cff-186">For example this would include any result set returned to the client.</span></span> <span data-ttu-id="08cff-187">Für Cursors wird jede "fetch"- oder "block-fetch"-Operation als unabhängiges Resultset behandelt.</span><span class="sxs-lookup"><span data-stu-id="08cff-187">For cursors, each fetch or block-fetch operation is considered an independent result set.</span></span>|  
|`Transactions`|<span data-ttu-id="08cff-188">Gibt die Anzahl der gestarteten Benutzertransaktionen (einschließlich Rollbacks) zurück, seitdem die Anwendung den Anbieter verwendet und die Statistik aktiviert hat.</span><span class="sxs-lookup"><span data-stu-id="08cff-188">Returns the number of user transactions started once the application has started using the provider and has enabled statistics, including rollbacks.</span></span> <span data-ttu-id="08cff-189">Wenn eine Verbindung mit aktiviertem Autocommit ausgeführt wird, wird jeder Befehl als Transaktion behandelt.</span><span class="sxs-lookup"><span data-stu-id="08cff-189">If a connection is running with auto commit on, each command is considered a transaction.</span></span><br /><br /> <span data-ttu-id="08cff-190">Dieser Zähler erhöht die Transaktionszählung, sobald eine BEGIN TRAN-Anweisung ausgeführt wird, unabhängig davon, ob die Transaktion später gespeichert oder zurückgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="08cff-190">This counter increments the transaction count as soon as a BEGIN TRAN statement is executed, regardless of whether the transaction is committed or rolled back later.</span></span>|  
|`UnpreparedExecs`|<span data-ttu-id="08cff-191">Gibt die Anzahl der nicht vorbereiteten Anweisungen zurück, die über die Verbindung ausgeführt wurden, seitdem die Anwendung den Anbieter verwendet und die Statistik aktiviert hat.</span><span class="sxs-lookup"><span data-stu-id="08cff-191">Returns the number of unprepared statements executed through the connection once the application has started using the provider and has enabled statistics.</span></span>|  
  
### <a name="retrieving-a-value"></a><span data-ttu-id="08cff-192">Abrufen eines Werts</span><span class="sxs-lookup"><span data-stu-id="08cff-192">Retrieving a Value</span></span>  
 <span data-ttu-id="08cff-193">Die folgende Konsolenanwendung zeigt, wie die Statistik für eine Verbindung aktiviert, vier einzelne statistischen Werte abgerufen und diese in das Konsolenfenster geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="08cff-193">The following console application shows how to enable statistics on a connection, retrieve four individual statistic values, and write them out to the console window.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="08cff-194">Im folgenden Beispiel wird das Beispiel **AdventureWorks** Datenbank in SQL Server enthalten.</span><span class="sxs-lookup"><span data-stu-id="08cff-194">The following example uses the sample **AdventureWorks** database included with SQL Server.</span></span> <span data-ttu-id="08cff-195">Bei der im Beispielcode bereitgestellten Verbindungszeichenfolge wird angenommen, dass die Datenbank auf dem lokalen Computer installiert und verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="08cff-195">The connection string provided in the sample code assumes the database is installed and available on the local computer.</span></span> <span data-ttu-id="08cff-196">Ändern Sie die Verbindungszeichenfolge entsprechend der Umgebung.</span><span class="sxs-lookup"><span data-stu-id="08cff-196">Modify the connection string as necessary for your environment.</span></span>  
  
```vb  
Option Strict On  
  
Imports System  
Imports System.Collections  
Imports System.Data  
Imports System.Data.SqlClient  
  
Module Module1  
  
  Sub Main()  
    Dim connectionString As String = GetConnectionString()  
  
    Using awConnection As New SqlConnection(connectionString)  
      ' StatisticsEnabled is False by default.  
      ' It must be set to True to start the   
      ' statistic collection process.  
      awConnection.StatisticsEnabled = True  
  
      Dim productSQL As String = "SELECT * FROM Production.Product"  
      Dim productAdapter As _  
          New SqlDataAdapter(productSQL, awConnection)  
  
      Dim awDataSet As New DataSet()  
  
      awConnection.Open()  
  
      productAdapter.Fill(awDataSet, "ProductTable")  
  
      ' Retrieve the current statistics as  
      ' a collection of values at this point  
      ' and time.  
      Dim currentStatistics As IDictionary = _  
          awConnection.RetrieveStatistics()  
  
      Console.WriteLine("Total Counters: " & _  
          currentStatistics.Count.ToString())  
      Console.WriteLine()  
  
      ' Retrieve a few individual values  
      ' related to the previous command.  
      Dim bytesReceived As Long = _  
          CLng(currentStatistics.Item("BytesReceived"))  
      Dim bytesSent As Long = _  
          CLng(currentStatistics.Item("BytesSent"))  
      Dim selectCount As Long = _  
          CLng(currentStatistics.Item("SelectCount"))  
      Dim selectRows As Long = _  
          CLng(currentStatistics.Item("SelectRows"))  
  
      Console.WriteLine("BytesReceived: " & bytesReceived.ToString())  
      Console.WriteLine("BytesSent: " & bytesSent.ToString())  
      Console.WriteLine("SelectCount: " & selectCount.ToString())  
      Console.WriteLine("SelectRows: " & selectRows.ToString())  
  
      Console.WriteLine()  
      Console.WriteLine("Press any key to continue")  
      Console.ReadLine()  
    End Using  
  
  End Sub  
  
  Function GetConnectionString() As String  
    ' To avoid storing the connection string in your code,  
    ' you can retrive it from a configuration file.  
    Return "Data Source=localhost;Integrated Security=SSPI;" & _  
      "Initial Catalog=AdventureWorks"  
  End Function  
End Module  
```  
  
```csharp  
using System;  
using System.Collections;  
using System.Collections.Generic;  
using System.Data;  
using System.Data.SqlClient;  
  
namespace CS_Stats_Console_GetValue  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      string connectionString = GetConnectionString();  
  
      using (SqlConnection awConnection =   
        new SqlConnection(connectionString))  
      {  
        // StatisticsEnabled is False by default.  
        // It must be set to True to start the   
        // statistic collection process.  
        awConnection.StatisticsEnabled = true;  
  
        string productSQL = "SELECT * FROM Production.Product";  
        SqlDataAdapter productAdapter =   
          new SqlDataAdapter(productSQL, awConnection);  
  
        DataSet awDataSet = new DataSet();  
  
        awConnection.Open();  
  
        productAdapter.Fill(awDataSet, "ProductTable");  
        // Retrieve the current statistics as  
        // a collection of values at this point  
        // and time.  
        IDictionary currentStatistics =  
          awConnection.RetrieveStatistics();  
  
        Console.WriteLine("Total Counters: " +  
          currentStatistics.Count.ToString());  
        Console.WriteLine();  
  
        // Retrieve a few individual values  
        // related to the previous command.  
        long bytesReceived =  
            (long) currentStatistics["BytesReceived"];  
        long bytesSent =  
            (long) currentStatistics["BytesSent"];  
        long selectCount =  
            (long) currentStatistics["SelectCount"];  
        long selectRows =  
            (long) currentStatistics["SelectRows"];  
  
        Console.WriteLine("BytesReceived: " +  
            bytesReceived.ToString());  
        Console.WriteLine("BytesSent: " +  
            bytesSent.ToString());  
        Console.WriteLine("SelectCount: " +  
            selectCount.ToString());  
        Console.WriteLine("SelectRows: " +  
            selectRows.ToString());  
  
        Console.WriteLine();  
        Console.WriteLine("Press any key to continue");  
        Console.ReadLine();  
      }  
  
    }  
    private static string GetConnectionString()  
    {  
      // To avoid storing the connection string in your code,  
      // you can retrive it from a configuration file.  
      return "Data Source=localhost;Integrated Security=SSPI;" +   
        "Initial Catalog=AdventureWorks";  
    }  
  }  
}  
```  
  
### <a name="retrieving-all-values"></a><span data-ttu-id="08cff-197">Abrufen aller Werte</span><span class="sxs-lookup"><span data-stu-id="08cff-197">Retrieving All Values</span></span>  
 <span data-ttu-id="08cff-198">Die folgende Konsolenanwendung zeigt, wie die Statistik für eine Verbindung aktiviert, vier einzelne statistischen Werte abgerufen und diese in das Konsolenfenster geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="08cff-198">The following console application shows how to enable statistics on a connection, retrieve all available statistic values using the enumerator, and write them to the console window.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="08cff-199">Im folgenden Beispiel wird das Beispiel **AdventureWorks** Datenbank in SQL Server enthalten.</span><span class="sxs-lookup"><span data-stu-id="08cff-199">The following example uses the sample **AdventureWorks** database included with SQL Server.</span></span> <span data-ttu-id="08cff-200">Bei der im Beispielcode bereitgestellten Verbindungszeichenfolge wird angenommen, dass die Datenbank auf dem lokalen Computer installiert und verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="08cff-200">The connection string provided in the sample code assumes the database is installed and available on the local computer.</span></span> <span data-ttu-id="08cff-201">Ändern Sie die Verbindungszeichenfolge entsprechend der Umgebung.</span><span class="sxs-lookup"><span data-stu-id="08cff-201">Modify the connection string as necessary for your environment.</span></span>  
  
```vb  
Option Strict On  
  
Imports System  
Imports System.Collections  
Imports System.Data  
Imports System.Data.SqlClient  
  
Module Module1  
  Sub Main()  
    Dim connectionString As String = GetConnectionString()  
  
    Using awConnection As New SqlConnection(connectionString)  
      ' StatisticsEnabled is False by default.  
      ' It must be set to True to start the   
      ' statistic collection process.  
      awConnection.StatisticsEnabled = True  
  
      Dim productSQL As String = "SELECT * FROM Production.Product"  
      Dim productAdapter As _  
          New SqlDataAdapter(productSQL, awConnection)  
  
      Dim awDataSet As New DataSet()  
  
      awConnection.Open()  
  
      productAdapter.Fill(awDataSet, "ProductTable")  
  
      ' Retrieve the current statistics as  
      ' a collection of values at this point  
      ' and time.  
      Dim currentStatistics As IDictionary = _  
          awConnection.RetrieveStatistics()  
  
      Console.WriteLine("Total Counters: " & _  
          currentStatistics.Count.ToString())  
      Console.WriteLine()  
  
      Console.WriteLine("Key Name and Value")  
  
      ' Note the entries are unsorted.  
      For Each entry As DictionaryEntry In currentStatistics  
        Console.WriteLine(entry.Key.ToString() & _  
            ": " & entry.Value.ToString())  
      Next  
  
      Console.WriteLine()  
      Console.WriteLine("Press any key to continue")  
      Console.ReadLine()  
    End Using  
  
  End Sub  
  
  Function GetConnectionString() As String  
    ' To avoid storing the connection string in your code,  
    ' you can retrive it from a configuration file.  
    Return "Data Source=localhost;Integrated Security=SSPI;" & _  
      "Initial Catalog=AdventureWorks"  
  End Function  
End Module  
```  
  
```csharp  
using System;  
using System.Collections;  
using System.Collections.Generic;  
using System.Text;  
using System.Data;  
using System.Data.SqlClient;  
  
namespace CS_Stats_Console_GetAll  
{  
  class Program  
  {  
    static void Main(string[] args)  
    {  
      string connectionString = GetConnectionString();  
  
      using (SqlConnection awConnection =   
        new SqlConnection(connectionString))  
      {  
        // StatisticsEnabled is False by default.  
        // It must be set to True to start the   
        // statistic collection process.  
        awConnection.StatisticsEnabled = true;  
  
        string productSQL = "SELECT * FROM Production.Product";  
        SqlDataAdapter productAdapter =  
            new SqlDataAdapter(productSQL, awConnection);  
  
        DataSet awDataSet = new DataSet();  
  
        awConnection.Open();  
  
        productAdapter.Fill(awDataSet, "ProductTable");  
  
        // Retrieve the current statistics as  
        // a collection of values at this point  
        // and time.  
        IDictionary currentStatistics =  
            awConnection.RetrieveStatistics();  
  
        Console.WriteLine("Total Counters: " +  
            currentStatistics.Count.ToString());  
        Console.WriteLine();  
  
        Console.WriteLine("Key Name and Value");  
  
        // Note the entries are unsorted.  
        foreach (DictionaryEntry entry in currentStatistics)  
        {  
          Console.WriteLine(entry.Key.ToString() +  
              ": " + entry.Value.ToString());  
        }  
  
        Console.WriteLine();  
        Console.WriteLine("Press any key to continue");  
        Console.ReadLine();  
      }  
  
    }  
    private static string GetConnectionString()  
    {  
      // To avoid storing the connection string in your code,  
      // you can retrive it from a configuration file.  
      return "Data Source=localhost;Integrated Security=SSPI;" +   
        "Initial Catalog=AdventureWorks";  
    }  
  }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="08cff-202">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="08cff-202">See Also</span></span>  
 [<span data-ttu-id="08cff-203">SQL Server und ADO.NET</span><span class="sxs-lookup"><span data-stu-id="08cff-203">SQL Server and ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/index.md)  
 [<span data-ttu-id="08cff-204">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="08cff-204">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
