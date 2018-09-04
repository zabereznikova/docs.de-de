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
ms.openlocfilehash: af81e65dfd4661d62d7aa4a3e6075be312765cb7
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43538214"
---
# <a name="how-to-develop-a-wcf-data-service-running-on-iis"></a><span data-ttu-id="f5953-102">Vorgehensweise: Entwickeln von WCF Data Services auf IIS ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="f5953-102">How to: Develop a WCF data service running on IIS</span></span>

<span data-ttu-id="f5953-103">In diesem Thema wird gezeigt, wie mit WCF Data Services einen Datendienst erstellen, der auf der Northwind-Beispieldatenbank basiert, die von einer ASP.NET-Webanwendung gehostet wird, die auf Internet Information Services (IIS) ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f5953-103">This topic shows how to use WCF Data Services to create a data service that is based on the Northwind sample database that is hosted by an ASP.NET Web application that is running on Internet Information Services (IIS).</span></span> <span data-ttu-id="f5953-104">Ein Beispiel zum gleichen Northwind-Datendienst als eine ASP.NET-Webanwendung erstellen, die auf ASP.NET Development Server ausgeführt wird, finden Sie die [WCF Data Services-Schnellstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="f5953-104">For an example of how to create the same Northwind data service as an ASP.NET Web application that runs on the ASP.NET Development Server, see the [WCF Data Services quickstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).</span></span>

