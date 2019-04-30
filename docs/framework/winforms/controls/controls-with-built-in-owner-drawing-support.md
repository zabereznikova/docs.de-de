---
title: Steuerelemente mit integrierter Ownerdrawing-Unterstützung
ms.date: 03/30/2017
helpviewer_keywords:
- drawing [Windows Forms], owner
- drawing [Windows Forms], custom
- controls [Windows Forms], changing appearance
- custom drawing
- owner drawing
ms.assetid: 3823d01e-9610-43e6-864d-99f9b7c2b351
ms.openlocfilehash: 1807170b2f5df2333ec3b271a11f9b929c1e7993
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62011579"
---
# <a name="controls-with-built-in-owner-drawing-support"></a><span data-ttu-id="69df2-102">Steuerelemente mit integrierter Ownerdrawing-Unterstützung</span><span class="sxs-lookup"><span data-stu-id="69df2-102">Controls with Built-In Owner-Drawing Support</span></span>
<span data-ttu-id="69df2-103">Ownerdrawing in Windows Forms, das auch als benutzerdefiniertes Zeichnen bezeichnet, ist ein Verfahren zum Ändern der Darstellung bestimmter Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="69df2-103">Owner drawing in Windows Forms, which is also known as custom drawing, is a technique for changing the visual appearance of certain controls.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="69df2-104">Das Wort "Control" in diesem Thema wird verwendet, um Klassen bezeichnet, die entweder ableiten <xref:System.Windows.Forms.Control> oder <xref:System.ComponentModel.Component>.</span><span class="sxs-lookup"><span data-stu-id="69df2-104">The word "control" in this topic is used to mean classes that derive from either <xref:System.Windows.Forms.Control> or <xref:System.ComponentModel.Component>.</span></span>  
  
 <span data-ttu-id="69df2-105">In der Regel Windows das Zeichnen behandelt automatisch indem eigenschafteneinstellungen wie z. B. <xref:System.Windows.Forms.Control.BackColor%2A> um die Darstellung eines Steuerelements zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="69df2-105">Typically, Windows handles painting automatically by using property settings such as <xref:System.Windows.Forms.Control.BackColor%2A> to determine the appearance of a control.</span></span> <span data-ttu-id="69df2-106">Beim Ownerdrawing übernehmen Sie das Zeichnen und können Darstellungselemente ändern, die nicht mithilfe von Eigenschaften angepasst werden können.</span><span class="sxs-lookup"><span data-stu-id="69df2-106">With owner drawing, you take over the painting process, changing elements of appearance that are not available by using properties.</span></span> <span data-ttu-id="69df2-107">Beispielsweise kann bei zahlreichen Steuerelementen die Farbe des angezeigten Textes festgelegt werden. Dabei ist die Anzeige jedoch auf eine Farbe beschränkt.</span><span class="sxs-lookup"><span data-stu-id="69df2-107">For example, many controls let you set the color of the text that is displayed, but you are limited to a single color.</span></span> <span data-ttu-id="69df2-108">Das Ownerdrawing bietet beispielsweise die Möglichkeit, einen Teil des Textes schwarz und den anderen rot anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="69df2-108">Owner drawing enables you to do things like display part of the text in black and part in red.</span></span>  
  
 <span data-ttu-id="69df2-109">In der Praxis ähnelt Ownerdrawing dem Zeichnen von Grafiken auf einem Formular.</span><span class="sxs-lookup"><span data-stu-id="69df2-109">In practice, owner drawing is similar to drawing graphics on a form.</span></span> <span data-ttu-id="69df2-110">Angenommen, Sie können Grafikmethoden in einem Ereignishandler für Verwenden des Formulars <xref:System.Windows.Forms.Control.Paint> Ereignis zum Emulieren einer `ListBox` -Steuerelement, müssten Sie jedoch Ihren eigenen Code so ändern alle Benutzerinteraktionen zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="69df2-110">For example, you could use graphics methods in a handler for the form's <xref:System.Windows.Forms.Control.Paint> event to emulate a `ListBox` control, but you would have to write your own code to handle all user interaction.</span></span> <span data-ttu-id="69df2-111">Beim Ownerdrawing verwendet das Steuerelement den von Ihnen geschriebenen Code, um den Inhalt zu zeichnen, behält im Übrigen aber seine gesamte systeminterne Funktionalität bei.</span><span class="sxs-lookup"><span data-stu-id="69df2-111">With owner drawing, the control uses your code to draw its contents but otherwise retains all its intrinsic capabilities.</span></span> <span data-ttu-id="69df2-112">Sie können Grafikmethoden zum Zeichnen der einzelnen Elemente im Steuerelement oder zum Anpassen einiger Aspekte einzelner Elemente verwenden, während für andere Aspekte einzelner Elemente wiederum die Standarddarstellung übernommen werden kann.</span><span class="sxs-lookup"><span data-stu-id="69df2-112">You can use graphics methods to draw each item in the control or to customize some aspects of each item while you use the default appearance for other aspects of each item.</span></span>  
  
