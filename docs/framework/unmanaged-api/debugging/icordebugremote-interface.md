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
ms.openlocfilehash: ab8ed5c4fa3dc0ed77c1948aa6c1b940ecc25c14
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33421450"
---
# <a name="icordebugremote-interface"></a><span data-ttu-id="5ff79-102">ICorDebugRemote-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5ff79-102">ICorDebugRemote Interface</span></span>
<span data-ttu-id="5ff79-103">Bietet die Möglichkeit, einen verwalteten Debugger an einen Remotezielprozess anzufügen oder dort zu starten.</span><span class="sxs-lookup"><span data-stu-id="5ff79-103">Provides the ability to launch or attach a managed debugger to a remote target process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ff79-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5ff79-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="5ff79-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="5ff79-105">Methods</span></span>  
  
|<span data-ttu-id="5ff79-106">Methode</span><span class="sxs-lookup"><span data-stu-id="5ff79-106">Method</span></span>|<span data-ttu-id="5ff79-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5ff79-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5ff79-108">ICorDebugRemote::CreateProcessEx-Methode</span><span class="sxs-lookup"><span data-stu-id="5ff79-108">ICorDebugRemote::CreateProcessEx Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremote-createprocessex-method.md)|<span data-ttu-id="5ff79-109">Erstellt einen Prozess auf einem Remotecomputer an, für das Debuggen von verwaltetem.</span><span class="sxs-lookup"><span data-stu-id="5ff79-109">Creates a process on a remote machine for managed debugging.</span></span>|  
|[<span data-ttu-id="5ff79-110">ICorDebugRemote::DebugActiveProcessEx-Methode</span><span class="sxs-lookup"><span data-stu-id="5ff79-110">ICorDebugRemote::DebugActiveProcessEx Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremote-debugactiveprocessex-method.md)|<span data-ttu-id="5ff79-111">Startet einen Prozess auf einem Remotecomputer unter dem Debugger.</span><span class="sxs-lookup"><span data-stu-id="5ff79-111">Launches a process on a remote machine under the debugger.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5ff79-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5ff79-112">Remarks</span></span>  
 <span data-ttu-id="5ff79-113">Derzeit wird diese Funktion unterstützt, nur für das Debuggen einer Silverlight-basierten Anwendung-Ziel, das auf einem Macintosh-Remotecomputer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="5ff79-113">Currently, this functionality is supported only for debugging a Silverlight-based application target that is running on a remote Macintosh machine.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5ff79-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5ff79-114">Requirements</span></span>  
 <span data-ttu-id="5ff79-115">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5ff79-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5ff79-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5ff79-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5ff79-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5ff79-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5ff79-118">**.NET Framework-Versionen:** 4.5, 4, 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="5ff79-118">**.NET Framework Versions:** 4.5, 4, 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ff79-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5ff79-119">See Also</span></span>  
 [<span data-ttu-id="5ff79-120">ICorDebugRemoteTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5ff79-120">ICorDebugRemoteTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)  
 [<span data-ttu-id="5ff79-121">ICorDebug-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5ff79-121">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)  
    
 [<span data-ttu-id="5ff79-122">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="5ff79-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
