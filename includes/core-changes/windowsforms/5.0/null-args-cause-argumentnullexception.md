---
ms.openlocfilehash: be496cd586f149ca9fd851d6aa00186e8080c66f
ms.sourcegitcommit: 7137e12f54c4e83a94ae43ec320f8cf59c1772ea
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/10/2020
ms.locfileid: "84680270"
---
### <a name="winforms-methods-now-throw-argumentnullexception"></a><span data-ttu-id="d1231-101">WinForms-Methoden lösen jetzt ArgumentNullException aus</span><span class="sxs-lookup"><span data-stu-id="d1231-101">WinForms methods now throw ArgumentNullException</span></span>

<span data-ttu-id="d1231-102">Einige Windows Forms-Methoden lösen nun eine <xref:System.ArgumentNullException>-Ausnahme für NULL-Argumente aus, für die sie zuvor eine <xref:System.NullReferenceException>-Ausnahme ausgelöst haben.</span><span class="sxs-lookup"><span data-stu-id="d1231-102">Some Windows Forms methods now throw an <xref:System.ArgumentNullException> for null arguments, where previously they threw a <xref:System.NullReferenceException>.</span></span>

#### <a name="change-description"></a><span data-ttu-id="d1231-103">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="d1231-103">Change description</span></span>

<span data-ttu-id="d1231-104">Zuvor haben bestimmte Windows Forms-Methoden eine <xref:System.NullReferenceException>-Ausnahme ausgelöst, wenn ein Argument mit dem Wert NULL übergeben wurde.</span><span class="sxs-lookup"><span data-stu-id="d1231-104">Previously, certain Windows Forms methods threw a <xref:System.NullReferenceException> if passed an argument that was null.</span></span> <span data-ttu-id="d1231-105">Ab .NET 5.0 lösen diese Methoden stattdessen eine <xref:System.ArgumentNullException>-Ausnahme für NULL-Argumente aus.</span><span class="sxs-lookup"><span data-stu-id="d1231-105">Starting in .NET 5.0, these methods now throw an <xref:System.ArgumentNullException> for null arguments, instead.</span></span>

<span data-ttu-id="d1231-106">Das Auslösen einer <xref:System.ArgumentNullException>-Ausnahme entspricht dem Verhalten der .NET Runtime.</span><span class="sxs-lookup"><span data-stu-id="d1231-106">Throwing an <xref:System.ArgumentNullException> conforms to the behavior of the .NET runtime.</span></span> <span data-ttu-id="d1231-107">Außerdem wird die Debugfunktion verbessert, indem ausdrücklich kommuniziert wird, dass ein Argument den Wert NULL aufweist und welches Argument betroffen ist.</span><span class="sxs-lookup"><span data-stu-id="d1231-107">It also improves the debugging experience by clearly communicating that an argument is null and which argument it is.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="d1231-108">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="d1231-108">Version introduced</span></span>

<span data-ttu-id="d1231-109">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="d1231-109">.NET 5.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="d1231-110">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="d1231-110">Recommended action</span></span>

<span data-ttu-id="d1231-111">Wenn Sie eine dieser Methoden aufrufen und Ihr Code <xref:System.NullReferenceException> für NULL-Argumente abfängt, sollte stattdessen <xref:System.ArgumentNullException> abgefangen werden.</span><span class="sxs-lookup"><span data-stu-id="d1231-111">If you call any of these methods and your code currently catches a <xref:System.NullReferenceException> for null arguments, catch an <xref:System.ArgumentNullException> instead.</span></span> <span data-ttu-id="d1231-112">Außerdem sollten Sie ein Update für den Code in Betracht ziehen, um die Übergabe von NULL-Argumenten an die aufgeführten Methoden zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="d1231-112">In addition, consider updating the code to prevent passing null arguments to the listed methods.</span></span>

#### <a name="category"></a><span data-ttu-id="d1231-113">Kategorie</span><span class="sxs-lookup"><span data-stu-id="d1231-113">Category</span></span>

<span data-ttu-id="d1231-114">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d1231-114">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="d1231-115">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="d1231-115">Affected APIs</span></span>

<span data-ttu-id="d1231-116">In der folgenden Tabelle sind die betroffenen Methoden und Parameter aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="d1231-116">The following table lists the affected methods and parameters:</span></span>

