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
ms.openlocfilehash: 182424632e4f81dfdf86e87dc6bb2c75c2780fce
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793763"
---
# <a name="_efn_getmanagedobjectfieldinfo-function"></a><span data-ttu-id="970c3-102">\_EFN\_getmanagedobjectfieldinfo-Funktion</span><span class="sxs-lookup"><span data-stu-id="970c3-102">\_EFN\_GetManagedObjectFieldInfo Function</span></span>
<span data-ttu-id="970c3-103">Ruft den Offset vom Beginn eines Objekts zu einem Feld sowie den Wert des Felds mit dem bereitgestellten Objektzeiger und Feldnamen ab.</span><span class="sxs-lookup"><span data-stu-id="970c3-103">Gets the offset from the start of an object to a field and the field's value, using the provided object pointer and field name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="970c3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="970c3-104">Syntax</span></span>  
  
```cpp  
HRESULT _EFN_GetManagedObjectFieldInfo(  
    [in]  PDEBUG_CLIENT Client,  
    [in]  ULONG64       objAddr,  
    [in]  __out_ecount (mdNameLen) PSTR szFieldName,  
    [out] PULONG64      pValue,  
    [out] PULONG        pOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="970c3-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="970c3-105">Parameters</span></span>  
 `Client`  
 <span data-ttu-id="970c3-106">in Ein Zeiger auf den Debugclient.</span><span class="sxs-lookup"><span data-stu-id="970c3-106">[in] A pointer to the debug client.</span></span>  
  
 `objAddr`  
 <span data-ttu-id="970c3-107">in Ein Zeiger für verwaltete Objekte.</span><span class="sxs-lookup"><span data-stu-id="970c3-107">[in] A managed object pointer.</span></span>  
  
 <span data-ttu-id="970c3-108">szFieldName</span><span class="sxs-lookup"><span data-stu-id="970c3-108">szFieldName</span></span>  
 <span data-ttu-id="970c3-109">in Ein verwalteter Objekt Zeiger auf den Feldnamen.</span><span class="sxs-lookup"><span data-stu-id="970c3-109">[in] A managed object pointer to the field name.</span></span>  
  
 `pValue`  
 <span data-ttu-id="970c3-110">vorgenommen Der Feldwert.</span><span class="sxs-lookup"><span data-stu-id="970c3-110">[out] The field value.</span></span> <span data-ttu-id="970c3-111">Dieser Parameter kann null sein.</span><span class="sxs-lookup"><span data-stu-id="970c3-111">This parameter can be null.</span></span>  
  
 `pOffset`  
 <span data-ttu-id="970c3-112">vorgenommen Der Offset von `objAddr` in das Feld.</span><span class="sxs-lookup"><span data-stu-id="970c3-112">[out] The offset from `objAddr` to the field.</span></span> <span data-ttu-id="970c3-113">Dieser Parameter kann null sein.</span><span class="sxs-lookup"><span data-stu-id="970c3-113">This parameter can be null.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="970c3-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="970c3-114">Remarks</span></span>  
 <span data-ttu-id="970c3-115">Wenn der Offset 0 (null) ist, wird kein Offset geschrieben.</span><span class="sxs-lookup"><span data-stu-id="970c3-115">If the offset is 0, no offset is written.</span></span>  
  
 <span data-ttu-id="970c3-116">Wenn im Thread derzeit kein verwalteter Code vorhanden ist, gibt die Funktion HRESULT SOS_E_NOMANAGEDCODE mit einem Einrichtungs Wert von 0xa0 und dem Fehlercode 0x1000 zurück.</span><span class="sxs-lookup"><span data-stu-id="970c3-116">If there is no managed code on the thread currently in context, the function returns HRESULT SOS_E_NOMANAGEDCODE with a facility value of 0xa0 and an error code of 0x1000.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="970c3-117">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="970c3-117">Requirements</span></span>  
 <span data-ttu-id="970c3-118">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="970c3-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="970c3-119">**Header:** SOS_Stacktrace. h</span><span class="sxs-lookup"><span data-stu-id="970c3-119">**Header:** SOS_Stacktrace.h</span></span>  
  
 <span data-ttu-id="970c3-120">**.NET Framework Version:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="970c3-120">**.NET Framework Version:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="970c3-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="970c3-121">See also</span></span>

- [<span data-ttu-id="970c3-122">Debuggen von globalen statischen Funktionen</span><span class="sxs-lookup"><span data-stu-id="970c3-122">Debugging Global Static Functions</span></span>](debugging-global-static-functions.md)
