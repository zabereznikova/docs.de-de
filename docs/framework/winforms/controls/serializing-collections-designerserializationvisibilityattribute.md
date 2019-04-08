---
title: 'Exemplarische Vorgehensweise: Serialisieren der Auflistungen von Standardtypen mit dem DesignerSerializationVisibilityAttribute'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- serialization [Windows Forms], collections
- standard types [Windows Forms], collections
- collections [Windows Forms], serializing
- collections [Windows Forms], standard types
ms.assetid: 020c9df4-fdc5-4dae-815a-963ecae5668c
ms.openlocfilehash: 04eb56fe78aa2d9ef5ab0daae4ba1c873cfc2b26
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59097758"
---
# <a name="walkthrough-serializing-collections-of-standard-types-with-the-designerserializationvisibilityattribute"></a><span data-ttu-id="f0954-102">Exemplarische Vorgehensweise: Serialisieren der Auflistungen von Standardtypen mit dem DesignerSerializationVisibilityAttribute</span><span class="sxs-lookup"><span data-stu-id="f0954-102">Walkthrough: Serializing Collections of Standard Types with the DesignerSerializationVisibilityAttribute</span></span>
<span data-ttu-id="f0954-103">Ihre benutzerdefinierten Steuerelemente werden manchmal eine Auflistung als Eigenschaft verfügbar machen.</span><span class="sxs-lookup"><span data-stu-id="f0954-103">Your custom controls will sometimes expose a collection as a property.</span></span> <span data-ttu-id="f0954-104">In dieser exemplarischen Vorgehensweise wird veranschaulicht, wie Sie mit der <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute> Klasse, um zu steuern, wie eine Auflistung zur Entwurfszeit serialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="f0954-104">This walkthrough demonstrates how to use the <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute> class to control how a collection is serialized at design time.</span></span> <span data-ttu-id="f0954-105">Anwenden der <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content> Wert, der die Auflistungseigenschaft wird sichergestellt, dass die Eigenschaft serialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="f0954-105">Applying the <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content> value to your collection property ensures that the property will be serialized.</span></span>  
  
 <span data-ttu-id="f0954-106">Zum Kopieren des Codes in diesem Thema als einzelne Auflistung lesen Sie [Vorgehensweise: Serialisieren der Auflistungen von Standardtypen mit dem DesignerSerializationVisibilityAttribute](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171833(v=vs.120)).</span><span class="sxs-lookup"><span data-stu-id="f0954-106">To copy the code in this topic as a single listing, see [How to: Serialize Collections of Standard Types with the DesignerSerializationVisibilityAttribute](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171833(v=vs.120)).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f0954-107">Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.</span><span class="sxs-lookup"><span data-stu-id="f0954-107">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="f0954-108">Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="f0954-108">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="f0954-109">Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="f0954-109">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="f0954-110">Vorraussetzungen</span><span class="sxs-lookup"><span data-stu-id="f0954-110">Prerequisites</span></span>  
 <span data-ttu-id="f0954-111">Für die Durchführung dieser exemplarischen Vorgehensweise benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="f0954-111">In order to complete this walkthrough, you will need:</span></span>  
  
-   <span data-ttu-id="f0954-112">Berechtigt sind, können zum Erstellen und Ausführen von Windows Forms-Anwendungsprojekten auf dem Computer, auf dem Visual Studio installiert ist.</span><span class="sxs-lookup"><span data-stu-id="f0954-112">Sufficient permissions to be able to create and run Windows Forms application projects on the computer where Visual Studio is installed.</span></span>  
  
## <a name="creating-a-control-that-has-a-serializable-collection"></a><span data-ttu-id="f0954-113">Erstellen eines Steuerelements, verfügt über eine serialisierbare Auflistung</span><span class="sxs-lookup"><span data-stu-id="f0954-113">Creating a Control That Has a Serializable Collection</span></span>  
 <span data-ttu-id="f0954-114">Der erste Schritt ist zum Erstellen eines Steuerelements, das eine serialisierbare Auflistung als Eigenschaft verfügt.</span><span class="sxs-lookup"><span data-stu-id="f0954-114">The first step is to create a control that has a serializable collection as a property.</span></span> <span data-ttu-id="f0954-115">Sie können den Inhalt dieser Sammlung mit Bearbeiten der **Auflistungs-Editor**, die Sie zugreifen können die **Eigenschaften** Fenster.</span><span class="sxs-lookup"><span data-stu-id="f0954-115">You can edit the contents of this collection using the **Collection Editor**, which you can access from the **Properties** window.</span></span>  
  
