---
title: ICorThreadpool::CorBindIoCompletionCallback-Methode
ms.date: 03/30/2017
api_name:
- ICorThreadpool.CorBindIoCompletionCallback
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorBindIoCompletionCallback
helpviewer_keywords:
- CorBindIoCompletionCallback method [.NET Framework hosting]
- ICorThreadpool::CorBindIoCompletionCallback method [.NET Framework hosting]
ms.assetid: 2b159225-f09c-42f1-aa7c-44087e121249
topic_type:
- apiref
ms.openlocfilehash: 7baf144f5d14a8757101bdb29a8bc81ff3a05231
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95690056"
---
# <a name="icorthreadpoolcorbindiocompletioncallback-method"></a><span data-ttu-id="d8dac-102">ICorThreadpool::CorBindIoCompletionCallback-Methode</span><span class="sxs-lookup"><span data-stu-id="d8dac-102">ICorThreadpool::CorBindIoCompletionCallback Method</span></span>

<span data-ttu-id="d8dac-103">Diese Methode unterstützt die .NET Framework-Infrastruktur und ist nicht für eine direkte Verwendung im Code vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="d8dac-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8dac-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d8dac-104">Syntax</span></span>  
  
```cpp  
HRESULT CorBindIoCompletionCallback (  
    [in] HANDLE                          fileHandle,  
    [in] LPOVERLAPPED_COMPLETION_ROUTINE callback  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="d8dac-105">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="d8dac-105">Requirements</span></span>  

 <span data-ttu-id="d8dac-106">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d8dac-106">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d8dac-107">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="d8dac-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d8dac-108">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="d8dac-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d8dac-109">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d8dac-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8dac-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d8dac-110">See also</span></span>

- [<span data-ttu-id="d8dac-111">ICorThreadpool-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d8dac-111">ICorThreadpool Interface</span></span>](icorthreadpool-interface.md)
