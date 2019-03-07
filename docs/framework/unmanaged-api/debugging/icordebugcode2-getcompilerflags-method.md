---
title: ICorDebugCode2::GetCompilerFlags-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugCode2.GetCompilerFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode2::GetCompilerFlags
helpviewer_keywords:
- GetCompilerFlags method [.NET Framework debugging]
- ICorDebugCode2::GetCompilerFlags method [.NET Framework debugging]
ms.assetid: 532e9dfd-d114-4c75-b952-1accce102643
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6b2fb8e2594af27beac5e0386b7ecdc7ad3e436b
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57501413"
---
# <a name="icordebugcode2getcompilerflags-method"></a><span data-ttu-id="4fcfb-102">ICorDebugCode2::GetCompilerFlags-Methode</span><span class="sxs-lookup"><span data-stu-id="4fcfb-102">ICorDebugCode2::GetCompilerFlags Method</span></span>
<span data-ttu-id="4fcfb-103">Ruft die Flags ab, die die Bedingungen angeben, unter denen dieses Codeobjekt JIT-kompiliert (Just-In-Time) oder unter Verwendung des Native Image Generator (Ngen.exe) generiert wurde.</span><span class="sxs-lookup"><span data-stu-id="4fcfb-103">Gets the flags that specify the conditions under which this code object was either just-in-time (JIT) compiled or generated using the native image generator (Ngen.exe).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4fcfb-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4fcfb-104">Syntax</span></span>  
  
```  
HRESULT GetCompilerFlags (  
    [out] DWORD *pdwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4fcfb-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="4fcfb-105">Parameters</span></span>  
 `pdwFlags`  
 <span data-ttu-id="4fcfb-106">[out] Ein Zeiger auf den Wert der [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) -Enumeration, die das Verhalten des JIT-Compilers oder des native Image Generator angibt.</span><span class="sxs-lookup"><span data-stu-id="4fcfb-106">[out] A pointer to a value of the [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) enumeration that specifies the behavior of the JIT compiler or the native image generator.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4fcfb-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4fcfb-107">Requirements</span></span>  
 <span data-ttu-id="4fcfb-108">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4fcfb-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4fcfb-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4fcfb-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4fcfb-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4fcfb-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4fcfb-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4fcfb-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4fcfb-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4fcfb-112">See also</span></span>