## <a name="owner-drawing-in-windows-forms-controls"></a><span data-ttu-id="69df2-113">Ownerdrawing in Windows Forms-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="69df2-113">Owner Drawing in Windows Forms Controls</span></span>  
 <span data-ttu-id="69df2-114">Um Ownerdrawing in Steuerelementen auszuführen, die diese Art des Zeichnens unterstützen, legen Sie normalerweise eine Eigenschaft fest und behandeln mindestens ein Ereignis.</span><span class="sxs-lookup"><span data-stu-id="69df2-114">To perform owner drawing in controls that support it, you will typically set one property and handle one or more events.</span></span>  
  
 <span data-ttu-id="69df2-115">Die meisten Steuerelemente mit Ownerdrawing-Unterstützung verfügen über die `OwnerDraw`-Eigenschaft oder `DrawMode`-Eigenschaft, die angibt, ob das Steuerelement eines oder mehrere zeichnungsbezogene Ereignisse auslöst, sobald es gezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="69df2-115">Most controls that support owner drawing have an `OwnerDraw` or `DrawMode` property that indicates whether the control will raise its drawing-related event or events when it paints itself.</span></span>  
  
 <span data-ttu-id="69df2-116">Zu den Steuerelementen, die keine `OwnerDraw`-Eigenschaft oder `DrawMode`-Eigenschaft aufweisen, gehört das `DataGridView`-Steuerelement, das automatisch ausgelöste Zeichnungsereignisse bereitstellt, sowie das `ToolStrip`-Steuerelement, das unter Verwendung einer externen Renderklasse gezeichnet wird, die eigene zeichnungsbezogene Ereignisse aufweist.</span><span class="sxs-lookup"><span data-stu-id="69df2-116">Controls that do not have an `OwnerDraw` or `DrawMode` property include the `DataGridView` control, which provides drawing events that occur automatically, and the `ToolStrip` control, which is drawn using an external rendering class that has its own drawing-related events.</span></span>  
  
 <span data-ttu-id="69df2-117">Es stehen viele verschiedene Arten von Zeichnungsereignissen zur Verfügung. Ein typisches Zeichnungsereignis tritt jedoch auf, wenn ein einzelnes Element innerhalb eines Steuerelements gezeichnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="69df2-117">There are many different kinds of drawing events, but a typical drawing event occurs in order to draw a single item within a control.</span></span> <span data-ttu-id="69df2-118">Der Ereignishandler empfängt ein `EventArgs`-Objekt mit Informationen zum gezeichneten Element sowie zu den Tools, die zum Zeichnen verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="69df2-118">The event handler receives an `EventArgs` object that contains information about the item being drawn and tools you can use to draw it.</span></span> <span data-ttu-id="69df2-119">Dieses Objekt enthält z. B. in der Regel Indexnummer des Elements, in der übergeordneten Auflistung, eine <xref:System.Drawing.Rectangle> , der angibt, die Anzeige des Elements der Grenzen, und ein <xref:System.Drawing.Graphics> Objekt zum Aufrufen von Zeichnungsmethoden.</span><span class="sxs-lookup"><span data-stu-id="69df2-119">For example, this object typically contains the item's index number within its parent collection, a <xref:System.Drawing.Rectangle> that indicates the item's display boundaries, and a <xref:System.Drawing.Graphics> object for calling paint methods.</span></span> <span data-ttu-id="69df2-120">Bei einigen Ereignissen umfasst das `EventArgs`-Objekt zusätzliche Informationen zum Element sowie zu den Methoden, die aufgerufen werden können, um einige Aspekte des Elements in der Standarddarstellung zu zeichnen, z. B. den Hintergrund oder ein Fokusrechteck.</span><span class="sxs-lookup"><span data-stu-id="69df2-120">For some events, the `EventArgs` object provides additional information about the item and methods that you can call to paint some aspects of the item by default, such as the background or a focus rectangle.</span></span>  
  
 <span data-ttu-id="69df2-121">Zum Erstellen eines wiederverwendbaren Steuerelements, das Ownerdrawing-Anpassungen enthält, erstellen Sie eine neue Klasse, die von einer Steuerelementklasse mit Ownerdrawing-Unterstützung abgeleitet ist.</span><span class="sxs-lookup"><span data-stu-id="69df2-121">To create a reusable control that contains your owner-drawn customizations, create a new class that derives from a control class that supports owner drawing.</span></span> <span data-ttu-id="69df2-122">Anstatt Zeichnungsereignisse zu behandeln, sollten Sie Ownerdrawing-Code in Überschreibungen für mindestens eine geeignete `On`*EventName*-Methode in der neuen Klasse einfügen.</span><span class="sxs-lookup"><span data-stu-id="69df2-122">Rather than handling drawing events, include your owner-drawing code in overrides for the appropriate `On`*EventName* method or methods in the new class.</span></span> <span data-ttu-id="69df2-123">Stellen Sie in diesem Fall sicher, dass die `On`*EventName*-Methoden der Basisklasse aufgerufen werden, damit Benutzer des Steuerelements Ownerdrawing-Ereignisse behandeln und weitere Anpassungen vornehmen können.</span><span class="sxs-lookup"><span data-stu-id="69df2-123">Make sure that you call the base class `On`*EventName* method or methods in this case so that users of your control can handle owner-drawing events and provide additional customization.</span></span>  
  
 <span data-ttu-id="69df2-124">Die folgenden Windows Forms-Steuerelemente unterstützen Ownerdrawing in allen Versionen von .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="69df2-124">The following Windows Forms controls support owner drawing in all versions of the .NET Framework:</span></span>  
  
