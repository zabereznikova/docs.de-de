---
title: Verwenden eines "DataSet" von einem XML-Webdienst aus
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 9edd6b71-0fa5-4649-ae1d-ac1c12541019
ms.openlocfilehash: d7328949e3eb4822b1a645bb5f0c1866f01ecb0a
ms.sourcegitcommit: c91110ef6ee3fedb591f3d628dc17739c4a7071e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/15/2020
ms.locfileid: "81389755"
---
# <a name="consume-a-dataset-from-an-xml-web-service"></a><span data-ttu-id="f7fee-102">Verwenden eines DataSets aus einem XML-Webdienst</span><span class="sxs-lookup"><span data-stu-id="f7fee-102">Consume a DataSet from an XML web service</span></span>

<span data-ttu-id="f7fee-103">Das <xref:System.Data.DataSet> wurde mit einer nicht verbundenen Struktur erstellt. Auf diese Art und Weise wird z. B. eine komfortable Übertragung von Daten über das Internet ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="f7fee-103">The <xref:System.Data.DataSet> was architected with a disconnected design, in part to facilitate the convenient transport of data over the Internet.</span></span> <span data-ttu-id="f7fee-104">Das **DataSet** ist "serialisierbar", da es als Eingabe für XML-Webdienste oder als Ausgabe von XML-Webdiensten angegeben werden kann, ohne dass zusätzliche Codierung erforderlich ist, um den Inhalt des **DataSets** von einem XML-Webdienst auf einen Client und zurück zu streamen.</span><span class="sxs-lookup"><span data-stu-id="f7fee-104">The **DataSet** is "serializable" in that it can be specified as an input to or output from XML Web services without any additional coding required to stream the contents of the **DataSet** from an XML Web service to a client and back.</span></span> <span data-ttu-id="f7fee-105">Das **DataSet** wird implizit im DiffGram-Format in einen XML-Stream konvertiert, über das Netzwerk gesendet und dann aus dem XML-Stream als **DataSet** auf dem empfangenden Ende rekonstruiert.</span><span class="sxs-lookup"><span data-stu-id="f7fee-105">The **DataSet** is implicitly converted to an XML stream using the DiffGram format, sent over the network, and then reconstructed from the XML stream as a **DataSet** on the receiving end.</span></span> <span data-ttu-id="f7fee-106">Dadurch steht Ihnen eine sehr einfache und flexible Methode zum Übertragen und Zurückübertragen von relationalen Daten mithilfe von XML-Webdiensten zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="f7fee-106">This gives you a very simple and flexible method for transmitting and returning relational data using XML Web services.</span></span> <span data-ttu-id="f7fee-107">Weitere Informationen zum DiffGram-Format finden Sie unter [DiffGrams](diffgrams.md).</span><span class="sxs-lookup"><span data-stu-id="f7fee-107">For more information about the DiffGram format, see [DiffGrams](diffgrams.md).</span></span>  
  
 <span data-ttu-id="f7fee-108">Das folgende Beispiel zeigt, wie Sie einen XML-Webdienst und -client erstellen, die das **DataSet** zum Transport relationaler Daten (einschließlich geänderter Daten) und zum Auflösen von Aktualisierungen in die ursprüngliche Datenquelle verwenden.</span><span class="sxs-lookup"><span data-stu-id="f7fee-108">The following example shows how to create an XML Web service and client that use the **DataSet** to transport relational data (including modified data) and resolve any updates back to the original data source.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f7fee-109">Es wird empfohlen, beim Erstellen eines XML-Webdiensts immer die Sicherheitsaspekte zu berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="f7fee-109">We recommend that you always consider security implications when creating an XML Web service.</span></span> <span data-ttu-id="f7fee-110">Informationen zum Sichern eines XML-Webdiensts finden Sie unter [Sichern von XML-Webdiensten,](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/w67h0dw7(v=vs.100))die mit ASP.NET erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="f7fee-110">For information on securing an XML Web service, see [Securing XML Web Services Created Using ASP.NET](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/w67h0dw7(v=vs.100)).</span></span>  
  
