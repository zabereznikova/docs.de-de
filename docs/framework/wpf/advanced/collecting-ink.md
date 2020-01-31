---
title: Erfassen digitaler Freihand
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
ms.openlocfilehash: 813a5313a6fbf83c36cdbed1f64ce69a217ad788
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76747029"
---
# <a name="collect-ink"></a><span data-ttu-id="9d366-102">Frei Hand Eingaben erfassen</span><span class="sxs-lookup"><span data-stu-id="9d366-102">Collect Ink</span></span>

<span data-ttu-id="9d366-103">Als einen ihrer zentralen Funktionsbestandteile erfasst die [Windows Presentation Foundation](../index.md)-Plattform Freihandeingaben.</span><span class="sxs-lookup"><span data-stu-id="9d366-103">The [Windows Presentation Foundation](../index.md) platform collects digital ink as a core part of its functionality.</span></span> <span data-ttu-id="9d366-104">In diesem Thema werden die Methoden für die Sammlung von frei Hand Eingaben in Windows Presentation Foundation (WPF) erläutert.</span><span class="sxs-lookup"><span data-stu-id="9d366-104">This topic discusses methods for collection of ink in Windows Presentation Foundation (WPF).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9d366-105">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="9d366-105">Prerequisites</span></span>

<span data-ttu-id="9d366-106">Um die folgenden Beispiele verwenden zu können, müssen Sie zuerst Visual Studio und den Windows SDK installieren.</span><span class="sxs-lookup"><span data-stu-id="9d366-106">To use the following examples, you must first install Visual Studio and the Windows SDK.</span></span> <span data-ttu-id="9d366-107">Außerdem sollten Sie wissen, wie Anwendungen für das WPF geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="9d366-107">You should also understand how to write applications for the WPF.</span></span> <span data-ttu-id="9d366-108">Weitere Informationen zu den ersten Schritten mit WPF finden Sie unter Exemplarische Vorgehensweise [: meine erste WPF-Desktop Anwendung](../getting-started/walkthrough-my-first-wpf-desktop-application.md).</span><span class="sxs-lookup"><span data-stu-id="9d366-108">For more information about getting started with WPF, see [Walkthrough: My first WPF desktop application](../getting-started/walkthrough-my-first-wpf-desktop-application.md).</span></span>

## <a name="use-the-inkcanvas-element"></a><span data-ttu-id="9d366-109">Verwenden des InkCanvas-Elements</span><span class="sxs-lookup"><span data-stu-id="9d366-109">Use the InkCanvas Element</span></span>

<span data-ttu-id="9d366-110">Das <xref:System.Windows.Controls.InkCanvas?displayProperty=fullName>-Element bietet die einfachste Möglichkeit, frei Hand Eingaben in WPF zu erfassen.</span><span class="sxs-lookup"><span data-stu-id="9d366-110">The <xref:System.Windows.Controls.InkCanvas?displayProperty=fullName> element provides the easiest way to collect ink in WPF.</span></span> <span data-ttu-id="9d366-111">Verwenden Sie ein <xref:System.Windows.Controls.InkCanvas>-Element, um frei Hand Eingaben zu empfangen und anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="9d366-111">Use an <xref:System.Windows.Controls.InkCanvas> element to receive and display ink input.</span></span> <span data-ttu-id="9d366-112">Freihandeingaben erfolgen im Allgemeinen mithilfe eines Tablettstifts, der über ein Digitalisierungsgerät Freihandstriche erzeugt.</span><span class="sxs-lookup"><span data-stu-id="9d366-112">You commonly input ink through the use of a stylus, which interacts with a digitizer to produce ink strokes.</span></span> <span data-ttu-id="9d366-113">Anstelle eines Tablettstifts kann auch eine Maus verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9d366-113">In addition, a mouse can be used in place of a stylus.</span></span> <span data-ttu-id="9d366-114">Die erstellten Striche werden als <xref:System.Windows.Ink.Stroke> Objekte dargestellt und können sowohl Programm gesteuert als auch durch Benutzereingaben bearbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="9d366-114">The created strokes are represented as <xref:System.Windows.Ink.Stroke> objects, and they can be manipulated both programmatically and by user input.</span></span> <span data-ttu-id="9d366-115">Der <xref:System.Windows.Controls.InkCanvas> ermöglicht Benutzern das auswählen, ändern oder Löschen eines vorhandenen <xref:System.Windows.Ink.Stroke>.</span><span class="sxs-lookup"><span data-stu-id="9d366-115">The <xref:System.Windows.Controls.InkCanvas> enables users to select, modify, or delete an existing <xref:System.Windows.Ink.Stroke>.</span></span>

