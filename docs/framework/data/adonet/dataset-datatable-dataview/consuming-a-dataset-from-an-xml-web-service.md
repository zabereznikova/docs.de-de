---
title: Verwenden eines "DataSet" von einem XML-Webdienst aus
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 9edd6b71-0fa5-4649-ae1d-ac1c12541019
ms.openlocfilehash: e07fd6598d6b2d1bbd52e5e6735264821b8986bf
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59180244"
---
# <a name="consuming-a-dataset-from-an-xml-web-service"></a>Verwenden eines "DataSet" von einem XML-Webdienst aus
Das <xref:System.Data.DataSet> wurde mit einer nicht verbundenen Struktur erstellt. Auf diese Art und Weise wird z. B. eine komfortable Übertragung von Daten über das Internet ermöglicht. Die **DataSet** ist "serializable" insofern, als Eingabe für angegeben werden oder Ausgabe aus XML-Webdiensten, ohne eine zusätzliche Codierung erforderlich, um den Inhalt der Streamen der **DataSet** aus einem XML-Webdienst zu einem Client und zurück. Die **DataSet** implizit in einen XML-Stream mit dem DiffGram-Format konvertiert, über das Netzwerk gesendet und dann aus der XML-Stream rekonstruiert eine **DataSet** auf der Empfangsseite. Dadurch steht Ihnen eine sehr einfache und flexible Methode zum Übertragen und Zurückübertragen von relationalen Daten mithilfe von XML-Webdiensten zur Verfügung. Weitere Informationen zum DiffGram-Format finden Sie unter [DiffGrams](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/diffgrams.md).  
  
 Das folgende Beispiel zeigt die Vorgehensweise: Erstellen einer XML-Webdienst und den Client, mit denen die **DataSet** Übertragung relationaler Daten (einschließlich der geänderte Daten), und beheben alle Updates zurück an die ursprüngliche Datenquelle.  
  
> [!NOTE]
>  Es wird empfohlen, beim Erstellen eines XML-Webdiensts immer die Sicherheitsaspekte zu berücksichtigen. Informationen zum Sichern eines XML-Webdiensts finden Sie unter [schützen mithilfe von ASP.NET erstellte XML-Web-Dienste](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/w67h0dw7(v=vs.100)).  
  
### <a name="to-create-an-xml-web-service-that-returns-and-consumes-a-dataset"></a>So erstellen Sie einen XML-Webdienst, der ein "DataSet" zurückgibt und verarbeitet  
  
1.  Erstellen Sie den XML-Webdienst.  
  
     Im Beispiel wird ein XML-Webdienst erstellt, die Daten in diesem Fall eine Liste der Kunden zurückgibt der **Northwind** Datenbank, und empfängt eine **DataSet** mit Updates, die die Daten, die den XML-Webdienst Löst in der ursprünglichen Datenquelle zurück.  
  
     Der XML-Webdienst macht zwei Methoden verfügbar: **GetCustomers**, um die Liste der Kunden zurückzugeben und **UpdateCustomers**, um Updates in der Datenquelle abzugleichen. Der XML-Webdienst wird in einer Datei auf dem Webserver mit dem Namen "DataSetSample.asmx" gespeichert. Im folgenden Code wird der Inhalt von "DataSetSample.asmx" dargestellt.  
  
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
  
     In einem typischen Szenario stellt die **UpdateCustomers** Methode würde geschrieben werden, um Verletzung der vollständigen Parallelität abzufangen. Zur Vereinfachung wurde in diesem Beispiel darauf verzichtet. Weitere Informationen zur vollständigen Parallelität finden Sie unter [optimistische Parallelität](../../../../../docs/framework/data/adonet/optimistic-concurrency.md).  
  
