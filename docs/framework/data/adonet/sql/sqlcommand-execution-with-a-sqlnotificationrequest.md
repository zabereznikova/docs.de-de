---
title: SqlCommand-Ausführung mit "SqlNotificationRequest"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1776f48f-9bea-41f6-83a4-c990c7a2c991
ms.openlocfilehash: 83450e6ace33e89ddd263a1514f74f4d4e231cf7
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43798572"
---
# <a name="sqlcommand-execution-with-a-sqlnotificationrequest"></a><span data-ttu-id="c00fa-102">SqlCommand-Ausführung mit "SqlNotificationRequest"</span><span class="sxs-lookup"><span data-stu-id="c00fa-102">SqlCommand Execution with a SqlNotificationRequest</span></span>
<span data-ttu-id="c00fa-103">Ein <xref:System.Data.SqlClient.SqlCommand>-Objekt kann so konfiguriert werden, dass eine Benachrichtigung generiert wird, sobald zuvor vom Server abgerufene Daten geändert werden, wodurch die Ergebnisse einer erneuten Ausführung der Abfrage anders aussehen würden.</span><span class="sxs-lookup"><span data-stu-id="c00fa-103">A <xref:System.Data.SqlClient.SqlCommand> can be configured to generate a notification when data changes after it has been fetched from the server and the result set would be different if the query were executed again.</span></span> <span data-ttu-id="c00fa-104">Eine solche Konfiguration bietet sich für Szenarien an, in denen Sie benutzerdefinierte Benachrichtigungswarteschlangen auf dem Server verwenden oder keine aktiven Objekte verwalten möchten.</span><span class="sxs-lookup"><span data-stu-id="c00fa-104">This is useful for scenarios where you want to use custom notification queues on the server or when you do not want to maintain live objects.</span></span>  
  
## <a name="creating-the-notification-request"></a><span data-ttu-id="c00fa-105">Erstellen der Benachrichtigungsanforderung</span><span class="sxs-lookup"><span data-stu-id="c00fa-105">Creating the Notification Request</span></span>  
 <span data-ttu-id="c00fa-106">Sie können ein <xref:System.Data.Sql.SqlNotificationRequest>-Objekt verwenden, um die Benachrichtigungsanforderung zu erstellen, indem Sie es an ein `SqlCommand`-Objekt binden.</span><span class="sxs-lookup"><span data-stu-id="c00fa-106">You can use a <xref:System.Data.Sql.SqlNotificationRequest> object to create the notification request by binding it to a `SqlCommand` object.</span></span> <span data-ttu-id="c00fa-107">Sobald die Anforderung erstellt ist, benötigen Sie das `SqlNotificationRequest`-Objekt nicht mehr.</span><span class="sxs-lookup"><span data-stu-id="c00fa-107">Once the request is created, you no longer need the `SqlNotificationRequest` object.</span></span> <span data-ttu-id="c00fa-108">Sie können die Warteschlange dann nach Benachrichtigungen abfragen und auf diese entsprechend reagieren.</span><span class="sxs-lookup"><span data-stu-id="c00fa-108">You can query the queue for any notifications and respond appropriately.</span></span> <span data-ttu-id="c00fa-109">Benachrichtigungen können auch dann ausgegeben werden, wenn die Anwendung geschlossen und anschließend wieder gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="c00fa-109">Notifications can occur even if the application is shut down and subsequently restarted.</span></span>  
  
 <span data-ttu-id="c00fa-110">Wenn der Befehl mit der zugehörigen Benachrichtigung ausgeführt wird, lösen alle Änderungen im ursprünglichen Resultset das Senden einer Nachricht an die SQL Server-Warteschlange aus, die in der Benachrichtigungsanforderung konfiguriert wurde.</span><span class="sxs-lookup"><span data-stu-id="c00fa-110">When the command with the associated notification is executed, any changes to the original result set trigger sending a message to the SQL Server queue that was configured in the notification request.</span></span>  
  
 <span data-ttu-id="c00fa-111">Wie Sie die SQL Server-Warteschlange abrufen können und die Meldung interpretieren müssen, hängt von Ihrer Anwendung ab.</span><span class="sxs-lookup"><span data-stu-id="c00fa-111">How you poll the SQL Server queue and interpret the message is specific to your application.</span></span> <span data-ttu-id="c00fa-112">Die Anwendung ist dafür verantwortlich, die Warteschlange abzufragen und aufgrund der Meldung zu reagieren.</span><span class="sxs-lookup"><span data-stu-id="c00fa-112">The application is responsible for polling the queue and reacting based on the contents of the message.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c00fa-113">Wenn Sie die SQL Server-Benachrichtigungsanforderungen mit <xref:System.Data.SqlClient.SqlDependency> verwenden, erstellen Sie einen eigenen Warteschlangennamen, statt den Standarddienstnamen zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="c00fa-113">When using SQL Server notification requests with <xref:System.Data.SqlClient.SqlDependency>, create your own queue name instead of using the default service name.</span></span>  
  
 <span data-ttu-id="c00fa-114">Es gibt keine neuen clientseitigen Sicherheitselemente für <xref:System.Data.Sql.SqlNotificationRequest>.</span><span class="sxs-lookup"><span data-stu-id="c00fa-114">There are no new client-side security elements for <xref:System.Data.Sql.SqlNotificationRequest>.</span></span> <span data-ttu-id="c00fa-115">Dies ist vor allem eine Serverfunktion, und der Server hat Sonderberechtigungen erstellt, die Benutzer für das Anfordern einer Benachrichtigung besitzen müssen.</span><span class="sxs-lookup"><span data-stu-id="c00fa-115">This is primarily a server feature, and the server has created special privileges that users must have to request a notification.</span></span>  
  
