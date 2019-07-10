---
title: ICorDebugAppDomainEnum::Next-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomainEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomainEnum::Next method
helpviewer_keywords:
- ICorDebugAppDomainEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugAppDomainEnum interface [.NET Framework debugging]
ms.assetid: b8d1def7-0ebc-4314-a3a2-fd36a75973e7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 12787382686cc056c157ed7a6e8e4984ab93588f
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67737611"
---
# <a name="icordebugappdomainenumnext-method"></a><span data-ttu-id="c211e-102">ICorDebugAppDomainEnum::Next-Methode</span><span class="sxs-lookup"><span data-stu-id="c211e-102">ICorDebugAppDomainEnum::Next Method</span></span>
<span data-ttu-id="c211e-103">Ruft die angegebene Anzahl von Anwendungsdomänen aus der Auflistung, beginnend ab der aktuellen Cursorposition ab.</span><span class="sxs-lookup"><span data-stu-id="c211e-103">Gets the specified number of application domains from the collection, starting at the current cursor position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c211e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c211e-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
                           ICorDebugAppDomain *values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c211e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c211e-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="c211e-106">[in] Die Anzahl von Anwendungsdomänen abgerufen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="c211e-106">[in] The number of application domains to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="c211e-107">[out] Ein Array von Zeigern, von denen jeder zu einem ICorDebugAppDomain-Objekt verweist, die eine Anwendungsdomäne darstellt.</span><span class="sxs-lookup"><span data-stu-id="c211e-107">[out] An array of pointers, each of which points to an ICorDebugAppDomain object that represents an application domain.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="c211e-108">[out] Ein Zeiger auf die Anzahl von Anwendungsdomänen, die tatsächlich zurückgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="c211e-108">[out] A pointer to the number of application domains actually returned.</span></span> <span data-ttu-id="c211e-109">Dieser Wert kann null sein, wenn `celt` ist.</span><span class="sxs-lookup"><span data-stu-id="c211e-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c211e-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c211e-110">Requirements</span></span>  
 <span data-ttu-id="c211e-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c211e-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c211e-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c211e-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c211e-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c211e-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c211e-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c211e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
