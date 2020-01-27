---
title: App-Daten zwischenspeichern
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- walkthroughs [WPF], caching
- caching [.NET Framework]
- caching [WPF]
ms.assetid: dac2c9ce-042b-4d23-91eb-28f584415cef
ms.openlocfilehash: b7d999f94e2f2ae410a16e537d51c0f890def4e1
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76728059"
---
# <a name="walkthrough-caching-application-data-in-a-wpf-application"></a><span data-ttu-id="69d40-102">Exemplarische Vorgehensweise: Zwischenspeichern von Anwendungsdaten in einer WPF-Anwendung</span><span class="sxs-lookup"><span data-stu-id="69d40-102">Walkthrough: Caching Application Data in a WPF Application</span></span>
<span data-ttu-id="69d40-103">Das Zwischenspeichern ermöglicht es Ihnen, Daten für schnellen Zugriff im Arbeitsspeicher zu speichern.</span><span class="sxs-lookup"><span data-stu-id="69d40-103">Caching enables you to store data in memory for rapid access.</span></span> <span data-ttu-id="69d40-104">Wenn erneut auf die Daten zugegriffen wird, erhalten Anwendungen die Daten aus dem Zwischenspeicher, anstatt sie aus der Originalquelle abzurufen.</span><span class="sxs-lookup"><span data-stu-id="69d40-104">When the data is accessed again, applications can get the data from the cache instead of retrieving it from the original source.</span></span> <span data-ttu-id="69d40-105">Dies kann die Leistung und Skalierbarkeit verbessern.</span><span class="sxs-lookup"><span data-stu-id="69d40-105">This can improve performance and scalability.</span></span> <span data-ttu-id="69d40-106">Darüber hinaus macht das Zwischenspeichern Daten verfügbar, wenn die Datenquelle vorübergehend nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="69d40-106">In addition, caching makes data available when the data source is temporarily unavailable.</span></span>

 <span data-ttu-id="69d40-107">Der .NET Framework stellt Klassen bereit, die es Ihnen ermöglichen, das Caching in .NET Framework Anwendungen zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="69d40-107">The .NET Framework provides classes that enable you to use caching in .NET Framework applications.</span></span> <span data-ttu-id="69d40-108">Diese Klassen befinden sich im <xref:System.Runtime.Caching>-Namespace.</span><span class="sxs-lookup"><span data-stu-id="69d40-108">These classes are located in the <xref:System.Runtime.Caching> namespace.</span></span>

> [!NOTE]
> <span data-ttu-id="69d40-109">Der <xref:System.Runtime.Caching>-Namespace ist neu in .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="69d40-109">The <xref:System.Runtime.Caching> namespace is new in the .NET Framework 4.</span></span> <span data-ttu-id="69d40-110">Dieser Namespace macht das Zwischenspeichern für alle .NET Framework Anwendungen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="69d40-110">This namespace makes caching is available to all .NET Framework applications.</span></span> <span data-ttu-id="69d40-111">In früheren Versionen der .NET Framework war das Zwischenspeichern nur im <xref:System.Web>-Namespace verfügbar und erforderte daher eine Abhängigkeit von ASP.NET-Klassen.</span><span class="sxs-lookup"><span data-stu-id="69d40-111">In previous versions of the .NET Framework, caching was available only in the <xref:System.Web> namespace and therefore required a dependency on ASP.NET classes.</span></span>

 <span data-ttu-id="69d40-112">In dieser exemplarischen Vorgehensweise erfahren Sie, wie Sie die im .NET Framework verfügbare cachingrichtfunktion als Teil einer [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]-Anwendung verwenden.</span><span class="sxs-lookup"><span data-stu-id="69d40-112">This walkthrough shows you how to use the caching functionality that is available in the .NET Framework as part of a [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] application.</span></span> <span data-ttu-id="69d40-113">In der exemplarischen Vorgehensweise Zwischenspeichern Sie den Inhalt einer Textdatei.</span><span class="sxs-lookup"><span data-stu-id="69d40-113">In the walkthrough, you cache the contents of a text file.</span></span>

 <span data-ttu-id="69d40-114">In dieser exemplarischen Vorgehensweise werden u. a. die folgenden Aufgaben beschrieben:</span><span class="sxs-lookup"><span data-stu-id="69d40-114">Tasks illustrated in this walkthrough include the following:</span></span>

- <span data-ttu-id="69d40-115">Erstellen eines WPF-Anwendungs Projekts.</span><span class="sxs-lookup"><span data-stu-id="69d40-115">Creating a WPF application project.</span></span>

- <span data-ttu-id="69d40-116">Hinzufügen eines Verweises auf die .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="69d40-116">Adding a reference to the .NET Framework 4.</span></span>

- <span data-ttu-id="69d40-117">Initialisieren eines Caches.</span><span class="sxs-lookup"><span data-stu-id="69d40-117">Initializing a cache.</span></span>

- <span data-ttu-id="69d40-118">Hinzufügen eines Cache Eintrags, der den Inhalt einer Textdatei enthält.</span><span class="sxs-lookup"><span data-stu-id="69d40-118">Adding a cache entry that contains the contents of a text file.</span></span>

