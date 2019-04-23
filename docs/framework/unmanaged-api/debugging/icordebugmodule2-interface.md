---
title: ICorDebugModule2-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugModule2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule2
helpviewer_keywords:
- ICorDebugModule2 interface [.NET Framework debugging]
ms.assetid: 0847e64f-fdbe-4c96-8168-da20fdc84d80
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d3fb1bf3f61c78f4eb157b93363b1c06b25bee04
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59119898"
---
# <a name="icordebugmodule2-interface"></a><span data-ttu-id="91562-102">ICorDebugModule2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="91562-102">ICorDebugModule2 Interface</span></span>

<span data-ttu-id="91562-103">Fungiert als logische Erweiterung von der ICorDebugModule-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="91562-103">Serves as a logical extension to the ICorDebugModule interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="91562-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="91562-104">Methods</span></span>  
  
|<span data-ttu-id="91562-105">Methode</span><span class="sxs-lookup"><span data-stu-id="91562-105">Method</span></span>|<span data-ttu-id="91562-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="91562-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="91562-107">ApplyChanges-Methode</span><span class="sxs-lookup"><span data-stu-id="91562-107">ApplyChanges Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-applychanges-method.md)|<span data-ttu-id="91562-108">Wendet die Änderungen in den Metadaten und die Änderungen in der Microsoft intermediate Language (MSIL)-Code an den laufenden Prozess an.</span><span class="sxs-lookup"><span data-stu-id="91562-108">Applies the changes in the metadata and the changes in the Microsoft intermediate language (MSIL) code to the running process.</span></span>|  
|[<span data-ttu-id="91562-109">GetJITCompilerFlags-Methode</span><span class="sxs-lookup"><span data-stu-id="91562-109">GetJITCompilerFlags Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-getjitcompilerflags-method.md)|<span data-ttu-id="91562-110">Ruft die Flags ab, die steuern, die just-in-Time (JIT)-Kompilierung für diese `ICorDebugModule2`.</span><span class="sxs-lookup"><span data-stu-id="91562-110">Gets the flags that control the just-in-time (JIT) compilation for this `ICorDebugModule2`.</span></span>|  
|[<span data-ttu-id="91562-111">ResolveAssembly-Methode</span><span class="sxs-lookup"><span data-stu-id="91562-111">ResolveAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-resolveassembly-method.md)|<span data-ttu-id="91562-112">Löst die Assembly, die vom angegebenen Metadatentoken verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="91562-112">Resolves the assembly referenced by the specified metadata token.</span></span>|  
|[<span data-ttu-id="91562-113">SetJITCompilerFlags-Methode</span><span class="sxs-lookup"><span data-stu-id="91562-113">SetJITCompilerFlags Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-setjitcompilerflags-method.md)|<span data-ttu-id="91562-114">Legt die Flags, die steuern, die JIT-Kompilierung für diese `ICorDebugModule2`.</span><span class="sxs-lookup"><span data-stu-id="91562-114">Sets the flags that control the JIT compilation for this `ICorDebugModule2`.</span></span>|  
|[<span data-ttu-id="91562-115">SetJMCStatus-Methode</span><span class="sxs-lookup"><span data-stu-id="91562-115">SetJMCStatus Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-setjmcstatus-method.md)|<span data-ttu-id="91562-116">Wird von der Status nur mein Code (JMC) alle Methoden, die alle Klassen in diesem `ICorDebugModule2` auf den angegebenen Wert, mit Ausnahme der `pTokens` Array, das auf den entgegengesetzten Wert festgelegt.</span><span class="sxs-lookup"><span data-stu-id="91562-116">Sets the Just My Code (JMC) status of all methods of all the classes in this `ICorDebugModule2` to the specified value, except those in the `pTokens` array, which it sets to the opposite value.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="91562-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="91562-117">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="91562-118">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="91562-118">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="91562-119">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="91562-119">Requirements</span></span>  
 <span data-ttu-id="91562-120">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="91562-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="91562-121">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="91562-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="91562-122">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="91562-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="91562-123">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="91562-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91562-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="91562-124">See also</span></span>

- [<span data-ttu-id="91562-125">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="91562-125">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
