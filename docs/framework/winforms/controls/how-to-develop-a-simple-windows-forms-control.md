---
title: Entwickeln Sie ein einfaches Steuerelement
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms]
- custom controls [Windows Forms], creating simple controls using code
- Control class [Windows Forms], Windows Forms
ms.assetid: 86cbe435-45b7-4cb4-9b5a-47418369758d
ms.openlocfilehash: 5383cee5358dbd260fc6c023d3db607da6b10ea4
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742251"
---
# <a name="how-to-develop-a-simple-windows-forms-control"></a><span data-ttu-id="2ac66-102">Gewusst wie: Entwickeln eines einfachen Windows Forms-Steuerelements</span><span class="sxs-lookup"><span data-stu-id="2ac66-102">How to: Develop a Simple Windows Forms Control</span></span>

<span data-ttu-id="2ac66-103">Dieser Abschnitt führt Sie durch die wichtigsten Schritte zum Erstellen von benutzerdefinierten Windows Forms-Steuerelementen.</span><span class="sxs-lookup"><span data-stu-id="2ac66-103">This section walks you through the key steps for authoring a custom Windows Forms control.</span></span> <span data-ttu-id="2ac66-104">Das in dieser exemplarischen Vorgehensweise entwickelte einfache Steuerelement ermöglicht die Änderung der Ausrichtung der <xref:System.Windows.Forms.Control.Text%2A>-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="2ac66-104">The simple control developed in this walkthrough allows the alignment of its <xref:System.Windows.Forms.Control.Text%2A> property to be changed.</span></span> <span data-ttu-id="2ac66-105">Es löst keine Ereignisse aus oder behandelt sie.</span><span class="sxs-lookup"><span data-stu-id="2ac66-105">It does not raise or handle events.</span></span>

### <a name="to-create-a-simple-custom-control"></a><span data-ttu-id="2ac66-106">So erstellen Sie ein einfaches benutzerdefiniertes Steuerelement</span><span class="sxs-lookup"><span data-stu-id="2ac66-106">To create a simple custom control</span></span>

1. <span data-ttu-id="2ac66-107">Definieren Sie eine Klasse, die sich von <xref:System.Windows.Forms.Control?displayProperty=nameWithType> ableitet.</span><span class="sxs-lookup"><span data-stu-id="2ac66-107">Define a class that derives from <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.</span></span>

    ```vb
    Public Class FirstControl
       Inherits Control

    End Class
    ```

    ```csharp
    public class FirstControl:Control {}
    ```

