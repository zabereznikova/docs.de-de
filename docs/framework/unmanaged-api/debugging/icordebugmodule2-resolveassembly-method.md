---
title: ICorDebugModule2::ResolveAssembly-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugModule2.ResolveAssembly
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugModule2::ResolveAssembly
helpviewer_keywords:
- ICorDebugModule2::ResolveAssembly method [.NET Framework debugging]
- ResolveAssembly method [.NET Framework debugging]
ms.assetid: ddf9085c-7161-44bd-9609-cd2732b9009f
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 37ddb0e8871d9ec5f8eed4f00d81098feafb01de
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugmodule2resolveassembly-method"></a><span data-ttu-id="dcaad-102">ICorDebugModule2::ResolveAssembly-Methode</span><span class="sxs-lookup"><span data-stu-id="dcaad-102">ICorDebugModule2::ResolveAssembly Method</span></span>
<span data-ttu-id="dcaad-103">Löst die Assembly auf, die vom angegebenen Metadatentoken verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="dcaad-103">Resolves the assembly referenced by the specified metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dcaad-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="dcaad-104">Syntax</span></span>  
  
```  
HRESULT ResolveAssembly (  
    [in]  mdToken             tkAssemblyRef,  
    [out] ICorDebugAssembly   **ppAssembly  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="dcaad-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="dcaad-105">Parameters</span></span>  
 `tkAsemblyRef`  
 <span data-ttu-id="dcaad-106">[in] Ein `mdToken` Wert, der die Assembly verweist.</span><span class="sxs-lookup"><span data-stu-id="dcaad-106">[in] An `mdToken` value that references the assembly.</span></span>  
  
 `ppAssembly`  
 <span data-ttu-id="dcaad-107">[out] Ein Zeiger auf die Adresse eines ICorDebugAssembly-Objekts, das die Assembly darstellt.</span><span class="sxs-lookup"><span data-stu-id="dcaad-107">[out] A pointer to the address of an ICorDebugAssembly object that represents the assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dcaad-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="dcaad-108">Remarks</span></span>  
 <span data-ttu-id="dcaad-109">Wenn die Assembly nicht bereits geladen ist `ResolveAssembly` aufgerufen wird, wird ein HRESULT Wert CORDBG_E_CANNOT_RESOLVE_ASSEMBLY zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="dcaad-109">If the assembly is not already loaded when `ResolveAssembly` is called, an HRESULT value of CORDBG_E_CANNOT_RESOLVE_ASSEMBLY is returned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dcaad-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="dcaad-110">Requirements</span></span>  
 <span data-ttu-id="dcaad-111">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dcaad-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dcaad-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dcaad-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dcaad-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dcaad-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dcaad-114">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dcaad-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
