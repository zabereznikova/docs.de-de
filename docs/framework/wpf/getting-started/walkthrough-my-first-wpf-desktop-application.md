---
title: Erstellen einer WPF-Anwendung in Visual Studio
ms.date: 10/26/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- getting started [WPF], WPF
- WPF [WPF], getting started
ms.assetid: b96bed40-8946-4285-8fe4-88045ab854ed
author: mairaw
ms.author: mairaw
ms.custom: vs-dotnet
ms.openlocfilehash: bfbe1bb413e0d9f46fe587d7a412af5303685b7a
ms.sourcegitcommit: 8f95d3a37e591963ebbb9af6e90686fd5f3b8707
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2019
ms.locfileid: "56748374"
---
# <a name="walkthrough-my-first-wpf-desktop-application"></a><span data-ttu-id="c2bdc-102">Exemplarische Vorgehensweise: Meine erste WPF-Desktopanwendung</span><span class="sxs-lookup"><span data-stu-id="c2bdc-102">Walkthrough: My first WPF desktop application</span></span>

<span data-ttu-id="c2bdc-103">In diesem Artikel erfahren Sie, wie Sie eine einfache Windows Presentation Foundation (WPF)-Anwendung entwickeln, die die Elemente enthält, die für die meisten WPF-Anwendungen gelten: Extensible Application Markup Language (XAML) Markup, CodeBehind, Anwendungsdefinitionen, Steuerelemente, Layout, Datenbindung und Stile.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-103">This article shows you how to develop a simple Windows Presentation Foundation (WPF) application that includes the elements that are common to most WPF applications: Extensible Application Markup Language (XAML) markup, code-behind, application definitions, controls, layout, data binding, and styles.</span></span>

<span data-ttu-id="c2bdc-104">Diese exemplarische Vorgehensweise umfasst die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="c2bdc-104">This walkthrough includes the following steps:</span></span>

- <span data-ttu-id="c2bdc-105">Verwenden Sie XAML zum Entwerfen der Darstellung der Benutzeroberfläche (UI) der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-105">Use XAML to design the appearance of the application's user interface (UI).</span></span>

- <span data-ttu-id="c2bdc-106">Schreiben Sie Code, um das Verhalten der Anwendung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-106">Write code to build the application's behavior.</span></span>

- <span data-ttu-id="c2bdc-107">Erstellen Sie eine Anwendungsdefinition, um die Anwendung zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-107">Create an application definition to manage the application.</span></span>

- <span data-ttu-id="c2bdc-108">Fügen Sie Steuerelemente hinzu, und erstellen Sie das Layout der Benutzeroberfläche die Anwendung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-108">Add controls and create the layout to compose the application UI.</span></span>

- <span data-ttu-id="c2bdc-109">Stile für ein konsistentes Erscheinungsbild in der gesamten Benutzeroberfläche einer Anwendung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-109">Create styles for a consistent appearance throughout an application's UI.</span></span>

- <span data-ttu-id="c2bdc-110">Binden Sie die Benutzeroberfläche, auf Daten in der Benutzeroberfläche aus Daten füllen und behalten Sie die Daten und die Benutzeroberfläche, die synchronisiert.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-110">Bind the UI to data to both populate the UI from data and keep the data and UI synchronized.</span></span>

<span data-ttu-id="c2bdc-111">Am Ende dieser exemplarischen Vorgehensweise werden Sie eine eigenständigen Windows-Anwendung erstellt haben, die Benutzer spesenabrechnungen für bestimmte Personen anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-111">By the end of the walkthrough, you'll have built a standalone Windows application that allows users to view expense reports for selected people.</span></span> <span data-ttu-id="c2bdc-112">Die Anwendung besteht aus der WPF-Seiten, die in einem Fenster im Browserstil gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-112">The application is composed of several WPF pages that are hosted in a browser-style window.</span></span>

> [!TIP]
> <span data-ttu-id="c2bdc-113">Der Beispielcode, der verwendet wird, in dieser exemplarischen Vorgehensweise steht für Visual Basic und c# in [Introduction to Building WPF Applications](https://go.microsoft.com/fwlink/?LinkID=160008).</span><span class="sxs-lookup"><span data-stu-id="c2bdc-113">The sample code that is used to build this walkthrough is available for both Visual Basic and C# at [Introduction to Building WPF Applications](https://go.microsoft.com/fwlink/?LinkID=160008).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c2bdc-114">Vorraussetzungen</span><span class="sxs-lookup"><span data-stu-id="c2bdc-114">Prerequisites</span></span>