- <xref:System.Windows.Forms.ListBox>  
  
- <xref:System.Windows.Forms.ComboBox>  
  
- <span data-ttu-id="69df2-125"><xref:System.Windows.Forms.MenuItem> (verwendet von <xref:System.Windows.Forms.MainMenu> und <xref:System.Windows.Forms.ContextMenu>)</span><span class="sxs-lookup"><span data-stu-id="69df2-125"><xref:System.Windows.Forms.MenuItem> (used by <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu>)</span></span>  
  
- <xref:System.Windows.Forms.TabControl>  
  
 <span data-ttu-id="69df2-126">Die folgenden Steuerelemente unterstützen Ownerdrawing nur in [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="69df2-126">The following controls support owner drawing only in [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)]:</span></span>  
  
- <xref:System.Windows.Forms.ToolTip>  
  
- <xref:System.Windows.Forms.ListView>  
  
- <xref:System.Windows.Forms.TreeView>  
  
 <span data-ttu-id="69df2-127">Die folgenden Steuerelemente unterstützen Ownerdrawing und sind in [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)] neu:</span><span class="sxs-lookup"><span data-stu-id="69df2-127">The following controls support owner drawing and are new in [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)]:</span></span>  
  
- <xref:System.Windows.Forms.DataGridView>  
  
- <xref:System.Windows.Forms.ToolStrip>  
  
 <span data-ttu-id="69df2-128">Die folgenden Abschnitte enthalten zusätzliche Details zu jedem dieser Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="69df2-128">The following sections provide additional details for each of these controls.</span></span>  
  
