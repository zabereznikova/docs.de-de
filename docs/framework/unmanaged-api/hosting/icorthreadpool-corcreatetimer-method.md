---
title: ICorThreadpool::CorCreateTimer-Methode
ms.date: 03/30/2017
api_name:
- ICorThreadpool.CorCreateTimer
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorCreateTimer
helpviewer_keywords:
- CorCreateTimer method [.NET Framework hosting]
- ICorThreadpool::CorCreateTimer method [.NET Framework hosting]
ms.assetid: 0d56ef25-30f1-4499-8a1f-76e7654ec614
topic_type:
- apiref
ms.openlocfilehash: bd48b9167a803da6e27c8d8ebc3a2b13508ff5c9
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/21/2020
ms.locfileid: "83760330"
---
# <a name="icorthreadpoolcorcreatetimer-method"></a><span data-ttu-id="4fa38-102">ICorThreadpool::CorCreateTimer-Methode</span><span class="sxs-lookup"><span data-stu-id="4fa38-102">ICorThreadpool::CorCreateTimer Method</span></span>
<span data-ttu-id="4fa38-103">Diese Methode unterstützt die .NET Framework-Infrastruktur und ist nicht für eine direkte Verwendung im Code vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="4fa38-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4fa38-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4fa38-104">Syntax</span></span>  
  
```cpp  
HRESULT CorCreateTimer (  
    [in]  HANDLE*             phNewTimer,  
    [in]  WAITORTIMERCALLBACK Callback,  
    [in]  PVOID               Parameter,  
    [in]  DWORD               DueTime,  
    [in]  DWORD               Period,  
    [out] BOOL*               result  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="4fa38-105">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="4fa38-105">Requirements</span></span>  
 <span data-ttu-id="4fa38-106">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4fa38-106">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4fa38-107">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="4fa38-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4fa38-108">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="4fa38-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4fa38-109">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4fa38-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4fa38-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4fa38-110">See also</span></span>

- [<span data-ttu-id="4fa38-111">ICorThreadpool-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4fa38-111">ICorThreadpool Interface</span></span>](icorthreadpool-interface.md)
