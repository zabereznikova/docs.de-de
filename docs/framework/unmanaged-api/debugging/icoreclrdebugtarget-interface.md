---
title: ICoreClrDebugTarget-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICoreClrDebugTarget
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- ICoreClrDebugTarget
helpviewer_keywords:
- remote debugging API [Silverlight]
- ICorClrDebugTarget interface
- Silverlight, remote debugging
ms.assetid: 7cfaee76-e284-4a66-a431-8e33f0f60038
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 371768a8306c3751e7fc54b91a8583df41ad219b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33422281"
---
# <a name="icoreclrdebugtarget-interface"></a><span data-ttu-id="ff862-102">ICoreClrDebugTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ff862-102">ICoreClrDebugTarget Interface</span></span>
<span data-ttu-id="ff862-103">Stellt Methoden, die zum Steuern der Verweiszähler, Auflisten von Prozessen und einen Debugger, der mit einem Remoteziel für Macintosh Silverlight angefügt ist zugeordneten Arbeitsspeicher freizugeben.</span><span class="sxs-lookup"><span data-stu-id="ff862-103">Provides methods that control reference counts, enumerate processes, and free the memory associated with a debugger that is attached to a remote Macintosh Silverlight target.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff862-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ff862-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="ff862-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="ff862-105">Methods</span></span>  
  
|<span data-ttu-id="ff862-106">Methode</span><span class="sxs-lookup"><span data-stu-id="ff862-106">Method</span></span>|<span data-ttu-id="ff862-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ff862-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ff862-108">ICoreClrDebugTarget::EnumProcesses-Methode</span><span class="sxs-lookup"><span data-stu-id="ff862-108">ICoreClrDebugTarget::EnumProcesses Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-enumprocesses-method.md)|<span data-ttu-id="ff862-109">Listet die Prozesse auf, die auf einem Remotecomputer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="ff862-109">Enumerates the processes that are running on a remote computer.</span></span>|  
|[<span data-ttu-id="ff862-110">ICoreClrDebugTarget::EnumRuntimes-Methode</span><span class="sxs-lookup"><span data-stu-id="ff862-110">ICoreClrDebugTarget::EnumRuntimes Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-enumruntimes-method.md)|<span data-ttu-id="ff862-111">Listet die common Language Runtime (Runtime) in den angegebenen Prozess auf einem Remotecomputer befindet.</span><span class="sxs-lookup"><span data-stu-id="ff862-111">Enumerates the common language runtimes (CLRs) in the specified process on a remote computer.</span></span>|  
|[<span data-ttu-id="ff862-112">ICoreClrDebugTarget::FreeMemory-Methode</span><span class="sxs-lookup"><span data-stu-id="ff862-112">ICoreClrDebugTarget::FreeMemory Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-freememory-method.md)|<span data-ttu-id="ff862-113">Gibt den Arbeitsspeicher frei, der durch die Enumerationsmethoden in dieser Klasse zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="ff862-113">Frees the memory that is allocated by the enumeration methods in this class.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ff862-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ff862-114">Remarks</span></span>  
 <span data-ttu-id="ff862-115">Derzeit wird diese Funktion unterstützt, nur für das Debuggen einer Silverlight-basierten Anwendung-Ziel, das auf einem Macintosh-Remotecomputer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ff862-115">Currently, this functionality is supported only for debugging a Silverlight-based application target that is running on a remote Macintosh computer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ff862-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ff862-116">Requirements</span></span>  
 <span data-ttu-id="ff862-117">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ff862-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ff862-118">**Header:** CoreClrRemoteDebuggingInterfaces.h</span><span class="sxs-lookup"><span data-stu-id="ff862-118">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="ff862-119">**Bibliothek:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="ff862-119">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="ff862-120">**.NET Framework-Versionen:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="ff862-120">**.NET Framework Versions:** 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff862-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ff862-121">See Also</span></span>  
 [<span data-ttu-id="ff862-122">ICorDebugRemoteTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ff862-122">ICorDebugRemoteTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)  
 [<span data-ttu-id="ff862-123">ICorDebug-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ff862-123">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)  
    
 [<span data-ttu-id="ff862-124">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="ff862-124">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
