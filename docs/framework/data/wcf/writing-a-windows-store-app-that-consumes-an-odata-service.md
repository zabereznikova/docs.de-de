---
title: Schreiben einer Windows Store-App, die einen OData-Dienst beansprucht
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
ms.assetid: 9917a0e9-ec93-49e5-a366-fd39b892eb8b
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3a2eb79e8bf8a5c683c9d48a0a69e4d7f5d270eb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="writing-a-windows-store-app-that-consumes-an-odata-service"></a><span data-ttu-id="62ce4-102">Schreiben einer Windows Store-App, die einen OData-Dienst beansprucht</span><span class="sxs-lookup"><span data-stu-id="62ce4-102">Writing a Windows Store App that consumes an OData Service</span></span>
<span data-ttu-id="62ce4-103">Windows 8 wird eine neue Art von Anwendung eingeführt: die Windows Store-app.</span><span class="sxs-lookup"><span data-stu-id="62ce4-103">Windows 8 introduces a new type of application: the Windows Store app.</span></span> <span data-ttu-id="62ce4-104">Windows Store-Apps haben ein neues Erscheinungsbild, können auf einer Vielzahl von Geräten ausgeführt werden und werden im Windows Store bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="62ce4-104">Windows Store apps have a brand new look and feel, run on a variety of devices, and are made available on the Windows Store.</span></span> <span data-ttu-id="62ce4-105">In diesem Thema wird beschrieben, wie Sie eine Windows Store-App schreiben, die einen OData-Dienst beansprucht, den NetFlix Catalog OData-Dienst.</span><span class="sxs-lookup"><span data-stu-id="62ce4-105">This topic describes how to write a Windows Store app that consumes an OData service, specifically the NetFlix Catalog OData service.</span></span> <span data-ttu-id="62ce4-106">Weitere Informationen zu Windows Store-Apps, lesen Sie [erste Schritte mit Windows Store-apps](http://msdn.microsoft.com/library/windows/apps/br211386.aspx).</span><span class="sxs-lookup"><span data-stu-id="62ce4-106">For more information about Windows Store Apps, please read [Getting Started with Windows Store apps](http://msdn.microsoft.com/library/windows/apps/br211386.aspx).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="62ce4-107">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="62ce4-107">Prerequisites</span></span>  
  
1.  [<span data-ttu-id="62ce4-108">Microsoft Windows 8</span><span class="sxs-lookup"><span data-stu-id="62ce4-108">Microsoft Windows 8</span></span>](http://go.microsoft.com/fwlink/p/?LinkId=266654)  
  
2.  [<span data-ttu-id="62ce4-109">Microsoft Visual Studio 2012</span><span class="sxs-lookup"><span data-stu-id="62ce4-109">Microsoft Visual Studio 2012</span></span>](http://go.microsoft.com/fwlink/p/?LinkId=266655)  
  
3.  [<span data-ttu-id="62ce4-110">WCF Data Services</span><span class="sxs-lookup"><span data-stu-id="62ce4-110">WCF Data Services</span></span>](http://msdn.microsoft.com/data/bb931106)  
  
#### <a name="creating-the-default-windows-store-grid-application"></a><span data-ttu-id="62ce4-111">Erstellen der standardmäßigen Windows Store-Rasteranwendung</span><span class="sxs-lookup"><span data-stu-id="62ce4-111">Creating the default Windows Store Grid Application</span></span>  
  
1.  <span data-ttu-id="62ce4-112">Erstellen Sie eine neue Windows Store-Rasteranwendung mithilfe von C# und XAML.</span><span class="sxs-lookup"><span data-stu-id="62ce4-112">Create a new Windows Store Grid Application using C# and XAML.</span></span> <span data-ttu-id="62ce4-113">Benennen Sie die Anwendung als OData.WindowsStore.NetflixDemo:</span><span class="sxs-lookup"><span data-stu-id="62ce4-113">Name the application OData.WindowsStore.NetflixDemo:</span></span>  
  
     <span data-ttu-id="62ce4-114">![Dialogfeld "Neues Projekt"](../../../../docs/framework/data/wcf/media/win8clientcreatenewproject.png "Win8ClientCreateNewProject")</span><span class="sxs-lookup"><span data-stu-id="62ce4-114">![New Project Dialog](../../../../docs/framework/data/wcf/media/win8clientcreatenewproject.png "Win8ClientCreateNewProject")</span></span>  
  
2.  <span data-ttu-id="62ce4-115">Öffnen Sie Package.appxmanifest, und geben sie im Textfeld Anzeigename einen Anzeigenamen ein.</span><span class="sxs-lookup"><span data-stu-id="62ce4-115">Open the Package.appxmanifest and enter a friendly name in the Display name text box.</span></span> <span data-ttu-id="62ce4-116">Dies gibt den Anwendungsnamen an, der für die Windows 8-Suchfunktion verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="62ce4-116">This specifies the application name used with the Windows 8 search functionality.</span></span>  
  
     <span data-ttu-id="62ce4-117">![Anwendungsmanifestdatei](../../../../docs/framework/data/wcf/media/appxmanifest.png "Appxmanifest")</span><span class="sxs-lookup"><span data-stu-id="62ce4-117">![Application manifest file](../../../../docs/framework/data/wcf/media/appxmanifest.png "appxmanifest")</span></span>  
  
3.  <span data-ttu-id="62ce4-118">Geben Sie einen Anzeigenamen in der \<AppName >-Element in der Datei "App.xaml".</span><span class="sxs-lookup"><span data-stu-id="62ce4-118">Enter a friendly name in the \<AppName> element in the App.xaml file.</span></span> <span data-ttu-id="62ce4-119">Hiermit legen Sie den Anwendungsnamen fest, der beim Anwendungsstart angezeigt wird:</span><span class="sxs-lookup"><span data-stu-id="62ce4-119">This sets the application name that is displayed when the application is launched:</span></span>  
  
     <span data-ttu-id="62ce4-120">![Datei "App.xaml"](../../../../docs/framework/data/wcf/media/appxaml.png "Appxaml")</span><span class="sxs-lookup"><span data-stu-id="62ce4-120">![App.xaml file](../../../../docs/framework/data/wcf/media/appxaml.png "appxaml")</span></span>  
  
4.  <span data-ttu-id="62ce4-121">Erstellen Sie die Anwendung und führen Sie sie aus.</span><span class="sxs-lookup"><span data-stu-id="62ce4-121">Build and launch the application.</span></span> <span data-ttu-id="62ce4-122">Zunächst wird der Begrüßungsbildschirm der Anwendung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="62ce4-122">You first see the application’s splash screen.</span></span> <span data-ttu-id="62ce4-123">Der folgende Screenshot zeigt den Standardbegrüßungsbildschirm.</span><span class="sxs-lookup"><span data-stu-id="62ce4-123">The screenshot below displays the default splash screen.</span></span> <span data-ttu-id="62ce4-124">Das verwendete Bild wird im Ressourcenordner des Projekts gespeichert.</span><span class="sxs-lookup"><span data-stu-id="62ce4-124">The image used is stored in the project’s Assets folder.</span></span>  
  
     <span data-ttu-id="62ce4-125">![Der Standardbegrüßungsbildschirm der app](../../../../docs/framework/data/wcf/media/defualtappsplash.png "DefualtAppSplash")</span><span class="sxs-lookup"><span data-stu-id="62ce4-125">![The default app splash screen](../../../../docs/framework/data/wcf/media/defualtappsplash.png "defualtAppSplash")</span></span>  
  
     <span data-ttu-id="62ce4-126">Anschließend wird die Anwendung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="62ce4-126">Then the application will be displayed.</span></span>  
  
     <span data-ttu-id="62ce4-127">![Die standardanwendung](../../../../docs/framework/data/wcf/media/defaultapplication.png "DefaultApplication")</span><span class="sxs-lookup"><span data-stu-id="62ce4-127">![The default application](../../../../docs/framework/data/wcf/media/defaultapplication.png "DefaultApplication")</span></span>  
  
     <span data-ttu-id="62ce4-128">Die Standardanwendung definiert eine Reihe von Klassen in SampleDataSource.cs: SampleDataGroup und SampleDataItem, die von SampleDataCommon abgeleitet werden, die wiederum von BindableBase abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="62ce4-128">The default application defines a set of classes in SampleDataSource.cs: SampleDataGroup and SampleDataItem, both of which are derived from SampleDataCommon, which itself is derived from BindableBase.</span></span> <span data-ttu-id="62ce4-129">SampleDataGroup und SampleDataItem sind an den Standardwert GridView gebunden.</span><span class="sxs-lookup"><span data-stu-id="62ce4-129">SampleDataGroup and SampleDataItem are bound to the default GridView.</span></span> <span data-ttu-id="62ce4-130">SampleDataSource.cs befindet sich im DataModel-Ordner innerhalb des NetflixDemo-Projekts.</span><span class="sxs-lookup"><span data-stu-id="62ce4-130">SampleDataSource.cs is located in the DataModel folder within the NetflixDemo project.</span></span> <span data-ttu-id="62ce4-131">Die Anwendung zeigt eine gruppierte Auflistung an.</span><span class="sxs-lookup"><span data-stu-id="62ce4-131">The application displays a grouped collection.</span></span> <span data-ttu-id="62ce4-132">Jede Gruppe enthält eine Reihe von Elementen, die jeweils durch SampleDataGroup und SampleDataItem dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="62ce4-132">Each group contains any number of items, represented by SampleDataGroup and SampleDataItem, respectively.</span></span> <span data-ttu-id="62ce4-133">Der vorherige Screenshot enthält die Gruppe Group Title 1. Alle Elemente in der Gruppe werden zusammen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="62ce4-133">In the previous screen shot you can see a group called Group Title 1 and all of the items in the group displayed together.</span></span>  
  
     <span data-ttu-id="62ce4-134">Die Hauptseite der Anwendung ist GroupedItemsPage.xaml.</span><span class="sxs-lookup"><span data-stu-id="62ce4-134">The main page of the application is GroupedItemsPage.xaml.</span></span> <span data-ttu-id="62ce4-135">Sie enthält eine GridView, die die von der SampleDataSource.cs-Klasse erstellten Beispieldaten anzeigt.</span><span class="sxs-lookup"><span data-stu-id="62ce4-135">It contains a GridView that displays the sample data created by the SampleDataSource.cs class.</span></span> <span data-ttu-id="62ce4-136">GroupedItemsPage wird von App.xaml.cs durch einen Aufruf von rootFrame.Navigate geladen:</span><span class="sxs-lookup"><span data-stu-id="62ce4-136">The GroupedItemsPage is loaded by the App.xaml.cs in a call to rootFrame.Navigate:</span></span>  
  
    ```csharp  
    if (!rootFrame.Navigate(typeof(GroupedItemsPage), "AllGroups"))  
    {  
        throw new Exception("Failed to create initial page");  
    }  
    ```  
  
     <span data-ttu-id="62ce4-137">Hierdurch wird GroupedItemsPage instanziiert, und die zugehörige LoadState-Methode wird aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="62ce4-137">This causes the GroupedItemsPage to be instantiated and it’s LoadState method is called.</span></span> <span data-ttu-id="62ce4-138">LoadState bewirkt die Erstellung der statischen SampleDataSource-Instanz, die eine Auflistung von SampleDataGroup-Objekten erstellt.</span><span class="sxs-lookup"><span data-stu-id="62ce4-138">LoadState causes the static SampleDataSource instance to be created, which creates a collection of SampleDataGroup objects.</span></span> <span data-ttu-id="62ce4-139">Jedes SampleDataGroup-Objekt enthält eine Auflistung von SampleDataItem-Objekten.</span><span class="sxs-lookup"><span data-stu-id="62ce4-139">Each SampleDataGroup object contains a collection of SampleDataItem objects.</span></span> <span data-ttu-id="62ce4-140">LoadState speichert die Auflistung von SampleDataGroup-Objekten in DefaultViewModel:</span><span class="sxs-lookup"><span data-stu-id="62ce4-140">LoadState stores the collection of SampleDataGroup objects in the DefaultViewModel:</span></span>  
  
    ```csharp  
    protected override void LoadState(Object navigationParameter, Dictionary<String, Object> pageState)  
    {  
        var sampleDataGroups = SampleDataSource.GetGroups((String)navigationParameter);  
        this.DefaultViewModel["Groups"] = sampleDataGroups;  
    }  
    ```  
  
     <span data-ttu-id="62ce4-141">Das DefaultViewModel wird dann an die GridView gebunden.</span><span class="sxs-lookup"><span data-stu-id="62ce4-141">The DefaultViewModel is then bound to the GridView.</span></span> <span data-ttu-id="62ce4-142">Hierauf wird bei der Konfiguration der Datenbindung in der Datei GroupedItemsPage.xaml verwiesen.</span><span class="sxs-lookup"><span data-stu-id="62ce4-142">This is referenced in the GroupedItemsPage.xaml file when configuring the data binding.</span></span>  
  
    ```xaml
    <CollectionViewSource  
                x:Name="groupedItemsViewSource"  
                Source="{Binding Groups}"  
                IsSourceGrouped="true"  
                ItemsPath="TopItems"  
                d:Source="{Binding AllGroups, Source={d:DesignInstance Type=data:SampleDataSource, IsDesignTimeCreatable=True}}"/>  
    ```  
  
     <span data-ttu-id="62ce4-143">CollectionViewSource wird als Proxy zum Behandeln von gruppierten Auflistungen verwendet.</span><span class="sxs-lookup"><span data-stu-id="62ce4-143">The CollectionViewSource is used as a proxy for handling grouped collections.</span></span> <span data-ttu-id="62ce4-144">Bei der Ausführung der Bindung durchläuft sie die Auflistung von SampleDataGroup-Objekten, um die GridView aufzufüllen.</span><span class="sxs-lookup"><span data-stu-id="62ce4-144">When binding occurs, it iterates through the collection of SampleDataGroup objects to populate the GridView.</span></span>  <span data-ttu-id="62ce4-145">Das ItemsPath-Attribut teilt CollectionViewSource mit, welche Eigenschaft für jedes SampleDataGroup-Objekt verwendet werden soll, um die enthaltenen SampleDataItems.</span><span class="sxs-lookup"><span data-stu-id="62ce4-145">The ItemsPath attribute tells the CollectionViewSource what property on each SampleDataGroup object to use to find the SampleDataItems it contains.</span></span> <span data-ttu-id="62ce4-146">In diesem Fall enthält jedes SampleDataGroup-Objekt eine TopItems-Auflistung von SampleDataItem-Objekten.</span><span class="sxs-lookup"><span data-stu-id="62ce4-146">In this case each SampleDataGroup object contains a TopItems collection of SampleDataItem objects.</span></span>  
  
     <span data-ttu-id="62ce4-147">Für die Netflix-Anwendung werden Filme nach Genre gruppiert.</span><span class="sxs-lookup"><span data-stu-id="62ce4-147">For the Netflix application, movies are grouped by genre.</span></span> <span data-ttu-id="62ce4-148">Daher zeigt die Anwendung mehrere Genres und eine Liste von Filmen innerhalb dieses Genres an.</span><span class="sxs-lookup"><span data-stu-id="62ce4-148">So the application displays a number of genres and a list of movies within that genre.</span></span>  
  
#### <a name="add-a-service-reference-to-the-netflix-odata-service"></a><span data-ttu-id="62ce4-149">Hinzufügen eines Dienstverweises auf den Netflix-OData-Dienst</span><span class="sxs-lookup"><span data-stu-id="62ce4-149">Add a Service Reference to the Netflix OData Service</span></span>  
  
1.  <span data-ttu-id="62ce4-150">Bevor Aufrufe des Netflix-OData-Diensts möglich sind, muss ein Dienstverweis hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="62ce4-150">Before we can make any calls to the Netflix OData service we need to add a service reference.</span></span> <span data-ttu-id="62ce4-151">Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das Projekt, und wählen Sie Dienstverweis hinzufügen aus.</span><span class="sxs-lookup"><span data-stu-id="62ce4-151">Right-click the project in the Solution Explorer and select Add Service Reference…</span></span>  
  
     <span data-ttu-id="62ce4-152">![Hinzufügen von "Dienstverweis"](../../../../docs/framework/data/wcf/media/addservicereferenceodata.png "AddServiceReferenceOData")</span><span class="sxs-lookup"><span data-stu-id="62ce4-152">![Add Service Reference Dialog](../../../../docs/framework/data/wcf/media/addservicereferenceodata.png "AddServiceReferenceOData")</span></span>  
  
2.  <span data-ttu-id="62ce4-153">Geben Sie die URL für den Netflix-OData-Dienst in der Adressleiste ein, und klicken Sie auf Gehe zu.</span><span class="sxs-lookup"><span data-stu-id="62ce4-153">Enter the URL for the Netflix OData service in the Address bar and click Go.</span></span> <span data-ttu-id="62ce4-154">Legen Sie den Namespace des Dienstverweises auf Netflix fest, und klicken Sie auf OK.</span><span class="sxs-lookup"><span data-stu-id="62ce4-154">Set the Namespace of the service reference to Netflix and click OK.</span></span>  
  
     <span data-ttu-id="62ce4-155">![Referenz-Dienstfehler hinzufügen](../../../../docs/framework/data/wcf/media/addservicereferenceerror.png "AddServiceReferenceError")</span><span class="sxs-lookup"><span data-stu-id="62ce4-155">![Add Service Reference Error](../../../../docs/framework/data/wcf/media/addservicereferenceerror.png "AddServiceReferenceError")</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="62ce4-156">Wenn Sie noch nicht installiert haben [WCF Data Services-Tools für Windows Store-Apps](http://go.microsoft.com/fwlink/p/?LinkId=266652), werden Sie mit einer Meldung wie der obigen aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="62ce4-156">If you have not yet installed [WCF Data Services Tools for Windows Store Apps](http://go.microsoft.com/fwlink/p/?LinkId=266652), you will be prompted with a message such as the one above.</span></span> <span data-ttu-id="62ce4-157">Sie müssen die im Link aufgeführten Tools herunterladen und installieren, um den Vorgang fortzusetzen.</span><span class="sxs-lookup"><span data-stu-id="62ce4-157">You will need to download and install the tools referenced in the link to continue.</span></span>  
  
 <span data-ttu-id="62ce4-158">Durch das Hinzufügen eines Dienstverweises werden stark typisierte Klassen generiert, die WCF Data Services verwendet, um die vom Netflix-OData-Dienst zurückgegebenen OData zu analysieren.</span><span class="sxs-lookup"><span data-stu-id="62ce4-158">Adding a service reference generates strongly typed classes that WCF Data Services will use to parse the OData returned by the Netflix OData service.</span></span> <span data-ttu-id="62ce4-159">Die in SampleDataSource.cs definierten Klassen können an die GridView gebunden werden. Daher müssen die Daten aus den generierten OData-Clientklassen in die bindungsfähigen Klassen übertragen werden, die in SampleDataSource.cs definiert sind.</span><span class="sxs-lookup"><span data-stu-id="62ce4-159">The classes defined in SampleDataSource.cs can be bound to the GridView so we need to transfer the data from the generated OData client classes into the bindable classes defined in SampleDataSource.cs.</span></span>  <span data-ttu-id="62ce4-160">Um dies zu erreichen, müssen einige Änderungen an dem in SampleDataSource.cs definierten Datenmodell vorgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="62ce4-160">In order to do this, we need to make some changes to the data model defined in SampleDataSource.cs.</span></span>  
  
#### <a name="update-the-data-model-for-the-application"></a><span data-ttu-id="62ce4-161">Aktualisieren des Datenmodells für die Anwendung</span><span class="sxs-lookup"><span data-stu-id="62ce4-161">Update the data model for the application</span></span>  
  
1.  <span data-ttu-id="62ce4-162">Ersetzen Sie den vorhandenen Code in SampleDataSource.cs durch Code aus [diesem gist-Archiv](https://gist.github.com/3419288).</span><span class="sxs-lookup"><span data-stu-id="62ce4-162">Replace the existing code in SampleDataSource.cs with the code from [this gist](https://gist.github.com/3419288).</span></span> <span data-ttu-id="62ce4-163">Der aktualisierte Code fügt (der SampleDataSource-Klasse) eine LoadMovies-Methode hinzu, die eine Abfrage für den Netflix-OData-Dienst ausführt und eine Liste von Genres (allGroups) und innerhalb jedes Genres eine Liste von Filmen auffüllt.</span><span class="sxs-lookup"><span data-stu-id="62ce4-163">The updated code adds a LoadMovies method (to the SampleDataSource class)  that performs a query against the Netflix OData service and populates a list of genres (allGroups) and within each genre a list of movies.</span></span> <span data-ttu-id="62ce4-164">Die SampleDataGroup-Klasse wird verwendet, um ein Genre darzustellen, und die SampleDataItem-Klasse wird verwendet, um einen Film darzustellen.</span><span class="sxs-lookup"><span data-stu-id="62ce4-164">The SampleDataGroup class is used to represent a genre and the SampleDataItem class is used to represent a movie.</span></span>  
  
    ```csharp  
    public static async void LoadMovies()  
    {  
        IEnumerable<Title> titles = await ((DataServiceQuery<Title>)Context.Titles  
            .Expand("Genres,AudioFormats,AudioFormats/Language,Awards,Cast")  
            .Where(t => t.Rating == "PG")  
            .OrderByDescending(t => t.ReleaseYear)  
            .Take(300)).ExecuteAsync();  
  
        foreach (Title title in titles)  
        {  
            foreach (Genre netflixGenre in title.Genres)  
            {  
                SampleDataGroup genre = GetGroup(netflixGenre.Name);  
                if (genre == null)  
                {  
                    genre = new SampleDataGroup(netflixGenre.Name, netflixGenre.Name, String.Empty, title.BoxArt.LargeUrl, String.Empty);  
                    Instance.AllGroups.Add(genre);  
                }  
                var content = new StringBuilder();  
                // Write additional things to content here if you want them to display in the item detail.  
                genre.Items.Add(new SampleDataItem(title.Id, title.Name, String.Format("{0}rnrn{1} ({2})", title.Synopsis, title.Rating, title.ReleaseYear), title.BoxArt.HighDefinitionUrl ?? title.BoxArt.LargeUrl, "Description", content.ToString()));  
            }  
        }  
    }  
    ```  
  
     <span data-ttu-id="62ce4-165">Die [aufgabenbasierte asynchrone Muster](http://go.microsoft.com/fwlink/p/?LinkId=266651) (TAP) wird verwendet, um asynchron abrufen von 300 (Take) neue (OrderByDescending) PG-bewertete (Where) Filme von netflix abzurufen.</span><span class="sxs-lookup"><span data-stu-id="62ce4-165">The [Task-based Asynchronous Pattern](http://go.microsoft.com/fwlink/p/?LinkId=266651) (TAP) is used to asynchronously get 300 (Take) recent (OrderByDescending) PG-rated (Where) movies back from Netflix.</span></span> <span data-ttu-id="62ce4-166">Der restliche Code erstellt SimpleDataItems und SimpleDataGroups aus den Entitäten, die im OData-Feed zurückgegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="62ce4-166">The rest of the code constructs SimpleDataItems and SimpleDataGroups from the entities that were returned in the OData feed.</span></span>  
  
     <span data-ttu-id="62ce4-167">Die SampleDataSource-Klasse implementiert auch eine einfache Suchmethode.</span><span class="sxs-lookup"><span data-stu-id="62ce4-167">The SampleDataSource class also implements a simple search method.</span></span> <span data-ttu-id="62ce4-168">In diesem Fall wird eine einfache Suche im Arbeitsspeicher für die geladenen Filme ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="62ce4-168">In this case, it does a simple in-memory search of the loaded movies.</span></span>  
  
    ```csharp  
    public static IEnumerable<SampleDataItem> Search(string searchString)  
    {  
            var regex = new Regex(searchString, RegexOptions.CultureInvariant | RegexOptions.IgnoreCase | RegexOptions.IgnorePatternWhitespace);  
            return Instance.AllGroups  
                .SelectMany(g => g.Items)  
                .Where(m => regex.IsMatch(m.Title) || regex.IsMatch(m.Subtitle))  
                    .Distinct(new SampleDataItemComparer());  
    }  
    ```  
  
     <span data-ttu-id="62ce4-169">Ebenfalls in SampleDataSource.cs wird die Klasse mit dem Namen ExtensionMethods definiert.</span><span class="sxs-lookup"><span data-stu-id="62ce4-169">Also in SampleDataSource.cs a class called ExtensionMethods is defined.</span></span> <span data-ttu-id="62ce4-170">Jede dieser Erweiterungsmethoden verwendet das TAP-Muster, um es SampleDataSource zu ermöglichen, eine OData-Abfrage auszuführen, ohne die Benutzeroberfläche zu blockieren.</span><span class="sxs-lookup"><span data-stu-id="62ce4-170">Each of these extension methods uses the TAP pattern to allow the SampleDataSource to execute an OData query without blocking the UI.</span></span> <span data-ttu-id="62ce4-171">Beispielsweise verwenden die folgenden Codebeispiele die Task.Factory.FromAsync-Methode, um TAP zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="62ce4-171">For example, the following code uses the Task.Factory.FromAsync method to implement TAP.</span></span>  
  
    ```csharp  
    public static async Task<IEnumerable<T>> ExecuteAsync<T>(this DataServiceQuery<T> query)  
    {  
        return await Task.Factory.FromAsync<IEnumerable<T>>(query.BeginExecute(null, null), query.EndExecute);  
    }  
    ```  
  
     <span data-ttu-id="62ce4-172">Wie in der Standardanwendung ist die Hauptseite der Anwendung GroupedItemsPage.</span><span class="sxs-lookup"><span data-stu-id="62ce4-172">As in the default application, the main page of the application is GroupedItemsPage.</span></span> <span data-ttu-id="62ce4-173">Hier werden jedoch die von Netflix abgerufenen Filme nach Genre gruppiert angezeigt.</span><span class="sxs-lookup"><span data-stu-id="62ce4-173">This time, however, it displays the movies retrieved from Netflix grouped by genre.</span></span>  <span data-ttu-id="62ce4-174">Wenn GroupedItemsPage instanziiert ist, wird die zugehörige LoadState-Methode aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="62ce4-174">When the GroupedItemsPage is instantiated, its LoadState method is called.</span></span> <span data-ttu-id="62ce4-175">LoadState bewirkt die Erstellung der statischen SampleDataSource-Instanz und ruft den Netflix-OData-Dienst wie oben beschrieben auf.</span><span class="sxs-lookup"><span data-stu-id="62ce4-175">LoadState causes the static SampleDataSource instance to be created, making a call to the Netflix OData service as discussed previously.</span></span> <span data-ttu-id="62ce4-176">LoadState speichert die Auflistung von Genres (SampleDataGroup-Objekte) in DefaultViewModel:</span><span class="sxs-lookup"><span data-stu-id="62ce4-176">LoadState stores the collection of genres (SampleDataGroup objects) in the DefaultViewModel:</span></span>  
  
    ```csharp  
    protected override void LoadState(Object navigationParameter, Dictionary<String, Object> pageState)  
    {  
  
        var sampleDataGroups = SampleDataSource.GetGroups((String)navigationParameter);  
        this.DefaultViewModel["Groups"] = sampleDataGroups;  
    }  
    ```  
  
     <span data-ttu-id="62ce4-177">Wie oben beschrieben, wird dann das DefaultViewModel verwendet, um die Daten an die GridView zu binden.</span><span class="sxs-lookup"><span data-stu-id="62ce4-177">As described previously, the DefaultViewModel is then used to bind the data to the GridView.</span></span>  
  
#### <a name="add-a-search-contract-to-allow-the-application-to-participate-in-windows-search"></a><span data-ttu-id="62ce4-178">Hinzufügen eines Suchvertrags, damit die Anwendung an der Windows-Suche teilnehmen kann</span><span class="sxs-lookup"><span data-stu-id="62ce4-178">Add a search contract to allow the application to participate in Windows search</span></span>  
  
1.  <span data-ttu-id="62ce4-179">Fügen Sie der Anwendung einen Suchvertrag hinzu.</span><span class="sxs-lookup"><span data-stu-id="62ce4-179">Add a search contract to the application.</span></span> <span data-ttu-id="62ce4-180">Dies ermöglicht der Anwendung die Integration mit den Windows 8-Suchfunktionen.</span><span class="sxs-lookup"><span data-stu-id="62ce4-180">This allows the application to integrate with the Windows 8 search experience.</span></span> <span data-ttu-id="62ce4-181">Geben Sie dem Suchvertrag den Namen SearchResultsPage.xaml.</span><span class="sxs-lookup"><span data-stu-id="62ce4-181">Name the search contract SearchResultsPage.xaml</span></span>  
  
     <span data-ttu-id="62ce4-182">![Hinzufügen eines suchvertrags](../../../../docs/framework/data/wcf/media/addsearchcontract.png "AddSearchContract")</span><span class="sxs-lookup"><span data-stu-id="62ce4-182">![Add a search contract](../../../../docs/framework/data/wcf/media/addsearchcontract.png "AddSearchContract")</span></span>  
  
2.  <span data-ttu-id="62ce4-183">Ändern Sie Zeile 58 in SearchResultsPage.xaml.cs, indem Sie die eingebetteten Anführungszeichen um queryText entfernen.</span><span class="sxs-lookup"><span data-stu-id="62ce4-183">Modify line 58 of SearchResultsPage.xaml.cs by removing the embedded quotes around queryText.</span></span>  
  
    ```csharp  
    // Communicate results through the view model  
    this.DefaultViewModel["QueryText"] = queryText;  
    this.DefaultViewModel["Filters"] = filterList;  
    this.DefaultViewModel["ShowFilters"] = filterList.Count > 1;  
    ```  
  
3.  <span data-ttu-id="62ce4-184">Fügen Sie die beiden folgenden Codezeilen in Zeile 81 in SearchResultsPage.xaml.cs ein, um die Suchergebnisse abzurufen.</span><span class="sxs-lookup"><span data-stu-id="62ce4-184">Insert the following two lines of code at line 81 in SearchResultsPage.xaml.cs to retrieve the search results.</span></span>  
  
    ```csharp  
    // TODO: Respond to the change in active filter by setting this.DefaultViewModel["Results"]  
                    //       to a collection of items with bindable Image, Title, Subtitle, and Description properties  
                    var searchValue = (string)this.DefaultViewModel["QueryText"];  
                    this.DefaultViewModel["Results"] = new List<SampleDataItem>(SampleDataSource.Search(searchValue));  
    ```  
  
 <span data-ttu-id="62ce4-185">Wenn ein Benutzer die Windows-Suche aufruft, einen Suchbegriff eingibt und dann das Symbol der Netflix-Demo-App in der Suchleiste berührt, wird die LoadState-Methode von SearchResultsPage ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="62ce4-185">When a user invokes Windows search, types in a search term and then touches the Netflix Demo app icon in the search bar, the LoadState method of the SearchResultsPage is executed.</span></span> <span data-ttu-id="62ce4-186">Der an LoadState gesendete Navigationsparameter enthält den Abfragetext.</span><span class="sxs-lookup"><span data-stu-id="62ce4-186">The navigation parameter sent to LoadState contains the query text.</span></span> <span data-ttu-id="62ce4-187">Als Nächstes wird die Filter_SelectionChanged-Methode aufgerufen, die dann die Suchmethode für die SampleDataSource-Klasse aufruft.</span><span class="sxs-lookup"><span data-stu-id="62ce4-187">Next the Filter_SelectionChanged method is called which then calls the Search method on the SampleDataSource class.</span></span> <span data-ttu-id="62ce4-188">Die Ergebnisse werden zurückgegeben und auf der SearchResultsPage.xaml-Seite angezeigt.</span><span class="sxs-lookup"><span data-stu-id="62ce4-188">The results are returned and displayed in the SearchResultsPage.xaml page.</span></span>  
  
```csharp  
/// <summary>  
        /// Invoked when a filter is selected using the ComboBox in snapped view state.  
        /// </summary>  
        /// <param name="sender">The ComboBox instance.</param>  
        /// <param name="e">Event data describing how the selected filter was changed.</param>  
        void Filter_SelectionChanged(object sender, SelectionChangedEventArgs e)  
        {  
            // Determine what filter was selected  
            var selectedFilter = e.AddedItems.FirstOrDefault() as Filter;  
            if (selectedFilter != null)  
            {  
                // Mirror the results into the corresponding Filter object to allow the  
                // RadioButton representation used when not snapped to reflect the change  
                selectedFilter.Active = true;  
  
                // TODO: Respond to the change in active filter by setting this.DefaultViewModel["Results"]  
                //       to a collection of items with bindable Image, Title, Subtitle, and Description properties  
                var searchValue = (string)this.DefaultViewModel["QueryText"];  
                this.DefaultViewModel["Results"] = new List<SampleDataItem>(SampleDataSource.Search(searchValue));  
  
                // Ensure results are found  
                object results;  
                ICollection resultsCollection;  
                if (this.DefaultViewModel.TryGetValue("Results", out results) &&  
                    (resultsCollection = results as ICollection) != null &&  
                    resultsCollection.Count != 0)  
                {  
                    VisualStateManager.GoToState(this, "ResultsFound", true);  
                    return;  
                }  
            }  
  
            // Display informational text when there are no search results.  
            VisualStateManager.GoToState(this, "NoResultsFound", true);  
        }  
```  
  
 <span data-ttu-id="62ce4-189">Weitere Informationen zur Integration der Suche in einer Anwendung finden Sie unter [Suche: Integration in die Windows 8-Suchfunktionen](http://go.microsoft.com/fwlink/p/?LinkId=266650).</span><span class="sxs-lookup"><span data-stu-id="62ce4-189">For more information on integrating search into an application see, [Search: integrating into the Windows 8 search experience](http://go.microsoft.com/fwlink/p/?LinkId=266650).</span></span>  
  
## <a name="run-the-application"></a><span data-ttu-id="62ce4-190">Ausführen der Anwendung</span><span class="sxs-lookup"><span data-stu-id="62ce4-190">Run the application</span></span>  
 <span data-ttu-id="62ce4-191">Drücken Sie F5, um die Anwendung zu starten.</span><span class="sxs-lookup"><span data-stu-id="62ce4-191">Launch the application by pressing F5.</span></span> <span data-ttu-id="62ce4-192">Beachten Sie, dass es einige Sekunden dauert, bis die Bilder nach dem Anwendungsstart geladen sind.</span><span class="sxs-lookup"><span data-stu-id="62ce4-192">Note that it will take a few seconds to load the images upon application launch.</span></span> <span data-ttu-id="62ce4-193">Außerdem gibt der erste Suchversuch möglicherweise keine Ergebnisse zurück.</span><span class="sxs-lookup"><span data-stu-id="62ce4-193">Also, your first search attempt may not return any results.</span></span> <span data-ttu-id="62ce4-194">In einer realen Anwendung sollten beide Probleme behoben werden.</span><span class="sxs-lookup"><span data-stu-id="62ce4-194">In a real-world application, you would want to deal with both of these issues.</span></span>  
  
 <span data-ttu-id="62ce4-195">Die Anwendung ruft den Netflix-OData-Dienst auf, empfängt die Daten in den generierten OData-Clientklassen und überträgt diese Daten dann an die bindungsfähigen Datenklassen (SampleDataSource, SampleDataGroup und SampleDataItem).</span><span class="sxs-lookup"><span data-stu-id="62ce4-195">The application calls the Netflix OData service, receives the data in the generated OData client classes and then transfers that data to bindable data classes (SampleDataSource, SampleDataGroup, and SampleDataItem).</span></span> <span data-ttu-id="62ce4-196">Diese bindungsfähigen Klassen werden verwendet, um die Daten an die GridView zu binden.</span><span class="sxs-lookup"><span data-stu-id="62ce4-196">It uses these bindable classes to bind the data to the GridView.</span></span> <span data-ttu-id="62ce4-197">Wenn Sie nicht mit der Funktionsweise finden Sie unter Verwendung von XAML-Datenbindung vertraut sind [zum Gruppieren von Elementen in einer Liste oder Raster (Windows Store-apps mit C#-/ VB-/C++ und XAML)](http://msdn.microsoft.com/library/windows/apps/xaml/hh780627).</span><span class="sxs-lookup"><span data-stu-id="62ce4-197">If you are unfamiliar with how XAML databinding works see [How to group items in a list or grid (Windows Store apps using C#/VB/C++ and XAML)](http://msdn.microsoft.com/library/windows/apps/xaml/hh780627).</span></span>
