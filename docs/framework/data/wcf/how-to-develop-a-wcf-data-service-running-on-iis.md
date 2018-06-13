---
title: 'Vorgehensweise: Entwickeln eines WCF-Datendiensts, der auf IIS ausgeführt wird'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, developing
- WCF Data Services, deploying
- WCF Data Services, hosting
ms.assetid: f6f768c5-4989-49e3-a36f-896ab4ded86e
ms.openlocfilehash: c9b0128de6459c65e42fc2935222aecc643ec1d5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33362513"
---
# <a name="how-to-develop-a-wcf-data-service-running-on-iis"></a><span data-ttu-id="967ad-102">Vorgehensweise: Entwickeln eines WCF-Datendiensts, der auf IIS ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="967ad-102">How to: Develop a WCF Data Service Running on IIS</span></span>
<span data-ttu-id="967ad-103">In diesem Thema zeigt, wie [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] einen Datendienst erstellen, die auf die Beispieldatenbank Northwind basiert, die von einer ASP.NET-Webanwendung gehostet wird, die auf Internet Information Services (IIS) ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="967ad-103">This topic shows how to use [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] to create a data service that is based on the Northwind sample database that is hosted by an ASP.NET Web application that is running on Internet Information Services (IIS).</span></span> <span data-ttu-id="967ad-104">Ein Beispiel zum gleichen Northwind-Datendienst als eine ASP.NET-Webanwendung erstellen, die auf dem ASP.NET Development Server ausgeführt wird, finden Sie die [WCF Data Services-Schnellstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="967ad-104">For an example of how to create the same Northwind data service as an ASP.NET Web application that runs on the ASP.NET Development Server, see the [WCF Data Services quickstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="967ad-105">Um den Northwind-Datendienst zu erstellen, muss die Northwind-Beispieldatenbank auf dem lokalen Computer installiert sein.</span><span class="sxs-lookup"><span data-stu-id="967ad-105">To create the Northwind data service, you must have installed the Northwind sample database on the local computer.</span></span> <span data-ttu-id="967ad-106">Diese Beispieldatenbank kann von der Downloadseite [Beispieldatenbanken für SQL Server](http://go.microsoft.com/fwlink/?linkid=24758)heruntergeladen werden.</span><span class="sxs-lookup"><span data-stu-id="967ad-106">To download this sample database, see the download page, [Sample Databases for SQL Server](http://go.microsoft.com/fwlink/?linkid=24758).</span></span>  
  
 <span data-ttu-id="967ad-107">In diesem Thema wird gezeigt, wie ein Datendienst mithilfe des Entity Framework-Anbieters erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="967ad-107">This topic shows how to create a data service by using the Entity Framework provider.</span></span> <span data-ttu-id="967ad-108">Weitere Datendiensteanbieter sind verfügbar.</span><span class="sxs-lookup"><span data-stu-id="967ad-108">Other data services providers are available.</span></span> <span data-ttu-id="967ad-109">Weitere Informationen finden Sie unter [Datendiensteanbieter](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="967ad-109">For more information, see [Data Services Providers](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md).</span></span>  
  
 <span data-ttu-id="967ad-110">Nach dem Erstellen des Diensts, müssen Sie explizit den Zugriff auf Datendienstressourcen bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="967ad-110">After you create the service, you must explicitly provide access to data service resources.</span></span> <span data-ttu-id="967ad-111">Weitere Informationen finden Sie unter [Vorgehensweise: Aktivieren von Zugriff auf den Datendienst](../../../../docs/framework/data/wcf/how-to-enable-access-to-the-data-service-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="967ad-111">For more information, see [How to: Enable Access to the Data Service](../../../../docs/framework/data/wcf/how-to-enable-access-to-the-data-service-wcf-data-services.md).</span></span>  
  
### <a name="to-create-the-aspnet-web-application-that-runs-on-iis"></a><span data-ttu-id="967ad-112">So erstellen Sie die in IIS ausgeführte ASP.NET-Webanwendung</span><span class="sxs-lookup"><span data-stu-id="967ad-112">To create the ASP.NET Web application that runs on IIS</span></span>  
  
1.  <span data-ttu-id="967ad-113">In Visual Studio auf die **Datei** klicken Sie im Menü **neu**, und wählen Sie dann **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="967ad-113">In Visual Studio, on the **File** menu, select **New**, and then select **Project**.</span></span>  
  
2.  <span data-ttu-id="967ad-114">In der **neues Projekt** Dialogfeld Wählen Visual Basic oder Visual c# als Programmiersprache.</span><span class="sxs-lookup"><span data-stu-id="967ad-114">In the **New Project** dialog box, select either Visual Basic or Visual C# as the programming language.</span></span>  
  
3.  <span data-ttu-id="967ad-115">In der **Vorlagen** klicken Sie im Bereich **ASP.NET-Webanwendung**.</span><span class="sxs-lookup"><span data-stu-id="967ad-115">In the **Templates** pane, select **ASP.NET Web Application**.</span></span> <span data-ttu-id="967ad-116">Hinweis: Wenn Sie Visual Studio Web Developer verwenden, müssen Sie anstelle einer neuen Webanwendung eine neue Website erstellen.</span><span class="sxs-lookup"><span data-stu-id="967ad-116">Note: If you use Visual Studio Web Developer, you must create a new Web site instead of a new Web application.</span></span>  
  
4.  <span data-ttu-id="967ad-117">Typ `NorthwindService` als den Namen des Projekts.</span><span class="sxs-lookup"><span data-stu-id="967ad-117">Type `NorthwindService` as the name of the project.</span></span>  
  
5.  <span data-ttu-id="967ad-118">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="967ad-118">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="967ad-119">Auf der **Projekt** klicken Sie im Menü **NorthwindService-Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="967ad-119">On the **Project** menu, select **NorthwindService Properties**.</span></span>  
  
7.  <span data-ttu-id="967ad-120">Wählen Sie die **Web** Registerkarte, und wählen Sie dann **lokalen IIS-Webserver verwenden**.</span><span class="sxs-lookup"><span data-stu-id="967ad-120">Select the **Web** tab, and then select **Use Local IIS Web Server**.</span></span>  
  
8.  <span data-ttu-id="967ad-121">Klicken Sie auf **virtuelles Verzeichnis erstellen** , und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="967ad-121">Click **Create Virtual Directory** and then click **OK**.</span></span>  
  
9. <span data-ttu-id="967ad-122">Führen Sie an der Eingabeaufforderung mit Administratorrechten einen der folgenden Befehle aus (je nach Betriebssystem):</span><span class="sxs-lookup"><span data-stu-id="967ad-122">From the command prompt with administrator privileges, execute one of the following commands (depending on the operating system):</span></span>  
  
    -   <span data-ttu-id="967ad-123">32-Bit-Systeme:</span><span class="sxs-lookup"><span data-stu-id="967ad-123">32-bit systems:</span></span>  
  
        ```console
        "%windir%\Microsoft.NET\Framework\v3.0\Windows Communication Foundation\ServiceModelReg.exe" -i  
        ```  
  
    -   <span data-ttu-id="967ad-124">64-Bit-Systeme:</span><span class="sxs-lookup"><span data-stu-id="967ad-124">64-bit systems:</span></span>  
  
        ```console
        "%windir%\Microsoft.NET\Framework64\v3.0\Windows Communication Foundation\ServiceModelReg.exe" -i  
        ```  
  
     <span data-ttu-id="967ad-125">Hierdurch wird sichergestellt, dass Windows Communication Foundation (WCF) auf dem Computer registriert wird.</span><span class="sxs-lookup"><span data-stu-id="967ad-125">This makes sure that Windows Communication Foundation (WCF) is registered on the computer.</span></span>  
  
10. <span data-ttu-id="967ad-126">Führen Sie an der Eingabeaufforderung mit Administratorrechten einen der folgenden Befehle aus (je nach Betriebssystem):</span><span class="sxs-lookup"><span data-stu-id="967ad-126">From the command prompt with administrator privileges, execute one of the following commands (depending on the operating system):</span></span>  
  
    -   <span data-ttu-id="967ad-127">32-Bit-Systeme:</span><span class="sxs-lookup"><span data-stu-id="967ad-127">32-bit systems:</span></span>  
  
        ```console
        "%windir%\Microsoft.NET\Framework\v4.0.30319\aspnet_regiis.exe" -i -enable  
        ```  
  
    -   <span data-ttu-id="967ad-128">64-Bit-Systeme:</span><span class="sxs-lookup"><span data-stu-id="967ad-128">64-bit systems:</span></span>  
  
        ```console
        "%windir%\Microsoft.NET\Framework64\v4.0.30319\aspnet_regiis.exe" -i -enable  
        ```  
  
     <span data-ttu-id="967ad-129">Dadurch wird sichergestellt, dass ISS ordnungsgemäß ausgeführt wird, nachdem WCF auf dem Computer installiert wurde.</span><span class="sxs-lookup"><span data-stu-id="967ad-129">This makes sure that IIS runs correctly after WCF has been installed on the computer.</span></span> <span data-ttu-id="967ad-130">Möglicherweise müssen Sie außerdem einen Neustart von IIS ausführen.</span><span class="sxs-lookup"><span data-stu-id="967ad-130">You might have to also restart IIS.</span></span>  
  
11. <span data-ttu-id="967ad-131">Wenn die ASP.NET-Anwendung in IIS7 ausgeführt wird, müssen Sie außerdem die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="967ad-131">When the ASP.NET application runs on IIS7, you must also perform the following steps:</span></span>  
  
    1.  <span data-ttu-id="967ad-132">Öffnen Sie den IIS-Manager, und navigieren Sie zu der Anwendung PhotoService unter **Default Web Site**.</span><span class="sxs-lookup"><span data-stu-id="967ad-132">Open IIS Manager and navigate to the PhotoService application under **Default Web Site**.</span></span>  
  
    2.  <span data-ttu-id="967ad-133">In **Ansicht "Features"**, doppelklicken Sie auf **Authentifizierung**.</span><span class="sxs-lookup"><span data-stu-id="967ad-133">In **Features View**, double-click **Authentication**.</span></span>  
  
    3.  <span data-ttu-id="967ad-134">Auf der **Authentifizierung** Seite **anonyme Authentifizierung**.</span><span class="sxs-lookup"><span data-stu-id="967ad-134">On the **Authentication** page, select **Anonymous Authentication**.</span></span>  
  
    4.  <span data-ttu-id="967ad-135">In der **Aktionen** Bereich, klicken Sie auf **bearbeiten** um den Sicherheitsprinzipal festzulegen, unter dem anonyme Benutzer der Website hergestellt wird.</span><span class="sxs-lookup"><span data-stu-id="967ad-135">In the **Actions** pane, click **Edit** to set the security principal under which anonymous users will connect to the site.</span></span>  
  
    5.  <span data-ttu-id="967ad-136">In der **Anmeldeinformationen für anonyme Authentifizierung bearbeiten** wählen Sie im Dialogfeld **Anwendungspoolidentität**.</span><span class="sxs-lookup"><span data-stu-id="967ad-136">In the **Edit Anonymous Authentication Credentials** dialog box, select **Application pool identity**.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="967ad-137">Wenn Sie das Netzwerkdienstkonto verwenden, gewähren Sie anonymen Benutzern alle Zugriffsrechte dieses Kontos für das interne Netzwerk.</span><span class="sxs-lookup"><span data-stu-id="967ad-137">When you use the Network Service account, you grant anonymous users all the internal network access associated with that account.</span></span>  
  
12. <span data-ttu-id="967ad-138">Führen Sie mit SQL Server Management Studio, dem SQLCMD-Hilfsprogramm oder dem Transact-SQL-Editor in Visual Studio den folgenden Transact-SQL-Befehl für die Instanz von SQL Server aus, der die Northwind-Datenbank angefügt ist:</span><span class="sxs-lookup"><span data-stu-id="967ad-138">By using SQL Server Management Studio, the sqlcmd.exe utility, or the Transact-SQL Editor in Visual Studio, execute the following Transact-SQL command against the instance of SQL Server that has the Northwind database attached:</span></span>  
  
    ```sql  
    CREATE LOGIN [NT AUTHORITY\NETWORK SERVICE] FROM WINDOWS;  
    GO   
    ```  
  
     <span data-ttu-id="967ad-139">Dadurch wird in der SQL Server-Instanz eine Anmeldung für das Windows-Konto erstellt, das verwendet wurde, um IIS auszuführen.</span><span class="sxs-lookup"><span data-stu-id="967ad-139">This creates a login in the SQL Server instance for the Windows account used to run IIS.</span></span> <span data-ttu-id="967ad-140">Dies ermöglicht es IIS, eine Verbindung mit der SQL Server-Instanz herzustellen.</span><span class="sxs-lookup"><span data-stu-id="967ad-140">This enables IIS to connect to the SQL Server instance.</span></span>  
  
13. <span data-ttu-id="967ad-141">Führen Sie mit der angefügten Northwind-Datenbank, die folgenden Transact-SQL-Befehle aus:</span><span class="sxs-lookup"><span data-stu-id="967ad-141">With the Northwind database attached, execute the following Transact-SQL commands:</span></span>  
  
    ```sql  
    USE Northwind  
    GO  
    CREATE USER [NT AUTHORITY\NETWORK SERVICE]   
    FOR LOGIN [NT AUTHORITY\NETWORK SERVICE] WITH DEFAULT_SCHEMA=[dbo];  
    GO  
    ALTER LOGIN [NT AUTHORITY\NETWORK SERVICE]   
    WITH DEFAULT_DATABASE=[Northwind];   
    GO  
    EXEC sp_addrolemember 'db_datareader', 'NT AUTHORITY\NETWORK SERVICE'  
    GO  
    EXEC sp_addrolemember 'db_datawriter', 'NT AUTHORITY\NETWORK SERVICE'  
    GO   
    ```  
  
     <span data-ttu-id="967ad-142">Hierdurch werden der neuen Anmeldung Rechte erteilt, die IIS den Lese- und Schreibzugriff für Daten der Northwind-Datenbank zu gewähren.</span><span class="sxs-lookup"><span data-stu-id="967ad-142">This grants rights to the new login, which enables IIS to read data from and write data to the Northwind database.</span></span>  
  
### <a name="to-define-the-data-model"></a><span data-ttu-id="967ad-143">So definieren Sie das Datenmodell</span><span class="sxs-lookup"><span data-stu-id="967ad-143">To define the data model</span></span>  
  
1.  <span data-ttu-id="967ad-144">In **Projektmappen-Explorer**mit der rechten Maustaste auf den Namen des ASP.NET-Projekts,, und klicken Sie dann auf **neues Element hinzufügen.**</span><span class="sxs-lookup"><span data-stu-id="967ad-144">In **Solution Explorer**, right-click the name of the ASP.NET project, and then click **Add New Item.**</span></span>  
  
2.  <span data-ttu-id="967ad-145">In der **neues Element hinzufügen** wählen Sie im Dialogfeld **ADO.NET Entity Data Model**.</span><span class="sxs-lookup"><span data-stu-id="967ad-145">In the **Add New Item** dialog box, select **ADO.NET Entity Data Model**.</span></span>  
  
3.  <span data-ttu-id="967ad-146">Geben Sie für den Namen des Datenmodells, `Northwind.edmx`.</span><span class="sxs-lookup"><span data-stu-id="967ad-146">For the name of the data model, type `Northwind.edmx`.</span></span>  
  
4.  <span data-ttu-id="967ad-147">Wählen Sie in der Entity Data Model-Assistenten **aus Datenbank generieren**, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="967ad-147">In the Entity Data Model Wizard, select **Generate from Database**, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="967ad-148">Das Datenmodell mit der Datenbank zu verbinden, indem Sie einen der folgenden Schritte aus, und klicken Sie dann auf **Weiter**:</span><span class="sxs-lookup"><span data-stu-id="967ad-148">Connect the data model to the database by doing one of the following steps, and then click **Next**:</span></span>  
  
    -   <span data-ttu-id="967ad-149">Wenn Sie keine datenbankverbindung, die bereits konfiguriert haben, klicken Sie auf **neue Verbindung** und erstellen Sie eine neue Verbindung.</span><span class="sxs-lookup"><span data-stu-id="967ad-149">If you do not have a database connection already configured, click **New Connection** and create a new connection.</span></span> <span data-ttu-id="967ad-150">Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen von Verbindungen mit SQL Server-Datenbanken](http://go.microsoft.com/fwlink/?LinkId=123631).</span><span class="sxs-lookup"><span data-stu-id="967ad-150">For more information, see [How to: Create Connections to SQL Server Databases](http://go.microsoft.com/fwlink/?LinkId=123631).</span></span> <span data-ttu-id="967ad-151">Dieser SQL Server-Instanz muss die Northwind-Beispieldatenbank angefügt sein.</span><span class="sxs-lookup"><span data-stu-id="967ad-151">This SQL Server instance must have the Northwind sample database attached.</span></span>  
  
         <span data-ttu-id="967ad-152">\- oder –</span><span class="sxs-lookup"><span data-stu-id="967ad-152">\- or -</span></span>  
  
    -   <span data-ttu-id="967ad-153">Wenn bereits eine Datenbankverbindung für die Northwind-Datenbank konfiguriert wurde, wählen Sie diese Verbindung in der Liste der Verbindungen aus.</span><span class="sxs-lookup"><span data-stu-id="967ad-153">If you have a database connection already configured to connect to the Northwind database, select that connection from the list of connections.</span></span>  
  
6.  <span data-ttu-id="967ad-154">Aktivieren Sie auf der letzten Seite des Assistenten die Kontrollkästchen für alle Tabellen in der Datenbank, und deaktivieren Sie die Kontrollkästchen für Sichten und gespeicherte Prozeduren.</span><span class="sxs-lookup"><span data-stu-id="967ad-154">On the final page of the wizard, select the check boxes for all tables in the database, and clear the check boxes for views and stored procedures.</span></span>  
  
7.  <span data-ttu-id="967ad-155">Klicken Sie auf **Fertig stellen** um den Assistenten zu schließen.</span><span class="sxs-lookup"><span data-stu-id="967ad-155">Click **Finish** to close the wizard.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="967ad-156">Das erstellte Datenmodell macht Fremdschlüsseleigenschaften von Entitätstypen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="967ad-156">This generated data model exposes foreign key properties on entity types.</span></span> <span data-ttu-id="967ad-157">Mit Visual Studio 2008 erstellte Datenmodelle enthalten diese Fremdschlüsseleigenschaften nicht.</span><span class="sxs-lookup"><span data-stu-id="967ad-157">Data models created using Visual Studio 2008 do not include these foreign key properties.</span></span> <span data-ttu-id="967ad-158">Aus diesem Grund müssen Sie die Clientdatendienstklassen jeglicher Clientanwendungen aktualisieren, die für den Zugriff auf den mit Visual Studio 2008 erstellten Northwind-Datendienst erstellt wurden, bevor Sie auf diese Version des Northwind-Datendiensts zugreifen.</span><span class="sxs-lookup"><span data-stu-id="967ad-158">Because of this, you must update the client data service classes of any client applications that were created to access the Northwind data service that was created using Visual Studio 2008 before attempting to access this version of the Northwind data service.</span></span>  
  
### <a name="to-create-the-data-service"></a><span data-ttu-id="967ad-159">So erstellen Sie den Datendienst</span><span class="sxs-lookup"><span data-stu-id="967ad-159">To create the data service</span></span>  
  
1.  <span data-ttu-id="967ad-160">In **Projektmappen-Explorer**mit der rechten Maustaste auf den Namen des ASP.NET-Projekts,, und klicken Sie dann auf **neues Element hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="967ad-160">In **Solution Explorer**, right-click the name of your ASP.NET project, and then click **Add New Item**.</span></span>  
  
2.  <span data-ttu-id="967ad-161">In der **neues Element hinzufügen** wählen Sie im Dialogfeld **ADO.NET-Datendienst**.</span><span class="sxs-lookup"><span data-stu-id="967ad-161">In the **Add New Item** dialog box, select **ADO.NET Data Service**.</span></span>  
  
3.  <span data-ttu-id="967ad-162">Geben Sie den Namen des Diensts zu `Northwind`.</span><span class="sxs-lookup"><span data-stu-id="967ad-162">For the name of the service, type `Northwind`.</span></span>  
  
     <span data-ttu-id="967ad-163">Visual Studio erstellt das XML-Markup und die Codedateien für den neuen Dienst.</span><span class="sxs-lookup"><span data-stu-id="967ad-163">Visual Studio creates the XML markup and code files for the new service.</span></span> <span data-ttu-id="967ad-164">In der Standardeinstellung wird das Fenster des Code-Editors geöffnet.</span><span class="sxs-lookup"><span data-stu-id="967ad-164">By default, the code-editor window opens.</span></span> <span data-ttu-id="967ad-165">In **Projektmappen-Explorer**, der Dienst müssen die Namen "Northwind", mit der Erweiterung. svc.cs oder. svc.vb.</span><span class="sxs-lookup"><span data-stu-id="967ad-165">In **Solution Explorer**, the service will have the name, Northwind, with the extension .svc.cs or .svc.vb.</span></span>  
  
4.  <span data-ttu-id="967ad-166">Ersetzen Sie im Code für den Datendienst in der Definition der Klasse, die den Datendienst definiert, den Kommentar `/* TODO: put your data source class name here */` durch den Typ des Entitätscontainers des Datenmodells, in diesem Fall `NorthwindEntities`.</span><span class="sxs-lookup"><span data-stu-id="967ad-166">In the code for the data service, replace the comment `/* TODO: put your data source class name here */` in the definition of the class that defines the data service with the type that is the entity container of the data model, which in this case is `NorthwindEntities`.</span></span> <span data-ttu-id="967ad-167">Die Klassendefinition sollte wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="967ad-167">The class definition should look this the following:</span></span>  
  
     [!code-csharp[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria quickstart service/cs/northwind.svc.cs#servicedefinition)]
     [!code-vb[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart service/vb/northwind.svc.vb#servicedefinition)]  
  
## <a name="see-also"></a><span data-ttu-id="967ad-168">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="967ad-168">See Also</span></span>  
 [<span data-ttu-id="967ad-169">Verfügbarmachen der Daten als Dienst</span><span class="sxs-lookup"><span data-stu-id="967ad-169">Exposing Your Data as a Service</span></span>](../../../../docs/framework/data/wcf/exposing-your-data-as-a-service-wcf-data-services.md)
