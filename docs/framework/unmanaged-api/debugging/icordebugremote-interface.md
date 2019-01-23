---
title: ICorDebugRemote-Schnittstelle
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5cb7a3100e1f0839b50e0430c16a02879f1b8988
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54553476"
---
# <a name="icordebugremote-interface"></a><span data-ttu-id="7ccf8-102">ICorDebugRemote-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7ccf8-102">ICorDebugRemote Interface</span></span>
<span data-ttu-id="7ccf8-103">Bietet die Möglichkeit, einen verwalteten Debugger an einen Remotezielprozess anzufügen oder dort zu starten.</span><span class="sxs-lookup"><span data-stu-id="7ccf8-103">Provides the ability to launch or attach a managed debugger to a remote target process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ccf8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7ccf8-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="7ccf8-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="7ccf8-105">Methods</span></span>  
  
|<span data-ttu-id="7ccf8-106">Methode</span><span class="sxs-lookup"><span data-stu-id="7ccf8-106">Method</span></span>|<span data-ttu-id="7ccf8-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7ccf8-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7ccf8-108">ICorDebugRemote::CreateProcessEx-Methode</span><span class="sxs-lookup"><span data-stu-id="7ccf8-108">ICorDebugRemote::CreateProcessEx Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremote-createprocessex-method.md)|<span data-ttu-id="7ccf8-109">Erstellt einen Prozess auf einem Remotecomputer an, für das verwaltete Debuggen.</span><span class="sxs-lookup"><span data-stu-id="7ccf8-109">Creates a process on a remote machine for managed debugging.</span></span>|  
|[<span data-ttu-id="7ccf8-110">ICorDebugRemote::DebugActiveProcessEx-Methode</span><span class="sxs-lookup"><span data-stu-id="7ccf8-110">ICorDebugRemote::DebugActiveProcessEx Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremote-debugactiveprocessex-method.md)|<span data-ttu-id="7ccf8-111">Startet einen Prozess auf einem Remotecomputer unter dem Debugger.</span><span class="sxs-lookup"><span data-stu-id="7ccf8-111">Launches a process on a remote machine under the debugger.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7ccf8-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7ccf8-112">Remarks</span></span>  
 <span data-ttu-id="7ccf8-113">Derzeit wird diese Funktion unterstützt, nur für das Debuggen ein Silverlight-Anwendung-Ziel, das auf einem Macintosh-Remotecomputer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="7ccf8-113">Currently, this functionality is supported only for debugging a Silverlight-based application target that is running on a remote Macintosh machine.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7ccf8-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7ccf8-114">Requirements</span></span>  
 <span data-ttu-id="7ccf8-115">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7ccf8-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7ccf8-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7ccf8-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7ccf8-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7ccf8-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7ccf8-118">**.NET Framework-Versionen:** 4.5, 4, 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="7ccf8-118">**.NET Framework Versions:** 4.5, 4, 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ccf8-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7ccf8-119">See also</span></span>
- [<span data-ttu-id="7ccf8-120">ICorDebugRemoteTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7ccf8-120">ICorDebugRemoteTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)
- [<span data-ttu-id="7ccf8-121">ICorDebug-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7ccf8-121">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)

- [<span data-ttu-id="7ccf8-122">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="7ccf8-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
