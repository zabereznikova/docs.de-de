---
title: ICorDebugModule2::GetJITCompilerFlags-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugModule2.GetJITCompilerFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule2::GetJITCompilerFlags
helpviewer_keywords:
- GetJITCompilerFlags method [.NET Framework debugging]
- ICorDebugModule2::GetJITCompilerFlags method [.NET Framework debugging]
ms.assetid: 7212d9f4-989b-44e3-b8d4-ffc35922f6a0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4bb275f08143362d62f241ea659ea39ff8eef5d0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33413081"
---
# <a name="icordebugmodule2getjitcompilerflags-method"></a><span data-ttu-id="9f5db-102">ICorDebugModule2::GetJITCompilerFlags-Methode</span><span class="sxs-lookup"><span data-stu-id="9f5db-102">ICorDebugModule2::GetJITCompilerFlags Method</span></span>
<span data-ttu-id="9f5db-103">Ruft die Flags, die die Just-in-Time (JIT)-Kompilierung für diese ICorDebugModule2 steuern.</span><span class="sxs-lookup"><span data-stu-id="9f5db-103">Gets the flags that control the just-in-time (JIT) compilation of this ICorDebugModule2.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f5db-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9f5db-104">Syntax</span></span>  
  
```  
HRESULT GetJITCompilerFlags (  
    [out] DWORD   *pdwFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9f5db-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="9f5db-105">Parameters</span></span>  
 `pdwFlags`  
 <span data-ttu-id="9f5db-106">[out] Ein Zeiger auf den Wert der [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) -Enumeration, die die JIT-Kompilierung steuert.</span><span class="sxs-lookup"><span data-stu-id="9f5db-106">[out] A pointer to a value of the [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) enumeration that controls the JIT compilation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9f5db-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9f5db-107">Requirements</span></span>  
 <span data-ttu-id="9f5db-108">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9f5db-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9f5db-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9f5db-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9f5db-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9f5db-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9f5db-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9f5db-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
