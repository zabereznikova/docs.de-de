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
ms.openlocfilehash: ccb5cda11a2466496a4b3981e8185cbb7130f66f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122898"
---
# <a name="iclrdatatargetgetcurrentthreadid-method"></a><span data-ttu-id="ea8fa-102">ICLRDataTarget::GetCurrentThreadID-Methode</span><span class="sxs-lookup"><span data-stu-id="ea8fa-102">ICLRDataTarget::GetCurrentThreadID Method</span></span>
<span data-ttu-id="ea8fa-103">Ruft den Betriebssystem Bezeichner für den aktuellen Thread ab.</span><span class="sxs-lookup"><span data-stu-id="ea8fa-103">Gets the operating system identifier for the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea8fa-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ea8fa-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentThreadID (  
    [out] ULONG32    *threadID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ea8fa-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ea8fa-105">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="ea8fa-106">vorgenommen Ein Zeiger auf den Betriebssystem Bezeichner des aktuellen Threads für den Ziel Prozess.</span><span class="sxs-lookup"><span data-stu-id="ea8fa-106">[out] A pointer to the operating system identifier of the current thread for the target process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ea8fa-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ea8fa-107">Remarks</span></span>  
 <span data-ttu-id="ea8fa-108">Wenn es keinen aktuellen Thread für den Ziel Prozess gibt, schlägt die `GetCurrentThreadID` Methode möglicherweise fehl.</span><span class="sxs-lookup"><span data-stu-id="ea8fa-108">If there is no current thread for the target process, the `GetCurrentThreadID` method may fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ea8fa-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ea8fa-109">Requirements</span></span>  
 <span data-ttu-id="ea8fa-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ea8fa-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ea8fa-111">**Header:** Clrdata. idl, Clrdata. h</span><span class="sxs-lookup"><span data-stu-id="ea8fa-111">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="ea8fa-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ea8fa-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ea8fa-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ea8fa-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea8fa-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ea8fa-114">See also</span></span>

- [<span data-ttu-id="ea8fa-115">ICLRDataTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ea8fa-115">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
