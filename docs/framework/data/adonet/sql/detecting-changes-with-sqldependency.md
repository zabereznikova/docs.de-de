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
# <a name="detecting-changes-with-sqldependency"></a><span data-ttu-id="b353f-103">Ermitteln von Änderungen mit "SqlDependency"</span><span class="sxs-lookup"><span data-stu-id="b353f-103">Detecting Changes with SqlDependency</span></span>

<span data-ttu-id="b353f-104">Ein <xref:System.Data.SqlClient.SqlDependency>-Objekt kann einem <xref:System.Data.SqlClient.SqlCommand> zugeordnet werden, um zu erkennen, wenn die Abfrageergebnisse von den ursprünglich abgerufenen Ergebnissen abweichen.</span><span class="sxs-lookup"><span data-stu-id="b353f-104">A <xref:System.Data.SqlClient.SqlDependency> object can be associated with a <xref:System.Data.SqlClient.SqlCommand> in order to detect when query results differ from those originally retrieved.</span></span> <span data-ttu-id="b353f-105">Darüber hinaus können Sie dem Ereignis `OnChange` einen Delegaten zuweisen, der ausgelöst wird, wenn sich die Ergebnisse für einen zugeordneten Befehl ändern.</span><span class="sxs-lookup"><span data-stu-id="b353f-105">You can also assign a delegate to the `OnChange` event, which will fire when the results change for an associated command.</span></span> <span data-ttu-id="b353f-106">Sie müssen die <xref:System.Data.SqlClient.SqlDependency> dem Befehl zuordnen, bevor Sie den Befehl ausführen.</span><span class="sxs-lookup"><span data-stu-id="b353f-106">You must associate the <xref:System.Data.SqlClient.SqlDependency> with the command before you execute the command.</span></span> <span data-ttu-id="b353f-107">Die Eigenschaft `HasChanges` der <xref:System.Data.SqlClient.SqlDependency> kann auch verwendet werden, um zu ermitteln, ob sich die Abfrageergebnisse seit dem ersten Abruf der Daten geändert haben.</span><span class="sxs-lookup"><span data-stu-id="b353f-107">The `HasChanges` property of the <xref:System.Data.SqlClient.SqlDependency> can also be used to determine if the query results have changed since the data was first retrieved.</span></span>

## <a name="security-considerations"></a><span data-ttu-id="b353f-108">Überlegungen zur Sicherheit</span><span class="sxs-lookup"><span data-stu-id="b353f-108">Security Considerations</span></span>

<span data-ttu-id="b353f-109">Für die Abhängigkeiteninfrastruktur ist eine <xref:System.Data.SqlClient.SqlConnection> erforderlich, die hergestellt wird, sobald <xref:System.Data.SqlClient.SqlDependency.Start%2A> aufgerufen wird, um Benachrichtigungen zu Änderungen an den zugrunde liegenden Daten für einen bestimmten Befehl zu empfangen.</span><span class="sxs-lookup"><span data-stu-id="b353f-109">The dependency infrastructure relies on a <xref:System.Data.SqlClient.SqlConnection> that is opened when <xref:System.Data.SqlClient.SqlDependency.Start%2A> is called in order to receive notifications that the underlying data has changed for a given command.</span></span> <span data-ttu-id="b353f-110">Die Fähigkeit eines Clients, den Aufruf an `SqlDependency.Start` zu initiieren, wird mithilfe von <xref:System.Data.SqlClient.SqlClientPermission> und Attributen für die Codezugriffssicherheit gesteuert.</span><span class="sxs-lookup"><span data-stu-id="b353f-110">The ability for a client to initiate the call to `SqlDependency.Start` is controlled through the use of <xref:System.Data.SqlClient.SqlClientPermission> and code access security attributes.</span></span> <span data-ttu-id="b353f-111">Weitere Informationen finden Sie unter [Aktivieren von Abfrage Benachrichtigungen](enabling-query-notifications.md) und [Code Zugriffssicherheit und ADO.net](../code-access-security.md).</span><span class="sxs-lookup"><span data-stu-id="b353f-111">For more information, see [Enabling Query Notifications](enabling-query-notifications.md) and [Code Access Security and ADO.NET](../code-access-security.md).</span></span>

### <a name="example"></a><span data-ttu-id="b353f-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b353f-112">Example</span></span>

<span data-ttu-id="b353f-113">Die folgenden Schritte veranschaulichen, wie Sie eine Abhängigkeit deklarieren, einen Befehl ausführen und eine Benachrichtigung erhalten, sobald sich das Resultset ändert:</span><span class="sxs-lookup"><span data-stu-id="b353f-113">The following steps illustrate how to declare a dependency, execute a command, and receive a notification when the result set changes:</span></span>

1. <span data-ttu-id="b353f-114">Initiieren Sie eine `SqlDependency`-Verbindung mit dem Server.</span><span class="sxs-lookup"><span data-stu-id="b353f-114">Initiate a `SqlDependency` connection to the server.</span></span>

