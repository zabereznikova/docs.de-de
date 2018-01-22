---
title: 'Gewusst wie: Erstellen eines Datendiensts mit einer ADO.NET-Entity Framework-Datenquelle (WCF Data Services)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF Data Services, providers
- WCF Data Services, Entity Framework
ms.assetid: 6d11fec8-0108-42f5-8719-2a7866d04428
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e90b11800685707460171e5e2d250ef757979c44
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-create-a-data-service-using-an-adonet-entity-framework-data-source-wcf-data-services"></a><span data-ttu-id="c7951-102">Gewusst wie: Erstellen eines Datendiensts mit einer ADO.NET-Entity Framework-Datenquelle (WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="c7951-102">How to: Create a Data Service Using an ADO.NET Entity Framework Data Source (WCF Data Services)</span></span>
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]<span data-ttu-id="c7951-103"> macht Entitätsdaten als Datendienst verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c7951-103"> exposes entity data as a data service.</span></span> <span data-ttu-id="c7951-104">Diese Entitätsdaten erfolgt durch die [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] Wenn die Datenquelle eine relationale Datenbank ist.</span><span class="sxs-lookup"><span data-stu-id="c7951-104">This entity data is provided by the [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)][!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] when the data source is a relational database.</span></span> <span data-ttu-id="c7951-105">In diesem Thema wird gezeigt, wie ein [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)]-basiertes Datenmodell in einer [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)]-Webanwendung erstellt wird, die auf einer vorhandenen Datenbank basiert, und wie mit diesem Datenmodell ein neuer Datendienst erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="c7951-105">This topic shows you how to create an [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)]-based data model in a [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] Web application that is based on an existing database and use this data model to create a new data service.</span></span>  
  
 <span data-ttu-id="c7951-106">Das [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] stellt auch ein Befehlszeilentool bereit, das ein [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)]-Modell außerhalb eines [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)]-Projekts generieren kann.</span><span class="sxs-lookup"><span data-stu-id="c7951-106">The [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] also provides a command line tool that can generate an [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] model outside of a [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] project.</span></span> <span data-ttu-id="c7951-107">Weitere Informationen finden Sie unter [Vorgehensweise: verwenden EdmGen.exe generiert die Modell- und Zuordnen von Dateien](../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span><span class="sxs-lookup"><span data-stu-id="c7951-107">For more information, see [How to: Use EdmGen.exe to Generate the Model and Mapping Files](../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span></span>  
  
### <a name="to-add-an-entity-framework-model-that-is-based-on-an-existing-database-to-an-existing-web-application"></a><span data-ttu-id="c7951-108">So fügen Sie einer vorhandenen Webanwendung ein Entity Framework-Modell hinzu, das auf einer vorhandenen Datenbank basiert</span><span class="sxs-lookup"><span data-stu-id="c7951-108">To add an Entity Framework model that is based on an existing database to an existing Web application</span></span>  
  
1.  <span data-ttu-id="c7951-109">Auf der **Projekt** Menü klicken Sie auf **neues Element hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="c7951-109">On the **Project** menu, click **Add new item**.</span></span>  
  
2.  <span data-ttu-id="c7951-110">In der **Vorlagen** Bereich, klicken Sie auf die **Daten** Kategorie, und wählen Sie dann **ADO.NET Entity Data Model**.</span><span class="sxs-lookup"><span data-stu-id="c7951-110">In the **Templates** pane, click the **Data** category, and then select **ADO.NET Entity Data Model**.</span></span>  
  
3.  <span data-ttu-id="c7951-111">Geben Sie den Modellnamen, und klicken Sie dann auf **hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="c7951-111">Type the model name and then click **Add**.</span></span>  
  
     <span data-ttu-id="c7951-112">Die erste Seite des Assistenten für [!INCLUDE[adonet_edm](../../../../includes/adonet-edm-md.md)] wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c7951-112">The first page of the [!INCLUDE[adonet_edm](../../../../includes/adonet-edm-md.md)] Wizard is displayed.</span></span>  
  
4.  <span data-ttu-id="c7951-113">In der **Modellinhalte** wählen Sie im Dialogfeld **aus Datenbank generieren**.</span><span class="sxs-lookup"><span data-stu-id="c7951-113">In the **Choose Model Contents** dialog box, select **Generate from database**.</span></span> <span data-ttu-id="c7951-114">Klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="c7951-114">Then click **Next**.</span></span>  
  
5.  <span data-ttu-id="c7951-115">Klicken Sie auf die **neue Verbindung** Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="c7951-115">Click the **New Connection** button.</span></span>  
  
6.  <span data-ttu-id="c7951-116">In der **Verbindungseigenschaften** (Dialogfeld), geben Sie Ihren Server ein, wählen Sie die Authentifizierungsmethode aus, geben Sie den Datenbanknamen ein und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="c7951-116">In the **Connection Properties** dialog box, type your server name, select the authentication method, type the database name, and then click **OK**.</span></span>  
  
     <span data-ttu-id="c7951-117">Die **wählen Sie Ihre Datenverbindung**im Dialogfeld mit den Verbindungseinstellungen des Datenbank aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="c7951-117">The **Choose Your Data Connection**s dialog box is updated with your database connection settings.</span></span>  
  
7.  <span data-ttu-id="c7951-118">Sicherstellen, dass die **Entität Verbindungseinstellungen in app.config-Datei als speichern:** aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="c7951-118">Ensure that the **Save entity connection settings in App.Config as:** checkbox is checked.</span></span> <span data-ttu-id="c7951-119">Klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="c7951-119">Then click **Next**.</span></span>  
  
8.  <span data-ttu-id="c7951-120">In der **Datenbankobjekte auswählen** (Dialogfeld), wählen Sie alle Datenbankobjekte aus, dass Sie im Datendienst verfügbar machen möchten.</span><span class="sxs-lookup"><span data-stu-id="c7951-120">In the **Choose Your Database Objects** dialog box, select all of database objects that you plan to expose in the data service.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c7951-121">Im Datenmodell enthaltene Objekte werden nicht automatisch vom Datendienst verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="c7951-121">Objects included in the data model are not automatically exposed by the data service.</span></span> <span data-ttu-id="c7951-122">Sie müssen explizit vom Dienst selbst verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="c7951-122">They must be explicitly exposed by the service itself.</span></span> <span data-ttu-id="c7951-123">Weitere Informationen finden Sie unter [Konfigurieren des Datendiensts](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="c7951-123">For more information, see [Configuring the Data Service](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md).</span></span>  
  
9. <span data-ttu-id="c7951-124">Klicken Sie auf **Fertig stellen** um den Assistenten abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="c7951-124">Click **Finish** to complete the wizard.</span></span>  
  
     <span data-ttu-id="c7951-125">Dadurch wird ein Standarddatenmodell auf Grundlage der bestimmten Datenbank erstellt.</span><span class="sxs-lookup"><span data-stu-id="c7951-125">This creates a default data model based on the specific database.</span></span> <span data-ttu-id="c7951-126">Das [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] ermöglicht das Anpassen des Datenmodells.</span><span class="sxs-lookup"><span data-stu-id="c7951-126">The [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] enables to customize the data model.</span></span> <span data-ttu-id="c7951-127">Weitere Informationen finden Sie unter [MSBuild-Aufgaben](http://msdn.microsoft.com/library/7166f1f1-4de8-4bd4-86b5-5e20a2ebaccb).</span><span class="sxs-lookup"><span data-stu-id="c7951-127">For more information, see [Tasks](http://msdn.microsoft.com/library/7166f1f1-4de8-4bd4-86b5-5e20a2ebaccb).</span></span>  
  
### <a name="to-create-the-data-service-by-using-the-new-data-model"></a><span data-ttu-id="c7951-128">So erstellen Sie den Datendienst mit dem neuen Datenmodell</span><span class="sxs-lookup"><span data-stu-id="c7951-128">To create the data service by using the new data model</span></span>  
  
1.  <span data-ttu-id="c7951-129">Öffnen Sie in [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] die EDMX-Datei, die das Datenmodell darstellt.</span><span class="sxs-lookup"><span data-stu-id="c7951-129">In [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)], open the .edmx file that represents the data model.</span></span>  
  
2.  <span data-ttu-id="c7951-130">In der **Modellbrowser**mit der rechten Maustaste auf das Modell, klicken Sie auf **Eigenschaften**, und notieren Sie den Namen des Entitätscontainers handelt.</span><span class="sxs-lookup"><span data-stu-id="c7951-130">In the **Model Browser**, right-click the model, click **Properties**, and then note the name of the entity container.</span></span>  
  
3.  <span data-ttu-id="c7951-131">In **Projektmappen-Explorer**, mit der rechten Maustaste in des Namens Ihrer [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Projekt, und klicken Sie dann auf **neues Element hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="c7951-131">In **Solution Explorer**, right-click the name of your [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] project, and then click **Add New Item**.</span></span>  
  
4.  <span data-ttu-id="c7951-132">In der **neues Element hinzufügen** wählen Sie im Dialogfeld **WCF Data Service**.</span><span class="sxs-lookup"><span data-stu-id="c7951-132">In the **Add New Item** dialog box, select **WCF Data Service**.</span></span>  
  
5.  <span data-ttu-id="c7951-133">Geben Sie einen Namen für den Dienst, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="c7951-133">Supply a name for the service, and then click **OK**.</span></span>  
  
     [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)]<span data-ttu-id="c7951-134"> erstellt das XML-Markup und die Codedateien für den neuen Dienst.</span><span class="sxs-lookup"><span data-stu-id="c7951-134"> creates the XML markup and code files for the new service.</span></span> <span data-ttu-id="c7951-135">In der Standardeinstellung wird das Fenster des Code-Editors geöffnet.</span><span class="sxs-lookup"><span data-stu-id="c7951-135">By default, the code-editor window opens.</span></span>  
  
6.  <span data-ttu-id="c7951-136">Ersetzen Sie im Code für den Datendienst den Kommentar `/* TODO: put your data source class name here */` in der Definition der Klasse, die den Datendienst definiert, durch den Typ, der von der <xref:System.Data.Objects.ObjectContext>-Klasse erbt und der Entitätscontainer des Datenmodells ist, der in Schritt 2 notiert wurde.</span><span class="sxs-lookup"><span data-stu-id="c7951-136">In the code for the data service, replace the comment `/* TODO: put your data source class name here */` in the definition of the class that defines the data service with the type that inherits from the <xref:System.Data.Objects.ObjectContext> class and that is the entity container of the data model, which was noted in step 2.</span></span>  
  
7.  <span data-ttu-id="c7951-137">Ermöglichen Sie im Code für den Datendienst berechtigten Clients, auf die Entitätenmengen zuzugreifen, die der Datendienst verfügbar macht.</span><span class="sxs-lookup"><span data-stu-id="c7951-137">In the code for the data service, enable authorized clients to access the entity sets that the data service exposes.</span></span> <span data-ttu-id="c7951-138">Weitere Informationen finden Sie unter [Erstellen des Datendiensts](../../../../docs/framework/data/wcf/creating-the-data-service.md).</span><span class="sxs-lookup"><span data-stu-id="c7951-138">For more information, see [Creating the Data Service](../../../../docs/framework/data/wcf/creating-the-data-service.md).</span></span>  
  
8.  <span data-ttu-id="c7951-139">Um den Datendienst Northwind.svc mithilfe eines Webbrowsers zu testen, führen Sie die Anweisungen im Thema [Zugriff auf den Dienst über einen Webbrowser](../../../../docs/framework/data/wcf/accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md).</span><span class="sxs-lookup"><span data-stu-id="c7951-139">To test the Northwind.svc data service by using a Web browser, follow the instructions in the topic [Accessing the Service from a Web Browser](../../../../docs/framework/data/wcf/accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7951-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c7951-140">See Also</span></span>  
 [<span data-ttu-id="c7951-141">Defining WCF Data Services</span><span class="sxs-lookup"><span data-stu-id="c7951-141">Defining WCF Data Services</span></span>](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)  
 [<span data-ttu-id="c7951-142">Datendienstanbieter</span><span class="sxs-lookup"><span data-stu-id="c7951-142">Data Services Providers</span></span>](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md)  
 [<span data-ttu-id="c7951-143">: Erstellen eines Datendiensts mit dem Reflektionsanbieter</span><span class="sxs-lookup"><span data-stu-id="c7951-143">How to: Create a Data Service Using the Reflection Provider</span></span>](../../../../docs/framework/data/wcf/create-a-data-service-using-rp-wcf-data-services.md)  
 [<span data-ttu-id="c7951-144">Vorgehensweise: Erstellen eines Datendiensts mit einer LINQ to SQL-Datenquelle</span><span class="sxs-lookup"><span data-stu-id="c7951-144">How to: Create a Data Service Using a LINQ to SQL Data Source</span></span>](../../../../docs/framework/data/wcf/create-a-data-service-using-linq-to-sql-wcf.md)
