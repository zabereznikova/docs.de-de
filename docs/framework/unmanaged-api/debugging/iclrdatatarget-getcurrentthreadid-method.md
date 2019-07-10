---
title: ICLRDataTarget::GetCurrentThreadID-Methode
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.GetCurrentThreadID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::GetCurrentThreadID
helpviewer_keywords:
- GetCurrentThreadID method, ICLRDataTarget interface [.NET Framework debugging]
- ICLRDataTarget::GetCurrentThreadID method [.NET Framework debugging]
ms.assetid: dc9a0a6c-d592-4fb7-86ed-62684da3b0e1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 45a409bda8861701e68d3ea1a956a4c35ce88ddd
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67738780"
---
# <a name="iclrdatatargetgetcurrentthreadid-method"></a><span data-ttu-id="2b932-102">ICLRDataTarget::GetCurrentThreadID-Methode</span><span class="sxs-lookup"><span data-stu-id="2b932-102">ICLRDataTarget::GetCurrentThreadID Method</span></span>
<span data-ttu-id="2b932-103">Ruft den Bezeichner für den aktuellen Thread ab.</span><span class="sxs-lookup"><span data-stu-id="2b932-103">Gets the operating system identifier for the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b932-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2b932-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentThreadID (  
    [out] ULONG32    *threadID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2b932-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2b932-105">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="2b932-106">[out] Ein Zeiger auf die Betriebssystem-ID des aktuellen Threads für den Zielprozess.</span><span class="sxs-lookup"><span data-stu-id="2b932-106">[out] A pointer to the operating system identifier of the current thread for the target process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2b932-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2b932-107">Remarks</span></span>  
 <span data-ttu-id="2b932-108">Es ist kein aktueller Thread für den Zielprozess die `GetCurrentThreadID` -Methode schlägt möglicherweise fehl.</span><span class="sxs-lookup"><span data-stu-id="2b932-108">If there is no current thread for the target process, the `GetCurrentThreadID` method may fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2b932-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2b932-109">Requirements</span></span>  
 <span data-ttu-id="2b932-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2b932-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2b932-111">**Header:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="2b932-111">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="2b932-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2b932-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2b932-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2b932-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b932-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2b932-114">See also</span></span>

- [<span data-ttu-id="2b932-115">ICLRDataTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2b932-115">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
