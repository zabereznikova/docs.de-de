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
ms.openlocfilehash: f4b51fe4510f4172227d9afd049eb6815790a165
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67783085"
---
# <a name="verifyclientkey-function"></a><span data-ttu-id="aa65e-103">VerifyClientKey-Funktion</span><span class="sxs-lookup"><span data-stu-id="aa65e-103">VerifyClientKey function</span></span>
<span data-ttu-id="aa65e-104">Stellt sicher, dass der Clientschlüssel die richtige Sicherheit aufweist.</span><span class="sxs-lookup"><span data-stu-id="aa65e-104">Ensures that the client key has the correct security.</span></span>  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="aa65e-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="aa65e-105">Syntax</span></span>  
  
```cpp  
LONG VerifyClientKey(); 
```  

## <a name="return-value"></a><span data-ttu-id="aa65e-106">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="aa65e-106">Return value</span></span>

<span data-ttu-id="aa65e-107">Wenn die Funktion erfolgreich ist, wird der Rückgabewert ist `ERROR_SUCCESS` (0).</span><span class="sxs-lookup"><span data-stu-id="aa65e-107">If the function succeeds, the return value is `ERROR_SUCCESS` (0).</span></span>

<span data-ttu-id="aa65e-108">Wenn die Funktion fehlschlägt, wird der Rückgabewert ist ein ungleich NULL-Fehlercode in definiert *"Winerror.h"* .</span><span class="sxs-lookup"><span data-stu-id="aa65e-108">If the function fails, the return value is a non-zero error code defined in *WinError.h*.</span></span>

## <a name="requirements"></a><span data-ttu-id="aa65e-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="aa65e-109">Requirements</span></span>  
 <span data-ttu-id="aa65e-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aa65e-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aa65e-111">**Header:** WMINet_Utils.def</span><span class="sxs-lookup"><span data-stu-id="aa65e-111">**Header:** WMINet_Utils.def</span></span>  
  
 <span data-ttu-id="aa65e-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="aa65e-112">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa65e-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="aa65e-113">See also</span></span>

- [<span data-ttu-id="aa65e-114">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="aa65e-114">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