## <a name="create-an-xml-web-service"></a><span data-ttu-id="f7fee-111">Erstellen eines XML-Webdiensts</span><span class="sxs-lookup"><span data-stu-id="f7fee-111">Create an XML web service</span></span>
  
1. <span data-ttu-id="f7fee-112">Erstellen Sie den XML-Webdienst.</span><span class="sxs-lookup"><span data-stu-id="f7fee-112">Create the XML Web service.</span></span>  
  
     <span data-ttu-id="f7fee-113">Im Beispiel wird ein XML-Webdienst erstellt, der Daten zurückgibt, in diesem Fall eine Liste von Kunden aus der **Northwind-Datenbank,** und ein **DataSet** mit Aktualisierungen der Daten empfängt, die der XML-Webdienst in der ursprünglichen Datenquelle auflöst.</span><span class="sxs-lookup"><span data-stu-id="f7fee-113">In the example, an XML Web service is created that returns data, in this case a list of customers from the **Northwind** database, and receives a **DataSet** with updates to the data, which the XML Web service resolves back to the original data source.</span></span>  
  
     <span data-ttu-id="f7fee-114">Der XML-Webdienst macht zwei Methoden verfügbar: **GetCustomers**, um die Liste der Kunden zurückzugeben, und **UpdateCustomers**, um Aktualisierungen an die Datenquelle zurückzusenden.</span><span class="sxs-lookup"><span data-stu-id="f7fee-114">The XML Web service exposes two methods: **GetCustomers**, to return the list of customers, and **UpdateCustomers**, to resolve updates back to the data source.</span></span> <span data-ttu-id="f7fee-115">Der XML-Webdienst wird in einer Datei auf dem Webserver mit dem Namen "DataSetSample.asmx" gespeichert.</span><span class="sxs-lookup"><span data-stu-id="f7fee-115">The XML Web service is stored in a file on the Web server called DataSetSample.asmx.</span></span> <span data-ttu-id="f7fee-116">Im folgenden Code wird der Inhalt von "DataSetSample.asmx" dargestellt.</span><span class="sxs-lookup"><span data-stu-id="f7fee-116">The following code outlines the contents of DataSetSample.asmx.</span></span>  
  
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
  
     <span data-ttu-id="f7fee-117">In einem typischen Szenario wird die **UpdateCustomers-Methode** geschrieben, um optimistische Parallelitätsverletzungen abzufangen.</span><span class="sxs-lookup"><span data-stu-id="f7fee-117">In a typical scenario, the **UpdateCustomers** method would be written to catch optimistic concurrency violations.</span></span> <span data-ttu-id="f7fee-118">Zur Vereinfachung wurde in diesem Beispiel darauf verzichtet.</span><span class="sxs-lookup"><span data-stu-id="f7fee-118">For simplicity, the example does not include this.</span></span> <span data-ttu-id="f7fee-119">Weitere Informationen zur optimistischen Parallelität finden Sie unter [Optimistische Parallelität](../optimistic-concurrency.md).</span><span class="sxs-lookup"><span data-stu-id="f7fee-119">For more information about optimistic concurrency, see [Optimistic Concurrency](../optimistic-concurrency.md).</span></span>  
  
