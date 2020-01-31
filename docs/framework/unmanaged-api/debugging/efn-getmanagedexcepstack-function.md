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
ms.openlocfilehash: 824be4a401d265575b48f66045dd944d521e64a4
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789155"
---
# <a name="_efn_getmanagedexcepstack-function"></a><span data-ttu-id="58d77-102">\_EFN\_getmanagedexcepstack-Funktion</span><span class="sxs-lookup"><span data-stu-id="58d77-102">\_EFN\_GetManagedExcepStack Function</span></span>
<span data-ttu-id="58d77-103">Gibt bei Angabe der Adresse eines verwalteten Ausnahmeobjekts eine Zeichenfolgenversion der enthaltenen Stapelüberwachung zurück.</span><span class="sxs-lookup"><span data-stu-id="58d77-103">Given a managed exception object address, returns a string version of the stack trace contained inside.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58d77-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="58d77-104">Syntax</span></span>  
  
```cpp  
HRESULT _EFN_GetManagedExcepStack(  
    [in]  PDEBUG_CLIENT Client,  
    [in]  ULONG64       StackObjAddr,  
    [out] __out_ecount(cbString) PSTR szStackString,  
    [out] ULONG         cbString  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="58d77-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="58d77-105">Parameters</span></span>  
 `Client`  
 <span data-ttu-id="58d77-106">in Der Client, der deentschlgt wird.</span><span class="sxs-lookup"><span data-stu-id="58d77-106">[in] The client being debugged.</span></span>  
  
 `StackObjAddr`  
 <span data-ttu-id="58d77-107">in Ein von <xref:System.Exception>abgeleiteter verwalteter Objekt Zeiger.</span><span class="sxs-lookup"><span data-stu-id="58d77-107">[in] A managed object pointer, derived from <xref:System.Exception>.</span></span>  
  
 <span data-ttu-id="58d77-108">szStackString</span><span class="sxs-lookup"><span data-stu-id="58d77-108">szStackString</span></span>  
 <span data-ttu-id="58d77-109">vorgenommen Die zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="58d77-109">[out] The returned string.</span></span>  
  
 `cbString`  
 <span data-ttu-id="58d77-110">vorgenommen Die Anzahl von Zeichen, die im Zeichen folgen Puffer verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="58d77-110">[out] The number of characters available in the string buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="58d77-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="58d77-111">Remarks</span></span>  
 <span data-ttu-id="58d77-112">Wenn im Thread derzeit kein verwalteter Code vorhanden ist, gibt die Funktion HRESULT SOS_E_NOMANAGEDCODE mit einem Einrichtungs Wert von 0xa0 und dem Fehlercode 0x1000 zurück.</span><span class="sxs-lookup"><span data-stu-id="58d77-112">If there is no managed code on the thread currently in context, the function returns HRESULT SOS_E_NOMANAGEDCODE with a facility value of 0xa0 and an error code of 0x1000.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="58d77-113">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="58d77-113">Requirements</span></span>  
 <span data-ttu-id="58d77-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="58d77-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="58d77-115">**Header:** SOS_Stacktrace. h</span><span class="sxs-lookup"><span data-stu-id="58d77-115">**Header:** SOS_Stacktrace.h</span></span>  
  
 <span data-ttu-id="58d77-116">**.NET Framework Version:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="58d77-116">**.NET Framework Version:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58d77-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="58d77-117">See also</span></span>

- [<span data-ttu-id="58d77-118">Debuggen von globalen statischen Funktionen</span><span class="sxs-lookup"><span data-stu-id="58d77-118">Debugging Global Static Functions</span></span>](debugging-global-static-functions.md)
