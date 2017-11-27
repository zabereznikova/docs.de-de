---
title: Erstellen des Datendiensts
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 34d1d971-5e18-4c22-9bf6-d3612e27ea59
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 37d32d938f49d0767594e0f141d5a463ad5fc95f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="creating-the-data-service"></a><span data-ttu-id="8ef14-102">Erstellen des Datendiensts</span><span class="sxs-lookup"><span data-stu-id="8ef14-102">Creating the Data Service</span></span>
<span data-ttu-id="8ef14-103">In dieser Aufgabe erstellen Sie einen beispieldatendienst, der verwendet [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] verfügbar machen eine [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] Feed, die auf die Beispieldatenbank Northwind basiert.</span><span class="sxs-lookup"><span data-stu-id="8ef14-103">In this task, you will create a sample data service that uses [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] to expose an [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] feed that is based on the Northwind sample database.</span></span> <span data-ttu-id="8ef14-104">Die Aufgabe umfasst die folgenden grundlegenden Schritte:</span><span class="sxs-lookup"><span data-stu-id="8ef14-104">The task involves the following basic steps:</span></span>  
  
1.  <span data-ttu-id="8ef14-105">Erstellen Sie eine [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]-Webanwendung.</span><span class="sxs-lookup"><span data-stu-id="8ef14-105">Create an [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Web application.</span></span>  
  
2.  <span data-ttu-id="8ef14-106">Definieren Sie mit den [!INCLUDE[adonet_edm](../../../../includes/adonet-edm-md.md)]-Tools das Datenmodell.</span><span class="sxs-lookup"><span data-stu-id="8ef14-106">Define the data model by using the [!INCLUDE[adonet_edm](../../../../includes/adonet-edm-md.md)] tools.</span></span>  
  
3.  <span data-ttu-id="8ef14-107">Fügen Sie den Datendienst der Webanwendung hinzu.</span><span class="sxs-lookup"><span data-stu-id="8ef14-107">Add the data service to the Web application.</span></span>  
  
4.  <span data-ttu-id="8ef14-108">Aktivieren Sie den Zugriff auf den Datendienst.</span><span class="sxs-lookup"><span data-stu-id="8ef14-108">Enable access to the data service.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8ef14-109">Die beim Durchführen dieser Aufgabe erstellte [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]-Webanwendung wird auf dem von [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] bereitgestellten [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] Development Server ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="8ef14-109">The [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Web application that you create when you complete this task runs on the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Development Server provided by [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)].</span></span> [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]<span data-ttu-id="8ef14-110"> Development Server unterstützt nur Zugriff vom lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="8ef14-110"> Development Server only supports access from the local computer.</span></span> <span data-ttu-id="8ef14-111">Um außerdem das Testen und die Problembehebung des Datendiensts während der Entwicklung zu vereinfachen, sollte die Anwendung, die den Datendienst hostet, möglicherweise mithilfe von Internetinformationsdienste (IIS) ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="8ef14-111">To also make it easier to test and troubleshoot the data service during development, consider running the application that hosts the data service by using Internet Information Services (IIS).</span></span> <span data-ttu-id="8ef14-112">Weitere Informationen finden Sie unter [How to: Develop a WCF Data Service Running on IIS](../../../../docs/framework/data/wcf/how-to-develop-a-wcf-data-service-running-on-iis.md).</span><span class="sxs-lookup"><span data-stu-id="8ef14-112">For more information, see [How to: Develop a WCF Data Service Running on IIS](../../../../docs/framework/data/wcf/how-to-develop-a-wcf-data-service-running-on-iis.md).</span></span>  
  
### <a name="to-create-the-aspnet-web-application"></a><span data-ttu-id="8ef14-113">So erstellen Sie die ASP.NET-Webanwendung</span><span class="sxs-lookup"><span data-stu-id="8ef14-113">To create the ASP.NET Web application</span></span>  
  
1.  <span data-ttu-id="8ef14-114">In [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)]auf die **Datei** klicken Sie im Menü **neu**, und wählen Sie dann **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="8ef14-114">In [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)], on the **File** menu, select **New**, and then select **Project**.</span></span>  
  
2.  <span data-ttu-id="8ef14-115">In der **neues Projekt** im Dialogfeld unter entweder [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] oder [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] wählen Sie die **Web** Vorlage, und wählen Sie dann **ASP.NET-Webanwendung**.</span><span class="sxs-lookup"><span data-stu-id="8ef14-115">In the **New Project** dialog box, under either [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] or [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] select the **Web** template, and then select **ASP.NET Web Application**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8ef14-116">Wenn Sie [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] Web Developer verwenden, müssen Sie anstelle einer neuen Webanwendung eine neue Website erstellen.</span><span class="sxs-lookup"><span data-stu-id="8ef14-116">If you use [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] Web Developer, you must create a new Web site instead of a new Web application.</span></span>  
  
