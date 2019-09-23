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
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: f051d7a51a5f4ff8debf40fafbb8acfd8f7098f5
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2019
ms.locfileid: "71182629"
---
# <a name="walkthrough-serialize-collections-of-standard-types"></a><span data-ttu-id="edbcf-102">Exemplarische Vorgehensweise: Serialisieren von Auflistungen von Standardtypen</span><span class="sxs-lookup"><span data-stu-id="edbcf-102">Walkthrough: Serialize collections of standard types</span></span>

<span data-ttu-id="edbcf-103">Die benutzerdefinierten Steuerelemente machen manchmal eine Auflistung als Eigenschaft verfügbar.</span><span class="sxs-lookup"><span data-stu-id="edbcf-103">Your custom controls will sometimes expose a collection as a property.</span></span> <span data-ttu-id="edbcf-104">Diese exemplarische Vorgehensweise veranschaulicht die Verwendung <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute> der-Klasse, um zu steuern, wie eine Auflistung zur Entwurfszeit serialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="edbcf-104">This walkthrough demonstrates how to use the <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute> class to control how a collection is serialized at design time.</span></span> <span data-ttu-id="edbcf-105">Wenn Sie <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content> den Wert auf Ihre Auflistungs Eigenschaft anwenden, wird sichergestellt, dass die Eigenschaft serialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="edbcf-105">Applying the <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content> value to your collection property ensures that the property will be serialized.</span></span>

<span data-ttu-id="edbcf-106">Zum Kopieren des Codes in diesem Thema als einzelne Auflistung lesen Sie [Vorgehensweise: Serialisieren Sie Auflistungen von Standard Typen mit dem DesignerSerializationVisibilityAttribute](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171833(v=vs.120)).</span><span class="sxs-lookup"><span data-stu-id="edbcf-106">To copy the code in this topic as a single listing, see [How to: Serialize Collections of Standard Types with the DesignerSerializationVisibilityAttribute](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171833(v=vs.120)).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="edbcf-107">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="edbcf-107">Prerequisites</span></span>

<span data-ttu-id="edbcf-108">Für diese exemplarische Vorgehensweise benötigen Sie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="edbcf-108">You need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-a-control-with-a-serializable-collection"></a><span data-ttu-id="edbcf-109">Erstellen eines Steuer Elements mit einer serialisierbaren Sammlung</span><span class="sxs-lookup"><span data-stu-id="edbcf-109">Create a control with a serializable collection</span></span>

<span data-ttu-id="edbcf-110">Der erste Schritt besteht darin, ein Steuerelement zu erstellen, das über eine serialisierbare Auflistung als Eigenschaft verfügt.</span><span class="sxs-lookup"><span data-stu-id="edbcf-110">The first step is to create a control that has a serializable collection as a property.</span></span> <span data-ttu-id="edbcf-111">Sie können den Inhalt dieser Sammlung mit dem Auflistungs- **Editor**bearbeiten, auf den Sie über das **Eigenschaften** Fenster zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="edbcf-111">You can edit the contents of this collection using the **Collection Editor**, which you can access from the **Properties** window.</span></span>

1. <span data-ttu-id="edbcf-112">Erstellen Sie in Visual Studio ein Windows-Steuerelement Bibliothek-Projekt, und nennen Sie es " **SerializationDemoControlLib**".</span><span class="sxs-lookup"><span data-stu-id="edbcf-112">In Visual Studio, create a Windows Control Library project, and name it **SerializationDemoControlLib**.</span></span>

2. <span data-ttu-id="edbcf-113">Benennen `UserControl1` Sie `SerializationDemoControl`in um.</span><span class="sxs-lookup"><span data-stu-id="edbcf-113">Rename `UserControl1` to `SerializationDemoControl`.</span></span> <span data-ttu-id="edbcf-114">Weitere Informationen finden Sie unter [Umbenennen einer Code Symbol Umgestaltung](/visualstudio/ide/reference/rename).</span><span class="sxs-lookup"><span data-stu-id="edbcf-114">For more information, see [Rename a code symbol refactoring](/visualstudio/ide/reference/rename).</span></span>

3. <span data-ttu-id="edbcf-115">Legen Sie im Fenster **Eigenschaften** den Wert <xref:System.Windows.Forms.Padding.All%2A?displayProperty=nameWithType> der-Eigenschaft auf **10**fest.</span><span class="sxs-lookup"><span data-stu-id="edbcf-115">In the **Properties** window, set the value of the <xref:System.Windows.Forms.Padding.All%2A?displayProperty=nameWithType> property to **10**.</span></span>

