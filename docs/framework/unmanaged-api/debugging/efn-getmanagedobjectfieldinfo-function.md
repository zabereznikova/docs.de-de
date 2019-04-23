---
title: _EFN_GetManagedObjectFieldInfo-Funktion
ms.date: 03/30/2017
api_name:
- _EFN_GetManagedObjectFieldInfo
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- _EFN_GetManagedObjectFieldInfo
helpviewer_keywords:
- _EFN_GetManagedObjectFieldInfo function [.NET Framework debugging]
ms.assetid: 3b93bcff-62a4-47b2-babc-6bcf4216119a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9e7d031d4a4f4e67134f4b88f3e3ff47316ce3b5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59183143"
---
# <a name="efngetmanagedobjectfieldinfo-function"></a><span data-ttu-id="a061c-102">_EFN_GetManagedObjectFieldInfo-Funktion</span><span class="sxs-lookup"><span data-stu-id="a061c-102">_EFN_GetManagedObjectFieldInfo Function</span></span>
<span data-ttu-id="a061c-103">Ruft den Offset vom Beginn eines Objekts zu einem Feld sowie den Wert des Felds mit dem bereitgestellten Objektzeiger und Feldnamen ab.</span><span class="sxs-lookup"><span data-stu-id="a061c-103">Gets the offset from the start of an object to a field and the field's value, using the provided object pointer and field name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a061c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a061c-104">Syntax</span></span>  
  
```  
HRESULT _EFN_GetManagedObjectFieldInfo(  
    [in]  PDEBUG_CLIENT Client,  
    [in]  ULONG64       objAddr,  
    [in]  __out_ecount (mdNameLen) PSTR szFieldName,  
    [out] PULONG64      pValue,  
    [out] PULONG        pOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a061c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a061c-105">Parameters</span></span>  
 `Client`  
 <span data-ttu-id="a061c-106">[in] Ein Zeiger auf den Client Debuggen.</span><span class="sxs-lookup"><span data-stu-id="a061c-106">[in] A pointer to the debug client.</span></span>  
  
 `objAddr`  
 <span data-ttu-id="a061c-107">[in] Ein Zeiger des verwalteten Objekts.</span><span class="sxs-lookup"><span data-stu-id="a061c-107">[in] A managed object pointer.</span></span>  
  
 <span data-ttu-id="a061c-108">szFieldName</span><span class="sxs-lookup"><span data-stu-id="a061c-108">szFieldName</span></span>  
 <span data-ttu-id="a061c-109">[in] Ein verwaltetes Objektzeiger auf den Namen des Felds.</span><span class="sxs-lookup"><span data-stu-id="a061c-109">[in] A managed object pointer to the field name.</span></span>  
  
 `pValue`  
 <span data-ttu-id="a061c-110">[out] Der Wert des Felds.</span><span class="sxs-lookup"><span data-stu-id="a061c-110">[out] The field value.</span></span> <span data-ttu-id="a061c-111">Dieser Parameter kann NULL sein.</span><span class="sxs-lookup"><span data-stu-id="a061c-111">This parameter can be null.</span></span>  
  
 `pOffset`  
 <span data-ttu-id="a061c-112">[out] Der Offset vom `objAddr` auf das Feld.</span><span class="sxs-lookup"><span data-stu-id="a061c-112">[out] The offset from `objAddr` to the field.</span></span> <span data-ttu-id="a061c-113">Dieser Parameter kann NULL sein.</span><span class="sxs-lookup"><span data-stu-id="a061c-113">This parameter can be null.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a061c-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a061c-114">Remarks</span></span>  
 <span data-ttu-id="a061c-115">Wenn der Offset 0 ist, wird kein Offset geschrieben.</span><span class="sxs-lookup"><span data-stu-id="a061c-115">If the offset is 0, no offset is written.</span></span>  
  
 <span data-ttu-id="a061c-116">Es ist kein verwalteter Code für den Thread aktuell im Kontext, gibt die Funktion HRESULT SOS_E_NOMANAGEDCODE mit einer Funktion 0xa0 und Fehlercode 0 x 1000 zurück.</span><span class="sxs-lookup"><span data-stu-id="a061c-116">If there is no managed code on the thread currently in context, the function returns HRESULT SOS_E_NOMANAGEDCODE with a facility value of 0xa0 and an error code of 0x1000.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a061c-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a061c-117">Requirements</span></span>  
 <span data-ttu-id="a061c-118">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a061c-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a061c-119">**Header:** SOS_Stacktrace.h</span><span class="sxs-lookup"><span data-stu-id="a061c-119">**Header:** SOS_Stacktrace.h</span></span>  
  
 <span data-ttu-id="a061c-120">**.NET Framework Version:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a061c-120">**.NET Framework Version:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a061c-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a061c-121">See also</span></span>

- [<span data-ttu-id="a061c-122">Debuggen von globalen statischen Funktionen</span><span class="sxs-lookup"><span data-stu-id="a061c-122">Debugging Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)
