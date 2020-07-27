---
title: 'Exemplarische Vorgehensweise: Aktivieren der Drag & Drop-Funktion auf einem Benutzersteuerelement'
description: Erfahren Sie, wie Sie ein benutzerdefiniertes Benutzer Steuerelement erstellen, das in Windows Presentation Foundation an Drag & Drop-Datenübertragungen beteiligt sein kann.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- walkthrough [WPF], drag-and-drop
- drag-and-drop [WPF], walkthrough
ms.assetid: cc844419-1a77-4906-95d9-060d79107fc7
ms.openlocfilehash: 12ad47035a09995094014841b083062743fc2574
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2020
ms.locfileid: "87168277"
---
# <a name="walkthrough-enabling-drag-and-drop-on-a-user-control"></a><span data-ttu-id="fb23e-103">Exemplarische Vorgehensweise: Aktivieren der Drag & Drop-Funktion auf einem Benutzersteuerelement</span><span class="sxs-lookup"><span data-stu-id="fb23e-103">Walkthrough: Enabling Drag and Drop on a User Control</span></span>

<span data-ttu-id="fb23e-104">In dieser exemplarische Vorgehensweise wird veranschaulicht, wie man in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] ein benutzerdefiniertes Steuerelement erstellt, das Drag & Drop-Datenübertragung unterstützt.</span><span class="sxs-lookup"><span data-stu-id="fb23e-104">This walkthrough demonstrates how to create a custom user control that can participate in drag-and-drop data transfer in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].</span></span>

<span data-ttu-id="fb23e-105">In dieser exemplarischen Vorgehensweise erstellen Sie ein benutzerdefiniertes WPF <xref:System.Windows.Controls.UserControl> , das eine Kreisform darstellt.</span><span class="sxs-lookup"><span data-stu-id="fb23e-105">In this walkthrough, you will create a custom WPF <xref:System.Windows.Controls.UserControl> that represents a circle shape.</span></span> <span data-ttu-id="fb23e-106">Sie werden dabei Funktionen für das Steuerelement implementieren, welche die Übertragung von Daten durch Drag & Drop ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="fb23e-106">You will implement functionality on the control to enable data transfer through drag-and-drop.</span></span> <span data-ttu-id="fb23e-107">Wenn Sie z.B. von einem Kreis-Steuerelement auf ein anderes ziehen, werden die Füllfarbdaten vom Quellkreis auf den Zielkreis kopiert.</span><span class="sxs-lookup"><span data-stu-id="fb23e-107">For example, if you drag from one Circle control to another, the Fill color data is copied from the source Circle to the target.</span></span> <span data-ttu-id="fb23e-108">Wenn Sie von einem Kreis-Steuerelement zu einem ziehen <xref:System.Windows.Controls.TextBox> , wird die Zeichen folgen Darstellung der Füllfarbe in den kopiert <xref:System.Windows.Controls.TextBox> .</span><span class="sxs-lookup"><span data-stu-id="fb23e-108">If you drag from a Circle control to a <xref:System.Windows.Controls.TextBox>, the string representation of the Fill color is copied to the <xref:System.Windows.Controls.TextBox>.</span></span> <span data-ttu-id="fb23e-109">Außerdem erstellen Sie eine kleine Anwendung, die zwei Panel-Steuerelemente und ein-Element enthält <xref:System.Windows.Controls.TextBox> , um die Drag & amp; Drop-Funktionalität zu testen.</span><span class="sxs-lookup"><span data-stu-id="fb23e-109">You will also create a small application that contains two panel controls and a <xref:System.Windows.Controls.TextBox> to test the drag-and-drop functionality.</span></span> <span data-ttu-id="fb23e-110">Sie werden Code erstellen, der es den Panels ermöglicht, abgelegte Kreisdaten zu verarbeiten, sodass Sie Kreise aus der Auflistung untergeordneter Elemente von einem Panel zum anderen hin verschieben oder kopieren können.</span><span class="sxs-lookup"><span data-stu-id="fb23e-110">You will write code that enables the panels to process dropped Circle data, which will enable you to move or copy Circles from the Children collection of one panel to the other.</span></span>

<span data-ttu-id="fb23e-111">In dieser exemplarischen Vorgehensweise werden die folgenden Aufgaben veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="fb23e-111">This walkthrough illustrates the following tasks:</span></span>

- <span data-ttu-id="fb23e-112">Erstellen eines benutzerdefinierten Steuerelements.</span><span class="sxs-lookup"><span data-stu-id="fb23e-112">Create a custom user control.</span></span>

- <span data-ttu-id="fb23e-113">Konfigurieren des benutzerdefinierten Steuerelements, sodass es als Quelle eines Ziehvorgangs dienen kann.</span><span class="sxs-lookup"><span data-stu-id="fb23e-113">Enable the user control to be a drag source.</span></span>

- <span data-ttu-id="fb23e-114">Konfigurieren des benutzerdefinierten Steuerelements, sodass es als Ziel eines Ablegevorgangs dienen kann.</span><span class="sxs-lookup"><span data-stu-id="fb23e-114">Enable the user control to be a drop target.</span></span>

- <span data-ttu-id="fb23e-115">Konfigurieren eines Panels, sodass es von dem Benutzersteuerelement abgelegte Daten empfangen kann.</span><span class="sxs-lookup"><span data-stu-id="fb23e-115">Enable a panel to receive data dropped from the user control.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="fb23e-116">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="fb23e-116">Prerequisites</span></span>

<span data-ttu-id="fb23e-117">Für diese exemplarische Vorgehensweise benötigen Sie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="fb23e-117">You need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-the-application-project"></a><span data-ttu-id="fb23e-118">Erstellen des Anwendungs Projekts</span><span class="sxs-lookup"><span data-stu-id="fb23e-118">Create the Application Project</span></span>
 <span data-ttu-id="fb23e-119">In diesem Abschnitt erstellen Sie die Anwendungs Infrastruktur, die eine Hauptseite mit zwei Panels und enthält <xref:System.Windows.Controls.TextBox> .</span><span class="sxs-lookup"><span data-stu-id="fb23e-119">In this section, you will create the application infrastructure, which includes a main page with two panels and a <xref:System.Windows.Controls.TextBox>.</span></span>

1. <span data-ttu-id="fb23e-120">Erstellen Sie ein neues WPF-Anwendungsprojekt in Visual Basic oder Visual C# mit dem Namen `DragDropExample`.</span><span class="sxs-lookup"><span data-stu-id="fb23e-120">Create a new WPF Application project in Visual Basic or Visual C# named `DragDropExample`.</span></span> <span data-ttu-id="fb23e-121">Weitere Informationen finden Sie unter Exemplarische Vorgehensweise [: meine erste WPF-Desktop Anwendung](../getting-started/walkthrough-my-first-wpf-desktop-application.md).</span><span class="sxs-lookup"><span data-stu-id="fb23e-121">For more information, see [Walkthrough: My first WPF desktop application](../getting-started/walkthrough-my-first-wpf-desktop-application.md).</span></span>

2. <span data-ttu-id="fb23e-122">Öffnen Sie „MainWindow.xaml“.</span><span class="sxs-lookup"><span data-stu-id="fb23e-122">Open MainWindow.xaml.</span></span>

