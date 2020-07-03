---
ms.openlocfilehash: 00f89e6ae49982917fa7591c3283adec3947eed2
ms.sourcegitcommit: 63bb83322814f5e5e5c5b69939b14a3139a6ca7e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/25/2020
ms.locfileid: "85365644"
---
### <a name="winforms-methods-now-throw-argumentnullexception"></a><span data-ttu-id="fbf55-101">WinForms-Methoden lösen jetzt ArgumentNullException aus</span><span class="sxs-lookup"><span data-stu-id="fbf55-101">WinForms methods now throw ArgumentNullException</span></span>

<span data-ttu-id="fbf55-102">Einige Windows Forms-Methoden lösen nun eine <xref:System.ArgumentNullException>-Ausnahme für NULL-Argumente aus, für die sie zuvor eine <xref:System.NullReferenceException>-Ausnahme ausgelöst haben.</span><span class="sxs-lookup"><span data-stu-id="fbf55-102">Some Windows Forms methods now throw an <xref:System.ArgumentNullException> for null arguments, where previously they threw a <xref:System.NullReferenceException>.</span></span>

#### <a name="change-description"></a><span data-ttu-id="fbf55-103">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="fbf55-103">Change description</span></span>

<span data-ttu-id="fbf55-104">Zuvor haben bestimmte Windows Forms-Methoden eine <xref:System.NullReferenceException>-Ausnahme ausgelöst, wenn ein Argument mit dem Wert NULL übergeben wurde.</span><span class="sxs-lookup"><span data-stu-id="fbf55-104">Previously, certain Windows Forms methods threw a <xref:System.NullReferenceException> if passed an argument that was null.</span></span> <span data-ttu-id="fbf55-105">Ab .NET 5.0 lösen diese Methoden stattdessen eine <xref:System.ArgumentNullException>-Ausnahme für NULL-Argumente aus.</span><span class="sxs-lookup"><span data-stu-id="fbf55-105">Starting in .NET 5.0, these methods now throw an <xref:System.ArgumentNullException> for null arguments, instead.</span></span>

<span data-ttu-id="fbf55-106">Das Auslösen einer <xref:System.ArgumentNullException>-Ausnahme entspricht dem Verhalten der .NET Runtime.</span><span class="sxs-lookup"><span data-stu-id="fbf55-106">Throwing an <xref:System.ArgumentNullException> conforms to the behavior of the .NET runtime.</span></span> <span data-ttu-id="fbf55-107">Außerdem wird die Debugfunktion verbessert, indem ausdrücklich kommuniziert wird, dass ein Argument den Wert NULL aufweist und welches Argument betroffen ist.</span><span class="sxs-lookup"><span data-stu-id="fbf55-107">It also improves the debugging experience by clearly communicating that an argument is null and which argument it is.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="fbf55-108">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="fbf55-108">Version introduced</span></span>

<span data-ttu-id="fbf55-109">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="fbf55-109">.NET 5.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="fbf55-110">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="fbf55-110">Recommended action</span></span>

<span data-ttu-id="fbf55-111">Wenn Sie eine dieser Methoden aufrufen und Ihr Code <xref:System.NullReferenceException> für NULL-Argumente abfängt, sollte stattdessen <xref:System.ArgumentNullException> abgefangen werden.</span><span class="sxs-lookup"><span data-stu-id="fbf55-111">If you call any of these methods and your code currently catches a <xref:System.NullReferenceException> for null arguments, catch an <xref:System.ArgumentNullException> instead.</span></span> <span data-ttu-id="fbf55-112">Außerdem sollten Sie ein Update für den Code in Betracht ziehen, um die Übergabe von NULL-Argumenten an die aufgeführten Methoden zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="fbf55-112">In addition, consider updating the code to prevent passing null arguments to the listed methods.</span></span>

#### <a name="category"></a><span data-ttu-id="fbf55-113">Kategorie</span><span class="sxs-lookup"><span data-stu-id="fbf55-113">Category</span></span>

<span data-ttu-id="fbf55-114">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="fbf55-114">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="fbf55-115">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="fbf55-115">Affected APIs</span></span>

<span data-ttu-id="fbf55-116">In der folgenden Tabelle sind die betroffenen Methoden und Parameter aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="fbf55-116">The following table lists the affected methods and parameters:</span></span>

