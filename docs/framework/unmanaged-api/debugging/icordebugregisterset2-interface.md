---
title: ICorDebugRegisterSet2-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet2
helpviewer_keywords:
- ICorDebugRegisterSet2 interface [.NET Framework debugging]
ms.assetid: d7fbccbf-3b6b-4db8-a96d-768e1cb6b1a6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: da2759219901a4f49808300ea3b038b10ce2d032
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59101171"
---
# <a name="icordebugregisterset2-interface"></a><span data-ttu-id="28847-102">ICorDebugRegisterSet2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="28847-102">ICorDebugRegisterSet2 Interface</span></span>
<span data-ttu-id="28847-103">Erweitert die Fähigkeiten der [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) Schnittstelle für die Hardwareplattformen, die mehr als 64 Registern.</span><span class="sxs-lookup"><span data-stu-id="28847-103">Extends the capabilities of the [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) interface for hardware platforms that have more than 64 registers.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="28847-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="28847-104">Methods</span></span>  
  
|<span data-ttu-id="28847-105">Methode</span><span class="sxs-lookup"><span data-stu-id="28847-105">Method</span></span>|<span data-ttu-id="28847-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="28847-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="28847-107">GetRegisters-Methode</span><span class="sxs-lookup"><span data-stu-id="28847-107">GetRegisters Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-getregisters-method.md)|<span data-ttu-id="28847-108">Ruft den Wert jedes Register (auf dem Computer, die gerade Code ausführt) ab, das durch die Bitmaske angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="28847-108">Gets the value of each register (on the computer that is currently executing code) that is specified by the bit mask.</span></span>|  
|[<span data-ttu-id="28847-109">GetRegistersAvailable-Methode</span><span class="sxs-lookup"><span data-stu-id="28847-109">GetRegistersAvailable Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-getregistersavailable-method.md)|<span data-ttu-id="28847-110">Ruft ein Array von Bytes, die eine Bitmap der die verfügbaren Register bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="28847-110">Gets an array of bytes that provides a bitmap of the available registers.</span></span>|  
|[<span data-ttu-id="28847-111">SetRegisters-Methode</span><span class="sxs-lookup"><span data-stu-id="28847-111">SetRegisters Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-setregisters-method.md)|<span data-ttu-id="28847-112">In .NET Framework, Version 2.0 implementiert nicht.</span><span class="sxs-lookup"><span data-stu-id="28847-112">Not implemented in the .NET Framework version 2.0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="28847-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="28847-113">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="28847-114">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="28847-114">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="28847-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="28847-115">Requirements</span></span>  
 <span data-ttu-id="28847-116">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="28847-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="28847-117">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="28847-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="28847-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="28847-118">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="28847-119">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="28847-119">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="28847-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="28847-120">See also</span></span>

- [<span data-ttu-id="28847-121">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="28847-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="28847-122">ICorDebugRegisterSet-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="28847-122">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
