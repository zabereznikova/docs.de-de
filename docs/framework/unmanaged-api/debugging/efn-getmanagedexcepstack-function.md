---
title: _EFN_GetManagedExcepStack-Funktion
ms.date: 03/30/2017
api_name:
- _EFN_GetManagedExcepStack
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- _EFN_GetManagedExcepStack
helpviewer_keywords:
- _EFN_GetManagedExcepStack function [.NET Framework debugging]
ms.assetid: 21ceed9e-62b2-4024-b027-6d095109955a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7e201b9a350c030da59e2b6ed27f84f570c8e621
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59126658"
---
# <a name="efngetmanagedexcepstack-function"></a><span data-ttu-id="2e8c0-102">_EFN_GetManagedExcepStack-Funktion</span><span class="sxs-lookup"><span data-stu-id="2e8c0-102">_EFN_GetManagedExcepStack Function</span></span>
<span data-ttu-id="2e8c0-103">Gibt bei Angabe der Adresse eines verwalteten Ausnahmeobjekts eine Zeichenfolgenversion der enthaltenen Stapelüberwachung zurück.</span><span class="sxs-lookup"><span data-stu-id="2e8c0-103">Given a managed exception object address, returns a string version of the stack trace contained inside.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e8c0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2e8c0-104">Syntax</span></span>  
  
```  
HRESULT _EFN_GetManagedExcepStack(  
    [in]  PDEBUG_CLIENT Client,  
    [in]  ULONG64       StackObjAddr,  
    [out] __out_ecount(cbString) PSTR szStackString,  
    [out] ULONG         cbString  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2e8c0-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2e8c0-105">Parameters</span></span>  
 `Client`  
 <span data-ttu-id="2e8c0-106">[in] Der Client, der gedebuggt wird.</span><span class="sxs-lookup"><span data-stu-id="2e8c0-106">[in] The client being debugged.</span></span>  
  
 `StackObjAddr`  
 <span data-ttu-id="2e8c0-107">[in] Ein Zeiger des verwalteten Objekts abgeleitet <xref:System.Exception>.</span><span class="sxs-lookup"><span data-stu-id="2e8c0-107">[in] A managed object pointer, derived from <xref:System.Exception>.</span></span>  
  
 <span data-ttu-id="2e8c0-108">szStackString</span><span class="sxs-lookup"><span data-stu-id="2e8c0-108">szStackString</span></span>  
 <span data-ttu-id="2e8c0-109">[out] Die zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="2e8c0-109">[out] The returned string.</span></span>  
  
 `cbString`  
 <span data-ttu-id="2e8c0-110">[out] Die Anzahl der Zeichen in den Puffer verfügbar.</span><span class="sxs-lookup"><span data-stu-id="2e8c0-110">[out] The number of characters available in the string buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2e8c0-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2e8c0-111">Remarks</span></span>  
 <span data-ttu-id="2e8c0-112">Es ist kein verwalteter Code für den Thread aktuell im Kontext, gibt die Funktion HRESULT SOS_E_NOMANAGEDCODE mit einer Funktion 0xa0 und Fehlercode 0 x 1000 zurück.</span><span class="sxs-lookup"><span data-stu-id="2e8c0-112">If there is no managed code on the thread currently in context, the function returns HRESULT SOS_E_NOMANAGEDCODE with a facility value of 0xa0 and an error code of 0x1000.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2e8c0-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2e8c0-113">Requirements</span></span>  
 <span data-ttu-id="2e8c0-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2e8c0-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2e8c0-115">**Header:** SOS_Stacktrace.h</span><span class="sxs-lookup"><span data-stu-id="2e8c0-115">**Header:** SOS_Stacktrace.h</span></span>  
  
 <span data-ttu-id="2e8c0-116">**.NET Framework Version:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2e8c0-116">**.NET Framework Version:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e8c0-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2e8c0-117">See also</span></span>

- [<span data-ttu-id="2e8c0-118">Debuggen von globalen statischen Funktionen</span><span class="sxs-lookup"><span data-stu-id="2e8c0-118">Debugging Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)
