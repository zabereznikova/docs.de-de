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
ms.openlocfilehash: 172e49c2c255db4d24d2180f919b1305326b5e82
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2019
ms.locfileid: "70991806"
---
# <a name="walkthrough-enabling-drag-and-drop-on-a-user-control"></a><span data-ttu-id="7d445-102">Exemplarische Vorgehensweise: Aktivieren der Drag & Drop-Funktion auf einem Benutzersteuerelement</span><span class="sxs-lookup"><span data-stu-id="7d445-102">Walkthrough: Enabling Drag and Drop on a User Control</span></span>

<span data-ttu-id="7d445-103">In dieser exemplarische Vorgehensweise wird veranschaulicht, wie man in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] ein benutzerdefiniertes Steuerelement erstellt, das Drag & Drop-Datenübertragung unterstützt.</span><span class="sxs-lookup"><span data-stu-id="7d445-103">This walkthrough demonstrates how to create a custom user control that can participate in drag-and-drop data transfer in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].</span></span>

<span data-ttu-id="7d445-104">In dieser exemplarischen Vorgehensweise erstellen Sie ein benutzerdefiniertes <xref:System.Windows.Controls.UserControl> WPF, das eine Kreisform darstellt.</span><span class="sxs-lookup"><span data-stu-id="7d445-104">In this walkthrough, you will create a custom WPF <xref:System.Windows.Controls.UserControl> that represents a circle shape.</span></span> <span data-ttu-id="7d445-105">Sie werden dabei Funktionen für das Steuerelement implementieren, welche die Übertragung von Daten durch Drag & Drop ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="7d445-105">You will implement functionality on the control to enable data transfer through drag-and-drop.</span></span> <span data-ttu-id="7d445-106">Wenn Sie z.B. von einem Kreis-Steuerelement auf ein anderes ziehen, werden die Füllfarbdaten vom Quellkreis auf den Zielkreis kopiert.</span><span class="sxs-lookup"><span data-stu-id="7d445-106">For example, if you drag from one Circle control to another, the Fill color data is copied from the source Circle to the target.</span></span> <span data-ttu-id="7d445-107">Wenn Sie von einem Kreis-Steuerelement zu <xref:System.Windows.Controls.TextBox>einem ziehen, wird die Zeichen folgen Darstellung der Füllfarbe in <xref:System.Windows.Controls.TextBox>den kopiert.</span><span class="sxs-lookup"><span data-stu-id="7d445-107">If you drag from a Circle control to a <xref:System.Windows.Controls.TextBox>, the string representation of the Fill color is copied to the <xref:System.Windows.Controls.TextBox>.</span></span> <span data-ttu-id="7d445-108">Außerdem erstellen Sie eine kleine Anwendung, die zwei Panel-Steuerelemente und <xref:System.Windows.Controls.TextBox> ein-Element enthält, um die Drag & amp; Drop-Funktionalität zu testen.</span><span class="sxs-lookup"><span data-stu-id="7d445-108">You will also create a small application that contains two panel controls and a <xref:System.Windows.Controls.TextBox> to test the drag-and-drop functionality.</span></span> <span data-ttu-id="7d445-109">Sie werden Code erstellen, der es den Panels ermöglicht, abgelegte Kreisdaten zu verarbeiten, sodass Sie Kreise aus der Auflistung untergeordneter Elemente von einem Panel zum anderen hin verschieben oder kopieren können.</span><span class="sxs-lookup"><span data-stu-id="7d445-109">You will write code that enables the panels to process dropped Circle data, which will enable you to move or copy Circles from the Children collection of one panel to the other.</span></span>

<span data-ttu-id="7d445-110">In dieser exemplarischen Vorgehensweise werden die folgenden Aufgaben veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="7d445-110">This walkthrough illustrates the following tasks:</span></span>

- <span data-ttu-id="7d445-111">Erstellen eines benutzerdefinierten Steuerelements.</span><span class="sxs-lookup"><span data-stu-id="7d445-111">Create a custom user control.</span></span>

- <span data-ttu-id="7d445-112">Konfigurieren des benutzerdefinierten Steuerelements, sodass es als Quelle eines Ziehvorgangs dienen kann.</span><span class="sxs-lookup"><span data-stu-id="7d445-112">Enable the user control to be a drag source.</span></span>

- <span data-ttu-id="7d445-113">Konfigurieren des benutzerdefinierten Steuerelements, sodass es als Ziel eines Ablegevorgangs dienen kann.</span><span class="sxs-lookup"><span data-stu-id="7d445-113">Enable the user control to be a drop target.</span></span>

- <span data-ttu-id="7d445-114">Konfigurieren eines Panels, sodass es von dem Benutzersteuerelement abgelegte Daten empfangen kann.</span><span class="sxs-lookup"><span data-stu-id="7d445-114">Enable a panel to receive data dropped from the user control.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="7d445-115">Vorraussetzungen</span><span class="sxs-lookup"><span data-stu-id="7d445-115">Prerequisites</span></span>

<span data-ttu-id="7d445-116">Für diese exemplarische Vorgehensweise benötigen Sie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="7d445-116">You need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-the-application-project"></a><span data-ttu-id="7d445-117">Erstellen des Anwendungs Projekts</span><span class="sxs-lookup"><span data-stu-id="7d445-117">Create the Application Project</span></span>
 <span data-ttu-id="7d445-118">In diesem Abschnitt erstellen Sie die Anwendungs Infrastruktur, die eine Hauptseite mit zwei Panels und <xref:System.Windows.Controls.TextBox>enthält.</span><span class="sxs-lookup"><span data-stu-id="7d445-118">In this section, you will create the application infrastructure, which includes a main page with two panels and a <xref:System.Windows.Controls.TextBox>.</span></span>

1. <span data-ttu-id="7d445-119">Erstellen Sie ein neues WPF-Anwendungsprojekt in Visual Basic oder Visual C# mit dem Namen `DragDropExample`.</span><span class="sxs-lookup"><span data-stu-id="7d445-119">Create a new WPF Application project in Visual Basic or Visual C# named `DragDropExample`.</span></span> <span data-ttu-id="7d445-120">Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Meine erste WPF-Desktop](../getting-started/walkthrough-my-first-wpf-desktop-application.md)Anwendung.</span><span class="sxs-lookup"><span data-stu-id="7d445-120">For more information, see [Walkthrough: My first WPF desktop application](../getting-started/walkthrough-my-first-wpf-desktop-application.md).</span></span>

2. <span data-ttu-id="7d445-121">Öffnen Sie „MainWindow.xaml“.</span><span class="sxs-lookup"><span data-stu-id="7d445-121">Open MainWindow.xaml.</span></span>

