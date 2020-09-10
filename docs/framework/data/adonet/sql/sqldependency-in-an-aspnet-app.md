---
title: "\"SqlDependency\" in einer ASP.NET-Anwendung"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ff226ce3-f6b5-47a1-8d22-dc78b67e07f5
ms.openlocfilehash: 2ec9415f63151443d5008fbce471fabeb89cdb91
ms.sourcegitcommit: 1e8382d0ce8b5515864f8fbb178b9fd692a7503f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2020
ms.locfileid: "89656170"
---
# <a name="sqldependency-in-an-aspnet-application"></a>"SqlDependency" in einer ASP.NET-Anwendung
Das Beispiel in diesem Abschnitt zeigt, wie <xref:System.Data.SqlClient.SqlDependency> durch die Nutzung des ASP.NET <xref:System.Web.Caching.SqlCacheDependency>-Objekts indirekt verwendet werden kann. Das <xref:System.Web.Caching.SqlCacheDependency>-Objekt verwendet ein <xref:System.Data.SqlClient.SqlDependency>, um auf Benachrichtigungen zu lauschen und den Cache ordnungsgemäß zu aktualisieren.  
  
> [!NOTE]
> Im Beispielcode wird davon ausgegangen, dass Sie Abfrage Benachrichtigungen aktiviert haben, indem Sie die Skripts unter [Aktivieren von Abfrage Benachrichtigungen](enabling-query-notifications.md)ausführen.  
  
## <a name="about-the-sample-application"></a>Die Beispielanwendung  
 In der Beispielanwendung wird eine einzelne ASP.NET-Webseite verwendet, um Produktinformationen aus der SQL Server-**AdventureWorks**-Datenbank in einem <xref:System.Web.UI.WebControls.GridView>-Steuerelement anzuzeigen. Wenn die Seite geladen wird, schreibt der Code die aktuelle Uhrzeit in ein <xref:System.Web.UI.WebControls.Label>-Steuerelement. Anschließend wird ein <xref:System.Web.Caching.SqlCacheDependency>-Objekt definiert, und es werden Eigenschaften für das <xref:System.Web.Caching.Cache>-Objekt festgelegt, um die Cachedaten bis zu drei Minuten zu speichern. Der Code stellt dann eine Verbindung mit der Datenbank her und ruft die Daten ab. Wenn die Seite geladen ist und die Anwendung ausgeführt wird, ruft ASP.NET Daten aus dem Cache ab, was Sie bestätigen können, indem Sie feststellen, dass sich die Zeit auf der Seite nicht ändert. Wenn sich die überwachten Daten ändern, macht ASP.NET den Cache ungültig und füllt das `GridView`-Steuerelement erneut mit aktuellen Daten auf, wobei die im `Label`-Steuerelement angezeigte Uhrzeit aktualisiert wird.  
  
## <a name="creating-the-sample-application"></a>Erstellen der Beispielanwendung  
 Befolgen Sie diese Anweisungen, um die Beispielanwendung zu erstellen und auszuführen:  
  
1. Erstellen Sie eine neue ASP.NET-Website.  
  
2. Fügen Sie der Seite „Default.aspx“ die Steuerelemente <xref:System.Web.UI.WebControls.Label> und <xref:System.Web.UI.WebControls.GridView> hinzu.  
  
3. Öffnen Sie das Klassenmodul der Seite, und fügen Sie die folgenden Anweisungen hinzu:  
  
    ```vb  
    Option Strict On  
    Option Explicit On  
  
    Imports System.Data.SqlClient  
    ```  
  
    ```csharp  
    using System.Data.SqlClient;  
    using System.Web.Caching;  
    ```  
  
4. Fügen Sie den folgenden Code in das Ereignis `Page_Load` der Seite ein:  
  
     [!code-csharp[DataWorks SqlDependency.AspNet#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlDependency.AspNet/CS/Default.aspx.cs#1)]
     [!code-vb[DataWorks SqlDependency.AspNet#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlDependency.AspNet/VB/Default.aspx.vb#1)]  
  
5. Fügen Sie die beiden Hilfsmethoden `GetConnectionString` und `GetSQL` hinzu. Die definierte Verbindungszeichenfolge verwendet die integrierte Sicherheit. Sie müssen sicherstellen, dass das verwendete Konto über die erforderlichen Datenbankberechtigungen verfügt und dass für die Beispieldatenbank **AdventureWorks** Benachrichtigungen aktiviert sind.
  
     [!code-csharp[DataWorks SqlDependency.AspNet#2](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlDependency.AspNet/CS/Default.aspx.cs#2)]
     [!code-vb[DataWorks SqlDependency.AspNet#2](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlDependency.AspNet/VB/Default.aspx.vb#2)]  
  
### <a name="testing-the-application"></a>Testen der Anwendung  
 Die Anwendung speichert die auf dem Webformular angezeigten Daten im Cache und aktualisiert sie alle drei Minuten, sofern keine Aktivität stattfindet. Wenn eine Änderung an der Datenbank vorgenommen wird, wird der Cache sofort aktualisiert. Führen Sie die Anwendung in Visual Studio aus, wodurch die Seite in den Browser geladen wird. Die gezeigte Aktualisierungszeit des Caches gibt an, wann der Cache zuletzt aktualisiert wurde. Warten Sie drei Minuten, und laden Sie dann die Seite neu, wodurch ein Postback-Ereignis ausgelöst wird. Beachten Sie, dass sich die auf der Seite gezeigte Zeit geändert hat. Wenn Sie die Seite in weniger als drei Minuten aktualisieren, bleibt die auf der Seite gezeigte Zeit gleich.  
  
 Aktualisieren Sie nun mit dem Transact-SQL-Befehl UPDATE die Daten in der Datenbank und anschließend die Seite. Die jetzt gezeigte Zeit bedeutet, dass der Cache mit den neuen Daten aus der Datenbank aktualisiert wurde. Beachten Sie, dass, obwohl der Cache aktualisiert wurde, die auf der Seite gezeigte Zeit sich solange nicht ändert, bis ein Postback-Ereignis eintritt.  

## <a name="distributed-cache-synchronization-using-sql-dependency"></a>Synchronisierung verteilter Caches mithilfe von SQL-Abhängigkeit

Einige der verteilten Caches von Drittanbietern, z. b. [NCache](https://www.alachisoft.com/ncache) , bieten Unterstützung für die Synchronisierung von SQL-Datenbank und Cache mithilfe von [SQL-Abhängigkeiten](https://www.alachisoft.com/resources/docs/ncache/prog-guide/sql-dependency.html). Weitere Informationen und eine Beispiel-Quell Code Implementierung finden Sie unter [SQL-Abhängigkeits Beispiel für verteilte Caches](https://github.com/Alachisoft/NCache-Samples/tree/master/dotnet/Dependencies/SQLDependency).

## <a name="see-also"></a>Weitere Informationen

- [Abfrage Benachrichtigungen in SQL Server](query-notifications-in-sql-server.md)
- [Übersicht über ADO.NET](../ado-net-overview.md)
