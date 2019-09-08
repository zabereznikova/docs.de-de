---
title: Initialize-Funktion (Referenz zur nicht verwalteten API)
description: Die Initialize-Funktion führt die WMI-Initialisierung aus.
ms.date: 11/06/2017
api_name:
- Initialize
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Initialize
helpviewer_keywords:
- Initialize function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1bc3688b30180bdcde0a87027955a789de749f90
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798441"
---
# <a name="initialize-function"></a><span data-ttu-id="73d8f-103">Initialize-Funktion</span><span class="sxs-lookup"><span data-stu-id="73d8f-103">Initialize function</span></span>

<span data-ttu-id="73d8f-104">Führt die WMI-Initialisierung aus.</span><span class="sxs-lookup"><span data-stu-id="73d8f-104">Performs WMI initialization.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="73d8f-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="73d8f-105">Syntax</span></span>

```cpp
HRESULT Initialize(
   [in] boolean bAllowIManagementObjectQI
);
```

## <a name="parameters"></a><span data-ttu-id="73d8f-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="73d8f-106">Parameters</span></span>

`bAllowIManagementObjectQI`

<span data-ttu-id="73d8f-107">in `true` , um anzugeben, dass Aufrufe von QueryInterface für WMI-Objekte zulässig sind. `false` andernfalls.</span><span class="sxs-lookup"><span data-stu-id="73d8f-107">[in] `true` to indicate that calls to QueryInterface on WMI objects are allowed; `false` otherwise.</span></span>

## <a name="return-value"></a><span data-ttu-id="73d8f-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="73d8f-108">Return value</span></span>

<span data-ttu-id="73d8f-109">Die Funktion gibt immer `S_OK` (0) zurück.</span><span class="sxs-lookup"><span data-stu-id="73d8f-109">The function always returns `S_OK` (0).</span></span>

## <a name="requirements"></a><span data-ttu-id="73d8f-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="73d8f-110">Requirements</span></span>

<span data-ttu-id="73d8f-111">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="73d8f-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="73d8f-112">**Header:** WMINet_Utils.def</span><span class="sxs-lookup"><span data-stu-id="73d8f-112">**Header:** WMINet_Utils.def</span></span>

<span data-ttu-id="73d8f-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="73d8f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="73d8f-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="73d8f-114">See also</span></span>

- [<span data-ttu-id="73d8f-115">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="73d8f-115">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
