---
title: ICorDebugAssemblyEnum::Next-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugAssemblyEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssemblyEnum::Next method
helpviewer_keywords:
- ICorDebugAssemblyEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugAssemblyEnum interface [.NET Framework debugging]
ms.assetid: b3e7d0c2-3baa-4ef8-8e3f-b865cf252940
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 25861b2635605042acc1bf81f3f7a4739e678522
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57493111"
---
# <a name="icordebugassemblyenumnext-method"></a><span data-ttu-id="a3b30-102">ICorDebugAssemblyEnum::Next-Methode</span><span class="sxs-lookup"><span data-stu-id="a3b30-102">ICorDebugAssemblyEnum::Next Method</span></span>
<span data-ttu-id="a3b30-103">Ruft die angegebene Anzahl von Assemblys aus der Auflistung, beginnend ab der aktuellen Cursorposition ab.</span><span class="sxs-lookup"><span data-stu-id="a3b30-103">Gets the specified number of assemblies from the collection, starting at the current cursor position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3b30-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a3b30-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugAssembly *values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a3b30-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a3b30-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="a3b30-106">[in] Die Anzahl der Assemblys abgerufen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="a3b30-106">[in] The number of assemblies to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="a3b30-107">[out] Ein Array von Zeigern, von denen jeder zu einem ICorDebugAssembly-Objekt verweist, die eine Assembly darstellt.</span><span class="sxs-lookup"><span data-stu-id="a3b30-107">[out] An array of pointers, each of which points to an ICorDebugAssembly object that represents an assembly.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="a3b30-108">[out] Ein Zeiger auf die Anzahl der tatsächlich zurückgegebenen Assemblys.</span><span class="sxs-lookup"><span data-stu-id="a3b30-108">[out] A pointer to the number of assemblies actually returned.</span></span> <span data-ttu-id="a3b30-109">Dieser Wert kann null sein, wenn `celt` ist.</span><span class="sxs-lookup"><span data-stu-id="a3b30-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a3b30-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a3b30-110">Requirements</span></span>  
 <span data-ttu-id="a3b30-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a3b30-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a3b30-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a3b30-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a3b30-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a3b30-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a3b30-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a3b30-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
