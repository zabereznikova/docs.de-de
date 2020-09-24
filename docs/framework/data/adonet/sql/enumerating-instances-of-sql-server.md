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
# <a name="enumerating-instances-of-sql-server-adonet"></a><span data-ttu-id="af59c-102">Aufzählen von SQL Server-Instanzen (ADO.NET)</span><span class="sxs-lookup"><span data-stu-id="af59c-102">Enumerating Instances of SQL Server (ADO.NET)</span></span>

<span data-ttu-id="af59c-103">SQL Server ermöglicht es Anwendungen, SQL Server-Instanzen im aktuellen Netzwerk zu finden.</span><span class="sxs-lookup"><span data-stu-id="af59c-103">SQL Server permits applications to find SQL Server instances within the current network.</span></span> <span data-ttu-id="af59c-104">Die <xref:System.Data.Sql.SqlDataSourceEnumerator>-Klasse stellt diese Informationen dem Anwendungsentwickler zur Verfügung, wobei eine <xref:System.Data.DataTable> Informationen zu allen sichtbaren Servern enthält.</span><span class="sxs-lookup"><span data-stu-id="af59c-104">The <xref:System.Data.Sql.SqlDataSourceEnumerator> class exposes this information to the application developer, providing a <xref:System.Data.DataTable> containing information about all the visible servers.</span></span> <span data-ttu-id="af59c-105">Diese zurückgegebene Tabelle enthält eine Liste der im Netzwerk verfügbaren Serverinstanzen. Diese Liste entspricht der Liste, die bereitgestellt wird, wenn ein Benutzer beim Erstellen einer neuen Verbindung im Dialogfeld **Verbindungseigenschaften** die Dropdownliste mit allen verfügbaren Servern erweitert.</span><span class="sxs-lookup"><span data-stu-id="af59c-105">This returned table contains a list of server instances available on the network that matches the list provided when a user attempts to create a new connection, and expands the drop-down list containing all the available servers on the **Connection Properties** dialog box.</span></span> <span data-ttu-id="af59c-106">Die angezeigten Ergebnisse sind nicht immer vollständig.</span><span class="sxs-lookup"><span data-stu-id="af59c-106">The results displayed are not always complete.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="af59c-107">Wie bei den meisten Windows-Diensten ist es am besten, den SQL-Browser-Dienst mit den geringstmöglichen Rechten auszuführen.</span><span class="sxs-lookup"><span data-stu-id="af59c-107">As with most Windows services, it is best to run the SQL Browser service with the least possible privileges.</span></span> <span data-ttu-id="af59c-108">Weitere Informationen zum SQL-Browserdienst und dessen Verwaltung finden Sie in der SQL Server-Onlinedokumentation.</span><span class="sxs-lookup"><span data-stu-id="af59c-108">See SQL Server Books Online for more information on the SQL Browser service, and how to manage its behavior.</span></span>  
  
## <a name="retrieving-an-enumerator-instance"></a><span data-ttu-id="af59c-109">Abrufen einer Enumeratorinstanz</span><span class="sxs-lookup"><span data-stu-id="af59c-109">Retrieving an Enumerator Instance</span></span>  

 <span data-ttu-id="af59c-110">Damit Sie die Tabelle mit den Informationen zu den verfügbaren SQL Server-Instanzen abrufen können, müssen Sie zunächst einen Enumerator abrufen. Hierzu verwenden Sie die freigegebene/statische <xref:System.Data.Sql.SqlDataSourceEnumerator.Instance%2A>-Eigenschaft:</span><span class="sxs-lookup"><span data-stu-id="af59c-110">In order to retrieve the table containing information about the available SQL Server instances, you must first retrieve an enumerator, using the shared/static <xref:System.Data.Sql.SqlDataSourceEnumerator.Instance%2A> property:</span></span>  
  
```vb  
Dim instance As System.Data.Sql.SqlDataSourceEnumerator = _  
   System.Data.Sql.SqlDataSourceEnumerator.Instance  
```  
  
