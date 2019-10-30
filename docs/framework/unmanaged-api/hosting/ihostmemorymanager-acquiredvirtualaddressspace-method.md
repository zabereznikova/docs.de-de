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
ms.openlocfilehash: b70454cd1e2d6d38e6ca4d0ea0bd8974963c201c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136739"
---
# <a name="ihostmemorymanageracquiredvirtualaddressspace-method"></a><span data-ttu-id="ccd26-102">IHostMemoryManager::AcquiredVirtualAddressSpace-Methode</span><span class="sxs-lookup"><span data-stu-id="ccd26-102">IHostMemoryManager::AcquiredVirtualAddressSpace Method</span></span>
<span data-ttu-id="ccd26-103">Benachrichtigt den Host, dass die Common Language Runtime (CLR) den angegebenen Arbeitsspeicher vom Betriebssystem abgerufen hat.</span><span class="sxs-lookup"><span data-stu-id="ccd26-103">Notifies the host that the common language runtime (CLR) has acquired the specified memory from the operating system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ccd26-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ccd26-104">Syntax</span></span>  
  
```cpp  
HRESULT AcquiredVirtualAddressSpace(  
    [in] LPVOID  startAddress,  
    [in] SIZE_T  size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ccd26-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ccd26-105">Parameters</span></span>  
 `startAddress`  
 <span data-ttu-id="ccd26-106">in Die Startadresse des Speichers.</span><span class="sxs-lookup"><span data-stu-id="ccd26-106">[in] The starting address of the memory.</span></span>  
  
 `size`  
 <span data-ttu-id="ccd26-107">in Die Größe des Arbeitsspeichers in Bytes.</span><span class="sxs-lookup"><span data-stu-id="ccd26-107">[in] The size, in bytes, of the memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ccd26-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ccd26-108">Remarks</span></span>  
 <span data-ttu-id="ccd26-109">Bei der `AcquiredVirtualAddressSpace`-Methode handelt es sich um eine Rückruf Methode, die vom Writer der Host Anwendung implementiert werden muss.</span><span class="sxs-lookup"><span data-stu-id="ccd26-109">The `AcquiredVirtualAddressSpace` method is a callback method and must be implemented by the writer of the hosting application.</span></span> <span data-ttu-id="ccd26-110">Sie wird von der CLR aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="ccd26-110">It is called by the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ccd26-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ccd26-111">Requirements</span></span>  
 <span data-ttu-id="ccd26-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ccd26-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ccd26-113">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="ccd26-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ccd26-114">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="ccd26-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ccd26-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ccd26-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ccd26-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ccd26-116">See also</span></span>

- [<span data-ttu-id="ccd26-117">IHostMemoryManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ccd26-117">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
