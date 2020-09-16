---
title: 'Gewusst wie: Erstellen eines Datendiensts mit einer ADO.NET-Entity Framework-Datenquelle (WCF Data Services)'
ms.date: 08/24/2018
helpviewer_keywords:
- WCF Data Services, providers
- WCF Data Services, Entity Framework
ms.assetid: 6d11fec8-0108-42f5-8719-2a7866d04428
ms.openlocfilehash: 1e559488a3260fafe6c211ff47226a258fc1289a
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90557696"
---
# <a name="how-to-create-a-data-service-using-an-adonet-entity-framework-data-source-wcf-data-services"></a><span data-ttu-id="f4668-102">Gewusst wie: Erstellen eines Datendiensts mit einer ADO.NET-Entity Framework-Datenquelle (WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="f4668-102">How to: Create a Data Service Using an ADO.NET Entity Framework Data Source (WCF Data Services)</span></span>

<span data-ttu-id="f4668-103">WCF Data Services macht Entitäts Daten als Datendienst verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f4668-103">WCF Data Services exposes entity data as a data service.</span></span> <span data-ttu-id="f4668-104">Diese Entitäts Daten werden vom ADO. ntentity-Framework bereitgestellt, wenn die Datenquelle eine relationale Datenbank ist.</span><span class="sxs-lookup"><span data-stu-id="f4668-104">This entity data is provided by the ADO.NETEntity Framework when the data source is a relational database.</span></span> <span data-ttu-id="f4668-105">In diesem Thema wird gezeigt, wie ein Entity Framework-basiertes Datenmodell in einer Visual Studio-Webanwendung erstellt wird, die auf einer vorhandenen Datenbank basiert, und wie mit diesem Datenmodell ein neuer Datendienst erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="f4668-105">This topic shows you how to create an Entity Framework-based data model in a Visual Studio Web application that is based on an existing database and use this data model to create a new data service.</span></span>

