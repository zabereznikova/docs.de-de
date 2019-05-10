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
ms.openlocfilehash: c8321f98b25026e32e7c69f7029f2c589d0567f7
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211602"
---
# <a name="walkthrough-serializing-collections-of-standard-types-with-the-designerserializationvisibilityattribute"></a><span data-ttu-id="1eb76-102">Exemplarische Vorgehensweise: Serialisieren der Auflistungen von Standardtypen mit dem DesignerSerializationVisibilityAttribute</span><span class="sxs-lookup"><span data-stu-id="1eb76-102">Walkthrough: Serializing Collections of Standard Types with the DesignerSerializationVisibilityAttribute</span></span>

<span data-ttu-id="1eb76-103">Ihre benutzerdefinierten Steuerelemente werden manchmal eine Auflistung als Eigenschaft verfügbar machen.</span><span class="sxs-lookup"><span data-stu-id="1eb76-103">Your custom controls will sometimes expose a collection as a property.</span></span> <span data-ttu-id="1eb76-104">In dieser exemplarischen Vorgehensweise wird veranschaulicht, wie Sie mit der <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute> Klasse, um zu steuern, wie eine Auflistung zur Entwurfszeit serialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="1eb76-104">This walkthrough demonstrates how to use the <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute> class to control how a collection is serialized at design time.</span></span> <span data-ttu-id="1eb76-105">Anwenden der <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content> Wert, der die Auflistungseigenschaft wird sichergestellt, dass die Eigenschaft serialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="1eb76-105">Applying the <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content> value to your collection property ensures that the property will be serialized.</span></span>

<span data-ttu-id="1eb76-106">Zum Kopieren des Codes in diesem Thema als einzelne Auflistung lesen Sie [Vorgehensweise: Serialisieren der Auflistungen von Standardtypen mit dem DesignerSerializationVisibilityAttribute](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171833(v=vs.120)).</span><span class="sxs-lookup"><span data-stu-id="1eb76-106">To copy the code in this topic as a single listing, see [How to: Serialize Collections of Standard Types with the DesignerSerializationVisibilityAttribute](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171833(v=vs.120)).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1eb76-107">Vorraussetzungen</span><span class="sxs-lookup"><span data-stu-id="1eb76-107">Prerequisites</span></span>

<span data-ttu-id="1eb76-108">Für diese exemplarische Vorgehensweise benötigen Sie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="1eb76-108">You need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-a-control-with-a-serializable-collection"></a><span data-ttu-id="1eb76-109">Erstellen eines Steuerelements über eine serialisierbare Auflistung</span><span class="sxs-lookup"><span data-stu-id="1eb76-109">Create a control with a serializable collection</span></span>

<span data-ttu-id="1eb76-110">Der erste Schritt ist zum Erstellen eines Steuerelements, das eine serialisierbare Auflistung als Eigenschaft verfügt.</span><span class="sxs-lookup"><span data-stu-id="1eb76-110">The first step is to create a control that has a serializable collection as a property.</span></span> <span data-ttu-id="1eb76-111">Sie können den Inhalt dieser Sammlung mit Bearbeiten der **Auflistungs-Editor**, die Sie zugreifen können die **Eigenschaften** Fenster.</span><span class="sxs-lookup"><span data-stu-id="1eb76-111">You can edit the contents of this collection using the **Collection Editor**, which you can access from the **Properties** window.</span></span>

