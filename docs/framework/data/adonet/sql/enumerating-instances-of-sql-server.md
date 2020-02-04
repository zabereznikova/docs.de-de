---
title: Auflisten von Instanzen von SQL Server
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ddf1c83c-9d40-45e6-b04d-9828c6cbbfdc
ms.openlocfilehash: c59db5869ed848071611cdbf985b45dc59790d69
ms.sourcegitcommit: 19014f9c081ca2ff19652ca12503828db8239d48
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "76979988"
---
# <a name="enumerating-instances-of-sql-server-adonet"></a>Aufzählen von SQL Server-Instanzen (ADO.NET)
SQL Server ermöglicht es Anwendungen, SQL Server Instanzen im aktuellen Netzwerk zu finden. Die hierzu erforderlichen Informationen werden den Entwicklern von Anwendungen durch die <xref:System.Data.Sql.SqlDataSourceEnumerator>-Klasse als <xref:System.Data.DataTable> verfügbar gemacht, die Informationen zu allen sichtbaren Servern enthält. Diese zurückgegebene Tabelle enthält eine Liste der im Netzwerk verfügbaren Server Instanzen, die der Liste entspricht, wenn ein Benutzer versucht, eine neue Verbindung zu erstellen, und erweitert die Dropdown Liste, die alle verfügbaren Server enthält, im Dialogfeld **Verbindungs Eigenschaften** . Die Liste der angezeigten Ergebnisse ist nicht immer vollständig.  
  
> [!NOTE]
> Wie bei den meisten Windows-Diensten wird auch hier empfohlen, den SQL-Browserdienst mit minimalen Berechtigungen auszuführen. Weitere Informationen zum SQL-Browserdienst und dessen Verwaltung finden Sie in der Onlinedokumentation zu SQL Server.  
  
## <a name="retrieving-an-enumerator-instance"></a>Abrufen einer Enumeratorinstanz  
 Damit Sie die Tabelle mit den Informationen zu den verfügbaren SQL Server-Instanzen abrufen können, müssen Sie zunächst einen Enumerator abrufen. Hierzu verwenden Sie die freigegebene/statische <xref:System.Data.Sql.SqlDataSourceEnumerator.Instance%2A>-Eigenschaft:  
  
```vb  
Dim instance As System.Data.Sql.SqlDataSourceEnumerator = _  
   System.Data.Sql.SqlDataSourceEnumerator.Instance  
```  
  
```csharp  
System.Data.Sql.SqlDataSourceEnumerator instance =   
   System.Data.Sql.SqlDataSourceEnumerator.Instance  
```  
  
 Nachdem Sie die statische Instanz abgerufen haben, können Sie die <xref:System.Data.Sql.SqlDataSourceEnumerator.GetDataSources%2A>-Methode aufrufen. Diese gibt eine <xref:System.Data.DataTable> mit den Informationen zu den verfügbaren Servern zurück:  
  
```vb  
Dim dataTable As System.Data.DataTable = instance.GetDataSources()  
```  
  
```csharp  
System.Data.DataTable dataTable = instance.GetDataSources();  
```  
  
 Die vom Methodenaufruf zurückgegebene Tabelle enthält die folgenden Spalten, die wiederum jeweils alle `string`-Werte enthalten:  
  
|Spalte|Beschreibung|  
|------------|-----------------|  
|**Servername**|Name des Servers.|  
|**InstanceName**|Name der Serverinstanz. Die Spalte bleibt leer, wenn der Server als Standardinstanz ausgeführt wird.|  
|**IsClustered**|Gibt an, ob der Server Teil eines Clusters ist.|  
|**Version**|Serverversion. Beispiel:<br /><br /> -9. x (SQL Server 2005)<br />-10.0. XX (SQL Server 2008)<br />-10.50. x (SQL Server 2008 R2)<br />-11.0. XX (SQL Server 2012)|  
  
