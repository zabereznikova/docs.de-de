---
title: Verifyclientkey-Funktion (Referenz zur nicht verwalteten API)
description: Mit der verifyclientkey-Funktion wird sichergestellt, dass der Client Schlüssel über die richtige Sicherheit verfügt.
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
ms.openlocfilehash: b674e959ab93cf76b84e2af41e875a50b7d115f4
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798193"
---
# <a name="verifyclientkey-function"></a><span data-ttu-id="80797-103">Verifyclientkey-Funktion</span><span class="sxs-lookup"><span data-stu-id="80797-103">VerifyClientKey function</span></span>
<span data-ttu-id="80797-104">Stellt sicher, dass der Clientschlüssel die richtige Sicherheit aufweist.</span><span class="sxs-lookup"><span data-stu-id="80797-104">Ensures that the client key has the correct security.</span></span>  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="80797-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="80797-105">Syntax</span></span>  
  
```cpp  
LONG VerifyClientKey(); 
```  

## <a name="return-value"></a><span data-ttu-id="80797-106">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="80797-106">Return value</span></span>

<span data-ttu-id="80797-107">Wenn die Funktion erfolgreich ausgeführt wird, ist `ERROR_SUCCESS` der Rückgabewert (0).</span><span class="sxs-lookup"><span data-stu-id="80797-107">If the function succeeds, the return value is `ERROR_SUCCESS` (0).</span></span>

<span data-ttu-id="80797-108">Wenn die Funktion fehlschlägt, ist der Rückgabewert ein Fehlercode ungleich 0 (null), der in *Winerror. h*definiert ist.</span><span class="sxs-lookup"><span data-stu-id="80797-108">If the function fails, the return value is a non-zero error code defined in *WinError.h*.</span></span>

## <a name="requirements"></a><span data-ttu-id="80797-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="80797-109">Requirements</span></span>  
 <span data-ttu-id="80797-110">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="80797-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="80797-111">**Header:** WMINet_Utils.def</span><span class="sxs-lookup"><span data-stu-id="80797-111">**Header:** WMINet_Utils.def</span></span>  
  
 <span data-ttu-id="80797-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="80797-112">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80797-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="80797-113">See also</span></span>

- [<span data-ttu-id="80797-114">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="80797-114">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