1. <span data-ttu-id="1eb76-112">Erstellen Sie in Visual Studio ein Windows-Steuerelementbibliothek-Projekt namens `SerializationDemoControlLib`.</span><span class="sxs-lookup"><span data-stu-id="1eb76-112">In Visual Studio, create a Windows Control Library project called `SerializationDemoControlLib`.</span></span> <span data-ttu-id="1eb76-113">Weitere Informationen finden Sie unter [Vorlage für Windows-Steuerelementbibliothek](https://docs.microsoft.com/previous-versions/kxczf775(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="1eb76-113">For more information, see [Windows Control Library Template](https://docs.microsoft.com/previous-versions/kxczf775(v=vs.100)).</span></span>

2. <span data-ttu-id="1eb76-114">Benennen Sie `UserControl1` zu `SerializationDemoControl`.</span><span class="sxs-lookup"><span data-stu-id="1eb76-114">Rename `UserControl1` to `SerializationDemoControl`.</span></span> <span data-ttu-id="1eb76-115">Weitere Informationen finden Sie unter [Umbenennen eines Codesymbols](/visualstudio/ide/reference/rename).</span><span class="sxs-lookup"><span data-stu-id="1eb76-115">For more information, see [Rename a code symbol refactoring](/visualstudio/ide/reference/rename).</span></span>

3. <span data-ttu-id="1eb76-116">In der **Eigenschaften** legen den Wert des der <xref:System.Windows.Forms.Padding.All%2A?displayProperty=nameWithType> Eigenschaft `10`.</span><span class="sxs-lookup"><span data-stu-id="1eb76-116">In the **Properties** window, set the value of the <xref:System.Windows.Forms.Padding.All%2A?displayProperty=nameWithType> property to `10`.</span></span>

4. <span data-ttu-id="1eb76-117">Stelle eine <xref:System.Windows.Forms.TextBox> steuern, der `SerializationDemoControl`.</span><span class="sxs-lookup"><span data-stu-id="1eb76-117">Place a <xref:System.Windows.Forms.TextBox> control in the `SerializationDemoControl`.</span></span>

5. <span data-ttu-id="1eb76-118">Wählen Sie das <xref:System.Windows.Forms.TextBox>-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="1eb76-118">Select the <xref:System.Windows.Forms.TextBox> control.</span></span> <span data-ttu-id="1eb76-119">In der **Eigenschaften** Fenster die folgenden Eigenschaften festlegen.</span><span class="sxs-lookup"><span data-stu-id="1eb76-119">In the **Properties** window, set the following properties.</span></span>

    |<span data-ttu-id="1eb76-120">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="1eb76-120">Property</span></span>|<span data-ttu-id="1eb76-121">Ändern in</span><span class="sxs-lookup"><span data-stu-id="1eb76-121">Change to</span></span>|
    |--------------|---------------|
    |<span data-ttu-id="1eb76-122">**Multiline**</span><span class="sxs-lookup"><span data-stu-id="1eb76-122">**Multiline**</span></span>|`true`|
    |<span data-ttu-id="1eb76-123">**Dock**</span><span class="sxs-lookup"><span data-stu-id="1eb76-123">**Dock**</span></span>|<xref:System.Windows.Forms.DockStyle.Fill>|
    |<span data-ttu-id="1eb76-124">**ScrollBars**</span><span class="sxs-lookup"><span data-stu-id="1eb76-124">**ScrollBars**</span></span>|<xref:System.Windows.Forms.ScrollBars.Vertical>|
    |<span data-ttu-id="1eb76-125">**ReadOnly**</span><span class="sxs-lookup"><span data-stu-id="1eb76-125">**ReadOnly**</span></span>|`true`|

6. <span data-ttu-id="1eb76-126">In der **Code-Editor**, deklarieren Sie einen Zeichenfolgen-Arrayfeld mit dem Namen `stringsValue` in `SerializationDemoControl`.</span><span class="sxs-lookup"><span data-stu-id="1eb76-126">In the **Code Editor**, declare a string array field named `stringsValue` in `SerializationDemoControl`.</span></span>

     [!code-cpp[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/cpp/form1.cpp#4)]
     [!code-csharp[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/CS/form1.cs#4)]
     [!code-vb[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/VB/form1.vb#4)]

7. <span data-ttu-id="1eb76-127">Definieren der `Strings` Eigenschaft für die `SerializationDemoControl`.</span><span class="sxs-lookup"><span data-stu-id="1eb76-127">Define the `Strings` property on the `SerializationDemoControl`.</span></span>

   > [!NOTE]
   > <span data-ttu-id="1eb76-128">Die <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content> Wert wird verwendet, um die Serialisierung der Auflistung zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="1eb76-128">The <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content> value is used to enable serialization of the collection.</span></span>

   [!code-cpp[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/cpp/form1.cpp#5)]
   [!code-csharp[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/CS/form1.cs#5)]
   [!code-vb[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/VB/form1.vb#5)]

8. <span data-ttu-id="1eb76-129">Drücken Sie **F5** zum Erstellen des Projekts, und führen Sie das Steuerelement der **UserControl-Testcontainer**.</span><span class="sxs-lookup"><span data-stu-id="1eb76-129">Press **F5** to build the project and run your control in the **UserControl Test Container**.</span></span>

9. <span data-ttu-id="1eb76-130">Suchen der `Strings` -Eigenschaft in der <xref:System.Windows.Forms.PropertyGrid> von der **UserControl-Testcontainer**.</span><span class="sxs-lookup"><span data-stu-id="1eb76-130">Find the `Strings` property in the <xref:System.Windows.Forms.PropertyGrid> of the **UserControl Test Container**.</span></span> <span data-ttu-id="1eb76-131">Klicken Sie auf die `Strings` -Eigenschaft, klicken Sie dann auf die Auslassungspunkte (![VisualStudioEllipsesButton-bildschirmabbildung](../media/vbellipsesbutton.png "VbEllipsesButton")) die Schaltfläche, um die **Zeichenfolgen-Editor**.</span><span class="sxs-lookup"><span data-stu-id="1eb76-131">Click the `Strings` property, then click the ellipsis (![VisualStudioEllipsesButton screenshot](../media/vbellipsesbutton.png "vbEllipsesButton")) button to open the **String Collection Editor**.</span></span>

10. <span data-ttu-id="1eb76-132">Geben Sie mehrere Zeichenfolgen in die **Zeichenfolgen-Editor**.</span><span class="sxs-lookup"><span data-stu-id="1eb76-132">Enter several strings in the **String Collection Editor**.</span></span> <span data-ttu-id="1eb76-133">Trennen Sie diese durch Drücken der **EINGABETASTE** Schlüssel am Ende einer Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="1eb76-133">Separate them by pressing the **Enter** key at the end of each string.</span></span> <span data-ttu-id="1eb76-134">Klicken Sie auf **OK** , wenn Sie Zeichenfolgen eingegeben haben.</span><span class="sxs-lookup"><span data-stu-id="1eb76-134">Click **OK** when you are finished entering strings.</span></span>

   > [!NOTE]
   > <span data-ttu-id="1eb76-135">Die eingegebene Zeichenfolgen angezeigt werden, der <xref:System.Windows.Forms.TextBox> von der `SerializationDemoControl`.</span><span class="sxs-lookup"><span data-stu-id="1eb76-135">The strings you typed appear in the <xref:System.Windows.Forms.TextBox> of the `SerializationDemoControl`.</span></span>

## <a name="serializing-a-collection-property"></a><span data-ttu-id="1eb76-136">Eine Auflistungseigenschaft serialisiert</span><span class="sxs-lookup"><span data-stu-id="1eb76-136">Serializing a Collection Property</span></span>

<span data-ttu-id="1eb76-137">Um das Serialisierungsverhalten des Steuerelements zu testen, werden Sie ihn in einem Formular zu platzieren und ändern Sie den Inhalt der Auflistung mit den **Auflistungs-Editor**.</span><span class="sxs-lookup"><span data-stu-id="1eb76-137">To test the serialization behavior of your control, you will place it on a form and change the contents of the collection with the **Collection Editor**.</span></span> <span data-ttu-id="1eb76-138">Sie sehen den Status für die serialisierte Auflistung anhand einer speziellen Designer-Datei in dem die **Windows Forms-Designer** Code ausgibt.</span><span class="sxs-lookup"><span data-stu-id="1eb76-138">You can see the serialized collection state by looking at a special designer file into which the **Windows Forms Designer** emits code.</span></span>

### <a name="to-serialize-a-collection"></a><span data-ttu-id="1eb76-139">Um eine Auflistung zu serialisieren.</span><span class="sxs-lookup"><span data-stu-id="1eb76-139">To serialize a collection</span></span>

1. <span data-ttu-id="1eb76-140">Fügen Sie ein Windows-Anwendungsprojekt mit der Lösung.</span><span class="sxs-lookup"><span data-stu-id="1eb76-140">Add a Windows Application project to the solution.</span></span> <span data-ttu-id="1eb76-141">Benennen Sie das Projekt mit `SerializationDemoControlTest`.</span><span class="sxs-lookup"><span data-stu-id="1eb76-141">Name the project `SerializationDemoControlTest`.</span></span>

2. <span data-ttu-id="1eb76-142">In der **Toolbox**, suchen Sie die Registerkarte mit dem Namen **SerializationDemoControlLib Components**.</span><span class="sxs-lookup"><span data-stu-id="1eb76-142">In the **Toolbox**, find the tab named **SerializationDemoControlLib Components**.</span></span> <span data-ttu-id="1eb76-143">In dieser Registerkarte finden Sie die `SerializationDemoControl`.</span><span class="sxs-lookup"><span data-stu-id="1eb76-143">In this tab, you will find the `SerializationDemoControl`.</span></span> <span data-ttu-id="1eb76-144">Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Automatisches Füllen der Toolbox mit benutzerdefinierten Komponenten](walkthrough-automatically-populating-the-toolbox-with-custom-components.md).</span><span class="sxs-lookup"><span data-stu-id="1eb76-144">For more information, see [Walkthrough: Automatically Populating the Toolbox with Custom Components](walkthrough-automatically-populating-the-toolbox-with-custom-components.md).</span></span>

3. <span data-ttu-id="1eb76-145">Stelle eine `SerializationDemoControl` in Ihrem Formular.</span><span class="sxs-lookup"><span data-stu-id="1eb76-145">Place a `SerializationDemoControl` on your form.</span></span>

4. <span data-ttu-id="1eb76-146">Suchen der `Strings` -Eigenschaft in der **Eigenschaften** Fenster.</span><span class="sxs-lookup"><span data-stu-id="1eb76-146">Find the `Strings` property in the **Properties** window.</span></span> <span data-ttu-id="1eb76-147">Klicken Sie auf die `Strings` -Eigenschaft, klicken Sie dann auf die Auslassungspunkte (![VisualStudioEllipsesButton-bildschirmabbildung](../media/vbellipsesbutton.png "VbEllipsesButton")) die Schaltfläche, um die **Zeichenfolgen-Editor**.</span><span class="sxs-lookup"><span data-stu-id="1eb76-147">Click the `Strings` property, then click the ellipsis (![VisualStudioEllipsesButton screenshot](../media/vbellipsesbutton.png "vbEllipsesButton")) button to open the **String Collection Editor**.</span></span>

5. <span data-ttu-id="1eb76-148">Geben Sie mehrere Zeichenfolgen in die **Zeichenfolgen-Editor**.</span><span class="sxs-lookup"><span data-stu-id="1eb76-148">Type several strings in the **String Collection Editor**.</span></span> <span data-ttu-id="1eb76-149">Trennen sie durch Drücken der EINGABETASTE am Ende einer Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="1eb76-149">Separate them by pressing the ENTER key at the end of each string.</span></span> <span data-ttu-id="1eb76-150">Klicken Sie auf **OK** , wenn Sie Zeichenfolgen eingegeben haben.</span><span class="sxs-lookup"><span data-stu-id="1eb76-150">Click **OK** when you are finished entering strings.</span></span>

> [!NOTE]
> <span data-ttu-id="1eb76-151">Die eingegebene Zeichenfolgen angezeigt werden, der <xref:System.Windows.Forms.TextBox> von der `SerializationDemoControl`.</span><span class="sxs-lookup"><span data-stu-id="1eb76-151">The strings you typed appear in the <xref:System.Windows.Forms.TextBox> of the `SerializationDemoControl`.</span></span>

1. <span data-ttu-id="1eb76-152">Klicken Sie im **Projektmappen-Explorer** auf die Schaltfläche **Alle Dateien anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="1eb76-152">In **Solution Explorer**, click the **Show All Files** button.</span></span>

2. <span data-ttu-id="1eb76-153">Öffnen der **Form1** Knoten.</span><span class="sxs-lookup"><span data-stu-id="1eb76-153">Open the **Form1** node.</span></span> <span data-ttu-id="1eb76-154">Darunter befindet sich eine Datei namens **Form1.Designer.cs** oder **Form1.Designer.vb**.</span><span class="sxs-lookup"><span data-stu-id="1eb76-154">Beneath it is a file called **Form1.Designer.cs** or **Form1.Designer.vb**.</span></span> <span data-ttu-id="1eb76-155">Dies ist die Datei in dem die **Windows Forms-Designer** gibt Code aus, das den Entwurfszeitzustand des Formulars und seiner untergeordneten Steuerelemente darstellt.</span><span class="sxs-lookup"><span data-stu-id="1eb76-155">This is the file into which the **Windows Forms Designer** emits code representing the design-time state of your form and its child controls.</span></span> <span data-ttu-id="1eb76-156">Öffnen Sie diese Datei im **Code-Editor**.</span><span class="sxs-lookup"><span data-stu-id="1eb76-156">Open this file in the **Code Editor**.</span></span>

3. <span data-ttu-id="1eb76-157">Öffnen Sie den Bereich **Windows Form Designer generierter Code** und suchen Sie den Abschnitt mit der Bezeichnung **serializationDemoControl1**.</span><span class="sxs-lookup"><span data-stu-id="1eb76-157">Open the region called **Windows Form Designer generated code** and find the section labeled **serializationDemoControl1**.</span></span> <span data-ttu-id="1eb76-158">Unter diesen Label befindet sich der Code, der den serialisierten Zustand des Steuerelements darstellt.</span><span class="sxs-lookup"><span data-stu-id="1eb76-158">Beneath this label is the code representing the serialized state of your control.</span></span> <span data-ttu-id="1eb76-159">Die Zeichenfolgen, die in Schritt 5 eingegebenen angezeigt werden, in einer Zuweisung auf die `Strings` Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="1eb76-159">The strings you typed in step 5 appear in an assignment to the `Strings` property.</span></span> <span data-ttu-id="1eb76-160">Die folgenden Codebeispiele in c# und Visual Basic-Code anzeigen ähnelt, wird angezeigt, wenn Sie die Zeichenfolgen "Rot", "orange" und "Gelb" eingegeben.</span><span class="sxs-lookup"><span data-stu-id="1eb76-160">The following code examples in C# and Visual Basic, show code similar to what you will see if you typed the strings "red", "orange", and "yellow".</span></span>

    ```csharp
    this.serializationDemoControl1.Strings = new string[] {
            "red",
            "orange",
            "yellow"};
    ```

    ```vb
    Me.serializationDemoControl1.Strings = New String() {"red", "orange", "yellow"}
    ```

4. <span data-ttu-id="1eb76-161">In der **Code-Editor**, ändern Sie den Wert von der <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute> auf die `Strings` Eigenschaft <xref:System.ComponentModel.DesignerSerializationVisibility.Hidden>.</span><span class="sxs-lookup"><span data-stu-id="1eb76-161">In the **Code Editor**, change the value of the <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute> on the `Strings` property to <xref:System.ComponentModel.DesignerSerializationVisibility.Hidden>.</span></span>

    ```csharp
    [DesignerSerializationVisibility(DesignerSerializationVisibility.Hidden)]
    ```

    ```vb
    <DesignerSerializationVisibility(DesignerSerializationVisibility.Hidden)> _
    ```

5. <span data-ttu-id="1eb76-162">Erneutes Erstellen von Projektmappen und wiederholen Sie die Schritte 3 und 4.</span><span class="sxs-lookup"><span data-stu-id="1eb76-162">Rebuild the solution and repeat steps 3 and 4.</span></span>

> [!NOTE]
> <span data-ttu-id="1eb76-163">In diesem Fall die **Windows Forms-Designer** gibt keine Zuweisung, die `Strings` Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="1eb76-163">In this case, the **Windows Forms Designer** emits no assignment to the `Strings` property.</span></span>

## <a name="next-steps"></a><span data-ttu-id="1eb76-164">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="1eb76-164">Next Steps</span></span>

<span data-ttu-id="1eb76-165">Sobald Sie wissen wie eine Auflistung von standardmäßigen Typen serialisieren, sollten Sie Ihre benutzerdefinierten Steuerelemente besser in der Entwurfszeit-Umgebung integrieren.</span><span class="sxs-lookup"><span data-stu-id="1eb76-165">Once you know how to serialize a collection of standard types, consider integrating your custom controls more deeply into the design-time environment.</span></span> <span data-ttu-id="1eb76-166">In den folgenden Themen wird beschrieben, wie die während der Entwurfszeit-Integration von benutzerdefinierten Steuerelementen zu verbessern:</span><span class="sxs-lookup"><span data-stu-id="1eb76-166">The following topics describe how to enhance the design-time integration of your custom controls:</span></span>

- <span data-ttu-id="1eb76-167">[Entwurfszeitarchitektur](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/c5z9s1h4(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="1eb76-167">[Design-Time Architecture](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/c5z9s1h4(v=vs.120))</span></span>

- [<span data-ttu-id="1eb76-168">Attribute in Windows Forms-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="1eb76-168">Attributes in Windows Forms Controls</span></span>](attributes-in-windows-forms-controls.md)

- <span data-ttu-id="1eb76-169">[Übersicht über die Designerserialisierung](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171834(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="1eb76-169">[Designer Serialization Overview](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171834(v=vs.120))</span></span>

- [<span data-ttu-id="1eb76-170">Exemplarische Vorgehensweise: Erstellen eines Windows Forms-Steuerelements, das von Visual Studio-Entwurfszeitfunktionen nutzt</span><span class="sxs-lookup"><span data-stu-id="1eb76-170">Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features</span></span>](creating-a-wf-control-design-time-features.md)

## <a name="see-also"></a><span data-ttu-id="1eb76-171">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1eb76-171">See also</span></span>

- <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute>
- <span data-ttu-id="1eb76-172">[Übersicht über die Designerserialisierung](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171834(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="1eb76-172">[Designer Serialization Overview](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171834(v=vs.120))</span></span>
- <span data-ttu-id="1eb76-173">[Vorgehensweise: Serialisieren der Auflistungen von Standardtypen mit dem DesignerSerializationVisibilityAttribute](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171833(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="1eb76-173">[How to: Serialize Collections of Standard Types with the DesignerSerializationVisibilityAttribute](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171833(v=vs.120))</span></span>
- [<span data-ttu-id="1eb76-174">Exemplarische Vorgehensweise: Automatisches Füllen der Toolbox mit benutzerdefinierten Komponenten</span><span class="sxs-lookup"><span data-stu-id="1eb76-174">Walkthrough: Automatically Populating the Toolbox with Custom Components</span></span>](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)
