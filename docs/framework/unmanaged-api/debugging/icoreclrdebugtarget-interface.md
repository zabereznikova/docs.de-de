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
ms.openlocfilehash: 2972b87b2d0136f182f8e8223988953e1896f2bd
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59183338"
---
# <a name="icoreclrdebugtarget-interface"></a><span data-ttu-id="efe25-102">ICoreClrDebugTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="efe25-102">ICoreClrDebugTarget Interface</span></span>
<span data-ttu-id="efe25-103">Bietet Methoden, die einen Zähler zu steuern, Auflisten von Prozessen und einen Debugger, der mit einem Remoteziel für Macintosh Silverlight verknüpft zugeordneten Arbeitsspeicher freizugeben.</span><span class="sxs-lookup"><span data-stu-id="efe25-103">Provides methods that control reference counts, enumerate processes, and free the memory associated with a debugger that is attached to a remote Macintosh Silverlight target.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="efe25-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="efe25-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="efe25-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="efe25-105">Methods</span></span>  
  
|<span data-ttu-id="efe25-106">Methode</span><span class="sxs-lookup"><span data-stu-id="efe25-106">Method</span></span>|<span data-ttu-id="efe25-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="efe25-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="efe25-108">ICoreClrDebugTarget::EnumProcesses-Methode</span><span class="sxs-lookup"><span data-stu-id="efe25-108">ICoreClrDebugTarget::EnumProcesses Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-enumprocesses-method.md)|<span data-ttu-id="efe25-109">Listet die Prozesse auf, die auf einem Remotecomputer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="efe25-109">Enumerates the processes that are running on a remote computer.</span></span>|  
|[<span data-ttu-id="efe25-110">ICoreClrDebugTarget::EnumRuntimes-Methode</span><span class="sxs-lookup"><span data-stu-id="efe25-110">ICoreClrDebugTarget::EnumRuntimes Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-enumruntimes-method.md)|<span data-ttu-id="efe25-111">Listet die common Language Runtimes (Runtime) in den angegebenen Prozess auf einem Remotecomputer befindet.</span><span class="sxs-lookup"><span data-stu-id="efe25-111">Enumerates the common language runtimes (CLRs) in the specified process on a remote computer.</span></span>|  
|[<span data-ttu-id="efe25-112">ICoreClrDebugTarget::FreeMemory-Methode</span><span class="sxs-lookup"><span data-stu-id="efe25-112">ICoreClrDebugTarget::FreeMemory Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-freememory-method.md)|<span data-ttu-id="efe25-113">Gibt den Arbeitsspeicher frei, der von der Enumerationsmethoden in dieser Klasse zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="efe25-113">Frees the memory that is allocated by the enumeration methods in this class.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="efe25-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="efe25-114">Remarks</span></span>  
 <span data-ttu-id="efe25-115">Derzeit wird diese Funktion unterstützt, nur für das Debuggen ein Silverlight-Anwendung-Ziel, das auf einem Macintosh-Remotecomputer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="efe25-115">Currently, this functionality is supported only for debugging a Silverlight-based application target that is running on a remote Macintosh computer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="efe25-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="efe25-116">Requirements</span></span>  
 <span data-ttu-id="efe25-117">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="efe25-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="efe25-118">**Header:** CoreClrRemoteDebuggingInterfaces.h</span><span class="sxs-lookup"><span data-stu-id="efe25-118">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="efe25-119">**Bibliothek:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="efe25-119">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="efe25-120">**.NET Framework-Versionen:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="efe25-120">**.NET Framework Versions:** 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efe25-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="efe25-121">See also</span></span>

- [<span data-ttu-id="efe25-122">ICorDebugRemoteTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="efe25-122">ICorDebugRemoteTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)
- [<span data-ttu-id="efe25-123">ICorDebug-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="efe25-123">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)

- [<span data-ttu-id="efe25-124">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="efe25-124">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
