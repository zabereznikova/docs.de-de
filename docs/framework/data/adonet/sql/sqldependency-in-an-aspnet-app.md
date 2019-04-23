---
title: "\"SqlDependency\" in einer ASP.NET-Anwendung"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ff226ce3-f6b5-47a1-8d22-dc78b67e07f5
ms.openlocfilehash: 67c1307bb18b3e86e05b56f4853a39f6831ab9cc
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59313592"
---
# <a name="sqldependency-in-an-aspnet-application"></a><span data-ttu-id="fad90-102">"SqlDependency" in einer ASP.NET-Anwendung</span><span class="sxs-lookup"><span data-stu-id="fad90-102">SqlDependency in an ASP.NET Application</span></span>
<span data-ttu-id="fad90-103">Das Beispiel in diesem Abschnitt zeigt die indirekte Verwendung von <xref:System.Data.SqlClient.SqlDependency> durch Verwendung des ASP.NET-<xref:System.Web.Caching.SqlCacheDependency>-Objekts.</span><span class="sxs-lookup"><span data-stu-id="fad90-103">The example in this section shows how to use <xref:System.Data.SqlClient.SqlDependency> indirectly by leveraging the ASP.NET <xref:System.Web.Caching.SqlCacheDependency> object.</span></span> <span data-ttu-id="fad90-104">Das <xref:System.Web.Caching.SqlCacheDependency>-Objekt verwendet eine <xref:System.Data.SqlClient.SqlDependency>, um Benachrichtigungen zu empfangen und den Cache ordnungsgemäß zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="fad90-104">The <xref:System.Web.Caching.SqlCacheDependency> object uses a <xref:System.Data.SqlClient.SqlDependency> to listen for notifications and correctly update the cache.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fad90-105">Im Beispielcode wird davon ausgegangen, dass Sie abfragebenachrichtigungen aktiviert haben, durch Ausführen der Skripts in [Aktivieren von Abfragebenachrichtigungen](../../../../../docs/framework/data/adonet/sql/enabling-query-notifications.md).</span><span class="sxs-lookup"><span data-stu-id="fad90-105">The sample code assumes that you have enabled query notifications by executing the scripts in [Enabling Query Notifications](../../../../../docs/framework/data/adonet/sql/enabling-query-notifications.md).</span></span>  
  
## <a name="about-the-sample-application"></a><span data-ttu-id="fad90-106">Die Beispielanwendung</span><span class="sxs-lookup"><span data-stu-id="fad90-106">About the Sample Application</span></span>  
 <span data-ttu-id="fad90-107">Der beispielanwendung wird eine einzelne ASP.NET-Webseite verwendet, um Produktinformationen aus anzuzeigen die **AdventureWorks** SQL Server-Datenbank in eine <xref:System.Web.UI.WebControls.GridView> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="fad90-107">The sample application uses a single ASP.NET Web page to display product information from the **AdventureWorks** SQL Server database in a <xref:System.Web.UI.WebControls.GridView> control.</span></span> <span data-ttu-id="fad90-108">Beim Laden der Seite schreibt der Code die aktuelle Zeit in ein <xref:System.Web.UI.WebControls.Label>-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="fad90-108">When the page loads, the code writes the current time to a <xref:System.Web.UI.WebControls.Label> control.</span></span> <span data-ttu-id="fad90-109">Anschließend wird ein <xref:System.Web.Caching.SqlCacheDependency>-Objekt definiert, und es werden Eigenschaften für das <xref:System.Web.Caching.Cache>-Objekt festgelegt, um die Daten für bis zu drei Minuten zwischenzuspeichern.</span><span class="sxs-lookup"><span data-stu-id="fad90-109">It then defines a <xref:System.Web.Caching.SqlCacheDependency> object and sets properties on the <xref:System.Web.Caching.Cache> object to store the cache data for up to three minutes.</span></span> <span data-ttu-id="fad90-110">Der Code stellt dann eine Verbindung mit der Datenbank her und ruft die Daten ab.</span><span class="sxs-lookup"><span data-stu-id="fad90-110">The code then connects to the database and retrieves the data.</span></span> <span data-ttu-id="fad90-111">Wenn die Seite geladen ist und die Anwendung ausgeführt wird, ruft ASP.NET Daten aus dem Cache ab, die Sie anhand dessen verifizieren können, dass sich die Zeit auf der Seite nicht ändert.</span><span class="sxs-lookup"><span data-stu-id="fad90-111">When the page is loaded and the application is running ASP.NET will retrieve data from the cache, which you can verify by noting that the time on the page does not change.</span></span> <span data-ttu-id="fad90-112">Wenn sich die überwachten Daten ändern, macht ASP.NET den Cache ungültig und füllt das `GridView`-Steuerelement mit frischen Daten auf. Dabei wird die im `Label`-Steuerelement angezeigte Zeit aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="fad90-112">If the data being monitored changes, ASP.NET invalidates the cache and repopulate the `GridView` control with fresh data, updating the time displayed in the `Label` control.</span></span>  
  
