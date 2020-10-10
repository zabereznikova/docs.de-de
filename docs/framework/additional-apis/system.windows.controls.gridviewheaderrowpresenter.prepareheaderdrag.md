---
title: Prepareheaderdrag-Methode (System. Windows. Controls. GridViewHeaderRowPresenter)
description: Erfahren Sie mehr über die private WPF-Methode mit dem Namen prepareheaderdrag.
ms.date: 09/25/2020
ms.technology: dotnet-wpf
topic_type:
- apiref
api_name:
- System.Windows.Controls.GridViewHeaderRowPresenter.PrepareHeaderDrag
api_location:
- PresentationFramework.dll
api_type:
- Assembly
ms.openlocfilehash: 6d806b8a50de3234cd04198f4ab86621dcd6ede1
ms.sourcegitcommit: eb7e87496f42361b1da98562dd75b516c9d58bbc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/09/2020
ms.locfileid: "91877784"
---
# <a name="prepareheaderdrag-method"></a><span data-ttu-id="1ddeb-103">Prepareheaderdrag-Methode</span><span class="sxs-lookup"><span data-stu-id="1ddeb-103">PrepareHeaderDrag method</span></span>

<span data-ttu-id="1ddeb-104">Bereitet den angegebenen Spaltenheader für die Neuanordnung vor.</span><span class="sxs-lookup"><span data-stu-id="1ddeb-104">Prepares the specified column header for reordering.</span></span>

```csharp
private void PrepareHeaderDrag(GridViewColumnHeader header, Point pos, Point relativePos, bool cancelInvoke)
```

> [!WARNING]
> <span data-ttu-id="1ddeb-105">Diese Methode ist privat und sollte nicht direkt im Code verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1ddeb-105">This method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="1ddeb-106">Microsoft unterstützt die Verwendung dieser Methode in einer Produktionsanwendung unter keinen Umständen.</span><span class="sxs-lookup"><span data-stu-id="1ddeb-106">Microsoft does not support the use of this method in a production application under any circumstance.</span></span>

## <a name="parameters"></a><span data-ttu-id="1ddeb-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="1ddeb-107">Parameters</span></span>

<span data-ttu-id="1ddeb-108">`header` <xref:System.Windows.Controls.GridViewColumnHeader></span><span class="sxs-lookup"><span data-stu-id="1ddeb-108">`header` <xref:System.Windows.Controls.GridViewColumnHeader></span></span>\
<span data-ttu-id="1ddeb-109">Der Spaltenheader, der für die Neuanordnung vorbereitet werden soll.</span><span class="sxs-lookup"><span data-stu-id="1ddeb-109">The column header to prepare for reordering.</span></span>

<span data-ttu-id="1ddeb-110">`pos` <xref:System.Windows.Point></span><span class="sxs-lookup"><span data-stu-id="1ddeb-110">`pos` <xref:System.Windows.Point></span></span>\
<span data-ttu-id="1ddeb-111">Die Position relativ zu <xref:System.Windows.Controls.GridViewHeaderRowPresenter> , an der der Zieh Vorgang beginnt.</span><span class="sxs-lookup"><span data-stu-id="1ddeb-111">The position, relative to <xref:System.Windows.Controls.GridViewHeaderRowPresenter>, where the dragging starts.</span></span>

<span data-ttu-id="1ddeb-112">`relativePos` <xref:System.Windows.Point></span><span class="sxs-lookup"><span data-stu-id="1ddeb-112">`relativePos` <xref:System.Windows.Point></span></span>\
<span data-ttu-id="1ddeb-113">Die Position relativ zu `header` , an der der Zieh Vorgang beginnt.</span><span class="sxs-lookup"><span data-stu-id="1ddeb-113">The position, relative to `header`, where the dragging starts.</span></span>

<span data-ttu-id="1ddeb-114">`cancelInvoke` <xref:System.Boolean></span><span class="sxs-lookup"><span data-stu-id="1ddeb-114">`cancelInvoke` <xref:System.Boolean></span></span>\
<span data-ttu-id="1ddeb-115">`true` , wenn die Neuanordnung abgebrochen werden soll. andernfalls `false` .</span><span class="sxs-lookup"><span data-stu-id="1ddeb-115">`true` to cancel the reordering; otherwise, `false`.</span></span>

## <a name="requirements"></a><span data-ttu-id="1ddeb-116">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="1ddeb-116">Requirements</span></span>

<span data-ttu-id="1ddeb-117">**Namespace:** <xref:System.Windows.Controls></span><span class="sxs-lookup"><span data-stu-id="1ddeb-117">**Namespace:** <xref:System.Windows.Controls></span></span>

<span data-ttu-id="1ddeb-118">**Assembly:** PresentationFramework.dll</span><span class="sxs-lookup"><span data-stu-id="1ddeb-118">**Assembly:** PresentationFramework.dll</span></span>

## <a name="see-also"></a><span data-ttu-id="1ddeb-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1ddeb-119">See also</span></span>

- <xref:System.Windows.Controls.GridViewHeaderRowPresenter>
