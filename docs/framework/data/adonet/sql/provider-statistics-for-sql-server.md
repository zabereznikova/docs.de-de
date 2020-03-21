---
title: Anbieterstatistiken für SQL Server
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 429c9d09-92ac-46ec-829a-fbff0a9575a2
ms.openlocfilehash: 5e37a04ff731a99664d636e0d4175f99214c2646
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174510"
---
# <a name="provider-statistics-for-sql-server"></a><span data-ttu-id="ed44a-102">Anbieterstatistiken für SQL Server</span><span class="sxs-lookup"><span data-stu-id="ed44a-102">Provider Statistics for SQL Server</span></span>
<span data-ttu-id="ed44a-103">Ab .NET Framework Version 2.0 unterstützt der .NET Framework-Datenanbieter für SQL Server Laufzeitstatistiken.</span><span class="sxs-lookup"><span data-stu-id="ed44a-103">Starting with the .NET Framework version 2.0, the .NET Framework Data Provider for SQL Server supports run-time statistics.</span></span> <span data-ttu-id="ed44a-104">Sie müssen Statistiken aktivieren, indem Sie die Eigenschaft <xref:System.Data.SqlClient.SqlConnection.StatisticsEnabled%2A> des <xref:System.Data.SqlClient.SqlConnection>-Objekts auf `True` festlegen, nachdem Sie ein gültiges Verbindungsobjekt erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="ed44a-104">You must enable statistics by setting the <xref:System.Data.SqlClient.SqlConnection.StatisticsEnabled%2A> property of the <xref:System.Data.SqlClient.SqlConnection> object to `True` after you have a valid connection object created.</span></span> <span data-ttu-id="ed44a-105">Nachdem Statistiken aktiviert wurden, können Sie sie als Momentaufnahme überprüfen, indem Sie einen <xref:System.Collections.IDictionary>-Verweis über die <xref:System.Data.SqlClient.SqlConnection.RetrieveStatistics%2A>-Methode des <xref:System.Data.SqlClient.SqlConnection>-Objekts abrufen.</span><span class="sxs-lookup"><span data-stu-id="ed44a-105">After statistics are enabled, you can review them as a "snapshot in time" by retrieving an <xref:System.Collections.IDictionary> reference via the <xref:System.Data.SqlClient.SqlConnection.RetrieveStatistics%2A> method of the <xref:System.Data.SqlClient.SqlConnection> object.</span></span> <span data-ttu-id="ed44a-106">Sie zählen die Liste als eine Reihe von Wörterbucheinträgen in Form von Name-Wert-Paaren durch.</span><span class="sxs-lookup"><span data-stu-id="ed44a-106">You enumerate through the list as a set of name/value pair dictionary entries.</span></span> <span data-ttu-id="ed44a-107">Diese Name-Wert-Paare sind nicht geordnet.</span><span class="sxs-lookup"><span data-stu-id="ed44a-107">These name/value pairs are unordered.</span></span> <span data-ttu-id="ed44a-108">Sie können jederzeit die <xref:System.Data.SqlClient.SqlConnection.ResetStatistics%2A>-Methode des <xref:System.Data.SqlClient.SqlConnection>-Objekts zum Zurücksetzen der Zähler aufrufen.</span><span class="sxs-lookup"><span data-stu-id="ed44a-108">At any time, you can call the <xref:System.Data.SqlClient.SqlConnection.ResetStatistics%2A> method of the <xref:System.Data.SqlClient.SqlConnection> object to reset the counters.</span></span> <span data-ttu-id="ed44a-109">Wenn die Statistikerfassung nicht aktiviert ist, wird keine Ausnahme generiert.</span><span class="sxs-lookup"><span data-stu-id="ed44a-109">If statistic gathering has not been enabled, an exception is not generated.</span></span> <span data-ttu-id="ed44a-110">Wenn außerdem <xref:System.Data.SqlClient.SqlConnection.RetrieveStatistics%2A> aufgerufen wird, ohne dass zuvor <xref:System.Data.SqlClient.SqlConnection.StatisticsEnabled%2A> aufgerufen wurde, sind die abgerufenen Werte die Anfangswerte jedes Eintrags.</span><span class="sxs-lookup"><span data-stu-id="ed44a-110">In addition, if <xref:System.Data.SqlClient.SqlConnection.RetrieveStatistics%2A> is called without <xref:System.Data.SqlClient.SqlConnection.StatisticsEnabled%2A> having been called first, the values retrieved are the initial values for each entry.</span></span> <span data-ttu-id="ed44a-111">Wenn Sie Statistiken aktivieren, Ihre Anwendung eine Weile ausführen und Statistiken dann deaktivieren, spiegeln die abgerufenen Werte die Werte wider, die bis zu dem Punkt erfasst wurden, an dem Statistiken deaktiviert wurden.</span><span class="sxs-lookup"><span data-stu-id="ed44a-111">If you enable statistics, run your application for a while, and then disable statistics, the values retrieved will reflect the values collected up to the point where statistics were disabled.</span></span> <span data-ttu-id="ed44a-112">Alle erfassten statistischen Werte gelten verbindungsbezogen.</span><span class="sxs-lookup"><span data-stu-id="ed44a-112">All statistical values gathered are on a per-connection basis.</span></span>  
  