### <a name="example"></a><span data-ttu-id="c00fa-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c00fa-116">Example</span></span>  
 <span data-ttu-id="c00fa-117">Das folgende Codefragment veranschaulicht, wie ein <xref:System.Data.Sql.SqlNotificationRequest>-Objekt erstellt und einem <xref:System.Data.SqlClient.SqlCommand>-Objekt zugeordnet wird.</span><span class="sxs-lookup"><span data-stu-id="c00fa-117">The following code fragment demonstrates how to create a <xref:System.Data.Sql.SqlNotificationRequest> and associate it with a <xref:System.Data.SqlClient.SqlCommand>.</span></span>  
  
```vb  
' Assume connection is an open SqlConnection.  
' Create a new SqlCommand object.  
Dim command As New SqlCommand( _  
  "SELECT ShipperID, CompanyName, Phone FROM dbo.Shippers", connection)  
  
' Create a SqlNotificationRequest object.  
Dim notficationRequest As New SqlNotificationRequest()  
notficationRequest.id = "NotificationID"  
notficationRequest.Service = "mySSBQueue"  
  
' Associate the notification request with the command.  
command.Notification = notficationRequest  
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
SqlNotificationRequest notficationRequest=new SqlNotificationRequest();  
notficationRequest.id="NotificationID";  
notficationRequest.Service="mySSBQueue";  
  
// Associate the notification request with the command.  
command.Notification=notficationRequest;  
// Execute the command.  
command.ExecuteReader();  
// Process the DataReader.  
// You can use Transact-SQL syntax to periodically poll the   
// SQL Server queue to see if you have a new message.  
```  
  
## <a name="see-also"></a><span data-ttu-id="c00fa-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c00fa-118">See Also</span></span>  
 [<span data-ttu-id="c00fa-119">Abfragebenachrichtigungen in SQL Server</span><span class="sxs-lookup"><span data-stu-id="c00fa-119">Query Notifications in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/query-notifications-in-sql-server.md)  
 [<span data-ttu-id="c00fa-120">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="c00fa-120">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