2. <span data-ttu-id="f7fee-120">Erstellen Sie einen XML-Webdienstproxy.</span><span class="sxs-lookup"><span data-stu-id="f7fee-120">Create an XML Web service proxy.</span></span>  
  
     <span data-ttu-id="f7fee-121">Clients des XML-Webdiensts benötigen einen SOAP-Proxy, um die verfügbar gemachten Methoden verarbeiten zu können.</span><span class="sxs-lookup"><span data-stu-id="f7fee-121">Clients of the XML Web service require a SOAP proxy in order to consume the exposed methods.</span></span> <span data-ttu-id="f7fee-122">Sie können diesen Proxy von Visual Studio generieren lassen.</span><span class="sxs-lookup"><span data-stu-id="f7fee-122">You can have Visual Studio generate this proxy for you.</span></span> <span data-ttu-id="f7fee-123">Das in diesem Schritt beschriebene Verhalten wird transparent, wenn Sie einen Webverweis auf einen vorhandenen Webdienst von Visual Studio aus festlegen.</span><span class="sxs-lookup"><span data-stu-id="f7fee-123">By setting a Web reference to an existing Web service from within Visual Studio, all the behavior described in this step occurs transparently.</span></span> <span data-ttu-id="f7fee-124">Wenn Sie die Proxyklasse selbst erstellen möchten, finden Sie im Folgenden die notwendigen Informationen.</span><span class="sxs-lookup"><span data-stu-id="f7fee-124">If you want to create the proxy class yourself, continue with this discussion.</span></span> <span data-ttu-id="f7fee-125">In den meisten Fällen ist es jedoch ausreichend, wenn die Proxyklasse für die Clientanwendung mithilfe von Visual Studio erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="f7fee-125">In most circumstances, however, using Visual Studio to create the proxy class for the client application is sufficient.</span></span>  
  
     <span data-ttu-id="f7fee-126">Ein Proxy kann mit dem Web Services Description Language-Tool erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="f7fee-126">A proxy can be created using the Web Services Description Language Tool.</span></span> <span data-ttu-id="f7fee-127">Wenn der XML-Webdienst z. B. unter der URL `http://myserver/data/DataSetSample.asmx`verfügbar gemacht wird, geben Sie einen Befehl wie den folgenden aus, um einen Visual Basic .NET-Proxy mit einem Namespace von **WebData.DSSample** zu erstellen und im Dateibeispiel zu speichern.vb.</span><span class="sxs-lookup"><span data-stu-id="f7fee-127">For example, if the XML Web service is exposed at the URL `http://myserver/data/DataSetSample.asmx`, issue a command such as the following to create a Visual Basic .NET proxy with a namespace of **WebData.DSSample** and store it in the file sample.vb.</span></span>  
  
    ```console
    wsdl /l:VB -out:sample.vb http://myserver/data/DataSetSample.asmx /n:WebData.DSSample  
    ```  
  
     <span data-ttu-id="f7fee-128">Zum Erstellen eines C#-Proxys in der Datei "sample.cs" verwenden Sie den folgenden Befehl:</span><span class="sxs-lookup"><span data-stu-id="f7fee-128">To create a C# proxy in the file sample.cs, issue the following command.</span></span>  
  
    ```console
    wsdl -l:CS -out:sample.cs http://myserver/data/DataSetSample.asmx -n:WebData.DSSample  
    ```  
  
     <span data-ttu-id="f7fee-129">Der Proxy kann dann als Bibliothek kompiliert und in einen XML-Webdienstclient importiert werden.</span><span class="sxs-lookup"><span data-stu-id="f7fee-129">The proxy can then be compiled as a library and imported into the XML Web service client.</span></span> <span data-ttu-id="f7fee-130">Zum Kompilieren des Visual Basic .NET-Proxycodes, der in der Datei "sample.vb" als "sample.dll" gespeichert wird, verwenden Sie den folgenden Befehl:</span><span class="sxs-lookup"><span data-stu-id="f7fee-130">To compile the Visual Basic .NET proxy code stored in sample.vb as sample.dll, issue the following command.</span></span>  
  
    ```console  
    vbc -t:library -out:sample.dll sample.vb -r:System.dll -r:System.Web.Services.dll -r:System.Data.dll -r:System.Xml.dll  
    ```  
  
     <span data-ttu-id="f7fee-131">Zum Kompilieren des C#-Proxycodes, der in der Datei "sample.vb" als "sample.dll" gespeichert wird, verwenden Sie den folgenden Befehl:</span><span class="sxs-lookup"><span data-stu-id="f7fee-131">To compile the C# proxy code stored in sample.cs as sample.dll, issue the following command.</span></span>  
  
    ```console
    csc -t:library -out:sample.dll sample.cs -r:System.dll -r:System.Web.Services.dll -r:System.Data.dll -r:System.Xml.dll  
    ```  
  
