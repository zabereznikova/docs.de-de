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
ms.openlocfilehash: d93c50968192a7789cbf08968d7ec272c9775d6f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33438512"
---
# <a name="ihostmemorymanageracquiredvirtualaddressspace-method"></a><span data-ttu-id="bc151-102">IHostMemoryManager::AcquiredVirtualAddressSpace-Methode</span><span class="sxs-lookup"><span data-stu-id="bc151-102">IHostMemoryManager::AcquiredVirtualAddressSpace Method</span></span>
<span data-ttu-id="bc151-103">Benachrichtigt den Host, dass die common Language Runtime (CLR) auf den angegebenen Arbeitsspeicher vom Betriebssystem abgerufen wurden.</span><span class="sxs-lookup"><span data-stu-id="bc151-103">Notifies the host that the common language runtime (CLR) has acquired the specified memory from the operating system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc151-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="bc151-104">Syntax</span></span>  
  
```  
HRESULT AcquiredVirtualAddressSpace(  
    [in] LPVOID  startAddress,  
    [in] SIZE_T  size  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bc151-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="bc151-105">Parameters</span></span>  
 `startAddress`  
 <span data-ttu-id="bc151-106">[in] Die Startadresse des Arbeitsspeichers.</span><span class="sxs-lookup"><span data-stu-id="bc151-106">[in] The starting address of the memory.</span></span>  
  
 `size`  
 <span data-ttu-id="bc151-107">[in] Die Größe in Bytes, des Arbeitsspeichers.</span><span class="sxs-lookup"><span data-stu-id="bc151-107">[in] The size, in bytes, of the memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bc151-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="bc151-108">Remarks</span></span>  
 <span data-ttu-id="bc151-109">Die `AcquiredVirtualAddressSpace` Methode ist eine Rückrufmethode und muss vom Writer der Hostinganwendung implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="bc151-109">The `AcquiredVirtualAddressSpace` method is a callback method and must be implemented by the writer of the hosting application.</span></span> <span data-ttu-id="bc151-110">Sie wird von der CLR aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="bc151-110">It is called by the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bc151-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="bc151-111">Requirements</span></span>  
 <span data-ttu-id="bc151-112">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bc151-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bc151-113">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="bc151-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="bc151-114">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="bc151-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bc151-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bc151-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc151-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bc151-116">See Also</span></span>  
 [<span data-ttu-id="bc151-117">IHostMemoryManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bc151-117">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
