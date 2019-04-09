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
ms.openlocfilehash: d0f029c8fbab97afe3089956391e8446d4cc5e15
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59215494"
---
# <a name="ihostmemorymanagerneedsvirtualaddressspace-method"></a><span data-ttu-id="71940-102">IHostMemoryManager::NeedsVirtualAddressSpace-Methode</span><span class="sxs-lookup"><span data-stu-id="71940-102">IHostMemoryManager::NeedsVirtualAddressSpace Method</span></span>
<span data-ttu-id="71940-103">Benachrichtigt den Host, dass die common Language Runtime (CLR) wird versuchen, den angegebenen Speicher zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="71940-103">Notifies the host that the common language runtime (CLR) is going to attempt to use the specified memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71940-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="71940-104">Syntax</span></span>  
  
```  
HRESULT NeedsVirtualAddressSpace (  
    [in] LPVOID  startAddress,  
    [in] SIZE_T  size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="71940-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="71940-105">Parameters</span></span>  
 `startAddress`  
 <span data-ttu-id="71940-106">[in] Die Startadresse des Arbeitsspeichers.</span><span class="sxs-lookup"><span data-stu-id="71940-106">[in] The starting address of the memory.</span></span>  
  
 `size`  
 <span data-ttu-id="71940-107">[in] Die Größe in Bytes, des Arbeitsspeichers.</span><span class="sxs-lookup"><span data-stu-id="71940-107">[in] The size, in bytes, of the memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="71940-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="71940-108">Remarks</span></span>  
 <span data-ttu-id="71940-109">Die `NeedsVirtualAddressSpace` -Methode ist eine Rückrufmethode und muss vom Writer der hostanwendung implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="71940-109">The `NeedsVirtualAddressSpace` method is a callback method and must be implemented by the writer of the hosting application.</span></span> <span data-ttu-id="71940-110">Sie wird von der CLR aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="71940-110">It is called by the CLR.</span></span>  
  
 <span data-ttu-id="71940-111">Wenn der Host die CLR mit den angegebenen Arbeitsspeicher nicht möchte, wird möglicherweise ein HRESULT E_OUTOFMEMORY zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="71940-111">If the host does not want the CLR to use the specified memory, it may return an E_OUTOFMEMORY HRESULT.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="71940-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="71940-112">Requirements</span></span>  
 <span data-ttu-id="71940-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="71940-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71940-114">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="71940-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="71940-115">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="71940-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="71940-116">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="71940-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="71940-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="71940-117">See also</span></span>

- [<span data-ttu-id="71940-118">IHostMemoryManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="71940-118">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
