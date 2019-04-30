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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c14d364320c82f061ef606a402563dacfce28139
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61986647"
---
# <a name="icorpublishappdomainenumnext-method"></a><span data-ttu-id="24ed0-102">ICorPublishAppDomainEnum::Next-Methode</span><span class="sxs-lookup"><span data-stu-id="24ed0-102">ICorPublishAppDomainEnum::Next Method</span></span>
<span data-ttu-id="24ed0-103">Ruft die angegebene Anzahl von Anwendungsdomänen, die derzeit vorhandenen in den Prozess, beginnend mit der aktuellen Position ab.</span><span class="sxs-lookup"><span data-stu-id="24ed0-103">Gets the specified number of application domains that currently exist in the process, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24ed0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="24ed0-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]   
        ICorPublishAppDomain **objects,  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="24ed0-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="24ed0-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="24ed0-106">[in] Die Anzahl der Elemente abgerufen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="24ed0-106">[in] The number of elements to be retrieved.</span></span>  
  
 `objects`  
 <span data-ttu-id="24ed0-107">[out] Ein Zeiger auf das Array der abgerufenen [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md) Objekte, von denen jedes eine Anwendungsdomäne darstellt.</span><span class="sxs-lookup"><span data-stu-id="24ed0-107">[out] A pointer to the array of retrieved [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md) objects, each of which represents an application domain.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="24ed0-108">[out] Zeiger auf die Anzahl von Anwendungsdomänen, die tatsächlich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="24ed0-108">[out] Pointer to the number of application domains actually returned.</span></span> <span data-ttu-id="24ed0-109">Dieser Wert kann null sein, wenn `celt` ist.</span><span class="sxs-lookup"><span data-stu-id="24ed0-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="24ed0-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="24ed0-110">Requirements</span></span>  
 <span data-ttu-id="24ed0-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="24ed0-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="24ed0-112">**Header:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="24ed0-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="24ed0-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="24ed0-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="24ed0-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="24ed0-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24ed0-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="24ed0-115">See also</span></span>

- [<span data-ttu-id="24ed0-116">ICorPublishAppDomainEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="24ed0-116">ICorPublishAppDomainEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md)
