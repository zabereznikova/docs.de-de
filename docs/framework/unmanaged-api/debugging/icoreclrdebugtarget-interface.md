---
title: ICoreClrDebugTarget-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICoreClrDebugTarget
api_location: mscordbi_macx86.dll
api_type: COM
f1_keywords: ICoreClrDebugTarget
helpviewer_keywords:
- remote debugging API [Silverlight]
- ICorClrDebugTarget interface
- Silverlight, remote debugging
ms.assetid: 7cfaee76-e284-4a66-a431-8e33f0f60038
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e13355078727a55c950bed795d3b01b6c7d52564
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icoreclrdebugtarget-interface"></a><span data-ttu-id="e5016-102">ICoreClrDebugTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e5016-102">ICoreClrDebugTarget Interface</span></span>
<span data-ttu-id="e5016-103">Stellt Methoden, die zum Steuern der Verweiszähler, Auflisten von Prozessen und einen Debugger, der mit einem Remoteziel für Macintosh Silverlight angefügt ist zugeordneten Arbeitsspeicher freizugeben.</span><span class="sxs-lookup"><span data-stu-id="e5016-103">Provides methods that control reference counts, enumerate processes, and free the memory associated with a debugger that is attached to a remote Macintosh Silverlight target.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5016-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e5016-104">Syntax</span></span>  
  
```  
class ICoreClrDebugTarget {  
      HRESULT EnumProcesses (  
          [out] DWORD*                    pcProcs,  
          [out] CoreClrDebugProcInfo**    ppProcs  
      );  
  
      HRESULT EnumRuntimes (  
      [in]  DWORD                      dwInternalProcessID,  
      [out] DWORD*                     pcRuntimes,  
      [out] CoreClrDebugRuntimeInfo**  ppRuntimes  
      );  
  
      void FreeMemory (  
      [in] void*      pMemory  
    );  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="e5016-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="e5016-105">Methods</span></span>  
  
|<span data-ttu-id="e5016-106">Methode</span><span class="sxs-lookup"><span data-stu-id="e5016-106">Method</span></span>|<span data-ttu-id="e5016-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e5016-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e5016-108">ICoreClrDebugTarget:: EnumProcesses-Methode</span><span class="sxs-lookup"><span data-stu-id="e5016-108">ICoreClrDebugTarget::EnumProcesses Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-enumprocesses-method.md)|<span data-ttu-id="e5016-109">Listet die Prozesse auf, die auf einem Remotecomputer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="e5016-109">Enumerates the processes that are running on a remote computer.</span></span>|  
|[<span data-ttu-id="e5016-110">ICoreClrDebugTarget:: EnumRuntimes-Methode</span><span class="sxs-lookup"><span data-stu-id="e5016-110">ICoreClrDebugTarget::EnumRuntimes Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-enumruntimes-method.md)|<span data-ttu-id="e5016-111">Listet die common Language Runtime (Runtime) in den angegebenen Prozess auf einem Remotecomputer befindet.</span><span class="sxs-lookup"><span data-stu-id="e5016-111">Enumerates the common language runtimes (CLRs) in the specified process on a remote computer.</span></span>|  
|[<span data-ttu-id="e5016-112">ICoreClrDebugTarget:: FreeMemory-Methode</span><span class="sxs-lookup"><span data-stu-id="e5016-112">ICoreClrDebugTarget::FreeMemory Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-freememory-method.md)|<span data-ttu-id="e5016-113">Gibt den Arbeitsspeicher frei, der durch die Enumerationsmethoden in dieser Klasse zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="e5016-113">Frees the memory that is allocated by the enumeration methods in this class.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e5016-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e5016-114">Remarks</span></span>  
 <span data-ttu-id="e5016-115">Derzeit wird diese Funktion unterstützt, nur für das Debuggen einer Silverlight-basierten Anwendung-Ziel, das auf einem Macintosh-Remotecomputer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="e5016-115">Currently, this functionality is supported only for debugging a Silverlight-based application target that is running on a remote Macintosh computer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5016-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e5016-116">Requirements</span></span>  
 <span data-ttu-id="e5016-117">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e5016-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5016-118">**Header:** CoreClrRemoteDebuggingInterfaces.h</span><span class="sxs-lookup"><span data-stu-id="e5016-118">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="e5016-119">**Bibliothek:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="e5016-119">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="e5016-120">**.NET Framework-Versionen:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="e5016-120">**.NET Framework Versions:** 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5016-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e5016-121">See Also</span></span>  
 [<span data-ttu-id="e5016-122">ICorDebugRemoteTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e5016-122">ICorDebugRemoteTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)  
 [<span data-ttu-id="e5016-123">ICorDebug-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e5016-123">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)  
    
 [<span data-ttu-id="e5016-124">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="e5016-124">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