## <a name="creating-the-sample-application"></a><span data-ttu-id="fad90-113">Erstellen der Beispielanwendung</span><span class="sxs-lookup"><span data-stu-id="fad90-113">Creating the Sample Application</span></span>  
 <span data-ttu-id="fad90-114">Gehen Sie zum Erstellen und Ausführen der Beispielanwendung wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="fad90-114">Follow these steps to create and run the sample application:</span></span>  
  
1. <span data-ttu-id="fad90-115">Erstellen Sie eine neue ASP.NET-Website.</span><span class="sxs-lookup"><span data-stu-id="fad90-115">Create a new ASP.NET Web site.</span></span>  
  
2. <span data-ttu-id="fad90-116">Fügen Sie der Seite Default.aspx<xref:System.Web.UI.WebControls.Label> ein <xref:System.Web.UI.WebControls.GridView>-Steuerelement und ein -Steuerelement hinzu.</span><span class="sxs-lookup"><span data-stu-id="fad90-116">Add a <xref:System.Web.UI.WebControls.Label> and a <xref:System.Web.UI.WebControls.GridView> control to the Default.aspx page.</span></span>  
  
3. <span data-ttu-id="fad90-117">Öffnen Sie das Klassenmodul der Seite, und fügen Sie die folgenden Anweisungen hinzu:</span><span class="sxs-lookup"><span data-stu-id="fad90-117">Open the page's class module and add the following directives:</span></span>  
  
    ```vb  
    Option Strict On  
    Option Explicit On  
  
    Imports System.Data.SqlClient  
    ```  
  
    ```csharp  
    using System.Data.SqlClient;  
    using System.Web.Caching;  
    ```  
  
