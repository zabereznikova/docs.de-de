---
title: IHostMemoryManager::ReleasedVirtualAddressSpace-Methode
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.ReleasedVirtualAddressSpace
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::ReleasedVirtualAddressSpace
helpviewer_keywords:
- ReleasedVirtualAddressSpace method [.NET Framework hosting]
- IHostMemoryManager::ReleasedVirtualAddressSpace method [.NET Framework hosting]
ms.assetid: d1876601-6ab9-48e1-8ebd-184af1d0cd76
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1b7bf2a3e359ca05a147553d89a1d2bb3d235209
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54571048"
---
# <a name="ihostmemorymanagerreleasedvirtualaddressspace-method"></a><span data-ttu-id="91afe-102">IHostMemoryManager::ReleasedVirtualAddressSpace-Methode</span><span class="sxs-lookup"><span data-stu-id="91afe-102">IHostMemoryManager::ReleasedVirtualAddressSpace Method</span></span>
<span data-ttu-id="91afe-103">Benachrichtigt den Host, dass die common Language Runtime (CLR) über den angegebenen Speicher abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="91afe-103">Notifies the host that the common language runtime (CLR) has finished using the specified memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91afe-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="91afe-104">Syntax</span></span>  
  
```  
HRESULT ReleasedVirtualAddressSpace(  
    [in] LPVOID startAddress  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="91afe-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="91afe-105">Parameters</span></span>  
 `startAddress`  
 <span data-ttu-id="91afe-106">[in] Zeiger auf die Startadresse des Arbeitsspeichers, der freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="91afe-106">[in] Pointer to the starting address of the memory to be released.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="91afe-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="91afe-107">Remarks</span></span>  
 <span data-ttu-id="91afe-108">Die `ReleasedVirtualAddressSpace` -Methode ist eine Rückrufmethode und muss vom Writer der hostanwendung implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="91afe-108">The `ReleasedVirtualAddressSpace` method is a callback method and must be implemented by the writer of the hosting application.</span></span> <span data-ttu-id="91afe-109">Sie wird von der CLR aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="91afe-109">It is called by the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="91afe-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="91afe-110">Requirements</span></span>  
 <span data-ttu-id="91afe-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="91afe-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="91afe-112">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="91afe-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="91afe-113">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="91afe-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="91afe-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="91afe-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91afe-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="91afe-115">See also</span></span>
- [<span data-ttu-id="91afe-116">IHostMemoryManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="91afe-116">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