### <a name="listbox-and-combobox-controls"></a><span data-ttu-id="69df2-129">Die Steuerelemente ListBox und ComboBox</span><span class="sxs-lookup"><span data-stu-id="69df2-129">ListBox and ComboBox Controls</span></span>  
 <span data-ttu-id="69df2-130">Die <xref:System.Windows.Forms.ListBox> und <xref:System.Windows.Forms.ComboBox> Steuerelemente ermöglichen Ihnen, einzelne Elemente im Steuerelement entweder in derselben oder in verschiedenen Größen zu zeichnen.</span><span class="sxs-lookup"><span data-stu-id="69df2-130">The <xref:System.Windows.Forms.ListBox> and <xref:System.Windows.Forms.ComboBox> controls enable you to draw individual items in the control either all in one size, or in varying sizes.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="69df2-131">Obwohl die <xref:System.Windows.Forms.CheckedListBox> Steuerelement ergibt sich aus der <xref:System.Windows.Forms.ListBox> -Steuerelement, er unterstützt keine Ownerdrawing.</span><span class="sxs-lookup"><span data-stu-id="69df2-131">Although the <xref:System.Windows.Forms.CheckedListBox> control is derived from the <xref:System.Windows.Forms.ListBox> control, it does not support owner drawing.</span></span>  
  
 <span data-ttu-id="69df2-132">Um alle Elemente in derselben Größe zu zeichnen, legen die `DrawMode` Eigenschaft <xref:System.Windows.Forms.DrawMode.OwnerDrawFixed> und behandeln die `DrawItem` Ereignis.</span><span class="sxs-lookup"><span data-stu-id="69df2-132">To draw each item the same size, set the `DrawMode` property to <xref:System.Windows.Forms.DrawMode.OwnerDrawFixed> and handle the `DrawItem` event.</span></span>  
  
 <span data-ttu-id="69df2-133">Um alle Elemente in einer anderen Größe zu zeichnen, legen die `DrawMode` Eigenschaft <xref:System.Windows.Forms.DrawMode.OwnerDrawVariable> und behandeln sowohl die `MeasureItem` und `DrawItem` Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="69df2-133">To draw each item using a different size, set the `DrawMode` property to <xref:System.Windows.Forms.DrawMode.OwnerDrawVariable> and handle both the `MeasureItem` and `DrawItem` events.</span></span> <span data-ttu-id="69df2-134">Mit dem `MeasureItem`-Ereignis können Sie die Größe eines Elements angeben, bevor das `DrawItem`-Ereignis für das jeweilige Element auftritt.</span><span class="sxs-lookup"><span data-stu-id="69df2-134">The `MeasureItem` event lets you indicate the size of an item before the `DrawItem` event occurs for that item.</span></span>  
  
 <span data-ttu-id="69df2-135">Weitere Informationen, einschließlich Codebeispiele, finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="69df2-135">For more information, including code examples, see the following topics:</span></span>  
  
- <xref:System.Windows.Forms.ListBox.DrawMode%2A?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.ListBox.MeasureItem?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.ListBox.DrawItem?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.ComboBox.DrawMode%2A?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.ComboBox.MeasureItem?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.ComboBox.DrawItem?displayProperty=nameWithType>  
  
- [<span data-ttu-id="69df2-136">Vorgehensweise: Erstellen von Text mit variabler Größe in einem ComboBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="69df2-136">How to: Create Variable Sized Text in a ComboBox Control</span></span>](how-to-create-variable-sized-text-in-a-combobox-control.md)  
  
### <a name="menuitem-component"></a><span data-ttu-id="69df2-137">MenuItem-Komponente</span><span class="sxs-lookup"><span data-stu-id="69df2-137">MenuItem Component</span></span>  
 <span data-ttu-id="69df2-138">Die <xref:System.Windows.Forms.MenuItem> -Komponente darstellt, ein einzelnes Menüelement in einem <xref:System.Windows.Forms.MainMenu> oder <xref:System.Windows.Forms.ContextMenu> Komponente.</span><span class="sxs-lookup"><span data-stu-id="69df2-138">The <xref:System.Windows.Forms.MenuItem> component represents a single menu item in a <xref:System.Windows.Forms.MainMenu> or <xref:System.Windows.Forms.ContextMenu> component.</span></span>  
  
 <span data-ttu-id="69df2-139">Zum Zeichnen einer <xref:System.Windows.Forms.MenuItem>, legen die `OwnerDraw` Eigenschaft `true` und behandeln die `DrawItem` Ereignis.</span><span class="sxs-lookup"><span data-stu-id="69df2-139">To draw a <xref:System.Windows.Forms.MenuItem>, set its `OwnerDraw` property to `true` and handle its `DrawItem` event.</span></span> <span data-ttu-id="69df2-140">Um die Größe des Menüelements anzupassen, bevor das `DrawItem`-Ereignis auftritt, behandeln Sie das `MeasureItem`-Ereignis des Elements.</span><span class="sxs-lookup"><span data-stu-id="69df2-140">To customize the size of the menu item before the `DrawItem` event occurs, handle the item's `MeasureItem` event.</span></span>  
  
 <span data-ttu-id="69df2-141">Weitere Informationen, einschließlich Codebeispiele, finden Sie unter den folgenden Referenzthemen:</span><span class="sxs-lookup"><span data-stu-id="69df2-141">For more information, including code examples, see the following reference topics:</span></span>  
  
