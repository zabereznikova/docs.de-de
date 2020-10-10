---
title: Findheaderbycolumn-Methode (System. Windows. Controls. GridViewHeaderRowPresenter)
description: Erfahren Sie mehr über die private WPF-Methode namens "findheaderbycolumn".
ms.date: 09/25/2020
ms.technology: dotnet-wpf
topic_type:
- apiref
api_name:
- System.Windows.Controls.GridViewHeaderRowPresenter.FindHeaderByColumn
api_location:
- PresentationFramework.dll
api_type:
- Assembly
ms.openlocfilehash: 88ed2928f86602d1078488354de6d5267c0311f5
ms.sourcegitcommit: eb7e87496f42361b1da98562dd75b516c9d58bbc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/09/2020
ms.locfileid: "91877789"
---
# <a name="findheaderbycolumn-method"></a><span data-ttu-id="1071a-103">Findheaderbycolumn-Methode</span><span class="sxs-lookup"><span data-stu-id="1071a-103">FindHeaderByColumn method</span></span>

<span data-ttu-id="1071a-104">Sucht den Spaltenheader für die angegebene Spalte in der visuellen Struktur.</span><span class="sxs-lookup"><span data-stu-id="1071a-104">Finds the column header for the specified column in the visual tree.</span></span>

```csharp
private GridViewColumnHeader FindHeaderByColumn(GridViewColumn column)
```

> [!WARNING]
> <span data-ttu-id="1071a-105">Diese Methode ist privat und sollte nicht direkt im Code verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1071a-105">This method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="1071a-106">Microsoft unterstützt die Verwendung dieser Methode in einer Produktionsanwendung unter keinen Umständen.</span><span class="sxs-lookup"><span data-stu-id="1071a-106">Microsoft does not support the use of this method in a production application under any circumstance.</span></span>

## <a name="parameters"></a><span data-ttu-id="1071a-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="1071a-107">Parameters</span></span>

<span data-ttu-id="1071a-108">`column` <xref:System.Windows.Controls.GridViewColumn></span><span class="sxs-lookup"><span data-stu-id="1071a-108">`column` <xref:System.Windows.Controls.GridViewColumn></span></span>\
<span data-ttu-id="1071a-109">Die Spalte, deren Header gefunden und zurückgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="1071a-109">The column whose header should be found and returned.</span></span>

## <a name="return-value"></a><span data-ttu-id="1071a-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="1071a-110">Return value</span></span>

<xref:System.Windows.Controls.GridViewColumnHeader>\
<span data-ttu-id="1071a-111">Der Header der angegebenen Spalte oder, `null` Wenn die angegebene Spalte nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="1071a-111">The header of the specified column, or `null` if the specified column doesn't exist.</span></span>

## <a name="requirements"></a><span data-ttu-id="1071a-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="1071a-112">Requirements</span></span>

<span data-ttu-id="1071a-113">**Namespace:** <xref:System.Windows.Controls></span><span class="sxs-lookup"><span data-stu-id="1071a-113">**Namespace:** <xref:System.Windows.Controls></span></span>

<span data-ttu-id="1071a-114">**Assembly:** PresentationFramework.dll</span><span class="sxs-lookup"><span data-stu-id="1071a-114">**Assembly:** PresentationFramework.dll</span></span>

## <a name="see-also"></a><span data-ttu-id="1071a-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1071a-115">See also</span></span>

- <xref:System.Windows.Controls.GridViewHeaderRowPresenter>