- <span data-ttu-id="c2bdc-115">Visual Studio 2017 oder höher</span><span class="sxs-lookup"><span data-stu-id="c2bdc-115">Visual Studio 2017 or later</span></span>

   <span data-ttu-id="c2bdc-116">Weitere Informationen zum Installieren der neuesten Version von Visual Studio finden Sie unter [Installieren von Visual Studio](/visualstudio/install/install-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="c2bdc-116">For more information about installing the latest version of Visual Studio, see [Install Visual Studio](/visualstudio/install/install-visual-studio).</span></span>

## <a name="create-the-application-project"></a><span data-ttu-id="c2bdc-117">Erstellen des Anwendungsprojekts</span><span class="sxs-lookup"><span data-stu-id="c2bdc-117">Create the application project</span></span>

<span data-ttu-id="c2bdc-118">Der erste Schritt ist die Erstellung von Infrastruktur der Anwendung, die eine Anwendungsdefinition, zwei Seiten und ein Bild enthält.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-118">The first step is to create the application infrastructure, which includes an application definition, two pages, and an image.</span></span>

1. <span data-ttu-id="c2bdc-119">Erstellen Sie ein neues WPF-Anwendungsprojekt in Visual Basic oder Visual c# mit dem Namen **`ExpenseIt`**:</span><span class="sxs-lookup"><span data-stu-id="c2bdc-119">Create a new WPF Application project in Visual Basic or Visual C# named **`ExpenseIt`**:</span></span>

   1. <span data-ttu-id="c2bdc-120">Öffnen Sie Visual Studio, und wählen Sie **Datei** > **neu** > **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-120">Open Visual Studio and select **File** > **New** > **Project**.</span></span>

      <span data-ttu-id="c2bdc-121">Die **neues Projekt** Dialogfeld wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-121">The **New Project** dialog opens.</span></span>

   2. <span data-ttu-id="c2bdc-122">Unter den **installiert** (Kategorie), erweitern Sie entweder die **Visual C#**  oder **Visual Basic** Knoten, und wählen Sie dann **Windows Desktop**.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-122">Under the **Installed** category, expand either the **Visual C#** or **Visual Basic** node, and then select **Windows Desktop**.</span></span>

   3. <span data-ttu-id="c2bdc-123">Wählen Sie die **WPF-App ((.NET Framework)** Vorlage.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-123">Select the **WPF App (.NET Framework)** template.</span></span> <span data-ttu-id="c2bdc-124">Geben Sie den Namen **`ExpenseIt`** und wählen Sie dann **OK**.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-124">Enter the name **`ExpenseIt`** and then select **OK**.</span></span>

      ![Dialogfeld "Neues Projekt" in WPF-app ausgewählt](media/new-project-dialog.png)

      <span data-ttu-id="c2bdc-126">Visual Studio erstellt das Projekt und öffnet den Designer für das standardanwendungsfenster namens **"MainWindow.xaml"**.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-126">Visual Studio creates the project and opens the designer for the default application window named **MainWindow.xaml**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="c2bdc-127">Diese exemplarische Vorgehensweise verwendet die <xref:System.Windows.Controls.DataGrid> Steuerelement, das in .NET Framework 4 und höher verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-127">This walkthrough uses the <xref:System.Windows.Controls.DataGrid> control that is available in the .NET Framework 4 and later.</span></span> <span data-ttu-id="c2bdc-128">Stellen Sie sicher, dass das Projekt auf .NET Framework 4 abzielt oder höher.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-128">Be sure that your project targets the .NET Framework 4 or later.</span></span> <span data-ttu-id="c2bdc-129">Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen von Projekten für eine bestimmte .NET Framework-Version](/visualstudio/ide/how-to-target-a-version-of-the-dotnet-framework).</span><span class="sxs-lookup"><span data-stu-id="c2bdc-129">For more information, see [How to: Target a Version of the .NET Framework](/visualstudio/ide/how-to-target-a-version-of-the-dotnet-framework).</span></span>

2. <span data-ttu-id="c2bdc-130">Open *"Application.xaml"* (Visual Basic) oder *"App.xaml"* (c#).</span><span class="sxs-lookup"><span data-stu-id="c2bdc-130">Open *Application.xaml* (Visual Basic) or *App.xaml* (C#).</span></span>

    <span data-ttu-id="c2bdc-131">Diese XAML-Datei definiert eine WPF-Anwendung und alle Anwendungsressourcen.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-131">This XAML file defines a WPF application and any application resources.</span></span> <span data-ttu-id="c2bdc-132">Sie verwenden diese Datei auch an der Benutzeroberfläche, die automatisch, wenn zeigt die Anwendung gestartet wird. In diesem Fall *"MainWindow.xaml"*.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-132">You also use this file to specify the UI that automatically shows when the application starts; in this case, *MainWindow.xaml*.</span></span>

    <span data-ttu-id="c2bdc-133">Ihre XAML sollte in Visual Basic wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="c2bdc-133">Your XAML should look like this in Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#1_A](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/Application.xaml#1_a)]

    <span data-ttu-id="c2bdc-134">Oder in C# wie folgt:</span><span class="sxs-lookup"><span data-stu-id="c2bdc-134">Or like this in C#:</span></span>

    [!code-xaml[ExpenseIt#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/App.xaml#1)]

3. <span data-ttu-id="c2bdc-135">Open *"MainWindow.xaml"*.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-135">Open *MainWindow.xaml*.</span></span>

    <span data-ttu-id="c2bdc-136">Dieser XAML-Datei ist das Hauptfenster der Anwendung und zeigt erstellten Inhalt auf Seiten.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-136">This XAML file is the main window of your application and displays content created in pages.</span></span> <span data-ttu-id="c2bdc-137">Die <xref:System.Windows.Window> Klasse definiert die Eigenschaften eines Fensters wie Titel, Größe oder Symbol, und behandelt Ereignisse wie schließen oder ausblenden.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-137">The <xref:System.Windows.Window> class defines the properties of a window, such as its title, size, or icon, and handles events, such as closing or hiding.</span></span>

4. <span data-ttu-id="c2bdc-138">Ändern der <xref:System.Windows.Window> Element eine <xref:System.Windows.Navigation.NavigationWindow>, wie in den folgenden XAML dargestellt:</span><span class="sxs-lookup"><span data-stu-id="c2bdc-138">Change the <xref:System.Windows.Window> element to a <xref:System.Windows.Navigation.NavigationWindow>, as shown in the following XAML:</span></span>

   ```xaml
   <NavigationWindow x:Class="ExpenseIt.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        ...
   </NavigationWindow>
   ```

   <span data-ttu-id="c2bdc-139">Diese app navigiert zu anderem Inhalt, abhängig von der Benutzereingabe.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-139">This app navigates to different content depending on the user input.</span></span> <span data-ttu-id="c2bdc-140">Deshalb ist die Main <xref:System.Windows.Window> muss geändert werden, um eine <xref:System.Windows.Navigation.NavigationWindow>.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-140">This is why the main <xref:System.Windows.Window> needs to be changed to a <xref:System.Windows.Navigation.NavigationWindow>.</span></span> <span data-ttu-id="c2bdc-141"><xref:System.Windows.Navigation.NavigationWindow> erbt alle Eigenschaften des <xref:System.Windows.Window>.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-141"><xref:System.Windows.Navigation.NavigationWindow> inherits all the properties of <xref:System.Windows.Window>.</span></span> <span data-ttu-id="c2bdc-142">Die <xref:System.Windows.Navigation.NavigationWindow> Element in der XAML-Datei erstellt eine Instanz der <xref:System.Windows.Navigation.NavigationWindow> Klasse.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-142">The <xref:System.Windows.Navigation.NavigationWindow> element in the XAML file creates an instance of the <xref:System.Windows.Navigation.NavigationWindow> class.</span></span> <span data-ttu-id="c2bdc-143">Weitere Informationen finden Sie unter [Übersicht über die Navigation](../../../../docs/framework/wpf/app-development/navigation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="c2bdc-143">For more information, see [Navigation overview](../../../../docs/framework/wpf/app-development/navigation-overview.md).</span></span>

5. <span data-ttu-id="c2bdc-144">Ändern Sie die folgenden Eigenschaften auf der <xref:System.Windows.Navigation.NavigationWindow> Element:</span><span class="sxs-lookup"><span data-stu-id="c2bdc-144">Change the following properties on the <xref:System.Windows.Navigation.NavigationWindow> element:</span></span>

    - <span data-ttu-id="c2bdc-145">Legen Sie die <xref:System.Windows.Window.Title%2A> Eigenschaft "`ExpenseIt`".</span><span class="sxs-lookup"><span data-stu-id="c2bdc-145">Set the <xref:System.Windows.Window.Title%2A> property to "`ExpenseIt`".</span></span>

    - <span data-ttu-id="c2bdc-146">Legen Sie die <xref:System.Windows.FrameworkElement.Width%2A> Eigenschaft auf 500 Pixel.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-146">Set the <xref:System.Windows.FrameworkElement.Width%2A> property to 500 pixels.</span></span>

    - <span data-ttu-id="c2bdc-147">Legen Sie die <xref:System.Windows.FrameworkElement.Height%2A> -Eigenschaft auf 350 Pixel.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-147">Set the <xref:System.Windows.FrameworkElement.Height%2A> property to 350 pixels.</span></span>

    - <span data-ttu-id="c2bdc-148">Entfernen Sie die <xref:System.Windows.Controls.Grid> Elemente zwischen den <xref:System.Windows.Navigation.NavigationWindow> Tags.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-148">Remove the <xref:System.Windows.Controls.Grid> elements between the <xref:System.Windows.Navigation.NavigationWindow> tags.</span></span>

    <span data-ttu-id="c2bdc-149">Ihre XAML sollte in Visual Basic wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="c2bdc-149">Your XAML should look like this in Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#2_A](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt/MainWindow.xaml#2_a)]

    <span data-ttu-id="c2bdc-150">Oder in C# wie folgt:</span><span class="sxs-lookup"><span data-stu-id="c2bdc-150">Or like this in C#:</span></span>

    [!code-xaml[ExpenseIt#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/MainWindow.xaml#2)]

6. <span data-ttu-id="c2bdc-151">Open *"MainWindow.Xaml.vb"* oder *"MainWindow.Xaml.cs"*.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-151">Open *MainWindow.xaml.vb* or *MainWindow.xaml.cs*.</span></span>

    <span data-ttu-id="c2bdc-152">Diese Datei ist eine Code-Behind-Datei Code zum Behandeln der Ereignisse, die im deklarierten mit *"MainWindow.xaml"*.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-152">This file is a code-behind file that contains code to handle the events declared in *MainWindow.xaml*.</span></span> <span data-ttu-id="c2bdc-153">Diese Datei enthält eine partielle Klasse für das in XAML definierte Fenster.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-153">This file contains a partial class for the window defined in XAML.</span></span>

7. <span data-ttu-id="c2bdc-154">Wenn Sie c# verwenden, ändern Sie die `MainWindow` Klasse abgeleitet <xref:System.Windows.Navigation.NavigationWindow>.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-154">If you are using C#, change the `MainWindow` class to derive from <xref:System.Windows.Navigation.NavigationWindow>.</span></span> <span data-ttu-id="c2bdc-155">(In Visual Basic geschieht dies automatisch, wenn Sie das Fenster in XAML ändern.)</span><span class="sxs-lookup"><span data-stu-id="c2bdc-155">(In Visual Basic, this happens automatically when you change the window in XAML.)</span></span>

   <span data-ttu-id="c2bdc-156">Ihr Code sollte wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="c2bdc-156">Your code should look like this:</span></span>

   [!code-csharp[ExpenseIt#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/MainWindow.xaml.cs#3)]
   [!code-vb[ExpenseIt#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/MainWindow.xaml.vb#3)]

   > [!TIP]
   > <span data-ttu-id="c2bdc-157">Sie können die Codesprache des Beispielcodes zwischen c# und Visual Basic in Umschalten der **Sprache** Dropdownliste oben rechts auf der in diesem Artikel.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-157">You can toggle the code language of the sample code between C# and Visual Basic in the **Language** drop-down on the upper right side of this article.</span></span>

## <a name="add-files-to-the-application"></a><span data-ttu-id="c2bdc-158">Hinzufügen von Dateien zur Anwendung</span><span class="sxs-lookup"><span data-stu-id="c2bdc-158">Add files to the application</span></span>

<span data-ttu-id="c2bdc-159">In diesem Abschnitt fügen Sie der Anwendung zwei Seiten und ein Bild hinzu.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-159">In this section, you'll add two pages and an image to the application.</span></span>

1. <span data-ttu-id="c2bdc-160">Fügen Sie eine neue WPF-Seite auf das Projekt, und nennen Sie sie *`ExpenseItHome.xaml`*:</span><span class="sxs-lookup"><span data-stu-id="c2bdc-160">Add a new WPF page to the project, and name it *`ExpenseItHome.xaml`*:</span></span>

   1. <span data-ttu-id="c2bdc-161">In **Projektmappen-Explorer**, mit der rechten Maustaste auf die **`ExpenseIt`** Projektknoten und wählen **hinzufügen** > **Seite**.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-161">In **Solution Explorer**, right-click on the **`ExpenseIt`** project node and choose **Add** > **Page**.</span></span>

   1. <span data-ttu-id="c2bdc-162">In der **neues Element hinzufügen** im Dialogfeld die **Seite (WPF)** Vorlage bereits ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-162">In the **Add New Item** dialog, the **Page (WPF)** template is already selected.</span></span> <span data-ttu-id="c2bdc-163">Geben Sie den Namen **`ExpenseItHome`**, und wählen Sie dann **hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-163">Enter the name **`ExpenseItHome`**, and then select **Add**.</span></span>

    <span data-ttu-id="c2bdc-164">Diese Seite ist die erste Seite, die angezeigt wird, wenn die Anwendung gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-164">This page is the first page that's displayed when the application is launched.</span></span> <span data-ttu-id="c2bdc-165">Es zeigt eine Liste der Personen an, wählen aus, um eine Spesenabrechnung anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-165">It will show a list of people to select from, to show an expense report for.</span></span>

2. <span data-ttu-id="c2bdc-166">Open *`ExpenseItHome.xaml`*.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-166">Open *`ExpenseItHome.xaml`*.</span></span>

3. <span data-ttu-id="c2bdc-167">Legen Sie die <xref:System.Windows.Controls.Page.Title%2A> auf "`ExpenseIt - Home`".</span><span class="sxs-lookup"><span data-stu-id="c2bdc-167">Set the <xref:System.Windows.Controls.Page.Title%2A> to "`ExpenseIt - Home`".</span></span>

    <span data-ttu-id="c2bdc-168">Ihre XAML sollte in Visual Basic wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="c2bdc-168">Your XAML should look like this in Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#6_A](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml#6_a)]

    <span data-ttu-id="c2bdc-169">Oder in C# wie folgt:</span><span class="sxs-lookup"><span data-stu-id="c2bdc-169">Or this in C#:</span></span>

    [!code-xaml[ExpenseIt#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml#6)]

4. <span data-ttu-id="c2bdc-170">Open *"MainWindow.xaml"*.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-170">Open *MainWindow.xaml*.</span></span>

5. <span data-ttu-id="c2bdc-171">Legen Sie die <xref:System.Windows.Navigation.NavigationWindow.Source%2A> Eigenschaft für die <xref:System.Windows.Navigation.NavigationWindow> auf "`ExpenseItHome.xaml`".</span><span class="sxs-lookup"><span data-stu-id="c2bdc-171">Set the <xref:System.Windows.Navigation.NavigationWindow.Source%2A> property on the <xref:System.Windows.Navigation.NavigationWindow> to "`ExpenseItHome.xaml`".</span></span>

    <span data-ttu-id="c2bdc-172">Hiermit *`ExpenseItHome.xaml`* werden von der ersten Seite geöffnet werden soll, wenn die Anwendung gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-172">This sets *`ExpenseItHome.xaml`* to be the first page opened when the application starts.</span></span> <span data-ttu-id="c2bdc-173">Ihre XAML sollte in Visual Basic wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="c2bdc-173">Your XAML should look like this in Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#7_A](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/MainWindow.xaml#7_a)]

    <span data-ttu-id="c2bdc-174">Oder in C# wie folgt:</span><span class="sxs-lookup"><span data-stu-id="c2bdc-174">Or this in C#:</span></span>

    [!code-xaml[ExpenseIt#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/MainWindow.xaml#7)]

   > [!TIP]
   > <span data-ttu-id="c2bdc-175">Sie können auch Festlegen der **Quelle** -Eigenschaft in der **Sonstiges** Kategorie der **Eigenschaften** Fenster.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-175">You can also set the **Source** property in the **Miscellaneous** category of the **Properties** window.</span></span>
   >
   > ![Source-Eigenschaft im Fenster "Eigenschaften"](media/properties-source.png)

6. <span data-ttu-id="c2bdc-177">Hinzufügen einer anderen neuen WPF-Seite auf das Projekt, und nennen Sie sie *"ExpenseReportPage.xaml"*::</span><span class="sxs-lookup"><span data-stu-id="c2bdc-177">Add another new WPF page to the project, and name it *ExpenseReportPage.xaml*::</span></span>

   1. <span data-ttu-id="c2bdc-178">In **Projektmappen-Explorer**, mit der rechten Maustaste auf die **`ExpenseIt`** Projektknoten und wählen **hinzufügen** > **Seite**.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-178">In **Solution Explorer**, right-click on the **`ExpenseIt`** project node and choose **Add** > **Page**.</span></span>

   1. <span data-ttu-id="c2bdc-179">In der **neues Element hinzufügen** im Dialogfeld die **Seite (WPF)** Vorlage bereits ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-179">In the **Add New Item** dialog, the **Page (WPF)** template is already selected.</span></span> <span data-ttu-id="c2bdc-180">Geben Sie den Namen **ExpenseReportPage**, und wählen Sie dann **hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-180">Enter the name **ExpenseReportPage**, and then select **Add**.</span></span>

    <span data-ttu-id="c2bdc-181">Auf dieser Seite zeigt die Spesenabrechnung für die Person, die für ausgewählt, wird die **`ExpenseItHome`** Seite.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-181">This page will show the expense report for the person that is selected on the **`ExpenseItHome`** page.</span></span>

7. <span data-ttu-id="c2bdc-182">Öffnen Sie *ExpenseReportPage.xaml*.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-182">Open *ExpenseReportPage.xaml*.</span></span>

8. <span data-ttu-id="c2bdc-183">Legen Sie die <xref:System.Windows.Controls.Page.Title%2A> auf "`ExpenseIt - View Expense`".</span><span class="sxs-lookup"><span data-stu-id="c2bdc-183">Set the <xref:System.Windows.Controls.Page.Title%2A> to "`ExpenseIt - View Expense`".</span></span>

    <span data-ttu-id="c2bdc-184">Ihre XAML sollte in Visual Basic wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="c2bdc-184">Your XAML should look like this in Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#4_A](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml#4_a)]

    <span data-ttu-id="c2bdc-185">Oder in C# wie folgt:</span><span class="sxs-lookup"><span data-stu-id="c2bdc-185">Or this in C#:</span></span>

    [!code-xaml[ExpenseIt#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml#4)]

9. <span data-ttu-id="c2bdc-186">Open *"ExpenseItHome.Xaml.vb"* und *ExpenseReportPage.xaml.vb*, oder *"ExpenseItHome.Xaml.cs"* und *"ExpenseReportPage.Xaml.cs"*.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-186">Open *ExpenseItHome.xaml.vb* and *ExpenseReportPage.xaml.vb*, or *ExpenseItHome.xaml.cs* and *ExpenseReportPage.xaml.cs*.</span></span>

    <span data-ttu-id="c2bdc-187">Wenn Sie eine neue Seitendatei erstellen, erstellt Visual Studio automatisch eine *CodeBehind* Datei.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-187">When you create a new Page file, Visual Studio automatically creates a *code-behind* file.</span></span> <span data-ttu-id="c2bdc-188">Diese CodeBehind-Dateien behandeln die Logik zum Reagieren auf Benutzereingabe.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-188">These code-behind files handle the logic for responding to user input.</span></span>

    <span data-ttu-id="c2bdc-189">Der Code sollte aussehen wie folgt für **`ExpenseItHome`**:</span><span class="sxs-lookup"><span data-stu-id="c2bdc-189">Your code should look like this for **`ExpenseItHome`**:</span></span>

    [!code-csharp[ExpenseIt#2_5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml.cs#2_5)]
    [!code-vb[ExpenseIt#2_5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml.vb#2_5)]

    <span data-ttu-id="c2bdc-190">Und wie folgt für **ExpenseReportPage**:</span><span class="sxs-lookup"><span data-stu-id="c2bdc-190">And like this for **ExpenseReportPage**:</span></span>

    [!code-csharp[ExpenseIt#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml.cs#5)]
    [!code-vb[ExpenseIt#5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml.vb#5)]

10. <span data-ttu-id="c2bdc-191">Fügen Sie ein Bild mit dem Namen *watermark.png* zum Projekt.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-191">Add an image named *watermark.png* to the project.</span></span> <span data-ttu-id="c2bdc-192">Sie können Ihr eigenes Image erstellen, kopieren Sie die Datei aus dem Beispielcode oder erhalten sie [hier](https://github.com/dotnet/docs/blob/master/docs/framework/wpf/getting-started/media/watermark.png).</span><span class="sxs-lookup"><span data-stu-id="c2bdc-192">You can create your own image, copy the file from the sample code, or get it [here](https://github.com/dotnet/docs/blob/master/docs/framework/wpf/getting-started/media/watermark.png).</span></span>

   1. <span data-ttu-id="c2bdc-193">Mit der rechten Maustaste auf den Projektknoten, und wählen Sie **hinzufügen** > **vorhandenes Element**, oder drücken Sie **UMSCHALT**+**Alt** + **Ein**.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-193">Right-click on the project node and select **Add** > **Existing Item**, or press **Shift**+**Alt**+**A**.</span></span>

   2. <span data-ttu-id="c2bdc-194">In der **vorhandenes Element hinzufügen** suchen Sie die Image-Datei, die Sie verwenden möchten, und wählen Sie dann im Dialogfeld **hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-194">In the **Add Existing Item** dialog, browse to the image file you want to use, and then select **Add**.</span></span>

## <a name="build-and-run-the-application"></a><span data-ttu-id="c2bdc-195">Erstellen eines Builds und Ausführen der Anwendung</span><span class="sxs-lookup"><span data-stu-id="c2bdc-195">Build and run the application</span></span>

1. <span data-ttu-id="c2bdc-196">Zum Erstellen und die Anwendung auszuführen, drücken Sie die **F5** oder wählen Sie **Debuggen starten** aus der **Debuggen** Menü.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-196">To build and run the application, press **F5** or select **Start Debugging** from the **Debug** menu.</span></span>

    <span data-ttu-id="c2bdc-197">Die folgende Abbildung zeigt die Anwendung mit der <xref:System.Windows.Navigation.NavigationWindow> Schaltflächen:</span><span class="sxs-lookup"><span data-stu-id="c2bdc-197">The following illustration shows the application with the <xref:System.Windows.Navigation.NavigationWindow> buttons:</span></span>

    ![Bildschirmabbildung für ExpenseIt-Beispiel](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure1.png)

2. <span data-ttu-id="c2bdc-199">Schließen Sie die Anwendung zu Visual Studio zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-199">Close the application to return to Visual Studio.</span></span>

## <a name="create-the-layout"></a><span data-ttu-id="c2bdc-200">Erstellen Sie das layout</span><span class="sxs-lookup"><span data-stu-id="c2bdc-200">Create the layout</span></span>

<span data-ttu-id="c2bdc-201">Layout bietet die Möglichkeit, Elemente der Benutzeroberfläche zu platzieren und verwaltet auch die Größe und Position dieser Elemente beim Ändern der Größe einer Benutzeroberflächenautomatisierungs.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-201">Layout provides an ordered way to place UI elements, and also manages the size and position of those elements when a UI is resized.</span></span> <span data-ttu-id="c2bdc-202">In der Regel erstellen Sie Layout mit einem der folgenden Layoutsteuerelemente:</span><span class="sxs-lookup"><span data-stu-id="c2bdc-202">You typically create a layout with one of the following layout controls:</span></span>

- <xref:System.Windows.Controls.Canvas>
- <xref:System.Windows.Controls.DockPanel>
- <xref:System.Windows.Controls.Grid>
- <xref:System.Windows.Controls.StackPanel>
- <xref:System.Windows.Controls.VirtualizingStackPanel>
- <xref:System.Windows.Controls.WrapPanel>

<span data-ttu-id="c2bdc-203">Jedes dieser Layoutsteuerelemente unterstützt einen speziellen Layouttyp für seine untergeordneten Elemente.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-203">Each of these layout controls supports a special type of layout for its child elements.</span></span> <span data-ttu-id="c2bdc-204">`ExpenseIt` Seiten geändert werden können, und jede Seite verfügt über Elemente, die horizontal und vertikal neben anderen Elementen angeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-204">`ExpenseIt` pages can be resized, and each page has elements that are arranged horizontally and vertically alongside other elements.</span></span> <span data-ttu-id="c2bdc-205">Daher die <xref:System.Windows.Controls.Grid> ist das ideale Layoutelement für die Anwendung.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-205">Consequently, the <xref:System.Windows.Controls.Grid> is the ideal layout element for the application.</span></span>

> [!TIP]
> <span data-ttu-id="c2bdc-206">Weitere Informationen zu <xref:System.Windows.Controls.Panel> Elemente finden Sie unter [Übersicht über Panel](../../../../docs/framework/wpf/controls/panels-overview.md).</span><span class="sxs-lookup"><span data-stu-id="c2bdc-206">For more information about <xref:System.Windows.Controls.Panel> elements, see [Panels overview](../../../../docs/framework/wpf/controls/panels-overview.md).</span></span> <span data-ttu-id="c2bdc-207">Weitere Informationen zum Layout finden Sie unter [Layout](../../../../docs/framework/wpf/advanced/layout.md).</span><span class="sxs-lookup"><span data-stu-id="c2bdc-207">For more information about layout, see [Layout](../../../../docs/framework/wpf/advanced/layout.md).</span></span>

<span data-ttu-id="c2bdc-208">Klicken Sie im Abschnitt erstellen Sie eine einspaltige Tabelle mit drei Zeilen und einen 10-Pixel-Rand durch Hinzufügen von Spalten- und Zeilendefinitionen zu den <xref:System.Windows.Controls.Grid> in *`ExpenseItHome.xaml`*.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-208">In the section, you create a single-column table with three rows and a 10-pixel margin by adding column and row definitions to the <xref:System.Windows.Controls.Grid> in *`ExpenseItHome.xaml`*.</span></span>

1. <span data-ttu-id="c2bdc-209">Open *`ExpenseItHome.xaml`*.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-209">Open *`ExpenseItHome.xaml`*.</span></span>

2. <span data-ttu-id="c2bdc-210">Legen Sie die <xref:System.Windows.FrameworkElement.Margin%2A> Eigenschaft für die <xref:System.Windows.Controls.Grid> Element auf "10,0,10,10", auf der linken, oberen, rechten und unteren Ränder entspricht:</span><span class="sxs-lookup"><span data-stu-id="c2bdc-210">Set the <xref:System.Windows.FrameworkElement.Margin%2A> property on the <xref:System.Windows.Controls.Grid> element to "10,0,10,10", which corresponds to left, top, right and bottom margins:</span></span>

   ```xaml
   <Grid Margin="10,0,10,10">
   ```

   > [!TIP]
   > <span data-ttu-id="c2bdc-211">Sie können auch Festlegen der **Rand** Werte in der **Eigenschaften** Fenster unter dem **Layout** Kategorie:</span><span class="sxs-lookup"><span data-stu-id="c2bdc-211">You can also set the **Margin** values in the **Properties** window, under the **Layout** category:</span></span>
   >
   > ![Randwerte in Fenster "Eigenschaften"](media/properties-margin.png)

3. <span data-ttu-id="c2bdc-213">Fügen Sie das folgende XAML zwischen den <xref:System.Windows.Controls.Grid> Tags aus, um die Zeilen- und Spaltendefinitionen zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="c2bdc-213">Add the following XAML between the <xref:System.Windows.Controls.Grid> tags to create the row and column definitions:</span></span>

    [!code-xaml[ExpenseIt#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#8)]

    <span data-ttu-id="c2bdc-214">Die <xref:System.Windows.Controls.RowDefinition.Height%2A> zwei Zeilen wird festgelegt <xref:System.Windows.GridLength.Auto%2A>, was bedeutet, dass die Größe der Zeilen basierend auf dem Inhalt in den Zeilen.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-214">The <xref:System.Windows.Controls.RowDefinition.Height%2A> of two rows is set to <xref:System.Windows.GridLength.Auto%2A>, which means that the rows are sized based on the content in the rows.</span></span> <span data-ttu-id="c2bdc-215">Der Standardwert <xref:System.Windows.Controls.RowDefinition.Height%2A> ist <xref:System.Windows.GridUnitType.Star> größenanpassung, was bedeutet, dass die Zeilenhöhe eine gewichtete Proportion des verfügbaren Platzes ist.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-215">The default <xref:System.Windows.Controls.RowDefinition.Height%2A> is <xref:System.Windows.GridUnitType.Star> sizing, which means that the row height is a weighted proportion of the available space.</span></span> <span data-ttu-id="c2bdc-216">Wenn z. B. zwei Zeilen jeweils eine <xref:System.Windows.Controls.RowDefinition.Height%2A> von "\*", sie verfügen jeweils über eine Höhe von der Hälfte des verfügbaren Platzes ist.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-216">For example if two rows each have a <xref:System.Windows.Controls.RowDefinition.Height%2A> of "\*", they each have a height that is half of the available space.</span></span>

    <span data-ttu-id="c2bdc-217">Ihre <xref:System.Windows.Controls.Grid> sollte jetzt aussehen wie der folgende XAML:</span><span class="sxs-lookup"><span data-stu-id="c2bdc-217">Your <xref:System.Windows.Controls.Grid> should now look like the following XAML:</span></span>

    [!code-xaml[ExpenseIt#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#9)]

## <a name="add-controls"></a><span data-ttu-id="c2bdc-218">Hinzufügen von Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="c2bdc-218">Add controls</span></span>

<span data-ttu-id="c2bdc-219">In diesem Abschnitt Aktualisieren Sie die Homepage Benutzeroberfläche, um eine Liste der Personen anzuzeigen, die ein Benutzer auswählen kann, die Spesenabrechnung anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-219">In this section, you'll update the home page UI to show a list of people that a user can select from to show the expense report for.</span></span> <span data-ttu-id="c2bdc-220">Steuerelemente sind Benutzeroberflächenobjekte, die Benutzern die Interaktion mit der Anwendung ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-220">Controls are UI objects that allow users to interact with your application.</span></span> <span data-ttu-id="c2bdc-221">Weitere Informationen finden Sie unter [Steuerelemente](../../../../docs/framework/wpf/controls/index.md).</span><span class="sxs-lookup"><span data-stu-id="c2bdc-221">For more information, see [Controls](../../../../docs/framework/wpf/controls/index.md).</span></span>

<span data-ttu-id="c2bdc-222">Um diese Benutzeroberfläche zu erstellen, fügen Sie die folgenden Elemente zu *`ExpenseItHome.xaml`*:</span><span class="sxs-lookup"><span data-stu-id="c2bdc-222">To create this UI, you'll add the following elements to *`ExpenseItHome.xaml`*:</span></span>

- <span data-ttu-id="c2bdc-223"><xref:System.Windows.Controls.ListBox> (für die Liste der Personen).</span><span class="sxs-lookup"><span data-stu-id="c2bdc-223"><xref:System.Windows.Controls.ListBox> (for the list of people).</span></span>
- <span data-ttu-id="c2bdc-224"><xref:System.Windows.Controls.Label> (für den Listenheader).</span><span class="sxs-lookup"><span data-stu-id="c2bdc-224"><xref:System.Windows.Controls.Label> (for the list header).</span></span>
- <span data-ttu-id="c2bdc-225"><xref:System.Windows.Controls.Button> (zum klicken, um die Spesenabrechnung für die Person anzuzeigen, die in der Liste ausgewählt ist).</span><span class="sxs-lookup"><span data-stu-id="c2bdc-225"><xref:System.Windows.Controls.Button> (to click to view the expense report for the person that is selected in the list).</span></span>

<span data-ttu-id="c2bdc-226">Jedes Steuerelement wird in einer Zeile platziert die <xref:System.Windows.Controls.Grid> durch Festlegen der <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> angefügte Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-226">Each control is placed in a row of the <xref:System.Windows.Controls.Grid> by setting the <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> attached property.</span></span> <span data-ttu-id="c2bdc-227">Weitere Informationen zu angefügten Eigenschaften finden Sie unter [Übersicht über angefügte Eigenschaften](../../../../docs/framework/wpf/advanced/attached-properties-overview.md).</span><span class="sxs-lookup"><span data-stu-id="c2bdc-227">For more information about attached properties, see [Attached Properties Overview](../../../../docs/framework/wpf/advanced/attached-properties-overview.md).</span></span>

1. <span data-ttu-id="c2bdc-228">Open *`ExpenseItHome.xaml`*.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-228">Open *`ExpenseItHome.xaml`*.</span></span>

2. <span data-ttu-id="c2bdc-229">Fügen Sie den folgenden XAML an einer beliebigen Stelle zwischen den <xref:System.Windows.Controls.Grid> Tags:</span><span class="sxs-lookup"><span data-stu-id="c2bdc-229">Add the following XAML somewhere between the <xref:System.Windows.Controls.Grid> tags:</span></span>

   [!code-xaml[ExpenseIt#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt4/ExpenseItHome.xaml#10)]

   > [!TIP]
   > <span data-ttu-id="c2bdc-230">Sie können die Steuerelemente auch erstellen, ziehen sie aus der **Toolbox** Fenster in das Entwurfsfenster, und klicken Sie dann ihre Einstellungen der **Eigenschaften** Fenster.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-230">You can also create the controls by dragging them from the **Toolbox** window onto the design window, and then setting their properties in the **Properties** window.</span></span>

3. <span data-ttu-id="c2bdc-231">Erstellen Sie die Anwendung, und führen Sie sie aus.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-231">Build and run the application.</span></span>

<span data-ttu-id="c2bdc-232">Die folgende Abbildung zeigt die Steuerelemente, dass Sie gerade erstellt haben:</span><span class="sxs-lookup"><span data-stu-id="c2bdc-232">The following illustration shows the controls you just created:</span></span>

![Bildschirmabbildung für ExpenseIt-Beispiel](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure2.png)

## <a name="add-an-image-and-a-title"></a><span data-ttu-id="c2bdc-234">Fügen Sie ein Image und einen Titel hinzu</span><span class="sxs-lookup"><span data-stu-id="c2bdc-234">Add an image and a title</span></span>

<span data-ttu-id="c2bdc-235">In diesem Abschnitt Aktualisieren Sie die Benutzeroberfläche der Homepage mit einem Bild und einem Seitentitel.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-235">In this section, you'll update the home page UI with an image and a page title.</span></span>

1. <span data-ttu-id="c2bdc-236">Open *`ExpenseItHome.xaml`*.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-236">Open *`ExpenseItHome.xaml`*.</span></span>

2. <span data-ttu-id="c2bdc-237">Fügen Sie eine andere Spalte als die <xref:System.Windows.Controls.Grid.ColumnDefinitions%2A> mit einer festen <xref:System.Windows.Controls.ColumnDefinition.Width%2A> von 230 Pixel:</span><span class="sxs-lookup"><span data-stu-id="c2bdc-237">Add another column to the <xref:System.Windows.Controls.Grid.ColumnDefinitions%2A> with a fixed <xref:System.Windows.Controls.ColumnDefinition.Width%2A> of 230 pixels:</span></span>

    [!code-xaml[ExpenseIt#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#11)]

3. <span data-ttu-id="c2bdc-238">Hinzufügen zu einer anderen Zeile der <xref:System.Windows.Controls.Grid.RowDefinitions%2A>, also insgesamt vier Zeilen:</span><span class="sxs-lookup"><span data-stu-id="c2bdc-238">Add another row to the <xref:System.Windows.Controls.Grid.RowDefinitions%2A>, for a total of four rows:</span></span>

    [!code-xaml[ExpenseIt#11b](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#11b)]

4. <span data-ttu-id="c2bdc-239">Verschieben Sie die Steuerelemente in die zweite Spalte, durch Festlegen der <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> -Eigenschaft auf 1 in jedem der drei Steuerelemente (Rahmen, ListBox und Schaltfläche ").</span><span class="sxs-lookup"><span data-stu-id="c2bdc-239">Move the controls to the second column by setting the <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> property to 1 in each of the three controls (Border, ListBox, and Button).</span></span>

5. <span data-ttu-id="c2bdc-240">Verschieben Sie jedes Steuerelement eine Zeile aus, nach unten durch Erhöhen der <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> -Wert um 1.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-240">Move each control down a row, by incrementing its <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> value by 1.</span></span>

   <span data-ttu-id="c2bdc-241">Der XAML für die drei Steuerelemente sieht nun folgendermaßen aus:</span><span class="sxs-lookup"><span data-stu-id="c2bdc-241">The XAML for the three controls now looks like this:</span></span>

    [!code-xaml[ExpenseIt#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#12)]

6. <span data-ttu-id="c2bdc-242">Festlegen der <xref:System.Windows.Controls.Panel.Background%2A> von der <xref:System.Windows.Controls.Grid> sein der *watermark.png* Bilddatei, durch das Hinzufügen der folgende XAML irgendwo zwischen der `<Grid>` und `</Grid>` Tags:</span><span class="sxs-lookup"><span data-stu-id="c2bdc-242">Set the <xref:System.Windows.Controls.Panel.Background%2A> of the <xref:System.Windows.Controls.Grid> to be the *watermark.png* image file, by adding the following XAML somewhere between the `<Grid>` and `</Grid>` tags:</span></span>

    [!code-xaml[ExpenseIt#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#14)]

7. <span data-ttu-id="c2bdc-243">Vor der <xref:System.Windows.Controls.Border> -Element, Hinzufügen einer <xref:System.Windows.Controls.Label> mit dem Inhalt "View Expense Report".</span><span class="sxs-lookup"><span data-stu-id="c2bdc-243">Before the <xref:System.Windows.Controls.Border> element, add a <xref:System.Windows.Controls.Label> with the content "View Expense Report".</span></span> <span data-ttu-id="c2bdc-244">Dies ist der Titel der Seite.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-244">This is the title of the page.</span></span>

    [!code-xaml[ExpenseIt#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#13)]

8. <span data-ttu-id="c2bdc-245">Erstellen Sie die Anwendung, und führen Sie sie aus.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-245">Build and run the application.</span></span>

<span data-ttu-id="c2bdc-246">Die folgende Abbildung zeigt die Ergebnisse von was Sie gerade hinzugefügt haben:</span><span class="sxs-lookup"><span data-stu-id="c2bdc-246">The following illustration shows the results of what you just added:</span></span>

![Bildschirmabbildung für ExpenseIt-Beispiel](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure3.png)

## <a name="add-code-to-handle-events"></a><span data-ttu-id="c2bdc-248">Fügen Sie Code zum Verarbeiten von Ereignissen</span><span class="sxs-lookup"><span data-stu-id="c2bdc-248">Add code to handle events</span></span>

1. <span data-ttu-id="c2bdc-249">Open *`ExpenseItHome.xaml`*.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-249">Open *`ExpenseItHome.xaml`*.</span></span>

2. <span data-ttu-id="c2bdc-250">Hinzufügen einer <xref:System.Windows.Controls.Primitives.ButtonBase.Click> -Ereignishandler der <xref:System.Windows.Controls.Button> Element.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-250">Add a <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler to the <xref:System.Windows.Controls.Button> element.</span></span> <span data-ttu-id="c2bdc-251">Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen eines einfachen ereignishandlers](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb675300(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="c2bdc-251">For more information, see [How to: Create a simple event handler](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb675300(v=vs.100)).</span></span>

    [!code-xaml[ExpenseIt#15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml#15)]

3. <span data-ttu-id="c2bdc-252">Open *`ExpenseItHome.xaml.vb`* oder *`ExpenseItHome.xaml.cs`*.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-252">Open *`ExpenseItHome.xaml.vb`* or *`ExpenseItHome.xaml.cs`*.</span></span>

4. <span data-ttu-id="c2bdc-253">Fügen Sie den folgenden Code der `ExpenseItHome` Klasse, um eine Schaltfläche hinzufügen-click-Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-253">Add the following code to the `ExpenseItHome` class to add a button click event handler.</span></span> <span data-ttu-id="c2bdc-254">Der Ereignishandler öffnet die **ExpenseReportPage** Seite.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-254">The event handler opens the **ExpenseReportPage** page.</span></span>

    [!code-csharp[ExpenseIt#16](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml.cs#16)]
    [!code-vb[ExpenseIt#16](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt6/ExpenseItHome.xaml.vb#16)]

## <a name="create-the-ui-for-expensereportpage"></a><span data-ttu-id="c2bdc-255">Erstellen der Benutzeroberfläche für ExpenseReportPage</span><span class="sxs-lookup"><span data-stu-id="c2bdc-255">Create the UI for ExpenseReportPage</span></span>

<span data-ttu-id="c2bdc-256">*"ExpenseReportPage.xaml"* zeigt die Spesenabrechnung für die Person, die für ausgewählt, wird die **`ExpenseItHome`** Seite.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-256">*ExpenseReportPage.xaml* displays the expense report for the person that's selected on the **`ExpenseItHome`** page.</span></span> <span data-ttu-id="c2bdc-257">In diesem Abschnitt erstellen Sie die Benutzeroberfläche für **ExpenseReportPage**.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-257">In this section, you'll create the UI for **ExpenseReportPage**.</span></span> <span data-ttu-id="c2bdc-258">Außerdem fügen Hintergrund und Füllfarben zwischen den verschiedenen UI-Elementen.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-258">You'll also add background and fill colors to the various UI elements.</span></span>

1. <span data-ttu-id="c2bdc-259">Öffnen Sie *ExpenseReportPage.xaml*.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-259">Open *ExpenseReportPage.xaml*.</span></span>

2. <span data-ttu-id="c2bdc-260">Fügen Sie das folgende XAML zwischen den <xref:System.Windows.Controls.Grid> Tags:</span><span class="sxs-lookup"><span data-stu-id="c2bdc-260">Add the following XAML between the <xref:System.Windows.Controls.Grid> tags:</span></span>

    [!code-xaml[ExpenseIt#17](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseReportPage.xaml#17)]

    <span data-ttu-id="c2bdc-261">Diese Benutzeroberfläche ähnelt *`ExpenseItHome.xaml`*, außer dass die Daten des Berichts, in angezeigt werden einem <xref:System.Windows.Controls.DataGrid>.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-261">This UI is similar to *`ExpenseItHome.xaml`*, except the report data is displayed in a <xref:System.Windows.Controls.DataGrid>.</span></span>

3. <span data-ttu-id="c2bdc-262">Erstellen Sie die Anwendung, und führen Sie sie aus.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-262">Build and run the application.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c2bdc-263">Wenn Sie eine Fehlermeldung, die erhalten die <xref:System.Windows.Controls.DataGrid> wurde nicht gefunden oder nicht vorhanden ist, stellen Sie sicher, dass das Projekt auf .NET Framework 4 oder höher abzielt.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-263">If you get an error that the <xref:System.Windows.Controls.DataGrid> was not found or does not exist, make sure that your project targets the .NET Framework 4 or later.</span></span> <span data-ttu-id="c2bdc-264">Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen von Projekten für eine bestimmte .NET Framework-Version](/visualstudio/ide/how-to-target-a-version-of-the-dotnet-framework).</span><span class="sxs-lookup"><span data-stu-id="c2bdc-264">For more information, see [How to: Target a Version of the .NET Framework](/visualstudio/ide/how-to-target-a-version-of-the-dotnet-framework).</span></span>

4. <span data-ttu-id="c2bdc-265">Wählen Sie die **Ansicht** Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-265">Select the **View** button.</span></span>

    <span data-ttu-id="c2bdc-266">Die Spesenabrechnungsseite wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-266">The expense report page appears.</span></span> <span data-ttu-id="c2bdc-267">Beachten Sie außerdem, dass die Navigationsschaltfläche "zurück" aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-267">Also notice that the back navigation button is enabled.</span></span>

<span data-ttu-id="c2bdc-268">Die folgende Abbildung zeigt die Elemente der Benutzeroberfläche hinzugefügt *"ExpenseReportPage.xaml"*.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-268">The following illustration shows the UI elements added to *ExpenseReportPage.xaml*.</span></span>

![Bildschirmabbildung für ExpenseIt-Beispiel](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure4.png)

## <a name="style-controls"></a><span data-ttu-id="c2bdc-270">Formatieren von Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="c2bdc-270">Style controls</span></span>

<span data-ttu-id="c2bdc-271">Die Darstellung verschiedener Elemente ist häufig für alle Elemente des gleichen Typs in einer Benutzeroberfläche identisch.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-271">The appearance of various elements is often the same for all elements of the same type in a UI.</span></span> <span data-ttu-id="c2bdc-272">Benutzeroberfläche verwendet [Stile](../../../../docs/framework/wpf/controls/styling-and-templating.md) Darstellungen in mehreren Elementen wieder verwendbaren vornehmen.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-272">UI uses [styles](../../../../docs/framework/wpf/controls/styling-and-templating.md) to make appearances reusable across multiple elements.</span></span> <span data-ttu-id="c2bdc-273">Die wiederverwendbarkeit von Stilen können Sie die um XAML-Erstellung und Verwaltung zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-273">The reusability of styles helps to simplify XAML creation and management.</span></span> <span data-ttu-id="c2bdc-274">Dieser Abschnitt ersetzt die Attribute pro Element, die in den vorherigen Schritten mit Stilen definiert wurden.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-274">This section replaces the per-element attributes that were defined in previous steps with styles.</span></span>

1. <span data-ttu-id="c2bdc-275">Open *"Application.xaml"* oder *"App.xaml"*.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-275">Open *Application.xaml* or *App.xaml*.</span></span>

2. <span data-ttu-id="c2bdc-276">Fügen Sie das folgende XAML zwischen den <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> Tags:</span><span class="sxs-lookup"><span data-stu-id="c2bdc-276">Add the following XAML between the <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> tags:</span></span>

    [!code-xaml[ExpenseIt#18](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/App.xaml#18)]

    <span data-ttu-id="c2bdc-277">Durch diese XAML werden folgende Stile hinzugefügt:</span><span class="sxs-lookup"><span data-stu-id="c2bdc-277">This XAML adds the following styles:</span></span>

    - <span data-ttu-id="c2bdc-278">`headerTextStyle`: Zum Formatieren des Seitentitels <xref:System.Windows.Controls.Label>.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-278">`headerTextStyle`: To format the page title <xref:System.Windows.Controls.Label>.</span></span>

    - <span data-ttu-id="c2bdc-279">`labelStyle`: Zum Formatieren der <xref:System.Windows.Controls.Label> Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-279">`labelStyle`: To format the <xref:System.Windows.Controls.Label> controls.</span></span>

    - <span data-ttu-id="c2bdc-280">`columnHeaderStyle`: Zum Formatieren der <xref:System.Windows.Controls.Primitives.DataGridColumnHeader>.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-280">`columnHeaderStyle`: To format the <xref:System.Windows.Controls.Primitives.DataGridColumnHeader>.</span></span>

    - <span data-ttu-id="c2bdc-281">`listHeaderStyle`: Zum Formatieren der Kopfzeile <xref:System.Windows.Controls.Border> Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-281">`listHeaderStyle`: To format the list header <xref:System.Windows.Controls.Border> controls.</span></span>

    - <span data-ttu-id="c2bdc-282">`listHeaderTextStyle`: Zum Formatieren der Kopfzeile <xref:System.Windows.Controls.Label>.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-282">`listHeaderTextStyle`: To format the list header <xref:System.Windows.Controls.Label>.</span></span>

    - <span data-ttu-id="c2bdc-283">`buttonStyle`: Zum Formatieren der <xref:System.Windows.Controls.Button> auf `ExpenseItHome.xaml`.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-283">`buttonStyle`: To format the <xref:System.Windows.Controls.Button> on `ExpenseItHome.xaml`.</span></span>

    <span data-ttu-id="c2bdc-284">Beachten Sie, dass die Ressourcen und die untergeordneten Elemente werden der <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> Property-Element.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-284">Notice that the styles are resources and children of the <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> property element.</span></span> <span data-ttu-id="c2bdc-285">An diesem Speicherort werden die Stile auf alle Elemente in einer Anwendung angewendet.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-285">In this location, the styles are applied to all the elements in an application.</span></span> <span data-ttu-id="c2bdc-286">Ein Beispiel der Verwendung von Ressourcen in einer .NET Framework-Anwendung finden Sie unter [Verwenden von Anwendungsressourcen](../../../../docs/framework/wpf/advanced/how-to-use-application-resources.md).</span><span class="sxs-lookup"><span data-stu-id="c2bdc-286">For an example of using resources in a .NET Framework application, see [Use Application Resources](../../../../docs/framework/wpf/advanced/how-to-use-application-resources.md).</span></span>

3. <span data-ttu-id="c2bdc-287">Open *`ExpenseItHome.xaml`*.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-287">Open *`ExpenseItHome.xaml`*.</span></span>

4. <span data-ttu-id="c2bdc-288">Ersetzen Sie alles zwischen dem <xref:System.Windows.Controls.Grid> Elemente mit den folgenden XAML:</span><span class="sxs-lookup"><span data-stu-id="c2bdc-288">Replace everything between the <xref:System.Windows.Controls.Grid> elements with the following XAML:</span></span>

    [!code-xaml[ExpenseIt#19](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseItHome.xaml#19)]

    <span data-ttu-id="c2bdc-289">Eigenschaften wie <xref:System.Windows.VerticalAlignment> und <xref:System.Windows.Media.FontFamily> , die die Darstellung der einzelnen Steuerelemente definieren, werden entfernt und ersetzt, indem die Stile angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-289">The properties such as <xref:System.Windows.VerticalAlignment> and <xref:System.Windows.Media.FontFamily> that define the look of each control are removed and replaced by applying the styles.</span></span> <span data-ttu-id="c2bdc-290">Z. B. die `headerTextStyle` gilt für die "View Expense Report" <xref:System.Windows.Controls.Label>.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-290">For example, the `headerTextStyle` is applied to the "View Expense Report" <xref:System.Windows.Controls.Label>.</span></span>

5. <span data-ttu-id="c2bdc-291">Öffnen Sie *ExpenseReportPage.xaml*.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-291">Open *ExpenseReportPage.xaml*.</span></span>

6. <span data-ttu-id="c2bdc-292">Ersetzen Sie alles zwischen dem <xref:System.Windows.Controls.Grid> Elemente mit den folgenden XAML:</span><span class="sxs-lookup"><span data-stu-id="c2bdc-292">Replace everything between the <xref:System.Windows.Controls.Grid> elements with the following XAML:</span></span>

    [!code-xaml[ExpenseIt#20](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseReportPage.xaml#20)]

    <span data-ttu-id="c2bdc-293">Dadurch werden dem <xref:System.Windows.Controls.Label> -Element und <xref:System.Windows.Controls.Border> -Element Stile hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-293">This adds styles to the <xref:System.Windows.Controls.Label> and <xref:System.Windows.Controls.Border> elements.</span></span>

## <a name="bind-data-to-a-control"></a><span data-ttu-id="c2bdc-294">Binden von Daten an ein Steuerelement</span><span class="sxs-lookup"><span data-stu-id="c2bdc-294">Bind data to a control</span></span>

<span data-ttu-id="c2bdc-295">In diesem Abschnitt erstellen Sie die XML-Daten, die an verschiedene Steuerelemente gebunden ist.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-295">In this section, you'll create the XML data that is bound to various controls.</span></span>

1. <span data-ttu-id="c2bdc-296">Open *`ExpenseItHome.xaml`*.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-296">Open *`ExpenseItHome.xaml`*.</span></span>

2. <span data-ttu-id="c2bdc-297">Nach dem öffnenden <xref:System.Windows.Controls.Grid> -Element, fügen Sie den folgenden XAML zum Erstellen einer <xref:System.Windows.Data.XmlDataProvider> , die Daten für jede Person enthält:</span><span class="sxs-lookup"><span data-stu-id="c2bdc-297">After the opening <xref:System.Windows.Controls.Grid> element, add the following XAML to create an <xref:System.Windows.Data.XmlDataProvider> that contains the data for each person:</span></span>

    [!code-xaml[ExpenseIt#21](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#21)]
    [!code-xaml[ExpenseIt#23](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#23)]
    [!code-xaml[ExpenseIt#22](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#22)]

    <span data-ttu-id="c2bdc-298">Die Daten werden als erstellt eine <xref:System.Windows.Controls.Grid> Ressource.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-298">The data is created as a <xref:System.Windows.Controls.Grid> resource.</span></span> <span data-ttu-id="c2bdc-299">Normalerweise würde sie als Datei geladen, aus Gründen der Einfachheit werden die Daten aber inline hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-299">Normally this would be loaded as a file, but for simplicity the data is added inline.</span></span>

3. <span data-ttu-id="c2bdc-300">In der `<Grid.Resources>` -Element, fügen Sie die folgenden <xref:System.Windows.DataTemplate>, die definiert, wie zum Anzeigen der Daten in die <xref:System.Windows.Controls.ListBox>:</span><span class="sxs-lookup"><span data-stu-id="c2bdc-300">Within the `<Grid.Resources>` element, add the following <xref:System.Windows.DataTemplate>, which defines how to display the data in the <xref:System.Windows.Controls.ListBox>:</span></span>

    [!code-xaml[ExpenseIt#21](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#21)]
    [!code-xaml[ExpenseIt#24](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#24)]
    [!code-xaml[ExpenseIt#22](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#22)]

    <span data-ttu-id="c2bdc-301">Weitere Informationen zu Datenvorlagen finden Sie unter [Übersicht über Datenvorlagen](../../../../docs/framework/wpf/data/data-templating-overview.md).</span><span class="sxs-lookup"><span data-stu-id="c2bdc-301">For more information about data templates, see [Data templating overview](../../../../docs/framework/wpf/data/data-templating-overview.md).</span></span>

4. <span data-ttu-id="c2bdc-302">Ersetzen Sie die vorhandene <xref:System.Windows.Controls.ListBox> mit den folgenden XAML:</span><span class="sxs-lookup"><span data-stu-id="c2bdc-302">Replace the existing <xref:System.Windows.Controls.ListBox> with the following XAML:</span></span>

    [!code-xaml[ExpenseIt#25](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#25)]

    <span data-ttu-id="c2bdc-303">Dieses XAML bindet die <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> Eigenschaft der <xref:System.Windows.Controls.ListBox> an die Datenquelle und wendet die Datenvorlage als die <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-303">This XAML binds the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> property of the <xref:System.Windows.Controls.ListBox> to the data source and applies the data template as the <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>.</span></span>

## <a name="connect-data-to-controls"></a><span data-ttu-id="c2bdc-304">Verbinden Sie Daten an Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="c2bdc-304">Connect data to controls</span></span>

<span data-ttu-id="c2bdc-305">Anschließend fügen Sie Code zum Abrufen des Namens, der ausgewählt wird die **`ExpenseItHome`** Seite, und übergeben Sie es an den Konstruktor der **ExpenseReportPage**.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-305">Next, you'll add code to retrieve the name that's selected on the **`ExpenseItHome`** page and pass it to the constructor of **ExpenseReportPage**.</span></span> <span data-ttu-id="c2bdc-306">**ExpenseReportPage** legt den Datenkontext mithilfe des übergebenen Elements, die die Steuerelemente definierten in *"ExpenseReportPage.xaml"* Binden an.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-306">**ExpenseReportPage** sets its data context with the passed item, which is what the controls defined in *ExpenseReportPage.xaml* bind to.</span></span>

1. <span data-ttu-id="c2bdc-307">Öffnen Sie *ExpenseReportPage.xaml.vb* oder *ExpenseReportPage.xaml.cs*.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-307">Open *ExpenseReportPage.xaml.vb* or *ExpenseReportPage.xaml.cs*.</span></span>

2. <span data-ttu-id="c2bdc-308">Fügen Sie einen Konstruktor hinzu, der ein Objekt akzeptiert, damit Sie die Spesenabrechnungsdaten der ausgewählten Person übergeben können.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-308">Add a constructor that takes an object so you can pass the expense report data of the selected person.</span></span>

    [!code-csharp[ExpenseIt#26](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseReportPage.xaml.cs#26)]
    [!code-vb[ExpenseIt#26](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseReportPage.xaml.vb#26)]

3. <span data-ttu-id="c2bdc-309">Open *`ExpenseItHome.xaml.vb`* oder *`ExpenseItHome.xaml.cs`*.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-309">Open *`ExpenseItHome.xaml.vb`* or *`ExpenseItHome.xaml.cs`*.</span></span>

4. <span data-ttu-id="c2bdc-310">Ändern der <xref:System.Windows.Controls.Primitives.ButtonBase.Click> -Ereignishandler aufrufen, den neuen Konstruktor, der die Spesenabrechnungsdaten der ausgewählten Person übergeben.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-310">Change the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler to call the new constructor passing the expense report data of the selected person.</span></span>

    [!code-csharp[ExpenseIt#27](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml.cs#27)]
    [!code-vb[ExpenseIt#27](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseItHome.xaml.vb#27)]

## <a name="style-data-with-data-templates"></a><span data-ttu-id="c2bdc-311">Style-Daten mit Datenvorlagen</span><span class="sxs-lookup"><span data-stu-id="c2bdc-311">Style data with data templates</span></span>

<span data-ttu-id="c2bdc-312">In diesem Abschnitt Aktualisieren Sie die Benutzeroberfläche für jedes Element in den datengebundenen Listen mithilfe von Datenvorlagen.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-312">In this section, you'll update the UI for each item in the data-bound lists by using data templates.</span></span>

1. <span data-ttu-id="c2bdc-313">Öffnen Sie *ExpenseReportPage.xaml*.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-313">Open *ExpenseReportPage.xaml*.</span></span>

2. <span data-ttu-id="c2bdc-314">Binden Sie den Inhalt der "Name" und "Department" <xref:System.Windows.Controls.Label> Elemente an die entsprechende Datenquelleneigenschaft.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-314">Bind the content of the "Name" and "Department" <xref:System.Windows.Controls.Label> elements to the appropriate data source property.</span></span> <span data-ttu-id="c2bdc-315">Weitere Informationen zur Datenbindung finden Sie unter [Übersicht über die Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md).</span><span class="sxs-lookup"><span data-stu-id="c2bdc-315">For more information about data binding, see [Data binding overview](../../../../docs/framework/wpf/data/data-binding-overview.md).</span></span>

    [!code-xaml[ExpenseIt#31](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#31)]

3. <span data-ttu-id="c2bdc-316">Nach dem öffnenden <xref:System.Windows.Controls.Grid> -Element, fügen Sie die folgenden Datenvorlagen, die definieren, wie die Spesenabrechnungsdaten angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="c2bdc-316">After the opening <xref:System.Windows.Controls.Grid> element, add the following data templates, which define how to display the expense report data:</span></span>

    [!code-xaml[ExpenseIt#30](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#30)]

4. <span data-ttu-id="c2bdc-317">Ersetzen Sie die <xref:System.Windows.Controls.DataGridTextColumn> Elemente mit <xref:System.Windows.Controls.DataGridTemplateColumn> unter der <xref:System.Windows.Controls.DataGrid> Element und die Vorlagen auf sie angewendet.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-317">Replace the <xref:System.Windows.Controls.DataGridTextColumn> elements with <xref:System.Windows.Controls.DataGridTemplateColumn> under the <xref:System.Windows.Controls.DataGrid> element and apply the templates to them.</span></span>

    [!code-xaml[ExpenseIt#32](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#32)]

5. <span data-ttu-id="c2bdc-318">Erstellen Sie die Anwendung, und führen Sie sie aus.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-318">Build and run the application.</span></span>

6. <span data-ttu-id="c2bdc-319">Wählen Sie eine Person ein, und wählen Sie dann die **Ansicht** Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-319">Select a person and then select the **View** button.</span></span>

<span data-ttu-id="c2bdc-320">Die folgende Abbildung zeigt die beiden Seiten von der `ExpenseIt` Anwendung mit Steuerelementen, Layout, Stilen, Datenbindung und Datenvorlagen angewendet:</span><span class="sxs-lookup"><span data-stu-id="c2bdc-320">The following illustration shows both pages of the `ExpenseIt` application with controls, layout, styles, data binding, and data templates applied:</span></span>

![Bildschirmabbildungen für ExpenseIt-Beispiel](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure5.png)

> [!NOTE]
> <span data-ttu-id="c2bdc-322">In diesem Beispiel wird veranschaulicht, eine bestimmte Funktion von WPF und nicht alle bewährte Methoden für Aspekte wie Sicherheit, Lokalisierung und Eingabehilfen.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-322">This sample demonstrates a specific feature of WPF and doesn't follow all best practices for things like security, localization, and accessibility.</span></span> <span data-ttu-id="c2bdc-323">Umfassende Behandlung von WPF und bewährte Methoden für die Anwendungsentwicklung die .NET Framework finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="c2bdc-323">For comprehensive coverage of WPF and the .NET Framework application development best practices, see the following topics:</span></span>
>
> - [<span data-ttu-id="c2bdc-324">Barrierefreiheit</span><span class="sxs-lookup"><span data-stu-id="c2bdc-324">Accessibility</span></span>](../../../../docs/framework/ui-automation/accessibility-best-practices.md)
>
> - [<span data-ttu-id="c2bdc-325">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="c2bdc-325">Security</span></span>](../../../../docs/framework/wpf/security-wpf.md)
>
> - [<span data-ttu-id="c2bdc-326">Übersicht über WPF-Globalisierung und -Lokalisierung</span><span class="sxs-lookup"><span data-stu-id="c2bdc-326">WPF globalization and localization</span></span>](../../../../docs/framework/wpf/advanced/wpf-globalization-and-localization-overview.md)
>
> - [<span data-ttu-id="c2bdc-327">Von WPF</span><span class="sxs-lookup"><span data-stu-id="c2bdc-327">WPF performance</span></span>](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)

## <a name="next-steps"></a><span data-ttu-id="c2bdc-328">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="c2bdc-328">Next steps</span></span>

<span data-ttu-id="c2bdc-329">In dieser exemplarischen Vorgehensweise haben Sie gelernt, eine Reihe von Techniken zum Erstellen einer Benutzeroberfläche mit Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="c2bdc-329">In this walkthrough you learned a number of techniques for creating a UI using Windows Presentation Foundation (WPF).</span></span> <span data-ttu-id="c2bdc-330">Sie verfügen nun über einen grundlegenden Überblick über die Bausteine einer datengebundenen, .NET Framework-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="c2bdc-330">You should now have a basic understanding of the building blocks of a data-bound, .NET Framework application.</span></span> <span data-ttu-id="c2bdc-331">Weitere Informationen über die WPF-Architektur und -Programmiermodelle finden Sie in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="c2bdc-331">For more information about the WPF architecture and programming models, see the following topics:</span></span>

- [<span data-ttu-id="c2bdc-332">WPF-Architektur</span><span class="sxs-lookup"><span data-stu-id="c2bdc-332">WPF architecture</span></span>](../../../../docs/framework/wpf/advanced/wpf-architecture.md)
- [<span data-ttu-id="c2bdc-333">Übersicht über XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="c2bdc-333">XAML overview (WPF)</span></span>](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)
- [<span data-ttu-id="c2bdc-334">Übersicht über Abhängigkeitseigenschaften</span><span class="sxs-lookup"><span data-stu-id="c2bdc-334">Dependency properties overview</span></span>](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)
- [<span data-ttu-id="c2bdc-335">Layout</span><span class="sxs-lookup"><span data-stu-id="c2bdc-335">Layout</span></span>](../../../../docs/framework/wpf/advanced/layout.md)

<span data-ttu-id="c2bdc-336">Weitere Informationen zum Erstellen von Anwendungen finden Sie in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="c2bdc-336">For more information about creating applications, see the following topics:</span></span>

- [<span data-ttu-id="c2bdc-337">Anwendungsentwicklung</span><span class="sxs-lookup"><span data-stu-id="c2bdc-337">Application development</span></span>](../../../../docs/framework/wpf/app-development/index.md)
- [<span data-ttu-id="c2bdc-338">Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="c2bdc-338">Controls</span></span>](../../../../docs/framework/wpf/controls/index.md)
- [<span data-ttu-id="c2bdc-339">Übersicht über Datenbindung</span><span class="sxs-lookup"><span data-stu-id="c2bdc-339">Data binding overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)
- [<span data-ttu-id="c2bdc-340">Grafiken und multimedia</span><span class="sxs-lookup"><span data-stu-id="c2bdc-340">Graphics and multimedia</span></span>](../../../../docs/framework/wpf/graphics-multimedia/index.md)
- [<span data-ttu-id="c2bdc-341">Dokumente in WPF</span><span class="sxs-lookup"><span data-stu-id="c2bdc-341">Documents in WPF</span></span>](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)

## <a name="see-also"></a><span data-ttu-id="c2bdc-342">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c2bdc-342">See also</span></span>

- [<span data-ttu-id="c2bdc-343">Übersicht über Panel</span><span class="sxs-lookup"><span data-stu-id="c2bdc-343">Panels overview</span></span>](../../../../docs/framework/wpf/controls/panels-overview.md)
- [<span data-ttu-id="c2bdc-344">Übersicht über Datenvorlagen</span><span class="sxs-lookup"><span data-stu-id="c2bdc-344">Data templating overview</span></span>](../../../../docs/framework/wpf/data/data-templating-overview.md)
- [<span data-ttu-id="c2bdc-345">Erstellen einer WPF-Anwendung</span><span class="sxs-lookup"><span data-stu-id="c2bdc-345">Build a WPF application</span></span>](../../../../docs/framework/wpf/app-development/building-a-wpf-application-wpf.md)
- [<span data-ttu-id="c2bdc-346">Stile und-Vorlagen</span><span class="sxs-lookup"><span data-stu-id="c2bdc-346">Styles and templates</span></span>](../../../../docs/framework/wpf/controls/styles-and-templates.md)
