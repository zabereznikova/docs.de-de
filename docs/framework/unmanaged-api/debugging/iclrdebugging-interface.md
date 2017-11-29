---
title: ICLRDebugging-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDebugging
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICLRDebugging
helpviewer_keywords: ICLRDebugging interface [.NET Framework debugging]
ms.assetid: 429d8fce-b1b1-49d7-895c-28c1c1aa2dbd
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ac3e061b95faafeec3c3d233ab54f128a23c3264
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="iclrdebugging-interface"></a><span data-ttu-id="65868-102">ICLRDebugging-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="65868-102">ICLRDebugging Interface</span></span>
<span data-ttu-id="65868-103">Stellt Methoden bereit, die das Laden und Entladen von Modulen für Debuggingzwecke behandeln.</span><span class="sxs-lookup"><span data-stu-id="65868-103">Provides methods that handle loading and unloading modules for debugging.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="65868-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="65868-104">Methods</span></span>  
  
|<span data-ttu-id="65868-105">Methode</span><span class="sxs-lookup"><span data-stu-id="65868-105">Method</span></span>|<span data-ttu-id="65868-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="65868-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="65868-107">OpenVirtualProcess-Methode</span><span class="sxs-lookup"><span data-stu-id="65868-107">OpenVirtualProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md)|<span data-ttu-id="65868-108">Ruft die "ICorDebugProcess"-Schnittstelle, die eine common Language Runtime (CLR)-Modul im Prozess geladenen entspricht.</span><span class="sxs-lookup"><span data-stu-id="65868-108">Gets the "ICorDebugProcess" interface that corresponds to a common language runtime (CLR) module loaded in the process.</span></span>|  
|[<span data-ttu-id="65868-109">CanUnloadNow-Methode</span><span class="sxs-lookup"><span data-stu-id="65868-109">CanUnloadNow Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-canunloadnow-method.md)|<span data-ttu-id="65868-110">Bestimmt, ob eine Bibliothek, die vom bereitgestellt wurde ein [ICLRDebuggingLibraryProvider](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md) Schnittstelle wird weiterhin verwendet oder können entladen werden.</span><span class="sxs-lookup"><span data-stu-id="65868-110">Determines whether a library that was provided by an [ICLRDebuggingLibraryProvider](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md) interface is still in use or can be unloaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="65868-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="65868-111">Remarks</span></span>  
 <span data-ttu-id="65868-112">Sie erhalten eine Instanz von der `ICLRDebugging` -Schnittstelle mithilfe der [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) Funktion.</span><span class="sxs-lookup"><span data-stu-id="65868-112">You can obtain an instance of the `ICLRDebugging` interface by using the [CLRCreateInstance](../../../../docs/framework/unmanaged-api/hosting/clrcreateinstance-function.md) function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="65868-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="65868-113">Requirements</span></span>  
 <span data-ttu-id="65868-114">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="65868-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="65868-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="65868-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="65868-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="65868-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="65868-117">**.NET Framework-Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="65868-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65868-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="65868-118">See Also</span></span>  
 [<span data-ttu-id="65868-119">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="65868-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="65868-120">Debuggen</span><span class="sxs-lookup"><span data-stu-id="65868-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
