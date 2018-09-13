---
title: 'Gewusst wie: Erstellen eines Datendiensts mit einer ADO.NET-Entity Framework-Datenquelle (WCF Data Services)'
ms.date: 08/24/2018
helpviewer_keywords:
- WCF Data Services, providers
- WCF Data Services, Entity Framework
ms.assetid: 6d11fec8-0108-42f5-8719-2a7866d04428
ms.openlocfilehash: 72439596ec6dc6c42024ed38116ba0026922154c
ms.sourcegitcommit: ba5c189bf44d44204a3e8838e59ec378a62d82f3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2018
ms.locfileid: "44705783"
---
# <a name="how-to-create-a-data-service-using-an-adonet-entity-framework-data-source-wcf-data-services"></a><span data-ttu-id="d2176-102">Gewusst wie: Erstellen eines Datendiensts mit einer ADO.NET-Entity Framework-Datenquelle (WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="d2176-102">How to: Create a Data Service Using an ADO.NET Entity Framework Data Source (WCF Data Services)</span></span>

<span data-ttu-id="d2176-103">WCF Data Services macht Entitätsdaten als Datendienst verfügbar.</span><span class="sxs-lookup"><span data-stu-id="d2176-103">WCF Data Services exposes entity data as a data service.</span></span> <span data-ttu-id="d2176-104">Diese Entitätsdaten erfolgt über die [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] Wenn die Datenquelle eine relationale Datenbank ist.</span><span class="sxs-lookup"><span data-stu-id="d2176-104">This entity data is provided by the [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)][!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] when the data source is a relational database.</span></span> <span data-ttu-id="d2176-105">In diesem Thema erfahren Sie, wie zum Erstellen einer [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)]--basiertes Datenmodell in einer Visual Studio Web-Anwendung, die auf einer vorhandenen Datenbank basiert dieses Datenmodell zu verwenden, um einen neuen Datendienst zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d2176-105">This topic shows you how to create an [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)]-based data model in a Visual Studio Web application that is based on an existing database and use this data model to create a new data service.</span></span>

