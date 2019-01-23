---
title: IDebuggerInfo::IsDebuggerAttached-Methode
ms.date: 03/30/2017
api_name:
- IDebuggerInfo.IsDebuggerAttached
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IsDebuggerAttached
helpviewer_keywords:
- IDebuggerInfo::IsDebuggerAttached method [.NET Framework hosting]
- IsDebuggerAttached method, IDebuggerInfo interface [.NET Framework hosting]
ms.assetid: 6e21872f-602f-411a-a423-bff5cdf27000
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7d471ac13061cfb3a0320801445fb5c931718691
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54562923"
---
# <a name="idebuggerinfoisdebuggerattached-method"></a><span data-ttu-id="b5c2b-102">IDebuggerInfo::IsDebuggerAttached-Methode</span><span class="sxs-lookup"><span data-stu-id="b5c2b-102">IDebuggerInfo::IsDebuggerAttached Method</span></span>
<span data-ttu-id="b5c2b-103">Ruft einen Wert, der angibt, ob dieses Prozesses ein verwalteter Debugger angefügt wird.</span><span class="sxs-lookup"><span data-stu-id="b5c2b-103">Gets a value that indicates whether a managed debugger is attached to this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5c2b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b5c2b-104">Syntax</span></span>  
  
```  
HRESULT IsDebuggerAttached (  
    [out] BOOL *pbAttached  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b5c2b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b5c2b-105">Parameters</span></span>  
 `pbAttached`  
 <span data-ttu-id="b5c2b-106">[out] Ein Zeiger auf einen Wert `true` ist ein verwalteter Debugger an den Prozess angefügt ist, andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="b5c2b-106">[out] A pointer to a value that is `true` if a managed debugger is attached to the process; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b5c2b-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b5c2b-107">Requirements</span></span>  
 <span data-ttu-id="b5c2b-108">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b5c2b-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b5c2b-109">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b5c2b-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b5c2b-110">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="b5c2b-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b5c2b-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b5c2b-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5c2b-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b5c2b-112">See also</span></span>
- [<span data-ttu-id="b5c2b-113">IDebuggerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b5c2b-113">IDebuggerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerinfo-interface.md)
