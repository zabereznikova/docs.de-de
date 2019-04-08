---
title: "\"SqlDependency\" in einer ASP.NET-Anwendung"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ff226ce3-f6b5-47a1-8d22-dc78b67e07f5
ms.openlocfilehash: c49d28f42dec311d4a0c35a7115b00d989411358
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59073714"
---
# <a name="sqldependency-in-an-aspnet-application"></a>"SqlDependency" in einer ASP.NET-Anwendung
Das Beispiel in diesem Abschnitt zeigt die indirekte Verwendung von <xref:System.Data.SqlClient.SqlDependency> durch Verwendung des ASP.NET-<xref:System.Web.Caching.SqlCacheDependency>-Objekts. Das <xref:System.Web.Caching.SqlCacheDependency>-Objekt verwendet eine <xref:System.Data.SqlClient.SqlDependency>, um Benachrichtigungen zu empfangen und den Cache ordnungsgemäß zu aktualisieren.  
  
> [!NOTE]
>  Im Beispielcode wird davon ausgegangen, dass Sie abfragebenachrichtigungen aktiviert haben, durch Ausführen der Skripts in [Aktivieren von Abfragebenachrichtigungen](../../../../../docs/framework/data/adonet/sql/enabling-query-notifications.md).  
  
## <a name="about-the-sample-application"></a>Die Beispielanwendung  
 Der beispielanwendung wird eine einzelne ASP.NET-Webseite verwendet, um Produktinformationen aus anzuzeigen die **AdventureWorks** SQL Server-Datenbank in eine <xref:System.Web.UI.WebControls.GridView> Steuerelement. Beim Laden der Seite schreibt der Code die aktuelle Zeit in ein <xref:System.Web.UI.WebControls.Label>-Steuerelement. Anschließend wird ein <xref:System.Web.Caching.SqlCacheDependency>-Objekt definiert, und es werden Eigenschaften für das <xref:System.Web.Caching.Cache>-Objekt festgelegt, um die Daten für bis zu drei Minuten zwischenzuspeichern. Der Code stellt dann eine Verbindung mit der Datenbank her und ruft die Daten ab. Wenn die Seite geladen ist und die Anwendung ausgeführt wird, ruft ASP.NET Daten aus dem Cache ab, die Sie anhand dessen verifizieren können, dass sich die Zeit auf der Seite nicht ändert. Wenn sich die überwachten Daten ändern, macht ASP.NET den Cache ungültig und füllt das `GridView`-Steuerelement mit frischen Daten auf. Dabei wird die im `Label`-Steuerelement angezeigte Zeit aktualisiert.  
  
## <a name="creating-the-sample-application"></a>Erstellen der Beispielanwendung  
 Gehen Sie zum Erstellen und Ausführen der Beispielanwendung wie folgt vor:  
  
1.  Erstellen Sie eine neue ASP.NET-Website.  
  
2.  Fügen Sie der Seite Default.aspx<xref:System.Web.UI.WebControls.Label> ein <xref:System.Web.UI.WebControls.GridView>-Steuerelement und ein -Steuerelement hinzu.  
  
3.  Öffnen Sie das Klassenmodul der Seite, und fügen Sie die folgenden Anweisungen hinzu:  
  
    ```vb  
    Option Strict On  
    Option Explicit On  
  
    Imports System.Data.SqlClient  
    ```  
  
    ```csharp  
    using System.Data.SqlClient;  
    using System.Web.Caching;  
    ```  
  
4.  Fügen Sie dem `Page_Load`-Ereignis der Seite folgenden Code hinzu:  
  
     [!code-csharp[DataWorks SqlDependency.AspNet#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlDependency.AspNet/CS/Default.aspx.cs#1)]
     [!code-vb[DataWorks SqlDependency.AspNet#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlDependency.AspNet/VB/Default.aspx.vb#1)]  
  
5.  Fügen Sie zwei Hilfsmethoden hinzu, `GetConnectionString` und `GetSQL`. Die definierte Verbindungszeichenfolge verwendet integrierte Sicherheit. Sie müssen Sie sicherstellen, dass die von Ihnen verwendete Konto, die erforderlichen Datenbankberechtigungen und dass verfügt der-Beispieldatenbank **AdventureWorks**, Benachrichtigungen aktiviert.
  
     [!code-csharp[DataWorks SqlDependency.AspNet#2](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlDependency.AspNet/CS/Default.aspx.cs#2)]
     [!code-vb[DataWorks SqlDependency.AspNet#2](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlDependency.AspNet/VB/Default.aspx.vb#2)]  
  
### <a name="testing-the-application"></a>Testen der Anwendung  
 Die im Webformular angezeigten Daten werden von der Anwendung zwischengespeichert und, sofern keine Aktivitäten zu verzeichnen sind, alle drei Minuten aktualisiert. Wenn eine Änderung an der Datenbank vorgenommen wird, wird der Cache sofort aktualisiert. Starten Sie die Anwendung von Visual Studio aus. Visual Studio lädt die Seite in den Browser. Die angezeigte Uhrzeit für das Cacheupdate gibt an, wann der Cache zuletzt aktualisiert wurde. Warten Sie drei Minuten, und aktualisieren Sie dann die Seite. Daraufhin kommt es zu einem Postbackereignis. Beachten Sie, dass sich die auf der Seite angezeigte Zeit geändert hat. Wenn Sie die Seite vor Ablauf von drei Minuten aktualisieren, ändert sich die auf der Seite angezeigte Uhrzeit nicht.  
  
 Aktualisieren Sie jetzt die Daten in der Datenbank mit einem Transact-SQL-UPDATE-Befehl. Die angezeigte Uhrzeit gibt jetzt an, dass der Cache mit den neuen Daten aus der Datenbank aktualisiert wurde. Beachten Sie, dass der Cache zwar aktualisiert wurde, dass aber die auf der Seite angezeigte Uhrzeit sich erst ändert, wenn ein Postbackereignis eintritt.  
  
## <a name="see-also"></a>Siehe auch

- [Abfragebenachrichtigungen in SQL Server](../../../../../docs/framework/data/adonet/sql/query-notifications-in-sql-server.md)
- [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
