---
title: ICorDebugModule::IsInMemory-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugModule.IsInMemory
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::IsInMemory
helpviewer_keywords:
- IsInMemory method [.NET Framework debugging]
- ICorDebugModule::IsInMemory method [.NET Framework debugging]
ms.assetid: 89940711-98e7-4aa6-bffc-5e39e91e1b7d
topic_type:
- apiref
ms.openlocfilehash: 637cac67e73d38aca0fdc5eaeae5405c4a859aa3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95709816"
---
# <a name="icordebugmoduleisinmemory-method"></a><span data-ttu-id="6ef0c-102">ICorDebugModule::IsInMemory-Methode</span><span class="sxs-lookup"><span data-stu-id="6ef0c-102">ICorDebugModule::IsInMemory Method</span></span>

<span data-ttu-id="6ef0c-103">Ruft einen Wert ab, der angibt, ob dieses Modul nur im Arbeitsspeicher vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="6ef0c-103">Gets a value that indicates whether this module exists only in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ef0c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6ef0c-104">Syntax</span></span>  
  
```cpp  
HRESULT IsInMemory(  
    [out] BOOL *pInMemory  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6ef0c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="6ef0c-105">Parameters</span></span>  

 `pInMemory`  
 <span data-ttu-id="6ef0c-106">[out] `true` , wenn dieses Modul nur im Arbeitsspeicher vorhanden ist. andernfalls `false` .</span><span class="sxs-lookup"><span data-stu-id="6ef0c-106">[out] `true` if this module exists only in memory; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6ef0c-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6ef0c-107">Remarks</span></span>  

 <span data-ttu-id="6ef0c-108">Der Common Language Runtime (CLR) unterstützt das Laden von Modulen aus unformatierten Datenströmen.</span><span class="sxs-lookup"><span data-stu-id="6ef0c-108">The common language runtime (CLR) supports the loading of modules from raw streams of bytes.</span></span> <span data-ttu-id="6ef0c-109">Solche Module werden als *in-Memory-Module* bezeichnet und sind auf dem Datenträger nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="6ef0c-109">Such modules are called *in-memory modules* and do not exist on disk.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6ef0c-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="6ef0c-110">Requirements</span></span>  

 <span data-ttu-id="6ef0c-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6ef0c-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6ef0c-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6ef0c-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6ef0c-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6ef0c-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6ef0c-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6ef0c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ef0c-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6ef0c-115">See also</span></span>
