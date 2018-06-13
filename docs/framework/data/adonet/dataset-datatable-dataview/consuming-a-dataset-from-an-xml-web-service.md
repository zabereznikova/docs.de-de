---
title: Verwenden eines "DataSet" von einem XML-Webdienst aus
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 9edd6b71-0fa5-4649-ae1d-ac1c12541019
ms.openlocfilehash: da3eca875df9b80f66241a2ecb72c5ba5c1df309
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32758840"
---
# <a name="consuming-a-dataset-from-an-xml-web-service"></a><span data-ttu-id="3600d-102">Verwenden eines "DataSet" von einem XML-Webdienst aus</span><span class="sxs-lookup"><span data-stu-id="3600d-102">Consuming a DataSet from an XML Web Service</span></span>
<span data-ttu-id="3600d-103">Das <xref:System.Data.DataSet> wurde mit einer nicht verbundenen Struktur erstellt. Auf diese Art und Weise wird z. B. eine komfortable Übertragung von Daten über das Internet ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="3600d-103">The <xref:System.Data.DataSet> was architected with a disconnected design, in part to facilitate the convenient transport of data over the Internet.</span></span> <span data-ttu-id="3600d-104">Die **DataSet** ist "serializable", als Eingabe für angegeben werden, oder Ausgabe aus XML-Webdiensten, ohne eine zusätzliche Codierung erforderlich, um den Inhalt zu streamen der **DataSet** aus einem XML-Webdienst zu einem Client und zurück.</span><span class="sxs-lookup"><span data-stu-id="3600d-104">The **DataSet** is "serializable" in that it can be specified as an input to or output from XML Web services without any additional coding required to stream the contents of the **DataSet** from an XML Web service to a client and back.</span></span> <span data-ttu-id="3600d-105">Die **DataSet** wird implizit in einen XML-Stream mit dem DiffGram-Format konvertiert, über das Netzwerk gesendet und dann aus dem XML-Stream als rekonstruiert ein **DataSet** auf der Empfängerseite.</span><span class="sxs-lookup"><span data-stu-id="3600d-105">The **DataSet** is implicitly converted to an XML stream using the DiffGram format, sent over the network, and then reconstructed from the XML stream as a **DataSet** on the receiving end.</span></span> <span data-ttu-id="3600d-106">Dadurch steht Ihnen eine sehr einfache und flexible Methode zum Übertragen und Zurückübertragen von relationalen Daten mithilfe von XML-Webdiensten zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="3600d-106">This gives you a very simple and flexible method for transmitting and returning relational data using XML Web services.</span></span> <span data-ttu-id="3600d-107">Weitere Informationen über das DiffGram-Format finden Sie unter [DiffGrams](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/diffgrams.md).</span><span class="sxs-lookup"><span data-stu-id="3600d-107">For more information about the DiffGram format, see [DiffGrams](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/diffgrams.md).</span></span>  
  
 <span data-ttu-id="3600d-108">Im folgende Beispiel wird gezeigt, wie zum Erstellen einer XML-Webdienst und den Client, mit denen die **DataSet** Übertragung relationaler Daten (einschließlich der geänderte Daten), und beheben Sie alle Updates zurück, an die ursprüngliche Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="3600d-108">The following example shows how to create an XML Web service and client that use the **DataSet** to transport relational data (including modified data) and resolve any updates back to the original data source.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3600d-109">Es wird empfohlen, beim Erstellen eines XML-Webdiensts immer die Sicherheitsaspekte zu berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="3600d-109">We recommend that you always consider security implications when creating an XML Web service.</span></span> <span data-ttu-id="3600d-110">Informationen zum Sichern von einem XML-Webdienst finden Sie unter [Sichern von mit ASP.NET erstellte XML-Webdienste Services](https://msdn.microsoft.com/library/354b2ab1-2782-4542-b32a-dc560178b90c).</span><span class="sxs-lookup"><span data-stu-id="3600d-110">For information on securing an XML Web service, see [Securing XML Web Services Created Using ASP.NET](https://msdn.microsoft.com/library/354b2ab1-2782-4542-b32a-dc560178b90c).</span></span>  
  