<span data-ttu-id="f4668-106">Das Entity Framework stellt auch ein Befehlszeilentool bereit, das ein Entity Framework-Modell außerhalb eines Visual Studio-Projekts generieren kann.</span><span class="sxs-lookup"><span data-stu-id="f4668-106">The Entity Framework also provides a command line tool that can generate an Entity Framework model outside of a Visual Studio project.</span></span> <span data-ttu-id="f4668-107">Weitere Informationen finden Sie unter Gewusst [wie: Verwenden von EdmGen.exe zum Generieren von Modell-und Mapping-Dateien](../adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span><span class="sxs-lookup"><span data-stu-id="f4668-107">For more information, see [How to: Use EdmGen.exe to Generate the Model and Mapping Files](../adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span></span>

## <a name="to-add-an-entity-framework-model-that-is-based-on-an-existing-database-to-an-existing-web-application"></a><span data-ttu-id="f4668-108">So fügen Sie einer vorhandenen Webanwendung ein Entity Framework-Modell hinzu, das auf einer vorhandenen Datenbank basiert</span><span class="sxs-lookup"><span data-stu-id="f4668-108">To add an Entity Framework model that is based on an existing database to an existing Web application</span></span>

1. <span data-ttu-id="f4668-109">Klicken Sie im Menü **Projekt** auf **Add**  >  **Neues Element**hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="f4668-109">On the **Project** menu, click **Add** > **New Item**.</span></span>

2. <span data-ttu-id="f4668-110">Klicken Sie im Bereich **Vorlagen** auf die Kategorie **Daten** , und wählen Sie dann **ADO.NET Entity Data Model**aus.</span><span class="sxs-lookup"><span data-stu-id="f4668-110">In the **Templates** pane, click the **Data** category, and then select **ADO.NET Entity Data Model**.</span></span>

3. <span data-ttu-id="f4668-111">Geben Sie den Modellnamen ein, und klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="f4668-111">Enter the model name and then click **Add**.</span></span>

     <span data-ttu-id="f4668-112">Die erste Seite des Entity Data Model-Assistenten wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f4668-112">The first page of the Entity Data Model Wizard is displayed.</span></span>

4. <span data-ttu-id="f4668-113">Wählen Sie im Dialogfeld **Modell Inhalte auswählen** die Option **aus Datenbank generieren aus**.</span><span class="sxs-lookup"><span data-stu-id="f4668-113">In the **Choose Model Contents** dialog box, select **Generate from database**.</span></span> <span data-ttu-id="f4668-114">Klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="f4668-114">Then click **Next**.</span></span>

5. <span data-ttu-id="f4668-115">Klicken Sie auf die Schaltfläche **neue Verbindung** .</span><span class="sxs-lookup"><span data-stu-id="f4668-115">Click the **New Connection** button.</span></span>

6. <span data-ttu-id="f4668-116">Geben Sie im Dialogfeld **Verbindungs Eigenschaften** den Servernamen ein, wählen Sie die Authentifizierungsmethode aus, geben Sie den Datenbanknamen ein, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="f4668-116">In the **Connection Properties** dialog box, type your server name, select the authentication method, type the database name, and then click **OK**.</span></span>

     <span data-ttu-id="f4668-117">Das Dialogfeld **Wählen Sie Ihre Datenverbindung** aus wird mit den Einstellungen für die Datenbankverbindung aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="f4668-117">The **Choose Your Data Connection** dialog box is updated with your database connection settings.</span></span>

7. <span data-ttu-id="f4668-118">Stellen Sie sicher, dass das Kontrollkästchen **Entitäts Verbindungseinstellungen in App.Config unter: Speichern** aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="f4668-118">Ensure that the **Save entity connection settings in App.Config as:** checkbox is checked.</span></span> <span data-ttu-id="f4668-119">Klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="f4668-119">Then click **Next**.</span></span>

8. <span data-ttu-id="f4668-120">Wählen Sie im Dialogfeld **Wählen Sie Ihre Datenbankobjekte** aus alle Datenbankobjekte aus, die im Datendienst verfügbar gemacht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="f4668-120">In the **Choose Your Database Objects** dialog box, select all of database objects that you plan to expose in the data service.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f4668-121">Im Datenmodell enthaltene Objekte werden nicht automatisch vom Datendienst verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="f4668-121">Objects included in the data model are not automatically exposed by the data service.</span></span> <span data-ttu-id="f4668-122">Sie müssen explizit vom Dienst selbst verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="f4668-122">They must be explicitly exposed by the service itself.</span></span> <span data-ttu-id="f4668-123">Weitere Informationen finden Sie unter [Konfigurieren des Daten Dienstanbieter](configuring-the-data-service-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="f4668-123">For more information, see [Configuring the Data Service](configuring-the-data-service-wcf-data-services.md).</span></span>

9. <span data-ttu-id="f4668-124">Klicken Sie auf **Fertig stellen**, um den Assistenten abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="f4668-124">Click **Finish** to complete the wizard.</span></span>

     <span data-ttu-id="f4668-125">Dadurch wird ein Standarddatenmodell auf Grundlage der bestimmten Datenbank erstellt.</span><span class="sxs-lookup"><span data-stu-id="f4668-125">This creates a default data model based on the specific database.</span></span> <span data-ttu-id="f4668-126">Das Entity Framework ermöglicht das Anpassen des Datenmodells.</span><span class="sxs-lookup"><span data-stu-id="f4668-126">The Entity Framework enables to customize the data model.</span></span> <span data-ttu-id="f4668-127">Weitere Informationen finden Sie unter [Entity Data Model Tools Tasks](/previous-versions/dotnet/netframework-4.0/bb738480(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="f4668-127">For more information, see [Entity Data Model Tools Tasks](/previous-versions/dotnet/netframework-4.0/bb738480(v=vs.100)).</span></span>

## <a name="to-create-the-data-service-by-using-the-new-data-model"></a><span data-ttu-id="f4668-128">So erstellen Sie den Datendienst mit dem neuen Datenmodell</span><span class="sxs-lookup"><span data-stu-id="f4668-128">To create the data service by using the new data model</span></span>

1. <span data-ttu-id="f4668-129">Öffnen Sie in Visual Studio die EDMX-Datei, die das Datenmodell darstellt.</span><span class="sxs-lookup"><span data-stu-id="f4668-129">In Visual Studio, open the .edmx file that represents the data model.</span></span>

2. <span data-ttu-id="f4668-130">Klicken Sie im **Modell Browser**mit der rechten Maustaste auf das Modell, klicken Sie auf **Eigenschaften**, und notieren Sie dann den Namen des Entitätencontainers.</span><span class="sxs-lookup"><span data-stu-id="f4668-130">In the **Model Browser**, right-click the model, click **Properties**, and then note the name of the entity container.</span></span>

3. <span data-ttu-id="f4668-131">Klicken Sie in **Projektmappen-Explorer**mit der rechten Maustaste auf den Namen Ihres ASP.NET-Projekts, und klicken Sie dann auf **Add**  >  **Neues Element**hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="f4668-131">In **Solution Explorer**, right-click the name of your ASP.NET project, and then click **Add** > **New Item**.</span></span>

4. <span data-ttu-id="f4668-132">Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Vorlage **WCF Data Service** in der Kategorie **Web** aus.</span><span class="sxs-lookup"><span data-stu-id="f4668-132">In the **Add New Item** dialog box, select the **WCF Data Service** template in the **Web** category.</span></span>

   ![WCF Data Service-Element Vorlage in Visual Studio 2015](./media/wcf-data-service-item-template.png)

   > [!NOTE]
   > <span data-ttu-id="f4668-134">Die **WCF Data Service** -Vorlage ist in Visual Studio 2015 verfügbar, aber nicht in Visual Studio 2017 oder höher.</span><span class="sxs-lookup"><span data-stu-id="f4668-134">The **WCF Data Service** template is available in Visual Studio 2015, but not in Visual Studio 2017 or later.</span></span>

5. <span data-ttu-id="f4668-135">Geben Sie einen Namen für den Dienst an, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="f4668-135">Supply a name for the service, and then click **OK**.</span></span>

     <span data-ttu-id="f4668-136">Visual Studio erstellt das XML-Markup und die Codedateien für den neuen Dienst.</span><span class="sxs-lookup"><span data-stu-id="f4668-136">Visual Studio creates the XML markup and code files for the new service.</span></span> <span data-ttu-id="f4668-137">In der Standardeinstellung wird das Fenster des Code-Editors geöffnet.</span><span class="sxs-lookup"><span data-stu-id="f4668-137">By default, the code-editor window opens.</span></span>

6. <span data-ttu-id="f4668-138">Ersetzen Sie im Code für den Datendienst den Kommentar `/* TODO: put your data source class name here */` in der Definition der Klasse, die den Datendienst definiert, durch den Typ, der von der <xref:System.Data.Objects.ObjectContext>-Klasse erbt und der Entitätscontainer des Datenmodells ist, der in Schritt 2 notiert wurde.</span><span class="sxs-lookup"><span data-stu-id="f4668-138">In the code for the data service, replace the comment `/* TODO: put your data source class name here */` in the definition of the class that defines the data service with the type that inherits from the <xref:System.Data.Objects.ObjectContext> class and that is the entity container of the data model, which was noted in step 2.</span></span>

7. <span data-ttu-id="f4668-139">Ermöglichen Sie im Code für den Datendienst berechtigten Clients, auf die Entitätenmengen zuzugreifen, die der Datendienst verfügbar macht.</span><span class="sxs-lookup"><span data-stu-id="f4668-139">In the code for the data service, enable authorized clients to access the entity sets that the data service exposes.</span></span> <span data-ttu-id="f4668-140">Weitere Informationen finden Sie unter [Erstellen des Daten Dienstanbieter](creating-the-data-service.md).</span><span class="sxs-lookup"><span data-stu-id="f4668-140">For more information, see [Creating the Data Service](creating-the-data-service.md).</span></span>

8. <span data-ttu-id="f4668-141">Befolgen Sie die Anweisungen im Thema [zugreifen auf den Dienst über einen Webbrowser](accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md), um den Datendienst Northwind. svc mithilfe eines Webbrowsers zu testen.</span><span class="sxs-lookup"><span data-stu-id="f4668-141">To test the Northwind.svc data service by using a Web browser, follow the instructions in the topic [Accessing the Service from a Web Browser](accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f4668-142">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f4668-142">See also</span></span>

- [<span data-ttu-id="f4668-143">Definieren von WCF Data Services</span><span class="sxs-lookup"><span data-stu-id="f4668-143">Defining WCF Data Services</span></span>](defining-wcf-data-services.md)
- [<span data-ttu-id="f4668-144">Datendienstanbieter</span><span class="sxs-lookup"><span data-stu-id="f4668-144">Data Services Providers</span></span>](data-services-providers-wcf-data-services.md)
- [<span data-ttu-id="f4668-145">Vorgehensweise: Erstellen eines Datendiensts mit dem Reflektionsanbieter</span><span class="sxs-lookup"><span data-stu-id="f4668-145">How to: Create a Data Service Using the Reflection Provider</span></span>](create-a-data-service-using-rp-wcf-data-services.md)
- [<span data-ttu-id="f4668-146">Vorgehensweise: Erstellen eines Datendiensts mit einer LINQ to SQL-Datenquelle</span><span class="sxs-lookup"><span data-stu-id="f4668-146">How to: Create a Data Service Using a LINQ to SQL Data Source</span></span>](create-a-data-service-using-linq-to-sql-wcf.md)
