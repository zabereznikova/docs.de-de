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
ms.openlocfilehash: 26cffe9936f2e01078b6f54e8499b58519f1018e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729420"
---
# <a name="verifyclientkey-function"></a><span data-ttu-id="02889-103">Verifyclientkey-Funktion</span><span class="sxs-lookup"><span data-stu-id="02889-103">VerifyClientKey function</span></span>

<span data-ttu-id="02889-104">Stellt sicher, dass der Clientschlüssel die richtige Sicherheit aufweist.</span><span class="sxs-lookup"><span data-stu-id="02889-104">Ensures that the client key has the correct security.</span></span>  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="02889-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="02889-105">Syntax</span></span>  
  
```cpp  
LONG VerifyClientKey();
```  

## <a name="return-value"></a><span data-ttu-id="02889-106">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="02889-106">Return value</span></span>

<span data-ttu-id="02889-107">Wenn die Funktion erfolgreich ausgeführt wird, ist der Rückgabewert `ERROR_SUCCESS` (0).</span><span class="sxs-lookup"><span data-stu-id="02889-107">If the function succeeds, the return value is `ERROR_SUCCESS` (0).</span></span>

<span data-ttu-id="02889-108">Wenn die Funktion fehlschlägt, ist der Rückgabewert ein Fehlercode ungleich 0 (null), der in *Winerror. h* definiert ist.</span><span class="sxs-lookup"><span data-stu-id="02889-108">If the function fails, the return value is a non-zero error code defined in *WinError.h*.</span></span>

## <a name="requirements"></a><span data-ttu-id="02889-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="02889-109">Requirements</span></span>  

 <span data-ttu-id="02889-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="02889-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="02889-111">**Header:** WMINet_Utils. def</span><span class="sxs-lookup"><span data-stu-id="02889-111">**Header:** WMINet_Utils.def</span></span>  
  
 <span data-ttu-id="02889-112">**.NET Framework Versionen:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="02889-112">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02889-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="02889-113">See also</span></span>

- [<span data-ttu-id="02889-114">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="02889-114">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
