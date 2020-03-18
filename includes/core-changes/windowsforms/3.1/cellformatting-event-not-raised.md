---
ms.openlocfilehash: add3ff8faed2e7fab245e5b6f1b9158b7bdd06f5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "74567367"
---
### <a name="cellformatting-event-not-raised-if-tooltip-is-shown"></a><span data-ttu-id="810b3-101">CellFormatting-Ereignis wird nicht ausgelöst, wenn QuickInfo angezeigt wird</span><span class="sxs-lookup"><span data-stu-id="810b3-101">CellFormatting event not raised if tooltip is shown</span></span>

<span data-ttu-id="810b3-102">Eine <xref:System.Windows.Forms.DataGridView> zeigt nun Text- und die Fehler-QuickInfos einer Zelle an, wenn mit der Maus darauf gezeigt wird oder wenn sie mit der Tastatur ausgewählt wird.</span><span class="sxs-lookup"><span data-stu-id="810b3-102">A <xref:System.Windows.Forms.DataGridView> now shows a cell's text and error tooltips when hovered by a mouse and when selected via the keyboard.</span></span> <span data-ttu-id="810b3-103">Wenn eine QuickInfo angezeigt wird, wird das <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType>-Ereignis nicht ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="810b3-103">If a tooltip is shown, the <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> event is not raised.</span></span>

#### <a name="change-description"></a><span data-ttu-id="810b3-104">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="810b3-104">Change description</span></span>

<span data-ttu-id="810b3-105">Vor .NET Core 3.1 wurde bei einer <xref:System.Windows.Forms.DataGridView>, für die die <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A>-Eigenschaft auf `true` festgelegt wurde, eine QuickInfo für den Text und Fehler einer Zelle angezeigt, wenn mit der Maus auf die Zelle gezeigt wurde.</span><span class="sxs-lookup"><span data-stu-id="810b3-105">Prior to .NET Core 3.1, a <xref:System.Windows.Forms.DataGridView> that had the <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A> property set to `true` showed a tooltip for a cell's text and errors when the cell was hovered by a mouse.</span></span> <span data-ttu-id="810b3-106">Es wurden keine QuickInfos angezeigt, wenn die Maus mit der Tastatur ausgewählt wurde (z. B. mit der TAB-TASTE, einer Tastenkombination oder den Pfeiltasten).</span><span class="sxs-lookup"><span data-stu-id="810b3-106">Tooltips were not shown when a cell was selected via the keyboard (for example, by using the Tab key, shortcut keys, or arrow navigation).</span></span> <span data-ttu-id="810b3-107">Wenn der Benutzer eine Zelle bearbeitet hat und die <xref:System.Windows.Forms.DataGridView> sich noch im Bearbeitungsmodus befunden hat und mit der Maus auf eine Zelle gezeigt wurde, für die die <xref:System.Windows.Forms.DataGridViewCell.ToolTipText>-Eigenschaft nicht festgelegt war, wurde ein <xref:System.Windows.Forms.DataGridView.CellFormatting>-Ereignis ausgelöst, um den Text der Zelle für die Anzeige in der Zelle zu formatieren.</span><span class="sxs-lookup"><span data-stu-id="810b3-107">If the user edited a cell, and then, while the <xref:System.Windows.Forms.DataGridView> was still in edit mode, hovered over a cell that did not have the <xref:System.Windows.Forms.DataGridViewCell.ToolTipText> property set, a <xref:System.Windows.Forms.DataGridView.CellFormatting> event was raised to format the cell's text for display in the cell.</span></span>

<span data-ttu-id="810b3-108">Um die Barrierefreiheitsstandards zu erfüllen, werden ab .NET Core 3.1 bei einer <xref:System.Windows.Forms.DataGridView>, für die die <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A>-Eigenschaft auf `true` festgelegt ist, QuickInfos für den Text und Fehler der Zelle nicht nur dann angezeigt, wenn mit der Maus darauf gezeigt wird, sondern auch, wenn sie mit der Tastatur ausgewählt wird.</span><span class="sxs-lookup"><span data-stu-id="810b3-108">To meet accessibility standards, starting in .NET Core 3.1, a <xref:System.Windows.Forms.DataGridView> that has the <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A> property set to `true` shows tooltips for a cell's text and errors not only when the cell is hovered, but also when it's selected via the keyboard.</span></span> <span data-ttu-id="810b3-109">Infolge dieser Änderung wird das <xref:System.Windows.Forms.DataGridView.CellFormatting>-Ereignis *nicht* ausgelöst, wenn mit der Maus auf Zellen gezeigt wird, für die <xref:System.Windows.Forms.DataGridViewCell.ToolTipText>-Eigenschaft nicht festgelegt ist, und die <xref:System.Windows.Forms.DataGridView> sich im Bearbeitungsmodus befindet.</span><span class="sxs-lookup"><span data-stu-id="810b3-109">As a consequence of this change, the <xref:System.Windows.Forms.DataGridView.CellFormatting> event is *not* raised when cells that don't have the <xref:System.Windows.Forms.DataGridViewCell.ToolTipText> property set are hovered while the <xref:System.Windows.Forms.DataGridView> is in edit mode.</span></span> <span data-ttu-id="810b3-110">Das Ereignis wird nicht ausgelöst, da der Inhalt der Zelle, auf die gezeigt wird, als QuickInfo und nicht in der Zelle dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="810b3-110">The event is not raised because the content of the hovered cell is shown as a tooltip instead of being displayed in the cell.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="810b3-111">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="810b3-111">Version introduced</span></span>

<span data-ttu-id="810b3-112">3.1</span><span class="sxs-lookup"><span data-stu-id="810b3-112">3.1</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="810b3-113">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="810b3-113">Recommended action</span></span>

<span data-ttu-id="810b3-114">Schreiben Sie Code um, der das <xref:System.Windows.Forms.DataGridView.CellFormatting>-Ereignis benötigt, während sich die <xref:System.Windows.Forms.DataGridView> im Bearbeitungsmodus befindet.</span><span class="sxs-lookup"><span data-stu-id="810b3-114">Refactor any code that depends on the <xref:System.Windows.Forms.DataGridView.CellFormatting> event while the <xref:System.Windows.Forms.DataGridView> is in edit mode.</span></span>

#### <a name="category"></a><span data-ttu-id="810b3-115">Kategorie</span><span class="sxs-lookup"><span data-stu-id="810b3-115">Category</span></span>

<span data-ttu-id="810b3-116">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="810b3-116">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="810b3-117">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="810b3-117">Affected APIs</span></span>

<span data-ttu-id="810b3-118">Nicht über API-Analyse erkennbar.</span><span class="sxs-lookup"><span data-stu-id="810b3-118">Not detectable via API analysis.</span></span>

<!-- 

### Affected APIs

- Not detectable via API analysis.

-->