> [!div class="mx-tdBreakAll"]
> | <span data-ttu-id="fbf55-117">Methode</span><span class="sxs-lookup"><span data-stu-id="fbf55-117">Method</span></span> | <span data-ttu-id="fbf55-118">Parametername</span><span class="sxs-lookup"><span data-stu-id="fbf55-118">Parameter name</span></span> | <span data-ttu-id="fbf55-119">Hinzugefügte Version</span><span class="sxs-lookup"><span data-stu-id="fbf55-119">Version added</span></span> |
> |-|-|-|
> | <xref:System.Windows.Forms.Control.ControlCollection.%23ctor(System.Windows.Forms.Control)> | `owner` | <span data-ttu-id="fbf55-120">5.0 Preview 1</span><span class="sxs-lookup"><span data-stu-id="fbf55-120">5.0 Preview 1</span></span> |
> | <xref:System.Windows.Forms.TabControl.GetToolTipText(System.Object)?displayProperty=nameWithType> | `item` | <span data-ttu-id="fbf55-121">5.0 Preview 1</span><span class="sxs-lookup"><span data-stu-id="fbf55-121">5.0 Preview 1</span></span> |
> | <xref:System.Windows.Forms.TableLayoutControlCollection.%23ctor(System.Windows.Forms.TableLayoutPanel)> | `container` | <span data-ttu-id="fbf55-122">5.0 Preview 1</span><span class="sxs-lookup"><span data-stu-id="fbf55-122">5.0 Preview 1</span></span> |
> | <xref:System.Windows.Forms.ToolStripRenderer.OnRenderArrow(System.Windows.Forms.ToolStripArrowRenderEventArgs)?displayProperty=nameWithType> | `e` | <span data-ttu-id="fbf55-123">5.0 Preview 1</span><span class="sxs-lookup"><span data-stu-id="fbf55-123">5.0 Preview 1</span></span> |
> | <xref:System.Windows.Forms.ToolStripRenderer.OnRenderItemCheck(System.Windows.Forms.ToolStripItemImageRenderEventArgs)?displayProperty=nameWithType> | `e` | <span data-ttu-id="fbf55-124">5.0 Preview 1</span><span class="sxs-lookup"><span data-stu-id="fbf55-124">5.0 Preview 1</span></span> |
> | <xref:System.Windows.Forms.ToolStripRenderer.OnRenderItemImage(System.Windows.Forms.ToolStripItemImageRenderEventArgs)?displayProperty=nameWithType> | `e` | <span data-ttu-id="fbf55-125">5.0 Preview 1</span><span class="sxs-lookup"><span data-stu-id="fbf55-125">5.0 Preview 1</span></span> |
> | <xref:System.Windows.Forms.ToolStripRenderer.OnRenderItemText(System.Windows.Forms.ToolStripItemTextRenderEventArgs)?displayProperty=nameWithType> | `e` | <span data-ttu-id="fbf55-126">5.0 Preview 1</span><span class="sxs-lookup"><span data-stu-id="fbf55-126">5.0 Preview 1</span></span> |
> | <xref:System.Windows.Forms.ToolStripRenderer.OnRenderStatusStripSizingGrip(System.Windows.Forms.ToolStripRenderEventArgs)?displayProperty=nameWithType> > | `e` | <span data-ttu-id="fbf55-127">5.0 Preview 1</span><span class="sxs-lookup"><span data-stu-id="fbf55-127">5.0 Preview 1</span></span> |
> | <xref:System.Windows.Forms.DataGridViewComboBoxEditingControl.ApplyCellStyleToEditingControl(System.Windows.Forms.DataGridViewCellStyle)?displayProperty=nameWithType> | `dataGridViewCellStyle` | <span data-ttu-id="fbf55-128">5.0 Preview 2</span><span class="sxs-lookup"><span data-stu-id="fbf55-128">5.0 Preview 2</span></span> |
> | <xref:System.Windows.Forms.RichTextBox.LoadFile(System.IO.Stream,System.Windows.Forms.RichTextBoxStreamType)?displayProperty=nameWithType> | `data` | <span data-ttu-id="fbf55-129">5.0 Preview 2</span><span class="sxs-lookup"><span data-stu-id="fbf55-129">5.0 Preview 2</span></span> |
> | <xref:System.Windows.Forms.ListBox.IntegerCollection.%23ctor(System.Windows.Forms.ListBox)> | `owner` | <span data-ttu-id="fbf55-130">5.0 Vorschau 5</span><span class="sxs-lookup"><span data-stu-id="fbf55-130">5.0 Preview 5</span></span> |
> | <xref:System.Windows.Forms.ListBox.IntegerCollection.CopyTo(System.Array,System.Int32)?displayProperty=nameWithType> | `destination` | <span data-ttu-id="fbf55-131">5.0 Vorschau 5</span><span class="sxs-lookup"><span data-stu-id="fbf55-131">5.0 Preview 5</span></span> |
> | <xref:System.Windows.Forms.ListViewGroup.System%23Runtime%23Serialization%23ISerializable%23GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | `info` | <span data-ttu-id="fbf55-132">5.0 Vorschau 5</span><span class="sxs-lookup"><span data-stu-id="fbf55-132">5.0 Preview 5</span></span> |
> | <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer.%23ctor(System.String,System.Int32,System.Int32)> | `className` | <span data-ttu-id="fbf55-133">5.0 Vorschau 5</span><span class="sxs-lookup"><span data-stu-id="fbf55-133">5.0 Preview 5</span></span> |
> | <xref:System.Windows.Forms.ListBox.ObjectCollection.%23ctor(System.Windows.Forms.ListBox)> | `owner` | <span data-ttu-id="fbf55-134">Version 5.0 Vorschau 6</span><span class="sxs-lookup"><span data-stu-id="fbf55-134">5.0 Preview 6</span></span> |
> | <xref:System.Windows.Forms.ListBox.ObjectCollection.%23ctor(System.Windows.Forms.ListBox,System.Object[])> | <span data-ttu-id="fbf55-135">`owner`, `value`</span><span class="sxs-lookup"><span data-stu-id="fbf55-135">`owner`, `value`</span></span> | <span data-ttu-id="fbf55-136">Version 5.0 Vorschau 6</span><span class="sxs-lookup"><span data-stu-id="fbf55-136">5.0 Preview 6</span></span> |
> | <xref:System.Windows.Forms.ListBox.ObjectCollection.%23ctor(System.Windows.Forms.ListBox,System.Windows.Forms.ListBox.ObjectCollection)> | <span data-ttu-id="fbf55-137">`owner`, `value`</span><span class="sxs-lookup"><span data-stu-id="fbf55-137">`owner`, `value`</span></span> | <span data-ttu-id="fbf55-138">Version 5.0 Vorschau 6</span><span class="sxs-lookup"><span data-stu-id="fbf55-138">5.0 Preview 6</span></span> |
> | <xref:System.Windows.Forms.ListBox.ObjectCollection.AddRange(System.Object[])?displayProperty=nameWithType> | `items` | <span data-ttu-id="fbf55-139">Version 5.0 Vorschau 6</span><span class="sxs-lookup"><span data-stu-id="fbf55-139">5.0 Preview 6</span></span> |
> | <xref:System.Windows.Forms.ListBox.ObjectCollection.AddRange(System.Windows.Forms.ListBox.ObjectCollection)?displayProperty=nameWithType> | `value` | <span data-ttu-id="fbf55-140">Version 5.0 Vorschau 6</span><span class="sxs-lookup"><span data-stu-id="fbf55-140">5.0 Preview 6</span></span> |
> | <xref:System.Windows.Forms.ListBox.ObjectCollection.CopyTo(System.Object[],System.Int32)?displayProperty=nameWithType> | `destination` | <span data-ttu-id="fbf55-141">Version 5.0 Vorschau 6</span><span class="sxs-lookup"><span data-stu-id="fbf55-141">5.0 Preview 6</span></span> |
> | <xref:System.Windows.Forms.ListBox.ObjectCollection.System%23Collections%23ICollection%23CopyTo(System.Array,System.Int32)?displayProperty=nameWithType> | <span data-ttu-id="fbf55-142">`destination`q\`</span><span class="sxs-lookup"><span data-stu-id="fbf55-142">`destination`q\`</span></span> | <span data-ttu-id="fbf55-143">Version 5.0 Vorschau 6</span><span class="sxs-lookup"><span data-stu-id="fbf55-143">5.0 Preview 6</span></span> |

<!-- 

#### Affected APIs

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
- `M:System.Windows.Forms.ListViewGroup.System%23Runtime%23Serialization%23ISerializable%23GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)`
- `M:System.Windows.Forms.VisualStyles.VisualStyleRenderer.%23ctor(System.String,System.Int32,System.Int32)`
- `M:System.Windows.Forms.ListBox.IntegerCollection.%23ctor(System.Windows.Forms.ListBox)`
- `M:System.Windows.Forms.ListBox.IntegerCollection.CopyTo(System.Array,System.Int32)`
- `M:System.Windows.Forms.ListBox.ObjectCollection.%23ctor(System.Windows.Forms.ListBox)`
- `M:System.Windows.Forms.ListBox.ObjectCollection.%23ctor(System.Windows.Forms.ListBox,System.Object[])`
- `M:System.Windows.Forms.ListBox.ObjectCollection.%23ctor(System.Windows.Forms.ListBox,System.Windows.Forms.ListBox.ObjectCollection)`
- `M:System.Windows.Forms.ListBox.ObjectCollection.AddRange(System.Object[])`
- `M:System.Windows.Forms.ListBox.ObjectCollection.AddRange(System.Windows.Forms.ListBox.ObjectCollection)`
- `M:System.Windows.Forms.ListBox.ObjectCollection.CopyTo(System.Object[],System.Int32)`
- `M:System.Windows.Forms.ListBox.ObjectCollection.System%23Collections%23ICollection%23CopyTo(System.Array,System.Int32)`

-->
