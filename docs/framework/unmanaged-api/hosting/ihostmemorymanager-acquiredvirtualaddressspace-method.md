---
title: IHostMemoryManager::AcquiredVirtualAddressSpace-Methode
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.AcquiredVirtualAddressSpace
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::AcquiredVirtualAddressSpace
helpviewer_keywords:
- IHostMemoryManager::AcquiredVirtualAddressSpace method [.NET Framework hosting]
- AcquiredVirtualAddressSpace method [.NET Framework hosting]
ms.assetid: ef2f83c2-127e-4c38-8385-306c03cd2167
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4675c34bfe8d1d79c184c43e5f7f5dd3a03be6a3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59200999"
---
# <a name="ihostmemorymanageracquiredvirtualaddressspace-method"></a><span data-ttu-id="cb9c8-102">IHostMemoryManager::AcquiredVirtualAddressSpace-Methode</span><span class="sxs-lookup"><span data-stu-id="cb9c8-102">IHostMemoryManager::AcquiredVirtualAddressSpace Method</span></span>
<span data-ttu-id="cb9c8-103">Benachrichtigt den Host aus, die common Language Runtime (CLR) auf den angegebenen Arbeitsspeicher vom Betriebssystem abgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="cb9c8-103">Notifies the host that the common language runtime (CLR) has acquired the specified memory from the operating system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb9c8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="cb9c8-104">Syntax</span></span>  
  
```  
HRESULT AcquiredVirtualAddressSpace(  
    [in] LPVOID  startAddress,  
    [in] SIZE_T  size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cb9c8-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="cb9c8-105">Parameters</span></span>  
 `startAddress`  
 <span data-ttu-id="cb9c8-106">[in] Die Startadresse des Arbeitsspeichers.</span><span class="sxs-lookup"><span data-stu-id="cb9c8-106">[in] The starting address of the memory.</span></span>  
  
 `size`  
 <span data-ttu-id="cb9c8-107">[in] Die Größe in Bytes, des Arbeitsspeichers.</span><span class="sxs-lookup"><span data-stu-id="cb9c8-107">[in] The size, in bytes, of the memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cb9c8-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="cb9c8-108">Remarks</span></span>  
 <span data-ttu-id="cb9c8-109">Die `AcquiredVirtualAddressSpace` -Methode ist eine Rückrufmethode und muss vom Writer der hostanwendung implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="cb9c8-109">The `AcquiredVirtualAddressSpace` method is a callback method and must be implemented by the writer of the hosting application.</span></span> <span data-ttu-id="cb9c8-110">Sie wird von der CLR aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="cb9c8-110">It is called by the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cb9c8-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="cb9c8-111">Requirements</span></span>  
 <span data-ttu-id="cb9c8-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cb9c8-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cb9c8-113">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="cb9c8-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cb9c8-114">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="cb9c8-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="cb9c8-115">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="cb9c8-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="cb9c8-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cb9c8-116">See also</span></span>

- [<span data-ttu-id="cb9c8-117">IHostMemoryManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="cb9c8-117">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
