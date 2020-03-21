---
title: VerifyClientKey-Funktion (Nicht verwaltete API-Referenz)
description: Die VerifyClientKey-Funktion stellt sicher, dass der Clientschlüssel über die richtige Sicherheit verfügt.
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
ms.openlocfilehash: ebb794240494deb0c831b50e95461ec52017a215
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176707"
---
# <a name="verifyclientkey-function"></a><span data-ttu-id="c2fca-103">VerifyClientKey-Funktion</span><span class="sxs-lookup"><span data-stu-id="c2fca-103">VerifyClientKey function</span></span>
<span data-ttu-id="c2fca-104">Stellt sicher, dass der Clientschlüssel die richtige Sicherheit aufweist.</span><span class="sxs-lookup"><span data-stu-id="c2fca-104">Ensures that the client key has the correct security.</span></span>  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="c2fca-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="c2fca-105">Syntax</span></span>  
  
```cpp  
LONG VerifyClientKey();
```  

## <a name="return-value"></a><span data-ttu-id="c2fca-106">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="c2fca-106">Return value</span></span>

<span data-ttu-id="c2fca-107">Wenn die Funktion erfolgreich ist, `ERROR_SUCCESS` ist der Rückgabewert (0).</span><span class="sxs-lookup"><span data-stu-id="c2fca-107">If the function succeeds, the return value is `ERROR_SUCCESS` (0).</span></span>

<span data-ttu-id="c2fca-108">Wenn die Funktion fehlschlägt, ist der Rückgabewert ein Fehlercode ungleich Null, der in *WinError.h*definiert ist.</span><span class="sxs-lookup"><span data-stu-id="c2fca-108">If the function fails, the return value is a non-zero error code defined in *WinError.h*.</span></span>

## <a name="requirements"></a><span data-ttu-id="c2fca-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="c2fca-109">Requirements</span></span>  
 <span data-ttu-id="c2fca-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c2fca-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2fca-111">**Kopfzeile:** WMINet_Utils.def</span><span class="sxs-lookup"><span data-stu-id="c2fca-111">**Header:** WMINet_Utils.def</span></span>  
  
 <span data-ttu-id="c2fca-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="c2fca-112">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2fca-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c2fca-113">See also</span></span>

- [<span data-ttu-id="c2fca-114">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="c2fca-114">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
