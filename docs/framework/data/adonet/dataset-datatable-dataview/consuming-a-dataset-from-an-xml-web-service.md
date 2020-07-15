---
title: Verwenden eines Datasets von einem XML-Webdienst
ms.date: 07/14/2020
dev_langs:
- csharp
- vb
ms.assetid: 9edd6b71-0fa5-4649-ae1d-ac1c12541019
ms.openlocfilehash: 2c8924ee3374489dded7e819ecde8e4d9da750bb
ms.sourcegitcommit: e7748001b1cee80ced691d8a76ca814c0b02dd9b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/14/2020
ms.locfileid: "86374385"
---
# <a name="consume-a-dataset-from-an-xml-web-service"></a>Verwenden eines Datasets von einem XML-Webdienst

Das <xref:System.Data.DataSet> wurde mit einer nicht verbundenen Struktur erstellt. Auf diese Art und Weise wird z. B. eine komfortable Übertragung von Daten über das Internet ermöglicht. Das **DataSet** ist "serialisierbar", da es als Eingabe oder Ausgabe aus XML-Webdiensten angegeben werden kann, ohne dass zusätzliche Codierungen erforderlich sind, um den Inhalt des **DataSets** von einem XML-Webdienst zu einem Client und zurück zu streamen. Das **DataSet** wird implizit in einen XML-Stream mit dem DiffGram-Format konvertiert, über das Netzwerk gesendet und anschließend aus dem XML-Stream als **DataSet** am empfangenden Ende rekonstruiert. Dadurch erhalten Sie eine einfache und flexible Methode zum übertragen und Zurückgeben von relationalen Daten mithilfe von XML-Webdiensten. Weitere Informationen über das DiffGram-Format finden Sie unter [DiffGrams](diffgrams.md).  
  
 Im folgenden Beispiel wird gezeigt, wie ein XML-Webdienst und-Client erstellt werden, die das **DataSet** zum transportieren relationaler Daten (einschließlich der geänderten Daten) und zum Auflösen von Aktualisierungen in die ursprüngliche Datenquelle verwenden.  
  
> [!NOTE]
> `DataSet`Das Übertragen von-oder- `DataTable` Instanzen als Teil von XML-Webdienst aufrufen ist nicht sicher, wenn die Eingabe nicht vertrauenswürdig ist. Weitere Informationen finden Sie unter [Leitfaden für Datasets und Daten](/dotnet/framework/data/adonet/dataset-datatable-dataview/security-guidance)Tabelle.
> Außerdem wird empfohlen, dass Sie beim Erstellen eines XML-Webdiensts stets Sicherheits Implikationen in Erwägung gezogen. Informationen zum Sichern eines XML-Webdiensts finden [Sie unter Sichern von mit ASP.NET erstellten XML-Webdiensten](/previous-versions/dotnet/netframework-4.0/w67h0dw7(v=vs.100)).  
  
## <a name="create-an-xml-web-service"></a>Erstellen eines XML-Webdiensts
  
1. Erstellen Sie den XML-Webdienst.  
  
     Im Beispiel wird ein XML-Webdienst erstellt, der Daten zurückgibt, in diesem Fall eine Kundenliste aus der **Northwind** -Datenbank, und ein **DataSet** mit Updates an den Daten empfängt, die der XML-Webdienst wieder in die ursprüngliche Datenquelle auflöst.  
  
     Der XML-Webdienst macht zwei Methoden verfügbar: **GetCustomers**, um die Kundenliste zurückzugeben, und **UpdateCustomer**, um Updates wieder in die Datenquelle aufzulösen. Der XML-Webdienst wird in einer Datei auf dem Webserver mit dem Namen "DataSetSample.asmx" gespeichert. Im folgenden Code wird der Inhalt von "DataSetSample.asmx" dargestellt.  
  
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
  
     In einem typischen Szenario würde die **UpdateCustomer-Methode** geschrieben, um Verletzungen der vollständigen Parallelität abzufangen. Zur Vereinfachung wurde in diesem Beispiel darauf verzichtet. Weitere Informationen [zur optimistischen](../optimistic-concurrency.md)Parallelität finden Sie unter vollständige Parallelität.  
  
