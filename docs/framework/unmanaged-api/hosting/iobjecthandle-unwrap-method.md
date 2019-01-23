---
title: IObjectHandle::Unwrap-Methode
ms.date: 03/30/2017
api_name:
- IObjectHandle.Unwrap
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- Unwrap
helpviewer_keywords:
- Unwrap method [.NET Framework hosting]
- IObjectHandle::Unwrap method [.NET Framework hosting]
ms.assetid: 794c6f8e-ed58-416b-b756-e864f2c958f7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: da25055917743481f5a8314023ed94d552fe49ce
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54526417"
---
# <a name="iobjecthandleunwrap-method"></a><span data-ttu-id="116ee-102">IObjectHandle::Unwrap-Methode</span><span class="sxs-lookup"><span data-stu-id="116ee-102">IObjectHandle::Unwrap Method</span></span>
<span data-ttu-id="116ee-103">Eine Marshal-by-Value-Objekt, aus der Dereferenzierung entpackt.</span><span class="sxs-lookup"><span data-stu-id="116ee-103">Unwraps a marshal-by-value object from indirection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="116ee-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="116ee-104">Syntax</span></span>  
  
```  
HRESULT Unwrap (  
    [out, retval] VARIANT *ppv  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="116ee-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="116ee-105">Parameters</span></span>  
 `ppv`  
 <span data-ttu-id="116ee-106">[out] Ein Zeiger auf das Objekt, dessen Wrapper entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="116ee-106">[out] A pointer to the object to be unwrapped.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="116ee-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="116ee-107">Requirements</span></span>  
 <span data-ttu-id="116ee-108">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="116ee-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="116ee-109">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="116ee-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="116ee-110">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="116ee-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="116ee-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="116ee-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="116ee-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="116ee-112">See also</span></span>

