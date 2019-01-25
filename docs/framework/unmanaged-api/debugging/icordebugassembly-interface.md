---
title: ICorDebugAssembly-Schnittstelle1
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
ms.openlocfilehash: 8a6776467eb9f5eaaacadb2908de17fc277e495b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54569179"
---
# <a name="icordebugassembly-interface1"></a><span data-ttu-id="ab812-102">ICorDebugAssembly-Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="ab812-102">ICorDebugAssembly Interface1</span></span>
<span data-ttu-id="ab812-103">Stellt eine Assembly dar.</span><span class="sxs-lookup"><span data-stu-id="ab812-103">Represents an assembly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ab812-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="ab812-104">Methods</span></span>  
  
|<span data-ttu-id="ab812-105">Methode</span><span class="sxs-lookup"><span data-stu-id="ab812-105">Method</span></span>|<span data-ttu-id="ab812-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ab812-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ab812-107">EnumerateModules-Methode</span><span class="sxs-lookup"><span data-stu-id="ab812-107">EnumerateModules Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-enumeratemodules-method.md)|<span data-ttu-id="ab812-108">Ruft einen Enumerator für die in der Assembly enthaltenen Module ab.</span><span class="sxs-lookup"><span data-stu-id="ab812-108">Gets an enumerator for the modules contained in the assembly.</span></span>|  
|[<span data-ttu-id="ab812-109">GetAppDomain-Methode</span><span class="sxs-lookup"><span data-stu-id="ab812-109">GetAppDomain Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getappdomain-method.md)|<span data-ttu-id="ab812-110">Ruft einen Schnittstellenzeiger auf die Anwendungsdomäne, der diesen `ICorDebugAssembly` Instanz.</span><span class="sxs-lookup"><span data-stu-id="ab812-110">Gets an interface pointer to the application domain that contains this `ICorDebugAssembly` instance.</span></span>|  
|[<span data-ttu-id="ab812-111">GetCodeBase-Methode</span><span class="sxs-lookup"><span data-stu-id="ab812-111">GetCodeBase Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getcodebase-method.md)|<span data-ttu-id="ab812-112">In der aktuellen Version von .NET Framework implementiert nicht.</span><span class="sxs-lookup"><span data-stu-id="ab812-112">Not implemented in the current version of the .NET Framework.</span></span>|  
|[<span data-ttu-id="ab812-113">GetName-Methode</span><span class="sxs-lookup"><span data-stu-id="ab812-113">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getname-method.md)|<span data-ttu-id="ab812-114">Ruft den Namen der Assembly ab.</span><span class="sxs-lookup"><span data-stu-id="ab812-114">Gets the name of the assembly.</span></span>|  
|[<span data-ttu-id="ab812-115">GetProcess-Methode</span><span class="sxs-lookup"><span data-stu-id="ab812-115">GetProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getprocess-method.md)|<span data-ttu-id="ab812-116">Ruft die ICorDebugProcess-Instanz, die in der Assembly ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ab812-116">Gets the ICorDebugProcess instance in which the assembly is running.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ab812-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ab812-117">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ab812-118">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="ab812-118">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ab812-119">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ab812-119">Requirements</span></span>  
 <span data-ttu-id="ab812-120">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ab812-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ab812-121">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ab812-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ab812-122">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ab812-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ab812-123">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ab812-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab812-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ab812-124">See also</span></span>
- [<span data-ttu-id="ab812-125">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="ab812-125">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