3.  <span data-ttu-id="8ef14-117">Typ `NorthwindService` als den Namen des Projekts.</span><span class="sxs-lookup"><span data-stu-id="8ef14-117">Type `NorthwindService` as the name of the project.</span></span>  
  
4.  <span data-ttu-id="8ef14-118">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="8ef14-118">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="8ef14-119">(Optional) Geben Sie eine bestimmte Portnummer für die Webanwendung an.</span><span class="sxs-lookup"><span data-stu-id="8ef14-119">(Optional) Specify a specific port number for your Web application.</span></span> <span data-ttu-id="8ef14-120">Hinweis: Im weiteren Verlauf des Schnellstarts wird die Portnummer `12345` verwendet.</span><span class="sxs-lookup"><span data-stu-id="8ef14-120">Note: the port number `12345` is used in the rest of the quickstart.</span></span>  
  
    1.  <span data-ttu-id="8ef14-121">In **Projektmappen-Explorer**, mit der rechten Maustaste in des Namens der [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Projekt, die Sie gerade erstellt haben, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="8ef14-121">In **Solution Explorer**, right-click the name of the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] project that you just created, and then click **Properties**.</span></span>  
  
    2.  <span data-ttu-id="8ef14-122">Wählen Sie die **Web** Registerkarte, und legen Sie den Wert von der **bestimmten Port** Textfeld `12345`.</span><span class="sxs-lookup"><span data-stu-id="8ef14-122">Select the **Web** tab, and set the value of the **Specific port** text box to `12345`.</span></span>  
  
### <a name="to-define-the-data-model"></a><span data-ttu-id="8ef14-123">So definieren Sie das Datenmodell</span><span class="sxs-lookup"><span data-stu-id="8ef14-123">To define the data model</span></span>  
  
1.  <span data-ttu-id="8ef14-124">In **Projektmappen-Explorer**, mit der rechten Maustaste in des Namens der [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Projekt, und klicken Sie dann auf **neues Element hinzufügen.**</span><span class="sxs-lookup"><span data-stu-id="8ef14-124">In **Solution Explorer**, right-click the name of the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] project, and then click **Add New Item.**</span></span>  
  
2.  <span data-ttu-id="8ef14-125">In der **neues Element hinzufügen** (Dialogfeld), klicken Sie auf die **Daten** Vorlage, und wählen Sie dann **ADO.NET Entity Data Model**.</span><span class="sxs-lookup"><span data-stu-id="8ef14-125">In the **Add New Item** dialog box, click the **Data** template and then select **ADO.NET Entity Data Model**.</span></span>  
  
3.  <span data-ttu-id="8ef14-126">Geben Sie für den Namen des Datenmodells, `Northwind.edmx`.</span><span class="sxs-lookup"><span data-stu-id="8ef14-126">For the name of the data model, type `Northwind.edmx`.</span></span>  
  
