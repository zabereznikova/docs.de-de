---
title: SqlCommand-Ausführung mit "SqlNotificationRequest"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1776f48f-9bea-41f6-83a4-c990c7a2c991
ms.openlocfilehash: 3115bfb80d4e5e61ed49da11e36eaa37bc24334f
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70791533"
---
# <a name="sqlcommand-execution-with-a-sqlnotificationrequest"></a><span data-ttu-id="c5e0c-102">SqlCommand-Ausführung mit "SqlNotificationRequest"</span><span class="sxs-lookup"><span data-stu-id="c5e0c-102">SqlCommand Execution with a SqlNotificationRequest</span></span>

<span data-ttu-id="c5e0c-103">Ein <xref:System.Data.SqlClient.SqlCommand>-Objekt kann so konfiguriert werden, dass eine Benachrichtigung generiert wird, sobald zuvor vom Server abgerufene Daten geändert werden, wodurch die Ergebnisse einer erneuten Ausführung der Abfrage anders aussehen würden.</span><span class="sxs-lookup"><span data-stu-id="c5e0c-103">A <xref:System.Data.SqlClient.SqlCommand> can be configured to generate a notification when data changes after it has been fetched from the server and the result set would be different if the query were executed again.</span></span> <span data-ttu-id="c5e0c-104">Eine solche Konfiguration bietet sich für Szenarien an, in denen Sie benutzerdefinierte Benachrichtigungswarteschlangen auf dem Server verwenden oder keine aktiven Objekte verwalten möchten.</span><span class="sxs-lookup"><span data-stu-id="c5e0c-104">This is useful for scenarios where you want to use custom notification queues on the server or when you do not want to maintain live objects.</span></span>

## <a name="creating-the-notification-request"></a><span data-ttu-id="c5e0c-105">Erstellen der Benachrichtigungsanforderung</span><span class="sxs-lookup"><span data-stu-id="c5e0c-105">Creating the Notification Request</span></span>

<span data-ttu-id="c5e0c-106">Sie können ein <xref:System.Data.Sql.SqlNotificationRequest>-Objekt verwenden, um die Benachrichtigungsanforderung zu erstellen, indem Sie es an ein `SqlCommand`-Objekt binden.</span><span class="sxs-lookup"><span data-stu-id="c5e0c-106">You can use a <xref:System.Data.Sql.SqlNotificationRequest> object to create the notification request by binding it to a `SqlCommand` object.</span></span> <span data-ttu-id="c5e0c-107">Sobald die Anforderung erstellt ist, benötigen Sie das `SqlNotificationRequest`-Objekt nicht mehr.</span><span class="sxs-lookup"><span data-stu-id="c5e0c-107">Once the request is created, you no longer need the `SqlNotificationRequest` object.</span></span> <span data-ttu-id="c5e0c-108">Sie können die Warteschlange dann nach Benachrichtigungen abfragen und auf diese entsprechend reagieren.</span><span class="sxs-lookup"><span data-stu-id="c5e0c-108">You can query the queue for any notifications and respond appropriately.</span></span> <span data-ttu-id="c5e0c-109">Benachrichtigungen können auch dann ausgegeben werden, wenn die Anwendung geschlossen und anschließend wieder gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="c5e0c-109">Notifications can occur even if the application is shut down and subsequently restarted.</span></span>

<span data-ttu-id="c5e0c-110">Wenn der Befehl mit der zugehörigen Benachrichtigung ausgeführt wird, lösen alle Änderungen im ursprünglichen Resultset das Senden einer Nachricht an die SQL Server-Warteschlange aus, die in der Benachrichtigungsanforderung konfiguriert wurde.</span><span class="sxs-lookup"><span data-stu-id="c5e0c-110">When the command with the associated notification is executed, any changes to the original result set trigger sending a message to the SQL Server queue that was configured in the notification request.</span></span>

