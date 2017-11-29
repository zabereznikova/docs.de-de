---
title: IDebuggerInfo::IsDebuggerAttached-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IDebuggerInfo.IsDebuggerAttached
api_location: mscoree.dll
api_type: COM
f1_keywords: IsDebuggerAttached
helpviewer_keywords:
- IDebuggerInfo::IsDebuggerAttached method [.NET Framework hosting]
- IsDebuggerAttached method, IDebuggerInfo interface [.NET Framework hosting]
ms.assetid: 6e21872f-602f-411a-a423-bff5cdf27000
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a6e1f11939bc4f11b1fb49dc44f129176143fbca
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="idebuggerinfoisdebuggerattached-method"></a><span data-ttu-id="b9b27-102">IDebuggerInfo::IsDebuggerAttached-Methode</span><span class="sxs-lookup"><span data-stu-id="b9b27-102">IDebuggerInfo::IsDebuggerAttached Method</span></span>
<span data-ttu-id="b9b27-103">Ruft einen Wert, der angibt, ob dieser Prozess ein verwalteter Debugger angefügt ist.</span><span class="sxs-lookup"><span data-stu-id="b9b27-103">Gets a value that indicates whether a managed debugger is attached to this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9b27-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b9b27-104">Syntax</span></span>  
  
```  
HRESULT IsDebuggerAttached (  
    [out] BOOL *pbAttached  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b9b27-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b9b27-105">Parameters</span></span>  
 `pbAttached`  
 <span data-ttu-id="b9b27-106">[out] Ein Zeiger auf einen Wert, der `true` ist ein verwalteter Debugger an den Prozess angefügt ist, andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="b9b27-106">[out] A pointer to a value that is `true` if a managed debugger is attached to the process; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b9b27-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b9b27-107">Requirements</span></span>  
 <span data-ttu-id="b9b27-108">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b9b27-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b9b27-109">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b9b27-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b9b27-110">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="b9b27-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b9b27-111">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b9b27-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9b27-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b9b27-112">See Also</span></span>  
 [<span data-ttu-id="b9b27-113">IDebuggerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b9b27-113">IDebuggerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerinfo-interface.md)