```csharp  
System.Data.Sql.SqlDataSourceEnumerator instance =
   System.Data.Sql.SqlDataSourceEnumerator.Instance  
```  
  
 <span data-ttu-id="af59c-111">Sobald Sie die statische Instanz abgerufen haben, können Sie die <xref:System.Data.Sql.SqlDataSourceEnumerator.GetDataSources%2A>-Methode aufrufen, die eine <xref:System.Data.DataTable> mit Informationen zu den verfügbaren Servern zurückgibt:</span><span class="sxs-lookup"><span data-stu-id="af59c-111">Once you have retrieved the static instance, you can call the <xref:System.Data.Sql.SqlDataSourceEnumerator.GetDataSources%2A> method, which returns a <xref:System.Data.DataTable> containing information about the available servers:</span></span>  
  
```vb  
Dim dataTable As System.Data.DataTable = instance.GetDataSources()  
```  
  
```csharp  
System.Data.DataTable dataTable = instance.GetDataSources();  
```  
  
 <span data-ttu-id="af59c-112">Die vom Methodenaufruf zurückgegebene Tabelle enthält die folgenden Spalten, die allesamt `string`-Werte enthalten:</span><span class="sxs-lookup"><span data-stu-id="af59c-112">The table returned from the method call contains the following columns, all of which contain `string` values:</span></span>  
  
|<span data-ttu-id="af59c-113">Column</span><span class="sxs-lookup"><span data-stu-id="af59c-113">Column</span></span>|<span data-ttu-id="af59c-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="af59c-114">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="af59c-115">**ServerName**</span><span class="sxs-lookup"><span data-stu-id="af59c-115">**ServerName**</span></span>|<span data-ttu-id="af59c-116">Name des Servers.</span><span class="sxs-lookup"><span data-stu-id="af59c-116">Name of the server.</span></span>|  
|<span data-ttu-id="af59c-117">**InstanceName**</span><span class="sxs-lookup"><span data-stu-id="af59c-117">**InstanceName**</span></span>|<span data-ttu-id="af59c-118">Name der Serverinstanz.</span><span class="sxs-lookup"><span data-stu-id="af59c-118">Name of the server instance.</span></span> <span data-ttu-id="af59c-119">Leer, wenn der Server als Standardinstanz ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="af59c-119">Blank if the server is running as the default instance.</span></span>|  
|<span data-ttu-id="af59c-120">**IsClustered**</span><span class="sxs-lookup"><span data-stu-id="af59c-120">**IsClustered**</span></span>|<span data-ttu-id="af59c-121">Gibt ab, ob die Serverinstanz zu einem Cluster gehört.</span><span class="sxs-lookup"><span data-stu-id="af59c-121">Indicates whether the server is part of a cluster.</span></span>|  
|<span data-ttu-id="af59c-122">**Version**</span><span class="sxs-lookup"><span data-stu-id="af59c-122">**Version**</span></span>|<span data-ttu-id="af59c-123">Die Version des Servers.</span><span class="sxs-lookup"><span data-stu-id="af59c-123">Version of the server.</span></span> <span data-ttu-id="af59c-124">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="af59c-124">For example:</span></span><br /><br /> <span data-ttu-id="af59c-125">- 9.00.x (SQL Server 2005)</span><span class="sxs-lookup"><span data-stu-id="af59c-125">-   9.00.x (SQL Server 2005)</span></span><br /><span data-ttu-id="af59c-126">10.0.xx (SQL Server 2008)</span><span class="sxs-lookup"><span data-stu-id="af59c-126">-   10.0.xx (SQL Server 2008)</span></span><br /><span data-ttu-id="af59c-127">- 10.50.x (SQL Server 2008 R2)</span><span class="sxs-lookup"><span data-stu-id="af59c-127">-   10.50.x (SQL Server 2008 R2)</span></span><br /><span data-ttu-id="af59c-128">11.0.xx (SQL Server 2012)</span><span class="sxs-lookup"><span data-stu-id="af59c-128">-   11.0.xx (SQL Server 2012)</span></span>|  
  
