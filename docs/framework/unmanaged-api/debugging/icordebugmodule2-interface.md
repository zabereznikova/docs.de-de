---
title: ICorDebugModule2 Schnittstelle1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a3d62619fd83264bdc774cc1f09f4d98492d0a57
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmodule2-interface1"></a><span data-ttu-id="397cd-102">ICorDebugModule2 Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="397cd-102">ICorDebugModule2 Interface1</span></span>
<span data-ttu-id="397cd-103">Fungiert als logische Erweiterung von ICorDebugModule-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="397cd-103">Serves as a logical extension to the ICorDebugModule interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="397cd-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="397cd-104">Methods</span></span>  
  
|<span data-ttu-id="397cd-105">Methode</span><span class="sxs-lookup"><span data-stu-id="397cd-105">Method</span></span>|<span data-ttu-id="397cd-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="397cd-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="397cd-107">ApplyChanges-Methode</span><span class="sxs-lookup"><span data-stu-id="397cd-107">ApplyChanges Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-applychanges-method.md)|<span data-ttu-id="397cd-108">Wendet die Änderungen in den Metadaten und die Änderungen in der Microsoft intermediate Language (MSIL)-Code an den laufenden Prozess an.</span><span class="sxs-lookup"><span data-stu-id="397cd-108">Applies the changes in the metadata and the changes in the Microsoft intermediate language (MSIL) code to the running process.</span></span>|  
|[<span data-ttu-id="397cd-109">GetJITCompilerFlags-Methode</span><span class="sxs-lookup"><span data-stu-id="397cd-109">GetJITCompilerFlags Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-getjitcompilerflags-method.md)|<span data-ttu-id="397cd-110">Ruft die Flags ab, die die Just-in-Time (JIT)-Kompilierung für diese steuern `ICorDebugModule2`.</span><span class="sxs-lookup"><span data-stu-id="397cd-110">Gets the flags that control the just-in-time (JIT) compilation for this `ICorDebugModule2`.</span></span>|  
|[<span data-ttu-id="397cd-111">ResolveAssembly-Methode</span><span class="sxs-lookup"><span data-stu-id="397cd-111">ResolveAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-resolveassembly-method.md)|<span data-ttu-id="397cd-112">Löst die Assembly auf, die vom angegebenen Metadatentoken verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="397cd-112">Resolves the assembly referenced by the specified metadata token.</span></span>|  
|[<span data-ttu-id="397cd-113">SetJITCompilerFlags-Methode</span><span class="sxs-lookup"><span data-stu-id="397cd-113">SetJITCompilerFlags Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-setjitcompilerflags-method.md)|<span data-ttu-id="397cd-114">Legt die Flags, die steuern, die JIT-Kompilierung für diese `ICorDebugModule2`.</span><span class="sxs-lookup"><span data-stu-id="397cd-114">Sets the flags that control the JIT compilation for this `ICorDebugModule2`.</span></span>|  
|[<span data-ttu-id="397cd-115">SetJMCStatus-Methode</span><span class="sxs-lookup"><span data-stu-id="397cd-115">SetJMCStatus Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-setjmcstatus-method.md)|<span data-ttu-id="397cd-116">Legt den Status nur mein Code (JMC) aller Methoden aller Klassen in diesem `ICorDebugModule2` auf den angegebenen Wert, mit Ausnahme derjenigen in den `pTokens` -Array, das auf den entgegengesetzten Wert festgelegt.</span><span class="sxs-lookup"><span data-stu-id="397cd-116">Sets the Just My Code (JMC) status of all methods of all the classes in this `ICorDebugModule2` to the specified value, except those in the `pTokens` array, which it sets to the opposite value.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="397cd-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="397cd-117">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="397cd-118">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="397cd-118">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="397cd-119">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="397cd-119">Requirements</span></span>  
 <span data-ttu-id="397cd-120">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="397cd-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="397cd-121">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="397cd-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="397cd-122">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="397cd-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="397cd-123">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="397cd-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="397cd-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="397cd-124">See Also</span></span>  
 [<span data-ttu-id="397cd-125">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="397cd-125">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