- <xref:System.Windows.Forms.MenuItem.OwnerDraw%2A?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.MenuItem.DrawItem?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.MenuItem.MeasureItem?displayProperty=nameWithType>  
  
### <a name="tabcontrol-control"></a><span data-ttu-id="69df2-142">TabControl-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="69df2-142">TabControl Control</span></span>  
 <span data-ttu-id="69df2-143">Die <xref:System.Windows.Forms.TabControl> -Steuerelement ermöglicht Ihnen, einzelne Registerkarten im Steuerelement zu zeichnen.</span><span class="sxs-lookup"><span data-stu-id="69df2-143">The <xref:System.Windows.Forms.TabControl> control enables you to draw individual tabs in the control.</span></span> <span data-ttu-id="69df2-144">Ownerdrawing wirkt sich nur die Registerkarten an. die <xref:System.Windows.Forms.TabPage> Inhalt sind nicht betroffen.</span><span class="sxs-lookup"><span data-stu-id="69df2-144">Owner drawing affects only the tabs; the <xref:System.Windows.Forms.TabPage> contents are not affected.</span></span>  
  
 <span data-ttu-id="69df2-145">Zum Zeichnen der einzelnen Registerkarten in einem <xref:System.Windows.Forms.TabControl>, legen die `DrawMode` Eigenschaft, um <xref:System.Windows.Forms.TabDrawMode.OwnerDrawFixed> und behandeln die `DrawItem` Ereignis.</span><span class="sxs-lookup"><span data-stu-id="69df2-145">To draw each tab in a <xref:System.Windows.Forms.TabControl>, set the `DrawMode` property to <xref:System.Windows.Forms.TabDrawMode.OwnerDrawFixed> and handle the `DrawItem` event.</span></span> <span data-ttu-id="69df2-146">Dieses Ereignis tritt jeweils einmal für jede Registerkarte auf, jedoch nur dann, wenn die Registerkarte im Steuerelement sichtbar ist.</span><span class="sxs-lookup"><span data-stu-id="69df2-146">This event occurs once for each tab only when the tab is visible in the control.</span></span>  
  
 <span data-ttu-id="69df2-147">Weitere Informationen, einschließlich Codebeispiele, finden Sie unter den folgenden Referenzthemen:</span><span class="sxs-lookup"><span data-stu-id="69df2-147">For more information, including code examples, see the following reference topics:</span></span>  
  
- <xref:System.Windows.Forms.TabControl.DrawMode%2A?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.TabControl.DrawItem?displayProperty=nameWithType>  
  
### <a name="tooltip-component"></a><span data-ttu-id="69df2-148">ToolTip-Komponente</span><span class="sxs-lookup"><span data-stu-id="69df2-148">ToolTip Component</span></span>  
 <span data-ttu-id="69df2-149">Die <xref:System.Windows.Forms.ToolTip> -Komponente können Sie die gesamte QuickInfo zu zeichnen, wenn er angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="69df2-149">The <xref:System.Windows.Forms.ToolTip> component enables you to draw the entire ToolTip when it is displayed.</span></span>  
  
 <span data-ttu-id="69df2-150">Zum Zeichnen einer <xref:System.Windows.Forms.ToolTip>, legen die `OwnerDraw` Eigenschaft `true` und behandeln die `Draw` Ereignis.</span><span class="sxs-lookup"><span data-stu-id="69df2-150">To draw a <xref:System.Windows.Forms.ToolTip>, set its `OwnerDraw` property to `true` and handle its `Draw` event.</span></span> <span data-ttu-id="69df2-151">Zum Anpassen der Größe des der <xref:System.Windows.Forms.ToolTip> vor der `Draw` -Ereignis auftritt, behandeln die `Popup` -Ereignis und legen die <xref:System.Windows.Forms.PopupEventArgs.ToolTipSize%2A> Eigenschaft im Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="69df2-151">To customize the size of the <xref:System.Windows.Forms.ToolTip> before the `Draw` event occurs, handle the `Popup` event and set the <xref:System.Windows.Forms.PopupEventArgs.ToolTipSize%2A> property in the event handler.</span></span>  
  
 <span data-ttu-id="69df2-152">Weitere Informationen, einschließlich Codebeispiele, finden Sie unter den folgenden Referenzthemen:</span><span class="sxs-lookup"><span data-stu-id="69df2-152">For more information, including code examples, see the following reference topics:</span></span>  
  