3. <span data-ttu-id="7d445-122">Fügen Sie das folgende Markup zwischen den öffnenden <xref:System.Windows.Controls.Grid> und schließenden Tags hinzu.</span><span class="sxs-lookup"><span data-stu-id="7d445-122">Add the following markup between the opening and closing <xref:System.Windows.Controls.Grid> tags.</span></span>

     <span data-ttu-id="7d445-123">Dieses Markup erstellt die Benutzeroberfläche für die Testanwendung.</span><span class="sxs-lookup"><span data-stu-id="7d445-123">This markup creates the user interface for the test application.</span></span>

     [!code-xaml[DragDropWalkthrough#PanelsStep1XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/SnippetWindow.xaml#panelsstep1xaml)]

## <a name="add-a-new-user-control-to-the-project"></a><span data-ttu-id="7d445-124">Hinzufügen eines neuen Benutzer Steuer Elements zum Projekt</span><span class="sxs-lookup"><span data-stu-id="7d445-124">Add a New User Control to the Project</span></span>
 <span data-ttu-id="7d445-125">In diesem Abschnitt fügen Sie dem Projekt ein neues Benutzersteuerelement hinzu.</span><span class="sxs-lookup"><span data-stu-id="7d445-125">In this section, you will add a new user control to the project.</span></span>

1. <span data-ttu-id="7d445-126">Klicken Sie im Menü „Projekt” auf **Benutzersteuerelement hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="7d445-126">On the Project menu, select **Add User Control**.</span></span>

2. <span data-ttu-id="7d445-127">Ändern Sie im Dialogfeld **Neues Element hinzufügen** den Namen `Circle.xaml`in, und klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="7d445-127">In the **Add New Item** dialog box, change the name to `Circle.xaml`, and click **Add**.</span></span>

     <span data-ttu-id="7d445-128">Circle.XAML und der dazugehörige CodeBehind werden dem Projekt hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="7d445-128">Circle.xaml and its code-behind is added to the project.</span></span>

3. <span data-ttu-id="7d445-129">Öffnen Sie Circle.xaml.</span><span class="sxs-lookup"><span data-stu-id="7d445-129">Open Circle.xaml.</span></span>

     <span data-ttu-id="7d445-130">Diese Datei enthält die Benutzeroberflächenelemente des Benutzersteuerelements.</span><span class="sxs-lookup"><span data-stu-id="7d445-130">This file will contain the user interface elements of the user control.</span></span>

4. <span data-ttu-id="7d445-131">Fügen Sie dem Stamm das folgende Markup <xref:System.Windows.Controls.Grid> hinzu, um ein einfaches Benutzer Steuerelement mit einem blauen Kreis als Benutzeroberfläche zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="7d445-131">Add the following markup to the root <xref:System.Windows.Controls.Grid> to create a simple user control that has a blue circle as its UI.</span></span>

     [!code-xaml[DragDropWalkthrough#EllipseXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml#ellipsexaml)]

5. <span data-ttu-id="7d445-132">Öffnen Sie "Circle.Xaml.cs" oder "Circle.Xaml.vb".</span><span class="sxs-lookup"><span data-stu-id="7d445-132">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>

6. <span data-ttu-id="7d445-133">Fügen C#Sie in den folgenden Code nach dem Parameter losen Konstruktor hinzu, um einen Kopierkonstruktor zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="7d445-133">In C#, add the following code after the parameterless constructor to create a copy constructor.</span></span> <span data-ttu-id="7d445-134">Fügen Sie in Visual Basic den folgenden Code hinzu, um einen Parameter losen Konstruktor und einen Kopierkonstruktor zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="7d445-134">In Visual Basic, add the following code to create both a parameterless constructor and a copy constructor.</span></span>

     <span data-ttu-id="7d445-135">Fügen Sie eine Kopierkonstruktor-Methode in die CodeBehind-Datei ein, damit das Benutzersteuerelement kopiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="7d445-135">In order to allow the user control to be copied, you add a copy constructor method in the code-behind file.</span></span> <span data-ttu-id="7d445-136">Im vereinfachten kreisförmigen Benutzersteuerelement wollen wir nur die Füllfarbe und die Größe des Benutzersteuerelements kopieren.</span><span class="sxs-lookup"><span data-stu-id="7d445-136">In the simplified Circle user control, you will only copy the Fill and the size of the of the user control.</span></span>

     [!code-csharp[DragDropWalkthrough#CopyCtor](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#copyctor)]
     [!code-vb[DragDropWalkthrough#CopyCtor](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#copyctor)]

## <a name="add-the-user-control-to-the-main-window"></a><span data-ttu-id="7d445-137">Hinzufügen des Benutzer Steuer Elements zum Hauptfenster</span><span class="sxs-lookup"><span data-stu-id="7d445-137">Add the user control to the main window</span></span>

1. <span data-ttu-id="7d445-138">Öffnen Sie „MainWindow.xaml“.</span><span class="sxs-lookup"><span data-stu-id="7d445-138">Open MainWindow.xaml.</span></span>

2. <span data-ttu-id="7d445-139">Fügen Sie dem öffnenden <xref:System.Windows.Window> Tag den folgenden XAML-Code hinzu, um einen XML-Namespace Verweis auf die aktuelle Anwendung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="7d445-139">Add the following XAML to the opening <xref:System.Windows.Window> tag to create an XML namespace reference to the current application.</span></span>

    ```xaml
    xmlns:local="clr-namespace:DragDropExample"
    ```

3. <span data-ttu-id="7d445-140">Fügen Sie im <xref:System.Windows.Controls.StackPanel>ersten-Element den folgenden XAML-Code hinzu, um zwei Instanzen des Kreis-Benutzer Steuer Elements im ersten Panel zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="7d445-140">In the first <xref:System.Windows.Controls.StackPanel>, add the following XAML to create two instances of the Circle user control in the first panel.</span></span>

     [!code-xaml[DragDropWalkthrough#CirclesXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/SnippetWindow.xaml#circlesxaml)]

     <span data-ttu-id="7d445-141">Der vollständige XAML-Code für das Panel sieht folgendermaßen aus.</span><span class="sxs-lookup"><span data-stu-id="7d445-141">The full XAML for the panel looks like the following.</span></span>

     [!code-xaml[DragDropWalkthrough#PanelsStep2XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/SnippetWindow.xaml#panelsstep2xaml)]

## <a name="implement-drag-source-events-in-the-user-control"></a><span data-ttu-id="7d445-142">Implementieren von Drag Source-Ereignissen im Benutzer Steuerelement</span><span class="sxs-lookup"><span data-stu-id="7d445-142">Implement Drag Source Events in the User Control</span></span>
 <span data-ttu-id="7d445-143">In diesem Abschnitt überschreiben Sie die <xref:System.Windows.UIElement.OnMouseMove%2A> -Methode und initiieren den Drag & Drop-Vorgang.</span><span class="sxs-lookup"><span data-stu-id="7d445-143">In this section, you will override the <xref:System.Windows.UIElement.OnMouseMove%2A> method and initiate the drag-and-drop operation.</span></span>

 <span data-ttu-id="7d445-144">Wenn ein Drag-Vorgang gestartet wird (eine Maustaste gedrückt wird und die Maus bewegt wird), Verpacken Sie die Daten, die in eine <xref:System.Windows.DataObject>übertragen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="7d445-144">If a drag is started (a mouse button is pressed and the mouse is moved), you will package the data to be transferred into a <xref:System.Windows.DataObject>.</span></span> <span data-ttu-id="7d445-145">In diesem Fall wird das Kreis-Steuerelement drei Datenelemente verpacken: eine Zeichenfolgendarstellung seiner Füllfarbe, eine double-Darstellung seiner Höhe und eine Kopie von sich selbst.</span><span class="sxs-lookup"><span data-stu-id="7d445-145">In this case, the Circle control will package three data items; a string representation of its Fill color, a double representation of its height, and a copy of itself.</span></span>

### <a name="to-initiate-a-drag-and-drop-operation"></a><span data-ttu-id="7d445-146">Initiieren eines Drag & Drop-Vorgangs</span><span class="sxs-lookup"><span data-stu-id="7d445-146">To initiate a drag-and-drop operation</span></span>

1. <span data-ttu-id="7d445-147">Öffnen Sie "Circle.Xaml.cs" oder "Circle.Xaml.vb".</span><span class="sxs-lookup"><span data-stu-id="7d445-147">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>

2. <span data-ttu-id="7d445-148">Fügen Sie die <xref:System.Windows.UIElement.OnMouseMove%2A> folgende außer Kraft Setzung hinzu, um <xref:System.Windows.UIElement.MouseMove> Klassen Behandlung für das-Ereignis bereitzustellen</span><span class="sxs-lookup"><span data-stu-id="7d445-148">Add the following <xref:System.Windows.UIElement.OnMouseMove%2A> override to provide class handling for the <xref:System.Windows.UIElement.MouseMove> event.</span></span>

     [!code-csharp[DragDropWalkthrough#OnMouseMove](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#onmousemove)]
     [!code-vb[DragDropWalkthrough#OnMouseMove](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#onmousemove)]

     <span data-ttu-id="7d445-149">Diese <xref:System.Windows.UIElement.OnMouseMove%2A> außer Kraft Setzung führt die folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="7d445-149">This <xref:System.Windows.UIElement.OnMouseMove%2A> override performs the following tasks:</span></span>

    - <span data-ttu-id="7d445-150">Überprüft, ob die linke Maustaste gedrückt wird, während sich die Maus bewegt.</span><span class="sxs-lookup"><span data-stu-id="7d445-150">Checks whether the left mouse button is pressed while the mouse is moving.</span></span>

    - <span data-ttu-id="7d445-151">Verpackt die Zirkel Daten in <xref:System.Windows.DataObject>eine.</span><span class="sxs-lookup"><span data-stu-id="7d445-151">Packages the Circle data into a <xref:System.Windows.DataObject>.</span></span> <span data-ttu-id="7d445-152">In diesem Fall verpackt das Kreis-Steuerelement drei Datenelemente: eine Zeichenfolgendarstellung seiner Füllfarbe, eine double-Darstellung seiner Höhe und eine Kopie von sich selbst.</span><span class="sxs-lookup"><span data-stu-id="7d445-152">In this case, the Circle control packages three data items; a string representation of its Fill color, a double representation of its height, and a copy of itself.</span></span>

    - <span data-ttu-id="7d445-153">Ruft die statische <xref:System.Windows.DragDrop.DoDragDrop%2A?displayProperty=nameWithType> -Methode auf, um den Drag & Drop-Vorgang zu initiieren.</span><span class="sxs-lookup"><span data-stu-id="7d445-153">Calls the static <xref:System.Windows.DragDrop.DoDragDrop%2A?displayProperty=nameWithType> method to initiate the drag-and-drop operation.</span></span> <span data-ttu-id="7d445-154">Sie übergeben die folgenden drei Parameter an die <xref:System.Windows.DragDrop.DoDragDrop%2A> -Methode:</span><span class="sxs-lookup"><span data-stu-id="7d445-154">You pass the following three parameters to the <xref:System.Windows.DragDrop.DoDragDrop%2A> method:</span></span>

        - <span data-ttu-id="7d445-155">`dragSource`: Ein Verweis auf dieses Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="7d445-155">`dragSource` – A reference to this control.</span></span>

        - <span data-ttu-id="7d445-156">`data`– Die <xref:System.Windows.DataObject> , die im vorherigen Code erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="7d445-156">`data` – The <xref:System.Windows.DataObject> created in the previous code.</span></span>

        - <span data-ttu-id="7d445-157">`allowedEffects`– Die zulässigen Drag & Drop-Vorgänge, die oder <xref:System.Windows.DragDropEffects.Copy> <xref:System.Windows.DragDropEffects.Move>sind.</span><span class="sxs-lookup"><span data-stu-id="7d445-157">`allowedEffects` – The allowed drag-and-drop operations, which are <xref:System.Windows.DragDropEffects.Copy> or <xref:System.Windows.DragDropEffects.Move>.</span></span>

3. <span data-ttu-id="7d445-158">Drücken Sie **F5**, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="7d445-158">Press **F5** to build and run the application.</span></span>

4. <span data-ttu-id="7d445-159">Klicken Sie auf eines der Kreis-Steuerelemente, und ziehen Sie es über die Bereiche, den <xref:System.Windows.Controls.TextBox>anderen Kreis und.</span><span class="sxs-lookup"><span data-stu-id="7d445-159">Click one of the Circle controls and drag it over the panels, the other Circle, and the <xref:System.Windows.Controls.TextBox>.</span></span> <span data-ttu-id="7d445-160">Beim ziehen über das <xref:System.Windows.Controls.TextBox>wird der Cursor geändert, um eine Verschiebung anzugeben.</span><span class="sxs-lookup"><span data-stu-id="7d445-160">When dragging over the <xref:System.Windows.Controls.TextBox>, the cursor changes to indicate a move.</span></span>

5. <span data-ttu-id="7d445-161">Drücken Sie beim Ziehen eines Kreises <xref:System.Windows.Controls.TextBox>über die **STRG** -Taste.</span><span class="sxs-lookup"><span data-stu-id="7d445-161">While dragging a Circle over the <xref:System.Windows.Controls.TextBox>, press the **Ctrl** key.</span></span> <span data-ttu-id="7d445-162">Beachten Sie, wie sich der Cursor ändert, um einen Kopiervorgang anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="7d445-162">Notice how the cursor changes to indicate a copy.</span></span>

6. <span data-ttu-id="7d445-163">Ziehen Sie einen Kreis mit Drag und <xref:System.Windows.Controls.TextBox>Drop auf die.</span><span class="sxs-lookup"><span data-stu-id="7d445-163">Drag and drop a Circle onto the <xref:System.Windows.Controls.TextBox>.</span></span> <span data-ttu-id="7d445-164">Die Zeichen folgen Darstellung der Füllfarbe des Kreises wird an den <xref:System.Windows.Controls.TextBox>angefügt.</span><span class="sxs-lookup"><span data-stu-id="7d445-164">The string representation of the Circle’s fill color is appended to the <xref:System.Windows.Controls.TextBox>.</span></span>

     <span data-ttu-id="7d445-165">![Zeichenfolgendarstellung der Füllfarbe des Kreises](./media/dragdrop-colorstring.png "DragDrop_ColorString")</span><span class="sxs-lookup"><span data-stu-id="7d445-165">![String representation of Circle's fill color](./media/dragdrop-colorstring.png "DragDrop_ColorString")</span></span>

<span data-ttu-id="7d445-166">Standardmäßig ändert sich der Cursor während eines Drag & Drop-Vorgangs, um anzuzeigen, welche Auswirkungen das Ablegen der Daten hat.</span><span class="sxs-lookup"><span data-stu-id="7d445-166">By default, the cursor will change during a drag-and-drop operation to indicate what effect dropping the data will have.</span></span> <span data-ttu-id="7d445-167">Sie können das Feedback an den Benutzer anpassen, indem Sie das <xref:System.Windows.UIElement.GiveFeedback> -Ereignis behandeln und einen anderen Cursor festlegen.</span><span class="sxs-lookup"><span data-stu-id="7d445-167">You can customize the feedback given to the user by handling the <xref:System.Windows.UIElement.GiveFeedback> event and setting a different cursor.</span></span>

## <a name="give-feedback-to-the-user"></a><span data-ttu-id="7d445-168">Feedback an den Benutzer senden</span><span class="sxs-lookup"><span data-stu-id="7d445-168">Give feedback to the user</span></span>

1. <span data-ttu-id="7d445-169">Öffnen Sie "Circle.Xaml.cs" oder "Circle.Xaml.vb".</span><span class="sxs-lookup"><span data-stu-id="7d445-169">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>

2. <span data-ttu-id="7d445-170">Fügen Sie die <xref:System.Windows.UIElement.OnGiveFeedback%2A> folgende außer Kraft Setzung hinzu, um <xref:System.Windows.UIElement.GiveFeedback> Klassen Behandlung für das-Ereignis bereitzustellen</span><span class="sxs-lookup"><span data-stu-id="7d445-170">Add the following <xref:System.Windows.UIElement.OnGiveFeedback%2A> override to provide class handling for the <xref:System.Windows.UIElement.GiveFeedback> event.</span></span>

     [!code-csharp[DragDropWalkthrough#OnGiveFeedback](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ongivefeedback)]
     [!code-vb[DragDropWalkthrough#OnGiveFeedback](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ongivefeedback)]

     <span data-ttu-id="7d445-171">Diese <xref:System.Windows.UIElement.OnGiveFeedback%2A> außer Kraft Setzung führt die folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="7d445-171">This <xref:System.Windows.UIElement.OnGiveFeedback%2A> override performs the following tasks:</span></span>

    - <span data-ttu-id="7d445-172">Überprüft die <xref:System.Windows.GiveFeedbackEventArgs.Effects%2A> Werte, die im-Ereignishandler des Drop <xref:System.Windows.UIElement.DragOver> -Ziels festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="7d445-172">Checks the <xref:System.Windows.GiveFeedbackEventArgs.Effects%2A> values that are set in the drop target's <xref:System.Windows.UIElement.DragOver> event handler.</span></span>

    - <span data-ttu-id="7d445-173">Legt einen benutzerdefinierten Cursor basierend auf <xref:System.Windows.GiveFeedbackEventArgs.Effects%2A> dem-Wert fest.</span><span class="sxs-lookup"><span data-stu-id="7d445-173">Sets a custom cursor based on the <xref:System.Windows.GiveFeedbackEventArgs.Effects%2A> value.</span></span> <span data-ttu-id="7d445-174">Der Cursor soll visuelles Feedback an den Benutzer geben, welche Auswirkungen das Ablegen der Daten hat.</span><span class="sxs-lookup"><span data-stu-id="7d445-174">The cursor is intended to give visual feedback to the user about what effect dropping the data will have.</span></span>

3. <span data-ttu-id="7d445-175">Drücken Sie **F5**, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="7d445-175">Press **F5** to build and run the application.</span></span>

4. <span data-ttu-id="7d445-176">Ziehen Sie eines der Kreis-Steuerelemente auf die Bereiche, den anderen Kreis und <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="7d445-176">Drag one of the Circle controls over the panels, the other Circle, and the <xref:System.Windows.Controls.TextBox>.</span></span> <span data-ttu-id="7d445-177">Beachten Sie, dass die Cursor jetzt die benutzerdefinierten Cursor sind, die <xref:System.Windows.UIElement.OnGiveFeedback%2A> Sie in der Überschreibung angegeben haben.</span><span class="sxs-lookup"><span data-stu-id="7d445-177">Notice that the cursors are now the custom cursors that you specified in the <xref:System.Windows.UIElement.OnGiveFeedback%2A> override.</span></span>

     <span data-ttu-id="7d445-178">![Drag & Drop mit benutzerdefiniertem Cursor](./media/dragdrop-customcursor.png "DragDrop_CustomCursor")</span><span class="sxs-lookup"><span data-stu-id="7d445-178">![Drag and drop with custom cursors](./media/dragdrop-customcursor.png "DragDrop_CustomCursor")</span></span>

5. <span data-ttu-id="7d445-179">Wählen Sie den `green` Text aus <xref:System.Windows.Controls.TextBox>der aus.</span><span class="sxs-lookup"><span data-stu-id="7d445-179">Select the text `green` from the <xref:System.Windows.Controls.TextBox>.</span></span>

6. <span data-ttu-id="7d445-180">Ziehen Sie den Text `green` auf ein Kreis-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="7d445-180">Drag the `green` text to a Circle control.</span></span> <span data-ttu-id="7d445-181">Beachten Sie, dass die standardmäßigen Cursor angezeigt werden, um die Auswirkungen des Drag & Drop-Vorgangs anzugeben.</span><span class="sxs-lookup"><span data-stu-id="7d445-181">Notice that the default cursors are shown to indicate the effects of the drag-and-drop operation.</span></span> <span data-ttu-id="7d445-182">Der Feedbackcursor wird immer durch die Quelle des Ziehvorgangs festgelegt.</span><span class="sxs-lookup"><span data-stu-id="7d445-182">The feedback cursor is always set by the drag source.</span></span>

## <a name="implement-drop-target-events-in-the-user-control"></a><span data-ttu-id="7d445-183">Implementieren von Drop Target-Ereignissen im Benutzer Steuerelement</span><span class="sxs-lookup"><span data-stu-id="7d445-183">Implement Drop Target Events in the User Control</span></span>
 <span data-ttu-id="7d445-184">In diesem Abschnitt geben Sie an, dass das Benutzersteuerelement ein Ablageziel ist, überschreiben die Methoden, die das Benutzersteuerelement befähigen, ein Ablageziel sein und verarbeiten die Daten, die darauf abgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="7d445-184">In this section, you will specify that the user control is a drop target, override the methods that enable the user control to be a drop target, and process the data that is dropped on it.</span></span>

### <a name="to-enable-the-user-control-to-be-a-drop-target"></a><span data-ttu-id="7d445-185">So konfigurieren Sie das Benutzersteuerelement als Ziel eines Ablegevorgangs</span><span class="sxs-lookup"><span data-stu-id="7d445-185">To enable the user control to be a drop target</span></span>

1. <span data-ttu-id="7d445-186">Öffnen Sie Circle.xaml.</span><span class="sxs-lookup"><span data-stu-id="7d445-186">Open Circle.xaml.</span></span>

2. <span data-ttu-id="7d445-187">Fügen Sie im <xref:System.Windows.Controls.UserControl> öffnenden Tag die <xref:System.Windows.UIElement.AllowDrop%2A> -Eigenschaft hinzu, und `true`legen Sie Sie auf fest.</span><span class="sxs-lookup"><span data-stu-id="7d445-187">In the opening <xref:System.Windows.Controls.UserControl> tag, add the <xref:System.Windows.UIElement.AllowDrop%2A> property and set it to `true`.</span></span>

     [!code-xaml[DragDropWalkthrough#UCTagXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml#uctagxaml)]

<span data-ttu-id="7d445-188">Die <xref:System.Windows.UIElement.OnDrop%2A> -Methode wird aufgerufen, <xref:System.Windows.UIElement.AllowDrop%2A> wenn die-Eigenschaft `true` auf festgelegt ist und Daten aus der Zieh Quelle im Kreis-Benutzer Steuerelement abgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="7d445-188">The <xref:System.Windows.UIElement.OnDrop%2A> method is called when the <xref:System.Windows.UIElement.AllowDrop%2A> property is set to `true` and data from the drag source is dropped on the Circle user control.</span></span> <span data-ttu-id="7d445-189">In dieser Methode verarbeiten Sie die Daten, die abgelegt wurden und wenden sie auf den Kreis an.</span><span class="sxs-lookup"><span data-stu-id="7d445-189">In this method, you will process the data that was dropped and apply the data to the Circle.</span></span>

### <a name="to-process-the-dropped-data"></a><span data-ttu-id="7d445-190">So verarbeiten Sie die abgelegten Daten</span><span class="sxs-lookup"><span data-stu-id="7d445-190">To process the dropped data</span></span>

1. <span data-ttu-id="7d445-191">Öffnen Sie "Circle.Xaml.cs" oder "Circle.Xaml.vb".</span><span class="sxs-lookup"><span data-stu-id="7d445-191">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>

2. <span data-ttu-id="7d445-192">Fügen Sie die <xref:System.Windows.UIElement.OnDrop%2A> folgende außer Kraft Setzung hinzu, um <xref:System.Windows.UIElement.Drop> Klassen Behandlung für das-Ereignis bereitzustellen</span><span class="sxs-lookup"><span data-stu-id="7d445-192">Add the following <xref:System.Windows.UIElement.OnDrop%2A> override to provide class handling for the <xref:System.Windows.UIElement.Drop> event.</span></span>

     [!code-csharp[DragDropWalkthrough#OnDrop](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondrop)]
     [!code-vb[DragDropWalkthrough#OnDrop](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondrop)]

     <span data-ttu-id="7d445-193">Diese <xref:System.Windows.UIElement.OnDrop%2A> außer Kraft Setzung führt die folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="7d445-193">This <xref:System.Windows.UIElement.OnDrop%2A> override performs the following tasks:</span></span>

    - <span data-ttu-id="7d445-194">Verwendet die <xref:System.Windows.DataObject.GetDataPresent%2A> -Methode, um zu überprüfen, ob die gezogenen Daten ein Zeichen folgen Objekt enthalten.</span><span class="sxs-lookup"><span data-stu-id="7d445-194">Uses the <xref:System.Windows.DataObject.GetDataPresent%2A> method to check if the dragged data contains a string object.</span></span>

    - <span data-ttu-id="7d445-195">Verwendet die <xref:System.Windows.DataObject.GetData%2A> -Methode, um die Zeichen folgen Daten zu extrahieren, sofern diese vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="7d445-195">Uses the <xref:System.Windows.DataObject.GetData%2A> method to extract the string data if it is present.</span></span>

    - <span data-ttu-id="7d445-196">Verwendet einen <xref:System.Windows.Media.BrushConverter> , um zu versuchen, die Zeichenfolge <xref:System.Windows.Media.Brush>in eine zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="7d445-196">Uses a <xref:System.Windows.Media.BrushConverter> to try to convert the string to a <xref:System.Windows.Media.Brush>.</span></span>

    - <span data-ttu-id="7d445-197">Wenn die Konvertierung erfolgreich ist, wendet den Pinsel auf den <xref:System.Windows.Shapes.Shape.Fill%2A> <xref:System.Windows.Shapes.Ellipse> des an, der die Benutzeroberfläche des Kreis-Steuer Elements bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="7d445-197">If the conversion is successful, applies the brush to the <xref:System.Windows.Shapes.Shape.Fill%2A> of the <xref:System.Windows.Shapes.Ellipse> that provides the UI of the Circle control.</span></span>

    - <span data-ttu-id="7d445-198">Markiert das <xref:System.Windows.UIElement.Drop> Ereignis als behandelt.</span><span class="sxs-lookup"><span data-stu-id="7d445-198">Marks the <xref:System.Windows.UIElement.Drop> event as handled.</span></span> <span data-ttu-id="7d445-199">Sie sollten das Drop-Ereignis als behandelt kennzeichnen, damit andere Elemente, die dieses Ereignis empfangen, wissen, dass das Kreis-Steuerelement es behandelt hat.</span><span class="sxs-lookup"><span data-stu-id="7d445-199">You should mark the drop event as handled so that other elements that receive this event know that the Circle user control handled it.</span></span>

3. <span data-ttu-id="7d445-200">Drücken Sie **F5**, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="7d445-200">Press **F5** to build and run the application.</span></span>

4. <span data-ttu-id="7d445-201">Wählen Sie den `green` Text <xref:System.Windows.Controls.TextBox>in aus.</span><span class="sxs-lookup"><span data-stu-id="7d445-201">Select the text `green` in the <xref:System.Windows.Controls.TextBox>.</span></span>

5. <span data-ttu-id="7d445-202">Ziehen Sie den Text auf ein Kreis-Steuerelement, und legen Sie ihn ab.</span><span class="sxs-lookup"><span data-stu-id="7d445-202">Drag the text to a Circle control and drop it.</span></span> <span data-ttu-id="7d445-203">Der Kreis ändert sich von Blau in Grün.</span><span class="sxs-lookup"><span data-stu-id="7d445-203">The Circle changes from blue to green.</span></span>

     <span data-ttu-id="7d445-204">![Konvertieren einer Zeichenfolge in einen Pinsel](./media/dragdrop-dropgreentext.png "DragDrop_DropGreenText")</span><span class="sxs-lookup"><span data-stu-id="7d445-204">![Convert a string to a brush](./media/dragdrop-dropgreentext.png "DragDrop_DropGreenText")</span></span>

6. <span data-ttu-id="7d445-205">Geben Sie den `green` Text in <xref:System.Windows.Controls.TextBox>der ein.</span><span class="sxs-lookup"><span data-stu-id="7d445-205">Type the text `green` in the <xref:System.Windows.Controls.TextBox>.</span></span>

7. <span data-ttu-id="7d445-206">Wählen Sie den `gre` Text <xref:System.Windows.Controls.TextBox>in aus.</span><span class="sxs-lookup"><span data-stu-id="7d445-206">Select the text `gre` in the <xref:System.Windows.Controls.TextBox>.</span></span>

8. <span data-ttu-id="7d445-207">Ziehen Sie ihn auf ein Kreis-Steuerelement, und legen Sie ihn ab.</span><span class="sxs-lookup"><span data-stu-id="7d445-207">Drag it to a Circle control and drop it.</span></span> <span data-ttu-id="7d445-208">Beachten Sie, dass sich zwar der Cursor ändert, um anzuzeigen, dass der Ablegevorgang zulässig ist, die Farbe des Kreises sich aber nicht ändert, da `gre` keine gültige Farbe ist.</span><span class="sxs-lookup"><span data-stu-id="7d445-208">Notice that the cursor changes to indicate that the drop is allowed, but the color of the Circle does not change because `gre` is not a valid color.</span></span>

9. <span data-ttu-id="7d445-209">Ziehen Sie vom grünen Kreis-Steuerelement auf das blaue Kreis-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="7d445-209">Drag from the green Circle control and drop on the blue Circle control.</span></span> <span data-ttu-id="7d445-210">Der Kreis ändert sich von Blau in Grün.</span><span class="sxs-lookup"><span data-stu-id="7d445-210">The Circle changes from blue to green.</span></span> <span data-ttu-id="7d445-211">Beachten Sie, dass der angezeigte Cursor davon abhängt <xref:System.Windows.Controls.TextBox> , ob der oder der Kreis die Zieh Quelle ist.</span><span class="sxs-lookup"><span data-stu-id="7d445-211">Notice that which cursor is shown depends on whether the <xref:System.Windows.Controls.TextBox> or the Circle is the drag source.</span></span>

<span data-ttu-id="7d445-212">Das Festlegen <xref:System.Windows.UIElement.AllowDrop%2A> der- `true` Eigenschaft auf und die Verarbeitung der gelöschten Daten ist alles, was erforderlich ist, um ein Element als Ablage Ziel zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="7d445-212">Setting the <xref:System.Windows.UIElement.AllowDrop%2A> property to `true` and processing the dropped data is all that is required to enable an element to be a drop target.</span></span> <span data-ttu-id="7d445-213">Um jedoch eine bessere Benutzer Leistung zu gewährleisten, sollten Sie auch die <xref:System.Windows.UIElement.DragEnter>Ereignisse <xref:System.Windows.UIElement.DragLeave>, und <xref:System.Windows.UIElement.DragOver> behandeln.</span><span class="sxs-lookup"><span data-stu-id="7d445-213">However, to provide a better user experience, you should also handle the <xref:System.Windows.UIElement.DragEnter>, <xref:System.Windows.UIElement.DragLeave>, and <xref:System.Windows.UIElement.DragOver> events.</span></span> <span data-ttu-id="7d445-214">In diesen Ereignissen können Sie vor Ablage der Daten diese überprüfen und zusätzliches Feedback für den Benutzer bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="7d445-214">In these events, you can perform checks and provide additional feedback to the user before the data is dropped.</span></span>

<span data-ttu-id="7d445-215">Wenn Daten über das Kreis-Steuerelement gezogen werden, sollte das Steuerelement die Quelle des Ziehvorgangs darüber benachrichtigen, ob die darüber gezogenen Daten verarbeitet werden können.</span><span class="sxs-lookup"><span data-stu-id="7d445-215">When data is dragged over the Circle user control, the control should notify the drag source whether it can process the data that is being dragged.</span></span> <span data-ttu-id="7d445-216">Wenn das Steuerelement nicht weiß, wie die Daten zu verarbeiten sind, sollte es den Ablegevorgang ablehnen.</span><span class="sxs-lookup"><span data-stu-id="7d445-216">If the control does not know how to process the data, it should refuse the drop.</span></span> <span data-ttu-id="7d445-217">Zu diesem Zweck behandeln Sie das <xref:System.Windows.UIElement.DragOver> -Ereignis und legen die <xref:System.Windows.DragEventArgs.Effects%2A> -Eigenschaft fest.</span><span class="sxs-lookup"><span data-stu-id="7d445-217">To do this, you will handle the <xref:System.Windows.UIElement.DragOver> event and set the <xref:System.Windows.DragEventArgs.Effects%2A> property.</span></span>

### <a name="to-verify-that-the-data-drop-is-allowed"></a><span data-ttu-id="7d445-218">So stellen sie sicher, dass die Datenablage zulässig ist</span><span class="sxs-lookup"><span data-stu-id="7d445-218">To verify that the data drop is allowed</span></span>

1. <span data-ttu-id="7d445-219">Öffnen Sie "Circle.Xaml.cs" oder "Circle.Xaml.vb".</span><span class="sxs-lookup"><span data-stu-id="7d445-219">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>

2. <span data-ttu-id="7d445-220">Fügen Sie die <xref:System.Windows.UIElement.OnDragOver%2A> folgende außer Kraft Setzung hinzu, um <xref:System.Windows.UIElement.DragOver> Klassen Behandlung für das-Ereignis bereitzustellen</span><span class="sxs-lookup"><span data-stu-id="7d445-220">Add the following <xref:System.Windows.UIElement.OnDragOver%2A> override to provide class handling for the <xref:System.Windows.UIElement.DragOver> event.</span></span>

     [!code-csharp[DragDropWalkthrough#OnDragOver](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondragover)]
     [!code-vb[DragDropWalkthrough#OnDragOver](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondragover)]

     <span data-ttu-id="7d445-221">Diese <xref:System.Windows.UIElement.OnDragOver%2A> außer Kraft Setzung führt die folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="7d445-221">This <xref:System.Windows.UIElement.OnDragOver%2A> override performs the following tasks:</span></span>

    - <span data-ttu-id="7d445-222">Legt die <xref:System.Windows.DragEventArgs.Effects%2A>-Eigenschaft auf <xref:System.Windows.DragDropEffects.None> fest.</span><span class="sxs-lookup"><span data-stu-id="7d445-222">Sets the <xref:System.Windows.DragEventArgs.Effects%2A> property to <xref:System.Windows.DragDropEffects.None>.</span></span>

    - <span data-ttu-id="7d445-223">Führt die gleichen Überprüfungen durch, die in <xref:System.Windows.UIElement.OnDrop%2A> der-Methode ausgeführt werden, um zu bestimmen, ob das Kreis-Benutzer Steuerelement die gezogenen Daten verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="7d445-223">Performs the same checks that are performed in the <xref:System.Windows.UIElement.OnDrop%2A> method to determine whether the Circle user control can process the dragged data.</span></span>

    - <span data-ttu-id="7d445-224">Wenn das Benutzer Steuerelement die Daten verarbeiten kann, wird <xref:System.Windows.DragEventArgs.Effects%2A> die- <xref:System.Windows.DragDropEffects.Copy> Eigenschaft <xref:System.Windows.DragDropEffects.Move>auf oder festgelegt.</span><span class="sxs-lookup"><span data-stu-id="7d445-224">If the user control can process the data, sets the <xref:System.Windows.DragEventArgs.Effects%2A> property to <xref:System.Windows.DragDropEffects.Copy> or <xref:System.Windows.DragDropEffects.Move>.</span></span>

3. <span data-ttu-id="7d445-225">Drücken Sie **F5**, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="7d445-225">Press **F5** to build and run the application.</span></span>

4. <span data-ttu-id="7d445-226">Wählen Sie den `gre` Text <xref:System.Windows.Controls.TextBox>in aus.</span><span class="sxs-lookup"><span data-stu-id="7d445-226">Select the text `gre` in the <xref:System.Windows.Controls.TextBox>.</span></span>

5. <span data-ttu-id="7d445-227">Ziehen Sie den Text auf ein Kreis-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="7d445-227">Drag the text to a Circle control.</span></span> <span data-ttu-id="7d445-228">Beachten Sie, dass sich der Cursor jetzt so ändert, dass er anzeigt, dass der Ablegevorgang nicht zulässig ist, da `gre` keine gültige Farbe ist.</span><span class="sxs-lookup"><span data-stu-id="7d445-228">Notice that the cursor now changes to indicate that the drop is not allowed because `gre` is not a valid color.</span></span>

 <span data-ttu-id="7d445-229">Sie können die Benutzerfunktionalität weiter verbessern, indem Sie eine Vorschau des Drop-Vorgangs anwenden.</span><span class="sxs-lookup"><span data-stu-id="7d445-229">You can further enhance the user experience by applying a preview of the drop operation.</span></span> <span data-ttu-id="7d445-230">Für das Kreis-Benutzer Steuerelement überschreiben Sie <xref:System.Windows.UIElement.OnDragEnter%2A> die <xref:System.Windows.UIElement.OnDragLeave%2A> -Methode und die-Methode.</span><span class="sxs-lookup"><span data-stu-id="7d445-230">For the Circle user control, you will override the <xref:System.Windows.UIElement.OnDragEnter%2A> and <xref:System.Windows.UIElement.OnDragLeave%2A> methods.</span></span> <span data-ttu-id="7d445-231">Wenn die Daten über das Steuerelement gezogen werden, wird der <xref:System.Windows.Shapes.Shape.Fill%2A> aktuelle Hintergrund in einer Platzhalter Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="7d445-231">When the data is dragged over the control, the current background <xref:System.Windows.Shapes.Shape.Fill%2A> is saved in a placeholder variable.</span></span> <span data-ttu-id="7d445-232">Die Zeichenfolge wird dann in einen Pinsel konvertiert und auf das <xref:System.Windows.Shapes.Ellipse> angewendet, das die Benutzeroberfläche des Kreises bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="7d445-232">The string is then converted to a brush and applied to the <xref:System.Windows.Shapes.Ellipse> that provides the Circle's UI.</span></span> <span data-ttu-id="7d445-233">Wenn die Daten aus dem Kreis gezogen werden, ohne gelöscht zu werden, wird <xref:System.Windows.Shapes.Shape.Fill%2A> der ursprüngliche Wert erneut auf den Kreis angewendet.</span><span class="sxs-lookup"><span data-stu-id="7d445-233">If the data is dragged out of the Circle without being dropped, the original <xref:System.Windows.Shapes.Shape.Fill%2A> value is re-applied to the Circle.</span></span>

### <a name="to-preview-the-effects-of-the-drag-and-drop-operation"></a><span data-ttu-id="7d445-234">So können Sie die Auswirkungen eines Drag & Drop-Vorgangs in der Vorschau anzeigen</span><span class="sxs-lookup"><span data-stu-id="7d445-234">To preview the effects of the drag-and-drop operation</span></span>

1. <span data-ttu-id="7d445-235">Öffnen Sie "Circle.Xaml.cs" oder "Circle.Xaml.vb".</span><span class="sxs-lookup"><span data-stu-id="7d445-235">Open Circle.xaml.cs or Circle.xaml.vb.</span></span>

2. <span data-ttu-id="7d445-236">Deklarieren Sie in der Klasse Circle eine <xref:System.Windows.Media.Brush> private Variable `_previousFill` mit dem Namen, und `null`Initialisieren Sie Sie mit.</span><span class="sxs-lookup"><span data-stu-id="7d445-236">In the Circle class, declare a private <xref:System.Windows.Media.Brush> variable named `_previousFill` and initialize it to `null`.</span></span>

     [!code-csharp[DragDropWalkthrough#Brush](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#brush)]
     [!code-vb[DragDropWalkthrough#Brush](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#brush)]

3. <span data-ttu-id="7d445-237">Fügen Sie die <xref:System.Windows.UIElement.OnDragEnter%2A> folgende außer Kraft Setzung hinzu, um <xref:System.Windows.UIElement.DragEnter> Klassen Behandlung für das-Ereignis bereitzustellen</span><span class="sxs-lookup"><span data-stu-id="7d445-237">Add the following <xref:System.Windows.UIElement.OnDragEnter%2A> override to provide class handling for the <xref:System.Windows.UIElement.DragEnter> event.</span></span>

     [!code-csharp[DragDropWalkthrough#OnDragEnter](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondragenter)]
     [!code-vb[DragDropWalkthrough#OnDragEnter](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondragenter)]

     <span data-ttu-id="7d445-238">Diese <xref:System.Windows.UIElement.OnDragEnter%2A> außer Kraft Setzung führt die folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="7d445-238">This <xref:System.Windows.UIElement.OnDragEnter%2A> override performs the following tasks:</span></span>

    - <span data-ttu-id="7d445-239">Speichert die <xref:System.Windows.Shapes.Shape.Fill%2A> -Eigenschaft <xref:System.Windows.Shapes.Ellipse> des in der `_previousFill` Variablen.</span><span class="sxs-lookup"><span data-stu-id="7d445-239">Saves the <xref:System.Windows.Shapes.Shape.Fill%2A> property of the <xref:System.Windows.Shapes.Ellipse> in the `_previousFill` variable.</span></span>

    - <span data-ttu-id="7d445-240">Führt die gleichen Überprüfungen durch, die in <xref:System.Windows.UIElement.OnDrop%2A> der-Methode ausgeführt werden, um zu bestimmen, ob <xref:System.Windows.Media.Brush>die Daten in einen konvertiert werden können.</span><span class="sxs-lookup"><span data-stu-id="7d445-240">Performs the same checks that are performed in the <xref:System.Windows.UIElement.OnDrop%2A> method to determine whether the data can be converted to a <xref:System.Windows.Media.Brush>.</span></span>

    - <span data-ttu-id="7d445-241">Wenn die Daten in einen gültigen <xref:System.Windows.Media.Brush>konvertiert werden, wendet ihn auf den <xref:System.Windows.Shapes.Shape.Fill%2A> von <xref:System.Windows.Shapes.Ellipse>an.</span><span class="sxs-lookup"><span data-stu-id="7d445-241">If the data is converted to a valid <xref:System.Windows.Media.Brush>, applies it to the <xref:System.Windows.Shapes.Shape.Fill%2A> of the <xref:System.Windows.Shapes.Ellipse>.</span></span>

4. <span data-ttu-id="7d445-242">Fügen Sie die <xref:System.Windows.UIElement.OnDragLeave%2A> folgende außer Kraft Setzung hinzu, um <xref:System.Windows.UIElement.DragLeave> Klassen Behandlung für das-Ereignis bereitzustellen</span><span class="sxs-lookup"><span data-stu-id="7d445-242">Add the following <xref:System.Windows.UIElement.OnDragLeave%2A> override to provide class handling for the <xref:System.Windows.UIElement.DragLeave> event.</span></span>

     [!code-csharp[DragDropWalkthrough#OnDragLeave](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/Circle.xaml.cs#ondragleave)]
     [!code-vb[DragDropWalkthrough#OnDragLeave](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/Circle.xaml.vb#ondragleave)]

     <span data-ttu-id="7d445-243">Diese <xref:System.Windows.UIElement.OnDragLeave%2A> außer Kraft Setzung führt die folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="7d445-243">This <xref:System.Windows.UIElement.OnDragLeave%2A> override performs the following tasks:</span></span>

    - <span data-ttu-id="7d445-244">Wendet das <xref:System.Windows.Media.Brush> ,dasinder<xref:System.Windows.Shapes.Ellipse> <xref:System.Windows.Shapes.Shape.Fill%2A> `_previousFill` Variablen gespeichert ist, auf die des an, das die Benutzeroberfläche des Kreis-Benutzer Steuer Elements bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="7d445-244">Applies the <xref:System.Windows.Media.Brush> saved in the `_previousFill` variable to the <xref:System.Windows.Shapes.Shape.Fill%2A> of the <xref:System.Windows.Shapes.Ellipse> that provides the UI of the Circle user control.</span></span>

5. <span data-ttu-id="7d445-245">Drücken Sie **F5**, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="7d445-245">Press **F5** to build and run the application.</span></span>

6. <span data-ttu-id="7d445-246">Wählen Sie den `green` Text <xref:System.Windows.Controls.TextBox>in aus.</span><span class="sxs-lookup"><span data-stu-id="7d445-246">Select the text `green` in the <xref:System.Windows.Controls.TextBox>.</span></span>

7. <span data-ttu-id="7d445-247">Ziehen Sie den Text über ein Kreis-Steuerelement ohne ihn abzulegen.</span><span class="sxs-lookup"><span data-stu-id="7d445-247">Drag the text over a Circle control without dropping it.</span></span> <span data-ttu-id="7d445-248">Der Kreis ändert sich von Blau in Grün.</span><span class="sxs-lookup"><span data-stu-id="7d445-248">The Circle changes from blue to green.</span></span>

     <span data-ttu-id="7d445-249">![Vorschau der Auswirkungen eines Drag & Drop-Vorgangs](./media/dragdrop-previeweffects.png "DragDrop_PreviewEffects")</span><span class="sxs-lookup"><span data-stu-id="7d445-249">![Preview the effects of a drag&#45;and&#45;drop operation](./media/dragdrop-previeweffects.png "DragDrop_PreviewEffects")</span></span>

8. <span data-ttu-id="7d445-250">Ziehen Sie den Text vom Kreis-Steuerelement weg.</span><span class="sxs-lookup"><span data-stu-id="7d445-250">Drag the text away from the Circle control.</span></span> <span data-ttu-id="7d445-251">Der Kreis ändert sich von Grün zurück in Blau.</span><span class="sxs-lookup"><span data-stu-id="7d445-251">The Circle changes from green back to blue.</span></span>

## <a name="enable-a-panel-to-receive-dropped-data"></a><span data-ttu-id="7d445-252">Aktivieren eines Panels zum Empfangen von gelöschten Daten</span><span class="sxs-lookup"><span data-stu-id="7d445-252">Enable a Panel to Receive Dropped Data</span></span>

<span data-ttu-id="7d445-253">In diesem Abschnitt ermöglichen Sie den Bereichen, die die Kreis-Benutzer Steuerelemente hosten, als Dropziele für gezogene Kreis Daten zu fungieren.</span><span class="sxs-lookup"><span data-stu-id="7d445-253">In this section, you enable the panels that host the Circle user controls to act as drop targets for dragged Circle data.</span></span> <span data-ttu-id="7d445-254">Sie implementieren Code, der es Ihnen ermöglicht, einen Kreis von einem Bereich in einen anderen zu verschieben oder eine Kopie eines Kreis-Steuer Elements zu erstellen, indem Sie die **STRG** -Taste gedrückt halten, während Sie einen Kreis ziehen und ablegen.</span><span class="sxs-lookup"><span data-stu-id="7d445-254">You will implement code that enables you to move a Circle from one panel to another, or to make a copy of a Circle control by holding down the **Ctrl** key while dragging and dropping a Circle.</span></span>

1. <span data-ttu-id="7d445-255">Öffnen Sie „MainWindow.xaml“.</span><span class="sxs-lookup"><span data-stu-id="7d445-255">Open MainWindow.xaml.</span></span>

2. <span data-ttu-id="7d445-256">Fügen Sie, wie im folgenden XAML-Code gezeigt, <xref:System.Windows.Controls.StackPanel> Handler für das-Ereignis und das <xref:System.Windows.UIElement.DragOver> - <xref:System.Windows.UIElement.Drop> Ereignis hinzu.</span><span class="sxs-lookup"><span data-stu-id="7d445-256">As shown in the following XAML, in each of the <xref:System.Windows.Controls.StackPanel> controls, add handlers for the <xref:System.Windows.UIElement.DragOver> and <xref:System.Windows.UIElement.Drop> events.</span></span> <span data-ttu-id="7d445-257">Benennen Sie <xref:System.Windows.UIElement.DragOver> den Ereignishandler `panel_DragOver`,, und `panel_Drop`benennen <xref:System.Windows.UIElement.Drop> Sie den Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="7d445-257">Name the <xref:System.Windows.UIElement.DragOver> event handler, `panel_DragOver`, and name the <xref:System.Windows.UIElement.Drop> event handler, `panel_Drop`.</span></span>

     [!code-xaml[DragDropWalkthrough#PanelsXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/MainWindow.xaml#panelsxaml)]

3. <span data-ttu-id="7d445-258">Öffnen Sie „MainWindow.xaml.cs“ bzw. „MainWindow.xaml.vb“.</span><span class="sxs-lookup"><span data-stu-id="7d445-258">Open MainWindows.xaml.cs or MainWindow.xaml.vb.</span></span>

4. <span data-ttu-id="7d445-259">Fügen Sie den folgenden Code für <xref:System.Windows.UIElement.DragOver> den-Ereignishandler hinzu.</span><span class="sxs-lookup"><span data-stu-id="7d445-259">Add the following code for the <xref:System.Windows.UIElement.DragOver> event handler.</span></span>

     [!code-csharp[DragDropWalkthrough#PanelDragOver](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/MainWindow.xaml.cs#paneldragover)]
     [!code-vb[DragDropWalkthrough#PanelDragOver](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/MainWindow.xaml.vb#paneldragover)]

     <span data-ttu-id="7d445-260">Dieser <xref:System.Windows.UIElement.DragOver> Ereignishandler führt die folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="7d445-260">This <xref:System.Windows.UIElement.DragOver> event handler performs the following tasks:</span></span>

    - <span data-ttu-id="7d445-261">Überprüft, ob die gezogenen Daten die "Objekt"-Daten enthalten, die vom <xref:System.Windows.DataObject> Kreis-Benutzer Steuerelement in den gepackt und in den <xref:System.Windows.DragDrop.DoDragDrop%2A>-Befehl übermittelt wurden.</span><span class="sxs-lookup"><span data-stu-id="7d445-261">Checks that the dragged data contains the "Object" data that was packaged in the <xref:System.Windows.DataObject> by the Circle user control and passed in the call to <xref:System.Windows.DragDrop.DoDragDrop%2A>.</span></span>

    - <span data-ttu-id="7d445-262">Wenn die "Objekt"-Daten vorhanden sind, wird überprüft, ob die **STRG** -Taste gedrückt wird.</span><span class="sxs-lookup"><span data-stu-id="7d445-262">If the "Object" data is present, checks whether the **Ctrl** key is pressed.</span></span>

    - <span data-ttu-id="7d445-263">Wenn die **STRG** -Taste gedrückt wird, wird <xref:System.Windows.DragEventArgs.Effects%2A> die- <xref:System.Windows.DragDropEffects.Copy>Eigenschaft auf festgelegt.</span><span class="sxs-lookup"><span data-stu-id="7d445-263">If the **Ctrl** key is pressed, sets the <xref:System.Windows.DragEventArgs.Effects%2A> property to <xref:System.Windows.DragDropEffects.Copy>.</span></span> <span data-ttu-id="7d445-264">Legen Sie andernfalls die <xref:System.Windows.DragEventArgs.Effects%2A> -Eigenschaft <xref:System.Windows.DragDropEffects.Move>auf fest.</span><span class="sxs-lookup"><span data-stu-id="7d445-264">Otherwise, set the <xref:System.Windows.DragEventArgs.Effects%2A> property to <xref:System.Windows.DragDropEffects.Move>.</span></span>

5. <span data-ttu-id="7d445-265">Fügen Sie den folgenden Code für <xref:System.Windows.UIElement.Drop> den-Ereignishandler hinzu.</span><span class="sxs-lookup"><span data-stu-id="7d445-265">Add the following code for the <xref:System.Windows.UIElement.Drop> event handler.</span></span>

     [!code-csharp[DragDropWalkthrough#PanelDrop](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDropWalkthrough/CS/MainWindow.xaml.cs#paneldrop)]
     [!code-vb[DragDropWalkthrough#PanelDrop](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDropWalkthrough/VB/MainWindow.xaml.vb#paneldrop)]

     <span data-ttu-id="7d445-266">Dieser <xref:System.Windows.UIElement.Drop> Ereignishandler führt die folgenden Aufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="7d445-266">This <xref:System.Windows.UIElement.Drop> event handler performs the following tasks:</span></span>

    - <span data-ttu-id="7d445-267">Überprüft, ob <xref:System.Windows.UIElement.Drop> das Ereignis bereits behandelt wurde.</span><span class="sxs-lookup"><span data-stu-id="7d445-267">Checks whether the <xref:System.Windows.UIElement.Drop> event has already been handled.</span></span> <span data-ttu-id="7d445-268">Wenn beispielsweise ein Kreis in einem anderen Kreis abgelegt wird, der das <xref:System.Windows.UIElement.Drop> -Ereignis behandelt, soll der Bereich, der den Kreis enthält, nicht ebenfalls behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="7d445-268">For instance, if a Circle is dropped on another Circle which handles the <xref:System.Windows.UIElement.Drop> event, you do not want the panel that contains the Circle to also handle it.</span></span>

    - <span data-ttu-id="7d445-269">Wenn das <xref:System.Windows.UIElement.Drop> Ereignis nicht behandelt wird, überprüft, ob die **STRG** -Taste gedrückt ist.</span><span class="sxs-lookup"><span data-stu-id="7d445-269">If the <xref:System.Windows.UIElement.Drop> event is not handled, checks whether the **Ctrl** key is pressed.</span></span>

    - <span data-ttu-id="7d445-270">Wenn beim Auftreten der **STRG** -Taste gedrückt <xref:System.Windows.UIElement.Drop> wird, erstellt eine Kopie des Kreis-Steuer Elements und fügt es <xref:System.Windows.Controls.StackPanel>der <xref:System.Windows.Controls.Panel.Children%2A> -Auflistung von hinzu.</span><span class="sxs-lookup"><span data-stu-id="7d445-270">If the **Ctrl** key is pressed when the <xref:System.Windows.UIElement.Drop> happens, makes a copy of the Circle control and add it to the <xref:System.Windows.Controls.Panel.Children%2A> collection of the <xref:System.Windows.Controls.StackPanel>.</span></span>

    - <span data-ttu-id="7d445-271">Wenn die **STRG** -Taste nicht gedrückt wird, verschiebt den Kreis aus <xref:System.Windows.Controls.Panel.Children%2A> der-Auflistung des übergeordneten Bereichs <xref:System.Windows.Controls.Panel.Children%2A> in die-Auflistung des Panels, in dem Sie abgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="7d445-271">If the **Ctrl** key is not pressed, moves the Circle from the <xref:System.Windows.Controls.Panel.Children%2A> collection of its parent panel to the <xref:System.Windows.Controls.Panel.Children%2A> collection of the panel that it was dropped on.</span></span>

    - <span data-ttu-id="7d445-272">Legt die <xref:System.Windows.DragEventArgs.Effects%2A> -Eigenschaft fest, <xref:System.Windows.DragDrop.DoDragDrop%2A> um die Methode zu benachrichtigen, ob ein verschiebe-oder Kopiervorgang ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="7d445-272">Sets the <xref:System.Windows.DragEventArgs.Effects%2A> property to notify the <xref:System.Windows.DragDrop.DoDragDrop%2A> method whether a move or copy operation was performed.</span></span>

6. <span data-ttu-id="7d445-273">Drücken Sie **F5**, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="7d445-273">Press **F5** to build and run the application.</span></span>

7. <span data-ttu-id="7d445-274">Wählen Sie den `green` Text aus <xref:System.Windows.Controls.TextBox>der aus.</span><span class="sxs-lookup"><span data-stu-id="7d445-274">Select the text `green` from the <xref:System.Windows.Controls.TextBox>.</span></span>

8. <span data-ttu-id="7d445-275">Ziehen Sie den Text auf ein Kreis-Steuerelement, und legen Sie ihn ab.</span><span class="sxs-lookup"><span data-stu-id="7d445-275">Drag the text over a Circle control and drop it.</span></span>

9. <span data-ttu-id="7d445-276">Ziehen Sie ein Kreis-Steuerelement vom linken Panel in das rechte Panel und legen Sie es ab.</span><span class="sxs-lookup"><span data-stu-id="7d445-276">Drag a Circle control from the left panel to the right panel and drop it.</span></span> <span data-ttu-id="7d445-277">Der Kreis wird aus der <xref:System.Windows.Controls.Panel.Children%2A> Auflistung des linken Bereichs entfernt und der Auflistung Children des rechten Panels hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="7d445-277">The Circle is removed from the <xref:System.Windows.Controls.Panel.Children%2A> collection of the left panel and added to the Children collection of the right panel.</span></span>

10. <span data-ttu-id="7d445-278">Ziehen Sie ein Kreis-Steuerelement aus dem Bereich in den anderen Bereich, und legen Sie es beim Drücken der **STRG** -Taste ab.</span><span class="sxs-lookup"><span data-stu-id="7d445-278">Drag a Circle control from the panel it is in to the other panel and drop it while pressing the **Ctrl** key.</span></span> <span data-ttu-id="7d445-279">Der Kreis wird kopiert, <xref:System.Windows.Controls.Panel.Children%2A> und die Kopie wird der Auflistung des Empfangsbereichs hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="7d445-279">The Circle is copied and the copy is added to the <xref:System.Windows.Controls.Panel.Children%2A> collection of the receiving panel.</span></span>

     <span data-ttu-id="7d445-280">![Ziehen eines Kreises bei gedrückter STRG-Taste](./media/dragdrop-paneldrop.png "DragDrop_PanelDrop")</span><span class="sxs-lookup"><span data-stu-id="7d445-280">![Dragging a Circle while pressing the CTRL key](./media/dragdrop-paneldrop.png "DragDrop_PanelDrop")</span></span>

## <a name="see-also"></a><span data-ttu-id="7d445-281">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7d445-281">See also</span></span>

- [<span data-ttu-id="7d445-282">Übersicht über Drag & Drop</span><span class="sxs-lookup"><span data-stu-id="7d445-282">Drag and Drop Overview</span></span>](drag-and-drop-overview.md)
