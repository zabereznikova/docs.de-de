---
title: VerifyClientKey-Funktion (Referenz zur nicht verwalteten API)
description: Die VerifyClientKey-Funktion stellt sicher, dass der Clientschlüssel die richtigen Sicherheit hat.
ms.date: 11/06/2017
api_name:
- VerifyClientKey
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- VerifyClientKey
helpviewer_keywords:
- VerifyClientKey function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 47fee26a0c4c25e4bff5bca94e5e26daaf98cccd
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59214714"
---
# <a name="verifyclientkey-function"></a><span data-ttu-id="cc2be-103">VerifyClientKey-Funktion</span><span class="sxs-lookup"><span data-stu-id="cc2be-103">VerifyClientKey function</span></span>
<span data-ttu-id="cc2be-104">Stellt sicher, dass der Clientschlüssel die richtige Sicherheit aufweist.</span><span class="sxs-lookup"><span data-stu-id="cc2be-104">Ensures that the client key has the correct security.</span></span>  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="cc2be-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="cc2be-105">Syntax</span></span>  
  
```  
LONG VerifyClientKey(); 
```  

## <a name="return-value"></a><span data-ttu-id="cc2be-106">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="cc2be-106">Return value</span></span>

<span data-ttu-id="cc2be-107">Wenn die Funktion erfolgreich ist, wird der Rückgabewert ist `ERROR_SUCCESS` (0).</span><span class="sxs-lookup"><span data-stu-id="cc2be-107">If the function succeeds, the return value is `ERROR_SUCCESS` (0).</span></span>

<span data-ttu-id="cc2be-108">Wenn die Funktion fehlschlägt, wird der Rückgabewert ist ein ungleich NULL-Fehlercode in definiert *"Winerror.h"*.</span><span class="sxs-lookup"><span data-stu-id="cc2be-108">If the function fails, the return value is a non-zero error code defined in *WinError.h*.</span></span>

## <a name="requirements"></a><span data-ttu-id="cc2be-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="cc2be-109">Requirements</span></span>  
 <span data-ttu-id="cc2be-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cc2be-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cc2be-111">**Header:** WMINet_Utils.def</span><span class="sxs-lookup"><span data-stu-id="cc2be-111">**Header:** WMINet_Utils.def</span></span>  
  
 **<span data-ttu-id="cc2be-112">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="cc2be-112">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a><span data-ttu-id="cc2be-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cc2be-113">See also</span></span>

- [<span data-ttu-id="cc2be-114">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="cc2be-114">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