- <xref:System.Windows.Forms.ToolTip.OwnerDraw%2A?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.ToolTip.Draw?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.ToolTip.Popup?displayProperty=nameWithType>  
  
### <a name="listview-control"></a><span data-ttu-id="69df2-153">ListView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="69df2-153">ListView Control</span></span>  
 <span data-ttu-id="69df2-154">Die <xref:System.Windows.Forms.ListView> -Steuerelement ermöglicht Ihnen, einzelne Elemente, Unterelemente und Spaltenheader im Steuerelement zu zeichnen.</span><span class="sxs-lookup"><span data-stu-id="69df2-154">The <xref:System.Windows.Forms.ListView> control enables you to draw individual items, subitems, and column headers in the control.</span></span>  
  
 <span data-ttu-id="69df2-155">Um Ownerdrawing im Steuerelement zu aktivieren, legen Sie die `OwnerDraw`-Eigenschaft `true` fest.</span><span class="sxs-lookup"><span data-stu-id="69df2-155">To enable owner drawing in the control, set the `OwnerDraw` property to `true`.</span></span>  
  
 <span data-ttu-id="69df2-156">Um jedes Element im Steuerelement zu zeichnen, behandeln Sie das `DrawItem`-Ereignis.</span><span class="sxs-lookup"><span data-stu-id="69df2-156">To draw each item in the control, handle the `DrawItem` event.</span></span>  
  
 <span data-ttu-id="69df2-157">Um jedes Unterelement oder jeden Spaltenheader im Steuerelement zu zeichnen. wenn der <xref:System.Windows.Forms.ListView.View%2A> -Eigenschaftensatz auf <xref:System.Windows.Forms.View.Details>, behandeln die `DrawSubItem` und `DrawColumnHeader` Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="69df2-157">To draw each subitem or column header in the control when the <xref:System.Windows.Forms.ListView.View%2A> property is set to <xref:System.Windows.Forms.View.Details>, handle the `DrawSubItem` and `DrawColumnHeader` events.</span></span>  
  
 <span data-ttu-id="69df2-158">Weitere Informationen, einschließlich Codebeispiele, finden Sie unter den folgenden Referenzthemen:</span><span class="sxs-lookup"><span data-stu-id="69df2-158">For more information, including code examples, see the following reference topics:</span></span>  
  
- <xref:System.Windows.Forms.ListView.OwnerDraw%2A?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.ListView.DrawItem?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.ListView.DrawSubItem?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.ListView.DrawColumnHeader?displayProperty=nameWithType>  
  