4. <span data-ttu-id="fad90-118">Fügen Sie dem `Page_Load`-Ereignis der Seite folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="fad90-118">Add the following code in the page's `Page_Load` event:</span></span>  
  
     [!code-csharp[DataWorks SqlDependency.AspNet#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlDependency.AspNet/CS/Default.aspx.cs#1)]
     [!code-vb[DataWorks SqlDependency.AspNet#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlDependency.AspNet/VB/Default.aspx.vb#1)]  
  
5. <span data-ttu-id="fad90-119">Fügen Sie zwei Hilfsmethoden hinzu, `GetConnectionString` und `GetSQL`.</span><span class="sxs-lookup"><span data-stu-id="fad90-119">Add two helper methods, `GetConnectionString` and `GetSQL`.</span></span> <span data-ttu-id="fad90-120">Die definierte Verbindungszeichenfolge verwendet integrierte Sicherheit.</span><span class="sxs-lookup"><span data-stu-id="fad90-120">The connection string defined uses integrated security.</span></span> <span data-ttu-id="fad90-121">Sie müssen Sie sicherstellen, dass die von Ihnen verwendete Konto, die erforderlichen Datenbankberechtigungen und dass verfügt der-Beispieldatenbank **AdventureWorks**, Benachrichtigungen aktiviert.</span><span class="sxs-lookup"><span data-stu-id="fad90-121">You will need to verify that the account you are using has the necessary database permissions and that the sample database, **AdventureWorks**, has notifications enabled.</span></span>
  
     [!code-csharp[DataWorks SqlDependency.AspNet#2](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlDependency.AspNet/CS/Default.aspx.cs#2)]
     [!code-vb[DataWorks SqlDependency.AspNet#2](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlDependency.AspNet/VB/Default.aspx.vb#2)]  
  
### <a name="testing-the-application"></a><span data-ttu-id="fad90-122">Testen der Anwendung</span><span class="sxs-lookup"><span data-stu-id="fad90-122">Testing the Application</span></span>  
 <span data-ttu-id="fad90-123">Die im Webformular angezeigten Daten werden von der Anwendung zwischengespeichert und, sofern keine Aktivitäten zu verzeichnen sind, alle drei Minuten aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="fad90-123">The application caches the data displayed on the Web form and refreshes it every three minutes if there is no activity.</span></span> <span data-ttu-id="fad90-124">Wenn eine Änderung an der Datenbank vorgenommen wird, wird der Cache sofort aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="fad90-124">If a change occurs to the database, the cache is refreshed immediately.</span></span> <span data-ttu-id="fad90-125">Starten Sie die Anwendung von Visual Studio aus. Visual Studio lädt die Seite in den Browser.</span><span class="sxs-lookup"><span data-stu-id="fad90-125">Run the application from Visual Studio, which loads the page into the browser.</span></span> <span data-ttu-id="fad90-126">Die angezeigte Uhrzeit für das Cacheupdate gibt an, wann der Cache zuletzt aktualisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="fad90-126">The cache refresh time displayed indicates when the cache was last refreshed.</span></span> <span data-ttu-id="fad90-127">Warten Sie drei Minuten, und aktualisieren Sie dann die Seite. Daraufhin kommt es zu einem Postbackereignis.</span><span class="sxs-lookup"><span data-stu-id="fad90-127">Wait three minutes, and then refresh the page, causing a postback event to occur.</span></span> <span data-ttu-id="fad90-128">Beachten Sie, dass sich die auf der Seite angezeigte Zeit geändert hat.</span><span class="sxs-lookup"><span data-stu-id="fad90-128">Note that the time displayed on the page has changed.</span></span> <span data-ttu-id="fad90-129">Wenn Sie die Seite vor Ablauf von drei Minuten aktualisieren, ändert sich die auf der Seite angezeigte Uhrzeit nicht.</span><span class="sxs-lookup"><span data-stu-id="fad90-129">If you refresh the page in less than three minutes, the time displayed on the page will remain the same.</span></span>  
  
 <span data-ttu-id="fad90-130">Aktualisieren Sie jetzt die Daten in der Datenbank mit einem Transact-SQL-UPDATE-Befehl.</span><span class="sxs-lookup"><span data-stu-id="fad90-130">Now update the data in the database, using a Transact-SQL UPDATE command and refresh the page.</span></span> <span data-ttu-id="fad90-131">Die angezeigte Uhrzeit gibt jetzt an, dass der Cache mit den neuen Daten aus der Datenbank aktualisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="fad90-131">The time displayed now indicates that the cache was refreshed with the new data from the database.</span></span> <span data-ttu-id="fad90-132">Beachten Sie, dass der Cache zwar aktualisiert wurde, dass aber die auf der Seite angezeigte Uhrzeit sich erst ändert, wenn ein Postbackereignis eintritt.</span><span class="sxs-lookup"><span data-stu-id="fad90-132">Note that although the cache is updated, the time displayed on the page does not change until a postback event occurs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fad90-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fad90-133">See also</span></span>

- [<span data-ttu-id="fad90-134">Abfragebenachrichtigungen in SQL Server</span><span class="sxs-lookup"><span data-stu-id="fad90-134">Query Notifications in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/query-notifications-in-sql-server.md)
- [<span data-ttu-id="fad90-135">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="fad90-135">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
