---
title: "Aufzählen von SQL Server-Instanzen (ADO.NET)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: ddf1c83c-9d40-45e6-b04d-9828c6cbbfdc
caps.latest.revision: "8"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 679196a6cc21705c8cc07e373a928f3c77c6befb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="enumerating-instances-of-sql-server-adonet"></a>Aufzählen von SQL Server-Instanzen (ADO.NET)
[!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] ermöglicht Anwendungen die Suche von [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]-Instanzen im aktuellen Netzwerk. Die hierzu erforderlichen Informationen werden den Entwicklern von Anwendungen durch die <xref:System.Data.Sql.SqlDataSourceEnumerator>-Klasse als <xref:System.Data.DataTable> verfügbar gemacht, die Informationen zu allen sichtbaren Servern enthält. Diese zurückgegebene Tabelle enthält eine Liste der verfügbaren im Netzwerk entspricht der Liste bereitgestellt, wenn ein Benutzer versucht, eine neue Verbindung zu erstellen, wird die Dropdown-Liste mit allen verfügbaren Servern erweitert Serverinstanzen die **Verbindung Eigenschaften** (Dialogfeld). Die Liste der angezeigten Ergebnisse ist nicht immer vollständig.  
  
> [!NOTE]
>  Wie bei den meisten Windows-Diensten wird auch hier empfohlen, den SQL-Browserdienst mit minimalen Berechtigungen auszuführen. Weitere Informationen zum SQL-Browserdienst und dessen Verwaltung finden Sie in der [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]-Onlinedokumentation.  
  
## <a name="retrieving-an-enumerator-instance"></a>Abrufen einer Enumeratorinstanz  
 Damit Sie die Tabelle mit den Informationen zu den verfügbaren [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]-Instanzen abrufen können, müssen Sie zunächst einen Enumerator abrufen. Hierzu verwenden Sie die freigegebene/statische <xref:System.Data.Sql.SqlDataSourceEnumerator.Instance%2A>-Eigenschaft:  
  
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
|**ServerName**|Name des Servers.|  
|**Instanzname**|Name der Serverinstanz. Die Spalte bleibt leer, wenn der Server als Standardinstanz ausgeführt wird.|  
|**IsClustered**|Gibt an, ob der Server Teil eines Clusters ist.|  
|**Version**|Serverversion. Zum Beispiel:<br /><br /> -9.00.x ([!INCLUDE[ssVersion2005](../../../../../includes/ssversion2005-md.md)])<br />-10.0.xx ([!INCLUDE[ssKatmai](../../../../../includes/sskatmai-md.md)])<br />-10.50.x ([!INCLUDE[ssKilimanjaro](../../../../../includes/sskilimanjaro-md.md)])<br />-11.0.xx ([!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 2012)|  
  
## <a name="enumeration-limitations"></a>Einschränkungen bei der Enumeration  
 Möglicherweise werden nicht immer alle verfügbaren Server aufgelistet. Der Umfang der Liste kann je nach Faktoren wie Timeouts und Datenverkehr im Netzwerk variieren. Daher kann die Liste bei zwei aufeinander folgenden Aufrufen unterschiedlich ausfallen. Es werden nur Server aufgelistet, die sich im gleichen Netzwerk befinden. Da Broadcastpakete i. d. R. von Routern nicht weitergeleitet werden, wird möglicherweise ein verfügbarer Server nicht aufgelistet. Dieses Verhalten ist bei jedem Aufruf gleich.  
  
 Zu den aufgelisteten Servern werden ggf. zusätzliche Informationen aufgeführt, z. B. `IsClustered` oder die Version. Dies ist davon abhängig, wie die Liste abgerufen wurde. Es werden ausführlichere Informationen angezeigt, wenn die Server über den [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]-Browserdienst aufgelistet werden. Bei Servern, die über die Windows-Infrastruktur ermittelt werden, wird nur der Name aufgeführt.  
  
> [!NOTE]
>  Serverenumeration ist nur in vollständig vertrauenswürdigen Umgebungen verfügbar. Assemblys, die in einer nur teilweise vertrauenswürdigen Umgebung ausgeführt werden, können die Enumeration nicht verwenden. Dies gilt auch, wenn sie über die <xref:System.Data.SqlClient.SqlClientPermission>-Codezugriffssicherheitsberechtigung (CAS) verfügen.  
  
 [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] stellt Informationen für <xref:System.Data.Sql.SqlDataSourceEnumerator> mithilfe eines externen Windows-Diensts namens SQL-Browser bereit. Dieser Dienst ist in der Standardeinstellung aktiviert, kann vom Administrator jedoch deaktiviert werden. Dadurch wird die Serverinstanz für diese Klasse unsichtbar.  
  
## <a name="example"></a>Beispiel  
 Die folgende Konsolenanwendung ruft Informationen zu allen sichtbaren [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]-Instanzen ab und zeigt die Informationen im Konsolenfenster an.  
  
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
 [SQL Server und ADO.NET](../../../../../docs/framework/data/adonet/sql/index.md)  
 [ADO.NET Managed Provider und DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917)