### <a name="treeview-control"></a><span data-ttu-id="69df2-159">TreeView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="69df2-159">TreeView Control</span></span>  
 <span data-ttu-id="69df2-160">Die <xref:System.Windows.Forms.TreeView> -Steuerelement ermöglicht Ihnen, einzelne Knoten im Steuerelement zu zeichnen.</span><span class="sxs-lookup"><span data-stu-id="69df2-160">The <xref:System.Windows.Forms.TreeView> control enables you to draw individual nodes in the control.</span></span>  
  
 <span data-ttu-id="69df2-161">Um nur den in den einzelnen Knoten angezeigten Text zu zeichnen, legen die `DrawMode` Eigenschaft <xref:System.Windows.Forms.TreeViewDrawMode.OwnerDrawText> und behandeln die `DrawNode` -Ereignis zum Zeichnen des Texts.</span><span class="sxs-lookup"><span data-stu-id="69df2-161">To draw only the text displayed in each node, set the `DrawMode` property to <xref:System.Windows.Forms.TreeViewDrawMode.OwnerDrawText> and handle the `DrawNode` event to draw the text.</span></span>  
  
 <span data-ttu-id="69df2-162">Um alle Elemente der einzelnen Knoten zu zeichnen, legen die `DrawMode` Eigenschaft <xref:System.Windows.Forms.TreeViewDrawMode.OwnerDrawAll> und behandeln die `DrawNode` -Ereignis zum Zeichnen Sie benötigen, wie z. B. Text, Symbole, Kontrollkästchen, Plus- und Minuszeichen sowie der Verbindungslinien zwischen die Knoten.</span><span class="sxs-lookup"><span data-stu-id="69df2-162">To draw all elements of each node, set the `DrawMode` property to <xref:System.Windows.Forms.TreeViewDrawMode.OwnerDrawAll> and handle the `DrawNode` event to draw whichever elements you need, such as text, icons, check boxes, plus and minus signs, and lines connecting the nodes.</span></span>  
  
 <span data-ttu-id="69df2-163">Weitere Informationen, einschließlich Codebeispiele, finden Sie unter den folgenden Referenzthemen:</span><span class="sxs-lookup"><span data-stu-id="69df2-163">For more information, including code examples, see the following reference topics:</span></span>  
  
- <xref:System.Windows.Forms.TreeView.DrawMode%2A?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.TreeView.DrawNode?displayProperty=nameWithType>  
  
### <a name="datagridview-control"></a><span data-ttu-id="69df2-164">DataGridView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="69df2-164">DataGridView Control</span></span>  
 <span data-ttu-id="69df2-165">Die <xref:System.Windows.Forms.DataGridView> -Steuerelement ermöglicht Ihnen, einzelne Zellen und Zeilen im Steuerelement zu zeichnen.</span><span class="sxs-lookup"><span data-stu-id="69df2-165">The <xref:System.Windows.Forms.DataGridView> control enables you to draw individual cells and rows in the control.</span></span>  
  
 <span data-ttu-id="69df2-166">Um einzelne Zellen zu zeichnen, behandeln Sie das `CellPainting`-Ereignis.</span><span class="sxs-lookup"><span data-stu-id="69df2-166">To draw individual cells, handle the `CellPainting` event.</span></span>  
  
 <span data-ttu-id="69df2-167">Um einzelne Zeilen oder Zeilenelemente zu zeichnen, behandeln Sie das `RowPrePaint`- und/oder `RowPostPaint`-Ereignis.</span><span class="sxs-lookup"><span data-stu-id="69df2-167">To draw individual rows or elements of rows, handle one or both of the `RowPrePaint` and `RowPostPaint` events.</span></span> <span data-ttu-id="69df2-168">Das `RowPrePaint`-Ereignis tritt vor dem Zeichnen der Zellen in einer Zeile und das `RowPostPaint`-Ereignis danach auf.</span><span class="sxs-lookup"><span data-stu-id="69df2-168">The `RowPrePaint` event occurs before the cells in a row are painted, and the `RowPostPaint` event occurs after the cells are painted.</span></span> <span data-ttu-id="69df2-169">Sie können beide Ereignisse und das `CellPainting`-Ereignis behandeln, um den Zeilenhintergrund, einzelne Zellen sowie den Zeilenvordergrund separat zu zeichnen. Alternativ können Sie für bestimmte Elemente spezielle Anpassungen bereitstellen und für die übrigen Zeilenelemente die Standarddarstellung verwenden.</span><span class="sxs-lookup"><span data-stu-id="69df2-169">You can handle both events and the `CellPainting` event to paint row background, individual cells, and row foreground separately, or you can provide specific customizations where you need them and use the default display for other elements of the row.</span></span>  
  
 <span data-ttu-id="69df2-170">Weitere Informationen, einschließlich Codebeispiele, finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="69df2-170">For more information, including code examples, see the following topics:</span></span>  
  
- <xref:System.Windows.Forms.DataGridView.CellPainting>  
  
- <xref:System.Windows.Forms.DataGridView.RowPrePaint>  
  
