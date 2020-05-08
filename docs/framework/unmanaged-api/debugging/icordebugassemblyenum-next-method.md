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
ms.openlocfilehash: 155354b335caf83c466c8d9d6711f36c7efc9298
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894811"
---
# <a name="icordebugassemblyenumnext-method"></a><span data-ttu-id="a3c49-102">ICorDebugAssemblyEnum::Next-Methode</span><span class="sxs-lookup"><span data-stu-id="a3c49-102">ICorDebugAssemblyEnum::Next Method</span></span>
<span data-ttu-id="a3c49-103">Ruft die angegebene Anzahl von Assemblys aus der Auflistung ab, beginnend bei der aktuellen Cursorposition.</span><span class="sxs-lookup"><span data-stu-id="a3c49-103">Gets the specified number of assemblies from the collection, starting at the current cursor position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3c49-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a3c49-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugAssembly *values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a3c49-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a3c49-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="a3c49-106">in Die Anzahl der abzurufenden Assemblys.</span><span class="sxs-lookup"><span data-stu-id="a3c49-106">[in] The number of assemblies to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="a3c49-107">vorgenommen Ein Array von Zeigern, von denen jedes auf ein ICorDebug-Objekt verweist, das eine Assembly darstellt.</span><span class="sxs-lookup"><span data-stu-id="a3c49-107">[out] An array of pointers, each of which points to an ICorDebugAssembly object that represents an assembly.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="a3c49-108">vorgenommen Ein Zeiger auf die Anzahl der tatsächlich zurückgegebenen Assemblys.</span><span class="sxs-lookup"><span data-stu-id="a3c49-108">[out] A pointer to the number of assemblies actually returned.</span></span> <span data-ttu-id="a3c49-109">Dieser Wert kann NULL sein, `celt` wenn ein Wert ist.</span><span class="sxs-lookup"><span data-stu-id="a3c49-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a3c49-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a3c49-110">Requirements</span></span>  
 <span data-ttu-id="a3c49-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a3c49-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a3c49-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a3c49-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a3c49-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a3c49-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a3c49-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a3c49-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
