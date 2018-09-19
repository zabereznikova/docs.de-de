---
title: Erfassen von Freihandeingaben in WPF-apps
ms.date: 08/15/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ink [WPF], collecting
- InkCanvas element [WPF]
- properties [WPF], DrawingAttributes
- collecting digital ink [WPF]
- digital ink [WPF], collecting
- properties [WPF], DefaultDrawingAttributes
- DefaultDrawingAttributes property [WPF]
ms.assetid: 66a3129d-9577-43eb-acbd-56c147282016
ms.openlocfilehash: 25f9c0141a97d8e52e0883b14fd3e1f4574a05ea
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46004278"
---
# <a name="collect-ink"></a><span data-ttu-id="f2c85-102">Erfassen von Freihandeingaben</span><span class="sxs-lookup"><span data-stu-id="f2c85-102">Collect Ink</span></span>

<span data-ttu-id="f2c85-103">Als einen ihrer zentralen Funktionsbestandteile erfasst die [Windows Presentation Foundation](../../../../docs/framework/wpf/index.md)-Plattform Freihandeingaben.</span><span class="sxs-lookup"><span data-stu-id="f2c85-103">The [Windows Presentation Foundation](../../../../docs/framework/wpf/index.md) platform collects digital ink as a core part of its functionality.</span></span> <span data-ttu-id="f2c85-104">Dieses Thema beschreibt Methoden zum Erfassen von Freihandeingaben in Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="f2c85-104">This topic discusses methods for collection of ink in Windows Presentation Foundation (WPF).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f2c85-105">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="f2c85-105">Prerequisites</span></span>

