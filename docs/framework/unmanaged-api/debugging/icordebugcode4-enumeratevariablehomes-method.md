---
title: ICorDebugCode4::EnumerateVariableHomes-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
api_name: ICorDebugCode4.EnumerateVariableHomes
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugCode4::EnumerateVariableHomes
helpviewer_keywords:
- EnumerateVariableHomes method [.NET Framework debugging]
- ICorDebugCode4::EnumerateVariableHomes method [.NET Framework debugging]
ms.assetid: 802c01ff-8b80-4733-b6dd-03ab6ff7fa11
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b1478ed89c216f9cd520bf1122571f09024283ac
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugcode4enumeratevariablehomes-method"></a><span data-ttu-id="7aa84-102">ICorDebugCode4::EnumerateVariableHomes-Methode</span><span class="sxs-lookup"><span data-stu-id="7aa84-102">ICorDebugCode4::EnumerateVariableHomes Method</span></span>
<span data-ttu-id="7aa84-103">Ruft einen Enumerator für die lokalen Variablen und Argumente in einer Funktion ab.</span><span class="sxs-lookup"><span data-stu-id="7aa84-103">Gets an enumerator to the local variables and arguments in a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7aa84-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7aa84-104">Syntax</span></span>  
  
```  
HRESULT EnumerateVariableHomes(  
    [out] ICorDebugVariableHomeEnum **ppEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7aa84-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="7aa84-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="7aa84-106">Ein Zeiger auf die Adresse des ein [ICorDebugVariableHomeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md) Schnittstellenobjekts, das einen Enumerator für die lokalen Variablen und Argumente in einer Funktion ist.</span><span class="sxs-lookup"><span data-stu-id="7aa84-106">A pointer to the address of an [ICorDebugVariableHomeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md) interface object that is an enumerator for the local variables and arguments in a function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7aa84-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7aa84-107">Remarks</span></span>  
 <span data-ttu-id="7aa84-108">Die [ICorDebugVariableHomeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md) -Schnittstellenobjekt ist ein standard Enumerator, der die "ICorDebugEnum"-Schnittstelle, die Ihnen ermöglicht, Auflisten von abgeleitet [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) Objekte.</span><span class="sxs-lookup"><span data-stu-id="7aa84-108">The [ICorDebugVariableHomeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md) interface object is a standard enumerator derived from the "ICorDebugEnum" interface that allows you to enumerate [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) objects.</span></span> <span data-ttu-id="7aa84-109">Die Auflistung eventuell mehrere [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) von Objekten für die gleichen Slot oder ein Argument Index besäßen sie unterschiedliche greift an verschiedenen Punkten in der Funktion.</span><span class="sxs-lookup"><span data-stu-id="7aa84-109">The collection may include multiple [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) objects for the same slot or      argument index if they have different homes at different points in the      function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7aa84-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7aa84-110">Requirements</span></span>  
 <span data-ttu-id="7aa84-111">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7aa84-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7aa84-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7aa84-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7aa84-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7aa84-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7aa84-114">**.NET Framework-Versionen:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7aa84-114">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7aa84-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7aa84-115">See Also</span></span>  
 [<span data-ttu-id="7aa84-116">ICorDebugCode4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7aa84-116">ICorDebugCode4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode4-interface.md)  
 [<span data-ttu-id="7aa84-117">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="7aa84-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
