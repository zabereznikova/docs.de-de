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
ms.openlocfilehash: 00aff9ab4edbbebe4b924d335fa12f92e9840737
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95693696"
---
# <a name="icorpublishappdomainenumnext-method"></a><span data-ttu-id="65765-102">ICorPublishAppDomainEnum::Next-Methode</span><span class="sxs-lookup"><span data-stu-id="65765-102">ICorPublishAppDomainEnum::Next Method</span></span>

<span data-ttu-id="65765-103">Ruft die angegebene Anzahl von Anwendungs Domänen ab, die derzeit im Prozess vorhanden sind, beginnend an der aktuellen Position.</span><span class="sxs-lookup"><span data-stu-id="65765-103">Gets the specified number of application domains that currently exist in the process, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65765-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="65765-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]
        ICorPublishAppDomain **objects,  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="65765-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="65765-105">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="65765-106">in Die Anzahl der abzurufenden Elemente.</span><span class="sxs-lookup"><span data-stu-id="65765-106">[in] The number of elements to be retrieved.</span></span>  
  
 `objects`  
 <span data-ttu-id="65765-107">vorgenommen Ein Zeiger auf das Array von abgerufenen [ICorPublishAppDomain](icorpublishappdomain-interface.md) -Objekten, von denen jedes eine Anwendungsdomäne darstellt.</span><span class="sxs-lookup"><span data-stu-id="65765-107">[out] A pointer to the array of retrieved [ICorPublishAppDomain](icorpublishappdomain-interface.md) objects, each of which represents an application domain.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="65765-108">vorgenommen Ein Zeiger auf die Anzahl der tatsächlich zurückgegebenen Anwendungs Domänen.</span><span class="sxs-lookup"><span data-stu-id="65765-108">[out] Pointer to the number of application domains actually returned.</span></span> <span data-ttu-id="65765-109">Dieser Wert kann NULL sein, wenn `celt` ein Wert ist.</span><span class="sxs-lookup"><span data-stu-id="65765-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="65765-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="65765-110">Requirements</span></span>  

 <span data-ttu-id="65765-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="65765-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="65765-112">**Header:** Corpub. idl, Corpub. h</span><span class="sxs-lookup"><span data-stu-id="65765-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="65765-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="65765-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="65765-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="65765-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65765-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="65765-115">See also</span></span>

- [<span data-ttu-id="65765-116">ICorPublishAppDomainEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="65765-116">ICorPublishAppDomainEnum Interface</span></span>](icorpublishappdomainenum-interface.md)
