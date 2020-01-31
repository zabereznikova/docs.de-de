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
ms.openlocfilehash: ecd4ad31b8dad55e9538642a4dc652341bc84b97
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76784675"
---
# <a name="icordebugassembly-interface"></a><span data-ttu-id="5529a-102">ICorDebugAssembly-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5529a-102">ICorDebugAssembly Interface</span></span>

<span data-ttu-id="5529a-103">Stellt eine Assembly dar.</span><span class="sxs-lookup"><span data-stu-id="5529a-103">Represents an assembly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5529a-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="5529a-104">Methods</span></span>  
  
|<span data-ttu-id="5529a-105">-Methode</span><span class="sxs-lookup"><span data-stu-id="5529a-105">Method</span></span>|<span data-ttu-id="5529a-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5529a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5529a-107">EnumerateModules-Methode</span><span class="sxs-lookup"><span data-stu-id="5529a-107">EnumerateModules Method</span></span>](icordebugassembly-enumeratemodules-method.md)|<span data-ttu-id="5529a-108">Ruft einen Enumerator für die Module ab, die in der Assembly enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="5529a-108">Gets an enumerator for the modules contained in the assembly.</span></span>|  
|[<span data-ttu-id="5529a-109">GetAppDomain-Methode</span><span class="sxs-lookup"><span data-stu-id="5529a-109">GetAppDomain Method</span></span>](icordebugassembly-getappdomain-method.md)|<span data-ttu-id="5529a-110">Ruft einen Schnittstellen Zeiger auf die Anwendungsdomäne ab, die diese `ICorDebugAssembly` Instanz enthält.</span><span class="sxs-lookup"><span data-stu-id="5529a-110">Gets an interface pointer to the application domain that contains this `ICorDebugAssembly` instance.</span></span>|  
|[<span data-ttu-id="5529a-111">GetCodeBase-Methode</span><span class="sxs-lookup"><span data-stu-id="5529a-111">GetCodeBase Method</span></span>](icordebugassembly-getcodebase-method.md)|<span data-ttu-id="5529a-112">Nicht in der aktuellen Version des .NET Framework implementiert.</span><span class="sxs-lookup"><span data-stu-id="5529a-112">Not implemented in the current version of the .NET Framework.</span></span>|  
|[<span data-ttu-id="5529a-113">GetName-Methode</span><span class="sxs-lookup"><span data-stu-id="5529a-113">GetName Method</span></span>](icordebugassembly-getname-method.md)|<span data-ttu-id="5529a-114">Ruft den Namen der Assembly ab.</span><span class="sxs-lookup"><span data-stu-id="5529a-114">Gets the name of the assembly.</span></span>|  
|[<span data-ttu-id="5529a-115">GetProcess-Methode</span><span class="sxs-lookup"><span data-stu-id="5529a-115">GetProcess Method</span></span>](icordebugassembly-getprocess-method.md)|<span data-ttu-id="5529a-116">Ruft die ICorDebugProcess-Instanz ab, in der die Assembly ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="5529a-116">Gets the ICorDebugProcess instance in which the assembly is running.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5529a-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5529a-117">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5529a-118">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="5529a-118">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5529a-119">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5529a-119">Requirements</span></span>  
 <span data-ttu-id="5529a-120">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5529a-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5529a-121">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5529a-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5529a-122">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5529a-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5529a-123">**.NET Framework Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5529a-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5529a-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5529a-124">See also</span></span>

- [<span data-ttu-id="5529a-125">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="5529a-125">Debugging Interfaces</span></span>](debugging-interfaces.md)
