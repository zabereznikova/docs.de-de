---
title: Leistungsindikatoren
description: Verwenden Sie ADO.NET-Leistungsindikatoren zum Überwachen des Anwendungs Status und der zugehörigen Verbindungs Ressourcen mithilfe von Windows Performance Monitor oder Programm gesteuert.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0b121b71-78f8-4ae2-9aa1-0b2e15778e57
ms.openlocfilehash: dca259ef6d8a2229349d88a9fcae3298cb8a829c
ms.sourcegitcommit: ecd9e9bb2225eb76f819722ea8b24988fe46f34c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2020
ms.locfileid: "96739463"
---
# <a name="performance-counters-in-adonet"></a>Leistungsindikatoren in ADO.NET

Neu in ADO.NET 2.0 ist die erweiterte Unterstützung für Leistungsindikatoren. Dazu gehört auch die Unterstützung für <xref:System.Data.SqlClient> und <xref:System.Data.OracleClient>. Die in früheren ADO.NET-Versionen verfügbaren <xref:System.Data.SqlClient>-Leistungsindikatoren wurden durch neue Leistungsindikatoren ersetzt, die in diesem Thema beschrieben werden. Mit den ADO.NET-Leistungsindikatoren können Sie den Status Ihrer Anwendung und die Verbindungsressourcen überwachen, die die Anwendung verwendet. Für die Überwachung der Leistungsindikatoren kann der Windows-Leistungsmonitor verwendet werden, und die <xref:System.Diagnostics.PerformanceCounter>-Klasse im <xref:System.Diagnostics>-Namespace ermöglicht den programmgesteuerten Zugriff auf diese Indikatoren.

## <a name="available-performance-counters"></a>Verfügbare Leistungsindikatoren

 Derzeit sind für <xref:System.Data.SqlClient> und <xref:System.Data.OracleClient> 14 verschiedene Leistungsindikatoren verfügbar (siehe Beschreibung in der folgenden Tabelle). Die Indikatoren behalten in allen lokalisierten Microsoft .NET Framework-Versionen ihre englischen Namen.