> [!NOTE]
> <span data-ttu-id="f5953-105">Um den Northwind-Datendienst zu erstellen, muss die Northwind-Beispieldatenbank auf dem lokalen Computer installiert sein.</span><span class="sxs-lookup"><span data-stu-id="f5953-105">To create the Northwind data service, you must have installed the Northwind sample database on the local computer.</span></span> <span data-ttu-id="f5953-106">Diese Beispieldatenbank, finden Sie unter auf der Downloadseite des [Beispieldatenbanken für SQL Server](https://go.microsoft.com/fwlink/?linkid=24758).</span><span class="sxs-lookup"><span data-stu-id="f5953-106">To download this sample database, see the download page, [Sample Databases for SQL Server](https://go.microsoft.com/fwlink/?linkid=24758).</span></span>

 <span data-ttu-id="f5953-107">In diesem Thema wird gezeigt, wie ein Datendienst mithilfe des Entity Framework-Anbieters erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="f5953-107">This topic shows how to create a data service by using the Entity Framework provider.</span></span> <span data-ttu-id="f5953-108">Weitere Datendiensteanbieter sind verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f5953-108">Other data services providers are available.</span></span> <span data-ttu-id="f5953-109">Weitere Informationen finden Sie unter [Datendiensteanbieter](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="f5953-109">For more information, see [Data Services Providers](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md).</span></span>

 <span data-ttu-id="f5953-110">Nach dem Erstellen des Diensts, müssen Sie explizit den Zugriff auf Datendienstressourcen bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="f5953-110">After you create the service, you must explicitly provide access to data service resources.</span></span> <span data-ttu-id="f5953-111">Weitere Informationen finden Sie unter [Vorgehensweise: Aktivieren Sie den Zugriff auf den Datendienst](../../../../docs/framework/data/wcf/how-to-enable-access-to-the-data-service-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="f5953-111">For more information, see [How to: Enable Access to the Data Service](../../../../docs/framework/data/wcf/how-to-enable-access-to-the-data-service-wcf-data-services.md).</span></span>

## <a name="create-the-aspnet-web-application-that-runs-on-iis"></a><span data-ttu-id="f5953-112">Erstellen der ASP.NET-Webanwendung, die unter IIS ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f5953-112">Create the ASP.NET web application that runs on IIS</span></span>

1. <span data-ttu-id="f5953-113">In Visual Studio auf die **Datei** , wählen Sie im Menü **neu** > **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="f5953-113">In Visual Studio, on the **File** menu, select **New** > **Project**.</span></span>

2. <span data-ttu-id="f5953-114">In der **neues Projekt** wählen Sie im Dialogfeld die **installiert** > [**Visual C#-** oder **Visual Basic**] > **Web** Kategorie.</span><span class="sxs-lookup"><span data-stu-id="f5953-114">In the **New Project** dialog box, select the **Installed** > [**Visual C#** or **Visual Basic**] > **Web** category.</span></span>

3. <span data-ttu-id="f5953-115">Wählen Sie die **ASP.NET-Webanwendung** Vorlage.</span><span class="sxs-lookup"><span data-stu-id="f5953-115">Select the **ASP.NET Web Application** template.</span></span>

1. <span data-ttu-id="f5953-116">Geben Sie `NorthwindService` als den Namen des Projekts.</span><span class="sxs-lookup"><span data-stu-id="f5953-116">Enter `NorthwindService` as the name of the project.</span></span>

5. <span data-ttu-id="f5953-117">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="f5953-117">Click **OK**.</span></span>

6. <span data-ttu-id="f5953-118">Auf der **Projekt** , wählen Sie im Menü **NorthwindService-Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="f5953-118">On the **Project** menu, select **NorthwindService Properties**.</span></span>

7. <span data-ttu-id="f5953-119">Wählen Sie die **Web** Registerkarte, und wählen Sie dann **lokalen IIS-Webserver verwenden**.</span><span class="sxs-lookup"><span data-stu-id="f5953-119">Select the **Web** tab, and then select **Use Local IIS Web Server**.</span></span>

8. <span data-ttu-id="f5953-120">Klicken Sie auf **virtuelles Verzeichnis erstellen** , und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="f5953-120">Click **Create Virtual Directory** and then click **OK**.</span></span>

9. <span data-ttu-id="f5953-121">Führen Sie an der Eingabeaufforderung mit Administratorrechten einen der folgenden Befehle aus (je nach Betriebssystem):</span><span class="sxs-lookup"><span data-stu-id="f5953-121">From the command prompt with administrator privileges, execute one of the following commands (depending on the operating system):</span></span>

    -   <span data-ttu-id="f5953-122">32-Bit-Systeme:</span><span class="sxs-lookup"><span data-stu-id="f5953-122">32-bit systems:</span></span>

        ```console
        "%windir%\Microsoft.NET\Framework\v3.0\Windows Communication Foundation\ServiceModelReg.exe" -i
        ```

    -   <span data-ttu-id="f5953-123">64-Bit-Systeme:</span><span class="sxs-lookup"><span data-stu-id="f5953-123">64-bit systems:</span></span>

        ```console
        "%windir%\Microsoft.NET\Framework64\v3.0\Windows Communication Foundation\ServiceModelReg.exe" -i
        ```

     <span data-ttu-id="f5953-124">Hierdurch wird sichergestellt, dass Windows Communication Foundation (WCF) auf dem Computer registriert wird.</span><span class="sxs-lookup"><span data-stu-id="f5953-124">This makes sure that Windows Communication Foundation (WCF) is registered on the computer.</span></span>

10. <span data-ttu-id="f5953-125">Führen Sie an der Eingabeaufforderung mit Administratorrechten einen der folgenden Befehle aus (je nach Betriebssystem):</span><span class="sxs-lookup"><span data-stu-id="f5953-125">From the command prompt with administrator privileges, execute one of the following commands (depending on the operating system):</span></span>

    -   <span data-ttu-id="f5953-126">32-Bit-Systeme:</span><span class="sxs-lookup"><span data-stu-id="f5953-126">32-bit systems:</span></span>

        ```console
        "%windir%\Microsoft.NET\Framework\v4.0.30319\aspnet_regiis.exe" -i -enable
        ```

    -   <span data-ttu-id="f5953-127">64-Bit-Systeme:</span><span class="sxs-lookup"><span data-stu-id="f5953-127">64-bit systems:</span></span>

        ```console
        "%windir%\Microsoft.NET\Framework64\v4.0.30319\aspnet_regiis.exe" -i -enable
        ```

     <span data-ttu-id="f5953-128">Dadurch wird sichergestellt, dass ISS ordnungsgemäß ausgeführt wird, nachdem WCF auf dem Computer installiert wurde.</span><span class="sxs-lookup"><span data-stu-id="f5953-128">This makes sure that IIS runs correctly after WCF has been installed on the computer.</span></span> <span data-ttu-id="f5953-129">Möglicherweise müssen Sie außerdem einen Neustart von IIS ausführen.</span><span class="sxs-lookup"><span data-stu-id="f5953-129">You might have to also restart IIS.</span></span>

11. <span data-ttu-id="f5953-130">Wenn die ASP.NET-Anwendung in IIS7 ausgeführt wird, müssen Sie außerdem die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="f5953-130">When the ASP.NET application runs on IIS7, you must also perform the following steps:</span></span>

    1. <span data-ttu-id="f5953-131">Öffnen Sie IIS-Manager, und navigieren Sie zur Anwendung PhotoService unter **Default Web Site**.</span><span class="sxs-lookup"><span data-stu-id="f5953-131">Open IIS Manager and navigate to the PhotoService application under **Default Web Site**.</span></span>

    2. <span data-ttu-id="f5953-132">In **Ansicht "Features"**, doppelklicken Sie auf **Authentifizierung**.</span><span class="sxs-lookup"><span data-stu-id="f5953-132">In **Features View**, double-click **Authentication**.</span></span>

    3. <span data-ttu-id="f5953-133">Auf der **Authentifizierung** Seite **anonyme Authentifizierung**.</span><span class="sxs-lookup"><span data-stu-id="f5953-133">On the **Authentication** page, select **Anonymous Authentication**.</span></span>

    4. <span data-ttu-id="f5953-134">In der **Aktionen** Bereich, klicken Sie auf **bearbeiten** um den Sicherheitsprinzipal festzulegen, unter dem anonyme Benutzer der Website hergestellt wird.</span><span class="sxs-lookup"><span data-stu-id="f5953-134">In the **Actions** pane, click **Edit** to set the security principal under which anonymous users will connect to the site.</span></span>

    5. <span data-ttu-id="f5953-135">In der **Anmeldeinformationen für anonyme Authentifizierung bearbeiten** wählen Sie im Dialogfeld **Identität des Anwendungspools**.</span><span class="sxs-lookup"><span data-stu-id="f5953-135">In the **Edit Anonymous Authentication Credentials** dialog box, select **Application pool identity**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="f5953-136">Wenn Sie das Netzwerkdienstkonto verwenden, gewähren Sie anonymen Benutzern alle Zugriffsrechte dieses Kontos für das interne Netzwerk.</span><span class="sxs-lookup"><span data-stu-id="f5953-136">When you use the Network Service account, you grant anonymous users all the internal network access associated with that account.</span></span>

12. <span data-ttu-id="f5953-137">Führen Sie mit SQL Server Management Studio, dem SQLCMD-Hilfsprogramm oder dem Transact-SQL-Editor in Visual Studio den folgenden Transact-SQL-Befehl für die Instanz von SQL Server aus, der die Northwind-Datenbank angefügt ist:</span><span class="sxs-lookup"><span data-stu-id="f5953-137">By using SQL Server Management Studio, the sqlcmd.exe utility, or the Transact-SQL Editor in Visual Studio, execute the following Transact-SQL command against the instance of SQL Server that has the Northwind database attached:</span></span>

    ```sql
    CREATE LOGIN [NT AUTHORITY\NETWORK SERVICE] FROM WINDOWS;
    GO
    ```

    <span data-ttu-id="f5953-138">Dadurch wird in der SQL Server-Instanz eine Anmeldung für das Windows-Konto erstellt, das verwendet wurde, um IIS auszuführen.</span><span class="sxs-lookup"><span data-stu-id="f5953-138">This creates a login in the SQL Server instance for the Windows account used to run IIS.</span></span> <span data-ttu-id="f5953-139">Dies ermöglicht es IIS, eine Verbindung mit der SQL Server-Instanz herzustellen.</span><span class="sxs-lookup"><span data-stu-id="f5953-139">This enables IIS to connect to the SQL Server instance.</span></span>

13. <span data-ttu-id="f5953-140">Führen Sie mit der angefügten Northwind-Datenbank, die folgenden Transact-SQL-Befehle aus:</span><span class="sxs-lookup"><span data-stu-id="f5953-140">With the Northwind database attached, execute the following Transact-SQL commands:</span></span>

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

    <span data-ttu-id="f5953-141">Hierdurch werden der neuen Anmeldung Rechte erteilt, die IIS den Lese- und Schreibzugriff für Daten der Northwind-Datenbank zu gewähren.</span><span class="sxs-lookup"><span data-stu-id="f5953-141">This grants rights to the new login, which enables IIS to read data from and write data to the Northwind database.</span></span>

## <a name="define-the-data-model"></a><span data-ttu-id="f5953-142">Definieren des Datenmodells</span><span class="sxs-lookup"><span data-stu-id="f5953-142">Define the data model</span></span>

1. <span data-ttu-id="f5953-143">In **Projektmappen-Explorer**mit der rechten Maustaste auf den Namen des ASP.NET-Projekts,, und klicken Sie dann auf **hinzufügen** > **neues Element**.</span><span class="sxs-lookup"><span data-stu-id="f5953-143">In **Solution Explorer**, right-click the name of the ASP.NET project, and then click **Add** > **New Item**.</span></span>

2. <span data-ttu-id="f5953-144">In der **neues Element hinzufügen** wählen Sie im Dialogfeld **ADO.NET Entity Data Model**.</span><span class="sxs-lookup"><span data-stu-id="f5953-144">In the **Add New Item** dialog box, select **ADO.NET Entity Data Model**.</span></span>

3. <span data-ttu-id="f5953-145">Geben Sie den Namen des Datenmodells `Northwind.edmx`.</span><span class="sxs-lookup"><span data-stu-id="f5953-145">For the name of the data model, type `Northwind.edmx`.</span></span>

4. <span data-ttu-id="f5953-146">Wählen Sie in der Assistent für Entity Data Model **aus Datenbank generieren**, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="f5953-146">In the Entity Data Model Wizard, select **Generate from Database**, and then click **Next**.</span></span>

5. <span data-ttu-id="f5953-147">Verbinden Sie das Datenmodell mit der Datenbank, indem er einen der folgenden Schritte aus, und klicken Sie dann auf **Weiter**:</span><span class="sxs-lookup"><span data-stu-id="f5953-147">Connect the data model to the database by doing one of the following steps, and then click **Next**:</span></span>

    -   <span data-ttu-id="f5953-148">Wenn Sie keine datenbankverbindung, die bereits konfiguriert haben, klicken Sie auf **neue Verbindung** , und erstellen Sie eine neue Verbindung.</span><span class="sxs-lookup"><span data-stu-id="f5953-148">If you do not have a database connection already configured, click **New Connection** and create a new connection.</span></span> <span data-ttu-id="f5953-149">Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen von Verbindungen mit SQL Server-Datenbanken](https://go.microsoft.com/fwlink/?LinkId=123631).</span><span class="sxs-lookup"><span data-stu-id="f5953-149">For more information, see [How to: Create Connections to SQL Server Databases](https://go.microsoft.com/fwlink/?LinkId=123631).</span></span> <span data-ttu-id="f5953-150">Dieser SQL Server-Instanz muss die Northwind-Beispieldatenbank angefügt sein.</span><span class="sxs-lookup"><span data-stu-id="f5953-150">This SQL Server instance must have the Northwind sample database attached.</span></span>

         <span data-ttu-id="f5953-151">\- oder –</span><span class="sxs-lookup"><span data-stu-id="f5953-151">\- or -</span></span>

    -   <span data-ttu-id="f5953-152">Wenn bereits eine Datenbankverbindung für die Northwind-Datenbank konfiguriert wurde, wählen Sie diese Verbindung in der Liste der Verbindungen aus.</span><span class="sxs-lookup"><span data-stu-id="f5953-152">If you have a database connection already configured to connect to the Northwind database, select that connection from the list of connections.</span></span>

6. <span data-ttu-id="f5953-153">Aktivieren Sie auf der letzten Seite des Assistenten die Kontrollkästchen für alle Tabellen in der Datenbank, und deaktivieren Sie die Kontrollkästchen für Sichten und gespeicherte Prozeduren.</span><span class="sxs-lookup"><span data-stu-id="f5953-153">On the final page of the wizard, select the check boxes for all tables in the database, and clear the check boxes for views and stored procedures.</span></span>

7. <span data-ttu-id="f5953-154">Klicken Sie auf **Fertig stellen** um den Assistenten zu schließen.</span><span class="sxs-lookup"><span data-stu-id="f5953-154">Click **Finish** to close the wizard.</span></span>

## <a name="create-the-data-service"></a><span data-ttu-id="f5953-155">Erstellen des Datendiensts</span><span class="sxs-lookup"><span data-stu-id="f5953-155">Create the data service</span></span>

1. <span data-ttu-id="f5953-156">In **Projektmappen-Explorer**mit der rechten Maustaste auf den Namen des ASP.NET-Projekts,, und klicken Sie dann auf **hinzufügen** > **neues Element**.</span><span class="sxs-lookup"><span data-stu-id="f5953-156">In **Solution Explorer**, right-click the name of your ASP.NET project, and then click **Add** > **New Item**.</span></span>

2. <span data-ttu-id="f5953-157">In der **neues Element hinzufügen** wählen Sie im Dialogfeld **WCF Data Service**.</span><span class="sxs-lookup"><span data-stu-id="f5953-157">In the **Add New Item** dialog box, select **WCF Data Service**.</span></span>

   ![WCF Data Service-Elementvorlage in Visual Studio 2015](media/wcf-data-service-item-template.png)

   > [!NOTE]
   > <span data-ttu-id="f5953-159">Die **WCF Data Service** Vorlage ist in Visual Studio 2015, aber nicht in Visual Studio 2017 verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f5953-159">The **WCF Data Service** template is available in Visual Studio 2015, but not in Visual Studio 2017.</span></span>

3. <span data-ttu-id="f5953-160">Geben Sie für den Namen des Diensts, `Northwind`.</span><span class="sxs-lookup"><span data-stu-id="f5953-160">For the name of the service, enter `Northwind`.</span></span>

     <span data-ttu-id="f5953-161">Visual Studio erstellt das XML-Markup und die Codedateien für den neuen Dienst.</span><span class="sxs-lookup"><span data-stu-id="f5953-161">Visual Studio creates the XML markup and code files for the new service.</span></span> <span data-ttu-id="f5953-162">In der Standardeinstellung wird das Fenster des Code-Editors geöffnet.</span><span class="sxs-lookup"><span data-stu-id="f5953-162">By default, the code-editor window opens.</span></span> <span data-ttu-id="f5953-163">In **Projektmappen-Explorer**, der Dienst hat den Namen, Northwind und der Erweiterung. svc.cs oder. svc.vb.</span><span class="sxs-lookup"><span data-stu-id="f5953-163">In **Solution Explorer**, the service has the name, Northwind, and the extension .svc.cs or .svc.vb.</span></span>

4. <span data-ttu-id="f5953-164">Ersetzen Sie im Code für den Datendienst in der Definition der Klasse, die den Datendienst definiert, den Kommentar `/* TODO: put your data source class name here */` durch den Typ des Entitätscontainers des Datenmodells, in diesem Fall `NorthwindEntities`.</span><span class="sxs-lookup"><span data-stu-id="f5953-164">In the code for the data service, replace the comment `/* TODO: put your data source class name here */` in the definition of the class that defines the data service with the type that is the entity container of the data model, which in this case is `NorthwindEntities`.</span></span> <span data-ttu-id="f5953-165">Die Klassendefinition sollte wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="f5953-165">The class definition should look this the following:</span></span>

     [!code-csharp[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria quickstart service/cs/northwind.svc.cs#servicedefinition)]
     [!code-vb[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart service/vb/northwind.svc.vb#servicedefinition)]

## <a name="see-also"></a><span data-ttu-id="f5953-166">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f5953-166">See also</span></span>

- [<span data-ttu-id="f5953-167">Verfügbarmachen der Daten als Dienst</span><span class="sxs-lookup"><span data-stu-id="f5953-167">Exposing Your Data as a Service</span></span>](../../../../docs/framework/data/wcf/exposing-your-data-as-a-service-wcf-data-services.md)
