---
title: ICorDebugDebugEvent::GetEventKind-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: c37aaceb-c948-46bd-a943-08be4cbb76f4
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 25bb63f1b1fa759cd6d61a71682b803e3320f22d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugdebugeventgeteventkind-method"></a><span data-ttu-id="c2307-102">ICorDebugDebugEvent::GetEventKind-Methode</span><span class="sxs-lookup"><span data-stu-id="c2307-102">ICorDebugDebugEvent::GetEventKind Method</span></span>
<span data-ttu-id="c2307-103">Gibt an, welche Art von Ereignis dieses `ICorDebugDebugEvent`-Objekt darstellt.</span><span class="sxs-lookup"><span data-stu-id="c2307-103">Indicates what kind of event this `ICorDebugDebugEvent` object represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2307-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c2307-104">Syntax</span></span>  
  
```  
HRESULT GetEventKind(  
    [out]CorDebugDebugEventKind *pDebugEventKind  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c2307-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c2307-105">Parameters</span></span>  
 <span data-ttu-id="c2307-106">pDebugEventKind</span><span class="sxs-lookup"><span data-stu-id="c2307-106">pDebugEventKind</span></span>  
 <span data-ttu-id="c2307-107">Ein Zeiger auf eine [CorDebugDebugEventKind](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md) Enumerationsmember, der den Typ des Ereignisses angibt.</span><span class="sxs-lookup"><span data-stu-id="c2307-107">A pointer to a [CorDebugDebugEventKind](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md) enumeration member that indicates the type of event.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c2307-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c2307-108">Remarks</span></span>  
 <span data-ttu-id="c2307-109">Basierend auf dem `pDebugEventKind`-Wert können Sie `QueryInterface` aufrufen, um eine präzisere Debug-Ereignisschnittstelle abzurufen, welche zusätzliche Daten enthält.</span><span class="sxs-lookup"><span data-stu-id="c2307-109">Based on the value of `pDebugEventKind`, you can call `QueryInterface` to get a more precise debug event interface that has additional data.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c2307-110">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c2307-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c2307-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c2307-111">Requirements</span></span>  
 <span data-ttu-id="c2307-112">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c2307-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2307-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c2307-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c2307-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c2307-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c2307-115">**.NET Framework-Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c2307-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2307-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c2307-116">See Also</span></span>  
 [<span data-ttu-id="c2307-117">ICorDebugDebugEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c2307-117">ICorDebugDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md)  
 [<span data-ttu-id="c2307-118">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="c2307-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