2. <span data-ttu-id="b353f-115">Erstellen Sie <xref:System.Data.SqlClient.SqlConnection>- und <xref:System.Data.SqlClient.SqlCommand>-Objekte für die Verbindung mit dem Server, und definieren Sie eine Transact-SQL-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="b353f-115">Create <xref:System.Data.SqlClient.SqlConnection> and <xref:System.Data.SqlClient.SqlCommand> objects to connect to the server and define a Transact-SQL statement.</span></span>

3. <span data-ttu-id="b353f-116">Erstellen Sie ein neues `SqlDependency`-Objekt, oder verwenden Sie ein vorhandenes Objekt, und binden Sie es an das `SqlCommand`-Objekt.</span><span class="sxs-lookup"><span data-stu-id="b353f-116">Create a new `SqlDependency` object, or use an existing one, and bind it to the `SqlCommand` object.</span></span> <span data-ttu-id="b353f-117">Intern wird dadurch ein <xref:System.Data.Sql.SqlNotificationRequest>-Objekt erstellt und bei Bedarf an das Befehlsobjekt gebunden.</span><span class="sxs-lookup"><span data-stu-id="b353f-117">Internally, this creates a <xref:System.Data.Sql.SqlNotificationRequest> object and binds it to the command object as needed.</span></span> <span data-ttu-id="b353f-118">Diese Benachrichtigungsanforderung enthält einen internen Bezeichner, der dieses `SqlDependency`-Objekt eindeutig identifiziert.</span><span class="sxs-lookup"><span data-stu-id="b353f-118">This notification request contains an internal identifier that uniquely identifies this `SqlDependency` object.</span></span> <span data-ttu-id="b353f-119">Außerdem wird der Clientlistener gestartet, sofern er noch nicht aktiv ist.</span><span class="sxs-lookup"><span data-stu-id="b353f-119">It also starts the client listener if it is not already active.</span></span>

4. <span data-ttu-id="b353f-120">Abonnieren Sie einen Ereignishandler für das `OnChange`-Ereignis des `SqlDependency`-Objekts.</span><span class="sxs-lookup"><span data-stu-id="b353f-120">Subscribe an event handler to the `OnChange` event of the `SqlDependency` object.</span></span>

5. <span data-ttu-id="b353f-121">Führen Sie den Befehl mit einer der `Execute`-Methoden des `SqlCommand`-Objekts aus.</span><span class="sxs-lookup"><span data-stu-id="b353f-121">Execute the command using any of the `Execute` methods of the `SqlCommand` object.</span></span> <span data-ttu-id="b353f-122">Da der Befehl an das Benachrichtigungsobjekt gebunden ist, erkennt der Server, dass er eine Benachrichtigung generieren muss, und die Warteschlangeninformation zeigt auf die Abhängigkeitenwarteschlange.</span><span class="sxs-lookup"><span data-stu-id="b353f-122">Because the command is bound to the notification object, the server recognizes that it must generate a notification, and the queue information will point to the dependencies queue.</span></span>

6. <span data-ttu-id="b353f-123">Beenden Sie die `SqlDependency`-Verbindung mit dem Server.</span><span class="sxs-lookup"><span data-stu-id="b353f-123">Stop the `SqlDependency` connection to the server.</span></span>

<span data-ttu-id="b353f-124">Wenn ein Benutzer anschließend die zugrunde liegenden Daten ändert, erkennt Microsoft SQL Server, dass eine Benachrichtigung zu einer solchen Änderung aussteht. Er sendet eine Benachrichtigung, die verarbeitet und an den Client weitergeleitet wird. Diese Weiterleitung erfolgt über die zugrunde liegende `SqlConnection`, die durch den Aufruf von `SqlDependency.Start` erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="b353f-124">If any user subsequently changes the underlying data, Microsoft SQL Server detects that there is a notification pending for such a change, and posts a notification that is processed and forwarded to the client through the underlying `SqlConnection` that was created by calling `SqlDependency.Start`.</span></span> <span data-ttu-id="b353f-125">Der Clientlistener empfängt die Invalidierungsnachricht.</span><span class="sxs-lookup"><span data-stu-id="b353f-125">The client listener receives the invalidation message.</span></span> <span data-ttu-id="b353f-126">Anschließend ermittelt der Clientlistener das zugeordnete `SqlDependency`-Objekt und löst das `OnChange`-Ereignis aus.</span><span class="sxs-lookup"><span data-stu-id="b353f-126">The client listener then locates the associated `SqlDependency` object and fires the `OnChange` event.</span></span>

<span data-ttu-id="b353f-127">Das folgende Codefragment zeigt das Entwurfsmuster, mit dem Sie eine Beispielanwendung erstellen würden.</span><span class="sxs-lookup"><span data-stu-id="b353f-127">The following code fragment shows the design pattern you would use to create a sample application.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="b353f-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b353f-128">See also</span></span>

- [<span data-ttu-id="b353f-129">Abfragebenachrichtigungen in SQL Server</span><span class="sxs-lookup"><span data-stu-id="b353f-129">Query Notifications in SQL Server</span></span>](query-notifications-in-sql-server.md)
- [<span data-ttu-id="b353f-130">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="b353f-130">ADO.NET Overview</span></span>](../ado-net-overview.md)