4.  <span data-ttu-id="8ef14-127">In der [!INCLUDE[adonet_edm](../../../../includes/adonet-edm-md.md)] -Assistenten die Option **aus Datenbank generieren**, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="8ef14-127">In the [!INCLUDE[adonet_edm](../../../../includes/adonet-edm-md.md)] Wizard, select **Generate from Database**, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="8ef14-128">Das Datenmodell mit der Datenbank zu verbinden, indem Sie einen der folgenden Schritte aus, und klicken Sie dann auf **Weiter**:</span><span class="sxs-lookup"><span data-stu-id="8ef14-128">Connect the data model to the database by doing one of the following steps, and then click **Next**:</span></span>  
  
    -   <span data-ttu-id="8ef14-129">Wenn Sie keine datenbankverbindung, die bereits konfiguriert haben, klicken Sie auf **neue Verbindung** und erstellen Sie eine neue Verbindung.</span><span class="sxs-lookup"><span data-stu-id="8ef14-129">If you do not have a database connection already configured, click **New Connection** and create a new connection.</span></span> <span data-ttu-id="8ef14-130">Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen von Verbindungen mit SQL Server-Datenbanken](http://go.microsoft.com/fwlink/?LinkId=123631).</span><span class="sxs-lookup"><span data-stu-id="8ef14-130">For more information, see [How to: Create Connections to SQL Server Databases](http://go.microsoft.com/fwlink/?LinkId=123631).</span></span> <span data-ttu-id="8ef14-131">Dieser [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)]-Instanz muss die Northwind-Beispieldatenbank angefügt worden sein.</span><span class="sxs-lookup"><span data-stu-id="8ef14-131">This [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] instance must have the Northwind sample database attached.</span></span>  
  
         <span data-ttu-id="8ef14-132">\- oder –</span><span class="sxs-lookup"><span data-stu-id="8ef14-132">\- or -</span></span>  
  
    -   <span data-ttu-id="8ef14-133">Wenn bereits eine Datenbankverbindung für die Northwind-Datenbank konfiguriert wurde, wählen Sie diese Verbindung in der Liste der Verbindungen aus.</span><span class="sxs-lookup"><span data-stu-id="8ef14-133">If you have a database connection already configured to connect to the Northwind database, select that connection from the list of connections.</span></span>  
  
6.  <span data-ttu-id="8ef14-134">Aktivieren Sie auf der letzten Seite des Assistenten die Kontrollkästchen für alle Tabellen in der Datenbank, und deaktivieren Sie die Kontrollkästchen für Sichten und gespeicherte Prozeduren.</span><span class="sxs-lookup"><span data-stu-id="8ef14-134">On the final page of the wizard, select the check boxes for all tables in the database, and clear the check boxes for views and stored procedures.</span></span>  
  
7.  <span data-ttu-id="8ef14-135">Klicken Sie auf **Fertig stellen** um den Assistenten zu schließen.</span><span class="sxs-lookup"><span data-stu-id="8ef14-135">Click **Finish** to close the wizard.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8ef14-136">Das erstellte Datenmodell macht Fremdschlüsseleigenschaften von Entitätstypen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="8ef14-136">This generated data model exposes foreign key properties on entity types.</span></span> <span data-ttu-id="8ef14-137">Mit [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] 2008 erstellte Datenmodelle enthalten diese Fremdschlüsseleigenschaften nicht.</span><span class="sxs-lookup"><span data-stu-id="8ef14-137">Data models created using [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] 2008 do not include these foreign key properties.</span></span> <span data-ttu-id="8ef14-138">Aus diesem Grund müssen Sie die Clientdatendienstklassen jeglicher Clientanwendungen aktualisieren, die für den Zugriff auf den mit [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] 2008 erstellten Northwind-Datendienst erstellt wurden, bevor Sie auf diese Version des Northwind-Datendiensts zugreifen.</span><span class="sxs-lookup"><span data-stu-id="8ef14-138">Because of this, you must update the client data service classes of any client applications that were created to access the Northwind data service that was created using [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] 2008 before attempting to access this version of the Northwind data service.</span></span>  
  
### <a name="to-create-the-data-service"></a><span data-ttu-id="8ef14-139">So erstellen Sie den Datendienst</span><span class="sxs-lookup"><span data-stu-id="8ef14-139">To create the data service</span></span>  
  
1.  <span data-ttu-id="8ef14-140">In **Projektmappen-Explorer**, mit der rechten Maustaste in des Namens Ihrer [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Projekt, und klicken Sie dann auf **neues Element hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="8ef14-140">In **Solution Explorer**, right-click the name of your [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] project, and then click **Add New Item**.</span></span>  
  
2.  <span data-ttu-id="8ef14-141">In der **neues Element hinzufügen** wählen Sie im Dialogfeld **WCF Data Service**.</span><span class="sxs-lookup"><span data-stu-id="8ef14-141">In the **Add New Item** dialog box, select **WCF Data Service**.</span></span>  
  
3.  <span data-ttu-id="8ef14-142">Geben Sie den Namen des Diensts zu `Northwind`.</span><span class="sxs-lookup"><span data-stu-id="8ef14-142">For the name of the service, type `Northwind`.</span></span>  
  
     [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)]<span data-ttu-id="8ef14-143">Visual Studio erstellt das XML-Markup und die Codedateien für den neuen Dienst.</span><span class="sxs-lookup"><span data-stu-id="8ef14-143">Visual Studio creates the XML markup and code files for the new service.</span></span> <span data-ttu-id="8ef14-144">In der Standardeinstellung wird das Fenster des Code-Editors geöffnet.</span><span class="sxs-lookup"><span data-stu-id="8ef14-144">By default, the code-editor window opens.</span></span> <span data-ttu-id="8ef14-145">In **Projektmappen-Explorer**, der Dienst müssen die Namen "Northwind", mit der Erweiterung. svc.cs oder. svc.vb.</span><span class="sxs-lookup"><span data-stu-id="8ef14-145">In **Solution Explorer**, the service will have the name, Northwind, with the extension .svc.cs or .svc.vb.</span></span>  
  
4.  <span data-ttu-id="8ef14-146">Ersetzen Sie im Code für den Datendienst in der Definition der Klasse, die den Datendienst definiert, den Kommentar `/* TODO: put your data source class name here */` durch den Typ des Entitätscontainers des Datenmodells, in diesem Fall `NorthwindEntities`.</span><span class="sxs-lookup"><span data-stu-id="8ef14-146">In the code for the data service, replace the comment `/* TODO: put your data source class name here */` in the definition of the class that defines the data service with the type that is the entity container of the data model, which in this case is `NorthwindEntities`.</span></span> <span data-ttu-id="8ef14-147">Die Klassendefinition sollte wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="8ef14-147">The class definition should look this the following:</span></span>  
  
     [!code-csharp[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria quickstart service/cs/northwind.svc.cs#servicedefinition)]
     [!code-vb[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart service/vb/northwind.svc.vb#servicedefinition)]  
  
### <a name="to-enable-access-to-data-service-resources"></a><span data-ttu-id="8ef14-148">So aktivieren Sie den Zugriff auf Datendienstressourcen</span><span class="sxs-lookup"><span data-stu-id="8ef14-148">To enable access to data service resources</span></span>  
  
1.  <span data-ttu-id="8ef14-149">Ersetzen Sie im Code für den Datendienst den Platzhaltercode in der `InitializeService`-Funktion durch Folgendes:</span><span class="sxs-lookup"><span data-stu-id="8ef14-149">In the code for the data service, replace the placeholder code in the `InitializeService` function with the following:</span></span>  
  
     [!code-csharp[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria quickstart service/cs/northwind.svc.cs#allreadconfig)]
     [!code-vb[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart service/vb/northwind.svc.vb#allreadconfig)]  
  
     <span data-ttu-id="8ef14-150">So können autorisierte Clients, Lese- und Schreibzugriff auf Ressourcen für die angegebenen Entitätenmengen erhalten.</span><span class="sxs-lookup"><span data-stu-id="8ef14-150">This enables authorized clients to have read and write access to resources for the specified entity sets.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8ef14-151">Jeder Client, der auf die [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]-Anwendung zugreifen kann, kann auch auf die vom Datendienst verfügbar gemachten Ressourcen zugreifen.</span><span class="sxs-lookup"><span data-stu-id="8ef14-151">Any client that can access the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] application can also access the resources exposed by the data service.</span></span> <span data-ttu-id="8ef14-152">Sie sollten in einem Produktionsdatendienst auch die Anwendung selbst sichern, um nicht autorisierten Zugriff auf Ressourcen zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="8ef14-152">In a production data service, to prevent unauthorized access to resources you should also secure the application itself.</span></span> <span data-ttu-id="8ef14-153">Weitere Informationen finden Sie unter [Securing WCF Data Services](../../../../docs/framework/data/wcf/securing-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="8ef14-153">For more information, see [Securing WCF Data Services](../../../../docs/framework/data/wcf/securing-wcf-data-services.md).</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="8ef14-154">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="8ef14-154">Next Steps</span></span>  
 <span data-ttu-id="8ef14-155">Einen neuer Datendienst, die verfügbar gemacht wurde erfolgreich erstellt ein [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] Feed, die auf die Beispieldatenbank Northwind, und Sie basiert aktiviert haben Zugriff auf den Feed für Clients, die über Berechtigungen verfügen, auf die [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Webanwendung.</span><span class="sxs-lookup"><span data-stu-id="8ef14-155">You have successfully created a new data service that exposes an [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed that is based on the Northwind sample database, and you have enabled access to the feed for clients that have permissions on the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Web application.</span></span> <span data-ttu-id="8ef14-156">Als Nächstes starten Sie den Datendienst aus [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] und greifen Sie auf die [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed von einer HTTP-GET-Anforderungen über einen Webbrowser senden:</span><span class="sxs-lookup"><span data-stu-id="8ef14-156">Next, you will start the data service from [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] and you will access the [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed by submitting HTTP GET requests through a Web browser:</span></span>  
  
 [<span data-ttu-id="8ef14-157">Zugriff auf den Dienst über einen Webbrowser</span><span class="sxs-lookup"><span data-stu-id="8ef14-157">Accessing the Service from a Web Browser</span></span>](../../../../docs/framework/data/wcf/accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md)  
  
## <a name="see-also"></a><span data-ttu-id="8ef14-158">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8ef14-158">See Also</span></span>  
 [<span data-ttu-id="8ef14-159">ADO.NET Entity Data Model Tools (ADO.NET Entity Data Model-Tools)</span><span class="sxs-lookup"><span data-stu-id="8ef14-159">ADO.NET Entity Data Model  Tools</span></span>](http://msdn.microsoft.com/en-us/91076853-0881-421b-837a-f582f36be527)