### <a name="to-create-an-xml-web-service-that-returns-and-consumes-a-dataset"></a><span data-ttu-id="3600d-111">So erstellen Sie einen XML-Webdienst, der ein "DataSet" zurückgibt und verarbeitet</span><span class="sxs-lookup"><span data-stu-id="3600d-111">To create an XML Web service that returns and consumes a DataSet</span></span>  
  
1.  <span data-ttu-id="3600d-112">Erstellen Sie den XML-Webdienst.</span><span class="sxs-lookup"><span data-stu-id="3600d-112">Create the XML Web service.</span></span>  
  
     <span data-ttu-id="3600d-113">Im Beispiel wird ein XML-Webdienst erstellt, das Daten zurückgibt, in diesem Fall eine Liste von Kunden aus der **Northwind** Datenbank, und erhält eine **DataSet** mit Updates, die die Daten der der XML-Webdienst Löst in der ursprünglichen Datenquelle zurück.</span><span class="sxs-lookup"><span data-stu-id="3600d-113">In the example, an XML Web service is created that returns data, in this case a list of customers from the **Northwind** database, and receives a **DataSet** with updates to the data, which the XML Web service resolves back to the original data source.</span></span>  
  
     <span data-ttu-id="3600d-114">Der XML-Webdienst stellt zwei Methoden: **GetCustomers**, um die Liste mit Kunden zurückzugeben und **UpdateCustomers**, um Updates an der Datenquelle zu beheben.</span><span class="sxs-lookup"><span data-stu-id="3600d-114">The XML Web service exposes two methods: **GetCustomers**, to return the list of customers, and **UpdateCustomers**, to resolve updates back to the data source.</span></span> <span data-ttu-id="3600d-115">Der XML-Webdienst wird in einer Datei auf dem Webserver mit dem Namen "DataSetSample.asmx" gespeichert.</span><span class="sxs-lookup"><span data-stu-id="3600d-115">The XML Web service is stored in a file on the Web server called DataSetSample.asmx.</span></span> <span data-ttu-id="3600d-116">Im folgenden Code wird der Inhalt von "DataSetSample.asmx" dargestellt.</span><span class="sxs-lookup"><span data-stu-id="3600d-116">The following code outlines the contents of DataSetSample.asmx.</span></span>  
  
    ```vb  
    <% @ WebService Language = "vb" Class = "Sample" %>  
    Imports System  
    Imports System.Data  
    Imports System.Data.SqlClient  
    Imports System.Web.Services  
  
    <WebService(Namespace:="http://microsoft.com/webservices/")> _  
    Public Class Sample  
  
    Public connection As SqlConnection = New SqlConnection("Data Source=(local);Integrated Security=SSPI;Initial Catalog=Northwind")  
  
      <WebMethod( Description := "Returns Northwind Customers", EnableSession := False )> _  
      Public Function GetCustomers() As DataSet  
        Dim adapter As SqlDataAdapter = New SqlDataAdapter( _  
          "SELECT CustomerID, CompanyName FROM Customers", connection)  
  
        Dim custDS As DataSet = New DataSet()  
        adapter.MissingSchemaAction = MissingSchemaAction.AddWithKey  
        adapter.Fill(custDS, "Customers")  
  
        Return custDS  
      End Function  
  
      <WebMethod( Description := "Updates Northwind Customers", EnableSession := False )> _  
      Public Function UpdateCustomers(custDS As DataSet) As DataSet  
        Dim adapter As SqlDataAdapter = New SqlDataAdapter()  
  
        adapter.InsertCommand = New SqlCommand( _  
          "INSERT INTO Customers (CustomerID, CompanyName) " & _  
          "Values(@CustomerID, @CompanyName)", connection)  
        adapter.InsertCommand.Parameters.Add( _  
          "@CustomerID", SqlDbType.NChar, 5, "CustomerID")  
        adapter.InsertCommand.Parameters.Add( _  
          "@CompanyName", SqlDbType.NChar, 15, "CompanyName")  
  
        adapter.UpdateCommand = New SqlCommand( _  
          "UPDATE Customers Set CustomerID = @CustomerID, " & _  
          "CompanyName = @CompanyName WHERE CustomerID = " & _  
          @OldCustomerID", connection)  
        adapter.UpdateCommand.Parameters.Add( _  
          "@CustomerID", SqlDbType.NChar, 5, "CustomerID")  
        adapter.UpdateCommand.Parameters.Add( _  
          "@CompanyName", SqlDbType.NChar, 15, "CompanyName")  
  
        Dim parameter As SqlParameter = _  
          adapter.UpdateCommand.Parameters.Add( _  
          "@OldCustomerID", SqlDbType.NChar, 5, "CustomerID")  
        parameter.SourceVersion = DataRowVersion.Original  
  
        adapter.DeleteCommand = New SqlCommand( _  
          "DELETE FROM Customers WHERE CustomerID = @CustomerID", _  
          connection)  
        parameter = adapter.DeleteCommand.Parameters.Add( _  
          "@CustomerID", SqlDbType.NChar, 5, "CustomerID")  
        parameter.SourceVersion = DataRowVersion.Original  
  
        adapter.Update(custDS, "Customers")  
  
        Return custDS  
      End Function  
    End Class  
    ```  
  
    ```csharp  
    <% @ WebService Language = "C#" Class = "Sample" %>  
    using System;  
    using System.Data;  
    using System.Data.SqlClient;  
    using System.Web.Services;  
  
    [WebService(Namespace="http://microsoft.com/webservices/")]  
    public class Sample  
    {  
      public SqlConnection connection = new SqlConnection("Data Source=(local);Integrated Security=SSPI;Initial Catalog=Northwind");  
  
      [WebMethod( Description = "Returns Northwind Customers", EnableSession = false )]  
      public DataSet GetCustomers()  
      {  
        SqlDataAdapter adapter = new SqlDataAdapter(  
          "SELECT CustomerID, CompanyName FROM Customers", connection);  
  
        DataSet custDS = new DataSet();  
        adapter.MissingSchemaAction = MissingSchemaAction.AddWithKey;  
        adapter.Fill(custDS, "Customers");  
  
        return custDS;  
      }  
  
      [WebMethod( Description = "Updates Northwind Customers",  
        EnableSession = false )]  
      public DataSet UpdateCustomers(DataSet custDS)  
      {  
        SqlDataAdapter adapter = new SqlDataAdapter();  
  
        adapter.InsertCommand = new SqlCommand(  
          "INSERT INTO Customers (CustomerID, CompanyName) " +  
          "Values(@CustomerID, @CompanyName)", connection);  
        adapter.InsertCommand.Parameters.Add(  
          "@CustomerID", SqlDbType.NChar, 5, "CustomerID");  
        adapter.InsertCommand.Parameters.Add(  
          "@CompanyName", SqlDbType.NChar, 15, "CompanyName");  
  
        adapter.UpdateCommand = new SqlCommand(  
          "UPDATE Customers Set CustomerID = @CustomerID, " +  
          "CompanyName = @CompanyName WHERE CustomerID = " +  
          "@OldCustomerID", connection);  
        adapter.UpdateCommand.Parameters.Add(  
          "@CustomerID", SqlDbType.NChar, 5, "CustomerID");  
        adapter.UpdateCommand.Parameters.Add(  
          "@CompanyName", SqlDbType.NChar, 15, "CompanyName");  
        SqlParameter parameter = adapter.UpdateCommand.Parameters.Add(  
          "@OldCustomerID", SqlDbType.NChar, 5, "CustomerID");  
        parameter.SourceVersion = DataRowVersion.Original;  
  
        adapter.DeleteCommand = new SqlCommand(  
        "DELETE FROM Customers WHERE CustomerID = @CustomerID",  
         connection);  
        parameter = adapter.DeleteCommand.Parameters.Add(  
          "@CustomerID", SqlDbType.NChar, 5, "CustomerID");  
        parameter.SourceVersion = DataRowVersion.Original;  
  
        adapter.Update(custDS, "Customers");  
  
        return custDS;  
      }  
    }  
    ```  
  
     <span data-ttu-id="3600d-117">In einem typischen Szenario die **UpdateCustomers** Methode würde geschrieben werden, um Verletzung der vollständigen Parallelität abzufangen.</span><span class="sxs-lookup"><span data-stu-id="3600d-117">In a typical scenario, the **UpdateCustomers** method would be written to catch optimistic concurrency violations.</span></span> <span data-ttu-id="3600d-118">Zur Vereinfachung wurde in diesem Beispiel darauf verzichtet.</span><span class="sxs-lookup"><span data-stu-id="3600d-118">For simplicity, the example does not include this.</span></span> <span data-ttu-id="3600d-119">Weitere Informationen zur vollständigen Parallelität finden Sie unter [vollständige Parallelität](../../../../../docs/framework/data/adonet/optimistic-concurrency.md).</span><span class="sxs-lookup"><span data-stu-id="3600d-119">For more information about optimistic concurrency, see [Optimistic Concurrency](../../../../../docs/framework/data/adonet/optimistic-concurrency.md).</span></span>  
  
