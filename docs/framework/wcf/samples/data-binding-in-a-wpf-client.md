---
title: Datenbindung in einem Windows Presentation Foundation-Client
ms.date: 03/30/2017
ms.assetid: bb8c8293-5973-4aef-9b07-afeff5d3293c
ms.openlocfilehash: fe7b1934fa2abfa8d2f812caca2363c1cc603d1a
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602608"
---
# <a name="data-binding-in-a-windows-presentation-foundation-client"></a><span data-ttu-id="6aa04-102">Datenbindung in einem Windows Presentation Foundation-Client</span><span class="sxs-lookup"><span data-stu-id="6aa04-102">Data Binding in a Windows Presentation Foundation Client</span></span>
<span data-ttu-id="6aa04-103">In diesem Beispiel wird die Verwendung der Datenbindung in einem Windows Presentation Foundation (WPF)-Client veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="6aa04-103">This sample demonstrates the use of data binding in a Windows Presentation Foundation (WPF) client.</span></span> <span data-ttu-id="6aa04-104">Das Beispiel verwendet einen Windows Communication Foundation (WCF)-Dienst, der nach dem Zufallsprinzip ein Array von Alben generiert, das an den Client zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="6aa04-104">The sample uses a Windows Communication Foundation (WCF) service that randomly generates an array of albums to return to the client.</span></span> <span data-ttu-id="6aa04-105">Jedes Album hat einen Namen, einen Preis und eine Liste von Albumtiteln.</span><span class="sxs-lookup"><span data-stu-id="6aa04-105">Each album has a name, a price, and a list of album tracks.</span></span> <span data-ttu-id="6aa04-106">Die Albumtitel haben einen Namen und eine Dauer.</span><span class="sxs-lookup"><span data-stu-id="6aa04-106">The album tracks have a name and duration.</span></span> <span data-ttu-id="6aa04-107">Die vom Dienst zurückgegebenen Informationen werden automatisch an die Benutzeroberfläche (UI) gebunden, die vom WPF-Client (Windows Presentation Foundation) bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="6aa04-107">The information that is returned by the service is automatically bound to the user interface (UI) provided by the Windows Presentation Foundation (WPF) client.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6aa04-108">Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="6aa04-108">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="6aa04-109">Durch die Datenbindung kann eine Datenquelle automatisch an eine Benutzeroberfläche gebunden werden.</span><span class="sxs-lookup"><span data-stu-id="6aa04-109">Data binding allows a data source to be automatically bound to a UI.</span></span> <span data-ttu-id="6aa04-110">Dadurch wird das Programmiermodell vereinfacht, da Sie nicht jedes Element der Benutzeroberfläche programmgesteuert mit den Daten aus einem Datenobjekt oder einem Array von Datenobjekten aktualisieren müssen.</span><span class="sxs-lookup"><span data-stu-id="6aa04-110">This simplifies the programming model because it does not require that you programmatically update each UI element with the data from a data object or an array of data objects.</span></span> <span data-ttu-id="6aa04-111">Sie können ein Objekt an ein Benutzeroberflächenelement oder ein Array an ein Steuerelement mit mehreren Eingaben binden, beispielsweise `ListBox`.</span><span class="sxs-lookup"><span data-stu-id="6aa04-111">You can bind an object to a single UI element or an array to a control that takes multiple inputs, such as a `ListBox`.</span></span> <span data-ttu-id="6aa04-112">Im folgenden Codebeispiel wird das Binden von Daten an den `DataContext` eines Benutzeroberflächenelements veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="6aa04-112">The following code shows how to bind data to the `DataContext` of a UI element.</span></span>  
  
```csharp  
// Event handler executed when call is complete  
void client_GetAlbumListCompleted(object sender, GetAlbumListCompletedEventArgs e)  
{  
    // This is on the UI thread, myPanel can be accessed directly  
    myPanel.DataContext = e.Result;
}  
```  
  
 <span data-ttu-id="6aa04-113">Im obigen Beispiel wird der `DataContext` für das `grid`-Layoutelement `myPanel` auf die von der `GetAlbumList`-Methode zurückgegebenen Daten festgelegt.</span><span class="sxs-lookup"><span data-stu-id="6aa04-113">In the previous sample, the `DataContext` for the `grid` layout element named `myPanel` is set to the data returned by the `GetAlbumList` method.</span></span> <span data-ttu-id="6aa04-114">Durch den `DataContext` können Elemente Informationen zu der für die Bindung verwendete Datenquelle sowie andere Merkmale der Bindung (beispielsweise den Pfad) von den übergeordneten Elementen erben.</span><span class="sxs-lookup"><span data-stu-id="6aa04-114">The `DataContext` allows elements to inherit information from their parent elements about the data source that is used for binding, as well as other characteristics of the binding such as the path.</span></span> <span data-ttu-id="6aa04-115">Die Codezeile muss jedes Mal ausgeführt werden, wenn die Daten auf dem Server aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="6aa04-115">The line of code must be executed every time the data on the server is updated.</span></span> <span data-ttu-id="6aa04-116">Sie wird beispielsweise ausgeführt, wenn das Fenster initialisiert wird und wenn ein neues Album hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="6aa04-116">For example, it is executed when the window is initialized and when a new album is added.</span></span>  
  
 <span data-ttu-id="6aa04-117">Im folgenden XAML-Beispielcode wird `ListBox` von `ItemsSource="{Binding }"` angegeben.</span><span class="sxs-lookup"><span data-stu-id="6aa04-117">In the following sample XAML code, the `ListBox` specifies `ItemsSource="{Binding }"`.</span></span>  
  
