---
title: Initialize-Funktion (Referenz zur nicht verwalteten API)
description: Die Initialize-Funktion führt eine WMI-Initialisierung.
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
ms.openlocfilehash: 7c71b2b6d6f102d19d30d480ee9bafcac3c204be
ms.sourcegitcommit: 438919211260bb415fc8f96ca3eabc33cf2d681d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2019
ms.locfileid: "59611080"
---
# <a name="initialize-function"></a><span data-ttu-id="fd5cc-103">Initialize-Funktion</span><span class="sxs-lookup"><span data-stu-id="fd5cc-103">Initialize function</span></span>

<span data-ttu-id="fd5cc-104">Führt die WMI-Initialisierung aus.</span><span class="sxs-lookup"><span data-stu-id="fd5cc-104">Performs WMI initialization.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="fd5cc-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="fd5cc-105">Syntax</span></span>

```cpp
HRESULT Initialize(
   [in] boolean bAllowIManagementObjectQI
);
```

## <a name="parameters"></a><span data-ttu-id="fd5cc-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="fd5cc-106">Parameters</span></span>

`bAllowIManagementObjectQI`

<span data-ttu-id="fd5cc-107">[in] `true` um anzugeben, dass Aufrufe an die QueryInterface für WMI-Objekte zulässig sind. `false` andernfalls.</span><span class="sxs-lookup"><span data-stu-id="fd5cc-107">[in] `true` to indicate that calls to QueryInterface on WMI objects are allowed; `false` otherwise.</span></span>

## <a name="return-value"></a><span data-ttu-id="fd5cc-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="fd5cc-108">Return value</span></span>

<span data-ttu-id="fd5cc-109">Die Funktion gibt immer zurück `S_OK` (0).</span><span class="sxs-lookup"><span data-stu-id="fd5cc-109">The function always returns `S_OK` (0).</span></span>

## <a name="requirements"></a><span data-ttu-id="fd5cc-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fd5cc-110">Requirements</span></span>

<span data-ttu-id="fd5cc-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fd5cc-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="fd5cc-112">**Header:** WMINet_Utils.def</span><span class="sxs-lookup"><span data-stu-id="fd5cc-112">**Header:** WMINet_Utils.def</span></span>

<span data-ttu-id="fd5cc-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="fd5cc-113">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="fd5cc-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fd5cc-114">See also</span></span>

- [<span data-ttu-id="fd5cc-115">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="fd5cc-115">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
