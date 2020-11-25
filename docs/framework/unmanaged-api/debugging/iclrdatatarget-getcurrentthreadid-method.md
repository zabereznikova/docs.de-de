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
ms.openlocfilehash: 3a355822710394e9351f10be78dea283e2e9907c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95703590"
---
# <a name="iclrdatatargetgetcurrentthreadid-method"></a><span data-ttu-id="2bab0-102">ICLRDataTarget::GetCurrentThreadID-Methode</span><span class="sxs-lookup"><span data-stu-id="2bab0-102">ICLRDataTarget::GetCurrentThreadID Method</span></span>

<span data-ttu-id="2bab0-103">Ruft den Betriebssystem Bezeichner für den aktuellen Thread ab.</span><span class="sxs-lookup"><span data-stu-id="2bab0-103">Gets the operating system identifier for the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2bab0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2bab0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentThreadID (  
    [out] ULONG32    *threadID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2bab0-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2bab0-105">Parameters</span></span>  

 `threadID`  
 <span data-ttu-id="2bab0-106">vorgenommen Ein Zeiger auf den Betriebssystem Bezeichner des aktuellen Threads für den Ziel Prozess.</span><span class="sxs-lookup"><span data-stu-id="2bab0-106">[out] A pointer to the operating system identifier of the current thread for the target process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2bab0-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2bab0-107">Remarks</span></span>  

 <span data-ttu-id="2bab0-108">Wenn es keinen aktuellen Thread für den Ziel Prozess gibt, `GetCurrentThreadID` schlägt die Methode möglicherweise fehl.</span><span class="sxs-lookup"><span data-stu-id="2bab0-108">If there is no current thread for the target process, the `GetCurrentThreadID` method may fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2bab0-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="2bab0-109">Requirements</span></span>  

 <span data-ttu-id="2bab0-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2bab0-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2bab0-111">**Header:** Clrdata. idl, Clrdata. h</span><span class="sxs-lookup"><span data-stu-id="2bab0-111">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="2bab0-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2bab0-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2bab0-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2bab0-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2bab0-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2bab0-114">See also</span></span>

- [<span data-ttu-id="2bab0-115">ICLRDataTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2bab0-115">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
