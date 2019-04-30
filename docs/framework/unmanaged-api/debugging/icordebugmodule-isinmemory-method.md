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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d79a8b0c3c56ffe2b8f57ec26f5942ee0d681194
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61994837"
---
# <a name="icordebugmoduleisinmemory-method"></a><span data-ttu-id="21ce2-102">ICorDebugModule::IsInMemory-Methode</span><span class="sxs-lookup"><span data-stu-id="21ce2-102">ICorDebugModule::IsInMemory Method</span></span>
<span data-ttu-id="21ce2-103">Ruft einen Wert, der angibt, ob dieses Modul nur im Arbeitsspeicher vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="21ce2-103">Gets a value that indicates whether this module exists only in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21ce2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="21ce2-104">Syntax</span></span>  
  
```  
HRESULT IsInMemory(  
    [out] BOOL *pInMemory  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="21ce2-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="21ce2-105">Parameters</span></span>  
 `pInMemory`  
 <span data-ttu-id="21ce2-106">[out] `true` Wenn dieses Modul nur im Speicher vorhanden ist, andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="21ce2-106">[out] `true` if this module exists only in memory; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="21ce2-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="21ce2-107">Remarks</span></span>  
 <span data-ttu-id="21ce2-108">Die common Language Runtime (CLR) unterstützt das Laden der Module von unformatierte Bytedatenströme.</span><span class="sxs-lookup"><span data-stu-id="21ce2-108">The common language runtime (CLR) supports the loading of modules from raw streams of bytes.</span></span> <span data-ttu-id="21ce2-109">Solcher Module heißen *in-Memory-Module* und sind nicht auf dem Datenträger vorhanden.</span><span class="sxs-lookup"><span data-stu-id="21ce2-109">Such modules are called *in-memory modules* and do not exist on disk.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="21ce2-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="21ce2-110">Requirements</span></span>  
 <span data-ttu-id="21ce2-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="21ce2-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="21ce2-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="21ce2-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="21ce2-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="21ce2-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="21ce2-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="21ce2-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21ce2-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="21ce2-115">See also</span></span>
