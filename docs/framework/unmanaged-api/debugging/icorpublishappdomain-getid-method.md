---
title: ICorPublishAppDomain::GetID-Methode
ms.date: 03/30/2017
api_name:
- ICorPublishAppDomain.GetID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishAppDomain::GetID
helpviewer_keywords:
- GetID method, ICorPublishAppDomain interface [.NET Framework debugging]
- ICorPublishAppDomain::GetID method [.NET Framework debugging]
ms.assetid: 229437e3-1465-4bd8-8846-9804b2488133
topic_type:
- apiref
ms.openlocfilehash: ab331145a8147e8830cb9b158a1975bc748c7cce
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95716862"
---
# <a name="icorpublishappdomaingetid-method"></a><span data-ttu-id="6824b-102">ICorPublishAppDomain::GetID-Methode</span><span class="sxs-lookup"><span data-stu-id="6824b-102">ICorPublishAppDomain::GetID Method</span></span>

<span data-ttu-id="6824b-103">Ruft den eindeutigen Bezeichner für diese [ICorPublishAppDomain](icorpublishappdomain-interface.md)ab.</span><span class="sxs-lookup"><span data-stu-id="6824b-103">Gets the unique identifier for this [ICorPublishAppDomain](icorpublishappdomain-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6824b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6824b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetID (  
    [out] ULONG32   *puId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6824b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="6824b-105">Parameters</span></span>  

 `puId`  
 <span data-ttu-id="6824b-106">vorgenommen Ein Zeiger auf den Bezeichner der Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="6824b-106">[out] A pointer to the identifier of the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6824b-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6824b-107">Remarks</span></span>  

 <span data-ttu-id="6824b-108">Der Bezeichner ist nur im Gültigkeitsbereich des enthaltenden Prozesses eindeutig.</span><span class="sxs-lookup"><span data-stu-id="6824b-108">The identifier is unique only in the scope of the containing process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6824b-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="6824b-109">Requirements</span></span>  

 <span data-ttu-id="6824b-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6824b-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6824b-111">**Header:** Corpub. idl, Corpub. h</span><span class="sxs-lookup"><span data-stu-id="6824b-111">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="6824b-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6824b-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6824b-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6824b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6824b-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6824b-114">See also</span></span>

- [<span data-ttu-id="6824b-115">ICorPublishAppDomain-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6824b-115">ICorPublishAppDomain Interface</span></span>](icorpublishappdomain-interface.md)
