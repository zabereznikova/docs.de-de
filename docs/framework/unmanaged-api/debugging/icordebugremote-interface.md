---
title: ICorDebugRemote-Schnittstelle
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
- ICorDebugRemote
api_location:
- CorDebug.dll
api_type:
- COM
f1_keywords:
- ICorDebugRemote
helpviewer_keywords:
- ICorDebugRemote interface [.NET Framework debugging]
ms.assetid: 53d073c6-fa02-40d2-82e1-b9452bb6abaa
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: cc34c3a1049a24a27fae4d13288efbd5a98a4dc9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugremote-interface"></a><span data-ttu-id="bdb3b-102">ICorDebugRemote-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bdb3b-102">ICorDebugRemote Interface</span></span>
<span data-ttu-id="bdb3b-103">Bietet die Möglichkeit, einen verwalteten Debugger an einen Remotezielprozess anzufügen oder dort zu starten.</span><span class="sxs-lookup"><span data-stu-id="bdb3b-103">Provides the ability to launch or attach a managed debugger to a remote target process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bdb3b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="bdb3b-104">Syntax</span></span>  
  
```  
interface ICorDebugRemote : IUnknown  
{  
    HRESULT CreateProcessEx  
      (  
      [in] ICorDebugRemoteTarget *     pRemoteTarget,  
      [in] LPCWSTR                     lpApplicationName,  
      [in] LPWSTR                      lpCommandLine,  
      [in] LPSECURITY_ATTRIBUTES       lpProcessAttributes,  
      [in] LPSECURITY_ATTRIBUTES       lpThreadAttributes,  
      [in] BOOL                        bInheritHandles,  
      [in] DWORD                       dwCreationFlags,  
      [in] PVOID                       lpEnvironment,  
      [in] LPCWSTR                     lpCurrentDirectory,  
      [in] LPSTARTUPINFOW              lpStartupInfo,  
      [in] LPPROCESS_INFORMATION       lpProcessInformation,  
      [in] CorDebugCreateProcessFlags  debuggingFlags,  
      [out] ICorDebugProcess **        ppProcess  
      );  
  
    HRESULT DebugActiveProcessEx  
      (  
      [in] ICorDebugRemoteTarget *   pRemoteTarget,  
      [in] DWORD                     dwProcessId,  
      [in] BOOL                      fWin32Attach,  
      [out] ICorDebugProcess **      ppProcess  
      );  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="bdb3b-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="bdb3b-105">Methods</span></span>  
  
|<span data-ttu-id="bdb3b-106">Methode</span><span class="sxs-lookup"><span data-stu-id="bdb3b-106">Method</span></span>|<span data-ttu-id="bdb3b-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bdb3b-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="bdb3b-108">ICorDebugRemote::CreateProcessEx-Methode</span><span class="sxs-lookup"><span data-stu-id="bdb3b-108">ICorDebugRemote::CreateProcessEx Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremote-createprocessex-method.md)|<span data-ttu-id="bdb3b-109">Erstellt einen Prozess auf einem Remotecomputer an, für das Debuggen von verwaltetem.</span><span class="sxs-lookup"><span data-stu-id="bdb3b-109">Creates a process on a remote machine for managed debugging.</span></span>|  
|[<span data-ttu-id="bdb3b-110">ICorDebugRemote::DebugActiveProcessEx-Methode</span><span class="sxs-lookup"><span data-stu-id="bdb3b-110">ICorDebugRemote::DebugActiveProcessEx Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremote-debugactiveprocessex-method.md)|<span data-ttu-id="bdb3b-111">Startet einen Prozess auf einem Remotecomputer unter dem Debugger.</span><span class="sxs-lookup"><span data-stu-id="bdb3b-111">Launches a process on a remote machine under the debugger.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bdb3b-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="bdb3b-112">Remarks</span></span>  
 <span data-ttu-id="bdb3b-113">Derzeit wird diese Funktion unterstützt, nur für das Debuggen einer Silverlight-basierten Anwendung-Ziel, das auf einem Macintosh-Remotecomputer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="bdb3b-113">Currently, this functionality is supported only for debugging a Silverlight-based application target that is running on a remote Macintosh machine.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bdb3b-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="bdb3b-114">Requirements</span></span>  
 <span data-ttu-id="bdb3b-115">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bdb3b-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bdb3b-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bdb3b-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bdb3b-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bdb3b-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bdb3b-118">**.NET Framework-Versionen:** 4.5, 4, 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="bdb3b-118">**.NET Framework Versions:** 4.5, 4, 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bdb3b-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bdb3b-119">See Also</span></span>  
 [<span data-ttu-id="bdb3b-120">ICorDebugRemoteTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bdb3b-120">ICorDebugRemoteTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)  
 [<span data-ttu-id="bdb3b-121">ICorDebug-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bdb3b-121">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)  
    
 [<span data-ttu-id="bdb3b-122">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="bdb3b-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
