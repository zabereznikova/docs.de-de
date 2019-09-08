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
# <a name="sqlcommand-execution-with-a-sqlnotificationrequest"></a>SqlCommand-Ausführung mit "SqlNotificationRequest"

Ein <xref:System.Data.SqlClient.SqlCommand>-Objekt kann so konfiguriert werden, dass eine Benachrichtigung generiert wird, sobald zuvor vom Server abgerufene Daten geändert werden, wodurch die Ergebnisse einer erneuten Ausführung der Abfrage anders aussehen würden. Eine solche Konfiguration bietet sich für Szenarien an, in denen Sie benutzerdefinierte Benachrichtigungswarteschlangen auf dem Server verwenden oder keine aktiven Objekte verwalten möchten.

## <a name="creating-the-notification-request"></a>Erstellen der Benachrichtigungsanforderung

Sie können ein <xref:System.Data.Sql.SqlNotificationRequest>-Objekt verwenden, um die Benachrichtigungsanforderung zu erstellen, indem Sie es an ein `SqlCommand`-Objekt binden. Sobald die Anforderung erstellt ist, benötigen Sie das `SqlNotificationRequest`-Objekt nicht mehr. Sie können die Warteschlange dann nach Benachrichtigungen abfragen und auf diese entsprechend reagieren. Benachrichtigungen können auch dann ausgegeben werden, wenn die Anwendung geschlossen und anschließend wieder gestartet wird.

Wenn der Befehl mit der zugehörigen Benachrichtigung ausgeführt wird, lösen alle Änderungen im ursprünglichen Resultset das Senden einer Nachricht an die SQL Server-Warteschlange aus, die in der Benachrichtigungsanforderung konfiguriert wurde.

Wie Sie die SQL Server-Warteschlange abrufen können und die Meldung interpretieren müssen, hängt von Ihrer Anwendung ab. Die Anwendung ist dafür verantwortlich, die Warteschlange abzufragen und aufgrund der Meldung zu reagieren.

> [!NOTE]
> Wenn Sie die SQL Server-Benachrichtigungsanforderungen mit <xref:System.Data.SqlClient.SqlDependency> verwenden, erstellen Sie einen eigenen Warteschlangennamen, statt den Standarddienstnamen zu verwenden.

Es gibt keine neuen clientseitigen Sicherheitselemente für <xref:System.Data.Sql.SqlNotificationRequest>. Dies ist vor allem eine Serverfunktion, und der Server hat Sonderberechtigungen erstellt, die Benutzer für das Anfordern einer Benachrichtigung besitzen müssen.

### <a name="example"></a>Beispiel

Das folgende Codefragment veranschaulicht, wie ein <xref:System.Data.Sql.SqlNotificationRequest>-Objekt erstellt und einem <xref:System.Data.SqlClient.SqlCommand>-Objekt zugeordnet wird.

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

## <a name="see-also"></a>Siehe auch

- [Abfragebenachrichtigungen in SQL Server](query-notifications-in-sql-server.md)
- [Übersicht über ADO.NET](../ado-net-overview.md)
