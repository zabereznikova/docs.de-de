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
ms.openlocfilehash: 99111cb9e48bd5ccd4463afcee6b78bc2387cf7b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="enumerating-instances-of-sql-server-adonet"></a><span data-ttu-id="c7616-102">Aufzählen von SQL Server-Instanzen (ADO.NET)</span><span class="sxs-lookup"><span data-stu-id="c7616-102">Enumerating Instances of SQL Server (ADO.NET)</span></span>
[!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]<span data-ttu-id="c7616-103"> ermöglicht Anwendungen die Suche von [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]-Instanzen im aktuellen Netzwerk.</span><span class="sxs-lookup"><span data-stu-id="c7616-103"> permits applications to find [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] instances within the current network.</span></span> <span data-ttu-id="c7616-104">Die hierzu erforderlichen Informationen werden den Entwicklern von Anwendungen durch die <xref:System.Data.Sql.SqlDataSourceEnumerator>-Klasse als <xref:System.Data.DataTable> verfügbar gemacht, die Informationen zu allen sichtbaren Servern enthält.</span><span class="sxs-lookup"><span data-stu-id="c7616-104">The <xref:System.Data.Sql.SqlDataSourceEnumerator> class exposes this information to the application developer, providing a <xref:System.Data.DataTable> containing information about all the visible servers.</span></span> <span data-ttu-id="c7616-105">Diese zurückgegebene Tabelle enthält eine Liste der verfügbaren im Netzwerk entspricht der Liste bereitgestellt, wenn ein Benutzer versucht, eine neue Verbindung zu erstellen, wird die Dropdown-Liste mit allen verfügbaren Servern erweitert Serverinstanzen die **Verbindung Eigenschaften** (Dialogfeld).</span><span class="sxs-lookup"><span data-stu-id="c7616-105">This returned table contains a list of server instances available on the network that matches the list provided when a user attempts to create a new connection, and expands the drop-down list containing all the available servers on the **Connection Properties** dialog box.</span></span> <span data-ttu-id="c7616-106">Die Liste der angezeigten Ergebnisse ist nicht immer vollständig.</span><span class="sxs-lookup"><span data-stu-id="c7616-106">The results displayed are not always complete.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c7616-107">Wie bei den meisten Windows-Diensten wird auch hier empfohlen, den SQL-Browserdienst mit minimalen Berechtigungen auszuführen.</span><span class="sxs-lookup"><span data-stu-id="c7616-107">As with most Windows services, it is best to run the SQL Browser service with the least possible privileges.</span></span> <span data-ttu-id="c7616-108">Weitere Informationen zum SQL-Browserdienst und dessen Verwaltung finden Sie in der [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]-Onlinedokumentation.</span><span class="sxs-lookup"><span data-stu-id="c7616-108">See [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] Books Online for more information on the SQL Browser service, and how to manage its behavior.</span></span>  
  
## <a name="retrieving-an-enumerator-instance"></a><span data-ttu-id="c7616-109">Abrufen einer Enumeratorinstanz</span><span class="sxs-lookup"><span data-stu-id="c7616-109">Retrieving an Enumerator Instance</span></span>  
 <span data-ttu-id="c7616-110">Damit Sie die Tabelle mit den Informationen zu den verfügbaren [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]-Instanzen abrufen können, müssen Sie zunächst einen Enumerator abrufen. Hierzu verwenden Sie die freigegebene/statische <xref:System.Data.Sql.SqlDataSourceEnumerator.Instance%2A>-Eigenschaft:</span><span class="sxs-lookup"><span data-stu-id="c7616-110">In order to retrieve the table containing information about the available [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] instances, you must first retrieve an enumerator, using the shared/static <xref:System.Data.Sql.SqlDataSourceEnumerator.Instance%2A> property:</span></span>  
  
```vb  
Dim instance As System.Data.Sql.SqlDataSourceEnumerator = _  
   System.Data.Sql.SqlDataSourceEnumerator.Instance  
```  
  
```csharp  
System.Data.Sql.SqlDataSourceEnumerator instance =   
   System.Data.Sql.SqlDataSourceEnumerator.Instance  
```  
  
 <span data-ttu-id="c7616-111">Nachdem Sie die statische Instanz abgerufen haben, können Sie die <xref:System.Data.Sql.SqlDataSourceEnumerator.GetDataSources%2A>-Methode aufrufen. Diese gibt eine <xref:System.Data.DataTable> mit den Informationen zu den verfügbaren Servern zurück:</span><span class="sxs-lookup"><span data-stu-id="c7616-111">Once you have retrieved the static instance, you can call the <xref:System.Data.Sql.SqlDataSourceEnumerator.GetDataSources%2A> method, which returns a <xref:System.Data.DataTable> containing information about the available servers:</span></span>  
  
