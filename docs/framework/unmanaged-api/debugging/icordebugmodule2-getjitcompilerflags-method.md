---
title: ICorDebugModule2::GetJITCompilerFlags-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugModule2.GetJITCompilerFlags
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugModule2::GetJITCompilerFlags
helpviewer_keywords:
- GetJITCompilerFlags method [.NET Framework debugging]
- ICorDebugModule2::GetJITCompilerFlags method [.NET Framework debugging]
ms.assetid: 7212d9f4-989b-44e3-b8d4-ffc35922f6a0
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 25830b2d6ae7aedba0bb0ec0447d0b10605453eb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmodule2getjitcompilerflags-method"></a><span data-ttu-id="8a8ce-102">ICorDebugModule2::GetJITCompilerFlags-Methode</span><span class="sxs-lookup"><span data-stu-id="8a8ce-102">ICorDebugModule2::GetJITCompilerFlags Method</span></span>
<span data-ttu-id="8a8ce-103">Ruft die Flags, die die Just-in-Time (JIT)-Kompilierung für diese ICorDebugModule2 steuern.</span><span class="sxs-lookup"><span data-stu-id="8a8ce-103">Gets the flags that control the just-in-time (JIT) compilation of this ICorDebugModule2.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a8ce-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8a8ce-104">Syntax</span></span>  
  
```  
HRESULT GetJITCompilerFlags (  
    [out] DWORD   *pdwFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8a8ce-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="8a8ce-105">Parameters</span></span>  
 `pdwFlags`  
 <span data-ttu-id="8a8ce-106">[out] Ein Zeiger auf den Wert der [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) -Enumeration, die die JIT-Kompilierung steuert.</span><span class="sxs-lookup"><span data-stu-id="8a8ce-106">[out] A pointer to a value of the [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) enumeration that controls the JIT compilation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a8ce-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8a8ce-107">Requirements</span></span>  
 <span data-ttu-id="8a8ce-108">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8a8ce-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a8ce-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8a8ce-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8a8ce-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8a8ce-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8a8ce-111">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8a8ce-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
