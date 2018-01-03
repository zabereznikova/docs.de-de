---
title: ICorDebugEnum::GetCount-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugEnum.GetCount
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugEnum::GetCount
helpviewer_keywords:
- ICorDebugEnum::GetCount method [.NET Framework debugging]
- GetCount method, ICorDebugEnum interface [.NET Framework debugging]
ms.assetid: d8a74304-1cb2-4977-a21d-e1af48c563ff
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b2be2e198007e15a0bae3ba0d3dd0cf1cf9983c6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugenumgetcount-method"></a><span data-ttu-id="c8efc-102">ICorDebugEnum::GetCount-Methode</span><span class="sxs-lookup"><span data-stu-id="c8efc-102">ICorDebugEnum::GetCount Method</span></span>
<span data-ttu-id="c8efc-103">Ruft die Anzahl der Elemente in der Enumeration.</span><span class="sxs-lookup"><span data-stu-id="c8efc-103">Gets the number of items in the enumeration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8efc-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c8efc-104">Syntax</span></span>  
  
```  
HRESULT GetCount (  
    [out] ULONG *pcelt  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c8efc-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c8efc-105">Parameters</span></span>  
 `pcelt`  
 <span data-ttu-id="c8efc-106">[out] Ein Zeiger auf die Anzahl der Elemente in der Enumeration.</span><span class="sxs-lookup"><span data-stu-id="c8efc-106">[out] A pointer to the number of items in the enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c8efc-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c8efc-107">Requirements</span></span>  
 <span data-ttu-id="c8efc-108">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c8efc-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c8efc-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c8efc-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c8efc-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c8efc-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c8efc-111">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c8efc-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
