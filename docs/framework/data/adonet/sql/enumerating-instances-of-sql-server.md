---
title: Auflisten von Instanzen von SQL Server
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ddf1c83c-9d40-45e6-b04d-9828c6cbbfdc
ms.openlocfilehash: 2966157921894356836765edee6160d8e0f3e6e0
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91156133"
---
# <a name="enumerating-instances-of-sql-server-adonet"></a>Aufzählen von SQL Server-Instanzen (ADO.NET)

SQL Server ermöglicht es Anwendungen, SQL Server-Instanzen im aktuellen Netzwerk zu finden. Die <xref:System.Data.Sql.SqlDataSourceEnumerator>-Klasse stellt diese Informationen dem Anwendungsentwickler zur Verfügung, wobei eine <xref:System.Data.DataTable> Informationen zu allen sichtbaren Servern enthält. Diese zurückgegebene Tabelle enthält eine Liste der im Netzwerk verfügbaren Serverinstanzen. Diese Liste entspricht der Liste, die bereitgestellt wird, wenn ein Benutzer beim Erstellen einer neuen Verbindung im Dialogfeld **Verbindungseigenschaften** die Dropdownliste mit allen verfügbaren Servern erweitert. Die angezeigten Ergebnisse sind nicht immer vollständig.  
  
> [!NOTE]
> Wie bei den meisten Windows-Diensten ist es am besten, den SQL-Browser-Dienst mit den geringstmöglichen Rechten auszuführen. Weitere Informationen zum SQL-Browserdienst und dessen Verwaltung finden Sie in der SQL Server-Onlinedokumentation.  
  
## <a name="retrieving-an-enumerator-instance"></a>Abrufen einer Enumeratorinstanz  

 Damit Sie die Tabelle mit den Informationen zu den verfügbaren SQL Server-Instanzen abrufen können, müssen Sie zunächst einen Enumerator abrufen. Hierzu verwenden Sie die freigegebene/statische <xref:System.Data.Sql.SqlDataSourceEnumerator.Instance%2A>-Eigenschaft:  
  
```vb  
Dim instance As System.Data.Sql.SqlDataSourceEnumerator = _  
   System.Data.Sql.SqlDataSourceEnumerator.Instance  
```  
  
```csharp  
System.Data.Sql.SqlDataSourceEnumerator instance =
   System.Data.Sql.SqlDataSourceEnumerator.Instance  
```  
  
 Sobald Sie die statische Instanz abgerufen haben, können Sie die <xref:System.Data.Sql.SqlDataSourceEnumerator.GetDataSources%2A>-Methode aufrufen, die eine <xref:System.Data.DataTable> mit Informationen zu den verfügbaren Servern zurückgibt:  
  
```vb  
Dim dataTable As System.Data.DataTable = instance.GetDataSources()  
```  
  
```csharp  
System.Data.DataTable dataTable = instance.GetDataSources();  
```  
  
 Die vom Methodenaufruf zurückgegebene Tabelle enthält die folgenden Spalten, die allesamt `string`-Werte enthalten:  
  
|Column|Beschreibung|  
|------------|-----------------|  
|**ServerName**|Name des Servers.|  
|**InstanceName**|Name der Serverinstanz. Leer, wenn der Server als Standardinstanz ausgeführt wird.|  
|**IsClustered**|Gibt ab, ob die Serverinstanz zu einem Cluster gehört.|  
|**Version**|Die Version des Servers. Zum Beispiel:<br /><br /> - 9.00.x (SQL Server 2005)<br />10.0.xx (SQL Server 2008)<br />- 10.50.x (SQL Server 2008 R2)<br />11.0.xx (SQL Server 2012)|  
  
## <a name="enumeration-limitations"></a>Einschränkungen bei der Enumeration  

 Alle verfügbaren Server werden möglicherweise aufgelistet oder nicht. Die Liste kann je nach Faktoren wie Zeitlimits und Netzwerkdatenverkehr variieren. Dies kann dazu führen, dass die Liste bei zwei aufeinander folgenden Aufrufen unterschiedlich ist. Nur Server im selben Netzwerk werden aufgelistet. Übertragungspakete durchlaufen normalerweise keine Router, weshalb ein Server zwar ggf. nicht aufgelistet wird, aber aufrufübergreifend stabil bleibt.  
  
 Aufgelistete Server können zusätzliche Informationen wie `IsClustered` und die Version enthalten oder auch nicht. Dies hängt davon ab, wie die Liste abgerufen wurde. Es werden ausführlichere Informationen angezeigt, wenn die Server über den SQL Server-Browserdienst aufgelistet werden. Bei Servern, die über die Windows-Infrastruktur ermittelt werden, wird nur der Name aufgeführt.  
  
> [!NOTE]
> Die Serverenumeration ist nur verfügbar, wenn sie im vollständig vertrauenswürdigen Modus ausgeführt wird. Assemblys, die in einer teilweise vertrauenswürdigen Umgebung ausgeführt werden, können sie nicht verwenden, selbst wenn sie die CAS-Berechtigung (Code Access Security, Codezugriffssicherheit) <xref:System.Data.SqlClient.SqlClientPermission> haben.  
  
 SQL Server stellt Informationen für <xref:System.Data.Sql.SqlDataSourceEnumerator> mithilfe eines externen Windows-Diensts namens SQL-Browser bereit. Dieser Dienst ist standardmäßig aktiviert. Administratoren können ihn jedoch deaktivieren, sodass die Serverinstanz für diese Klasse nicht sichtbar ist.  
  
## <a name="example"></a>Beispiel  

 Die folgende Konsolenanwendung ruft Informationen zu allen sichtbaren SQL Server-Instanzen ab und zeigt die Informationen im Konsolenfenster an.  
  
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
  
## <a name="see-also"></a>Weitere Informationen

- [SQL Server und ADO.NET](index.md)
- [Übersicht über ADO.NET](../ado-net-overview.md)
