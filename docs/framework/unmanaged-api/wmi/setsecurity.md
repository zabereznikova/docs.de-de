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
ms.openlocfilehash: 0fd354e1103832abee7f634eace3dd6defa8b646
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33458750"
---
# <a name="setsecurity-function"></a><span data-ttu-id="b3fb8-103">SetSecurity-Funktion</span><span class="sxs-lookup"><span data-stu-id="b3fb8-103">SetSecurity function</span></span>
<span data-ttu-id="b3fb8-104">Ruft das Identitätstoken des aktuellen Threads zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="b3fb8-104">Retrieves the impersonation token associated with the current thread.</span></span>   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="b3fb8-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="b3fb8-105">Syntax</span></span>  
  
```  
HRESULT SetSecurity (
   [out] boolean* pNeedToReset, 
   [out] HANDLE* pCurrentThreadToken
); 
```  

## <a name="parameters"></a><span data-ttu-id="b3fb8-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="b3fb8-106">Parameters</span></span>

<span data-ttu-id="b3fb8-107">`pNeedToReset` [out] Bei Rückgabe der Funktion enthält einen Zeiger auf eine `boolean` , der angibt, ob das Token soll, durch Aufrufen zurückgesetzt werden der [ResetSecurity](resetsecurity.md) Funktion.</span><span class="sxs-lookup"><span data-stu-id="b3fb8-107">`pNeedToReset` [out] When the function returns, contains a pointer to a `boolean` that indicates whether the token should be reset by calling the [ResetSecurity](resetsecurity.md) function.</span></span>  

`token`  
<span data-ttu-id="b3fb8-108">[out] Wenn die Funktion zurückgibt, enthält einen Zeiger auf das Handle für das Identitätswechseltoken, das dem aktuellen Thread zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="b3fb8-108">[out] When the function returns, contains a pointer to the handle of the impersonation token associated with the current thread.</span></span> <span data-ttu-id="b3fb8-109">Der Wert kann `null` Wenn kein Token, das dem aktuellen Thread zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="b3fb8-109">Its value can be `null` if there is no token associated with the current thread.</span></span> 

## <a name="return-value"></a><span data-ttu-id="b3fb8-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="b3fb8-110">Return value</span></span>

<span data-ttu-id="b3fb8-111">Wenn die Funktion erfolgreich ausgeführt wird, ist der Rückgabewert `S_OK` (0).</span><span class="sxs-lookup"><span data-stu-id="b3fb8-111">If the function succeeds, the return value is `S_OK` (0).</span></span>

<span data-ttu-id="b3fb8-112">Wenn die Funktion fehlschlägt, ist der Rückgabewert ein Fehlercode ungleich 0 (null).</span><span class="sxs-lookup"><span data-stu-id="b3fb8-112">If the function fails, the return value is a non-zero error code.</span></span> <span data-ttu-id="b3fb8-113">Um erweiterte Fehlerinformationen abzurufen, rufen Sie die [GetErrorInfo](geterrorinfo.md) Funktion.</span><span class="sxs-lookup"><span data-stu-id="b3fb8-113">To get extended error information, call the [GetErrorInfo](geterrorinfo.md) function.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="b3fb8-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b3fb8-114">Requirements</span></span>  
 <span data-ttu-id="b3fb8-115">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b3fb8-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b3fb8-116">**Header:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="b3fb8-116">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="b3fb8-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="b3fb8-117">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3fb8-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b3fb8-118">See also</span></span>  
[<span data-ttu-id="b3fb8-119">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="b3fb8-119">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
