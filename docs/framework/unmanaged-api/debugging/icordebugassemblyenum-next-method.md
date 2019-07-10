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
ms.openlocfilehash: 00adc852a0940766cdd4188ffa5d6be2b472e51f
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67744877"
---
# <a name="icordebugassemblyenumnext-method"></a><span data-ttu-id="14b48-102">ICorDebugAssemblyEnum::Next-Methode</span><span class="sxs-lookup"><span data-stu-id="14b48-102">ICorDebugAssemblyEnum::Next Method</span></span>
<span data-ttu-id="14b48-103">Ruft die angegebene Anzahl von Assemblys aus der Auflistung, beginnend ab der aktuellen Cursorposition ab.</span><span class="sxs-lookup"><span data-stu-id="14b48-103">Gets the specified number of assemblies from the collection, starting at the current cursor position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14b48-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="14b48-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugAssembly *values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="14b48-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="14b48-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="14b48-106">[in] Die Anzahl der Assemblys abgerufen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="14b48-106">[in] The number of assemblies to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="14b48-107">[out] Ein Array von Zeigern, von denen jeder zu einem ICorDebugAssembly-Objekt verweist, die eine Assembly darstellt.</span><span class="sxs-lookup"><span data-stu-id="14b48-107">[out] An array of pointers, each of which points to an ICorDebugAssembly object that represents an assembly.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="14b48-108">[out] Ein Zeiger auf die Anzahl der tatsächlich zurückgegebenen Assemblys.</span><span class="sxs-lookup"><span data-stu-id="14b48-108">[out] A pointer to the number of assemblies actually returned.</span></span> <span data-ttu-id="14b48-109">Dieser Wert kann null sein, wenn `celt` ist.</span><span class="sxs-lookup"><span data-stu-id="14b48-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="14b48-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="14b48-110">Requirements</span></span>  
 <span data-ttu-id="14b48-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="14b48-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="14b48-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="14b48-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="14b48-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="14b48-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="14b48-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="14b48-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
