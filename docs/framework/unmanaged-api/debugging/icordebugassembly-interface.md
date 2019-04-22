---
title: ICorDebugAssembly-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugAssembly
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssembly
helpviewer_keywords:
- ICorDebugAssembly interface [.NET Framework debugging]
ms.assetid: 9d657a28-6984-4c5e-8a54-89d20080baff
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3dd60defc1c003fa4b235ddcb0a78b9a819b1b0c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59198022"
---
# <a name="icordebugassembly-interface"></a><span data-ttu-id="a1e11-102">ICorDebugAssembly-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a1e11-102">ICorDebugAssembly Interface</span></span>

<span data-ttu-id="a1e11-103">Stellt eine Assembly dar.</span><span class="sxs-lookup"><span data-stu-id="a1e11-103">Represents an assembly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a1e11-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="a1e11-104">Methods</span></span>  
  
|<span data-ttu-id="a1e11-105">Methode</span><span class="sxs-lookup"><span data-stu-id="a1e11-105">Method</span></span>|<span data-ttu-id="a1e11-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a1e11-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a1e11-107">EnumerateModules-Methode</span><span class="sxs-lookup"><span data-stu-id="a1e11-107">EnumerateModules Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-enumeratemodules-method.md)|<span data-ttu-id="a1e11-108">Ruft einen Enumerator für die in der Assembly enthaltenen Module ab.</span><span class="sxs-lookup"><span data-stu-id="a1e11-108">Gets an enumerator for the modules contained in the assembly.</span></span>|  
|[<span data-ttu-id="a1e11-109">GetAppDomain-Methode</span><span class="sxs-lookup"><span data-stu-id="a1e11-109">GetAppDomain Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getappdomain-method.md)|<span data-ttu-id="a1e11-110">Ruft einen Schnittstellenzeiger auf die Anwendungsdomäne, der diesen `ICorDebugAssembly` Instanz.</span><span class="sxs-lookup"><span data-stu-id="a1e11-110">Gets an interface pointer to the application domain that contains this `ICorDebugAssembly` instance.</span></span>|  
|[<span data-ttu-id="a1e11-111">GetCodeBase-Methode</span><span class="sxs-lookup"><span data-stu-id="a1e11-111">GetCodeBase Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getcodebase-method.md)|<span data-ttu-id="a1e11-112">In der aktuellen Version von .NET Framework implementiert nicht.</span><span class="sxs-lookup"><span data-stu-id="a1e11-112">Not implemented in the current version of the .NET Framework.</span></span>|  
|[<span data-ttu-id="a1e11-113">GetName-Methode</span><span class="sxs-lookup"><span data-stu-id="a1e11-113">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getname-method.md)|<span data-ttu-id="a1e11-114">Ruft den Namen der Assembly ab.</span><span class="sxs-lookup"><span data-stu-id="a1e11-114">Gets the name of the assembly.</span></span>|  
|[<span data-ttu-id="a1e11-115">GetProcess-Methode</span><span class="sxs-lookup"><span data-stu-id="a1e11-115">GetProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getprocess-method.md)|<span data-ttu-id="a1e11-116">Ruft die ICorDebugProcess-Instanz, die in der Assembly ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a1e11-116">Gets the ICorDebugProcess instance in which the assembly is running.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a1e11-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a1e11-117">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a1e11-118">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="a1e11-118">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a1e11-119">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a1e11-119">Requirements</span></span>  
 <span data-ttu-id="a1e11-120">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a1e11-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a1e11-121">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a1e11-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a1e11-122">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a1e11-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a1e11-123">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a1e11-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1e11-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a1e11-124">See also</span></span>

- [<span data-ttu-id="a1e11-125">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="a1e11-125">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
