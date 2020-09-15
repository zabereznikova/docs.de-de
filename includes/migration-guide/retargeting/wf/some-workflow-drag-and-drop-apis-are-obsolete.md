---
ms.openlocfilehash: b6cb7edcd6bed50efdf59f3321320ac8cd1b1ab8
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617227"
---
### <a name="some-workflow-drag-and-drop-apis-are-obsolete"></a><span data-ttu-id="b84ae-101">Einige Drag & Drop-APIs für WorkFlow sind veraltet.</span><span class="sxs-lookup"><span data-stu-id="b84ae-101">Some WorkFlow drag-and-drop APIs are obsolete</span></span>

#### <a name="details"></a><span data-ttu-id="b84ae-102">Details</span><span class="sxs-lookup"><span data-stu-id="b84ae-102">Details</span></span>

<span data-ttu-id="b84ae-103">Diese Drag & Drop-API für WorkFlow ist veraltet und löst Compilerwarnungen aus, wenn die App mit Version 4.5 neu erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="b84ae-103">This WorkFlow drag-and-drop API is obsolete and will cause compiler warnings if the app is rebuilt against 4.5.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="b84ae-104">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="b84ae-104">Suggestion</span></span>

<span data-ttu-id="b84ae-105">Stattdessen sollten neue <xref:System.Activities.Presentation.DragDropHelper?displayProperty=fullName>-APIs verwendet werden, die Vorgänge mit mehreren Objekten unterstützen.</span><span class="sxs-lookup"><span data-stu-id="b84ae-105">New <xref:System.Activities.Presentation.DragDropHelper?displayProperty=fullName> APIs that support operations with multiple objects should be used instead.</span></span> <span data-ttu-id="b84ae-106">Alternativ können die Buildwarnungen unterdrückt oder durch die Verwendung eines älteren Compilers vermieden werden.</span><span class="sxs-lookup"><span data-stu-id="b84ae-106">Alternatively, the build warnings can be suppressed or they can be avoided by using an older compiler.</span></span> <span data-ttu-id="b84ae-107">Die APIs werden weiterhin unterstützt.</span><span class="sxs-lookup"><span data-stu-id="b84ae-107">The APIs are still supported.</span></span>

| <span data-ttu-id="b84ae-108">name</span><span class="sxs-lookup"><span data-stu-id="b84ae-108">Name</span></span>    | <span data-ttu-id="b84ae-109">Wert</span><span class="sxs-lookup"><span data-stu-id="b84ae-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="b84ae-110">Bereich</span><span class="sxs-lookup"><span data-stu-id="b84ae-110">Scope</span></span>   | <span data-ttu-id="b84ae-111">Gering</span><span class="sxs-lookup"><span data-stu-id="b84ae-111">Minor</span></span>       |
| <span data-ttu-id="b84ae-112">Version</span><span class="sxs-lookup"><span data-stu-id="b84ae-112">Version</span></span> | <span data-ttu-id="b84ae-113">4.5</span><span class="sxs-lookup"><span data-stu-id="b84ae-113">4.5</span></span>         |
| <span data-ttu-id="b84ae-114">Typ</span><span class="sxs-lookup"><span data-stu-id="b84ae-114">Type</span></span>    | <span data-ttu-id="b84ae-115">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="b84ae-115">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="b84ae-116">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="b84ae-116">Affected APIs</span></span>

- <xref:System.Activities.Presentation.DragDropHelper.DoDragMove(System.Activities.Presentation.WorkflowViewElement,System.Windows.Point)?displayProperty=nameWithType>
- <xref:System.Activities.Presentation.DragDropHelper.GetCompositeView(System.Windows.DragEventArgs)?displayProperty=nameWithType>
- <xref:System.Activities.Presentation.DragDropHelper.GetDraggedModelItem(System.Windows.DragEventArgs)?displayProperty=nameWithType>
- <xref:System.Activities.Presentation.DragDropHelper.GetDroppedObject(System.Windows.DependencyObject,System.Windows.DragEventArgs,System.Activities.Presentation.EditingContext)?displayProperty=nameWithType>
