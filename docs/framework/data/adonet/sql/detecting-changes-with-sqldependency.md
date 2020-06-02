---
title: Ermitteln von Änderungen mit "SqlDependency"
description: Ordnen Sie einem sqlQuery-Objekt einen SqlCommand zu, um zu erkennen, wann sich die Abfrageergebnisse von den ursprünglich in ADO.net abgerufenen unterscheiden.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e6a58316-f005-4477-92e1-45cc2eb8c5b4
ms.openlocfilehash: b196d42477e1778c45df64b1390502645fdd649d
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286467"
---
# <a name="detecting-changes-with-sqldependency"></a>Ermitteln von Änderungen mit "SqlDependency"

Ein <xref:System.Data.SqlClient.SqlDependency>-Objekt kann einem <xref:System.Data.SqlClient.SqlCommand> zugeordnet werden, um zu erkennen, wenn die Abfrageergebnisse von den ursprünglich abgerufenen Ergebnissen abweichen. Darüber hinaus können Sie dem Ereignis `OnChange` einen Delegaten zuweisen, der ausgelöst wird, wenn sich die Ergebnisse für einen zugeordneten Befehl ändern. Sie müssen die <xref:System.Data.SqlClient.SqlDependency> dem Befehl zuordnen, bevor Sie den Befehl ausführen. Die Eigenschaft `HasChanges` der <xref:System.Data.SqlClient.SqlDependency> kann auch verwendet werden, um zu ermitteln, ob sich die Abfrageergebnisse seit dem ersten Abruf der Daten geändert haben.

## <a name="security-considerations"></a>Überlegungen zur Sicherheit

Für die Abhängigkeiteninfrastruktur ist eine <xref:System.Data.SqlClient.SqlConnection> erforderlich, die hergestellt wird, sobald <xref:System.Data.SqlClient.SqlDependency.Start%2A> aufgerufen wird, um Benachrichtigungen zu Änderungen an den zugrunde liegenden Daten für einen bestimmten Befehl zu empfangen. Die Fähigkeit eines Clients, den Aufruf an `SqlDependency.Start` zu initiieren, wird mithilfe von <xref:System.Data.SqlClient.SqlClientPermission> und Attributen für die Codezugriffssicherheit gesteuert. Weitere Informationen finden Sie unter [Aktivieren von Abfrage Benachrichtigungen](enabling-query-notifications.md) und [Code Zugriffssicherheit und ADO.net](../code-access-security.md).

### <a name="example"></a>Beispiel

Die folgenden Schritte veranschaulichen, wie Sie eine Abhängigkeit deklarieren, einen Befehl ausführen und eine Benachrichtigung erhalten, sobald sich das Resultset ändert:

1. Initiieren Sie eine `SqlDependency`-Verbindung mit dem Server.

2. Erstellen Sie <xref:System.Data.SqlClient.SqlConnection>- und <xref:System.Data.SqlClient.SqlCommand>-Objekte für die Verbindung mit dem Server, und definieren Sie eine Transact-SQL-Anweisung.

3. Erstellen Sie ein neues `SqlDependency`-Objekt, oder verwenden Sie ein vorhandenes Objekt, und binden Sie es an das `SqlCommand`-Objekt. Intern wird dadurch ein <xref:System.Data.Sql.SqlNotificationRequest>-Objekt erstellt und bei Bedarf an das Befehlsobjekt gebunden. Diese Benachrichtigungsanforderung enthält einen internen Bezeichner, der dieses `SqlDependency`-Objekt eindeutig identifiziert. Außerdem wird der Clientlistener gestartet, sofern er noch nicht aktiv ist.

4. Abonnieren Sie einen Ereignishandler für das `OnChange`-Ereignis des `SqlDependency`-Objekts.

5. Führen Sie den Befehl mit einer der `Execute`-Methoden des `SqlCommand`-Objekts aus. Da der Befehl an das Benachrichtigungsobjekt gebunden ist, erkennt der Server, dass er eine Benachrichtigung generieren muss, und die Warteschlangeninformation zeigt auf die Abhängigkeitenwarteschlange.

6. Beenden Sie die `SqlDependency`-Verbindung mit dem Server.

Wenn ein Benutzer anschließend die zugrunde liegenden Daten ändert, erkennt Microsoft SQL Server, dass eine Benachrichtigung zu einer solchen Änderung aussteht. Er sendet eine Benachrichtigung, die verarbeitet und an den Client weitergeleitet wird. Diese Weiterleitung erfolgt über die zugrunde liegende `SqlConnection`, die durch den Aufruf von `SqlDependency.Start` erstellt wurde. Der Clientlistener empfängt die Invalidierungsnachricht. Anschließend ermittelt der Clientlistener das zugeordnete `SqlDependency`-Objekt und löst das `OnChange`-Ereignis aus.

Das folgende Codefragment zeigt das Entwurfsmuster, mit dem Sie eine Beispielanwendung erstellen würden.

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
        ' Maintain the refernce in a class member.
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

- [Abfragebenachrichtigungen in SQL Server](query-notifications-in-sql-server.md)
- [Übersicht über ADO.NET](../ado-net-overview.md)
