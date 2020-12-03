---
title: 'Breaking Change: WinForms-Methoden lösen jetzt ArgumentNullException aus'
description: Hier erfahren Sie mehr über den Breaking Change in .NET 5.0, durch den einige Windows Forms-Methoden nun eine ArgumentNullException-Ausnahme für NULL-Argumente auslösen.
ms.date: 09/18/2020
ms.openlocfilehash: 77280827d44b0e58533339a09357d518a0bfe508
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759512"
---
# <a name="winforms-methods-now-throw-argumentnullexception"></a><span data-ttu-id="5059d-103">WinForms-Methoden lösen jetzt ArgumentNullException aus</span><span class="sxs-lookup"><span data-stu-id="5059d-103">WinForms methods now throw ArgumentNullException</span></span>

<span data-ttu-id="5059d-104">Einige Windows Forms-Methoden lösen nun eine <xref:System.ArgumentNullException>-Ausnahme für NULL-Argumente aus, für die sie zuvor eine <xref:System.NullReferenceException>-Ausnahme ausgelöst haben.</span><span class="sxs-lookup"><span data-stu-id="5059d-104">Some Windows Forms methods now throw an <xref:System.ArgumentNullException> for null arguments, where previously they threw a <xref:System.NullReferenceException>.</span></span>

## <a name="change-description"></a><span data-ttu-id="5059d-105">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="5059d-105">Change description</span></span>

<span data-ttu-id="5059d-106">Zuvor haben bestimmte Windows Forms-Methoden eine <xref:System.NullReferenceException>-Ausnahme ausgelöst, wenn ein Argument mit dem Wert NULL übergeben wurde.</span><span class="sxs-lookup"><span data-stu-id="5059d-106">Previously, certain Windows Forms methods threw a <xref:System.NullReferenceException> if passed an argument that was null.</span></span> <span data-ttu-id="5059d-107">Ab .NET 5.0 lösen diese Methoden stattdessen eine <xref:System.ArgumentNullException>-Ausnahme für NULL-Argumente aus.</span><span class="sxs-lookup"><span data-stu-id="5059d-107">Starting in .NET 5.0, these methods now throw an <xref:System.ArgumentNullException> for null arguments, instead.</span></span>

<span data-ttu-id="5059d-108">Das Auslösen einer <xref:System.ArgumentNullException>-Ausnahme entspricht dem Verhalten der .NET Runtime.</span><span class="sxs-lookup"><span data-stu-id="5059d-108">Throwing an <xref:System.ArgumentNullException> conforms to the behavior of the .NET runtime.</span></span> <span data-ttu-id="5059d-109">Außerdem wird die Debugfunktion verbessert, indem ausdrücklich kommuniziert wird, dass ein Argument den Wert NULL aufweist und welches Argument betroffen ist.</span><span class="sxs-lookup"><span data-stu-id="5059d-109">It also improves the debugging experience by clearly communicating that an argument is null and which argument it is.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="5059d-110">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="5059d-110">Version introduced</span></span>

<span data-ttu-id="5059d-111">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="5059d-111">.NET 5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="5059d-112">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="5059d-112">Recommended action</span></span>

<span data-ttu-id="5059d-113">Wenn Sie eine dieser Methoden aufrufen und Ihr Code <xref:System.NullReferenceException> für NULL-Argumente abfängt, sollte stattdessen <xref:System.ArgumentNullException> abgefangen werden.</span><span class="sxs-lookup"><span data-stu-id="5059d-113">If you call any of these methods and your code currently catches a <xref:System.NullReferenceException> for null arguments, catch an <xref:System.ArgumentNullException> instead.</span></span> <span data-ttu-id="5059d-114">Außerdem sollten Sie ein Update für den Code in Betracht ziehen, um die Übergabe von NULL-Argumenten an die aufgeführten Methoden zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="5059d-114">In addition, consider updating the code to prevent passing null arguments to the listed methods.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="5059d-115">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="5059d-115">Affected APIs</span></span>

<span data-ttu-id="5059d-116">In der folgenden Tabelle sind die betroffenen Methoden und Parameter aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="5059d-116">The following table lists the affected methods and parameters:</span></span>

