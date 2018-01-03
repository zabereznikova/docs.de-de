---
title: ICorDebugFunction::GetModule-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugFunction.GetModule
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugFunction::GetModule
helpviewer_keywords:
- ICorDebugFunction::GetModule method [.NET Framework debugging]
- GetModule method, ICorDebugFunction interface [.NET Framework debugging]
ms.assetid: 5031a5d3-2564-412a-9007-e36d4631308a
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 59808b2a1de969f7d530a1be4cb500fc32cec33f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugfunctiongetmodule-method"></a><span data-ttu-id="e68aa-102">ICorDebugFunction::GetModule-Methode</span><span class="sxs-lookup"><span data-stu-id="e68aa-102">ICorDebugFunction::GetModule Method</span></span>
<span data-ttu-id="e68aa-103">Ruft das Modul, in dem diese Funktion definiert ist.</span><span class="sxs-lookup"><span data-stu-id="e68aa-103">Gets the module in which this function is defined.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e68aa-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e68aa-104">Syntax</span></span>  
  
```  
HRESULT GetModule (  
    [out] ICorDebugModule **ppModule  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e68aa-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e68aa-105">Parameters</span></span>  
 `ppModule`  
 <span data-ttu-id="e68aa-106">[out] Ein Zeiger auf die Adresse eines ICorDebugModule-Objekts, das das Modul darstellt, in dem diese Funktion definiert ist.</span><span class="sxs-lookup"><span data-stu-id="e68aa-106">[out] A pointer to the address of an ICorDebugModule object that represents the module in which this function is defined.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e68aa-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e68aa-107">Requirements</span></span>  
 <span data-ttu-id="e68aa-108">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e68aa-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e68aa-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e68aa-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e68aa-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e68aa-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e68aa-111">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e68aa-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
