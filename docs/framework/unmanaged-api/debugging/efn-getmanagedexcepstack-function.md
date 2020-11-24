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
ms.openlocfilehash: b86277836b1be48c9f8020d59071aba8c5b1e457
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95676230"
---
# <a name="_efn_getmanagedexcepstack-function"></a><span data-ttu-id="2b41d-102">\_EFN \_ getmanagedexcepstack-Funktion</span><span class="sxs-lookup"><span data-stu-id="2b41d-102">\_EFN\_GetManagedExcepStack Function</span></span>

<span data-ttu-id="2b41d-103">Gibt bei Angabe der Adresse eines verwalteten Ausnahmeobjekts eine Zeichenfolgenversion der enthaltenen Stapelüberwachung zurück.</span><span class="sxs-lookup"><span data-stu-id="2b41d-103">Given a managed exception object address, returns a string version of the stack trace contained inside.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b41d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2b41d-104">Syntax</span></span>  
  
```cpp  
HRESULT _EFN_GetManagedExcepStack(  
    [in]  PDEBUG_CLIENT Client,  
    [in]  ULONG64       StackObjAddr,  
    [out] __out_ecount(cbString) PSTR szStackString,  
    [out] ULONG         cbString  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2b41d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2b41d-105">Parameters</span></span>  

 `Client`  
 <span data-ttu-id="2b41d-106">in Der Client, der deentschlgt wird.</span><span class="sxs-lookup"><span data-stu-id="2b41d-106">[in] The client being debugged.</span></span>  
  
 `StackObjAddr`  
 <span data-ttu-id="2b41d-107">in Ein von abgeleiteter verwalteter Objekt Zeiger <xref:System.Exception> .</span><span class="sxs-lookup"><span data-stu-id="2b41d-107">[in] A managed object pointer, derived from <xref:System.Exception>.</span></span>  
  
 <span data-ttu-id="2b41d-108">szStackString</span><span class="sxs-lookup"><span data-stu-id="2b41d-108">szStackString</span></span>  
 <span data-ttu-id="2b41d-109">vorgenommen Die zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="2b41d-109">[out] The returned string.</span></span>  
  
 `cbString`  
 <span data-ttu-id="2b41d-110">vorgenommen Die Anzahl von Zeichen, die im Zeichen folgen Puffer verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="2b41d-110">[out] The number of characters available in the string buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2b41d-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2b41d-111">Remarks</span></span>  

 <span data-ttu-id="2b41d-112">Wenn im Thread derzeit kein verwalteter Code vorhanden ist, gibt die Funktion HRESULT SOS_E_NOMANAGEDCODE mit einem Einrichtungs Wert von 0xa0 und dem Fehlercode 0x1000 zurück.</span><span class="sxs-lookup"><span data-stu-id="2b41d-112">If there is no managed code on the thread currently in context, the function returns HRESULT SOS_E_NOMANAGEDCODE with a facility value of 0xa0 and an error code of 0x1000.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2b41d-113">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="2b41d-113">Requirements</span></span>  

 <span data-ttu-id="2b41d-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2b41d-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2b41d-115">**Header:** SOS_Stacktrace. h</span><span class="sxs-lookup"><span data-stu-id="2b41d-115">**Header:** SOS_Stacktrace.h</span></span>  
  
 <span data-ttu-id="2b41d-116">**.NET Framework Version:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2b41d-116">**.NET Framework Version:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b41d-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2b41d-117">See also</span></span>

- [<span data-ttu-id="2b41d-118">Debuggen von globalen statischen Funktionen</span><span class="sxs-lookup"><span data-stu-id="2b41d-118">Debugging Global Static Functions</span></span>](debugging-global-static-functions.md)