## <a name="enumeration-limitations"></a><span data-ttu-id="af59c-129">Einschränkungen bei der Enumeration</span><span class="sxs-lookup"><span data-stu-id="af59c-129">Enumeration Limitations</span></span>  

 <span data-ttu-id="af59c-130">Alle verfügbaren Server werden möglicherweise aufgelistet oder nicht.</span><span class="sxs-lookup"><span data-stu-id="af59c-130">All of the available servers may or may not be listed.</span></span> <span data-ttu-id="af59c-131">Die Liste kann je nach Faktoren wie Zeitlimits und Netzwerkdatenverkehr variieren.</span><span class="sxs-lookup"><span data-stu-id="af59c-131">The list can vary depending on factors such as timeouts and network traffic.</span></span> <span data-ttu-id="af59c-132">Dies kann dazu führen, dass die Liste bei zwei aufeinander folgenden Aufrufen unterschiedlich ist.</span><span class="sxs-lookup"><span data-stu-id="af59c-132">This can cause the list to be different on two consecutive calls.</span></span> <span data-ttu-id="af59c-133">Nur Server im selben Netzwerk werden aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="af59c-133">Only servers on the same network will be listed.</span></span> <span data-ttu-id="af59c-134">Übertragungspakete durchlaufen normalerweise keine Router, weshalb ein Server zwar ggf. nicht aufgelistet wird, aber aufrufübergreifend stabil bleibt.</span><span class="sxs-lookup"><span data-stu-id="af59c-134">Broadcast packets typically won't traverse routers, which is why you may not see a server listed, but it will be stable across calls.</span></span>  
  
 <span data-ttu-id="af59c-135">Aufgelistete Server können zusätzliche Informationen wie `IsClustered` und die Version enthalten oder auch nicht.</span><span class="sxs-lookup"><span data-stu-id="af59c-135">Listed servers may or may not have additional information such as `IsClustered` and version.</span></span> <span data-ttu-id="af59c-136">Dies hängt davon ab, wie die Liste abgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="af59c-136">This is dependent on how the list was obtained.</span></span> <span data-ttu-id="af59c-137">Es werden ausführlichere Informationen angezeigt, wenn die Server über den SQL Server-Browserdienst aufgelistet werden. Bei Servern, die über die Windows-Infrastruktur ermittelt werden, wird nur der Name aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="af59c-137">Servers listed through the SQL Server browser service will have more details than those found through the Windows infrastructure, which will list only the name.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="af59c-138">Die Serverenumeration ist nur verfügbar, wenn sie im vollständig vertrauenswürdigen Modus ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="af59c-138">Server enumeration is only available when running in full-trust.</span></span> <span data-ttu-id="af59c-139">Assemblys, die in einer teilweise vertrauenswürdigen Umgebung ausgeführt werden, können sie nicht verwenden, selbst wenn sie die CAS-Berechtigung (Code Access Security, Codezugriffssicherheit) <xref:System.Data.SqlClient.SqlClientPermission> haben.</span><span class="sxs-lookup"><span data-stu-id="af59c-139">Assemblies running in a partially-trusted environment will not be able to use it, even if they have the <xref:System.Data.SqlClient.SqlClientPermission> Code Access Security (CAS) permission.</span></span>  
  
 <span data-ttu-id="af59c-140">SQL Server stellt Informationen für <xref:System.Data.Sql.SqlDataSourceEnumerator> mithilfe eines externen Windows-Diensts namens SQL-Browser bereit.</span><span class="sxs-lookup"><span data-stu-id="af59c-140">SQL Server provides information for the <xref:System.Data.Sql.SqlDataSourceEnumerator> through the use of an external Windows service named SQL Browser.</span></span> <span data-ttu-id="af59c-141">Dieser Dienst ist standardmäßig aktiviert. Administratoren können ihn jedoch deaktivieren, sodass die Serverinstanz für diese Klasse nicht sichtbar ist.</span><span class="sxs-lookup"><span data-stu-id="af59c-141">This service is enabled by default, but administrators may turn it off or disable it, making the server instance invisible to this class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="af59c-142">Beispiel</span><span class="sxs-lookup"><span data-stu-id="af59c-142">Example</span></span>  

 <span data-ttu-id="af59c-143">Die folgende Konsolenanwendung ruft Informationen zu allen sichtbaren SQL Server-Instanzen ab und zeigt die Informationen im Konsolenfenster an.</span><span class="sxs-lookup"><span data-stu-id="af59c-143">The following console application retrieves information about all of the visible SQL Server instances and displays the information in the console window.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="af59c-144">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="af59c-144">See also</span></span>

- [<span data-ttu-id="af59c-145">SQL Server und ADO.NET</span><span class="sxs-lookup"><span data-stu-id="af59c-145">SQL Server and ADO.NET</span></span>](index.md)
- [<span data-ttu-id="af59c-146">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="af59c-146">ADO.NET Overview</span></span>](../ado-net-overview.md)