#### <a name="to-create-a-control-with-a-serializable-collection"></a><span data-ttu-id="f0954-116">So erstellen Sie ein Steuerelement über eine serialisierbare Auflistung</span><span class="sxs-lookup"><span data-stu-id="f0954-116">To create a control with a serializable collection</span></span>  
  
1.  <span data-ttu-id="f0954-117">Erstellen Sie ein Windows-Steuerelementbibliothek-Projekt namens `SerializationDemoControlLib`.</span><span class="sxs-lookup"><span data-stu-id="f0954-117">Create a Windows Control Library project called `SerializationDemoControlLib`.</span></span> <span data-ttu-id="f0954-118">Weitere Informationen finden Sie unter [Vorlage für Windows-Steuerelementbibliothek](https://docs.microsoft.com/previous-versions/kxczf775(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="f0954-118">For more information, see [Windows Control Library Template](https://docs.microsoft.com/previous-versions/kxczf775(v=vs.100)).</span></span>  
  
2.  <span data-ttu-id="f0954-119">Benennen Sie `UserControl1` zu `SerializationDemoControl`.</span><span class="sxs-lookup"><span data-stu-id="f0954-119">Rename `UserControl1` to `SerializationDemoControl`.</span></span> <span data-ttu-id="f0954-120">Weitere Informationen finden Sie unter [Umbenennen eines Codesymbols](/visualstudio/ide/reference/rename).</span><span class="sxs-lookup"><span data-stu-id="f0954-120">For more information, see [Rename a code symbol refactoring](/visualstudio/ide/reference/rename).</span></span>  
  
3.  <span data-ttu-id="f0954-121">In der **Eigenschaften** legen den Wert des der <xref:System.Windows.Forms.Padding.All%2A?displayProperty=nameWithType> Eigenschaft `10`.</span><span class="sxs-lookup"><span data-stu-id="f0954-121">In the **Properties** window, set the value of the <xref:System.Windows.Forms.Padding.All%2A?displayProperty=nameWithType> property to `10`.</span></span>  
  
4.  <span data-ttu-id="f0954-122">Stelle eine <xref:System.Windows.Forms.TextBox> steuern, der `SerializationDemoControl`.</span><span class="sxs-lookup"><span data-stu-id="f0954-122">Place a <xref:System.Windows.Forms.TextBox> control in the `SerializationDemoControl`.</span></span>  
  
5.  <span data-ttu-id="f0954-123">Wählen Sie das <xref:System.Windows.Forms.TextBox>-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="f0954-123">Select the <xref:System.Windows.Forms.TextBox> control.</span></span> <span data-ttu-id="f0954-124">In der **Eigenschaften** Fenster die folgenden Eigenschaften festlegen.</span><span class="sxs-lookup"><span data-stu-id="f0954-124">In the **Properties** window, set the following properties.</span></span>  
  
    |<span data-ttu-id="f0954-125">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="f0954-125">Property</span></span>|<span data-ttu-id="f0954-126">Ändern in</span><span class="sxs-lookup"><span data-stu-id="f0954-126">Change to</span></span>|  
    |--------------|---------------|  
    |**<span data-ttu-id="f0954-127">Multiline</span><span class="sxs-lookup"><span data-stu-id="f0954-127">Multiline</span></span>**|`true`|  
    |**<span data-ttu-id="f0954-128">Andocken</span><span class="sxs-lookup"><span data-stu-id="f0954-128">Dock</span></span>**|<xref:System.Windows.Forms.DockStyle.Fill>|  
    |**<span data-ttu-id="f0954-129">ScrollBars</span><span class="sxs-lookup"><span data-stu-id="f0954-129">ScrollBars</span></span>**|<xref:System.Windows.Forms.ScrollBars.Vertical>|  
    |**<span data-ttu-id="f0954-130">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="f0954-130">ReadOnly</span></span>**|`true`|  
  
6.  <span data-ttu-id="f0954-131">In der **Code-Editor**, deklarieren Sie einen Zeichenfolgen-Arrayfeld mit dem Namen `stringsValue` in `SerializationDemoControl`.</span><span class="sxs-lookup"><span data-stu-id="f0954-131">In the **Code Editor**, declare a string array field named `stringsValue` in `SerializationDemoControl`.</span></span>  
  
     [!code-cpp[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/cpp/form1.cpp#4)]
     [!code-csharp[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/CS/form1.cs#4)]
     [!code-vb[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/VB/form1.vb#4)]  
  
7.  <span data-ttu-id="f0954-132">Definieren der `Strings` Eigenschaft für die `SerializationDemoControl`.</span><span class="sxs-lookup"><span data-stu-id="f0954-132">Define the `Strings` property on the `SerializationDemoControl`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f0954-133">Die <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content> Wert wird verwendet, um die Serialisierung der Auflistung zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="f0954-133">The <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content> value is used to enable serialization of the collection.</span></span>  
  
 [!code-cpp[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/cpp/form1.cpp#5)]
 [!code-csharp[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/CS/form1.cs#5)]
 [!code-vb[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/VB/form1.vb#5)]  
  
1.  <span data-ttu-id="f0954-134">Drücken Sie F5, um das Projekt zu erstellen, und führen Sie das Steuerelement im **UserControl-Testcontainer** aus.</span><span class="sxs-lookup"><span data-stu-id="f0954-134">Press F5 to build the project and run your control in the **UserControl Test Container**.</span></span>  
  
2.  <span data-ttu-id="f0954-135">Suchen der `Strings` -Eigenschaft in der <xref:System.Windows.Forms.PropertyGrid> von der **UserControl-Testcontainer**.</span><span class="sxs-lookup"><span data-stu-id="f0954-135">Find the `Strings` property in the <xref:System.Windows.Forms.PropertyGrid> of the **UserControl Test Container**.</span></span> <span data-ttu-id="f0954-136">Klicken Sie auf die `Strings` -Eigenschaft, klicken Sie dann auf die Auslassungspunkte (![VisualStudioEllipsesButton-bildschirmabbildung](../media/vbellipsesbutton.png "VbEllipsesButton")) die Schaltfläche, um die **Zeichenfolgen-Editor**.</span><span class="sxs-lookup"><span data-stu-id="f0954-136">Click the `Strings` property, then click the ellipsis (![VisualStudioEllipsesButton screenshot](../media/vbellipsesbutton.png "vbEllipsesButton")) button to open the **String Collection Editor**.</span></span>  
  
3.  <span data-ttu-id="f0954-137">Geben Sie mehrere Zeichenfolgen in die **Zeichenfolgen-Editor**.</span><span class="sxs-lookup"><span data-stu-id="f0954-137">Enter several strings in the **String Collection Editor**.</span></span> <span data-ttu-id="f0954-138">Trennen sie durch Drücken der EINGABETASTE am Ende einer Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="f0954-138">Separate them by pressing the ENTER key at the end of each string.</span></span> <span data-ttu-id="f0954-139">Klicken Sie auf **OK** , wenn Sie Zeichenfolgen eingegeben haben.</span><span class="sxs-lookup"><span data-stu-id="f0954-139">Click **OK** when you are finished entering strings.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f0954-140">Die eingegebene Zeichenfolgen angezeigt werden, der <xref:System.Windows.Forms.TextBox> von der `SerializationDemoControl`.</span><span class="sxs-lookup"><span data-stu-id="f0954-140">The strings you typed appear in the <xref:System.Windows.Forms.TextBox> of the `SerializationDemoControl`.</span></span>  
  
## <a name="serializing-a-collection-property"></a><span data-ttu-id="f0954-141">Eine Auflistungseigenschaft serialisiert</span><span class="sxs-lookup"><span data-stu-id="f0954-141">Serializing a Collection Property</span></span>  
 <span data-ttu-id="f0954-142">Um das Serialisierungsverhalten des Steuerelements zu testen, werden Sie ihn in einem Formular zu platzieren und ändern Sie den Inhalt der Auflistung mit den **Auflistungs-Editor**.</span><span class="sxs-lookup"><span data-stu-id="f0954-142">To test the serialization behavior of your control, you will place it on a form and change the contents of the collection with the **Collection Editor**.</span></span> <span data-ttu-id="f0954-143">Sie sehen den Status für die serialisierte Auflistung anhand einer speziellen Designer-Datei, in dem die **Windows Forms-Designer** Code ausgibt.</span><span class="sxs-lookup"><span data-stu-id="f0954-143">You can see the serialized collection state by looking at a special designer file, into which the **Windows Forms Designer** emits code.</span></span>  
  
#### <a name="to-serialize-a-collection"></a><span data-ttu-id="f0954-144">Um eine Auflistung zu serialisieren.</span><span class="sxs-lookup"><span data-stu-id="f0954-144">To serialize a collection</span></span>  
  
1.  <span data-ttu-id="f0954-145">Fügen Sie ein Windows-Anwendungsprojekt mit der Lösung.</span><span class="sxs-lookup"><span data-stu-id="f0954-145">Add a Windows Application project to the solution.</span></span> <span data-ttu-id="f0954-146">Benennen Sie das Projekt mit `SerializationDemoControlTest`.</span><span class="sxs-lookup"><span data-stu-id="f0954-146">Name the project `SerializationDemoControlTest`.</span></span>  
  
2.  <span data-ttu-id="f0954-147">In der **Toolbox**, suchen Sie die Registerkarte mit dem Namen **SerializationDemoControlLib Components**.</span><span class="sxs-lookup"><span data-stu-id="f0954-147">In the **Toolbox**, find the tab named **SerializationDemoControlLib Components**.</span></span> <span data-ttu-id="f0954-148">In dieser Registerkarte finden Sie die `SerializationDemoControl`.</span><span class="sxs-lookup"><span data-stu-id="f0954-148">In this tab, you will find the `SerializationDemoControl`.</span></span> <span data-ttu-id="f0954-149">Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Automatisches Füllen der Toolbox mit benutzerdefinierten Komponenten](walkthrough-automatically-populating-the-toolbox-with-custom-components.md).</span><span class="sxs-lookup"><span data-stu-id="f0954-149">For more information, see [Walkthrough: Automatically Populating the Toolbox with Custom Components](walkthrough-automatically-populating-the-toolbox-with-custom-components.md).</span></span>  
  
3.  <span data-ttu-id="f0954-150">Stelle eine `SerializationDemoControl` in Ihrem Formular.</span><span class="sxs-lookup"><span data-stu-id="f0954-150">Place a `SerializationDemoControl` on your form.</span></span>  
  
4.  <span data-ttu-id="f0954-151">Suchen der `Strings` -Eigenschaft in der **Eigenschaften** Fenster.</span><span class="sxs-lookup"><span data-stu-id="f0954-151">Find the `Strings` property in the **Properties** window.</span></span> <span data-ttu-id="f0954-152">Klicken Sie auf die `Strings` -Eigenschaft, klicken Sie dann auf die Auslassungspunkte (![VisualStudioEllipsesButton-bildschirmabbildung](../media/vbellipsesbutton.png "VbEllipsesButton")) die Schaltfläche, um die **Zeichenfolgen-Editor**.</span><span class="sxs-lookup"><span data-stu-id="f0954-152">Click the `Strings` property, then click the ellipsis (![VisualStudioEllipsesButton screenshot](../media/vbellipsesbutton.png "vbEllipsesButton")) button to open the **String Collection Editor**.</span></span>  
  
5.  <span data-ttu-id="f0954-153">Geben Sie mehrere Zeichenfolgen in die **Zeichenfolgen-Editor**.</span><span class="sxs-lookup"><span data-stu-id="f0954-153">Type several strings in the **String Collection Editor**.</span></span> <span data-ttu-id="f0954-154">Trennen sie durch Drücken der EINGABETASTE am Ende einer Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="f0954-154">Separate them by pressing the ENTER key at the end of each string.</span></span> <span data-ttu-id="f0954-155">Klicken Sie auf **OK** , wenn Sie Zeichenfolgen eingegeben haben.</span><span class="sxs-lookup"><span data-stu-id="f0954-155">Click **OK** when you are finished entering strings.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f0954-156">Die eingegebene Zeichenfolgen angezeigt werden, der <xref:System.Windows.Forms.TextBox> von der `SerializationDemoControl`.</span><span class="sxs-lookup"><span data-stu-id="f0954-156">The strings you typed appear in the <xref:System.Windows.Forms.TextBox> of the `SerializationDemoControl`.</span></span>  
  
1.  <span data-ttu-id="f0954-157">Klicken Sie im **Projektmappen-Explorer** auf die Schaltfläche **Alle Dateien anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="f0954-157">In **Solution Explorer**, click the **Show All Files** button.</span></span>  
  
2.  <span data-ttu-id="f0954-158">Öffnen der **Form1** Knoten.</span><span class="sxs-lookup"><span data-stu-id="f0954-158">Open the **Form1** node.</span></span> <span data-ttu-id="f0954-159">Darunter befindet sich eine Datei namens **Form1.Designer.cs** oder **Form1.Designer.vb**.</span><span class="sxs-lookup"><span data-stu-id="f0954-159">Beneath it is a file called **Form1.Designer.cs** or **Form1.Designer.vb**.</span></span> <span data-ttu-id="f0954-160">Dies ist die Datei in dem die **Windows Forms-Designer** gibt Code aus, das den Entwurfszeitzustand des Formulars und seiner untergeordneten Steuerelemente darstellt.</span><span class="sxs-lookup"><span data-stu-id="f0954-160">This is the file into which the **Windows Forms Designer** emits code representing the design-time state of your form and its child controls.</span></span> <span data-ttu-id="f0954-161">Öffnen Sie diese Datei im **Code-Editor**.</span><span class="sxs-lookup"><span data-stu-id="f0954-161">Open this file in the **Code Editor**.</span></span>  
  
3.  <span data-ttu-id="f0954-162">Öffnen Sie den Bereich **Windows Form Designer generierter Code** und suchen Sie den Abschnitt mit der Bezeichnung **serializationDemoControl1**.</span><span class="sxs-lookup"><span data-stu-id="f0954-162">Open the region called **Windows Form Designer generated code** and find the section labeled **serializationDemoControl1**.</span></span> <span data-ttu-id="f0954-163">Unter diesen Label befindet sich der Code, der den serialisierten Zustand des Steuerelements darstellt.</span><span class="sxs-lookup"><span data-stu-id="f0954-163">Beneath this label is the code representing the serialized state of your control.</span></span> <span data-ttu-id="f0954-164">Die Zeichenfolgen, die in Schritt 5 eingegebenen angezeigt werden, in einer Zuweisung auf die `Strings` Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="f0954-164">The strings you typed in step 5 appear in an assignment to the `Strings` property.</span></span> <span data-ttu-id="f0954-165">Die folgenden Codebeispiele in c# und Visual Basic-Code anzeigen ähnelt, wird angezeigt, wenn Sie die Zeichenfolgen "Rot", "orange" und "Gelb" eingegeben.</span><span class="sxs-lookup"><span data-stu-id="f0954-165">The following code examples in C# and Visual Basic, show code similar to what you will see if you typed the strings "red", "orange", and "yellow".</span></span>  
  
    ```csharp  
    this.serializationDemoControl1.Strings = new string[] {  
            "red",  
            "orange",  
            "yellow"};  
    ```  
    
    ```vb  
    Me.serializationDemoControl1.Strings = New String() {"red", "orange", "yellow"}  
    ```
  
4.  <span data-ttu-id="f0954-166">In der **Code-Editor**, ändern Sie den Wert von der <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute> auf die `Strings` Eigenschaft <xref:System.ComponentModel.DesignerSerializationVisibility.Hidden>.</span><span class="sxs-lookup"><span data-stu-id="f0954-166">In the **Code Editor**, change the value of the <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute> on the `Strings` property to <xref:System.ComponentModel.DesignerSerializationVisibility.Hidden>.</span></span>  
  
    ```csharp  
    [DesignerSerializationVisibility(DesignerSerializationVisibility.Hidden)]  
    ```  
    ```vb  
    <DesignerSerializationVisibility(DesignerSerializationVisibility.Hidden)> _  
    ```  
  
5. <span data-ttu-id="f0954-167">Erneutes Erstellen von Projektmappen und wiederholen Sie die Schritte 3 und 4.</span><span class="sxs-lookup"><span data-stu-id="f0954-167">Rebuild the solution and repeat steps 3 and 4.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f0954-168">In diesem Fall die **Windows Forms-Designer** gibt keine Zuweisung, die `Strings` Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="f0954-168">In this case, the **Windows Forms Designer** emits no assignment to the `Strings` property.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="f0954-169">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="f0954-169">Next Steps</span></span>  
 <span data-ttu-id="f0954-170">Sobald Sie wissen wie eine Auflistung von standardmäßigen Typen serialisieren, sollten Sie Ihre benutzerdefinierten Steuerelemente besser in der Entwurfszeit-Umgebung integrieren.</span><span class="sxs-lookup"><span data-stu-id="f0954-170">Once you know how to serialize a collection of standard types, consider integrating your custom controls more deeply into the design-time environment.</span></span> <span data-ttu-id="f0954-171">In den folgenden Themen wird beschrieben, wie die während der Entwurfszeit-Integration von benutzerdefinierten Steuerelementen zu verbessern:</span><span class="sxs-lookup"><span data-stu-id="f0954-171">The following topics describe how to enhance the design-time integration of your custom controls:</span></span>  
  
-   [<span data-ttu-id="f0954-172">Architektur der Entwurfszeit</span><span class="sxs-lookup"><span data-stu-id="f0954-172">Design-Time Architecture</span></span>](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/c5z9s1h4(v=vs.120))  
  
-   [<span data-ttu-id="f0954-173">Attribute in Windows Forms-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="f0954-173">Attributes in Windows Forms Controls</span></span>](attributes-in-windows-forms-controls.md)  
  
-   [<span data-ttu-id="f0954-174">Übersicht über die Designerserialisierung</span><span class="sxs-lookup"><span data-stu-id="f0954-174">Designer Serialization Overview</span></span>](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171834(v=vs.120))  
  
-   [<span data-ttu-id="f0954-175">Exemplarische Vorgehensweise: Erstellen eines Windows Forms-Steuerelements, das Visual Studio-Entwurfszeitfunktionen nutzt</span><span class="sxs-lookup"><span data-stu-id="f0954-175">Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features</span></span>](creating-a-wf-control-design-time-features.md)  
  
## <a name="see-also"></a><span data-ttu-id="f0954-176">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f0954-176">See also</span></span>

- <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute>
- [<span data-ttu-id="f0954-177">Übersicht über die Designerserialisierung</span><span class="sxs-lookup"><span data-stu-id="f0954-177">Designer Serialization Overview</span></span>](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171834(v=vs.120))
- [<span data-ttu-id="f0954-178">Vorgehensweise: Serialisieren der Auflistungen von Standardtypen mit dem DesignerSerializationVisibilityAttribute</span><span class="sxs-lookup"><span data-stu-id="f0954-178">How to: Serialize Collections of Standard Types with the DesignerSerializationVisibilityAttribute</span></span>](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171833(v=vs.120))
- [<span data-ttu-id="f0954-179">Exemplarische Vorgehensweise: Automatisches Füllen der Toolbox mit benutzerdefinierten Komponenten</span><span class="sxs-lookup"><span data-stu-id="f0954-179">Walkthrough: Automatically Populating the Toolbox with Custom Components</span></span>](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)
