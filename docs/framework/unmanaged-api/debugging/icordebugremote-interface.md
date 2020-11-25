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
ms.openlocfilehash: 276d36c511105087190cb7e9dfeaa6932efc67ff
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95712104"
---
# <a name="icordebugremote-interface"></a><span data-ttu-id="ea978-102">ICorDebugRemote-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ea978-102">ICorDebugRemote Interface</span></span>

<span data-ttu-id="ea978-103">Bietet die Möglichkeit, einen verwalteten Debugger an einen Remotezielprozess anzufügen oder dort zu starten.</span><span class="sxs-lookup"><span data-stu-id="ea978-103">Provides the ability to launch or attach a managed debugger to a remote target process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea978-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ea978-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="ea978-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="ea978-105">Methods</span></span>  
  
|<span data-ttu-id="ea978-106">Methode</span><span class="sxs-lookup"><span data-stu-id="ea978-106">Method</span></span>|<span data-ttu-id="ea978-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="ea978-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ea978-108">ICorDebugRemote::CreateProcessEx-Methode</span><span class="sxs-lookup"><span data-stu-id="ea978-108">ICorDebugRemote::CreateProcessEx Method</span></span>](icordebugremote-createprocessex-method.md)|<span data-ttu-id="ea978-109">Erstellt einen Prozess auf einem Remote Computer für verwaltetes Debuggen.</span><span class="sxs-lookup"><span data-stu-id="ea978-109">Creates a process on a remote machine for managed debugging.</span></span>|  
|[<span data-ttu-id="ea978-110">ICorDebugRemote::DebugActiveProcessEx-Methode</span><span class="sxs-lookup"><span data-stu-id="ea978-110">ICorDebugRemote::DebugActiveProcessEx Method</span></span>](icordebugremote-debugactiveprocessex-method.md)|<span data-ttu-id="ea978-111">Startet einen Prozess auf einem Remote Computer unter dem Debugger.</span><span class="sxs-lookup"><span data-stu-id="ea978-111">Launches a process on a remote machine under the debugger.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ea978-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ea978-112">Remarks</span></span>  

 <span data-ttu-id="ea978-113">Diese Funktion wird zurzeit nur für das Debuggen eines Silverlight-basierten Anwendungs Ziels unterstützt, das auf einem Macintosh-Remote Computer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ea978-113">Currently, this functionality is supported only for debugging a Silverlight-based application target that is running on a remote Macintosh machine.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ea978-114">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="ea978-114">Requirements</span></span>  

 <span data-ttu-id="ea978-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ea978-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ea978-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ea978-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ea978-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ea978-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ea978-118">**.NET Framework Versionen:** 4,5, 4, 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="ea978-118">**.NET Framework Versions:** 4.5, 4, 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea978-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ea978-119">See also</span></span>

- [<span data-ttu-id="ea978-120">ICorDebugRemoteTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ea978-120">ICorDebugRemoteTarget Interface</span></span>](icordebugremotetarget-interface.md)
- [<span data-ttu-id="ea978-121">ICorDebug-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ea978-121">ICorDebug Interface</span></span>](icordebug-interface.md)

- [<span data-ttu-id="ea978-122">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="ea978-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
