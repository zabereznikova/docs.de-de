---
ms.openlocfilehash: b6cb7edcd6bed50efdf59f3321320ac8cd1b1ab8
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617227"
---
### <a name="some-workflow-drag-and-drop-apis-are-obsolete"></a>Einige Drag & Drop-APIs für WorkFlow sind veraltet.

#### <a name="details"></a>Details

Diese Drag & Drop-API für WorkFlow ist veraltet und löst Compilerwarnungen aus, wenn die App mit Version 4.5 neu erstellt wird.

#### <a name="suggestion"></a>Vorschlag

Stattdessen sollten neue <xref:System.Activities.Presentation.DragDropHelper?displayProperty=fullName>-APIs verwendet werden, die Vorgänge mit mehreren Objekten unterstützen. Alternativ können die Buildwarnungen unterdrückt oder durch die Verwendung eines älteren Compilers vermieden werden. Die APIs werden weiterhin unterstützt.

| name    | Wert       |
|:--------|:------------|
| Bereich   | Gering       |
| Version | 4.5         |
| Typ    | Neuzuweisung |

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Activities.Presentation.DragDropHelper.DoDragMove(System.Activities.Presentation.WorkflowViewElement,System.Windows.Point)?displayProperty=nameWithType>
- <xref:System.Activities.Presentation.DragDropHelper.GetCompositeView(System.Windows.DragEventArgs)?displayProperty=nameWithType>
- <xref:System.Activities.Presentation.DragDropHelper.GetDraggedModelItem(System.Windows.DragEventArgs)?displayProperty=nameWithType>
- <xref:System.Activities.Presentation.DragDropHelper.GetDroppedObject(System.Windows.DependencyObject,System.Windows.DragEventArgs,System.Activities.Presentation.EditingContext)?displayProperty=nameWithType>
