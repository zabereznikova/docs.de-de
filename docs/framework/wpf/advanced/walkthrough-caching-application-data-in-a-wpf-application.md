---
title: 'Exemplarische Vorgehensweise: Zwischenspeichern von Anwendungsdaten in einer WPF-Anwendung'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- walkthroughs [WPF], caching
- caching [.NET Framework]
- caching [WPF]
ms.assetid: dac2c9ce-042b-4d23-91eb-28f584415cef
ms.openlocfilehash: 1d00c222dabf446c7c102307c3b904d3f1ff4bca
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62007278"
---
# <a name="walkthrough-caching-application-data-in-a-wpf-application"></a><span data-ttu-id="b3a7d-102">Exemplarische Vorgehensweise: Zwischenspeichern von Anwendungsdaten in einer WPF-Anwendung</span><span class="sxs-lookup"><span data-stu-id="b3a7d-102">Walkthrough: Caching Application Data in a WPF Application</span></span>
<span data-ttu-id="b3a7d-103">Das Zwischenspeichern ermöglicht es Ihnen, Daten für schnellen Zugriff im Arbeitsspeicher zu speichern.</span><span class="sxs-lookup"><span data-stu-id="b3a7d-103">Caching enables you to store data in memory for rapid access.</span></span> <span data-ttu-id="b3a7d-104">Wenn erneut auf die Daten zugegriffen wird, erhalten Anwendungen die Daten aus dem Zwischenspeicher, anstatt sie aus der Originalquelle abzurufen.</span><span class="sxs-lookup"><span data-stu-id="b3a7d-104">When the data is accessed again, applications can get the data from the cache instead of retrieving it from the original source.</span></span> <span data-ttu-id="b3a7d-105">Dies kann die Leistung und Skalierbarkeit verbessern.</span><span class="sxs-lookup"><span data-stu-id="b3a7d-105">This can improve performance and scalability.</span></span> <span data-ttu-id="b3a7d-106">Darüber hinaus macht das Zwischenspeichern Daten verfügbar, wenn die Datenquelle vorübergehend nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="b3a7d-106">In addition, caching makes data available when the data source is temporarily unavailable.</span></span>

 <span data-ttu-id="b3a7d-107">Die [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] bietet Klassen, die Ihnen ermöglichen, verwenden der Zwischenspeicherung in [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="b3a7d-107">The [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] provides classes that enable you to use caching in [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] applications.</span></span> <span data-ttu-id="b3a7d-108">Diese Klassen befinden sich in der <xref:System.Runtime.Caching> Namespace.</span><span class="sxs-lookup"><span data-stu-id="b3a7d-108">These classes are located in the <xref:System.Runtime.Caching> namespace.</span></span>

> [!NOTE]
>  <span data-ttu-id="b3a7d-109">Die <xref:System.Runtime.Caching> Namespace ist neu in der [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b3a7d-109">The <xref:System.Runtime.Caching> namespace is new in the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span> <span data-ttu-id="b3a7d-110">Dieser Namespace stellt Zwischenspeichern steht allen [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="b3a7d-110">This namespace makes caching is available to all [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] applications.</span></span> <span data-ttu-id="b3a7d-111">In früheren [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]-Versionen war die Zwischenspeicherung nur im <xref:System.Web>-Namespace verfügbar, und erforderte daher eine Abhängigkeit der ASP.NET-Klassen.</span><span class="sxs-lookup"><span data-stu-id="b3a7d-111">In previous versions of the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], caching was available only in the <xref:System.Web> namespace and therefore required a dependency on ASP.NET classes.</span></span>

 <span data-ttu-id="b3a7d-112">In dieser exemplarischen Vorgehensweise erfahren Sie, wie Sie die Funktionen zum Zwischenspeichern verwenden, verfügbar in der [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] als Teil einer [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Anwendung.</span><span class="sxs-lookup"><span data-stu-id="b3a7d-112">This walkthrough shows you how to use the caching functionality that is available in the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] as part of a [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] application.</span></span> <span data-ttu-id="b3a7d-113">In der exemplarischen Vorgehensweise Zwischenspeichern Sie den Inhalt einer Textdatei.</span><span class="sxs-lookup"><span data-stu-id="b3a7d-113">In the walkthrough, you cache the contents of a text file.</span></span>

 <span data-ttu-id="b3a7d-114">In dieser exemplarischen Vorgehensweise werden u. a. die folgenden Aufgaben beschrieben:</span><span class="sxs-lookup"><span data-stu-id="b3a7d-114">Tasks illustrated in this walkthrough include the following:</span></span>

- <span data-ttu-id="b3a7d-115">Erstellen ein WPF-Anwendungsprojekt.</span><span class="sxs-lookup"><span data-stu-id="b3a7d-115">Creating a WPF application project.</span></span>

- <span data-ttu-id="b3a7d-116">Hinzufügen eines Verweises auf die [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b3a7d-116">Adding a reference to the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span>

- <span data-ttu-id="b3a7d-117">Initialisieren einen Cache.</span><span class="sxs-lookup"><span data-stu-id="b3a7d-117">Initializing a cache.</span></span>

- <span data-ttu-id="b3a7d-118">Hinzufügen eines Eintrags mit dem Inhalt einer Textdatei.</span><span class="sxs-lookup"><span data-stu-id="b3a7d-118">Adding a cache entry that contains the contents of a text file.</span></span>

- <span data-ttu-id="b3a7d-119">Bereitstellen von eine Entfernungsrichtlinie für den Cacheeintrag.</span><span class="sxs-lookup"><span data-stu-id="b3a7d-119">Providing an eviction policy for the cache entry.</span></span>

- <span data-ttu-id="b3a7d-120">Überwachen den Pfad, der die zwischengespeicherte Datei und die Cache-Instanz zu benachrichtigen, die in der Überwachungskapazität für Elemente geändert werden.</span><span class="sxs-lookup"><span data-stu-id="b3a7d-120">Monitoring the path of the cached file and notifying the cache instance about changes to the monitored item.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b3a7d-121">Vorraussetzungen</span><span class="sxs-lookup"><span data-stu-id="b3a7d-121">Prerequisites</span></span>
 <span data-ttu-id="b3a7d-122">Für die Durchführung dieser exemplarischen Vorgehensweise benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="b3a7d-122">In order to complete this walkthrough, you will need:</span></span>

- <span data-ttu-id="b3a7d-123">Microsoft Visual Studio 2010</span><span class="sxs-lookup"><span data-stu-id="b3a7d-123">Microsoft Visual Studio 2010.</span></span>

- <span data-ttu-id="b3a7d-124">Eine Textdatei, die eine kleine Menge an Text enthält.</span><span class="sxs-lookup"><span data-stu-id="b3a7d-124">A text file that contains a small amount of text.</span></span> <span data-ttu-id="b3a7d-125">(Sie werden der Inhalt der Textdatei in einem Meldungsfeld angezeigt.) Der Code in der exemplarischen Vorgehensweise wird davon ausgegangen, dass Sie mit der folgenden Datei arbeiten:</span><span class="sxs-lookup"><span data-stu-id="b3a7d-125">(You will display the contents of the text file in a message box.) The code illustrated in the walkthrough assumes that you are working with the following file:</span></span>

     `c:\cache\cacheText.txt`

     <span data-ttu-id="b3a7d-126">Allerdings können Sie eine Textdatei verwenden und kleine Änderungen vornehmen, um den Code in dieser exemplarischen Vorgehensweise.</span><span class="sxs-lookup"><span data-stu-id="b3a7d-126">However, you can use any text file and make small changes to the code in this walkthrough.</span></span>

## <a name="creating-a-wpf-application-project"></a><span data-ttu-id="b3a7d-127">Erstellen eines WPF-Anwendungsprojekts</span><span class="sxs-lookup"><span data-stu-id="b3a7d-127">Creating a WPF Application Project</span></span>
 <span data-ttu-id="b3a7d-128">Sie zunächst erstellen ein WPF-Anwendungsprojekt.</span><span class="sxs-lookup"><span data-stu-id="b3a7d-128">You will start by creating a WPF application project.</span></span>

#### <a name="to-create-a-wpf-application"></a><span data-ttu-id="b3a7d-129">So erstellen Sie eine WPF-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="b3a7d-129">To create a WPF application</span></span>

1. <span data-ttu-id="b3a7d-130">Starten Sie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b3a7d-130">Start Visual Studio.</span></span>

2. <span data-ttu-id="b3a7d-131">In der **Datei** Menü klicken Sie auf **neu**, und klicken Sie dann auf **neues Projekt**.</span><span class="sxs-lookup"><span data-stu-id="b3a7d-131">In the **File** menu, click **New**, and then click **New Project**.</span></span>

     <span data-ttu-id="b3a7d-132">Das Dialogfeld **Neues Projekt** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b3a7d-132">The **New Project** dialog box is displayed.</span></span>

3. <span data-ttu-id="b3a7d-133">Klicken Sie unter **installierte Vorlagen**, wählen Sie die Programmiersprache, die Sie verwenden möchten (**Visual Basic** oder **Visual C#-**).</span><span class="sxs-lookup"><span data-stu-id="b3a7d-133">Under **Installed Templates**, select the programming language you want to use (**Visual Basic** or **Visual C#**).</span></span>

4. <span data-ttu-id="b3a7d-134">In der **neues Projekt** wählen Sie im Dialogfeld **WPF-Anwendung**.</span><span class="sxs-lookup"><span data-stu-id="b3a7d-134">In the **New Project** dialog box, select **WPF Application**.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="b3a7d-135">Wenn Sie nicht angezeigt werden der **WPF-Anwendung** Vorlage stellen Sie sicher, dass Sie eine Version Anzielen der [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] , die WPF unterstützt.</span><span class="sxs-lookup"><span data-stu-id="b3a7d-135">If you do not see the **WPF Application** template, make sure that you are targeting a version of the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] that supports WPF.</span></span> <span data-ttu-id="b3a7d-136">In der **neues Projekt** wählen Sie im Dialogfeld [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] aus der Liste.</span><span class="sxs-lookup"><span data-stu-id="b3a7d-136">In the **New Project** dialog box, select [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] from the list.</span></span>

5. <span data-ttu-id="b3a7d-137">In der **Namen** Text Geben Sie einen Namen für Ihr Projekt.</span><span class="sxs-lookup"><span data-stu-id="b3a7d-137">In the **Name** text box, enter a name for your project.</span></span> <span data-ttu-id="b3a7d-138">Sie können z. B. eingeben **"WPFCaching"**.</span><span class="sxs-lookup"><span data-stu-id="b3a7d-138">For example, you can enter **WPFCaching**.</span></span>

6. <span data-ttu-id="b3a7d-139">Aktivieren Sie das Kontrollkästchen **Verzeichnis für Projektmappe erstellen**.</span><span class="sxs-lookup"><span data-stu-id="b3a7d-139">Select the **Create directory for solution** check box.</span></span>

7. <span data-ttu-id="b3a7d-140">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="b3a7d-140">Click **OK**.</span></span>

     <span data-ttu-id="b3a7d-141">Der WPF-Designer wird geöffnet, **Entwurf** anzeigen und die Datei "MainWindow.xaml" angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b3a7d-141">The WPF Designer opens in **Design** view and displays the MainWindow.xaml file.</span></span> <span data-ttu-id="b3a7d-142">Visual Studio erstellt die **Mein Projekt** Ordner, die Datei "Application.xaml" und die Datei "MainWindow.xaml".</span><span class="sxs-lookup"><span data-stu-id="b3a7d-142">Visual Studio creates the **My Project** folder, the Application.xaml file, and the MainWindow.xaml file.</span></span>

## <a name="targeting-the-net-framework-and-adding-a-reference-to-the-caching-assemblies"></a><span data-ttu-id="b3a7d-143">Das .NET Framework und Hinzufügen eines Verweises auf die Zwischenspeicherung Assemblys</span><span class="sxs-lookup"><span data-stu-id="b3a7d-143">Targeting the .NET Framework and Adding a Reference to the Caching Assemblies</span></span>
 <span data-ttu-id="b3a7d-144">Standardmäßig werden in WPF-Anwendungen Ziel der [!INCLUDE[net_client_v40_long](../../../../includes/net-client-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b3a7d-144">By default, WPF applications target the [!INCLUDE[net_client_v40_long](../../../../includes/net-client-v40-long-md.md)].</span></span> <span data-ttu-id="b3a7d-145">Verwenden der <xref:System.Runtime.Caching> -Namespace in einer WPF-Anwendung, die Anwendung muss Ziel der [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] (nicht die [!INCLUDE[net_client_v40_long](../../../../includes/net-client-v40-long-md.md)]) und einen Verweis auf den Namespace enthalten.</span><span class="sxs-lookup"><span data-stu-id="b3a7d-145">To use the <xref:System.Runtime.Caching> namespace in a WPF application, the application must target the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] (not the [!INCLUDE[net_client_v40_long](../../../../includes/net-client-v40-long-md.md)]) and must include a reference to the namespace.</span></span>

 <span data-ttu-id="b3a7d-146">Daher der nächste Schritt ist die .NET Framework-Zielversion ändern, und fügen einen Verweis auf die <xref:System.Runtime.Caching> Namespace.</span><span class="sxs-lookup"><span data-stu-id="b3a7d-146">Therefore, the next step is to change the .NET Framework target and add a reference to the <xref:System.Runtime.Caching> namespace.</span></span>

> [!NOTE]
>  <span data-ttu-id="b3a7d-147">Das Verfahren zum Ändern der Zielversion von .NET Framework ist in Visual Basic-Projekt und in ein Visual Basic#-Projekt.</span><span class="sxs-lookup"><span data-stu-id="b3a7d-147">The procedure for changing the .NET Framework target is different in a Visual Basic project and in a Visual C# project.</span></span>

#### <a name="to-change-the-target-net-framework-in-visual-basic"></a><span data-ttu-id="b3a7d-148">So ändern Sie das Ziel .NET Framework in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b3a7d-148">To change the target .NET Framework in Visual Basic</span></span>

1. <span data-ttu-id="b3a7d-149">In **Projektmappen-Explorer**mit der rechten Maustaste auf den Projektnamen, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="b3a7d-149">In **Solutions Explorer**, right-click the project name, and then click **Properties**.</span></span>

     <span data-ttu-id="b3a7d-150">Fenster "Eigenschaften" für die Anwendung wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b3a7d-150">The properties window for the application is displayed.</span></span>

2. <span data-ttu-id="b3a7d-151">Klicken Sie auf die Registerkarte **Kompilieren**.</span><span class="sxs-lookup"><span data-stu-id="b3a7d-151">Click the **Compile** tab.</span></span>

3. <span data-ttu-id="b3a7d-152">Am unteren Rand des Fensters, klicken Sie auf **Erweiterte Kompilierungsoptionen...** .</span><span class="sxs-lookup"><span data-stu-id="b3a7d-152">At the bottom of the window, click **Advanced Compile Options…**.</span></span>

     <span data-ttu-id="b3a7d-153">Die **erweiterte Compilereinstellungen** Dialogfeld wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b3a7d-153">The **Advanced Compiler Settings** dialog box is displayed.</span></span>

4. <span data-ttu-id="b3a7d-154">In der **Zielframework (alle Konfigurationen)** Liste [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b3a7d-154">In the **Target framework (all configurations)** list, select [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span> <span data-ttu-id="b3a7d-155">(Wählen Sie nicht [!INCLUDE[net_client_v40_long](../../../../includes/net-client-v40-long-md.md)].)</span><span class="sxs-lookup"><span data-stu-id="b3a7d-155">(Do not select [!INCLUDE[net_client_v40_long](../../../../includes/net-client-v40-long-md.md)].)</span></span>

5. <span data-ttu-id="b3a7d-156">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="b3a7d-156">Click **OK**.</span></span>

     <span data-ttu-id="b3a7d-157">Das Dialogfeld **Änderung des Zielframeworks** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b3a7d-157">The **Target Framework Change** dialog box is displayed.</span></span>

6. <span data-ttu-id="b3a7d-158">In der **Zielframeworkänderung** Dialogfeld klicken Sie auf **Ja**.</span><span class="sxs-lookup"><span data-stu-id="b3a7d-158">In the **Target Framework Change** dialog box, click **Yes**.</span></span>

     <span data-ttu-id="b3a7d-159">Das Projekt geschlossen und erneut geöffnet wird.</span><span class="sxs-lookup"><span data-stu-id="b3a7d-159">The project is closed and is then reopened.</span></span>

7. <span data-ttu-id="b3a7d-160">Fügen Sie einen Verweis auf die caching-Assembly mit folgenden Schritten hinzu:</span><span class="sxs-lookup"><span data-stu-id="b3a7d-160">Add a reference to the caching assembly by following these steps:</span></span>

    1. <span data-ttu-id="b3a7d-161">In **Projektmappen-Explorer**mit der rechten Maustaste auf den Namen des Projekts, und klicken Sie dann auf **Verweis hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="b3a7d-161">In **Solution Explorer**, right-click the name of the project and then click **Add Reference**.</span></span>

    2. <span data-ttu-id="b3a7d-162">Wählen Sie die **.NET** Registerkarte `System.Runtime.Caching`, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="b3a7d-162">Select the **.NET** tab, select `System.Runtime.Caching`, and then click **OK**.</span></span>

#### <a name="to-change-the-target-net-framework-in-a-visual-c-project"></a><span data-ttu-id="b3a7d-163">So ändern Sie die .NET Framework-Zielversion in einem Visual C#-Projekt</span><span class="sxs-lookup"><span data-stu-id="b3a7d-163">To change the target .NET Framework in a Visual C# project</span></span>

1. <span data-ttu-id="b3a7d-164">In **Projektmappen-Explorer**mit der rechten Maustaste auf den Projektnamen, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="b3a7d-164">In **Solution Explorer**, right-click the project name and then click **Properties**.</span></span>

     <span data-ttu-id="b3a7d-165">Fenster "Eigenschaften" für die Anwendung wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b3a7d-165">The properties window for the application is displayed.</span></span>

2. <span data-ttu-id="b3a7d-166">Klicken Sie auf die Registerkarte **Anwendung** .</span><span class="sxs-lookup"><span data-stu-id="b3a7d-166">Click the **Application** tab.</span></span>

3. <span data-ttu-id="b3a7d-167">In der **Zielframework** Liste [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b3a7d-167">In the **Target framework** list, select [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span> <span data-ttu-id="b3a7d-168">(Wählen Sie nicht **.NET Framework 4 Client Profile**.)</span><span class="sxs-lookup"><span data-stu-id="b3a7d-168">(Do not select **.NET Framework 4 Client Profile**.)</span></span>

4. <span data-ttu-id="b3a7d-169">Fügen Sie einen Verweis auf die caching-Assembly mit folgenden Schritten hinzu:</span><span class="sxs-lookup"><span data-stu-id="b3a7d-169">Add a reference to the caching assembly by following these steps:</span></span>

    1. <span data-ttu-id="b3a7d-170">Mit der rechten Maustaste die **Verweise** Ordner, und klicken Sie dann auf **Verweis hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="b3a7d-170">Right-click the **References** folder and then click **Add Reference**.</span></span>

    2. <span data-ttu-id="b3a7d-171">Wählen Sie die **.NET** Registerkarte `System.Runtime.Caching`, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="b3a7d-171">Select the **.NET** tab, select `System.Runtime.Caching`, and then click **OK**.</span></span>

## <a name="adding-a-button-to-the-wpf-window"></a><span data-ttu-id="b3a7d-172">Hinzufügen einer Schaltfläche in der WPF-Fenster</span><span class="sxs-lookup"><span data-stu-id="b3a7d-172">Adding a Button to the WPF Window</span></span>
 <span data-ttu-id="b3a7d-173">Als Nächstes, Sie fügen ein Schaltflächensteuerelement hinzu und erstellen Sie einen Ereignishandler für der Schaltfläche " `Click` Ereignis.</span><span class="sxs-lookup"><span data-stu-id="b3a7d-173">Next, you will add a button control and create an event handler for the button's `Click` event.</span></span> <span data-ttu-id="b3a7d-174">Später fügen Sie Code hinzu, sodass Wenn Sie die Schaltfläche klicken, den Inhalt der Textdatei zwischengespeichert und angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="b3a7d-174">Later you will add code to so when you click the button, the contents of the text file are cached and displayed.</span></span>

#### <a name="to-add-a-button-control"></a><span data-ttu-id="b3a7d-175">Ein Schaltflächen-Steuerelement hinzufügen</span><span class="sxs-lookup"><span data-stu-id="b3a7d-175">To add a button control</span></span>

1. <span data-ttu-id="b3a7d-176">In **Projektmappen-Explorer**, doppelklicken Sie auf die Datei "MainWindow.xaml", um ihn zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="b3a7d-176">In **Solution Explorer**, double-click the MainWindow.xaml file to open it.</span></span>

2. <span data-ttu-id="b3a7d-177">Von der **Toolbox**unter **WPF-Standardsteuerelemente**, ziehen Sie eine `Button` die Steuerung an die `MainWindow` Fenster.</span><span class="sxs-lookup"><span data-stu-id="b3a7d-177">From the **Toolbox**, under **Common WPF Controls**, drag a `Button` control to the `MainWindow` window.</span></span>

3. <span data-ttu-id="b3a7d-178">In der **Eigenschaften** legen die `Content` Eigenschaft der `Button` die Steuerung an **Cache abrufen**.</span><span class="sxs-lookup"><span data-stu-id="b3a7d-178">In the **Properties** window, set the `Content` property of the `Button` control to **Get Cache**.</span></span>

## <a name="initializing-the-cache-and-caching-an-entry"></a><span data-ttu-id="b3a7d-179">Initialisieren des Caches und Zwischenspeichern eines Eintrags</span><span class="sxs-lookup"><span data-stu-id="b3a7d-179">Initializing the Cache and Caching an Entry</span></span>
 <span data-ttu-id="b3a7d-180">Anschließend fügen Sie den Code, um die folgenden Aufgaben ausführen:</span><span class="sxs-lookup"><span data-stu-id="b3a7d-180">Next, you will add the code to perform the following tasks:</span></span>

- <span data-ttu-id="b3a7d-181">Erstellen Sie eine Instanz der Cacheklasse – d. h., instanziieren Sie ein neues <xref:System.Runtime.Caching.MemoryCache> Objekt.</span><span class="sxs-lookup"><span data-stu-id="b3a7d-181">Create an instance of the cache class—that is, you will instantiate a new <xref:System.Runtime.Caching.MemoryCache> object.</span></span>

- <span data-ttu-id="b3a7d-182">Gibt an, dass der Cache verwendet einen <xref:System.Runtime.Caching.HostFileChangeMonitor> Objekt für die Überwachung von Änderungen in der Textdatei.</span><span class="sxs-lookup"><span data-stu-id="b3a7d-182">Specify that the cache uses a <xref:System.Runtime.Caching.HostFileChangeMonitor> object to monitor changes in the text file.</span></span>

- <span data-ttu-id="b3a7d-183">Lesen Sie die Textdatei, und dessen Inhalt als einen Eintrag im Cache zwischengespeichert.</span><span class="sxs-lookup"><span data-stu-id="b3a7d-183">Read the text file and cache its contents as a cache entry.</span></span>

- <span data-ttu-id="b3a7d-184">Zeigt den Inhalt der Textdatei zwischengespeichert.</span><span class="sxs-lookup"><span data-stu-id="b3a7d-184">Display the contents of the cached text file.</span></span>

#### <a name="to-create-the-cache-object"></a><span data-ttu-id="b3a7d-185">Um das Cache-Objekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="b3a7d-185">To create the cache object</span></span>

1. <span data-ttu-id="b3a7d-186">Doppelklicken Sie auf die Schaltfläche, die Sie gerade hinzugefügt haben, um einen Ereignishandler in der Datei "MainWindow.Xaml.cs" oder "MainWindow.Xaml.vb" zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="b3a7d-186">Double-click the button you just added in order to create an event handler in the MainWindow.xaml.cs or MainWindow.Xaml.vb file.</span></span>

2. <span data-ttu-id="b3a7d-187">Fügen Sie am Anfang der Datei (vor der Klassendeklaration), die folgenden `Imports` (Visual Basic) oder `using` (c#)-Anweisungen:</span><span class="sxs-lookup"><span data-stu-id="b3a7d-187">At the top of the file (before the class declaration), add the following `Imports` (Visual Basic) or `using` (C#) statements:</span></span>

    ```csharp
    using System.Runtime.Caching;
    using System.IO;
    ```

    ```vb
    Imports System.Runtime.Caching
    Imports System.IO
    ```

3. <span data-ttu-id="b3a7d-188">Fügen Sie den folgenden Code zum Instanziieren des Cache-Objekts, in dem Ereignishandler:</span><span class="sxs-lookup"><span data-stu-id="b3a7d-188">In the event handler, add the following code to instantiate the cache object:</span></span>

    ```csharp
    ObjectCache cache = MemoryCache.Default;
    ```

    ```vb
    Dim cache As ObjectCache = MemoryCache.Default
    ```

     <span data-ttu-id="b3a7d-189">Die <xref:System.Runtime.Caching.ObjectCache> -Klasse ist eine integrierte, die Cache ein Objekt im Speicher bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="b3a7d-189">The <xref:System.Runtime.Caching.ObjectCache> class is a built-in class that provides an in-memory object cache.</span></span>

4. <span data-ttu-id="b3a7d-190">Fügen Sie den folgenden Code zum Lesen des Inhalts ein Cacheeintrag mit dem Namen `filecontents`:</span><span class="sxs-lookup"><span data-stu-id="b3a7d-190">Add the following code to read the contents of a cache entry named `filecontents`:</span></span>

    ```vb
    Dim fileContents As String = TryCast(cache("filecontents"), String)
    ```

    ```csharp
    string fileContents = cache["filecontents"] as string;
    ```

5. <span data-ttu-id="b3a7d-191">Fügen Sie den folgenden Code zum Überprüfen, ob der Cacheeintrag mit dem Namen `filecontents` vorhanden ist:</span><span class="sxs-lookup"><span data-stu-id="b3a7d-191">Add the following code to check whether the cache entry named `filecontents` exists:</span></span>

    ```vb
    If fileContents Is Nothing Then

    End If
    ```

    ```csharp
    if (fileContents == null)
    {

    }
    ```

     <span data-ttu-id="b3a7d-192">Wenn der angegebene Cacheeintrag nicht vorhanden ist, müssen Sie die Textdatei lesen und als einen Cacheeintrag in den Cache hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="b3a7d-192">If the specified cache entry does not exist, you must read the text file and add it as a cache entry to the cache.</span></span>

6. <span data-ttu-id="b3a7d-193">In der `if/then` blockieren, fügen Sie den folgenden Code zum Erstellen eines neuen <xref:System.Runtime.Caching.CacheItemPolicy> Objekt, das angibt, dass nach 10 Sekunden der Cacheeintrag abläuft.</span><span class="sxs-lookup"><span data-stu-id="b3a7d-193">In the `if/then` block, add the following code to create a new <xref:System.Runtime.Caching.CacheItemPolicy> object that specifies that the cache entry expires after 10 seconds.</span></span>

    ```vb
    Dim policy As New CacheItemPolicy()
    policy.AbsoluteExpiration = DateTimeOffset.Now.AddSeconds(10.0)
    ```

    ```csharp
    CacheItemPolicy policy = new CacheItemPolicy();
    policy.AbsoluteExpiration = DateTimeOffset.Now.AddSeconds(10.0);
    ```

     <span data-ttu-id="b3a7d-194">Wenn keine Informationen Cachelöschungs- oder Ablaufrichtlinie angegeben wird, wird der Standardwert ist <xref:System.Runtime.Caching.ObjectCache.InfiniteAbsoluteExpiration>, was bedeutet, dass die Cacheeinträge läuft nie ab basiert nur auf einer absoluten Zeit.</span><span class="sxs-lookup"><span data-stu-id="b3a7d-194">If no eviction or expiration information is provided, the default is <xref:System.Runtime.Caching.ObjectCache.InfiniteAbsoluteExpiration>, which means the cache entries never expire based only on an absolute time.</span></span> <span data-ttu-id="b3a7d-195">Stattdessen laufen die Einträge im Cache nur, wenn genügend Arbeitsspeicher vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="b3a7d-195">Instead, cache entries expire only when there is memory pressure.</span></span> <span data-ttu-id="b3a7d-196">Als bewährte Methode sollten Sie entweder ein absoluter oder ein variabler Ablauf immer explizit bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="b3a7d-196">As a best practice, you should always explicitly provide either an absolute or a sliding expiration.</span></span>

7. <span data-ttu-id="b3a7d-197">In der `if/then` blockieren und die folgenden den Code, die Sie im vorherigen Schritt hinzugefügt haben, fügen Sie den folgenden Code aus, um eine Sammlung für die Dateipfade zu erstellen, überwachen und den Pfad der Textdatei, die Auflistung hinzugefügt werden soll:</span><span class="sxs-lookup"><span data-stu-id="b3a7d-197">Inside the `if/then` block and following the code you added in the previous step, add the following code to create a collection for the file paths that you want to monitor, and to add the path of the text file to the collection:</span></span>

    ```vb
    Dim filePaths As New List(Of String)()
    filePaths.Add("c:\cache\cacheText.txt")
    ```

    ```csharp
    List<string> filePaths = new List<string>();
    filePaths.Add("c:\\cache\\cacheText.txt");
    ```

    > [!NOTE]
    >  <span data-ttu-id="b3a7d-198">Wenn die Textdatei, die Sie verwenden möchten nicht `c:\cache\cacheText.txt`, geben Sie den Pfad die Textdatei, die Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="b3a7d-198">If the text file you want to use is not `c:\cache\cacheText.txt`, specify the path where the text file is that you want to use.</span></span>

8. <span data-ttu-id="b3a7d-199">Nach dem Code, die Sie im vorherigen Schritt hinzugefügt haben, fügen den folgenden Code zum Hinzufügen einer neuen <xref:System.Runtime.Caching.HostFileChangeMonitor> Objekt, das die Auflistung der Änderung für den Cacheeintrag überwacht:</span><span class="sxs-lookup"><span data-stu-id="b3a7d-199">Following the code that you added in the previous step, add the following code to add a new <xref:System.Runtime.Caching.HostFileChangeMonitor> object to the collection of change monitors for the cache entry:</span></span>

    ```vb
    policy.ChangeMonitors.Add(New HostFileChangeMonitor(filePaths))
    ```

    ```csharp
    policy.ChangeMonitors.Add(new HostFileChangeMonitor(filePaths));
    ```

     <span data-ttu-id="b3a7d-200">Die <xref:System.Runtime.Caching.HostFileChangeMonitor> Objekt der Pfad der Textdatei überwacht und benachrichtigt Sie den Cache ein, wenn Änderungen auftreten.</span><span class="sxs-lookup"><span data-stu-id="b3a7d-200">The <xref:System.Runtime.Caching.HostFileChangeMonitor> object monitors the text file's path and notifies the cache if changes occur.</span></span> <span data-ttu-id="b3a7d-201">In diesem Beispiel wird der Cacheeintrag abläuft, wenn der Inhalt der Datei ändert.</span><span class="sxs-lookup"><span data-stu-id="b3a7d-201">In this example, the cache entry will expire if the content of the file changes.</span></span>

9. <span data-ttu-id="b3a7d-202">Fügen Sie folgenden Code, der Sie im vorherigen Schritt hinzugefügt haben, lesen Sie den Inhalt der Textdatei den folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="b3a7d-202">Following the code that you added in the previous step, add the following code to read the contents of the text file:</span></span>

    ```vb
    fileContents = File.ReadAllText("c:\cache\cacheText.txt") & vbCrLf & DateTime.Now.ToString()
    ```

    ```csharp
    fileContents = File.ReadAllText("c:\\cache\\cacheText.txt") + "\n" + DateTime.Now;
    ```

     <span data-ttu-id="b3a7d-203">Die Datums- / Zeitstempel wird hinzugefügt, sodass Sie sehen werden, wenn der Cacheeintrag abläuft.</span><span class="sxs-lookup"><span data-stu-id="b3a7d-203">The date and time timestamp is added so that you will be able to see when the cache entry expires.</span></span>

10. <span data-ttu-id="b3a7d-204">Nach dem Code, die Sie im vorherigen Schritt hinzugefügt haben, fügen den folgenden Code zum Einfügen von den Inhalt der Datei in das Cache-Objekt als eine <xref:System.Runtime.Caching.CacheItem> Instanz:</span><span class="sxs-lookup"><span data-stu-id="b3a7d-204">Following the code that you added in the previous step, add the following code to insert the contents of the file into the cache object as a <xref:System.Runtime.Caching.CacheItem> instance:</span></span>

    ```vb
    cache.Set("filecontents", fileContents, policy)
    ```

    ```csharp
    cache.Set("filecontents", fileContents, policy);
    ```

     <span data-ttu-id="b3a7d-205">Geben Sie Informationen wie der Cacheeintrag sollten, indem Sie übergeben entfernt werden die <xref:System.Runtime.Caching.CacheItemPolicy> -Objekt, das Sie zuvor erstellt, als Parameter haben.</span><span class="sxs-lookup"><span data-stu-id="b3a7d-205">You specify information about how the cache entry should be evicted by passing the <xref:System.Runtime.Caching.CacheItemPolicy> object that you created earlier as a parameter.</span></span>

11. <span data-ttu-id="b3a7d-206">Nach der `if/then` blockieren, fügen Sie den folgenden Code, um den Inhalt zwischengespeicherter Dateien in einem Meldungsfeld anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="b3a7d-206">After the `if/then` block, add the following code to display the cached file content in a message box:</span></span>

    ```vb
    MessageBox.Show(fileContents)
    ```

    ```csharp
    MessageBox.Show(fileContents);
    ```

12. <span data-ttu-id="b3a7d-207">In der **erstellen** Menü klicken Sie auf **erstellen "WPFCaching"** zum Erstellen Ihres Projekts.</span><span class="sxs-lookup"><span data-stu-id="b3a7d-207">In the **Build** menu, click **Build WPFCaching** to build your project.</span></span>

## <a name="testing-caching-in-the-wpf-application"></a><span data-ttu-id="b3a7d-208">Testen der Zwischenspeicherung in WPF-Anwendung</span><span class="sxs-lookup"><span data-stu-id="b3a7d-208">Testing Caching in the WPF Application</span></span>
 <span data-ttu-id="b3a7d-209">Sie können jetzt die Anwendung testen.</span><span class="sxs-lookup"><span data-stu-id="b3a7d-209">You can now test the application.</span></span>

#### <a name="to-test-caching-in-the-wpf-application"></a><span data-ttu-id="b3a7d-210">Zum Testen der Zwischenspeicherung in WPF-Anwendung</span><span class="sxs-lookup"><span data-stu-id="b3a7d-210">To test caching in the WPF application</span></span>

1. <span data-ttu-id="b3a7d-211">Drücken Sie STRG+F5, um die Anwendung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="b3a7d-211">Press CTRL+F5 to run the application.</span></span>

     <span data-ttu-id="b3a7d-212">Die `MainWindow` Fenster wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b3a7d-212">The `MainWindow` window is displayed.</span></span>

2. <span data-ttu-id="b3a7d-213">Klicken Sie auf **Cache abrufen**.</span><span class="sxs-lookup"><span data-stu-id="b3a7d-213">Click **Get Cache**.</span></span>

     <span data-ttu-id="b3a7d-214">Die zwischengespeicherte Inhalte aus der Textdatei wird in einem Meldungsfeld angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b3a7d-214">The cached content from the text file is displayed in a message box.</span></span> <span data-ttu-id="b3a7d-215">Beachten Sie, dass die Zeitstempel der Datei.</span><span class="sxs-lookup"><span data-stu-id="b3a7d-215">Notice the timestamp on the file.</span></span>

3. <span data-ttu-id="b3a7d-216">Das Meldungsfeld zu schließen, und klicken Sie dann auf **Cache abrufen** erneut aus.</span><span class="sxs-lookup"><span data-stu-id="b3a7d-216">Close the message box and then click **Get Cache** again.</span></span>

     <span data-ttu-id="b3a7d-217">Der Zeitstempel ist unverändert.</span><span class="sxs-lookup"><span data-stu-id="b3a7d-217">The timestamp is unchanged.</span></span> <span data-ttu-id="b3a7d-218">Dies gibt an, dass der zwischengespeicherte Inhalt angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="b3a7d-218">This indicates the cached content is displayed.</span></span>

4. <span data-ttu-id="b3a7d-219">Warten Sie mindestens 10 Sekunden festzulegen, und klicken Sie dann auf **Cache abrufen** erneut aus.</span><span class="sxs-lookup"><span data-stu-id="b3a7d-219">Wait 10 seconds or more and then click **Get Cache** again.</span></span>

     <span data-ttu-id="b3a7d-220">Dieses Mal wird es sich um ein neuer Zeitstempel angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b3a7d-220">This time a new timestamp is displayed.</span></span> <span data-ttu-id="b3a7d-221">Dies bedeutet, dass die Richtlinie den Cacheeintrag abläuft und neue zwischengespeicherte Inhalte angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="b3a7d-221">This indicates that the policy let the cache entry expire and that new cached content is displayed.</span></span>

5. <span data-ttu-id="b3a7d-222">Öffnen Sie in einem Text-Editor die Textdatei, die Sie erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="b3a7d-222">In a text editor, open the text file that you created.</span></span> <span data-ttu-id="b3a7d-223">Nehmen Sie Änderungen noch nicht.</span><span class="sxs-lookup"><span data-stu-id="b3a7d-223">Do not make any changes yet.</span></span>

6. <span data-ttu-id="b3a7d-224">Das Meldungsfeld zu schließen, und klicken Sie dann auf **Cache abrufen** erneut aus.</span><span class="sxs-lookup"><span data-stu-id="b3a7d-224">Close the message box and then click **Get Cache** again.</span></span>

     <span data-ttu-id="b3a7d-225">Beachten Sie den Zeitstempel erneut ein.</span><span class="sxs-lookup"><span data-stu-id="b3a7d-225">Notice the timestamp again.</span></span>

7. <span data-ttu-id="b3a7d-226">Nehmen Sie eine Änderung in die Textdatei, und speichern Sie die Datei.</span><span class="sxs-lookup"><span data-stu-id="b3a7d-226">Make a change to the text file and then save the file.</span></span>

8. <span data-ttu-id="b3a7d-227">Das Meldungsfeld zu schließen, und klicken Sie dann auf **Cache abrufen** erneut aus.</span><span class="sxs-lookup"><span data-stu-id="b3a7d-227">Close the message box and then click **Get Cache** again.</span></span>

     <span data-ttu-id="b3a7d-228">Das Meldungsfeld enthält des aktualisierten Inhalts aus der Textdatei und einen neuen Zeitstempel.</span><span class="sxs-lookup"><span data-stu-id="b3a7d-228">This message box contains the updated content from the text file and a new timestamp.</span></span> <span data-ttu-id="b3a7d-229">Dies gibt an, dass die änderungsüberwachung Hostdatei der Cacheeintrag entfernt sofort, wenn Sie die Datei geändert, obwohl die absoluten Ablauf des Zeitlimits nicht hatten.</span><span class="sxs-lookup"><span data-stu-id="b3a7d-229">This indicates that the host-file change monitor evicted the cache entry immediately when you changed the file, even though the absolute timeout period had not expired.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="b3a7d-230">Sie können die Entfernungszeit auf 20 Sekunden oder mehr zusätzlichen Zeitaufwand für das Sie in der Datei eine Änderung vornehmen zu erhöhen.</span><span class="sxs-lookup"><span data-stu-id="b3a7d-230">You can increase the eviction time to 20 seconds or more to allow more time for you to make a change in the file.</span></span>

## <a name="code-example"></a><span data-ttu-id="b3a7d-231">Codebeispiel</span><span class="sxs-lookup"><span data-stu-id="b3a7d-231">Code Example</span></span>
 <span data-ttu-id="b3a7d-232">Nachdem Sie diese exemplarische Vorgehensweise abgeschlossen haben, wird der Code für das erstellte Projekt im folgende Beispiel entsprechen.</span><span class="sxs-lookup"><span data-stu-id="b3a7d-232">After you have completed this walkthrough, the code for the project you created will resemble the following example.</span></span>

 [!code-csharp[CachingWPFApplications#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CachingWPFApplications/CSharp/MainWindow.xaml.cs#1)]
 [!code-vb[CachingWPFApplications#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CachingWPFApplications/VisualBasic/MainWindow.xaml.vb#1)]

## <a name="see-also"></a><span data-ttu-id="b3a7d-233">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b3a7d-233">See also</span></span>

- <xref:System.Runtime.Caching.MemoryCache>
- <xref:System.Runtime.Caching.ObjectCache>
- <xref:System.Runtime.Caching>
- [<span data-ttu-id="b3a7d-234">Caching in .NET Framework Applications (Caching in .NET Framework-Anwendungen)</span><span class="sxs-lookup"><span data-stu-id="b3a7d-234">Caching in .NET Framework Applications</span></span>](../../performance/caching-in-net-framework-applications.md)
