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
ms.openlocfilehash: 190671b4f690f8c2cad43cf446a1196985ec5a42
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790752"
---
# <a name="icoreclrdebugtarget-interface"></a><span data-ttu-id="867d0-102">ICoreClrDebugTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="867d0-102">ICoreClrDebugTarget Interface</span></span>
<span data-ttu-id="867d0-103">Stellt Methoden bereit, die Verweis Zählungen steuern, Prozesse aufzählen und den Arbeitsspeicher freigeben, der einem Debugger zugeordnet ist, der einem Remote Macintosh-Silverlight-Ziel zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="867d0-103">Provides methods that control reference counts, enumerate processes, and free the memory associated with a debugger that is attached to a remote Macintosh Silverlight target.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="867d0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="867d0-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="867d0-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="867d0-105">Methods</span></span>  
  
|<span data-ttu-id="867d0-106">-Methode</span><span class="sxs-lookup"><span data-stu-id="867d0-106">Method</span></span>|<span data-ttu-id="867d0-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="867d0-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="867d0-108">ICoreClrDebugTarget::EnumProcesses-Methode</span><span class="sxs-lookup"><span data-stu-id="867d0-108">ICoreClrDebugTarget::EnumProcesses Method</span></span>](icoreclrdebugtarget-enumprocesses-method.md)|<span data-ttu-id="867d0-109">Listet die Prozesse auf, die auf einem Remotecomputer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="867d0-109">Enumerates the processes that are running on a remote computer.</span></span>|  
|[<span data-ttu-id="867d0-110">ICoreClrDebugTarget::EnumRuntimes-Methode</span><span class="sxs-lookup"><span data-stu-id="867d0-110">ICoreClrDebugTarget::EnumRuntimes Method</span></span>](icoreclrdebugtarget-enumruntimes-method.md)|<span data-ttu-id="867d0-111">Listet die Common Language Runtime (clrs) im angegebenen Prozess auf einem Remote Computer auf.</span><span class="sxs-lookup"><span data-stu-id="867d0-111">Enumerates the common language runtimes (CLRs) in the specified process on a remote computer.</span></span>|  
|[<span data-ttu-id="867d0-112">ICoreClrDebugTarget::FreeMemory-Methode</span><span class="sxs-lookup"><span data-stu-id="867d0-112">ICoreClrDebugTarget::FreeMemory Method</span></span>](icoreclrdebugtarget-freememory-method.md)|<span data-ttu-id="867d0-113">Gibt den Arbeitsspeicher frei, der von den Enumerationsmethoden in dieser Klasse zugeordnet wird.</span><span class="sxs-lookup"><span data-stu-id="867d0-113">Frees the memory that is allocated by the enumeration methods in this class.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="867d0-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="867d0-114">Remarks</span></span>  
 <span data-ttu-id="867d0-115">Diese Funktion wird zurzeit nur für das Debuggen eines Silverlight-basierten Anwendungs Ziels unterstützt, das auf einem Macintosh-Remote Computer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="867d0-115">Currently, this functionality is supported only for debugging a Silverlight-based application target that is running on a remote Macintosh computer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="867d0-116">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="867d0-116">Requirements</span></span>  
 <span data-ttu-id="867d0-117">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="867d0-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="867d0-118">**Header:** Coreclrremotedebugginginterfaces. h</span><span class="sxs-lookup"><span data-stu-id="867d0-118">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="867d0-119">**Bibliothek:** mscordbi_macx86. dll</span><span class="sxs-lookup"><span data-stu-id="867d0-119">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="867d0-120">**.NET Framework Versionen:** 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="867d0-120">**.NET Framework Versions:** 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="867d0-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="867d0-121">See also</span></span>

- [<span data-ttu-id="867d0-122">ICorDebugRemoteTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="867d0-122">ICorDebugRemoteTarget Interface</span></span>](icordebugremotetarget-interface.md)
- [<span data-ttu-id="867d0-123">ICorDebug-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="867d0-123">ICorDebug Interface</span></span>](icordebug-interface.md)

- [<span data-ttu-id="867d0-124">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="867d0-124">Debugging Interfaces</span></span>](debugging-interfaces.md)
