---
title: 'Exemplarische Vorgehensweise: Aktivieren der Drag & Drop-Funktion auf einem Benutzersteuerelement'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- walkthrough [WPF], drag-and-drop
- drag-and-drop [WPF], walkthrough
ms.assetid: cc844419-1a77-4906-95d9-060d79107fc7
ms.openlocfilehash: e151eb7f428fecb330970210fd7addb1603a211f
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43534231"
---
# <a name="walkthrough-enabling-drag-and-drop-on-a-user-control"></a><span data-ttu-id="99deb-102">Exemplarische Vorgehensweise: Aktivieren der Drag & Drop-Funktion auf einem Benutzersteuerelement</span><span class="sxs-lookup"><span data-stu-id="99deb-102">Walkthrough: Enabling Drag and Drop on a User Control</span></span>
<span data-ttu-id="99deb-103">In dieser exemplarische Vorgehensweise wird veranschaulicht, wie man in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] ein benutzerdefiniertes Steuerelement erstellt, das Drag & Drop-Datenübertragung unterstützt.</span><span class="sxs-lookup"><span data-stu-id="99deb-103">This walkthrough demonstrates how to create a custom user control that can participate in drag-and-drop data transfer in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].</span></span>  
  
 <span data-ttu-id="99deb-104">In dieser exemplarischen Vorgehensweise erstellen Sie eine benutzerdefinierte WPF <xref:System.Windows.Controls.UserControl> , das eine Kreisform darstellt.</span><span class="sxs-lookup"><span data-stu-id="99deb-104">In this walkthrough, you will create a custom WPF <xref:System.Windows.Controls.UserControl> that represents a circle shape.</span></span> <span data-ttu-id="99deb-105">Sie werden dabei Funktionen für das Steuerelement implementieren, welche die Übertragung von Daten durch Drag & Drop ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="99deb-105">You will implement functionality on the control to enable data transfer through drag-and-drop.</span></span> <span data-ttu-id="99deb-106">Wenn Sie z.B. von einem Kreis-Steuerelement auf ein anderes ziehen, werden die Füllfarbdaten vom Quellkreis auf den Zielkreis kopiert.</span><span class="sxs-lookup"><span data-stu-id="99deb-106">For example, if you drag from one Circle control to another, the Fill color data is copied from the source Circle to the target.</span></span> <span data-ttu-id="99deb-107">Wenn Sie ein Kreis-Steuerelement, ziehen Sie eine <xref:System.Windows.Controls.TextBox>, die Zeichenfolgendarstellung der Füllfarbe in kopiert die <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="99deb-107">If you drag from a Circle control to a <xref:System.Windows.Controls.TextBox>, the string representation of the Fill color is copied to the <xref:System.Windows.Controls.TextBox>.</span></span> <span data-ttu-id="99deb-108">Außerdem erstellen Sie eine kleine Anwendung, die zwei Panel-Steuerelemente enthält und eine <xref:System.Windows.Controls.TextBox> zum Testen der Drag & Drop-Funktionalität.</span><span class="sxs-lookup"><span data-stu-id="99deb-108">You will also create a small application that contains two panel controls and a <xref:System.Windows.Controls.TextBox> to test the drag-and-drop functionality.</span></span> <span data-ttu-id="99deb-109">Sie werden Code erstellen, der es den Panels ermöglicht, abgelegte Kreisdaten zu verarbeiten, sodass Sie Kreise aus der Auflistung untergeordneter Elemente von einem Panel zum anderen hin verschieben oder kopieren können.</span><span class="sxs-lookup"><span data-stu-id="99deb-109">You will write code that enables the panels to process dropped Circle data, which will enable you to move or copy Circles from the Children collection of one panel to the other.</span></span>  
  
 <span data-ttu-id="99deb-110">In dieser exemplarischen Vorgehensweise werden die folgenden Aufgaben veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="99deb-110">This walkthrough illustrates the following tasks:</span></span>  
  
-   <span data-ttu-id="99deb-111">Erstellen eines benutzerdefinierten Steuerelements.</span><span class="sxs-lookup"><span data-stu-id="99deb-111">Create a custom user control.</span></span>  
  
-   <span data-ttu-id="99deb-112">Konfigurieren des benutzerdefinierten Steuerelements, sodass es als Quelle eines Ziehvorgangs dienen kann.</span><span class="sxs-lookup"><span data-stu-id="99deb-112">Enable the user control to be a drag source.</span></span>  
  
-   <span data-ttu-id="99deb-113">Konfigurieren des benutzerdefinierten Steuerelements, sodass es als Ziel eines Ablegevorgangs dienen kann.</span><span class="sxs-lookup"><span data-stu-id="99deb-113">Enable the user control to be a drop target.</span></span>  
  
-   <span data-ttu-id="99deb-114">Konfigurieren eines Panels, sodass es von dem Benutzersteuerelement abgelegte Daten empfangen kann.</span><span class="sxs-lookup"><span data-stu-id="99deb-114">Enable a panel to receive data dropped from the user control.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="99deb-115">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="99deb-115">Prerequisites</span></span>  
 <span data-ttu-id="99deb-116">Zum Durchführen dieser exemplarischen Vorgehensweise benötigen Sie die folgenden Komponenten:</span><span class="sxs-lookup"><span data-stu-id="99deb-116">You need the following components to complete this walkthrough:</span></span>  
  
-   <span data-ttu-id="99deb-117">Visual Studio 2010</span><span class="sxs-lookup"><span data-stu-id="99deb-117">Visual Studio 2010</span></span>  
  
## <a name="creating-the-application-project"></a><span data-ttu-id="99deb-118">Erstellen des Anwendungsprojekts</span><span class="sxs-lookup"><span data-stu-id="99deb-118">Creating the Application Project</span></span>  
 <span data-ttu-id="99deb-119">In diesem Abschnitt erstellen Sie die Anwendungsstruktur, einschließlich eine Hauptseite mit zwei Panels und einer <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="99deb-119">In this section, you will create the application infrastructure, which includes a main page with two panels and a <xref:System.Windows.Controls.TextBox>.</span></span>  
  
### <a name="to-create-the-project"></a><span data-ttu-id="99deb-120">So erstellen Sie das Projekt</span><span class="sxs-lookup"><span data-stu-id="99deb-120">To create the project</span></span>  
  
1.  <span data-ttu-id="99deb-121">Erstellen Sie ein neues WPF-Anwendungsprojekt in Visual Basic oder Visual C# mit dem Namen `DragDropExample`.</span><span class="sxs-lookup"><span data-stu-id="99deb-121">Create a new WPF Application project in Visual Basic or Visual C# named `DragDropExample`.</span></span> <span data-ttu-id="99deb-122">Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen eines neuen WPF-Anwendungsprojekts](https://msdn.microsoft.com/library/1f6aea7a-33e1-4d3f-8555-1daa42e95d82).</span><span class="sxs-lookup"><span data-stu-id="99deb-122">For more information, see [How to: Create a New WPF Application Project](https://msdn.microsoft.com/library/1f6aea7a-33e1-4d3f-8555-1daa42e95d82).</span></span>  
  
2.  <span data-ttu-id="99deb-123">Öffnen Sie „MainWindow.xaml“.</span><span class="sxs-lookup"><span data-stu-id="99deb-123">Open MainWindow.xaml.</span></span>  
  
