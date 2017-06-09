---
title: "Verwenden eines DataSet aus einem XML-Webdienst | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 9edd6b71-0fa5-4649-ae1d-ac1c12541019
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Verwenden eines DataSet aus einem XML-Webdienst
Das <xref:System.Data.DataSet> wurde mit einer nicht verbundenen Struktur erstellt. Auf diese Art und Weise wird z. B. eine komfortable Übertragung von Daten über das Internet ermöglicht.  Das **DataSet** ist insofern "serialisierbar", als es als Eingabe in oder Ausgabe aus XML\-Webdiensten angegeben werden kann, ohne dass eine zusätzliche Codierung erforderlich ist, um den Inhalt des **DataSet** von einem XML\-Webdienst zu einem Client und zurück zu übertragen.  Das **DataSet** wird implizit mit dem DiffGram\-Format in einen XML\-Stream konvertiert, über das Netzwerk gesendet und dann beim Empfänger aus dem XML\-Stream als **DataSet** wiederhergestellt.  Dadurch steht Ihnen eine sehr einfache und flexible Methode zum Übertragen und Zurückübertragen von relationalen Daten mithilfe von XML\-Webdiensten zur Verfügung.  Weitere Informationen zum DiffGram\-Format finden Sie unter [DiffGrams](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/diffgrams.md).  
  
 Im folgenden Beispiel werden die Schritte zum Erstellen eines XML\-Webdiensts sowie eines Clients für diesen Dienst veranschaulicht, der das **DataSet** zur Übertragung relationaler Daten \(einschließlich der Änderungen an diesen Daten\) verwendet und alle Updates mit der ursprünglichen Datenquelle abgleicht.  
  