- <span data-ttu-id="69d40-119">Bereitstellen einer Entfernungs Richtlinie für den Cache Eintrag.</span><span class="sxs-lookup"><span data-stu-id="69d40-119">Providing an eviction policy for the cache entry.</span></span>

- <span data-ttu-id="69d40-120">Überwachen des Pfads der zwischengespeicherten Datei und Benachrichtigen der Cache Instanz über Änderungen am überwachten Element.</span><span class="sxs-lookup"><span data-stu-id="69d40-120">Monitoring the path of the cached file and notifying the cache instance about changes to the monitored item.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="69d40-121">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="69d40-121">Prerequisites</span></span>
 <span data-ttu-id="69d40-122">Für die Durchführung dieser exemplarischen Vorgehensweise benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="69d40-122">In order to complete this walkthrough, you will need:</span></span>

- <span data-ttu-id="69d40-123">Visual Studio 2010.</span><span class="sxs-lookup"><span data-stu-id="69d40-123">Visual Studio 2010.</span></span>

- <span data-ttu-id="69d40-124">Eine Textdatei, die eine kleine Menge an Text enthält.</span><span class="sxs-lookup"><span data-stu-id="69d40-124">A text file that contains a small amount of text.</span></span> <span data-ttu-id="69d40-125">(Der Inhalt der Textdatei wird in einem Meldungs Feld angezeigt.) Der in der exemplarischen Vorgehensweise dargestellte Code setzt voraus, dass Sie mit der folgenden Datei arbeiten:</span><span class="sxs-lookup"><span data-stu-id="69d40-125">(You will display the contents of the text file in a message box.) The code illustrated in the walkthrough assumes that you are working with the following file:</span></span>

     `c:\cache\cacheText.txt`

     <span data-ttu-id="69d40-126">Allerdings können Sie eine beliebige Textdatei verwenden und kleinere Änderungen am Code in dieser exemplarischen Vorgehensweise vornehmen.</span><span class="sxs-lookup"><span data-stu-id="69d40-126">However, you can use any text file and make small changes to the code in this walkthrough.</span></span>

## <a name="creating-a-wpf-application-project"></a><span data-ttu-id="69d40-127">Erstellen eines WPF-Anwendungs Projekts</span><span class="sxs-lookup"><span data-stu-id="69d40-127">Creating a WPF Application Project</span></span>
 <span data-ttu-id="69d40-128">Zunächst erstellen Sie ein WPF-Anwendungsprojekt.</span><span class="sxs-lookup"><span data-stu-id="69d40-128">You will start by creating a WPF application project.</span></span>

#### <a name="to-create-a-wpf-application"></a><span data-ttu-id="69d40-129">So erstellen Sie eine WPF-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="69d40-129">To create a WPF application</span></span>

1. <span data-ttu-id="69d40-130">Starten Sie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="69d40-130">Start Visual Studio.</span></span>

2. <span data-ttu-id="69d40-131">Klicken Sie im Menü **Datei** auf **neu**, und klicken Sie dann auf **Neues Projekt**.</span><span class="sxs-lookup"><span data-stu-id="69d40-131">In the **File** menu, click **New**, and then click **New Project**.</span></span>

     <span data-ttu-id="69d40-132">Das Dialogfeld **Neues Projekt** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="69d40-132">The **New Project** dialog box is displayed.</span></span>