- <xref:System.Windows.Forms.DataGridView.RowPostPaint>  
  
- [<span data-ttu-id="69df2-171">Vorgehensweise: Anpassen der Darstellung von Zellen in der DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="69df2-171">How to: Customize the Appearance of Cells in the Windows Forms DataGridView Control</span></span>](customize-the-appearance-of-cells-in-the-datagrid.md)  
  
- [<span data-ttu-id="69df2-172">Vorgehensweise: Anpassen der Darstellung von Zeilen im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="69df2-172">How to: Customize the Appearance of Rows in the Windows Forms DataGridView Control</span></span>](customize-the-appearance-of-rows-in-the-datagrid.md)  
  
### <a name="toolstrip-control"></a><span data-ttu-id="69df2-173">ToolStrip-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="69df2-173">ToolStrip Control</span></span>  
 <span data-ttu-id="69df2-174"><xref:System.Windows.Forms.ToolStrip> und abgeleitete Steuerelemente ermöglichen Ihnen, alle Aspekte der steuerelementdarstellung anzupassen.</span><span class="sxs-lookup"><span data-stu-id="69df2-174"><xref:System.Windows.Forms.ToolStrip> and derived controls enable you to customize any aspect of their appearance.</span></span>  
  
 <span data-ttu-id="69df2-175">Benutzerdefiniert Rendern zu <xref:System.Windows.Forms.ToolStrip> legen Sie die Steuerelemente, die `Renderer` Eigenschaft eine <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.ToolStripManager>, <xref:System.Windows.Forms.ToolStripPanel>, oder <xref:System.Windows.Forms.ToolStripContentPanel> auf eine `ToolStripRenderer` -Objekt fest und behandeln mindestens eine der zahlreichen Zeichnungsereignisse, die von der `ToolStripRenderer` Klasse.</span><span class="sxs-lookup"><span data-stu-id="69df2-175">To provide custom rendering for <xref:System.Windows.Forms.ToolStrip> controls, set the `Renderer` property of a <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.ToolStripManager>, <xref:System.Windows.Forms.ToolStripPanel>, or <xref:System.Windows.Forms.ToolStripContentPanel> to a `ToolStripRenderer` object and handle one or more of the many drawing events provided by the `ToolStripRenderer` class.</span></span> <span data-ttu-id="69df2-176">Alternativ eine `Renderer` -Eigenschaft auf eine Instanz Ihrer eigenen Klasse abgeleitet `ToolStripRenderer`, <xref:System.Windows.Forms.ToolStripProfessionalRenderer>, oder <xref:System.Windows.Forms.ToolStripSystemRenderer> implementiert oder überschreibt bestimmte `On` *EventName* Methoden.</span><span class="sxs-lookup"><span data-stu-id="69df2-176">Alternatively, set a `Renderer` property to an instance of your own class derived from `ToolStripRenderer`, <xref:System.Windows.Forms.ToolStripProfessionalRenderer>, or <xref:System.Windows.Forms.ToolStripSystemRenderer> that implements or overrides specific `On`*EventName* methods.</span></span>  
  
 <span data-ttu-id="69df2-177">Weitere Informationen, einschließlich Codebeispiele, finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="69df2-177">For more information, including code examples, see the following topics:</span></span>  
  
- <xref:System.Windows.Forms.ToolStripRenderer>  
  
- [<span data-ttu-id="69df2-178">Vorgehensweise: Erstellen und Festlegen eines benutzerdefinierten Renderers für das ToolStrip-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="69df2-178">How to: Create and Set a Custom Renderer for the ToolStrip Control in Windows Forms</span></span>](create-and-set-a-custom-renderer-for-the-toolstrip-control-in-wf.md)  
  
- [<span data-ttu-id="69df2-179">Vorgehensweise: Benutzerdefiniertes Zeichnen eines ToolStrip-Steuerelements</span><span class="sxs-lookup"><span data-stu-id="69df2-179">How to: Custom Draw a ToolStrip Control</span></span>](how-to-custom-draw-a-toolstrip-control.md)  
  
## <a name="see-also"></a><span data-ttu-id="69df2-180">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="69df2-180">See also</span></span>

- [<span data-ttu-id="69df2-181">Windows Forms-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="69df2-181">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
