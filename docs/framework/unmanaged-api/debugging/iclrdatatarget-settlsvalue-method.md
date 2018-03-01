---
title: ICLRDataTarget::SetTLSValue-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICLRDataTarget.SetTLSValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::SetTLSValue
helpviewer_keywords:
- ICLRDataTarget::SetTLSValue method [.NET Framework debugging]
- SetTLSValue method [.NET Framework debugging]
ms.assetid: 4a2d6a24-749a-47ad-9f01-4517203d3f35
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4d63f20c3a5c90fab2347ea56a8adedc6b8dc5e0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="iclrdatatargetsettlsvalue-method"></a><span data-ttu-id="b8376-102">ICLRDataTarget::SetTLSValue-Methode</span><span class="sxs-lookup"><span data-stu-id="b8376-102">ICLRDataTarget::SetTLSValue Method</span></span>
<span data-ttu-id="b8376-103">Legt einen Wert in den lokalen Threadspeicher (TLS) des angegebenen Threads im Zielprozess.</span><span class="sxs-lookup"><span data-stu-id="b8376-103">Sets a value in the thread local storage (TLS) of the specified thread in the target process.</span></span> <span data-ttu-id="b8376-104">Diese Methode wird von den Datenzugriffsdiensten der common Language Runtime (CLR) aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="b8376-104">This method is called by the common language runtime (CLR) data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8376-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="b8376-105">Syntax</span></span>  
  
```  
HRESULT SetTLSValue (  
    [in] ULONG32            threadID,  
    [in] ULONG32            index,  
    [in] CLRDATA_ADDRESS    value  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b8376-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="b8376-106">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="b8376-107">[in] Der Betriebssystem-Bezeichner eines Threads im Zielprozess.</span><span class="sxs-lookup"><span data-stu-id="b8376-107">[in] The operating system identifier of a thread in the target process.</span></span>  
  
 `index`  
 <span data-ttu-id="b8376-108">[in] Der Index der Position.</span><span class="sxs-lookup"><span data-stu-id="b8376-108">[in] The index of the location.</span></span> <span data-ttu-id="b8376-109">Dieser Wert muss ein gültiger Index in den lokalen Speicher des angegebenen Threads.</span><span class="sxs-lookup"><span data-stu-id="b8376-109">This value must be a valid index in the local store of the specified thread.</span></span>  
  
 `value`  
 <span data-ttu-id="b8376-110">[in] Ein `CLRDATA_ADDRESS` Wert, der angibt, den Wert, der in den angegebenen TLS-Speicherort zu platzieren.</span><span class="sxs-lookup"><span data-stu-id="b8376-110">[in] A `CLRDATA_ADDRESS` value that specifies the value to place in the given TLS location.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b8376-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b8376-111">Remarks</span></span>  
 <span data-ttu-id="b8376-112">Diese Methode wird vom Writer der Debuganwendung implementiert.</span><span class="sxs-lookup"><span data-stu-id="b8376-112">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b8376-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b8376-113">Requirements</span></span>  
 <span data-ttu-id="b8376-114">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b8376-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b8376-115">**Header:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="b8376-115">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="b8376-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b8376-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b8376-117">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b8376-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8376-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b8376-118">See Also</span></span>  
 [<span data-ttu-id="b8376-119">ICLRDataTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b8376-119">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
