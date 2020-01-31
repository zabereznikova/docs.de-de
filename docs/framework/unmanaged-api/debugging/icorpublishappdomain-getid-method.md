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
ms.openlocfilehash: 8d6e130981693268ae5c2cd615036b84ca8ed2d8
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790701"
---
# <a name="icorpublishappdomaingetid-method"></a><span data-ttu-id="6df4c-102">ICorPublishAppDomain::GetID-Methode</span><span class="sxs-lookup"><span data-stu-id="6df4c-102">ICorPublishAppDomain::GetID Method</span></span>
<span data-ttu-id="6df4c-103">Ruft den eindeutigen Bezeichner für diese [ICorPublishAppDomain](icorpublishappdomain-interface.md)ab.</span><span class="sxs-lookup"><span data-stu-id="6df4c-103">Gets the unique identifier for this [ICorPublishAppDomain](icorpublishappdomain-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6df4c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6df4c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetID (  
    [out] ULONG32   *puId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6df4c-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="6df4c-105">Parameters</span></span>  
 `puId`  
 <span data-ttu-id="6df4c-106">vorgenommen Ein Zeiger auf den Bezeichner der Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="6df4c-106">[out] A pointer to the identifier of the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6df4c-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6df4c-107">Remarks</span></span>  
 <span data-ttu-id="6df4c-108">Der Bezeichner ist nur im Gültigkeitsbereich des enthaltenden Prozesses eindeutig.</span><span class="sxs-lookup"><span data-stu-id="6df4c-108">The identifier is unique only in the scope of the containing process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6df4c-109">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6df4c-109">Requirements</span></span>  
 <span data-ttu-id="6df4c-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6df4c-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6df4c-111">**Header:** Corpub. idl, Corpub. h</span><span class="sxs-lookup"><span data-stu-id="6df4c-111">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="6df4c-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6df4c-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6df4c-113">**.NET Framework Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6df4c-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6df4c-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6df4c-114">See also</span></span>

- [<span data-ttu-id="6df4c-115">ICorPublishAppDomain-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6df4c-115">ICorPublishAppDomain Interface</span></span>](icorpublishappdomain-interface.md)