<span data-ttu-id="c5e0c-111">Wie Sie die SQL Server-Warteschlange abrufen können und die Meldung interpretieren müssen, hängt von Ihrer Anwendung ab.</span><span class="sxs-lookup"><span data-stu-id="c5e0c-111">How you poll the SQL Server queue and interpret the message is specific to your application.</span></span> <span data-ttu-id="c5e0c-112">Die Anwendung ist dafür verantwortlich, die Warteschlange abzufragen und aufgrund der Meldung zu reagieren.</span><span class="sxs-lookup"><span data-stu-id="c5e0c-112">The application is responsible for polling the queue and reacting based on the contents of the message.</span></span>

> [!NOTE]
> <span data-ttu-id="c5e0c-113">Wenn Sie die SQL Server-Benachrichtigungsanforderungen mit <xref:System.Data.SqlClient.SqlDependency> verwenden, erstellen Sie einen eigenen Warteschlangennamen, statt den Standarddienstnamen zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="c5e0c-113">When using SQL Server notification requests with <xref:System.Data.SqlClient.SqlDependency>, create your own queue name instead of using the default service name.</span></span>

<span data-ttu-id="c5e0c-114">Es gibt keine neuen clientseitigen Sicherheitselemente für <xref:System.Data.Sql.SqlNotificationRequest>.</span><span class="sxs-lookup"><span data-stu-id="c5e0c-114">There are no new client-side security elements for <xref:System.Data.Sql.SqlNotificationRequest>.</span></span> <span data-ttu-id="c5e0c-115">Dies ist vor allem eine Serverfunktion, und der Server hat Sonderberechtigungen erstellt, die Benutzer für das Anfordern einer Benachrichtigung besitzen müssen.</span><span class="sxs-lookup"><span data-stu-id="c5e0c-115">This is primarily a server feature, and the server has created special privileges that users must have to request a notification.</span></span>

### <a name="example"></a><span data-ttu-id="c5e0c-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c5e0c-116">Example</span></span>

<span data-ttu-id="c5e0c-117">Das folgende Codefragment veranschaulicht, wie ein <xref:System.Data.Sql.SqlNotificationRequest>-Objekt erstellt und einem <xref:System.Data.SqlClient.SqlCommand>-Objekt zugeordnet wird.</span><span class="sxs-lookup"><span data-stu-id="c5e0c-117">The following code fragment demonstrates how to create a <xref:System.Data.Sql.SqlNotificationRequest> and associate it with a <xref:System.Data.SqlClient.SqlCommand>.</span></span>

```vb
' Assume connection is an open SqlConnection.
' Create a new SqlCommand object.
Dim command As New SqlCommand( _
  "SELECT ShipperID, CompanyName, Phone FROM dbo.Shippers", connection)

' Create a SqlNotificationRequest object.
Dim notifcationRequest As New SqlNotificationRequest()
notificationRequest.id = "NotificationID"
notificationRequest.Service = "mySSBQueue"

' Associate the notification request with the command.
command.Notification = notificationRequest
' Execute the command.
command.ExecuteReader()
' Process the DataReader.
' You can use Transact-SQL syntax to periodically poll the
' SQL Server queue to see if you have a new message.
```

```csharp
// Assume connection is an open SqlConnection.
// Create a new SqlCommand object.
SqlCommand command=new SqlCommand(
 "SELECT ShipperID, CompanyName, Phone FROM dbo.Shippers", connection);

// Create a SqlNotificationRequest object.
SqlNotificationRequest notificationRequest=new SqlNotificationRequest();
notificationRequest.id="NotificationID";
notificationRequest.Service="mySSBQueue";

// Associate the notification request with the command.
command.Notification=notificationRequest;
// Execute the command.
command.ExecuteReader();
// Process the DataReader.
// You can use Transact-SQL syntax to periodically poll the
// SQL Server queue to see if you have a new message.
```

## <a name="see-also"></a><span data-ttu-id="c5e0c-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c5e0c-118">See also</span></span>

- [<span data-ttu-id="c5e0c-119">Abfragebenachrichtigungen in SQL Server</span><span class="sxs-lookup"><span data-stu-id="c5e0c-119">Query Notifications in SQL Server</span></span>](query-notifications-in-sql-server.md)
- [<span data-ttu-id="c5e0c-120">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="c5e0c-120">ADO.NET Overview</span></span>](../ado-net-overview.md)
