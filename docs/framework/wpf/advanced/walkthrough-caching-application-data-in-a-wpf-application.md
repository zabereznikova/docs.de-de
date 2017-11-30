---
title: 'Exemplarische Vorgehensweise: Zwischenspeichern von Anwendungsdaten in einer WPF-Anwendung'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- walkthroughs [WPF], caching
- caching [.NET Framework]
- caching [WPF]
ms.assetid: dac2c9ce-042b-4d23-91eb-28f584415cef
caps.latest.revision: "25"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7c04a2860b46460065a09de3dafedc7010753d36
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-caching-application-data-in-a-wpf-application"></a><span data-ttu-id="ea831-102">Exemplarische Vorgehensweise: Zwischenspeichern von Anwendungsdaten in einer WPF-Anwendung</span><span class="sxs-lookup"><span data-stu-id="ea831-102">Walkthrough: Caching Application Data in a WPF Application</span></span>
<span data-ttu-id="ea831-103">Das Zwischenspeichern ermöglicht es Ihnen, Daten für schnellen Zugriff im Arbeitsspeicher zu speichern.</span><span class="sxs-lookup"><span data-stu-id="ea831-103">Caching enables you to store data in memory for rapid access.</span></span> <span data-ttu-id="ea831-104">Die Daten erneut zugegriffen wird, können Anwendungen die Daten aus dem Cache, die sie aus der Originalquelle stattdessen abrufen zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="ea831-104">When the data is accessed again, applications can get the data from the cache instead retrieving it from the original source.</span></span> <span data-ttu-id="ea831-105">Dies kann die Leistung und Skalierbarkeit verbessern.</span><span class="sxs-lookup"><span data-stu-id="ea831-105">This can improve performance and scalability.</span></span> <span data-ttu-id="ea831-106">Darüber hinaus macht das Zwischenspeichern Daten verfügbar, wenn die Datenquelle vorübergehend nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="ea831-106">In addition, caching makes data available when the data source is temporarily unavailable.</span></span>  
  
 <span data-ttu-id="ea831-107">Die [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] bietet Klassen, die Ihnen ermöglichen, verwenden der Zwischenspeicherung in [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="ea831-107">The [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] provides classes that enable you to use caching in [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] applications.</span></span> <span data-ttu-id="ea831-108">Diese Klassen befinden sich der <xref:System.Runtime.Caching> Namespace.</span><span class="sxs-lookup"><span data-stu-id="ea831-108">These classes are located in the <xref:System.Runtime.Caching> namespace.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ea831-109">Die <xref:System.Runtime.Caching> Namespace ist neu in der [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ea831-109">The <xref:System.Runtime.Caching> namespace is new in the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span> <span data-ttu-id="ea831-110">Dieser Namespace stellt Zwischenspeichern steht allen [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="ea831-110">This namespace makes caching is available to all [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] applications.</span></span> <span data-ttu-id="ea831-111">In früheren [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]-Versionen war die Zwischenspeicherung nur im <xref:System.Web>-Namespace verfügbar, und erforderte daher eine Abhängigkeit der ASP.NET-Klassen.</span><span class="sxs-lookup"><span data-stu-id="ea831-111">In previous versions of the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], caching was available only in the <xref:System.Web> namespace and therefore required a dependency on ASP.NET classes.</span></span>  
  
 <span data-ttu-id="ea831-112">In dieser exemplarischen Vorgehensweise wird veranschaulicht, wie die Funktionen zum Zwischenspeichern verwenden, das in verfügbar ist die [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] als Teil einer [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Anwendung.</span><span class="sxs-lookup"><span data-stu-id="ea831-112">This walkthrough shows you how to use the caching functionality that is available in the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] as part of a [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] application.</span></span> <span data-ttu-id="ea831-113">In der exemplarischen Vorgehensweise Zwischenspeichern Sie den Inhalt einer Textdatei.</span><span class="sxs-lookup"><span data-stu-id="ea831-113">In the walkthrough, you cache the contents of a text file.</span></span>  
  
 <span data-ttu-id="ea831-114">In dieser exemplarischen Vorgehensweise werden u. a. die folgenden Aufgaben beschrieben:</span><span class="sxs-lookup"><span data-stu-id="ea831-114">Tasks illustrated in this walkthrough include the following:</span></span>  
  
-   <span data-ttu-id="ea831-115">Erstellen ein WPF-Anwendungsprojekt.</span><span class="sxs-lookup"><span data-stu-id="ea831-115">Creating a WPF application project.</span></span>  
  
-   <span data-ttu-id="ea831-116">Hinzufügen eines Verweises auf die [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ea831-116">Adding a reference to the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span>  
  
-   <span data-ttu-id="ea831-117">Initialisieren einen Cache.</span><span class="sxs-lookup"><span data-stu-id="ea831-117">Initializing a cache.</span></span>  
  
-   <span data-ttu-id="ea831-118">Hinzufügen eines Cache-Eintrags mit dem Inhalt einer Textdatei.</span><span class="sxs-lookup"><span data-stu-id="ea831-118">Adding a cache entry that contains the contents of a text file.</span></span>  
  
-   <span data-ttu-id="ea831-119">Bereitstellen einer Entfernungsrichtlinie für den Cacheeintrag.</span><span class="sxs-lookup"><span data-stu-id="ea831-119">Providing an eviction policy for the cache entry.</span></span>  
  
-   <span data-ttu-id="ea831-120">Überwachen den Pfad der zwischengespeicherte Datei und die Cacheinstanz zu benachrichtigen, die in der Überwachungskapazität für Elemente geändert werden.</span><span class="sxs-lookup"><span data-stu-id="ea831-120">Monitoring the path of the cached file and notifying the cache instance about changes to the monitored item.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="ea831-121">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="ea831-121">Prerequisites</span></span>  
 <span data-ttu-id="ea831-122">Für die Durchführung dieser exemplarischen Vorgehensweise benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="ea831-122">In order to complete this walkthrough, you will need:</span></span>  
  
-   <span data-ttu-id="ea831-123">Microsoft [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ea831-123">Microsoft [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)].</span></span>  
  
-   <span data-ttu-id="ea831-124">Eine Textdatei, die eine kleine Menge an Text enthält.</span><span class="sxs-lookup"><span data-stu-id="ea831-124">A text file that contains a small amount of text.</span></span> <span data-ttu-id="ea831-125">(Der Inhalt der Textdatei wird in einem Meldungsfeld angezeigt werden.) In der exemplarischen Vorgehensweise dargestellte Code wird davon ausgegangen, dass Sie mit der folgenden Datei arbeiten:</span><span class="sxs-lookup"><span data-stu-id="ea831-125">(You will display the contents of the text file in a message box.) The code illustrated in the walkthrough assumes that you are working with the following file:</span></span>  
  
     `c:\cache\cacheText.txt`  
  
     <span data-ttu-id="ea831-126">Allerdings können Sie eine Textdatei verwenden und kleine Änderungen an den Code in dieser exemplarischen Vorgehensweise.</span><span class="sxs-lookup"><span data-stu-id="ea831-126">However, you can use any text file and make small changes to the code in this walkthrough.</span></span>  
  
## <a name="creating-a-wpf-application-project"></a><span data-ttu-id="ea831-127">Erstellen eines WPF-Anwendungsprojekts</span><span class="sxs-lookup"><span data-stu-id="ea831-127">Creating a WPF Application Project</span></span>  
 <span data-ttu-id="ea831-128">Sie werden gestartet, indem Sie ein WPF-Anwendungsprojekt erstellen.</span><span class="sxs-lookup"><span data-stu-id="ea831-128">You will start by creating a WPF application project.</span></span>  
  
#### <a name="to-create-a-wpf-application"></a><span data-ttu-id="ea831-129">So erstellen Sie eine WPF-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="ea831-129">To create a WPF application</span></span>  
  
1.  <span data-ttu-id="ea831-130">Starten Sie [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ea831-130">Start [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)].</span></span>  
  
2.  <span data-ttu-id="ea831-131">In der **Datei** Menü klicken Sie auf **neu**, und klicken Sie dann auf **neues Projekt**.</span><span class="sxs-lookup"><span data-stu-id="ea831-131">In the **File** menu, click **New**, and then click **New Project**.</span></span>  
  
     <span data-ttu-id="ea831-132">Das Dialogfeld **Neues Projekt** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ea831-132">The **New Project** dialog box is displayed.</span></span>  
  
3.  <span data-ttu-id="ea831-133">Klicken Sie unter **installierte Vorlagen**, wählen Sie die Programmiersprache ab, die Sie verwenden möchten (**Visual Basic** oder **Visual C#-**).</span><span class="sxs-lookup"><span data-stu-id="ea831-133">Under **Installed Templates**, select the programming language you want to use (**Visual Basic** or **Visual C#**).</span></span>  
  
4.  <span data-ttu-id="ea831-134">In der **neues Projekt** wählen Sie im Dialogfeld **WPF-Anwendung**.</span><span class="sxs-lookup"><span data-stu-id="ea831-134">In the **New Project** dialog box, select **WPF Application**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ea831-135">Wenn Sie nicht sehen die **WPF-Anwendung** Vorlage, stellen Sie sicher, dass eine Version des anvisierten der [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] , die WPF unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ea831-135">If you do not see the **WPF Application** template, make sure that you are targeting a version of the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] that supports WPF.</span></span> <span data-ttu-id="ea831-136">In der **neues Projekt** wählen Sie im Dialogfeld [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] aus der Liste.</span><span class="sxs-lookup"><span data-stu-id="ea831-136">In the **New Project** dialog box, select [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] from the list.</span></span>  
  
5.  <span data-ttu-id="ea831-137">In der **Namen** Text Geben Sie einen Namen für das Projekt.</span><span class="sxs-lookup"><span data-stu-id="ea831-137">In the **Name** text box, enter a name for your project.</span></span> <span data-ttu-id="ea831-138">Sie können z. B. eingeben **"WPFCaching"**.</span><span class="sxs-lookup"><span data-stu-id="ea831-138">For example, you can enter **WPFCaching**.</span></span>  
  
6.  <span data-ttu-id="ea831-139">Wählen Sie die **Projektmappenverzeichnis erstellen** Kontrollkästchen.</span><span class="sxs-lookup"><span data-stu-id="ea831-139">Select the **Create directory for solution** check box.</span></span>  
  
7.  <span data-ttu-id="ea831-140">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="ea831-140">Click **OK**.</span></span>  
  
     <span data-ttu-id="ea831-141">Der WPF-Designer wird geöffnet, **Entwurf** anzeigen und die Datei "MainWindow.xaml" angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ea831-141">The WPF Designer opens in **Design** view and displays the MainWindow.xaml file.</span></span> [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)]<span data-ttu-id="ea831-142">erstellt die **Mein Projekt** Ordner die Datei "Application.xaml" und die Datei "MainWindow.xaml".</span><span class="sxs-lookup"><span data-stu-id="ea831-142"> creates the **My Project** folder, the Application.xaml file, and the MainWindow.xaml file.</span></span>  
  
## <a name="targeting-the-net-framework-and-adding-a-reference-to-the-caching-assemblies"></a><span data-ttu-id="ea831-143">Für .NET Framework und Hinzufügen eines Verweises auf die Caching-Assemblys</span><span class="sxs-lookup"><span data-stu-id="ea831-143">Targeting the .NET Framework and Adding a Reference to the Caching Assemblies</span></span>  
 <span data-ttu-id="ea831-144">Standardmäßig ist Ziel der WPF-Anwendungen die [!INCLUDE[net_client_v40_long](../../../../includes/net-client-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ea831-144">By default, WPF applications target the [!INCLUDE[net_client_v40_long](../../../../includes/net-client-v40-long-md.md)].</span></span> <span data-ttu-id="ea831-145">Verwenden der <xref:System.Runtime.Caching> Namespace in einer WPF-Anwendung, die Anwendung muss Ziel der [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] (nicht die [!INCLUDE[net_client_v40_long](../../../../includes/net-client-v40-long-md.md)]) und einen Verweis auf den Namespace enthalten.</span><span class="sxs-lookup"><span data-stu-id="ea831-145">To use the <xref:System.Runtime.Caching> namespace in a WPF application, the application must target the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] (not the [!INCLUDE[net_client_v40_long](../../../../includes/net-client-v40-long-md.md)]) and must include a reference to the namespace.</span></span>  
  
 <span data-ttu-id="ea831-146">Daher ist der nächste Schritt zum Ändern der Zielversion von .NET Framework, und fügen einen Verweis auf die <xref:System.Runtime.Caching> Namespace.</span><span class="sxs-lookup"><span data-stu-id="ea831-146">Therefore, the next step is to change the .NET Framework target and add a reference to the <xref:System.Runtime.Caching> namespace.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ea831-147">Das Verfahren zum Ändern der Zielversion von .NET Framework unterscheidet sich in einem Visual Basic-Projekt und in einem Visual C#-Projekt.</span><span class="sxs-lookup"><span data-stu-id="ea831-147">The procedure for changing the .NET Framework target is different in a Visual Basic project and in a Visual C# project.</span></span>  
  
#### <a name="to-change-the-target-net-framework-in-visual-basic"></a><span data-ttu-id="ea831-148">So ändern Sie das Ziel-.NET Framework in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ea831-148">To change the target .NET Framework in Visual Basic</span></span>  
  
1.  <span data-ttu-id="ea831-149">In **Projektmappen-Explorer**mit der rechten Maustaste auf den Projektnamen, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="ea831-149">In **Solutions Explorer**, right-click the project name, and then click **Properties**.</span></span>  
  
     <span data-ttu-id="ea831-150">Das Eigenschaftenfenster für die Anwendung wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ea831-150">The properties window for the application is displayed.</span></span>  
  
2.  <span data-ttu-id="ea831-151">Klicken Sie auf die Registerkarte **Kompilieren**.</span><span class="sxs-lookup"><span data-stu-id="ea831-151">Click the **Compile** tab.</span></span>  
  
3.  <span data-ttu-id="ea831-152">Klicken Sie am unteren Rand des Fensters, **Erweiterte Kompilierungsoptionen...** .</span><span class="sxs-lookup"><span data-stu-id="ea831-152">At the bottom of the window, click **Advanced Compile Options…**.</span></span>  
  
     <span data-ttu-id="ea831-153">Die **erweiterte Compilereinstellungen** Dialogfeld wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ea831-153">The **Advanced Compiler Settings** dialog box is displayed.</span></span>  
  
4.  <span data-ttu-id="ea831-154">In der **Zielframework (alle Konfigurationen)** Liste [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ea831-154">In the **Target framework (all configurations)** list, select [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span> <span data-ttu-id="ea831-155">(Wählen Sie nicht [!INCLUDE[net_client_v40_long](../../../../includes/net-client-v40-long-md.md)].)</span><span class="sxs-lookup"><span data-stu-id="ea831-155">(Do not select [!INCLUDE[net_client_v40_long](../../../../includes/net-client-v40-long-md.md)].)</span></span>  
  
5.  <span data-ttu-id="ea831-156">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="ea831-156">Click **OK**.</span></span>  
  
     <span data-ttu-id="ea831-157">Die **Änderung des Zielframeworks** Dialogfeld wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ea831-157">The **Target Framework Change** dialog box is displayed.</span></span>  
  
6.  <span data-ttu-id="ea831-158">In der **Änderung des Zielframeworks** (Dialogfeld), klicken Sie auf **Ja**.</span><span class="sxs-lookup"><span data-stu-id="ea831-158">In the **Target Framework Change** dialog box, click **Yes**.</span></span>  
  
     <span data-ttu-id="ea831-159">Das Projekt wird geschlossen und erneut geöffnet wird.</span><span class="sxs-lookup"><span data-stu-id="ea831-159">The project is closed and is then reopened.</span></span>  
  
7.  <span data-ttu-id="ea831-160">Fügen Sie einen Verweis auf die caching-Assembly hinzu, durch die folgenden Schritte:</span><span class="sxs-lookup"><span data-stu-id="ea831-160">Add a reference to the caching assembly by following these steps:</span></span>  
  
    1.  <span data-ttu-id="ea831-161">In **Projektmappen-Explorer**mit der rechten Maustaste auf den Namen des Projekts, und klicken Sie dann auf **Verweis hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="ea831-161">In **Solution Explorer**, right-click the name of the project and then click **Add Reference**.</span></span>  
  
    2.  <span data-ttu-id="ea831-162">Wählen Sie die **.NET** Registerkarte `System.Runtime.Caching`, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="ea831-162">Select the **.NET** tab, select `System.Runtime.Caching`, and then click **OK**.</span></span>  
  
#### <a name="to-change-the-target-net-framework-in-a-visual-c-project"></a><span data-ttu-id="ea831-163">So ändern Sie das Ziel-.NET Framework in einem Visual C#-Projekt</span><span class="sxs-lookup"><span data-stu-id="ea831-163">To change the target .NET Framework in a Visual C# project</span></span>  
  
1.  <span data-ttu-id="ea831-164">In **Projektmappen-Explorer**mit der rechten Maustaste auf den Projektnamen, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="ea831-164">In **Solution Explorer**, right-click the project name and then click **Properties**.</span></span>  
  
     <span data-ttu-id="ea831-165">Das Eigenschaftenfenster für die Anwendung wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ea831-165">The properties window for the application is displayed.</span></span>  
  
2.  <span data-ttu-id="ea831-166">Klicken Sie auf die Registerkarte **Anwendung** .</span><span class="sxs-lookup"><span data-stu-id="ea831-166">Click the **Application** tab.</span></span>  
  
3.  <span data-ttu-id="ea831-167">In der **Zielframework** Liste [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ea831-167">In the **Target framework** list, select [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span> <span data-ttu-id="ea831-168">(Wählen Sie nicht **.NET Framework 4 Client Profile**.)</span><span class="sxs-lookup"><span data-stu-id="ea831-168">(Do not select **.NET Framework 4 Client Profile**.)</span></span>  
  
4.  <span data-ttu-id="ea831-169">Fügen Sie einen Verweis auf die caching-Assembly hinzu, durch die folgenden Schritte:</span><span class="sxs-lookup"><span data-stu-id="ea831-169">Add a reference to the caching assembly by following these steps:</span></span>  
  
    1.  <span data-ttu-id="ea831-170">Mit der rechten Maustaste die **Verweise** Ordner, und klicken Sie dann auf **Verweis hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="ea831-170">Right-click the **References** folder and then click **Add Reference**.</span></span>  
  
    2.  <span data-ttu-id="ea831-171">Wählen Sie die **.NET** Registerkarte `System.Runtime.Caching`, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="ea831-171">Select the **.NET** tab, select `System.Runtime.Caching`, and then click **OK**.</span></span>  
  
## <a name="adding-a-button-to-the-wpf-window"></a><span data-ttu-id="ea831-172">Hinzufügen einer Schaltfläche zum WPF-Fenster</span><span class="sxs-lookup"><span data-stu-id="ea831-172">Adding a Button to the WPF Window</span></span>  
 <span data-ttu-id="ea831-173">Als Nächstes fügen Sie ein Button-Steuerelement und erstellen Sie einen Ereignishandler für der Schaltfläche `Click` Ereignis.</span><span class="sxs-lookup"><span data-stu-id="ea831-173">Next, you will add a button control and create an event handler for the button's `Click` event.</span></span> <span data-ttu-id="ea831-174">Später fügen Sie Code hinzu, wenn Sie die Schaltfläche klicken, den Inhalt der Textdatei zwischengespeichert und angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="ea831-174">Later you will add code to so when you click the button, the contents of the text file are cached and displayed.</span></span>  
  
#### <a name="to-add-a-button-control"></a><span data-ttu-id="ea831-175">So fügen Sie ein Button-Steuerelement hinzu</span><span class="sxs-lookup"><span data-stu-id="ea831-175">To add a button control</span></span>  
  
1.  <span data-ttu-id="ea831-176">In **Projektmappen-Explorer**, doppelklicken Sie auf die Datei "MainWindow.xaml", um ihn zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="ea831-176">In **Solution Explorer**, double-click the MainWindow.xaml file to open it.</span></span>  
  
2.  <span data-ttu-id="ea831-177">Aus der **Toolbox**unter **WPF-Standardsteuerelementen**, ziehen Sie eine `Button` die Steuerung an die `MainWindow` Fenster.</span><span class="sxs-lookup"><span data-stu-id="ea831-177">From the **Toolbox**, under **Common WPF Controls**, drag a `Button` control to the `MainWindow` window.</span></span>  
  
3.  <span data-ttu-id="ea831-178">In der **Eigenschaften** legen die `Content` Eigenschaft von der `Button` die Steuerung an **Cache abrufen**.</span><span class="sxs-lookup"><span data-stu-id="ea831-178">In the **Properties** window, set the `Content` property of the `Button` control to **Get Cache**.</span></span>  
  
## <a name="initializing-the-cache-and-caching-an-entry"></a><span data-ttu-id="ea831-179">Initialisieren des Caches und Zwischenspeichern eines Eintrags</span><span class="sxs-lookup"><span data-stu-id="ea831-179">Initializing the Cache and Caching an Entry</span></span>  
 <span data-ttu-id="ea831-180">Anschließend fügen Sie den Code, um die folgenden Aufgaben ausführen:</span><span class="sxs-lookup"><span data-stu-id="ea831-180">Next, you will add the code to perform the following tasks:</span></span>  
  
-   <span data-ttu-id="ea831-181">Erstellen Sie eine Instanz der Cacheklasse – d. h., instanziieren Sie ein neues <xref:System.Runtime.Caching.MemoryCache> Objekt.</span><span class="sxs-lookup"><span data-stu-id="ea831-181">Create an instance of the cache class—that is, you will instantiate a new <xref:System.Runtime.Caching.MemoryCache> object.</span></span>  
  
-   <span data-ttu-id="ea831-182">Gibt an, dass der Cache verwendet einen <xref:System.Runtime.Caching.HostFileChangeMonitor> Objekt zum Überwachen von Änderungen in der Textdatei.</span><span class="sxs-lookup"><span data-stu-id="ea831-182">Specify that the cache uses a <xref:System.Runtime.Caching.HostFileChangeMonitor> object to monitor changes in the text file.</span></span>  
  
-   <span data-ttu-id="ea831-183">Lesen Sie die Textdatei, und sein Inhalt als einen Eintrag im Cache zwischengespeichert.</span><span class="sxs-lookup"><span data-stu-id="ea831-183">Read the text file and cache its contents as a cache entry.</span></span>  
  
-   <span data-ttu-id="ea831-184">Zeigt den Inhalt der zwischengespeicherten Textdatei.</span><span class="sxs-lookup"><span data-stu-id="ea831-184">Display the contents of the cached text file.</span></span>  
  
#### <a name="to-create-the-cache-object"></a><span data-ttu-id="ea831-185">Zum Erstellen des Cache-Objekts</span><span class="sxs-lookup"><span data-stu-id="ea831-185">To create the cache object</span></span>  
  
1.  <span data-ttu-id="ea831-186">Doppelklicken Sie auf die Schaltfläche, die Sie gerade hinzugefügt haben, um einen Ereignishandler in der Datei "MainWindow.Xaml.cs" oder "MainWindow.Xaml.vb" zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="ea831-186">Double-click the button you just added in order to create an event handler in the MainWindow.xaml.cs or MainWindow.Xaml.vb file.</span></span>  
  
2.  <span data-ttu-id="ea831-187">Fügen Sie am Anfang der Datei (vor der Klassendeklaration) die folgenden `Imports` (Visual Basic) oder `using` (c#)-Anweisungen:</span><span class="sxs-lookup"><span data-stu-id="ea831-187">At the top of the file (before the class declaration), add the following `Imports` (Visual Basic) or `using` (C#) statements:</span></span>  
  
    ```csharp  
    using System.Runtime.Caching;  
    using System.IO;  
    ```  
  
    ```vb  
    Imports System.Runtime.Caching  
    Imports System.IO  
    ```  
  
3.  <span data-ttu-id="ea831-188">Fügen Sie in der Ereignishandler den folgenden Code zum Instanziieren des Cache-Objekts:</span><span class="sxs-lookup"><span data-stu-id="ea831-188">In the event handler, add the following code to instantiate the cache object:</span></span>  
  
    ```csharp  
    ObjectCache cache = MemoryCache.Default;  
    ```  
  
    ```vb  
    Dim cache As ObjectCache = MemoryCache.Default  
    ```  
  
     <span data-ttu-id="ea831-189">Die <xref:System.Runtime.Caching.ObjectCache> ist eine integrierte Klasse, die einen in-Memory-Objektcache bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="ea831-189">The <xref:System.Runtime.Caching.ObjectCache> class is a built-in class that provides an in-memory object cache.</span></span>  
  
4.  <span data-ttu-id="ea831-190">Hinzufügen des folgenden Codes zum Lesen des Inhalts eines Cache-Eintrags mit dem Namen `filecontents`:</span><span class="sxs-lookup"><span data-stu-id="ea831-190">Add the following code to read the contents of a cache entry named `filecontents`:</span></span>  
  
    ```vb  
    Dim fileContents As String = TryCast(cache("filecontents"), String)  
    ```  
  
    ```csharp  
    string fileContents = cache["filecontents"] as string;  
    ```  
  
5.  <span data-ttu-id="ea831-191">Fügen Sie den folgenden Code zum Überprüfen, ob der Cacheeintrag mit dem Namen `filecontents` vorhanden ist:</span><span class="sxs-lookup"><span data-stu-id="ea831-191">Add the following code to check whether the cache entry named `filecontents` exists:</span></span>  
  
    ```vb  
    If fileContents Is Nothing Then  
  
    End If  
    ```  
  
    ```csharp  
    if (fileContents == null)  
    {  
  
    }  
    ```  
  
     <span data-ttu-id="ea831-192">Der angegebene Cacheeintrag nicht vorhanden ist, müssen Lesen die Textdatei und als einen Cacheeintrag in den Cache hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="ea831-192">If the specified cache entry does not exist, you must read the text file and add it as a cache entry to the cache.</span></span>  
  
6.  <span data-ttu-id="ea831-193">In der `if/then` blockieren, fügen Sie den folgenden Code zum Erstellen eines neuen <xref:System.Runtime.Caching.CacheItemPolicy> Objekt, das angibt, dass nach 10 Sekunden der Cacheeintrag abläuft.</span><span class="sxs-lookup"><span data-stu-id="ea831-193">In the `if/then` block, add the following code to create a new <xref:System.Runtime.Caching.CacheItemPolicy> object that specifies that the cache entry expires after 10 seconds.</span></span>  
  
    ```vb  
    Dim policy As New CacheItemPolicy()  
    policy.AbsoluteExpiration = DateTimeOffset.Now.AddSeconds(10.0)  
    ```  
  
    ```csharp  
    CacheItemPolicy policy = new CacheItemPolicy();  
    policy.AbsoluteExpiration = DateTimeOffset.Now.AddSeconds(10.0);  
    ```  
  
     <span data-ttu-id="ea831-194">Wenn keine Entfernung oder den Ablauf von Informationen bereitgestellt wird, ist die Standardeinstellung <xref:System.Runtime.Caching.ObjectCache.InfiniteAbsoluteExpiration>, was bedeutet, dass die Einträge im Cache nur auf einem absoluten Zeitpunkt nie basierend ablaufen.</span><span class="sxs-lookup"><span data-stu-id="ea831-194">If no eviction or expiration information is provided, the default is <xref:System.Runtime.Caching.ObjectCache.InfiniteAbsoluteExpiration>, which means the cache entries never expire based only on an absolute time.</span></span> <span data-ttu-id="ea831-195">Stattdessen ablaufen Cacheeinträge nur, wenn Arbeitsspeicher vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="ea831-195">Instead, cache entries expire only when there is memory pressure.</span></span> <span data-ttu-id="ea831-196">Als bewährte Methode sollten Sie entweder ein absoluter oder ein Wetterseite Ablauf immer explizit bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="ea831-196">As a best practice, you should always explicitly provide either an absolute or a siding expiration.</span></span>  
  
7.  <span data-ttu-id="ea831-197">Innerhalb der `if/then` blockieren und gemäß den Code, die Sie im vorherigen Schritt hinzugefügt haben, fügen Sie den folgenden Code zum Erstellen einer Auflistung für die Dateipfade, die zur Überwachung sowie den Pfad der Textdatei, die Auflistung hinzugefügt werden sollen:</span><span class="sxs-lookup"><span data-stu-id="ea831-197">Inside the `if/then` block and following the code you added in the previous step, add the following code to create a collection for the file paths that you want to monitor, and to add the path of the text file to the collection:</span></span>  
  
    ```vb  
    Dim filePaths As New List(Of String)()  
    filePaths.Add("c:\cache\cacheText.txt")  
    ```  
  
    ```csharp  
    List<string> filePaths = new List<string>();  
    filePaths.Add("c:\\cache\\cacheText.txt");  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="ea831-198">Die Textdatei, die Sie verwenden möchten ist nicht `c:\cache\cacheText.txt`, geben Sie den Pfad die Textdatei, die Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="ea831-198">If the text file you want to use is not `c:\cache\cacheText.txt`, specify the path where the text file is that you want to use.</span></span>  
  
8.  <span data-ttu-id="ea831-199">Hinter dem Code, die Sie im vorherigen Schritt hinzugefügt haben, fügen Sie den folgenden Code zum Hinzufügen einer neuen <xref:System.Runtime.Caching.HostFileChangeMonitor> Objekt, das die Auflistung der Änderung für den Cacheeintrag überwacht:</span><span class="sxs-lookup"><span data-stu-id="ea831-199">Following the code that you added in the previous step, add the following code to add a new <xref:System.Runtime.Caching.HostFileChangeMonitor> object to the collection of change monitors for the cache entry:</span></span>  
  
    ```vb  
    policy.ChangeMonitors.Add(New HostFileChangeMonitor(filePaths))  
    ```  
  
    ```csharp  
    policy.ChangeMonitors.Add(new HostFileChangeMonitor(filePaths));  
    ```  
  
     <span data-ttu-id="ea831-200">Die <xref:System.Runtime.Caching.HostFileChangeMonitor> -Objekt überwacht die Textdatei Pfad und den Cache benachrichtigt, wenn Änderungen auftreten.</span><span class="sxs-lookup"><span data-stu-id="ea831-200">The <xref:System.Runtime.Caching.HostFileChangeMonitor> object monitors the text file's path and notifies the cache if changes occur.</span></span> <span data-ttu-id="ea831-201">In diesem Beispiel wird der Cacheeintrag abläuft, wenn der Inhalt der Datei geändert.</span><span class="sxs-lookup"><span data-stu-id="ea831-201">In this example, the cache entry will expire if the content of the file changes.</span></span>  
  
9. <span data-ttu-id="ea831-202">Fügen Sie nach dem Code, der Sie im vorherigen Schritt hinzugefügt haben den folgenden Code zum Lesen des Inhalts der Textdatei hinzu:</span><span class="sxs-lookup"><span data-stu-id="ea831-202">Following the code that you added in the previous step, add the following code to read the contents of the text file:</span></span>  
  
    ```vb  
    fileContents = File.ReadAllText("c:\cache\cacheText.txt") & vbCrLf & DateTime.Now.ToString()  
    ```  
  
    ```csharp  
    fileContents = File.ReadAllText("c:\\cache\\cacheText.txt") + + "\n" + DateTime.Now;   
    ```  
  
     <span data-ttu-id="ea831-203">Der Datums- und Zeitstempel hinzugefügt, damit Sie werden sehen, wenn der Cacheeintrag abläuft.</span><span class="sxs-lookup"><span data-stu-id="ea831-203">The date and time timestamp is added so that you will be able to see when the cache entry expires.</span></span>  
  
10. <span data-ttu-id="ea831-204">Hinter dem Code, die Sie im vorherigen Schritt hinzugefügt haben, fügen Sie den folgenden Code zum Einfügen von den Inhalt der Datei in das Cacheobjekt als eine <xref:System.Runtime.Caching.CacheItem> Instanz:</span><span class="sxs-lookup"><span data-stu-id="ea831-204">Following the code that you added in the previous step, add the following code to insert the contents of the file into the cache object as a <xref:System.Runtime.Caching.CacheItem> instance:</span></span>  
  
    ```vb  
    cache.Set("filecontents", fileContents, policy)  
    ```  
  
    ```csharp  
    cache.Set("filecontents", fileContents, policy);  
    ```  
  
     <span data-ttu-id="ea831-205">Geben Sie Informationen wie der Cacheeintrag soll, indem übergeben entfernt werden der <xref:System.Runtime.Caching.CacheItemPolicy> -Objekt, das Sie zuvor erstellt, als Parameter haben.</span><span class="sxs-lookup"><span data-stu-id="ea831-205">You specify information about how the cache entry should be evicted by passing the <xref:System.Runtime.Caching.CacheItemPolicy> object that you created earlier as a parameter.</span></span>  
  
11. <span data-ttu-id="ea831-206">Nach der `if/then` blockieren, fügen Sie folgenden Code aus, um den zwischengespeicherten Dateiinhalt in einem Meldungsfeld anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="ea831-206">After the `if/then` block, add the following code to display the cached file content in a message box:</span></span>  
  
    ```vb  
    MessageBox.Show(fileContents)  
    ```  
  
    ```csharp  
    MessageBox.Show(fileContents);  
    ```  
  
12. <span data-ttu-id="ea831-207">In der **erstellen** Menü klicken Sie auf **"WPFCaching erstellen"** zum Erstellen des Projekts.</span><span class="sxs-lookup"><span data-stu-id="ea831-207">In the **Build** menu, click **Build WPFCaching** to build your project.</span></span>  
  
## <a name="testing-caching-in-the-wpf-application"></a><span data-ttu-id="ea831-208">Testen der Zwischenspeicherung in der WPF-Anwendung</span><span class="sxs-lookup"><span data-stu-id="ea831-208">Testing Caching in the WPF Application</span></span>  
 <span data-ttu-id="ea831-209">Sie können nun die Anwendung testen.</span><span class="sxs-lookup"><span data-stu-id="ea831-209">You can now test the application.</span></span>  
  
#### <a name="to-test-caching-in-the-wpf-application"></a><span data-ttu-id="ea831-210">So testen Sie caching in der WPF-Anwendung</span><span class="sxs-lookup"><span data-stu-id="ea831-210">To test caching in the WPF application</span></span>  
  
1.  <span data-ttu-id="ea831-211">Drücken Sie STRG+F5, um die Anwendung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="ea831-211">Press CTRL+F5 to run the application.</span></span>  
  
     <span data-ttu-id="ea831-212">Die `MainWindow` Fenster wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ea831-212">The `MainWindow` window is displayed.</span></span>  
  
2.  <span data-ttu-id="ea831-213">Klicken Sie auf **Cache abrufen**.</span><span class="sxs-lookup"><span data-stu-id="ea831-213">Click **Get Cache**.</span></span>  
  
     <span data-ttu-id="ea831-214">Zwischengespeicherte Inhalt aus der Textdatei wird in einem Meldungsfeld angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ea831-214">The cached content from the text file is displayed in a message box.</span></span> <span data-ttu-id="ea831-215">Beachten Sie den Zeitstempel der Datei.</span><span class="sxs-lookup"><span data-stu-id="ea831-215">Notice the timestamp on the file.</span></span>  
  
3.  <span data-ttu-id="ea831-216">Das Meldungsfeld zu schließen, und klicken Sie dann auf **Cache abrufen** erneut**.**</span><span class="sxs-lookup"><span data-stu-id="ea831-216">Close the message box and then click **Get Cache** again**.**</span></span>  
  
     <span data-ttu-id="ea831-217">Der Zeitstempel ist unverändert.</span><span class="sxs-lookup"><span data-stu-id="ea831-217">The timestamp is unchanged.</span></span> <span data-ttu-id="ea831-218">Dies gibt an, dass zwischengespeicherte Inhalt angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="ea831-218">This indicates the cached content is displayed.</span></span>  
  
4.  <span data-ttu-id="ea831-219">Warten Sie mindestens 10 Sekunden festzulegen, und klicken Sie dann auf **Cache abrufen** erneut aus.</span><span class="sxs-lookup"><span data-stu-id="ea831-219">Wait 10 seconds or more and then click **Get Cache** again.</span></span>  
  
     <span data-ttu-id="ea831-220">Dieses Mal wird ein neuer Zeitstempel angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ea831-220">This time a new timestamp is displayed.</span></span> <span data-ttu-id="ea831-221">Dies gibt an, dass die Richtlinie des Eintrags im Cache ablaufen lassen und neue zwischengespeicherte Inhalte angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="ea831-221">This indicates that the policy let the cache entry expire and that new cached content is displayed.</span></span>  
  
5.  <span data-ttu-id="ea831-222">Öffnen Sie in einem Text-Editor die Textdatei, die Sie erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="ea831-222">In a text editor, open the text file that you created.</span></span> <span data-ttu-id="ea831-223">Nehmen Sie Änderungen noch nicht.</span><span class="sxs-lookup"><span data-stu-id="ea831-223">Do not make any changes yet.</span></span>  
  
6.  <span data-ttu-id="ea831-224">Das Meldungsfeld zu schließen, und klicken Sie dann auf **Cache abrufen** erneut**.**</span><span class="sxs-lookup"><span data-stu-id="ea831-224">Close the message box and then click **Get Cache** again**.**</span></span>  
  
     <span data-ttu-id="ea831-225">Beachten Sie den Zeitstempel erneut ein.</span><span class="sxs-lookup"><span data-stu-id="ea831-225">Notice the timestamp again.</span></span>  
  
7.  <span data-ttu-id="ea831-226">Nehmen Sie eine Änderung in der Textdatei, und speichern Sie die Datei.</span><span class="sxs-lookup"><span data-stu-id="ea831-226">Make a change to the text file and then save the file.</span></span>  
  
8.  <span data-ttu-id="ea831-227">Das Meldungsfeld zu schließen, und klicken Sie dann auf **Cache abrufen** erneut aus.</span><span class="sxs-lookup"><span data-stu-id="ea831-227">Close the message box and then click **Get Cache** again.</span></span>  
  
     <span data-ttu-id="ea831-228">Das Meldungsfeld enthält des aktualisierten Inhalts aus der Textdatei und einen neuen Zeitstempel.</span><span class="sxs-lookup"><span data-stu-id="ea831-228">This message box contains the updated content from the text file and a new timestamp.</span></span> <span data-ttu-id="ea831-229">Dies gibt an, dass der Hostdatei geändert Monitor der Cacheeintrag entfernt sofort, wenn Sie die Datei geändert haben, obwohl das absolute Timeout nicht abgelaufen ist.</span><span class="sxs-lookup"><span data-stu-id="ea831-229">This indicates that the host-file change monitor evicted the cache entry immediately when you changed the file, even though the absolute timeout period had not expired.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ea831-230">Sie können die Entfernungszeit auf 20 Sekunden oder mehr zusätzlichen Zeitaufwand für das Sie in der Datei ändern zu erhöhen.</span><span class="sxs-lookup"><span data-stu-id="ea831-230">You can increase the eviction time to 20 seconds or more to allow more time for you to make a change in the file.</span></span>  
  
## <a name="code-example"></a><span data-ttu-id="ea831-231">Codebeispiel</span><span class="sxs-lookup"><span data-stu-id="ea831-231">Code Example</span></span>  
 <span data-ttu-id="ea831-232">Nachdem Sie diese exemplarische Vorgehensweise abgeschlossen haben, wird der Code für das Projekt erstellten im folgende Beispiel entsprechen.</span><span class="sxs-lookup"><span data-stu-id="ea831-232">After you have completed this walkthrough, the code for the project you created will resemble the following example.</span></span>  
  
 [!code-csharp[CachingWPFApplications#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CachingWPFApplications/CSharp/MainWindow.xaml.cs#1)]
 [!code-vb[CachingWPFApplications#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CachingWPFApplications/VisualBasic/MainWindow.xaml.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="ea831-233">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ea831-233">See Also</span></span>  
 <xref:System.Runtime.Caching.MemoryCache>  
 <xref:System.Runtime.Caching.ObjectCache>  
 <xref:System.Runtime.Caching>  
 [<span data-ttu-id="ea831-234">Caching in .NET Framework Applications (Caching in .NET Framework-Anwendungen)</span><span class="sxs-lookup"><span data-stu-id="ea831-234">Caching in .NET Framework Applications</span></span>](../../../../docs/framework/performance/caching-in-net-framework-applications.md)
