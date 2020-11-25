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
ms.openlocfilehash: 821eae8ea5b4147408e9fe60d1e5b70c7936959e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95696244"
---
# <a name="icordebugassembly-interface"></a><span data-ttu-id="9e860-102">ICorDebugAssembly-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9e860-102">ICorDebugAssembly Interface</span></span>

<span data-ttu-id="9e860-103">Stellt eine Assembly dar.</span><span class="sxs-lookup"><span data-stu-id="9e860-103">Represents an assembly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9e860-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="9e860-104">Methods</span></span>  
  
|<span data-ttu-id="9e860-105">Methode</span><span class="sxs-lookup"><span data-stu-id="9e860-105">Method</span></span>|<span data-ttu-id="9e860-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="9e860-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9e860-107">EnumerateModules-Methode</span><span class="sxs-lookup"><span data-stu-id="9e860-107">EnumerateModules Method</span></span>](icordebugassembly-enumeratemodules-method.md)|<span data-ttu-id="9e860-108">Ruft einen Enumerator für die Module ab, die in der Assembly enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="9e860-108">Gets an enumerator for the modules contained in the assembly.</span></span>|  
|[<span data-ttu-id="9e860-109">GetAppDomain-Methode</span><span class="sxs-lookup"><span data-stu-id="9e860-109">GetAppDomain Method</span></span>](icordebugassembly-getappdomain-method.md)|<span data-ttu-id="9e860-110">Ruft einen Schnittstellen Zeiger auf die Anwendungsdomäne ab, die diese `ICorDebugAssembly` Instanz enthält.</span><span class="sxs-lookup"><span data-stu-id="9e860-110">Gets an interface pointer to the application domain that contains this `ICorDebugAssembly` instance.</span></span>|  
|[<span data-ttu-id="9e860-111">GetCodeBase-Methode</span><span class="sxs-lookup"><span data-stu-id="9e860-111">GetCodeBase Method</span></span>](icordebugassembly-getcodebase-method.md)|<span data-ttu-id="9e860-112">Nicht in der aktuellen Version des .NET Framework implementiert.</span><span class="sxs-lookup"><span data-stu-id="9e860-112">Not implemented in the current version of the .NET Framework.</span></span>|  
|[<span data-ttu-id="9e860-113">GetName-Methode</span><span class="sxs-lookup"><span data-stu-id="9e860-113">GetName Method</span></span>](icordebugassembly-getname-method.md)|<span data-ttu-id="9e860-114">Ruft den Namen der Assembly ab.</span><span class="sxs-lookup"><span data-stu-id="9e860-114">Gets the name of the assembly.</span></span>|  
|[<span data-ttu-id="9e860-115">GetProcess-Methode</span><span class="sxs-lookup"><span data-stu-id="9e860-115">GetProcess Method</span></span>](icordebugassembly-getprocess-method.md)|<span data-ttu-id="9e860-116">Ruft die ICorDebugProcess-Instanz ab, in der die Assembly ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="9e860-116">Gets the ICorDebugProcess instance in which the assembly is running.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9e860-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9e860-117">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9e860-118">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="9e860-118">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9e860-119">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="9e860-119">Requirements</span></span>  

 <span data-ttu-id="9e860-120">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9e860-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9e860-121">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9e860-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9e860-122">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9e860-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9e860-123">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9e860-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e860-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9e860-124">See also</span></span>

- [<span data-ttu-id="9e860-125">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="9e860-125">Debugging Interfaces</span></span>](debugging-interfaces.md)