3. <span data-ttu-id="69d40-133">Wählen Sie unter **installierte Vorlagen**die Programmiersprache aus, die Sie verwenden möchten (**Visual Basic** oder **Visual C#** ).</span><span class="sxs-lookup"><span data-stu-id="69d40-133">Under **Installed Templates**, select the programming language you want to use (**Visual Basic** or **Visual C#**).</span></span>

4. <span data-ttu-id="69d40-134">Wählen Sie im Dialogfeld **Neues Projekt** die Option **WPF-Anwendung**aus.</span><span class="sxs-lookup"><span data-stu-id="69d40-134">In the **New Project** dialog box, select **WPF Application**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="69d40-135">Wenn die **WPF-Anwendungs** Vorlage nicht angezeigt wird, stellen Sie sicher, dass Sie auf eine Version der .NET Framework abzielen, die WPF unterstützt.</span><span class="sxs-lookup"><span data-stu-id="69d40-135">If you do not see the **WPF Application** template, make sure that you are targeting a version of the .NET Framework that supports WPF.</span></span> <span data-ttu-id="69d40-136">Wählen Sie im Dialogfeld **Neues Projekt** in der Liste .NET Framework 4 aus.</span><span class="sxs-lookup"><span data-stu-id="69d40-136">In the **New Project** dialog box, select .NET Framework 4 from the list.</span></span>

5. <span data-ttu-id="69d40-137">Geben Sie im Textfeld **Name** einen Namen für das Projekt ein.</span><span class="sxs-lookup"><span data-stu-id="69d40-137">In the **Name** text box, enter a name for your project.</span></span> <span data-ttu-id="69d40-138">Sie können z. b. **wpfcaching**eingeben.</span><span class="sxs-lookup"><span data-stu-id="69d40-138">For example, you can enter **WPFCaching**.</span></span>

6. <span data-ttu-id="69d40-139">Aktivieren Sie das Kontrollkästchen **Verzeichnis für Projektmappe erstellen**.</span><span class="sxs-lookup"><span data-stu-id="69d40-139">Select the **Create directory for solution** check box.</span></span>

7. <span data-ttu-id="69d40-140">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="69d40-140">Click **OK**.</span></span>

     <span data-ttu-id="69d40-141">Der WPF-Designer wird in der **Entwurfs** Ansicht geöffnet und zeigt die Datei "MainWindow. XAML" an.</span><span class="sxs-lookup"><span data-stu-id="69d40-141">The WPF Designer opens in **Design** view and displays the MainWindow.xaml file.</span></span> <span data-ttu-id="69d40-142">Visual Studio erstellt den Ordner " **My Project** ", die Datei "Application. XAML" und die Datei "MainWindow. XAML".</span><span class="sxs-lookup"><span data-stu-id="69d40-142">Visual Studio creates the **My Project** folder, the Application.xaml file, and the MainWindow.xaml file.</span></span>

## <a name="targeting-the-net-framework-and-adding-a-reference-to-the-caching-assemblies"></a><span data-ttu-id="69d40-143">.NET Framework und Hinzufügen eines Verweises auf die cacheassemblys</span><span class="sxs-lookup"><span data-stu-id="69d40-143">Targeting the .NET Framework and Adding a Reference to the Caching Assemblies</span></span>
 <span data-ttu-id="69d40-144">Standardmäßig richten sich WPF-Anwendungen an das .NET Framework 4 Client Profile.</span><span class="sxs-lookup"><span data-stu-id="69d40-144">By default, WPF applications target the .NET Framework 4 Client Profile.</span></span> <span data-ttu-id="69d40-145">Um den <xref:System.Runtime.Caching>-Namespace in einer WPF-Anwendung zu verwenden, muss die Anwendung auf .NET Framework 4 (nicht auf das .NET Framework 4-Client Profil) abzielen und muss einen Verweis auf den-Namespace enthalten.</span><span class="sxs-lookup"><span data-stu-id="69d40-145">To use the <xref:System.Runtime.Caching> namespace in a WPF application, the application must target the .NET Framework 4 (not the .NET Framework 4 Client Profile) and must include a reference to the namespace.</span></span>

 <span data-ttu-id="69d40-146">Der nächste Schritt besteht daher darin, das .NET Framework Ziel zu ändern und einen Verweis auf den <xref:System.Runtime.Caching>-Namespace hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="69d40-146">Therefore, the next step is to change the .NET Framework target and add a reference to the <xref:System.Runtime.Caching> namespace.</span></span>

> [!NOTE]
> <span data-ttu-id="69d40-147">Die Vorgehensweise zum Ändern des .NET Framework Ziels unterscheidet sich in einem Visual Basic Projekt und in C# einem visuellen Projekt.</span><span class="sxs-lookup"><span data-stu-id="69d40-147">The procedure for changing the .NET Framework target is different in a Visual Basic project and in a Visual C# project.</span></span>

#### <a name="to-change-the-target-net-framework-in-visual-basic"></a><span data-ttu-id="69d40-148">So ändern Sie die Ziel .NET Framework in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="69d40-148">To change the target .NET Framework in Visual Basic</span></span>

1. <span data-ttu-id="69d40-149">Klicken Sie im Projektmappen- **Explorer**mit der rechten Maustaste auf den Projektnamen, und klicken Sie auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="69d40-149">In **Solutions Explorer**, right-click the project name, and then click **Properties**.</span></span>

     <span data-ttu-id="69d40-150">Das Fenster Eigenschaften für die Anwendung wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="69d40-150">The properties window for the application is displayed.</span></span>

2. <span data-ttu-id="69d40-151">Klicken Sie auf die Registerkarte **Kompilieren**.</span><span class="sxs-lookup"><span data-stu-id="69d40-151">Click the **Compile** tab.</span></span>

3. <span data-ttu-id="69d40-152">Klicken Sie am unteren Rand des Fensters auf **Erweiterte Kompilierungsoptionen...** .</span><span class="sxs-lookup"><span data-stu-id="69d40-152">At the bottom of the window, click **Advanced Compile Options…**.</span></span>

     <span data-ttu-id="69d40-153">Das Dialogfeld **Erweiterte Compilereinstellungen** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="69d40-153">The **Advanced Compiler Settings** dialog box is displayed.</span></span>

4. <span data-ttu-id="69d40-154">Wählen Sie in der Liste **Ziel Framework (alle Konfigurationen)** die Option .NET Framework 4 aus.</span><span class="sxs-lookup"><span data-stu-id="69d40-154">In the **Target framework (all configurations)** list, select .NET Framework 4.</span></span> <span data-ttu-id="69d40-155">(Wählen Sie nicht .NET Framework 4 Client Profil aus.)</span><span class="sxs-lookup"><span data-stu-id="69d40-155">(Do not select .NET Framework 4 Client Profile.)</span></span>

5. <span data-ttu-id="69d40-156">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="69d40-156">Click **OK**.</span></span>

     <span data-ttu-id="69d40-157">Das Dialogfeld **Änderung des Zielframeworks** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="69d40-157">The **Target Framework Change** dialog box is displayed.</span></span>

6. <span data-ttu-id="69d40-158">Klicken Sie im Dialogfeld **Ziel Framework-Änderung** auf **Ja**.</span><span class="sxs-lookup"><span data-stu-id="69d40-158">In the **Target Framework Change** dialog box, click **Yes**.</span></span>

     <span data-ttu-id="69d40-159">Das Projekt ist geschlossen und wird dann erneut geöffnet.</span><span class="sxs-lookup"><span data-stu-id="69d40-159">The project is closed and is then reopened.</span></span>

7. <span data-ttu-id="69d40-160">Fügen Sie einen Verweis auf die Cacheassembly hinzu, indem Sie die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="69d40-160">Add a reference to the caching assembly by following these steps:</span></span>

    1. <span data-ttu-id="69d40-161">Klicken Sie in **Projektmappen-Explorer**mit der rechten Maustaste auf den Namen des Projekts, und klicken Sie dann auf **Verweis hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="69d40-161">In **Solution Explorer**, right-click the name of the project and then click **Add Reference**.</span></span>

    2. <span data-ttu-id="69d40-162">Wählen Sie die Registerkarte **.net** , wählen Sie `System.Runtime.Caching`aus, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="69d40-162">Select the **.NET** tab, select `System.Runtime.Caching`, and then click **OK**.</span></span>

#### <a name="to-change-the-target-net-framework-in-a-visual-c-project"></a><span data-ttu-id="69d40-163">So ändern Sie die Ziel .NET Framework in einem C# visuellen Projekt</span><span class="sxs-lookup"><span data-stu-id="69d40-163">To change the target .NET Framework in a Visual C# project</span></span>

1. <span data-ttu-id="69d40-164">Klicken Sie in **Projektmappen-Explorer**mit der rechten Maustaste auf den Projektnamen, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="69d40-164">In **Solution Explorer**, right-click the project name and then click **Properties**.</span></span>

     <span data-ttu-id="69d40-165">Das Fenster Eigenschaften für die Anwendung wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="69d40-165">The properties window for the application is displayed.</span></span>

2. <span data-ttu-id="69d40-166">Klicken Sie auf die Registerkarte **Anwendung** .</span><span class="sxs-lookup"><span data-stu-id="69d40-166">Click the **Application** tab.</span></span>

3. <span data-ttu-id="69d40-167">Wählen Sie in der Liste **Ziel Framework** die Option .NET Framework 4 aus.</span><span class="sxs-lookup"><span data-stu-id="69d40-167">In the **Target framework** list, select .NET Framework 4.</span></span> <span data-ttu-id="69d40-168">(Wählen Sie nicht **.NET Framework 4 Client Profil**aus.)</span><span class="sxs-lookup"><span data-stu-id="69d40-168">(Do not select **.NET Framework 4 Client Profile**.)</span></span>

4. <span data-ttu-id="69d40-169">Fügen Sie einen Verweis auf die Cacheassembly hinzu, indem Sie die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="69d40-169">Add a reference to the caching assembly by following these steps:</span></span>

    1. <span data-ttu-id="69d40-170">Klicken Sie mit der rechten Maustaste auf den Ordner **Verweise** und dann auf **Verweis hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="69d40-170">Right-click the **References** folder and then click **Add Reference**.</span></span>

    2. <span data-ttu-id="69d40-171">Wählen Sie die Registerkarte **.net** , wählen Sie `System.Runtime.Caching`aus, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="69d40-171">Select the **.NET** tab, select `System.Runtime.Caching`, and then click **OK**.</span></span>

## <a name="adding-a-button-to-the-wpf-window"></a><span data-ttu-id="69d40-172">Hinzufügen einer Schaltfläche zum WPF-Fenster</span><span class="sxs-lookup"><span data-stu-id="69d40-172">Adding a Button to the WPF Window</span></span>
 <span data-ttu-id="69d40-173">Als Nächstes fügen Sie ein Schaltflächen-Steuerelement hinzu und erstellen einen Ereignishandler für das `Click`-Ereignis der Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="69d40-173">Next, you will add a button control and create an event handler for the button's `Click` event.</span></span> <span data-ttu-id="69d40-174">Später fügen Sie Code hinzu. Wenn Sie auf die Schaltfläche klicken, wird der Inhalt der Textdatei zwischengespeichert und angezeigt.</span><span class="sxs-lookup"><span data-stu-id="69d40-174">Later you will add code to so when you click the button, the contents of the text file are cached and displayed.</span></span>

#### <a name="to-add-a-button-control"></a><span data-ttu-id="69d40-175">Hinzufügen eines Schaltflächen-Steuer Elements</span><span class="sxs-lookup"><span data-stu-id="69d40-175">To add a button control</span></span>

1. <span data-ttu-id="69d40-176">Doppelklicken Sie in **Projektmappen-Explorer**auf die Datei "MainWindow. XAML", um Sie zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="69d40-176">In **Solution Explorer**, double-click the MainWindow.xaml file to open it.</span></span>

2. <span data-ttu-id="69d40-177">Ziehen Sie aus der **Toolbox**unter **Common WPF**-Steuerelemente ein `Button`-Steuerelement in das Fenster `MainWindow`.</span><span class="sxs-lookup"><span data-stu-id="69d40-177">From the **Toolbox**, under **Common WPF Controls**, drag a `Button` control to the `MainWindow` window.</span></span>

3. <span data-ttu-id="69d40-178">Legen Sie im Fenster **Eigenschaften** für die `Content`-Eigenschaft des `Button`-Steuer Elements den Wert **Get Cache**fest.</span><span class="sxs-lookup"><span data-stu-id="69d40-178">In the **Properties** window, set the `Content` property of the `Button` control to **Get Cache**.</span></span>

## <a name="initializing-the-cache-and-caching-an-entry"></a><span data-ttu-id="69d40-179">Initialisieren des Caches und Zwischenspeichern eines Eintrags</span><span class="sxs-lookup"><span data-stu-id="69d40-179">Initializing the Cache and Caching an Entry</span></span>
 <span data-ttu-id="69d40-180">Fügen Sie als nächstes den Code hinzu, um die folgenden Aufgaben auszuführen:</span><span class="sxs-lookup"><span data-stu-id="69d40-180">Next, you will add the code to perform the following tasks:</span></span>

- <span data-ttu-id="69d40-181">Erstellen Sie eine Instanz der Cache-Klasse, d. –., Sie instanziieren Sie ein neues <xref:System.Runtime.Caching.MemoryCache>-Objekt.</span><span class="sxs-lookup"><span data-stu-id="69d40-181">Create an instance of the cache class—that is, you will instantiate a new <xref:System.Runtime.Caching.MemoryCache> object.</span></span>

- <span data-ttu-id="69d40-182">Legen Sie fest, dass der Cache ein <xref:System.Runtime.Caching.HostFileChangeMonitor> Objekt verwendet, um Änderungen in der Textdatei zu überwachen.</span><span class="sxs-lookup"><span data-stu-id="69d40-182">Specify that the cache uses a <xref:System.Runtime.Caching.HostFileChangeMonitor> object to monitor changes in the text file.</span></span>

- <span data-ttu-id="69d40-183">Lesen Sie die Textdatei, und speichern Sie Ihren Inhalt als Cache Eintrag.</span><span class="sxs-lookup"><span data-stu-id="69d40-183">Read the text file and cache its contents as a cache entry.</span></span>

- <span data-ttu-id="69d40-184">Zeigen Sie den Inhalt der zwischengespeicherten Textdatei an.</span><span class="sxs-lookup"><span data-stu-id="69d40-184">Display the contents of the cached text file.</span></span>

#### <a name="to-create-the-cache-object"></a><span data-ttu-id="69d40-185">So erstellen Sie das Cache Objekt</span><span class="sxs-lookup"><span data-stu-id="69d40-185">To create the cache object</span></span>

1. <span data-ttu-id="69d40-186">Doppelklicken Sie auf die Schaltfläche, die Sie soeben hinzugefügt haben, um einen Ereignishandler in der MainWindow.XAML.cs-oder MainWindow. XAML. vb-Datei zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="69d40-186">Double-click the button you just added in order to create an event handler in the MainWindow.xaml.cs or MainWindow.Xaml.vb file.</span></span>

2. <span data-ttu-id="69d40-187">Fügen Sie am Anfang der Datei (vor der Klassen Deklaration) die folgenden `Imports` (Visual Basic)-oder `using` (C#)-Anweisung hinzu:</span><span class="sxs-lookup"><span data-stu-id="69d40-187">At the top of the file (before the class declaration), add the following `Imports` (Visual Basic) or `using` (C#) statements:</span></span>

    ```csharp
    using System.Runtime.Caching;
    using System.IO;
    ```

    ```vb
    Imports System.Runtime.Caching
    Imports System.IO
    ```

3. <span data-ttu-id="69d40-188">Fügen Sie im-Ereignishandler den folgenden Code hinzu, um das Cache Objekt zu instanziieren:</span><span class="sxs-lookup"><span data-stu-id="69d40-188">In the event handler, add the following code to instantiate the cache object:</span></span>

    ```csharp
    ObjectCache cache = MemoryCache.Default;
    ```

    ```vb
    Dim cache As ObjectCache = MemoryCache.Default
    ```

     <span data-ttu-id="69d40-189">Die <xref:System.Runtime.Caching.ObjectCache>-Klasse ist eine integrierte Klasse, die einen in-Memory-Objekt Cache bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="69d40-189">The <xref:System.Runtime.Caching.ObjectCache> class is a built-in class that provides an in-memory object cache.</span></span>

4. <span data-ttu-id="69d40-190">Fügen Sie den folgenden Code hinzu, um den Inhalt eines Cache Eintrags namens `filecontents`zu lesen:</span><span class="sxs-lookup"><span data-stu-id="69d40-190">Add the following code to read the contents of a cache entry named `filecontents`:</span></span>

    ```vb
    Dim fileContents As String = TryCast(cache("filecontents"), String)
    ```

    ```csharp
    string fileContents = cache["filecontents"] as string;
    ```

5. <span data-ttu-id="69d40-191">Fügen Sie folgenden Code hinzu, um zu überprüfen, ob der Cache Eintrag namens `filecontents` vorhanden ist:</span><span class="sxs-lookup"><span data-stu-id="69d40-191">Add the following code to check whether the cache entry named `filecontents` exists:</span></span>

    ```vb
    If fileContents Is Nothing Then

    End If
    ```

    ```csharp
    if (fileContents == null)
    {

    }
    ```

     <span data-ttu-id="69d40-192">Wenn der angegebene Cache Eintrag nicht vorhanden ist, müssen Sie die Textdatei lesen und als Cache Eintrag dem Cache hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="69d40-192">If the specified cache entry does not exist, you must read the text file and add it as a cache entry to the cache.</span></span>

6. <span data-ttu-id="69d40-193">Fügen Sie im `if/then`-Block den folgenden Code hinzu, um ein neues <xref:System.Runtime.Caching.CacheItemPolicy>-Objekt zu erstellen, das angibt, dass der Cache Eintrag nach 10 Sekunden abläuft.</span><span class="sxs-lookup"><span data-stu-id="69d40-193">In the `if/then` block, add the following code to create a new <xref:System.Runtime.Caching.CacheItemPolicy> object that specifies that the cache entry expires after 10 seconds.</span></span>

    ```vb
    Dim policy As New CacheItemPolicy()
    policy.AbsoluteExpiration = DateTimeOffset.Now.AddSeconds(10.0)
    ```

    ```csharp
    CacheItemPolicy policy = new CacheItemPolicy();
    policy.AbsoluteExpiration = DateTimeOffset.Now.AddSeconds(10.0);
    ```

     <span data-ttu-id="69d40-194">Wenn keine Entfernungs-oder Ablauf Informationen bereitgestellt werden, wird der Standardwert <xref:System.Runtime.Caching.ObjectCache.InfiniteAbsoluteExpiration>. Dies bedeutet, dass die Cache Einträge nie auf der Grundlage eines absoluten Zeitraums ablaufen.</span><span class="sxs-lookup"><span data-stu-id="69d40-194">If no eviction or expiration information is provided, the default is <xref:System.Runtime.Caching.ObjectCache.InfiniteAbsoluteExpiration>, which means the cache entries never expire based only on an absolute time.</span></span> <span data-ttu-id="69d40-195">Stattdessen laufen Cache Einträge nur dann ab, wenn genügend Arbeitsspeicher vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="69d40-195">Instead, cache entries expire only when there is memory pressure.</span></span> <span data-ttu-id="69d40-196">Als bewährte Vorgehensweise sollten Sie immer explizit einen absoluten oder einen gleitenden Ablauf angeben.</span><span class="sxs-lookup"><span data-stu-id="69d40-196">As a best practice, you should always explicitly provide either an absolute or a sliding expiration.</span></span>

7. <span data-ttu-id="69d40-197">Fügen Sie im `if/then` Block und befolgen Sie den Code, den Sie im vorherigen Schritt hinzugefügt haben, um eine Sammlung für die Dateipfade zu erstellen, die Sie überwachen möchten, und um den Pfad der Textdatei der Auflistung hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="69d40-197">Inside the `if/then` block and following the code you added in the previous step, add the following code to create a collection for the file paths that you want to monitor, and to add the path of the text file to the collection:</span></span>

    ```vb
    Dim filePaths As New List(Of String)()
    filePaths.Add("c:\cache\cacheText.txt")
    ```

    ```csharp
    List<string> filePaths = new List<string>();
    filePaths.Add("c:\\cache\\cacheText.txt");
    ```

    > [!NOTE]
    > <span data-ttu-id="69d40-198">Wenn die zu verwendende Textdatei nicht `c:\cache\cacheText.txt`ist, geben Sie den Pfad an, in dem die Textdatei verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="69d40-198">If the text file you want to use is not `c:\cache\cacheText.txt`, specify the path where the text file is that you want to use.</span></span>

8. <span data-ttu-id="69d40-199">Fügen Sie nach dem Code, den Sie im vorherigen Schritt hinzugefügt haben, den folgenden Code hinzu, um der Sammlung von Änderungs Monitoren für den Cache Eintrag ein neues <xref:System.Runtime.Caching.HostFileChangeMonitor> Objekt hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="69d40-199">Following the code that you added in the previous step, add the following code to add a new <xref:System.Runtime.Caching.HostFileChangeMonitor> object to the collection of change monitors for the cache entry:</span></span>

    ```vb
    policy.ChangeMonitors.Add(New HostFileChangeMonitor(filePaths))
    ```

    ```csharp
    policy.ChangeMonitors.Add(new HostFileChangeMonitor(filePaths));
    ```

     <span data-ttu-id="69d40-200">Das <xref:System.Runtime.Caching.HostFileChangeMonitor>-Objekt überwacht den Pfad der Textdatei und benachrichtigt den Cache, wenn Änderungen auftreten.</span><span class="sxs-lookup"><span data-stu-id="69d40-200">The <xref:System.Runtime.Caching.HostFileChangeMonitor> object monitors the text file's path and notifies the cache if changes occur.</span></span> <span data-ttu-id="69d40-201">In diesem Beispiel läuft der Cache Eintrag ab, wenn sich der Inhalt der Datei ändert.</span><span class="sxs-lookup"><span data-stu-id="69d40-201">In this example, the cache entry will expire if the content of the file changes.</span></span>

9. <span data-ttu-id="69d40-202">Fügen Sie nach dem Code, den Sie im vorherigen Schritt hinzugefügt haben, den folgenden Code hinzu, um den Inhalt der Textdatei zu lesen:</span><span class="sxs-lookup"><span data-stu-id="69d40-202">Following the code that you added in the previous step, add the following code to read the contents of the text file:</span></span>

    ```vb
    fileContents = File.ReadAllText("c:\cache\cacheText.txt") & vbCrLf & DateTime.Now.ToString()
    ```

    ```csharp
    fileContents = File.ReadAllText("c:\\cache\\cacheText.txt") + "\n" + DateTime.Now;
    ```

     <span data-ttu-id="69d40-203">Der Zeitstempel für Datum und Uhrzeit wird hinzugefügt, damit Sie sehen können, wann der Cache Eintrag abläuft.</span><span class="sxs-lookup"><span data-stu-id="69d40-203">The date and time timestamp is added so that you will be able to see when the cache entry expires.</span></span>

10. <span data-ttu-id="69d40-204">Fügen Sie nach dem Code, den Sie im vorherigen Schritt hinzugefügt haben, den folgenden Code hinzu, um den Inhalt der Datei in das Cache Objekt als <xref:System.Runtime.Caching.CacheItem> Instanz einzufügen:</span><span class="sxs-lookup"><span data-stu-id="69d40-204">Following the code that you added in the previous step, add the following code to insert the contents of the file into the cache object as a <xref:System.Runtime.Caching.CacheItem> instance:</span></span>

    ```vb
    cache.Set("filecontents", fileContents, policy)
    ```

    ```csharp
    cache.Set("filecontents", fileContents, policy);
    ```

     <span data-ttu-id="69d40-205">Sie geben Informationen darüber an, wie der Cache Eintrag entfernt werden soll, indem Sie das <xref:System.Runtime.Caching.CacheItemPolicy> Objekt, das Sie zuvor erstellt haben, als Parameter übergeben.</span><span class="sxs-lookup"><span data-stu-id="69d40-205">You specify information about how the cache entry should be evicted by passing the <xref:System.Runtime.Caching.CacheItemPolicy> object that you created earlier as a parameter.</span></span>

11. <span data-ttu-id="69d40-206">Fügen Sie nach dem `if/then`-Block den folgenden Code hinzu, um den zwischengespeicherten Dateiinhalt in einem Meldungs Feld anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="69d40-206">After the `if/then` block, add the following code to display the cached file content in a message box:</span></span>

    ```vb
    MessageBox.Show(fileContents)
    ```

    ```csharp
    MessageBox.Show(fileContents);
    ```

12. <span data-ttu-id="69d40-207">Klicken Sie im Menü **Erstellen** auf **wpfcaching erstellen** , um das Projekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="69d40-207">In the **Build** menu, click **Build WPFCaching** to build your project.</span></span>

## <a name="testing-caching-in-the-wpf-application"></a><span data-ttu-id="69d40-208">Testen der Zwischenspeicherung in der WPF-Anwendung</span><span class="sxs-lookup"><span data-stu-id="69d40-208">Testing Caching in the WPF Application</span></span>
 <span data-ttu-id="69d40-209">Die Anwendung kann nun getestet werden.</span><span class="sxs-lookup"><span data-stu-id="69d40-209">You can now test the application.</span></span>

#### <a name="to-test-caching-in-the-wpf-application"></a><span data-ttu-id="69d40-210">So testen Sie die Zwischenspeicherung in der WPF-Anwendung</span><span class="sxs-lookup"><span data-stu-id="69d40-210">To test caching in the WPF application</span></span>

1. <span data-ttu-id="69d40-211">Drücken Sie STRG+F5, um die Anwendung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="69d40-211">Press CTRL+F5 to run the application.</span></span>

     <span data-ttu-id="69d40-212">Das Fenster `MainWindow` wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="69d40-212">The `MainWindow` window is displayed.</span></span>

2. <span data-ttu-id="69d40-213">Klicken Sie auf **Cache erhalten**.</span><span class="sxs-lookup"><span data-stu-id="69d40-213">Click **Get Cache**.</span></span>

     <span data-ttu-id="69d40-214">Der zwischengespeicherte Inhalt aus der Textdatei wird in einem Meldungs Feld angezeigt.</span><span class="sxs-lookup"><span data-stu-id="69d40-214">The cached content from the text file is displayed in a message box.</span></span> <span data-ttu-id="69d40-215">Beachten Sie den Zeitstempel der Datei.</span><span class="sxs-lookup"><span data-stu-id="69d40-215">Notice the timestamp on the file.</span></span>

3. <span data-ttu-id="69d40-216">Schließen Sie das Meldungs Feld, und klicken Sie dann erneut auf **Cache erhalten** .</span><span class="sxs-lookup"><span data-stu-id="69d40-216">Close the message box and then click **Get Cache** again.</span></span>

     <span data-ttu-id="69d40-217">Der Zeitstempel ist unverändert.</span><span class="sxs-lookup"><span data-stu-id="69d40-217">The timestamp is unchanged.</span></span> <span data-ttu-id="69d40-218">Dies gibt an, dass der zwischengespeicherte Inhalt angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="69d40-218">This indicates the cached content is displayed.</span></span>

4. <span data-ttu-id="69d40-219">Warten Sie 10 Sekunden oder mehr, und klicken Sie dann erneut auf **Cache erhalten** .</span><span class="sxs-lookup"><span data-stu-id="69d40-219">Wait 10 seconds or more and then click **Get Cache** again.</span></span>

     <span data-ttu-id="69d40-220">Dieses Mal wird ein neuer Zeitstempel angezeigt.</span><span class="sxs-lookup"><span data-stu-id="69d40-220">This time a new timestamp is displayed.</span></span> <span data-ttu-id="69d40-221">Dies gibt an, dass die Richtlinie den Cache Eintrag ablaufen lässt und dass neuer zwischen gespeicherter Inhalt angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="69d40-221">This indicates that the policy let the cache entry expire and that new cached content is displayed.</span></span>

5. <span data-ttu-id="69d40-222">Öffnen Sie in einem Text-Editor die Textdatei, die Sie erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="69d40-222">In a text editor, open the text file that you created.</span></span> <span data-ttu-id="69d40-223">Nehmen Sie noch keine Änderungen vor.</span><span class="sxs-lookup"><span data-stu-id="69d40-223">Do not make any changes yet.</span></span>

6. <span data-ttu-id="69d40-224">Schließen Sie das Meldungs Feld, und klicken Sie dann erneut auf **Cache erhalten** .</span><span class="sxs-lookup"><span data-stu-id="69d40-224">Close the message box and then click **Get Cache** again.</span></span>

     <span data-ttu-id="69d40-225">Beachten Sie den Zeitstempel.</span><span class="sxs-lookup"><span data-stu-id="69d40-225">Notice the timestamp again.</span></span>

7. <span data-ttu-id="69d40-226">Nehmen Sie eine Änderung an der Textdatei vor, und speichern Sie die Datei.</span><span class="sxs-lookup"><span data-stu-id="69d40-226">Make a change to the text file and then save the file.</span></span>

8. <span data-ttu-id="69d40-227">Schließen Sie das Meldungs Feld, und klicken Sie dann erneut auf **Cache erhalten** .</span><span class="sxs-lookup"><span data-stu-id="69d40-227">Close the message box and then click **Get Cache** again.</span></span>

     <span data-ttu-id="69d40-228">Dieses Meldungs Feld enthält den aktualisierten Inhalt aus der Textdatei und einen neuen Zeitstempel.</span><span class="sxs-lookup"><span data-stu-id="69d40-228">This message box contains the updated content from the text file and a new timestamp.</span></span> <span data-ttu-id="69d40-229">Dadurch wird angegeben, dass der Cache Eintrag vom Host Datei-Änderungs Monitor sofort entfernt wurde, als Sie die Datei geändert haben, obwohl der absolute Timeout Zeitraum nicht abgelaufen war.</span><span class="sxs-lookup"><span data-stu-id="69d40-229">This indicates that the host-file change monitor evicted the cache entry immediately when you changed the file, even though the absolute timeout period had not expired.</span></span>

    > [!NOTE]
    > <span data-ttu-id="69d40-230">Sie können die Entfernungs Zeit auf 20 Sekunden oder mehr erhöhen, damit Sie mehr Zeit für eine Änderung in der Datei haben.</span><span class="sxs-lookup"><span data-stu-id="69d40-230">You can increase the eviction time to 20 seconds or more to allow more time for you to make a change in the file.</span></span>

## <a name="code-example"></a><span data-ttu-id="69d40-231">Codebeispiel</span><span class="sxs-lookup"><span data-stu-id="69d40-231">Code Example</span></span>
 <span data-ttu-id="69d40-232">Nachdem Sie diese exemplarische Vorgehensweise abgeschlossen haben, ähnelt der Code für das Projekt, das Sie erstellt haben, dem folgenden Beispiel.</span><span class="sxs-lookup"><span data-stu-id="69d40-232">After you have completed this walkthrough, the code for the project you created will resemble the following example.</span></span>

 [!code-csharp[CachingWPFApplications#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CachingWPFApplications/CSharp/MainWindow.xaml.cs#1)]
 [!code-vb[CachingWPFApplications#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CachingWPFApplications/VisualBasic/MainWindow.xaml.vb#1)]

## <a name="see-also"></a><span data-ttu-id="69d40-233">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="69d40-233">See also</span></span>

- <xref:System.Runtime.Caching.MemoryCache>
- <xref:System.Runtime.Caching.ObjectCache>
- <xref:System.Runtime.Caching>
- [<span data-ttu-id="69d40-234">Caching in .NET Framework Applications (Caching in .NET Framework-Anwendungen)</span><span class="sxs-lookup"><span data-stu-id="69d40-234">Caching in .NET Framework Applications</span></span>](../../performance/caching-in-net-framework-applications.md)