2. Erstellen Sie einen XML-Webdienstproxy.  
  
     Clients des XML-Webdiensts benötigen einen SOAP-Proxy, um die verfügbar gemachten Methoden verarbeiten zu können. Sie können diesen Proxy von Visual Studio generieren lassen. Das in diesem Schritt beschriebene Verhalten wird transparent, wenn Sie einen Webverweis auf einen vorhandenen Webdienst von Visual Studio aus festlegen. Wenn Sie die Proxyklasse selbst erstellen möchten, finden Sie im Folgenden die notwendigen Informationen. In den meisten Fällen ist es jedoch ausreichend, wenn die Proxyklasse für die Clientanwendung mithilfe von Visual Studio erstellt wird.  
  
     Ein Proxy kann mit dem Web Services Description Language-Tool erstellt werden. Wenn der XML-Webdienst z. b. über die URL verfügbar gemacht wird `http://myserver/data/DataSetSample.asmx` , geben Sie einen Befehl wie den folgenden aus, um einen Visual Basic .NET-Proxy mit einem Namespace von " **WebData. DSSample** " zu erstellen und in der Datei Sample. VB zu speichern.  
  
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
  
3. Erstellen Sie einen XML-Webdienstclient.  
  
     Wenn Sie möchten, dass Visual Studio die Webdienst-Proxy Klasse für Sie generiert, erstellen Sie einfach das Client Projekt, und klicken Sie im Projektmappen-Explorer Fenster mit der rechten Maustaste auf das Projekt, **Add**und wählen Sie dann  >  **Dienst Verweis**hinzufügen aus. Wählen Sie im Dialogfeld **Dienstverweis hinzufügen** die Option **erweitert**aus, und klicken Sie dann auf **Webverweis hinzufügen**. Wählen Sie in der Liste der verfügbaren Webdienste den Webdienst aus (Dies erfordert möglicherweise die Angabe der Adresse des Webdienst-Endpunkts, wenn der Webdienst nicht innerhalb der aktuellen Projekt Mappe oder auf dem aktuellen Computer verfügbar ist). Wenn Sie den XML-Webdienstproxy (wie im vorigen Schritt beschrieben) selbst erstellen, können Sie ihn in den Clientcode importieren und die XML-Webdienstmethoden verwenden.

     Im folgenden Beispielcode wird die Proxy Bibliothek importiert, **GetCustomers** aufgerufen, um eine Kundenliste zu erhalten, ein neuer Kunde hinzugefügt und dann ein **DataSet** mit den Updates an **UpdateCustomer**zurückgegeben.  
  
     Das Beispiel übergibt das von DataSet zurückgegebene **DataSet** **. GetChanges** an **UpdateCustomer** , da nur geänderte Zeilen an **UpdateCustomer**weitergegeben werden müssen. **UpdateCustomer** gibt das aufgelöste **DataSet**zurück, das Sie dann in das vorhandene **DataSet** zusammen **führen** können, um die aufgelösten Änderungen und alle Zeilen Fehlerinformationen aus dem Update einzubeziehen. Der folgende Code setzt voraus, dass Sie Visual Studio zum Erstellen des Webverweises verwendet haben und dass Sie im Dialogfeld " **Webverweis hinzufügen** " den Webverweis in "DsSample" umbenannt haben.  
  
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
  
## <a name="see-also"></a>Weitere Informationen

- [ADO.NET](../index.md)
- ["DataSets", "DataTables" und "DataViews"](index.md)
- ["DataTables"](datatables.md)
- [Auffüllen eines "DataSets" durch einen "DataAdapter"](../populating-a-dataset-from-a-dataadapter.md)
- [Aktualisieren von Datenquellen mit "DataAdapters"](../updating-data-sources-with-dataadapters.md)
- [DataAdapter-Parameter](../dataadapter-parameters.md)
- [Web Services Description Language-Tool (Wsdl.exe)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7h3ystb6(v=vs.100))
- [Übersicht über ADO.NET](../ado-net-overview.md)
