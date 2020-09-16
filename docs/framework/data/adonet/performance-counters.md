---
title: Leistungsindikatoren
description: Verwenden Sie ADO.NET-Leistungsindikatoren zum Überwachen des Anwendungs Status und der zugehörigen Verbindungs Ressourcen mithilfe von Windows Performance Monitor oder Programm gesteuert.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0b121b71-78f8-4ae2-9aa1-0b2e15778e57
ms.openlocfilehash: 4c1da6041b2343565bdaeb53e586c893bd85c922
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90557904"
---
# <a name="performance-counters-in-adonet"></a><span data-ttu-id="1393e-103">Leistungsindikatoren in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="1393e-103">Performance Counters in ADO.NET</span></span>
<span data-ttu-id="1393e-104">Neu in ADO.NET 2.0 ist die erweiterte Unterstützung für Leistungsindikatoren. Dazu gehört auch die Unterstützung für <xref:System.Data.SqlClient> und <xref:System.Data.OracleClient>.</span><span class="sxs-lookup"><span data-stu-id="1393e-104">ADO.NET 2.0 introduced expanded support for performance counters that includes support for both <xref:System.Data.SqlClient> and <xref:System.Data.OracleClient>.</span></span> <span data-ttu-id="1393e-105">Die in früheren ADO.NET-Versionen verfügbaren <xref:System.Data.SqlClient>-Leistungsindikatoren wurden durch neue Leistungsindikatoren ersetzt, die in diesem Thema beschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="1393e-105">The <xref:System.Data.SqlClient> performance counters available in previous versions of ADO.NET have been deprecated and replaced with the new performance counters discussed in this topic.</span></span> <span data-ttu-id="1393e-106">Mit den ADO.NET-Leistungsindikatoren können Sie den Status Ihrer Anwendung und die Verbindungsressourcen überwachen, die die Anwendung verwendet.</span><span class="sxs-lookup"><span data-stu-id="1393e-106">You can use ADO.NET performance counters to monitor the status of your application and the connection resources that it uses.</span></span> <span data-ttu-id="1393e-107">Für die Überwachung der Leistungsindikatoren kann der Windows-Leistungsmonitor verwendet werden, und die <xref:System.Diagnostics.PerformanceCounter>-Klasse im <xref:System.Diagnostics>-Namespace ermöglicht den programmgesteuerten Zugriff auf diese Indikatoren.</span><span class="sxs-lookup"><span data-stu-id="1393e-107">Performance counters can be monitored by using Windows Performance Monitor or can be accessed programmatically using the <xref:System.Diagnostics.PerformanceCounter> class in the <xref:System.Diagnostics> namespace.</span></span>  
  
## <a name="available-performance-counters"></a><span data-ttu-id="1393e-108">Verfügbare Leistungsindikatoren</span><span class="sxs-lookup"><span data-stu-id="1393e-108">Available Performance Counters</span></span>  
 <span data-ttu-id="1393e-109">Derzeit sind für <xref:System.Data.SqlClient> und <xref:System.Data.OracleClient> 14 verschiedene Leistungsindikatoren verfügbar (siehe Beschreibung in der folgenden Tabelle).</span><span class="sxs-lookup"><span data-stu-id="1393e-109">Currently there are 14 different performance counters available for <xref:System.Data.SqlClient> and <xref:System.Data.OracleClient> as described in the following table.</span></span> <span data-ttu-id="1393e-110">Die Indikatoren behalten in allen lokalisierten Microsoft .NET Framework-Versionen ihre englischen Namen.</span><span class="sxs-lookup"><span data-stu-id="1393e-110">Note that the names for the individual counters are not localized across regional versions of the Microsoft .NET Framework.</span></span>  
  