```xml  
<ListBox
          ItemTemplate="{StaticResource AlbumStyle}"  
          ItemsSource="{Binding }"
          IsSynchronizedWithCurrentItem="true" />  
```  
  
 <span data-ttu-id="6aa04-118">Dies gibt an, dass die an das Benutzeroberflächenelement der obersten Ebene gebundenen Daten auch an dieses Steuerelement gebunden werden (d.&#160;h. an das Array von Alben).</span><span class="sxs-lookup"><span data-stu-id="6aa04-118">This specifies that the data bound to the top-level UI element is also bound to this control (that is, the array of Albums).</span></span> <span data-ttu-id="6aa04-119">Außerdem gibt `ItemTemplate="{StaticResource AlbumStyle}"` die Datenvorlage an, die in `ListBox` für jedes Element verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="6aa04-119">In addition, `ItemTemplate="{StaticResource AlbumStyle}"` specifies the data template to be used for each item in the `ListBox`.</span></span> <span data-ttu-id="6aa04-120">Sie können auch Datenvorlagen definieren, um anzugeben, wie die Daten formatiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="6aa04-120">You can also define data templates to specify how the data should be formatted.</span></span> <span data-ttu-id="6aa04-121">Diese Datenvorlagen können für andere Benutzeroberflächenelemente in der Anwendung wiederverwendet werden. Der Vorteil liegt darin, dass die Datenvorlage an einem Ort definiert und verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="6aa04-121">These data templates can be reused for other UI elements in the application, the advantage is that the data template is defined and maintained in one place.</span></span>  
  
 <span data-ttu-id="6aa04-122">Die `AlbumStyle`-Datenvorlage definiert ein Raster mit zwei nebeneinanderliegenden `TextBlock`s.</span><span class="sxs-lookup"><span data-stu-id="6aa04-122">The `AlbumStyle` data template lays out a grid with two `TextBlock`s side by side.</span></span> <span data-ttu-id="6aa04-123">In einem wird der Name des Albums angegeben, im anderen die Anzahl der Titel auf dem Album.</span><span class="sxs-lookup"><span data-stu-id="6aa04-123">One specifies the name of the Album and the other the number of Tracks in the album.</span></span>  
  
```xaml  
<DataTemplate x:Key="AlbumStyle">  
    <Grid>  
        <Grid.ColumnDefinitions>  
            <ColumnDefinition Width="260" />  
            <ColumnDefinition Width="60" />  
        </Grid.ColumnDefinitions>  
        <TextBlock Grid.Column="0" TextContent="{Binding Path=Title}" />  
        <TextBlock Grid.Column="1" TextContent="{Binding Path=Tracks#.Count}" HorizontalAlignment="Right" />  
    </Grid>  
</DataTemplate>  
```  
  
 <span data-ttu-id="6aa04-124">Mit dem folgenden XAML-Code wird eine zweite `ListBox` erstellt.</span><span class="sxs-lookup"><span data-stu-id="6aa04-124">The following XAML code creates a second `ListBox`.</span></span>  
  
```xaml  
<ListBox Grid.Row="2"
            Grid.ColumnSpan="2"
            ItemTemplate="{StaticResource TrackStyle}"  
            ItemsSource="{Binding Path=Tracks}" />  
```  
  
 <span data-ttu-id="6aa04-125">Im Code wird ein Pfad für `ItemsSource` angegeben.</span><span class="sxs-lookup"><span data-stu-id="6aa04-125">The code specifies a path for the `ItemsSource`.</span></span> <span data-ttu-id="6aa04-126">Damit wird angegeben, dass die an dieses Steuerelement gebundenen Daten keine Daten der obersten Ebene, sondern eine Eigenschaft der Daten der obersten Ebene namens `Tracks` sind.</span><span class="sxs-lookup"><span data-stu-id="6aa04-126">This indicates that the data bound to this control is not the top-level data but a property of the top-level data named `Tracks`.</span></span> <span data-ttu-id="6aa04-127">Diese Eigenschaft stellt das Array der im Album enthaltenen Titel dar.</span><span class="sxs-lookup"><span data-stu-id="6aa04-127">This property represents the array of tracks contained within the album.</span></span> <span data-ttu-id="6aa04-128">Außerdem wird eine weitere `DataTemplate` namens `TrackStyle` angegeben.</span><span class="sxs-lookup"><span data-stu-id="6aa04-128">In addition, a different `DataTemplate` named `TrackStyle` is specified.</span></span> <span data-ttu-id="6aa04-129">Das Layout der `TrackStyle`-Vorlage entspricht weitgehend dem der `AlbumStyle`-Vorlage, die `TextBlock`s sind jedoch an andere Eigenschaften gebunden.</span><span class="sxs-lookup"><span data-stu-id="6aa04-129">The layout of the `TrackStyle` template is similar to that of the `AlbumStyle` template, but the `TextBlock`s are bound to different properties.</span></span> <span data-ttu-id="6aa04-130">Dies liegt daran, dass die beiden Vorlagen mit unterschiedlichen Datenobjekten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="6aa04-130">This is because the two templates are used with different data objects.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="6aa04-131">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="6aa04-131">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="6aa04-132">Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="6aa04-132">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="6aa04-133">Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](building-the-samples.md)aufgeführten Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="6aa04-133">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="6aa04-134">Um das Beispiel in einer Konfiguration mit einem einzigen Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="6aa04-134">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="6aa04-135">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="6aa04-135">The samples may already be installed on your machine.</span></span> <span data-ttu-id="6aa04-136">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="6aa04-136">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="6aa04-137">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und Beispiele herunterzuladen [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6aa04-137">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="6aa04-138">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="6aa04-138">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Scenario\DataBinding\WPFDataBinding`  
