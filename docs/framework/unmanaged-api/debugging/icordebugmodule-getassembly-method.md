---
title: ICorDebugModule::GetAssembly-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugModule.GetAssembly
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugModule::GetAssembly
helpviewer_keywords:
- ICorDebugModule::GetAssembly method [.NET Framework debugging]
- GetAssembly method [.NET Framework debugging]
ms.assetid: 989762c4-3d15-4485-b8ee-69e0fa8ec895
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7b359b68c1bff91e1077afe8ccf52befe22c246b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmodulegetassembly-method"></a><span data-ttu-id="07da5-102">ICorDebugModule::GetAssembly-Methode</span><span class="sxs-lookup"><span data-stu-id="07da5-102">ICorDebugModule::GetAssembly Method</span></span>
<span data-ttu-id="07da5-103">Ruft die enthaltende Assembly für dieses Modul ab.</span><span class="sxs-lookup"><span data-stu-id="07da5-103">Gets the containing assembly for this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="07da5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="07da5-104">Syntax</span></span>  
  
```  
HRESULT GetAssembly(  
    [out] ICorDebugAssembly **ppAssembly  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="07da5-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="07da5-105">Parameters</span></span>  
 `ppAssembly`  
 <span data-ttu-id="07da5-106">[out] Ein Zeiger auf ein ICorDebugAssembly-Objekt, das die Assembly mit diesem Modul darstellt.</span><span class="sxs-lookup"><span data-stu-id="07da5-106">[out] A pointer to an ICorDebugAssembly object that represents the assembly containing this module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="07da5-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="07da5-107">Requirements</span></span>  
 <span data-ttu-id="07da5-108">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="07da5-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="07da5-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="07da5-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="07da5-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="07da5-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="07da5-111">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="07da5-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
