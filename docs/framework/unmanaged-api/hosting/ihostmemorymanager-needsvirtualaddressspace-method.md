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
ms.openlocfilehash: a3ae474a73f4c8e4b98c4b2bc5d04e55bcae6874
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128665"
---
# <a name="ihostmemorymanagerneedsvirtualaddressspace-method"></a><span data-ttu-id="ad0a6-102">IHostMemoryManager::NeedsVirtualAddressSpace-Methode</span><span class="sxs-lookup"><span data-stu-id="ad0a6-102">IHostMemoryManager::NeedsVirtualAddressSpace Method</span></span>
<span data-ttu-id="ad0a6-103">Benachrichtigt den Host, dass der Common Language Runtime (CLR) versucht, den angegebenen Arbeitsspeicher zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="ad0a6-103">Notifies the host that the common language runtime (CLR) is going to attempt to use the specified memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad0a6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ad0a6-104">Syntax</span></span>  
  
```cpp  
HRESULT NeedsVirtualAddressSpace (  
    [in] LPVOID  startAddress,  
    [in] SIZE_T  size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ad0a6-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ad0a6-105">Parameters</span></span>  
 `startAddress`  
 <span data-ttu-id="ad0a6-106">in Die Startadresse des Speichers.</span><span class="sxs-lookup"><span data-stu-id="ad0a6-106">[in] The starting address of the memory.</span></span>  
  
 `size`  
 <span data-ttu-id="ad0a6-107">in Die Größe des Arbeitsspeichers in Bytes.</span><span class="sxs-lookup"><span data-stu-id="ad0a6-107">[in] The size, in bytes, of the memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ad0a6-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ad0a6-108">Remarks</span></span>  
 <span data-ttu-id="ad0a6-109">Bei der `NeedsVirtualAddressSpace`-Methode handelt es sich um eine Rückruf Methode, die vom Writer der Host Anwendung implementiert werden muss.</span><span class="sxs-lookup"><span data-stu-id="ad0a6-109">The `NeedsVirtualAddressSpace` method is a callback method and must be implemented by the writer of the hosting application.</span></span> <span data-ttu-id="ad0a6-110">Sie wird von der CLR aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="ad0a6-110">It is called by the CLR.</span></span>  
  
 <span data-ttu-id="ad0a6-111">Wenn der Host nicht möchten, dass die CLR den angegebenen Arbeitsspeicher verwendet, wird möglicherweise ein E_OUTOFMEMORY HRESULT zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="ad0a6-111">If the host does not want the CLR to use the specified memory, it may return an E_OUTOFMEMORY HRESULT.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ad0a6-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ad0a6-112">Requirements</span></span>  
 <span data-ttu-id="ad0a6-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ad0a6-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ad0a6-114">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="ad0a6-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ad0a6-115">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="ad0a6-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ad0a6-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ad0a6-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad0a6-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ad0a6-117">See also</span></span>

- [<span data-ttu-id="ad0a6-118">IHostMemoryManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ad0a6-118">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
