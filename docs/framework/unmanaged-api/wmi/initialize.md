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
ms.openlocfilehash: b1f96b6285911b12d72ac136127d736b75d44023
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127390"
---
# <a name="initialize-function"></a><span data-ttu-id="97ff7-103">Initialize-Funktion</span><span class="sxs-lookup"><span data-stu-id="97ff7-103">Initialize function</span></span>

<span data-ttu-id="97ff7-104">Führt die WMI-Initialisierung aus.</span><span class="sxs-lookup"><span data-stu-id="97ff7-104">Performs WMI initialization.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="97ff7-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="97ff7-105">Syntax</span></span>

```cpp
HRESULT Initialize(
   [in] boolean bAllowIManagementObjectQI
);
```

## <a name="parameters"></a><span data-ttu-id="97ff7-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="97ff7-106">Parameters</span></span>

`bAllowIManagementObjectQI`

<span data-ttu-id="97ff7-107">[in] `true`, um anzugeben, dass Aufrufe von QueryInterface für WMI-Objekte zulässig sind. Andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="97ff7-107">[in] `true` to indicate that calls to QueryInterface on WMI objects are allowed; `false` otherwise.</span></span>

## <a name="return-value"></a><span data-ttu-id="97ff7-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="97ff7-108">Return value</span></span>

<span data-ttu-id="97ff7-109">Die Funktion gibt immer `S_OK` (0) zurück.</span><span class="sxs-lookup"><span data-stu-id="97ff7-109">The function always returns `S_OK` (0).</span></span>

## <a name="requirements"></a><span data-ttu-id="97ff7-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="97ff7-110">Requirements</span></span>

<span data-ttu-id="97ff7-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="97ff7-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="97ff7-112">**Header:** WMINet_Utils. def</span><span class="sxs-lookup"><span data-stu-id="97ff7-112">**Header:** WMINet_Utils.def</span></span>

<span data-ttu-id="97ff7-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="97ff7-113">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="97ff7-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="97ff7-114">See also</span></span>

- [<span data-ttu-id="97ff7-115">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="97ff7-115">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
