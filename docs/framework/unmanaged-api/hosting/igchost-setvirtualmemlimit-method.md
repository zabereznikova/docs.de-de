---
title: IGCHost::SetVirtualMemLimit-Methode
ms.date: 03/30/2017
api_name:
- IGCHost.SetVirtualMemLimit
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SetVirtualMemLimit
helpviewer_keywords:
- IGCHost::SetVirtualMemLimit method [.NET Framework hosting]
- SetVirtualMemLimit method [.NET Framework hosting]
ms.assetid: c7e7c2d0-e58c-4650-b40c-47b2be2cda45
topic_type:
- apiref
ms.openlocfilehash: 93ed63b4abacce1d8943434965aacf67190631b6
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/22/2020
ms.locfileid: "83805188"
---
# <a name="igchostsetvirtualmemlimit-method"></a><span data-ttu-id="572b6-102">IGCHost::SetVirtualMemLimit-Methode</span><span class="sxs-lookup"><span data-stu-id="572b6-102">IGCHost::SetVirtualMemLimit Method</span></span>
<span data-ttu-id="572b6-103">Legt die maximale Größe des virtuellen Arbeitsspeichers der Laufzeit fest.</span><span class="sxs-lookup"><span data-stu-id="572b6-103">Sets the maximum size of the runtime's virtual memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="572b6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="572b6-104">Syntax</span></span>  
  
```cpp  
HRESULT SetVirtualMemLimit (  
    [in] SIZE_T sztMaxVirtualMemMB  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="572b6-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="572b6-105">Parameters</span></span>  
 `sztMaxVirtualMemMB`  
 <span data-ttu-id="572b6-106">in Die maximale Größe des virtuellen Arbeitsspeichers der Laufzeit in Megabyte.</span><span class="sxs-lookup"><span data-stu-id="572b6-106">[in] The maximum size, in megabytes, of the runtime's virtual memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="572b6-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="572b6-107">Remarks</span></span>  
 <span data-ttu-id="572b6-108">Die maximale Größe des virtuellen Arbeitsspeichers der Laufzeit kann dynamisch geändert werden.</span><span class="sxs-lookup"><span data-stu-id="572b6-108">The maximum size of the runtime's virtual memory can be changed dynamically.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="572b6-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="572b6-109">Requirements</span></span>  
 <span data-ttu-id="572b6-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="572b6-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="572b6-111">**Header:** Gchost. idl, gchost. h</span><span class="sxs-lookup"><span data-stu-id="572b6-111">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="572b6-112">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="572b6-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="572b6-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="572b6-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="572b6-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="572b6-114">See also</span></span>

- [<span data-ttu-id="572b6-115">IGCHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="572b6-115">IGCHost Interface</span></span>](igchost-interface.md)