2.  Erstellen Sie einen XML-Webdienstproxy.  
  
     Clients des XML-Webdiensts benötigen einen SOAP-Proxy, um die verfügbar gemachten Methoden verarbeiten zu können. Sie können diesen Proxy von Visual Studio generieren lassen. Das in diesem Schritt beschriebene Verhalten wird transparent, wenn Sie einen Webverweis auf einen vorhandenen Webdienst von Visual Studio aus festlegen. Wenn Sie die Proxyklasse selbst erstellen möchten, finden Sie im Folgenden die notwendigen Informationen. In den meisten Fällen ist es jedoch ausreichend, wenn die Proxyklasse für die Clientanwendung mithilfe von Visual Studio erstellt wird.  
  
     Ein Proxy kann mit dem Web Services Description Language-Tool erstellt werden. Wenn der XML-Webdienst verfügbar gemacht wird, unter der URL beispielsweise `http://myserver/data/DataSetSample.asmx`, einen Befehl wie den folgenden erstellen Sie einen Proxy für die Visual Basic .NET mit dem Namespace **WebData.DSSample** und in der Datei Datei "Sample.vb" zu speichern.  
  
    ```console
    wsdl /l:VB -out:sample.vb http://myserver/data/DataSetSample.asmx /n:WebData.DSSample  
    ```  
  
     Zum Erstellen eines C#-Proxys in der Datei "sample.cs" verwenden Sie den folgenden Befehl:  
  
    ```console
    wsdl -l:CS -out:sample.cs http://myserver/data/DataSetSample.asmx -n:WebData.DSSample  
    ```  
  
     Der Proxy kann dann als Bibliothek kompiliert und in einen XML-Webdienstclient importiert werden. Zum Kompilieren des Visual Basic .NET-Proxycodes, der in der Datei "sample.vb" als "sample.dll" gespeichert wird, verwenden Sie den folgenden Befehl:  
  
    ```console  
    vbc -t:library -out:sample.dll sample.vb -r:System.dll -r:System.Web.Services.dll -r:System.Data.dll -r:System.Xml.dll  
    ```  
  
     Zum Kompilieren des C#-Proxycodes, der in der Datei "sample.vb" als "sample.dll" gespeichert wird, verwenden Sie den folgenden Befehl:  
  
    ```console
    csc -t:library -out:sample.dll sample.cs -r:System.dll -r:System.Web.Services.dll -r:System.Data.dll -r:System.Xml.dll  
    ```  
  
3.  Erstellen Sie einen XML-Webdienstclient.  
  
     Wenn Sie Visual Studio die Webdienst-Proxyklasse für Sie generiert haben möchten, einfach Client-Projekt erstellen und im Fenster Projektmappen-Explorer das Projekt der rechten Maustaste auf **Webverweis hinzufügen**, und wählen Sie den Webdienst die Liste der verfügbaren Webdienste (Dies erfordert möglicherweise die Adresse des Webdienst-Endpunkt, wenn der Webdienst nicht innerhalb der aktuellen Projektmappe oder auf dem aktuellen Computer verfügbar ist.) Wenn Sie den XML-Webdienstproxy (wie im vorigen Schritt beschrieben) selbst erstellen, können Sie ihn in den Clientcode importieren und die XML-Webdienstmethoden verwenden. Im folgenden Beispielcode wird die Proxybibliothek, Aufrufe importiert **GetCustomers** zum Abrufen einer Liste von Kunden, fügt einen neuen Kunden und gibt dann eine **DataSet** mit den Updates **UpdateCustomers** .  
  
     Beachten Sie, die im Beispiel übergibt die **DataSet** zurückgegebenes **DataSet.GetChanges** zu **UpdateCustomers** da nur geänderte Zeilen übergeben werden müssen  **UpdateCustomers**. **UpdateCustomers** gibt das aufgelöste **DataSet**, Sie klicken können **Merge** in die vorhandenen **DataSet** die aufgelösten Änderungen und allen integrieren Zeilenfehlerinformationen aus dem Update. Der folgende Code wird davon ausgegangen, dass Sie Visual Studio verwendet haben, um den Webverweis zu erstellen und Sie den Webverweis DsSample in umbenannt haben die **Webverweis hinzufügen** Dialogfeld.  
  
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
  
     Wenn Sie sich entschlossen haben, die Proxyklasse selbst zu erstellen, müssen Sie die folgenden zusätzlichen Schritte ausführen. Zum Kompilieren des Beispiels geben Sie die erstellte Proxybibliothek ("sample.dll") und die diesbezüglichen .NET-Bibliotheken an. Zum Kompilieren der Visual Basic .NET-Version des Beispiels, die in der Datei "client.vb" gespeichert wurde, verwenden Sie den folgenden Befehl:  
  
    ```console
    vbc client.vb -r:sample.dll -r:System.dll -r:System.Data.dll -r:System.Xml.dll -r:System.Web.Services.dll  
    ```  
  
     Zum Kompilieren der C#-Version des Beispiels, die in der Datei "client.cs" gespeichert wurde, verwenden Sie den folgenden Befehl:  
  
    ```console
    csc client.cs -r:sample.dll -r:System.dll -r:System.Data.dll -r:System.Xml.dll -r:System.Web.Services.dll  
    ```  
  
## <a name="see-also"></a>Siehe auch

- [ADO.NET](../../../../../docs/framework/data/adonet/index.md)
- ["DataSets", "DataTables" und "DataViews"](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)
- ["DataTables"](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)
- [Auffüllen eines "DataSets" durch einen "DataAdapter"](../../../../../docs/framework/data/adonet/populating-a-dataset-from-a-dataadapter.md)
- [Aktualisieren von Datenquellen mit "DataAdapters"](../../../../../docs/framework/data/adonet/updating-data-sources-with-dataadapters.md)
- [DataAdapter-Parameter](../../../../../docs/framework/data/adonet/dataadapter-parameters.md)
- [Web Services Description Language-Tool (Wsdl.exe)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7h3ystb6(v=vs.100))
- [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