```vb  
Dim dataTable As System.Data.DataTable = instance.GetDataSources()  
```  
  
```csharp  
System.Data.DataTable dataTable = instance.GetDataSources();  
```  
  
 <span data-ttu-id="c7616-112">Die vom Methodenaufruf zurückgegebene Tabelle enthält die folgenden Spalten, die wiederum jeweils alle `string`-Werte enthalten:</span><span class="sxs-lookup"><span data-stu-id="c7616-112">The table returned from the method call contains the following columns, all of which contain `string` values:</span></span>  
  
|<span data-ttu-id="c7616-113">Spalte</span><span class="sxs-lookup"><span data-stu-id="c7616-113">Column</span></span>|<span data-ttu-id="c7616-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c7616-114">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="c7616-115">**ServerName**</span><span class="sxs-lookup"><span data-stu-id="c7616-115">**ServerName**</span></span>|<span data-ttu-id="c7616-116">Name des Servers.</span><span class="sxs-lookup"><span data-stu-id="c7616-116">Name of the server.</span></span>|  
|<span data-ttu-id="c7616-117">**Instanzname**</span><span class="sxs-lookup"><span data-stu-id="c7616-117">**InstanceName**</span></span>|<span data-ttu-id="c7616-118">Name der Serverinstanz.</span><span class="sxs-lookup"><span data-stu-id="c7616-118">Name of the server instance.</span></span> <span data-ttu-id="c7616-119">Die Spalte bleibt leer, wenn der Server als Standardinstanz ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c7616-119">Blank if the server is running as the default instance.</span></span>|  
|<span data-ttu-id="c7616-120">**IsClustered**</span><span class="sxs-lookup"><span data-stu-id="c7616-120">**IsClustered**</span></span>|<span data-ttu-id="c7616-121">Gibt an, ob der Server Teil eines Clusters ist.</span><span class="sxs-lookup"><span data-stu-id="c7616-121">Indicates whether the server is part of a cluster.</span></span>|  
|<span data-ttu-id="c7616-122">**Version**</span><span class="sxs-lookup"><span data-stu-id="c7616-122">**Version**</span></span>|<span data-ttu-id="c7616-123">Serverversion.</span><span class="sxs-lookup"><span data-stu-id="c7616-123">Version of the server.</span></span> <span data-ttu-id="c7616-124">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="c7616-124">For example:</span></span><br /><br /> <span data-ttu-id="c7616-125">-9.00.x ([!INCLUDE[ssVersion2005](../../../../../includes/ssversion2005-md.md)])</span><span class="sxs-lookup"><span data-stu-id="c7616-125">-   9.00.x ([!INCLUDE[ssVersion2005](../../../../../includes/ssversion2005-md.md)])</span></span><br /><span data-ttu-id="c7616-126">-10.0.xx ([!INCLUDE[ssKatmai](../../../../../includes/sskatmai-md.md)])</span><span class="sxs-lookup"><span data-stu-id="c7616-126">-   10.0.xx ([!INCLUDE[ssKatmai](../../../../../includes/sskatmai-md.md)])</span></span><br /><span data-ttu-id="c7616-127">-10.50.x ([!INCLUDE[ssKilimanjaro](../../../../../includes/sskilimanjaro-md.md)])</span><span class="sxs-lookup"><span data-stu-id="c7616-127">-   10.50.x ([!INCLUDE[ssKilimanjaro](../../../../../includes/sskilimanjaro-md.md)])</span></span><br /><span data-ttu-id="c7616-128">-11.0.xx ([!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 2012)</span><span class="sxs-lookup"><span data-stu-id="c7616-128">-   11.0.xx ([!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 2012)</span></span>|  
  
## <a name="enumeration-limitations"></a><span data-ttu-id="c7616-129">Einschränkungen bei der Enumeration</span><span class="sxs-lookup"><span data-stu-id="c7616-129">Enumeration Limitations</span></span>  
 <span data-ttu-id="c7616-130">Möglicherweise werden nicht immer alle verfügbaren Server aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="c7616-130">All of the available servers may or may not be listed.</span></span> <span data-ttu-id="c7616-131">Der Umfang der Liste kann je nach Faktoren wie Timeouts und Datenverkehr im Netzwerk variieren.</span><span class="sxs-lookup"><span data-stu-id="c7616-131">The list can vary depending on factors such as timeouts and network traffic.</span></span> <span data-ttu-id="c7616-132">Daher kann die Liste bei zwei aufeinander folgenden Aufrufen unterschiedlich ausfallen.</span><span class="sxs-lookup"><span data-stu-id="c7616-132">This can cause the list to be different on two consecutive calls.</span></span> <span data-ttu-id="c7616-133">Es werden nur Server aufgelistet, die sich im gleichen Netzwerk befinden.</span><span class="sxs-lookup"><span data-stu-id="c7616-133">Only servers on the same network will be listed.</span></span> <span data-ttu-id="c7616-134">Da Broadcastpakete i. d. R. von Routern nicht weitergeleitet werden, wird möglicherweise ein verfügbarer Server nicht aufgelistet. Dieses Verhalten ist bei jedem Aufruf gleich.</span><span class="sxs-lookup"><span data-stu-id="c7616-134">Broadcast packets typically won't traverse routers, which is why you may not see a server listed, but it will be stable across calls.</span></span>  
  
 <span data-ttu-id="c7616-135">Zu den aufgelisteten Servern werden ggf. zusätzliche Informationen aufgeführt, z. B. `IsClustered` oder die Version.</span><span class="sxs-lookup"><span data-stu-id="c7616-135">Listed servers may or may not have additional information such as `IsClustered` and version.</span></span> <span data-ttu-id="c7616-136">Dies ist davon abhängig, wie die Liste abgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="c7616-136">This is dependent on how the list was obtained.</span></span> <span data-ttu-id="c7616-137">Es werden ausführlichere Informationen angezeigt, wenn die Server über den [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]-Browserdienst aufgelistet werden. Bei Servern, die über die Windows-Infrastruktur ermittelt werden, wird nur der Name aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="c7616-137">Servers listed through the [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] browser service will have more details than those found through the Windows infrastructure, which will list only the name.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c7616-138">Serverenumeration ist nur in vollständig vertrauenswürdigen Umgebungen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c7616-138">Server enumeration is only available when running in full-trust.</span></span> <span data-ttu-id="c7616-139">Assemblys, die in einer nur teilweise vertrauenswürdigen Umgebung ausgeführt werden, können die Enumeration nicht verwenden. Dies gilt auch, wenn sie über die <xref:System.Data.SqlClient.SqlClientPermission>-Codezugriffssicherheitsberechtigung (CAS) verfügen.</span><span class="sxs-lookup"><span data-stu-id="c7616-139">Assemblies running in a partially-trusted environment will not be able to use it, even if they have the <xref:System.Data.SqlClient.SqlClientPermission> Code Access Security (CAS) permission.</span></span>  
  
 [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]<span data-ttu-id="c7616-140"> stellt Informationen für <xref:System.Data.Sql.SqlDataSourceEnumerator> mithilfe eines externen Windows-Diensts namens SQL-Browser bereit.</span><span class="sxs-lookup"><span data-stu-id="c7616-140"> provides information for the <xref:System.Data.Sql.SqlDataSourceEnumerator> through the use of an external Windows service named SQL Browser.</span></span> <span data-ttu-id="c7616-141">Dieser Dienst ist in der Standardeinstellung aktiviert, kann vom Administrator jedoch deaktiviert werden. Dadurch wird die Serverinstanz für diese Klasse unsichtbar.</span><span class="sxs-lookup"><span data-stu-id="c7616-141">This service is enabled by default, but administrators may turn it off or disable it, making the server instance invisible to this class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c7616-142">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c7616-142">Example</span></span>  
 <span data-ttu-id="c7616-143">Die folgende Konsolenanwendung ruft Informationen zu allen sichtbaren [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]-Instanzen ab und zeigt die Informationen im Konsolenfenster an.</span><span class="sxs-lookup"><span data-stu-id="c7616-143">The following console application retrieves information about all of the visible [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] instances and displays the information in the console window.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="c7616-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c7616-144">See Also</span></span>  
 [<span data-ttu-id="c7616-145">SQL Server und ADO.NET</span><span class="sxs-lookup"><span data-stu-id="c7616-145">SQL Server and ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/index.md)  
 [<span data-ttu-id="c7616-146">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="c7616-146">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
