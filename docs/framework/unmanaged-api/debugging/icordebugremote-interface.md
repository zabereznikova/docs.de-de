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
ms.openlocfilehash: ef11aa48f679592126f736c2877c697f02cb5e62
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379249"
---
# <a name="icordebugremote-interface"></a><span data-ttu-id="c1fdd-102">ICorDebugRemote-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c1fdd-102">ICorDebugRemote Interface</span></span>
<span data-ttu-id="c1fdd-103">Bietet die Möglichkeit, einen verwalteten Debugger an einen Remotezielprozess anzufügen oder dort zu starten.</span><span class="sxs-lookup"><span data-stu-id="c1fdd-103">Provides the ability to launch or attach a managed debugger to a remote target process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1fdd-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c1fdd-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="c1fdd-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="c1fdd-105">Methods</span></span>  
  
|<span data-ttu-id="c1fdd-106">Methode</span><span class="sxs-lookup"><span data-stu-id="c1fdd-106">Method</span></span>|<span data-ttu-id="c1fdd-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c1fdd-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c1fdd-108">ICorDebugRemote::CreateProcessEx-Methode</span><span class="sxs-lookup"><span data-stu-id="c1fdd-108">ICorDebugRemote::CreateProcessEx Method</span></span>](icordebugremote-createprocessex-method.md)|<span data-ttu-id="c1fdd-109">Erstellt einen Prozess auf einem Remote Computer für verwaltetes Debuggen.</span><span class="sxs-lookup"><span data-stu-id="c1fdd-109">Creates a process on a remote machine for managed debugging.</span></span>|  
|[<span data-ttu-id="c1fdd-110">ICorDebugRemote::DebugActiveProcessEx-Methode</span><span class="sxs-lookup"><span data-stu-id="c1fdd-110">ICorDebugRemote::DebugActiveProcessEx Method</span></span>](icordebugremote-debugactiveprocessex-method.md)|<span data-ttu-id="c1fdd-111">Startet einen Prozess auf einem Remote Computer unter dem Debugger.</span><span class="sxs-lookup"><span data-stu-id="c1fdd-111">Launches a process on a remote machine under the debugger.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c1fdd-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c1fdd-112">Remarks</span></span>  
 <span data-ttu-id="c1fdd-113">Diese Funktion wird zurzeit nur für das Debuggen eines Silverlight-basierten Anwendungs Ziels unterstützt, das auf einem Macintosh-Remote Computer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c1fdd-113">Currently, this functionality is supported only for debugging a Silverlight-based application target that is running on a remote Macintosh machine.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c1fdd-114">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="c1fdd-114">Requirements</span></span>  
 <span data-ttu-id="c1fdd-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c1fdd-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c1fdd-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c1fdd-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c1fdd-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c1fdd-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c1fdd-118">**.NET Framework Versionen:** 4,5, 4, 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="c1fdd-118">**.NET Framework Versions:** 4.5, 4, 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1fdd-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c1fdd-119">See also</span></span>

- [<span data-ttu-id="c1fdd-120">ICorDebugRemoteTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c1fdd-120">ICorDebugRemoteTarget Interface</span></span>](icordebugremotetarget-interface.md)
- [<span data-ttu-id="c1fdd-121">ICorDebug-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c1fdd-121">ICorDebug Interface</span></span>](icordebug-interface.md)

- [<span data-ttu-id="c1fdd-122">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="c1fdd-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
