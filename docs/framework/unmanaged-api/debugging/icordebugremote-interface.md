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
ms.openlocfilehash: 0cc79c0a93fa4f05b8c793a8b7fb0b9b3f031b1a
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791957"
---
# <a name="icordebugremote-interface"></a><span data-ttu-id="99e65-102">ICorDebugRemote-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="99e65-102">ICorDebugRemote Interface</span></span>
<span data-ttu-id="99e65-103">Bietet die Möglichkeit, einen verwalteten Debugger an einen Remotezielprozess anzufügen oder dort zu starten.</span><span class="sxs-lookup"><span data-stu-id="99e65-103">Provides the ability to launch or attach a managed debugger to a remote target process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99e65-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="99e65-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="methods"></a><span data-ttu-id="99e65-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="99e65-105">Methods</span></span>  
  
|<span data-ttu-id="99e65-106">-Methode</span><span class="sxs-lookup"><span data-stu-id="99e65-106">Method</span></span>|<span data-ttu-id="99e65-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="99e65-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="99e65-108">ICorDebugRemote::CreateProcessEx-Methode</span><span class="sxs-lookup"><span data-stu-id="99e65-108">ICorDebugRemote::CreateProcessEx Method</span></span>](icordebugremote-createprocessex-method.md)|<span data-ttu-id="99e65-109">Erstellt einen Prozess auf einem Remote Computer für verwaltetes Debuggen.</span><span class="sxs-lookup"><span data-stu-id="99e65-109">Creates a process on a remote machine for managed debugging.</span></span>|  
|[<span data-ttu-id="99e65-110">ICorDebugRemote::DebugActiveProcessEx-Methode</span><span class="sxs-lookup"><span data-stu-id="99e65-110">ICorDebugRemote::DebugActiveProcessEx Method</span></span>](icordebugremote-debugactiveprocessex-method.md)|<span data-ttu-id="99e65-111">Startet einen Prozess auf einem Remote Computer unter dem Debugger.</span><span class="sxs-lookup"><span data-stu-id="99e65-111">Launches a process on a remote machine under the debugger.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="99e65-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="99e65-112">Remarks</span></span>  
 <span data-ttu-id="99e65-113">Diese Funktion wird zurzeit nur für das Debuggen eines Silverlight-basierten Anwendungs Ziels unterstützt, das auf einem Macintosh-Remote Computer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="99e65-113">Currently, this functionality is supported only for debugging a Silverlight-based application target that is running on a remote Macintosh machine.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="99e65-114">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="99e65-114">Requirements</span></span>  
 <span data-ttu-id="99e65-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="99e65-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="99e65-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="99e65-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="99e65-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="99e65-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="99e65-118">**.NET Framework Versionen:** 4,5, 4, 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="99e65-118">**.NET Framework Versions:** 4.5, 4, 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99e65-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="99e65-119">See also</span></span>

- [<span data-ttu-id="99e65-120">ICorDebugRemoteTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="99e65-120">ICorDebugRemoteTarget Interface</span></span>](icordebugremotetarget-interface.md)
- [<span data-ttu-id="99e65-121">ICorDebug-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="99e65-121">ICorDebug Interface</span></span>](icordebug-interface.md)

- [<span data-ttu-id="99e65-122">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="99e65-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
