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
ms.openlocfilehash: 192f2476aff91d3a8302d070852ab2a3722d137c
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56970128"
---
# <a name="icordebugmodule2-interface"></a><span data-ttu-id="f7b75-102">ICorDebugModule2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f7b75-102">ICorDebugModule2 Interface</span></span>

<span data-ttu-id="f7b75-103">Fungiert als logische Erweiterung von der ICorDebugModule-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="f7b75-103">Serves as a logical extension to the ICorDebugModule interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f7b75-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="f7b75-104">Methods</span></span>  
  
|<span data-ttu-id="f7b75-105">Methode</span><span class="sxs-lookup"><span data-stu-id="f7b75-105">Method</span></span>|<span data-ttu-id="f7b75-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f7b75-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f7b75-107">ApplyChanges-Methode</span><span class="sxs-lookup"><span data-stu-id="f7b75-107">ApplyChanges Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-applychanges-method.md)|<span data-ttu-id="f7b75-108">Wendet die Änderungen in den Metadaten und die Änderungen in der Microsoft intermediate Language (MSIL)-Code an den laufenden Prozess an.</span><span class="sxs-lookup"><span data-stu-id="f7b75-108">Applies the changes in the metadata and the changes in the Microsoft intermediate language (MSIL) code to the running process.</span></span>|  
|[<span data-ttu-id="f7b75-109">GetJITCompilerFlags-Methode</span><span class="sxs-lookup"><span data-stu-id="f7b75-109">GetJITCompilerFlags Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-getjitcompilerflags-method.md)|<span data-ttu-id="f7b75-110">Ruft die Flags ab, die steuern, die just-in-Time (JIT)-Kompilierung für diese `ICorDebugModule2`.</span><span class="sxs-lookup"><span data-stu-id="f7b75-110">Gets the flags that control the just-in-time (JIT) compilation for this `ICorDebugModule2`.</span></span>|  
|[<span data-ttu-id="f7b75-111">ResolveAssembly-Methode</span><span class="sxs-lookup"><span data-stu-id="f7b75-111">ResolveAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-resolveassembly-method.md)|<span data-ttu-id="f7b75-112">Löst die Assembly, die vom angegebenen Metadatentoken verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="f7b75-112">Resolves the assembly referenced by the specified metadata token.</span></span>|  
|[<span data-ttu-id="f7b75-113">SetJITCompilerFlags-Methode</span><span class="sxs-lookup"><span data-stu-id="f7b75-113">SetJITCompilerFlags Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-setjitcompilerflags-method.md)|<span data-ttu-id="f7b75-114">Legt die Flags, die steuern, die JIT-Kompilierung für diese `ICorDebugModule2`.</span><span class="sxs-lookup"><span data-stu-id="f7b75-114">Sets the flags that control the JIT compilation for this `ICorDebugModule2`.</span></span>|  
|[<span data-ttu-id="f7b75-115">SetJMCStatus-Methode</span><span class="sxs-lookup"><span data-stu-id="f7b75-115">SetJMCStatus Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-setjmcstatus-method.md)|<span data-ttu-id="f7b75-116">Wird von der Status nur mein Code (JMC) alle Methoden, die alle Klassen in diesem `ICorDebugModule2` auf den angegebenen Wert, mit Ausnahme der `pTokens` Array, das auf den entgegengesetzten Wert festgelegt.</span><span class="sxs-lookup"><span data-stu-id="f7b75-116">Sets the Just My Code (JMC) status of all methods of all the classes in this `ICorDebugModule2` to the specified value, except those in the `pTokens` array, which it sets to the opposite value.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f7b75-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f7b75-117">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f7b75-118">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="f7b75-118">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f7b75-119">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f7b75-119">Requirements</span></span>  
 <span data-ttu-id="f7b75-120">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f7b75-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f7b75-121">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f7b75-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f7b75-122">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f7b75-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f7b75-123">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f7b75-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7b75-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f7b75-124">See also</span></span>
- [<span data-ttu-id="f7b75-125">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="f7b75-125">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