<span data-ttu-id="f2c85-106">Um die folgenden Beispiele verwenden zu können, müssen Sie zunächst Visual Studio installieren und die [!INCLUDE[TLA2#tla_winfxsdk](../../../../includes/tla2sharptla-winfxsdk-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f2c85-106">To use the following examples, you must first install Visual Studio and the [!INCLUDE[TLA2#tla_winfxsdk](../../../../includes/tla2sharptla-winfxsdk-md.md)].</span></span> <span data-ttu-id="f2c85-107">Sie sollten auch Gewusst wie: Schreiben von Anwendungen für WPF kennen.</span><span class="sxs-lookup"><span data-stu-id="f2c85-107">You should also understand how to write applications for the WPF.</span></span> <span data-ttu-id="f2c85-108">Weitere Informationen zu den ersten Schritten mit WPF finden Sie unter [Exemplarische Vorgehensweise: Meine erste WPF-Desktopanwendung](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md).</span><span class="sxs-lookup"><span data-stu-id="f2c85-108">For more information about getting started with WPF, see [Walkthrough: My first WPF desktop application](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md).</span></span>

## <a name="use-the-inkcanvas-element"></a><span data-ttu-id="f2c85-109">Verwenden des InkCanvas-Elements</span><span class="sxs-lookup"><span data-stu-id="f2c85-109">Use the InkCanvas Element</span></span>

<span data-ttu-id="f2c85-110">Die <xref:System.Windows.Controls.InkCanvas?displayProperty=fullName> -Element stellt die einfachste Möglichkeit zum Erfassen von Freihandeingaben in WPF bereit.</span><span class="sxs-lookup"><span data-stu-id="f2c85-110">The <xref:System.Windows.Controls.InkCanvas?displayProperty=fullName> element provides the easiest way to collect ink in WPF.</span></span> <span data-ttu-id="f2c85-111">Verwenden einer <xref:System.Windows.Controls.InkCanvas> Element zu empfangen und Freihandeingaben anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="f2c85-111">Use an <xref:System.Windows.Controls.InkCanvas> element to receive and display ink input.</span></span> <span data-ttu-id="f2c85-112">Freihandeingaben erfolgen im Allgemeinen mithilfe eines Tablettstifts, der über ein Digitalisierungsgerät Freihandstriche erzeugt.</span><span class="sxs-lookup"><span data-stu-id="f2c85-112">You commonly input ink through the use of a stylus, which interacts with a digitizer to produce ink strokes.</span></span> <span data-ttu-id="f2c85-113">Anstelle eines Tablettstifts kann auch eine Maus verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f2c85-113">In addition, a mouse can be used in place of a stylus.</span></span> <span data-ttu-id="f2c85-114">Die erzeugten Striche werden als dargestellt <xref:System.Windows.Ink.Stroke> Objekte und, können sowohl programmgesteuert als auch durch Benutzereingaben geändert werden.</span><span class="sxs-lookup"><span data-stu-id="f2c85-114">The created strokes are represented as <xref:System.Windows.Ink.Stroke> objects, and they can be manipulated both programmatically and by user input.</span></span> <span data-ttu-id="f2c85-115">Die <xref:System.Windows.Controls.InkCanvas> ermöglicht Benutzern das auswählen, ändern oder Löschen eines vorhandenen <xref:System.Windows.Ink.Stroke>.</span><span class="sxs-lookup"><span data-stu-id="f2c85-115">The <xref:System.Windows.Controls.InkCanvas> enables users to select, modify, or delete an existing <xref:System.Windows.Ink.Stroke>.</span></span>

<span data-ttu-id="f2c85-116">Mit XAML, Sie können festlegen, Freihandeingaben so einfach wie das Hinzufügen einer **InkCanvas** -Elements zur Struktur.</span><span class="sxs-lookup"><span data-stu-id="f2c85-116">By using XAML, you can set up ink collection as easily as adding an **InkCanvas** element to your tree.</span></span> <span data-ttu-id="f2c85-117">Im folgenden Beispiel wird ein <xref:System.Windows.Controls.InkCanvas> auf ein Standard-WPF-Projekt in Visual Studio erstellt wurden:</span><span class="sxs-lookup"><span data-stu-id="f2c85-117">The following example adds an <xref:System.Windows.Controls.InkCanvas> to a default WPF project created in Visual Studio:</span></span>

[!code-xaml[DigitalInkTopics#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#6)]

<span data-ttu-id="f2c85-118">Die **InkCanvas** Element kann auch untergeordnete Elemente enthalten, wodurch Anmerkungsfunktionen von Freihandeingaben auf nahezu jede Art von XAML-Element hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="f2c85-118">The **InkCanvas** element can also contain child elements, making it possible to add ink annotation capabilities to almost any type of XAML element.</span></span> <span data-ttu-id="f2c85-119">Zum Beispiel um ein Textelement Freihandfunktionen hinzufügen, indem Sie es einfach ein untergeordnetes Element des ein <xref:System.Windows.Controls.InkCanvas>:</span><span class="sxs-lookup"><span data-stu-id="f2c85-119">For example, to add inking capabilities to a text element, simply make it a child of an <xref:System.Windows.Controls.InkCanvas>:</span></span>

[!code-xaml[DigitalInkTopics#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#5)]

<span data-ttu-id="f2c85-120">Hinzufügen von Unterstützung zum Markieren eines Bilds per Freihandeingabe ist ebenso einfach:</span><span class="sxs-lookup"><span data-stu-id="f2c85-120">Adding support for marking up an image with ink is just as easy:</span></span>

[!code-xaml[DigitalInkTopics#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#7)]

### <a name="inkcollection-modes"></a><span data-ttu-id="f2c85-121">InkCollection-Modi</span><span class="sxs-lookup"><span data-stu-id="f2c85-121">InkCollection Modes</span></span>

<span data-ttu-id="f2c85-122">Die <xref:System.Windows.Controls.InkCanvas> bietet Unterstützung für verschiedene Modi durch Eingabe der <xref:System.Windows.Controls.InkCanvas.EditingMode%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="f2c85-122">The <xref:System.Windows.Controls.InkCanvas> provides support for various input modes through its <xref:System.Windows.Controls.InkCanvas.EditingMode%2A> property.</span></span>

### <a name="manipulate-ink"></a><span data-ttu-id="f2c85-123">Bearbeitung von Freihandeingaben</span><span class="sxs-lookup"><span data-stu-id="f2c85-123">Manipulate Ink</span></span>

<span data-ttu-id="f2c85-124">Die <xref:System.Windows.Controls.InkCanvas> bietet Unterstützung für viele Freihandbearbeitungsvorgänge.</span><span class="sxs-lookup"><span data-stu-id="f2c85-124">The <xref:System.Windows.Controls.InkCanvas> provides support for many ink editing operations.</span></span> <span data-ttu-id="f2c85-125">Z. B. <xref:System.Windows.Controls.InkCanvas> unterstützt das Back-von-Stift löschen und kein zusätzlicher Code ist erforderlich, um die Funktionalität auf das Element hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="f2c85-125">For example, <xref:System.Windows.Controls.InkCanvas> supports back-of-pen erase, and no additional code is needed to add the functionality to the element.</span></span>

#### <a name="selection"></a><span data-ttu-id="f2c85-126">Auswahl</span><span class="sxs-lookup"><span data-stu-id="f2c85-126">Selection</span></span>

<span data-ttu-id="f2c85-127">Auswahlmodus ist so einfach wie das Festlegen der <xref:System.Windows.Controls.InkCanvasEditingMode> Eigenschaft **wählen**.</span><span class="sxs-lookup"><span data-stu-id="f2c85-127">Setting selection mode is as simple as setting the <xref:System.Windows.Controls.InkCanvasEditingMode> property to **Select**.</span></span>

<span data-ttu-id="f2c85-128">Im folgenden Code wird den Bearbeitungsmodus basierend auf den Wert des einem <xref:System.Windows.Forms.CheckBox>:</span><span class="sxs-lookup"><span data-stu-id="f2c85-128">The following code sets the editing mode based on the value of a <xref:System.Windows.Forms.CheckBox>:</span></span>

[!code-csharp[DigitalInkTopics#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#8)]
[!code-vb[DigitalInkTopics#8](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#8)]

#### <a name="drawingattributes"></a><span data-ttu-id="f2c85-129">DrawingAttributes</span><span class="sxs-lookup"><span data-stu-id="f2c85-129">DrawingAttributes</span></span>

<span data-ttu-id="f2c85-130">Verwenden der <xref:System.Windows.Ink.Stroke.DrawingAttributes%2A> Eigenschaft, um die Darstellung von Freihandstrichen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="f2c85-130">Use the <xref:System.Windows.Ink.Stroke.DrawingAttributes%2A> property to change the appearance of ink strokes.</span></span> <span data-ttu-id="f2c85-131">Z. B. die <xref:System.Windows.Ink.DrawingAttributes.Color%2A> Mitglied <xref:System.Windows.Ink.DrawingAttributes> legt die Farbe des gerenderten <xref:System.Windows.Ink.Stroke>.</span><span class="sxs-lookup"><span data-stu-id="f2c85-131">For instance, the <xref:System.Windows.Ink.DrawingAttributes.Color%2A> member of <xref:System.Windows.Ink.DrawingAttributes> sets the color of the rendered <xref:System.Windows.Ink.Stroke>.</span></span>

<span data-ttu-id="f2c85-132">Im folgende Beispiel ändert die Farbe der ausgewählten Striche in Rot angezeigt:</span><span class="sxs-lookup"><span data-stu-id="f2c85-132">The following example changes the color of the selected strokes to red:</span></span>

[!code-csharp[DigitalInkTopics#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#9)]
[!code-vb[DigitalInkTopics#9](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#9)]

### <a name="defaultdrawingattributes"></a><span data-ttu-id="f2c85-133">DefaultDrawingAttributes</span><span class="sxs-lookup"><span data-stu-id="f2c85-133">DefaultDrawingAttributes</span></span>

<span data-ttu-id="f2c85-134">Die <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> Eigenschaft bietet Zugriff auf Eigenschaften, z. B. Höhe, Breite und Farbe der Striche zu erstellende ein <xref:System.Windows.Controls.InkCanvas>.</span><span class="sxs-lookup"><span data-stu-id="f2c85-134">The <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> property provides access to properties such as the height, width, and color of the strokes to be created in an <xref:System.Windows.Controls.InkCanvas>.</span></span> <span data-ttu-id="f2c85-135">Sobald Sie ändern die <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>, alle zukünftigen Striche eingegeben haben, in der <xref:System.Windows.Controls.InkCanvas> werden mit den neuen Eigenschaftswerten gerendert.</span><span class="sxs-lookup"><span data-stu-id="f2c85-135">Once you change the <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>, all future strokes entered into the <xref:System.Windows.Controls.InkCanvas> are rendered with the new property values.</span></span>

<span data-ttu-id="f2c85-136">Zusätzlich zum Ändern der <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> in der CodeBehind-Datei können Sie XAML-Syntax verwenden, für die Angabe <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="f2c85-136">In addition to modifying the <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> in the code-behind file, you can use XAML syntax for specifying <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> properties.</span></span>

<span data-ttu-id="f2c85-137">Im nächste Beispiel veranschaulicht das Festlegen der <xref:System.Windows.Ink.DrawingAttributes.Color%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="f2c85-137">The next example demonstrates how to set the <xref:System.Windows.Ink.DrawingAttributes.Color%2A> property.</span></span> <span data-ttu-id="f2c85-138">Um diesen Code zu verwenden, erstellen Sie ein neues WPF-Projekt, das Namen "HelloInkCanvas" in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f2c85-138">To use this code, create a new WPF project called "HelloInkCanvas" in Visual Studio.</span></span> <span data-ttu-id="f2c85-139">Ersetzen Sie den Code in die *"MainWindow.xaml"* -Datei mit den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="f2c85-139">Replace the code in the *MainWindow.xaml* file with the following code:</span></span>

[!code-xaml[HelloInkCanvas#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HelloInkCanvas/CSharp/Window1.xaml#1)]

<span data-ttu-id="f2c85-140">Fügen Sie die folgenden Ereignishandler der Schaltfläche auf der CodeBehind-Datei, in der MainWindow-Klasse:</span><span class="sxs-lookup"><span data-stu-id="f2c85-140">Next, add the following button event handlers to the code behind file, inside the MainWindow class:</span></span>

[!code-csharp[HelloInkCanvas#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HelloInkCanvas/CSharp/Window1.xaml.cs#2)]

<span data-ttu-id="f2c85-141">Drücken Sie nach dem Kopieren dieser Code **F5** in Visual Studio, um das Programm im Debugger auszuführen.</span><span class="sxs-lookup"><span data-stu-id="f2c85-141">After copying this code, press **F5** in Visual Studio to run the program in the debugger.</span></span>

<span data-ttu-id="f2c85-142">Beachten Sie, dass die <xref:System.Windows.Controls.StackPanel> platziert die Schaltflächen oben auf der <xref:System.Windows.Controls.InkCanvas>.</span><span class="sxs-lookup"><span data-stu-id="f2c85-142">Notice how the <xref:System.Windows.Controls.StackPanel> places the buttons on top of the <xref:System.Windows.Controls.InkCanvas>.</span></span> <span data-ttu-id="f2c85-143">Wenn Sie, Freihandeingaben oberhalb der Schaltflächen versuchen, die <xref:System.Windows.Controls.InkCanvas> erfasst und rendert Freihandeingaben hinter den Schaltflächen.</span><span class="sxs-lookup"><span data-stu-id="f2c85-143">If you try to ink over the top of the buttons, the <xref:System.Windows.Controls.InkCanvas> collects and renders the ink behind the buttons.</span></span> <span data-ttu-id="f2c85-144">Dies ist, da die Schaltflächen gleichgeordnete Elemente des sind die <xref:System.Windows.Controls.InkCanvas> und nicht untergeordnet.</span><span class="sxs-lookup"><span data-stu-id="f2c85-144">This is because the buttons are siblings of the <xref:System.Windows.Controls.InkCanvas> as opposed to children.</span></span> <span data-ttu-id="f2c85-145">Außerdem sind die Schaltflächen in der Z-Reihenfolge weiter oben, weshalb die Freihandeingaben dahinter gerendert werden.</span><span class="sxs-lookup"><span data-stu-id="f2c85-145">Also, the buttons are higher in the z-order, so the ink is rendered behind them.</span></span>

## <a name="see-also"></a><span data-ttu-id="f2c85-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f2c85-146">See Also</span></span>

- <xref:System.Windows.Ink.DrawingAttributes>
- <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>
- <xref:System.Windows.Ink>