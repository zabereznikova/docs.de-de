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
ms.openlocfilehash: 4c18607d5373b415228846350a3dd0637ade1b45
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59150799"
---
# <a name="iobjecthandleunwrap-method"></a><span data-ttu-id="f0691-102">IObjectHandle::Unwrap-Methode</span><span class="sxs-lookup"><span data-stu-id="f0691-102">IObjectHandle::Unwrap Method</span></span>
<span data-ttu-id="f0691-103">Eine Marshal-by-Value-Objekt, aus der Dereferenzierung entpackt.</span><span class="sxs-lookup"><span data-stu-id="f0691-103">Unwraps a marshal-by-value object from indirection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0691-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f0691-104">Syntax</span></span>  
  
```  
HRESULT Unwrap (  
    [out, retval] VARIANT *ppv  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f0691-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f0691-105">Parameters</span></span>  
 `ppv`  
 <span data-ttu-id="f0691-106">[out] Ein Zeiger auf das Objekt, dessen Wrapper entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="f0691-106">[out] A pointer to the object to be unwrapped.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f0691-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f0691-107">Requirements</span></span>  
 <span data-ttu-id="f0691-108">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f0691-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f0691-109">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f0691-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f0691-110">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="f0691-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f0691-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f0691-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
