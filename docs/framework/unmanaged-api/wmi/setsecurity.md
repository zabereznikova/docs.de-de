---
title: SetSecurity-Funktion (Referenz zur nicht verwalteten API)
description: Die SetSecurity-Funktion ruft Identitätswechseltoken für den aktuellen Thread ab.
ms.date: 11/06/2017
api_name:
- SetSecurity
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- SetSecurity
helpviewer_keywords:
- SetSecurity function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a2cb71263201c86a93ca0bfbd783f2b8512055e6
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67783115"
---
# <a name="setsecurity-function"></a><span data-ttu-id="9d5ef-103">SetSecurity-Funktion</span><span class="sxs-lookup"><span data-stu-id="9d5ef-103">SetSecurity function</span></span>

<span data-ttu-id="9d5ef-104">Ruft das Identitätswechseltoken ab, das dem aktuellen Thread zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="9d5ef-104">Retrieves the impersonation token associated with the current thread.</span></span> 

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="9d5ef-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="9d5ef-105">Syntax</span></span>

```cpp
HRESULT SetSecurity (
   [out] boolean* pNeedToReset, 
   [out] HANDLE* pCurrentThreadToken
); 
```

## <a name="parameters"></a><span data-ttu-id="9d5ef-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="9d5ef-106">Parameters</span></span>

`pNeedToReset`\
<span data-ttu-id="9d5ef-107">[out] Wenn die Funktion zurückgibt, enthält einen Zeiger auf eine `boolean` , der angibt, ob das Token soll, durch den Aufruf zurückgesetzt werden der [ResetSecurity](resetsecurity.md) Funktion.</span><span class="sxs-lookup"><span data-stu-id="9d5ef-107">[out] When the function returns, contains a pointer to a `boolean` that indicates whether the token should be reset by calling the [ResetSecurity](resetsecurity.md) function.</span></span>

`token`\
<span data-ttu-id="9d5ef-108">[out] Wenn die Funktion zurückgibt, enthält einen Zeiger auf das Handle des Token für den Identitätswechsel des aktuellen Threads zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="9d5ef-108">[out] When the function returns, contains a pointer to the handle of the impersonation token associated with the current thread.</span></span> <span data-ttu-id="9d5ef-109">Die Werte sind möglich `null` liegt kein Token, das den aktuellen Thread zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="9d5ef-109">Its value can be `null` if there is no token associated with the current thread.</span></span> 

## <a name="return-value"></a><span data-ttu-id="9d5ef-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="9d5ef-110">Return value</span></span>

<span data-ttu-id="9d5ef-111">Wenn die Funktion erfolgreich ist, wird der Rückgabewert ist `S_OK` (0).</span><span class="sxs-lookup"><span data-stu-id="9d5ef-111">If the function succeeds, the return value is `S_OK` (0).</span></span>

<span data-ttu-id="9d5ef-112">Wenn die Funktion fehlschlägt, ist der Rückgabewert ein NULL-Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="9d5ef-112">If the function fails, the return value is a non-zero error code.</span></span> <span data-ttu-id="9d5ef-113">Um erweiterte Fehlerinformationen abzurufen, rufen Sie die [GetErrorInfo](geterrorinfo.md) Funktion.</span><span class="sxs-lookup"><span data-stu-id="9d5ef-113">To get extended error information, call the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="9d5ef-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9d5ef-114">Requirements</span></span>

 <span data-ttu-id="9d5ef-115">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9d5ef-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

 <span data-ttu-id="9d5ef-116">**Header:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="9d5ef-116">**Header:** WMINet_Utils.idl</span></span>

 <span data-ttu-id="9d5ef-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="9d5ef-117">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="9d5ef-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9d5ef-118">See also</span></span>

- [<span data-ttu-id="9d5ef-119">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="9d5ef-119">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
