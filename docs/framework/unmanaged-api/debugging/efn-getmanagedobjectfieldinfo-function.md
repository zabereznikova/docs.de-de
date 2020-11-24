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
ms.openlocfilehash: 4c088b7e1096f8b4cad11a3e27b4045e233989ae
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95676217"
---
# <a name="_efn_getmanagedobjectfieldinfo-function"></a><span data-ttu-id="0a0f2-102">\_EFN \_ getmanagedobjectfieldinfo-Funktion</span><span class="sxs-lookup"><span data-stu-id="0a0f2-102">\_EFN\_GetManagedObjectFieldInfo Function</span></span>

<span data-ttu-id="0a0f2-103">Ruft den Offset vom Beginn eines Objekts zu einem Feld sowie den Wert des Felds mit dem bereitgestellten Objektzeiger und Feldnamen ab.</span><span class="sxs-lookup"><span data-stu-id="0a0f2-103">Gets the offset from the start of an object to a field and the field's value, using the provided object pointer and field name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a0f2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0a0f2-104">Syntax</span></span>  
  
```cpp  
HRESULT _EFN_GetManagedObjectFieldInfo(  
    [in]  PDEBUG_CLIENT Client,  
    [in]  ULONG64       objAddr,  
    [in]  __out_ecount (mdNameLen) PSTR szFieldName,  
    [out] PULONG64      pValue,  
    [out] PULONG        pOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0a0f2-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="0a0f2-105">Parameters</span></span>  

 `Client`  
 <span data-ttu-id="0a0f2-106">in Ein Zeiger auf den Debugclient.</span><span class="sxs-lookup"><span data-stu-id="0a0f2-106">[in] A pointer to the debug client.</span></span>  
  
 `objAddr`  
 <span data-ttu-id="0a0f2-107">in Ein Zeiger für verwaltete Objekte.</span><span class="sxs-lookup"><span data-stu-id="0a0f2-107">[in] A managed object pointer.</span></span>  
  
 <span data-ttu-id="0a0f2-108">szFieldName</span><span class="sxs-lookup"><span data-stu-id="0a0f2-108">szFieldName</span></span>  
 <span data-ttu-id="0a0f2-109">in Ein verwalteter Objekt Zeiger auf den Feldnamen.</span><span class="sxs-lookup"><span data-stu-id="0a0f2-109">[in] A managed object pointer to the field name.</span></span>  
  
 `pValue`  
 <span data-ttu-id="0a0f2-110">vorgenommen Der Feldwert.</span><span class="sxs-lookup"><span data-stu-id="0a0f2-110">[out] The field value.</span></span> <span data-ttu-id="0a0f2-111">Dieser Parameter kann NULL sein.</span><span class="sxs-lookup"><span data-stu-id="0a0f2-111">This parameter can be null.</span></span>  
  
 `pOffset`  
 <span data-ttu-id="0a0f2-112">vorgenommen Der Offset von `objAddr` bis zum-Feld.</span><span class="sxs-lookup"><span data-stu-id="0a0f2-112">[out] The offset from `objAddr` to the field.</span></span> <span data-ttu-id="0a0f2-113">Dieser Parameter kann NULL sein.</span><span class="sxs-lookup"><span data-stu-id="0a0f2-113">This parameter can be null.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0a0f2-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0a0f2-114">Remarks</span></span>  

 <span data-ttu-id="0a0f2-115">Wenn der Offset 0 (null) ist, wird kein Offset geschrieben.</span><span class="sxs-lookup"><span data-stu-id="0a0f2-115">If the offset is 0, no offset is written.</span></span>  
  
 <span data-ttu-id="0a0f2-116">Wenn im Thread derzeit kein verwalteter Code vorhanden ist, gibt die Funktion HRESULT SOS_E_NOMANAGEDCODE mit einem Einrichtungs Wert von 0xa0 und dem Fehlercode 0x1000 zurück.</span><span class="sxs-lookup"><span data-stu-id="0a0f2-116">If there is no managed code on the thread currently in context, the function returns HRESULT SOS_E_NOMANAGEDCODE with a facility value of 0xa0 and an error code of 0x1000.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0a0f2-117">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="0a0f2-117">Requirements</span></span>  

 <span data-ttu-id="0a0f2-118">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0a0f2-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0a0f2-119">**Header:** SOS_Stacktrace. h</span><span class="sxs-lookup"><span data-stu-id="0a0f2-119">**Header:** SOS_Stacktrace.h</span></span>  
  
 <span data-ttu-id="0a0f2-120">**.NET Framework Version:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0a0f2-120">**.NET Framework Version:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a0f2-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0a0f2-121">See also</span></span>

- [<span data-ttu-id="0a0f2-122">Debuggen von globalen statischen Funktionen</span><span class="sxs-lookup"><span data-stu-id="0a0f2-122">Debugging Global Static Functions</span></span>](debugging-global-static-functions.md)
