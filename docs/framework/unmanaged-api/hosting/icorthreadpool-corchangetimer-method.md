---
title: ICorThreadpool::CorChangeTimer-Methode
ms.date: 03/30/2017
api_name:
- ICorThreadpool.CorChangeTimer
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorChangeTimer
helpviewer_keywords:
- CorChangeTimer method [.NET Framework hosting]
- ICorThreadpool::CorChangeTimer method [.NET Framework hosting]
ms.assetid: 82b03a59-5a87-43ed-9b75-e04b256e1a46
topic_type:
- apiref
ms.openlocfilehash: 3d119c8355f5b58a05f1ea1695969b2e98682c72
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95690238"
---
# <a name="icorthreadpoolcorchangetimer-method"></a><span data-ttu-id="1d7cd-102">ICorThreadpool::CorChangeTimer-Methode</span><span class="sxs-lookup"><span data-stu-id="1d7cd-102">ICorThreadpool::CorChangeTimer Method</span></span>

<span data-ttu-id="1d7cd-103">Diese Methode unterstützt die .NET Framework-Infrastruktur und ist nicht für eine direkte Verwendung im Code vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="1d7cd-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d7cd-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1d7cd-104">Syntax</span></span>  
  
```cpp  
HRESULT CorChangeTimer (  
    [in]  HANDLE Timer,
    [in]  ULONG  DueTime,
    [in]  ULONG  Period,  
    [out] BOOL*  result  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="1d7cd-105">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="1d7cd-105">Requirements</span></span>  

 <span data-ttu-id="1d7cd-106">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1d7cd-106">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1d7cd-107">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="1d7cd-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1d7cd-108">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="1d7cd-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1d7cd-109">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1d7cd-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d7cd-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1d7cd-110">See also</span></span>

- [<span data-ttu-id="1d7cd-111">ICorThreadpool-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1d7cd-111">ICorThreadpool Interface</span></span>](icorthreadpool-interface.md)
