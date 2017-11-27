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
ms.openlocfilehash: 4623f4bb1af21d19446b4e0f65dd5d826c412ccd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugcode4enumeratevariablehomes-method"></a><span data-ttu-id="59522-102">ICorDebugCode4::EnumerateVariableHomes-Methode</span><span class="sxs-lookup"><span data-stu-id="59522-102">ICorDebugCode4::EnumerateVariableHomes Method</span></span>
<span data-ttu-id="59522-103">Ruft einen Enumerator für die lokalen Variablen und Argumente in einer Funktion ab.</span><span class="sxs-lookup"><span data-stu-id="59522-103">Gets an enumerator to the local variables and arguments in a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59522-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="59522-104">Syntax</span></span>  
  
```  
HRESULT EnumerateVariableHomes(  
    [out] ICorDebugVariableHomeEnum **ppEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="59522-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="59522-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="59522-106">Ein Zeiger auf die Adresse des ein [ICorDebugVariableHomeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md) Schnittstellenobjekts, das einen Enumerator für die lokalen Variablen und Argumente in einer Funktion ist.</span><span class="sxs-lookup"><span data-stu-id="59522-106">A pointer to the address of an [ICorDebugVariableHomeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md) interface object that is an enumerator for the local variables and arguments in a function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="59522-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="59522-107">Remarks</span></span>  
 <span data-ttu-id="59522-108">Die [ICorDebugVariableHomeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md) -Schnittstellenobjekt ist ein standard Enumerator, der die "ICorDebugEnum"-Schnittstelle, die Ihnen ermöglicht, Auflisten von abgeleitet [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) Objekte.</span><span class="sxs-lookup"><span data-stu-id="59522-108">The [ICorDebugVariableHomeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md) interface object is a standard enumerator derived from the "ICorDebugEnum" interface that allows you to enumerate [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) objects.</span></span> <span data-ttu-id="59522-109">Die Auflistung eventuell mehrere [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) von Objekten für die gleichen Slot oder ein Argument Index besäßen sie unterschiedliche greift an verschiedenen Punkten in der Funktion.</span><span class="sxs-lookup"><span data-stu-id="59522-109">The collection may include multiple [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) objects for the same slot or      argument index if they have different homes at different points in the      function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="59522-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="59522-110">Requirements</span></span>  
 <span data-ttu-id="59522-111">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="59522-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="59522-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="59522-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="59522-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="59522-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="59522-114">**.NET Framework-Versionen:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="59522-114">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59522-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="59522-115">See Also</span></span>  
 [<span data-ttu-id="59522-116">ICorDebugCode4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="59522-116">ICorDebugCode4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode4-interface.md)  
 [<span data-ttu-id="59522-117">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="59522-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
