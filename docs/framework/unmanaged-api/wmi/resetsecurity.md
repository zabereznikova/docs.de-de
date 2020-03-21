---
title: ResetSecurity-Funktion (Nicht verwaltete API-Referenz)
description: Die ResetSecurity-Funktion weist dem aktuellen Thread ein Identitätswechseltoken zu.
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
ms.openlocfilehash: ce74494455c6cc7fe382a4ea4ef2ff0c4e98c61b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174861"
---
# <a name="resetsecurity-function"></a><span data-ttu-id="61545-103">ResetSecurity-Funktion</span><span class="sxs-lookup"><span data-stu-id="61545-103">ResetSecurity function</span></span>
<span data-ttu-id="61545-104">Weist das angegebene Identitätswechseltoken dem aktuellen Thread zu.</span><span class="sxs-lookup"><span data-stu-id="61545-104">Assigns the supplied impersonation token to the current thread.</span></span>
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="61545-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="61545-105">Syntax</span></span>  
  
```cpp  
HRESULT ResetSecurity (
   [in] HANDLE token
);
```  

## <a name="parameters"></a><span data-ttu-id="61545-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="61545-106">Parameters</span></span>

`token`  
<span data-ttu-id="61545-107">[in] Das Identitätswechseltoken, das dem aktuellen Thread zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="61545-107">[in] The impersonation token to associate with the current thread.</span></span> <span data-ttu-id="61545-108">Ihr Wert kann `null` sein.</span><span class="sxs-lookup"><span data-stu-id="61545-108">Its value can be `null`.</span></span>

## <a name="return-value"></a><span data-ttu-id="61545-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="61545-109">Return value</span></span>

<span data-ttu-id="61545-110">Wenn die Funktion erfolgreich ist, `S_OK` ist der Rückgabewert (0).</span><span class="sxs-lookup"><span data-stu-id="61545-110">If the function succeeds, the return value is `S_OK` (0).</span></span>

<span data-ttu-id="61545-111">Wenn die Funktion fehlschlägt, ist der Rückgabewert ein Fehlercode ungleich Null.</span><span class="sxs-lookup"><span data-stu-id="61545-111">If the function fails, the return value is a non-zero error code.</span></span> <span data-ttu-id="61545-112">Um erweiterte Fehlerinformationen zu erhalten, rufen Sie die [GetErrorInfo-Funktion](geterrorinfo.md) auf.</span><span class="sxs-lookup"><span data-stu-id="61545-112">To get extended error information, call the [GetErrorInfo](geterrorinfo.md) function.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="61545-113">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="61545-113">Requirements</span></span>  
 <span data-ttu-id="61545-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="61545-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="61545-115">**Kopfzeile:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="61545-115">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="61545-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="61545-116">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61545-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="61545-117">See also</span></span>

- [<span data-ttu-id="61545-118">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="61545-118">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
