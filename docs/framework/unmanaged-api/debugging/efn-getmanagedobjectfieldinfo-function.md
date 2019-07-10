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
ms.openlocfilehash: c1de0b3b05d38c1fec38b9436c653973dfaa4136
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67739003"
---
# <a name="efngetmanagedobjectfieldinfo-function"></a><span data-ttu-id="edad0-102">\_EFN\_GetManagedObjectFieldInfo-Funktion</span><span class="sxs-lookup"><span data-stu-id="edad0-102">\_EFN\_GetManagedObjectFieldInfo Function</span></span>
<span data-ttu-id="edad0-103">Ruft den Offset vom Beginn eines Objekts zu einem Feld sowie den Wert des Felds mit dem bereitgestellten Objektzeiger und Feldnamen ab.</span><span class="sxs-lookup"><span data-stu-id="edad0-103">Gets the offset from the start of an object to a field and the field's value, using the provided object pointer and field name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="edad0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="edad0-104">Syntax</span></span>  
  
```cpp  
HRESULT _EFN_GetManagedObjectFieldInfo(  
    [in]  PDEBUG_CLIENT Client,  
    [in]  ULONG64       objAddr,  
    [in]  __out_ecount (mdNameLen) PSTR szFieldName,  
    [out] PULONG64      pValue,  
    [out] PULONG        pOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="edad0-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="edad0-105">Parameters</span></span>  
 `Client`  
 <span data-ttu-id="edad0-106">[in] Ein Zeiger auf den Client Debuggen.</span><span class="sxs-lookup"><span data-stu-id="edad0-106">[in] A pointer to the debug client.</span></span>  
  
 `objAddr`  
 <span data-ttu-id="edad0-107">[in] Ein Zeiger des verwalteten Objekts.</span><span class="sxs-lookup"><span data-stu-id="edad0-107">[in] A managed object pointer.</span></span>  
  
 <span data-ttu-id="edad0-108">szFieldName</span><span class="sxs-lookup"><span data-stu-id="edad0-108">szFieldName</span></span>  
 <span data-ttu-id="edad0-109">[in] Ein verwaltetes Objektzeiger auf den Namen des Felds.</span><span class="sxs-lookup"><span data-stu-id="edad0-109">[in] A managed object pointer to the field name.</span></span>  
  
 `pValue`  
 <span data-ttu-id="edad0-110">[out] Der Wert des Felds.</span><span class="sxs-lookup"><span data-stu-id="edad0-110">[out] The field value.</span></span> <span data-ttu-id="edad0-111">Dieser Parameter kann NULL sein.</span><span class="sxs-lookup"><span data-stu-id="edad0-111">This parameter can be null.</span></span>  
  
 `pOffset`  
 <span data-ttu-id="edad0-112">[out] Der Offset vom `objAddr` auf das Feld.</span><span class="sxs-lookup"><span data-stu-id="edad0-112">[out] The offset from `objAddr` to the field.</span></span> <span data-ttu-id="edad0-113">Dieser Parameter kann NULL sein.</span><span class="sxs-lookup"><span data-stu-id="edad0-113">This parameter can be null.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="edad0-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="edad0-114">Remarks</span></span>  
 <span data-ttu-id="edad0-115">Wenn der Offset 0 ist, wird kein Offset geschrieben.</span><span class="sxs-lookup"><span data-stu-id="edad0-115">If the offset is 0, no offset is written.</span></span>  
  
 <span data-ttu-id="edad0-116">Es ist kein verwalteter Code für den Thread aktuell im Kontext, gibt die Funktion HRESULT SOS_E_NOMANAGEDCODE mit einer Funktion 0xa0 und Fehlercode 0 x 1000 zurück.</span><span class="sxs-lookup"><span data-stu-id="edad0-116">If there is no managed code on the thread currently in context, the function returns HRESULT SOS_E_NOMANAGEDCODE with a facility value of 0xa0 and an error code of 0x1000.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="edad0-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="edad0-117">Requirements</span></span>  
 <span data-ttu-id="edad0-118">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="edad0-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="edad0-119">**Header:** SOS_Stacktrace.h</span><span class="sxs-lookup"><span data-stu-id="edad0-119">**Header:** SOS_Stacktrace.h</span></span>  
  
 <span data-ttu-id="edad0-120">**.NET Framework Version:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="edad0-120">**.NET Framework Version:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="edad0-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="edad0-121">See also</span></span>

- [<span data-ttu-id="edad0-122">Debuggen von globalen statischen Funktionen</span><span class="sxs-lookup"><span data-stu-id="edad0-122">Debugging Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)