## <a name="statistical-values-available"></a><span data-ttu-id="ed44a-113">Verfügbare statistische Werte</span><span class="sxs-lookup"><span data-stu-id="ed44a-113">Statistical Values Available</span></span>  
 <span data-ttu-id="ed44a-114">Gegenwärtig bietet der Microsoft SQL Server-Anbieter 18 Elemente.</span><span class="sxs-lookup"><span data-stu-id="ed44a-114">Currently there are 18 different items available from the Microsoft SQL Server provider.</span></span> <span data-ttu-id="ed44a-115">Die Anzahl der verfügbaren Elemente kann über die **Count**-Eigenschaft des <xref:System.Collections.IDictionary>-Schnittstellenverweises abgerufen werden, die von <xref:System.Data.SqlClient.SqlConnection.RetrieveStatistics%2A> zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="ed44a-115">The number of items available can be accessed via the **Count** property of the <xref:System.Collections.IDictionary> interface reference returned by <xref:System.Data.SqlClient.SqlConnection.RetrieveStatistics%2A>.</span></span> <span data-ttu-id="ed44a-116">Alle Zähler für Anbieterstatistiken verwenden den <xref:System.Int64>-CLR-Typ (Common Language Runtime) (**long** in C# und Visual Basic), der 64 Bit lang ist.</span><span class="sxs-lookup"><span data-stu-id="ed44a-116">All of the counters for provider statistics use the common language runtime <xref:System.Int64> type (**long** in C# and Visual Basic), which is 64 bits wide.</span></span> <span data-ttu-id="ed44a-117">Der maximale Wert des im Feld **int64.MaxValue** definierten **int64**-Datentyps beträgt ((2^63)-1)).</span><span class="sxs-lookup"><span data-stu-id="ed44a-117">The maximum value of the **int64** data type, as defined by the **int64.MaxValue** field, is ((2^63)-1)).</span></span> <span data-ttu-id="ed44a-118">Wenn die Werte für die Zähler diesen Maximalwert erreichen, dürfen sie nicht mehr als genau betrachtet werden.</span><span class="sxs-lookup"><span data-stu-id="ed44a-118">When the values for the counters reach this maximum value, they should no longer be considered accurate.</span></span> <span data-ttu-id="ed44a-119">Das bedeutet, dass **int64.MaxValue**-1((2^63)-2) tatsächlich der größte gültige Wert für alle Statistiken ist.</span><span class="sxs-lookup"><span data-stu-id="ed44a-119">This means that **int64.MaxValue**-1((2^63)-2) is effectively the greatest valid value for any statistic.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ed44a-120">Ein Wörterbuch wird für die Rückgabe von Anbieterstatistiken verwendet, da sich Anzahl, Namen und Reihenfolge der zurückgegebenen Statistiken in Zukunft ändern können.</span><span class="sxs-lookup"><span data-stu-id="ed44a-120">A dictionary is used for returning provider statistics because the number, names and order of the returned statistics may change in the future.</span></span> <span data-ttu-id="ed44a-121">Anwendungen dürfen sich nicht darauf verlassen, dass ein bestimmter Wert im Wörterbuch zu finden ist, sondern müssen prüfen, ob der Wert vorhanden ist und entsprechend verzweigen.</span><span class="sxs-lookup"><span data-stu-id="ed44a-121">Applications should not rely on a specific value being found in the dictionary, but should instead check whether the value is there and branch accordingly.</span></span>  
  
 <span data-ttu-id="ed44a-122">In der folgenden Tabelle werden die aktuell verfügbaren statistischen Werte beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ed44a-122">The following table describes the current statistical values available.</span></span> <span data-ttu-id="ed44a-123">Beachten Sie, dass die Schlüsselnamen für die einzelnen Werte für regionale Versionen von Microsoft .NET Framework nicht lokalisiert werden.</span><span class="sxs-lookup"><span data-stu-id="ed44a-123">Note that the key names for the individual values are not localized across regional versions of the Microsoft .NET Framework.</span></span>  
  
|<span data-ttu-id="ed44a-124">Schlüsselname</span><span class="sxs-lookup"><span data-stu-id="ed44a-124">Key Name</span></span>|<span data-ttu-id="ed44a-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ed44a-125">Description</span></span>|  
|--------------|-----------------|  
|`BuffersReceived`|<span data-ttu-id="ed44a-126">Gibt die Anzahl der TDS-Pakete (Tabular Data Stream) zurück, die der Anbieter von SQL Server empfangen hat, nachdem die Anwendung die Nutzung des Anbieters gestartet und Statistiken aktiviert hat.</span><span class="sxs-lookup"><span data-stu-id="ed44a-126">Returns the number of tabular data stream (TDS) packets received by the provider from SQL Server after the application has started using the provider and has enabled statistics.</span></span>|  
|`BuffersSent`|<span data-ttu-id="ed44a-127">Gibt die Anzahl der TDS-Pakete zurück, die vom Anbieter nach Aktivieren von Statistiken an SQL Server gesendet wurden.</span><span class="sxs-lookup"><span data-stu-id="ed44a-127">Returns the number of TDS packets sent to SQL Server by the provider after statistics have been enabled.</span></span> <span data-ttu-id="ed44a-128">Für große Befehle sind möglicherweise mehrere Puffer erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ed44a-128">Large commands can require multiple buffers.</span></span> <span data-ttu-id="ed44a-129">Wenn z. B. ein großer Befehl an den Server gesendet wird und er sechs Pakete erfordert, wird `ServerRoundtrips` um 1 und `BuffersSent` um 6 erhöht.</span><span class="sxs-lookup"><span data-stu-id="ed44a-129">For example, if a large command is sent to the server and it requires six packets, `ServerRoundtrips` is incremented by one and `BuffersSent` is incremented by six.</span></span>|  
|`BytesReceived`|<span data-ttu-id="ed44a-130">Gibt die Anzahl der Datenbytes in den TDS-Paketen zurück, die der Anbieter von SQL Server empfangen hat, nachdem die Anwendung mit der Nutzung des Anbieters begonnen und Statistiken aktiviert hat.</span><span class="sxs-lookup"><span data-stu-id="ed44a-130">Returns the number of bytes of data in the TDS packets received by the provider from SQL Server once the application has started using the provider and has enabled statistics.</span></span>|  
|`BytesSent`|<span data-ttu-id="ed44a-131">Gibt die Anzahl der Datenbytes zurück, die in TDS-Paketen an SQL Server gesendet wurden, nachdem die Anwendung mit der Nutzung des Anbieters begonnen und Statistiken aktiviert hat.</span><span class="sxs-lookup"><span data-stu-id="ed44a-131">Returns the number of bytes of data sent to SQL Server in TDS packets after the application has started using the provider and has enabled statistics.</span></span>|  
|`ConnectionTime`|<span data-ttu-id="ed44a-132">Die Zeitspanne (in Millisekunden), für die die Verbindung nach dem Aktivieren der Statistik geöffnet war (die Gesamtverbindungszeit, wenn die Statistik vor dem Öffnen der Verbindung aktiviert wurde).</span><span class="sxs-lookup"><span data-stu-id="ed44a-132">The amount of time (in milliseconds) that the connection has been opened after statistics have been enabled (total connection time if statistics were enabled before opening the connection).</span></span>|  
|`CursorOpens`|<span data-ttu-id="ed44a-133">Gibt zurück, wie oft ein Cursor über die Verbindung geöffnet wurde, nachdem die Anwendung mit der Nutzung des Anbieters begonnen und Statistiken aktiviert hat.</span><span class="sxs-lookup"><span data-stu-id="ed44a-133">Returns the number of times a cursor was open through the connection once the application has started using the provider and has enabled statistics.</span></span><br /><br /> <span data-ttu-id="ed44a-134">Beachten Sie, dass schreibgeschützte/vorwärtsgerichtete Ergebnisse, die von SELECT-Anweisungen zurückgegeben werden, nicht als Cursor betrachtet werden und daher diesen Zähler nicht beeinflussen.</span><span class="sxs-lookup"><span data-stu-id="ed44a-134">Note that read-only/forward-only results returned by SELECT statements are not considered cursors and thus do not affect this counter.</span></span>|  
|`ExecutionTime`|<span data-ttu-id="ed44a-135">Gibt die Gesamtzeitspanne (in Millisekunden) zurück, die der Anbieter seit dem Aktivieren der Statistik mit der Verarbeitung verbracht hat, einschließlich der Zeit zum Warten auf Antworten vom Server und zum Ausführen von Code im Anbieter selbst.</span><span class="sxs-lookup"><span data-stu-id="ed44a-135">Returns the cumulative amount of time (in milliseconds) that the provider has spent processing once statistics have been enabled, including the time spent waiting for replies from the server as well as the time spent executing code in the provider itself.</span></span><br /><br /> <span data-ttu-id="ed44a-136">Die Klassen, die Zeitsteuerungscode enthalten, lauten:</span><span class="sxs-lookup"><span data-stu-id="ed44a-136">The classes that include timing code are:</span></span><br /><br /> <span data-ttu-id="ed44a-137">SqlConnection</span><span class="sxs-lookup"><span data-stu-id="ed44a-137">SqlConnection</span></span><br /><br /> <span data-ttu-id="ed44a-138">SqlCommand</span><span class="sxs-lookup"><span data-stu-id="ed44a-138">SqlCommand</span></span><br /><br /> <span data-ttu-id="ed44a-139">SqlDataReader</span><span class="sxs-lookup"><span data-stu-id="ed44a-139">SqlDataReader</span></span><br /><br /> <span data-ttu-id="ed44a-140">SqlDataAdapter</span><span class="sxs-lookup"><span data-stu-id="ed44a-140">SqlDataAdapter</span></span><br /><br /> <span data-ttu-id="ed44a-141">SqlTransaction</span><span class="sxs-lookup"><span data-stu-id="ed44a-141">SqlTransaction</span></span><br /><br /> <span data-ttu-id="ed44a-142">SqlCommandBuilder</span><span class="sxs-lookup"><span data-stu-id="ed44a-142">SqlCommandBuilder</span></span><br /><br /> <span data-ttu-id="ed44a-143">Um leistungskritische Member so klein wie möglich zu halten, werden die folgenden Member nicht zeitgesteuert:</span><span class="sxs-lookup"><span data-stu-id="ed44a-143">To keep performance-critical members as small as possible, the following members are not timed:</span></span><br /><br /> <span data-ttu-id="ed44a-144">SqlDataReader</span><span class="sxs-lookup"><span data-stu-id="ed44a-144">SqlDataReader</span></span><br /><br /> <span data-ttu-id="ed44a-145">this []-Operator (alle Überladungen)</span><span class="sxs-lookup"><span data-stu-id="ed44a-145">this[] operator (all overloads)</span></span><br /><br /> <span data-ttu-id="ed44a-146">GetBoolean</span><span class="sxs-lookup"><span data-stu-id="ed44a-146">GetBoolean</span></span><br /><br /> <span data-ttu-id="ed44a-147">GetChar</span><span class="sxs-lookup"><span data-stu-id="ed44a-147">GetChar</span></span><br /><br /> <span data-ttu-id="ed44a-148">GetDateTime</span><span class="sxs-lookup"><span data-stu-id="ed44a-148">GetDateTime</span></span><br /><br /> <span data-ttu-id="ed44a-149">GetDecimal</span><span class="sxs-lookup"><span data-stu-id="ed44a-149">GetDecimal</span></span><br /><br /> <span data-ttu-id="ed44a-150">GetDouble</span><span class="sxs-lookup"><span data-stu-id="ed44a-150">GetDouble</span></span><br /><br /> <span data-ttu-id="ed44a-151">GetFloat</span><span class="sxs-lookup"><span data-stu-id="ed44a-151">GetFloat</span></span><br /><br /> <span data-ttu-id="ed44a-152">GetGuid</span><span class="sxs-lookup"><span data-stu-id="ed44a-152">GetGuid</span></span><br /><br /> <span data-ttu-id="ed44a-153">GetInt16</span><span class="sxs-lookup"><span data-stu-id="ed44a-153">GetInt16</span></span><br /><br /> <span data-ttu-id="ed44a-154">GetInt32</span><span class="sxs-lookup"><span data-stu-id="ed44a-154">GetInt32</span></span><br /><br /> <span data-ttu-id="ed44a-155">GetInt64</span><span class="sxs-lookup"><span data-stu-id="ed44a-155">GetInt64</span></span><br /><br /> <span data-ttu-id="ed44a-156">GetName</span><span class="sxs-lookup"><span data-stu-id="ed44a-156">GetName</span></span><br /><br /> <span data-ttu-id="ed44a-157">GetOrdinal</span><span class="sxs-lookup"><span data-stu-id="ed44a-157">GetOrdinal</span></span><br /><br /> <span data-ttu-id="ed44a-158">GetSqlBinary</span><span class="sxs-lookup"><span data-stu-id="ed44a-158">GetSqlBinary</span></span><br /><br /> <span data-ttu-id="ed44a-159">GetSqlBoolean</span><span class="sxs-lookup"><span data-stu-id="ed44a-159">GetSqlBoolean</span></span><br /><br /> <span data-ttu-id="ed44a-160">GetSqlByte</span><span class="sxs-lookup"><span data-stu-id="ed44a-160">GetSqlByte</span></span><br /><br /> <span data-ttu-id="ed44a-161">GetSqlDateTime</span><span class="sxs-lookup"><span data-stu-id="ed44a-161">GetSqlDateTime</span></span><br /><br /> <span data-ttu-id="ed44a-162">GetSqlDecimal</span><span class="sxs-lookup"><span data-stu-id="ed44a-162">GetSqlDecimal</span></span><br /><br /> <span data-ttu-id="ed44a-163">GetSqlDouble</span><span class="sxs-lookup"><span data-stu-id="ed44a-163">GetSqlDouble</span></span><br /><br /> <span data-ttu-id="ed44a-164">GetSqlGuid</span><span class="sxs-lookup"><span data-stu-id="ed44a-164">GetSqlGuid</span></span><br /><br /> <span data-ttu-id="ed44a-165">GetSqlInt16</span><span class="sxs-lookup"><span data-stu-id="ed44a-165">GetSqlInt16</span></span><br /><br /> <span data-ttu-id="ed44a-166">GetSqlInt32</span><span class="sxs-lookup"><span data-stu-id="ed44a-166">GetSqlInt32</span></span><br /><br /> <span data-ttu-id="ed44a-167">GetSqlInt64</span><span class="sxs-lookup"><span data-stu-id="ed44a-167">GetSqlInt64</span></span><br /><br /> <span data-ttu-id="ed44a-168">GetSqlMoney</span><span class="sxs-lookup"><span data-stu-id="ed44a-168">GetSqlMoney</span></span><br /><br /> <span data-ttu-id="ed44a-169">GetSqlSingle</span><span class="sxs-lookup"><span data-stu-id="ed44a-169">GetSqlSingle</span></span><br /><br /> <span data-ttu-id="ed44a-170">GetSqlString</span><span class="sxs-lookup"><span data-stu-id="ed44a-170">GetSqlString</span></span><br /><br /> <span data-ttu-id="ed44a-171">GetString</span><span class="sxs-lookup"><span data-stu-id="ed44a-171">GetString</span></span><br /><br /> <span data-ttu-id="ed44a-172">IsDBNull</span><span class="sxs-lookup"><span data-stu-id="ed44a-172">IsDBNull</span></span>|  
|`IduCount`|<span data-ttu-id="ed44a-173">Gibt die Gesamtanzahl der über die Verbindung ausgeführten INSERT-, DELETE- und UPDATE-Anweisungen zurück, sobald die Anwendung mit der Nutzung des Anbieters begonnen und Statistiken aktiviert hat.</span><span class="sxs-lookup"><span data-stu-id="ed44a-173">Returns the total number of INSERT, DELETE, and UPDATE statements executed through the connection once the application has started using the provider and has enabled statistics.</span></span>|  
|`IduRows`|<span data-ttu-id="ed44a-174">Gibt die Gesamtanzahl der Zeilen zurück, die von INSERT-, DELETE- und UPDATE-Anweisungen betroffen sind, die über die Verbindung ausgeführt wurden, sobald die Anwendung mit der Verwendung des Anbieters begonnen und Statistiken aktiviert hat.</span><span class="sxs-lookup"><span data-stu-id="ed44a-174">Returns the total number of rows affected by INSERT, DELETE, and UPDATE statements executed through the connection once the application has started using the provider and has enabled statistics.</span></span>|  
|`NetworkServerTime`|<span data-ttu-id="ed44a-175">Gibt die kumulative Zeitspanne (in Millisekunden) zurück, die der Anbieter zum Warten auf Antworten vom Server verwendet hat, seitdem die Anwendung den Anbieter verwendet und die Statistik aktiviert hat.</span><span class="sxs-lookup"><span data-stu-id="ed44a-175">Returns the cumulative amount of time (in milliseconds) that the provider spent waiting for replies from the server once the application has started using the provider and has enabled statistics.</span></span>|  
|`PreparedExecs`|<span data-ttu-id="ed44a-176">Gibt die Anzahl vorbereiteter Befehle zurück, die über die Verbindung ausgeführt wurden, sobald die Anwendung mit der Nutzung des Anbieters begonnen und Statistiken aktiviert hat.</span><span class="sxs-lookup"><span data-stu-id="ed44a-176">Returns the number of prepared commands executed through the connection once the application has started using the provider and has enabled statistics.</span></span>|  
|`Prepares`|<span data-ttu-id="ed44a-177">Gibt die Anzahl der über die Verbindung vorbereiteten Anweisungen zurück, sobald die Anwendung mit der Nutzung des Anbieters begonnen und Statistiken aktiviert hat.</span><span class="sxs-lookup"><span data-stu-id="ed44a-177">Returns the number of statements prepared through the connection once the application has started using the provider and has enabled statistics.</span></span>|  
|`SelectCount`|<span data-ttu-id="ed44a-178">Gibt die Anzahl der über die Verbindung ausgeführten SELECT-Anweisungen zurück, nachdem die Anwendung mit der Nutzung des Anbieters begonnen und Statistiken aktiviert hat.</span><span class="sxs-lookup"><span data-stu-id="ed44a-178">Returns the number of SELECT statements executed through the connection once the application has started using the provider and has enabled statistics.</span></span> <span data-ttu-id="ed44a-179">Dazu gehören FETCH-Anweisungen zum Abrufen von Zeilen aus Cursorn. Der Zähler für SELECT-Anweisungen wird aktualisiert, wenn das Ende von <xref:System.Data.SqlClient.SqlDataReader> erreicht ist.</span><span class="sxs-lookup"><span data-stu-id="ed44a-179">This includes FETCH statements to retrieve rows from cursors, and the count for SELECT statements is updated when the end of a <xref:System.Data.SqlClient.SqlDataReader> is reached.</span></span>|  
|`SelectRows`|<span data-ttu-id="ed44a-180">Gibt die Anzahl der ausgewählten Zeilen zurück, nachdem die Anwendung mit der Nutzung des Anbieters begonnen und Statistiken aktiviert hat.</span><span class="sxs-lookup"><span data-stu-id="ed44a-180">Returns the number of rows selected once the application has started using the provider and has enabled statistics.</span></span> <span data-ttu-id="ed44a-181">Dieser Zähler spiegelt alle von SQL-Anweisungen erstellten Zeilen wider, auch solche, die vom Aufrufer nicht wirklich genutzt wurden.</span><span class="sxs-lookup"><span data-stu-id="ed44a-181">This counter reflects all the rows generated by SQL statements, even those that were not actually consumed by the caller.</span></span> <span data-ttu-id="ed44a-182">Beispielsweise würde das Schließen eines Datenlesers vor dem Lesen des gesamten Resultsets die Anzahl nicht beeinflussen.</span><span class="sxs-lookup"><span data-stu-id="ed44a-182">For example, closing a data reader before reading the entire result set would not affect the count.</span></span> <span data-ttu-id="ed44a-183">Dies schließt die Zeilen ein, die von den Cursorn über FETCH-Anweisungen abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="ed44a-183">This includes the rows retrieved from cursors through FETCH statements.</span></span>|  
|`ServerRoundtrips`|<span data-ttu-id="ed44a-184">Gibt zurück, wie oft die Verbindung Befehle an den Server gesendet und eine Antwort erhalten hat, sobald die Anwendung mit der Nutzung des Anbieters begonnen und Statistiken aktiviert hat.</span><span class="sxs-lookup"><span data-stu-id="ed44a-184">Returns the number of times the connection sent commands to the server and got a reply back once the application has started using the provider and has enabled statistics.</span></span>|  
|`SumResultSets`|<span data-ttu-id="ed44a-185">Gibt die Anzahl der Resultsets zurück, die verwendet wurden, nachdem die Anwendung mit der Nutzung des Anbieters begonnen und Statistiken aktiviert hat.</span><span class="sxs-lookup"><span data-stu-id="ed44a-185">Returns the number of result sets that have been used once the application has started using the provider and has enabled statistics.</span></span> <span data-ttu-id="ed44a-186">Dies würde z. B. jedes an den Client zurückgegebene Resultset umfassen.</span><span class="sxs-lookup"><span data-stu-id="ed44a-186">For example this would include any result set returned to the client.</span></span> <span data-ttu-id="ed44a-187">Bei Cursorn wird jeder Abruf oder Blockabruf als unabhängiges Resultset betrachtet.</span><span class="sxs-lookup"><span data-stu-id="ed44a-187">For cursors, each fetch or block-fetch operation is considered an independent result set.</span></span>|  
|`Transactions`|<span data-ttu-id="ed44a-188">Gibt die Anzahl der Benutzertransaktionen zurück, die gestartet wurden, nachdem die Anwendung mit der Nutzung des Anbieters begonnen und Statistiken, einschließlich Rollbacks, aktiviert hat.</span><span class="sxs-lookup"><span data-stu-id="ed44a-188">Returns the number of user transactions started once the application has started using the provider and has enabled statistics, including rollbacks.</span></span> <span data-ttu-id="ed44a-189">Wenn eine Verbindung mit aktiviertem Autocommit ausgeführt wird, gilt jeder Befehl als Transaktion.</span><span class="sxs-lookup"><span data-stu-id="ed44a-189">If a connection is running with auto commit on, each command is considered a transaction.</span></span><br /><br /> <span data-ttu-id="ed44a-190">Dieser Zähler erhöht den Transaktionszähler, sobald eine BEGIN TRAN-Anweisung ausgeführt wird, unabhängig davon, ob die Transaktion committet oder später rückgängig gemacht wird.</span><span class="sxs-lookup"><span data-stu-id="ed44a-190">This counter increments the transaction count as soon as a BEGIN TRAN statement is executed, regardless of whether the transaction is committed or rolled back later.</span></span>|  
|`UnpreparedExecs`|<span data-ttu-id="ed44a-191">Gibt die Anzahl der über die Verbindung ausgeführten unvorbereiteten Anweisungen zurück, nachdem die Anwendung mit der Nutzung des Anbieters begonnen und Statistiken aktiviert hat.</span><span class="sxs-lookup"><span data-stu-id="ed44a-191">Returns the number of unprepared statements executed through the connection once the application has started using the provider and has enabled statistics.</span></span>|  
  
### <a name="retrieving-a-value"></a><span data-ttu-id="ed44a-192">Abrufen eines Werts</span><span class="sxs-lookup"><span data-stu-id="ed44a-192">Retrieving a Value</span></span>  
 <span data-ttu-id="ed44a-193">Die folgende Konsolenanwendung zeigt, wie Statistiken über eine Verbindung aktiviert, vier einzelne Statistikwerte abgerufen und in das Konsolenfenster geschrieben werden können.</span><span class="sxs-lookup"><span data-stu-id="ed44a-193">The following console application shows how to enable statistics on a connection, retrieve four individual statistic values, and write them out to the console window.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ed44a-194">Im folgenden Beispiel wird die in SQL Server enthaltene **AdventureWorks**-Beispieldatenbank verwendet.</span><span class="sxs-lookup"><span data-stu-id="ed44a-194">The following example uses the sample **AdventureWorks** database included with SQL Server.</span></span> <span data-ttu-id="ed44a-195">In der im Beispielcode bereitgestellten Verbindungszeichenfolge wird davon ausgegangen, dass die Datenbank auf dem lokalen Computer installiert und verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="ed44a-195">The connection string provided in the sample code assumes the database is installed and available on the local computer.</span></span> <span data-ttu-id="ed44a-196">Ändern Sie die Verbindungszeichenfolge nach Bedarf für Ihre Umgebung.</span><span class="sxs-lookup"><span data-stu-id="ed44a-196">Modify the connection string as necessary for your environment.</span></span>  
  
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
    ' you can retrieve it from a configuration file.  
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
      // you can retrieve it from a configuration file.  
      return "Data Source=localhost;Integrated Security=SSPI;" +
        "Initial Catalog=AdventureWorks";  
    }  
  }  
}  
```  
  
### <a name="retrieving-all-values"></a><span data-ttu-id="ed44a-197">Abrufen aller Werte</span><span class="sxs-lookup"><span data-stu-id="ed44a-197">Retrieving All Values</span></span>  
 <span data-ttu-id="ed44a-198">Die folgende Konsolenanwendung zeigt, wie Statistiken über eine Verbindung aktiviert, alle verfügbaren Statistikwerte mit dem Enumerator abgerufen und in das Konsolenfenster geschrieben werden können.</span><span class="sxs-lookup"><span data-stu-id="ed44a-198">The following console application shows how to enable statistics on a connection, retrieve all available statistic values using the enumerator, and write them to the console window.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ed44a-199">Im folgenden Beispiel wird die in SQL Server enthaltene **AdventureWorks**-Beispieldatenbank verwendet.</span><span class="sxs-lookup"><span data-stu-id="ed44a-199">The following example uses the sample **AdventureWorks** database included with SQL Server.</span></span> <span data-ttu-id="ed44a-200">In der im Beispielcode bereitgestellten Verbindungszeichenfolge wird davon ausgegangen, dass die Datenbank auf dem lokalen Computer installiert und verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="ed44a-200">The connection string provided in the sample code assumes the database is installed and available on the local computer.</span></span> <span data-ttu-id="ed44a-201">Ändern Sie die Verbindungszeichenfolge nach Bedarf für Ihre Umgebung.</span><span class="sxs-lookup"><span data-stu-id="ed44a-201">Modify the connection string as necessary for your environment.</span></span>  
  
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
    ' you can retrieve it from a configuration file.  
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
      // you can retrieve it from a configuration file.  
      return "Data Source=localhost;Integrated Security=SSPI;" +
        "Initial Catalog=AdventureWorks";  
    }  
  }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="ed44a-202">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ed44a-202">See also</span></span>

- [<span data-ttu-id="ed44a-203">SQL Server und ADO.NET</span><span class="sxs-lookup"><span data-stu-id="ed44a-203">SQL Server and ADO.NET</span></span>](index.md)
- [<span data-ttu-id="ed44a-204">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="ed44a-204">ADO.NET Overview</span></span>](../ado-net-overview.md)
