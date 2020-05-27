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
ms.openlocfilehash: 4a246fb95ab5b4a7f187aa660f20e590c63ddff2
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804466"
---
# <a name="ihostmemorymanagerreleasedvirtualaddressspace-method"></a><span data-ttu-id="afec9-102">IHostMemoryManager::ReleasedVirtualAddressSpace-Methode</span><span class="sxs-lookup"><span data-stu-id="afec9-102">IHostMemoryManager::ReleasedVirtualAddressSpace Method</span></span>
<span data-ttu-id="afec9-103">Benachrichtigt den Host, dass die Common Language Runtime (CLR) die Verwendung des angegebenen Speichers abgeschlossen hat.</span><span class="sxs-lookup"><span data-stu-id="afec9-103">Notifies the host that the common language runtime (CLR) has finished using the specified memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="afec9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="afec9-104">Syntax</span></span>  
  
```cpp  
HRESULT ReleasedVirtualAddressSpace(  
    [in] LPVOID startAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="afec9-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="afec9-105">Parameters</span></span>  
 `startAddress`  
 <span data-ttu-id="afec9-106">in Ein Zeiger auf die Startadresse des frei zugegenden Speichers.</span><span class="sxs-lookup"><span data-stu-id="afec9-106">[in] Pointer to the starting address of the memory to be released.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="afec9-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="afec9-107">Remarks</span></span>  
 <span data-ttu-id="afec9-108">`ReleasedVirtualAddressSpace`Bei der-Methode handelt es sich um eine Rückruf Methode, die vom Writer der Host Anwendung implementiert werden muss.</span><span class="sxs-lookup"><span data-stu-id="afec9-108">The `ReleasedVirtualAddressSpace` method is a callback method and must be implemented by the writer of the hosting application.</span></span> <span data-ttu-id="afec9-109">Sie wird von der CLR aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="afec9-109">It is called by the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="afec9-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="afec9-110">Requirements</span></span>  
 <span data-ttu-id="afec9-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="afec9-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="afec9-112">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="afec9-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="afec9-113">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="afec9-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="afec9-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="afec9-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="afec9-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="afec9-115">See also</span></span>

- [<span data-ttu-id="afec9-116">IHostMemoryManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="afec9-116">IHostMemoryManager Interface</span></span>](ihostmemorymanager-interface.md)