<span data-ttu-id="d2176-106">Die [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] bietet auch ein Befehlszeilentool, das Generieren einer [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] Modell außerhalb eines Visual Studio-Projekts.</span><span class="sxs-lookup"><span data-stu-id="d2176-106">The [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] also provides a command line tool that can generate an [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] model outside of a Visual Studio project.</span></span> <span data-ttu-id="d2176-107">Weitere Informationen finden Sie unter [wie: Generieren Sie das Modell und die Mapping-Dateien mithilfe von EdmGen.exe](../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span><span class="sxs-lookup"><span data-stu-id="d2176-107">For more information, see [How to: Use EdmGen.exe to Generate the Model and Mapping Files](../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span></span>

## <a name="to-add-an-entity-framework-model-that-is-based-on-an-existing-database-to-an-existing-web-application"></a><span data-ttu-id="d2176-108">So fügen Sie einer vorhandenen Webanwendung ein Entity Framework-Modell hinzu, das auf einer vorhandenen Datenbank basiert</span><span class="sxs-lookup"><span data-stu-id="d2176-108">To add an Entity Framework model that is based on an existing database to an existing Web application</span></span>

1. <span data-ttu-id="d2176-109">Auf der **Projekt** Menü klicken Sie auf **hinzufügen** > **neues Element**.</span><span class="sxs-lookup"><span data-stu-id="d2176-109">On the **Project** menu, click **Add** > **New Item**.</span></span>

2. <span data-ttu-id="d2176-110">In der **Vorlagen** Bereich, klicken Sie auf die **Daten** Kategorie, und wählen Sie dann **ADO.NET Entity Data Model**.</span><span class="sxs-lookup"><span data-stu-id="d2176-110">In the **Templates** pane, click the **Data** category, and then select **ADO.NET Entity Data Model**.</span></span>

3. <span data-ttu-id="d2176-111">Geben Sie den Modellnamen ein, und klicken Sie dann auf **hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="d2176-111">Enter the model name and then click **Add**.</span></span>

     <span data-ttu-id="d2176-112">Die erste Seite des Assistenten für [!INCLUDE[adonet_edm](../../../../includes/adonet-edm-md.md)] wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d2176-112">The first page of the [!INCLUDE[adonet_edm](../../../../includes/adonet-edm-md.md)] Wizard is displayed.</span></span>

4. <span data-ttu-id="d2176-113">In der **auswählen des Modellinhalts** wählen Sie im Dialogfeld **aus Datenbank generieren**.</span><span class="sxs-lookup"><span data-stu-id="d2176-113">In the **Choose Model Contents** dialog box, select **Generate from database**.</span></span> <span data-ttu-id="d2176-114">Klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="d2176-114">Then click **Next**.</span></span>

5. <span data-ttu-id="d2176-115">Klicken Sie auf die **neue Verbindung** Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="d2176-115">Click the **New Connection** button.</span></span>

6. <span data-ttu-id="d2176-116">In der **Verbindungseigenschaften** im Dialogfeld Geben Sie Ihren Server ein, wählen Sie die Authentifizierungsmethode aus, geben Sie den Datenbanknamen, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="d2176-116">In the **Connection Properties** dialog box, type your server name, select the authentication method, type the database name, and then click **OK**.</span></span>

     <span data-ttu-id="d2176-117">Die **wählen Sie Ihre Datenverbindung**Dialogfeld wird mit der Datenbank-Verbindungseinstellungen aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="d2176-117">The **Choose Your Data Connection**s dialog box is updated with your database connection settings.</span></span>

7. <span data-ttu-id="d2176-118">Sicherstellen, dass die **Entitätsverbindungseinstellungen in App.Config speichern als:** aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="d2176-118">Ensure that the **Save entity connection settings in App.Config as:** checkbox is checked.</span></span> <span data-ttu-id="d2176-119">Klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="d2176-119">Then click **Next**.</span></span>

8. <span data-ttu-id="d2176-120">In der **Datenbankobjekte auswählen** im Dialogfeld auf alle Datenbankobjekte aus, dass im Datendienst verfügbar gemacht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="d2176-120">In the **Choose Your Database Objects** dialog box, select all of database objects that you plan to expose in the data service.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d2176-121">Im Datenmodell enthaltene Objekte werden nicht automatisch vom Datendienst verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="d2176-121">Objects included in the data model are not automatically exposed by the data service.</span></span> <span data-ttu-id="d2176-122">Sie müssen explizit vom Dienst selbst verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="d2176-122">They must be explicitly exposed by the service itself.</span></span> <span data-ttu-id="d2176-123">Weitere Informationen finden Sie unter [Konfigurieren des Datendiensts](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="d2176-123">For more information, see [Configuring the Data Service](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md).</span></span>

9. <span data-ttu-id="d2176-124">Klicken Sie auf **Fertig stellen** um den Assistenten abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="d2176-124">Click **Finish** to complete the wizard.</span></span>

     <span data-ttu-id="d2176-125">Dadurch wird ein Standarddatenmodell auf Grundlage der bestimmten Datenbank erstellt.</span><span class="sxs-lookup"><span data-stu-id="d2176-125">This creates a default data model based on the specific database.</span></span> <span data-ttu-id="d2176-126">Das [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] ermöglicht das Anpassen des Datenmodells.</span><span class="sxs-lookup"><span data-stu-id="d2176-126">The [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] enables to customize the data model.</span></span> <span data-ttu-id="d2176-127">Weitere Informationen finden Sie unter [MSBuild-Aufgaben](https://msdn.microsoft.com/library/7166f1f1-4de8-4bd4-86b5-5e20a2ebaccb).</span><span class="sxs-lookup"><span data-stu-id="d2176-127">For more information, see [Tasks](https://msdn.microsoft.com/library/7166f1f1-4de8-4bd4-86b5-5e20a2ebaccb).</span></span>

## <a name="to-create-the-data-service-by-using-the-new-data-model"></a><span data-ttu-id="d2176-128">So erstellen Sie den Datendienst mit dem neuen Datenmodell</span><span class="sxs-lookup"><span data-stu-id="d2176-128">To create the data service by using the new data model</span></span>

1. <span data-ttu-id="d2176-129">Öffnen Sie in Visual Studio die EDMX-Datei, die das Datenmodell darstellt.</span><span class="sxs-lookup"><span data-stu-id="d2176-129">In Visual Studio, open the .edmx file that represents the data model.</span></span>

2. <span data-ttu-id="d2176-130">In der **Modellbrowser**mit der rechten Maustaste auf das Modell, klicken Sie auf **Eigenschaften**, und notieren Sie den Namen des Entitätscontainers handelt.</span><span class="sxs-lookup"><span data-stu-id="d2176-130">In the **Model Browser**, right-click the model, click **Properties**, and then note the name of the entity container.</span></span>

3. <span data-ttu-id="d2176-131">In **Projektmappen-Explorer**, mit der rechten Maustaste in des Namens Ihrer [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Projekt, und klicken Sie dann auf **hinzufügen** > **neues Element**.</span><span class="sxs-lookup"><span data-stu-id="d2176-131">In **Solution Explorer**, right-click the name of your [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] project, and then click **Add** > **New Item**.</span></span>

4. <span data-ttu-id="d2176-132">In der **neues Element hinzufügen** wählen Sie im Dialogfeld die **WCF Data Service** Vorlage in der **Web** Kategorie.</span><span class="sxs-lookup"><span data-stu-id="d2176-132">In the **Add New Item** dialog box, select the **WCF Data Service** template in the **Web** category.</span></span>

   ![WCF Data Service-Elementvorlage in Visual Studio 2015](media/wcf-data-service-item-template.png)

   > [!NOTE]
   > <span data-ttu-id="d2176-134">Die **WCF Data Service** Vorlage ist in Visual Studio 2015, aber nicht in Visual Studio 2017 verfügbar.</span><span class="sxs-lookup"><span data-stu-id="d2176-134">The **WCF Data Service** template is available in Visual Studio 2015, but not in Visual Studio 2017.</span></span>

5. <span data-ttu-id="d2176-135">Geben Sie einen Namen für den Dienst, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="d2176-135">Supply a name for the service, and then click **OK**.</span></span>

     <span data-ttu-id="d2176-136">Visual Studio erstellt das XML-Markup und die Codedateien für den neuen Dienst.</span><span class="sxs-lookup"><span data-stu-id="d2176-136">Visual Studio creates the XML markup and code files for the new service.</span></span> <span data-ttu-id="d2176-137">In der Standardeinstellung wird das Fenster des Code-Editors geöffnet.</span><span class="sxs-lookup"><span data-stu-id="d2176-137">By default, the code-editor window opens.</span></span>

6. <span data-ttu-id="d2176-138">Ersetzen Sie im Code für den Datendienst den Kommentar `/* TODO: put your data source class name here */` in der Definition der Klasse, die den Datendienst definiert, durch den Typ, der von der <xref:System.Data.Objects.ObjectContext>-Klasse erbt und der Entitätscontainer des Datenmodells ist, der in Schritt 2 notiert wurde.</span><span class="sxs-lookup"><span data-stu-id="d2176-138">In the code for the data service, replace the comment `/* TODO: put your data source class name here */` in the definition of the class that defines the data service with the type that inherits from the <xref:System.Data.Objects.ObjectContext> class and that is the entity container of the data model, which was noted in step 2.</span></span>

7. <span data-ttu-id="d2176-139">Ermöglichen Sie im Code für den Datendienst berechtigten Clients, auf die Entitätenmengen zuzugreifen, die der Datendienst verfügbar macht.</span><span class="sxs-lookup"><span data-stu-id="d2176-139">In the code for the data service, enable authorized clients to access the entity sets that the data service exposes.</span></span> <span data-ttu-id="d2176-140">Weitere Informationen finden Sie unter [Erstellen des Datendiensts](../../../../docs/framework/data/wcf/creating-the-data-service.md).</span><span class="sxs-lookup"><span data-stu-id="d2176-140">For more information, see [Creating the Data Service](../../../../docs/framework/data/wcf/creating-the-data-service.md).</span></span>

8. <span data-ttu-id="d2176-141">Führen Sie die Anweisungen im Thema, um den Northwind.svc-Datendienst mit einem Webbrowser zu testen, [Zugriff auf den Dienst über einen Webbrowser](../../../../docs/framework/data/wcf/accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md).</span><span class="sxs-lookup"><span data-stu-id="d2176-141">To test the Northwind.svc data service by using a Web browser, follow the instructions in the topic [Accessing the Service from a Web Browser](../../../../docs/framework/data/wcf/accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d2176-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d2176-142">See Also</span></span>

- [<span data-ttu-id="d2176-143">Defining WCF Data Services</span><span class="sxs-lookup"><span data-stu-id="d2176-143">Defining WCF Data Services</span></span>](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)
- [<span data-ttu-id="d2176-144">Datendienstanbieter</span><span class="sxs-lookup"><span data-stu-id="d2176-144">Data Services Providers</span></span>](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md)
- [<span data-ttu-id="d2176-145">: Erstellen eines Datendiensts mit dem Reflektionsanbieter</span><span class="sxs-lookup"><span data-stu-id="d2176-145">How to: Create a Data Service Using the Reflection Provider</span></span>](../../../../docs/framework/data/wcf/create-a-data-service-using-rp-wcf-data-services.md)
- [<span data-ttu-id="d2176-146">Vorgehensweise: Erstellen eines Datendiensts mit einer LINQ to SQL-Datenquelle</span><span class="sxs-lookup"><span data-stu-id="d2176-146">How to: Create a Data Service Using a LINQ to SQL Data Source</span></span>](../../../../docs/framework/data/wcf/create-a-data-service-using-linq-to-sql-wcf.md)