> [!NOTE]
>  Es wird empfohlen, beim Erstellen eines XML\-Webdiensts immer die Sicherheitsaspekte zu berücksichtigen.  Informationen zum Gewährleisten der Sicherheit für XML\-Webdienste finden Sie unter [Securing XML Web Services Created Using ASP.NET](http://msdn.microsoft.com/de-de/354b2ab1-2782-4542-b32a-dc560178b90c).  
  
### So erstellen Sie einen XML\-Webdienst, der ein "DataSet" zurückgibt und verarbeitet  
  
1.  Erstellen Sie den XML\-Webdienst.  
  
     Im Beispiel wird ein XML\-Webdienst erstellt, der Daten zurückgibt – in diesem Fall eine Kundenliste aus der **Northwind**\-Datenbank – und ein **DataSet** mit Updates zu den Daten empfängt, die der XML\-Webdienst mit der ursprünglichen Datenquelle abgleicht.  
  
     Der XML\-Webdienst enthält zwei Methoden: **GetCustomers**, um die Kundenliste zurückzugeben, und **UpdateCustomers**, um Updates mit der Datenquelle abzugleichen.  Der XML\-Webdienst wird in einer Datei auf dem Webserver mit dem Namen "DataSetSample.asmx" gespeichert.  Im folgenden Code wird der Inhalt von "DataSetSample.asmx" dargestellt.  
  
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
  
     In einem typischen Szenario würde die **UpdateCustomers**\-Methode geschrieben, um Verletzungen der vollständigen Parallelität abzufangen.  Zur Vereinfachung wurde in diesem Beispiel darauf verzichtet.  Weitere Informationen zur vollständigen Parallelität finden Sie unter [Vollständige Parallelität](../../../../../docs/framework/data/adonet/optimistic-concurrency.md).  
  
2.  Erstellen Sie einen XML\-Webdienstproxy.  
  
     Clients des XML\-Webdiensts benötigen einen SOAP\-Proxy, um die verfügbar gemachten Methoden verarbeiten zu können.  Sie können diesen Proxy von Visual Studio generieren lassen.  Das in diesem Schritt beschriebene Verhalten wird transparent, wenn Sie einen Webverweis auf einen vorhandenen Webdienst von Visual Studio aus festlegen.  Wenn Sie die Proxyklasse selbst erstellen möchten, finden Sie im Folgenden die notwendigen Informationen.  In den meisten Fällen ist es jedoch ausreichend, wenn die Proxyklasse für die Clientanwendung mithilfe von Visual Studio erstellt wird.  
  
     Ein Proxy kann mit dem Web Services Description Language\-Tool erstellt werden.  Wenn der XML\-Webdienst z. B. unter der URL **http:\/\/myserver\/data\/DataSetSample.asmx** verfügbar gemacht wird, verwenden Sie einen Befehl ähnlich dem folgenden, um einen Visual Basic .NET\-Proxy mit dem Namespace "WebData.DSSample" zu erstellen und in der Datei "sample.vb" zu speichern.  
  
    ```  
    wsdl /l:VB /out:sample.vb http://myserver/data/DataSetSample.asmx /n:WebData.DSSample  
    ```  
  
     Zum Erstellen eines C\#\-Proxys in der Datei "sample.cs" verwenden Sie den folgenden Befehl:  
  
    ```  
    wsdl /l:CS /out:sample.cs http://myserver/data/DataSetSample.asmx /n:WebData.DSSample  
    ```  
  
     Der Proxy kann dann als Bibliothek kompiliert und in einen XML\-Webdienstclient importiert werden.  Zum Kompilieren des Visual Basic .NET\-Proxycodes, der in der Datei "sample.vb" als "sample.dll" gespeichert wird, verwenden Sie den folgenden Befehl:  
  
    ```  
    vbc /t:library /out:sample.dll sample.vb /r:System.dll /r:System.Web.Services.dll /r:System.Data.dll /r:System.Xml.dll  
    ```  
  
     Zum Kompilieren des C\#\-Proxycodes, der in der Datei "sample.vb" als "sample.dll" gespeichert wird, verwenden Sie den folgenden Befehl:  
  
    ```  
    csc /t:library /out:sample.dll sample.cs /r:System.dll /r:System.Web.Services.dll /r:System.Data.dll /r:System.Xml.dll  
    ```  
  
3.  Erstellen Sie einen XML\-Webdienstclient.  
  
     Wenn Sie die Webdienst\-Proxyklasse von Visual Studio generieren lassen möchten, erstellen Sie einfach das Clientprojekt. Klicken Sie anschließend im Fenster des Projektmappen\-Explorers mit der rechten Maustaste auf das Projekt, klicken Sie auf **Webverweis hinzufügen**, und wählen Sie in der Liste der verfügbaren Webdienste den gewünschten Webdienst aus. \(Möglicherweise müssen Sie die Adresse des Webdienst\-Endpunkts angeben, wenn der Webdienst in der aktuellen Projektmappe oder auf dem aktuellen Computer nicht verfügbar ist.\) Wenn Sie den XML\-Webdienstproxy \(wie im vorigen Schritt beschrieben\) selbst erstellen, können Sie ihn in den Clientcode importieren und die XML\-Webdienstmethoden verwenden.  Im folgenden Codebeispiel wird die Proxybibliothek importiert, anschließend zum Abrufen einer Kundenliste **GetCustomers** aufgerufen, ein neuer Kunde hinzugefügt und dann ein **DataSet** mit den Updates an **UpdateCustomers** zurückgegeben.  
  
     Beachten Sie, dass in diesem Beispiel das von **DataSet.GetChanges** zurückgegebene **DataSet** an **UpdateCustomers** übergeben wird, da nur geänderte Zeilen an **UpdateCustomers** übergeben werden müssen.  **UpdateCustomers** gibt das aufgelöste **DataSet** zurück, das Sie anschließend über **Merge** mit dem vorhandenen **DataSet** zusammenführen können, um die aufgelösten Änderungen und die Zeilenfehlerinformationen aus dem Update zu integrieren.  Bei dem folgenden Codebeispiel wird davon ausgegangen, dass Sie den Webverweis mithilfe von Visual Studio erstellt haben und ihn im Dialogfeld **Webverweis hinzufügen** in "DsSample" umbenannt haben.  
  
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
  
     Wenn Sie sich entschlossen haben, die Proxyklasse selbst zu erstellen, müssen Sie die folgenden zusätzlichen Schritte ausführen.  Zum Kompilieren des Beispiels geben Sie die erstellte Proxybibliothek \("sample.dll"\) und die diesbezüglichen .NET\-Bibliotheken an.  Zum Kompilieren der Visual Basic .NET\-Version des Beispiels, die in der Datei "client.vb" gespeichert wurde, verwenden Sie den folgenden Befehl:  
  
    ```  
    vbc client.vb /r:sample.dll /r:System.dll /r:System.Data.dll /r:System.Xml.dll /r:System.Web.Services.dll  
    ```  
  
     Zum Kompilieren der C\#\-Version des Beispiels, die in der Datei "client.cs" gespeichert wurde, verwenden Sie den folgenden Befehl:  
  
    ```  
    csc client.cs /r:sample.dll /r:System.dll /r:System.Data.dll /r:System.Xml.dll /r:System.Web.Services.dll  
    ```  
  
## Siehe auch  
 [ADO.NET](../../../../../docs/framework/data/adonet/index.md)   
 [DataSets, DataTables und DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)   
 [DataTables](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)   
 [Auffüllen eines "DataSets" durch einen "DataAdapter"](../../../../../docs/framework/data/adonet/populating-a-dataset-from-a-dataadapter.md)   
 [Aktualisieren von Datenquellen mit DataAdapters](../../../../../docs/framework/data/adonet/updating-data-sources-with-dataadapters.md)   
 ['DataAdapter'\-Parameter](../../../../../docs/framework/data/adonet/dataadapter-parameters.md)   
 [Web Services Description Language Tool \(Wsdl.exe\)](http://msdn.microsoft.com/de-de/b9210348-8bc2-4367-8c91-d1a04b403e88)   
 [ADO.NET Verwaltete Anbieter und DataSet\-Entwicklercenter](http://go.microsoft.com/fwlink/?LinkId=217917)