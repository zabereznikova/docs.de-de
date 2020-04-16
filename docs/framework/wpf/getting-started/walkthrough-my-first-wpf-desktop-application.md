---
title: Erstellen Ihrer ersten WPF-App in Visual Studio 2019 - .NET Framework
titleSuffix: ''
ms.date: 09/06/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- getting started [WPF], WPF
- WPF [WPF], getting started
ms.assetid: b96bed40-8946-4285-8fe4-88045ab854ed
ms.topic: tutorial
ms.custom: mvc,vs-dotnet
ms.openlocfilehash: facb9ebebd9ce1904886a946277185ac2c2e4bc4
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463926"
---
# <a name="tutorial-create-your-first-wpf-application-in-visual-studio-2019"></a><span data-ttu-id="1881a-102">Tutorial: Erstellen Der ersten WPF-Anwendung in Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="1881a-102">Tutorial: Create your first WPF application in Visual Studio 2019</span></span>

<span data-ttu-id="1881a-103">In diesem Artikel erfahren Sie, wie Sie eine Windows Presentation Foundation (WPF)-Desktopanwendung entwickeln, die die Elemente enthält, die den meisten WPF-Anwendungen gemeinsam sind: XAML-Markup (Extensible Application Markup Language), CodeBehind, Anwendungsdefinitionen, Steuerelemente, Layout, Datenbindung und Stile.</span><span class="sxs-lookup"><span data-stu-id="1881a-103">This article shows you how to develop a Windows Presentation Foundation (WPF) desktop application that includes the elements that are common to most WPF applications: Extensible Application Markup Language (XAML) markup, code-behind, application definitions, controls, layout, data binding, and styles.</span></span> <span data-ttu-id="1881a-104">Zum Entwickeln der Anwendung verwenden Sie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="1881a-104">To develop the application, you'll use Visual Studio.</span></span>

<span data-ttu-id="1881a-105">In diesem Tutorial lernen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="1881a-105">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="1881a-106">Erstellen Sie ein WPF-Projekt.</span><span class="sxs-lookup"><span data-stu-id="1881a-106">Create a WPF project.</span></span>
> - <span data-ttu-id="1881a-107">Verwenden Sie XAML, um die Darstellung der Benutzeroberfläche der Anwendung zu entwerfen.</span><span class="sxs-lookup"><span data-stu-id="1881a-107">Use XAML to design the appearance of the application's user interface (UI).</span></span>
> - <span data-ttu-id="1881a-108">Schreiben Sie Code, um das Verhalten der Anwendung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="1881a-108">Write code to build the application's behavior.</span></span>
> - <span data-ttu-id="1881a-109">Erstellen Sie eine Anwendungsdefinition, um die Anwendung zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="1881a-109">Create an application definition to manage the application.</span></span>
> - <span data-ttu-id="1881a-110">Fügen Sie Steuerelemente hinzu, und erstellen Sie das Layout, um die Anwendungsbenutzeroberfläche zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="1881a-110">Add controls and create the layout to compose the application UI.</span></span>
> - <span data-ttu-id="1881a-111">Erstellen Sie Stile für eine konsistente Darstellung in der gesamten Benutzeroberfläche der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="1881a-111">Create styles for a consistent appearance throughout the application's UI.</span></span>
> - <span data-ttu-id="1881a-112">Binden Sie die Benutzeroberfläche an Daten, um die Benutzeroberfläche aus Daten aufzufüllen und die Daten und die Benutzeroberfläche zu synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="1881a-112">Bind the UI to data, both to populate the UI from data and to keep the data and UI synchronized.</span></span>

<span data-ttu-id="1881a-113">Am Ende des Tutorials haben Sie eine eigenständige Windows-Anwendung erstellt, mit der Benutzer Spesenabrechnungen für ausgewählte Personen anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="1881a-113">By the end of the tutorial, you'll have built a standalone Windows application that allows users to view expense reports for selected people.</span></span> <span data-ttu-id="1881a-114">Die Anwendung besteht aus mehreren WPF-Seiten, die in einem Browserfenster gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="1881a-114">The application is composed of several WPF pages that are hosted in a browser-style window.</span></span>

> [!TIP]
> <span data-ttu-id="1881a-115">Der In diesem Tutorial verwendete Beispielcode ist sowohl für Visual Basic als auch für C-Code unter [Tutorial WPF App Sample Code](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/WalkthroughFirstWPFApp)verfügbar.</span><span class="sxs-lookup"><span data-stu-id="1881a-115">The sample code that is used in this tutorial is available for both Visual Basic and C# at [Tutorial WPF App Sample Code](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/WalkthroughFirstWPFApp).</span></span>
>
> <span data-ttu-id="1881a-116">Sie können die Codesprache des Beispielcodes zwischen C- und Visual Basic umschalten, indem Sie die Sprachauswahl oben auf dieser Seite verwenden.</span><span class="sxs-lookup"><span data-stu-id="1881a-116">You can toggle the code language of the sample code between C# and Visual Basic by using the language selector on top of this page.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1881a-117">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="1881a-117">Prerequisites</span></span>