|<span data-ttu-id="1393e-111">Leistungsindikator</span><span class="sxs-lookup"><span data-stu-id="1393e-111">Performance counter</span></span>|<span data-ttu-id="1393e-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="1393e-112">Description</span></span>|  
|-------------------------|-----------------|  
|`HardConnectsPerSecond`|<span data-ttu-id="1393e-113">Anzahl der Verbindungen, die pro Sekunde mit einem Datenbankserver hergestellt wurden</span><span class="sxs-lookup"><span data-stu-id="1393e-113">The number of connections per second that are being made to a database server.</span></span>|  
|`HardDisconnectsPerSecond`|<span data-ttu-id="1393e-114">Anzahl der Verbindungen mit einem Datenbankserver, die pro Sekunde getrennt wurden</span><span class="sxs-lookup"><span data-stu-id="1393e-114">The number of disconnects per second that are being made to a database server.</span></span>|  
|`NumberOfActiveConnectionPoolGroups`|<span data-ttu-id="1393e-115">Anzahl der eindeutigen Verbindungspoolgruppen, die aktiv sind.</span><span class="sxs-lookup"><span data-stu-id="1393e-115">The number of unique connection pool groups that are active.</span></span> <span data-ttu-id="1393e-116">Dieser Indikator wird von der Anzahl der eindeutigen Verbindungszeichenfolgen gesteuert, die in der Anwendungsdomäne (AppDomain) gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="1393e-116">This counter is controlled by the number of unique connection strings that are found in the AppDomain.</span></span>|  
|`NumberOfActiveConnectionPools`|<span data-ttu-id="1393e-117">Gesamtzahl der Verbindungspools</span><span class="sxs-lookup"><span data-stu-id="1393e-117">The total number of connection pools.</span></span>|  
|`NumberOfActiveConnections`|<span data-ttu-id="1393e-118">Anzahl der aktiven Verbindungen, die gerade genutzt werden</span><span class="sxs-lookup"><span data-stu-id="1393e-118">The number of active connections that are currently in use.</span></span> <span data-ttu-id="1393e-119">**Hinweis:**  Dieser Leistungswert ist standardmäßig nicht aktiviert.</span><span class="sxs-lookup"><span data-stu-id="1393e-119">**Note:**  This performance counter is not enabled by default.</span></span> <span data-ttu-id="1393e-120">Informationen zum Aktivieren dieses Leistungsindikators finden Sie unter [Aktivieren von Standard](#ActivatingOffByDefault)mäßigen Leistungsindikatoren.</span><span class="sxs-lookup"><span data-stu-id="1393e-120">To enable this performance counter, see [Activating Off-By-Default Counters](#ActivatingOffByDefault).</span></span>|  
|`NumberOfFreeConnections`|<span data-ttu-id="1393e-121">Anzahl der Verbindungen, die für die Verwendung in den Verbindungspools verfügbar sind</span><span class="sxs-lookup"><span data-stu-id="1393e-121">The number of connections available for use in the connection pools.</span></span> <span data-ttu-id="1393e-122">**Hinweis:**  Dieser Leistungswert ist standardmäßig nicht aktiviert.</span><span class="sxs-lookup"><span data-stu-id="1393e-122">**Note:**  This performance counter is not enabled by default.</span></span> <span data-ttu-id="1393e-123">Informationen zum Aktivieren dieses Leistungsindikators finden Sie unter [Aktivieren von Standard](#ActivatingOffByDefault)mäßigen Leistungsindikatoren.</span><span class="sxs-lookup"><span data-stu-id="1393e-123">To enable this performance counter, see [Activating Off-By-Default Counters](#ActivatingOffByDefault).</span></span>|  
|`NumberOfInactiveConnectionPoolGroups`|<span data-ttu-id="1393e-124">Anzahl der eindeutigen Verbindungspoolgruppen, die zum Löschen gekennzeichnet sind.</span><span class="sxs-lookup"><span data-stu-id="1393e-124">The number of unique connection pool groups that are marked for pruning.</span></span> <span data-ttu-id="1393e-125">Dieser Indikator wird von der Anzahl der eindeutigen Verbindungszeichenfolgen gesteuert, die in der Anwendungsdomäne (AppDomain) gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="1393e-125">This counter is controlled by the number of unique connection strings that are found in the AppDomain.</span></span>|  
|`NumberOfInactiveConnectionPools`|<span data-ttu-id="1393e-126">Anzahl der inaktiven Verbindungspools, die in letzter Zeit keine Aktivitäten zu verzeichnen hatten und darauf warten, gelöscht zu werden</span><span class="sxs-lookup"><span data-stu-id="1393e-126">The number of inactive connection pools that have not had any recent activity and are waiting to be disposed.</span></span>|  
|`NumberOfNonPooledConnections`|<span data-ttu-id="1393e-127">Anzahl der aktiven Verbindungen, die sich nicht in einem Pool befinden</span><span class="sxs-lookup"><span data-stu-id="1393e-127">The number of active connections that are not pooled.</span></span>|  
|`NumberOfPooledConnections`|<span data-ttu-id="1393e-128">Anzahl der aktiven Verbindungen, die von der Verbindungspooling-Infrastruktur verwaltet werden</span><span class="sxs-lookup"><span data-stu-id="1393e-128">The number of active connections that are being managed by the connection pooling infrastructure.</span></span>|  
|`NumberOfReclaimedConnections`|<span data-ttu-id="1393e-129">Anzahl der Verbindungen, die durch die Garbage Collection (automatische Speicherbereinigung) wieder verfügbar gemacht wurden, bei denen die Anwendung weder `Close` noch `Dispose` aufgerufen hat.</span><span class="sxs-lookup"><span data-stu-id="1393e-129">The number of connections that have been reclaimed through garbage collection where `Close` or `Dispose` was not called by the application.</span></span> <span data-ttu-id="1393e-130">Nicht mehr benötigte Verbindungen, die weiterbestehen, weil sie nicht explizit geschlossen oder gelöscht wurden, beeinträchtigen die Arbeitsgeschwindigkeit.</span><span class="sxs-lookup"><span data-stu-id="1393e-130">Not explicitly closing or disposing connections hurts performance.</span></span>|  
|`NumberOfStasisConnections`|<span data-ttu-id="1393e-131">Anzahl der Verbindungen, die derzeit den Abschluss einer Aktion erwarten und die daher für die Verwendung durch Ihre Anwendung nicht zur Verfügung stehen</span><span class="sxs-lookup"><span data-stu-id="1393e-131">The number of connections currently awaiting completion of an action and which are therefore unavailable for use by your application.</span></span>|  
|`SoftConnectsPerSecond`|<span data-ttu-id="1393e-132">Anzahl der aktiven Verbindungen, die aus dem Verbindungspool herausgezogen werden.</span><span class="sxs-lookup"><span data-stu-id="1393e-132">The number of active connections being pulled from the connection pool.</span></span> <span data-ttu-id="1393e-133">**Hinweis:**  Dieser Leistungswert ist standardmäßig nicht aktiviert.</span><span class="sxs-lookup"><span data-stu-id="1393e-133">**Note:**  This performance counter is not enabled by default.</span></span> <span data-ttu-id="1393e-134">Informationen zum Aktivieren dieses Leistungsindikators finden Sie unter [Aktivieren von Standard](#ActivatingOffByDefault)mäßigen Leistungsindikatoren.</span><span class="sxs-lookup"><span data-stu-id="1393e-134">To enable this performance counter, see [Activating Off-By-Default Counters](#ActivatingOffByDefault).</span></span>|  
|`SoftDisconnectsPerSecond`|<span data-ttu-id="1393e-135">Anzahl der aktiven Verbindungen, die an den Verbindungspool zurückgegeben werden</span><span class="sxs-lookup"><span data-stu-id="1393e-135">The number of active connections that are being returned to the connection pool.</span></span> <span data-ttu-id="1393e-136">**Hinweis:**  Dieser Leistungswert ist standardmäßig nicht aktiviert.</span><span class="sxs-lookup"><span data-stu-id="1393e-136">**Note:**  This performance counter is not enabled by default.</span></span> <span data-ttu-id="1393e-137">Informationen zum Aktivieren dieses Leistungsindikators finden Sie unter [Aktivieren von Standard](#ActivatingOffByDefault)mäßigen Leistungsindikatoren.</span><span class="sxs-lookup"><span data-stu-id="1393e-137">To enable this performance counter, see [Activating Off-By-Default Counters](#ActivatingOffByDefault).</span></span>|  
  
### <a name="connection-pool-groups-and-connection-pools"></a><span data-ttu-id="1393e-138">Verbindungspoolgruppen und Verbindungspools</span><span class="sxs-lookup"><span data-stu-id="1393e-138">Connection Pool Groups and Connection Pools</span></span>  
 <span data-ttu-id="1393e-139">Bei der Verwendung der Windows-Authentifizierung (integrierte Sicherheit) müssen die folgenden beiden Leistungsindikatoren überwacht werden: `NumberOfActiveConnectionPoolGroups` und `NumberOfActiveConnectionPools`.</span><span class="sxs-lookup"><span data-stu-id="1393e-139">When using Windows Authentication (integrated security), you must monitor both the `NumberOfActiveConnectionPoolGroups` and `NumberOfActiveConnectionPools` performance counters.</span></span> <span data-ttu-id="1393e-140">Dies liegt daran, dass Verbindungspoolgruppen eindeutigen Verbindungszeichenfolgen zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="1393e-140">The reason is that connection pool groups map to unique connection strings.</span></span> <span data-ttu-id="1393e-141">Bei Verwendung der integrierten Sicherheit werden die Verbindungspools den Verbindungszeichenfolgen zugeordnet, und zusätzlich werden separate Pools für einzelne Windows-Identitäten erstellt.</span><span class="sxs-lookup"><span data-stu-id="1393e-141">When integrated security is used, connection pools map to connection strings and additionally create separate pools for individual Windows identities.</span></span> <span data-ttu-id="1393e-142">Wenn Fred und Julie z. B. innerhalb derselben Anwendungsdomäne beide die `"Data Source=MySqlServer;Integrated Security=true"`-Verbindungszeichenfolge verwenden, wird für die Verbindungszeichenfolge eine Verbindungspoolgruppe erstellt, und es werden zwei zusätzliche Pools erstellt: einer für Fred und einer für Julie.</span><span class="sxs-lookup"><span data-stu-id="1393e-142">For example, if Fred and Julie, each within the same AppDomain, both use the connection string `"Data Source=MySqlServer;Integrated Security=true"`, a connection pool group is created for the connection string, and two additional pools are created, one for Fred and one for Julie.</span></span> <span data-ttu-id="1393e-143">Wenn John und Martha eine Verbindungs Zeichenfolge mit einem identischen SQL Server-Anmelde Namen verwenden, `"Data Source=MySqlServer;User Id=lowPrivUser;Password=Strong?Password"` wird nur ein einzelner Pool für die **lowPrivUser** -Identität erstellt.</span><span class="sxs-lookup"><span data-stu-id="1393e-143">If John and Martha use a connection string with an identical SQL Server login, `"Data Source=MySqlServer;User Id=lowPrivUser;Password=Strong?Password"`, then only a single pool is created for the **lowPrivUser** identity.</span></span>  
  
<a name="ActivatingOffByDefault"></a>
### <a name="activating-off-by-default-counters"></a><span data-ttu-id="1393e-144">Aktivieren von Indikatoren, die standardmäßig deaktiviert sind</span><span class="sxs-lookup"><span data-stu-id="1393e-144">Activating Off-By-Default Counters</span></span>  
 <span data-ttu-id="1393e-145">Die Leistungsindikatoren `NumberOfFreeConnections`, `NumberOfActiveConnections`, `SoftDisconnectsPerSecond` und `SoftConnectsPerSecond` sind standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="1393e-145">The performance counters `NumberOfFreeConnections`, `NumberOfActiveConnections`, `SoftDisconnectsPerSecond`, and `SoftConnectsPerSecond` are off by default.</span></span> <span data-ttu-id="1393e-146">Fügen Sie zum Aktivieren dieser Indikatoren in der Konfigurationsdatei der Anwendung folgende Informationen hinzu:</span><span class="sxs-lookup"><span data-stu-id="1393e-146">Add the following information to the application's configuration file to enable them:</span></span>  
  
```xml  
<system.diagnostics>  
  <switches>  
    <add name="ConnectionPoolPerformanceCounterDetail"  
         value="4"/>  
  </switches>  
</system.diagnostics>  
```  
  
## <a name="retrieving-performance-counter-values"></a><span data-ttu-id="1393e-147">Abrufen von Leistungsindikatorwerten</span><span class="sxs-lookup"><span data-stu-id="1393e-147">Retrieving Performance Counter Values</span></span>  
 <span data-ttu-id="1393e-148">Die folgende Konsolenanwendung zeigt, wie Sie in Ihrer Anwendung Leistungsindikatorwerte abrufen können.</span><span class="sxs-lookup"><span data-stu-id="1393e-148">The following console application shows how to retrieve performance counter values in your application.</span></span> <span data-ttu-id="1393e-149">Die Verbindungen müssen offen und aktiv sein, damit Informationen für alle ADO.NET-Leistungsindikatoren zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="1393e-149">Connections must be open and active for information to be returned for all of the ADO.NET performance counters.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1393e-150">In diesem Beispiel wird die **AdventureWorks** -Beispieldatenbank verwendet, die in SQL Server enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="1393e-150">This example uses the sample **AdventureWorks** database included with SQL Server.</span></span> <span data-ttu-id="1393e-151">In der Verbindungszeichenfolge im Beispielcode wird davon ausgegangen, dass die Datenbank auf dem lokalen Computer installiert und mit dem Instanznamen SqlExpress verfügbar ist. Außerdem wird davon ausgegangen, dass Sie SQL Server-Anmeldungen erstellt haben, die mit denen in den Verbindungszeichenfolgen übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="1393e-151">The connection strings provided in the sample code assume that the database is installed and available on the local computer with an instance name of SqlExpress, and that you have created SQL Server logins that match those supplied in the connection strings.</span></span> <span data-ttu-id="1393e-152">Falls Ihr Server mit den Standardsicherheitseinstellungen konfiguriert ist, die nur die Windows-Authentifizierung zulassen, müssen Sie die SQL Server-Anmeldungen u. U. erst aktivieren.</span><span class="sxs-lookup"><span data-stu-id="1393e-152">You may need to enable SQL Server logins if your server is configured using the default security settings which allow only Windows Authentication.</span></span> <span data-ttu-id="1393e-153">Passen Sie die Verbindungszeichenfolgen an Ihre Umgebung an.</span><span class="sxs-lookup"><span data-stu-id="1393e-153">Modify the connection strings as necessary to suit your environment.</span></span>  
  
### <a name="example"></a><span data-ttu-id="1393e-154">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1393e-154">Example</span></span>  
  
```vb  
Option Explicit On  
Option Strict On  
  
Imports System.Data.SqlClient  
Imports System.Diagnostics  
Imports System.Runtime.InteropServices  
  
Class Program  
  
    Private PerfCounters(9) As PerformanceCounter  
    Private connection As SqlConnection = New SqlConnection  
  
    Public Shared Sub Main()  
        Dim prog As Program = New Program  
        ' Open a connection and create the performance counters.
        prog.connection.ConnectionString = _  
           GetIntegratedSecurityConnectionString()  
        prog.SetUpPerformanceCounters()  
        Console.WriteLine("Available Performance Counters:")  
  
        ' Create the connections and display the results.  
        prog.CreateConnections()  
        Console.WriteLine("Press Enter to finish.")  
        Console.ReadLine()  
    End Sub  
  
    Private Sub CreateConnections()  
        ' List the Performance counters.  
        WritePerformanceCounters()  
  
        ' Create 4 connections and display counter information.  
        Dim connection1 As SqlConnection = New SqlConnection( _  
           GetIntegratedSecurityConnectionString)  
        connection1.Open()  
        Console.WriteLine("Opened the 1st Connection:")  
        WritePerformanceCounters()  
  
        Dim connection2 As SqlConnection = New SqlConnection( _  
           GetSqlConnectionStringDifferent)  
        connection2.Open()  
        Console.WriteLine("Opened the 2nd Connection:")  
        WritePerformanceCounters()  
  
        Console.WriteLine("Opened the 3rd Connection:")  
        Dim connection3 As SqlConnection = New SqlConnection( _  
           GetSqlConnectionString)  
        connection3.Open()  
        WritePerformanceCounters()  
  
        Dim connection4 As SqlConnection = New SqlConnection( _  
           GetSqlConnectionString)  
        connection4.Open()  
        Console.WriteLine("Opened the 4th Connection:")  
        WritePerformanceCounters()  
  
        connection1.Close()  
        Console.WriteLine("Closed the 1st Connection:")  
        WritePerformanceCounters()  
  
        connection2.Close()  
        Console.WriteLine("Closed the 2nd Connection:")  
        WritePerformanceCounters()  
  
        connection3.Close()  
        Console.WriteLine("Closed the 3rd Connection:")  
        WritePerformanceCounters()  
  
        connection4.Close()  
        Console.WriteLine("Closed the 4th Connection:")  
        WritePerformanceCounters()  
    End Sub  
  
    Private Enum ADO_Net_Performance_Counters  
        NumberOfActiveConnectionPools  
        NumberOfReclaimedConnections  
        HardConnectsPerSecond  
        HardDisconnectsPerSecond  
        NumberOfActiveConnectionPoolGroups  
        NumberOfInactiveConnectionPoolGroups  
        NumberOfInactiveConnectionPools  
        NumberOfNonPooledConnections  
        NumberOfPooledConnections  
        NumberOfStasisConnections  
        ' The following performance counters are more expensive to track.  
        ' Enable ConnectionPoolPerformanceCounterDetail in your config file.  
        '     SoftConnectsPerSecond  
        '     SoftDisconnectsPerSecond  
        '     NumberOfActiveConnections  
        '     NumberOfFreeConnections  
    End Enum  
  
    Private Sub SetUpPerformanceCounters()  
        connection.Close()  
        Me.PerfCounters(9) = New PerformanceCounter()  
  
        Dim instanceName As String = GetInstanceName()  
        Dim apc As Type = GetType(ADO_Net_Performance_Counters)  
        Dim i As Integer = 0  
        Dim s As String = ""  
        For Each s In [Enum].GetNames(apc)  
            Me.PerfCounters(i) = New PerformanceCounter()  
            Me.PerfCounters(i).CategoryName = ".NET Data Provider for SqlServer"  
            Me.PerfCounters(i).CounterName = s  
            Me.PerfCounters(i).InstanceName = instanceName  
            i = (i + 1)  
        Next  
    End Sub  
  
    Private Declare Function GetCurrentProcessId Lib "kernel32.dll" () As Integer  
  
    Private Function GetInstanceName() As String  
        'This works for Winforms apps.
        Dim instanceName As String = _  
           System.Reflection.Assembly.GetEntryAssembly.GetName.Name  
  
        ' Must replace special characters like (, ), #, /, \\
        Dim instanceName2 As String = _  
           AppDomain.CurrentDomain.FriendlyName.ToString.Replace("(", "[") _  
           .Replace(")", "]").Replace("#", "_").Replace("/", "_").Replace("\\", "_")  
  
        'For ASP.NET applications your instanceName will be your CurrentDomain's
        'FriendlyName. Replace the line above that sets the instanceName with this:
        'instanceName = AppDomain.CurrentDomain.FriendlyName.ToString.Replace("(", "[") _  
        '    .Replace(")", "]").Replace("#", "_").Replace("/", "_").Replace("\\", "_")  
  
        Dim pid As String = GetCurrentProcessId.ToString  
        instanceName = (instanceName + ("[" & (pid & "]")))  
        Console.WriteLine("Instance Name: {0}", instanceName)  
        Console.WriteLine("---------------------------")  
        Return instanceName  
    End Function  
  
    Private Sub WritePerformanceCounters()  
        Console.WriteLine("---------------------------")  
        For Each p As PerformanceCounter In Me.PerfCounters  
            Console.WriteLine("{0} = {1}", p.CounterName, p.NextValue)  
        Next  
        Console.WriteLine("---------------------------")  
    End Sub  
  
    Private Shared Function GetIntegratedSecurityConnectionString() As String  
        ' To avoid storing the connection string in your code,
        ' you can retrieve it from a configuration file.
        Return ("Data Source=.\SqlExpress;Integrated Security=True;" &
          "Initial Catalog=AdventureWorks")  
    End Function  
  
    Private Shared Function GetSqlConnectionString() As String  
        ' To avoid storing the connection string in your code,
        ' you can retrieve it from a configuration file.
        Return ("Data Source=.\SqlExpress;User Id=LowPriv;Password=Data!05;" &
          "Initial Catalog=AdventureWorks")  
    End Function  
  
    Private Shared Function GetSqlConnectionStringDifferent() As String  
        ' To avoid storing the connection string in your code,
        ' you can retrieve it from a configuration file.
        Return ("Initial Catalog=AdventureWorks;Data Source=.\SqlExpress;" & _  
          "User Id=LowPriv;Password=Data!05;")  
    End Function  
End Class  
```  

```csharp  
using System;  
using System.Data.SqlClient;  
using System.Diagnostics;  
using System.Runtime.InteropServices;  
  
class Program  
{  
    PerformanceCounter[] PerfCounters = new PerformanceCounter[10];  
    SqlConnection connection = new SqlConnection();  
  
    static void Main()  
    {  
        Program prog = new Program();  
        // Open a connection and create the performance counters.  
        prog.connection.ConnectionString =  
           GetIntegratedSecurityConnectionString();  
        prog.SetUpPerformanceCounters();  
        Console.WriteLine("Available Performance Counters:");  
  
        // Create the connections and display the results.  
        prog.CreateConnections();  
        Console.WriteLine("Press Enter to finish.");  
        Console.ReadLine();  
    }  
  
    private void CreateConnections()  
    {  
        // List the Performance counters.  
        WritePerformanceCounters();  
  
        // Create 4 connections and display counter information.  
        SqlConnection connection1 = new SqlConnection(  
              GetIntegratedSecurityConnectionString());  
        connection1.Open();  
        Console.WriteLine("Opened the 1st Connection:");  
        WritePerformanceCounters();  
  
        SqlConnection connection2 = new SqlConnection(  
              GetSqlConnectionStringDifferent());  
        connection2.Open();  
        Console.WriteLine("Opened the 2nd Connection:");  
        WritePerformanceCounters();  
  
        SqlConnection connection3 = new SqlConnection(  
              GetSqlConnectionString());  
        connection3.Open();  
        Console.WriteLine("Opened the 3rd Connection:");  
        WritePerformanceCounters();  
  
        SqlConnection connection4 = new SqlConnection(  
              GetSqlConnectionString());  
        connection4.Open();  
        Console.WriteLine("Opened the 4th Connection:");  
        WritePerformanceCounters();  
  
        connection1.Close();  
        Console.WriteLine("Closed the 1st Connection:");  
        WritePerformanceCounters();  
  
        connection2.Close();  
        Console.WriteLine("Closed the 2nd Connection:");  
        WritePerformanceCounters();  
  
        connection3.Close();  
        Console.WriteLine("Closed the 3rd Connection:");  
        WritePerformanceCounters();  
  
        connection4.Close();  
        Console.WriteLine("Closed the 4th Connection:");  
        WritePerformanceCounters();  
    }  
  
    private enum ADO_Net_Performance_Counters  
    {  
        NumberOfActiveConnectionPools,  
        NumberOfReclaimedConnections,  
        HardConnectsPerSecond,  
        HardDisconnectsPerSecond,  
        NumberOfActiveConnectionPoolGroups,  
        NumberOfInactiveConnectionPoolGroups,  
        NumberOfInactiveConnectionPools,  
        NumberOfNonPooledConnections,  
        NumberOfPooledConnections,  
        NumberOfStasisConnections  
        // The following performance counters are more expensive to track.  
        // Enable ConnectionPoolPerformanceCounterDetail in your config file.  
        //     SoftConnectsPerSecond  
        //     SoftDisconnectsPerSecond  
        //     NumberOfActiveConnections  
        //     NumberOfFreeConnections  
    }  
  
    private void SetUpPerformanceCounters()  
    {  
        connection.Close();  
        this.PerfCounters = new PerformanceCounter[10];  
        string instanceName = GetInstanceName();  
        Type apc = typeof(ADO_Net_Performance_Counters);  
        int i = 0;  
        foreach (string s in Enum.GetNames(apc))  
        {  
            this.PerfCounters[i] = new PerformanceCounter();  
            this.PerfCounters[i].CategoryName = ".NET Data Provider for SqlServer";  
            this.PerfCounters[i].CounterName = s;  
            this.PerfCounters[i].InstanceName = instanceName;  
            i++;  
        }  
    }  
  
    [DllImport("kernel32.dll", SetLastError = true)]  
    static extern int GetCurrentProcessId();  
  
    private string GetInstanceName()  
    {  
        //This works for Winforms apps.  
        string instanceName =  
            System.Reflection.Assembly.GetEntryAssembly().GetName().Name;  
  
        // Must replace special characters like (, ), #, /, \\  
        string instanceName2 =  
            AppDomain.CurrentDomain.FriendlyName.ToString().Replace('(', '[')  
            .Replace(')', ']').Replace('#', '_').Replace('/', '_').Replace('\\', '_');  
  
        // For ASP.NET applications your instanceName will be your CurrentDomain's
        // FriendlyName. Replace the line above that sets the instanceName with this:  
        // instanceName = AppDomain.CurrentDomain.FriendlyName.ToString().Replace('(','[')  
        // .Replace(')',']').Replace('#','_').Replace('/','_').Replace('\\','_');  
  
        string pid = GetCurrentProcessId().ToString();  
        instanceName = instanceName + "[" + pid + "]";  
        Console.WriteLine("Instance Name: {0}", instanceName);  
        Console.WriteLine("---------------------------");  
        return instanceName;  
    }  
  
    private void WritePerformanceCounters()  
    {  
        Console.WriteLine("---------------------------");  
        foreach (PerformanceCounter p in this.PerfCounters)  
        {  
            Console.WriteLine("{0} = {1}", p.CounterName, p.NextValue());  
        }  
        Console.WriteLine("---------------------------");  
    }  
  
    private static string GetIntegratedSecurityConnectionString()  
    {  
        // To avoid storing the connection string in your code,  
        // you can retrieve it from a configuration file.  
        return @"Data Source=.\SqlExpress;Integrated Security=True;" +  
          "Initial Catalog=AdventureWorks";  
    }  
    private static string GetSqlConnectionString()  
    {  
        // To avoid storing the connection string in your code,  
        // you can retrieve it from a configuration file.  
        return @"Data Source=.\SqlExpress;User Id=LowPriv;Password=Data!05;" +  
          "Initial Catalog=AdventureWorks";  
    }  
  
    private static string GetSqlConnectionStringDifferent()  
    {  
        // To avoid storing the connection string in your code,  
        // you can retrieve it from a configuration file.  
        return @"Initial Catalog=AdventureWorks;Data Source=.\SqlExpress;" +  
          "User Id=LowPriv;Password=Data!05;";  
    }  
}  
```  

## <a name="see-also"></a><span data-ttu-id="1393e-155">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1393e-155">See also</span></span>

- [<span data-ttu-id="1393e-156">Herstellen der Verbindung mit einer Datenquelle</span><span class="sxs-lookup"><span data-stu-id="1393e-156">Connecting to a Data Source</span></span>](connecting-to-a-data-source.md)
- [<span data-ttu-id="1393e-157">OLE DB-, ODBC- und Oracle-Verbindungspooling</span><span class="sxs-lookup"><span data-stu-id="1393e-157">OLE DB, ODBC, and Oracle Connection Pooling</span></span>](ole-db-odbc-and-oracle-connection-pooling.md)
- <span data-ttu-id="1393e-158">[Leistungsindikatoren für ASP.NET](/previous-versions/aspnet/fxk122b4(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="1393e-158">[Performance Counters for ASP.NET](/previous-versions/aspnet/fxk122b4(v=vs.100))</span></span>
- [<span data-ttu-id="1393e-159">Laufzeit-Profilerstellung</span><span class="sxs-lookup"><span data-stu-id="1393e-159">Runtime Profiling</span></span>](../../debug-trace-profile/runtime-profiling.md)
- <span data-ttu-id="1393e-160">[Einführung in die Überwachung von Leistungs Schwellenwerten](/previous-versions/visualstudio/visual-studio-2008/bd20x32d(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="1393e-160">[Introduction to Monitoring Performance Thresholds](/previous-versions/visualstudio/visual-studio-2008/bd20x32d(v=vs.90))</span></span>
- [<span data-ttu-id="1393e-161">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="1393e-161">ADO.NET Overview</span></span>](ado-net-overview.md)
