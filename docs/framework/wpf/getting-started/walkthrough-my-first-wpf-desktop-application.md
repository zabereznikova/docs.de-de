---
title: 'Exemplarische Vorgehensweise: Meine erste WPF-Desktopanwendung'
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
- getting started [WPF], WPF
- WPF [WPF], getting started
ms.assetid: b96bed40-8946-4285-8fe4-88045ab854ed
caps.latest.revision: "71"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 16ed99181f8462e805638b5d3881464b16f21177
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
---
# <a name="walkthrough-my-first-wpf-desktop-application"></a><span data-ttu-id="98044-102">Exemplarische Vorgehensweise: Meine erste WPF-Desktopanwendung</span><span class="sxs-lookup"><span data-stu-id="98044-102">Walkthrough: My first WPF desktop application</span></span>
<span data-ttu-id="98044-103">In dieser exemplarischen Vorgehensweise bietet eine Einführung in die Entwicklung einer [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] Anwendung, die die Elemente enthält, die für die meisten gelten [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] Anwendungen: [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Markup, CodeBehind, Anwendungsdefinitionen, Steuerelemente, Layout, die Datenbindung und Stile.</span><span class="sxs-lookup"><span data-stu-id="98044-103">This walkthrough provides an introduction to the development of a [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] application that includes the elements that are common to most [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] applications: [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] markup, code-behind, application definitions, controls, layout, data binding, and styles.</span></span> 
  
 <span data-ttu-id="98044-104">Diese exemplarische Vorgehensweise führt Sie durch die Entwicklung einer einfachen [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] Anwendung mithilfe der folgenden Schritte.</span><span class="sxs-lookup"><span data-stu-id="98044-104">This walkthrough guides you through the development of a simple [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] application using the following steps.</span></span> 
  
-   <span data-ttu-id="98044-105">Definieren von [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] zum Entwerfen der Darstellung der Anwendung [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].</span><span class="sxs-lookup"><span data-stu-id="98044-105">Defining [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] to design the appearance of the application's [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].</span></span> 
  
-   <span data-ttu-id="98044-106">Schreiben von Code, um das Verhalten der Anwendung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="98044-106">Writing code to build the application's behavior.</span></span> 
  
-   <span data-ttu-id="98044-107">Erstellen einer Anwendungsdefinition, um die Anwendung zu verwalten</span><span class="sxs-lookup"><span data-stu-id="98044-107">Creating an application definition to manage the application.</span></span> 
  
-   <span data-ttu-id="98044-108">Hinzufügen von Steuerelementen und erstellen Sie das Layout die Anwendung zusammengesetzt [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].</span><span class="sxs-lookup"><span data-stu-id="98044-108">Adding controls and creating the layout to compose the application [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].</span></span> 
  
-   <span data-ttu-id="98044-109">Erstellen Formate, um eine konsistente Darstellung in einer Anwendungsverzeichnis erstellen [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].</span><span class="sxs-lookup"><span data-stu-id="98044-109">Creating styles to create a consistent appearance throughout an application's [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].</span></span> 
  
-   <span data-ttu-id="98044-110">Binden der [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Auffüllen mit Daten, sowohl die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] von Daten- und Beibehalten der Daten und [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] synchronisiert.</span><span class="sxs-lookup"><span data-stu-id="98044-110">Binding the [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] to data to both populate the [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] from data and keep the data and [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] synchronized.</span></span> 
  
 <span data-ttu-id="98044-111">Am Ende dieser exemplarischen Vorgehensweise, Sie werden erstellt haben, eine eigenständige [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] Anwendung, die Benutzern ermöglicht, Ausgabenberichte für ausgewählte Benutzer anzeigen.</span><span class="sxs-lookup"><span data-stu-id="98044-111">By the end of the walkthrough, you will have built a standalone [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] application that allows users to view expense reports for selected people.</span></span> <span data-ttu-id="98044-112">Die Anwendung besteht aus mehreren [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] Seiten, die in einem Fenster im Webbrowserstil gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="98044-112">The application will be composed of several [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] pages that are hosted in a browser-style window.</span></span> 
  
 <span data-ttu-id="98044-113">Der Beispielcode, der verwendet wird, erstellen Sie in dieser exemplarischen Vorgehensweise steht sowohl für [!INCLUDE[TLA#tla_visualb](../../../../includes/tlasharptla-visualb-md.md)] und [!INCLUDE[TLA#tla_cshrp](../../../../includes/tlasharptla-cshrp-md.md)] am [Einführung zum Erstellen von WPF-Anwendungen](http://go.microsoft.com/fwlink/?LinkID=160008).</span><span class="sxs-lookup"><span data-stu-id="98044-113">The sample code that is used to build this walkthrough is available for both [!INCLUDE[TLA#tla_visualb](../../../../includes/tlasharptla-visualb-md.md)] and [!INCLUDE[TLA#tla_cshrp](../../../../includes/tlasharptla-cshrp-md.md)] at  [Introduction to Building WPF Applications](http://go.microsoft.com/fwlink/?LinkID=160008).</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="98044-114">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="98044-114">Prerequisites</span></span>  

- [!INCLUDE[vs_dev11_long](../../../../includes/vs-dev11-long-md.md)]<span data-ttu-id="98044-115"> oder höher</span><span class="sxs-lookup"><span data-stu-id="98044-115"> or later</span></span>

<span data-ttu-id="98044-116">Weitere Informationen zum Installieren der neuesten Version von Visual Studio finden Sie unter [installieren Sie Visual Studio](/visualstudio/install/install-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="98044-116">For more information about installing the latest version of Visual Studio, see [Install Visual Studio](/visualstudio/install/install-visual-studio).</span></span>
  
## <a name="creating-the-application-project"></a><span data-ttu-id="98044-117">Erstellen des Anwendungsprojekts</span><span class="sxs-lookup"><span data-stu-id="98044-117">Creating the application project</span></span>  
 <span data-ttu-id="98044-118">n diesem Abschnitt erstellen Sie die Anwendungsstruktur, die eine Anwendungsdefinition, zwei Seiten und ein Bild enthält.</span><span class="sxs-lookup"><span data-stu-id="98044-118">In this section, you create the application infrastructure, which includes an application definition, two pages, and an image.</span></span> 
  
1. <span data-ttu-id="98044-119">Erstellen Sie ein neues WPF-Anwendungsprojekt in Visual Basic oder Visual C# mit dem Namen `ExpenseIt`.</span><span class="sxs-lookup"><span data-stu-id="98044-119">Create a new WPF Application project in Visual Basic or Visual C# named `ExpenseIt`.</span></span> <span data-ttu-id="98044-120">Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen eines neuen WPF-Anwendungsprojekts](http://msdn.microsoft.com/library/1f6aea7a-33e1-4d3f-8555-1daa42e95d82).</span><span class="sxs-lookup"><span data-stu-id="98044-120">For more information, see [How to: Create a New WPF Application Project](http://msdn.microsoft.com/library/1f6aea7a-33e1-4d3f-8555-1daa42e95d82).</span></span> 
  
    > [!NOTE]
    >  <span data-ttu-id="98044-121">Diese exemplarische Vorgehensweise verwendet die <xref:System.Windows.Controls.DataGrid> Steuerelement, das in .NET Framework 4 verfügbar.</span><span class="sxs-lookup"><span data-stu-id="98044-121">This walkthrough uses the <xref:System.Windows.Controls.DataGrid> control that is available in the .NET Framework 4.</span></span> <span data-ttu-id="98044-122">Stellen Sie sicher, dass Ihr Projekt auf .NET Framework 4 abzielt oder höher.</span><span class="sxs-lookup"><span data-stu-id="98044-122">Be sure that your project targets the .NET Framework 4 or later.</span></span> <span data-ttu-id="98044-123">Weitere Informationen finden Sie unter[wie: eine Version von .NET Framework als Ziel](/visualstudio/ide/how-to-target-a-version-of-the-dotnet-framework).</span><span class="sxs-lookup"><span data-stu-id="98044-123">For more information, see[How to: Target a Version of the .NET Framework](/visualstudio/ide/how-to-target-a-version-of-the-dotnet-framework).</span></span> 
  
2. <span data-ttu-id="98044-124">Öffnen Sie „Application.xaml“ (Visual Basic) oder „App.xaml“ (C#).</span><span class="sxs-lookup"><span data-stu-id="98044-124">Open Application.xaml (Visual Basic) or App.xaml (C#).</span></span> 
  
     <span data-ttu-id="98044-125">Dies [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] -Datei definiert eine [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] Anwendung und alle Ressourcen der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="98044-125">This [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file defines a [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] application and any application resources.</span></span> <span data-ttu-id="98044-126">Sie verwenden diese Datei auch an die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] automatisch das wird angezeigt, wenn die Anwendung gestartet wird; in diesem Fall "MainWindow.xaml".</span><span class="sxs-lookup"><span data-stu-id="98044-126">You also use this file to specify the [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] that automatically shows when the application starts; in this case, MainWindow.xaml.</span></span> 
  
     <span data-ttu-id="98044-127">Ihre [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] sollte in Visual Basic wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="98044-127">Your [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] should look like this in Visual Basic:</span></span>  
  
    [!code-xaml[ExpenseIt#1_A](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/Application.xaml#1_a)]  
  
     <span data-ttu-id="98044-128">Oder in C# wie folgt:</span><span class="sxs-lookup"><span data-stu-id="98044-128">Or like this in C#:</span></span>  
  
    [!code-xaml[ExpenseIt#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/App.xaml#1)]  
  
3. <span data-ttu-id="98044-129">Öffnen Sie „MainWindow.xaml“.</span><span class="sxs-lookup"><span data-stu-id="98044-129">Open MainWindow.xaml.</span></span> 
  
     <span data-ttu-id="98044-130">Dies [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Datei wird im Hauptfenster der Anwendung und zeigt den Inhalt in Seiten erstellt.</span><span class="sxs-lookup"><span data-stu-id="98044-130">This [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file is the main window of your application and displays content created in pages.</span></span> <span data-ttu-id="98044-131">Die <xref:System.Windows.Window> Klasse definiert die Eigenschaften eines Fensters, z. B. Titel, Größe oder Symbol, und behandelt Ereignisse, z. B. Schließen oder ausblenden.</span><span class="sxs-lookup"><span data-stu-id="98044-131">The <xref:System.Windows.Window> class defines the properties of a window, such as its title, size, or icon, and handles events, such as closing or hiding.</span></span> 
  
4. <span data-ttu-id="98044-132">Ändern der <xref:System.Windows.Window> Element zu einem <xref:System.Windows.Navigation.NavigationWindow>.</span><span class="sxs-lookup"><span data-stu-id="98044-132">Change the <xref:System.Windows.Window> element to a <xref:System.Windows.Navigation.NavigationWindow>.</span></span> 
  
     <span data-ttu-id="98044-133">Diese Anwendung navigiert je nach Benutzerinteraktion zu anderem Inhalt.</span><span class="sxs-lookup"><span data-stu-id="98044-133">This application will navigate to different content depending on the user interaction.</span></span> <span data-ttu-id="98044-134">Aus diesem Grund für den Hauptknoten <xref:System.Windows.Window> muss geändert werden, um eine <xref:System.Windows.Navigation.NavigationWindow>.</span><span class="sxs-lookup"><span data-stu-id="98044-134">Therefore, the main <xref:System.Windows.Window> needs to be changed to a <xref:System.Windows.Navigation.NavigationWindow>.</span></span> <span data-ttu-id="98044-135"><xref:System.Windows.Navigation.NavigationWindow>erbt alle Eigenschaften des <xref:System.Windows.Window>.</span><span class="sxs-lookup"><span data-stu-id="98044-135"><xref:System.Windows.Navigation.NavigationWindow> inherits all the properties of <xref:System.Windows.Window>.</span></span> <span data-ttu-id="98044-136">Die <xref:System.Windows.Navigation.NavigationWindow> Element in der XAML-Datei erstellt eine Instanz der <xref:System.Windows.Navigation.NavigationWindow> Klasse.</span><span class="sxs-lookup"><span data-stu-id="98044-136">The <xref:System.Windows.Navigation.NavigationWindow> element in the XAML file creates an instance of the <xref:System.Windows.Navigation.NavigationWindow> class.</span></span> <span data-ttu-id="98044-137">Weitere Informationen finden Sie unter [Übersicht über die Navigation](../../../../docs/framework/wpf/app-development/navigation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="98044-137">For more information, see [Navigation Overview](../../../../docs/framework/wpf/app-development/navigation-overview.md).</span></span> 
  
5. <span data-ttu-id="98044-138">Ändern Sie die folgenden Eigenschaften auf der <xref:System.Windows.Navigation.NavigationWindow> Element:</span><span class="sxs-lookup"><span data-stu-id="98044-138">Change the following properties on the <xref:System.Windows.Navigation.NavigationWindow> element:</span></span>  
  
    -   <span data-ttu-id="98044-139">Legen Sie die <xref:System.Windows.Window.Title%2A> -Eigenschaft auf "ExpenseIt".</span><span class="sxs-lookup"><span data-stu-id="98044-139">Set the <xref:System.Windows.Window.Title%2A> property to "ExpenseIt".</span></span> 
  
    -   <span data-ttu-id="98044-140">Legen Sie die <xref:System.Windows.FrameworkElement.Width%2A> Eigenschaft auf 500 Pixel.</span><span class="sxs-lookup"><span data-stu-id="98044-140">Set the <xref:System.Windows.FrameworkElement.Width%2A> property to 500 pixels.</span></span> 
  
    -   <span data-ttu-id="98044-141">Legen Sie die <xref:System.Windows.FrameworkElement.Height%2A> Eigenschaft auf 350 Pixel.</span><span class="sxs-lookup"><span data-stu-id="98044-141">Set the <xref:System.Windows.FrameworkElement.Height%2A> property to 350 pixels.</span></span> 
  
    -   <span data-ttu-id="98044-142">Entfernen Sie die <xref:System.Windows.Controls.Grid> Elemente zwischen den <xref:System.Windows.Navigation.NavigationWindow> Tags.</span><span class="sxs-lookup"><span data-stu-id="98044-142">Remove the <xref:System.Windows.Controls.Grid> elements between the <xref:System.Windows.Navigation.NavigationWindow> tags.</span></span> 
  
     <span data-ttu-id="98044-143">Ihre [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] sollte in Visual Basic wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="98044-143">Your [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] should look like this in Visual Basic:</span></span>  
  
    [!code-xaml[ExpenseIt#2_A](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt/MainWindow.xaml#2_a)]  
  
     <span data-ttu-id="98044-144">Oder in C# wie folgt:</span><span class="sxs-lookup"><span data-stu-id="98044-144">Or like this in C#:</span></span>  
  
    [!code-xaml[ExpenseIt#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/MainWindow.xaml#2)]  
  
6. <span data-ttu-id="98044-145">Öffnen Sie „MainWindow.Xaml.vb“ bzw. „MainWindow.Xaml.cs“.</span><span class="sxs-lookup"><span data-stu-id="98044-145">Open MainWindow.xaml.vb or MainWindow.xaml.cs.</span></span> 
  
     <span data-ttu-id="98044-146">Bei dieser Datei handelt es sich um eine CodeBehind-Datei, die Code enthält, um die in „MainWindow.xaml“ deklarierten Ereignisse zu behandeln.</span><span class="sxs-lookup"><span data-stu-id="98044-146">This file is a code-behind file that contains code to handle the events declared in MainWindow.xaml.</span></span> <span data-ttu-id="98044-147">Diese Datei enthält eine partielle Klasse für das in XAML definierte Fenster.</span><span class="sxs-lookup"><span data-stu-id="98044-147">This file contains a partial class for the window defined in XAML.</span></span> 
  
7. <span data-ttu-id="98044-148">Wenn Sie c# verwenden, ändern Sie die `MainWindow` Klasse abgeleitet <xref:System.Windows.Navigation.NavigationWindow>.</span><span class="sxs-lookup"><span data-stu-id="98044-148">If you are using C#, change the `MainWindow` class to derive from <xref:System.Windows.Navigation.NavigationWindow>.</span></span> 
  
     <span data-ttu-id="98044-149">In Visual Basic geschieht dies automatisch, wenn Sie das Fenster in XAML ändern.</span><span class="sxs-lookup"><span data-stu-id="98044-149">In Visual Basic, this happens automatically when you change the window in XAML.</span></span> 
  
     <span data-ttu-id="98044-150">Ihr Code sollte wie folgt aussehen.</span><span class="sxs-lookup"><span data-stu-id="98044-150">Your code should look like this.</span></span> 
  
    [!code-csharp[ExpenseIt#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/MainWindow.xaml.cs#3)]
    [!code-vb[ExpenseIt#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/MainWindow.xaml.vb#3)]  
  
## <a name="adding-files-to-the-application"></a><span data-ttu-id="98044-151">Hinzufügen von Dateien zur Anwendung</span><span class="sxs-lookup"><span data-stu-id="98044-151">Adding files to the application</span></span>  
 <span data-ttu-id="98044-152">In diesem Abschnitt fügen Sie der Anwendung zwei Seiten und ein Bild hinzu.</span><span class="sxs-lookup"><span data-stu-id="98044-152">In this section, you add two pages and an image to the application.</span></span> 
  
1. <span data-ttu-id="98044-153">Fügen Sie eine neue Seite (WPF) auf das Projekt mit dem Namen `ExpenseItHome.xaml`.</span><span class="sxs-lookup"><span data-stu-id="98044-153">Add a new Page (WPF) to the project named `ExpenseItHome.xaml`.</span></span> <span data-ttu-id="98044-154">Weitere Informationen finden Sie unter [wie: Hinzufügen neuer Elemente zu einem WPF-Projekt](http://msdn.microsoft.com/library/17e6b238-fc32-4385-98ef-2f66ca09d9ad).</span><span class="sxs-lookup"><span data-stu-id="98044-154">For more information, see [How to: Add New Items to a WPF Project](http://msdn.microsoft.com/library/17e6b238-fc32-4385-98ef-2f66ca09d9ad).</span></span> 
  
     <span data-ttu-id="98044-155">Diese Seite ist die erste Seite, das beim Anwendungsstart angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="98044-155">This page is the first page that is displayed when the application is launched.</span></span> <span data-ttu-id="98044-156">Sie zeigt eine Liste von Personen, aus denen ein Benutzer eine Person auswählen kann, um die zugehörige Spesenabrechnung anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="98044-156">It will show a list of people from which a user can select a person to show an expense report for.</span></span> 
  
2. <span data-ttu-id="98044-157">Öffnen Sie „ExpenseItHome.xaml“.</span><span class="sxs-lookup"><span data-stu-id="98044-157">Open ExpenseItHome.xaml.</span></span> 
  
3. <span data-ttu-id="98044-158">Legen Sie die <xref:System.Windows.Controls.Page.Title%2A> auf "ExpenseIt – Home".</span><span class="sxs-lookup"><span data-stu-id="98044-158">Set the <xref:System.Windows.Controls.Page.Title%2A> to "ExpenseIt - Home".</span></span> 
  
     <span data-ttu-id="98044-159">Ihre [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] sollte in Visual Basic wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="98044-159">Your [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] should look like this in Visual Basic:</span></span>  
  
    [!code-xaml[ExpenseIt#6_A](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml#6_a)]  
  
     <span data-ttu-id="98044-160">Oder in C# wie folgt:</span><span class="sxs-lookup"><span data-stu-id="98044-160">Or this in C#:</span></span>  
  
    [!code-xaml[ExpenseIt#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml#6)]  
  
4. <span data-ttu-id="98044-161">Öffnen Sie „MainWindow.xaml“.</span><span class="sxs-lookup"><span data-stu-id="98044-161">Open MainWindow.xaml.</span></span> 
  
5. <span data-ttu-id="98044-162">Legen Sie die <xref:System.Windows.Navigation.NavigationWindow.Source%2A> Eigenschaft auf die <xref:System.Windows.Navigation.NavigationWindow> auf "ExpenseItHome.xaml".</span><span class="sxs-lookup"><span data-stu-id="98044-162">Set the <xref:System.Windows.Navigation.NavigationWindow.Source%2A> property on the <xref:System.Windows.Navigation.NavigationWindow> to "ExpenseItHome.xaml".</span></span> 
  
     <span data-ttu-id="98044-163">Dadurch wird „ExpenseItHome.xaml“ als erste Seite festgelegt, die beim Start der Anwendung geöffnet wird.</span><span class="sxs-lookup"><span data-stu-id="98044-163">This sets ExpenseItHome.xaml to be the first page opened when the application starts.</span></span> <span data-ttu-id="98044-164">Ihre [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] sollte in Visual Basic wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="98044-164">Your [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] should look like this in Visual Basic:</span></span>  
  
    [!code-xaml[ExpenseIt#7_A](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/MainWindow.xaml#7_a)]  
  
     <span data-ttu-id="98044-165">Oder in C# wie folgt:</span><span class="sxs-lookup"><span data-stu-id="98044-165">Or this in C#:</span></span>  
  
    [!code-xaml[ExpenseIt#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/MainWindow.xaml#7)]  
  
6. <span data-ttu-id="98044-166">Fügen Sie eine neue Seite (WPF) auf das Projekt mit dem Namen `ExpenseReportPage.xaml`.</span><span class="sxs-lookup"><span data-stu-id="98044-166">Add a new Page (WPF) to the project named `ExpenseReportPage.xaml`.</span></span> 
  
     <span data-ttu-id="98044-167">Diese Seite zeigt die Spesenabrechnung für die Person an, die für „ExpenseItHome.xaml“ ausgewählt wird.</span><span class="sxs-lookup"><span data-stu-id="98044-167">This page will show the expense report for the person that is selected on ExpenseItHome.xaml.</span></span> 
  
7. <span data-ttu-id="98044-168">Öffnen Sie „ExpenseReportPage.xaml“.</span><span class="sxs-lookup"><span data-stu-id="98044-168">Open ExpenseReportPage.xaml.</span></span> 
  
8. <span data-ttu-id="98044-169">Legen Sie die <xref:System.Windows.Controls.Page.Title%2A> auf "ExpenseIt – View Expense".</span><span class="sxs-lookup"><span data-stu-id="98044-169">Set the <xref:System.Windows.Controls.Page.Title%2A> to "ExpenseIt - View Expense".</span></span> 
  
     <span data-ttu-id="98044-170">Ihre [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] sollte in Visual Basic wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="98044-170">Your [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] should look like this in Visual Basic:</span></span>  
  
    [!code-xaml[ExpenseIt#4_A](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml#4_a)]  
  
     <span data-ttu-id="98044-171">Oder in C# wie folgt:</span><span class="sxs-lookup"><span data-stu-id="98044-171">Or this in C#:</span></span>  
  
    [!code-xaml[ExpenseIt#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml#4)]  
  
9. <span data-ttu-id="98044-172">Öffnen Sie „ExpenseItHome.xaml.vb“ und „ExpenseReportPage.xaml.vb“ bzw. „ExpenseItHome.xaml.cs“ und „ExpenseReportPage.xaml.cs“.</span><span class="sxs-lookup"><span data-stu-id="98044-172">Open ExpenseItHome.xaml.vb and ExpenseReportPage.xaml.vb, or ExpenseItHome.xaml.cs and ExpenseReportPage.xaml.cs.</span></span> 
  
     <span data-ttu-id="98044-173">Wenn Sie eine neue Seitendatei erstellen, erstellt Visual Studio automatisch eine CodeBehind-Datei.</span><span class="sxs-lookup"><span data-stu-id="98044-173">When you create a new Page file, Visual Studio automatically creates a code behind file.</span></span> <span data-ttu-id="98044-174">Diese CodeBehind-Dateien behandeln die Logik zum Reagieren auf Benutzereingabe.</span><span class="sxs-lookup"><span data-stu-id="98044-174">These code-behind files handle the logic for responding to user input.</span></span> 
  
     <span data-ttu-id="98044-175">Ihr Code sollte wie folgt aussehen.</span><span class="sxs-lookup"><span data-stu-id="98044-175">Your code should look like this.</span></span> 
  
    [!code-csharp[ExpenseIt#2_5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml.cs#2_5)]
    [!code-vb[ExpenseIt#2_5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml.vb#2_5)]  
  
    [!code-csharp[ExpenseIt#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml.cs#5)]
    [!code-vb[ExpenseIt#5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml.vb#5)]  
  
10. <span data-ttu-id="98044-176">Fügen Sie dem Projekt ein Bild mit dem Namen „watermark.png“ hinzu.</span><span class="sxs-lookup"><span data-stu-id="98044-176">Add an image named watermark.png to the project.</span></span> <span data-ttu-id="98044-177">Sie können ein eigenes Bild erstellen oder die Datei aus dem Beispielcode kopieren.</span><span class="sxs-lookup"><span data-stu-id="98044-177">You can either create your own image, or copy the file from the sample code.</span></span> <span data-ttu-id="98044-178">Weitere Informationen finden Sie unter [NIB: Vorgehensweise: Hinzufügen von vorhandenen Elementen zu einem Projekt](http://msdn.microsoft.com/library/15f4cfb7-78ab-457f-9f14-099a25a6a2d3).</span><span class="sxs-lookup"><span data-stu-id="98044-178">For more information, see [NIB:How to: Add Existing Items to a Project](http://msdn.microsoft.com/library/15f4cfb7-78ab-457f-9f14-099a25a6a2d3).</span></span> 

## <a name="building-and-running-the-application"></a><span data-ttu-id="98044-179">Erstellen und Ausführen der Anwendung</span><span class="sxs-lookup"><span data-stu-id="98044-179">Building and running the application</span></span>  
 <span data-ttu-id="98044-180">In diesem Abschnitt wird die Anwendung erstellt und dann ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="98044-180">In this section, you build and run the application.</span></span> 
  
1. <span data-ttu-id="98044-181">Erstellen und Ausführen der Anwendung durch Drücken von F5 oder wählen Sie **Debuggen** aus der **Debuggen** Menü.</span><span class="sxs-lookup"><span data-stu-id="98044-181">Build and run the application by pressing F5 or select **Start Debugging** from the **Debug** menu.</span></span> 
  
     <span data-ttu-id="98044-182">Die folgende Abbildung zeigt die Anwendung mit der <xref:System.Windows.Navigation.NavigationWindow> Schaltflächen.</span><span class="sxs-lookup"><span data-stu-id="98044-182">The following illustration shows the application with the <xref:System.Windows.Navigation.NavigationWindow> buttons.</span></span> 
  
     <span data-ttu-id="98044-183">![Bildschirmabbildung für ExpenseIt-Beispiel](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure1.png "GettingStartedFigure1")</span><span class="sxs-lookup"><span data-stu-id="98044-183">![ExpenseIt sample screen shot](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure1.png "GettingStartedFigure1")</span></span>  
  
2. <span data-ttu-id="98044-184">Schließen Sie die Anwendung wieder [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="98044-184">Close the application to return to [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)].</span></span> 
  
## <a name="creating-the-layout"></a><span data-ttu-id="98044-185">Erstellen des Layouts</span><span class="sxs-lookup"><span data-stu-id="98044-185">Creating the layout</span></span>  
 <span data-ttu-id="98044-186">Layout bietet die Möglichkeit zum platzieren [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Elemente, und verwaltet auch die Größe und Position dieser Elemente bei einer [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] angepasst wird.</span><span class="sxs-lookup"><span data-stu-id="98044-186">Layout provides an ordered way to place [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] elements, and also manages the size and position of those elements when a [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] is resized.</span></span> <span data-ttu-id="98044-187">In der Regel erstellen Sie Layout mit einem der folgenden Layoutsteuerelemente:</span><span class="sxs-lookup"><span data-stu-id="98044-187">You typically create a layout with one of the following layout controls:</span></span>  
  
-   <xref:System.Windows.Controls.Canvas>  
  
-   <xref:System.Windows.Controls.DockPanel>  
  
-   <xref:System.Windows.Controls.Grid>  
  
-   <xref:System.Windows.Controls.StackPanel>  
  
-   <xref:System.Windows.Controls.VirtualizingStackPanel>  
  
-   <xref:System.Windows.Controls.WrapPanel>  
  
 <span data-ttu-id="98044-188">Jedes dieser Layoutsteuerelemente unterstützt einen speziellen Layouttyp für seine untergeordneten Elemente.</span><span class="sxs-lookup"><span data-stu-id="98044-188">Each of these layout controls supports a special type of layout for its child elements.</span></span> <span data-ttu-id="98044-189">Die Größe von „ExpenseIt“-Seiten kann geändert werden. Jede Seite verfügt über Elemente, die horizontal und vertikal neben anderen Elementen angeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="98044-189">ExpenseIt pages can be resized, and each page has elements that are arranged horizontally and vertically alongside other elements.</span></span> <span data-ttu-id="98044-190">Folglich die <xref:System.Windows.Controls.Grid> ist die ideale Layoutelement für die Anwendung.</span><span class="sxs-lookup"><span data-stu-id="98044-190">Consequently, the <xref:System.Windows.Controls.Grid> is the ideal layout element for the application.</span></span> 
  
> [!NOTE]
>  <span data-ttu-id="98044-191">Weitere Informationen zu <xref:System.Windows.Controls.Panel> Elemente finden Sie unter [Panels Overview](../../../../docs/framework/wpf/controls/panels-overview.md).</span><span class="sxs-lookup"><span data-stu-id="98044-191">For more information about <xref:System.Windows.Controls.Panel> elements, see [Panels Overview](../../../../docs/framework/wpf/controls/panels-overview.md).</span></span> <span data-ttu-id="98044-192">Weitere Informationen zum Layout finden Sie unter [Layout](../../../../docs/framework/wpf/advanced/layout.md).</span><span class="sxs-lookup"><span data-stu-id="98044-192">For more information about layout, see [Layout](../../../../docs/framework/wpf/advanced/layout.md).</span></span> 
  
 <span data-ttu-id="98044-193">Klicken Sie im Abschnitt erstellen Sie eine einspaltige Tabelle mit drei Zeilen und einen 10-Pixel-Rand durch Hinzufügen von Spalten- und Definitionen, um die <xref:System.Windows.Controls.Grid> in ExpenseItHome.xaml.</span><span class="sxs-lookup"><span data-stu-id="98044-193">In the section, you create a single-column table with three rows and a 10-pixel margin by adding column and row definitions to the <xref:System.Windows.Controls.Grid> in ExpenseItHome.xaml.</span></span> 
  
1. <span data-ttu-id="98044-194">Öffnen Sie „ExpenseItHome.xaml“.</span><span class="sxs-lookup"><span data-stu-id="98044-194">Open ExpenseItHome.xaml.</span></span> 
  
2. <span data-ttu-id="98044-195">Legen Sie die <xref:System.Windows.FrameworkElement.Margin%2A> Eigenschaft auf die <xref:System.Windows.Controls.Grid> -Elements auf "10,0,10,10" den linken, oberen, rechten und unteren Ränder.</span><span class="sxs-lookup"><span data-stu-id="98044-195">Set the <xref:System.Windows.FrameworkElement.Margin%2A> property on the <xref:System.Windows.Controls.Grid> element to "10,0,10,10" which corresponds to left, top, right and bottom margins.</span></span> 
  
3. <span data-ttu-id="98044-196">Fügen Sie die folgenden [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] zwischen den <xref:System.Windows.Controls.Grid> Tags aus, um die Zeilen- und Spaltendefinitionen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="98044-196">Add the following [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] between the <xref:System.Windows.Controls.Grid> tags to create the row and column definitions.</span></span> 
  
    [!code-xaml[ExpenseIt#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#8)]  
  
     <span data-ttu-id="98044-197">Die <xref:System.Windows.Controls.RowDefinition.Height%2A> von zwei Zeilen wird festgelegt <xref:System.Windows.GridLength.Auto%2A> was bedeutet, dass die Größe der Zeilen als Grundlage für den Inhalt in den Zeilen.</span><span class="sxs-lookup"><span data-stu-id="98044-197">The <xref:System.Windows.Controls.RowDefinition.Height%2A> of two rows is set to <xref:System.Windows.GridLength.Auto%2A> which means that the rows will be sized base on the content in the rows.</span></span> <span data-ttu-id="98044-198">Die Standardeinstellung <xref:System.Windows.Controls.RowDefinition.Height%2A> ist <xref:System.Windows.GridUnitType.Star> Sizing, was bedeutet, dass die Zeile eine gewichtete Proportion des verfügbaren Speicherplatzes.</span><span class="sxs-lookup"><span data-stu-id="98044-198">The default <xref:System.Windows.Controls.RowDefinition.Height%2A> is <xref:System.Windows.GridUnitType.Star> sizing, which means that the row will be a weighted proportion of the available space.</span></span> <span data-ttu-id="98044-199">Wenn z. B. zwei Zeilen jeweils eine Höhe von „\*“ haben, hat jede eine Höhe von der Hälfte des verfügbaren Platzes.</span><span class="sxs-lookup"><span data-stu-id="98044-199">For example if two rows each have a height of "\*", they will each have a height that is half of the available space.</span></span>  
  
     <span data-ttu-id="98044-200">Ihre <xref:System.Windows.Controls.Grid> sollte jetzt wie der folgende XAML-Code aussehen:</span><span class="sxs-lookup"><span data-stu-id="98044-200">Your <xref:System.Windows.Controls.Grid> should now look like the following XAML:</span></span>  
  
    [!code-xaml[ExpenseIt#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#9)]  
  
## <a name="adding-controls"></a><span data-ttu-id="98044-201">Hinzufügen von Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="98044-201">Adding controls</span></span>  
 <span data-ttu-id="98044-202">In diesem Abschnitt der Startseite [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] aktualisiert, um einer Liste der Personen anzuzeigen, dass Benutzer aus auswählen können, um die Ausgabenbericht für eine ausgewählte Person angezeigt.</span><span class="sxs-lookup"><span data-stu-id="98044-202">In this section, the home page [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] is updated to show a list of people that users can select from to show the expense report for a selected person.</span></span> <span data-ttu-id="98044-203">Steuerelemente sind Benutzeroberflächenobjekte, die Benutzern die Interaktion mit der Anwendung ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="98044-203">Controls are UI objects that allow users to interact with your application.</span></span> <span data-ttu-id="98044-204">Weitere Informationen finden Sie unter [Steuerelemente](../../../../docs/framework/wpf/controls/index.md).</span><span class="sxs-lookup"><span data-stu-id="98044-204">For more information, see [Controls](../../../../docs/framework/wpf/controls/index.md).</span></span> 
  
 <span data-ttu-id="98044-205">Zum Erstellen dieser [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], die folgenden Elemente ExpenseItHome.xaml hinzugefügt werden:</span><span class="sxs-lookup"><span data-stu-id="98044-205">To create this [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], the following elements are added to ExpenseItHome.xaml:</span></span>  
  
-   <span data-ttu-id="98044-206"><xref:System.Windows.Controls.ListBox>(für die Liste der Personen).</span><span class="sxs-lookup"><span data-stu-id="98044-206"><xref:System.Windows.Controls.ListBox> (for the list of people).</span></span> 
  
-   <span data-ttu-id="98044-207"><xref:System.Windows.Controls.Label>(für den List-Header).</span><span class="sxs-lookup"><span data-stu-id="98044-207"><xref:System.Windows.Controls.Label> (for the list header).</span></span> 
  
-   <span data-ttu-id="98044-208"><xref:System.Windows.Controls.Button>(um klicken, um die Ausgabenbericht für die Person anzuzeigen, die in der Liste ausgewählt ist).</span><span class="sxs-lookup"><span data-stu-id="98044-208"><xref:System.Windows.Controls.Button> (to click to view the expense report for the person that is selected in the list).</span></span> 
  
 <span data-ttu-id="98044-209">Jedes Steuerelement wird in einer Zeile platziert die <xref:System.Windows.Controls.Grid> durch Festlegen der <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> -Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="98044-209">Each control is placed in a row of the <xref:System.Windows.Controls.Grid> by setting the <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> attached property.</span></span> <span data-ttu-id="98044-210">Weitere Informationen über angefügte Eigenschaften finden Sie unter [Eigenschaftenübersicht angefügt](../../../../docs/framework/wpf/advanced/attached-properties-overview.md).</span><span class="sxs-lookup"><span data-stu-id="98044-210">For more information about attached properties, see [Attached Properties Overview](../../../../docs/framework/wpf/advanced/attached-properties-overview.md).</span></span> 
  
1. <span data-ttu-id="98044-211">Öffnen Sie „ExpenseItHome.xaml“.</span><span class="sxs-lookup"><span data-stu-id="98044-211">Open ExpenseItHome.xaml.</span></span> 
  
2. <span data-ttu-id="98044-212">Fügen Sie die folgenden [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] zwischen den <xref:System.Windows.Controls.Grid> Tags.</span><span class="sxs-lookup"><span data-stu-id="98044-212">Add the following [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] between the <xref:System.Windows.Controls.Grid> tags.</span></span> 
  
    [!code-xaml[ExpenseIt#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt4/ExpenseItHome.xaml#10)]  
  
3. <span data-ttu-id="98044-213">Erstellen Sie die Anwendung, und führen Sie sie aus.</span><span class="sxs-lookup"><span data-stu-id="98044-213">Build and run the application.</span></span> 
  
 <span data-ttu-id="98044-214">Die folgende Abbildung zeigt die Steuerelemente, die von der XAML in diesem Abschnitt erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="98044-214">The following illustration shows the controls that are created by the XAML in this section.</span></span> 
  
 <span data-ttu-id="98044-215">![Bildschirmabbildung für ExpenseIt-Beispiel](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure2.png "GettingStartedFigure2")</span><span class="sxs-lookup"><span data-stu-id="98044-215">![ExpenseIt sample screen shot](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure2.png "GettingStartedFigure2")</span></span>  
  
## <a name="adding-an-image-and-a-title"></a><span data-ttu-id="98044-216">Hinzufügen eines Bilds und einen Titel</span><span class="sxs-lookup"><span data-stu-id="98044-216">Adding an image and a title</span></span>  
 <span data-ttu-id="98044-217">In diesem Abschnitt der Startseite [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] mit ein Abbild und einen Seitentitel aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="98044-217">In this section, the home page [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] is updated with an image and a page title.</span></span> 
  
1. <span data-ttu-id="98044-218">Öffnen Sie „ExpenseItHome.xaml“.</span><span class="sxs-lookup"><span data-stu-id="98044-218">Open ExpenseItHome.xaml.</span></span> 
  
2. <span data-ttu-id="98044-219">Eine weitere Spalte zum Hinzufügen der <xref:System.Windows.Controls.Grid.ColumnDefinitions%2A> mit einer festen <xref:System.Windows.Controls.ColumnDefinition.Width%2A> von 230 Pixeln.</span><span class="sxs-lookup"><span data-stu-id="98044-219">Add another column to the <xref:System.Windows.Controls.Grid.ColumnDefinitions%2A> with a fixed <xref:System.Windows.Controls.ColumnDefinition.Width%2A> of 230 pixels.</span></span> 
  
    [!code-xaml[ExpenseIt#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#11)]  
  
3. <span data-ttu-id="98044-220">Hinzufügen zu einer anderen Zeile die <xref:System.Windows.Controls.Grid.RowDefinitions%2A>.</span><span class="sxs-lookup"><span data-stu-id="98044-220">Add another row to the <xref:System.Windows.Controls.Grid.RowDefinitions%2A>.</span></span> 
  
    [!code-xaml[ExpenseIt#11b](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#11b)]  
  
4. <span data-ttu-id="98044-221">Verschieben Sie die Steuerelemente in die zweite Spalte durch Festlegen von <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> auf 1.</span><span class="sxs-lookup"><span data-stu-id="98044-221">Move the controls to the second column by setting <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> to 1.</span></span> <span data-ttu-id="98044-222">Verschieben Sie jedes Steuerelement eine Zeile nach unten durch Erhöhen der <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> um 1.</span><span class="sxs-lookup"><span data-stu-id="98044-222">Move each control down a row, by increasing the <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> by 1.</span></span> 
  
    [!code-xaml[ExpenseIt#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#12)]  
  
5. <span data-ttu-id="98044-223">Legen Sie die <xref:System.Windows.Controls.Panel.Background%2A> von der <xref:System.Windows.Controls.Grid> auf die Bilddatei watermark.png sein.</span><span class="sxs-lookup"><span data-stu-id="98044-223">Set the <xref:System.Windows.Controls.Panel.Background%2A> of the <xref:System.Windows.Controls.Grid> to be the watermark.png image file.</span></span> 
  
    [!code-xaml[ExpenseIt#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#14)]  
  
6. <span data-ttu-id="98044-224">Bevor Sie die <xref:System.Windows.Controls.Border>, Hinzufügen einer <xref:System.Windows.Controls.Label> mit dem Inhalt "View Expense Report" als Titel der Seite.</span><span class="sxs-lookup"><span data-stu-id="98044-224">Before the <xref:System.Windows.Controls.Border>, add a <xref:System.Windows.Controls.Label> with the content "View Expense Report" to be the title of the page.</span></span> 
  
    [!code-xaml[ExpenseIt#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#13)]  
  
7. <span data-ttu-id="98044-225">Erstellen Sie die Anwendung, und führen Sie sie aus.</span><span class="sxs-lookup"><span data-stu-id="98044-225">Build and run the application.</span></span> 
  
 <span data-ttu-id="98044-226">In der folgenden Abbildung werden die Ergebnisse dieses Abschnitts dargestellt.</span><span class="sxs-lookup"><span data-stu-id="98044-226">The following illustration shows the results of this section.</span></span> 
  
 <span data-ttu-id="98044-227">![Bildschirmabbildung für ExpenseIt-Beispiel](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure3.png "GettingStartedFigure3")</span><span class="sxs-lookup"><span data-stu-id="98044-227">![ExpenseIt sample screen shot](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure3.png "GettingStartedFigure3")</span></span>  
  
## <a name="adding-code-to-handle-events"></a><span data-ttu-id="98044-228">Hinzufügen von Code zum Behandeln von Ereignissen</span><span class="sxs-lookup"><span data-stu-id="98044-228">Adding code to handle events</span></span>  
  
1. <span data-ttu-id="98044-229">Öffnen Sie „ExpenseItHome.xaml“.</span><span class="sxs-lookup"><span data-stu-id="98044-229">Open ExpenseItHome.xaml.</span></span> 
  
2. <span data-ttu-id="98044-230">Hinzufügen einer <xref:System.Windows.Controls.Primitives.ButtonBase.Click> -Ereignishandler, um die <xref:System.Windows.Controls.Button> Element.</span><span class="sxs-lookup"><span data-stu-id="98044-230">Add a <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler to the <xref:System.Windows.Controls.Button> element.</span></span> <span data-ttu-id="98044-231">Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen einer einfachen Ereignishandler](http://msdn.microsoft.com/library/b1456e07-9dec-4354-99cf-18666b64f480).</span><span class="sxs-lookup"><span data-stu-id="98044-231">For more information, see [How to: Create a Simple Event Handler](http://msdn.microsoft.com/library/b1456e07-9dec-4354-99cf-18666b64f480).</span></span> 
  
    [!code-xaml[ExpenseIt#15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml#15)]  
  
3. <span data-ttu-id="98044-232">Öffnen Sie „ExpenseItHome.xaml.vb“ bzw. „ExpenseItHome.xaml.cs“.</span><span class="sxs-lookup"><span data-stu-id="98044-232">Open ExpenseItHome.xaml.vb or ExpenseItHome.xaml.cs.</span></span> 
  
4. <span data-ttu-id="98044-233">Fügen Sie folgenden Code, der <xref:System.Windows.Controls.Primitives.ButtonBase.Click> -Ereignishandler bewirkt, das Fenster dass, navigieren Sie zu der Datei "ExpenseReportPage.xaml".</span><span class="sxs-lookup"><span data-stu-id="98044-233">Add the following code to the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler, which causes the window to navigate to the ExpenseReportPage.xaml file.</span></span> 
  
    [!code-csharp[ExpenseIt#16](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml.cs#16)]
    [!code-vb[ExpenseIt#16](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt6/ExpenseItHome.xaml.vb#16)]  
  
## <a name="creating-the-ui-for-expensereportpage"></a><span data-ttu-id="98044-234">Erstellen der Benutzeroberfläche für ExpenseReportPage</span><span class="sxs-lookup"><span data-stu-id="98044-234">Creating the UI for ExpenseReportPage</span></span>  
 <span data-ttu-id="98044-235">„ExpenseReportPage.xaml“ zeigt die Spesenabrechnung für die Person an, die für „ExpenseItHome.xaml“ ausgewählt wurde.</span><span class="sxs-lookup"><span data-stu-id="98044-235">ExpenseReportPage.xaml displays the expense report for the person that was selected on the ExpenseItHome.xaml.</span></span> <span data-ttu-id="98044-236">In diesem Abschnitt fügt Steuerelemente hinzu und erstellt die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] für ExpenseReportPage.xaml.</span><span class="sxs-lookup"><span data-stu-id="98044-236">This section adds controls and creates the [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] for ExpenseReportPage.xaml.</span></span> <span data-ttu-id="98044-237">In diesem Abschnitt sowie die Hintergrund-und ausfüllen zu den verschiedenen [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Elemente.</span><span class="sxs-lookup"><span data-stu-id="98044-237">This section also adds background and fill colors to the various [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] elements.</span></span> 
  
1. <span data-ttu-id="98044-238">Öffnen Sie „ExpenseReportPage.xaml“.</span><span class="sxs-lookup"><span data-stu-id="98044-238">Open ExpenseReportPage.xaml.</span></span> 
  
2. <span data-ttu-id="98044-239">Fügen Sie folgenden XAML-Code zwischen den <xref:System.Windows.Controls.Grid>-Tags hinzu.</span><span class="sxs-lookup"><span data-stu-id="98044-239">Add the following XAML between the <xref:System.Windows.Controls.Grid> tags.</span></span> 
  
     <span data-ttu-id="98044-240">Diese Benutzeroberfläche ähnelt der Benutzeroberfläche auf ExpenseItHome.xaml erstellt werden, außer die Berichtsdaten, in angezeigt werden einem <xref:System.Windows.Controls.DataGrid>.</span><span class="sxs-lookup"><span data-stu-id="98044-240">This UI is similar to the UI created on ExpenseItHome.xaml except the report data is displayed in a <xref:System.Windows.Controls.DataGrid>.</span></span> 
  
    [!code-xaml[ExpenseIt#17](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseReportPage.xaml#17)]  
  
3. <span data-ttu-id="98044-241">Erstellen Sie die Anwendung, und führen Sie sie aus.</span><span class="sxs-lookup"><span data-stu-id="98044-241">Build and run the application.</span></span> 
  
    > [!NOTE]
    >  <span data-ttu-id="98044-242">Wenn Sie eine Fehlermeldung, die erhalten die <xref:System.Windows.Controls.DataGrid> wurde nicht gefunden oder nicht vorhanden ist, stellen Sie sicher, dass das Projekt .NET Framework 4 oder höher abzielt.</span><span class="sxs-lookup"><span data-stu-id="98044-242">If you get an error that the <xref:System.Windows.Controls.DataGrid> was not found or does not exist, make sure that your project targets the .NET Framework 4 or later.</span></span> <span data-ttu-id="98044-243">Weitere Informationen finden Sie unter [Vorgehensweise: .NET Framework-Version als Ziel](/visualstudio/ide/how-to-target-a-version-of-the-dotnet-framework).</span><span class="sxs-lookup"><span data-stu-id="98044-243">For more information, see [How to: Target a Version of the .NET Framework](/visualstudio/ide/how-to-target-a-version-of-the-dotnet-framework).</span></span> 
  
4. <span data-ttu-id="98044-244">Klicken Sie auf die **Ansicht** Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="98044-244">Click the **View** button.</span></span> 
  
     <span data-ttu-id="98044-245">Die Spesenabrechnungsseite wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="98044-245">The expense report page appears.</span></span> 
  
 <span data-ttu-id="98044-246">Die folgende Abbildung zeigt die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] ExpenseReportPage.xaml hinzugefügte Elemente.</span><span class="sxs-lookup"><span data-stu-id="98044-246">The following illustration shows the [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] elements added to ExpenseReportPage.xaml.</span></span> <span data-ttu-id="98044-247">Beachten Sie, dass die Navigationsschaltfläche "Zurück" aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="98044-247">Notice that the back navigation button is enabled.</span></span> 
  
 <span data-ttu-id="98044-248">![Bildschirmabbildung für ExpenseIt-Beispiel](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure4.png "GettingStartedFigure4")</span><span class="sxs-lookup"><span data-stu-id="98044-248">![ExpenseIt sample screen shot](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure4.png "GettingStartedFigure4")</span></span>  
  
## <a name="styling-controls"></a><span data-ttu-id="98044-249">Formatieren von Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="98044-249">Styling controls</span></span>  
 <span data-ttu-id="98044-250">Die Darstellung der verschiedenen Elemente kann häufig derselbe Pfad werden für alle Elemente des gleichen Typs in eine [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].</span><span class="sxs-lookup"><span data-stu-id="98044-250">The appearance of various elements can often be the same for all elements of the same type in a [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].</span></span> <span data-ttu-id="98044-251">Die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] verwendet Stile, damit Darstellungen in mehreren Elementen wieder verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="98044-251">[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] uses styles to make appearances reusable across multiple elements.</span></span> <span data-ttu-id="98044-252">Die Wiederverwendung von Stilen kann zur Vereinfachung [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] erstellen und verwalten.</span><span class="sxs-lookup"><span data-stu-id="98044-252">The reusability of styles helps to simplify [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] creation and management.</span></span> <span data-ttu-id="98044-253">Weitere Informationen zu Stilen finden Sie unter [Erstellen von Formaten und Vorlagen](../../../../docs/framework/wpf/controls/styling-and-templating.md).</span><span class="sxs-lookup"><span data-stu-id="98044-253">For more information about styles, see [Styling and Templating](../../../../docs/framework/wpf/controls/styling-and-templating.md).</span></span> <span data-ttu-id="98044-254">Dieser Abschnitt ersetzt die Attribute pro Element, die in den vorherigen Schritten mit Stilen definiert wurden.</span><span class="sxs-lookup"><span data-stu-id="98044-254">This section replaces the per-element attributes that were defined in previous steps with styles.</span></span> 
  
1. <span data-ttu-id="98044-255">Öffnen Sie „Application.xaml“ oder „App.xaml“.</span><span class="sxs-lookup"><span data-stu-id="98044-255">Open Application.xaml or App.xaml.</span></span> 
  
2. <span data-ttu-id="98044-256">Fügen Sie den folgenden XAML-Code zwischen den <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> Tags:</span><span class="sxs-lookup"><span data-stu-id="98044-256">Add the following XAML between the <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> tags:</span></span>  
  
    [!code-xaml[ExpenseIt#18](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/App.xaml#18)]  
  
     <span data-ttu-id="98044-257">Dies [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] fügt die folgenden Stile hinzu:</span><span class="sxs-lookup"><span data-stu-id="98044-257">This [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] adds the following styles:</span></span>  
  
    -  <span data-ttu-id="98044-258">`headerTextStyle`: Zum Formatieren des Seitentitels für <xref:System.Windows.Controls.Label>.</span><span class="sxs-lookup"><span data-stu-id="98044-258">`headerTextStyle`: To format the page title <xref:System.Windows.Controls.Label>.</span></span> 
  
    -  <span data-ttu-id="98044-259">`labelStyle`: Zum Formatieren der <xref:System.Windows.Controls.Label> -Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="98044-259">`labelStyle`: To format the <xref:System.Windows.Controls.Label> controls.</span></span> 
  
    -  <span data-ttu-id="98044-260">`columnHeaderStyle`: Zum Formatieren von <xref:System.Windows.Controls.Primitives.DataGridColumnHeader>.</span><span class="sxs-lookup"><span data-stu-id="98044-260">`columnHeaderStyle`: To format the <xref:System.Windows.Controls.Primitives.DataGridColumnHeader>.</span></span> 
  
    -  <span data-ttu-id="98044-261">`listHeaderStyle`: Zum Formatieren der <xref:System.Windows.Controls.Border> -Kopfzeilensteuerelemente.</span><span class="sxs-lookup"><span data-stu-id="98044-261">`listHeaderStyle`: To format the list header <xref:System.Windows.Controls.Border> controls.</span></span> 
  
    -  <span data-ttu-id="98044-262">`listHeaderTextStyle`: Zum Formatieren der Kopfzeile <xref:System.Windows.Controls.Label>.</span><span class="sxs-lookup"><span data-stu-id="98044-262">`listHeaderTextStyle`: To format the list header <xref:System.Windows.Controls.Label>.</span></span> 
  
    -  <span data-ttu-id="98044-263">`buttonStyle`: Zum Formatieren der <xref:System.Windows.Controls.Button> auf ExpenseItHome.xaml.</span><span class="sxs-lookup"><span data-stu-id="98044-263">`buttonStyle`: To format the <xref:System.Windows.Controls.Button> on ExpenseItHome.xaml.</span></span> 
  
     <span data-ttu-id="98044-264">Beachten Sie, dass die Stile für Ressourcen und die untergeordneten Elemente sind die <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> Property-Element.</span><span class="sxs-lookup"><span data-stu-id="98044-264">Notice that the styles are resources and children of the <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> property element.</span></span> <span data-ttu-id="98044-265">An diesem Speicherort werden die Stile auf alle Elemente in einer Anwendung angewendet.</span><span class="sxs-lookup"><span data-stu-id="98044-265">In this location, the styles are applied to all the elements in an application.</span></span> <span data-ttu-id="98044-266">Ein Beispiel der Verwendung von Ressourcen in einer [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] -Anwendung finden Sie unter [verwenden Anwendungsressourcen](../../../../docs/framework/wpf/advanced/how-to-use-application-resources.md).</span><span class="sxs-lookup"><span data-stu-id="98044-266">For an example of using resources in a [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] application, see [Use Application Resources](../../../../docs/framework/wpf/advanced/how-to-use-application-resources.md).</span></span> 
  
3. <span data-ttu-id="98044-267">Öffnen Sie „ExpenseItHome.xaml“.</span><span class="sxs-lookup"><span data-stu-id="98044-267">Open ExpenseItHome.xaml.</span></span> 
  
4. <span data-ttu-id="98044-268">Ersetzen Sie alles zwischen dem <xref:System.Windows.Controls.Grid> Elemente durch Folgendes XAML.</span><span class="sxs-lookup"><span data-stu-id="98044-268">Replace everything between the <xref:System.Windows.Controls.Grid> elements with the following XAML.</span></span> 
  
    [!code-xaml[ExpenseIt#19](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseItHome.xaml#19)]  
  
     <span data-ttu-id="98044-269">Eigenschaften wie <xref:System.Windows.VerticalAlignment> und <xref:System.Windows.Media.FontFamily> , die die Darstellung der einzelnen Steuerelemente definieren, werden entfernt und ersetzt, indem die Stile angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="98044-269">The properties such as <xref:System.Windows.VerticalAlignment> and <xref:System.Windows.Media.FontFamily> that define the look of each control are removed and replaced by applying the styles.</span></span> <span data-ttu-id="98044-270">Z. B. die `headerTextStyle` wird angewendet, um die "View Expense Report" <xref:System.Windows.Controls.Label>.</span><span class="sxs-lookup"><span data-stu-id="98044-270">For example, the `headerTextStyle` is applied to the "View Expense Report" <xref:System.Windows.Controls.Label>.</span></span> 
  
5. <span data-ttu-id="98044-271">Öffnen Sie „ExpenseReportPage.xaml“.</span><span class="sxs-lookup"><span data-stu-id="98044-271">Open ExpenseReportPage.xaml.</span></span> 
  
6. <span data-ttu-id="98044-272">Ersetzen Sie alles zwischen dem <xref:System.Windows.Controls.Grid> Elemente durch Folgendes XAML.</span><span class="sxs-lookup"><span data-stu-id="98044-272">Replace everything between the <xref:System.Windows.Controls.Grid> elements with the following XAML.</span></span> 
  
    [!code-xaml[ExpenseIt#20](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseReportPage.xaml#20)]  
  
     <span data-ttu-id="98044-273">Dadurch werden dem <xref:System.Windows.Controls.Label> -Element und <xref:System.Windows.Controls.Border> -Element Stile hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="98044-273">This adds styles to the <xref:System.Windows.Controls.Label> and <xref:System.Windows.Controls.Border> elements.</span></span> 
  
7. <span data-ttu-id="98044-274">Erstellen Sie die Anwendung, und führen Sie sie aus.</span><span class="sxs-lookup"><span data-stu-id="98044-274">Build and run the application.</span></span> 
  
     <span data-ttu-id="98044-275">Nach dem Hinzufügen der [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] in diesem Abschnitt die Anwendung sieht genauso aus wie gewohnt mit Stilen aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="98044-275">After adding the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] in this section, the application looks the same as it did before being updated with styles.</span></span> 
  
## <a name="binding-data-to-a-control"></a><span data-ttu-id="98044-276">Binden von Daten an ein Steuerelement</span><span class="sxs-lookup"><span data-stu-id="98044-276">Binding data to a control</span></span>  
 <span data-ttu-id="98044-277">In diesem Abschnitt erstellen Sie die [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] Daten, die an verschiedene Steuerelemente gebunden ist.</span><span class="sxs-lookup"><span data-stu-id="98044-277">In this section, you create the [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] data that is bound to various controls.</span></span> 
  
1. <span data-ttu-id="98044-278">Öffnen Sie „ExpenseItHome.xaml“.</span><span class="sxs-lookup"><span data-stu-id="98044-278">Open ExpenseItHome.xaml.</span></span> 
  
2. <span data-ttu-id="98044-279">Nach dem Öffnen <xref:System.Windows.Controls.Grid> Element, fügen Sie den folgenden XAML-Code zum Erstellen einer <xref:System.Windows.Data.XmlDataProvider> , die Daten für jede Person enthält.</span><span class="sxs-lookup"><span data-stu-id="98044-279">After the opening <xref:System.Windows.Controls.Grid> element, add the following XAML to create an <xref:System.Windows.Data.XmlDataProvider> that contains the data for each person.</span></span> 
  
     <span data-ttu-id="98044-280">Die Daten werden als erstellt eine <xref:System.Windows.Controls.Grid> Ressource.</span><span class="sxs-lookup"><span data-stu-id="98044-280">The data is created as a <xref:System.Windows.Controls.Grid> resource.</span></span> <span data-ttu-id="98044-281">Normalerweise würde sie als Datei geladen, aus Gründen der Einfachheit werden die Daten aber inline hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="98044-281">Normally this would be loaded as a file, but for simplicity the data is added inline.</span></span> 
  
    [!code-xaml[ExpenseIt#21](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#21)]  
    [!code-xaml[ExpenseIt#23](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#23)]  
    [!code-xaml[ExpenseIt#22](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#22)]  
  
3. <span data-ttu-id="98044-282">In der <xref:System.Windows.Controls.Grid> Ressource, fügen Sie die folgenden <xref:System.Windows.DataTemplate>, die definiert, wie zum Anzeigen der Daten in der <xref:System.Windows.Controls.ListBox>.</span><span class="sxs-lookup"><span data-stu-id="98044-282">In the <xref:System.Windows.Controls.Grid> resource, add the following <xref:System.Windows.DataTemplate>, which defines how to display the data in the <xref:System.Windows.Controls.ListBox>.</span></span> <span data-ttu-id="98044-283">Weitere Informationen zu Datenvorlagen finden Sie in der [Übersicht über Datenvorlagen](../../../../docs/framework/wpf/data/data-templating-overview.md).</span><span class="sxs-lookup"><span data-stu-id="98044-283">For more information about data templates, see [Data Templating Overview](../../../../docs/framework/wpf/data/data-templating-overview.md).</span></span> 
  
    [!code-xaml[ExpenseIt#21](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#21)]  
    [!code-xaml[ExpenseIt#24](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#24)]  
    [!code-xaml[ExpenseIt#22](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#22)]  
  
4. <span data-ttu-id="98044-284">Ersetzen Sie die vorhandene <xref:System.Windows.Controls.ListBox> durch Folgendes XAML.</span><span class="sxs-lookup"><span data-stu-id="98044-284">Replace the existing <xref:System.Windows.Controls.ListBox> with the following XAML.</span></span> 
  
    [!code-xaml[ExpenseIt#25](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#25)]  
  
     <span data-ttu-id="98044-285">Dieser XAML-Code bindet die <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> Eigenschaft von der <xref:System.Windows.Controls.ListBox> mit der Datenquelle und wendet die Datenvorlage als die <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>.</span><span class="sxs-lookup"><span data-stu-id="98044-285">This XAML binds the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> property of the <xref:System.Windows.Controls.ListBox> to the data source and applies the data template as the <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>.</span></span> 
  
## <a name="connecting-data-to-controls"></a><span data-ttu-id="98044-286">Verbinden von Daten an Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="98044-286">Connecting data to controls</span></span>  
 <span data-ttu-id="98044-287">In diesem Abschnitt schreiben Sie Code, der das aktuelle Element, die in der Liste der Personen auf der Seite "ExpenseItHome.xaml" ausgewählt ist abruft, und übergibt den Verweis auf den Konstruktor des `ExpenseReportPage` während der Instanziierung.</span><span class="sxs-lookup"><span data-stu-id="98044-287">In this section, you write the code that retrieves the current item that is selected in the list of people on the ExpenseItHome.xaml page, and passes its reference to the constructor of `ExpenseReportPage` during instantiation.</span></span> <span data-ttu-id="98044-288">`ExpenseReportPage` legt den Datenkontext mithilfe des übergebenen Elements fest, und die in „ExpenseReportPage.xaml“ definierten Steuerelemente werden daran gebunden.</span><span class="sxs-lookup"><span data-stu-id="98044-288">`ExpenseReportPage` sets its data context with the passed item, which is what the controls defined in ExpenseReportPage.xaml will bind to.</span></span> 
  
1. <span data-ttu-id="98044-289">Öffnen Sie „ExpenseReportPage.xaml.vb“ oder „ExpenseReportPage.xaml.cs“.</span><span class="sxs-lookup"><span data-stu-id="98044-289">Open ExpenseReportPage.xaml.vb or ExpenseReportPage.xaml.cs.</span></span> 
  
2. <span data-ttu-id="98044-290">Fügen Sie einen Konstruktor hinzu, der ein Objekt akzeptiert, damit Sie die Spesenabrechnungsdaten der ausgewählten Person übergeben können.</span><span class="sxs-lookup"><span data-stu-id="98044-290">Add a constructor that takes an object so you can pass the expense report data of the selected person.</span></span> 
  
    [!code-csharp[ExpenseIt#26](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseReportPage.xaml.cs#26)]
    [!code-vb[ExpenseIt#26](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseReportPage.xaml.vb#26)]  
  
3. <span data-ttu-id="98044-291">Öffnen Sie „ExpenseItHome.xaml.vb“ bzw. „ExpenseItHome.xaml.cs“.</span><span class="sxs-lookup"><span data-stu-id="98044-291">Open ExpenseItHome.xaml.vb or ExpenseItHome.xaml.cs.</span></span> 
  
4. <span data-ttu-id="98044-292">Ändern der <xref:System.Windows.Controls.Primitives.ButtonBase.Click> Ereignishandler aufrufen, den neuen Konstruktor die Spesenabrechnungsdaten der ausgewählten Person übergeben.</span><span class="sxs-lookup"><span data-stu-id="98044-292">Change the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler to call the new constructor passing the expense report data of the selected person.</span></span> 
  
    [!code-csharp[ExpenseIt#27](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml.cs#27)]
    [!code-vb[ExpenseIt#27](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseItHome.xaml.vb#27)]  
  
## <a name="styling-data-with-data-templates"></a><span data-ttu-id="98044-293">Formatieren von Daten mit Datenvorlagen</span><span class="sxs-lookup"><span data-stu-id="98044-293">Styling data with data templates</span></span>  
 <span data-ttu-id="98044-294">In diesem Abschnitt wird die Aktualisierung der [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] für jedes Element in den Daten Listen mit Datenvorlagen gebunden.</span><span class="sxs-lookup"><span data-stu-id="98044-294">In this section, you update the [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] for each item in the data bound lists by using data templates.</span></span> 
  
1. <span data-ttu-id="98044-295">Öffnen Sie „ExpenseReportPage.xaml“.</span><span class="sxs-lookup"><span data-stu-id="98044-295">Open ExpenseReportPage.xaml.</span></span> 
  
2. <span data-ttu-id="98044-296">Binden Sie den Inhalt des "Name" und "Department" <xref:System.Windows.Controls.Label> Elemente, die die entsprechenden Daten source-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="98044-296">Bind the content of the "Name" and "Department" <xref:System.Windows.Controls.Label> elements to the appropriate data source property.</span></span> <span data-ttu-id="98044-297">Weitere Informationen zu Datenbindungen finden Sie unter [Übersicht über Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md).</span><span class="sxs-lookup"><span data-stu-id="98044-297">For more information about data binding, see [Data Binding Overview](../../../../docs/framework/wpf/data/data-binding-overview.md).</span></span> 
  
    [!code-xaml[ExpenseIt#31](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#31)]  
  
3. <span data-ttu-id="98044-298">Nach der öffnenden <xref:System.Windows.Controls.Grid> Element, fügen Sie die folgenden Datenvorlagen, die definieren, wie die Spesenabrechnungsdaten angezeigt.</span><span class="sxs-lookup"><span data-stu-id="98044-298">After the opening <xref:System.Windows.Controls.Grid> element, add the following data templates, which define how to display the expense report data.</span></span>  
    [!code-xaml[ExpenseIt#30](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#30)]  
  
4. <span data-ttu-id="98044-299">Wenden Sie die Vorlagen, die <xref:System.Windows.Controls.DataGrid> Berichtsdaten für Spalten, in denen die Ausgaben angezeigt.</span><span class="sxs-lookup"><span data-stu-id="98044-299">Apply the templates to the <xref:System.Windows.Controls.DataGrid> columns that display the expense report data.</span></span> 
  
    [!code-xaml[ExpenseIt#32](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#32)]  
  
5. <span data-ttu-id="98044-300">Erstellen Sie die Anwendung, und führen Sie sie aus.</span><span class="sxs-lookup"><span data-stu-id="98044-300">Build and run the application.</span></span> 
  
6. <span data-ttu-id="98044-301">Wählen Sie eine Person ein, und klicken Sie auf die **Ansicht** Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="98044-301">Select a person and click the **View** button.</span></span> 
  
 <span data-ttu-id="98044-302">Die folgende Abbildung zeigt die beiden Seiten der ExpenseIt-Anwendung mit Steuerelementen, Layout, Stilen, Datenbindung und Datenvorlagen, die angewendet wurden.</span><span class="sxs-lookup"><span data-stu-id="98044-302">The following illustration shows both pages of the ExpenseIt application with controls, layout, styles, data binding, and data templates applied.</span></span> 
  
 <span data-ttu-id="98044-303">![Bildschirmabbildungen für ExpenseIt-Beispiel](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure5.png "GettingStartedFigure5")</span><span class="sxs-lookup"><span data-stu-id="98044-303">![ExpenseIt sample screen shots](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure5.png "GettingStartedFigure5")</span></span>  
  
## <a name="best-practices"></a><span data-ttu-id="98044-304">Bewährte Methoden</span><span class="sxs-lookup"><span data-stu-id="98044-304">Best practices</span></span>  
 <span data-ttu-id="98044-305">In diesem Beispiel soll nur eine bestimmte Funktion von WPF veranschaulicht werden, daher werden die bewährten Methoden für die Anwendungsentwicklung nicht befolgt.</span><span class="sxs-lookup"><span data-stu-id="98044-305">This sample demonstrates a specific feature of WPF and, consequently, does not follow application development best practices.</span></span> <span data-ttu-id="98044-306">Für eine umfassende Erläuterung der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] und [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] bewährte Methoden für die Anwendungsentwicklung, finden Sie unter den folgenden Themen nach Bedarf:</span><span class="sxs-lookup"><span data-stu-id="98044-306">For comprehensive coverage of [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] and the [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] application development best practices, see the following topics as appropriate:</span></span>  
  
-   <span data-ttu-id="98044-307">Barrierefreiheit – [Bewährte Methoden für Eingabehilfen](../../../../docs/framework/ui-automation/accessibility-best-practices.md)</span><span class="sxs-lookup"><span data-stu-id="98044-307">Accessibility - [Accessibility Best Practices](../../../../docs/framework/ui-automation/accessibility-best-practices.md)</span></span>  
  
-   <span data-ttu-id="98044-308">Sicherheit – [Sicherheit](../../../../docs/framework/wpf/security-wpf.md)</span><span class="sxs-lookup"><span data-stu-id="98044-308">Security - [Security](../../../../docs/framework/wpf/security-wpf.md)</span></span>  
  
-   <span data-ttu-id="98044-309">Lokalisierung – [Übersicht über WPF-Globalisierung und -Lokalisierung](../../../../docs/framework/wpf/advanced/wpf-globalization-and-localization-overview.md)</span><span class="sxs-lookup"><span data-stu-id="98044-309">Localization - [WPF Globalization and Localization Overview](../../../../docs/framework/wpf/advanced/wpf-globalization-and-localization-overview.md)</span></span>  
  
-   <span data-ttu-id="98044-310">Leistung – [Optimieren der WPF-Anwendungsleistung](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)</span><span class="sxs-lookup"><span data-stu-id="98044-310">Performance - [Optimizing WPF Application Performance](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)</span></span>  
  
## <a name="whats-next"></a><span data-ttu-id="98044-311">Was kommt als nächstes</span><span class="sxs-lookup"><span data-stu-id="98044-311">What's next</span></span>  
 <span data-ttu-id="98044-312">Sie haben nun eine Reihe von Techniken zur Verfügung, die zum Erstellen einer [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] mit [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="98044-312">You now have a number of techniques at your disposal for creating a [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] using [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].</span></span> <span data-ttu-id="98044-313">Sie verfügen jetzt über fundierte Kenntnisse über die grundlegenden Bausteine von einem datengebundenen [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] Anwendung.</span><span class="sxs-lookup"><span data-stu-id="98044-313">You should now have a broad understanding of the basic building blocks of a data-bound [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] application.</span></span> <span data-ttu-id="98044-314">Dieses Thema erhebt keinen Anspruch auf Vollständigkeit, soll aber eine Vorstellung einiger Möglichkeiten vermitteln, die Sie neben den in diesem Thema vorgestellten Techniken selbst entdecken können.</span><span class="sxs-lookup"><span data-stu-id="98044-314">This topic is by no means exhaustive, but hopefully you also now have a sense of some of the possibilities you might discover on your own beyond the techniques in this topic.</span></span> 
  
 <span data-ttu-id="98044-315">Weitere Informationen über die WPF-Architektur und -Programmiermodelle finden Sie in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="98044-315">For more information about the WPF architecture and programming models, see the following topics:</span></span>  
  
-   [<span data-ttu-id="98044-316">WPF-Architektur</span><span class="sxs-lookup"><span data-stu-id="98044-316">WPF Architecture</span></span>](../../../../docs/framework/wpf/advanced/wpf-architecture.md)  
  
-   [<span data-ttu-id="98044-317">Übersicht über XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="98044-317">XAML Overview (WPF)</span></span>](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
  
-   [<span data-ttu-id="98044-318">Übersicht über Abhängigkeitseigenschaften</span><span class="sxs-lookup"><span data-stu-id="98044-318">Dependency Properties Overview</span></span>](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)  
  
-   [<span data-ttu-id="98044-319">Layout</span><span class="sxs-lookup"><span data-stu-id="98044-319">Layout</span></span>](../../../../docs/framework/wpf/advanced/layout.md)  
  
 <span data-ttu-id="98044-320">Weitere Informationen zum Erstellen von Anwendungen finden Sie in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="98044-320">For more information about creating applications, see the following topics:</span></span>  
  
-   [<span data-ttu-id="98044-321">Anwendungsentwicklung</span><span class="sxs-lookup"><span data-stu-id="98044-321">Application Development</span></span>](../../../../docs/framework/wpf/app-development/index.md)  
  
-   [<span data-ttu-id="98044-322">Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="98044-322">Controls</span></span>](../../../../docs/framework/wpf/controls/index.md)  
  
-   [<span data-ttu-id="98044-323">Übersicht zur Datenbindung</span><span class="sxs-lookup"><span data-stu-id="98044-323">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
  
-   [<span data-ttu-id="98044-324">Grafiken und Multimedia</span><span class="sxs-lookup"><span data-stu-id="98044-324">Graphics and Multimedia</span></span>](../../../../docs/framework/wpf/graphics-multimedia/index.md)  
  
-   [<span data-ttu-id="98044-325">Dokumente in WPF</span><span class="sxs-lookup"><span data-stu-id="98044-325">Documents in WPF</span></span>](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
  
## <a name="see-also"></a><span data-ttu-id="98044-326">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="98044-326">See also</span></span>  
 [<span data-ttu-id="98044-327">Übersicht über Panel-Elemente</span><span class="sxs-lookup"><span data-stu-id="98044-327">Panels Overview</span></span>](../../../../docs/framework/wpf/controls/panels-overview.md)  
 [<span data-ttu-id="98044-328">Übersicht über Datenvorlagen</span><span class="sxs-lookup"><span data-stu-id="98044-328">Data Templating Overview</span></span>](../../../../docs/framework/wpf/data/data-templating-overview.md)  
 [<span data-ttu-id="98044-329">Erstellen einer WPF-Anwendung</span><span class="sxs-lookup"><span data-stu-id="98044-329">Building a WPF Application</span></span>](../../../../docs/framework/wpf/app-development/building-a-wpf-application-wpf.md)  
 [<span data-ttu-id="98044-330">Stile und Vorlagen</span><span class="sxs-lookup"><span data-stu-id="98044-330">Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/styles-and-templates.md)