4. <span data-ttu-id="edbcf-116">Platzieren Sie <xref:System.Windows.Forms.TextBox> ein-Steuer `SerializationDemoControl`Element in der.</span><span class="sxs-lookup"><span data-stu-id="edbcf-116">Place a <xref:System.Windows.Forms.TextBox> control in the `SerializationDemoControl`.</span></span>

5. <span data-ttu-id="edbcf-117">Wählen Sie das <xref:System.Windows.Forms.TextBox>-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="edbcf-117">Select the <xref:System.Windows.Forms.TextBox> control.</span></span> <span data-ttu-id="edbcf-118">Legen Sie im **Eigenschaften** Fenster die folgenden Eigenschaften fest.</span><span class="sxs-lookup"><span data-stu-id="edbcf-118">In the **Properties** window, set the following properties.</span></span>

    |<span data-ttu-id="edbcf-119">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="edbcf-119">Property</span></span>|<span data-ttu-id="edbcf-120">Ändern in</span><span class="sxs-lookup"><span data-stu-id="edbcf-120">Change to</span></span>|
    |--------------|---------------|
    |<span data-ttu-id="edbcf-121">**Multiline**</span><span class="sxs-lookup"><span data-stu-id="edbcf-121">**Multiline**</span></span>|`true`|
    |<span data-ttu-id="edbcf-122">**Dock**</span><span class="sxs-lookup"><span data-stu-id="edbcf-122">**Dock**</span></span>|<xref:System.Windows.Forms.DockStyle.Fill>|
    |<span data-ttu-id="edbcf-123">**ScrollBars**</span><span class="sxs-lookup"><span data-stu-id="edbcf-123">**ScrollBars**</span></span>|<xref:System.Windows.Forms.ScrollBars.Vertical>|
    |<span data-ttu-id="edbcf-124">**ReadOnly**</span><span class="sxs-lookup"><span data-stu-id="edbcf-124">**ReadOnly**</span></span>|`true`|

