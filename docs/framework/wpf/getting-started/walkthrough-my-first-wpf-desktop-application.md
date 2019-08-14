---
title: Erstellen einer WPF-Anwendung in Visual Studio
ms.date: 03/20/2019
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
ms.openlocfilehash: 9d5b5b8a479efd3918dc23616aa331cc07a901ac
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/13/2019
ms.locfileid: "68972213"
---
# <a name="walkthrough-my-first-wpf-desktop-application"></a><span data-ttu-id="e70bc-102">Exemplarische Vorgehensweise: Meine erste WPF-Desktopanwendung</span><span class="sxs-lookup"><span data-stu-id="e70bc-102">Walkthrough: My first WPF desktop application</span></span>

<span data-ttu-id="e70bc-103">In diesem Artikel erfahren Sie, wie Sie eine WPF-Desktop Anwendung (Windows Presentation Foundation) entwickeln, die die Elemente enthält, die den meisten WPF-Anwendungen gemeinsam sind: Extensible Application Markup Language (XAML)-Markup, Code Behind, Anwendungs Definitionen, Steuerelemente, Layout, Datenbindung und Stile.</span><span class="sxs-lookup"><span data-stu-id="e70bc-103">This article shows you how to develop a Windows Presentation Foundation (WPF) desktop application that includes the elements that are common to most WPF applications: Extensible Application Markup Language (XAML) markup, code-behind, application definitions, controls, layout, data binding, and styles.</span></span> <span data-ttu-id="e70bc-104">Zum Entwickeln der Anwendung verwenden Sie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="e70bc-104">To develop the application, you'll use Visual Studio.</span></span> 

<span data-ttu-id="e70bc-105">Diese exemplarische Vorgehensweise umfasst die folgenden Schritte:</span><span class="sxs-lookup"><span data-stu-id="e70bc-105">This walkthrough includes the following steps:</span></span>

- <span data-ttu-id="e70bc-106">Verwenden Sie XAML, um die Darstellung der Benutzeroberfläche der Anwendung zu entwerfen.</span><span class="sxs-lookup"><span data-stu-id="e70bc-106">Use XAML to design the appearance of the application's user interface (UI).</span></span>

- <span data-ttu-id="e70bc-107">Schreiben Sie Code, um das Verhalten der Anwendung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="e70bc-107">Write code to build the application's behavior.</span></span>

- <span data-ttu-id="e70bc-108">Erstellen Sie eine Anwendungs Definition, um die Anwendung zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="e70bc-108">Create an application definition to manage the application.</span></span>

- <span data-ttu-id="e70bc-109">Fügen Sie Steuerelemente hinzu, und erstellen Sie das Layout zum Verfassen der Anwendungs Benutzeroberfläche.</span><span class="sxs-lookup"><span data-stu-id="e70bc-109">Add controls and create the layout to compose the application UI.</span></span>

- <span data-ttu-id="e70bc-110">Erstellen Sie Stile für ein konsistentes Erscheinungsbild in der Benutzeroberfläche der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="e70bc-110">Create styles for a consistent appearance throughout the application's UI.</span></span>

- <span data-ttu-id="e70bc-111">Binden Sie die Benutzeroberfläche an Daten, um die Benutzeroberfläche von Daten aufzufüllen und die Daten und die Benutzeroberfläche zu synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="e70bc-111">Bind the UI to data, both to populate the UI from data and to keep the data and UI synchronized.</span></span>

<span data-ttu-id="e70bc-112">Am Ende der exemplarischen Vorgehensweise haben Sie eine eigenständige Windows-Anwendung erstellt, die es Benutzern ermöglicht, Ausgaben Berichte für ausgewählte Personen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="e70bc-112">By the end of the walkthrough, you'll have built a standalone Windows application that allows users to view expense reports for selected people.</span></span> <span data-ttu-id="e70bc-113">Die Anwendung besteht aus mehreren WPF-Seiten, die in einem Browserfenster gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="e70bc-113">The application is composed of several WPF pages that are hosted in a browser-style window.</span></span>

> [!TIP]
> <span data-ttu-id="e70bc-114">Der Beispielcode, der zum Erstellen dieser exemplarischen Vorgehensweise verwendet wird, ist für C# Visual Basic und Exemplarische Vorgehensweise für [WPF-App-Beispielcode](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/WalkthroughFirstWPFApp)verfügbar.</span><span class="sxs-lookup"><span data-stu-id="e70bc-114">The sample code that is used to build this walkthrough is available for both Visual Basic and C# at [Walkthrough WPF App Sample Code](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/WalkthroughFirstWPFApp).</span></span>
>
> <span data-ttu-id="e70bc-115">Sie können die Codesprache des Beispielcodes zwischen C# und Visual Basic umschalten, indem Sie die **\< />** Dropdown Leiste oben rechts in diesem Artikel verwenden.</span><span class="sxs-lookup"><span data-stu-id="e70bc-115">You can toggle the code language of the sample code between C# and Visual Basic by using the **\</>** drop-down on the upper right side of this article.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e70bc-116">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="e70bc-116">Prerequisites</span></span>

