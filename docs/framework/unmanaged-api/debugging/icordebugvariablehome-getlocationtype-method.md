---
title: ICorDebugVariableHome::GetLocationType-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
api_name: ICorDebugVariableHome.GetLocationType
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugVariableHome::GetLocationType
helpviewer_keywords:
- ICorDebugVariableHome::GetLocationType method [.NET Framework debugging]
- GetLocationType method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: 88027c55-8ec6-4f1e-a55b-7eefdbbc3515
topic_type: apiref
caps.latest.revision: "3"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ec44705f75959dce893932789b026504d65a3105
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugvariablehomegetlocationtype-method"></a><span data-ttu-id="553e8-102">ICorDebugVariableHome::GetLocationType-Methode</span><span class="sxs-lookup"><span data-stu-id="553e8-102">ICorDebugVariableHome::GetLocationType Method</span></span>
<span data-ttu-id="553e8-103">Ruft den Typ des systemeigenen Speicherort der Variablen ab.</span><span class="sxs-lookup"><span data-stu-id="553e8-103">Gets the type of the variable's native location.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="553e8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="553e8-104">Syntax</span></span>  
  
```  
HRESULT GetLocationType(  
    [out] VariableLocationType *pLocationType  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="553e8-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="553e8-105">Parameters</span></span>  
 `pLocationType`  
 <span data-ttu-id="553e8-106">[out] Ein Zeiger auf den Typ des systemeigenen Standort die Variable.</span><span class="sxs-lookup"><span data-stu-id="553e8-106">[out] A pointer to the type of the variable's native location.</span></span>  <span data-ttu-id="553e8-107">Finden Sie unter der [VariableLocationType](../../../../docs/framework/unmanaged-api/debugging/variablelocationtype-enumeration.md) Enumeration für Weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="553e8-107">See the [VariableLocationType](../../../../docs/framework/unmanaged-api/debugging/variablelocationtype-enumeration.md) enumeration for more information.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="553e8-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="553e8-108">Requirements</span></span>  
 <span data-ttu-id="553e8-109">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="553e8-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="553e8-110">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="553e8-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="553e8-111">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="553e8-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="553e8-112">**.NET Framework-Versionen:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="553e8-112">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="553e8-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="553e8-113">See Also</span></span>  
 [<span data-ttu-id="553e8-114">ICorDebugVariableHome-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="553e8-114">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)  
 [<span data-ttu-id="553e8-115">VariableLocationType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="553e8-115">VariableLocationType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/variablelocationtype-enumeration.md)
