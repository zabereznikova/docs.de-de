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
ms.openlocfilehash: fe8826a390abd370361b84f99540b8dacbdedc5e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33549278"
---
# <a name="walkthrough-binding-to-data-in-hybrid-applications"></a><span data-ttu-id="ecc0b-102">Exemplarische Vorgehensweise: Datenbindung in Hybridanwendungen</span><span class="sxs-lookup"><span data-stu-id="ecc0b-102">Walkthrough: Binding to Data in Hybrid Applications</span></span>
<span data-ttu-id="ecc0b-103">Binden einer Datenquelle an ein Steuerelement ist wichtig für das Bereitstellen von Benutzern mit Zugriff auf die zugrunde liegenden Daten, unabhängig davon, ob Sie sind [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] oder [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ecc0b-103">Binding a data source to a control is essential for providing users with access to underlying data, whether you are using [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] or [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span></span> <span data-ttu-id="ecc0b-104">In dieser exemplarischen Vorgehensweise wird gezeigt, wie Sie die Datenbindung in hybridanwendungen verwenden können, die beide enthalten [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] und [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="ecc0b-104">This walkthrough shows how you can use data binding in hybrid applications that include both [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] and [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] controls.</span></span>  
  
 <span data-ttu-id="ecc0b-105">In dieser exemplarischen Vorgehensweise werden u. a. folgende Aufgaben veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="ecc0b-105">Tasks illustrated in this walkthrough include:</span></span>  
  
-   <span data-ttu-id="ecc0b-106">Erstellen des Projekts.</span><span class="sxs-lookup"><span data-stu-id="ecc0b-106">Creating the project.</span></span>  
  
-   <span data-ttu-id="ecc0b-107">Definieren der Datenvorlage.</span><span class="sxs-lookup"><span data-stu-id="ecc0b-107">Defining the data template.</span></span>  
  
-   <span data-ttu-id="ecc0b-108">Angeben des Formularlayouts.</span><span class="sxs-lookup"><span data-stu-id="ecc0b-108">Specifying the form layout.</span></span>  
  
-   <span data-ttu-id="ecc0b-109">Angeben von Datenbindungen.</span><span class="sxs-lookup"><span data-stu-id="ecc0b-109">Specifying data bindings.</span></span>  
  
-   <span data-ttu-id="ecc0b-110">Anzeigen von Daten mithilfe von Interoperation.</span><span class="sxs-lookup"><span data-stu-id="ecc0b-110">Displaying data by using interoperation.</span></span>  
  
-   <span data-ttu-id="ecc0b-111">Hinzufügen der Datenquelle zum Projekt.</span><span class="sxs-lookup"><span data-stu-id="ecc0b-111">Adding the data source to the project.</span></span>  
  
-   <span data-ttu-id="ecc0b-112">Bindung an die Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="ecc0b-112">Binding to the data source.</span></span>  
  
 <span data-ttu-id="ecc0b-113">Vollständige Codeliste der Aufgaben in dieser exemplarischen Vorgehensweise veranschaulicht, finden Sie unter [Binden von Daten in Anwendungen Hybridbeispiel](http://go.microsoft.com/fwlink/?LinkID=159983).</span><span class="sxs-lookup"><span data-stu-id="ecc0b-113">For a complete code listing of the tasks illustrated in this walkthrough, see [Data Binding in Hybrid Applications Sample](http://go.microsoft.com/fwlink/?LinkID=159983).</span></span>  
  
 <span data-ttu-id="ecc0b-114">Anschließend werden Sie verstehen, welche Rolle Datenbindungsfunktionen bei Hybridanwendungen spielen.</span><span class="sxs-lookup"><span data-stu-id="ecc0b-114">When you are finished, you will have an understanding of data binding features in hybrid applications.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="ecc0b-115">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="ecc0b-115">Prerequisites</span></span>  
 <span data-ttu-id="ecc0b-116">Zum Durchführen dieser exemplarischen Vorgehensweise benötigen Sie die folgenden Komponenten:</span><span class="sxs-lookup"><span data-stu-id="ecc0b-116">You need the following components to complete this walkthrough:</span></span>  
  
-   [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)]  
  
-   <span data-ttu-id="ecc0b-118">Zugriff auf die Beispieldatenbank Northwind für Microsoft SQL Server ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ecc0b-118">Access to the Northwind sample database running on Microsoft SQL Server.</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="ecc0b-119">Erstellen des Projekts</span><span class="sxs-lookup"><span data-stu-id="ecc0b-119">Creating the Project</span></span>  
  
#### <a name="to-create-and-set-up-the-project"></a><span data-ttu-id="ecc0b-120">So erstellen und richten Sie das Projekt ein</span><span class="sxs-lookup"><span data-stu-id="ecc0b-120">To create and set up the project</span></span>  
  
1.  <span data-ttu-id="ecc0b-121">Erstellen Sie ein WPF-Anwendungsprojekt mit dem Namen `WPFWithWFAndDatabinding`.</span><span class="sxs-lookup"><span data-stu-id="ecc0b-121">Create a WPF Application project named `WPFWithWFAndDatabinding`.</span></span>  
  
2.  <span data-ttu-id="ecc0b-122">Fügen Sie im Projektmappen-Explorer Verweise auf die folgenden Assemblys hinzu.</span><span class="sxs-lookup"><span data-stu-id="ecc0b-122">In Solution Explorer, add references to the following assemblies.</span></span>  
  
    -   <span data-ttu-id="ecc0b-123">WindowsFormsIntegration</span><span class="sxs-lookup"><span data-stu-id="ecc0b-123">WindowsFormsIntegration</span></span>  
  
    -   <span data-ttu-id="ecc0b-124">System.Windows.Forms</span><span class="sxs-lookup"><span data-stu-id="ecc0b-124">System.Windows.Forms</span></span>  
  
3.  <span data-ttu-id="ecc0b-125">Öffnen Sie "MainWindow.xaml" in der [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ecc0b-125">Open MainWindow.xaml in the [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span></span>  
  
4.  <span data-ttu-id="ecc0b-126">In der <xref:System.Windows.Window> Element, fügen Sie die folgenden [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Namespacezuordnung.</span><span class="sxs-lookup"><span data-stu-id="ecc0b-126">In the <xref:System.Windows.Window> element, add the following [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] namespaces mapping.</span></span>  
  
    ```xaml  
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"  
    ```  
  
5.  <span data-ttu-id="ecc0b-127">Benennen Sie die Standardeinstellung <xref:System.Windows.Controls.Grid> Element `mainGrid` durch Zuweisen der <xref:System.Windows.FrameworkElement.Name%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="ecc0b-127">Name the default <xref:System.Windows.Controls.Grid> element `mainGrid` by assigning the <xref:System.Windows.FrameworkElement.Name%2A> property.</span></span>  
  
     [!code-xaml[WPFWithWFAndDatabinding#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#8)]  
  
## <a name="defining-the-data-template"></a><span data-ttu-id="ecc0b-128">Definieren der Datenvorlage</span><span class="sxs-lookup"><span data-stu-id="ecc0b-128">Defining the Data Template</span></span>  
 <span data-ttu-id="ecc0b-129">Die Masterliste der Kunden wird angezeigt, einem <xref:System.Windows.Controls.ListBox> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="ecc0b-129">The master list of customers is displayed in a <xref:System.Windows.Controls.ListBox> control.</span></span> <span data-ttu-id="ecc0b-130">Das folgende Codebeispiel definiert eine <xref:System.Windows.DataTemplate> Objekt mit dem Namen `ListItemsTemplate` , steuert die visuelle Struktur der <xref:System.Windows.Controls.ListBox> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="ecc0b-130">The following code example defines a <xref:System.Windows.DataTemplate> object named `ListItemsTemplate` that controls the visual tree of the <xref:System.Windows.Controls.ListBox> control.</span></span> <span data-ttu-id="ecc0b-131">Dies <xref:System.Windows.DataTemplate> zugewiesen ist die <xref:System.Windows.Controls.ListBox> des Steuerelements <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="ecc0b-131">This <xref:System.Windows.DataTemplate> is assigned to the <xref:System.Windows.Controls.ListBox> control's <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> property.</span></span>  
  
#### <a name="to-define-the-data-template"></a><span data-ttu-id="ecc0b-132">Definieren der Datenvorlage</span><span class="sxs-lookup"><span data-stu-id="ecc0b-132">To define the data template</span></span>  
  
-   <span data-ttu-id="ecc0b-133">Kopieren Sie den folgenden XAML-Code in der <xref:System.Windows.Controls.Grid> Deklaration des Elements.</span><span class="sxs-lookup"><span data-stu-id="ecc0b-133">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element's declaration.</span></span>  
  
     [!code-xaml[WPFWithWFAndDatabinding#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#3)]  
  
## <a name="specifying-the-form-layout"></a><span data-ttu-id="ecc0b-134">Angeben des Formularlayouts</span><span class="sxs-lookup"><span data-stu-id="ecc0b-134">Specifying the Form Layout</span></span>  
 <span data-ttu-id="ecc0b-135">Das Layout des Formulars wird durch ein Raster mit drei Zeilen und drei Spalten definiert.</span><span class="sxs-lookup"><span data-stu-id="ecc0b-135">The layout of the form is defined by a grid with three rows and three columns.</span></span> <span data-ttu-id="ecc0b-136"><xref:System.Windows.Controls.Label> Steuerelemente werden bereitgestellt, um jede Spalte in der Customers-Tabelle zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="ecc0b-136"><xref:System.Windows.Controls.Label> controls are provided to identify each column in the Customers table.</span></span>  
  
#### <a name="to-set-up-the-grid-layout"></a><span data-ttu-id="ecc0b-137">Einrichten des Rasterlayouts</span><span class="sxs-lookup"><span data-stu-id="ecc0b-137">To set up the Grid layout</span></span>  
  
-   <span data-ttu-id="ecc0b-138">Kopieren Sie den folgenden XAML-Code in der <xref:System.Windows.Controls.Grid> Deklaration des Elements.</span><span class="sxs-lookup"><span data-stu-id="ecc0b-138">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element's declaration.</span></span>  
  
     [!code-xaml[WPFWithWFAndDatabinding#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#4)]  
  
#### <a name="to-set-up-the-label-controls"></a><span data-ttu-id="ecc0b-139">Label-Steuerelemente einrichten</span><span class="sxs-lookup"><span data-stu-id="ecc0b-139">To set up the Label controls</span></span>  
  
-   <span data-ttu-id="ecc0b-140">Kopieren Sie den folgenden XAML-Code in der <xref:System.Windows.Controls.Grid> Deklaration des Elements.</span><span class="sxs-lookup"><span data-stu-id="ecc0b-140">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element's declaration.</span></span>  
  
     [!code-xaml[WPFWithWFAndDatabinding#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#5)]  
  
## <a name="specifying-data-bindings"></a><span data-ttu-id="ecc0b-141">Angeben von Datenbindungen</span><span class="sxs-lookup"><span data-stu-id="ecc0b-141">Specifying Data Bindings</span></span>  
 <span data-ttu-id="ecc0b-142">Die Masterliste der Kunden wird angezeigt, einem <xref:System.Windows.Controls.ListBox> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="ecc0b-142">The master list of customers is displayed in a <xref:System.Windows.Controls.ListBox> control.</span></span> <span data-ttu-id="ecc0b-143">Der angefügte `ListItemsTemplate` bindet ein <xref:System.Windows.Controls.TextBlock> die Steuerung an die `ContactName` Feld aus der Datenbank.</span><span class="sxs-lookup"><span data-stu-id="ecc0b-143">The attached `ListItemsTemplate` binds a <xref:System.Windows.Controls.TextBlock> control to the `ContactName` field from the database.</span></span>  
  
 <span data-ttu-id="ecc0b-144">Die Details für jeden Kundendatensatz werden angezeigt, in mehreren <xref:System.Windows.Controls.TextBox> Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="ecc0b-144">The details of each customer record are displayed in several <xref:System.Windows.Controls.TextBox> controls.</span></span>  
  
#### <a name="to-specify-data-bindings"></a><span data-ttu-id="ecc0b-145">Datenbindungen angeben</span><span class="sxs-lookup"><span data-stu-id="ecc0b-145">To specify data bindings</span></span>  
  
-   <span data-ttu-id="ecc0b-146">Kopieren Sie den folgenden XAML-Code in der <xref:System.Windows.Controls.Grid> Deklaration des Elements.</span><span class="sxs-lookup"><span data-stu-id="ecc0b-146">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element's declaration.</span></span>  
  
     <span data-ttu-id="ecc0b-147">Die <xref:System.Windows.Data.Binding> -Klasse bindet die <xref:System.Windows.Controls.TextBox> Steuerelemente mit den entsprechenden Feldern in der Datenbank.</span><span class="sxs-lookup"><span data-stu-id="ecc0b-147">The <xref:System.Windows.Data.Binding> class binds the <xref:System.Windows.Controls.TextBox> controls to the appropriate fields in the database.</span></span>  
  
     [!code-xaml[WPFWithWFAndDatabinding#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#6)]  
  
## <a name="displaying-data-by-using-interoperation"></a><span data-ttu-id="ecc0b-148">Anzeigen von Daten mithilfe von Interoperation</span><span class="sxs-lookup"><span data-stu-id="ecc0b-148">Displaying Data by Using Interoperation</span></span>  
 <span data-ttu-id="ecc0b-149">Werden die Aufträge entsprechen, die dem ausgewählten Kunden angezeigt, einem <xref:System.Windows.Forms.DataGridView?displayProperty=nameWithType> Steuerelement namens `dataGridView1`.</span><span class="sxs-lookup"><span data-stu-id="ecc0b-149">The orders corresponding to the selected customer are displayed in a <xref:System.Windows.Forms.DataGridView?displayProperty=nameWithType> control named `dataGridView1`.</span></span> <span data-ttu-id="ecc0b-150">Die `dataGridView1` Steuerelement an die Datenquelle in der Code-Behind-Datei gebunden ist.</span><span class="sxs-lookup"><span data-stu-id="ecc0b-150">The `dataGridView1` control is bound to the data source in the code-behind file.</span></span> <span data-ttu-id="ecc0b-151">Ein <xref:System.Windows.Forms.Integration.WindowsFormsHost> Steuerelement ist das übergeordnete Element dieses [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="ecc0b-151">A <xref:System.Windows.Forms.Integration.WindowsFormsHost> control is the parent of this [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control.</span></span>  
  
#### <a name="to-display-data-in-the-datagridview-control"></a><span data-ttu-id="ecc0b-152">Anzeigen von Daten im DataGridView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="ecc0b-152">To display data in the DataGridView control</span></span>  
  
-   <span data-ttu-id="ecc0b-153">Kopieren Sie den folgenden XAML-Code in der <xref:System.Windows.Controls.Grid> Deklaration des Elements.</span><span class="sxs-lookup"><span data-stu-id="ecc0b-153">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element's declaration.</span></span>  
  
     [!code-xaml[WPFWithWFAndDatabinding#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#7)]  
  
## <a name="adding-the-data-source-to-the-project"></a><span data-ttu-id="ecc0b-154">Hinzufügen der Datenquelle zum Projekt</span><span class="sxs-lookup"><span data-stu-id="ecc0b-154">Adding the Data Source to the Project</span></span>  
 <span data-ttu-id="ecc0b-155">Mit Visual Studio können Sie problemlos eine Datenquelle zum Projekt hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="ecc0b-155">With Visual Studio, you can easily add a data source to your project.</span></span> <span data-ttu-id="ecc0b-156">Bei diesem Vorgang wird dem Projekt ein stark typisiertes Dataset hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="ecc0b-156">This procedure adds a strongly typed data set to your project.</span></span> <span data-ttu-id="ecc0b-157">Mehrere andere Unterstützungsklassen, wie z.B. Tabellenadapter für jede der ausgewählten Tabellen, werden ebenfalls hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="ecc0b-157">Several other support classes, such as table adapters for each of the chosen tables, are also added.</span></span>  
  
#### <a name="to-add-the-data-source"></a><span data-ttu-id="ecc0b-158">So fügen Sie die Datenquelle hinzu</span><span class="sxs-lookup"><span data-stu-id="ecc0b-158">To add the data source</span></span>  
  
1.  <span data-ttu-id="ecc0b-159">Aus der **Daten** klicken Sie im Menü **neue Datenquelle hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="ecc0b-159">From the **Data** menu, select **Add New Data Source**.</span></span>  
  
2.  <span data-ttu-id="ecc0b-160">In der **Data Source Configuration Wizard**, erstellen Sie eine Verbindung zur Northwind-Datenbank unter Verwendung eines Datasets.</span><span class="sxs-lookup"><span data-stu-id="ecc0b-160">In the **Data Source Configuration Wizard**, create a connection to the Northwind database by using a dataset.</span></span> <span data-ttu-id="ecc0b-161">Weitere Informationen finden Sie unter [Vorgehensweise: Herstellen einer Verbindung mit Daten in einer Datenbank](http://msdn.microsoft.com/library/6c56e54e-8834-4297-85aa-cc1a443ba556).</span><span class="sxs-lookup"><span data-stu-id="ecc0b-161">For more information, see [How to: Connect to Data in a Database](http://msdn.microsoft.com/library/6c56e54e-8834-4297-85aa-cc1a443ba556).</span></span>  
  
3.  <span data-ttu-id="ecc0b-162">Wenn Sie aufgefordert werden durch die **Datenquellen Konfigurations-Assistenten**, Speichern der Verbindungszeichenfolge als `NorthwindConnectionString`.</span><span class="sxs-lookup"><span data-stu-id="ecc0b-162">When you are prompted by the **Data Source Configuration Wizard**, save the connection string as `NorthwindConnectionString`.</span></span>  
  
4.  <span data-ttu-id="ecc0b-163">Wenn Sie aufgefordert werden, um Datenbankobjekte auszuwählen, wählen Sie die `Customers` und `Orders` Tabellen und der Name der generierten DataSet `NorthwindDataSet`.</span><span class="sxs-lookup"><span data-stu-id="ecc0b-163">When you are prompted to choose your database objects, select the `Customers` and `Orders` tables, and name the generated data set `NorthwindDataSet`.</span></span>  
  
## <a name="binding-to-the-data-source"></a><span data-ttu-id="ecc0b-164">Bindung an die Datenquelle</span><span class="sxs-lookup"><span data-stu-id="ecc0b-164">Binding to the Data Source</span></span>  
 <span data-ttu-id="ecc0b-165">Die <xref:System.Windows.Forms.BindingSource?displayProperty=nameWithType> Komponente bietet eine einheitliche Schnittstelle für die Anwendung die Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="ecc0b-165">The <xref:System.Windows.Forms.BindingSource?displayProperty=nameWithType> component provides a uniform interface for the application's data source.</span></span> <span data-ttu-id="ecc0b-166">Die Bindung an die Datenquelle wird in der CodeBehind-Datei implementiert.</span><span class="sxs-lookup"><span data-stu-id="ecc0b-166">Binding to the data source is implemented in the code-behind file.</span></span>  
  
#### <a name="to-bind-to-the-data-source"></a><span data-ttu-id="ecc0b-167">Bindung an die Datenquelle</span><span class="sxs-lookup"><span data-stu-id="ecc0b-167">To bind to the data source</span></span>  
  
1.  <span data-ttu-id="ecc0b-168">Öffnen Sie die CodeBehind-Datei mit die Namen „MainWindow.Xaml.vb“ bzw. „MainWindow.Xaml.cs“.</span><span class="sxs-lookup"><span data-stu-id="ecc0b-168">Open the code-behind file, which is named MainWindow.xaml.vb or MainWindow.xaml.cs.</span></span>  
  
2.  <span data-ttu-id="ecc0b-169">Kopieren Sie den folgenden Code in die `MainWindow` Klassendefinition.</span><span class="sxs-lookup"><span data-stu-id="ecc0b-169">Copy the following code into the `MainWindow` class definition.</span></span>  
  
     <span data-ttu-id="ecc0b-170">Dieser Code deklariert die <xref:System.Windows.Forms.BindingSource> Komponente und zugeordnete Hilfsklassen, die mit der Datenbank herstellen.</span><span class="sxs-lookup"><span data-stu-id="ecc0b-170">This code declares the <xref:System.Windows.Forms.BindingSource> component and associated helper classes that connect to the database.</span></span>  
  
     [!code-csharp[WPFWithWFAndDatabinding#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#11)]
     [!code-vb[WPFWithWFAndDatabinding#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#11)]  
  
3.  <span data-ttu-id="ecc0b-171">Kopieren Sie den folgenden Code in den Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="ecc0b-171">Copy the following code into the constructor.</span></span>  
  
     <span data-ttu-id="ecc0b-172">Dieser Code erstellt und initialisiert die <xref:System.Windows.Forms.BindingSource> Komponente.</span><span class="sxs-lookup"><span data-stu-id="ecc0b-172">This code creates and initializes the <xref:System.Windows.Forms.BindingSource> component.</span></span>  
  
     [!code-csharp[WPFWithWFAndDatabinding#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#12)]
     [!code-vb[WPFWithWFAndDatabinding#12](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#12)]  
  
4.  <span data-ttu-id="ecc0b-173">Öffnen Sie „MainWindow.xaml“.</span><span class="sxs-lookup"><span data-stu-id="ecc0b-173">Open MainWindow.xaml.</span></span>  
  
5.  <span data-ttu-id="ecc0b-174">Wählen Sie in der Entwurfsansicht oder der XAML-Ansicht, die <xref:System.Windows.Window> Element.</span><span class="sxs-lookup"><span data-stu-id="ecc0b-174">In Design view or XAML view, select the <xref:System.Windows.Window> element.</span></span>  
  
6.  <span data-ttu-id="ecc0b-175">Klicken Sie im Eigenschaftenfenster auf die **Ereignisse** Registerkarte.</span><span class="sxs-lookup"><span data-stu-id="ecc0b-175">In the Properties window, click the **Events** tab.</span></span>  
  
7.  <span data-ttu-id="ecc0b-176">Doppelklicken Sie auf die <xref:System.Windows.FrameworkElement.Loaded> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="ecc0b-176">Double-click the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span>  
  
8.  <span data-ttu-id="ecc0b-177">Kopieren Sie den folgenden Code in der <xref:System.Windows.FrameworkElement.Loaded> -Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="ecc0b-177">Copy the following code into the <xref:System.Windows.FrameworkElement.Loaded> event handler.</span></span>  
  
     <span data-ttu-id="ecc0b-178">Dieser Code weist die <xref:System.Windows.Forms.BindingSource> -Komponente als Datenkontext und füllt die `Customers` und `Orders` adapterobjekten.</span><span class="sxs-lookup"><span data-stu-id="ecc0b-178">This code assigns the <xref:System.Windows.Forms.BindingSource> component as the data context and populates the `Customers` and `Orders` adapter objects.</span></span>  
  
     [!code-csharp[WPFWithWFAndDatabinding#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#13)]
     [!code-vb[WPFWithWFAndDatabinding#13](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#13)]  
  
9. <span data-ttu-id="ecc0b-179">Kopieren Sie den folgenden Code in die `MainWindow` Klassendefinition.</span><span class="sxs-lookup"><span data-stu-id="ecc0b-179">Copy the following code into the `MainWindow` class definition.</span></span>  
  
     <span data-ttu-id="ecc0b-180">Diese Methode behandelt das <xref:System.Windows.Data.CollectionView.CurrentChanged> Ereignis und aktualisiert das aktuelle Element der Datenbindung.</span><span class="sxs-lookup"><span data-stu-id="ecc0b-180">This method handles the <xref:System.Windows.Data.CollectionView.CurrentChanged> event and updates the current item of the data binding.</span></span>  
  
     [!code-csharp[WPFWithWFAndDatabinding#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#14)]
     [!code-vb[WPFWithWFAndDatabinding#14](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#14)]  
  
10. <span data-ttu-id="ecc0b-181">Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="ecc0b-181">Press F5 to build and run the application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ecc0b-182">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ecc0b-182">See Also</span></span>  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [<span data-ttu-id="ecc0b-183">WPF-Designer</span><span class="sxs-lookup"><span data-stu-id="ecc0b-183">WPF Designer</span></span>](http://msdn.microsoft.com/library/c6c65214-8411-4e16-b254-163ed4099c26)  
 [<span data-ttu-id="ecc0b-184">Im Beispiel für Hybrid-Anwendungen Binden von Daten</span><span class="sxs-lookup"><span data-stu-id="ecc0b-184">Data Binding in Hybrid Applications Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=159983)  
 [<span data-ttu-id="ecc0b-185">Exemplarische Vorgehensweise: Hosten eines zusammengesetzten Windows Forms-Steuerelements in WPF</span><span class="sxs-lookup"><span data-stu-id="ecc0b-185">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)  
 [<span data-ttu-id="ecc0b-186">Exemplarische Vorgehensweise: Hosten eines zusammengesetzten WPF-Steuerelements in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ecc0b-186">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