> [!div class="mx-tdBreakAll"]
> | <span data-ttu-id="5059d-117">Methode</span><span class="sxs-lookup"><span data-stu-id="5059d-117">Method</span></span> | <span data-ttu-id="5059d-118">Parametername</span><span class="sxs-lookup"><span data-stu-id="5059d-118">Parameter name</span></span> | <span data-ttu-id="5059d-119">Hinzugefügte Version</span><span class="sxs-lookup"><span data-stu-id="5059d-119">Version added</span></span> |
> |-|-|-|
> | <xref:System.Windows.Forms.Control.ControlCollection.%23ctor(System.Windows.Forms.Control)> | `owner` | <span data-ttu-id="5059d-120">Vorschauversion 1</span><span class="sxs-lookup"><span data-stu-id="5059d-120">Preview 1</span></span> |
> | <xref:System.Windows.Forms.TabControl.GetToolTipText(System.Object)?displayProperty=nameWithType> | `item` | <span data-ttu-id="5059d-121">Vorschauversion 1</span><span class="sxs-lookup"><span data-stu-id="5059d-121">Preview 1</span></span> |
> | <xref:System.Windows.Forms.TableLayoutControlCollection.%23ctor(System.Windows.Forms.TableLayoutPanel)> | `container` | <span data-ttu-id="5059d-122">Vorschauversion 1</span><span class="sxs-lookup"><span data-stu-id="5059d-122">Preview 1</span></span> |
> | <xref:System.Windows.Forms.ToolStripRenderer.OnRenderArrow(System.Windows.Forms.ToolStripArrowRenderEventArgs)?displayProperty=nameWithType> | `e` | <span data-ttu-id="5059d-123">Vorschauversion 1</span><span class="sxs-lookup"><span data-stu-id="5059d-123">Preview 1</span></span> |
> | <xref:System.Windows.Forms.ToolStripRenderer.OnRenderItemCheck(System.Windows.Forms.ToolStripItemImageRenderEventArgs)?displayProperty=nameWithType> | `e` | <span data-ttu-id="5059d-124">Vorschauversion 1</span><span class="sxs-lookup"><span data-stu-id="5059d-124">Preview 1</span></span> |
> | <xref:System.Windows.Forms.ToolStripRenderer.OnRenderItemImage(System.Windows.Forms.ToolStripItemImageRenderEventArgs)?displayProperty=nameWithType> | `e` | <span data-ttu-id="5059d-125">Vorschauversion 1</span><span class="sxs-lookup"><span data-stu-id="5059d-125">Preview 1</span></span> |
> | <xref:System.Windows.Forms.ToolStripRenderer.OnRenderItemText(System.Windows.Forms.ToolStripItemTextRenderEventArgs)?displayProperty=nameWithType> | `e` | <span data-ttu-id="5059d-126">Vorschauversion 1</span><span class="sxs-lookup"><span data-stu-id="5059d-126">Preview 1</span></span> |
> | <xref:System.Windows.Forms.ToolStripRenderer.OnRenderStatusStripSizingGrip(System.Windows.Forms.ToolStripRenderEventArgs)?displayProperty=nameWithType> > | `e` | <span data-ttu-id="5059d-127">Vorschauversion 1</span><span class="sxs-lookup"><span data-stu-id="5059d-127">Preview 1</span></span> |
> | <xref:System.Windows.Forms.DataGridViewComboBoxEditingControl.ApplyCellStyleToEditingControl(System.Windows.Forms.DataGridViewCellStyle)?displayProperty=nameWithType> | `dataGridViewCellStyle` | <span data-ttu-id="5059d-128">Vorschau 2</span><span class="sxs-lookup"><span data-stu-id="5059d-128">Preview 2</span></span> |
> | <xref:System.Windows.Forms.RichTextBox.LoadFile(System.IO.Stream,System.Windows.Forms.RichTextBoxStreamType)?displayProperty=nameWithType> | `data` | <span data-ttu-id="5059d-129">Vorschau 2</span><span class="sxs-lookup"><span data-stu-id="5059d-129">Preview 2</span></span> |
> | <xref:System.Windows.Forms.ListBox.IntegerCollection.%23ctor(System.Windows.Forms.ListBox)> | `owner` | <span data-ttu-id="5059d-130">Preview 5</span><span class="sxs-lookup"><span data-stu-id="5059d-130">Preview 5</span></span> |
> | <xref:System.Windows.Forms.ListBox.IntegerCollection.CopyTo(System.Array,System.Int32)?displayProperty=nameWithType> | `destination` | <span data-ttu-id="5059d-131">Preview 5</span><span class="sxs-lookup"><span data-stu-id="5059d-131">Preview 5</span></span> |
> | <xref:System.Windows.Forms.ListViewGroup.System%23Runtime%23Serialization%23ISerializable%23GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | `info` | <span data-ttu-id="5059d-132">Preview 5</span><span class="sxs-lookup"><span data-stu-id="5059d-132">Preview 5</span></span> |
> | <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer.%23ctor(System.String,System.Int32,System.Int32)> | `className` | <span data-ttu-id="5059d-133">Preview 5</span><span class="sxs-lookup"><span data-stu-id="5059d-133">Preview 5</span></span> |
> | <xref:System.Windows.Forms.ListBox.ObjectCollection.%23ctor(System.Windows.Forms.ListBox)> | `owner` | <span data-ttu-id="5059d-134">Vorschau 6</span><span class="sxs-lookup"><span data-stu-id="5059d-134">Preview 6</span></span> |
> | <xref:System.Windows.Forms.ListBox.ObjectCollection.%23ctor(System.Windows.Forms.ListBox,System.Object[])> | <span data-ttu-id="5059d-135">`owner`, `value`</span><span class="sxs-lookup"><span data-stu-id="5059d-135">`owner`, `value`</span></span> | <span data-ttu-id="5059d-136">Vorschau 6</span><span class="sxs-lookup"><span data-stu-id="5059d-136">Preview 6</span></span> |
> | <xref:System.Windows.Forms.ListBox.ObjectCollection.%23ctor(System.Windows.Forms.ListBox,System.Windows.Forms.ListBox.ObjectCollection)> | <span data-ttu-id="5059d-137">`owner`, `value`</span><span class="sxs-lookup"><span data-stu-id="5059d-137">`owner`, `value`</span></span> | <span data-ttu-id="5059d-138">Vorschau 6</span><span class="sxs-lookup"><span data-stu-id="5059d-138">Preview 6</span></span> |
> | <xref:System.Windows.Forms.ListBox.ObjectCollection.AddRange(System.Object[])?displayProperty=nameWithType> | `items` | <span data-ttu-id="5059d-139">Vorschau 6</span><span class="sxs-lookup"><span data-stu-id="5059d-139">Preview 6</span></span> |
> | <xref:System.Windows.Forms.ListBox.ObjectCollection.AddRange(System.Windows.Forms.ListBox.ObjectCollection)?displayProperty=nameWithType> | `value` | <span data-ttu-id="5059d-140">Vorschau 6</span><span class="sxs-lookup"><span data-stu-id="5059d-140">Preview 6</span></span> |
> | <xref:System.Windows.Forms.ListBox.ObjectCollection.CopyTo(System.Object[],System.Int32)?displayProperty=nameWithType> | `destination` | <span data-ttu-id="5059d-141">Vorschau 6</span><span class="sxs-lookup"><span data-stu-id="5059d-141">Preview 6</span></span> |
> | <xref:System.Windows.Forms.ListBox.ObjectCollection.System%23Collections%23ICollection%23CopyTo(System.Array,System.Int32)?displayProperty=nameWithType> | `destination` | <span data-ttu-id="5059d-142">Vorschau 6</span><span class="sxs-lookup"><span data-stu-id="5059d-142">Preview 6</span></span> |
> | <xref:System.Windows.Forms.ListView.SelectedIndexCollection.%23ctor(System.Windows.Forms.ListView)> | `owner` | <span data-ttu-id="5059d-143">Preview 7</span><span class="sxs-lookup"><span data-stu-id="5059d-143">Preview 7</span></span> |
> | <xref:System.Windows.Forms.TreeNodeCollection.Find(System.String,System.Boolean)?displayProperty=nameWithType> | <span data-ttu-id="5059d-144">`key` hat den Wert `null` oder ist leer.</span><span class="sxs-lookup"><span data-stu-id="5059d-144">`key` is `null` or empty</span></span> | <span data-ttu-id="5059d-145">Preview 8</span><span class="sxs-lookup"><span data-stu-id="5059d-145">Preview 8</span></span> |
> | <xref:System.Windows.Forms.ListView.ListViewItemCollection.Find(System.String,System.Boolean)?displayProperty=nameWithType> | <span data-ttu-id="5059d-146">`key` hat den Wert `null` oder ist leer.</span><span class="sxs-lookup"><span data-stu-id="5059d-146">`key` is `null` or empty</span></span> | <span data-ttu-id="5059d-147">RC1</span><span class="sxs-lookup"><span data-stu-id="5059d-147">RC1</span></span> |
> | <xref:System.Windows.Forms.ScrollableControl.OnPaintBackground(System.Windows.Forms.PaintEventArgs)?displayProperty=nameWithType> | `e` | <span data-ttu-id="5059d-148">RC1</span><span class="sxs-lookup"><span data-stu-id="5059d-148">RC1</span></span> |

