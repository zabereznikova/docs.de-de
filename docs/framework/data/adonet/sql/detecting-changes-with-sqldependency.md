---
title: Ermitteln von Änderungen mit "SqlDependency"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e6a58316-f005-4477-92e1-45cc2eb8c5b4
ms.openlocfilehash: 63d6a17e5aaf3e5d39ed0eda288e75c071be4d73
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2018
ms.locfileid: "45649945"
---
# <a name="detecting-changes-with-sqldependency"></a>Ermitteln von Änderungen mit "SqlDependency"
Ein <xref:System.Data.SqlClient.SqlDependency>-Objekt kann mit einem <xref:System.Data.SqlClient.SqlCommand>-Objekt verknüpft werden, um so Abweichungen zwischen den aktuellen und den ursprünglichen Abfrageergebnissen zu erkennen. Sie können einen Delegaten auch dem `OnChange`-Ereignis zuweisen, das ausgelöst wird, wenn sich die Ergebnisse für einen verknüpften Befehl ändern. Vor dem Ausführen des Befehls müssen Sie ihm die <xref:System.Data.SqlClient.SqlDependency> zuordnen. Mit der `HasChanges`-Eigenschaft der <xref:System.Data.SqlClient.SqlDependency> kann auch ermittelt werden, ob sich die Abfrageergebnisse seit dem letzten Abrufen der Daten geändert haben.  
  
## <a name="security-considerations"></a>Sicherheitsüberlegungen  
 Die Abhängigkeitsinfrastruktur verwendet eine <xref:System.Data.SqlClient.SqlConnection>, die geöffnet wird, wenn <xref:System.Data.SqlClient.SqlDependency.Start%2A> aufgerufen wird, damit Benachrichtigungen über die Änderung der zugrunde liegenden Daten für einen bestimmten Befehl empfangen werden können. Ob ein Client den Aufruf von `SqlDependency.Start` initiieren kann, wird mit der <xref:System.Data.SqlClient.SqlClientPermission> und Sicherheitsattributen für den Codezugriff gesteuert. Weitere Informationen finden Sie unter [Aktivieren von Abfragebenachrichtigungen](../../../../../docs/framework/data/adonet/sql/enabling-query-notifications.md) und [Codezugriffssicherheit und ADO.NET](../../../../../docs/framework/data/adonet/code-access-security.md).  
  
### <a name="example"></a>Beispiel  
 Mit den folgenden Schritten können Sie eine Abhängigkeit deklarieren, einen Befehl ausführen und festlegen, dass Sie bei Änderungen des Resultsets benachrichtigt werden möchten:  
  
1.  Initiieren Sie eine `SqlDependency`-Verbindung mit dem Server.  
  
2.  Erstellen Sie das <xref:System.Data.SqlClient.SqlConnection>-Objekt und das <xref:System.Data.SqlClient.SqlCommand>-Objekt, um eine Verbindung mit dem Server herzustellen und eine Transact-SQL-Anweisung zu definieren.  
  
3.  Erstellen Sie ein neues `SqlDependency`-Objekt, oder verwenden Sie ein vorhandenes, und binden Sie es an das `SqlCommand`-Objekt. Dadurch wird intern ein <xref:System.Data.Sql.SqlNotificationRequest>-Objekt erstellt und bei Bedarf an das Befehlsobjekt gebunden. Diese Benachrichtigungsanforderung enthält einen internen Bezeichner zur eindeutigen Kennzeichnung dieses `SqlDependency`-Objekts. Er startet außerdem auch den Clientlistener, sofern dieser nicht bereits aktiv ist.  
  
4.  Abonnieren Sie einen Ereignishandler für das `OnChange`-Ereignis des `SqlDependency`-Objekts.  
  
5.  Führen Sie den Befehl mit einer der `Execute`-Methoden des `SqlCommand`-Objekts aus. Da der Befehl an das Benachrichtigungsobjekt gebunden ist, erkennt der Server, dass er eine Benachrichtigung generieren muss, und die Warteschlangeninformation zeigt auf die Abhängigkeitenwarteschlange.  
  
6.  Beenden Sie die `SqlDependency`-Verbindung mit dem Server.  
  
 Wenn ein Benutzer anschließend Änderungen an den zugrunde liegenden Daten vornimmt, erkennt Microsoft SQL Server, dass es für eine derartige Änderung eine Benachrichtigung gibt, und übermittelt diese Benachrichtigung über die zugrunde liegende, mit `SqlConnection` erstellte `SqlDependency.Start`. Der Clientlistener empfängt die Ungültigkeitserklärung. Der Clientlistener sucht dann das zugeordnete `SqlDependency`-Objekt und löst das `OnChange`-Ereignis aus.  
  
 Das folgende Codefragment zeigt das Entwurfsmuster, das Sie zum Erstellen einer Beispielanwendung verwenden können:  
  
```vb  
Sub Initialization()  
    ' Create a dependency connection.  
    SqlDependency.Start(connectionString, queueName)  
End Sub  
  
Sub SomeMethod()   
    ' Assume connection is an open SqlConnection.  
    ' Create a new SqlCommand object.  
    Using command As New SqlCommand( _  
      "SELECT ShipperID, CompanyName, Phone FROM dbo.Shippers", _  
      connection)  
  
        ' Create a dependency and associate it with the SqlCommand.  
        Dim dependency As New SqlDependency(command)  
        ' Maintain the refence in a class member.  
        ' Subscribe to the SqlDependency event.  
        AddHandler dependency.OnChange, AddressOf OnDependencyChange  
  
        ' Execute the command.  
        Using reader = command.ExecuteReader()  
            ' Process the DataReader.  
        End Using  
    End Using  
End Sub   
  
' Handler method  
Sub OnDependencyChange(ByVal sender As Object, _  
    ByVal e As SqlNotificationEventArgs)   
    ' Handle the event (for example, invalidate this cache entry).  
End Sub  
  
Sub Termination()  
    ' Release the dependency  
    SqlDependency.Stop(connectionString, queueName)  
End Sub  
```  
  
```csharp  
void Initialization()  
{  
    // Create a dependency connection.  
    SqlDependency.Start(connectionString, queueName);  
}  
  
void SomeMethod()  
{  
    // Assume connection is an open SqlConnection.  
  
    // Create a new SqlCommand object.  
    using (SqlCommand command=new SqlCommand(  
        "SELECT ShipperID, CompanyName, Phone FROM dbo.Shippers",   
        connection))  
    {  
  
        // Create a dependency and associate it with the SqlCommand.  
        SqlDependency dependency=new SqlDependency(command);  
        // Maintain the reference in a class member.  
  
        // Subscribe to the SqlDependency event.  
        dependency.OnChange+=new  
           OnChangeEventHandler(OnDependencyChange);  
  
        // Execute the command.  
        using (SqlDataReader reader = command.ExecuteReader())  
        {  
            // Process the DataReader.  
        }  
    }  
}  
  
// Handler method  
void OnDependencyChange(object sender,   
   SqlNotificationEventArgs e )  
{  
  // Handle the event (for example, invalidate this cache entry).  
}  
  
void Termination()  
{  
    // Release the dependency.  
    SqlDependency.Stop(connectionString, queueName);  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Abfragebenachrichtigungen in SQL Server](../../../../../docs/framework/data/adonet/sql/query-notifications-in-sql-server.md)  
 [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
