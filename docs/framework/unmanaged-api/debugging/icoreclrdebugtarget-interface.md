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
ms.openlocfilehash: 83afe121b6bf0de3c5542695e38b6605db7a8b6d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121816"
---
# <a name="icoreclrdebugtarget-interface"></a><span data-ttu-id="a90de-102">ICoreClrDebugTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a90de-102">ICoreClrDebugTarget Interface</span></span>
<span data-ttu-id="a90de-103">Stellt Methoden bereit, die Verweis Zählungen steuern, Prozesse aufzählen und den Arbeitsspeicher freigeben, der einem Debugger zugeordnet ist, der einem Remote Macintosh-Silverlight-Ziel zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="a90de-103">Provides methods that control reference counts, enumerate processes, and free the memory associated with a debugger that is attached to a remote Macintosh Silverlight target.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a90de-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a90de-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="methods"></a><span data-ttu-id="a90de-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="a90de-105">Methods</span></span>  
  
|<span data-ttu-id="a90de-106">Methode</span><span class="sxs-lookup"><span data-stu-id="a90de-106">Method</span></span>|<span data-ttu-id="a90de-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a90de-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a90de-108">ICoreClrDebugTarget::EnumProcesses-Methode</span><span class="sxs-lookup"><span data-stu-id="a90de-108">ICoreClrDebugTarget::EnumProcesses Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-enumprocesses-method.md)|<span data-ttu-id="a90de-109">Listet die Prozesse auf, die auf einem Remotecomputer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="a90de-109">Enumerates the processes that are running on a remote computer.</span></span>|  
|[<span data-ttu-id="a90de-110">ICoreClrDebugTarget::EnumRuntimes-Methode</span><span class="sxs-lookup"><span data-stu-id="a90de-110">ICoreClrDebugTarget::EnumRuntimes Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-enumruntimes-method.md)|<span data-ttu-id="a90de-111">Listet die Common Language Runtime (clrs) im angegebenen Prozess auf einem Remote Computer auf.</span><span class="sxs-lookup"><span data-stu-id="a90de-111">Enumerates the common language runtimes (CLRs) in the specified process on a remote computer.</span></span>|  
|[<span data-ttu-id="a90de-112">ICoreClrDebugTarget::FreeMemory-Methode</span><span class="sxs-lookup"><span data-stu-id="a90de-112">ICoreClrDebugTarget::FreeMemory Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-freememory-method.md)|<span data-ttu-id="a90de-113">Gibt den Arbeitsspeicher frei, der von den Enumerationsmethoden in dieser Klasse zugeordnet wird.</span><span class="sxs-lookup"><span data-stu-id="a90de-113">Frees the memory that is allocated by the enumeration methods in this class.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a90de-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a90de-114">Remarks</span></span>  
 <span data-ttu-id="a90de-115">Diese Funktion wird zurzeit nur für das Debuggen eines Silverlight-basierten Anwendungs Ziels unterstützt, das auf einem Macintosh-Remote Computer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a90de-115">Currently, this functionality is supported only for debugging a Silverlight-based application target that is running on a remote Macintosh computer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a90de-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a90de-116">Requirements</span></span>  
 <span data-ttu-id="a90de-117">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a90de-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a90de-118">**Header:** Coreclrremotedebugginginterfaces. h</span><span class="sxs-lookup"><span data-stu-id="a90de-118">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="a90de-119">**Bibliothek:** mscordbi_macx86. dll</span><span class="sxs-lookup"><span data-stu-id="a90de-119">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="a90de-120">**.NET Framework Versionen:** 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="a90de-120">**.NET Framework Versions:** 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a90de-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a90de-121">See also</span></span>

- [<span data-ttu-id="a90de-122">ICorDebugRemoteTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a90de-122">ICorDebugRemoteTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)
- [<span data-ttu-id="a90de-123">ICorDebug-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a90de-123">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)

- [<span data-ttu-id="a90de-124">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="a90de-124">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
