---
title: ICorDebugInternalFrame Schnittstelle1
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
ms.openlocfilehash: 45a710e6d8be4a041d9852585ea83fea85376f66
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33413825"
---
# <a name="icordebuginternalframe-interface1"></a><span data-ttu-id="3c31d-102">ICorDebugInternalFrame Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="3c31d-102">ICorDebugInternalFrame Interface1</span></span>
<span data-ttu-id="3c31d-103">Stellt einen internen Common Language Runtime Rahmen im Stapel dar.</span><span class="sxs-lookup"><span data-stu-id="3c31d-103">Represents a runtime-internal frame on the stack.</span></span> <span data-ttu-id="3c31d-104">Diese Schnittstelle ist eine Unterklasse von ICorDebugFrame-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="3c31d-104">This interface is a subclass of the ICorDebugFrame interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3c31d-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="3c31d-105">Methods</span></span>  
  
|<span data-ttu-id="3c31d-106">Methode</span><span class="sxs-lookup"><span data-stu-id="3c31d-106">Method</span></span>|<span data-ttu-id="3c31d-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3c31d-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3c31d-108">GetFrameType-Methode</span><span class="sxs-lookup"><span data-stu-id="3c31d-108">GetFrameType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe-getframetype-method.md)|<span data-ttu-id="3c31d-109">Ruft den Typ dieses interne Rahmens ab.</span><span class="sxs-lookup"><span data-stu-id="3c31d-109">Gets the type of this internal frame.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3c31d-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3c31d-110">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3c31d-111">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="3c31d-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3c31d-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3c31d-112">Requirements</span></span>  
 <span data-ttu-id="3c31d-113">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3c31d-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3c31d-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3c31d-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3c31d-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3c31d-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3c31d-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3c31d-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c31d-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3c31d-117">See Also</span></span>  
 [<span data-ttu-id="3c31d-118">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="3c31d-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
