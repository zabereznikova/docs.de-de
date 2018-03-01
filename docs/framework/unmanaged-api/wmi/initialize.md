---
title: Initialize-Funktion (Referenz zur nicht verwalteten API)
description: "Die Initialize-Funktion führt eine WMI-Initialisierung."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: reference
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
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d62d959c5dfeac237abb20b86df87ae07a077dbd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="initialize-function"></a><span data-ttu-id="38608-103">Initialize-Funktion</span><span class="sxs-lookup"><span data-stu-id="38608-103">Initialize function</span></span>
<span data-ttu-id="38608-104">Führt eine WMI-Initialisierung.</span><span class="sxs-lookup"><span data-stu-id="38608-104">Performs WMI initialization.</span></span>  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="38608-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="38608-105">Syntax</span></span> 
```  
HRESULT Initialize(
   [in] boolean bAllowIManagementObjectQI
); 
```  
## <a name="parameters"></a><span data-ttu-id="38608-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="38608-106">Parameters</span></span>

`bAllowIManagementObjectQI`   
<span data-ttu-id="38608-107">[in] `true` , um anzugeben, dass Aufrufe von QueryInterface auf WMI-Objekte zulässig sind; `false` andernfalls.</span><span class="sxs-lookup"><span data-stu-id="38608-107">[in] `true` to indicate that calls to QueryInterface on WMI objects are allowed; `false` otherwise.</span></span>

## <a name="return-value"></a><span data-ttu-id="38608-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="38608-108">Return value</span></span>

<span data-ttu-id="38608-109">Die Funktion gibt immer zurück `S_OK` (0).</span><span class="sxs-lookup"><span data-stu-id="38608-109">The function always returns `S_OK` (0).</span></span>
  
## <a name="requirements"></a><span data-ttu-id="38608-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="38608-110">Requirements</span></span>  
 <span data-ttu-id="38608-111">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="38608-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="38608-112">**Header:** WMINet_Utils.def</span><span class="sxs-lookup"><span data-stu-id="38608-112">**Header:** WMINet_Utils.def</span></span>  
  
 <span data-ttu-id="38608-113">**.NET Framework-Versionen:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="38608-113">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38608-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="38608-114">See also</span></span>  
[<span data-ttu-id="38608-115">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="38608-115">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
