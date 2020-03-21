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
ms.openlocfilehash: 6f7f400c51ded0b98c0c2286cb6f90bbd77e47d7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178396"
---
# <a name="icorpublishappdomainenumnext-method"></a><span data-ttu-id="667d4-102">ICorPublishAppDomainEnum::Next-Methode</span><span class="sxs-lookup"><span data-stu-id="667d4-102">ICorPublishAppDomainEnum::Next Method</span></span>
<span data-ttu-id="667d4-103">Ruft die angegebene Anzahl von Anwendungsdomänen ab, die derzeit im Prozess vorhanden sind, beginnend an der aktuellen Position.</span><span class="sxs-lookup"><span data-stu-id="667d4-103">Gets the specified number of application domains that currently exist in the process, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="667d4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="667d4-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]
        ICorPublishAppDomain **objects,  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="667d4-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="667d4-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="667d4-106">[in] Die Anzahl der abzuholenden Elemente.</span><span class="sxs-lookup"><span data-stu-id="667d4-106">[in] The number of elements to be retrieved.</span></span>  
  
 `objects`  
 <span data-ttu-id="667d4-107">[out] Ein Zeiger auf das Array der abgerufenen [ICorPublishAppDomain-Objekte,](icorpublishappdomain-interface.md) von denen jedes eine Anwendungsdomäne darstellt.</span><span class="sxs-lookup"><span data-stu-id="667d4-107">[out] A pointer to the array of retrieved [ICorPublishAppDomain](icorpublishappdomain-interface.md) objects, each of which represents an application domain.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="667d4-108">[out] Zeiger auf die Anzahl der tatsächlich zurückgegebenen Anwendungsdomänen.</span><span class="sxs-lookup"><span data-stu-id="667d4-108">[out] Pointer to the number of application domains actually returned.</span></span> <span data-ttu-id="667d4-109">Dieser Wert kann `celt` null sein, wenn es sich um einen Wert handelt.</span><span class="sxs-lookup"><span data-stu-id="667d4-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="667d4-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="667d4-110">Requirements</span></span>  
 <span data-ttu-id="667d4-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="667d4-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="667d4-112">**Kopfzeile:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="667d4-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="667d4-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="667d4-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="667d4-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="667d4-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="667d4-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="667d4-115">See also</span></span>

- [<span data-ttu-id="667d4-116">ICorPublishAppDomainEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="667d4-116">ICorPublishAppDomainEnum Interface</span></span>](icorpublishappdomainenum-interface.md)
