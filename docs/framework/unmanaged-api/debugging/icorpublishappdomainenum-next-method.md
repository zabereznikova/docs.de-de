---
title: ICorPublishAppDomainEnum::Next-Methode
ms.date: 03/30/2017
api_name:
- ICorPublishAppDomainEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishAppDomainEnum::Next
helpviewer_keywords:
- Next method, ICorPublishAppDomainEnum interface [.NET Framework debugging]
- ICorPublishAppDomainEnum::Next method [.NET Framework debugging]
ms.assetid: ad37cd10-0339-4d08-9b0e-4b3428bb4dc3
topic_type:
- apiref
ms.openlocfilehash: c5ac38005410ae6ed9c2f4160e926987791ad604
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2020
ms.locfileid: "83421214"
---
# <a name="icorpublishappdomainenumnext-method"></a><span data-ttu-id="bbc43-102">ICorPublishAppDomainEnum::Next-Methode</span><span class="sxs-lookup"><span data-stu-id="bbc43-102">ICorPublishAppDomainEnum::Next Method</span></span>
<span data-ttu-id="bbc43-103">Ruft die angegebene Anzahl von Anwendungs Domänen ab, die derzeit im Prozess vorhanden sind, beginnend an der aktuellen Position.</span><span class="sxs-lookup"><span data-stu-id="bbc43-103">Gets the specified number of application domains that currently exist in the process, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bbc43-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="bbc43-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]
        ICorPublishAppDomain **objects,  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bbc43-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="bbc43-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="bbc43-106">in Die Anzahl der abzurufenden Elemente.</span><span class="sxs-lookup"><span data-stu-id="bbc43-106">[in] The number of elements to be retrieved.</span></span>  
  
 `objects`  
 <span data-ttu-id="bbc43-107">vorgenommen Ein Zeiger auf das Array von abgerufenen [ICorPublishAppDomain](icorpublishappdomain-interface.md) -Objekten, von denen jedes eine Anwendungsdomäne darstellt.</span><span class="sxs-lookup"><span data-stu-id="bbc43-107">[out] A pointer to the array of retrieved [ICorPublishAppDomain](icorpublishappdomain-interface.md) objects, each of which represents an application domain.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="bbc43-108">vorgenommen Ein Zeiger auf die Anzahl der tatsächlich zurückgegebenen Anwendungs Domänen.</span><span class="sxs-lookup"><span data-stu-id="bbc43-108">[out] Pointer to the number of application domains actually returned.</span></span> <span data-ttu-id="bbc43-109">Dieser Wert kann NULL sein, wenn `celt` ein Wert ist.</span><span class="sxs-lookup"><span data-stu-id="bbc43-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bbc43-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="bbc43-110">Requirements</span></span>  
 <span data-ttu-id="bbc43-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bbc43-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bbc43-112">**Header:** Corpub. idl, Corpub. h</span><span class="sxs-lookup"><span data-stu-id="bbc43-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="bbc43-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bbc43-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bbc43-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bbc43-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbc43-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bbc43-115">See also</span></span>

- [<span data-ttu-id="bbc43-116">ICorPublishAppDomainEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bbc43-116">ICorPublishAppDomainEnum Interface</span></span>](icorpublishappdomainenum-interface.md)
