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
ms.openlocfilehash: 74fbb2f162fbb68871f1bb4e1a1de32f5f913cd7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731318"
---
# <a name="ihostmemorymanagerneedsvirtualaddressspace-method"></a><span data-ttu-id="b88c0-102">IHostMemoryManager::NeedsVirtualAddressSpace-Methode</span><span class="sxs-lookup"><span data-stu-id="b88c0-102">IHostMemoryManager::NeedsVirtualAddressSpace Method</span></span>

<span data-ttu-id="b88c0-103">Benachrichtigt den Host, dass der Common Language Runtime (CLR) versucht, den angegebenen Arbeitsspeicher zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="b88c0-103">Notifies the host that the common language runtime (CLR) is going to attempt to use the specified memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b88c0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b88c0-104">Syntax</span></span>  
  
```cpp  
HRESULT NeedsVirtualAddressSpace (  
    [in] LPVOID  startAddress,  
    [in] SIZE_T  size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b88c0-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b88c0-105">Parameters</span></span>  

 `startAddress`  
 <span data-ttu-id="b88c0-106">in Die Startadresse des Speichers.</span><span class="sxs-lookup"><span data-stu-id="b88c0-106">[in] The starting address of the memory.</span></span>  
  
 `size`  
 <span data-ttu-id="b88c0-107">in Die Größe des Arbeitsspeichers in Bytes.</span><span class="sxs-lookup"><span data-stu-id="b88c0-107">[in] The size, in bytes, of the memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b88c0-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b88c0-108">Remarks</span></span>  

 <span data-ttu-id="b88c0-109">`NeedsVirtualAddressSpace`Bei der-Methode handelt es sich um eine Rückruf Methode, die vom Writer der Host Anwendung implementiert werden muss.</span><span class="sxs-lookup"><span data-stu-id="b88c0-109">The `NeedsVirtualAddressSpace` method is a callback method and must be implemented by the writer of the hosting application.</span></span> <span data-ttu-id="b88c0-110">Sie wird von der CLR aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="b88c0-110">It is called by the CLR.</span></span>  
  
 <span data-ttu-id="b88c0-111">Wenn der Host nicht möchten, dass die CLR den angegebenen Arbeitsspeicher verwendet, wird möglicherweise ein E_OUTOFMEMORY HRESULT zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="b88c0-111">If the host does not want the CLR to use the specified memory, it may return an E_OUTOFMEMORY HRESULT.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b88c0-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="b88c0-112">Requirements</span></span>  

 <span data-ttu-id="b88c0-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b88c0-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b88c0-114">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="b88c0-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b88c0-115">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="b88c0-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b88c0-116">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b88c0-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b88c0-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b88c0-117">See also</span></span>

- [<span data-ttu-id="b88c0-118">IHostMemoryManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b88c0-118">IHostMemoryManager Interface</span></span>](ihostmemorymanager-interface.md)
