---
ms.openlocfilehash: 297af393e86c65e84ea7271d98eab36dbc6dbb0e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59774384"
---
### <a name="some-workflow-drag-and-drop-apis-are-obsolete"></a><span data-ttu-id="b6c30-101">Einige Drag & Drop-APIs für WorkFlow sind veraltet.</span><span class="sxs-lookup"><span data-stu-id="b6c30-101">Some WorkFlow drag-and-drop APIs are obsolete</span></span>

|   |   |
|---|---|
|<span data-ttu-id="b6c30-102">Details</span><span class="sxs-lookup"><span data-stu-id="b6c30-102">Details</span></span>|<span data-ttu-id="b6c30-103">Diese Drag & Drop-API für WorkFlow ist veraltet und löst Compilerwarnungen aus, wenn die App mit Version 4.5 neu erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="b6c30-103">This WorkFlow drag-and-drop API is obsolete and will cause compiler warnings if the app is rebuilt against 4.5.</span></span>|
|<span data-ttu-id="b6c30-104">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="b6c30-104">Suggestion</span></span>|<span data-ttu-id="b6c30-105">Stattdessen sollten neue <xref:System.Activities.Presentation.DragDropHelper?displayProperty=name>-APIs verwendet werden, die Vorgänge mit mehreren Objekten unterstützen.</span><span class="sxs-lookup"><span data-stu-id="b6c30-105">New <xref:System.Activities.Presentation.DragDropHelper?displayProperty=name> APIs that support operations with multiple objects should be used instead.</span></span> <span data-ttu-id="b6c30-106">Alternativ können die Buildwarnungen unterdrückt oder durch die Verwendung eines älteren Compilers vermieden werden.</span><span class="sxs-lookup"><span data-stu-id="b6c30-106">Alternatively, the build warnings can be suppressed or they can be avoided by using an older compiler.</span></span> <span data-ttu-id="b6c30-107">Die APIs werden weiterhin unterstützt.</span><span class="sxs-lookup"><span data-stu-id="b6c30-107">The APIs are still supported.</span></span>|
|<span data-ttu-id="b6c30-108">Bereich</span><span class="sxs-lookup"><span data-stu-id="b6c30-108">Scope</span></span>|<span data-ttu-id="b6c30-109">Gering</span><span class="sxs-lookup"><span data-stu-id="b6c30-109">Minor</span></span>|
|<span data-ttu-id="b6c30-110">Version</span><span class="sxs-lookup"><span data-stu-id="b6c30-110">Version</span></span>|<span data-ttu-id="b6c30-111">4.5</span><span class="sxs-lookup"><span data-stu-id="b6c30-111">4.5</span></span>|
|<span data-ttu-id="b6c30-112">Typ</span><span class="sxs-lookup"><span data-stu-id="b6c30-112">Type</span></span>|<span data-ttu-id="b6c30-113">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="b6c30-113">Retargeting</span></span>|
|<span data-ttu-id="b6c30-114">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="b6c30-114">Affected APIs</span></span>|<ul><li><xref:System.Activities.Presentation.DragDropHelper.DoDragMove(System.Activities.Presentation.WorkflowViewElement,System.Windows.Point)?displayProperty=nameWithType></li><li><xref:System.Activities.Presentation.DragDropHelper.GetCompositeView(System.Windows.DragEventArgs)?displayProperty=nameWithType></li><li><xref:System.Activities.Presentation.DragDropHelper.GetDraggedModelItem(System.Windows.DragEventArgs)?displayProperty=nameWithType></li><li><xref:System.Activities.Presentation.DragDropHelper.GetDroppedObject(System.Windows.DependencyObject,System.Windows.DragEventArgs,System.Activities.Presentation.EditingContext)?displayProperty=nameWithType></li></ul>|