2.  <span data-ttu-id="3600d-120">Erstellen Sie einen XML-Webdienstproxy.</span><span class="sxs-lookup"><span data-stu-id="3600d-120">Create an XML Web service proxy.</span></span>  
  
     <span data-ttu-id="3600d-121">Clients des XML-Webdiensts benötigen einen SOAP-Proxy, um die verfügbar gemachten Methoden verarbeiten zu können.</span><span class="sxs-lookup"><span data-stu-id="3600d-121">Clients of the XML Web service require a SOAP proxy in order to consume the exposed methods.</span></span> <span data-ttu-id="3600d-122">Sie können diesen Proxy von Visual Studio generieren lassen.</span><span class="sxs-lookup"><span data-stu-id="3600d-122">You can have Visual Studio generate this proxy for you.</span></span> <span data-ttu-id="3600d-123">Das in diesem Schritt beschriebene Verhalten wird transparent, wenn Sie einen Webverweis auf einen vorhandenen Webdienst von Visual Studio aus festlegen.</span><span class="sxs-lookup"><span data-stu-id="3600d-123">By setting a Web reference to an existing Web service from within Visual Studio, all the behavior described in this step occurs transparently.</span></span> <span data-ttu-id="3600d-124">Wenn Sie die Proxyklasse selbst erstellen möchten, finden Sie im Folgenden die notwendigen Informationen.</span><span class="sxs-lookup"><span data-stu-id="3600d-124">If you want to create the proxy class yourself, continue with this discussion.</span></span> <span data-ttu-id="3600d-125">In den meisten Fällen ist es jedoch ausreichend, wenn die Proxyklasse für die Clientanwendung mithilfe von Visual Studio erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="3600d-125">In most circumstances, however, using Visual Studio to create the proxy class for the client application is sufficient.</span></span>  
  
     <span data-ttu-id="3600d-126">Ein Proxy kann mit dem Web Services Description Language-Tool erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="3600d-126">A proxy can be created using the Web Services Description Language Tool.</span></span> <span data-ttu-id="3600d-127">Angenommen, die XML-Webdienst verfügbar gemacht wird, an der URL http://myserver/data/DataSetSample.asmx, geben Sie einen Befehl wie folgt So erstellen Sie einen Visual Basic .NET Proxy mit dem Namespace **http://myserver/data/DataSetSample.asmx** und in der Datei Datei "Sample.vb" zu speichern.</span><span class="sxs-lookup"><span data-stu-id="3600d-127">For example, if the XML Web service is exposed at the URL http://myserver/data/DataSetSample.asmx, issue a command such as the following to create a Visual Basic .NET proxy with a namespace of **WebData.DSSample** and store it in the file sample.vb.</span></span>  
  
    ```console
    wsdl /l:VB -out:sample.vb http://myserver/data/DataSetSample.asmx /n:WebData.DSSample  
    ```  
  
     <span data-ttu-id="3600d-128">Zum Erstellen eines C#-Proxys in der Datei "sample.cs" verwenden Sie den folgenden Befehl:</span><span class="sxs-lookup"><span data-stu-id="3600d-128">To create a C# proxy in the file sample.cs, issue the following command.</span></span>  
  
    ```console
    wsdl -l:CS -out:sample.cs http://myserver/data/DataSetSample.asmx -n:WebData.DSSample  
    ```  
  
     <span data-ttu-id="3600d-129">Der Proxy kann dann als Bibliothek kompiliert und in einen XML-Webdienstclient importiert werden.</span><span class="sxs-lookup"><span data-stu-id="3600d-129">The proxy can then be compiled as a library and imported into the XML Web service client.</span></span> <span data-ttu-id="3600d-130">Zum Kompilieren des Visual Basic .NET-Proxycodes, der in der Datei "sample.vb" als "sample.dll" gespeichert wird, verwenden Sie den folgenden Befehl:</span><span class="sxs-lookup"><span data-stu-id="3600d-130">To compile the Visual Basic .NET proxy code stored in sample.vb as sample.dll, issue the following command.</span></span>  
  
    ```console  
    vbc -t:library -out:sample.dll sample.vb -r:System.dll -r:System.Web.Services.dll -r:System.Data.dll -r:System.Xml.dll  
    ```  
  
     <span data-ttu-id="3600d-131">Zum Kompilieren des C#-Proxycodes, der in der Datei "sample.vb" als "sample.dll" gespeichert wird, verwenden Sie den folgenden Befehl:</span><span class="sxs-lookup"><span data-stu-id="3600d-131">To compile the C# proxy code stored in sample.cs as sample.dll, issue the following command.</span></span>  
  
    ```console
    csc -t:library -out:sample.dll sample.cs -r:System.dll -r:System.Web.Services.dll -r:System.Data.dll -r:System.Xml.dll  
    ```  
  
