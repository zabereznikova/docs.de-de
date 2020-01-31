---
title: 'Exemplarische Vorgehensweise: Datenbindung in Hybridanwendungen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hybrid applications [WPF interoperability]
- data binding [WPF interoperability]
ms.assetid: 18997e71-745a-4425-9c69-2cbce1d8669e
ms.openlocfilehash: 1bb38436049e338ab6033ae3b6370732a457d520
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794224"
---
# <a name="walkthrough-binding-to-data-in-hybrid-applications"></a><span data-ttu-id="6f201-102">Exemplarische Vorgehensweise: Datenbindung in Hybridanwendungen</span><span class="sxs-lookup"><span data-stu-id="6f201-102">Walkthrough: Binding to Data in Hybrid Applications</span></span>

<span data-ttu-id="6f201-103">Das Binden einer Datenquelle an ein Steuerelement ist entscheidend, um Benutzern den Zugriff auf die zugrunde liegenden Daten zu gewähren, unabhängig davon, ob Sie Windows Forms oder [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]verwenden.</span><span class="sxs-lookup"><span data-stu-id="6f201-103">Binding a data source to a control is essential for providing users with access to underlying data, whether you are using Windows Forms or [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span></span> <span data-ttu-id="6f201-104">In dieser exemplarischen Vorgehensweise wird gezeigt, wie Sie die Datenbindung in Hybrid Anwendungen verwenden können, die sowohl Windows Forms als auch [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Steuerelemente enthalten</span><span class="sxs-lookup"><span data-stu-id="6f201-104">This walkthrough shows how you can use data binding in hybrid applications that include both Windows Forms and [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] controls.</span></span>

<span data-ttu-id="6f201-105">In dieser exemplarischen Vorgehensweise werden u. a. folgende Aufgaben veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="6f201-105">Tasks illustrated in this walkthrough include:</span></span>

- <span data-ttu-id="6f201-106">Erstellen des Projekts</span><span class="sxs-lookup"><span data-stu-id="6f201-106">Creating the project.</span></span>

- <span data-ttu-id="6f201-107">Definieren der Datenvorlage.</span><span class="sxs-lookup"><span data-stu-id="6f201-107">Defining the data template.</span></span>

- <span data-ttu-id="6f201-108">Angeben des Formularlayouts.</span><span class="sxs-lookup"><span data-stu-id="6f201-108">Specifying the form layout.</span></span>

- <span data-ttu-id="6f201-109">Angeben von Datenbindungen.</span><span class="sxs-lookup"><span data-stu-id="6f201-109">Specifying data bindings.</span></span>

- <span data-ttu-id="6f201-110">Anzeigen von Daten mithilfe von Interoperation.</span><span class="sxs-lookup"><span data-stu-id="6f201-110">Displaying data by using interoperation.</span></span>

- <span data-ttu-id="6f201-111">Hinzufügen der Datenquelle zum Projekt.</span><span class="sxs-lookup"><span data-stu-id="6f201-111">Adding the data source to the project.</span></span>

- <span data-ttu-id="6f201-112">Bindung an die Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="6f201-112">Binding to the data source.</span></span>

<span data-ttu-id="6f201-113">Eine komplette Code Auflistung der Aufgaben, die in dieser exemplarischen Vorgehensweise veranschaulicht werden, finden Sie unter Beispiel für die [Datenbindung in Hybrid Anwendungen](https://go.microsoft.com/fwlink/?LinkID=159983).</span><span class="sxs-lookup"><span data-stu-id="6f201-113">For a complete code listing of the tasks illustrated in this walkthrough, see [Data Binding in Hybrid Applications Sample](https://go.microsoft.com/fwlink/?LinkID=159983).</span></span>

<span data-ttu-id="6f201-114">Anschließend werden Sie verstehen, welche Rolle Datenbindungsfunktionen bei Hybridanwendungen spielen.</span><span class="sxs-lookup"><span data-stu-id="6f201-114">When you are finished, you will have an understanding of data binding features in hybrid applications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="6f201-115">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="6f201-115">Prerequisites</span></span>

<span data-ttu-id="6f201-116">Zum Durchführen dieser exemplarischen Vorgehensweise benötigen Sie die folgenden Komponenten:</span><span class="sxs-lookup"><span data-stu-id="6f201-116">You need the following components to complete this walkthrough:</span></span>

- <span data-ttu-id="6f201-117">Visual Studio erstellen.</span><span class="sxs-lookup"><span data-stu-id="6f201-117">Visual Studio.</span></span>

- <span data-ttu-id="6f201-118">Zugriff auf die Beispieldatenbank Northwind, die auf Microsoft SQL Server ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="6f201-118">Access to the Northwind sample database running on Microsoft SQL Server.</span></span>

## <a name="creating-the-project"></a><span data-ttu-id="6f201-119">Erstellen des Projekts</span><span class="sxs-lookup"><span data-stu-id="6f201-119">Creating the Project</span></span>

### <a name="to-create-and-set-up-the-project"></a><span data-ttu-id="6f201-120">So erstellen und richten Sie das Projekt ein</span><span class="sxs-lookup"><span data-stu-id="6f201-120">To create and set up the project</span></span>

1. <span data-ttu-id="6f201-121">Erstellen Sie ein WPF-Anwendungsprojekt mit dem Namen `WPFWithWFAndDatabinding`.</span><span class="sxs-lookup"><span data-stu-id="6f201-121">Create a WPF Application project named `WPFWithWFAndDatabinding`.</span></span>

2. <span data-ttu-id="6f201-122">Fügen Sie im Projektmappen-Explorer die Verweise auf die folgenden Assemblys hinzu.</span><span class="sxs-lookup"><span data-stu-id="6f201-122">In Solution Explorer, add references to the following assemblies.</span></span>

    - <span data-ttu-id="6f201-123">WindowsFormsIntegration</span><span class="sxs-lookup"><span data-stu-id="6f201-123">WindowsFormsIntegration</span></span>

    - <span data-ttu-id="6f201-124">System.Windows.Forms</span><span class="sxs-lookup"><span data-stu-id="6f201-124">System.Windows.Forms</span></span>

3. <span data-ttu-id="6f201-125">Öffnen Sie die Datei "MainWindow. XAML" im WPF-Designer.</span><span class="sxs-lookup"><span data-stu-id="6f201-125">Open MainWindow.xaml in the WPF Designer.</span></span>

4. <span data-ttu-id="6f201-126">Fügen Sie im <xref:System.Windows.Window>-Element die folgenden Windows Forms Namespace Zuordnung hinzu.</span><span class="sxs-lookup"><span data-stu-id="6f201-126">In the <xref:System.Windows.Window> element, add the following Windows Forms namespaces mapping.</span></span>

    ```xaml
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"
    ```

5. <span data-ttu-id="6f201-127">Benennen Sie die Standard <xref:System.Windows.Controls.Grid> Element `mainGrid`, indem Sie die <xref:System.Windows.FrameworkElement.Name%2A>-Eigenschaft zuweisen.</span><span class="sxs-lookup"><span data-stu-id="6f201-127">Name the default <xref:System.Windows.Controls.Grid> element `mainGrid` by assigning the <xref:System.Windows.FrameworkElement.Name%2A> property.</span></span>

     [!code-xaml[WPFWithWFAndDatabinding#8](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#8)]

## <a name="defining-the-data-template"></a><span data-ttu-id="6f201-128">Definieren der Datenvorlage</span><span class="sxs-lookup"><span data-stu-id="6f201-128">Defining the Data Template</span></span>

<span data-ttu-id="6f201-129">Die Masterliste der Kunden wird in einem <xref:System.Windows.Controls.ListBox>-Steuerelement angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6f201-129">The master list of customers is displayed in a <xref:System.Windows.Controls.ListBox> control.</span></span> <span data-ttu-id="6f201-130">Im folgenden Codebeispiel wird ein <xref:System.Windows.DataTemplate> Objekt mit dem Namen `ListItemsTemplate` definiert, das die visuelle Struktur des <xref:System.Windows.Controls.ListBox>-Steuer Elements steuert.</span><span class="sxs-lookup"><span data-stu-id="6f201-130">The following code example defines a <xref:System.Windows.DataTemplate> object named `ListItemsTemplate` that controls the visual tree of the <xref:System.Windows.Controls.ListBox> control.</span></span> <span data-ttu-id="6f201-131">Diese <xref:System.Windows.DataTemplate> wird der <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>-Eigenschaft des <xref:System.Windows.Controls.ListBox> Steuer Elements zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="6f201-131">This <xref:System.Windows.DataTemplate> is assigned to the <xref:System.Windows.Controls.ListBox> control's <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> property.</span></span>

### <a name="to-define-the-data-template"></a><span data-ttu-id="6f201-132">Definieren der Datenvorlage</span><span class="sxs-lookup"><span data-stu-id="6f201-132">To define the data template</span></span>

- <span data-ttu-id="6f201-133">Kopieren Sie den folgenden XAML-Code in die Deklaration des <xref:System.Windows.Controls.Grid> Elements.</span><span class="sxs-lookup"><span data-stu-id="6f201-133">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element's declaration.</span></span>

     [!code-xaml[WPFWithWFAndDatabinding#3](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#3)]

## <a name="specifying-the-form-layout"></a><span data-ttu-id="6f201-134">Angeben des Formularlayouts</span><span class="sxs-lookup"><span data-stu-id="6f201-134">Specifying the Form Layout</span></span>

<span data-ttu-id="6f201-135">Das Layout des Formulars wird durch ein Raster mit drei Zeilen und drei Spalten definiert.</span><span class="sxs-lookup"><span data-stu-id="6f201-135">The layout of the form is defined by a grid with three rows and three columns.</span></span> <span data-ttu-id="6f201-136"><xref:System.Windows.Controls.Label>-Steuerelemente werden bereitgestellt, um jede Spalte in der Customers-Tabelle zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="6f201-136"><xref:System.Windows.Controls.Label> controls are provided to identify each column in the Customers table.</span></span>

### <a name="to-set-up-the-grid-layout"></a><span data-ttu-id="6f201-137">Einrichten des Rasterlayouts</span><span class="sxs-lookup"><span data-stu-id="6f201-137">To set up the Grid layout</span></span>

- <span data-ttu-id="6f201-138">Kopieren Sie den folgenden XAML-Code in die Deklaration des <xref:System.Windows.Controls.Grid> Elements.</span><span class="sxs-lookup"><span data-stu-id="6f201-138">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element's declaration.</span></span>

     [!code-xaml[WPFWithWFAndDatabinding#4](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#4)]

### <a name="to-set-up-the-label-controls"></a><span data-ttu-id="6f201-139">Label-Steuerelemente einrichten</span><span class="sxs-lookup"><span data-stu-id="6f201-139">To set up the Label controls</span></span>

- <span data-ttu-id="6f201-140">Kopieren Sie den folgenden XAML-Code in die Deklaration des <xref:System.Windows.Controls.Grid> Elements.</span><span class="sxs-lookup"><span data-stu-id="6f201-140">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element's declaration.</span></span>

     [!code-xaml[WPFWithWFAndDatabinding#5](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#5)]

## <a name="specifying-data-bindings"></a><span data-ttu-id="6f201-141">Angeben von Datenbindungen</span><span class="sxs-lookup"><span data-stu-id="6f201-141">Specifying Data Bindings</span></span>

<span data-ttu-id="6f201-142">Die Masterliste der Kunden wird in einem <xref:System.Windows.Controls.ListBox>-Steuerelement angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6f201-142">The master list of customers is displayed in a <xref:System.Windows.Controls.ListBox> control.</span></span> <span data-ttu-id="6f201-143">Der angefügte `ListItemsTemplate` bindet ein <xref:System.Windows.Controls.TextBlock> Steuerelement an das `ContactName` Feld aus der Datenbank.</span><span class="sxs-lookup"><span data-stu-id="6f201-143">The attached `ListItemsTemplate` binds a <xref:System.Windows.Controls.TextBlock> control to the `ContactName` field from the database.</span></span>

<span data-ttu-id="6f201-144">Die Details der einzelnen Kundendaten Sätze werden in mehreren <xref:System.Windows.Controls.TextBox>-Steuerelementen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6f201-144">The details of each customer record are displayed in several <xref:System.Windows.Controls.TextBox> controls.</span></span>

### <a name="to-specify-data-bindings"></a><span data-ttu-id="6f201-145">Datenbindungen angeben</span><span class="sxs-lookup"><span data-stu-id="6f201-145">To specify data bindings</span></span>

- <span data-ttu-id="6f201-146">Kopieren Sie den folgenden XAML-Code in die Deklaration des <xref:System.Windows.Controls.Grid> Elements.</span><span class="sxs-lookup"><span data-stu-id="6f201-146">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element's declaration.</span></span>

     <span data-ttu-id="6f201-147">Die <xref:System.Windows.Data.Binding>-Klasse bindet die <xref:System.Windows.Controls.TextBox>-Steuerelemente an die entsprechenden Felder in der Datenbank.</span><span class="sxs-lookup"><span data-stu-id="6f201-147">The <xref:System.Windows.Data.Binding> class binds the <xref:System.Windows.Controls.TextBox> controls to the appropriate fields in the database.</span></span>

     [!code-xaml[WPFWithWFAndDatabinding#6](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#6)]

## <a name="displaying-data-by-using-interoperation"></a><span data-ttu-id="6f201-148">Anzeigen von Daten mithilfe von Interoperation</span><span class="sxs-lookup"><span data-stu-id="6f201-148">Displaying Data by Using Interoperation</span></span>

<span data-ttu-id="6f201-149">Die Aufträge, die dem ausgewählten Kunden entsprechen, werden in einem <xref:System.Windows.Forms.DataGridView?displayProperty=nameWithType>-Steuerelement mit dem Namen `dataGridView1`angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6f201-149">The orders corresponding to the selected customer are displayed in a <xref:System.Windows.Forms.DataGridView?displayProperty=nameWithType> control named `dataGridView1`.</span></span> <span data-ttu-id="6f201-150">Das `dataGridView1`-Steuerelement ist an die Datenquelle in der Code-Behind-Datei gebunden.</span><span class="sxs-lookup"><span data-stu-id="6f201-150">The `dataGridView1` control is bound to the data source in the code-behind file.</span></span> <span data-ttu-id="6f201-151">Ein <xref:System.Windows.Forms.Integration.WindowsFormsHost>-Steuerelement ist das übergeordnete Element dieses Windows Forms Steuer Elements.</span><span class="sxs-lookup"><span data-stu-id="6f201-151">A <xref:System.Windows.Forms.Integration.WindowsFormsHost> control is the parent of this Windows Forms control.</span></span>

### <a name="to-display-data-in-the-datagridview-control"></a><span data-ttu-id="6f201-152">Anzeigen von Daten im DataGridView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="6f201-152">To display data in the DataGridView control</span></span>

- <span data-ttu-id="6f201-153">Kopieren Sie den folgenden XAML-Code in die Deklaration des <xref:System.Windows.Controls.Grid> Elements.</span><span class="sxs-lookup"><span data-stu-id="6f201-153">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element's declaration.</span></span>

     [!code-xaml[WPFWithWFAndDatabinding#7](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#7)]

## <a name="adding-the-data-source-to-the-project"></a><span data-ttu-id="6f201-154">Hinzufügen der Datenquelle zum Projekt</span><span class="sxs-lookup"><span data-stu-id="6f201-154">Adding the Data Source to the Project</span></span>

<span data-ttu-id="6f201-155">Mit Visual Studio können Sie Ihrem Projekt problemlos eine Datenquelle hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="6f201-155">With Visual Studio, you can easily add a data source to your project.</span></span> <span data-ttu-id="6f201-156">Bei diesem Vorgang wird dem Projekt ein stark typisiertes Dataset hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="6f201-156">This procedure adds a strongly typed data set to your project.</span></span> <span data-ttu-id="6f201-157">Mehrere andere Unterstützungsklassen, wie z.B. Tabellenadapter für jede der ausgewählten Tabellen, werden ebenfalls hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="6f201-157">Several other support classes, such as table adapters for each of the chosen tables, are also added.</span></span>

### <a name="to-add-the-data-source"></a><span data-ttu-id="6f201-158">So fügen Sie die Datenquelle hinzu</span><span class="sxs-lookup"><span data-stu-id="6f201-158">To add the data source</span></span>

1. <span data-ttu-id="6f201-159">Wählen Sie im Menü **Daten** die Option **neue Datenquelle hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="6f201-159">From the **Data** menu, select **Add New Data Source**.</span></span>

2. <span data-ttu-id="6f201-160">Erstellen Sie im **Assistenten zum Konfigurieren von Datenquellen**eine Verbindung mit der Northwind-Datenbank, indem Sie ein DataSet verwenden.</span><span class="sxs-lookup"><span data-stu-id="6f201-160">In the **Data Source Configuration Wizard**, create a connection to the Northwind database by using a dataset.</span></span> <span data-ttu-id="6f201-161">Weitere Informationen finden Sie unter [How to: Connect to Data in a Database](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/fxk9yw1t(v=vs.120)).</span><span class="sxs-lookup"><span data-stu-id="6f201-161">For more information, see [How to: Connect to Data in a Database](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/fxk9yw1t(v=vs.120)).</span></span>

3. <span data-ttu-id="6f201-162">Wenn Sie vom **Assistenten zum Konfigurieren von Datenquellen**dazu aufgefordert werden, speichern Sie die Verbindungs Zeichenfolge als `NorthwindConnectionString`.</span><span class="sxs-lookup"><span data-stu-id="6f201-162">When you are prompted by the **Data Source Configuration Wizard**, save the connection string as `NorthwindConnectionString`.</span></span>

4. <span data-ttu-id="6f201-163">Wenn Sie zur Auswahl der Datenbankobjekte aufgefordert werden, wählen Sie die `Customers`-und `Orders` Tabellen aus, und benennen Sie das generierte Dataset `NorthwindDataSet`.</span><span class="sxs-lookup"><span data-stu-id="6f201-163">When you are prompted to choose your database objects, select the `Customers` and `Orders` tables, and name the generated data set `NorthwindDataSet`.</span></span>

## <a name="binding-to-the-data-source"></a><span data-ttu-id="6f201-164">Bindung an die Datenquelle</span><span class="sxs-lookup"><span data-stu-id="6f201-164">Binding to the Data Source</span></span>

<span data-ttu-id="6f201-165">Die <xref:System.Windows.Forms.BindingSource?displayProperty=nameWithType> Komponente stellt eine einheitliche Schnittstelle für die Datenquelle der Anwendung bereit.</span><span class="sxs-lookup"><span data-stu-id="6f201-165">The <xref:System.Windows.Forms.BindingSource?displayProperty=nameWithType> component provides a uniform interface for the application's data source.</span></span> <span data-ttu-id="6f201-166">Die Bindung an die Datenquelle wird in der CodeBehind-Datei implementiert.</span><span class="sxs-lookup"><span data-stu-id="6f201-166">Binding to the data source is implemented in the code-behind file.</span></span>

### <a name="to-bind-to-the-data-source"></a><span data-ttu-id="6f201-167">Bindung an die Datenquelle</span><span class="sxs-lookup"><span data-stu-id="6f201-167">To bind to the data source</span></span>

1. <span data-ttu-id="6f201-168">Öffnen Sie die CodeBehind-Datei mit die Namen „MainWindow.Xaml.vb“ bzw. „MainWindow.Xaml.cs“.</span><span class="sxs-lookup"><span data-stu-id="6f201-168">Open the code-behind file, which is named MainWindow.xaml.vb or MainWindow.xaml.cs.</span></span>

2. <span data-ttu-id="6f201-169">Kopieren Sie den folgenden Code in die Definition der `MainWindow`-Klasse.</span><span class="sxs-lookup"><span data-stu-id="6f201-169">Copy the following code into the `MainWindow` class definition.</span></span>

     <span data-ttu-id="6f201-170">Dieser Code deklariert die <xref:System.Windows.Forms.BindingSource> Komponente und zugeordnete Hilfsklassen, die eine Verbindung mit der Datenbank herstellen.</span><span class="sxs-lookup"><span data-stu-id="6f201-170">This code declares the <xref:System.Windows.Forms.BindingSource> component and associated helper classes that connect to the database.</span></span>

     [!code-csharp[WPFWithWFAndDatabinding#11](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#11)]
     [!code-vb[WPFWithWFAndDatabinding#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#11)]

3. <span data-ttu-id="6f201-171">Kopieren Sie den folgenden Code in den Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="6f201-171">Copy the following code into the constructor.</span></span>

     <span data-ttu-id="6f201-172">Dieser Code erstellt und initialisiert die <xref:System.Windows.Forms.BindingSource> Komponente.</span><span class="sxs-lookup"><span data-stu-id="6f201-172">This code creates and initializes the <xref:System.Windows.Forms.BindingSource> component.</span></span>

     [!code-csharp[WPFWithWFAndDatabinding#12](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#12)]
     [!code-vb[WPFWithWFAndDatabinding#12](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#12)]

4. <span data-ttu-id="6f201-173">Öffnen Sie „MainWindow.xaml“.</span><span class="sxs-lookup"><span data-stu-id="6f201-173">Open MainWindow.xaml.</span></span>

5. <span data-ttu-id="6f201-174">Wählen Sie in Designansicht-oder XAML-Ansicht das <xref:System.Windows.Window> Element aus.</span><span class="sxs-lookup"><span data-stu-id="6f201-174">In Design view or XAML view, select the <xref:System.Windows.Window> element.</span></span>

6. <span data-ttu-id="6f201-175">Klicken Sie im Eigenschaftenfenster auf die Registerkarte **Ereignisse** .</span><span class="sxs-lookup"><span data-stu-id="6f201-175">In the Properties window, click the **Events** tab.</span></span>

7. <span data-ttu-id="6f201-176">Doppelklicken Sie auf das <xref:System.Windows.FrameworkElement.Loaded> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="6f201-176">Double-click the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span>

8. <span data-ttu-id="6f201-177">Kopieren Sie den folgenden Code in den <xref:System.Windows.FrameworkElement.Loaded>-Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="6f201-177">Copy the following code into the <xref:System.Windows.FrameworkElement.Loaded> event handler.</span></span>

     <span data-ttu-id="6f201-178">Dieser Code weist die <xref:System.Windows.Forms.BindingSource> Komponente als Datenkontext zu und füllt die `Customers` und `Orders` Adapter Objekte auf.</span><span class="sxs-lookup"><span data-stu-id="6f201-178">This code assigns the <xref:System.Windows.Forms.BindingSource> component as the data context and populates the `Customers` and `Orders` adapter objects.</span></span>

     [!code-csharp[WPFWithWFAndDatabinding#13](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#13)]
     [!code-vb[WPFWithWFAndDatabinding#13](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#13)]

9. <span data-ttu-id="6f201-179">Kopieren Sie den folgenden Code in die Definition der `MainWindow`-Klasse.</span><span class="sxs-lookup"><span data-stu-id="6f201-179">Copy the following code into the `MainWindow` class definition.</span></span>

     <span data-ttu-id="6f201-180">Diese Methode behandelt das <xref:System.Windows.Data.CollectionView.CurrentChanged>-Ereignis und aktualisiert das aktuelle Element der Datenbindung.</span><span class="sxs-lookup"><span data-stu-id="6f201-180">This method handles the <xref:System.Windows.Data.CollectionView.CurrentChanged> event and updates the current item of the data binding.</span></span>

     [!code-csharp[WPFWithWFAndDatabinding#14](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#14)]
     [!code-vb[WPFWithWFAndDatabinding#14](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#14)]

10. <span data-ttu-id="6f201-181">Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="6f201-181">Press F5 to build and run the application.</span></span>

## <a name="see-also"></a><span data-ttu-id="6f201-182">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6f201-182">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="6f201-183">Entwerfen von XAML-Code in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="6f201-183">Design XAML in Visual Studio</span></span>](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [<span data-ttu-id="6f201-184">Beispiel für Datenbindung in Hybrid Anwendungen</span><span class="sxs-lookup"><span data-stu-id="6f201-184">Data Binding in Hybrid Applications Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=159983)
- [<span data-ttu-id="6f201-185">Exemplarische Vorgehensweise: Hosten eines zusammengesetzten Windows Forms-Steuerelements in WPF</span><span class="sxs-lookup"><span data-stu-id="6f201-185">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [<span data-ttu-id="6f201-186">Exemplarische Vorgehensweise: Hosten eines zusammengesetzten WPF-Steuerelements in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6f201-186">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
