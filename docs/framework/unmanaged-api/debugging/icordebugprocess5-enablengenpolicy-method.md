---
title: ICorDebugProcess5::EnableNGENPolicy-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5::EnableNGenPolicy
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::EnableNGENPolicy
helpviewer_keywords:
- ICorDebugProcess5::EnableNGENPolicy method [.NET Framework debugging]
- EnableNGENPolicy method, ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: 3b8e15ca-3c72-4685-a937-da4c739cb9e9
topic_type:
- apiref
ms.openlocfilehash: 9497bea9b7cc5eb98876c923858dbcbc6adf9d07
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792449"
---
# <a name="icordebugprocess5enablengenpolicy-method"></a><span data-ttu-id="a3fb9-102">ICorDebugProcess5::EnableNGENPolicy-Methode</span><span class="sxs-lookup"><span data-stu-id="a3fb9-102">ICorDebugProcess5::EnableNGENPolicy Method</span></span>
<span data-ttu-id="a3fb9-103">Legt einen Wert fest, der bestimmt, wie eine Anwendung systemeigene Images lädt, während Sie unter einem verwalteten Debugger ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a3fb9-103">Sets a value that determines how an application loads native images while running under a managed debugger.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3fb9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a3fb9-104">Syntax</span></span>  
  
```cpp  
HRESULT EnableNGENPolicy(  
    [in] CorDebugNGENPolicy ePolicy  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a3fb9-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="a3fb9-105">Parameters</span></span>  
 `ePolicy`  
 <span data-ttu-id="a3fb9-106">in Eine [cordebugngenpolicy](cordebugngenpolicy-enumeration.md) -Konstante, die bestimmt, wie eine Anwendung systemeigene Images lädt, während Sie unter einem verwalteten Debugger ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a3fb9-106">[in] A [CorDebugNGenPolicy](cordebugngenpolicy-enumeration.md) constant that determines how an application loads native images while running under a managed debugger.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a3fb9-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a3fb9-107">Remarks</span></span>  
 <span data-ttu-id="a3fb9-108">Wenn die Richtlinie erfolgreich festgelegt wurde, gibt die Methode `S_OK`zurück.</span><span class="sxs-lookup"><span data-stu-id="a3fb9-108">If the policy is set successfully, the method returns `S_OK`.</span></span> <span data-ttu-id="a3fb9-109">Wenn `ePolicy` außerhalb des Bereichs der durch [cordebugngenpolicy](cordebugngenpolicy-enumeration.md)definierten Enumerationswerte liegt, gibt die Methode `E_INVALIDARG` zurück, und der Methodenaufruf hat keine Auswirkungen.</span><span class="sxs-lookup"><span data-stu-id="a3fb9-109">If `ePolicy` is outside the range of the enumerated values defined by [CorDebugNGenPolicy](cordebugngenpolicy-enumeration.md), the method returns `E_INVALIDARG` and the method call has no effect.</span></span> <span data-ttu-id="a3fb9-110">Wenn die Richtlinie des Native Image Generator (Ngen. exe) nicht aktualisiert werden kann, gibt die Methode `E_FAIL`zurück.</span><span class="sxs-lookup"><span data-stu-id="a3fb9-110">If the policy of the Native Image Generator (Ngen.exe) cannot be updated, the method returns `E_FAIL`.</span></span>  
  
 <span data-ttu-id="a3fb9-111">Die `ICorDebugProcess5::EnableNGenPolicy`-Methode kann zu einem beliebigen Zeitpunkt während der Lebensdauer des Prozesses aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="a3fb9-111">The `ICorDebugProcess5::EnableNGenPolicy` method can be called at any time during the lifetime of the process.</span></span> <span data-ttu-id="a3fb9-112">Die Richtlinie ist für alle Module wirksam, die geladen werden, nachdem die Richtlinie festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="a3fb9-112">The policy is in effect for any modules that are loaded after the policy is set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a3fb9-113">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a3fb9-113">Requirements</span></span>  
 <span data-ttu-id="a3fb9-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a3fb9-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a3fb9-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a3fb9-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a3fb9-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a3fb9-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a3fb9-117">**.NET Framework Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a3fb9-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3fb9-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a3fb9-118">See also</span></span>

- [<span data-ttu-id="a3fb9-119">ICorDebugProcess5-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a3fb9-119">ICorDebugProcess5 Interface</span></span>](icordebugprocess5-interface.md)
- [<span data-ttu-id="a3fb9-120">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="a3fb9-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="a3fb9-121">Debuggen</span><span class="sxs-lookup"><span data-stu-id="a3fb9-121">Debugging</span></span>](index.md)