<!--

### Affected APIs

- `M:System.Windows.Forms.Control.ControlCollection.#ctor(System.Windows.Forms.Control)`
- `M:System.Windows.Forms.TabControl.GetToolTipText(System.Object)`
- `M:System.Windows.Forms.TableLayoutControlCollection.#ctor(System.Windows.Forms.TableLayoutPanel)`
- `M:System.Windows.Forms.ToolStripRenderer.OnRenderArrow(System.Windows.Forms.ToolStripArrowRenderEventArgs)`
- `M:System.Windows.Forms.ToolStripRenderer.OnRenderItemImage(System.Windows.Forms.ToolStripItemImageRenderEventArgs)`
- `M:System.Windows.Forms.ToolStripRenderer.OnRenderItemCheck(System.Windows.Forms.ToolStripItemImageRenderEventArgs)`
- `M:System.Windows.Forms.ToolStripRenderer.OnRenderItemText(System.Windows.Forms.ToolStripItemTextRenderEventArgs)`
- `M:System.Windows.Forms.ToolStripRenderer.OnRenderStatusStripSizingGrip(System.Windows.Forms.ToolStripRenderEventArgs)`
- `M:System.Windows.Forms.DataGridViewComboBoxEditingControl.ApplyCellStyleToEditingControl(System.Windows.Forms.DataGridViewCellStyle)`
- `M:System.Windows.Forms.RichTextBox.LoadFile(System.IO.Stream,System.Windows.Forms.RichTextBoxStreamType)`
- `M:System.Windows.Forms.ListViewGroup.System#Runtime#Serialization#ISerializable#GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)`
- `M:System.Windows.Forms.VisualStyles.VisualStyleRenderer.#ctor(System.String,System.Int32,System.Int32)`
- `M:System.Windows.Forms.ListBox.IntegerCollection.#ctor(System.Windows.Forms.ListBox)`
- `M:System.Windows.Forms.ListBox.IntegerCollection.CopyTo(System.Array,System.Int32)`
- `M:System.Windows.Forms.ListBox.ObjectCollection.#ctor(System.Windows.Forms.ListBox)`
- `M:System.Windows.Forms.ListBox.ObjectCollection.#ctor(System.Windows.Forms.ListBox,System.Object[])`
- `M:System.Windows.Forms.ListBox.ObjectCollection.#ctor(System.Windows.Forms.ListBox,System.Windows.Forms.ListBox.ObjectCollection)`
- `M:System.Windows.Forms.ListBox.ObjectCollection.AddRange(System.Object[])`
- `M:System.Windows.Forms.ListBox.ObjectCollection.AddRange(System.Windows.Forms.ListBox.ObjectCollection)`
- `M:System.Windows.Forms.ListBox.ObjectCollection.CopyTo(System.Object[],System.Int32)`
- `M:System.Windows.Forms.ListBox.ObjectCollection.System#Collections#ICollection#CopyTo(System.Array,System.Int32)`
- `M:System.Windows.Forms.ListView.SelectedIndexCollection.#ctor(System.Windows.Forms.ListView)`
- `M:System.Windows.Forms.TreeNodeCollection.Find(System.String,System.Boolean)`
- `M:System.Windows.Forms.ListView.ListViewItemCollection.Find(System.String,System.Boolean)`
- `M:System.Windows.Forms.ScrollableControl.OnPaintBackground(System.Windows.Forms.PaintEventArgs)`

### Category

Windows Forms

-->