2. <span data-ttu-id="2ac66-108">Definieren Sie Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="2ac66-108">Define properties.</span></span> <span data-ttu-id="2ac66-109">(Sie müssen keine Eigenschaften definieren, da ein Steuerelement viele Eigenschaften von der <xref:System.Windows.Forms.Control> Klasse erbt, aber die meisten benutzerdefinierten Steuerelemente definieren in der Regel zusätzliche Eigenschaften.) Das folgende Code Fragment definiert eine Eigenschaft mit dem Namen `TextAlignment`, die `FirstControl` verwendet, um die Anzeige der <xref:System.Windows.Forms.Control.Text%2A>-Eigenschaft zu formatieren, die von <xref:System.Windows.Forms.Control>geerbt wird.</span><span class="sxs-lookup"><span data-stu-id="2ac66-109">(You are not required to define properties, because a control inherits many properties from the <xref:System.Windows.Forms.Control> class, but most custom controls generally do define additional properties.) The following code fragment defines a property named `TextAlignment` that `FirstControl` uses to format the display of the <xref:System.Windows.Forms.Control.Text%2A> property inherited from <xref:System.Windows.Forms.Control>.</span></span> <span data-ttu-id="2ac66-110">Weitere Informationen zum Definieren von Eigenschaften finden Sie in der [Übersicht über Eigenschaften](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/65zdfbdt(v%3dvs.120)).</span><span class="sxs-lookup"><span data-stu-id="2ac66-110">For more information about defining properties, see [Properties Overview](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/65zdfbdt(v%3dvs.120)).</span></span>

     [!code-csharp[System.Windows.Forms.FirstControl#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/CS/FirstControl.cs#3)]
     [!code-vb[System.Windows.Forms.FirstControl#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/VB/FirstControl.vb#3)]

     <span data-ttu-id="2ac66-111">Wenn Sie eine Eigenschaft festlegen, die die visuelle Darstellung des Steuer Elements ändert, müssen Sie die <xref:System.Windows.Forms.Control.Invalidate%2A>-Methode aufrufen, um das Steuerelement neu zu zeichnen.</span><span class="sxs-lookup"><span data-stu-id="2ac66-111">When you set a property that changes the visual display of the control, you must invoke the <xref:System.Windows.Forms.Control.Invalidate%2A> method to redraw the control.</span></span> <span data-ttu-id="2ac66-112"><xref:System.Windows.Forms.Control.Invalidate%2A> ist in der Basisklasse <xref:System.Windows.Forms.Control>definiert.</span><span class="sxs-lookup"><span data-stu-id="2ac66-112"><xref:System.Windows.Forms.Control.Invalidate%2A> is defined in the base class <xref:System.Windows.Forms.Control>.</span></span>

3. <span data-ttu-id="2ac66-113">Überschreiben Sie die von <xref:System.Windows.Forms.Control> geerbte geschützte <xref:System.Windows.Forms.Control.OnPaint%2A> Methode, um Renderinglogik für das Steuerelement bereitzustellen</span><span class="sxs-lookup"><span data-stu-id="2ac66-113">Override the protected <xref:System.Windows.Forms.Control.OnPaint%2A> method inherited from <xref:System.Windows.Forms.Control> to provide rendering logic to your control.</span></span> <span data-ttu-id="2ac66-114">Wenn Sie <xref:System.Windows.Forms.Control.OnPaint%2A>nicht überschreiben, kann das Steuerelement nicht selbst gezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="2ac66-114">If you do not override <xref:System.Windows.Forms.Control.OnPaint%2A>, your control will not be able to draw itself.</span></span> <span data-ttu-id="2ac66-115">Im folgenden Code Fragment zeigt die <xref:System.Windows.Forms.Control.OnPaint%2A>-Methode die <xref:System.Windows.Forms.Control.Text%2A>-Eigenschaft, die von <xref:System.Windows.Forms.Control> geerbt wurde, mit der Ausrichtung an, die vom `alignmentValue` Feld angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="2ac66-115">In the following code fragment, the <xref:System.Windows.Forms.Control.OnPaint%2A> method displays the <xref:System.Windows.Forms.Control.Text%2A> property inherited from <xref:System.Windows.Forms.Control> with the alignment specified by the `alignmentValue` field.</span></span>

     [!code-csharp[System.Windows.Forms.FirstControl#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/CS/FirstControl.cs#4)]
     [!code-vb[System.Windows.Forms.FirstControl#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/VB/FirstControl.vb#4)]

4. <span data-ttu-id="2ac66-116">Stellen Sie Attribute für das Steuerelement bereit.</span><span class="sxs-lookup"><span data-stu-id="2ac66-116">Provide attributes for your control.</span></span> <span data-ttu-id="2ac66-117">Attribute ermöglichen es einem visuellen Designer, Ihr Steuerelement und dessen Eigenschaften und Ereignisse entsprechend zur Entwurfszeit anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="2ac66-117">Attributes enable a visual designer to display your control and its properties and events appropriately at design time.</span></span> <span data-ttu-id="2ac66-118">Das folgende Codefragment wendet die Attribute auf die Eigenschaft `TextAlignment` an.</span><span class="sxs-lookup"><span data-stu-id="2ac66-118">The following code fragment applies attributes to the `TextAlignment` property.</span></span> <span data-ttu-id="2ac66-119">In einem Designer, wie z. b. Visual Studio, bewirkt das <xref:System.ComponentModel.CategoryAttribute.Category%2A>-Attribut (im Code Fragment gezeigt), dass die Eigenschaft unter einer logischen Kategorie angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="2ac66-119">In a designer such as Visual Studio, the <xref:System.ComponentModel.CategoryAttribute.Category%2A> attribute (shown in the code fragment) causes the property to be displayed under a logical category.</span></span> <span data-ttu-id="2ac66-120">Das <xref:System.ComponentModel.DescriptionAttribute.Description%2A>-Attribut bewirkt, dass eine beschreibende Zeichenfolge im unteren Bereich des **Eigenschaften** Fensters angezeigt wird, wenn die `TextAlignment`-Eigenschaft ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="2ac66-120">The <xref:System.ComponentModel.DescriptionAttribute.Description%2A> attribute causes a descriptive string to be displayed at the bottom of the **Properties** window when the `TextAlignment` property is selected.</span></span> <span data-ttu-id="2ac66-121">Weitere Informationen zu Attributen finden Sie unter [Entwurfszeitattribute für Komponenten](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/tk67c2t8(v=vs.120)).</span><span class="sxs-lookup"><span data-stu-id="2ac66-121">For more information about attributes, see [Design-Time Attributes for Components](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/tk67c2t8(v=vs.120)).</span></span>

     [!code-csharp[System.Windows.Forms.FirstControl#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/CS/FirstControl.cs#5)]
     [!code-vb[System.Windows.Forms.FirstControl#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/VB/FirstControl.vb#5)]

5. <span data-ttu-id="2ac66-122">(optional) Stellen Sie Ressourcen für Ihr Steuerelement zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="2ac66-122">(optional) Provide resources for your control.</span></span> <span data-ttu-id="2ac66-123">Sie können eine Ressource, z.B. eine Bitmap für das Steuerelement mit einer Compileroption bereitstellen (`/res` für C#), um Ressourcen mit dem Steuerelement zu verpacken.</span><span class="sxs-lookup"><span data-stu-id="2ac66-123">You can provide a resource, such as a bitmap, for your control by using a compiler option (`/res` for C#) to package resources with your control.</span></span> <span data-ttu-id="2ac66-124">Zur Laufzeit kann die Ressource mithilfe der Methoden der <xref:System.Resources.ResourceManager>-Klasse abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="2ac66-124">At run time, the resource can be retrieved using the methods of the <xref:System.Resources.ResourceManager> class.</span></span> <span data-ttu-id="2ac66-125">Weitere Informationen zum Erstellen und Verwenden von Ressourcen finden Sie unter [Ressourcen in Desktop-Apps](../../resources/index.md).</span><span class="sxs-lookup"><span data-stu-id="2ac66-125">For more information about creating and using resources, see the [Resources in Desktop Apps](../../resources/index.md).</span></span>

6. <span data-ttu-id="2ac66-126">Kompilieren Sie das Steuerelement, und stellen Sie es bereit.</span><span class="sxs-lookup"><span data-stu-id="2ac66-126">Compile and deploy your control.</span></span> <span data-ttu-id="2ac66-127">Führen Sie die folgenden Schritte aus, um `FirstControl,` zu kompilieren und bereitzustellen:</span><span class="sxs-lookup"><span data-stu-id="2ac66-127">To compile and deploy `FirstControl,` execute the following steps:</span></span>

    1. <span data-ttu-id="2ac66-128">Speichern Sie den Code im folgenden Beispiel als Quelldatei (z.B. als „FirstControl.cs“ oder „FirstControl.vb“).</span><span class="sxs-lookup"><span data-stu-id="2ac66-128">Save the code in the following sample to a source file (such as FirstControl.cs or FirstControl.vb).</span></span>

    2. <span data-ttu-id="2ac66-129">Kompilieren Sie den Quellcode in eine Assembly, und speichern Sie sie im Verzeichnis der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="2ac66-129">Compile the source code into an assembly and save it in your application's directory.</span></span> <span data-ttu-id="2ac66-130">Führen Sie hierfür den folgenden Befehl in dem Verzeichnis aus, das die Quelldatei enthält.</span><span class="sxs-lookup"><span data-stu-id="2ac66-130">To accomplish this, execute the following command from the directory that contains the source file.</span></span>

        ```console
        vbc -t:library -out:[path to your application's directory]/CustomWinControls.dll -r:System.dll -r:System.Windows.Forms.dll -r:System.Drawing.dll FirstControl.vb
        ```

        ```console
        csc -t:library -out:[path to your application's directory]/CustomWinControls.dll -r:System.dll -r:System.Windows.Forms.dll -r:System.Drawing.dll FirstControl.cs
        ```

         <span data-ttu-id="2ac66-131">Die Compileroption `/t:library` benachrichtigt den Compiler, dass es sich bei der erstellten Assembly um eine Bibliothek handelt (nicht um eine ausführbare Assembly).</span><span class="sxs-lookup"><span data-stu-id="2ac66-131">The `/t:library` compiler option tells the compiler that the assembly you are creating is a library (and not an executable).</span></span> <span data-ttu-id="2ac66-132">Die Option `/out` gibt den Pfad und den Namen der Assembly an.</span><span class="sxs-lookup"><span data-stu-id="2ac66-132">The `/out` option specifies the path and name of the assembly.</span></span> <span data-ttu-id="2ac66-133">Die Option `/r` gibt den Namen der Assembly an, auf die durch Ihren Code verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="2ac66-133">The`/r` option provides the name of the assemblies that are referenced by your code.</span></span> <span data-ttu-id="2ac66-134">In diesem Beispiel erstellen Sie eine private Assembly, die ausschließlich von Ihren Anwendungen verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="2ac66-134">In this example, you create a private assembly that only your applications can use.</span></span> <span data-ttu-id="2ac66-135">Daher müssen Sie sie im Verzeichnis der Anwendung speichern.</span><span class="sxs-lookup"><span data-stu-id="2ac66-135">Hence, you have to save it in your application's directory.</span></span> <span data-ttu-id="2ac66-136">Weitere Informationen über das Packen und Bereitstellen eines Steuerelements für die Verteilung finden Sie unter [Bereitstellung](../../deployment/index.md).</span><span class="sxs-lookup"><span data-stu-id="2ac66-136">For more information about packaging and deploying a control for distribution, see [Deployment](../../deployment/index.md).</span></span>

<span data-ttu-id="2ac66-137">Das folgende Beispiel zeigt den Code für `FirstControl`.</span><span class="sxs-lookup"><span data-stu-id="2ac66-137">The following sample shows the code for `FirstControl`.</span></span> <span data-ttu-id="2ac66-138">Das Steuerelement ist im Namespace `CustomWinControls` enthalten.</span><span class="sxs-lookup"><span data-stu-id="2ac66-138">The control is enclosed in the namespace `CustomWinControls`.</span></span> <span data-ttu-id="2ac66-139">Ein Namespace bietet eine logische Gruppierung von verwandten Typen.</span><span class="sxs-lookup"><span data-stu-id="2ac66-139">A namespace provides a logical grouping of related types.</span></span> <span data-ttu-id="2ac66-140">Sie können das Steuerelement in einem neuen oder vorhandenen Namespace erstellen.</span><span class="sxs-lookup"><span data-stu-id="2ac66-140">You can create your control in a new or existing namespace.</span></span> <span data-ttu-id="2ac66-141">In C# ermöglicht die Deklaration `using` (`Imports` in Visual Basic), dass auf Typen von einem Namespace zugegriffen wird, ohne dass der vollqualifizierte Name des Typs verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="2ac66-141">In C#, the `using` declaration (in Visual Basic, `Imports`) allows types to be accessed from a namespace without using the fully qualified name of the type.</span></span> <span data-ttu-id="2ac66-142">Im folgenden Beispiel ermöglicht die `using` Deklaration Code den Zugriff auf die-Klasse <xref:System.Windows.Forms.Control> von <xref:System.Windows.Forms?displayProperty=nameWithType> <xref:System.Windows.Forms.Control>, anstatt den voll qualifizierten Namen <xref:System.Windows.Forms.Control?displayProperty=nameWithType>zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="2ac66-142">In the following example, the `using` declaration allows code to access the class <xref:System.Windows.Forms.Control> from <xref:System.Windows.Forms?displayProperty=nameWithType> as simply <xref:System.Windows.Forms.Control> instead of having to use the fully qualified name <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.</span></span>

[!code-csharp[System.Windows.Forms.FirstControl#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/CS/FirstControl.cs#1)]
[!code-vb[System.Windows.Forms.FirstControl#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/VB/FirstControl.vb#1)]

## <a name="using-the-custom-control-on-a-form"></a><span data-ttu-id="2ac66-143">Verwenden des benutzerdefinierten Steuerelements in einem Formular</span><span class="sxs-lookup"><span data-stu-id="2ac66-143">Using the Custom Control on a Form</span></span>

<span data-ttu-id="2ac66-144">Im folgenden Beispiel wird ein einfaches Formular dargestellt, dass `FirstControl` verwendet.</span><span class="sxs-lookup"><span data-stu-id="2ac66-144">The following example shows a simple form that uses `FirstControl`.</span></span> <span data-ttu-id="2ac66-145">Es erstellt drei Instanzen von `FirstControl`, jede mit einem anderen Wert für die Eigenschaft `TextAlignment`.</span><span class="sxs-lookup"><span data-stu-id="2ac66-145">It creates three instances of `FirstControl`, each with a different value for the `TextAlignment` property.</span></span>

#### <a name="to-compile-and-run-this-sample"></a><span data-ttu-id="2ac66-146">So kompilieren Sie dieses Beispiel und führen es aus</span><span class="sxs-lookup"><span data-stu-id="2ac66-146">To compile and run this sample</span></span>

1. <span data-ttu-id="2ac66-147">Speichern Sie den Code im folgenden Beispiel als Quelldatei („SimpleForm.cs“ oder „SimpleForms.vb“).</span><span class="sxs-lookup"><span data-stu-id="2ac66-147">Save the code in the following example to a source file (SimpleForm.cs or SimpleForms.vb).</span></span>

2. <span data-ttu-id="2ac66-148">Kompilieren Sie den Quellcode in eine ausführbare Assembly, indem Sie den folgenden Befehl im Verzeichnis ausführen, das die Quelldatei enthält.</span><span class="sxs-lookup"><span data-stu-id="2ac66-148">Compile the source code into an executable assembly by executing the following command from the directory that contains the source file.</span></span>

    ```console
    vbc -r:CustomWinControls.dll -r:System.dll -r:System.Windows.Forms.dll -r:System.Drawing.dll SimpleForm.vb
    ```

    ```console
    csc -r:CustomWinControls.dll -r:System.dll -r:System.Windows.Forms.dll -r:System.Drawing.dll SimpleForm.cs
    ```

     <span data-ttu-id="2ac66-149">CustomWinControls. dll ist die Assembly, die die Klasse `FirstControl`enthält.</span><span class="sxs-lookup"><span data-stu-id="2ac66-149">CustomWinControls.dll is the assembly that contains the class `FirstControl`.</span></span> <span data-ttu-id="2ac66-150">Diese Assembly muss sich im gleichen Verzeichnis befinden wie die Quelldatei für das Formular, das auf sie zugreift („SimpleForm.cs“ oder „SimpleForms.vb“).</span><span class="sxs-lookup"><span data-stu-id="2ac66-150">This assembly must be in the same directory as the source file for the form that accesses it (SimpleForm.cs or SimpleForms.vb).</span></span>

3. <span data-ttu-id="2ac66-151">Führen Sie „SimpleForm.exe“ mit dem folgenden Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="2ac66-151">Execute SimpleForm.exe using the following command.</span></span>

    ```console
    SimpleForm
    ```

[!code-csharp[System.Windows.Forms.FirstControl#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/CS/SimpleForm.cs#10)]
[!code-vb[System.Windows.Forms.FirstControl#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/VB/SimpleForm.vb#10)]

## <a name="see-also"></a><span data-ttu-id="2ac66-152">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2ac66-152">See also</span></span>

- [<span data-ttu-id="2ac66-153">Eigenschaften von Windows Forms-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="2ac66-153">Properties in Windows Forms Controls</span></span>](properties-in-windows-forms-controls.md)
- [<span data-ttu-id="2ac66-154">Ereignisse in Windows Forms-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="2ac66-154">Events in Windows Forms Controls</span></span>](events-in-windows-forms-controls.md)