- <span data-ttu-id="1881a-118">[Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) mit der **installierten .NET Desktopentwicklungsworkload.**</span><span class="sxs-lookup"><span data-stu-id="1881a-118">[Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) with the **.NET desktop development** workload installed.</span></span>

   <span data-ttu-id="1881a-119">Weitere Informationen zum Installieren der neuesten Version von Visual Studio finden Sie unter Installieren von [Visual Studio](/visualstudio/install/install-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="1881a-119">For more information about installing the latest version of Visual Studio, see [Install Visual Studio](/visualstudio/install/install-visual-studio).</span></span>

## <a name="create-the-application-project"></a><span data-ttu-id="1881a-120">Erstellen des Anwendungsprojekts</span><span class="sxs-lookup"><span data-stu-id="1881a-120">Create the application project</span></span>

<span data-ttu-id="1881a-121">Der erste Schritt besteht darin, die Anwendungsinfrastruktur zu erstellen, die eine Anwendungsdefinition, zwei Seiten und ein Bild enthält.</span><span class="sxs-lookup"><span data-stu-id="1881a-121">The first step is to create the application infrastructure, which includes an application definition, two pages, and an image.</span></span>

1. <span data-ttu-id="1881a-122">Erstellen Sie ein neues WPF-Anwendungsprojekt in **`ExpenseIt`** Visual Basic oder Visual C mit dem Namen :</span><span class="sxs-lookup"><span data-stu-id="1881a-122">Create a new WPF Application project in Visual Basic or Visual C# named **`ExpenseIt`**:</span></span>

   1. <span data-ttu-id="1881a-123">Öffnen Sie Visual Studio, und wählen Sie Unter dem Menü **Erste** Schritte **ein neues Projekt** erstellen aus.</span><span class="sxs-lookup"><span data-stu-id="1881a-123">Open Visual Studio and select **Create a new project** under the **Get started** menu.</span></span>

      <span data-ttu-id="1881a-124">Das Dialogfeld **Neues Projekt** erstellen wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="1881a-124">The **Create a new project** dialog opens.</span></span>

   2. <span data-ttu-id="1881a-125">Wählen Sie in der Dropdown-Liste **Sprache** entweder **"C"** oder **"Visual Basic"** aus.</span><span class="sxs-lookup"><span data-stu-id="1881a-125">In the **Language** dropdown, select either **C#** or **Visual Basic**.</span></span>

   3. <span data-ttu-id="1881a-126">Wählen Sie die **Vorlage WPF App (.NET Framework)** und dann **Weiter**aus.</span><span class="sxs-lookup"><span data-stu-id="1881a-126">Select the **WPF App (.NET Framework)** template and then select **Next**.</span></span>

      ![Dialogfeld „Neues Projekt erstellen“](./media/walkthrough-my-first-wpf-desktop-application/create-new-project-dialog.png)

      <span data-ttu-id="1881a-128">Das Dialogfeld **Konfigurieren des neuen Projekts** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="1881a-128">The **Configure your new project** dialog opens.</span></span>

   4. <span data-ttu-id="1881a-129">Geben Sie **`ExpenseIt`** den Projektnamen ein, und wählen Sie dann **Erstellen**aus.</span><span class="sxs-lookup"><span data-stu-id="1881a-129">Enter the project name **`ExpenseIt`** and then select **Create**.</span></span>

      ![Konfigurieren eines neuen Projektdialogs](./media/walkthrough-my-first-wpf-desktop-application/configure-new-project-dialog.png)

      <span data-ttu-id="1881a-131">Visual Studio erstellt das Projekt und öffnet den Designer für das Standardanwendungsfenster mit dem Namen **MainWindow.xaml**.</span><span class="sxs-lookup"><span data-stu-id="1881a-131">Visual Studio creates the project and opens the designer for the default application window named **MainWindow.xaml**.</span></span>

2. <span data-ttu-id="1881a-132">Öffnen Sie *Application.xaml* (Visual Basic) oder *App.xaml* (C-Wert).</span><span class="sxs-lookup"><span data-stu-id="1881a-132">Open *Application.xaml* (Visual Basic) or *App.xaml* (C#).</span></span>

    <span data-ttu-id="1881a-133">Diese XAML-Datei definiert eine WPF-Anwendung und alle Anwendungsressourcen.</span><span class="sxs-lookup"><span data-stu-id="1881a-133">This XAML file defines a WPF application and any application resources.</span></span> <span data-ttu-id="1881a-134">Sie verwenden diese Datei auch, um die Benutzeroberfläche anzugeben, in diesem Fall *MainWindow.xaml*, die automatisch anzeigt, wann die Anwendung gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="1881a-134">You also use this file to specify the UI, in this case *MainWindow.xaml*, that automatically shows when the application starts.</span></span>

    <span data-ttu-id="1881a-135">Ihr XAML sollte in Visual Basic wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="1881a-135">Your XAML should look like the following in Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#1_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/Application.xaml#1_a)]

    <span data-ttu-id="1881a-136">Und wie folgt in C':</span><span class="sxs-lookup"><span data-stu-id="1881a-136">And like the following in C#:</span></span>

    [!code-xaml[ExpenseIt#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/App.xaml#1)]

3. <span data-ttu-id="1881a-137">Öffnen *MainWindow.xaml*.</span><span class="sxs-lookup"><span data-stu-id="1881a-137">Open *MainWindow.xaml*.</span></span>

    <span data-ttu-id="1881a-138">Diese XAML-Datei ist das Hauptfenster Ihrer Anwendung und zeigt Inhalte an, die auf Seiten erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="1881a-138">This XAML file is the main window of your application and displays content created in pages.</span></span> <span data-ttu-id="1881a-139">Die <xref:System.Windows.Window> Klasse definiert die Eigenschaften eines Fensters, z. B. Titel, Größe oder Symbol, und behandelt Ereignisse, z. B. schließen oder ausblenden.</span><span class="sxs-lookup"><span data-stu-id="1881a-139">The <xref:System.Windows.Window> class defines the properties of a window, such as its title, size, or icon, and handles events, such as closing or hiding.</span></span>

4. <span data-ttu-id="1881a-140">Ändern <xref:System.Windows.Window> Sie das <xref:System.Windows.Navigation.NavigationWindow>Element in ein , wie in der folgenden XAML gezeigt:</span><span class="sxs-lookup"><span data-stu-id="1881a-140">Change the <xref:System.Windows.Window> element to a <xref:System.Windows.Navigation.NavigationWindow>, as shown in the following XAML:</span></span>

   ```xaml
   <NavigationWindow x:Class="ExpenseIt.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        ...
   </NavigationWindow>
   ```

   <span data-ttu-id="1881a-141">Diese App navigiert zu unterschiedlichen Inhalten, abhängig von der Benutzereingabe.</span><span class="sxs-lookup"><span data-stu-id="1881a-141">This app navigates to different content depending on the user input.</span></span> <span data-ttu-id="1881a-142">Aus diesem Grund <xref:System.Windows.Window> muss die Hauptsache in eine <xref:System.Windows.Navigation.NavigationWindow>geändert werden.</span><span class="sxs-lookup"><span data-stu-id="1881a-142">This is why the main <xref:System.Windows.Window> needs to be changed to a <xref:System.Windows.Navigation.NavigationWindow>.</span></span> <span data-ttu-id="1881a-143"><xref:System.Windows.Navigation.NavigationWindow>erbt alle Eigenschaften <xref:System.Windows.Window>von .</span><span class="sxs-lookup"><span data-stu-id="1881a-143"><xref:System.Windows.Navigation.NavigationWindow> inherits all the properties of <xref:System.Windows.Window>.</span></span> <span data-ttu-id="1881a-144">Das <xref:System.Windows.Navigation.NavigationWindow> Element in der XAML-Datei <xref:System.Windows.Navigation.NavigationWindow> erstellt eine Instanz der Klasse.</span><span class="sxs-lookup"><span data-stu-id="1881a-144">The <xref:System.Windows.Navigation.NavigationWindow> element in the XAML file creates an instance of the <xref:System.Windows.Navigation.NavigationWindow> class.</span></span> <span data-ttu-id="1881a-145">Weitere Informationen finden Sie unter [Navigationsübersicht](../app-development/navigation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="1881a-145">For more information, see [Navigation overview](../app-development/navigation-overview.md).</span></span>

5. <span data-ttu-id="1881a-146">Entfernen <xref:System.Windows.Controls.Grid> Sie die <xref:System.Windows.Navigation.NavigationWindow> Elemente zwischen den Tags.</span><span class="sxs-lookup"><span data-stu-id="1881a-146">Remove the <xref:System.Windows.Controls.Grid> elements from between the <xref:System.Windows.Navigation.NavigationWindow> tags.</span></span>

6. <span data-ttu-id="1881a-147">Ändern Sie die folgenden Eigenschaften im <xref:System.Windows.Navigation.NavigationWindow> XAML-Code für das Element:</span><span class="sxs-lookup"><span data-stu-id="1881a-147">Change the following properties in the XAML code for the <xref:System.Windows.Navigation.NavigationWindow> element:</span></span>

    - <span data-ttu-id="1881a-148">Legen <xref:System.Windows.Window.Title%2A> Sie die`ExpenseIt`Eigenschaft auf " fest.</span><span class="sxs-lookup"><span data-stu-id="1881a-148">Set the <xref:System.Windows.Window.Title%2A> property to "`ExpenseIt`".</span></span>

    - <span data-ttu-id="1881a-149">Legen <xref:System.Windows.FrameworkElement.Height%2A> Sie die Eigenschaft auf 350 Pixel fest.</span><span class="sxs-lookup"><span data-stu-id="1881a-149">Set the <xref:System.Windows.FrameworkElement.Height%2A> property to 350 pixels.</span></span>

    - <span data-ttu-id="1881a-150">Legen <xref:System.Windows.FrameworkElement.Width%2A> Sie die Eigenschaft auf 500 Pixel fest.</span><span class="sxs-lookup"><span data-stu-id="1881a-150">Set the <xref:System.Windows.FrameworkElement.Width%2A> property to 500 pixels.</span></span>

    <span data-ttu-id="1881a-151">Ihr XAML sollte für Visual Basic wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="1881a-151">Your XAML should look like the following for Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#2_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt/MainWindow.xaml#2_a)]

    <span data-ttu-id="1881a-152">Und wie folgt für C':</span><span class="sxs-lookup"><span data-stu-id="1881a-152">And like the following for C#:</span></span>

    [!code-xaml[ExpenseIt#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/MainWindow.xaml#2)]

7. <span data-ttu-id="1881a-153">Öffnen Sie *MainWindow.xaml.vb* oder *MainWindow.xaml.cs*.</span><span class="sxs-lookup"><span data-stu-id="1881a-153">Open *MainWindow.xaml.vb* or *MainWindow.xaml.cs*.</span></span>

    <span data-ttu-id="1881a-154">Diese Datei ist eine CodeBehind-Datei, die Code enthält, um die in *MainWindow.xaml*deklarierten Ereignisse zu behandeln.</span><span class="sxs-lookup"><span data-stu-id="1881a-154">This file is a code-behind file that contains code to handle the events declared in *MainWindow.xaml*.</span></span> <span data-ttu-id="1881a-155">Diese Datei enthält eine partielle Klasse für das in XAML definierte Fenster.</span><span class="sxs-lookup"><span data-stu-id="1881a-155">This file contains a partial class for the window defined in XAML.</span></span>

8. <span data-ttu-id="1881a-156">Wenn Sie C- verwenden, `MainWindow` ändern Sie die <xref:System.Windows.Navigation.NavigationWindow>Klasse, um von abzuleiten.</span><span class="sxs-lookup"><span data-stu-id="1881a-156">If you're using C#, change the `MainWindow` class to derive from <xref:System.Windows.Navigation.NavigationWindow>.</span></span> <span data-ttu-id="1881a-157">(In Visual Basic geschieht dies automatisch, wenn Sie das Fenster in XAML ändern.) Ihr C-Code sollte nun wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="1881a-157">(In Visual Basic, this happens automatically when you change the window in XAML.) Your C# code should now look like this:</span></span>

   [!code-csharp[ExpenseIt#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/MainWindow.xaml.cs?highlight=21)]

## <a name="add-files-to-the-application"></a><span data-ttu-id="1881a-158">Hinzufügen von Dateien zur Anwendung</span><span class="sxs-lookup"><span data-stu-id="1881a-158">Add files to the application</span></span>

<span data-ttu-id="1881a-159">In diesem Abschnitt fügen Sie der Anwendung zwei Seiten und ein Bild hinzu.</span><span class="sxs-lookup"><span data-stu-id="1881a-159">In this section, you'll add two pages and an image to the application.</span></span>

1. <span data-ttu-id="1881a-160">Fügen Sie dem Projekt eine neue *`ExpenseItHome.xaml`* Seite hinzu, und benennen Sie es:</span><span class="sxs-lookup"><span data-stu-id="1881a-160">Add a new page to the project, and name it *`ExpenseItHome.xaml`*:</span></span>

   1. <span data-ttu-id="1881a-161">Klicken Sie im **Projektmappen-Explorer** **`ExpenseIt`** mit der rechten Maustaste auf den Projektknoten, und wählen Sie Seite **hinzufügen** > **Page**aus.</span><span class="sxs-lookup"><span data-stu-id="1881a-161">In **Solution Explorer**, right-click on the **`ExpenseIt`** project node and choose **Add** > **Page**.</span></span>

   1. <span data-ttu-id="1881a-162">Im Dialogfeld **Neues Element hinzufügen** ist die Vorlage Seite **(WPF)** bereits ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="1881a-162">In the **Add New Item** dialog, the **Page (WPF)** template is already selected.</span></span> <span data-ttu-id="1881a-163">Geben Sie **`ExpenseItHome`** den Namen ein, und wählen Sie dann **Hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="1881a-163">Enter the name **`ExpenseItHome`**, and then select **Add**.</span></span>

    <span data-ttu-id="1881a-164">Diese Seite ist die erste Seite, die beim Starten der Anwendung angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="1881a-164">This page is the first page that's displayed when the application is launched.</span></span> <span data-ttu-id="1881a-165">Es wird eine Liste der Personen angezeigt, aus denen eine Spesenabrechnung ausgewählt werden soll.</span><span class="sxs-lookup"><span data-stu-id="1881a-165">It will show a list of people to select from, to show an expense report for.</span></span>

1. <span data-ttu-id="1881a-166">Öffnen *`ExpenseItHome.xaml`*.</span><span class="sxs-lookup"><span data-stu-id="1881a-166">Open *`ExpenseItHome.xaml`*.</span></span>

1. <span data-ttu-id="1881a-167">Stellen <xref:System.Windows.Controls.Page.Title%2A> Sie`ExpenseIt - Home`die Einstellung auf " ein.</span><span class="sxs-lookup"><span data-stu-id="1881a-167">Set the <xref:System.Windows.Controls.Page.Title%2A> to "`ExpenseIt - Home`".</span></span>

1. <span data-ttu-id="1881a-168">Legen `DesignHeight` Sie die auf 350 Pixel und die `DesignWidth` auf 500 Pixel fest.</span><span class="sxs-lookup"><span data-stu-id="1881a-168">Set the `DesignHeight` to 350 pixels and the `DesignWidth` to 500 pixels.</span></span>

    <span data-ttu-id="1881a-169">Das XAML wird nun wie folgt für Visual Basic angezeigt:</span><span class="sxs-lookup"><span data-stu-id="1881a-169">The XAML now appears as follows for Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#6_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml#6_a)]

    <span data-ttu-id="1881a-170">Und wie folgt für C':</span><span class="sxs-lookup"><span data-stu-id="1881a-170">And like the following for C#:</span></span>

    [!code-xaml[ExpenseIt#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml#6)]

1. <span data-ttu-id="1881a-171">Öffnen *MainWindow.xaml*.</span><span class="sxs-lookup"><span data-stu-id="1881a-171">Open *MainWindow.xaml*.</span></span>

1. <span data-ttu-id="1881a-172">Fügen <xref:System.Windows.Navigation.NavigationWindow.Source%2A> Sie dem <xref:System.Windows.Navigation.NavigationWindow> Element eine Eigenschaft`ExpenseItHome.xaml`hinzu, und legen Sie sie auf " fest.</span><span class="sxs-lookup"><span data-stu-id="1881a-172">Add a <xref:System.Windows.Navigation.NavigationWindow.Source%2A> property to the <xref:System.Windows.Navigation.NavigationWindow> element and set it to "`ExpenseItHome.xaml`".</span></span>

    <span data-ttu-id="1881a-173">Dies *`ExpenseItHome.xaml`* wird als die erste Seite festgelegt, die beim Starten der Anwendung geöffnet wird.</span><span class="sxs-lookup"><span data-stu-id="1881a-173">This sets *`ExpenseItHome.xaml`* to be the first page opened when the application starts.</span></span>

    <span data-ttu-id="1881a-174">Beispiel XAML in Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="1881a-174">Example XAML in Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#7_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/MainWindow.xaml#7_a)]

    <span data-ttu-id="1881a-175">Und in C':</span><span class="sxs-lookup"><span data-stu-id="1881a-175">And in C#:</span></span>

    [!code-xaml[ExpenseIt#7](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/MainWindow.xaml#7)]

   > [!TIP]
   > <span data-ttu-id="1881a-176">Sie können die **Source-Eigenschaft** auch in der Kategorie **Verschiedenes** des **Fensters Eigenschaften** festlegen.</span><span class="sxs-lookup"><span data-stu-id="1881a-176">You can also set the **Source** property in the **Miscellaneous** category of the **Properties** window.</span></span>
   >
   > ![Quelleigenschaft im Fenster Eigenschaften](./media/properties-source.png)

1. <span data-ttu-id="1881a-178">Fügen Sie dem Projekt eine weitere neue WPF-Seite hinzu, und nennen Sie es *ExpenseReportPage.xaml*::</span><span class="sxs-lookup"><span data-stu-id="1881a-178">Add another new WPF page to the project, and name it *ExpenseReportPage.xaml*::</span></span>

   1. <span data-ttu-id="1881a-179">Klicken Sie im **Projektmappen-Explorer** **`ExpenseIt`** mit der rechten Maustaste auf den Projektknoten, und wählen Sie Seite **hinzufügen** > **Page**aus.</span><span class="sxs-lookup"><span data-stu-id="1881a-179">In **Solution Explorer**, right-click on the **`ExpenseIt`** project node and choose **Add** > **Page**.</span></span>

   1. <span data-ttu-id="1881a-180">Wählen Sie im Dialogfeld **Neues Element hinzufügen** die Vorlage Seite **(WPF)** aus.</span><span class="sxs-lookup"><span data-stu-id="1881a-180">In the **Add New Item** dialog, select the **Page (WPF)** template.</span></span> <span data-ttu-id="1881a-181">Geben Sie den Namen **ExpenseReportPage**ein, und wählen Sie dann **Hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="1881a-181">Enter the name **ExpenseReportPage**, and then select **Add**.</span></span>

    <span data-ttu-id="1881a-182">Auf dieser Seite wird die Spesenabrechnung **`ExpenseItHome`** für die auf der Seite ausgewählte Person angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1881a-182">This page will show the expense report for the person that is selected on the **`ExpenseItHome`** page.</span></span>

1. <span data-ttu-id="1881a-183">Öffnen Sie *ExpenseReportPage.xaml*.</span><span class="sxs-lookup"><span data-stu-id="1881a-183">Open *ExpenseReportPage.xaml*.</span></span>

1. <span data-ttu-id="1881a-184">Stellen <xref:System.Windows.Controls.Page.Title%2A> Sie`ExpenseIt - View Expense`die Einstellung auf " ein.</span><span class="sxs-lookup"><span data-stu-id="1881a-184">Set the <xref:System.Windows.Controls.Page.Title%2A> to "`ExpenseIt - View Expense`".</span></span>

1. <span data-ttu-id="1881a-185">Legen `DesignHeight` Sie die auf 350 Pixel und die `DesignWidth` auf 500 Pixel fest.</span><span class="sxs-lookup"><span data-stu-id="1881a-185">Set the `DesignHeight` to 350 pixels and the `DesignWidth` to 500 pixels.</span></span>

    <span data-ttu-id="1881a-186">*ExpenseReportPage.xaml* sieht jetzt wie folgt in Visual Basic aus:</span><span class="sxs-lookup"><span data-stu-id="1881a-186">*ExpenseReportPage.xaml* now looks like the following in Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#4_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml#4_a)]

    <span data-ttu-id="1881a-187">Und wie folgt in C':</span><span class="sxs-lookup"><span data-stu-id="1881a-187">And like the following in C#:</span></span>

    [!code-xaml[ExpenseIt#4](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml#4)]

1. <span data-ttu-id="1881a-188">Öffnen Sie *ExpenseItHome.xaml.vb* und *ExpenseReportPage.xaml.vb*oder *ExpenseItHome.xaml.cs* und *ExpenseReportPage.xaml.cs*.</span><span class="sxs-lookup"><span data-stu-id="1881a-188">Open *ExpenseItHome.xaml.vb* and *ExpenseReportPage.xaml.vb*, or *ExpenseItHome.xaml.cs* and *ExpenseReportPage.xaml.cs*.</span></span>

    <span data-ttu-id="1881a-189">Wenn Sie eine neue Seitendatei erstellen, erstellt Visual Studio automatisch die *CodeBehind-Datei.*</span><span class="sxs-lookup"><span data-stu-id="1881a-189">When you create a new Page file, Visual Studio automatically creates its *code-behind* file.</span></span> <span data-ttu-id="1881a-190">Diese CodeBehind-Dateien behandeln die Logik zum Reagieren auf Benutzereingabe.</span><span class="sxs-lookup"><span data-stu-id="1881a-190">These code-behind files handle the logic for responding to user input.</span></span>

    <span data-ttu-id="1881a-191">Ihr Code sollte wie **`ExpenseItHome`** folgt aussehen für:</span><span class="sxs-lookup"><span data-stu-id="1881a-191">Your code should look like the following for **`ExpenseItHome`**:</span></span>

    [!code-csharp[ExpenseIt#2_5](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml.cs#2_5)]

    [!code-vb[ExpenseIt#2_5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml.vb#2_5)]

    <span data-ttu-id="1881a-192">Und wie die folgenden für **ExpenseReportPage**:</span><span class="sxs-lookup"><span data-stu-id="1881a-192">And like the following for **ExpenseReportPage**:</span></span>

    [!code-csharp[ExpenseIt#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml.cs#5)]

    [!code-vb[ExpenseIt#5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml.vb#5)]

1. <span data-ttu-id="1881a-193">Fügen Sie dem Projekt ein Bild mit dem Namen *watermark.png* hinzu.</span><span class="sxs-lookup"><span data-stu-id="1881a-193">Add an image named *watermark.png* to the project.</span></span> <span data-ttu-id="1881a-194">Sie können Ein eigenes Image erstellen, die Datei aus dem Beispielcode kopieren oder aus dem [Microsoft/WPF-Samples](https://raw.githubusercontent.com/microsoft/WPF-Samples/master/Getting%20Started/WalkthroughFirstWPFApp/csharp/watermark.png) GitHub-Repository abrufen.</span><span class="sxs-lookup"><span data-stu-id="1881a-194">You can create your own image, copy the file from the sample code, or get it from the [microsoft/WPF-Samples](https://raw.githubusercontent.com/microsoft/WPF-Samples/master/Getting%20Started/WalkthroughFirstWPFApp/csharp/watermark.png) GitHub repository.</span></span>

    1. <span data-ttu-id="1881a-195">Klicken Sie mit der rechten Maustaste auf den Projektknoten, und wählen Sie**Vorhandenes Element** **hinzufügen** > aus , oder drücken Sie **Umschalttaste**+**Alt**+**A**.</span><span class="sxs-lookup"><span data-stu-id="1881a-195">Right-click on the project node and select **Add** > **Existing Item**, or press **Shift**+**Alt**+**A**.</span></span>

    2. <span data-ttu-id="1881a-196">Legen Sie im Dialogfeld **VorhandeneElemente hinzufügen** den Dateifilter auf **Alle Dateien** oder **Bilddateien**fest, navigieren Sie zu der Bilddatei, die Sie verwenden möchten, und wählen Sie dann **Hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="1881a-196">In the **Add Existing Item** dialog, set the file filter to either **All Files** or **Image Files**, browse to the image file you want to use, and then select **Add**.</span></span>

## <a name="build-and-run-the-application"></a><span data-ttu-id="1881a-197">Erstellen und Ausführen der Anwendung</span><span class="sxs-lookup"><span data-stu-id="1881a-197">Build and run the application</span></span>

1. <span data-ttu-id="1881a-198">Um die Anwendung zu erstellen und auszuführen, drücken Sie **F5** oder wählen Sie **Debuggen** im **Debug-Menü** starten aus.</span><span class="sxs-lookup"><span data-stu-id="1881a-198">To build and run the application, press **F5** or select **Start Debugging** from the **Debug** menu.</span></span>

    <span data-ttu-id="1881a-199">Die folgende Abbildung zeigt <xref:System.Windows.Navigation.NavigationWindow> die Anwendung mit den Schaltflächen:</span><span class="sxs-lookup"><span data-stu-id="1881a-199">The following illustration shows the application with the <xref:System.Windows.Navigation.NavigationWindow> buttons:</span></span>

    ![Anwendung, nachdem Sie sie erstellt und ausgeführt haben.](./media/walkthrough-my-first-wpf-desktop-application/build-run-application.png)

2. <span data-ttu-id="1881a-201">Schließen Sie die Anwendung, um zu Visual Studio zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="1881a-201">Close the application to return to Visual Studio.</span></span>

## <a name="create-the-layout"></a><span data-ttu-id="1881a-202">Erstellen des Layouts</span><span class="sxs-lookup"><span data-stu-id="1881a-202">Create the layout</span></span>

<span data-ttu-id="1881a-203">Layout bietet eine geordnete Möglichkeit zum Platzieren von UI-Elementen und verwaltet auch die Größe und Position dieser Elemente, wenn die Größe einer Benutzeroberfläche geändert wird.</span><span class="sxs-lookup"><span data-stu-id="1881a-203">Layout provides an ordered way to place UI elements, and also manages the size and position of those elements when a UI is resized.</span></span> <span data-ttu-id="1881a-204">In der Regel erstellen Sie Layout mit einem der folgenden Layoutsteuerelemente:</span><span class="sxs-lookup"><span data-stu-id="1881a-204">You typically create a layout with one of the following layout controls:</span></span>

- <span data-ttu-id="1881a-205"><xref:System.Windows.Controls.Canvas>- Definiert einen Bereich, innerhalb dem Sie untergeordnete Elemente explizit positionieren können, indem Sie Koordinaten verwenden, die relativ zum Canvas-Bereich sind.</span><span class="sxs-lookup"><span data-stu-id="1881a-205"><xref:System.Windows.Controls.Canvas> - Defines an area within which you can explicitly position child elements by using coordinates that are relative to the Canvas area.</span></span>
- <span data-ttu-id="1881a-206"><xref:System.Windows.Controls.DockPanel>- Definiert einen Bereich, in dem Sie untergeordnete Elemente entweder horizontal oder vertikal relativ zueinander anordnen können.</span><span class="sxs-lookup"><span data-stu-id="1881a-206"><xref:System.Windows.Controls.DockPanel> - Defines an area where you can arrange child elements either horizontally or vertically, relative to each other.</span></span>
- <span data-ttu-id="1881a-207"><xref:System.Windows.Controls.Grid>- Definiert einen flexiblen Rasterbereich, der aus Spalten und Zeilen besteht.</span><span class="sxs-lookup"><span data-stu-id="1881a-207"><xref:System.Windows.Controls.Grid> - Defines a flexible grid area that consists of columns and rows.</span></span>
- <span data-ttu-id="1881a-208"><xref:System.Windows.Controls.StackPanel>- Ordnet untergeordnete Elemente in eine einzelne Linie an, die horizontal oder vertikal ausgerichtet werden kann.</span><span class="sxs-lookup"><span data-stu-id="1881a-208"><xref:System.Windows.Controls.StackPanel> - Arranges child elements into a single line that can be oriented horizontally or vertically.</span></span>
- <span data-ttu-id="1881a-209"><xref:System.Windows.Controls.VirtualizingStackPanel>- Ordnet Inhalte auf einer einzigen Linie an, die entweder horizontal oder vertikal ausgerichtet ist.</span><span class="sxs-lookup"><span data-stu-id="1881a-209"><xref:System.Windows.Controls.VirtualizingStackPanel> - Arranges and virtualizes content on a single line that is oriented either horizontally or vertically.</span></span>
- <span data-ttu-id="1881a-210"><xref:System.Windows.Controls.WrapPanel>- Positioniert untergeordnete Elemente in sequenzieller Position von links nach rechts, indem der Inhalt in die nächste Zeile am Rand des enthaltenden Feldes gebrochen wird.</span><span class="sxs-lookup"><span data-stu-id="1881a-210"><xref:System.Windows.Controls.WrapPanel> - Positions child elements in sequential position from left to right, breaking content to the next line at the edge of the containing box.</span></span> <span data-ttu-id="1881a-211">Die nachfolgende Sortierung erfolgt sequenziell von oben nach unten oder von rechts nach links, abhängig vom Wert der Orientation-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="1881a-211">Subsequent ordering happens sequentially from top to bottom or from right to left, depending on the value of the Orientation property.</span></span>

<span data-ttu-id="1881a-212">Jedes dieser Layoutsteuerelemente unterstützt einen bestimmten Layouttyp für seine untergeordneten Elemente.</span><span class="sxs-lookup"><span data-stu-id="1881a-212">Each of these layout controls supports a particular type of layout for its child elements.</span></span> <span data-ttu-id="1881a-213">`ExpenseIt`Seiten können in der Größe geändert werden, und jede Seite enthält Elemente, die horizontal und vertikal neben anderen Elementen angeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="1881a-213">`ExpenseIt` pages can be resized, and each page has elements that are arranged horizontally and vertically alongside other elements.</span></span> <span data-ttu-id="1881a-214">In diesem Beispiel <xref:System.Windows.Controls.Grid> wird der als Layoutelement für die Anwendung verwendet.</span><span class="sxs-lookup"><span data-stu-id="1881a-214">In this example, the <xref:System.Windows.Controls.Grid> is used as  layout element for the application.</span></span>

> [!TIP]
> <span data-ttu-id="1881a-215">Weitere Informationen <xref:System.Windows.Controls.Panel> zu Elementen finden Sie unter [Übersicht der Panels](../controls/panels-overview.md).</span><span class="sxs-lookup"><span data-stu-id="1881a-215">For more information about <xref:System.Windows.Controls.Panel> elements, see [Panels overview](../controls/panels-overview.md).</span></span> <span data-ttu-id="1881a-216">Weitere Informationen zum Layout finden Sie unter [Layout](../advanced/layout.md).</span><span class="sxs-lookup"><span data-stu-id="1881a-216">For more information about layout, see [Layout](../advanced/layout.md).</span></span>

<span data-ttu-id="1881a-217">In diesem Abschnitt erstellen Sie eine einspaltige Tabelle mit drei Zeilen und einem 10-Pixel-Rand, indem Sie Spalten- <xref:System.Windows.Controls.Grid> und Zeilendefinitionen zum in *`ExpenseItHome.xaml`* hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="1881a-217">In this section, you create a single-column table with three rows and a 10-pixel margin by adding column and row definitions to the <xref:System.Windows.Controls.Grid> in *`ExpenseItHome.xaml`*.</span></span>

1. <span data-ttu-id="1881a-218">Legen *`ExpenseItHome.xaml`* Sie <xref:System.Windows.FrameworkElement.Margin%2A> in die <xref:System.Windows.Controls.Grid> Eigenschaft für das Element auf "10,0,10,10" fest, was dem linken, oberen, rechten und unteren Rand entspricht:</span><span class="sxs-lookup"><span data-stu-id="1881a-218">In *`ExpenseItHome.xaml`*, set the <xref:System.Windows.FrameworkElement.Margin%2A> property on the <xref:System.Windows.Controls.Grid> element to "10,0,10,10", which corresponds to left, top, right and bottom margins:</span></span>

   ```xaml
   <Grid Margin="10,0,10,10">
   ```

   > [!TIP]
   > <span data-ttu-id="1881a-219">Sie können die **Margin-Werte** auch im **Eigenschaftenfenster** unter der Kategorie **Layout** festlegen:</span><span class="sxs-lookup"><span data-stu-id="1881a-219">You can also set the **Margin** values in the **Properties** window, under the **Layout** category:</span></span>
   >
   > ![Margin-Werte im Eigenschaftenfenster](./media/properties-margin.png)

2. <span data-ttu-id="1881a-221">Fügen Sie das folgende <xref:System.Windows.Controls.Grid> XAML zwischen den Tags hinzu, um die Zeilen- und Spaltendefinitionen zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="1881a-221">Add the following XAML between the <xref:System.Windows.Controls.Grid> tags to create the row and column definitions:</span></span>

    [!code-xaml[ExpenseIt#8](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#8)]

    <span data-ttu-id="1881a-222">Die <xref:System.Windows.Controls.RowDefinition.Height%2A> Größe von zwei <xref:System.Windows.GridLength.Auto%2A>Zeilen ist auf festgelegt, was bedeutet, dass die Größe der Zeilen basierend auf dem Inhalt in den Zeilen festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="1881a-222">The <xref:System.Windows.Controls.RowDefinition.Height%2A> of two rows is set to <xref:System.Windows.GridLength.Auto%2A>, which means that the rows are sized based on the content in the rows.</span></span> <span data-ttu-id="1881a-223">Die <xref:System.Windows.Controls.RowDefinition.Height%2A> Standardgröße ist <xref:System.Windows.GridUnitType.Star> die Größe, was bedeutet, dass die Zeilenhöhe ein gewichteter Anteil des verfügbaren Speicherplatzes ist.</span><span class="sxs-lookup"><span data-stu-id="1881a-223">The default <xref:System.Windows.Controls.RowDefinition.Height%2A> is <xref:System.Windows.GridUnitType.Star> sizing, which means that the row height is a weighted proportion of the available space.</span></span> <span data-ttu-id="1881a-224">Wenn z. B. <xref:System.Windows.Controls.RowDefinition.Height%2A> zwei Zeilen jeweils eine von "\*" haben, haben sie jeweils eine Höhe, die die Hälfte des verfügbaren Speicherplatzes beträgt.</span><span class="sxs-lookup"><span data-stu-id="1881a-224">For example if two rows each have a <xref:System.Windows.Controls.RowDefinition.Height%2A> of "\*", they each have a height that is half of the available space.</span></span>

    <span data-ttu-id="1881a-225">Sie <xref:System.Windows.Controls.Grid> sollten nun Folgendes XAML enthalten:</span><span class="sxs-lookup"><span data-stu-id="1881a-225">Your <xref:System.Windows.Controls.Grid> should now contain the following XAML:</span></span>

    [!code-xaml[ExpenseIt#9](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#9)]

## <a name="add-controls"></a><span data-ttu-id="1881a-226">Hinzufügen von Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="1881a-226">Add controls</span></span>

<span data-ttu-id="1881a-227">In diesem Abschnitt aktualisieren Sie die Benutzeroberfläche der Homepage, um eine Liste von Personen anzuzeigen, in der Sie eine Person auswählen, um deren Spesenabrechnung anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="1881a-227">In this section, you'll update the home page UI to show a list of people, where you select one person to display their expense report.</span></span> <span data-ttu-id="1881a-228">Steuerelemente sind Benutzeroberflächenobjekte, die Benutzern die Interaktion mit der Anwendung ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="1881a-228">Controls are UI objects that allow users to interact with your application.</span></span> <span data-ttu-id="1881a-229">Weitere Informationen finden Sie unter [Steuerelemente](../controls/index.md).</span><span class="sxs-lookup"><span data-stu-id="1881a-229">For more information, see [Controls](../controls/index.md).</span></span>

<span data-ttu-id="1881a-230">Um diese Benutzeroberfläche zu erstellen, fügen *`ExpenseItHome.xaml`* Sie die folgenden Elemente hinzu:</span><span class="sxs-lookup"><span data-stu-id="1881a-230">To create this UI, you'll add the following elements to *`ExpenseItHome.xaml`*:</span></span>

- <span data-ttu-id="1881a-231">A <xref:System.Windows.Controls.ListBox> (für die Personenliste).</span><span class="sxs-lookup"><span data-stu-id="1881a-231">A <xref:System.Windows.Controls.ListBox> (for the list of people).</span></span>
- <span data-ttu-id="1881a-232">A <xref:System.Windows.Controls.Label> (für den Listenkopf).</span><span class="sxs-lookup"><span data-stu-id="1881a-232">A <xref:System.Windows.Controls.Label> (for the list header).</span></span>
- <span data-ttu-id="1881a-233">A <xref:System.Windows.Controls.Button> (klicken Sie auf , um die Spesenabrechnung für die in der Liste ausgewählte Person anzuzeigen).</span><span class="sxs-lookup"><span data-stu-id="1881a-233">A <xref:System.Windows.Controls.Button> (to click to view the expense report for the person that is selected in the list).</span></span>

<span data-ttu-id="1881a-234">Jedes Steuerelement wird in einer <xref:System.Windows.Controls.Grid> Zeile <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> des durch Festlegen der angefügten Eigenschaft platziert.</span><span class="sxs-lookup"><span data-stu-id="1881a-234">Each control is placed in a row of the <xref:System.Windows.Controls.Grid> by setting the <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> attached property.</span></span> <span data-ttu-id="1881a-235">Weitere Informationen zu angefügten Eigenschaften finden Sie unter [Übersicht über zugeordnete Eigenschaften](../advanced/attached-properties-overview.md).</span><span class="sxs-lookup"><span data-stu-id="1881a-235">For more information about attached properties, see [Attached Properties Overview](../advanced/attached-properties-overview.md).</span></span>

1. <span data-ttu-id="1881a-236">Fügen *`ExpenseItHome.xaml`* Sie in das folgende XAML irgendwo zwischen den <xref:System.Windows.Controls.Grid> Tags hinzu:</span><span class="sxs-lookup"><span data-stu-id="1881a-236">In *`ExpenseItHome.xaml`*, add the following XAML somewhere between the <xref:System.Windows.Controls.Grid> tags:</span></span>

   [!code-xaml[ExpenseIt#10](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt4/ExpenseItHome.xaml#10)]

   > [!TIP]
   > <span data-ttu-id="1881a-237">Sie können die Steuerelemente auch erstellen, indem Sie sie aus dem **Toolbox-Fenster** in das Entwurfsfenster ziehen und dann ihre Eigenschaften im **Eigenschaftenfenster** festlegen.</span><span class="sxs-lookup"><span data-stu-id="1881a-237">You can also create the controls by dragging them from the **Toolbox** window onto the design window, and then setting their properties in the **Properties** window.</span></span>

2. <span data-ttu-id="1881a-238">Erstellen Sie die Anwendung, und führen Sie sie aus.</span><span class="sxs-lookup"><span data-stu-id="1881a-238">Build and run the application.</span></span>

    <span data-ttu-id="1881a-239">Die folgende Abbildung zeigt die steuerelemente, die Sie erstellt haben:</span><span class="sxs-lookup"><span data-stu-id="1881a-239">The following illustration shows the controls you created:</span></span>

![ExpenseIt-Beispiel-Screenshot mit einer Namensliste](./media/walkthrough-my-first-wpf-desktop-application/add-application-controls.png)

## <a name="add-an-image-and-a-title"></a><span data-ttu-id="1881a-241">Hinzufügen eines Bildes und eines Titels</span><span class="sxs-lookup"><span data-stu-id="1881a-241">Add an image and a title</span></span>

<span data-ttu-id="1881a-242">In diesem Abschnitt aktualisieren Sie die Benutzeroberfläche der Homepage mit einem Bild und einem Seitentitel.</span><span class="sxs-lookup"><span data-stu-id="1881a-242">In this section, you'll update the home page UI with an image and a page title.</span></span>

1. <span data-ttu-id="1881a-243">Fügen *`ExpenseItHome.xaml`* Sie in eine <xref:System.Windows.Controls.Grid.ColumnDefinitions%2A> weitere <xref:System.Windows.Controls.ColumnDefinition.Width%2A> Spalte hinzu, die mit einem festen Von 230 Pixel n:</span><span class="sxs-lookup"><span data-stu-id="1881a-243">In *`ExpenseItHome.xaml`*, add another column to the <xref:System.Windows.Controls.Grid.ColumnDefinitions%2A> with a fixed <xref:System.Windows.Controls.ColumnDefinition.Width%2A> of 230 pixels:</span></span>

    [!code-xaml[ExpenseIt#11](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseItHome.xaml?highlight=2#NewColumn)]

2. <span data-ttu-id="1881a-244">Fügen Sie dem <xref:System.Windows.Controls.Grid.RowDefinitions%2A>eine weitere Zeile für insgesamt vier Zeilen hinzu:</span><span class="sxs-lookup"><span data-stu-id="1881a-244">Add another row to the <xref:System.Windows.Controls.Grid.RowDefinitions%2A>, for a total of four rows:</span></span>

    [!code-xaml[ExpenseIt#11b](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseItHome.xaml?highlight=2#NewRows)]

3. <span data-ttu-id="1881a-245">Verschieben Sie die Steuerelemente in <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> die zweite Spalte, indem Sie die Eigenschaft in jedem der drei Steuerelemente (Border, ListBox und Button) auf 1 festlegen.</span><span class="sxs-lookup"><span data-stu-id="1881a-245">Move the controls to the second column by setting the <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> property to 1 in each of the three controls (Border, ListBox, and Button).</span></span>

4. <span data-ttu-id="1881a-246">Verschieben Sie jedes Steuerelement in <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> einer Zeile nach unten, indem Sie den Wert für jedes der drei Steuerelemente (Border, ListBox und Button) und für das Border-Element um 1 erhöhen.</span><span class="sxs-lookup"><span data-stu-id="1881a-246">Move each control down a row by incrementing its <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> value by 1 for each of the three controls (Border, ListBox, and Button) and for the Border element.</span></span>

   <span data-ttu-id="1881a-247">Das XAML für die drei Steuerelemente sieht nun wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="1881a-247">The XAML for the three controls now looks like the following:</span></span>

    [!code-xaml[ExpenseIt#12](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#12)]

5. <span data-ttu-id="1881a-248">Legen <xref:System.Windows.Controls.Panel.Background%2A?displayProperty=nameWithType> Sie die Eigenschaft auf die *Bilddatei watermark.png* fest, `<Grid>` `</Grid>` indem Sie das folgende XAML an einer beliebigen Stelle zwischen den und-Tags hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="1881a-248">Set the <xref:System.Windows.Controls.Panel.Background%2A?displayProperty=nameWithType> property to the *watermark.png* image file, by adding the following XAML anywhere between the `<Grid>` and `</Grid>` tags:</span></span>

    [!code-xaml[ExpenseIt#14](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#14)]

6. <span data-ttu-id="1881a-249">Fügen <xref:System.Windows.Controls.Border> Sie vor <xref:System.Windows.Controls.Label> dem Element eine mit dem Inhalt "Spesenabrechnung anzeigen" hinzu.</span><span class="sxs-lookup"><span data-stu-id="1881a-249">Before the <xref:System.Windows.Controls.Border> element, add a <xref:System.Windows.Controls.Label> with the content "View Expense Report".</span></span> <span data-ttu-id="1881a-250">Diese Bezeichnung ist der Titel der Seite.</span><span class="sxs-lookup"><span data-stu-id="1881a-250">This label is the title of the page.</span></span>

    [!code-xaml[ExpenseIt#13](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#13)]

7. <span data-ttu-id="1881a-251">Erstellen Sie die Anwendung, und führen Sie sie aus.</span><span class="sxs-lookup"><span data-stu-id="1881a-251">Build and run the application.</span></span>

<span data-ttu-id="1881a-252">Die folgende Abbildung zeigt die Ergebnisse dessen, was Sie gerade hinzugefügt haben:</span><span class="sxs-lookup"><span data-stu-id="1881a-252">The following illustration shows the results of what you just added:</span></span>

![ExpenseIt-Beispiel-Screenshot mit dem neuen Bildhintergrund und Demseitentitel](./media/walkthrough-my-first-wpf-desktop-application/add-application-image-title.png)

## <a name="add-code-to-handle-events"></a><span data-ttu-id="1881a-254">Hinzufügen von Code zum Behandeln von Ereignissen</span><span class="sxs-lookup"><span data-stu-id="1881a-254">Add code to handle events</span></span>

1. <span data-ttu-id="1881a-255">Fügen *`ExpenseItHome.xaml`* Sie <xref:System.Windows.Controls.Primitives.ButtonBase.Click> dem <xref:System.Windows.Controls.Button> Element einen Ereignishandler hinzu.</span><span class="sxs-lookup"><span data-stu-id="1881a-255">In *`ExpenseItHome.xaml`*, add a <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler to the <xref:System.Windows.Controls.Button> element.</span></span> <span data-ttu-id="1881a-256">Weitere Informationen finden Sie unter [Gewusst wie: Erstellen eines einfachen Ereignishandlers](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb675300(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="1881a-256">For more information, see [How to: Create a simple event handler](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb675300(v=vs.100)).</span></span>

    [!code-xaml[ExpenseIt#15](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml#15)]

2. <span data-ttu-id="1881a-257">Öffnen *`ExpenseItHome.xaml.vb`* *`ExpenseItHome.xaml.cs`* oder .</span><span class="sxs-lookup"><span data-stu-id="1881a-257">Open *`ExpenseItHome.xaml.vb`* or *`ExpenseItHome.xaml.cs`*.</span></span>

3. <span data-ttu-id="1881a-258">Fügen Sie der `ExpenseItHome` Klasse den folgenden Code hinzu, um einen Schaltflächenklick-Ereignishandler hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="1881a-258">Add the following code to the `ExpenseItHome` class to add a button click event handler.</span></span> <span data-ttu-id="1881a-259">Der Ereignishandler öffnet die **Seite ExpenseReportPage.**</span><span class="sxs-lookup"><span data-stu-id="1881a-259">The event handler opens the **ExpenseReportPage** page.</span></span>

    [!code-csharp[ExpenseIt#16](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml.cs#16)]
    [!code-vb[ExpenseIt#16](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt6/ExpenseItHome.xaml.vb#16)]

## <a name="create-the-ui-for-expensereportpage"></a><span data-ttu-id="1881a-260">Erstellen der Benutzeroberfläche für ExpenseReportPage</span><span class="sxs-lookup"><span data-stu-id="1881a-260">Create the UI for ExpenseReportPage</span></span>

<span data-ttu-id="1881a-261">*ExpenseReportPage.xaml* zeigt die Spesenabrechnung für die **`ExpenseItHome`** Person an, die auf der Seite ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="1881a-261">*ExpenseReportPage.xaml* displays the expense report for the person that's selected on the **`ExpenseItHome`** page.</span></span> <span data-ttu-id="1881a-262">In diesem Abschnitt erstellen Sie die Benutzeroberfläche für **ExpenseReportPage**.</span><span class="sxs-lookup"><span data-stu-id="1881a-262">In this section, you'll create the UI for **ExpenseReportPage**.</span></span> <span data-ttu-id="1881a-263">Außerdem fügen Sie den verschiedenen UI-Elementen Hintergrund- und Füllfarben hinzu.</span><span class="sxs-lookup"><span data-stu-id="1881a-263">You'll also add background and fill colors to the various UI elements.</span></span>

1. <span data-ttu-id="1881a-264">Öffnen Sie *ExpenseReportPage.xaml*.</span><span class="sxs-lookup"><span data-stu-id="1881a-264">Open *ExpenseReportPage.xaml*.</span></span>

2. <span data-ttu-id="1881a-265">Fügen Sie das folgende <xref:System.Windows.Controls.Grid> XAML zwischen den Tags hinzu:</span><span class="sxs-lookup"><span data-stu-id="1881a-265">Add the following XAML between the <xref:System.Windows.Controls.Grid> tags:</span></span>

    [!code-xaml[ExpenseIt#17](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseReportPage.xaml#17)]

    <span data-ttu-id="1881a-266">Diese Benutzeroberfläche *`ExpenseItHome.xaml`* ähnelt , außer dass die <xref:System.Windows.Controls.DataGrid>Berichtsdaten in einer angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="1881a-266">This UI is similar to *`ExpenseItHome.xaml`*, except the report data is displayed in a <xref:System.Windows.Controls.DataGrid>.</span></span>

3. <span data-ttu-id="1881a-267">Erstellen Sie die Anwendung, und führen Sie sie aus.</span><span class="sxs-lookup"><span data-stu-id="1881a-267">Build and run the application.</span></span>

4. <span data-ttu-id="1881a-268">Wählen Sie die Schaltfläche **Ansicht** aus.</span><span class="sxs-lookup"><span data-stu-id="1881a-268">Select the **View** button.</span></span>

    <span data-ttu-id="1881a-269">Die Spesenabrechnungsseite wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1881a-269">The expense report page appears.</span></span> <span data-ttu-id="1881a-270">Beachten Sie auch, dass die Zurück-Navigationstaste aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="1881a-270">Also notice that the back navigation button is enabled.</span></span>

<span data-ttu-id="1881a-271">Die folgende Abbildung zeigt die UI-Elemente, die *ExpenseReportPage.xaml*hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="1881a-271">The following illustration shows the UI elements added to *ExpenseReportPage.xaml*.</span></span>

![ExpenseIt-Beispiel-Screenshot mit der ui, die gerade für die ExpenseReportPage erstellt wurde.](./media/walkthrough-my-first-wpf-desktop-application/create-application-ui.png)

## <a name="style-controls"></a><span data-ttu-id="1881a-273">Stilsteuerelemente</span><span class="sxs-lookup"><span data-stu-id="1881a-273">Style controls</span></span>

<span data-ttu-id="1881a-274">Das Erscheinungsbild verschiedener Elemente ist häufig für alle Elemente desselben Typs in einer Benutzeroberfläche gleich.</span><span class="sxs-lookup"><span data-stu-id="1881a-274">The appearance of various elements is often the same for all elements of the same type in a UI.</span></span> <span data-ttu-id="1881a-275">Die Benutzeroberfläche verwendet [Stile,](../controls/styling-and-templating.md) um Darstellungen über mehrere Elemente hinweg wiederverwendbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="1881a-275">UI uses [styles](../controls/styling-and-templating.md) to make appearances reusable across multiple elements.</span></span> <span data-ttu-id="1881a-276">Die Wiederverwendbarkeit von Stilen trägt zur Vereinfachung der XAML-Erstellung und -Verwaltung bei.</span><span class="sxs-lookup"><span data-stu-id="1881a-276">The reusability of styles helps to simplify XAML creation and management.</span></span> <span data-ttu-id="1881a-277">Dieser Abschnitt ersetzt die Attribute pro Element, die in den vorherigen Schritten mit Stilen definiert wurden.</span><span class="sxs-lookup"><span data-stu-id="1881a-277">This section replaces the per-element attributes that were defined in previous steps with styles.</span></span>

1. <span data-ttu-id="1881a-278">Öffnen Sie *Application.xaml* oder *App.xaml*.</span><span class="sxs-lookup"><span data-stu-id="1881a-278">Open *Application.xaml* or *App.xaml*.</span></span>

2. <span data-ttu-id="1881a-279">Fügen Sie das folgende <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> XAML zwischen den Tags hinzu:</span><span class="sxs-lookup"><span data-stu-id="1881a-279">Add the following XAML between the <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> tags:</span></span>

    [!code-xaml[ExpenseIt#18](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/App.xaml#18)]

    <span data-ttu-id="1881a-280">Durch diese XAML werden folgende Stile hinzugefügt:</span><span class="sxs-lookup"><span data-stu-id="1881a-280">This XAML adds the following styles:</span></span>

    - <span data-ttu-id="1881a-281">`headerTextStyle`: Zum Formatieren des Seitentitels für <xref:System.Windows.Controls.Label>.</span><span class="sxs-lookup"><span data-stu-id="1881a-281">`headerTextStyle`: To format the page title <xref:System.Windows.Controls.Label>.</span></span>

    - <span data-ttu-id="1881a-282">`labelStyle`: Zum Formatieren der <xref:System.Windows.Controls.Label> -Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="1881a-282">`labelStyle`: To format the <xref:System.Windows.Controls.Label> controls.</span></span>

    - <span data-ttu-id="1881a-283">`columnHeaderStyle`: Zum Formatieren von <xref:System.Windows.Controls.Primitives.DataGridColumnHeader>.</span><span class="sxs-lookup"><span data-stu-id="1881a-283">`columnHeaderStyle`: To format the <xref:System.Windows.Controls.Primitives.DataGridColumnHeader>.</span></span>

    - <span data-ttu-id="1881a-284">`listHeaderStyle`: Zum Formatieren der <xref:System.Windows.Controls.Border> -Kopfzeilensteuerelemente.</span><span class="sxs-lookup"><span data-stu-id="1881a-284">`listHeaderStyle`: To format the list header <xref:System.Windows.Controls.Border> controls.</span></span>

    - <span data-ttu-id="1881a-285">`listHeaderTextStyle`: So formatieren <xref:System.Windows.Controls.Label>Sie den Listenkopf .</span><span class="sxs-lookup"><span data-stu-id="1881a-285">`listHeaderTextStyle`: To format the list header <xref:System.Windows.Controls.Label>.</span></span>

    - <span data-ttu-id="1881a-286">`buttonStyle`: Formatieren <xref:System.Windows.Controls.Button> `ExpenseItHome.xaml`der on .</span><span class="sxs-lookup"><span data-stu-id="1881a-286">`buttonStyle`: To format the <xref:System.Windows.Controls.Button> on `ExpenseItHome.xaml`.</span></span>

    <span data-ttu-id="1881a-287">Beachten Sie, dass es sich <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> bei den Stilen um Ressourcen und untergeordnete Elemente des Eigenschaftselements handelt.</span><span class="sxs-lookup"><span data-stu-id="1881a-287">Notice that the styles are resources and children of the <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> property element.</span></span> <span data-ttu-id="1881a-288">An diesem Speicherort werden die Stile auf alle Elemente in einer Anwendung angewendet.</span><span class="sxs-lookup"><span data-stu-id="1881a-288">In this location, the styles are applied to all the elements in an application.</span></span> <span data-ttu-id="1881a-289">Ein Beispiel für die Verwendung von Ressourcen in einer .NET-App finden Sie unter [Verwenden von Anwendungsressourcen](../advanced/how-to-use-application-resources.md).</span><span class="sxs-lookup"><span data-stu-id="1881a-289">For an example of using resources in a .NET app, see [Use Application Resources](../advanced/how-to-use-application-resources.md).</span></span>

3. <span data-ttu-id="1881a-290">Ersetzen *`ExpenseItHome.xaml`* Sie in <xref:System.Windows.Controls.Grid> alles zwischen den Elementen durch das folgende XAML:</span><span class="sxs-lookup"><span data-stu-id="1881a-290">In *`ExpenseItHome.xaml`*, replace everything between the <xref:System.Windows.Controls.Grid> elements with the following XAML:</span></span>

    [!code-xaml[ExpenseIt#19](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseItHome.xaml#19)]

    <span data-ttu-id="1881a-291">Eigenschaften wie <xref:System.Windows.VerticalAlignment> und <xref:System.Windows.Media.FontFamily> , die die Darstellung der einzelnen Steuerelemente definieren, werden entfernt und ersetzt, indem die Stile angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="1881a-291">The properties such as <xref:System.Windows.VerticalAlignment> and <xref:System.Windows.Media.FontFamily> that define the look of each control are removed and replaced by applying the styles.</span></span> <span data-ttu-id="1881a-292">Die `headerTextStyle` wird z. B. auf den <xref:System.Windows.Controls.Label>"Spesenbericht anzeigen" angewendet.</span><span class="sxs-lookup"><span data-stu-id="1881a-292">For example, the `headerTextStyle` is applied to the "View Expense Report" <xref:System.Windows.Controls.Label>.</span></span>

4. <span data-ttu-id="1881a-293">Öffnen Sie *ExpenseReportPage.xaml*.</span><span class="sxs-lookup"><span data-stu-id="1881a-293">Open *ExpenseReportPage.xaml*.</span></span>

5. <span data-ttu-id="1881a-294">Ersetzen Sie <xref:System.Windows.Controls.Grid> alles zwischen den Elementen durch das folgende XAML:</span><span class="sxs-lookup"><span data-stu-id="1881a-294">Replace everything between the <xref:System.Windows.Controls.Grid> elements with the following XAML:</span></span>

    [!code-xaml[ExpenseIt#20](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseReportPage.xaml#20)]

    <span data-ttu-id="1881a-295">Dieses XAML fügt <xref:System.Windows.Controls.Label> Stile <xref:System.Windows.Controls.Border> zu den und Elementen hinzu.</span><span class="sxs-lookup"><span data-stu-id="1881a-295">This XAML adds styles to the <xref:System.Windows.Controls.Label> and <xref:System.Windows.Controls.Border> elements.</span></span>

6. <span data-ttu-id="1881a-296">Erstellen Sie die Anwendung, und führen Sie sie aus.</span><span class="sxs-lookup"><span data-stu-id="1881a-296">Build and run the application.</span></span> <span data-ttu-id="1881a-297">Die Fensterdarstellung ist die gleiche wie zuvor.</span><span class="sxs-lookup"><span data-stu-id="1881a-297">The window appearance is the same as previously.</span></span>

    ![ExpenseIt-Beispiel-Screenshot mit der gleichen Erscheinung wie im letzten Abschnitt.](./media/walkthrough-my-first-wpf-desktop-application/create-application-ui.png)

7. <span data-ttu-id="1881a-299">Schließen Sie die Anwendung, um zu Visual Studio zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="1881a-299">Close the application to return to Visual Studio.</span></span>

## <a name="bind-data-to-a-control"></a><span data-ttu-id="1881a-300">Binden von Daten an ein Steuerelement</span><span class="sxs-lookup"><span data-stu-id="1881a-300">Bind data to a control</span></span>

<span data-ttu-id="1881a-301">In diesem Abschnitt erstellen Sie die XML-Daten, die an verschiedene Steuerelemente gebunden sind.</span><span class="sxs-lookup"><span data-stu-id="1881a-301">In this section, you'll create the XML data that is bound to various controls.</span></span>

1. <span data-ttu-id="1881a-302">Fügen *`ExpenseItHome.xaml`* Sie nach <xref:System.Windows.Controls.Grid> dem Öffnenelement das folgende XAML hinzu, um ein <xref:System.Windows.Data.XmlDataProvider> zu erstellen, das die Daten für jede Person enthält:</span><span class="sxs-lookup"><span data-stu-id="1881a-302">In *`ExpenseItHome.xaml`*, after the opening <xref:System.Windows.Controls.Grid> element, add the following XAML to create an <xref:System.Windows.Data.XmlDataProvider> that contains the data for each person:</span></span>

    [!code-xaml[ExpenseIt#23](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml?range=13,16-40,49)]

    <span data-ttu-id="1881a-303">Die Daten werden <xref:System.Windows.Controls.Grid> als Ressource erstellt.</span><span class="sxs-lookup"><span data-stu-id="1881a-303">The data is created as a <xref:System.Windows.Controls.Grid> resource.</span></span> <span data-ttu-id="1881a-304">Normalerweise würden diese Daten als Datei geladen werden, aber der Einfachheit halber werden die Daten inline hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="1881a-304">Normally this data would be loaded as a file, but for simplicity the data is added inline.</span></span>

2. <span data-ttu-id="1881a-305">Fügen `<Grid.Resources>` Sie innerhalb des `<xref:System.Windows.DataTemplate>` Elements das folgende Element hinzu, <xref:System.Windows.Controls.ListBox>das definiert, wie die Daten im nach dem `<XmlDataProvider>` Element angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="1881a-305">Within the `<Grid.Resources>` element, add the following `<xref:System.Windows.DataTemplate>` element, which defines how to display the data in the <xref:System.Windows.Controls.ListBox>, after the `<XmlDataProvider>` element:</span></span>

    [!code-xaml[ExpenseIt#24](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml?range=13,43-46,49)]

    <span data-ttu-id="1881a-306">Weitere Informationen zu Datenvorlagen finden Sie unter Übersicht über die [Datenbearbeitung](../data/data-templating-overview.md).</span><span class="sxs-lookup"><span data-stu-id="1881a-306">For more information about data templates, see [Data templating overview](../data/data-templating-overview.md).</span></span>

3. <span data-ttu-id="1881a-307">Ersetzen Sie <xref:System.Windows.Controls.ListBox> das vorhandene durch das folgende XAML:</span><span class="sxs-lookup"><span data-stu-id="1881a-307">Replace the existing <xref:System.Windows.Controls.ListBox> with the following XAML:</span></span>

    [!code-xaml[ExpenseIt#25](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#25)]

    <span data-ttu-id="1881a-308">Dieser XAML bindet <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> die <xref:System.Windows.Controls.ListBox> Eigenschaft des an die Datenquelle und <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>wendet die Datenvorlage als .</span><span class="sxs-lookup"><span data-stu-id="1881a-308">This XAML binds the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> property of the <xref:System.Windows.Controls.ListBox> to the data source and applies the data template as the <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>.</span></span>

## <a name="connect-data-to-controls"></a><span data-ttu-id="1881a-309">Verbinden von Daten mit Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="1881a-309">Connect data to controls</span></span>

<span data-ttu-id="1881a-310">Als Nächstes fügen Sie Code hinzu, um den **`ExpenseItHome`** auf der Seite ausgewählten Namen abzurufen und an den Konstruktor von **ExpenseReportPage**zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="1881a-310">Next, you'll add code to retrieve the name that's selected on the **`ExpenseItHome`** page and pass it to the constructor of **ExpenseReportPage**.</span></span> <span data-ttu-id="1881a-311">**ExpenseReportPage** legt den Datenkontext mit dem übergebenen Element fest, an das die in *ExpenseReportPage.xaml* definierten Steuerelemente gebunden sind.</span><span class="sxs-lookup"><span data-stu-id="1881a-311">**ExpenseReportPage** sets its data context with the passed item, which is what the controls defined in *ExpenseReportPage.xaml* bind to.</span></span>

1. <span data-ttu-id="1881a-312">Öffnen Sie *ExpenseReportPage.xaml.vb* oder *ExpenseReportPage.xaml.cs*.</span><span class="sxs-lookup"><span data-stu-id="1881a-312">Open *ExpenseReportPage.xaml.vb* or *ExpenseReportPage.xaml.cs*.</span></span>

2. <span data-ttu-id="1881a-313">Fügen Sie einen Konstruktor hinzu, der ein Objekt akzeptiert, damit Sie die Spesenabrechnungsdaten der ausgewählten Person übergeben können.</span><span class="sxs-lookup"><span data-stu-id="1881a-313">Add a constructor that takes an object so you can pass the expense report data of the selected person.</span></span>

    [!code-csharp[ExpenseIt#26](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseReportPage.xaml.cs#26)]
    [!code-vb[ExpenseIt#26](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseReportPage.xaml.vb#26)]

3. <span data-ttu-id="1881a-314">Öffnen *`ExpenseItHome.xaml.vb`* *`ExpenseItHome.xaml.cs`* oder .</span><span class="sxs-lookup"><span data-stu-id="1881a-314">Open *`ExpenseItHome.xaml.vb`* or *`ExpenseItHome.xaml.cs`*.</span></span>

4. <span data-ttu-id="1881a-315">Ändern <xref:System.Windows.Controls.Primitives.ButtonBase.Click> Sie den Ereignishandler, um den neuen Konstruktor aufzurufen, der die Spesenabrechnungsdaten der ausgewählten Person übergibt.</span><span class="sxs-lookup"><span data-stu-id="1881a-315">Change the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler to call the new constructor passing the expense report data of the selected person.</span></span>

    [!code-csharp[ExpenseIt#27](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml.cs#27)]
    [!code-vb[ExpenseIt#27](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseItHome.xaml.vb#27)]

## <a name="style-data-with-data-templates"></a><span data-ttu-id="1881a-316">Formatieren von Daten mit Datenvorlagen</span><span class="sxs-lookup"><span data-stu-id="1881a-316">Style data with data templates</span></span>

<span data-ttu-id="1881a-317">In diesem Abschnitt aktualisieren Sie die Benutzeroberfläche für jedes Element in den datengebundenen Listen mithilfe von Datenvorlagen.</span><span class="sxs-lookup"><span data-stu-id="1881a-317">In this section, you'll update the UI for each item in the data-bound lists by using data templates.</span></span>

1. <span data-ttu-id="1881a-318">Öffnen Sie *ExpenseReportPage.xaml*.</span><span class="sxs-lookup"><span data-stu-id="1881a-318">Open *ExpenseReportPage.xaml*.</span></span>

2. <span data-ttu-id="1881a-319">Binden Sie den Inhalt der Elemente <xref:System.Windows.Controls.Label> "Name" und "Department" an die entsprechende Datenquelleneigenschaft.</span><span class="sxs-lookup"><span data-stu-id="1881a-319">Bind the content of the "Name" and "Department" <xref:System.Windows.Controls.Label> elements to the appropriate data source property.</span></span> <span data-ttu-id="1881a-320">Weitere Informationen zur Datenbindung finden Sie unter [Datenbindungsübersicht](../../../desktop-wpf/data/data-binding-overview.md).</span><span class="sxs-lookup"><span data-stu-id="1881a-320">For more information about data binding, see [Data binding overview](../../../desktop-wpf/data/data-binding-overview.md).</span></span>

    [!code-xaml[ExpenseIt#31](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#31)]

3. <span data-ttu-id="1881a-321">Fügen Sie <xref:System.Windows.Controls.Grid> nach dem Öffnenelement die folgenden Datenvorlagen hinzu, die definieren, wie die Spesenabrechnungsdaten angezeigt werden sollen:</span><span class="sxs-lookup"><span data-stu-id="1881a-321">After the opening <xref:System.Windows.Controls.Grid> element, add the following data templates, which define how to display the expense report data:</span></span>

    [!code-xaml[ExpenseIt#30](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#30)]

4. <span data-ttu-id="1881a-322">Ersetzen <xref:System.Windows.Controls.DataGridTextColumn> Sie <xref:System.Windows.Controls.DataGridTemplateColumn> die <xref:System.Windows.Controls.DataGrid> Elemente durch das Element, und wenden Sie die Vorlagen darauf an.</span><span class="sxs-lookup"><span data-stu-id="1881a-322">Replace the <xref:System.Windows.Controls.DataGridTextColumn> elements with <xref:System.Windows.Controls.DataGridTemplateColumn> under the <xref:System.Windows.Controls.DataGrid> element and apply the templates to them.</span></span>

    [!code-xaml[ExpenseIt#32](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#32)]

5. <span data-ttu-id="1881a-323">Erstellen Sie die Anwendung, und führen Sie sie aus.</span><span class="sxs-lookup"><span data-stu-id="1881a-323">Build and run the application.</span></span>

6. <span data-ttu-id="1881a-324">Wählen Sie eine Person aus, und wählen Sie dann die Schaltfläche **Ansicht** aus.</span><span class="sxs-lookup"><span data-stu-id="1881a-324">Select a person and then select the **View** button.</span></span>

<span data-ttu-id="1881a-325">Die folgende Abbildung zeigt `ExpenseIt` beide Seiten der Anwendung mit Steuerelementen, Layout, Stilen, Datenbindung und Datenvorlagen:</span><span class="sxs-lookup"><span data-stu-id="1881a-325">The following illustration shows both pages of the `ExpenseIt` application with controls, layout, styles, data binding, and data templates applied:</span></span>

![Beide Seiten der App mit der Namensliste und einer Spesenabrechnung.](./media/walkthrough-my-first-wpf-desktop-application/application-data-templates.png)

> [!NOTE]
> <span data-ttu-id="1881a-327">Dieses Beispiel veranschaulicht ein bestimmtes Feature von WPF und befolgt nicht alle bewährten Methoden für Dinge wie Sicherheit, Lokalisierung und Zugänglichkeit.</span><span class="sxs-lookup"><span data-stu-id="1881a-327">This sample demonstrates a specific feature of WPF and doesn't follow all best practices for things like security, localization, and accessibility.</span></span> <span data-ttu-id="1881a-328">Eine umfassende Abdeckung von WPF und den Best Practices für die .NET-App-Entwicklung finden Sie in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="1881a-328">For comprehensive coverage of WPF and the .NET app development best practices, see the following topics:</span></span>
>
> - [<span data-ttu-id="1881a-329">Zugriff</span><span class="sxs-lookup"><span data-stu-id="1881a-329">Accessibility</span></span>](../../ui-automation/accessibility-best-practices.md)
> - [<span data-ttu-id="1881a-330">Security</span><span class="sxs-lookup"><span data-stu-id="1881a-330">Security</span></span>](../security-wpf.md)
> - [<span data-ttu-id="1881a-331">Übersicht über WPF-Globalisierung und -Lokalisierung</span><span class="sxs-lookup"><span data-stu-id="1881a-331">WPF globalization and localization</span></span>](../advanced/wpf-globalization-and-localization-overview.md)
> - [<span data-ttu-id="1881a-332">WPF-Leistung</span><span class="sxs-lookup"><span data-stu-id="1881a-332">WPF performance</span></span>](../advanced/optimizing-wpf-application-performance.md)

## <a name="next-steps"></a><span data-ttu-id="1881a-333">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="1881a-333">Next steps</span></span>

<span data-ttu-id="1881a-334">In dieser exemplarischen Vorgehensweise haben Sie eine Reihe von Techniken zum Erstellen einer Benutzeroberfläche mit Windows Presentation Foundation (WPF) gelernt.</span><span class="sxs-lookup"><span data-stu-id="1881a-334">In this walkthrough you learned a number of techniques for creating a UI using Windows Presentation Foundation (WPF).</span></span> <span data-ttu-id="1881a-335">Sie sollten nun über ein grundlegendes Verständnis der Bausteine einer datengebundenen .NET-App verfügen.</span><span class="sxs-lookup"><span data-stu-id="1881a-335">You should now have a basic understanding of the building blocks of a data-bound .NET app.</span></span> <span data-ttu-id="1881a-336">Weitere Informationen über die WPF-Architektur und -Programmiermodelle finden Sie in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="1881a-336">For more information about the WPF architecture and programming models, see the following topics:</span></span>

- [<span data-ttu-id="1881a-337">WPF-Architektur</span><span class="sxs-lookup"><span data-stu-id="1881a-337">WPF architecture</span></span>](../advanced/wpf-architecture.md)
- [<span data-ttu-id="1881a-338">XAML-Übersicht (WPF)</span><span class="sxs-lookup"><span data-stu-id="1881a-338">XAML overview (WPF)</span></span>](../advanced/xaml-overview-wpf.md)
- [<span data-ttu-id="1881a-339">Überblick über Abhängigkeitseigenschaften</span><span class="sxs-lookup"><span data-stu-id="1881a-339">Dependency properties overview</span></span>](../advanced/dependency-properties-overview.md)
- [<span data-ttu-id="1881a-340">Layout</span><span class="sxs-lookup"><span data-stu-id="1881a-340">Layout</span></span>](../advanced/layout.md)

<span data-ttu-id="1881a-341">Weitere Informationen zum Erstellen von Anwendungen finden Sie in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="1881a-341">For more information about creating applications, see the following topics:</span></span>

- [<span data-ttu-id="1881a-342">Anwendungsentwicklung</span><span class="sxs-lookup"><span data-stu-id="1881a-342">Application development</span></span>](../app-development/index.md)
- [<span data-ttu-id="1881a-343">Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="1881a-343">Controls</span></span>](../controls/index.md)
- [<span data-ttu-id="1881a-344">Übersicht über Datenbindung</span><span class="sxs-lookup"><span data-stu-id="1881a-344">Data binding overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="1881a-345">Grafik und Multimedia</span><span class="sxs-lookup"><span data-stu-id="1881a-345">Graphics and multimedia</span></span>](../graphics-multimedia/index.md)
- [<span data-ttu-id="1881a-346">Dokumente in WPF</span><span class="sxs-lookup"><span data-stu-id="1881a-346">Documents in WPF</span></span>](../advanced/documents-in-wpf.md)

## <a name="see-also"></a><span data-ttu-id="1881a-347">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1881a-347">See also</span></span>

- [<span data-ttu-id="1881a-348">Panel-Übersicht</span><span class="sxs-lookup"><span data-stu-id="1881a-348">Panels overview</span></span>](../controls/panels-overview.md)
- [<span data-ttu-id="1881a-349">Übersicht über die Datenbearbeitbarkeit</span><span class="sxs-lookup"><span data-stu-id="1881a-349">Data templating overview</span></span>](../data/data-templating-overview.md)
- [<span data-ttu-id="1881a-350">Erstellen einer WPF-Anwendung</span><span class="sxs-lookup"><span data-stu-id="1881a-350">Build a WPF application</span></span>](../app-development/building-a-wpf-application-wpf.md)
- [<span data-ttu-id="1881a-351">Stile und Vorlagen</span><span class="sxs-lookup"><span data-stu-id="1881a-351">Styles and templates</span></span>](../controls/styles-and-templates.md)
