---
title: ICorDebugProcessEnum::Next-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugProcessEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcessEnum::Next
helpviewer_keywords:
- Next method, ICorDebugProcessEnum interface [.NET Framework debugging]
- ICorDebugProcessEnum::Next method [.NET Framework debugging]
ms.assetid: 4ac7077c-8d88-49c4-b360-b3af0c541c63
topic_type:
- apiref
ms.openlocfilehash: 0666becb5a34688d3f4cf5bddd1e2fa71785b38a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139790"
---
# <a name="icordebugprocessenumnext-method"></a><span data-ttu-id="acc42-102">ICorDebugProcessEnum::Next-Methode</span><span class="sxs-lookup"><span data-stu-id="acc42-102">ICorDebugProcessEnum::Next Method</span></span>
<span data-ttu-id="acc42-103">Ruft die angegebene Anzahl von ICorDebugProcess-Instanzen aus der-Enumeration ab, beginnend bei der aktuellen Position.</span><span class="sxs-lookup"><span data-stu-id="acc42-103">Gets the specified number of ICorDebugProcess instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="acc42-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="acc42-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in]  ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugProcess *processes[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="acc42-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="acc42-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="acc42-106">in Die Anzahl der `ICorDebugProcess` Instanzen, die abgerufen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="acc42-106">[in] The number of `ICorDebugProcess` instances to be retrieved.</span></span>  
  
 `processes`  
 <span data-ttu-id="acc42-107">vorgenommen Ein Array von Zeigern, von denen jedes auf ein `ICorDebugProcess` Objekt verweist, das einen Prozess darstellt.</span><span class="sxs-lookup"><span data-stu-id="acc42-107">[out] An array of pointers, each of which points to an `ICorDebugProcess` object that represents a process.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="acc42-108">vorgenommen Ein Zeiger auf die Anzahl von `ICorDebugProcess` Instanzen, die tatsächlich zurückgegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="acc42-108">[out] Pointer to the number of `ICorDebugProcess` instances actually returned.</span></span> <span data-ttu-id="acc42-109">Dieser Wert kann NULL sein, wenn `celt` ein Wert ist.</span><span class="sxs-lookup"><span data-stu-id="acc42-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="acc42-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="acc42-110">Requirements</span></span>  
 <span data-ttu-id="acc42-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="acc42-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="acc42-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="acc42-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="acc42-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="acc42-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="acc42-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="acc42-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
