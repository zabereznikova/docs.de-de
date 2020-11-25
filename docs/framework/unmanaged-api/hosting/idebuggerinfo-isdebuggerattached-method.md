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
ms.openlocfilehash: 28b0c5ad5ed8b706974399dcd5468e9810b9fd57
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721698"
---
# <a name="idebuggerinfoisdebuggerattached-method"></a><span data-ttu-id="80bbd-102">IDebuggerInfo::IsDebuggerAttached-Methode</span><span class="sxs-lookup"><span data-stu-id="80bbd-102">IDebuggerInfo::IsDebuggerAttached Method</span></span>

<span data-ttu-id="80bbd-103">Ruft einen Wert ab, der angibt, ob ein verwalteter Debugger an diesen Prozess angefügt ist.</span><span class="sxs-lookup"><span data-stu-id="80bbd-103">Gets a value that indicates whether a managed debugger is attached to this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80bbd-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="80bbd-104">Syntax</span></span>  
  
```cpp  
HRESULT IsDebuggerAttached (  
    [out] BOOL *pbAttached  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="80bbd-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="80bbd-105">Parameters</span></span>  

 `pbAttached`  
 <span data-ttu-id="80bbd-106">vorgenommen Ein Zeiger auf einen-Wert, der ist, `true` Wenn ein verwalteter Debugger an den Prozess angefügt ist, andernfalls `false` .</span><span class="sxs-lookup"><span data-stu-id="80bbd-106">[out] A pointer to a value that is `true` if a managed debugger is attached to the process; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="80bbd-107">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="80bbd-107">Requirements</span></span>  

 <span data-ttu-id="80bbd-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="80bbd-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="80bbd-109">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="80bbd-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="80bbd-110">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="80bbd-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="80bbd-111">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="80bbd-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80bbd-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="80bbd-112">See also</span></span>

- [<span data-ttu-id="80bbd-113">IDebuggerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="80bbd-113">IDebuggerInfo Interface</span></span>](idebuggerinfo-interface.md)
