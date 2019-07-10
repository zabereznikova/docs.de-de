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
ms.openlocfilehash: 223989d883c421be228fb3d6a608643a5246c060
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67763702"
---
# <a name="icordebugmoduleisinmemory-method"></a><span data-ttu-id="0dba9-102">ICorDebugModule::IsInMemory-Methode</span><span class="sxs-lookup"><span data-stu-id="0dba9-102">ICorDebugModule::IsInMemory Method</span></span>
<span data-ttu-id="0dba9-103">Ruft einen Wert, der angibt, ob dieses Modul nur im Arbeitsspeicher vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="0dba9-103">Gets a value that indicates whether this module exists only in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0dba9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0dba9-104">Syntax</span></span>  
  
```cpp  
HRESULT IsInMemory(  
    [out] BOOL *pInMemory  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0dba9-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="0dba9-105">Parameters</span></span>  
 `pInMemory`  
 <span data-ttu-id="0dba9-106">[out] `true` Wenn dieses Modul nur im Speicher vorhanden ist, andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="0dba9-106">[out] `true` if this module exists only in memory; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0dba9-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0dba9-107">Remarks</span></span>  
 <span data-ttu-id="0dba9-108">Die common Language Runtime (CLR) unterstützt das Laden der Module von unformatierte Bytedatenströme.</span><span class="sxs-lookup"><span data-stu-id="0dba9-108">The common language runtime (CLR) supports the loading of modules from raw streams of bytes.</span></span> <span data-ttu-id="0dba9-109">Solcher Module heißen *in-Memory-Module* und sind nicht auf dem Datenträger vorhanden.</span><span class="sxs-lookup"><span data-stu-id="0dba9-109">Such modules are called *in-memory modules* and do not exist on disk.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0dba9-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0dba9-110">Requirements</span></span>  
 <span data-ttu-id="0dba9-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0dba9-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0dba9-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0dba9-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0dba9-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0dba9-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0dba9-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0dba9-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0dba9-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0dba9-115">See also</span></span>
