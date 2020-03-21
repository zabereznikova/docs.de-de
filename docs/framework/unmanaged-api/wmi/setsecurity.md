---
title: SetSecurity-Funktion (Nicht verwaltete API-Referenz)
description: Die SetSecurity-Funktion ruft das Identitätswechseltoken des aktuellen Threads ab.
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
ms.openlocfilehash: 809f6a95fdd6854b3a591b496877838c48d52199
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176733"
---
# <a name="setsecurity-function"></a><span data-ttu-id="093ae-103">SetSecurity-Funktion</span><span class="sxs-lookup"><span data-stu-id="093ae-103">SetSecurity function</span></span>

<span data-ttu-id="093ae-104">Ruft das Identitätswechseltoken ab, das dem aktuellen Thread zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="093ae-104">Retrieves the impersonation token associated with the current thread.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="093ae-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="093ae-105">Syntax</span></span>

```cpp
HRESULT SetSecurity (
   [out] boolean* pNeedToReset,
   [out] HANDLE* pCurrentThreadToken
);
```

## <a name="parameters"></a><span data-ttu-id="093ae-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="093ae-106">Parameters</span></span>

`pNeedToReset`\
<span data-ttu-id="093ae-107">[out] Wenn die Funktion zurückkehrt, enthält `boolean` einen Zeiger auf einen, der angibt, ob das Token zurückgesetzt werden soll, indem die [ResetSecurity-Funktion](resetsecurity.md) aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="093ae-107">[out] When the function returns, contains a pointer to a `boolean` that indicates whether the token should be reset by calling the [ResetSecurity](resetsecurity.md) function.</span></span>

`token`\
<span data-ttu-id="093ae-108">[out] Wenn die Funktion zurückkehrt, enthält einen Zeiger auf das Handle des Identitätswechseltokens, das dem aktuellen Thread zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="093ae-108">[out] When the function returns, contains a pointer to the handle of the impersonation token associated with the current thread.</span></span> <span data-ttu-id="093ae-109">Sein Wert `null` kann sein, wenn dem aktuellen Thread kein Token zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="093ae-109">Its value can be `null` if there is no token associated with the current thread.</span></span>

## <a name="return-value"></a><span data-ttu-id="093ae-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="093ae-110">Return value</span></span>

<span data-ttu-id="093ae-111">Wenn die Funktion erfolgreich ist, `S_OK` ist der Rückgabewert (0).</span><span class="sxs-lookup"><span data-stu-id="093ae-111">If the function succeeds, the return value is `S_OK` (0).</span></span>

<span data-ttu-id="093ae-112">Wenn die Funktion fehlschlägt, ist der Rückgabewert ein Fehlercode ungleich Null.</span><span class="sxs-lookup"><span data-stu-id="093ae-112">If the function fails, the return value is a non-zero error code.</span></span> <span data-ttu-id="093ae-113">Um erweiterte Fehlerinformationen zu erhalten, rufen Sie die [GetErrorInfo-Funktion](geterrorinfo.md) auf.</span><span class="sxs-lookup"><span data-stu-id="093ae-113">To get extended error information, call the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="093ae-114">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="093ae-114">Requirements</span></span>

 <span data-ttu-id="093ae-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="093ae-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

 <span data-ttu-id="093ae-116">**Kopfzeile:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="093ae-116">**Header:** WMINet_Utils.idl</span></span>

 <span data-ttu-id="093ae-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="093ae-117">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="093ae-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="093ae-118">See also</span></span>

- [<span data-ttu-id="093ae-119">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="093ae-119">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