3. <span data-ttu-id="fb23e-123">Fügen Sie das folgende Markup zwischen den öffnenden und schließenden <xref:System.Windows.Controls.Grid> Tags hinzu.</span><span class="sxs-lookup"><span data-stu-id="fb23e-123">Add the following markup between the opening and closing <xref:System.Windows.Controls.Grid> tags.</span></span>

     <span data-ttu-id="fb23e-124">Dieses Markup erstellt die Benutzeroberfläche für die Testanwendung.</span><span class="sxs-lookup"><span data-stu-id="fb23e-124">This markup creates the user interface for the test application.</span></span>

     [!code-xaml[DragDropWalkthrough#PanelsStep1XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/SnippetWindow.xaml#panelsstep1xaml)]

## <a name="add-a-new-user-control-to-the-project"></a><span data-ttu-id="fb23e-125">Hinzufügen eines neuen Benutzer Steuer Elements zum Projekt</span><span class="sxs-lookup"><span data-stu-id="fb23e-125">Add a New User Control to the Project</span></span>
 <span data-ttu-id="fb23e-126">In diesem Abschnitt fügen Sie dem Projekt ein neues Benutzersteuerelement hinzu.</span><span class="sxs-lookup"><span data-stu-id="fb23e-126">In this section, you will add a new user control to the project.</span></span>

1. <span data-ttu-id="fb23e-127">Klicken Sie im Menü „Projekt” auf **Benutzersteuerelement hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="fb23e-127">On the Project menu, select **Add User Control**.</span></span>

2. <span data-ttu-id="fb23e-128">Ändern Sie im Dialogfeld **Neues Element hinzufügen** den Namen in `Circle.xaml` , und klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="fb23e-128">In the **Add New Item** dialog box, change the name to `Circle.xaml`, and click **Add**.</span></span>

     <span data-ttu-id="fb23e-129">Circle.XAML und der dazugehörige CodeBehind werden dem Projekt hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="fb23e-129">Circle.xaml and its code-behind is added to the project.</span></span>

3. <span data-ttu-id="fb23e-130">Öffnen Sie Circle.xaml.</span><span class="sxs-lookup"><span data-stu-id="fb23e-130">Open Circle.xaml.</span></span>

     <span data-ttu-id="fb23e-131">Diese Datei enthält die Benutzeroberflächenelemente des Benutzersteuerelements.</span><span class="sxs-lookup"><span data-stu-id="fb23e-131">This file will contain the user interface elements of the user control.</span></span>

4. <span data-ttu-id="fb23e-132">Fügen Sie dem Stamm das folgende Markup hinzu <xref:System.Windows.Controls.Grid> , um ein einfaches Benutzer Steuerelement mit einem blauen Kreis als Benutzeroberfläche zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="fb23e-132">Add the following markup to the root <xref:System.Windows.Controls.Grid> to create a simple user control that has a blue circle as its UI.</span></span>

     [!code-xaml[DragDropWalkthrough#EllipseXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml#ellipsexaml)]

5. <span data-ttu-id="fb23e-133">Öffnen Sie "Circle.Xaml.cs" oder "Circle.Xaml.vb".</span><span class="sxs-lookup"><span data-stu-id="fb23e-133">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>

6. <span data-ttu-id="fb23e-134">Fügen Sie in c# den folgenden Code nach dem Parameter losen Konstruktor hinzu, um einen Kopierkonstruktor zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="fb23e-134">In C#, add the following code after the parameterless constructor to create a copy constructor.</span></span> <span data-ttu-id="fb23e-135">Fügen Sie in Visual Basic den folgenden Code hinzu, um einen Parameter losen Konstruktor und einen Kopierkonstruktor zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="fb23e-135">In Visual Basic, add the following code to create both a parameterless constructor and a copy constructor.</span></span>

     <span data-ttu-id="fb23e-136">Fügen Sie eine Kopierkonstruktor-Methode in die CodeBehind-Datei ein, damit das Benutzersteuerelement kopiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="fb23e-136">In order to allow the user control to be copied, you add a copy constructor method in the code-behind file.</span></span> <span data-ttu-id="fb23e-137">Im vereinfachten kreisförmigen Benutzersteuerelement wollen wir nur die Füllfarbe und die Größe des Benutzersteuerelements kopieren.</span><span class="sxs-lookup"><span data-stu-id="fb23e-137">In the simplified Circle user control, you will only copy the Fill and the size of the of the user control.</span></span>

     [!code-csharp[DragDropWalkthrough#CopyCtor](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#copyctor)]
     [!code-vb[DragDropWalkthrough#CopyCtor](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#copyctor)]

## <a name="add-the-user-control-to-the-main-window"></a><span data-ttu-id="fb23e-138">Hinzufügen des Benutzer Steuer Elements zum Hauptfenster</span><span class="sxs-lookup"><span data-stu-id="fb23e-138">Add the user control to the main window</span></span>

1. <span data-ttu-id="fb23e-139">Öffnen Sie „MainWindow.xaml“.</span><span class="sxs-lookup"><span data-stu-id="fb23e-139">Open MainWindow.xaml.</span></span>

2. <span data-ttu-id="fb23e-140">Fügen Sie dem öffnenden Tag den folgenden XAML-Code hinzu <xref:System.Windows.Window> , um einen XML-Namespace Verweis auf die aktuelle Anwendung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="fb23e-140">Add the following XAML to the opening <xref:System.Windows.Window> tag to create an XML namespace reference to the current application.</span></span>

    ```xaml
    xmlns:local="clr-namespace:DragDropExample"
    ```

3. <span data-ttu-id="fb23e-141">Fügen Sie im ersten-Element <xref:System.Windows.Controls.StackPanel> den folgenden XAML-Code hinzu, um zwei Instanzen des Kreis-Benutzer Steuer Elements im ersten Panel zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="fb23e-141">In the first <xref:System.Windows.Controls.StackPanel>, add the following XAML to create two instances of the Circle user control in the first panel.</span></span>

     [!code-xaml[DragDropWalkthrough#CirclesXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/SnippetWindow.xaml#circlesxaml)]

     <span data-ttu-id="fb23e-142">Der vollständige XAML-Code für das Panel sieht folgendermaßen aus.</span><span class="sxs-lookup"><span data-stu-id="fb23e-142">The full XAML for the panel looks like the following.</span></span>

     [!code-xaml[DragDropWalkthrough#PanelsStep2XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/SnippetWindow.xaml#panelsstep2xaml)]

## <a name="implement-drag-source-events-in-the-user-control"></a><span data-ttu-id="fb23e-143">Implementieren von Drag Source-Ereignissen im Benutzer Steuerelement</span><span class="sxs-lookup"><span data-stu-id="fb23e-143">Implement Drag Source Events in the User Control</span></span>
 <span data-ttu-id="fb23e-144">In diesem Abschnitt überschreiben Sie die <xref:System.Windows.UIElement.OnMouseMove%2A> -Methode und initiieren den Drag & Drop-Vorgang.</span><span class="sxs-lookup"><span data-stu-id="fb23e-144">In this section, you will override the <xref:System.Windows.UIElement.OnMouseMove%2A> method and initiate the drag-and-drop operation.</span></span>

 <span data-ttu-id="fb23e-145">Wenn ein Drag-Vorgang gestartet wird (eine Maustaste gedrückt wird und die Maus bewegt wird), Verpacken Sie die Daten, die in eine übertragen werden sollen <xref:System.Windows.DataObject> .</span><span class="sxs-lookup"><span data-stu-id="fb23e-145">If a drag is started (a mouse button is pressed and the mouse is moved), you will package the data to be transferred into a <xref:System.Windows.DataObject>.</span></span> <span data-ttu-id="fb23e-146">In diesem Fall wird das Kreis-Steuerelement drei Datenelemente verpacken: eine Zeichenfolgendarstellung seiner Füllfarbe, eine double-Darstellung seiner Höhe und eine Kopie von sich selbst.</span><span class="sxs-lookup"><span data-stu-id="fb23e-146">In this case, the Circle control will package three data items; a string representation of its Fill color, a double representation of its height, and a copy of itself.</span></span>

### <a name="to-initiate-a-drag-and-drop-operation"></a><span data-ttu-id="fb23e-147">Initiieren eines Drag & Drop-Vorgangs</span><span class="sxs-lookup"><span data-stu-id="fb23e-147">To initiate a drag-and-drop operation</span></span>

1. <span data-ttu-id="fb23e-148">Öffnen Sie "Circle.Xaml.cs" oder "Circle.Xaml.vb".</span><span class="sxs-lookup"><span data-stu-id="fb23e-148">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>

2. <span data-ttu-id="fb23e-149">Fügen Sie die folgende <xref:System.Windows.UIElement.OnMouseMove%2A> außer Kraft Setzung hinzu, um Klassen Behandlung für das-Ereignis bereitzustellen <xref:System.Windows.UIElement.MouseMove></span><span class="sxs-lookup"><span data-stu-id="fb23e-149">Add the following <xref:System.Windows.UIElement.OnMouseMove%2A> override to provide class handling for the <xref:System.Windows.UIElement.MouseMove> event.</span></span>

     [!code-csharp[DragDropWalkthrough#OnMouseMove](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#onmousemove)]
     [!code-vb[DragDropWalkthrough#OnMouseMove](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#onmousemove)]

     <span data-ttu-id="fb23e-150">Diese <xref:System.Windows.UIElement.OnMouseMove%2A> außer Kraft Setzung führt die folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="fb23e-150">This <xref:System.Windows.UIElement.OnMouseMove%2A> override performs the following tasks:</span></span>

    - <span data-ttu-id="fb23e-151">Überprüft, ob die linke Maustaste gedrückt wird, während sich die Maus bewegt.</span><span class="sxs-lookup"><span data-stu-id="fb23e-151">Checks whether the left mouse button is pressed while the mouse is moving.</span></span>

    - <span data-ttu-id="fb23e-152">Verpackt die Zirkel Daten in eine <xref:System.Windows.DataObject> .</span><span class="sxs-lookup"><span data-stu-id="fb23e-152">Packages the Circle data into a <xref:System.Windows.DataObject>.</span></span> <span data-ttu-id="fb23e-153">In diesem Fall verpackt das Kreis-Steuerelement drei Datenelemente: eine Zeichenfolgendarstellung seiner Füllfarbe, eine double-Darstellung seiner Höhe und eine Kopie von sich selbst.</span><span class="sxs-lookup"><span data-stu-id="fb23e-153">In this case, the Circle control packages three data items; a string representation of its Fill color, a double representation of its height, and a copy of itself.</span></span>

    - <span data-ttu-id="fb23e-154">Ruft die statische- <xref:System.Windows.DragDrop.DoDragDrop%2A?displayProperty=nameWithType> Methode auf, um den Drag & Drop-Vorgang zu initiieren.</span><span class="sxs-lookup"><span data-stu-id="fb23e-154">Calls the static <xref:System.Windows.DragDrop.DoDragDrop%2A?displayProperty=nameWithType> method to initiate the drag-and-drop operation.</span></span> <span data-ttu-id="fb23e-155">Sie übergeben die folgenden drei Parameter an die- <xref:System.Windows.DragDrop.DoDragDrop%2A> Methode:</span><span class="sxs-lookup"><span data-stu-id="fb23e-155">You pass the following three parameters to the <xref:System.Windows.DragDrop.DoDragDrop%2A> method:</span></span>

        - <span data-ttu-id="fb23e-156">`dragSource`: Ein Verweis auf dieses Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="fb23e-156">`dragSource` – A reference to this control.</span></span>

        - <span data-ttu-id="fb23e-157">`data`– Die, die <xref:System.Windows.DataObject> im vorherigen Code erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="fb23e-157">`data` – The <xref:System.Windows.DataObject> created in the previous code.</span></span>

        - <span data-ttu-id="fb23e-158">`allowedEffects`– Die zulässigen Drag & Drop-Vorgänge, die oder sind <xref:System.Windows.DragDropEffects.Copy> <xref:System.Windows.DragDropEffects.Move> .</span><span class="sxs-lookup"><span data-stu-id="fb23e-158">`allowedEffects` – The allowed drag-and-drop operations, which are <xref:System.Windows.DragDropEffects.Copy> or <xref:System.Windows.DragDropEffects.Move>.</span></span>

3. <span data-ttu-id="fb23e-159">Drücken Sie **F5**, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="fb23e-159">Press **F5** to build and run the application.</span></span>

4. <span data-ttu-id="fb23e-160">Klicken Sie auf eines der Kreis-Steuerelemente, und ziehen Sie es über die Bereiche, den anderen Kreis und <xref:System.Windows.Controls.TextBox> .</span><span class="sxs-lookup"><span data-stu-id="fb23e-160">Click one of the Circle controls and drag it over the panels, the other Circle, and the <xref:System.Windows.Controls.TextBox>.</span></span> <span data-ttu-id="fb23e-161">Beim ziehen über das <xref:System.Windows.Controls.TextBox> wird der Cursor geändert, um eine Verschiebung anzugeben.</span><span class="sxs-lookup"><span data-stu-id="fb23e-161">When dragging over the <xref:System.Windows.Controls.TextBox>, the cursor changes to indicate a move.</span></span>

5. <span data-ttu-id="fb23e-162">Drücken Sie beim Ziehen eines Kreises über die <xref:System.Windows.Controls.TextBox> **STRG** -Taste.</span><span class="sxs-lookup"><span data-stu-id="fb23e-162">While dragging a Circle over the <xref:System.Windows.Controls.TextBox>, press the **Ctrl** key.</span></span> <span data-ttu-id="fb23e-163">Beachten Sie, wie sich der Cursor ändert, um einen Kopiervorgang anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="fb23e-163">Notice how the cursor changes to indicate a copy.</span></span>

6. <span data-ttu-id="fb23e-164">Ziehen Sie einen Kreis mit Drag und Drop auf die <xref:System.Windows.Controls.TextBox> .</span><span class="sxs-lookup"><span data-stu-id="fb23e-164">Drag and drop a Circle onto the <xref:System.Windows.Controls.TextBox>.</span></span> <span data-ttu-id="fb23e-165">Die Zeichen folgen Darstellung der Füllfarbe des Kreises wird an den angefügt <xref:System.Windows.Controls.TextBox> .</span><span class="sxs-lookup"><span data-stu-id="fb23e-165">The string representation of the Circle’s fill color is appended to the <xref:System.Windows.Controls.TextBox>.</span></span>

     <span data-ttu-id="fb23e-166">![Zeichenfolgendarstellung der Füllfarbe für den Kreis](./media/dragdrop-colorstring.png "DragDrop_ColorString")</span><span class="sxs-lookup"><span data-stu-id="fb23e-166">![String representation of Circle's fill color](./media/dragdrop-colorstring.png "DragDrop_ColorString")</span></span>

<span data-ttu-id="fb23e-167">Standardmäßig ändert sich der Cursor während eines Drag & Drop-Vorgangs, um anzuzeigen, welche Auswirkungen das Ablegen der Daten hat.</span><span class="sxs-lookup"><span data-stu-id="fb23e-167">By default, the cursor will change during a drag-and-drop operation to indicate what effect dropping the data will have.</span></span> <span data-ttu-id="fb23e-168">Sie können das Feedback an den Benutzer anpassen, indem Sie das <xref:System.Windows.UIElement.GiveFeedback> -Ereignis behandeln und einen anderen Cursor festlegen.</span><span class="sxs-lookup"><span data-stu-id="fb23e-168">You can customize the feedback given to the user by handling the <xref:System.Windows.UIElement.GiveFeedback> event and setting a different cursor.</span></span>

## <a name="give-feedback-to-the-user"></a><span data-ttu-id="fb23e-169">Feedback an den Benutzer senden</span><span class="sxs-lookup"><span data-stu-id="fb23e-169">Give feedback to the user</span></span>

1. <span data-ttu-id="fb23e-170">Öffnen Sie "Circle.Xaml.cs" oder "Circle.Xaml.vb".</span><span class="sxs-lookup"><span data-stu-id="fb23e-170">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>

2. <span data-ttu-id="fb23e-171">Fügen Sie die folgende <xref:System.Windows.UIElement.OnGiveFeedback%2A> außer Kraft Setzung hinzu, um Klassen Behandlung für das-Ereignis bereitzustellen <xref:System.Windows.UIElement.GiveFeedback></span><span class="sxs-lookup"><span data-stu-id="fb23e-171">Add the following <xref:System.Windows.UIElement.OnGiveFeedback%2A> override to provide class handling for the <xref:System.Windows.UIElement.GiveFeedback> event.</span></span>

     [!code-csharp[DragDropWalkthrough#OnGiveFeedback](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ongivefeedback)]
     [!code-vb[DragDropWalkthrough#OnGiveFeedback](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ongivefeedback)]

     <span data-ttu-id="fb23e-172">Diese <xref:System.Windows.UIElement.OnGiveFeedback%2A> außer Kraft Setzung führt die folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="fb23e-172">This <xref:System.Windows.UIElement.OnGiveFeedback%2A> override performs the following tasks:</span></span>

    - <span data-ttu-id="fb23e-173">Überprüft die <xref:System.Windows.GiveFeedbackEventArgs.Effects%2A> Werte, die im-Ereignishandler des Drop-Ziels festgelegt sind <xref:System.Windows.UIElement.DragOver> .</span><span class="sxs-lookup"><span data-stu-id="fb23e-173">Checks the <xref:System.Windows.GiveFeedbackEventArgs.Effects%2A> values that are set in the drop target's <xref:System.Windows.UIElement.DragOver> event handler.</span></span>

    - <span data-ttu-id="fb23e-174">Legt einen benutzerdefinierten Cursor basierend auf dem- <xref:System.Windows.GiveFeedbackEventArgs.Effects%2A> Wert fest.</span><span class="sxs-lookup"><span data-stu-id="fb23e-174">Sets a custom cursor based on the <xref:System.Windows.GiveFeedbackEventArgs.Effects%2A> value.</span></span> <span data-ttu-id="fb23e-175">Der Cursor soll visuelles Feedback an den Benutzer geben, welche Auswirkungen das Ablegen der Daten hat.</span><span class="sxs-lookup"><span data-stu-id="fb23e-175">The cursor is intended to give visual feedback to the user about what effect dropping the data will have.</span></span>

3. <span data-ttu-id="fb23e-176">Drücken Sie **F5**, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="fb23e-176">Press **F5** to build and run the application.</span></span>

4. <span data-ttu-id="fb23e-177">Ziehen Sie eines der Kreis-Steuerelemente auf die Bereiche, den anderen Kreis und <xref:System.Windows.Controls.TextBox> .</span><span class="sxs-lookup"><span data-stu-id="fb23e-177">Drag one of the Circle controls over the panels, the other Circle, and the <xref:System.Windows.Controls.TextBox>.</span></span> <span data-ttu-id="fb23e-178">Beachten Sie, dass die Cursor jetzt die benutzerdefinierten Cursor sind, die Sie in der Überschreibung angegeben haben <xref:System.Windows.UIElement.OnGiveFeedback%2A> .</span><span class="sxs-lookup"><span data-stu-id="fb23e-178">Notice that the cursors are now the custom cursors that you specified in the <xref:System.Windows.UIElement.OnGiveFeedback%2A> override.</span></span>

     <span data-ttu-id="fb23e-179">![Drag &amp; Drop mit benutzerdefiniertem Cursor](./media/dragdrop-customcursor.png "DragDrop_CustomCursor")</span><span class="sxs-lookup"><span data-stu-id="fb23e-179">![Drag and drop with custom cursors](./media/dragdrop-customcursor.png "DragDrop_CustomCursor")</span></span>

5. <span data-ttu-id="fb23e-180">Wählen Sie den Text `green` aus der aus <xref:System.Windows.Controls.TextBox> .</span><span class="sxs-lookup"><span data-stu-id="fb23e-180">Select the text `green` from the <xref:System.Windows.Controls.TextBox>.</span></span>

6. <span data-ttu-id="fb23e-181">Ziehen Sie den Text `green` auf ein Kreis-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="fb23e-181">Drag the `green` text to a Circle control.</span></span> <span data-ttu-id="fb23e-182">Beachten Sie, dass die standardmäßigen Cursor angezeigt werden, um die Auswirkungen des Drag & Drop-Vorgangs anzugeben.</span><span class="sxs-lookup"><span data-stu-id="fb23e-182">Notice that the default cursors are shown to indicate the effects of the drag-and-drop operation.</span></span> <span data-ttu-id="fb23e-183">Der Feedbackcursor wird immer durch die Quelle des Ziehvorgangs festgelegt.</span><span class="sxs-lookup"><span data-stu-id="fb23e-183">The feedback cursor is always set by the drag source.</span></span>

## <a name="implement-drop-target-events-in-the-user-control"></a><span data-ttu-id="fb23e-184">Implementieren von Drop Target-Ereignissen im Benutzer Steuerelement</span><span class="sxs-lookup"><span data-stu-id="fb23e-184">Implement Drop Target Events in the User Control</span></span>
 <span data-ttu-id="fb23e-185">In diesem Abschnitt geben Sie an, dass das Benutzersteuerelement ein Ablageziel ist, überschreiben die Methoden, die das Benutzersteuerelement befähigen, ein Ablageziel sein und verarbeiten die Daten, die darauf abgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="fb23e-185">In this section, you will specify that the user control is a drop target, override the methods that enable the user control to be a drop target, and process the data that is dropped on it.</span></span>

### <a name="to-enable-the-user-control-to-be-a-drop-target"></a><span data-ttu-id="fb23e-186">So konfigurieren Sie das Benutzersteuerelement als Ziel eines Ablegevorgangs</span><span class="sxs-lookup"><span data-stu-id="fb23e-186">To enable the user control to be a drop target</span></span>

1. <span data-ttu-id="fb23e-187">Öffnen Sie Circle.xaml.</span><span class="sxs-lookup"><span data-stu-id="fb23e-187">Open Circle.xaml.</span></span>

2. <span data-ttu-id="fb23e-188">Fügen Sie im öffnenden <xref:System.Windows.Controls.UserControl> Tag die <xref:System.Windows.UIElement.AllowDrop%2A> -Eigenschaft hinzu, und legen Sie Sie auf fest `true` .</span><span class="sxs-lookup"><span data-stu-id="fb23e-188">In the opening <xref:System.Windows.Controls.UserControl> tag, add the <xref:System.Windows.UIElement.AllowDrop%2A> property and set it to `true`.</span></span>

     [!code-xaml[DragDropWalkthrough#UCTagXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml#uctagxaml)]

<span data-ttu-id="fb23e-189">Die <xref:System.Windows.UIElement.OnDrop%2A> -Methode wird aufgerufen, wenn die <xref:System.Windows.UIElement.AllowDrop%2A> -Eigenschaft auf festgelegt ist `true` und Daten aus der Zieh Quelle im Kreis-Benutzer Steuerelement abgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="fb23e-189">The <xref:System.Windows.UIElement.OnDrop%2A> method is called when the <xref:System.Windows.UIElement.AllowDrop%2A> property is set to `true` and data from the drag source is dropped on the Circle user control.</span></span> <span data-ttu-id="fb23e-190">In dieser Methode verarbeiten Sie die Daten, die abgelegt wurden und wenden sie auf den Kreis an.</span><span class="sxs-lookup"><span data-stu-id="fb23e-190">In this method, you will process the data that was dropped and apply the data to the Circle.</span></span>

### <a name="to-process-the-dropped-data"></a><span data-ttu-id="fb23e-191">So verarbeiten Sie die abgelegten Daten</span><span class="sxs-lookup"><span data-stu-id="fb23e-191">To process the dropped data</span></span>

1. <span data-ttu-id="fb23e-192">Öffnen Sie "Circle.Xaml.cs" oder "Circle.Xaml.vb".</span><span class="sxs-lookup"><span data-stu-id="fb23e-192">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>

2. <span data-ttu-id="fb23e-193">Fügen Sie die folgende <xref:System.Windows.UIElement.OnDrop%2A> außer Kraft Setzung hinzu, um Klassen Behandlung für das-Ereignis bereitzustellen <xref:System.Windows.UIElement.Drop></span><span class="sxs-lookup"><span data-stu-id="fb23e-193">Add the following <xref:System.Windows.UIElement.OnDrop%2A> override to provide class handling for the <xref:System.Windows.UIElement.Drop> event.</span></span>

     [!code-csharp[DragDropWalkthrough#OnDrop](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondrop)]
     [!code-vb[DragDropWalkthrough#OnDrop](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondrop)]

     <span data-ttu-id="fb23e-194">Diese <xref:System.Windows.UIElement.OnDrop%2A> außer Kraft Setzung führt die folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="fb23e-194">This <xref:System.Windows.UIElement.OnDrop%2A> override performs the following tasks:</span></span>

    - <span data-ttu-id="fb23e-195">Verwendet die- <xref:System.Windows.DataObject.GetDataPresent%2A> Methode, um zu überprüfen, ob die gezogenen Daten ein Zeichen folgen Objekt enthalten.</span><span class="sxs-lookup"><span data-stu-id="fb23e-195">Uses the <xref:System.Windows.DataObject.GetDataPresent%2A> method to check if the dragged data contains a string object.</span></span>

    - <span data-ttu-id="fb23e-196">Verwendet die- <xref:System.Windows.DataObject.GetData%2A> Methode, um die Zeichen folgen Daten zu extrahieren, sofern diese vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="fb23e-196">Uses the <xref:System.Windows.DataObject.GetData%2A> method to extract the string data if it is present.</span></span>

    - <span data-ttu-id="fb23e-197">Verwendet einen <xref:System.Windows.Media.BrushConverter> , um zu versuchen, die Zeichenfolge in eine zu konvertieren <xref:System.Windows.Media.Brush> .</span><span class="sxs-lookup"><span data-stu-id="fb23e-197">Uses a <xref:System.Windows.Media.BrushConverter> to try to convert the string to a <xref:System.Windows.Media.Brush>.</span></span>

    - <span data-ttu-id="fb23e-198">Wenn die Konvertierung erfolgreich ist, wendet den Pinsel auf den des an, der <xref:System.Windows.Shapes.Shape.Fill%2A> <xref:System.Windows.Shapes.Ellipse> die Benutzeroberfläche des Kreis-Steuer Elements bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="fb23e-198">If the conversion is successful, applies the brush to the <xref:System.Windows.Shapes.Shape.Fill%2A> of the <xref:System.Windows.Shapes.Ellipse> that provides the UI of the Circle control.</span></span>

    - <span data-ttu-id="fb23e-199">Markiert das <xref:System.Windows.UIElement.Drop> Ereignis als behandelt.</span><span class="sxs-lookup"><span data-stu-id="fb23e-199">Marks the <xref:System.Windows.UIElement.Drop> event as handled.</span></span> <span data-ttu-id="fb23e-200">Sie sollten das Drop-Ereignis als behandelt kennzeichnen, damit andere Elemente, die dieses Ereignis empfangen, wissen, dass das Kreis-Steuerelement es behandelt hat.</span><span class="sxs-lookup"><span data-stu-id="fb23e-200">You should mark the drop event as handled so that other elements that receive this event know that the Circle user control handled it.</span></span>

3. <span data-ttu-id="fb23e-201">Drücken Sie **F5**, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="fb23e-201">Press **F5** to build and run the application.</span></span>

4. <span data-ttu-id="fb23e-202">Wählen Sie den Text `green` in aus <xref:System.Windows.Controls.TextBox> .</span><span class="sxs-lookup"><span data-stu-id="fb23e-202">Select the text `green` in the <xref:System.Windows.Controls.TextBox>.</span></span>

5. <span data-ttu-id="fb23e-203">Ziehen Sie den Text auf ein Kreis-Steuerelement, und legen Sie ihn ab.</span><span class="sxs-lookup"><span data-stu-id="fb23e-203">Drag the text to a Circle control and drop it.</span></span> <span data-ttu-id="fb23e-204">Der Kreis ändert sich von Blau in Grün.</span><span class="sxs-lookup"><span data-stu-id="fb23e-204">The Circle changes from blue to green.</span></span>

     <span data-ttu-id="fb23e-205">![Zeichenfolge in einen Pinsel konvertieren](./media/dragdrop-dropgreentext.png "DragDrop_DropGreenText")</span><span class="sxs-lookup"><span data-stu-id="fb23e-205">![Convert a string to a brush](./media/dragdrop-dropgreentext.png "DragDrop_DropGreenText")</span></span>

6. <span data-ttu-id="fb23e-206">Geben Sie den Text `green` in der ein <xref:System.Windows.Controls.TextBox> .</span><span class="sxs-lookup"><span data-stu-id="fb23e-206">Type the text `green` in the <xref:System.Windows.Controls.TextBox>.</span></span>

7. <span data-ttu-id="fb23e-207">Wählen Sie den Text `gre` in aus <xref:System.Windows.Controls.TextBox> .</span><span class="sxs-lookup"><span data-stu-id="fb23e-207">Select the text `gre` in the <xref:System.Windows.Controls.TextBox>.</span></span>

8. <span data-ttu-id="fb23e-208">Ziehen Sie ihn auf ein Kreis-Steuerelement, und legen Sie ihn ab.</span><span class="sxs-lookup"><span data-stu-id="fb23e-208">Drag it to a Circle control and drop it.</span></span> <span data-ttu-id="fb23e-209">Beachten Sie, dass sich zwar der Cursor ändert, um anzuzeigen, dass der Ablegevorgang zulässig ist, die Farbe des Kreises sich aber nicht ändert, da `gre` keine gültige Farbe ist.</span><span class="sxs-lookup"><span data-stu-id="fb23e-209">Notice that the cursor changes to indicate that the drop is allowed, but the color of the Circle does not change because `gre` is not a valid color.</span></span>

9. <span data-ttu-id="fb23e-210">Ziehen Sie vom grünen Kreis-Steuerelement auf das blaue Kreis-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="fb23e-210">Drag from the green Circle control and drop on the blue Circle control.</span></span> <span data-ttu-id="fb23e-211">Der Kreis ändert sich von Blau in Grün.</span><span class="sxs-lookup"><span data-stu-id="fb23e-211">The Circle changes from blue to green.</span></span> <span data-ttu-id="fb23e-212">Beachten Sie, dass der angezeigte Cursor davon abhängt, ob der <xref:System.Windows.Controls.TextBox> oder der Kreis die Zieh Quelle ist.</span><span class="sxs-lookup"><span data-stu-id="fb23e-212">Notice that which cursor is shown depends on whether the <xref:System.Windows.Controls.TextBox> or the Circle is the drag source.</span></span>

<span data-ttu-id="fb23e-213">Das Festlegen der <xref:System.Windows.UIElement.AllowDrop%2A> -Eigenschaft auf `true` und die Verarbeitung der gelöschten Daten ist alles, was erforderlich ist, um ein Element als Ablage Ziel zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="fb23e-213">Setting the <xref:System.Windows.UIElement.AllowDrop%2A> property to `true` and processing the dropped data is all that is required to enable an element to be a drop target.</span></span> <span data-ttu-id="fb23e-214">Um jedoch eine bessere Benutzer Leistung zu gewährleisten, sollten Sie auch die <xref:System.Windows.UIElement.DragEnter> <xref:System.Windows.UIElement.DragLeave> Ereignisse, und behandeln <xref:System.Windows.UIElement.DragOver> .</span><span class="sxs-lookup"><span data-stu-id="fb23e-214">However, to provide a better user experience, you should also handle the <xref:System.Windows.UIElement.DragEnter>, <xref:System.Windows.UIElement.DragLeave>, and <xref:System.Windows.UIElement.DragOver> events.</span></span> <span data-ttu-id="fb23e-215">In diesen Ereignissen können Sie vor Ablage der Daten diese überprüfen und zusätzliches Feedback für den Benutzer bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="fb23e-215">In these events, you can perform checks and provide additional feedback to the user before the data is dropped.</span></span>

<span data-ttu-id="fb23e-216">Wenn Daten über das Kreis-Steuerelement gezogen werden, sollte das Steuerelement die Quelle des Ziehvorgangs darüber benachrichtigen, ob die darüber gezogenen Daten verarbeitet werden können.</span><span class="sxs-lookup"><span data-stu-id="fb23e-216">When data is dragged over the Circle user control, the control should notify the drag source whether it can process the data that is being dragged.</span></span> <span data-ttu-id="fb23e-217">Wenn das Steuerelement nicht weiß, wie die Daten zu verarbeiten sind, sollte es den Ablegevorgang ablehnen.</span><span class="sxs-lookup"><span data-stu-id="fb23e-217">If the control does not know how to process the data, it should refuse the drop.</span></span> <span data-ttu-id="fb23e-218">Zu diesem Zweck behandeln Sie das <xref:System.Windows.UIElement.DragOver> -Ereignis und legen die- <xref:System.Windows.DragEventArgs.Effects%2A> Eigenschaft fest.</span><span class="sxs-lookup"><span data-stu-id="fb23e-218">To do this, you will handle the <xref:System.Windows.UIElement.DragOver> event and set the <xref:System.Windows.DragEventArgs.Effects%2A> property.</span></span>

### <a name="to-verify-that-the-data-drop-is-allowed"></a><span data-ttu-id="fb23e-219">So stellen sie sicher, dass die Datenablage zulässig ist</span><span class="sxs-lookup"><span data-stu-id="fb23e-219">To verify that the data drop is allowed</span></span>

1. <span data-ttu-id="fb23e-220">Öffnen Sie "Circle.Xaml.cs" oder "Circle.Xaml.vb".</span><span class="sxs-lookup"><span data-stu-id="fb23e-220">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>

2. <span data-ttu-id="fb23e-221">Fügen Sie die folgende <xref:System.Windows.UIElement.OnDragOver%2A> außer Kraft Setzung hinzu, um Klassen Behandlung für das-Ereignis bereitzustellen <xref:System.Windows.UIElement.DragOver></span><span class="sxs-lookup"><span data-stu-id="fb23e-221">Add the following <xref:System.Windows.UIElement.OnDragOver%2A> override to provide class handling for the <xref:System.Windows.UIElement.DragOver> event.</span></span>

     [!code-csharp[DragDropWalkthrough#OnDragOver](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondragover)]
     [!code-vb[DragDropWalkthrough#OnDragOver](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondragover)]

     <span data-ttu-id="fb23e-222">Diese <xref:System.Windows.UIElement.OnDragOver%2A> außer Kraft Setzung führt die folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="fb23e-222">This <xref:System.Windows.UIElement.OnDragOver%2A> override performs the following tasks:</span></span>

    - <span data-ttu-id="fb23e-223">Legt die <xref:System.Windows.DragEventArgs.Effects%2A>-Eigenschaft auf <xref:System.Windows.DragDropEffects.None> fest.</span><span class="sxs-lookup"><span data-stu-id="fb23e-223">Sets the <xref:System.Windows.DragEventArgs.Effects%2A> property to <xref:System.Windows.DragDropEffects.None>.</span></span>

    - <span data-ttu-id="fb23e-224">Führt die gleichen Überprüfungen durch, die in der-Methode ausgeführt werden <xref:System.Windows.UIElement.OnDrop%2A> , um zu bestimmen, ob das Kreis-Benutzer Steuerelement die gezogenen Daten verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="fb23e-224">Performs the same checks that are performed in the <xref:System.Windows.UIElement.OnDrop%2A> method to determine whether the Circle user control can process the dragged data.</span></span>

    - <span data-ttu-id="fb23e-225">Wenn das Benutzer Steuerelement die Daten verarbeiten kann, wird die- <xref:System.Windows.DragEventArgs.Effects%2A> Eigenschaft auf oder festgelegt <xref:System.Windows.DragDropEffects.Copy> <xref:System.Windows.DragDropEffects.Move> .</span><span class="sxs-lookup"><span data-stu-id="fb23e-225">If the user control can process the data, sets the <xref:System.Windows.DragEventArgs.Effects%2A> property to <xref:System.Windows.DragDropEffects.Copy> or <xref:System.Windows.DragDropEffects.Move>.</span></span>

3. <span data-ttu-id="fb23e-226">Drücken Sie **F5**, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="fb23e-226">Press **F5** to build and run the application.</span></span>

4. <span data-ttu-id="fb23e-227">Wählen Sie den Text `gre` in aus <xref:System.Windows.Controls.TextBox> .</span><span class="sxs-lookup"><span data-stu-id="fb23e-227">Select the text `gre` in the <xref:System.Windows.Controls.TextBox>.</span></span>

5. <span data-ttu-id="fb23e-228">Ziehen Sie den Text auf ein Kreis-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="fb23e-228">Drag the text to a Circle control.</span></span> <span data-ttu-id="fb23e-229">Beachten Sie, dass sich der Cursor jetzt so ändert, dass er anzeigt, dass der Ablegevorgang nicht zulässig ist, da `gre` keine gültige Farbe ist.</span><span class="sxs-lookup"><span data-stu-id="fb23e-229">Notice that the cursor now changes to indicate that the drop is not allowed because `gre` is not a valid color.</span></span>

 <span data-ttu-id="fb23e-230">Sie können die Benutzerfunktionalität weiter verbessern, indem Sie eine Vorschau des Drop-Vorgangs anwenden.</span><span class="sxs-lookup"><span data-stu-id="fb23e-230">You can further enhance the user experience by applying a preview of the drop operation.</span></span> <span data-ttu-id="fb23e-231">Für das Kreis-Benutzer Steuerelement überschreiben Sie die <xref:System.Windows.UIElement.OnDragEnter%2A> -Methode und die- <xref:System.Windows.UIElement.OnDragLeave%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="fb23e-231">For the Circle user control, you will override the <xref:System.Windows.UIElement.OnDragEnter%2A> and <xref:System.Windows.UIElement.OnDragLeave%2A> methods.</span></span> <span data-ttu-id="fb23e-232">Wenn die Daten über das Steuerelement gezogen werden, wird der aktuelle Hintergrund <xref:System.Windows.Shapes.Shape.Fill%2A> in einer Platzhalter Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="fb23e-232">When the data is dragged over the control, the current background <xref:System.Windows.Shapes.Shape.Fill%2A> is saved in a placeholder variable.</span></span> <span data-ttu-id="fb23e-233">Die Zeichenfolge wird dann in einen Pinsel konvertiert und auf das angewendet <xref:System.Windows.Shapes.Ellipse> , das die Benutzeroberfläche des Kreises bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="fb23e-233">The string is then converted to a brush and applied to the <xref:System.Windows.Shapes.Ellipse> that provides the Circle's UI.</span></span> <span data-ttu-id="fb23e-234">Wenn die Daten aus dem Kreis gezogen werden, ohne gelöscht zu werden, wird der ursprüngliche <xref:System.Windows.Shapes.Shape.Fill%2A> Wert erneut auf den Kreis angewendet.</span><span class="sxs-lookup"><span data-stu-id="fb23e-234">If the data is dragged out of the Circle without being dropped, the original <xref:System.Windows.Shapes.Shape.Fill%2A> value is re-applied to the Circle.</span></span>

### <a name="to-preview-the-effects-of-the-drag-and-drop-operation"></a><span data-ttu-id="fb23e-235">So können Sie die Auswirkungen eines Drag & Drop-Vorgangs in der Vorschau anzeigen</span><span class="sxs-lookup"><span data-stu-id="fb23e-235">To preview the effects of the drag-and-drop operation</span></span>

1. <span data-ttu-id="fb23e-236">Öffnen Sie "Circle.Xaml.cs" oder "Circle.Xaml.vb".</span><span class="sxs-lookup"><span data-stu-id="fb23e-236">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>

2. <span data-ttu-id="fb23e-237">Deklarieren Sie in der Klasse Circle eine private <xref:System.Windows.Media.Brush> Variable mit dem Namen, `_previousFill` und initialisieren Sie Sie mit `null` .</span><span class="sxs-lookup"><span data-stu-id="fb23e-237">In the Circle class, declare a private <xref:System.Windows.Media.Brush> variable named `_previousFill` and initialize it to `null`.</span></span>

     [!code-csharp[DragDropWalkthrough#Brush](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#brush)]
     [!code-vb[DragDropWalkthrough#Brush](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#brush)]

3. <span data-ttu-id="fb23e-238">Fügen Sie die folgende <xref:System.Windows.UIElement.OnDragEnter%2A> außer Kraft Setzung hinzu, um Klassen Behandlung für das-Ereignis bereitzustellen <xref:System.Windows.UIElement.DragEnter></span><span class="sxs-lookup"><span data-stu-id="fb23e-238">Add the following <xref:System.Windows.UIElement.OnDragEnter%2A> override to provide class handling for the <xref:System.Windows.UIElement.DragEnter> event.</span></span>

     [!code-csharp[DragDropWalkthrough#OnDragEnter](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondragenter)]
     [!code-vb[DragDropWalkthrough#OnDragEnter](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondragenter)]

     <span data-ttu-id="fb23e-239">Diese <xref:System.Windows.UIElement.OnDragEnter%2A> außer Kraft Setzung führt die folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="fb23e-239">This <xref:System.Windows.UIElement.OnDragEnter%2A> override performs the following tasks:</span></span>

    - <span data-ttu-id="fb23e-240">Speichert die- <xref:System.Windows.Shapes.Shape.Fill%2A> Eigenschaft des <xref:System.Windows.Shapes.Ellipse> in der `_previousFill` Variablen.</span><span class="sxs-lookup"><span data-stu-id="fb23e-240">Saves the <xref:System.Windows.Shapes.Shape.Fill%2A> property of the <xref:System.Windows.Shapes.Ellipse> in the `_previousFill` variable.</span></span>

    - <span data-ttu-id="fb23e-241">Führt die gleichen Überprüfungen durch, die in der-Methode ausgeführt werden <xref:System.Windows.UIElement.OnDrop%2A> , um zu bestimmen, ob die Daten in einen konvertiert werden können <xref:System.Windows.Media.Brush> .</span><span class="sxs-lookup"><span data-stu-id="fb23e-241">Performs the same checks that are performed in the <xref:System.Windows.UIElement.OnDrop%2A> method to determine whether the data can be converted to a <xref:System.Windows.Media.Brush>.</span></span>

    - <span data-ttu-id="fb23e-242">Wenn die Daten in einen gültigen konvertiert <xref:System.Windows.Media.Brush> werden, wendet ihn auf den <xref:System.Windows.Shapes.Shape.Fill%2A> von an <xref:System.Windows.Shapes.Ellipse> .</span><span class="sxs-lookup"><span data-stu-id="fb23e-242">If the data is converted to a valid <xref:System.Windows.Media.Brush>, applies it to the <xref:System.Windows.Shapes.Shape.Fill%2A> of the <xref:System.Windows.Shapes.Ellipse>.</span></span>

4. <span data-ttu-id="fb23e-243">Fügen Sie die folgende <xref:System.Windows.UIElement.OnDragLeave%2A> außer Kraft Setzung hinzu, um Klassen Behandlung für das-Ereignis bereitzustellen <xref:System.Windows.UIElement.DragLeave></span><span class="sxs-lookup"><span data-stu-id="fb23e-243">Add the following <xref:System.Windows.UIElement.OnDragLeave%2A> override to provide class handling for the <xref:System.Windows.UIElement.DragLeave> event.</span></span>

     [!code-csharp[DragDropWalkthrough#OnDragLeave](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondragleave)]
     [!code-vb[DragDropWalkthrough#OnDragLeave](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondragleave)]

     <span data-ttu-id="fb23e-244">Diese <xref:System.Windows.UIElement.OnDragLeave%2A> außer Kraft Setzung führt die folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="fb23e-244">This <xref:System.Windows.UIElement.OnDragLeave%2A> override performs the following tasks:</span></span>

    - <span data-ttu-id="fb23e-245">Wendet das <xref:System.Windows.Media.Brush> , das in der `_previousFill` Variablen gespeichert ist, auf die <xref:System.Windows.Shapes.Shape.Fill%2A> des an, das die Benutzer <xref:System.Windows.Shapes.Ellipse> Oberfläche des Kreis-Benutzer Steuer Elements bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="fb23e-245">Applies the <xref:System.Windows.Media.Brush> saved in the `_previousFill` variable to the <xref:System.Windows.Shapes.Shape.Fill%2A> of the <xref:System.Windows.Shapes.Ellipse> that provides the UI of the Circle user control.</span></span>

5. <span data-ttu-id="fb23e-246">Drücken Sie **F5**, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="fb23e-246">Press **F5** to build and run the application.</span></span>

6. <span data-ttu-id="fb23e-247">Wählen Sie den Text `green` in aus <xref:System.Windows.Controls.TextBox> .</span><span class="sxs-lookup"><span data-stu-id="fb23e-247">Select the text `green` in the <xref:System.Windows.Controls.TextBox>.</span></span>

7. <span data-ttu-id="fb23e-248">Ziehen Sie den Text über ein Kreis-Steuerelement ohne ihn abzulegen.</span><span class="sxs-lookup"><span data-stu-id="fb23e-248">Drag the text over a Circle control without dropping it.</span></span> <span data-ttu-id="fb23e-249">Der Kreis ändert sich von Blau in Grün.</span><span class="sxs-lookup"><span data-stu-id="fb23e-249">The Circle changes from blue to green.</span></span>

     <span data-ttu-id="fb23e-250">![Anzeigen einer Vorschau der Auswirkungen eines Drag-&#45;und&#45;Drop-Vorgangs](./media/dragdrop-previeweffects.png "DragDrop_PreviewEffects")</span><span class="sxs-lookup"><span data-stu-id="fb23e-250">![Preview the effects of a drag&#45;and&#45;drop operation](./media/dragdrop-previeweffects.png "DragDrop_PreviewEffects")</span></span>

8. <span data-ttu-id="fb23e-251">Ziehen Sie den Text vom Kreis-Steuerelement weg.</span><span class="sxs-lookup"><span data-stu-id="fb23e-251">Drag the text away from the Circle control.</span></span> <span data-ttu-id="fb23e-252">Der Kreis ändert sich von Grün zurück in Blau.</span><span class="sxs-lookup"><span data-stu-id="fb23e-252">The Circle changes from green back to blue.</span></span>

## <a name="enable-a-panel-to-receive-dropped-data"></a><span data-ttu-id="fb23e-253">Aktivieren eines Panels zum Empfangen von gelöschten Daten</span><span class="sxs-lookup"><span data-stu-id="fb23e-253">Enable a Panel to Receive Dropped Data</span></span>

<span data-ttu-id="fb23e-254">In diesem Abschnitt ermöglichen Sie den Bereichen, die die Kreis-Benutzer Steuerelemente hosten, als Dropziele für gezogene Kreis Daten zu fungieren.</span><span class="sxs-lookup"><span data-stu-id="fb23e-254">In this section, you enable the panels that host the Circle user controls to act as drop targets for dragged Circle data.</span></span> <span data-ttu-id="fb23e-255">Sie implementieren Code, der es Ihnen ermöglicht, einen Kreis von einem Bereich in einen anderen zu verschieben oder eine Kopie eines Kreis-Steuer Elements zu erstellen, indem Sie die **STRG** -Taste gedrückt halten, während Sie einen Kreis ziehen und ablegen.</span><span class="sxs-lookup"><span data-stu-id="fb23e-255">You will implement code that enables you to move a Circle from one panel to another, or to make a copy of a Circle control by holding down the **Ctrl** key while dragging and dropping a Circle.</span></span>

1. <span data-ttu-id="fb23e-256">Öffnen Sie „MainWindow.xaml“.</span><span class="sxs-lookup"><span data-stu-id="fb23e-256">Open MainWindow.xaml.</span></span>

2. <span data-ttu-id="fb23e-257">Fügen Sie, wie im folgenden XAML-Code gezeigt, <xref:System.Windows.Controls.StackPanel> Handler für das <xref:System.Windows.UIElement.DragOver> -Ereignis und das- <xref:System.Windows.UIElement.Drop> Ereignis hinzu.</span><span class="sxs-lookup"><span data-stu-id="fb23e-257">As shown in the following XAML, in each of the <xref:System.Windows.Controls.StackPanel> controls, add handlers for the <xref:System.Windows.UIElement.DragOver> and <xref:System.Windows.UIElement.Drop> events.</span></span> <span data-ttu-id="fb23e-258">Benennen Sie den <xref:System.Windows.UIElement.DragOver> Ereignishandler, `panel_DragOver` , und benennen Sie den <xref:System.Windows.UIElement.Drop> Ereignishandler `panel_Drop` .</span><span class="sxs-lookup"><span data-stu-id="fb23e-258">Name the <xref:System.Windows.UIElement.DragOver> event handler, `panel_DragOver`, and name the <xref:System.Windows.UIElement.Drop> event handler, `panel_Drop`.</span></span>

     [!code-xaml[DragDropWalkthrough#PanelsXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/MainWindow.xaml#panelsxaml)]

3. <span data-ttu-id="fb23e-259">Öffnen Sie „MainWindow.xaml.cs“ bzw. „MainWindow.xaml.vb“.</span><span class="sxs-lookup"><span data-stu-id="fb23e-259">Open MainWindows.xaml.cs or MainWindow.xaml.vb.</span></span>

4. <span data-ttu-id="fb23e-260">Fügen Sie den folgenden Code für den- <xref:System.Windows.UIElement.DragOver> Ereignishandler hinzu.</span><span class="sxs-lookup"><span data-stu-id="fb23e-260">Add the following code for the <xref:System.Windows.UIElement.DragOver> event handler.</span></span>

     [!code-csharp[DragDropWalkthrough#PanelDragOver](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/MainWindow.xaml.cs#paneldragover)]
     [!code-vb[DragDropWalkthrough#PanelDragOver](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/MainWindow.xaml.vb#paneldragover)]

     <span data-ttu-id="fb23e-261">Dieser <xref:System.Windows.UIElement.DragOver> Ereignishandler führt die folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="fb23e-261">This <xref:System.Windows.UIElement.DragOver> event handler performs the following tasks:</span></span>

    - <span data-ttu-id="fb23e-262">Überprüft, ob die gezogenen Daten die "Objekt"-Daten enthalten, die <xref:System.Windows.DataObject> vom Kreis-Benutzer Steuerelement in den gepackt und in den-Befehl übermittelt wurden <xref:System.Windows.DragDrop.DoDragDrop%2A> .</span><span class="sxs-lookup"><span data-stu-id="fb23e-262">Checks that the dragged data contains the "Object" data that was packaged in the <xref:System.Windows.DataObject> by the Circle user control and passed in the call to <xref:System.Windows.DragDrop.DoDragDrop%2A>.</span></span>

    - <span data-ttu-id="fb23e-263">Wenn die "Objekt"-Daten vorhanden sind, wird überprüft, ob die **STRG** -Taste gedrückt wird.</span><span class="sxs-lookup"><span data-stu-id="fb23e-263">If the "Object" data is present, checks whether the **Ctrl** key is pressed.</span></span>

    - <span data-ttu-id="fb23e-264">Wenn die **STRG** -Taste gedrückt wird, wird die- <xref:System.Windows.DragEventArgs.Effects%2A> Eigenschaft auf festgelegt <xref:System.Windows.DragDropEffects.Copy> .</span><span class="sxs-lookup"><span data-stu-id="fb23e-264">If the **Ctrl** key is pressed, sets the <xref:System.Windows.DragEventArgs.Effects%2A> property to <xref:System.Windows.DragDropEffects.Copy>.</span></span> <span data-ttu-id="fb23e-265">Legen Sie andernfalls die- <xref:System.Windows.DragEventArgs.Effects%2A> Eigenschaft auf fest <xref:System.Windows.DragDropEffects.Move> .</span><span class="sxs-lookup"><span data-stu-id="fb23e-265">Otherwise, set the <xref:System.Windows.DragEventArgs.Effects%2A> property to <xref:System.Windows.DragDropEffects.Move>.</span></span>

5. <span data-ttu-id="fb23e-266">Fügen Sie den folgenden Code für den- <xref:System.Windows.UIElement.Drop> Ereignishandler hinzu.</span><span class="sxs-lookup"><span data-stu-id="fb23e-266">Add the following code for the <xref:System.Windows.UIElement.Drop> event handler.</span></span>

     [!code-csharp[DragDropWalkthrough#PanelDrop](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/MainWindow.xaml.cs#paneldrop)]
     [!code-vb[DragDropWalkthrough#PanelDrop](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/MainWindow.xaml.vb#paneldrop)]

     <span data-ttu-id="fb23e-267">Dieser <xref:System.Windows.UIElement.Drop> Ereignishandler führt die folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="fb23e-267">This <xref:System.Windows.UIElement.Drop> event handler performs the following tasks:</span></span>

    - <span data-ttu-id="fb23e-268">Überprüft, ob das <xref:System.Windows.UIElement.Drop> Ereignis bereits behandelt wurde.</span><span class="sxs-lookup"><span data-stu-id="fb23e-268">Checks whether the <xref:System.Windows.UIElement.Drop> event has already been handled.</span></span> <span data-ttu-id="fb23e-269">Wenn beispielsweise ein Kreis in einem anderen Kreis abgelegt wird, der das-Ereignis behandelt, soll der Bereich, der <xref:System.Windows.UIElement.Drop> den Kreis enthält, nicht ebenfalls behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="fb23e-269">For instance, if a Circle is dropped on another Circle which handles the <xref:System.Windows.UIElement.Drop> event, you do not want the panel that contains the Circle to also handle it.</span></span>

    - <span data-ttu-id="fb23e-270">Wenn das <xref:System.Windows.UIElement.Drop> Ereignis nicht behandelt wird, überprüft, ob die **STRG** -Taste gedrückt ist.</span><span class="sxs-lookup"><span data-stu-id="fb23e-270">If the <xref:System.Windows.UIElement.Drop> event is not handled, checks whether the **Ctrl** key is pressed.</span></span>

    - <span data-ttu-id="fb23e-271">Wenn beim Auftreten der **STRG** -Taste gedrückt wird <xref:System.Windows.UIElement.Drop> , erstellt eine Kopie des Kreis-Steuer Elements und fügt es der-Auflistung <xref:System.Windows.Controls.Panel.Children%2A> von hinzu <xref:System.Windows.Controls.StackPanel> .</span><span class="sxs-lookup"><span data-stu-id="fb23e-271">If the **Ctrl** key is pressed when the <xref:System.Windows.UIElement.Drop> happens, makes a copy of the Circle control and add it to the <xref:System.Windows.Controls.Panel.Children%2A> collection of the <xref:System.Windows.Controls.StackPanel>.</span></span>

    - <span data-ttu-id="fb23e-272">Wenn die **STRG** -Taste nicht gedrückt wird, verschiebt den Kreis aus der-Auflistung <xref:System.Windows.Controls.Panel.Children%2A> des übergeordneten Bereichs in die-Auflistung <xref:System.Windows.Controls.Panel.Children%2A> des Panels, in dem Sie abgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="fb23e-272">If the **Ctrl** key is not pressed, moves the Circle from the <xref:System.Windows.Controls.Panel.Children%2A> collection of its parent panel to the <xref:System.Windows.Controls.Panel.Children%2A> collection of the panel that it was dropped on.</span></span>

    - <span data-ttu-id="fb23e-273">Legt die- <xref:System.Windows.DragEventArgs.Effects%2A> Eigenschaft fest, um die Methode zu benachrichtigen, ob ein Verschiebe- <xref:System.Windows.DragDrop.DoDragDrop%2A> oder Kopiervorgang ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="fb23e-273">Sets the <xref:System.Windows.DragEventArgs.Effects%2A> property to notify the <xref:System.Windows.DragDrop.DoDragDrop%2A> method whether a move or copy operation was performed.</span></span>

6. <span data-ttu-id="fb23e-274">Drücken Sie **F5**, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="fb23e-274">Press **F5** to build and run the application.</span></span>

7. <span data-ttu-id="fb23e-275">Wählen Sie den Text `green` aus der aus <xref:System.Windows.Controls.TextBox> .</span><span class="sxs-lookup"><span data-stu-id="fb23e-275">Select the text `green` from the <xref:System.Windows.Controls.TextBox>.</span></span>

8. <span data-ttu-id="fb23e-276">Ziehen Sie den Text auf ein Kreis-Steuerelement, und legen Sie ihn ab.</span><span class="sxs-lookup"><span data-stu-id="fb23e-276">Drag the text over a Circle control and drop it.</span></span>

9. <span data-ttu-id="fb23e-277">Ziehen Sie ein Kreis-Steuerelement vom linken Panel in das rechte Panel und legen Sie es ab.</span><span class="sxs-lookup"><span data-stu-id="fb23e-277">Drag a Circle control from the left panel to the right panel and drop it.</span></span> <span data-ttu-id="fb23e-278">Der Kreis wird aus der Auflistung <xref:System.Windows.Controls.Panel.Children%2A> des linken Bereichs entfernt und der Auflistung Children des rechten Panels hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="fb23e-278">The Circle is removed from the <xref:System.Windows.Controls.Panel.Children%2A> collection of the left panel and added to the Children collection of the right panel.</span></span>

10. <span data-ttu-id="fb23e-279">Ziehen Sie ein Kreis-Steuerelement aus dem Bereich in den anderen Bereich, und legen Sie es beim Drücken der **STRG** -Taste ab.</span><span class="sxs-lookup"><span data-stu-id="fb23e-279">Drag a Circle control from the panel it is in to the other panel and drop it while pressing the **Ctrl** key.</span></span> <span data-ttu-id="fb23e-280">Der Kreis wird kopiert, und die Kopie wird der Auflistung <xref:System.Windows.Controls.Panel.Children%2A> des Empfangsbereichs hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="fb23e-280">The Circle is copied and the copy is added to the <xref:System.Windows.Controls.Panel.Children%2A> collection of the receiving panel.</span></span>

     <span data-ttu-id="fb23e-281">![Ziehen eines Kreises beim Drücken der Strg-Taste](./media/dragdrop-paneldrop.png "DragDrop_PanelDrop")</span><span class="sxs-lookup"><span data-stu-id="fb23e-281">![Dragging a Circle while pressing the CTRL key](./media/dragdrop-paneldrop.png "DragDrop_PanelDrop")</span></span>

## <a name="see-also"></a><span data-ttu-id="fb23e-282">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fb23e-282">See also</span></span>

- [<span data-ttu-id="fb23e-283">Übersicht über Drag &amp; Drop</span><span class="sxs-lookup"><span data-stu-id="fb23e-283">Drag and Drop Overview</span></span>](drag-and-drop-overview.md)