> [!div class="mx-tdBreakAll"]
> | <span data-ttu-id="d1231-117">Methode</span><span class="sxs-lookup"><span data-stu-id="d1231-117">Method</span></span> | <span data-ttu-id="d1231-118">Parametername</span><span class="sxs-lookup"><span data-stu-id="d1231-118">Parameter name</span></span> | <span data-ttu-id="d1231-119">Hinzugefügte Version</span><span class="sxs-lookup"><span data-stu-id="d1231-119">Version added</span></span> |
> |-|-|-|
> | <xref:System.Windows.Forms.Control.ControlCollection.%23ctor(System.Windows.Forms.Control)> | `owner` | <span data-ttu-id="d1231-120">5.0 Preview 1</span><span class="sxs-lookup"><span data-stu-id="d1231-120">5.0 Preview 1</span></span> |
> | <xref:System.Windows.Forms.TabControl.GetToolTipText(System.Object)?displayProperty=nameWithType> | `item` | <span data-ttu-id="d1231-121">5.0 Preview 1</span><span class="sxs-lookup"><span data-stu-id="d1231-121">5.0 Preview 1</span></span> |
> | <xref:System.Windows.Forms.TableLayoutControlCollection.%23ctor(System.Windows.Forms.TableLayoutPanel)> | `container` | <span data-ttu-id="d1231-122">5.0 Preview 1</span><span class="sxs-lookup"><span data-stu-id="d1231-122">5.0 Preview 1</span></span> |
> | <xref:System.Windows.Forms.ToolStripRenderer.OnRenderArrow(System.Windows.Forms.ToolStripArrowRenderEventArgs)?displayProperty=nameWithType> | `e` | <span data-ttu-id="d1231-123">5.0 Preview 1</span><span class="sxs-lookup"><span data-stu-id="d1231-123">5.0 Preview 1</span></span> |
> | <xref:System.Windows.Forms.ToolStripRenderer.OnRenderItemCheck(System.Windows.Forms.ToolStripItemImageRenderEventArgs)?displayProperty=nameWithType> | `e` | <span data-ttu-id="d1231-124">5.0 Preview 1</span><span class="sxs-lookup"><span data-stu-id="d1231-124">5.0 Preview 1</span></span> |
> | <xref:System.Windows.Forms.ToolStripRenderer.OnRenderItemImage(System.Windows.Forms.ToolStripItemImageRenderEventArgs)?displayProperty=nameWithType> | `e` | <span data-ttu-id="d1231-125">5.0 Preview 1</span><span class="sxs-lookup"><span data-stu-id="d1231-125">5.0 Preview 1</span></span> |
> | <xref:System.Windows.Forms.ToolStripRenderer.OnRenderItemText(System.Windows.Forms.ToolStripItemTextRenderEventArgs)?displayProperty=nameWithType> | `e` | <span data-ttu-id="d1231-126">5.0 Preview 1</span><span class="sxs-lookup"><span data-stu-id="d1231-126">5.0 Preview 1</span></span> |
> | <xref:System.Windows.Forms.ToolStripRenderer.OnRenderStatusStripSizingGrip(System.Windows.Forms.ToolStripRenderEventArgs)?displayProperty=nameWithType> > | `e` | <span data-ttu-id="d1231-127">5.0 Preview 1</span><span class="sxs-lookup"><span data-stu-id="d1231-127">5.0 Preview 1</span></span> |
> | <xref:System.Windows.Forms.DataGridViewComboBoxEditingControl.ApplyCellStyleToEditingControl(System.Windows.Forms.DataGridViewCellStyle)?displayProperty=nameWithType> | `dataGridViewCellStyle` | <span data-ttu-id="d1231-128">5.0 Preview 2</span><span class="sxs-lookup"><span data-stu-id="d1231-128">5.0 Preview 2</span></span> |
> | <xref:System.Windows.Forms.RichTextBox.LoadFile(System.IO.Stream,System.Windows.Forms.RichTextBoxStreamType)?displayProperty=nameWithType> | `data` | <span data-ttu-id="d1231-129">5.0 Preview 2</span><span class="sxs-lookup"><span data-stu-id="d1231-129">5.0 Preview 2</span></span> |
> | <xref:System.Windows.Forms.ListBox.IntegerCollection.%23ctor(System.Windows.Forms.ListBox)> | `owner` | <span data-ttu-id="d1231-130">5.0 Vorschau 5</span><span class="sxs-lookup"><span data-stu-id="d1231-130">5.0 Preview 5</span></span> |
> | <xref:System.Windows.Forms.ListBox.IntegerCollection.CopyTo(System.Array,System.Int32)?displayProperty=nameWithType> | `destination` | <span data-ttu-id="d1231-131">5.0 Vorschau 5</span><span class="sxs-lookup"><span data-stu-id="d1231-131">5.0 Preview 5</span></span> |
> | <xref:System.Windows.Forms.ListViewGroup.System%23Runtime%23Serialization%23ISerializable%23GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | `info` | <span data-ttu-id="d1231-132">5.0 Vorschau 5</span><span class="sxs-lookup"><span data-stu-id="d1231-132">5.0 Preview 5</span></span> |
> | <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer.%23ctor(System.String,System.Int32,System.Int32)> | `className` | <span data-ttu-id="d1231-133">5.0 Vorschau 5</span><span class="sxs-lookup"><span data-stu-id="d1231-133">5.0 Preview 5</span></span> |

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

-->