|Leistungsindikator|BESCHREIBUNG|
|-------------------------|-----------------|
|`HardConnectsPerSecond`|Anzahl der Verbindungen, die pro Sekunde mit einem Datenbankserver hergestellt wurden|
|`HardDisconnectsPerSecond`|Anzahl der Verbindungen mit einem Datenbankserver, die pro Sekunde getrennt wurden|
|`NumberOfActiveConnectionPoolGroups`|Anzahl der eindeutigen Verbindungspoolgruppen, die aktiv sind. Dieser Indikator wird von der Anzahl der eindeutigen Verbindungszeichenfolgen gesteuert, die in der Anwendungsdomäne (AppDomain) gefunden werden.|
|`NumberOfActiveConnectionPools`|Gesamtzahl der Verbindungspools|
|`NumberOfActiveConnections`|Anzahl der aktiven Verbindungen, die gerade genutzt werden **Hinweis:**  Dieser Leistungswert ist standardmäßig nicht aktiviert. Informationen zum Aktivieren dieses Leistungsindikators finden Sie unter [Aktivieren von Standard](#ActivatingOffByDefault)mäßigen Leistungsindikatoren.|
|`NumberOfFreeConnections`|Anzahl der Verbindungen, die für die Verwendung in den Verbindungspools verfügbar sind **Hinweis:**  Dieser Leistungswert ist standardmäßig nicht aktiviert. Informationen zum Aktivieren dieses Leistungsindikators finden Sie unter [Aktivieren von Standard](#ActivatingOffByDefault)mäßigen Leistungsindikatoren.|
|`NumberOfInactiveConnectionPoolGroups`|Anzahl der eindeutigen Verbindungspoolgruppen, die zum Löschen gekennzeichnet sind. Dieser Indikator wird von der Anzahl der eindeutigen Verbindungszeichenfolgen gesteuert, die in der Anwendungsdomäne (AppDomain) gefunden werden.|
|`NumberOfInactiveConnectionPools`|Anzahl der inaktiven Verbindungspools, die in letzter Zeit keine Aktivitäten zu verzeichnen hatten und darauf warten, gelöscht zu werden|
|`NumberOfNonPooledConnections`|Anzahl der aktiven Verbindungen, die sich nicht in einem Pool befinden|
|`NumberOfPooledConnections`|Anzahl der aktiven Verbindungen, die von der Verbindungspooling-Infrastruktur verwaltet werden|
|`NumberOfReclaimedConnections`|Anzahl der Verbindungen, die durch die Garbage Collection (automatische Speicherbereinigung) wieder verfügbar gemacht wurden, bei denen die Anwendung weder `Close` noch `Dispose` aufgerufen hat. Nicht mehr benötigte Verbindungen, die weiterbestehen, weil sie nicht explizit geschlossen oder gelöscht wurden, beeinträchtigen die Arbeitsgeschwindigkeit.|
|`NumberOfStasisConnections`|Anzahl der Verbindungen, die derzeit den Abschluss einer Aktion erwarten und die daher für die Verwendung durch Ihre Anwendung nicht zur Verfügung stehen|
|`SoftConnectsPerSecond`|Anzahl der aktiven Verbindungen, die aus dem Verbindungspool herausgezogen werden. **Hinweis:**  Dieser Leistungswert ist standardmäßig nicht aktiviert. Informationen zum Aktivieren dieses Leistungsindikators finden Sie unter [Aktivieren von Standard](#ActivatingOffByDefault)mäßigen Leistungsindikatoren.|
|`SoftDisconnectsPerSecond`|Anzahl der aktiven Verbindungen, die an den Verbindungspool zurückgegeben werden **Hinweis:**  Dieser Leistungswert ist standardmäßig nicht aktiviert. Informationen zum Aktivieren dieses Leistungsindikators finden Sie unter [Aktivieren von Standard](#ActivatingOffByDefault)mäßigen Leistungsindikatoren.|

### <a name="connection-pool-groups-and-connection-pools"></a>Verbindungspoolgruppen und Verbindungspools

 Bei der Verwendung der Windows-Authentifizierung (integrierte Sicherheit) müssen die folgenden beiden Leistungsindikatoren überwacht werden: `NumberOfActiveConnectionPoolGroups` und `NumberOfActiveConnectionPools`. Dies liegt daran, dass Verbindungspoolgruppen eindeutigen Verbindungszeichenfolgen zugeordnet werden. Bei Verwendung der integrierten Sicherheit werden die Verbindungspools den Verbindungszeichenfolgen zugeordnet, und zusätzlich werden separate Pools für einzelne Windows-Identitäten erstellt. Wenn Fred und Julie z. B. innerhalb derselben Anwendungsdomäne beide die `"Data Source=MySqlServer;Integrated Security=true"`-Verbindungszeichenfolge verwenden, wird für die Verbindungszeichenfolge eine Verbindungspoolgruppe erstellt, und es werden zwei zusätzliche Pools erstellt: einer für Fred und einer für Julie. Wenn John und Martha eine Verbindungs Zeichenfolge mit einem identischen SQL Server-Anmelde Namen verwenden, `"Data Source=MySqlServer;User Id=lowPrivUser;Password=[PLACEHOLDER]"` wird nur ein einzelner Pool für die **lowPrivUser** -Identität erstellt.

<a name="ActivatingOffByDefault"></a>

### <a name="activating-off-by-default-counters"></a>Aktivieren von Indikatoren, die standardmäßig deaktiviert sind

 Die Leistungsindikatoren `NumberOfFreeConnections`, `NumberOfActiveConnections`, `SoftDisconnectsPerSecond` und `SoftConnectsPerSecond` sind standardmäßig deaktiviert. Fügen Sie zum Aktivieren dieser Indikatoren in der Konfigurationsdatei der Anwendung folgende Informationen hinzu:

```xml
<system.diagnostics>
  <switches>
    <add name="ConnectionPoolPerformanceCounterDetail"
         value="4"/>
  </switches>
</system.diagnostics>
```

## <a name="retrieving-performance-counter-values"></a>Abrufen von Leistungsindikatorwerten

 Die folgende Konsolenanwendung zeigt, wie Sie in Ihrer Anwendung Leistungsindikatorwerte abrufen können. Die Verbindungen müssen offen und aktiv sein, damit Informationen für alle ADO.NET-Leistungsindikatoren zurückgegeben werden.

> [!NOTE]
> In diesem Beispiel wird die **AdventureWorks** -Beispieldatenbank verwendet, die in SQL Server enthalten ist. In der Verbindungszeichenfolge im Beispielcode wird davon ausgegangen, dass die Datenbank auf dem lokalen Computer installiert und mit dem Instanznamen SqlExpress verfügbar ist. Außerdem wird davon ausgegangen, dass Sie SQL Server-Anmeldungen erstellt haben, die mit denen in den Verbindungszeichenfolgen übereinstimmen. Falls Ihr Server mit den Standardsicherheitseinstellungen konfiguriert ist, die nur die Windows-Authentifizierung zulassen, müssen Sie die SQL Server-Anmeldungen u. U. erst aktivieren. Passen Sie die Verbindungszeichenfolgen an Ihre Umgebung an.

### <a name="example"></a>Beispiel

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
        Return ("Data Source=.\SqlExpress;User Id=LowPriv;Password=[PLACEHOLDER];" &
          "Initial Catalog=AdventureWorks")
    End Function

    Private Shared Function GetSqlConnectionStringDifferent() As String
        ' To avoid storing the connection string in your code,
        ' you can retrieve it from a configuration file.
        Return ("Initial Catalog=AdventureWorks;Data Source=.\SqlExpress;" & _
          "User Id=LowPriv;Password=[PLACEHOLDER];")
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
        return @"Data Source=.\SqlExpress;User Id=LowPriv;Password=[PLACEHOLDER];" +
          "Initial Catalog=AdventureWorks";
    }

    private static string GetSqlConnectionStringDifferent()
    {
        // To avoid storing the connection string in your code,
        // you can retrieve it from a configuration file.
        return @"Initial Catalog=AdventureWorks;Data Source=.\SqlExpress;" +
          "User Id=LowPriv;Password=[PLACEHOLDER];";
    }
}
```

## <a name="see-also"></a>Weitere Informationen

- [Herstellen der Verbindung mit einer Datenquelle](connecting-to-a-data-source.md)
- [OLE DB-, ODBC- und Oracle-Verbindungspooling](ole-db-odbc-and-oracle-connection-pooling.md)
- [Leistungsindikatoren für ASP.NET](/previous-versions/aspnet/fxk122b4(v=vs.100))
- [Laufzeit-Profilerstellung](../../debug-trace-profile/runtime-profiling.md)
- [Einführung in die Überwachung von Leistungs Schwellenwerten](/previous-versions/visualstudio/visual-studio-2008/bd20x32d(v=vs.90))
- [Übersicht über ADO.NET](ado-net-overview.md)
