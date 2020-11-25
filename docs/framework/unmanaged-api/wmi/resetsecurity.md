---
title: Resetsecurity-Funktion (Referenz zur nicht verwalteten API)
description: Die resetsecurity-Funktion weist dem aktuellen Thread ein Identitätswechsel Token zu.
ms.date: 11/06/2017
api_name:
- ResetSecurity
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- ResetSecurity
helpviewer_keywords:
- ResetSecurity function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 259bef74356f16221f1453dd4086e2fbb26faa83
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721113"
---
# <a name="resetsecurity-function"></a><span data-ttu-id="e5e44-103">ResetSecurity-Funktion</span><span class="sxs-lookup"><span data-stu-id="e5e44-103">ResetSecurity function</span></span>

<span data-ttu-id="e5e44-104">Weist das angegebene Identitätswechseltoken dem aktuellen Thread zu.</span><span class="sxs-lookup"><span data-stu-id="e5e44-104">Assigns the supplied impersonation token to the current thread.</span></span>
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="e5e44-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="e5e44-105">Syntax</span></span>  
  
```cpp  
HRESULT ResetSecurity (
   [in] HANDLE token
);
```  

## <a name="parameters"></a><span data-ttu-id="e5e44-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="e5e44-106">Parameters</span></span>

`token`  
<span data-ttu-id="e5e44-107">in Das Identitätswechsel Token, das dem aktuellen Thread zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="e5e44-107">[in] The impersonation token to associate with the current thread.</span></span> <span data-ttu-id="e5e44-108">Ihr Wert kann `null` sein.</span><span class="sxs-lookup"><span data-stu-id="e5e44-108">Its value can be `null`.</span></span>

## <a name="return-value"></a><span data-ttu-id="e5e44-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="e5e44-109">Return value</span></span>

<span data-ttu-id="e5e44-110">Wenn die Funktion erfolgreich ausgeführt wird, ist der Rückgabewert `S_OK` (0).</span><span class="sxs-lookup"><span data-stu-id="e5e44-110">If the function succeeds, the return value is `S_OK` (0).</span></span>

<span data-ttu-id="e5e44-111">Wenn die Funktion fehlschlägt, ist der Rückgabewert ein Fehlercode ungleich 0 (null).</span><span class="sxs-lookup"><span data-stu-id="e5e44-111">If the function fails, the return value is a non-zero error code.</span></span> <span data-ttu-id="e5e44-112">Um erweiterte Fehlerinformationen abzurufen, wenden Sie die [GetErrorInfo](geterrorinfo.md) -Funktion an.</span><span class="sxs-lookup"><span data-stu-id="e5e44-112">To get extended error information, call the [GetErrorInfo](geterrorinfo.md) function.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="e5e44-113">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="e5e44-113">Requirements</span></span>  

 <span data-ttu-id="e5e44-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e5e44-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5e44-115">**Header:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="e5e44-115">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="e5e44-116">**.NET Framework Versionen:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="e5e44-116">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5e44-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e5e44-117">See also</span></span>

- [<span data-ttu-id="e5e44-118">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="e5e44-118">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
