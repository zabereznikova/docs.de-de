---
title: ICorDebugCode4::EnumerateVariableHomes-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugCode4.EnumerateVariableHomes
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode4::EnumerateVariableHomes
helpviewer_keywords:
- EnumerateVariableHomes method [.NET Framework debugging]
- ICorDebugCode4::EnumerateVariableHomes method [.NET Framework debugging]
ms.assetid: 802c01ff-8b80-4733-b6dd-03ab6ff7fa11
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e0e6acdf6996f437c85b629b0af886287b1aef03
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67748561"
---
# <a name="icordebugcode4enumeratevariablehomes-method"></a><span data-ttu-id="3ac89-102">ICorDebugCode4::EnumerateVariableHomes-Methode</span><span class="sxs-lookup"><span data-stu-id="3ac89-102">ICorDebugCode4::EnumerateVariableHomes Method</span></span>
<span data-ttu-id="3ac89-103">Ruft einen Enumerator auf das lokale Variablen und Argumente in einer Funktion ab.</span><span class="sxs-lookup"><span data-stu-id="3ac89-103">Gets an enumerator to the local variables and arguments in a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ac89-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3ac89-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateVariableHomes(  
    [out] ICorDebugVariableHomeEnum **ppEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3ac89-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="3ac89-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="3ac89-106">Ein Zeiger auf die Adresse einer [ICorDebugVariableHomeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md) Schnittstellenobjekts, das einen Enumerator für die lokalen Variablen und Argumente in einer Funktion ist.</span><span class="sxs-lookup"><span data-stu-id="3ac89-106">A pointer to the address of an [ICorDebugVariableHomeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md) interface object that is an enumerator for the local variables and arguments in a function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3ac89-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3ac89-107">Remarks</span></span>  
 <span data-ttu-id="3ac89-108">Die [ICorDebugVariableHomeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md) -Schnittstellenobjekt wird einen Standardenumerator, die von der "ICorDebugEnum"-Schnittstelle, die Sie zum Aufzählen kann abgeleitet [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) Objekte.</span><span class="sxs-lookup"><span data-stu-id="3ac89-108">The [ICorDebugVariableHomeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md) interface object is a standard enumerator derived from the "ICorDebugEnum" interface that allows you to enumerate [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) objects.</span></span> <span data-ttu-id="3ac89-109">Fügen Sie die Auflistung kann mehrere [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) Objekte für den Slot oder das Argument Index ggf. verschiedene Häuser an verschiedenen Punkten in der Funktion.</span><span class="sxs-lookup"><span data-stu-id="3ac89-109">The collection may include multiple [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) objects for the same slot or      argument index if they have different homes at different points in the      function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3ac89-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3ac89-110">Requirements</span></span>  
 <span data-ttu-id="3ac89-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3ac89-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3ac89-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3ac89-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3ac89-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3ac89-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3ac89-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3ac89-114">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ac89-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3ac89-115">See also</span></span>

- [<span data-ttu-id="3ac89-116">ICorDebugCode4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3ac89-116">ICorDebugCode4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode4-interface.md)
- [<span data-ttu-id="3ac89-117">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="3ac89-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
