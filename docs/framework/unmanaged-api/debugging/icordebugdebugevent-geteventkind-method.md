---
title: ICorDebugDebugEvent::GetEventKind-Methode
ms.date: 03/30/2017
ms.assetid: c37aaceb-c948-46bd-a943-08be4cbb76f4
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fdbc320e13e0cb140f5ef7aa63b878b43ca0189b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67750053"
---
# <a name="icordebugdebugeventgeteventkind-method"></a><span data-ttu-id="e0a51-102">ICorDebugDebugEvent::GetEventKind-Methode</span><span class="sxs-lookup"><span data-stu-id="e0a51-102">ICorDebugDebugEvent::GetEventKind Method</span></span>
<span data-ttu-id="e0a51-103">Gibt an, welche Art von Ereignis dieses `ICorDebugDebugEvent`-Objekt darstellt.</span><span class="sxs-lookup"><span data-stu-id="e0a51-103">Indicates what kind of event this `ICorDebugDebugEvent` object represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0a51-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e0a51-104">Syntax</span></span>  
  
```cpp  
HRESULT GetEventKind(  
    [out]CorDebugDebugEventKind *pDebugEventKind  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e0a51-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e0a51-105">Parameters</span></span>  
 <span data-ttu-id="e0a51-106">pDebugEventKind</span><span class="sxs-lookup"><span data-stu-id="e0a51-106">pDebugEventKind</span></span>  
 <span data-ttu-id="e0a51-107">Ein Zeiger auf eine [CorDebugDebugEventKind](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md) -Enumerationsmember, der den Typ des Ereignisses angibt.</span><span class="sxs-lookup"><span data-stu-id="e0a51-107">A pointer to a [CorDebugDebugEventKind](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md) enumeration member that indicates the type of event.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e0a51-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e0a51-108">Remarks</span></span>  
 <span data-ttu-id="e0a51-109">Basierend auf dem `pDebugEventKind`-Wert können Sie `QueryInterface` aufrufen, um eine präzisere Debug-Ereignisschnittstelle abzurufen, welche zusätzliche Daten enthält.</span><span class="sxs-lookup"><span data-stu-id="e0a51-109">Based on the value of `pDebugEventKind`, you can call `QueryInterface` to get a more precise debug event interface that has additional data.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e0a51-110">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="e0a51-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e0a51-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e0a51-111">Requirements</span></span>  
 <span data-ttu-id="e0a51-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e0a51-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e0a51-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e0a51-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e0a51-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e0a51-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e0a51-115">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e0a51-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0a51-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e0a51-116">See also</span></span>

- [<span data-ttu-id="e0a51-117">ICorDebugDebugEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e0a51-117">ICorDebugDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md)
- [<span data-ttu-id="e0a51-118">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="e0a51-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