3.  <span data-ttu-id="3600d-132">Erstellen Sie einen XML-Webdienstclient.</span><span class="sxs-lookup"><span data-stu-id="3600d-132">Create an XML Web service client.</span></span>  
  
     <span data-ttu-id="3600d-133">Wenn Sie Visual Studio die Webdienst-Proxyklasse für Sie generiert haben möchten, einfach das Client-Projekt erstellen und im Fenster Projektmappen-Explorer das Projekt der rechten Maustaste auf **Webverweis hinzufügen**, und wählen Sie den Webdienst aus die Liste der verfügbaren Webdienste (Dies erfordert möglicherweise die Adresse des Webdienst-Endpunkts, wenn der Webdienst nicht innerhalb der aktuellen Projektmappe oder auf dem aktuellen Computer verfügbar ist.) Wenn Sie den XML-Webdienstproxy (wie im vorigen Schritt beschrieben) selbst erstellen, können Sie ihn in den Clientcode importieren und die XML-Webdienstmethoden verwenden.</span><span class="sxs-lookup"><span data-stu-id="3600d-133">If you want to have Visual Studio generate the Web service proxy class for you, simply create the client project, and, in the Solution Explorer window, right-click the project, click **Add Web Reference**, and select the Web service from the list of available Web services (this may require supplying the address of the Web service endpoint, if the Web service isn't available within the current solution, or on the current computer.) If you create the XML Web service proxy yourself (as described in the previous step), you can import it into your client code and consume the XML Web service methods.</span></span> <span data-ttu-id="3600d-134">Im folgenden Beispielcode wird die Proxybibliothek, Aufrufe importiert **GetCustomers** zum Abrufen einer Liste von Kunden, fügt einen neuen Kunden und gibt dann eine **DataSet** mit den Updates **UpdateCustomers** .</span><span class="sxs-lookup"><span data-stu-id="3600d-134">The following sample code imports the proxy library, calls **GetCustomers** to get a list of customers, adds a new customer, and then returns a **DataSet** with the updates to **UpdateCustomers**.</span></span>  
  
     <span data-ttu-id="3600d-135">Beachten Sie, die das Beispiel übergibt die **DataSet** zurückgegebenes **DataSet.GetChanges** auf **UpdateCustomers** da nur geänderte Zeilen übergeben werden müssen  **UpdateCustomers**.</span><span class="sxs-lookup"><span data-stu-id="3600d-135">Notice that the example passes the **DataSet** returned by **DataSet.GetChanges** to **UpdateCustomers** because only modified rows need to be passed to **UpdateCustomers**.</span></span> <span data-ttu-id="3600d-136">**UpdateCustomers** gibt das aufgelöste **DataSet**, die Sie dann **Merge** mit dem vorhandenen **DataSet** die aufgelösten Änderungen und alle integriert Zeilenfehlerinformationen aus dem Update.</span><span class="sxs-lookup"><span data-stu-id="3600d-136">**UpdateCustomers** returns the resolved **DataSet**, which you can then **Merge** into the existing **DataSet** to incorporate the resolved changes and any row error information from the update.</span></span> <span data-ttu-id="3600d-137">Im folgende Code wird davon ausgegangen, dass Sie Visual Studio verwendet haben, um den Webverweis zu erstellen und Sie den Webverweis DsSample umbenannt haben die **Webverweis hinzufügen** (Dialogfeld).</span><span class="sxs-lookup"><span data-stu-id="3600d-137">The following code assumes that you have used Visual Studio to create the Web reference, and that you have renamed the Web reference to DsSample in the **Add Web Reference** dialog box.</span></span>  
  
    ```vb  
    Imports System  
    Imports System.Data  
  
    Public Class Client  
  
      Public Shared Sub Main()  
        Dim proxySample As New DsSample.Sample ()  ' Proxy object.  
        Dim customersDataSet As DataSet = proxySample.GetCustomers()  
        Dim customersTable As DataTable = _  
          customersDataSet.Tables("Customers")  
  
        Dim rowAs DataRow = customersTable.NewRow()  
        row("CustomerID") = "ABCDE"  
        row("CompanyName") = "New Company Name"  
        customersTable.Rows.Add(row)  
  
        Dim updateDataSet As DataSet = _  
          proxySample.UpdateCustomers(customersDataSet.GetChanges())  
  
        customersDataSet.Merge(updateDataSet)  
        customersDataSet.AcceptChanges()  
      End Sub  
    End Class  
    ```  
  
    ```csharp  
    using System;  
    using System.Data;  
  
    public class Client  
    {  
      public static void Main()  
      {  
        Sample proxySample = new DsSample.Sample();  // Proxy object.  
        DataSet customersDataSet = proxySample.GetCustomers();  
        DataTable customersTable = customersDataSet.Tables["Customers"];  
  
        DataRow row = customersTable.NewRow();  
        row["CustomerID"] = "ABCDE";  
        row["CompanyName"] = "New Company Name";  
        customersTable.Rows.Add(row);  
  
        DataSet updateDataSet = new DataSet();  
  
        updateDataSet =   
          proxySample.UpdateCustomers(customersDataSet.GetChanges());  
  
        customersDataSet.Merge(updateDataSet);  
        customersDataSet.AcceptChanges();  
      }  
    }  
    ```  
  
     <span data-ttu-id="3600d-138">Wenn Sie sich entschlossen haben, die Proxyklasse selbst zu erstellen, müssen Sie die folgenden zusätzlichen Schritte ausführen.</span><span class="sxs-lookup"><span data-stu-id="3600d-138">If you decide to create the proxy class yourself, you must take the following extra steps.</span></span> <span data-ttu-id="3600d-139">Zum Kompilieren des Beispiels geben Sie die erstellte Proxybibliothek ("sample.dll") und die diesbezüglichen .NET-Bibliotheken an.</span><span class="sxs-lookup"><span data-stu-id="3600d-139">To compile the sample, supply the proxy library that was created (sample.dll) and the related .NET libraries.</span></span> <span data-ttu-id="3600d-140">Zum Kompilieren der Visual Basic .NET-Version des Beispiels, die in der Datei "client.vb" gespeichert wurde, verwenden Sie den folgenden Befehl:</span><span class="sxs-lookup"><span data-stu-id="3600d-140">To compile the Visual Basic .NET version of the sample, stored in the file client.vb, issue the following command.</span></span>  
  
    ```console
    vbc client.vb -r:sample.dll -r:System.dll -r:System.Data.dll -r:System.Xml.dll -r:System.Web.Services.dll  
    ```  
  
     <span data-ttu-id="3600d-141">Zum Kompilieren der C#-Version des Beispiels, die in der Datei "client.cs" gespeichert wurde, verwenden Sie den folgenden Befehl:</span><span class="sxs-lookup"><span data-stu-id="3600d-141">To compile the C# version of the sample, stored in the file client.cs, issue the following command.</span></span>  
  
    ```console
    csc client.cs -r:sample.dll -r:System.dll -r:System.Data.dll -r:System.Xml.dll -r:System.Web.Services.dll  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="3600d-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3600d-142">See Also</span></span>  
 [<span data-ttu-id="3600d-143">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="3600d-143">ADO.NET</span></span>](../../../../../docs/framework/data/adonet/index.md)  
 [<span data-ttu-id="3600d-144">DataSets, DataTables und DataViews</span><span class="sxs-lookup"><span data-stu-id="3600d-144">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="3600d-145">DataTables</span><span class="sxs-lookup"><span data-stu-id="3600d-145">DataTables</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)  
 [<span data-ttu-id="3600d-146">Populating a DataSet from a DataAdapter (Auffüllen eines DataSets durch einen DataAdapter)</span><span class="sxs-lookup"><span data-stu-id="3600d-146">Populating a DataSet from a DataAdapter</span></span>](../../../../../docs/framework/data/adonet/populating-a-dataset-from-a-dataadapter.md)  
 [<span data-ttu-id="3600d-147">Updating Data Sources with DataAdapters (Aktualisieren von Datenquellen mit DataAdapters)</span><span class="sxs-lookup"><span data-stu-id="3600d-147">Updating Data Sources with DataAdapters</span></span>](../../../../../docs/framework/data/adonet/updating-data-sources-with-dataadapters.md)  
 [<span data-ttu-id="3600d-148">DataAdapter-Parameter</span><span class="sxs-lookup"><span data-stu-id="3600d-148">DataAdapter Parameters</span></span>](../../../../../docs/framework/data/adonet/dataadapter-parameters.md)  
 [<span data-ttu-id="3600d-149">Web Services Description Language Tool (Wsdl.exe)</span><span class="sxs-lookup"><span data-stu-id="3600d-149">Web Services Description Language Tool (Wsdl.exe)</span></span>](https://msdn.microsoft.com/library/b9210348-8bc2-4367-8c91-d1a04b403e88)  
 [<span data-ttu-id="3600d-150">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="3600d-150">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
