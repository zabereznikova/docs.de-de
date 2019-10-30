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
ms.openlocfilehash: cbd6fa5f7935a57799d695c3ebb617d856e6dbd9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133174"
---
# <a name="idebuggerinfoisdebuggerattached-method"></a><span data-ttu-id="005d2-102">IDebuggerInfo::IsDebuggerAttached-Methode</span><span class="sxs-lookup"><span data-stu-id="005d2-102">IDebuggerInfo::IsDebuggerAttached Method</span></span>
<span data-ttu-id="005d2-103">Ruft einen Wert ab, der angibt, ob ein verwalteter Debugger an diesen Prozess angefügt ist.</span><span class="sxs-lookup"><span data-stu-id="005d2-103">Gets a value that indicates whether a managed debugger is attached to this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="005d2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="005d2-104">Syntax</span></span>  
  
```cpp  
HRESULT IsDebuggerAttached (  
    [out] BOOL *pbAttached  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="005d2-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="005d2-105">Parameters</span></span>  
 `pbAttached`  
 <span data-ttu-id="005d2-106">vorgenommen Ein Zeiger auf einen Wert, der `true` wird, wenn ein verwalteter Debugger an den Prozess angefügt ist. Andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="005d2-106">[out] A pointer to a value that is `true` if a managed debugger is attached to the process; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="005d2-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="005d2-107">Requirements</span></span>  
 <span data-ttu-id="005d2-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="005d2-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="005d2-109">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="005d2-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="005d2-110">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="005d2-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="005d2-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="005d2-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="005d2-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="005d2-112">See also</span></span>

- [<span data-ttu-id="005d2-113">IDebuggerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="005d2-113">IDebuggerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerinfo-interface.md)
