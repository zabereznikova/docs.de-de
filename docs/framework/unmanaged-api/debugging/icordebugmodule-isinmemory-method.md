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
ms.openlocfilehash: 9ae5c16f9f508511e4a15b2eae2c28d68238f1d7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33415892"
---
# <a name="icordebugmoduleisinmemory-method"></a><span data-ttu-id="1855b-102">ICorDebugModule::IsInMemory-Methode</span><span class="sxs-lookup"><span data-stu-id="1855b-102">ICorDebugModule::IsInMemory Method</span></span>
<span data-ttu-id="1855b-103">Ruft einen Wert, der angibt, ob dieses Modul nur im Arbeitsspeicher vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="1855b-103">Gets a value that indicates whether this module exists only in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1855b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1855b-104">Syntax</span></span>  
  
```  
HRESULT IsInMemory(  
    [out] BOOL *pInMemory  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1855b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="1855b-105">Parameters</span></span>  
 `pInMemory`  
 <span data-ttu-id="1855b-106">[out] `true` Wenn dieses Modul nur im Arbeitsspeicher vorhanden ist, andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="1855b-106">[out] `true` if this module exists only in memory; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1855b-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1855b-107">Remarks</span></span>  
 <span data-ttu-id="1855b-108">Die common Language Runtime (CLR) unterstützt das Laden von Modulen aus unformatierten Bytestreams.</span><span class="sxs-lookup"><span data-stu-id="1855b-108">The common language runtime (CLR) supports the loading of modules from raw streams of bytes.</span></span> <span data-ttu-id="1855b-109">Solche Module heißen *in-Memory-Module* und sind nicht auf dem Datenträger vorhanden.</span><span class="sxs-lookup"><span data-stu-id="1855b-109">Such modules are called *in-memory modules* and do not exist on disk.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1855b-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1855b-110">Requirements</span></span>  
 <span data-ttu-id="1855b-111">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1855b-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1855b-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1855b-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1855b-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1855b-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1855b-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1855b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1855b-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1855b-115">See Also</span></span>  
    
 
