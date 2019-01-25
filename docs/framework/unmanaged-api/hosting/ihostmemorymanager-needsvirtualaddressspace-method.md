---
title: IHostMemoryManager::NeedsVirtualAddressSpace-Methode
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.NeedsVirtualAddressSpace
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::NeedsVirtualAddressSpace
helpviewer_keywords:
- IHostMemoryManager::NeedsVirtualAddressSpace method [.NET Framework hosting]
- NeedsVirtualAddressSpace method [.NET Framework hosting]
ms.assetid: 71f0eab5-0170-46f8-9f88-1df5abdeb34a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c4a67e1eb5a257cc6d4e4c9bc8798b61c97fba38
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54661749"
---
# <a name="ihostmemorymanagerneedsvirtualaddressspace-method"></a><span data-ttu-id="528fc-102">IHostMemoryManager::NeedsVirtualAddressSpace-Methode</span><span class="sxs-lookup"><span data-stu-id="528fc-102">IHostMemoryManager::NeedsVirtualAddressSpace Method</span></span>
<span data-ttu-id="528fc-103">Benachrichtigt den Host, dass die common Language Runtime (CLR) wird versuchen, den angegebenen Speicher zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="528fc-103">Notifies the host that the common language runtime (CLR) is going to attempt to use the specified memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="528fc-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="528fc-104">Syntax</span></span>  
  
```  
HRESULT NeedsVirtualAddressSpace (  
    [in] LPVOID  startAddress,  
    [in] SIZE_T  size  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="528fc-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="528fc-105">Parameters</span></span>  
 `startAddress`  
 <span data-ttu-id="528fc-106">[in] Die Startadresse des Arbeitsspeichers.</span><span class="sxs-lookup"><span data-stu-id="528fc-106">[in] The starting address of the memory.</span></span>  
  
 `size`  
 <span data-ttu-id="528fc-107">[in] Die Größe in Bytes, des Arbeitsspeichers.</span><span class="sxs-lookup"><span data-stu-id="528fc-107">[in] The size, in bytes, of the memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="528fc-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="528fc-108">Remarks</span></span>  
 <span data-ttu-id="528fc-109">Die `NeedsVirtualAddressSpace` -Methode ist eine Rückrufmethode und muss vom Writer der hostanwendung implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="528fc-109">The `NeedsVirtualAddressSpace` method is a callback method and must be implemented by the writer of the hosting application.</span></span> <span data-ttu-id="528fc-110">Sie wird von der CLR aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="528fc-110">It is called by the CLR.</span></span>  
  
 <span data-ttu-id="528fc-111">Wenn der Host die CLR mit den angegebenen Arbeitsspeicher nicht möchte, wird möglicherweise ein HRESULT E_OUTOFMEMORY zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="528fc-111">If the host does not want the CLR to use the specified memory, it may return an E_OUTOFMEMORY HRESULT.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="528fc-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="528fc-112">Requirements</span></span>  
 <span data-ttu-id="528fc-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="528fc-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="528fc-114">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="528fc-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="528fc-115">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="528fc-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="528fc-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="528fc-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="528fc-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="528fc-117">See also</span></span>
- [<span data-ttu-id="528fc-118">IHostMemoryManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="528fc-118">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