3.  <span data-ttu-id="99deb-124">Fügen Sie das folgende Markup zwischen die öffnenden und schließenden <xref:System.Windows.Controls.Grid> Tags.</span><span class="sxs-lookup"><span data-stu-id="99deb-124">Add the following markup between the opening and closing <xref:System.Windows.Controls.Grid> tags.</span></span>  
  
     <span data-ttu-id="99deb-125">Dieses Markup erstellt die Benutzeroberfläche für die Testanwendung.</span><span class="sxs-lookup"><span data-stu-id="99deb-125">This markup creates the user interface for the test application.</span></span>  
  
     [!code-xaml[DragDropWalkthrough#PanelsStep1XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/SnippetWindow.xaml#panelsstep1xaml)]  
  
## <a name="adding-a-new-user-control-to-the-project"></a><span data-ttu-id="99deb-126">Hinzufügen eines neuen Benutzersteuerelements zum Projekt</span><span class="sxs-lookup"><span data-stu-id="99deb-126">Adding a New User Control to the Project</span></span>  
 <span data-ttu-id="99deb-127">In diesem Abschnitt fügen Sie dem Projekt ein neues Benutzersteuerelement hinzu.</span><span class="sxs-lookup"><span data-stu-id="99deb-127">In this section, you will add a new user control to the project.</span></span>  
  
### <a name="to-add-a-new-user-control"></a><span data-ttu-id="99deb-128">So fügen Sie ein neues Benutzersteuerelement hinzu</span><span class="sxs-lookup"><span data-stu-id="99deb-128">To add a new user control</span></span>  
  
1.  <span data-ttu-id="99deb-129">Klicken Sie im Menü „Projekt” auf **Benutzersteuerelement hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="99deb-129">On the Project menu, select **Add User Control**.</span></span>  
  
2.  <span data-ttu-id="99deb-130">Ändern Sie im Dialogfeld „Neues Element hinzufügen” den Namen in `Circle.xaml`. Klicken Sie dann auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="99deb-130">In the Add New Item dialog box, change the name to `Circle.xaml`, and click **Add**.</span></span>  
  
     <span data-ttu-id="99deb-131">Circle.XAML und der dazugehörige CodeBehind werden dem Projekt hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="99deb-131">Circle.xaml and its code-behind is added to the project.</span></span>  
  
3.  <span data-ttu-id="99deb-132">Öffnen Sie Circle.xaml.</span><span class="sxs-lookup"><span data-stu-id="99deb-132">Open Circle.xaml.</span></span>  
  
     <span data-ttu-id="99deb-133">Diese Datei enthält die Benutzeroberflächenelemente des Benutzersteuerelements.</span><span class="sxs-lookup"><span data-stu-id="99deb-133">This file will contain the user interface elements of the user control.</span></span>  
  
4.  <span data-ttu-id="99deb-134">Fügen Sie das folgende Markup in das Stammverzeichnis <xref:System.Windows.Controls.Grid> ein einfaches Benutzersteuerelement zu erstellen, die über die Benutzeroberfläche ein blauer Kreis verfügt.</span><span class="sxs-lookup"><span data-stu-id="99deb-134">Add the following markup to the root <xref:System.Windows.Controls.Grid> to create a simple user control that has a blue circle as its UI.</span></span>  
  
     [!code-xaml[DragDropWalkthrough#EllipseXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml#ellipsexaml)]  
  
5.  <span data-ttu-id="99deb-135">Öffnen Sie "Circle.Xaml.cs" oder "Circle.Xaml.vb".</span><span class="sxs-lookup"><span data-stu-id="99deb-135">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>  
  
6.  <span data-ttu-id="99deb-136">Fügen Sie in C# den folgenden Code nach dem Standardkonstruktor hinzu, um einen Kopierkonstruktor zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="99deb-136">In C#, add the following code after the default constructor to create a copy constructor.</span></span> <span data-ttu-id="99deb-137">Fügen Sie in Visual Basic den folgenden Code hinzu, um sowohl einen Standardkonstruktor als auch einen Kopierkonstruktor zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="99deb-137">In Visual Basic, add the following code to create both a default constructor and a copy constructor.</span></span>  
  
     <span data-ttu-id="99deb-138">Fügen Sie eine Kopierkonstruktor-Methode in die CodeBehind-Datei ein, damit das Benutzersteuerelement kopiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="99deb-138">In order to allow the user control to be copied, you add a copy constructor method in the code-behind file.</span></span> <span data-ttu-id="99deb-139">Im vereinfachten kreisförmigen Benutzersteuerelement wollen wir nur die Füllfarbe und die Größe des Benutzersteuerelements kopieren.</span><span class="sxs-lookup"><span data-stu-id="99deb-139">In the simplified Circle user control, you will only copy the Fill and the size of the of the user control.</span></span>  
  
     [!code-csharp[DragDropWalkthrough#CopyCtor](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#copyctor)]
     [!code-vb[DragDropWalkthrough#CopyCtor](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#copyctor)]  
  
### <a name="to-add-the-user-control-to-the-main-window"></a><span data-ttu-id="99deb-140">So fügen Sie das Benutzersteuerelement dem Hauptfenster hinzu</span><span class="sxs-lookup"><span data-stu-id="99deb-140">To add the user control to the main window</span></span>  
  
1.  <span data-ttu-id="99deb-141">Öffnen Sie „MainWindow.xaml“.</span><span class="sxs-lookup"><span data-stu-id="99deb-141">Open MainWindow.xaml.</span></span>  
  
2.  <span data-ttu-id="99deb-142">Fügen Sie den folgenden XAML an das öffnende <xref:System.Windows.Window> Tag, um eine XML-Namespace-Referenz auf die aktuelle Anwendung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="99deb-142">Add the following XAML to the opening <xref:System.Windows.Window> tag to create an XML namespace reference to the current application.</span></span>  
  
    ```  
    xmlns:local="clr-namespace:DragDropExample"  
    ```  
  
3.  <span data-ttu-id="99deb-143">In der ersten <xref:System.Windows.Controls.StackPanel>, fügen Sie den folgenden XAML zum Erstellen von zwei Instanzen des Kreis-Steuerelements im ersten Bereich hinzu.</span><span class="sxs-lookup"><span data-stu-id="99deb-143">In the first <xref:System.Windows.Controls.StackPanel>, add the following XAML to create two instances of the Circle user control in the first panel.</span></span>  
  
     [!code-xaml[DragDropWalkthrough#CirclesXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/SnippetWindow.xaml#circlesxaml)]  
  
     <span data-ttu-id="99deb-144">Der vollständige XAML-Code für das Panel sieht folgendermaßen aus.</span><span class="sxs-lookup"><span data-stu-id="99deb-144">The full XAML for the panel looks like the following.</span></span>  
  
     [!code-xaml[DragDropWalkthrough#PanelsStep2XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/SnippetWindow.xaml#panelsstep2xaml)]  
  
## <a name="implementing-drag-source-events-in-the-user-control"></a><span data-ttu-id="99deb-145">Implementieren der Ereignisse der Ziehquelle im Benutzersteuerelement</span><span class="sxs-lookup"><span data-stu-id="99deb-145">Implementing Drag Source Events in the User Control</span></span>  
 <span data-ttu-id="99deb-146">In diesem Abschnitt überschreiben Sie die <xref:System.Windows.UIElement.OnMouseMove%2A> -Methode und initiieren den Drag & Drop-Vorgang.</span><span class="sxs-lookup"><span data-stu-id="99deb-146">In this section, you will override the <xref:System.Windows.UIElement.OnMouseMove%2A> method and initiate the drag-and-drop operation.</span></span>  
  
 <span data-ttu-id="99deb-147">Wenn ein Ziehvorgang gestartet wird (eine Maustaste gedrückt wird, und die Maus bewegt wird), Verpacken Sie die Daten in übertragen werden eine <xref:System.Windows.DataObject>.</span><span class="sxs-lookup"><span data-stu-id="99deb-147">If a drag is started (a mouse button is pressed and the mouse is moved), you will package the data to be transferred into a <xref:System.Windows.DataObject>.</span></span> <span data-ttu-id="99deb-148">In diesem Fall wird das Kreis-Steuerelement drei Datenelemente verpacken: eine Zeichenfolgendarstellung seiner Füllfarbe, eine double-Darstellung seiner Höhe und eine Kopie von sich selbst.</span><span class="sxs-lookup"><span data-stu-id="99deb-148">In this case, the Circle control will package three data items; a string representation of its Fill color, a double representation of its height, and a copy of itself.</span></span>  
  
### <a name="to-initiate-a-drag-and-drop-operation"></a><span data-ttu-id="99deb-149">Initiieren eines Drag & Drop-Vorgangs</span><span class="sxs-lookup"><span data-stu-id="99deb-149">To initiate a drag-and-drop operation</span></span>  
  
1.  <span data-ttu-id="99deb-150">Öffnen Sie "Circle.Xaml.cs" oder "Circle.Xaml.vb".</span><span class="sxs-lookup"><span data-stu-id="99deb-150">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>  
  
2.  <span data-ttu-id="99deb-151">Fügen Sie die folgenden <xref:System.Windows.UIElement.OnMouseMove%2A> überschreiben, um eine Klassenbehandlung für das Bereitstellen der <xref:System.Windows.UIElement.MouseMove> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="99deb-151">Add the following <xref:System.Windows.UIElement.OnMouseMove%2A> override to provide class handling for the <xref:System.Windows.UIElement.MouseMove> event.</span></span>  
  
     [!code-csharp[DragDropWalkthrough#OnMouseMove](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#onmousemove)]
     [!code-vb[DragDropWalkthrough#OnMouseMove](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#onmousemove)]  
  
     <span data-ttu-id="99deb-152">Dies <xref:System.Windows.UIElement.OnMouseMove%2A> -Überschreibung führt die folgenden Aufgaben:</span><span class="sxs-lookup"><span data-stu-id="99deb-152">This <xref:System.Windows.UIElement.OnMouseMove%2A> override performs the following tasks:</span></span>  
  
    -   <span data-ttu-id="99deb-153">Überprüft, ob die linke Maustaste gedrückt wird, während sich die Maus bewegt.</span><span class="sxs-lookup"><span data-stu-id="99deb-153">Checks whether the left mouse button is pressed while the mouse is moving.</span></span>  
  
    -   <span data-ttu-id="99deb-154">Verpackt die Kreisdaten in ein <xref:System.Windows.DataObject>.</span><span class="sxs-lookup"><span data-stu-id="99deb-154">Packages the Circle data into a <xref:System.Windows.DataObject>.</span></span> <span data-ttu-id="99deb-155">In diesem Fall verpackt das Kreis-Steuerelement drei Datenelemente: eine Zeichenfolgendarstellung seiner Füllfarbe, eine double-Darstellung seiner Höhe und eine Kopie von sich selbst.</span><span class="sxs-lookup"><span data-stu-id="99deb-155">In this case, the Circle control packages three data items; a string representation of its Fill color, a double representation of its height, and a copy of itself.</span></span>  
  
    -   <span data-ttu-id="99deb-156">Ruft die statische <xref:System.Windows.DragDrop.DoDragDrop%2A?displayProperty=nameWithType> Methode, um den Drag & Drop-Vorgang einzuleiten.</span><span class="sxs-lookup"><span data-stu-id="99deb-156">Calls the static <xref:System.Windows.DragDrop.DoDragDrop%2A?displayProperty=nameWithType> method to initiate the drag-and-drop operation.</span></span> <span data-ttu-id="99deb-157">Sie übergeben die folgenden drei Parameter für die <xref:System.Windows.DragDrop.DoDragDrop%2A> Methode:</span><span class="sxs-lookup"><span data-stu-id="99deb-157">You pass the following three parameters to the <xref:System.Windows.DragDrop.DoDragDrop%2A> method:</span></span>  
  
        -   <span data-ttu-id="99deb-158">`dragSource`: Ein Verweis auf dieses Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="99deb-158">`dragSource` – A reference to this control.</span></span>  
  
        -   <span data-ttu-id="99deb-159">`data` – Die <xref:System.Windows.DataObject> im vorherigen Code erstellte.</span><span class="sxs-lookup"><span data-stu-id="99deb-159">`data` – The <xref:System.Windows.DataObject> created in the previous code.</span></span>  
  
        -   <span data-ttu-id="99deb-160">`allowedEffects` – Die zulässigen Drag & Drop-Vorgänge, die <xref:System.Windows.DragDropEffects.Copy> oder <xref:System.Windows.DragDropEffects.Move>.</span><span class="sxs-lookup"><span data-stu-id="99deb-160">`allowedEffects` – The allowed drag-and-drop operations, which are <xref:System.Windows.DragDropEffects.Copy> or <xref:System.Windows.DragDropEffects.Move>.</span></span>  
  
3.  <span data-ttu-id="99deb-161">Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="99deb-161">Press F5 to build and run the application.</span></span>  
  
4.  <span data-ttu-id="99deb-162">Klicken Sie auf eines der Kreis-Steuerelemente, und ziehen Sie es über die Bereiche, die den anderen Kreis und die <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="99deb-162">Click one of the Circle controls and drag it over the panels, the other Circle, and the <xref:System.Windows.Controls.TextBox>.</span></span> <span data-ttu-id="99deb-163">Beim Ziehen über die <xref:System.Windows.Controls.TextBox>, ändert sich der Cursor um eine Verschiebung anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="99deb-163">When dragging over the <xref:System.Windows.Controls.TextBox>, the cursor changes to indicate a move.</span></span>  
  
5.  <span data-ttu-id="99deb-164">Beim Ziehen eines Kreises über die <xref:System.Windows.Controls.TextBox>, drücken Sie die STRG-Taste.</span><span class="sxs-lookup"><span data-stu-id="99deb-164">While dragging a Circle over the <xref:System.Windows.Controls.TextBox>, press the CTRL key.</span></span> <span data-ttu-id="99deb-165">Beachten Sie, wie sich der Cursor ändert, um einen Kopiervorgang anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="99deb-165">Notice how the cursor changes to indicate a copy.</span></span>  
  
6.  <span data-ttu-id="99deb-166">Drag & drop ein Kreises auf die <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="99deb-166">Drag and drop a Circle onto the <xref:System.Windows.Controls.TextBox>.</span></span> <span data-ttu-id="99deb-167">Die Zeichenfolgendarstellung der Füllfarbe des Kreises wird angefügt, um die <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="99deb-167">The string representation of the Circle’s fill color is appended to the <xref:System.Windows.Controls.TextBox>.</span></span>  
  
     <span data-ttu-id="99deb-168">![Zeichenfolgendarstellung der Füllfarbe des Kreises](../../../../docs/framework/wpf/advanced/media/dragdrop-colorstring.png "DragDrop_ColorString")</span><span class="sxs-lookup"><span data-stu-id="99deb-168">![String representation of Circle's fill color](../../../../docs/framework/wpf/advanced/media/dragdrop-colorstring.png "DragDrop_ColorString")</span></span>  
  
 <span data-ttu-id="99deb-169">Standardmäßig ändert sich der Cursor während eines Drag & Drop-Vorgangs, um anzuzeigen, welche Auswirkungen das Ablegen der Daten hat.</span><span class="sxs-lookup"><span data-stu-id="99deb-169">By default, the cursor will change during a drag-and-drop operation to indicate what effect dropping the data will have.</span></span> <span data-ttu-id="99deb-170">Sie können anpassen, dass das Feedback an den Benutzer gegeben werden, durch Behandeln der <xref:System.Windows.UIElement.GiveFeedback> Ereignis und einen anderen Cursor festlegen.</span><span class="sxs-lookup"><span data-stu-id="99deb-170">You can customize the feedback given to the user by handling the <xref:System.Windows.UIElement.GiveFeedback> event and setting a different cursor.</span></span>  
  
### <a name="to-give-feedback-to-the-user"></a><span data-ttu-id="99deb-171">Feedback an den Benutzer geben</span><span class="sxs-lookup"><span data-stu-id="99deb-171">To give feedback to the user</span></span>  
  
1.  <span data-ttu-id="99deb-172">Öffnen Sie "Circle.Xaml.cs" oder "Circle.Xaml.vb".</span><span class="sxs-lookup"><span data-stu-id="99deb-172">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>  
  
2.  <span data-ttu-id="99deb-173">Fügen Sie die folgenden <xref:System.Windows.UIElement.OnGiveFeedback%2A> überschreiben, um eine Klassenbehandlung für das Bereitstellen der <xref:System.Windows.UIElement.GiveFeedback> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="99deb-173">Add the following <xref:System.Windows.UIElement.OnGiveFeedback%2A> override to provide class handling for the <xref:System.Windows.UIElement.GiveFeedback> event.</span></span>  
  
     [!code-csharp[DragDropWalkthrough#OnGiveFeedback](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ongivefeedback)]
     [!code-vb[DragDropWalkthrough#OnGiveFeedback](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ongivefeedback)]  
  
     <span data-ttu-id="99deb-174">Dies <xref:System.Windows.UIElement.OnGiveFeedback%2A> -Überschreibung führt die folgenden Aufgaben:</span><span class="sxs-lookup"><span data-stu-id="99deb-174">This <xref:System.Windows.UIElement.OnGiveFeedback%2A> override performs the following tasks:</span></span>  
  
    -   <span data-ttu-id="99deb-175">Überprüft die <xref:System.Windows.GiveFeedbackEventArgs.Effects%2A> , in des Ablageziels festgelegte, Werte <xref:System.Windows.UIElement.DragOver> -Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="99deb-175">Checks the <xref:System.Windows.GiveFeedbackEventArgs.Effects%2A> values that are set in the drop target's <xref:System.Windows.UIElement.DragOver> event handler.</span></span>  
  
    -   <span data-ttu-id="99deb-176">Legt einen benutzerdefinierten Cursor auf der Grundlage der <xref:System.Windows.GiveFeedbackEventArgs.Effects%2A> Wert.</span><span class="sxs-lookup"><span data-stu-id="99deb-176">Sets a custom cursor based on the <xref:System.Windows.GiveFeedbackEventArgs.Effects%2A> value.</span></span> <span data-ttu-id="99deb-177">Der Cursor soll visuelles Feedback an den Benutzer geben, welche Auswirkungen das Ablegen der Daten hat.</span><span class="sxs-lookup"><span data-stu-id="99deb-177">The cursor is intended to give visual feedback to the user about what effect dropping the data will have.</span></span>  
  
3.  <span data-ttu-id="99deb-178">Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="99deb-178">Press F5 to build and run the application.</span></span>  
  
4.  <span data-ttu-id="99deb-179">Ziehen Sie eines der Kreis über die Bereiche, die den anderen Kreis Steuerelemente und die <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="99deb-179">Drag one of the Circle controls over the panels, the other Circle, and the <xref:System.Windows.Controls.TextBox>.</span></span> <span data-ttu-id="99deb-180">Beachten Sie, dass die Cursor jetzt die benutzerdefinierten Cursor, die Sie angegeben haben sind, in der <xref:System.Windows.UIElement.OnGiveFeedback%2A> außer Kraft setzen.</span><span class="sxs-lookup"><span data-stu-id="99deb-180">Notice that the cursors are now the custom cursors that you specified in the <xref:System.Windows.UIElement.OnGiveFeedback%2A> override.</span></span>  
  
     <span data-ttu-id="99deb-181">![Drag & Drop mit benutzerdefiniertem Cursor](../../../../docs/framework/wpf/advanced/media/dragdrop-customcursor.png "DragDrop_CustomCursor")</span><span class="sxs-lookup"><span data-stu-id="99deb-181">![Drag and drop with custom cursors](../../../../docs/framework/wpf/advanced/media/dragdrop-customcursor.png "DragDrop_CustomCursor")</span></span>  
  
5.  <span data-ttu-id="99deb-182">Wählen Sie den Text `green` aus der <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="99deb-182">Select the text `green` from the <xref:System.Windows.Controls.TextBox>.</span></span>  
  
6.  <span data-ttu-id="99deb-183">Ziehen Sie den Text `green` auf ein Kreis-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="99deb-183">Drag the `green` text to a Circle control.</span></span> <span data-ttu-id="99deb-184">Beachten Sie, dass die standardmäßigen Cursor angezeigt werden, um die Auswirkungen des Drag & Drop-Vorgangs anzugeben.</span><span class="sxs-lookup"><span data-stu-id="99deb-184">Notice that the default cursors are shown to indicate the effects of the drag-and-drop operation.</span></span> <span data-ttu-id="99deb-185">Der Feedbackcursor wird immer durch die Quelle des Ziehvorgangs festgelegt.</span><span class="sxs-lookup"><span data-stu-id="99deb-185">The feedback cursor is always set by the drag source.</span></span>  
  
## <a name="implementing-drop-target-events-in-the-user-control"></a><span data-ttu-id="99deb-186">Implementieren der Ereignisse des Ablageziels im Benutzersteuerelement</span><span class="sxs-lookup"><span data-stu-id="99deb-186">Implementing Drop Target Events in the User Control</span></span>  
 <span data-ttu-id="99deb-187">In diesem Abschnitt geben Sie an, dass das Benutzersteuerelement ein Ablageziel ist, überschreiben die Methoden, die das Benutzersteuerelement befähigen, ein Ablageziel sein und verarbeiten die Daten, die darauf abgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="99deb-187">In this section, you will specify that the user control is a drop target, override the methods that enable the user control to be a drop target, and process the data that is dropped on it.</span></span>  
  
### <a name="to-enable-the-user-control-to-be-a-drop-target"></a><span data-ttu-id="99deb-188">So konfigurieren Sie das Benutzersteuerelement als Ziel eines Ablegevorgangs</span><span class="sxs-lookup"><span data-stu-id="99deb-188">To enable the user control to be a drop target</span></span>  
  
1.  <span data-ttu-id="99deb-189">Öffnen Sie Circle.xaml.</span><span class="sxs-lookup"><span data-stu-id="99deb-189">Open Circle.xaml.</span></span>  
  
2.  <span data-ttu-id="99deb-190">Im öffnenden <xref:System.Windows.Controls.UserControl> markieren, fügen Sie der <xref:System.Windows.UIElement.AllowDrop%2A> Eigenschaft, und legen Sie ihn auf `true`.</span><span class="sxs-lookup"><span data-stu-id="99deb-190">In the opening <xref:System.Windows.Controls.UserControl> tag, add the <xref:System.Windows.UIElement.AllowDrop%2A> property and set it to `true`.</span></span>  
  
     [!code-xaml[DragDropWalkthrough#UCTagXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml#uctagxaml)]  
  
 <span data-ttu-id="99deb-191">Die <xref:System.Windows.UIElement.OnDrop%2A> Methode wird aufgerufen, wenn die <xref:System.Windows.UIElement.AllowDrop%2A> -Eigenschaftensatz auf `true` und Daten aus der Quelle des Ziehvorgangs auf das Kreis-Steuerelement abgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="99deb-191">The <xref:System.Windows.UIElement.OnDrop%2A> method is called when the <xref:System.Windows.UIElement.AllowDrop%2A> property is set to `true` and data from the drag source is dropped on the Circle user control.</span></span> <span data-ttu-id="99deb-192">In dieser Methode verarbeiten Sie die Daten, die abgelegt wurden und wenden sie auf den Kreis an.</span><span class="sxs-lookup"><span data-stu-id="99deb-192">In this method, you will process the data that was dropped and apply the data to the Circle.</span></span>  
  
### <a name="to-process-the-dropped-data"></a><span data-ttu-id="99deb-193">So verarbeiten Sie die abgelegten Daten</span><span class="sxs-lookup"><span data-stu-id="99deb-193">To process the dropped data</span></span>  
  
1.  <span data-ttu-id="99deb-194">Öffnen Sie "Circle.Xaml.cs" oder "Circle.Xaml.vb".</span><span class="sxs-lookup"><span data-stu-id="99deb-194">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>  
  
2.  <span data-ttu-id="99deb-195">Fügen Sie die folgenden <xref:System.Windows.UIElement.OnDrop%2A> überschreiben, um eine Klassenbehandlung für das Bereitstellen der <xref:System.Windows.UIElement.Drop> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="99deb-195">Add the following <xref:System.Windows.UIElement.OnDrop%2A> override to provide class handling for the <xref:System.Windows.UIElement.Drop> event.</span></span>  
  
     [!code-csharp[DragDropWalkthrough#OnDrop](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondrop)]
     [!code-vb[DragDropWalkthrough#OnDrop](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondrop)]  
  
     <span data-ttu-id="99deb-196">Dies <xref:System.Windows.UIElement.OnDrop%2A> -Überschreibung führt die folgenden Aufgaben:</span><span class="sxs-lookup"><span data-stu-id="99deb-196">This <xref:System.Windows.UIElement.OnDrop%2A> override performs the following tasks:</span></span>  
  
    -   <span data-ttu-id="99deb-197">Verwendet die <xref:System.Windows.DataObject.GetDataPresent%2A> Methode zum Überprüfen, ob die gezogenen Daten ein Zeichenfolgenobjekt enthalten.</span><span class="sxs-lookup"><span data-stu-id="99deb-197">Uses the <xref:System.Windows.DataObject.GetDataPresent%2A> method to check if the dragged data contains a string object.</span></span>  
  
    -   <span data-ttu-id="99deb-198">Verwendet die <xref:System.Windows.DataObject.GetData%2A> Methode, um die Zeichenfolgendaten zu extrahieren, wenn es vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="99deb-198">Uses the <xref:System.Windows.DataObject.GetData%2A> method to extract the string data if it is present.</span></span>  
  
    -   <span data-ttu-id="99deb-199">Verwendet eine <xref:System.Windows.Media.BrushConverter> versuchen, konvertieren Sie die Zeichenfolge, die eine <xref:System.Windows.Media.Brush>.</span><span class="sxs-lookup"><span data-stu-id="99deb-199">Uses a <xref:System.Windows.Media.BrushConverter> to try to convert the string to a <xref:System.Windows.Media.Brush>.</span></span>  
  
    -   <span data-ttu-id="99deb-200">Wenn die Konvertierung erfolgreich ist, gilt den Pinsel, der <xref:System.Windows.Shapes.Shape.Fill%2A> von der <xref:System.Windows.Shapes.Ellipse> , die die Benutzeroberfläche des Kreis-Steuerelements bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="99deb-200">If the conversion is successful, applies the brush to the <xref:System.Windows.Shapes.Shape.Fill%2A> of the <xref:System.Windows.Shapes.Ellipse> that provides the UI of the Circle control.</span></span>  
  
    -   <span data-ttu-id="99deb-201">Markiert die <xref:System.Windows.UIElement.Drop> Ereignis als behandelt.</span><span class="sxs-lookup"><span data-stu-id="99deb-201">Marks the <xref:System.Windows.UIElement.Drop> event as handled.</span></span> <span data-ttu-id="99deb-202">Sie sollten das Drop-Ereignis als behandelt kennzeichnen, damit andere Elemente, die dieses Ereignis empfangen, wissen, dass das Kreis-Steuerelement es behandelt hat.</span><span class="sxs-lookup"><span data-stu-id="99deb-202">You should mark the drop event as handled so that other elements that receive this event know that the Circle user control handled it.</span></span>  
  
3.  <span data-ttu-id="99deb-203">Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="99deb-203">Press F5 to build and run the application.</span></span>  
  
4.  <span data-ttu-id="99deb-204">Wählen Sie den Text `green` in die <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="99deb-204">Select the text `green` in the <xref:System.Windows.Controls.TextBox>.</span></span>  
  
5.  <span data-ttu-id="99deb-205">Ziehen Sie den Text auf ein Kreis-Steuerelement, und legen Sie ihn ab.</span><span class="sxs-lookup"><span data-stu-id="99deb-205">Drag the text to a Circle control and drop it.</span></span> <span data-ttu-id="99deb-206">Der Kreis ändert sich von Blau in Grün.</span><span class="sxs-lookup"><span data-stu-id="99deb-206">The Circle changes from blue to green.</span></span>  
  
     <span data-ttu-id="99deb-207">![Konvertieren einer Zeichenfolge in einen Pinsel](../../../../docs/framework/wpf/advanced/media/dragdrop-dropgreentext.png "DragDrop_DropGreenText")</span><span class="sxs-lookup"><span data-stu-id="99deb-207">![Convert a string to a brush](../../../../docs/framework/wpf/advanced/media/dragdrop-dropgreentext.png "DragDrop_DropGreenText")</span></span>  
  
6.  <span data-ttu-id="99deb-208">Geben Sie den Text `green` in die <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="99deb-208">Type the text `green` in the <xref:System.Windows.Controls.TextBox>.</span></span>  
  
7.  <span data-ttu-id="99deb-209">Wählen Sie den Text `gre` in die <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="99deb-209">Select the text `gre` in the <xref:System.Windows.Controls.TextBox>.</span></span>  
  
8.  <span data-ttu-id="99deb-210">Ziehen Sie ihn auf ein Kreis-Steuerelement, und legen Sie ihn ab.</span><span class="sxs-lookup"><span data-stu-id="99deb-210">Drag it to a Circle control and drop it.</span></span> <span data-ttu-id="99deb-211">Beachten Sie, dass sich zwar der Cursor ändert, um anzuzeigen, dass der Ablegevorgang zulässig ist, die Farbe des Kreises sich aber nicht ändert, da `gre` keine gültige Farbe ist.</span><span class="sxs-lookup"><span data-stu-id="99deb-211">Notice that the cursor changes to indicate that the drop is allowed, but the color of the Circle does not change because `gre` is not a valid color.</span></span>  
  
9. <span data-ttu-id="99deb-212">Ziehen Sie vom grünen Kreis-Steuerelement auf das blaue Kreis-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="99deb-212">Drag from the green Circle control and drop on the blue Circle control.</span></span> <span data-ttu-id="99deb-213">Der Kreis ändert sich von Blau in Grün.</span><span class="sxs-lookup"><span data-stu-id="99deb-213">The Circle changes from blue to green.</span></span> <span data-ttu-id="99deb-214">Beachten Sie, die angezeigte Cursor abhängig, ob davon die <xref:System.Windows.Controls.TextBox> oder der Kreis die Quelle des Ziehvorgangs.</span><span class="sxs-lookup"><span data-stu-id="99deb-214">Notice that which cursor is shown depends on whether the <xref:System.Windows.Controls.TextBox> or the Circle is the drag source.</span></span>  
  
 <span data-ttu-id="99deb-215">Festlegen der <xref:System.Windows.UIElement.AllowDrop%2A> Eigenschaft `true` und Verarbeiten der abgelegten Daten ist nur erforderlich, um ein Element, das Ziel eines Ablegevorgangs zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="99deb-215">Setting the <xref:System.Windows.UIElement.AllowDrop%2A> property to `true` and processing the dropped data is all that is required to enable an element to be a drop target.</span></span> <span data-ttu-id="99deb-216">Jedoch um eine bessere benutzererfahrung zu gewährleisten, sollten auch behandelt die <xref:System.Windows.UIElement.DragEnter>, <xref:System.Windows.UIElement.DragLeave>, und <xref:System.Windows.UIElement.DragOver> Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="99deb-216">However, to provide a better user experience, you should also handle the <xref:System.Windows.UIElement.DragEnter>, <xref:System.Windows.UIElement.DragLeave>, and <xref:System.Windows.UIElement.DragOver> events.</span></span> <span data-ttu-id="99deb-217">In diesen Ereignissen können Sie vor Ablage der Daten diese überprüfen und zusätzliches Feedback für den Benutzer bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="99deb-217">In these events, you can perform checks and provide additional feedback to the user before the data is dropped.</span></span>  
  
 <span data-ttu-id="99deb-218">Wenn Daten über das Kreis-Steuerelement gezogen werden, sollte das Steuerelement die Quelle des Ziehvorgangs darüber benachrichtigen, ob die darüber gezogenen Daten verarbeitet werden können.</span><span class="sxs-lookup"><span data-stu-id="99deb-218">When data is dragged over the Circle user control, the control should notify the drag source whether it can process the data that is being dragged.</span></span> <span data-ttu-id="99deb-219">Wenn das Steuerelement nicht weiß, wie die Daten zu verarbeiten sind, sollte es den Ablegevorgang ablehnen.</span><span class="sxs-lookup"><span data-stu-id="99deb-219">If the control does not know how to process the data, it should refuse the drop.</span></span> <span data-ttu-id="99deb-220">Behandeln Sie dazu die <xref:System.Windows.UIElement.DragOver> -Ereignis und legen die <xref:System.Windows.DragEventArgs.Effects%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="99deb-220">To do this, you will handle the <xref:System.Windows.UIElement.DragOver> event and set the <xref:System.Windows.DragEventArgs.Effects%2A> property.</span></span>  
  
### <a name="to-verify-that-the-data-drop-is-allowed"></a><span data-ttu-id="99deb-221">So stellen sie sicher, dass die Datenablage zulässig ist</span><span class="sxs-lookup"><span data-stu-id="99deb-221">To verify that the data drop is allowed</span></span>  
  
1.  <span data-ttu-id="99deb-222">Öffnen Sie "Circle.Xaml.cs" oder "Circle.Xaml.vb".</span><span class="sxs-lookup"><span data-stu-id="99deb-222">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>  
  
2.  <span data-ttu-id="99deb-223">Fügen Sie die folgenden <xref:System.Windows.UIElement.OnDragOver%2A> überschreiben, um eine Klassenbehandlung für das Bereitstellen der <xref:System.Windows.UIElement.DragOver> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="99deb-223">Add the following <xref:System.Windows.UIElement.OnDragOver%2A> override to provide class handling for the <xref:System.Windows.UIElement.DragOver> event.</span></span>  
  
     [!code-csharp[DragDropWalkthrough#OnDragOver](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondragover)]
     [!code-vb[DragDropWalkthrough#OnDragOver](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondragover)]  
  
     <span data-ttu-id="99deb-224">Dies <xref:System.Windows.UIElement.OnDragOver%2A> -Überschreibung führt die folgenden Aufgaben:</span><span class="sxs-lookup"><span data-stu-id="99deb-224">This <xref:System.Windows.UIElement.OnDragOver%2A> override performs the following tasks:</span></span>  
  
    -   <span data-ttu-id="99deb-225">Legt die <xref:System.Windows.DragEventArgs.Effects%2A>-Eigenschaft auf <xref:System.Windows.DragDropEffects.None> fest.</span><span class="sxs-lookup"><span data-stu-id="99deb-225">Sets the <xref:System.Windows.DragEventArgs.Effects%2A> property to <xref:System.Windows.DragDropEffects.None>.</span></span>  
  
    -   <span data-ttu-id="99deb-226">Führt die gleichen Überprüfungen, die in ausgeführt werden, die <xref:System.Windows.UIElement.OnDrop%2A> Methode, um zu bestimmen, ob das Kreis-Steuerelement die gezogenen Daten verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="99deb-226">Performs the same checks that are performed in the <xref:System.Windows.UIElement.OnDrop%2A> method to determine whether the Circle user control can process the dragged data.</span></span>  
  
    -   <span data-ttu-id="99deb-227">Legt fest, wenn das Benutzersteuerelement die Daten verarbeiten kann, die <xref:System.Windows.DragEventArgs.Effects%2A> Eigenschaft <xref:System.Windows.DragDropEffects.Copy> oder <xref:System.Windows.DragDropEffects.Move>.</span><span class="sxs-lookup"><span data-stu-id="99deb-227">If the user control can process the data, sets the <xref:System.Windows.DragEventArgs.Effects%2A> property to <xref:System.Windows.DragDropEffects.Copy> or <xref:System.Windows.DragDropEffects.Move>.</span></span>  
  
3.  <span data-ttu-id="99deb-228">Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="99deb-228">Press F5 to build and run the application.</span></span>  
  
4.  <span data-ttu-id="99deb-229">Wählen Sie den Text `gre` in die <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="99deb-229">Select the text `gre` in the <xref:System.Windows.Controls.TextBox>.</span></span>  
  
5.  <span data-ttu-id="99deb-230">Ziehen Sie den Text auf ein Kreis-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="99deb-230">Drag the text to a Circle control.</span></span> <span data-ttu-id="99deb-231">Beachten Sie, dass sich der Cursor jetzt so ändert, dass er anzeigt, dass der Ablegevorgang nicht zulässig ist, da `gre` keine gültige Farbe ist.</span><span class="sxs-lookup"><span data-stu-id="99deb-231">Notice that the cursor now changes to indicate that the drop is not allowed because `gre` is not a valid color.</span></span>  
  
 <span data-ttu-id="99deb-232">Sie können die Benutzerfunktionalität weiter verbessern, indem Sie eine Vorschau des Drop-Vorgangs anwenden.</span><span class="sxs-lookup"><span data-stu-id="99deb-232">You can further enhance the user experience by applying a preview of the drop operation.</span></span> <span data-ttu-id="99deb-233">Für das Kreis-Steuerelement, überschreiben Sie die <xref:System.Windows.UIElement.OnDragEnter%2A> und <xref:System.Windows.UIElement.OnDragLeave%2A> Methoden.</span><span class="sxs-lookup"><span data-stu-id="99deb-233">For the Circle user control, you will override the <xref:System.Windows.UIElement.OnDragEnter%2A> and <xref:System.Windows.UIElement.OnDragLeave%2A> methods.</span></span> <span data-ttu-id="99deb-234">Wenn die Daten gezogen werden, über dem Steuerelement, das die aktuelle Hintergrundfarbe <xref:System.Windows.Shapes.Shape.Fill%2A> wird in einer Platzhaltervariablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="99deb-234">When the data is dragged over the control, the current background <xref:System.Windows.Shapes.Shape.Fill%2A> is saved in a placeholder variable.</span></span> <span data-ttu-id="99deb-235">Klicken Sie dann die Zeichenfolge in einen Pinsel konvertiert und angewendet werden, um die <xref:System.Windows.Shapes.Ellipse> des Kreises bereitstellt Benutzeroberfläche.</span><span class="sxs-lookup"><span data-stu-id="99deb-235">The string is then converted to a brush and applied to the <xref:System.Windows.Shapes.Ellipse> that provides the Circle's UI.</span></span> <span data-ttu-id="99deb-236">Wenn die Daten aus den Kreis gezogen werden, ohne abgelegt zu werden, die ursprüngliche <xref:System.Windows.Shapes.Shape.Fill%2A> Wert erneut auf den Kreis angewendet.</span><span class="sxs-lookup"><span data-stu-id="99deb-236">If the data is dragged out of the Circle without being dropped, the original <xref:System.Windows.Shapes.Shape.Fill%2A> value is re-applied to the Circle.</span></span>  
  
### <a name="to-preview-the-effects-of-the-drag-and-drop-operation"></a><span data-ttu-id="99deb-237">So können Sie die Auswirkungen eines Drag & Drop-Vorgangs in der Vorschau anzeigen</span><span class="sxs-lookup"><span data-stu-id="99deb-237">To preview the effects of the drag-and-drop operation</span></span>  
  
1.  <span data-ttu-id="99deb-238">Öffnen Sie "Circle.Xaml.cs" oder "Circle.Xaml.vb".</span><span class="sxs-lookup"><span data-stu-id="99deb-238">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>  
  
2.  <span data-ttu-id="99deb-239">Deklarieren Sie in der Kreis-Klasse eine Private <xref:System.Windows.Media.Brush> Variable mit dem Namen `_previousFill` und initialisieren Sie es mit `null`.</span><span class="sxs-lookup"><span data-stu-id="99deb-239">In the Circle class, declare a private <xref:System.Windows.Media.Brush> variable named `_previousFill` and initialize it to `null`.</span></span>  
  
     [!code-csharp[DragDropWalkthrough#Brush](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#brush)]
     [!code-vb[DragDropWalkthrough#Brush](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#brush)]  
  
3.  <span data-ttu-id="99deb-240">Fügen Sie die folgenden <xref:System.Windows.UIElement.OnDragEnter%2A> überschreiben, um eine Klassenbehandlung für das Bereitstellen der <xref:System.Windows.UIElement.DragEnter> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="99deb-240">Add the following <xref:System.Windows.UIElement.OnDragEnter%2A> override to provide class handling for the <xref:System.Windows.UIElement.DragEnter> event.</span></span>  
  
     [!code-csharp[DragDropWalkthrough#OnDragEnter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondragenter)]
     [!code-vb[DragDropWalkthrough#OnDragEnter](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondragenter)]  
  
     <span data-ttu-id="99deb-241">Dies <xref:System.Windows.UIElement.OnDragEnter%2A> -Überschreibung führt die folgenden Aufgaben:</span><span class="sxs-lookup"><span data-stu-id="99deb-241">This <xref:System.Windows.UIElement.OnDragEnter%2A> override performs the following tasks:</span></span>  
  
    -   <span data-ttu-id="99deb-242">Speichert die <xref:System.Windows.Shapes.Shape.Fill%2A> Eigenschaft der <xref:System.Windows.Shapes.Ellipse> in die `_previousFill` Variable.</span><span class="sxs-lookup"><span data-stu-id="99deb-242">Saves the <xref:System.Windows.Shapes.Shape.Fill%2A> property of the <xref:System.Windows.Shapes.Ellipse> in the `_previousFill` variable.</span></span>  
  
    -   <span data-ttu-id="99deb-243">Führt die gleichen Überprüfungen, die in ausgeführt werden, die <xref:System.Windows.UIElement.OnDrop%2A> Methode, um zu bestimmen, ob die Daten können, um konvertiert werden eine <xref:System.Windows.Media.Brush>.</span><span class="sxs-lookup"><span data-stu-id="99deb-243">Performs the same checks that are performed in the <xref:System.Windows.UIElement.OnDrop%2A> method to determine whether the data can be converted to a <xref:System.Windows.Media.Brush>.</span></span>  
  
    -   <span data-ttu-id="99deb-244">Wenn die Daten auf eine gültige konvertiert werden <xref:System.Windows.Media.Brush>, wendet sie auf die <xref:System.Windows.Shapes.Shape.Fill%2A> von der <xref:System.Windows.Shapes.Ellipse>.</span><span class="sxs-lookup"><span data-stu-id="99deb-244">If the data is converted to a valid <xref:System.Windows.Media.Brush>, applies it to the <xref:System.Windows.Shapes.Shape.Fill%2A> of the <xref:System.Windows.Shapes.Ellipse>.</span></span>  
  
4.  <span data-ttu-id="99deb-245">Fügen Sie die folgenden <xref:System.Windows.UIElement.OnDragLeave%2A> überschreiben, um eine Klassenbehandlung für das Bereitstellen der <xref:System.Windows.UIElement.DragLeave> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="99deb-245">Add the following <xref:System.Windows.UIElement.OnDragLeave%2A> override to provide class handling for the <xref:System.Windows.UIElement.DragLeave> event.</span></span>  
  
     [!code-csharp[DragDropWalkthrough#OnDragLeave](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondragleave)]
     [!code-vb[DragDropWalkthrough#OnDragLeave](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondragleave)]  
  
     <span data-ttu-id="99deb-246">Dies <xref:System.Windows.UIElement.OnDragLeave%2A> -Überschreibung führt die folgenden Aufgaben:</span><span class="sxs-lookup"><span data-stu-id="99deb-246">This <xref:System.Windows.UIElement.OnDragLeave%2A> override performs the following tasks:</span></span>  
  
    -   <span data-ttu-id="99deb-247">Gilt die <xref:System.Windows.Media.Brush> gespeichert, der `_previousFill` Variable die <xref:System.Windows.Shapes.Shape.Fill%2A> von der <xref:System.Windows.Shapes.Ellipse> , der die Benutzeroberfläche des Kreis-Steuerelements bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="99deb-247">Applies the <xref:System.Windows.Media.Brush> saved in the `_previousFill` variable to the <xref:System.Windows.Shapes.Shape.Fill%2A> of the <xref:System.Windows.Shapes.Ellipse> that provides the UI of the Circle user control.</span></span>  
  
5.  <span data-ttu-id="99deb-248">Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="99deb-248">Press F5 to build and run the application.</span></span>  
  
6.  <span data-ttu-id="99deb-249">Wählen Sie den Text `green` in die <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="99deb-249">Select the text `green` in the <xref:System.Windows.Controls.TextBox>.</span></span>  
  
7.  <span data-ttu-id="99deb-250">Ziehen Sie den Text über ein Kreis-Steuerelement ohne ihn abzulegen.</span><span class="sxs-lookup"><span data-stu-id="99deb-250">Drag the text over a Circle control without dropping it.</span></span> <span data-ttu-id="99deb-251">Der Kreis ändert sich von Blau in Grün.</span><span class="sxs-lookup"><span data-stu-id="99deb-251">The Circle changes from blue to green.</span></span>  
  
     <span data-ttu-id="99deb-252">![Vorschau der Auswirkungen eines Drag & Drop-Vorgangs](../../../../docs/framework/wpf/advanced/media/dragdrop-previeweffects.png "DragDrop_PreviewEffects")</span><span class="sxs-lookup"><span data-stu-id="99deb-252">![Preview the effects of a drag&#45;and&#45;drop operation](../../../../docs/framework/wpf/advanced/media/dragdrop-previeweffects.png "DragDrop_PreviewEffects")</span></span>  
  
8.  <span data-ttu-id="99deb-253">Ziehen Sie den Text vom Kreis-Steuerelement weg.</span><span class="sxs-lookup"><span data-stu-id="99deb-253">Drag the text away from the Circle control.</span></span> <span data-ttu-id="99deb-254">Der Kreis ändert sich von Grün zurück in Blau.</span><span class="sxs-lookup"><span data-stu-id="99deb-254">The Circle changes from green back to blue.</span></span>  
  
## <a name="enabling-a-panel-to-receive-dropped-data"></a><span data-ttu-id="99deb-255">Einem Panel ermöglichen, abgelegte Daten zu empfangen</span><span class="sxs-lookup"><span data-stu-id="99deb-255">Enabling a Panel to Receive Dropped Data</span></span>  
 <span data-ttu-id="99deb-256">In diesem Abschnitt werden Sie den Panels, die die Kreis-Steuerelemente hosten, ermöglichen, als Ziele für gezogene Kreisdaten zu fungieren.</span><span class="sxs-lookup"><span data-stu-id="99deb-256">In this section, you will enable the panels that host the Circle user controls to act as drop targets for dragged Circle data.</span></span> <span data-ttu-id="99deb-257">Sie werden Code implementieren, der es Ihnen ermöglicht, einen Kreis von einem Panel in ein anderes zu verschieben, oder eine Kopie eines Kreis-Steuerelements zu erstellen, indem Sie die STRG-Taste gedrückt halten, während Sie einen Kreis ziehen und ablegen.</span><span class="sxs-lookup"><span data-stu-id="99deb-257">You will implement code that enables you to move a Circle from one panel to another, or to make a copy of a Circle control by holding down the CTRL key while dragging and dropping a Circle.</span></span>  
  
### <a name="to-enable-the-panel-to-be-a-drop-target"></a><span data-ttu-id="99deb-258">So konfigurieren Sie das Panel als Ziel eines Ablegevorgangs</span><span class="sxs-lookup"><span data-stu-id="99deb-258">To enable the panel to be a drop target</span></span>  
  
1.  <span data-ttu-id="99deb-259">Öffnen Sie „MainWindow.xaml“.</span><span class="sxs-lookup"><span data-stu-id="99deb-259">Open MainWindow.xaml.</span></span>  
  
2.  <span data-ttu-id="99deb-260">Siehe das folgende XAML, in den einzelnen der <xref:System.Windows.Controls.StackPanel> -Steuerelemente, Hinzufügen von Ereignishandlern für die <xref:System.Windows.UIElement.DragOver> und <xref:System.Windows.UIElement.Drop> Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="99deb-260">As shown in the following XAML, in each of the <xref:System.Windows.Controls.StackPanel> controls, add handlers for the <xref:System.Windows.UIElement.DragOver> and <xref:System.Windows.UIElement.Drop> events.</span></span> <span data-ttu-id="99deb-261">Name der <xref:System.Windows.UIElement.DragOver> -Ereignishandler `panel_DragOver`, und nennen Sie die <xref:System.Windows.UIElement.Drop> -Ereignishandler `panel_Drop`.</span><span class="sxs-lookup"><span data-stu-id="99deb-261">Name the <xref:System.Windows.UIElement.DragOver> event handler, `panel_DragOver`, and name the <xref:System.Windows.UIElement.Drop> event handler, `panel_Drop`.</span></span>  
  
     [!code-xaml[DragDropWalkthrough#PanelsXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/MainWindow.xaml#panelsxaml)]  
  
3.  <span data-ttu-id="99deb-262">Öffnen Sie „MainWindow.xaml.cs“ bzw. „MainWindow.xaml.vb“.</span><span class="sxs-lookup"><span data-stu-id="99deb-262">Open MainWindows.xaml.cs or MainWindow.xaml.vb.</span></span>  
  
4.  <span data-ttu-id="99deb-263">Fügen Sie den folgenden Code für die <xref:System.Windows.UIElement.DragOver> -Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="99deb-263">Add the following code for the <xref:System.Windows.UIElement.DragOver> event handler.</span></span>  
  
     [!code-csharp[DragDropWalkthrough#PanelDragOver](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/MainWindow.xaml.cs#paneldragover)]
     [!code-vb[DragDropWalkthrough#PanelDragOver](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/MainWindow.xaml.vb#paneldragover)]  
  
     <span data-ttu-id="99deb-264">Dies <xref:System.Windows.UIElement.DragOver> -Ereignishandler führt die folgenden Aufgaben:</span><span class="sxs-lookup"><span data-stu-id="99deb-264">This <xref:System.Windows.UIElement.DragOver> event handler performs the following tasks:</span></span>  
  
    -   <span data-ttu-id="99deb-265">Überprüft, ob die gezogenen Daten die "Objekt"-Daten enthält, die in gepackt wurde die <xref:System.Windows.DataObject> durch das Kreis-Steuerelement, und übergeben Sie im Aufruf von <xref:System.Windows.DragDrop.DoDragDrop%2A>.</span><span class="sxs-lookup"><span data-stu-id="99deb-265">Checks that the dragged data contains the "Object" data that was packaged in the <xref:System.Windows.DataObject> by the Circle user control and passed in the call to <xref:System.Windows.DragDrop.DoDragDrop%2A>.</span></span>  
  
    -   <span data-ttu-id="99deb-266">Überprüft, ob die STRG-Taste gedrückt wird, falls die „Objekt”-Daten vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="99deb-266">If the "Object" data is present, checks whether the CTRL key is pressed.</span></span>  
  
    -   <span data-ttu-id="99deb-267">Wenn die STRG-Taste gedrückt wird, legt die <xref:System.Windows.DragEventArgs.Effects%2A> Eigenschaft <xref:System.Windows.DragDropEffects.Copy>.</span><span class="sxs-lookup"><span data-stu-id="99deb-267">If the CTRL key is pressed, sets the <xref:System.Windows.DragEventArgs.Effects%2A> property to <xref:System.Windows.DragDropEffects.Copy>.</span></span> <span data-ttu-id="99deb-268">Andernfalls legen die <xref:System.Windows.DragEventArgs.Effects%2A> Eigenschaft <xref:System.Windows.DragDropEffects.Move>.</span><span class="sxs-lookup"><span data-stu-id="99deb-268">Otherwise, set the <xref:System.Windows.DragEventArgs.Effects%2A> property to <xref:System.Windows.DragDropEffects.Move>.</span></span>  
  
5.  <span data-ttu-id="99deb-269">Fügen Sie den folgenden Code für die <xref:System.Windows.UIElement.Drop> -Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="99deb-269">Add the following code for the <xref:System.Windows.UIElement.Drop> event handler.</span></span>  
  
     [!code-csharp[DragDropWalkthrough#PanelDrop](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/MainWindow.xaml.cs#paneldrop)]
     [!code-vb[DragDropWalkthrough#PanelDrop](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/MainWindow.xaml.vb#paneldrop)]  
  
     <span data-ttu-id="99deb-270">Dies <xref:System.Windows.UIElement.Drop> -Ereignishandler führt die folgenden Aufgaben:</span><span class="sxs-lookup"><span data-stu-id="99deb-270">This <xref:System.Windows.UIElement.Drop> event handler performs the following tasks:</span></span>  
  
    -   <span data-ttu-id="99deb-271">Überprüft, ob die <xref:System.Windows.UIElement.Drop> -Ereignis bereits behandelt wurde.</span><span class="sxs-lookup"><span data-stu-id="99deb-271">Checks whether the <xref:System.Windows.UIElement.Drop> event has already been handled.</span></span> <span data-ttu-id="99deb-272">Z. B. wenn ein Kreis auf einem anderen gelöscht wird Kreis die Handles der <xref:System.Windows.UIElement.Drop> -Ereignis, Sie möchten nicht im Bereich, der der Kreis zusätzlich behandeln enthält.</span><span class="sxs-lookup"><span data-stu-id="99deb-272">For instance, if a Circle is dropped on another Circle which handles the <xref:System.Windows.UIElement.Drop> event, you do not want the panel that contains the Circle to also handle it.</span></span>  
  
    -   <span data-ttu-id="99deb-273">Wenn die <xref:System.Windows.UIElement.Drop> -Ereignis nicht behandelt wird, überprüft, ob die STRG-Taste gedrückt wird.</span><span class="sxs-lookup"><span data-stu-id="99deb-273">If the <xref:System.Windows.UIElement.Drop> event is not handled, checks whether the CTRL key is pressed.</span></span>  
  
    -   <span data-ttu-id="99deb-274">Wenn die STRG-Taste, wenn gedrückt wird die <xref:System.Windows.UIElement.Drop> geschieht, wird eine Kopie des Kreises zu steuern, und fügen sie der <xref:System.Windows.Controls.Panel.Children%2A> Auflistung von der <xref:System.Windows.Controls.StackPanel>.</span><span class="sxs-lookup"><span data-stu-id="99deb-274">If the CTRL key is pressed when the <xref:System.Windows.UIElement.Drop> happens, makes a copy of the Circle control and add it to the <xref:System.Windows.Controls.Panel.Children%2A> collection of the <xref:System.Windows.Controls.StackPanel>.</span></span>  
  
    -   <span data-ttu-id="99deb-275">Wenn die STRG-Taste nicht gedrückt wird, verschiebt den Kreis aus der <xref:System.Windows.Controls.Panel.Children%2A> -Auflistung seines übergeordneten Panels, die <xref:System.Windows.Controls.Panel.Children%2A> -Auflistung des Panels, das er abgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="99deb-275">If the CTRL key is not pressed, moves the Circle from the <xref:System.Windows.Controls.Panel.Children%2A> collection of its parent panel to the <xref:System.Windows.Controls.Panel.Children%2A> collection of the panel that it was dropped on.</span></span>  
  
    -   <span data-ttu-id="99deb-276">Legt die <xref:System.Windows.DragEventArgs.Effects%2A> Eigenschaft benachrichtigt die <xref:System.Windows.DragDrop.DoDragDrop%2A> Methode gibt an, ob ein Verschiebe- oder Kopiervorgang-Vorgang ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="99deb-276">Sets the <xref:System.Windows.DragEventArgs.Effects%2A> property to notify the <xref:System.Windows.DragDrop.DoDragDrop%2A> method whether a move or copy operation was performed.</span></span>  
  
6.  <span data-ttu-id="99deb-277">Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="99deb-277">Press F5 to build and run the application.</span></span>  
  
7.  <span data-ttu-id="99deb-278">Wählen Sie den Text `green` aus der <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="99deb-278">Select the text `green` from the <xref:System.Windows.Controls.TextBox>.</span></span>  
  
8.  <span data-ttu-id="99deb-279">Ziehen Sie den Text auf ein Kreis-Steuerelement, und legen Sie ihn ab.</span><span class="sxs-lookup"><span data-stu-id="99deb-279">Drag the text over a Circle control and drop it.</span></span>  
  
9. <span data-ttu-id="99deb-280">Ziehen Sie ein Kreis-Steuerelement vom linken Panel in das rechte Panel und legen Sie es ab.</span><span class="sxs-lookup"><span data-stu-id="99deb-280">Drag a Circle control from the left panel to the right panel and drop it.</span></span> <span data-ttu-id="99deb-281">Der Kreis wird entfernt, von der <xref:System.Windows.Controls.Panel.Children%2A> Auflistung im linken Bereich und der Auflistung untergeordneter Elemente des rechten Panels hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="99deb-281">The Circle is removed from the <xref:System.Windows.Controls.Panel.Children%2A> collection of the left panel and added to the Children collection of the right panel.</span></span>  
  
10. <span data-ttu-id="99deb-282">Ziehen Sie ein Kreis-Steuerelement aus dem Panel, in dem es sich befindet, in das andere Panel und legen Sie es bei gedrückter STRG-Taste ab.</span><span class="sxs-lookup"><span data-stu-id="99deb-282">Drag a Circle control from the panel it is in to the other panel and drop it while pressing the CTRL key.</span></span> <span data-ttu-id="99deb-283">Der Kreis wird kopiert und die Kopie wird hinzugefügt, um die <xref:System.Windows.Controls.Panel.Children%2A> -Auflistung des empfangenden Panels.</span><span class="sxs-lookup"><span data-stu-id="99deb-283">The Circle is copied and the copy is added to the <xref:System.Windows.Controls.Panel.Children%2A> collection of the receiving panel.</span></span>  
  
     <span data-ttu-id="99deb-284">![Ziehen eines Kreises bei gedrückter STRG-Taste](../../../../docs/framework/wpf/advanced/media/dragdrop-paneldrop.png "DragDrop_PanelDrop")</span><span class="sxs-lookup"><span data-stu-id="99deb-284">![Dragging a Circle while pressing the CTRL key](../../../../docs/framework/wpf/advanced/media/dragdrop-paneldrop.png "DragDrop_PanelDrop")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99deb-285">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="99deb-285">See Also</span></span>  
 [<span data-ttu-id="99deb-286">Übersicht über Drag & Drop</span><span class="sxs-lookup"><span data-stu-id="99deb-286">Drag and Drop Overview</span></span>](../../../../docs/framework/wpf/advanced/drag-and-drop-overview.md)