- <span data-ttu-id="e70bc-117">Visual Studio 2017 oder höher (in diesem Artikel wird Visual Studio 2019 verwendet)</span><span class="sxs-lookup"><span data-stu-id="e70bc-117">Visual Studio 2017 or later (this article uses Visual Studio 2019)</span></span>

   <span data-ttu-id="e70bc-118">Weitere Informationen zum Installieren der neuesten Version von Visual Studio finden Sie unter [Installieren von Visual Studio](/visualstudio/install/install-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="e70bc-118">For more information about installing the latest version of Visual Studio, see [Install Visual Studio](/visualstudio/install/install-visual-studio).</span></span>

## <a name="create-the-application-project"></a><span data-ttu-id="e70bc-119">Erstellen des Anwendungs Projekts</span><span class="sxs-lookup"><span data-stu-id="e70bc-119">Create the application project</span></span>

<span data-ttu-id="e70bc-120">Der erste Schritt besteht darin, die Anwendungs Infrastruktur zu erstellen, die eine Anwendungs Definition, zwei Seiten und ein Bild enthält.</span><span class="sxs-lookup"><span data-stu-id="e70bc-120">The first step is to create the application infrastructure, which includes an application definition, two pages, and an image.</span></span>

1. <span data-ttu-id="e70bc-121">Erstellen Sie ein neues WPF-Anwendungsprojekt in Visual Basic C# oder **`ExpenseIt`** einem visuellen Element mit dem Namen:</span><span class="sxs-lookup"><span data-stu-id="e70bc-121">Create a new WPF Application project in Visual Basic or Visual C# named **`ExpenseIt`**:</span></span>

   1. <span data-ttu-id="e70bc-122">Öffnen Sie Visual Studio, und wählen Sie im Menü " **Get Started** " die Option **Neues Projekt erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="e70bc-122">Open Visual Studio and select **Create a new project** under the **Get started** menu.</span></span>

      <span data-ttu-id="e70bc-123">Das Dialogfeld **Neues Projekt erstellen** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="e70bc-123">The **Create a new project** dialog opens.</span></span>

   2. <span data-ttu-id="e70bc-124">Wählen Sie in der Dropdown Liste Sprache **C#** entweder oder **Visual Basic**aus.</span><span class="sxs-lookup"><span data-stu-id="e70bc-124">In the **Language** dropdown, select either **C#** or **Visual Basic**.</span></span>
      
   3. <span data-ttu-id="e70bc-125">Wählen Sie die Vorlage **WPF-App (.NET Framework)** aus, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="e70bc-125">Select the **WPF App (.NET Framework)** template and then select **Next**.</span></span> 
     
      ![Dialogfeld "Neues Projekt erstellen"](./media/walkthrough-my-first-wpf-desktop-application/create-new-project-dialog.png)
    
      <span data-ttu-id="e70bc-127">Das Dialogfeld **Neues Projekt konfigurieren** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="e70bc-127">The **Configure your new project** dialog opens.</span></span>

   4. <span data-ttu-id="e70bc-128">Geben Sie den Projekt **`ExpenseIt`** Namen ein, und wählen Sie dann **Erstellen**aus.</span><span class="sxs-lookup"><span data-stu-id="e70bc-128">Enter the project name **`ExpenseIt`** and then select **Create**.</span></span>

      ![Dialogfeld "Neues Projekt konfigurieren"](./media/walkthrough-my-first-wpf-desktop-application/configure-new-project-dialog.png)

      <span data-ttu-id="e70bc-130">Visual Studio erstellt das Projekt und öffnet den Designer für das Standard Anwendungsfenster namens **MainWindow. XAML**.</span><span class="sxs-lookup"><span data-stu-id="e70bc-130">Visual Studio creates the project and opens the designer for the default application window named **MainWindow.xaml**.</span></span>

2. <span data-ttu-id="e70bc-131">Öffnen Sie " *Application. XAML* (Visual Basic)" oder " *app. XAML* (C#)".</span><span class="sxs-lookup"><span data-stu-id="e70bc-131">Open *Application.xaml* (Visual Basic) or *App.xaml* (C#).</span></span>

    <span data-ttu-id="e70bc-132">Diese XAML-Datei definiert eine WPF-Anwendung und alle Anwendungs Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="e70bc-132">This XAML file defines a WPF application and any application resources.</span></span> <span data-ttu-id="e70bc-133">Außerdem verwenden Sie diese Datei, um die Benutzeroberfläche anzugeben, in diesem Fall " *MainWindow. XAML*", die automatisch anzeigt, wann die Anwendung gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="e70bc-133">You also use this file to specify the UI, in this case *MainWindow.xaml*, that automatically shows when the application starts.</span></span>

    <span data-ttu-id="e70bc-134">Der XAML-Code sollte in Visual Basic wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="e70bc-134">Your XAML should look like the following in Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#1_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/Application.xaml#1_a)]

    <span data-ttu-id="e70bc-135">Und wie im C#folgenden Beispiel:</span><span class="sxs-lookup"><span data-stu-id="e70bc-135">And like the following in C#:</span></span>

    [!code-xaml[ExpenseIt#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/App.xaml#1)]

3. <span data-ttu-id="e70bc-136">Öffnen Sie " *MainWindow. XAML*".</span><span class="sxs-lookup"><span data-stu-id="e70bc-136">Open *MainWindow.xaml*.</span></span>

    <span data-ttu-id="e70bc-137">Diese XAML-Datei ist das Hauptfenster der Anwendung und zeigt in Seiten erstellte Inhalte an.</span><span class="sxs-lookup"><span data-stu-id="e70bc-137">This XAML file is the main window of your application and displays content created in pages.</span></span> <span data-ttu-id="e70bc-138">Die <xref:System.Windows.Window> -Klasse definiert die Eigenschaften eines Fensters, z. b. Titel, Größe oder Symbol, und behandelt Ereignisse, z. b. das Schließen oder ausblenden.</span><span class="sxs-lookup"><span data-stu-id="e70bc-138">The <xref:System.Windows.Window> class defines the properties of a window, such as its title, size, or icon, and handles events, such as closing or hiding.</span></span>

4. <span data-ttu-id="e70bc-139">Ändern Sie <xref:System.Windows.Window> das-Element <xref:System.Windows.Navigation.NavigationWindow>in ein-Element, wie im folgenden XAML-Code dargestellt:</span><span class="sxs-lookup"><span data-stu-id="e70bc-139">Change the <xref:System.Windows.Window> element to a <xref:System.Windows.Navigation.NavigationWindow>, as shown in the following XAML:</span></span>

   ```xaml
   <NavigationWindow x:Class="ExpenseIt.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        ...
   </NavigationWindow>
   ```

   <span data-ttu-id="e70bc-140">Diese APP navigiert abhängig von der Benutzereingabe zu einem anderen Inhalt.</span><span class="sxs-lookup"><span data-stu-id="e70bc-140">This app navigates to different content depending on the user input.</span></span> <span data-ttu-id="e70bc-141">Aus diesem Grund muss der <xref:System.Windows.Window> Hauptgrund <xref:System.Windows.Navigation.NavigationWindow>in geändert werden.</span><span class="sxs-lookup"><span data-stu-id="e70bc-141">This is why the main <xref:System.Windows.Window> needs to be changed to a <xref:System.Windows.Navigation.NavigationWindow>.</span></span> <span data-ttu-id="e70bc-142"><xref:System.Windows.Navigation.NavigationWindow>erbt alle Eigenschaften von <xref:System.Windows.Window>.</span><span class="sxs-lookup"><span data-stu-id="e70bc-142"><xref:System.Windows.Navigation.NavigationWindow> inherits all the properties of <xref:System.Windows.Window>.</span></span> <span data-ttu-id="e70bc-143">Das <xref:System.Windows.Navigation.NavigationWindow> -Element in der XAML-Datei erstellt eine Instanz <xref:System.Windows.Navigation.NavigationWindow> der-Klasse.</span><span class="sxs-lookup"><span data-stu-id="e70bc-143">The <xref:System.Windows.Navigation.NavigationWindow> element in the XAML file creates an instance of the <xref:System.Windows.Navigation.NavigationWindow> class.</span></span> <span data-ttu-id="e70bc-144">Weitere Informationen finden Sie unter [Übersicht über die Navigation](../app-development/navigation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="e70bc-144">For more information, see [Navigation overview](../app-development/navigation-overview.md).</span></span>

5. <span data-ttu-id="e70bc-145">Entfernen Sie <xref:System.Windows.Controls.Grid> die Elemente zwischen den <xref:System.Windows.Navigation.NavigationWindow> Tags.</span><span class="sxs-lookup"><span data-stu-id="e70bc-145">Remove the <xref:System.Windows.Controls.Grid> elements from between the <xref:System.Windows.Navigation.NavigationWindow> tags.</span></span>

6. <span data-ttu-id="e70bc-146">Ändern Sie die folgenden Eigenschaften im XAML-Code für <xref:System.Windows.Navigation.NavigationWindow> das-Element:</span><span class="sxs-lookup"><span data-stu-id="e70bc-146">Change the following properties in the XAML code for the <xref:System.Windows.Navigation.NavigationWindow> element:</span></span>

    - <span data-ttu-id="e70bc-147">Legen Sie <xref:System.Windows.Window.Title%2A> die-Eigenschaft`ExpenseIt`auf "" fest.</span><span class="sxs-lookup"><span data-stu-id="e70bc-147">Set the <xref:System.Windows.Window.Title%2A> property to "`ExpenseIt`".</span></span>

    - <span data-ttu-id="e70bc-148">Legen Sie <xref:System.Windows.FrameworkElement.Height%2A> die-Eigenschaft auf 350 Pixel fest.</span><span class="sxs-lookup"><span data-stu-id="e70bc-148">Set the <xref:System.Windows.FrameworkElement.Height%2A> property to 350 pixels.</span></span>

    - <span data-ttu-id="e70bc-149">Legen Sie <xref:System.Windows.FrameworkElement.Width%2A> die-Eigenschaft auf 500 Pixel fest.</span><span class="sxs-lookup"><span data-stu-id="e70bc-149">Set the <xref:System.Windows.FrameworkElement.Width%2A> property to 500 pixels.</span></span>

    <span data-ttu-id="e70bc-150">Der XAML-Code sollte für Visual Basic wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="e70bc-150">Your XAML should look like the following for Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#2_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt/MainWindow.xaml#2_a)]

    <span data-ttu-id="e70bc-151">Und wie im folgenden Beispiel C#für:</span><span class="sxs-lookup"><span data-stu-id="e70bc-151">And like the following for C#:</span></span>

    [!code-xaml[ExpenseIt#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/MainWindow.xaml#2)]

7. <span data-ttu-id="e70bc-152">Öffnen Sie " *MainWindow. XAML. vb* " oder " *MainWindow.XAML.cs*".</span><span class="sxs-lookup"><span data-stu-id="e70bc-152">Open *MainWindow.xaml.vb* or *MainWindow.xaml.cs*.</span></span>

    <span data-ttu-id="e70bc-153">Bei dieser Datei handelt es sich um eine Code Behind-Datei, die Code zum Behandeln der in " *MainWindow. XAML*" deklarierten Ereignisse enthält.</span><span class="sxs-lookup"><span data-stu-id="e70bc-153">This file is a code-behind file that contains code to handle the events declared in *MainWindow.xaml*.</span></span> <span data-ttu-id="e70bc-154">Diese Datei enthält eine partielle Klasse für das in XAML definierte Fenster.</span><span class="sxs-lookup"><span data-stu-id="e70bc-154">This file contains a partial class for the window defined in XAML.</span></span>

8. <span data-ttu-id="e70bc-155">Wenn Sie verwenden C#, ändern Sie die `MainWindow` -Klasse so, <xref:System.Windows.Navigation.NavigationWindow>dass Sie von abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="e70bc-155">If you're using C#, change the `MainWindow` class to derive from <xref:System.Windows.Navigation.NavigationWindow>.</span></span> <span data-ttu-id="e70bc-156">(In Visual Basic erfolgt dies automatisch, wenn Sie das Fenster in XAML ändern.) Der C# Code sollte nun wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="e70bc-156">(In Visual Basic, this happens automatically when you change the window in XAML.) Your C# code should now look like this:</span></span>

   [!code-csharp[ExpenseIt#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/MainWindow.xaml.cs?highlight=21)]

## <a name="add-files-to-the-application"></a><span data-ttu-id="e70bc-157">Hinzufügen von Dateien zur Anwendung</span><span class="sxs-lookup"><span data-stu-id="e70bc-157">Add files to the application</span></span>

<span data-ttu-id="e70bc-158">In diesem Abschnitt fügen Sie der Anwendung zwei Seiten und ein Bild hinzu.</span><span class="sxs-lookup"><span data-stu-id="e70bc-158">In this section, you'll add two pages and an image to the application.</span></span>

1. <span data-ttu-id="e70bc-159">Fügen Sie dem Projekt eine neue Seite hinzu, und benennen *`ExpenseItHome.xaml`* Sie Sie:</span><span class="sxs-lookup"><span data-stu-id="e70bc-159">Add a new page to the project, and name it *`ExpenseItHome.xaml`*:</span></span>

   1. <span data-ttu-id="e70bc-160">Klicken Sie in **Projektmappen-Explorer**mit der rechten Maustaste **`ExpenseIt`** auf den Projekt Knoten, und wählen Sie**Seite** **Hinzufügen** > aus.</span><span class="sxs-lookup"><span data-stu-id="e70bc-160">In **Solution Explorer**, right-click on the **`ExpenseIt`** project node and choose **Add** > **Page**.</span></span>

   1. <span data-ttu-id="e70bc-161">Im Dialogfeld **Neues Element hinzufügen** ist die **Seite (WPF** -Vorlage) bereits ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="e70bc-161">In the **Add New Item** dialog, the **Page (WPF)** template is already selected.</span></span> <span data-ttu-id="e70bc-162">Geben Sie den **`ExpenseItHome`** Namen ein, und klicken Sie dann auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="e70bc-162">Enter the name **`ExpenseItHome`**, and then select **Add**.</span></span>

    <span data-ttu-id="e70bc-163">Diese Seite ist die erste Seite, die angezeigt wird, wenn die Anwendung gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="e70bc-163">This page is the first page that's displayed when the application is launched.</span></span> <span data-ttu-id="e70bc-164">Es wird eine Liste der Personen angezeigt, aus denen Sie auswählen können, um einen Spesen Abrechnungs Bericht anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="e70bc-164">It will show a list of people to select from, to show an expense report for.</span></span>

1. <span data-ttu-id="e70bc-165">Öffnen *`ExpenseItHome.xaml`* Sie.</span><span class="sxs-lookup"><span data-stu-id="e70bc-165">Open *`ExpenseItHome.xaml`*.</span></span>

1. <span data-ttu-id="e70bc-166">Legen Sie auf "`ExpenseIt - Home`" fest. <xref:System.Windows.Controls.Page.Title%2A></span><span class="sxs-lookup"><span data-stu-id="e70bc-166">Set the <xref:System.Windows.Controls.Page.Title%2A> to "`ExpenseIt - Home`".</span></span>

1. <span data-ttu-id="e70bc-167">Legen Sie `DesignHeight` die `DesignWidth` -und-Element Werte auf 300 Pixel fest.</span><span class="sxs-lookup"><span data-stu-id="e70bc-167">Set the `DesignHeight` and `DesignWidth` element values to 300 pixels.</span></span>

    <span data-ttu-id="e70bc-168">Der XAML-Code wird nun wie folgt für Visual Basic angezeigt:</span><span class="sxs-lookup"><span data-stu-id="e70bc-168">The XAML now appears as follows for Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#6_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml#6_a)]

    <span data-ttu-id="e70bc-169">Und wie im folgenden Beispiel C#für:</span><span class="sxs-lookup"><span data-stu-id="e70bc-169">And like the following for C#:</span></span>

    [!code-xaml[ExpenseIt#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml#6)]

1. <span data-ttu-id="e70bc-170">Öffnen Sie " *MainWindow. XAML*".</span><span class="sxs-lookup"><span data-stu-id="e70bc-170">Open *MainWindow.xaml*.</span></span>

1. <span data-ttu-id="e70bc-171">Fügen Sie <xref:System.Windows.Navigation.NavigationWindow.Source%2A> dem <xref:System.Windows.Navigation.NavigationWindow> -Element eine Eigenschaft hinzu, und legen`ExpenseItHome.xaml`Sie es auf "" fest.</span><span class="sxs-lookup"><span data-stu-id="e70bc-171">Add a <xref:System.Windows.Navigation.NavigationWindow.Source%2A> property to the <xref:System.Windows.Navigation.NavigationWindow> element and set it to "`ExpenseItHome.xaml`".</span></span>

    <span data-ttu-id="e70bc-172">Dadurch wird *`ExpenseItHome.xaml`* die erste Seite festgelegt, die beim Start der Anwendung geöffnet wird.</span><span class="sxs-lookup"><span data-stu-id="e70bc-172">This sets *`ExpenseItHome.xaml`* to be the first page opened when the application starts.</span></span> 

    <span data-ttu-id="e70bc-173">Beispiel-XAML in Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="e70bc-173">Example XAML in Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#7_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/MainWindow.xaml#7_a)]

    <span data-ttu-id="e70bc-174">Und in C#:</span><span class="sxs-lookup"><span data-stu-id="e70bc-174">And in C#:</span></span>

    [!code-xaml[ExpenseIt#7](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/MainWindow.xaml#7)]

   > [!TIP]
   > <span data-ttu-id="e70bc-175">Sie können auch die Eigenschaft **Quelle** in der Kategorie **Verschiedenes** im Fenster **Eigenschaften** festlegen.</span><span class="sxs-lookup"><span data-stu-id="e70bc-175">You can also set the **Source** property in the **Miscellaneous** category of the **Properties** window.</span></span>
   >
   > ![Quell Eigenschaft in Eigenschaftenfenster](./media/properties-source.png)

1. <span data-ttu-id="e70bc-177">Fügen Sie dem Projekt eine weitere neue WPF-Seite hinzu, und nennen Sie Sie *ExpenseReportPage. XAML*::</span><span class="sxs-lookup"><span data-stu-id="e70bc-177">Add another new WPF page to the project, and name it *ExpenseReportPage.xaml*::</span></span>

   1. <span data-ttu-id="e70bc-178">Klicken Sie in **Projektmappen-Explorer**mit der rechten Maustaste **`ExpenseIt`** auf den Projekt Knoten, und wählen Sie**Seite** **Hinzufügen** > aus.</span><span class="sxs-lookup"><span data-stu-id="e70bc-178">In **Solution Explorer**, right-click on the **`ExpenseIt`** project node and choose **Add** > **Page**.</span></span>

   1. <span data-ttu-id="e70bc-179">Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Vorlage **Page (WPF)** aus.</span><span class="sxs-lookup"><span data-stu-id="e70bc-179">In the **Add New Item** dialog, select the **Page (WPF)** template.</span></span> <span data-ttu-id="e70bc-180">Geben Sie den Namen **ExpenseReportPage**ein, und klicken Sie dann auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="e70bc-180">Enter the name **ExpenseReportPage**, and then select **Add**.</span></span>

    <span data-ttu-id="e70bc-181">Auf dieser Seite wird der Ausgaben Bericht für die Person angezeigt, die auf der **`ExpenseItHome`** Seite ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="e70bc-181">This page will show the expense report for the person that is selected on the **`ExpenseItHome`** page.</span></span>

1. <span data-ttu-id="e70bc-182">Öffnen Sie *ExpenseReportPage.xaml*.</span><span class="sxs-lookup"><span data-stu-id="e70bc-182">Open *ExpenseReportPage.xaml*.</span></span>

1. <span data-ttu-id="e70bc-183">Legen Sie auf "`ExpenseIt - View Expense`" fest. <xref:System.Windows.Controls.Page.Title%2A></span><span class="sxs-lookup"><span data-stu-id="e70bc-183">Set the <xref:System.Windows.Controls.Page.Title%2A> to "`ExpenseIt - View Expense`".</span></span>

1. <span data-ttu-id="e70bc-184">Legen Sie `DesignHeight` die `DesignWidth` -und-Element Werte auf 300 Pixel fest.</span><span class="sxs-lookup"><span data-stu-id="e70bc-184">Set the `DesignHeight` and `DesignWidth` element values to 300 pixels.</span></span>

    <span data-ttu-id="e70bc-185">*ExpenseReportPage. XAML* sieht nun in Visual Basic wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="e70bc-185">*ExpenseReportPage.xaml* now looks like the following in Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#4_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml#4_a)]

    <span data-ttu-id="e70bc-186">Und wie im C#folgenden Beispiel:</span><span class="sxs-lookup"><span data-stu-id="e70bc-186">And like the following in C#:</span></span>

    [!code-xaml[ExpenseIt#4](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml#4)]

1. <span data-ttu-id="e70bc-187">Öffnen Sie *expenseithome. XAML. vb* und *ExpenseReportPage. XAML. vb*oder *ExpenseItHome.XAML.cs* und *ExpenseReportPage.XAML.cs*.</span><span class="sxs-lookup"><span data-stu-id="e70bc-187">Open *ExpenseItHome.xaml.vb* and *ExpenseReportPage.xaml.vb*, or *ExpenseItHome.xaml.cs* and *ExpenseReportPage.xaml.cs*.</span></span>

    <span data-ttu-id="e70bc-188">Wenn Sie eine neue Auslagerungs Datei erstellen, erstellt Visual Studio automatisch die *zugehörige Code Behind-* Datei.</span><span class="sxs-lookup"><span data-stu-id="e70bc-188">When you create a new Page file, Visual Studio automatically creates its *code-behind* file.</span></span> <span data-ttu-id="e70bc-189">Diese CodeBehind-Dateien behandeln die Logik zum Reagieren auf Benutzereingabe.</span><span class="sxs-lookup"><span data-stu-id="e70bc-189">These code-behind files handle the logic for responding to user input.</span></span>

    <span data-ttu-id="e70bc-190">Der Code sollte wie folgt **`ExpenseItHome`** aussehen:</span><span class="sxs-lookup"><span data-stu-id="e70bc-190">Your code should look like the following for **`ExpenseItHome`**:</span></span>

    [!code-csharp[ExpenseIt#2_5](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml.cs#2_5)]

    [!code-vb[ExpenseIt#2_5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml.vb#2_5)]

    <span data-ttu-id="e70bc-191">Und wie im folgenden für **ExpenseReportPage**:</span><span class="sxs-lookup"><span data-stu-id="e70bc-191">And like the following for **ExpenseReportPage**:</span></span>

    [!code-csharp[ExpenseIt#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml.cs#5)]

    [!code-vb[ExpenseIt#5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml.vb#5)]

1. <span data-ttu-id="e70bc-192">Fügen Sie dem Projekt ein Bild mit dem Namen " *Watermark. png* " hinzu.</span><span class="sxs-lookup"><span data-stu-id="e70bc-192">Add an image named *watermark.png* to the project.</span></span> <span data-ttu-id="e70bc-193">Sie können ein eigenes Image erstellen, die Datei aus dem Beispielcode kopieren oder [hier](https://raw.githubusercontent.com/microsoft/WPF-Samples/master/Getting%20Started/WalkthroughFirstWPFApp/csharp/watermark.png)einfügen.</span><span class="sxs-lookup"><span data-stu-id="e70bc-193">You can create your own image, copy the file from the sample code, or get it [here](https://raw.githubusercontent.com/microsoft/WPF-Samples/master/Getting%20Started/WalkthroughFirstWPFApp/csharp/watermark.png).</span></span>

    1. <span data-ttu-id="e70bc-194">Klicken Sie mit der rechten Maustaste auf den Projekt Knoten, und wählen Sie**Vorhandenes Element** **Hinzufügen** > , oder drücken Sie **UMSCHALT**+**alt**+**A**.</span><span class="sxs-lookup"><span data-stu-id="e70bc-194">Right-click on the project node and select **Add** > **Existing Item**, or press **Shift**+**Alt**+**A**.</span></span>

    2. <span data-ttu-id="e70bc-195">Legen Sie im Dialogfeld **Vorhandenes Element hinzufügen** für den Dateifilter entweder **alle Dateien** oder **Bilddateien**fest, navigieren Sie zu der Bilddatei, die Sie verwenden möchten, und wählen Sie dann **Hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="e70bc-195">In the **Add Existing Item** dialog, set the file filter to either **All Files** or **Image Files**, browse to the image file you want to use, and then select **Add**.</span></span>

## <a name="build-and-run-the-application"></a><span data-ttu-id="e70bc-196">Erstellen eines Builds und Ausführen der Anwendung</span><span class="sxs-lookup"><span data-stu-id="e70bc-196">Build and run the application</span></span>

1. <span data-ttu-id="e70bc-197">Zum Erstellen und Ausführen der Anwendung drücken Sie **F5** , oder wählen Sie im Menü **Debuggen** die Option **Debuggen starten**</span><span class="sxs-lookup"><span data-stu-id="e70bc-197">To build and run the application, press **F5** or select **Start Debugging** from the **Debug** menu.</span></span>

    <span data-ttu-id="e70bc-198">Die folgende Abbildung zeigt die Anwendung mit den <xref:System.Windows.Navigation.NavigationWindow> Schaltflächen:</span><span class="sxs-lookup"><span data-stu-id="e70bc-198">The following illustration shows the application with the <xref:System.Windows.Navigation.NavigationWindow> buttons:</span></span>

    ![Anwendung, nachdem Sie Sie erstellt und ausgeführt haben.](./media/walkthrough-my-first-wpf-desktop-application/build-run-application.png)

2. <span data-ttu-id="e70bc-200">Schließen Sie die Anwendung, um zu Visual Studio zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="e70bc-200">Close the application to return to Visual Studio.</span></span>

## <a name="create-the-layout"></a><span data-ttu-id="e70bc-201">Layout erstellen</span><span class="sxs-lookup"><span data-stu-id="e70bc-201">Create the layout</span></span>

<span data-ttu-id="e70bc-202">Layout bietet eine geordnete Methode zum Platzieren von Benutzeroberflächen Elementen und verwaltet auch die Größe und Position dieser Elemente, wenn die Größe einer Benutzeroberfläche geändert wird.</span><span class="sxs-lookup"><span data-stu-id="e70bc-202">Layout provides an ordered way to place UI elements, and also manages the size and position of those elements when a UI is resized.</span></span> <span data-ttu-id="e70bc-203">In der Regel erstellen Sie Layout mit einem der folgenden Layoutsteuerelemente:</span><span class="sxs-lookup"><span data-stu-id="e70bc-203">You typically create a layout with one of the following layout controls:</span></span>

- <span data-ttu-id="e70bc-204"><xref:System.Windows.Controls.Canvas>-Definiert einen Bereich, in dem Sie untergeordnete Elemente explizit mithilfe von Koordinaten positionieren können, die relativ zum Canvas-Bereich sind.</span><span class="sxs-lookup"><span data-stu-id="e70bc-204"><xref:System.Windows.Controls.Canvas> - Defines an area within which you can explicitly position child elements by using coordinates that are relative to the Canvas area.</span></span>
- <span data-ttu-id="e70bc-205"><xref:System.Windows.Controls.DockPanel>-Definiert einen Bereich, in dem Sie untergeordnete Elemente entweder horizontal oder vertikal relativ zueinander anordnen können.</span><span class="sxs-lookup"><span data-stu-id="e70bc-205"><xref:System.Windows.Controls.DockPanel> - Defines an area where you can arrange child elements either horizontally or vertically, relative to each other.</span></span>
- <span data-ttu-id="e70bc-206"><xref:System.Windows.Controls.Grid>: Definiert einen flexiblen Raster Bereich, der aus Spalten und Zeilen besteht.</span><span class="sxs-lookup"><span data-stu-id="e70bc-206"><xref:System.Windows.Controls.Grid> - Defines a flexible grid area that consists of columns and rows.</span></span>
- <span data-ttu-id="e70bc-207"><xref:System.Windows.Controls.StackPanel>Ordnet untergeordnete Elemente in einer einzelnen Zeile an, die horizontal oder vertikal ausgerichtet werden kann.</span><span class="sxs-lookup"><span data-stu-id="e70bc-207"><xref:System.Windows.Controls.StackPanel> - Arranges child elements into a single line that can be oriented horizontally or vertically.</span></span>
- <span data-ttu-id="e70bc-208"><xref:System.Windows.Controls.VirtualizingStackPanel>: Ordnet den Inhalt in einer einzelnen Zeile an, die horizontal oder vertikal ausgerichtet ist, und virtualisiert diesen.</span><span class="sxs-lookup"><span data-stu-id="e70bc-208"><xref:System.Windows.Controls.VirtualizingStackPanel> - Arranges and virtualizes content on a single line that is oriented either horizontally or vertically.</span></span>
- <span data-ttu-id="e70bc-209"><xref:System.Windows.Controls.WrapPanel>-Positioniert untergeordnete Elemente in sequenzieller Position von links nach rechts, wobei der Inhalt in die nächste Zeile am Rand des enthaltenden Felds unterteilt wird.</span><span class="sxs-lookup"><span data-stu-id="e70bc-209"><xref:System.Windows.Controls.WrapPanel> - Positions child elements in sequential position from left to right, breaking content to the next line at the edge of the containing box.</span></span> <span data-ttu-id="e70bc-210">Die nachfolgende Reihenfolge erfolgt nacheinander von oben nach unten oder von rechts nach links, abhängig vom Wert der Orientation-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="e70bc-210">Subsequent ordering happens sequentially from top to bottom or from right to left, depending on the value of the Orientation property.</span></span>

<span data-ttu-id="e70bc-211">Jedes dieser Layoutsteuerelemente unterstützt einen bestimmten Layouttyp für seine untergeordneten Elemente.</span><span class="sxs-lookup"><span data-stu-id="e70bc-211">Each of these layout controls supports a particular type of layout for its child elements.</span></span> <span data-ttu-id="e70bc-212">`ExpenseIt`die Größe der Seiten kann geändert werden, und jede Seite weist Elemente auf, die horizontal und vertikal zusammen mit anderen Elementen angeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="e70bc-212">`ExpenseIt` pages can be resized, and each page has elements that are arranged horizontally and vertically alongside other elements.</span></span> <span data-ttu-id="e70bc-213">In diesem Beispiel <xref:System.Windows.Controls.Grid> wird als Layout-Element für die Anwendung verwendet.</span><span class="sxs-lookup"><span data-stu-id="e70bc-213">In this example, the <xref:System.Windows.Controls.Grid> is used as  layout element for the application.</span></span>

> [!TIP]
> <span data-ttu-id="e70bc-214">Weitere Informationen zu Elementen <xref:System.Windows.Controls.Panel> finden Sie unter [Übersicht über Panels](../controls/panels-overview.md).</span><span class="sxs-lookup"><span data-stu-id="e70bc-214">For more information about <xref:System.Windows.Controls.Panel> elements, see [Panels overview](../controls/panels-overview.md).</span></span> <span data-ttu-id="e70bc-215">Weitere Informationen zum Layout finden Sie unter [Layout](../advanced/layout.md).</span><span class="sxs-lookup"><span data-stu-id="e70bc-215">For more information about layout, see [Layout](../advanced/layout.md).</span></span>

<span data-ttu-id="e70bc-216">In diesem Abschnitt erstellen Sie eine einspaltige Tabelle mit drei Zeilen und einem 10-Pixel-Rand, indem Sie der <xref:System.Windows.Controls.Grid> in *`ExpenseItHome.xaml`* Spalten-und Zeilen Definitionen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="e70bc-216">In this section, you create a single-column table with three rows and a 10-pixel margin by adding column and row definitions to the <xref:System.Windows.Controls.Grid> in *`ExpenseItHome.xaml`*.</span></span>

1. <span data-ttu-id="e70bc-217">Legen *`ExpenseItHome.xaml`* Sie in die <xref:System.Windows.FrameworkElement.Margin%2A> -Eigenschaft <xref:System.Windows.Controls.Grid> des-Elements auf "10, 0, 10, 10" fest, was dem linken, oberen, rechten und unteren Rand entspricht:</span><span class="sxs-lookup"><span data-stu-id="e70bc-217">In *`ExpenseItHome.xaml`*, set the <xref:System.Windows.FrameworkElement.Margin%2A> property on the <xref:System.Windows.Controls.Grid> element to "10,0,10,10", which corresponds to left, top, right and bottom margins:</span></span>

   ```xaml
   <Grid Margin="10,0,10,10">
   ```

   > [!TIP]
   > <span data-ttu-id="e70bc-218">Sie können auch die **Rand** Werte im **Eigenschaften** Fenster unter der Kategorie **Layout** festlegen:</span><span class="sxs-lookup"><span data-stu-id="e70bc-218">You can also set the **Margin** values in the **Properties** window, under the **Layout** category:</span></span>
   >
   > ![Margin-Werte in Eigenschaftenfenster](./media/properties-margin.png)

2. <span data-ttu-id="e70bc-220">Fügen Sie den folgenden XAML- <xref:System.Windows.Controls.Grid> Code zwischen den Tags hinzu, um die Zeilen-und Spaltendefinitionen zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="e70bc-220">Add the following XAML between the <xref:System.Windows.Controls.Grid> tags to create the row and column definitions:</span></span>

    [!code-xaml[ExpenseIt#8](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#8)]

    <span data-ttu-id="e70bc-221">Der <xref:System.Windows.Controls.RowDefinition.Height%2A> von zwei Zeilen wird auf <xref:System.Windows.GridLength.Auto%2A>festgelegt, was bedeutet, dass die Zeilen auf Grundlage des Inhalts in den Zeilen skaliert werden.</span><span class="sxs-lookup"><span data-stu-id="e70bc-221">The <xref:System.Windows.Controls.RowDefinition.Height%2A> of two rows is set to <xref:System.Windows.GridLength.Auto%2A>, which means that the rows are sized based on the content in the rows.</span></span> <span data-ttu-id="e70bc-222">Der Standard <xref:System.Windows.Controls.RowDefinition.Height%2A> Wert <xref:System.Windows.GridUnitType.Star> ist "Sizing", was bedeutet, dass die Zeilenhöhe ein gewichteter Anteil des verfügbaren Speicherplatzes ist.</span><span class="sxs-lookup"><span data-stu-id="e70bc-222">The default <xref:System.Windows.Controls.RowDefinition.Height%2A> is <xref:System.Windows.GridUnitType.Star> sizing, which means that the row height is a weighted proportion of the available space.</span></span> <span data-ttu-id="e70bc-223">Wenn beispielsweise zwei Zeilen den Wert " <xref:System.Windows.Controls.RowDefinition.Height%2A> \*" aufweisen, haben Sie jeweils eine Höhe, die der Hälfte des verfügbaren Speicherplatzes entspricht.</span><span class="sxs-lookup"><span data-stu-id="e70bc-223">For example if two rows each have a <xref:System.Windows.Controls.RowDefinition.Height%2A> of "\*", they each have a height that is half of the available space.</span></span>

    <span data-ttu-id="e70bc-224">Ihr <xref:System.Windows.Controls.Grid> sollte nun den folgenden XAML-Code enthalten:</span><span class="sxs-lookup"><span data-stu-id="e70bc-224">Your <xref:System.Windows.Controls.Grid> should now contain the following XAML:</span></span>

    [!code-xaml[ExpenseIt#9](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#9)]

## <a name="add-controls"></a><span data-ttu-id="e70bc-225">Steuerelemente hinzufügen</span><span class="sxs-lookup"><span data-stu-id="e70bc-225">Add controls</span></span>

<span data-ttu-id="e70bc-226">In diesem Abschnitt aktualisieren Sie die Benutzeroberfläche der Startseite, um eine Liste der Personen anzuzeigen, in der Sie eine Person auswählen, um Ihren Abrechnungs Bericht anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="e70bc-226">In this section, you'll update the home page UI to show a list of people, where you select one person to display their expense report.</span></span> <span data-ttu-id="e70bc-227">Steuerelemente sind Benutzeroberflächenobjekte, die Benutzern die Interaktion mit der Anwendung ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="e70bc-227">Controls are UI objects that allow users to interact with your application.</span></span> <span data-ttu-id="e70bc-228">Weitere Informationen finden Sie unter [Steuerelemente](../controls/index.md).</span><span class="sxs-lookup"><span data-stu-id="e70bc-228">For more information, see [Controls](../controls/index.md).</span></span>

<span data-ttu-id="e70bc-229">Um diese Benutzeroberfläche zu erstellen, fügen Sie die folgenden Elemente *`ExpenseItHome.xaml`* hinzu:</span><span class="sxs-lookup"><span data-stu-id="e70bc-229">To create this UI, you'll add the following elements to *`ExpenseItHome.xaml`*:</span></span>

- <span data-ttu-id="e70bc-230">A <xref:System.Windows.Controls.ListBox> (für die Liste der Personen).</span><span class="sxs-lookup"><span data-stu-id="e70bc-230">A <xref:System.Windows.Controls.ListBox> (for the list of people).</span></span>
- <span data-ttu-id="e70bc-231">Eine <xref:System.Windows.Controls.Label> (für den Listen Header).</span><span class="sxs-lookup"><span data-stu-id="e70bc-231">A <xref:System.Windows.Controls.Label> (for the list header).</span></span>
- <span data-ttu-id="e70bc-232">A <xref:System.Windows.Controls.Button> (Klicken Sie auf diese Option, um den Ausgaben Bericht für die in der Liste ausgewählte Person anzuzeigen).</span><span class="sxs-lookup"><span data-stu-id="e70bc-232">A <xref:System.Windows.Controls.Button> (to click to view the expense report for the person that is selected in the list).</span></span>

<span data-ttu-id="e70bc-233">Jedes Steuerelement wird in eine Zeile der <xref:System.Windows.Controls.Grid> eingefügt, indem die <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> angefügte-Eigenschaft festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="e70bc-233">Each control is placed in a row of the <xref:System.Windows.Controls.Grid> by setting the <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> attached property.</span></span> <span data-ttu-id="e70bc-234">Weitere Informationen zu angefügten Eigenschaften finden Sie unter [Übersicht über angefügte Eigenschaften](../advanced/attached-properties-overview.md).</span><span class="sxs-lookup"><span data-stu-id="e70bc-234">For more information about attached properties, see [Attached Properties Overview](../advanced/attached-properties-overview.md).</span></span>

1. <span data-ttu-id="e70bc-235">Fügen *`ExpenseItHome.xaml`* Sie in den folgenden XAML-Code irgendwo <xref:System.Windows.Controls.Grid> zwischen den-Tags hinzu:</span><span class="sxs-lookup"><span data-stu-id="e70bc-235">In *`ExpenseItHome.xaml`*, add the following XAML somewhere between the <xref:System.Windows.Controls.Grid> tags:</span></span>

   [!code-xaml[ExpenseIt#10](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt4/ExpenseItHome.xaml#10)]

   > [!TIP]
   > <span data-ttu-id="e70bc-236">Sie können die Steuerelemente auch erstellen, indem Sie Sie aus dem Fenster **Toolbox** in das Entwurfs Fenster ziehen und dann ihre Eigenschaften im **Eigenschaften** Fenster festlegen.</span><span class="sxs-lookup"><span data-stu-id="e70bc-236">You can also create the controls by dragging them from the **Toolbox** window onto the design window, and then setting their properties in the **Properties** window.</span></span>

2. <span data-ttu-id="e70bc-237">Erstellen Sie die Anwendung, und führen Sie sie aus.</span><span class="sxs-lookup"><span data-stu-id="e70bc-237">Build and run the application.</span></span>

    <span data-ttu-id="e70bc-238">Die folgende Abbildung zeigt die Steuerelemente, die Sie erstellt haben:</span><span class="sxs-lookup"><span data-stu-id="e70bc-238">The following illustration shows the controls you created:</span></span>

![ExpenseIt-Beispiel Bildschirm Abbildung mit einer Liste von Namen](./media/walkthrough-my-first-wpf-desktop-application/add-application-controls.png)

## <a name="add-an-image-and-a-title"></a><span data-ttu-id="e70bc-240">Hinzufügen eines Bilds und Titels</span><span class="sxs-lookup"><span data-stu-id="e70bc-240">Add an image and a title</span></span>

<span data-ttu-id="e70bc-241">In diesem Abschnitt aktualisieren Sie die Benutzeroberfläche der Startseite mit einem Bild und einem Seitentitel.</span><span class="sxs-lookup"><span data-stu-id="e70bc-241">In this section, you'll update the home page UI with an image and a page title.</span></span>

1. <span data-ttu-id="e70bc-242">Fügen *`ExpenseItHome.xaml`* Sie in eine weitere Spalte <xref:System.Windows.Controls.Grid.ColumnDefinitions%2A> mit einem fester <xref:System.Windows.Controls.ColumnDefinition.Width%2A> Größe von 230 Pixeln hinzu:</span><span class="sxs-lookup"><span data-stu-id="e70bc-242">In *`ExpenseItHome.xaml`*, add another column to the <xref:System.Windows.Controls.Grid.ColumnDefinitions%2A> with a fixed <xref:System.Windows.Controls.ColumnDefinition.Width%2A> of 230 pixels:</span></span>

    [!code-xaml[ExpenseIt#11](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseItHome.xaml?highlight=52-55)]

2. <span data-ttu-id="e70bc-243">Fügen Sie eine weitere Zeile <xref:System.Windows.Controls.Grid.RowDefinitions%2A>hinzu, für insgesamt vier Zeilen:</span><span class="sxs-lookup"><span data-stu-id="e70bc-243">Add another row to the <xref:System.Windows.Controls.Grid.RowDefinitions%2A>, for a total of four rows:</span></span>

    [!code-xaml[ExpenseIt#11b](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseItHome.xaml?highlight=57-62)]

3. <span data-ttu-id="e70bc-244">Verschieben Sie die Steuerelemente in die zweite Spalte, <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> indem Sie die-Eigenschaft in jedem der drei Steuerelemente (Border, ListBox und Button) auf 1 festlegen.</span><span class="sxs-lookup"><span data-stu-id="e70bc-244">Move the controls to the second column by setting the <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> property to 1 in each of the three controls (Border, ListBox, and Button).</span></span>

4. <span data-ttu-id="e70bc-245">Verschieben Sie jedes Steuerelement um eine Zeile nach unten <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> , indem Sie den Wert für jedes der drei Steuerelemente (Border, ListBox und Button) und für das Border-Element um 1 erhöhen.</span><span class="sxs-lookup"><span data-stu-id="e70bc-245">Move each control down a row by incrementing its <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> value by 1 for each of the three controls (Border, ListBox, and Button) and for the Border element.</span></span>

   <span data-ttu-id="e70bc-246">Die XAML-Datei für die drei Steuerelemente sieht nun wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="e70bc-246">The XAML for the three controls now looks like the following:</span></span>

    [!code-xaml[ExpenseIt#12](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#12)]

5. <span data-ttu-id="e70bc-247">Legen Sie <xref:System.Windows.Controls.Panel.Background%2A?displayProperty=nameWithType> die-Eigenschaft auf die Bilddatei " *Watermark. png* " fest, indem Sie den folgenden XAML-Code zwischen den `<Grid>` Tags und `</Grid>` hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="e70bc-247">Set the <xref:System.Windows.Controls.Panel.Background%2A?displayProperty=nameWithType> property to the *watermark.png* image file, by adding the following XAML anywhere between the `<Grid>` and `</Grid>` tags:</span></span>

    [!code-xaml[ExpenseIt#14](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#14)]

6. <span data-ttu-id="e70bc-248">Fügen Sie <xref:System.Windows.Controls.Border> vor dem-Element <xref:System.Windows.Controls.Label> ein-Element mit dem Inhalt "Ansichts Ausgaben Bericht" hinzu.</span><span class="sxs-lookup"><span data-stu-id="e70bc-248">Before the <xref:System.Windows.Controls.Border> element, add a <xref:System.Windows.Controls.Label> with the content "View Expense Report".</span></span> <span data-ttu-id="e70bc-249">Diese Bezeichnung ist der Titel der Seite.</span><span class="sxs-lookup"><span data-stu-id="e70bc-249">This label is the title of the page.</span></span>

    [!code-xaml[ExpenseIt#13](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#13)]

7. <span data-ttu-id="e70bc-250">Erstellen Sie die Anwendung, und führen Sie sie aus.</span><span class="sxs-lookup"><span data-stu-id="e70bc-250">Build and run the application.</span></span>

<span data-ttu-id="e70bc-251">Die folgende Abbildung zeigt die Ergebnisse, die Sie soeben hinzugefügt haben:</span><span class="sxs-lookup"><span data-stu-id="e70bc-251">The following illustration shows the results of what you just added:</span></span>

![ExpenseIt-Beispiel Bildschirm Abbildung des neuen Bild Hintergrunds und Seitentitels](./media/walkthrough-my-first-wpf-desktop-application/add-application-image-title.png)

## <a name="add-code-to-handle-events"></a><span data-ttu-id="e70bc-253">Hinzufügen von Code zum Behandeln von Ereignissen</span><span class="sxs-lookup"><span data-stu-id="e70bc-253">Add code to handle events</span></span>

1. <span data-ttu-id="e70bc-254">Fügen *`ExpenseItHome.xaml`* Sie in einen <xref:System.Windows.Controls.Primitives.ButtonBase.Click> -Ereignishandler zum <xref:System.Windows.Controls.Button> -Element hinzu.</span><span class="sxs-lookup"><span data-stu-id="e70bc-254">In *`ExpenseItHome.xaml`*, add a <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler to the <xref:System.Windows.Controls.Button> element.</span></span> <span data-ttu-id="e70bc-255">Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen Sie einen einfachen Ereignis](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb675300(v=vs.100))Handler.</span><span class="sxs-lookup"><span data-stu-id="e70bc-255">For more information, see [How to: Create a simple event handler](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb675300(v=vs.100)).</span></span>

    [!code-xaml[ExpenseIt#15](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml#15)]

2. <span data-ttu-id="e70bc-256">Öffnen *`ExpenseItHome.xaml.vb`* Sie *`ExpenseItHome.xaml.cs`* oder.</span><span class="sxs-lookup"><span data-stu-id="e70bc-256">Open *`ExpenseItHome.xaml.vb`* or *`ExpenseItHome.xaml.cs`*.</span></span>

3. <span data-ttu-id="e70bc-257">Fügen Sie der- `ExpenseItHome` Klasse den folgenden Code hinzu, um einen Schaltflächen-Click-Ereignishandler hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="e70bc-257">Add the following code to the `ExpenseItHome` class to add a button click event handler.</span></span> <span data-ttu-id="e70bc-258">Der Ereignishandler öffnet die Seite **ExpenseReportPage** .</span><span class="sxs-lookup"><span data-stu-id="e70bc-258">The event handler opens the **ExpenseReportPage** page.</span></span>

    [!code-csharp[ExpenseIt#16](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml.cs#16)]
    [!code-vb[ExpenseIt#16](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt6/ExpenseItHome.xaml.vb#16)]

## <a name="create-the-ui-for-expensereportpage"></a><span data-ttu-id="e70bc-259">Erstellen der Benutzeroberfläche für ExpenseReportPage</span><span class="sxs-lookup"><span data-stu-id="e70bc-259">Create the UI for ExpenseReportPage</span></span>

<span data-ttu-id="e70bc-260">*ExpenseReportPage. XAML* zeigt den Ausgaben Bericht für die Person an, die auf der **`ExpenseItHome`** Seite ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="e70bc-260">*ExpenseReportPage.xaml* displays the expense report for the person that's selected on the **`ExpenseItHome`** page.</span></span> <span data-ttu-id="e70bc-261">In diesem Abschnitt erstellen Sie die Benutzeroberfläche für **ExpenseReportPage**.</span><span class="sxs-lookup"><span data-stu-id="e70bc-261">In this section, you'll create the UI for **ExpenseReportPage**.</span></span> <span data-ttu-id="e70bc-262">Außerdem fügen Sie den verschiedenen Benutzeroberflächen Elementen Hintergrund-und Füll Farben hinzu.</span><span class="sxs-lookup"><span data-stu-id="e70bc-262">You'll also add background and fill colors to the various UI elements.</span></span>

1. <span data-ttu-id="e70bc-263">Öffnen Sie *ExpenseReportPage.xaml*.</span><span class="sxs-lookup"><span data-stu-id="e70bc-263">Open *ExpenseReportPage.xaml*.</span></span>

2. <span data-ttu-id="e70bc-264">Fügen Sie den folgenden XAML- <xref:System.Windows.Controls.Grid> Code zwischen den-Tags hinzu:</span><span class="sxs-lookup"><span data-stu-id="e70bc-264">Add the following XAML between the <xref:System.Windows.Controls.Grid> tags:</span></span>

    [!code-xaml[ExpenseIt#17](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseReportPage.xaml#17)]

    <span data-ttu-id="e70bc-265">Diese Benutzeroberfläche ähnelt *`ExpenseItHome.xaml`* , mit dem Unterschied, dass die Berichtsdaten in einer <xref:System.Windows.Controls.DataGrid>angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="e70bc-265">This UI is similar to *`ExpenseItHome.xaml`*, except the report data is displayed in a <xref:System.Windows.Controls.DataGrid>.</span></span>

3. <span data-ttu-id="e70bc-266">Erstellen Sie die Anwendung, und führen Sie sie aus.</span><span class="sxs-lookup"><span data-stu-id="e70bc-266">Build and run the application.</span></span>

4. <span data-ttu-id="e70bc-267">Wählen Sie die Schaltfläche **Ansicht** aus.</span><span class="sxs-lookup"><span data-stu-id="e70bc-267">Select the **View** button.</span></span>

    <span data-ttu-id="e70bc-268">Die Spesenabrechnungsseite wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e70bc-268">The expense report page appears.</span></span> <span data-ttu-id="e70bc-269">Beachten Sie auch, dass die Navigations Schaltfläche zurück aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="e70bc-269">Also notice that the back navigation button is enabled.</span></span>

<span data-ttu-id="e70bc-270">Die folgende Abbildung zeigt die Benutzeroberflächen Elemente, die zu *ExpenseReportPage. XAML*hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="e70bc-270">The following illustration shows the UI elements added to *ExpenseReportPage.xaml*.</span></span>

![Der ExpenseIt-Beispiel-Screenshot mit der Benutzeroberfläche, die soeben für die ExpenseReportPage erstellt wurde.](./media/walkthrough-my-first-wpf-desktop-application/create-application-ui.png)

## <a name="style-controls"></a><span data-ttu-id="e70bc-272">Stil Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="e70bc-272">Style controls</span></span>

<span data-ttu-id="e70bc-273">Die Darstellung verschiedener Elemente ist für alle Elemente desselben Typs in einer Benutzeroberfläche häufig identisch.</span><span class="sxs-lookup"><span data-stu-id="e70bc-273">The appearance of various elements is often the same for all elements of the same type in a UI.</span></span> <span data-ttu-id="e70bc-274">Die Benutzeroberfläche verwendet [Stile](../controls/styling-and-templating.md) , um die übergreifende Wiederverwendung über mehrere Elemente hinweg</span><span class="sxs-lookup"><span data-stu-id="e70bc-274">UI uses [styles](../controls/styling-and-templating.md) to make appearances reusable across multiple elements.</span></span> <span data-ttu-id="e70bc-275">Die Wiederverwendbarkeit von Stilen vereinfacht die Erstellung und Verwaltung von XAML.</span><span class="sxs-lookup"><span data-stu-id="e70bc-275">The reusability of styles helps to simplify XAML creation and management.</span></span> <span data-ttu-id="e70bc-276">Dieser Abschnitt ersetzt die Attribute pro Element, die in den vorherigen Schritten mit Stilen definiert wurden.</span><span class="sxs-lookup"><span data-stu-id="e70bc-276">This section replaces the per-element attributes that were defined in previous steps with styles.</span></span>

1. <span data-ttu-id="e70bc-277">Öffnen Sie " *Application. XAML* " oder " *app. XAML*".</span><span class="sxs-lookup"><span data-stu-id="e70bc-277">Open *Application.xaml* or *App.xaml*.</span></span>

2. <span data-ttu-id="e70bc-278">Fügen Sie den folgenden XAML- <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> Code zwischen den-Tags hinzu:</span><span class="sxs-lookup"><span data-stu-id="e70bc-278">Add the following XAML between the <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> tags:</span></span>

    [!code-xaml[ExpenseIt#18](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/App.xaml#18)]

    <span data-ttu-id="e70bc-279">Durch diese XAML werden folgende Stile hinzugefügt:</span><span class="sxs-lookup"><span data-stu-id="e70bc-279">This XAML adds the following styles:</span></span>

    - <span data-ttu-id="e70bc-280">`headerTextStyle`: Zum Formatieren des Seiten <xref:System.Windows.Controls.Label>Titels.</span><span class="sxs-lookup"><span data-stu-id="e70bc-280">`headerTextStyle`: To format the page title <xref:System.Windows.Controls.Label>.</span></span>

    - <span data-ttu-id="e70bc-281">`labelStyle`: Zum Formatieren <xref:System.Windows.Controls.Label> der-Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="e70bc-281">`labelStyle`: To format the <xref:System.Windows.Controls.Label> controls.</span></span>

    - <span data-ttu-id="e70bc-282">`columnHeaderStyle`: Zum Formatieren <xref:System.Windows.Controls.Primitives.DataGridColumnHeader>von.</span><span class="sxs-lookup"><span data-stu-id="e70bc-282">`columnHeaderStyle`: To format the <xref:System.Windows.Controls.Primitives.DataGridColumnHeader>.</span></span>

    - <span data-ttu-id="e70bc-283">`listHeaderStyle`: Zum Formatieren der Listen <xref:System.Windows.Controls.Border> Header-Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="e70bc-283">`listHeaderStyle`: To format the list header <xref:System.Windows.Controls.Border> controls.</span></span>

    - <span data-ttu-id="e70bc-284">`listHeaderTextStyle`: , Um den Listen Header <xref:System.Windows.Controls.Label>zu formatieren.</span><span class="sxs-lookup"><span data-stu-id="e70bc-284">`listHeaderTextStyle`: To format the list header <xref:System.Windows.Controls.Label>.</span></span>

    - <span data-ttu-id="e70bc-285">`buttonStyle`: Zum Formatieren <xref:System.Windows.Controls.Button> von `ExpenseItHome.xaml`auf.</span><span class="sxs-lookup"><span data-stu-id="e70bc-285">`buttonStyle`: To format the <xref:System.Windows.Controls.Button> on `ExpenseItHome.xaml`.</span></span>

    <span data-ttu-id="e70bc-286">Beachten Sie, dass die Stile Ressourcen und untergeordnete <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> Elemente des Property-Elements sind.</span><span class="sxs-lookup"><span data-stu-id="e70bc-286">Notice that the styles are resources and children of the <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> property element.</span></span> <span data-ttu-id="e70bc-287">An diesem Speicherort werden die Stile auf alle Elemente in einer Anwendung angewendet.</span><span class="sxs-lookup"><span data-stu-id="e70bc-287">In this location, the styles are applied to all the elements in an application.</span></span> <span data-ttu-id="e70bc-288">Ein Beispiel für die Verwendung von Ressourcen in einer .net-App finden Sie unter [Verwenden von Anwendungs Ressourcen](../advanced/how-to-use-application-resources.md).</span><span class="sxs-lookup"><span data-stu-id="e70bc-288">For an example of using resources in a .NET app, see [Use Application Resources](../advanced/how-to-use-application-resources.md).</span></span>

3. <span data-ttu-id="e70bc-289">Ersetzen *`ExpenseItHome.xaml`* Sie in alles zwischen den <xref:System.Windows.Controls.Grid> Elementen durch den folgenden XAML-Code:</span><span class="sxs-lookup"><span data-stu-id="e70bc-289">In *`ExpenseItHome.xaml`*, replace everything between the <xref:System.Windows.Controls.Grid> elements with the following XAML:</span></span>

    [!code-xaml[ExpenseIt#19](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseItHome.xaml#19)]

    <span data-ttu-id="e70bc-290">Eigenschaften wie <xref:System.Windows.VerticalAlignment> und <xref:System.Windows.Media.FontFamily> , die die Darstellung der einzelnen Steuerelemente definieren, werden entfernt und ersetzt, indem die Stile angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="e70bc-290">The properties such as <xref:System.Windows.VerticalAlignment> and <xref:System.Windows.Media.FontFamily> that define the look of each control are removed and replaced by applying the styles.</span></span> <span data-ttu-id="e70bc-291">Beispielsweise `headerTextStyle` wird auf den Bericht "Ausgaben anzeigen" <xref:System.Windows.Controls.Label>angewendet.</span><span class="sxs-lookup"><span data-stu-id="e70bc-291">For example, the `headerTextStyle` is applied to the "View Expense Report" <xref:System.Windows.Controls.Label>.</span></span>

4. <span data-ttu-id="e70bc-292">Öffnen Sie *ExpenseReportPage.xaml*.</span><span class="sxs-lookup"><span data-stu-id="e70bc-292">Open *ExpenseReportPage.xaml*.</span></span>

5. <span data-ttu-id="e70bc-293">Ersetzen Sie alles zwischen <xref:System.Windows.Controls.Grid> den Elementen durch den folgenden XAML-Code:</span><span class="sxs-lookup"><span data-stu-id="e70bc-293">Replace everything between the <xref:System.Windows.Controls.Grid> elements with the following XAML:</span></span>

    [!code-xaml[ExpenseIt#20](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseReportPage.xaml#20)]

    <span data-ttu-id="e70bc-294">Dieses XAML fügt dem-Element <xref:System.Windows.Controls.Label> und <xref:System.Windows.Controls.Border> dem-Element Stile hinzu.</span><span class="sxs-lookup"><span data-stu-id="e70bc-294">This XAML adds styles to the <xref:System.Windows.Controls.Label> and <xref:System.Windows.Controls.Border> elements.</span></span>

6. <span data-ttu-id="e70bc-295">Erstellen Sie die Anwendung, und führen Sie sie aus.</span><span class="sxs-lookup"><span data-stu-id="e70bc-295">Build and run the application.</span></span> <span data-ttu-id="e70bc-296">Die Fenster Darstellung ist das gleiche wie zuvor.</span><span class="sxs-lookup"><span data-stu-id="e70bc-296">The window appearance is the same as previously.</span></span>

    ![Der ExpenseIt-Beispiel Bildschirm mit derselben Darstellung wie im letzten Abschnitt.](./media/walkthrough-my-first-wpf-desktop-application/create-application-ui.png)

7. <span data-ttu-id="e70bc-298">Schließen Sie die Anwendung, um zu Visual Studio zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="e70bc-298">Close the application to return to Visual Studio.</span></span>

## <a name="bind-data-to-a-control"></a><span data-ttu-id="e70bc-299">Binden von Daten an ein Steuerelement</span><span class="sxs-lookup"><span data-stu-id="e70bc-299">Bind data to a control</span></span>

<span data-ttu-id="e70bc-300">In diesem Abschnitt erstellen Sie die XML-Daten, die an verschiedene Steuerelemente gebunden sind.</span><span class="sxs-lookup"><span data-stu-id="e70bc-300">In this section, you'll create the XML data that is bound to various controls.</span></span>

1. <span data-ttu-id="e70bc-301">Fügen *`ExpenseItHome.xaml`* Sie in nach dem <xref:System.Windows.Controls.Grid> öffnenden-Element den folgenden XAML-Code <xref:System.Windows.Data.XmlDataProvider> hinzu, um ein-Element zu erstellen, das die Daten für jede Person enthält:</span><span class="sxs-lookup"><span data-stu-id="e70bc-301">In *`ExpenseItHome.xaml`*, after the opening <xref:System.Windows.Controls.Grid> element, add the following XAML to create an <xref:System.Windows.Data.XmlDataProvider> that contains the data for each person:</span></span>

    [!code-xaml[ExpenseIt#23](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml?range=13,16-40,49)]

    <span data-ttu-id="e70bc-302">Die Daten werden als <xref:System.Windows.Controls.Grid> Ressource erstellt.</span><span class="sxs-lookup"><span data-stu-id="e70bc-302">The data is created as a <xref:System.Windows.Controls.Grid> resource.</span></span> <span data-ttu-id="e70bc-303">Normalerweise werden diese Daten als Datei geladen, aber aus Gründen der Einfachheit werden die Daten Inline hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="e70bc-303">Normally this data would be loaded as a file, but for simplicity the data is added inline.</span></span>

2. <span data-ttu-id="e70bc-304">Fügen Sie im- `<xref:System.Windows.DataTemplate>` <xref:System.Windows.Controls.ListBox> `<XmlDataProvider>` Element das folgende-Element hinzu, das definiert, wie die Daten in nach dem-Element angezeigt werden sollen: `<Grid.Resources>`</span><span class="sxs-lookup"><span data-stu-id="e70bc-304">Within the `<Grid.Resources>` element, add the following `<xref:System.Windows.DataTemplate>` element, which defines how to display the data in the <xref:System.Windows.Controls.ListBox>, after the `<XmlDataProvider>` element:</span></span>

    [!code-xaml[ExpenseIt#24](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml?range=13,43-46,49)]

    <span data-ttu-id="e70bc-305">Weitere Informationen zu Datenvorlagen finden Sie unter [Übersicht über Daten](../data/data-templating-overview.md)Vorlagen.</span><span class="sxs-lookup"><span data-stu-id="e70bc-305">For more information about data templates, see [Data templating overview](../data/data-templating-overview.md).</span></span>

3. <span data-ttu-id="e70bc-306">Ersetzen Sie die <xref:System.Windows.Controls.ListBox> vorhandene durch den folgenden XAML-Code:</span><span class="sxs-lookup"><span data-stu-id="e70bc-306">Replace the existing <xref:System.Windows.Controls.ListBox> with the following XAML:</span></span>

    [!code-xaml[ExpenseIt#25](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#25)]

    <span data-ttu-id="e70bc-307">Dieses XAML bindet die <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> -Eigenschaft <xref:System.Windows.Controls.ListBox> von an die Datenquelle und wendet <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>die Daten Vorlage als an.</span><span class="sxs-lookup"><span data-stu-id="e70bc-307">This XAML binds the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> property of the <xref:System.Windows.Controls.ListBox> to the data source and applies the data template as the <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>.</span></span>

## <a name="connect-data-to-controls"></a><span data-ttu-id="e70bc-308">Verbinden von Daten mit Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="e70bc-308">Connect data to controls</span></span>

<span data-ttu-id="e70bc-309">Als Nächstes fügen Sie Code hinzu, um den auf der **`ExpenseItHome`** Seite ausgewählten Namen abzurufen und an den Konstruktor von **ExpenseReportPage**zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="e70bc-309">Next, you'll add code to retrieve the name that's selected on the **`ExpenseItHome`** page and pass it to the constructor of **ExpenseReportPage**.</span></span> <span data-ttu-id="e70bc-310">**ExpenseReportPage** legt seinen Datenkontext mit dem bestandenen Element fest. Dies ist das, an das die Steuerelemente, die in *ExpenseReportPage. XAML* definiert sind, an gebunden werden.</span><span class="sxs-lookup"><span data-stu-id="e70bc-310">**ExpenseReportPage** sets its data context with the passed item, which is what the controls defined in *ExpenseReportPage.xaml* bind to.</span></span>

1. <span data-ttu-id="e70bc-311">Öffnen Sie *ExpenseReportPage.xaml.vb* oder *ExpenseReportPage.xaml.cs*.</span><span class="sxs-lookup"><span data-stu-id="e70bc-311">Open *ExpenseReportPage.xaml.vb* or *ExpenseReportPage.xaml.cs*.</span></span>

2. <span data-ttu-id="e70bc-312">Fügen Sie einen Konstruktor hinzu, der ein Objekt akzeptiert, damit Sie die Spesenabrechnungsdaten der ausgewählten Person übergeben können.</span><span class="sxs-lookup"><span data-stu-id="e70bc-312">Add a constructor that takes an object so you can pass the expense report data of the selected person.</span></span>

    [!code-csharp[ExpenseIt#26](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseReportPage.xaml.cs#26)]
    [!code-vb[ExpenseIt#26](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseReportPage.xaml.vb#26)]

3. <span data-ttu-id="e70bc-313">Öffnen *`ExpenseItHome.xaml.vb`* Sie *`ExpenseItHome.xaml.cs`* oder.</span><span class="sxs-lookup"><span data-stu-id="e70bc-313">Open *`ExpenseItHome.xaml.vb`* or *`ExpenseItHome.xaml.cs`*.</span></span>

4. <span data-ttu-id="e70bc-314">Ändern Sie <xref:System.Windows.Controls.Primitives.ButtonBase.Click> den Ereignishandler, um den neuen Konstruktor aufzurufen, der die Spesen Abrechnungsdaten der ausgewählten Person übergibt.</span><span class="sxs-lookup"><span data-stu-id="e70bc-314">Change the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler to call the new constructor passing the expense report data of the selected person.</span></span>

    [!code-csharp[ExpenseIt#27](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml.cs#27)]
    [!code-vb[ExpenseIt#27](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseItHome.xaml.vb#27)]

## <a name="style-data-with-data-templates"></a><span data-ttu-id="e70bc-315">Formatieren von Daten mit Datenvorlagen</span><span class="sxs-lookup"><span data-stu-id="e70bc-315">Style data with data templates</span></span>

<span data-ttu-id="e70bc-316">In diesem Abschnitt aktualisieren Sie die Benutzeroberfläche für jedes Element in den Daten gebundenen Listen mithilfe von Datenvorlagen.</span><span class="sxs-lookup"><span data-stu-id="e70bc-316">In this section, you'll update the UI for each item in the data-bound lists by using data templates.</span></span>

1. <span data-ttu-id="e70bc-317">Öffnen Sie *ExpenseReportPage.xaml*.</span><span class="sxs-lookup"><span data-stu-id="e70bc-317">Open *ExpenseReportPage.xaml*.</span></span>

2. <span data-ttu-id="e70bc-318">Binden Sie den Inhalt der <xref:System.Windows.Controls.Label> Elemente "Name" und "Department" an die entsprechende Datenquellen Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="e70bc-318">Bind the content of the "Name" and "Department" <xref:System.Windows.Controls.Label> elements to the appropriate data source property.</span></span> <span data-ttu-id="e70bc-319">Weitere Informationen zur Datenbindung finden Sie unter [Übersicht über die Datenbindung](../data/data-binding-overview.md).</span><span class="sxs-lookup"><span data-stu-id="e70bc-319">For more information about data binding, see [Data binding overview](../data/data-binding-overview.md).</span></span>

    [!code-xaml[ExpenseIt#31](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#31)]

3. <span data-ttu-id="e70bc-320">Fügen Sie nach <xref:System.Windows.Controls.Grid> dem öffnenden Element die folgenden Datenvorlagen hinzu, die definieren, wie die Spesen Abrechnungsdaten angezeigt werden sollen:</span><span class="sxs-lookup"><span data-stu-id="e70bc-320">After the opening <xref:System.Windows.Controls.Grid> element, add the following data templates, which define how to display the expense report data:</span></span>

    [!code-xaml[ExpenseIt#30](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#30)]

4. <span data-ttu-id="e70bc-321">Ersetzen Sie <xref:System.Windows.Controls.DataGridTextColumn> die Elemente <xref:System.Windows.Controls.DataGridTemplateColumn> durch unter <xref:System.Windows.Controls.DataGrid> dem-Element, und wenden Sie die Vorlagen auf diese an.</span><span class="sxs-lookup"><span data-stu-id="e70bc-321">Replace the <xref:System.Windows.Controls.DataGridTextColumn> elements with <xref:System.Windows.Controls.DataGridTemplateColumn> under the <xref:System.Windows.Controls.DataGrid> element and apply the templates to them.</span></span>

    [!code-xaml[ExpenseIt#32](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#32)]

5. <span data-ttu-id="e70bc-322">Erstellen Sie die Anwendung, und führen Sie sie aus.</span><span class="sxs-lookup"><span data-stu-id="e70bc-322">Build and run the application.</span></span>

6. <span data-ttu-id="e70bc-323">Wählen Sie eine Person aus, und wählen Sie dann die Schaltfläche **Ansicht** .</span><span class="sxs-lookup"><span data-stu-id="e70bc-323">Select a person and then select the **View** button.</span></span>

<span data-ttu-id="e70bc-324">Die folgende Abbildung zeigt die beiden Seiten der `ExpenseIt` Anwendung mit den angewendeten Steuerelementen, Layout, Stilen, Datenbindung und Datenvorlagen:</span><span class="sxs-lookup"><span data-stu-id="e70bc-324">The following illustration shows both pages of the `ExpenseIt` application with controls, layout, styles, data binding, and data templates applied:</span></span>

![Beide Seiten der APP zeigen die Liste der Namen und einen Spesen Bericht an.](./media/walkthrough-my-first-wpf-desktop-application/application-data-templates.png)

> [!NOTE]
> <span data-ttu-id="e70bc-326">Dieses Beispiel veranschaulicht eine bestimmte Funktion von WPF und folgt nicht allen bewährten Methoden für Dinge wie Sicherheit, Lokalisierung und Barrierefreiheit.</span><span class="sxs-lookup"><span data-stu-id="e70bc-326">This sample demonstrates a specific feature of WPF and doesn't follow all best practices for things like security, localization, and accessibility.</span></span> <span data-ttu-id="e70bc-327">Eine umfassende Abdeckung von WPF und bewährten Methoden für die Entwicklung von .net-apps finden Sie in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="e70bc-327">For comprehensive coverage of WPF and the .NET app development best practices, see the following topics:</span></span>
>
> - [<span data-ttu-id="e70bc-328">Barrierefreiheit</span><span class="sxs-lookup"><span data-stu-id="e70bc-328">Accessibility</span></span>](../../ui-automation/accessibility-best-practices.md)
>
> - [<span data-ttu-id="e70bc-329">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="e70bc-329">Security</span></span>](../security-wpf.md)
>
> - [<span data-ttu-id="e70bc-330">Übersicht über WPF-Globalisierung und -Lokalisierung</span><span class="sxs-lookup"><span data-stu-id="e70bc-330">WPF globalization and localization</span></span>](../advanced/wpf-globalization-and-localization-overview.md)
>
> - [<span data-ttu-id="e70bc-331">WPF-Leistung</span><span class="sxs-lookup"><span data-stu-id="e70bc-331">WPF performance</span></span>](../advanced/optimizing-wpf-application-performance.md)

## <a name="next-steps"></a><span data-ttu-id="e70bc-332">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="e70bc-332">Next steps</span></span>

<span data-ttu-id="e70bc-333">In dieser exemplarischen Vorgehensweise haben Sie eine Reihe von Techniken zum Erstellen einer Benutzeroberfläche mithilfe von Windows Presentation Foundation (WPF) kennengelernt.</span><span class="sxs-lookup"><span data-stu-id="e70bc-333">In this walkthrough you learned a number of techniques for creating a UI using Windows Presentation Foundation (WPF).</span></span> <span data-ttu-id="e70bc-334">Sie sollten jetzt grundlegende Kenntnisse der Bausteine einer Daten gebundenen .net-APP haben.</span><span class="sxs-lookup"><span data-stu-id="e70bc-334">You should now have a basic understanding of the building blocks of a data-bound .NET app.</span></span> <span data-ttu-id="e70bc-335">Weitere Informationen über die WPF-Architektur und -Programmiermodelle finden Sie in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="e70bc-335">For more information about the WPF architecture and programming models, see the following topics:</span></span>

- [<span data-ttu-id="e70bc-336">WPF-Architektur</span><span class="sxs-lookup"><span data-stu-id="e70bc-336">WPF architecture</span></span>](../advanced/wpf-architecture.md)
- [<span data-ttu-id="e70bc-337">Übersicht über XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="e70bc-337">XAML overview (WPF)</span></span>](../advanced/xaml-overview-wpf.md)
- [<span data-ttu-id="e70bc-338">Übersicht über Abhängigkeits Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="e70bc-338">Dependency properties overview</span></span>](../advanced/dependency-properties-overview.md)
- [<span data-ttu-id="e70bc-339">Layout</span><span class="sxs-lookup"><span data-stu-id="e70bc-339">Layout</span></span>](../advanced/layout.md)

<span data-ttu-id="e70bc-340">Weitere Informationen zum Erstellen von Anwendungen finden Sie in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="e70bc-340">For more information about creating applications, see the following topics:</span></span>

- [<span data-ttu-id="e70bc-341">Anwendungsentwicklung</span><span class="sxs-lookup"><span data-stu-id="e70bc-341">Application development</span></span>](../app-development/index.md)
- [<span data-ttu-id="e70bc-342">Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="e70bc-342">Controls</span></span>](../controls/index.md)
- [<span data-ttu-id="e70bc-343">Übersicht über Datenbindung</span><span class="sxs-lookup"><span data-stu-id="e70bc-343">Data binding overview</span></span>](../data/data-binding-overview.md)
- [<span data-ttu-id="e70bc-344">Grafiken und Multimedia</span><span class="sxs-lookup"><span data-stu-id="e70bc-344">Graphics and multimedia</span></span>](../graphics-multimedia/index.md)
- [<span data-ttu-id="e70bc-345">Dokumente in WPF</span><span class="sxs-lookup"><span data-stu-id="e70bc-345">Documents in WPF</span></span>](../advanced/documents-in-wpf.md)

## <a name="see-also"></a><span data-ttu-id="e70bc-346">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e70bc-346">See also</span></span>

- [<span data-ttu-id="e70bc-347">Übersicht über Panels</span><span class="sxs-lookup"><span data-stu-id="e70bc-347">Panels overview</span></span>](../controls/panels-overview.md)
- [<span data-ttu-id="e70bc-348">Übersicht über Datenvorlagen</span><span class="sxs-lookup"><span data-stu-id="e70bc-348">Data templating overview</span></span>](../data/data-templating-overview.md)
- [<span data-ttu-id="e70bc-349">Erstellen einer WPF-Anwendung</span><span class="sxs-lookup"><span data-stu-id="e70bc-349">Build a WPF application</span></span>](../app-development/building-a-wpf-application-wpf.md)
- [<span data-ttu-id="e70bc-350">Stile und Vorlagen</span><span class="sxs-lookup"><span data-stu-id="e70bc-350">Styles and templates</span></span>](../controls/styles-and-templates.md)
