---
title: ICorDebugInternalFrame-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugInternalFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugInternalFrame
helpviewer_keywords:
- ICorDebugInternalFrame interface [.NET Framework debugging]
ms.assetid: bb4772ca-0d54-4185-b738-7a6ffe9ea85a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9764cdcd07a09f5192a8f43b9baa5be40305c40b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69910170"
---
# <a name="icordebuginternalframe-interface"></a><span data-ttu-id="a2461-102">ICorDebugInternalFrame-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a2461-102">ICorDebugInternalFrame Interface</span></span>

<span data-ttu-id="a2461-103">Stellt einen Lauf Zeit internen Frame im Stapel dar.</span><span class="sxs-lookup"><span data-stu-id="a2461-103">Represents a runtime-internal frame on the stack.</span></span> <span data-ttu-id="a2461-104">Diese Schnittstelle ist eine Unterklasse der ICorDebugFrame-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="a2461-104">This interface is a subclass of the ICorDebugFrame interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a2461-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="a2461-105">Methods</span></span>  
  
|<span data-ttu-id="a2461-106">Methode</span><span class="sxs-lookup"><span data-stu-id="a2461-106">Method</span></span>|<span data-ttu-id="a2461-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a2461-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a2461-108">GetFrameType-Methode</span><span class="sxs-lookup"><span data-stu-id="a2461-108">GetFrameType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe-getframetype-method.md)|<span data-ttu-id="a2461-109">Ruft den Typ dieses internen Frames ab.</span><span class="sxs-lookup"><span data-stu-id="a2461-109">Gets the type of this internal frame.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a2461-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a2461-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a2461-111">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="a2461-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a2461-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a2461-112">Requirements</span></span>  
 <span data-ttu-id="a2461-113">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a2461-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a2461-114">**Header:** Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="a2461-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a2461-115">**Fern** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a2461-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a2461-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a2461-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2461-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a2461-117">See also</span></span>

- [<span data-ttu-id="a2461-118">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="a2461-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
