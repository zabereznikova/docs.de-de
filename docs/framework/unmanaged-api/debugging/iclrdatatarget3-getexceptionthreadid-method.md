---
title: ICLRDataTarget3::GetExceptionThreadID-Methode
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICLRDataTarget3.GetExceptionThreadID
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 307d6ac7-4a86-45f3-999d-6b47004a68f2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: de3606e4763596038a2c573002d774c6348071e8
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57473512"
---
# <a name="iclrdatatarget3getexceptionthreadid-method"></a><span data-ttu-id="0f08c-102">ICLRDataTarget3::GetExceptionThreadID-Methode</span><span class="sxs-lookup"><span data-stu-id="0f08c-102">ICLRDataTarget3::GetExceptionThreadID Method</span></span>
<span data-ttu-id="0f08c-103">Wird durch die Common Language Runtime (CLR)-Datenzugriffsdienste aufgerufen, um die ID des Threads abzurufen, der die Ausnahme ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="0f08c-103">Called by the common language runtime (CLR) data access services to get the ID of the thread that threw the exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f08c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0f08c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetExceptionThreadID(  
    [out] ULONG32* threadID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0f08c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="0f08c-105">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="0f08c-106">[out] Die ID des Threads, der die Ausnahme ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="0f08c-106">[out] The ID of the thread that threw the exception.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0f08c-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="0f08c-107">Return Value</span></span>  
 <span data-ttu-id="0f08c-108">Der Rückgabewert ist `S_OK` bei Erfolg oder ein Fehler-`HRESULT`-Code bei einem Fehler.</span><span class="sxs-lookup"><span data-stu-id="0f08c-108">The return value is `S_OK` on success, or a failure `HRESULT` code on failure.</span></span> <span data-ttu-id="0f08c-109">Zu den `HRESULT`-Codes können u. a. folgende Codes gehören:</span><span class="sxs-lookup"><span data-stu-id="0f08c-109">The `HRESULT` codes can include but are not limited to the following:</span></span>  
  
|<span data-ttu-id="0f08c-110">Rückgabecode</span><span class="sxs-lookup"><span data-stu-id="0f08c-110">Return code</span></span>|<span data-ttu-id="0f08c-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0f08c-111">Description</span></span>|  
|-----------------|-----------------|  
|`S_OK`|<span data-ttu-id="0f08c-112">Methode war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="0f08c-112">Method succeeded.</span></span>|  
|`HRESULT_FROM_WIN32(ERROR_NOT_FOUND)`|<span data-ttu-id="0f08c-113">Für die Ausnahme konnte keine gültige Thread-ID gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="0f08c-113">Could not find a valid thread ID for the exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0f08c-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0f08c-114">Remarks</span></span>  
 <span data-ttu-id="0f08c-115">Diese Methode wird vom Writer der Debuganwendung implementiert.</span><span class="sxs-lookup"><span data-stu-id="0f08c-115">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0f08c-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0f08c-116">Requirements</span></span>  
 <span data-ttu-id="0f08c-117">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0f08c-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0f08c-118">**Header:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="0f08c-118">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="0f08c-119">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0f08c-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0f08c-120">**.NET Framework-Versionen:** [!INCLUDE[v451_update](../../../../includes/net-current-v451-nov-plus.md)]</span><span class="sxs-lookup"><span data-stu-id="0f08c-120">**.NET Framework Versions:** [!INCLUDE[v451_update](../../../../includes/net-current-v451-nov-plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f08c-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0f08c-121">See also</span></span>
- [<span data-ttu-id="0f08c-122">ICLRDataTarget3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0f08c-122">ICLRDataTarget3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-interface.md)
- [<span data-ttu-id="0f08c-123">GetExceptionContextRecord-Methode</span><span class="sxs-lookup"><span data-stu-id="0f08c-123">GetExceptionContextRecord Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptioncontextrecord-method.md)
- [<span data-ttu-id="0f08c-124">GetExceptionRecord-Methode</span><span class="sxs-lookup"><span data-stu-id="0f08c-124">GetExceptionRecord Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptionrecord-method.md)