<span data-ttu-id="9d366-116">Mithilfe von XAML können Sie die frei Hand Auflistung so einfach einrichten, wie Sie der Struktur ein **InkCanvas** -Element hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="9d366-116">By using XAML, you can set up ink collection as easily as adding an **InkCanvas** element to your tree.</span></span> <span data-ttu-id="9d366-117">Im folgenden Beispiel wird einem WPF-Standard Projekt, das in Visual Studio erstellt wurde, ein <xref:System.Windows.Controls.InkCanvas> hinzugefügt:</span><span class="sxs-lookup"><span data-stu-id="9d366-117">The following example adds an <xref:System.Windows.Controls.InkCanvas> to a default WPF project created in Visual Studio:</span></span>

[!code-xaml[DigitalInkTopics#6](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#6)]

<span data-ttu-id="9d366-118">Das **InkCanvas** -Element kann auch untergeordnete Elemente enthalten, sodass Sie nahezu allen Typen von XAML-Elementen frei Hand Anmerkung-Funktionen hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="9d366-118">The **InkCanvas** element can also contain child elements, making it possible to add ink annotation capabilities to almost any type of XAML element.</span></span> <span data-ttu-id="9d366-119">Wenn Sie z. b. einem Textelement Bindungsfunktionen hinzufügen möchten, machen Sie es einfach als untergeordnetes Element eines <xref:System.Windows.Controls.InkCanvas>:</span><span class="sxs-lookup"><span data-stu-id="9d366-119">For example, to add inking capabilities to a text element, simply make it a child of an <xref:System.Windows.Controls.InkCanvas>:</span></span>

[!code-xaml[DigitalInkTopics#5](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#5)]

<span data-ttu-id="9d366-120">Das Hinzufügen von Unterstützung für das Markieren eines Bilds mit frei Hand Eingaben ist ebenso einfach:</span><span class="sxs-lookup"><span data-stu-id="9d366-120">Adding support for marking up an image with ink is just as easy:</span></span>

[!code-xaml[DigitalInkTopics#7](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#7)]

### <a name="inkcollection-modes"></a><span data-ttu-id="9d366-121">InkCollection-Modi</span><span class="sxs-lookup"><span data-stu-id="9d366-121">InkCollection Modes</span></span>

<span data-ttu-id="9d366-122">Der <xref:System.Windows.Controls.InkCanvas> bietet Unterstützung für verschiedene Eingabemodi über seine <xref:System.Windows.Controls.InkCanvas.EditingMode%2A>-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="9d366-122">The <xref:System.Windows.Controls.InkCanvas> provides support for various input modes through its <xref:System.Windows.Controls.InkCanvas.EditingMode%2A> property.</span></span>

### <a name="manipulate-ink"></a><span data-ttu-id="9d366-123">Freihand bearbeiten</span><span class="sxs-lookup"><span data-stu-id="9d366-123">Manipulate Ink</span></span>

<span data-ttu-id="9d366-124">Der <xref:System.Windows.Controls.InkCanvas> bietet Unterstützung für viele Handschrift Bearbeitungsvorgänge.</span><span class="sxs-lookup"><span data-stu-id="9d366-124">The <xref:System.Windows.Controls.InkCanvas> provides support for many ink editing operations.</span></span> <span data-ttu-id="9d366-125"><xref:System.Windows.Controls.InkCanvas> unterstützt z. b. das Löschen von abblicken, und es ist kein zusätzlicher Code erforderlich, um dem-Element die Funktionalität hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="9d366-125">For example, <xref:System.Windows.Controls.InkCanvas> supports back-of-pen erase, and no additional code is needed to add the functionality to the element.</span></span>

#### <a name="selection"></a><span data-ttu-id="9d366-126">Markierung</span><span class="sxs-lookup"><span data-stu-id="9d366-126">Selection</span></span>

<span data-ttu-id="9d366-127">Das Festlegen des Auswahlmodus ist so einfach wie das Festlegen der <xref:System.Windows.Controls.InkCanvasEditingMode>-Eigenschaft auf **Select**.</span><span class="sxs-lookup"><span data-stu-id="9d366-127">Setting selection mode is as simple as setting the <xref:System.Windows.Controls.InkCanvasEditingMode> property to **Select**.</span></span>

<span data-ttu-id="9d366-128">Mit dem folgenden Code wird der Bearbeitungsmodus basierend auf dem Wert eines <xref:System.Windows.Forms.CheckBox>festgelegt:</span><span class="sxs-lookup"><span data-stu-id="9d366-128">The following code sets the editing mode based on the value of a <xref:System.Windows.Forms.CheckBox>:</span></span>

[!code-csharp[DigitalInkTopics#8](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#8)]
[!code-vb[DigitalInkTopics#8](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#8)]

#### <a name="drawingattributes"></a><span data-ttu-id="9d366-129">DrawingAttributes</span><span class="sxs-lookup"><span data-stu-id="9d366-129">DrawingAttributes</span></span>

<span data-ttu-id="9d366-130">Verwenden Sie die <xref:System.Windows.Ink.Stroke.DrawingAttributes%2A>-Eigenschaft, um die Darstellung von frei Hand Strichen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="9d366-130">Use the <xref:System.Windows.Ink.Stroke.DrawingAttributes%2A> property to change the appearance of ink strokes.</span></span> <span data-ttu-id="9d366-131">Beispielsweise legt der <xref:System.Windows.Ink.DrawingAttributes.Color%2A> Member von <xref:System.Windows.Ink.DrawingAttributes> die Farbe der gerenderten <xref:System.Windows.Ink.Stroke>fest.</span><span class="sxs-lookup"><span data-stu-id="9d366-131">For instance, the <xref:System.Windows.Ink.DrawingAttributes.Color%2A> member of <xref:System.Windows.Ink.DrawingAttributes> sets the color of the rendered <xref:System.Windows.Ink.Stroke>.</span></span>

<span data-ttu-id="9d366-132">Im folgenden Beispiel wird die Farbe der ausgewählten Striche in rot geändert:</span><span class="sxs-lookup"><span data-stu-id="9d366-132">The following example changes the color of the selected strokes to red:</span></span>

[!code-csharp[DigitalInkTopics#9](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#9)]
[!code-vb[DigitalInkTopics#9](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#9)]

### <a name="defaultdrawingattributes"></a><span data-ttu-id="9d366-133">DefaultDrawingAttributes</span><span class="sxs-lookup"><span data-stu-id="9d366-133">DefaultDrawingAttributes</span></span>

<span data-ttu-id="9d366-134">Die <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>-Eigenschaft ermöglicht den Zugriff auf Eigenschaften, z. b. Höhe, Breite und Farbe der Striche, die in einem <xref:System.Windows.Controls.InkCanvas>erstellt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="9d366-134">The <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> property provides access to properties such as the height, width, and color of the strokes to be created in an <xref:System.Windows.Controls.InkCanvas>.</span></span> <span data-ttu-id="9d366-135">Nachdem Sie die <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>geändert haben, werden alle zukünftigen Eingaben, die in die <xref:System.Windows.Controls.InkCanvas> eingegeben werden, mit den neuen Eigenschafts Werten gerendert.</span><span class="sxs-lookup"><span data-stu-id="9d366-135">Once you change the <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>, all future strokes entered into the <xref:System.Windows.Controls.InkCanvas> are rendered with the new property values.</span></span>

<span data-ttu-id="9d366-136">Zusätzlich zum Ändern der <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> in der Code Behind-Datei können Sie die XAML-Syntax zum Angeben von <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> Eigenschaften verwenden.</span><span class="sxs-lookup"><span data-stu-id="9d366-136">In addition to modifying the <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> in the code-behind file, you can use XAML syntax for specifying <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> properties.</span></span>

<span data-ttu-id="9d366-137">Im nächsten Beispiel wird veranschaulicht, wie die <xref:System.Windows.Ink.DrawingAttributes.Color%2A>-Eigenschaft festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="9d366-137">The next example demonstrates how to set the <xref:System.Windows.Ink.DrawingAttributes.Color%2A> property.</span></span> <span data-ttu-id="9d366-138">Um diesen Code zu verwenden, erstellen Sie in Visual Studio ein neues WPF-Projekt mit dem Namen "HelloInkCanvas".</span><span class="sxs-lookup"><span data-stu-id="9d366-138">To use this code, create a new WPF project called "HelloInkCanvas" in Visual Studio.</span></span> <span data-ttu-id="9d366-139">Ersetzen Sie den Code in der Datei " *MainWindow. XAML* " durch den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="9d366-139">Replace the code in the *MainWindow.xaml* file with the following code:</span></span>

[!code-xaml[HelloInkCanvas#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HelloInkCanvas/CSharp/Window1.xaml#1)]

<span data-ttu-id="9d366-140">Fügen Sie als nächstes die folgenden Ereignishandler für die Schaltfläche der Code-Behind-Datei innerhalb der MainWindow-Klasse hinzu:</span><span class="sxs-lookup"><span data-stu-id="9d366-140">Next, add the following button event handlers to the code behind file, inside the MainWindow class:</span></span>

[!code-csharp[HelloInkCanvas#2](~/samples/snippets/csharp/VS_Snippets_Wpf/HelloInkCanvas/CSharp/Window1.xaml.cs#2)]

<span data-ttu-id="9d366-141">Nachdem Sie diesen Code kopiert haben, drücken Sie in Visual Studio **F5** , um das Programm im Debugger auszuführen.</span><span class="sxs-lookup"><span data-stu-id="9d366-141">After copying this code, press **F5** in Visual Studio to run the program in the debugger.</span></span>

<span data-ttu-id="9d366-142">Beachten Sie, wie die <xref:System.Windows.Controls.StackPanel> die Schaltflächen oben auf der <xref:System.Windows.Controls.InkCanvas>platziert.</span><span class="sxs-lookup"><span data-stu-id="9d366-142">Notice how the <xref:System.Windows.Controls.StackPanel> places the buttons on top of the <xref:System.Windows.Controls.InkCanvas>.</span></span> <span data-ttu-id="9d366-143">Wenn Sie versuchen, über den oberen Rand der Schaltflächen zu übergeben, sammelt und rendert der <xref:System.Windows.Controls.InkCanvas> die frei Hand Eingaben hinter den Schaltflächen.</span><span class="sxs-lookup"><span data-stu-id="9d366-143">If you try to ink over the top of the buttons, the <xref:System.Windows.Controls.InkCanvas> collects and renders the ink behind the buttons.</span></span> <span data-ttu-id="9d366-144">Dies liegt daran, dass die Schaltflächen gleich geordnete Elemente der <xref:System.Windows.Controls.InkCanvas> im Gegensatz zu untergeordneten Elementen sind.</span><span class="sxs-lookup"><span data-stu-id="9d366-144">This is because the buttons are siblings of the <xref:System.Windows.Controls.InkCanvas> as opposed to children.</span></span> <span data-ttu-id="9d366-145">Außerdem sind die Schaltflächen in der Z-Reihenfolge weiter oben, weshalb die Freihandeingaben dahinter gerendert werden.</span><span class="sxs-lookup"><span data-stu-id="9d366-145">Also, the buttons are higher in the z-order, so the ink is rendered behind them.</span></span>

## <a name="see-also"></a><span data-ttu-id="9d366-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9d366-146">See also</span></span>

- <xref:System.Windows.Ink.DrawingAttributes>
- <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>
- <xref:System.Windows.Ink>