3. <span data-ttu-id="f7fee-132">Erstellen Sie einen XML-Webdienstclient.</span><span class="sxs-lookup"><span data-stu-id="f7fee-132">Create an XML Web service client.</span></span>  
  
     <span data-ttu-id="f7fee-133">Wenn Visual Studio die Webdienstproxyklasse für Sie generieren soll, erstellen Sie einfach das Clientprojekt, und klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das Projekt, und wählen Sie dann**Dienstreferenz** **hinzufügen** > aus.</span><span class="sxs-lookup"><span data-stu-id="f7fee-133">If you want to have Visual Studio generate the Web service proxy class for you, simply create the client project, and, in the Solution Explorer window, right-click the project, and then select **Add** > **Service Reference**.</span></span> <span data-ttu-id="f7fee-134">Wählen Sie im Dialogfeld **Dienstreferenz hinzufügen** die Option **Erweitert**aus, und wählen Sie dann **Webreferenz hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="f7fee-134">In the **Add Service Reference** dialog box, select **Advanced**, and then select **Add Web Reference**.</span></span> <span data-ttu-id="f7fee-135">Wählen Sie den Webdienst aus der Liste der verfügbaren Webdienste aus (dies erfordert möglicherweise die Angabe der Adresse des Webdienstendpunkts, wenn der Webdienst nicht innerhalb der aktuellen Lösung oder auf dem aktuellen Computer verfügbar ist).</span><span class="sxs-lookup"><span data-stu-id="f7fee-135">Select the Web service from the list of available Web services (this may require supplying the address of the Web service endpoint if the Web service isn't available within the current solution or on the current computer).</span></span> <span data-ttu-id="f7fee-136">Wenn Sie den XML-Webdienstproxy (wie im vorigen Schritt beschrieben) selbst erstellen, können Sie ihn in den Clientcode importieren und die XML-Webdienstmethoden verwenden.</span><span class="sxs-lookup"><span data-stu-id="f7fee-136">If you create the XML Web service proxy yourself (as described in the previous step), you can import it into your client code and consume the XML Web service methods.</span></span>

     <span data-ttu-id="f7fee-137">Der folgende Beispielcode importiert die Proxybibliothek, ruft **GetCustomers** auf, um eine Kundenliste abzubekommen, fügt einen neuen Kunden hinzu und gibt dann ein **DataSet** mit den Updates an **UpdateCustomers**zurück.</span><span class="sxs-lookup"><span data-stu-id="f7fee-137">The following sample code imports the proxy library, calls **GetCustomers** to get a list of customers, adds a new customer, and then returns a **DataSet** with the updates to **UpdateCustomers**.</span></span>  
  
     <span data-ttu-id="f7fee-138">Das Beispiel übergibt das von **DataSet.GetChanges** zurückgegebene **DataSet** an **UpdateCustomers,** da nur geänderte Zeilen an **UpdateCustomers**übergeben werden müssen.</span><span class="sxs-lookup"><span data-stu-id="f7fee-138">The example passes the **DataSet** returned by **DataSet.GetChanges** to **UpdateCustomers** because only modified rows need to be passed to **UpdateCustomers**.</span></span> <span data-ttu-id="f7fee-139">**UpdateCustomers** gibt das aufgelöste **DataSet**zurück, das Sie dann in das vorhandene **DataSet** **zusammenführen** können, um die behobenen Änderungen und alle Zeilenfehlerinformationen aus dem Update zu integrieren.</span><span class="sxs-lookup"><span data-stu-id="f7fee-139">**UpdateCustomers** returns the resolved **DataSet**, which you can then **Merge** into the existing **DataSet** to incorporate the resolved changes and any row error information from the update.</span></span> <span data-ttu-id="f7fee-140">Der folgende Code geht davon aus, dass Sie Visual Studio zum Erstellen des Webverweises verwendet haben und dass Sie den Webverweis im Dialogfeld **Webreferenz** hinzufügen in DsSample umbenannt haben.</span><span class="sxs-lookup"><span data-stu-id="f7fee-140">The following code assumes that you have used Visual Studio to create the Web reference, and that you have renamed the Web reference to DsSample in the **Add Web Reference** dialog box.</span></span>  
  
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
  
     <span data-ttu-id="f7fee-141">Wenn Sie sich entschlossen haben, die Proxyklasse selbst zu erstellen, müssen Sie die folgenden zusätzlichen Schritte ausführen.</span><span class="sxs-lookup"><span data-stu-id="f7fee-141">If you decide to create the proxy class yourself, you must take the following extra steps.</span></span> <span data-ttu-id="f7fee-142">Zum Kompilieren des Beispiels geben Sie die erstellte Proxybibliothek ("sample.dll") und die diesbezüglichen .NET-Bibliotheken an.</span><span class="sxs-lookup"><span data-stu-id="f7fee-142">To compile the sample, supply the proxy library that was created (sample.dll) and the related .NET libraries.</span></span> <span data-ttu-id="f7fee-143">Zum Kompilieren der Visual Basic .NET-Version des Beispiels, die in der Datei "client.vb" gespeichert wurde, verwenden Sie den folgenden Befehl:</span><span class="sxs-lookup"><span data-stu-id="f7fee-143">To compile the Visual Basic .NET version of the sample, stored in the file client.vb, issue the following command.</span></span>  
  
    ```console
    vbc client.vb -r:sample.dll -r:System.dll -r:System.Data.dll -r:System.Xml.dll -r:System.Web.Services.dll  
    ```  
  
     <span data-ttu-id="f7fee-144">Zum Kompilieren der C#-Version des Beispiels, die in der Datei "client.cs" gespeichert wurde, verwenden Sie den folgenden Befehl:</span><span class="sxs-lookup"><span data-stu-id="f7fee-144">To compile the C# version of the sample, stored in the file client.cs, issue the following command.</span></span>  
  
    ```console
    csc client.cs -r:sample.dll -r:System.dll -r:System.Data.dll -r:System.Xml.dll -r:System.Web.Services.dll  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="f7fee-145">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f7fee-145">See also</span></span>

- [<span data-ttu-id="f7fee-146">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="f7fee-146">ADO.NET</span></span>](../index.md)
- [<span data-ttu-id="f7fee-147">"DataSets", "DataTables" und "DataViews"</span><span class="sxs-lookup"><span data-stu-id="f7fee-147">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="f7fee-148">"DataTables"</span><span class="sxs-lookup"><span data-stu-id="f7fee-148">DataTables</span></span>](datatables.md)
- [<span data-ttu-id="f7fee-149">Auffüllen eines "DataSets" durch einen "DataAdapter"</span><span class="sxs-lookup"><span data-stu-id="f7fee-149">Populating a DataSet from a DataAdapter</span></span>](../populating-a-dataset-from-a-dataadapter.md)
- [<span data-ttu-id="f7fee-150">Aktualisieren von Datenquellen mit "DataAdapters"</span><span class="sxs-lookup"><span data-stu-id="f7fee-150">Updating Data Sources with DataAdapters</span></span>](../updating-data-sources-with-dataadapters.md)
- [<span data-ttu-id="f7fee-151">DataAdapter-Parameter</span><span class="sxs-lookup"><span data-stu-id="f7fee-151">DataAdapter Parameters</span></span>](../dataadapter-parameters.md)
- <span data-ttu-id="f7fee-152">[Web Services Description Language-Tool (Wsdl.exe)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7h3ystb6(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="f7fee-152">[Web Services Description Language Tool (Wsdl.exe)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7h3ystb6(v=vs.100))</span></span>
- [<span data-ttu-id="f7fee-153">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="f7fee-153">ADO.NET Overview</span></span>](../ado-net-overview.md)