6. <span data-ttu-id="edbcf-125">Deklarieren Sie im **Code-Editor**ein Zeichen folgen Array `stringsValue` Feld `SerializationDemoControl`mit dem Namen in.</span><span class="sxs-lookup"><span data-stu-id="edbcf-125">In the **Code Editor**, declare a string array field named `stringsValue` in `SerializationDemoControl`.</span></span>

     [!code-cpp[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/cpp/form1.cpp#4)]
     [!code-csharp[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/CS/form1.cs#4)]
     [!code-vb[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/VB/form1.vb#4)]

7. <span data-ttu-id="edbcf-126">Definieren Sie `Strings` die-Eigenschaft `SerializationDemoControl`auf dem.</span><span class="sxs-lookup"><span data-stu-id="edbcf-126">Define the `Strings` property on the `SerializationDemoControl`.</span></span>

   > [!NOTE]
   > <span data-ttu-id="edbcf-127">Der <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content> -Wert wird verwendet, um die Serialisierung der Auflistung zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="edbcf-127">The <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content> value is used to enable serialization of the collection.</span></span>

   [!code-cpp[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/cpp/form1.cpp#5)]
   [!code-csharp[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/CS/form1.cs#5)]
   [!code-vb[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/VB/form1.vb#5)]

8. <span data-ttu-id="edbcf-128">Drücken Sie **F5** , um das Projekt zu erstellen, und führen Sie das Steuerelement im **UserControl-Test Container**aus.</span><span class="sxs-lookup"><span data-stu-id="edbcf-128">Press **F5** to build the project and run your control in the **UserControl Test Container**.</span></span>

9. <span data-ttu-id="edbcf-129">Suchen Sie die Eigenschaft **Strings** in <xref:System.Windows.Forms.PropertyGrid> der des **UserControl-Test Containers**.</span><span class="sxs-lookup"><span data-stu-id="edbcf-129">Find the **Strings** property in the <xref:System.Windows.Forms.PropertyGrid> of the **UserControl Test Container**.</span></span> <span data-ttu-id="edbcf-130">Wählen Sie die Eigenschaft **Strings** aus, und wählen Sie dann![die Auslassungs Punkte (die Schaltfläche mit den Auslassungs Punkten (.](./media/visual-studio-ellipsis-button.png)..) in der Eigenschaftenfenster von Visual Studio) aus, um den Editor für die **Zeichen**folgen Auflistung</span><span class="sxs-lookup"><span data-stu-id="edbcf-130">Select the **Strings** property, then select the ellipsis (![The Ellipsis button (...) in the Properties window of Visual Studio](./media/visual-studio-ellipsis-button.png)) button to open the **String Collection Editor**.</span></span>

10. <span data-ttu-id="edbcf-131">Geben Sie im Zeichen folgen- **Sammlungs-Editor mehrere Zeichen**folgen ein.</span><span class="sxs-lookup"><span data-stu-id="edbcf-131">Enter several strings in the **String Collection Editor**.</span></span> <span data-ttu-id="edbcf-132">Trennen Sie diese durch Drücken der **Eingabe** Taste am Ende der einzelnen Zeichen folgen.</span><span class="sxs-lookup"><span data-stu-id="edbcf-132">Separate them by pressing the **Enter** key at the end of each string.</span></span> <span data-ttu-id="edbcf-133">Klicken Sie auf **OK** , wenn die Eingabe von Zeichen folgen abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="edbcf-133">Click **OK** when you are finished entering strings.</span></span>

   > [!NOTE]
   > <span data-ttu-id="edbcf-134">Die Zeichen folgen, die Sie eingegeben <xref:System.Windows.Forms.TextBox> haben, `SerializationDemoControl`werden in der von angezeigt.</span><span class="sxs-lookup"><span data-stu-id="edbcf-134">The strings you typed appear in the <xref:System.Windows.Forms.TextBox> of the `SerializationDemoControl`.</span></span>

## <a name="serialize-a-collection-property"></a><span data-ttu-id="edbcf-135">Serialisieren einer Sammlungs Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="edbcf-135">Serialize a collection property</span></span>

<span data-ttu-id="edbcf-136">Um das Serialisierungsverhalten Ihres Steuer Elements zu testen, platzieren Sie es in einem Formular, und ändern Sie den Inhalt der Auflistung mit dem Auflistungs- **Editor**.</span><span class="sxs-lookup"><span data-stu-id="edbcf-136">To test the serialization behavior of your control, you will place it on a form and change the contents of the collection with the **Collection Editor**.</span></span> <span data-ttu-id="edbcf-137">Sie können den serialisierten Auflistungs Status anzeigen, indem Sie eine spezielle Designer-Datei betrachten, in der die **Windows Forms-Designer** Code ausgibt.</span><span class="sxs-lookup"><span data-stu-id="edbcf-137">You can see the serialized collection state by looking at a special designer file into which the **Windows Forms Designer** emits code.</span></span>

1. <span data-ttu-id="edbcf-138">Fügen Sie der Projekt Mappe ein Windows-Anwendungsprojekt hinzu.</span><span class="sxs-lookup"><span data-stu-id="edbcf-138">Add a Windows Application project to the solution.</span></span> <span data-ttu-id="edbcf-139">Benennen Sie das Projekt mit `SerializationDemoControlTest`.</span><span class="sxs-lookup"><span data-stu-id="edbcf-139">Name the project `SerializationDemoControlTest`.</span></span>

2. <span data-ttu-id="edbcf-140">Suchen Sie in der **Toolbox**die Registerkarte mit dem Namen **SerializationDemoControlLib Components**.</span><span class="sxs-lookup"><span data-stu-id="edbcf-140">In the **Toolbox**, find the tab named **SerializationDemoControlLib Components**.</span></span> <span data-ttu-id="edbcf-141">Auf dieser Registerkarte finden Sie die `SerializationDemoControl`.</span><span class="sxs-lookup"><span data-stu-id="edbcf-141">In this tab, you will find the `SerializationDemoControl`.</span></span> <span data-ttu-id="edbcf-142">Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Automatisches Auffüllen der Toolbox mit benutzerdefinierten Komponenten](walkthrough-automatically-populating-the-toolbox-with-custom-components.md).</span><span class="sxs-lookup"><span data-stu-id="edbcf-142">For more information, see [Walkthrough: Automatically Populating the Toolbox with Custom Components](walkthrough-automatically-populating-the-toolbox-with-custom-components.md).</span></span>

3. <span data-ttu-id="edbcf-143">Platzieren Sie `SerializationDemoControl` einen auf dem Formular.</span><span class="sxs-lookup"><span data-stu-id="edbcf-143">Place a `SerializationDemoControl` on your form.</span></span>

4. <span data-ttu-id="edbcf-144">Suchen Sie `Strings` die-Eigenschaft im **Eigenschaften** Fenster.</span><span class="sxs-lookup"><span data-stu-id="edbcf-144">Find the `Strings` property in the **Properties** window.</span></span> <span data-ttu-id="edbcf-145">Klicken Sie `Strings` auf die-Eigenschaft, und klicken Sie![dann auf die Auslassungs Punkte (die Schaltfläche mit den Auslassungs Punkten (](./media/visual-studio-ellipsis-button.png)...) in der Eigenschaftenfenster von Visual **Studio.**</span><span class="sxs-lookup"><span data-stu-id="edbcf-145">Click the `Strings` property, then click the ellipsis (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) button to open the **String Collection Editor**.</span></span>

5. <span data-ttu-id="edbcf-146">Geben Sie im Zeichen folgen- **Sammlungs-Editor mehrere Zeichen**folgen ein.</span><span class="sxs-lookup"><span data-stu-id="edbcf-146">Type several strings in the **String Collection Editor**.</span></span> <span data-ttu-id="edbcf-147">Trennen Sie diese durch Drücken der **Eingabe** Taste am Ende jeder Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="edbcf-147">Separate them by pressing **Enter** at the end of each string.</span></span> <span data-ttu-id="edbcf-148">Klicken Sie auf **OK** , wenn die Eingabe von Zeichen folgen abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="edbcf-148">Click **OK** when you are finished entering strings.</span></span>

    > [!NOTE]
    > <span data-ttu-id="edbcf-149">Die Zeichen folgen, die Sie eingegeben <xref:System.Windows.Forms.TextBox> haben, `SerializationDemoControl`werden in der von angezeigt.</span><span class="sxs-lookup"><span data-stu-id="edbcf-149">The strings you typed appear in the <xref:System.Windows.Forms.TextBox> of the `SerializationDemoControl`.</span></span>

6. <span data-ttu-id="edbcf-150">Klicken Sie im **Projektmappen-Explorer** auf die Schaltfläche **Alle Dateien anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="edbcf-150">In **Solution Explorer**, click the **Show All Files** button.</span></span>

7. <span data-ttu-id="edbcf-151">Öffnen Sie den Knoten **Form1** .</span><span class="sxs-lookup"><span data-stu-id="edbcf-151">Open the **Form1** node.</span></span> <span data-ttu-id="edbcf-152">Darunter befindet sich eine Datei mit dem Namen **Form1.Designer.cs** oder **Form1. Designer. vb**.</span><span class="sxs-lookup"><span data-stu-id="edbcf-152">Beneath it is a file called **Form1.Designer.cs** or **Form1.Designer.vb**.</span></span> <span data-ttu-id="edbcf-153">Dies ist die Datei, in die der **Windows Forms-Designer** Code ausgibt, der den Entwurfszeit Zustand des Formulars und seiner untergeordneten Steuerelemente darstellt.</span><span class="sxs-lookup"><span data-stu-id="edbcf-153">This is the file into which the **Windows Forms Designer** emits code representing the design-time state of your form and its child controls.</span></span> <span data-ttu-id="edbcf-154">Öffnen Sie diese Datei im **Code-Editor**.</span><span class="sxs-lookup"><span data-stu-id="edbcf-154">Open this file in the **Code Editor**.</span></span>

8. <span data-ttu-id="edbcf-155">Öffnen Sie die Region namens **Windows Form-Designer generierter Code** , und suchen Sie den Abschnitt mit der Bezeichnung **serializationDemoControl1**.</span><span class="sxs-lookup"><span data-stu-id="edbcf-155">Open the region called **Windows Form Designer generated code** and find the section labeled **serializationDemoControl1**.</span></span> <span data-ttu-id="edbcf-156">Unterhalb dieser Bezeichnung befindet sich der Code, der den serialisierten Zustand des Steuer Elements darstellt.</span><span class="sxs-lookup"><span data-stu-id="edbcf-156">Beneath this label is the code representing the serialized state of your control.</span></span> <span data-ttu-id="edbcf-157">Die Zeichen folgen, die Sie in Schritt 5 eingegeben haben, werden `Strings` in einer Zuweisung zur-Eigenschaft angezeigt.</span><span class="sxs-lookup"><span data-stu-id="edbcf-157">The strings you typed in step 5 appear in an assignment to the `Strings` property.</span></span> <span data-ttu-id="edbcf-158">Die folgenden Codebeispiele in C# und Visual Basic zeigen Code ähnlich dem, was Sie sehen werden, wenn Sie die Zeichen folgen "Red", "Orange" und "Yellow" eingegeben haben.</span><span class="sxs-lookup"><span data-stu-id="edbcf-158">The following code examples in C# and Visual Basic, show code similar to what you will see if you typed the strings "red", "orange", and "yellow".</span></span>

    ```csharp
    this.serializationDemoControl1.Strings = new string[] {
            "red",
            "orange",
            "yellow"};
    ```

    ```vb
    Me.serializationDemoControl1.Strings = New String() {"red", "orange", "yellow"}
    ```

9. <span data-ttu-id="edbcf-159">Ändern Sie `Strings` <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute> im<xref:System.ComponentModel.DesignerSerializationVisibility.Hidden>Code- **Editor**den Wert von für die-Eigenschaft in.</span><span class="sxs-lookup"><span data-stu-id="edbcf-159">In the **Code Editor**, change the value of the <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute> on the `Strings` property to <xref:System.ComponentModel.DesignerSerializationVisibility.Hidden>.</span></span>

    ```csharp
    [DesignerSerializationVisibility(DesignerSerializationVisibility.Hidden)]
    ```

    ```vb
    <DesignerSerializationVisibility(DesignerSerializationVisibility.Hidden)> _
    ```

10. <span data-ttu-id="edbcf-160">Erstellen Sie die Lösung neu, und wiederholen Sie die Schritte 3 und 4</span><span class="sxs-lookup"><span data-stu-id="edbcf-160">Rebuild the solution and repeat steps 3 and 4.</span></span>

> [!NOTE]
> <span data-ttu-id="edbcf-161">In diesem Fall gibt der **Windows Forms-Designer** keine Zuweisung zur `Strings` -Eigenschaft aus.</span><span class="sxs-lookup"><span data-stu-id="edbcf-161">In this case, the **Windows Forms Designer** emits no assignment to the `Strings` property.</span></span>

## <a name="next-steps"></a><span data-ttu-id="edbcf-162">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="edbcf-162">Next steps</span></span>

<span data-ttu-id="edbcf-163">Wenn Sie wissen, wie eine Auflistung von Standardtypen serialisiert werden soll, sollten Sie in Erwägung gezogen werden, die benutzerdefinierten Steuerelemente tiefer in die Entwurfszeit Umgebung zu integrieren.</span><span class="sxs-lookup"><span data-stu-id="edbcf-163">Once you know how to serialize a collection of standard types, consider integrating your custom controls more deeply into the design-time environment.</span></span> <span data-ttu-id="edbcf-164">In den folgenden Themen wird beschrieben, wie Sie die Entwurfszeit Integration Ihrer benutzerdefinierten Steuerelemente verbessern:</span><span class="sxs-lookup"><span data-stu-id="edbcf-164">The following topics describe how to enhance the design-time integration of your custom controls:</span></span>

- <span data-ttu-id="edbcf-165">[Entwurfszeit Architektur](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/c5z9s1h4(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="edbcf-165">[Design-Time Architecture](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/c5z9s1h4(v=vs.120))</span></span>

- [<span data-ttu-id="edbcf-166">Attribute in Windows Forms-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="edbcf-166">Attributes in Windows Forms Controls</span></span>](attributes-in-windows-forms-controls.md)

- <span data-ttu-id="edbcf-167">[Übersicht über die Designer-Serialisierung](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171834(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="edbcf-167">[Designer Serialization Overview](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171834(v=vs.120))</span></span>

- [<span data-ttu-id="edbcf-168">Exemplarische Vorgehensweise: Erstellen eines Windows Forms-Steuer Elements, das Visual Studio-Entwurfszeit Funktionen nutzt</span><span class="sxs-lookup"><span data-stu-id="edbcf-168">Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features</span></span>](creating-a-wf-control-design-time-features.md)

## <a name="see-also"></a><span data-ttu-id="edbcf-169">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="edbcf-169">See also</span></span>

- <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute>
- [<span data-ttu-id="edbcf-170">Exemplarische Vorgehensweise: Automatisches Auffüllen der Toolbox mit benutzerdefinierten Komponenten</span><span class="sxs-lookup"><span data-stu-id="edbcf-170">Walkthrough: Automatically Populating the Toolbox with Custom Components</span></span>](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)
