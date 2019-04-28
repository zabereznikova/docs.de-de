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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61645447"
---
# <a name="icordebugassemblyenumnext-method"></a><span data-ttu-id="6270a-102">ICorDebugAssemblyEnum::Next-Methode</span><span class="sxs-lookup"><span data-stu-id="6270a-102">ICorDebugAssemblyEnum::Next Method</span></span>
<span data-ttu-id="6270a-103">Ruft die angegebene Anzahl von Assemblys aus der Auflistung, beginnend ab der aktuellen Cursorposition ab.</span><span class="sxs-lookup"><span data-stu-id="6270a-103">Gets the specified number of assemblies from the collection, starting at the current cursor position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6270a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6270a-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugAssembly *values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6270a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="6270a-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="6270a-106">[in] Die Anzahl der Assemblys abgerufen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="6270a-106">[in] The number of assemblies to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="6270a-107">[out] Ein Array von Zeigern, von denen jeder zu einem ICorDebugAssembly-Objekt verweist, die eine Assembly darstellt.</span><span class="sxs-lookup"><span data-stu-id="6270a-107">[out] An array of pointers, each of which points to an ICorDebugAssembly object that represents an assembly.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="6270a-108">[out] Ein Zeiger auf die Anzahl der tatsächlich zurückgegebenen Assemblys.</span><span class="sxs-lookup"><span data-stu-id="6270a-108">[out] A pointer to the number of assemblies actually returned.</span></span> <span data-ttu-id="6270a-109">Dieser Wert kann null sein, wenn `celt` ist.</span><span class="sxs-lookup"><span data-stu-id="6270a-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6270a-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6270a-110">Requirements</span></span>  
 <span data-ttu-id="6270a-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6270a-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6270a-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6270a-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6270a-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6270a-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6270a-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6270a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
