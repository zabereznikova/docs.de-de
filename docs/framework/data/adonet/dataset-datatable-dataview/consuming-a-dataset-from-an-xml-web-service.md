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
# <a name="consume-a-dataset-from-an-xml-web-service"></a>Verwenden eines DataSets aus einem XML-Webdienst

Das <xref:System.Data.DataSet> wurde mit einer nicht verbundenen Struktur erstellt. Auf diese Art und Weise wird z. B. eine komfortable Übertragung von Daten über das Internet ermöglicht. Das **DataSet** ist "serialisierbar", da es als Eingabe für XML-Webdienste oder als Ausgabe von XML-Webdiensten angegeben werden kann, ohne dass zusätzliche Codierung erforderlich ist, um den Inhalt des **DataSets** von einem XML-Webdienst auf einen Client und zurück zu streamen. Das **DataSet** wird implizit im DiffGram-Format in einen XML-Stream konvertiert, über das Netzwerk gesendet und dann aus dem XML-Stream als **DataSet** auf dem empfangenden Ende rekonstruiert. Dadurch steht Ihnen eine sehr einfache und flexible Methode zum Übertragen und Zurückübertragen von relationalen Daten mithilfe von XML-Webdiensten zur Verfügung. Weitere Informationen zum DiffGram-Format finden Sie unter [DiffGrams](diffgrams.md).  
  
 Das folgende Beispiel zeigt, wie Sie einen XML-Webdienst und -client erstellen, die das **DataSet** zum Transport relationaler Daten (einschließlich geänderter Daten) und zum Auflösen von Aktualisierungen in die ursprüngliche Datenquelle verwenden.  
  
> [!NOTE]
> Es wird empfohlen, beim Erstellen eines XML-Webdiensts immer die Sicherheitsaspekte zu berücksichtigen. Informationen zum Sichern eines XML-Webdiensts finden Sie unter [Sichern von XML-Webdiensten,](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/w67h0dw7(v=vs.100))die mit ASP.NET erstellt wurden.  
  
## <a name="create-an-xml-web-service"></a>Erstellen eines XML-Webdiensts
  
1. Erstellen Sie den XML-Webdienst.  
  
     Im Beispiel wird ein XML-Webdienst erstellt, der Daten zurückgibt, in diesem Fall eine Liste von Kunden aus der **Northwind-Datenbank,** und ein **DataSet** mit Aktualisierungen der Daten empfängt, die der XML-Webdienst in der ursprünglichen Datenquelle auflöst.  
  
     Der XML-Webdienst macht zwei Methoden verfügbar: **GetCustomers**, um die Liste der Kunden zurückzugeben, und **UpdateCustomers**, um Aktualisierungen an die Datenquelle zurückzusenden. Der XML-Webdienst wird in einer Datei auf dem Webserver mit dem Namen "DataSetSample.asmx" gespeichert. Im folgenden Code wird der Inhalt von "DataSetSample.asmx" dargestellt.  
  
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
  
     In einem typischen Szenario wird die **UpdateCustomers-Methode** geschrieben, um optimistische Parallelitätsverletzungen abzufangen. Zur Vereinfachung wurde in diesem Beispiel darauf verzichtet. Weitere Informationen zur optimistischen Parallelität finden Sie unter [Optimistische Parallelität](../optimistic-concurrency.md).  
  
2. Erstellen Sie einen XML-Webdienstproxy.  
  
     Clients des XML-Webdiensts benötigen einen SOAP-Proxy, um die verfügbar gemachten Methoden verarbeiten zu können. Sie können diesen Proxy von Visual Studio generieren lassen. Das in diesem Schritt beschriebene Verhalten wird transparent, wenn Sie einen Webverweis auf einen vorhandenen Webdienst von Visual Studio aus festlegen. Wenn Sie die Proxyklasse selbst erstellen möchten, finden Sie im Folgenden die notwendigen Informationen. In den meisten Fällen ist es jedoch ausreichend, wenn die Proxyklasse für die Clientanwendung mithilfe von Visual Studio erstellt wird.  
  
     Ein Proxy kann mit dem Web Services Description Language-Tool erstellt werden. Wenn der XML-Webdienst z. B. unter der URL `http://myserver/data/DataSetSample.asmx`verfügbar gemacht wird, geben Sie einen Befehl wie den folgenden aus, um einen Visual Basic .NET-Proxy mit einem Namespace von **WebData.DSSample** zu erstellen und im Dateibeispiel zu speichern.vb.  
  
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
  
     Wenn Visual Studio die Webdienstproxyklasse für Sie generieren soll, erstellen Sie einfach das Clientprojekt, und klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das Projekt, und wählen Sie dann**Dienstreferenz** **hinzufügen** > aus. Wählen Sie im Dialogfeld **Dienstreferenz hinzufügen** die Option **Erweitert**aus, und wählen Sie dann **Webreferenz hinzufügen**aus. Wählen Sie den Webdienst aus der Liste der verfügbaren Webdienste aus (dies erfordert möglicherweise die Angabe der Adresse des Webdienstendpunkts, wenn der Webdienst nicht innerhalb der aktuellen Lösung oder auf dem aktuellen Computer verfügbar ist). Wenn Sie den XML-Webdienstproxy (wie im vorigen Schritt beschrieben) selbst erstellen, können Sie ihn in den Clientcode importieren und die XML-Webdienstmethoden verwenden.

     Der folgende Beispielcode importiert die Proxybibliothek, ruft **GetCustomers** auf, um eine Kundenliste abzubekommen, fügt einen neuen Kunden hinzu und gibt dann ein **DataSet** mit den Updates an **UpdateCustomers**zurück.  
  
     Das Beispiel übergibt das von **DataSet.GetChanges** zurückgegebene **DataSet** an **UpdateCustomers,** da nur geänderte Zeilen an **UpdateCustomers**übergeben werden müssen. **UpdateCustomers** gibt das aufgelöste **DataSet**zurück, das Sie dann in das vorhandene **DataSet** **zusammenführen** können, um die behobenen Änderungen und alle Zeilenfehlerinformationen aus dem Update zu integrieren. Der folgende Code geht davon aus, dass Sie Visual Studio zum Erstellen des Webverweises verwendet haben und dass Sie den Webverweis im Dialogfeld **Webreferenz** hinzufügen in DsSample umbenannt haben.  
  
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
