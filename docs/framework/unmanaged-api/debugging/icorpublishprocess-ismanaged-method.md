---
title: ICorPublishProcess::IsManaged-Methode
ms.date: 03/30/2017
api_name:
- ICorPublishProcess.IsManaged
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcess::IsManaged
helpviewer_keywords:
- IsManaged method, ICorPublishProcess interface [.NET Framework debugging]
- ICorPublishProcess::IsManaged method [.NET Framework debugging]
ms.assetid: 06b1f7cc-acdf-47a6-9d53-d9dec2424152
topic_type:
- apiref
ms.openlocfilehash: 68931ba16ea1f8f61176c6d6ed8300e762b61690
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790527"
---
# <a name="icorpublishprocessismanaged-method"></a><span data-ttu-id="0d294-102">ICorPublishProcess::IsManaged-Methode</span><span class="sxs-lookup"><span data-stu-id="0d294-102">ICorPublishProcess::IsManaged Method</span></span>
<span data-ttu-id="0d294-103">Ruft einen Wert ab, der angibt, ob der Prozess, auf den von diesem [ICorPublishProcess](icorpublishprocess-interface.md) verwiesen wird, über verwalteten Code verfügt.</span><span class="sxs-lookup"><span data-stu-id="0d294-103">Gets a value that indicates whether the process referenced by this [ICorPublishProcess](icorpublishprocess-interface.md) is known to have managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d294-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0d294-104">Syntax</span></span>  
  
```cpp  
HRESULT IsManaged (  
    [out] BOOL   *pbManaged  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0d294-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="0d294-105">Parameters</span></span>  
 `pbManaged`  
 <span data-ttu-id="0d294-106">vorgenommen Ein Zeiger auf einen booleschen Wert, der angibt, ob der Prozess verwalteten Code aufweist.</span><span class="sxs-lookup"><span data-stu-id="0d294-106">[out] A pointer to a Boolean value that indicates whether the process has managed code.</span></span> <span data-ttu-id="0d294-107">Der Wert ist `true`, wenn der Prozess verwalteten Code hat. Andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="0d294-107">The value is `true` if the process has managed code; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0d294-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0d294-108">Remarks</span></span>  
 <span data-ttu-id="0d294-109">Da die aktuelle Version von `ICorPublishProcess` nur Zugriff auf Prozesse zulässt, die über verwalteten Code verfügen, gibt `IsManaged` immer `true`zurück.</span><span class="sxs-lookup"><span data-stu-id="0d294-109">Since the current version of `ICorPublishProcess` allows access only to processes that have managed code, `IsManaged` always returns `true`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0d294-110">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0d294-110">Requirements</span></span>  
 <span data-ttu-id="0d294-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0d294-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0d294-112">**Header:** Corpub. idl, Corpub. h</span><span class="sxs-lookup"><span data-stu-id="0d294-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="0d294-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0d294-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0d294-114">**.NET Framework Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0d294-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d294-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0d294-115">See also</span></span>

- [<span data-ttu-id="0d294-116">ICorPublishProcess-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0d294-116">ICorPublishProcess Interface</span></span>](icorpublishprocess-interface.md)
