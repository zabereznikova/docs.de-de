---
title: IGCHostControl::RequestVirtualMemLimit-Methode
ms.date: 03/30/2017
api_name:
- IGCHostControl.RequestVirtualMemLimit
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- RequestVirtualMemLimit
helpviewer_keywords:
- IGCHostControl::RequestVirtualMemLimit method [.NET Framework hosting]
- RequestVirtualMemLimit method [.NET Framework hosting]
ms.assetid: f4984a8c-4c0e-4460-9aa1-d022b3621228
topic_type:
- apiref
ms.openlocfilehash: d4814e44b1a5311cf6800c804df7a7e11000cbab
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/22/2020
ms.locfileid: "83805137"
---
# <a name="igchostcontrolrequestvirtualmemlimit-method"></a><span data-ttu-id="c97eb-102">IGCHostControl::RequestVirtualMemLimit-Methode</span><span class="sxs-lookup"><span data-stu-id="c97eb-102">IGCHostControl::RequestVirtualMemLimit Method</span></span>
<span data-ttu-id="c97eb-103">Fordert den Host auf, die Grenzwerte für den virtuellen Arbeitsspeicher zu ändern.</span><span class="sxs-lookup"><span data-stu-id="c97eb-103">Requests the host to change the limits of virtual memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c97eb-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c97eb-104">Syntax</span></span>  
  
```cpp  
HRESULT RequestVirtualMemLimit (  
    [in] SIZE_T       sztMaxVirtualMemMB,  
    [in, out] SIZE_T* psztNewMaxVirtualMemMB  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c97eb-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c97eb-105">Parameters</span></span>  
 `sztMaxVirtualMemMB`  
 <span data-ttu-id="c97eb-106">in Die angeforderte Größe des Arbeitsspeichers, der zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="c97eb-106">[in] The requested size of memory to be allocated.</span></span>  
  
 `psztNewMaxVirtualMemMB`  
 <span data-ttu-id="c97eb-107">[in, out] Ein Zeiger auf die tatsächliche Größe des zugeordneten Arbeitsspeichers.</span><span class="sxs-lookup"><span data-stu-id="c97eb-107">[in, out] A pointer to the actual size of memory allocated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c97eb-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c97eb-108">Requirements</span></span>  
 <span data-ttu-id="c97eb-109">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c97eb-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c97eb-110">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="c97eb-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c97eb-111">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="c97eb-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c97eb-112">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c97eb-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c97eb-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c97eb-113">See also</span></span>

- [<span data-ttu-id="c97eb-114">IGCHostControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c97eb-114">IGCHostControl Interface</span></span>](igchostcontrol-interface.md)
