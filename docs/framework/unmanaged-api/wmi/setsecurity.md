---
title: SetSecurity-Funktion (Referenz zur nicht verwalteten API)
description: Die SetSecurity-Funktion Ruft das Identitätswechsel Token des aktuellen Threads ab.
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
ms.openlocfilehash: 6d27779bcfc97e1c4156b8782896e83d4754491b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120227"
---
# <a name="setsecurity-function"></a><span data-ttu-id="a7da3-103">SetSecurity-Funktion</span><span class="sxs-lookup"><span data-stu-id="a7da3-103">SetSecurity function</span></span>

<span data-ttu-id="a7da3-104">Ruft das Identitätswechseltoken ab, das dem aktuellen Thread zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="a7da3-104">Retrieves the impersonation token associated with the current thread.</span></span> 

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="a7da3-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="a7da3-105">Syntax</span></span>

```cpp
HRESULT SetSecurity (
   [out] boolean* pNeedToReset, 
   [out] HANDLE* pCurrentThreadToken
); 
```

## <a name="parameters"></a><span data-ttu-id="a7da3-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="a7da3-106">Parameters</span></span>

`pNeedToReset`\
<span data-ttu-id="a7da3-107">vorgenommen Enthält bei Rückgabe der Funktion einen Zeiger auf einen `boolean` der angibt, ob das Token durch Aufrufen der [resetsecurity](resetsecurity.md) -Funktion zurückgesetzt werden soll.</span><span class="sxs-lookup"><span data-stu-id="a7da3-107">[out] When the function returns, contains a pointer to a `boolean` that indicates whether the token should be reset by calling the [ResetSecurity](resetsecurity.md) function.</span></span>

`token`\
<span data-ttu-id="a7da3-108">vorgenommen Wenn die Funktion zurückgegeben wird, enthält Sie einen Zeiger auf das Handle des Identitätswechsel Tokens, das mit dem aktuellen Thread verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="a7da3-108">[out] When the function returns, contains a pointer to the handle of the impersonation token associated with the current thread.</span></span> <span data-ttu-id="a7da3-109">Der Wert kann `null` sein, wenn dem aktuellen Thread kein Token zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="a7da3-109">Its value can be `null` if there is no token associated with the current thread.</span></span> 

## <a name="return-value"></a><span data-ttu-id="a7da3-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="a7da3-110">Return value</span></span>

<span data-ttu-id="a7da3-111">Wenn die Funktion erfolgreich ausgeführt wird, ist der Rückgabewert `S_OK` (0).</span><span class="sxs-lookup"><span data-stu-id="a7da3-111">If the function succeeds, the return value is `S_OK` (0).</span></span>

<span data-ttu-id="a7da3-112">Wenn die Funktion fehlschlägt, ist der Rückgabewert ein Fehlercode ungleich 0 (null).</span><span class="sxs-lookup"><span data-stu-id="a7da3-112">If the function fails, the return value is a non-zero error code.</span></span> <span data-ttu-id="a7da3-113">Um erweiterte Fehlerinformationen abzurufen, wenden Sie die [GetErrorInfo](geterrorinfo.md) -Funktion an.</span><span class="sxs-lookup"><span data-stu-id="a7da3-113">To get extended error information, call the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="a7da3-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a7da3-114">Requirements</span></span>

 <span data-ttu-id="a7da3-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a7da3-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

 <span data-ttu-id="a7da3-116">**Header:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="a7da3-116">**Header:** WMINet_Utils.idl</span></span>

 <span data-ttu-id="a7da3-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="a7da3-117">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="a7da3-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a7da3-118">See also</span></span>

- [<span data-ttu-id="a7da3-119">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="a7da3-119">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