## <a name="enumeration-limitations"></a>Einschränkungen bei der Enumeration  
 Möglicherweise werden nicht immer alle verfügbaren Server aufgelistet. Der Umfang der Liste kann je nach Faktoren wie Timeouts und Datenverkehr im Netzwerk variieren. Daher kann die Liste bei zwei aufeinander folgenden Aufrufen unterschiedlich ausfallen. Es werden nur Server aufgelistet, die sich im gleichen Netzwerk befinden. Da Broadcastpakete i. d. R. von Routern nicht weitergeleitet werden, wird möglicherweise ein verfügbarer Server nicht aufgelistet. Dieses Verhalten ist bei jedem Aufruf gleich.  
  
 Zu den aufgelisteten Servern werden ggf. zusätzliche Informationen aufgeführt, z. B. `IsClustered` oder die Version. Dies ist davon abhängig, wie die Liste abgerufen wurde. Es werden ausführlichere Informationen angezeigt, wenn die Server über den SQL Server-Browserdienst aufgelistet werden. Bei Servern, die über die Windows-Infrastruktur ermittelt werden, wird nur der Name aufgeführt.  
  
> [!NOTE]
> Serverenumeration ist nur in vollständig vertrauenswürdigen Umgebungen verfügbar. Assemblys, die in einer nur teilweise vertrauenswürdigen Umgebung ausgeführt werden, können die Enumeration nicht verwenden. Dies gilt auch, wenn sie über die <xref:System.Data.SqlClient.SqlClientPermission>-Codezugriffssicherheitsberechtigung (CAS) verfügen.  
  
 SQL Server stellt Informationen für die <xref:System.Data.Sql.SqlDataSourceEnumerator> durch die Verwendung eines externen Windows-Dienstanbieter namens SQL-Browser bereit. Dieser Dienst ist in der Standardeinstellung aktiviert, kann vom Administrator jedoch deaktiviert werden. Dadurch wird die Serverinstanz für diese Klasse unsichtbar.  
  
## <a name="example"></a>Beispiel  
 Die folgende Konsolenanwendung ruft Informationen zu allen sichtbaren Instanzen von SQL Server ab und zeigt diese Informationen im Konsolenfenster an.  
  
```vb  
Imports System.Data.Sql  
  
Module Module1  
  Sub Main()  
    ' Retrieve the enumerator instance and then the data.  
    Dim instance As SqlDataSourceEnumerator = _  
     SqlDataSourceEnumerator.Instance  
    Dim table As System.Data.DataTable = instance.GetDataSources()  
  
    ' Display the contents of the table.  
    DisplayData(table)  
  
    Console.WriteLine("Press any key to continue.")  
    Console.ReadKey()  
  End Sub  
  
  Private Sub DisplayData(ByVal table As DataTable)  
    For Each row As DataRow In table.Rows  
      For Each col As DataColumn In table.Columns  
        Console.WriteLine("{0} = {1}", col.ColumnName, row(col))  
      Next  
      Console.WriteLine("============================")  
    Next  
  End Sub  
End Module  
```  
  
```csharp  
using System.Data.Sql;  
  
class Program  
{  
  static void Main()  
  {  
    // Retrieve the enumerator instance and then the data.  
    SqlDataSourceEnumerator instance =  
      SqlDataSourceEnumerator.Instance;  
    System.Data.DataTable table = instance.GetDataSources();  
  
    // Display the contents of the table.  
    DisplayData(table);  
  
    Console.WriteLine("Press any key to continue.");  
    Console.ReadKey();  
  }  
  
  private static void DisplayData(System.Data.DataTable table)  
  {  
    foreach (System.Data.DataRow row in table.Rows)  
    {  
      foreach (System.Data.DataColumn col in table.Columns)  
      {  
        Console.WriteLine("{0} = {1}", col.ColumnName, row[col]);  
      }  
      Console.WriteLine("============================");  
    }  
  }  
}  
```  
  
## <a name="see-also"></a>Siehe auch

- [SQL Server und ADO.NET](index.md)
- [Übersicht über ADO.NET](../ado-net-overview.md)
