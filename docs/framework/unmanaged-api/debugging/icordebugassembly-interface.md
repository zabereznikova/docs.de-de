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
ms.openlocfilehash: dea3231e3bbb361b56254756c6d99b115f73e792
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133974"
---
# <a name="icordebugassembly-interface"></a><span data-ttu-id="d1f05-102">ICorDebugAssembly-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d1f05-102">ICorDebugAssembly Interface</span></span>

<span data-ttu-id="d1f05-103">Stellt eine Assembly dar.</span><span class="sxs-lookup"><span data-stu-id="d1f05-103">Represents an assembly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d1f05-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="d1f05-104">Methods</span></span>  
  
|<span data-ttu-id="d1f05-105">Methode</span><span class="sxs-lookup"><span data-stu-id="d1f05-105">Method</span></span>|<span data-ttu-id="d1f05-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d1f05-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d1f05-107">EnumerateModules-Methode</span><span class="sxs-lookup"><span data-stu-id="d1f05-107">EnumerateModules Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-enumeratemodules-method.md)|<span data-ttu-id="d1f05-108">Ruft einen Enumerator für die Module ab, die in der Assembly enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="d1f05-108">Gets an enumerator for the modules contained in the assembly.</span></span>|  
|[<span data-ttu-id="d1f05-109">GetAppDomain-Methode</span><span class="sxs-lookup"><span data-stu-id="d1f05-109">GetAppDomain Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getappdomain-method.md)|<span data-ttu-id="d1f05-110">Ruft einen Schnittstellen Zeiger auf die Anwendungsdomäne ab, die diese `ICorDebugAssembly` Instanz enthält.</span><span class="sxs-lookup"><span data-stu-id="d1f05-110">Gets an interface pointer to the application domain that contains this `ICorDebugAssembly` instance.</span></span>|  
|[<span data-ttu-id="d1f05-111">GetCodeBase-Methode</span><span class="sxs-lookup"><span data-stu-id="d1f05-111">GetCodeBase Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getcodebase-method.md)|<span data-ttu-id="d1f05-112">Nicht in der aktuellen Version des .NET Framework implementiert.</span><span class="sxs-lookup"><span data-stu-id="d1f05-112">Not implemented in the current version of the .NET Framework.</span></span>|  
|[<span data-ttu-id="d1f05-113">GetName-Methode</span><span class="sxs-lookup"><span data-stu-id="d1f05-113">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getname-method.md)|<span data-ttu-id="d1f05-114">Ruft den Namen der Assembly ab.</span><span class="sxs-lookup"><span data-stu-id="d1f05-114">Gets the name of the assembly.</span></span>|  
|[<span data-ttu-id="d1f05-115">GetProcess-Methode</span><span class="sxs-lookup"><span data-stu-id="d1f05-115">GetProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-getprocess-method.md)|<span data-ttu-id="d1f05-116">Ruft die ICorDebugProcess-Instanz ab, in der die Assembly ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="d1f05-116">Gets the ICorDebugProcess instance in which the assembly is running.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d1f05-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d1f05-117">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d1f05-118">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="d1f05-118">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d1f05-119">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d1f05-119">Requirements</span></span>  
 <span data-ttu-id="d1f05-120">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d1f05-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d1f05-121">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d1f05-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d1f05-122">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d1f05-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d1f05-123">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d1f05-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1f05-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d1f05-124">See also</span></span>

- [<span data-ttu-id="d1f05-125">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="d1f05-125">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
