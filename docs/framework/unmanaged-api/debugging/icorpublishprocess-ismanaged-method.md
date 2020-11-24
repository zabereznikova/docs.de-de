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
ms.openlocfilehash: dfe247bda75c3695c7c09b85729b4e057c13c62d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95692630"
---
# <a name="icorpublishprocessismanaged-method"></a><span data-ttu-id="43be5-102">ICorPublishProcess::IsManaged-Methode</span><span class="sxs-lookup"><span data-stu-id="43be5-102">ICorPublishProcess::IsManaged Method</span></span>

<span data-ttu-id="43be5-103">Ruft einen Wert ab, der angibt, ob der Prozess, auf den von diesem [ICorPublishProcess](icorpublishprocess-interface.md) verwiesen wird, über verwalteten Code verfügt.</span><span class="sxs-lookup"><span data-stu-id="43be5-103">Gets a value that indicates whether the process referenced by this [ICorPublishProcess](icorpublishprocess-interface.md) is known to have managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43be5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="43be5-104">Syntax</span></span>  
  
```cpp  
HRESULT IsManaged (  
    [out] BOOL   *pbManaged  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="43be5-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="43be5-105">Parameters</span></span>  

 `pbManaged`  
 <span data-ttu-id="43be5-106">vorgenommen Ein Zeiger auf einen booleschen Wert, der angibt, ob der Prozess verwalteten Code aufweist.</span><span class="sxs-lookup"><span data-stu-id="43be5-106">[out] A pointer to a Boolean value that indicates whether the process has managed code.</span></span> <span data-ttu-id="43be5-107">Der Wert ist `true` , wenn der Prozess verwalteten Code aufweist, andernfalls `false` .</span><span class="sxs-lookup"><span data-stu-id="43be5-107">The value is `true` if the process has managed code; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="43be5-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="43be5-108">Remarks</span></span>  

 <span data-ttu-id="43be5-109">Da die aktuelle Version von `ICorPublishProcess` nur auf Prozesse mit verwaltetem Code zugreifen kann, `IsManaged` gibt immer zurück `true` .</span><span class="sxs-lookup"><span data-stu-id="43be5-109">Since the current version of `ICorPublishProcess` allows access only to processes that have managed code, `IsManaged` always returns `true`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="43be5-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="43be5-110">Requirements</span></span>  

 <span data-ttu-id="43be5-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="43be5-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="43be5-112">**Header:** Corpub. idl, Corpub. h</span><span class="sxs-lookup"><span data-stu-id="43be5-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="43be5-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="43be5-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="43be5-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="43be5-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43be5-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="43be5-115">See also</span></span>

- [<span data-ttu-id="43be5-116">ICorPublishProcess-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="43be5-116">ICorPublishProcess Interface</span></span>](icorpublishprocess-interface.md)
