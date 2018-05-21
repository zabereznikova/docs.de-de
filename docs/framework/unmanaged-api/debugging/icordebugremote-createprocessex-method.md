---
title: ICorDebugRemote::CreateProcessEx-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugRemote.CreateProcessEx
api_location:
- CorDebug.dll
api_type:
- COM
f1_keywords:
- ICorDebugRemoteTarget::CreateProcessEx
helpviewer_keywords:
- CreateProcessEx method, ICorDebugRemote interface [.NET Framework debugging]
- ICorDebugRemote::CreateProcessEx method [.NET Framework debugging]
ms.assetid: 41af93c7-e448-4251-8d4d-413d38c635f2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 06bdc3605d981acad68a97901627f361da4061c7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugremotecreateprocessex-method"></a><span data-ttu-id="19004-102">ICorDebugRemote::CreateProcessEx-Methode</span><span class="sxs-lookup"><span data-stu-id="19004-102">ICorDebugRemote::CreateProcessEx Method</span></span>
<span data-ttu-id="19004-103">Startet einen Prozess auf einem Remotecomputer unter dem Debugger.</span><span class="sxs-lookup"><span data-stu-id="19004-103">Launches a process on a remote machine under the debugger.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19004-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="19004-104">Syntax</span></span>  
  
```  
HRESULT CreateProcessEx (  
    [in]  ICorDebugRemoteTarget*      pRemoteTarget,  
    [in]  LPCWSTR                     lpApplicationName,  
    [in]  LPWSTR                      lpCommandLine,  
    [in]  LPSECURITY_ATTRIBUTES       lpProcessAttributes,  
    [in]  LPSECURITY_ATTRIBUTES       lpThreadAttributes,  
    [in]  BOOL                        bInheritHandles,  
    [in]  DWORD                       dwCreationFlags,  
    [in]  PVOID                       lpEnvironment,  
    [in]  LPCWSTR                     lpCurrentDirectory,  
    [in]  LPSTARTUPINFOW              lpStartupInfo,  
    [in]  LPPROCESS_INFORMATION       lpProcessInformation,  
    [in]  CorDebugCreateProcessFlags  debuggingFlags,  
    [out] ICorDebugProcess**          ppProcess  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="19004-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="19004-105">Parameters</span></span>  
 `pRemoteTarget`  
 <span data-ttu-id="19004-106">[in] Zeiger auf eine [ICorDebugRemoteTarget-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md).</span><span class="sxs-lookup"><span data-stu-id="19004-106">[in] Pointer to an [ICorDebugRemoteTarget Interface](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md).</span></span> <span data-ttu-id="19004-107">Verwendet, um den Remotecomputer zu bestimmen, auf dem der Prozess gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="19004-107">Used to determine the remote machine on which the process will be launched.</span></span>  
  
 `lpApplicationName`  
 <span data-ttu-id="19004-108">[in] Ein Zeiger auf eine auf Null endende Zeichenfolge, die angibt, das Modul der gestartete Prozess ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="19004-108">[in] Pointer to a null-terminated string that specifies the module to be executed by the launched process.</span></span> <span data-ttu-id="19004-109">Das Modul wird im Sicherheitskontext des aufrufenden Prozesses ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="19004-109">The module is executed in the security context of the calling process.</span></span>  
  
 `lpCommandLine`  
 <span data-ttu-id="19004-110">[in] Ein Zeiger auf eine auf Null endende Zeichenfolge, die angibt, die Befehlszeile der gestartete Prozess ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="19004-110">[in] Pointer to a null-terminated string that specifies the command line to be executed by the launched process.</span></span>  
  
 `lpProcessAttributes`  
 <span data-ttu-id="19004-111">[in] Für das Remotedebuggen wird nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="19004-111">[in] Unused for remote debugging.</span></span>  
  
 `lpThreadAttributes`  
 <span data-ttu-id="19004-112">[in] Für das Remotedebuggen wird nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="19004-112">[in] Unused for remote debugging.</span></span>  
  
 `bInheritHandles`  
 <span data-ttu-id="19004-113">[in] Für das Remotedebuggen wird nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="19004-113">[in] Unused for remote debugging.</span></span>  
  
 `dwCreationFlags`  
 <span data-ttu-id="19004-114">[in] Für das Remotedebuggen wird nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="19004-114">[in] Unused for remote debugging.</span></span>  
  
 `lpEnvironment`  
 <span data-ttu-id="19004-115">[in] Ein Zeiger auf einen Umgebungsblock für den neuen Prozess.</span><span class="sxs-lookup"><span data-stu-id="19004-115">[in] Pointer to an environment block for the new process.</span></span>  
  
 `lpCurrentDirectory`  
 <span data-ttu-id="19004-116">[in] Ein Zeiger auf eine auf Null endende Zeichenfolge, die den vollständigen Pfad zum aktuellen Verzeichnis für den Prozess angibt.</span><span class="sxs-lookup"><span data-stu-id="19004-116">[in] Pointer to a null-terminated string that specifies the full path to the current directory for the process.</span></span> <span data-ttu-id="19004-117">Wenn dieser Parameter null ist, müssen der neue Prozess die gleichen aktuelle Laufwerk und Verzeichnis als der aufrufende Prozess.</span><span class="sxs-lookup"><span data-stu-id="19004-117">If this parameter is null, the new process will have the same current drive and directory as the calling process.</span></span>  
  
 `lpStartupInfo`  
 <span data-ttu-id="19004-118">[in] Für das Remotedebuggen wird nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="19004-118">[in] Unused for remote debugging.</span></span>  
  
 `lpProcessInformation`  
 <span data-ttu-id="19004-119">[in] Für das Remotedebuggen wird nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="19004-119">[in] Unused for remote debugging.</span></span>  
  
 `debuggingFlags`  
 <span data-ttu-id="19004-120">[in] Für das Remotedebuggen wird nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="19004-120">[in] Unused for remote debugging.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="19004-121">[out] Ein Zeiger auf die Adresse eines Objekts "ICorDebugProcess-Schnittstelle", das den Prozess darstellt.</span><span class="sxs-lookup"><span data-stu-id="19004-121">[out] A pointer to the address of a"ICorDebugProcess Interface" object that represents the process.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="19004-122">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="19004-122">Return Value</span></span>  
 <span data-ttu-id="19004-123">S_OK</span><span class="sxs-lookup"><span data-stu-id="19004-123">S_OK</span></span>  
 <span data-ttu-id="19004-124">Wurde erfolgreich gestartet den Prozess auf dem Remotecomputer und zurückgegebenen ein "ICorDebugProcess-Schnittstelle" für das Debuggen.</span><span class="sxs-lookup"><span data-stu-id="19004-124">Successfully launched the process on the remote machine and returned an "ICorDebugProcess Interface" for debugging.</span></span>  
  
 <span data-ttu-id="19004-125">E_FAIL (oder andere E_-Rückgabecodes)</span><span class="sxs-lookup"><span data-stu-id="19004-125">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="19004-126">Starten Sie den Prozess auf dem Remotecomputer und Zurückgeben von "ICorDebugProcess-Schnittstelle" für das Debuggen nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="19004-126">Unable to launch the process on the remote machine and return an "ICorDebugProcess Interface" for debugging.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="19004-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="19004-127">Remarks</span></span>  
 <span data-ttu-id="19004-128">Debuggen im gemischten Modus ist in Silverlight nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="19004-128">Mixed-mode debugging is not supported in Silverlight.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="19004-129">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="19004-129">Requirements</span></span>  
 <span data-ttu-id="19004-130">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="19004-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="19004-131">**Header:** CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="19004-131">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="19004-132">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="19004-132">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="19004-133">**.NET Framework-Versionen:** 4.5, 4, 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="19004-133">**.NET Framework Versions:** 4.5, 4, 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19004-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="19004-134">See Also</span></span>  
 [<span data-ttu-id="19004-135">ICorDebugRemote-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="19004-135">ICorDebugRemote Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremote-interface.md)  
 [<span data-ttu-id="19004-136">ICorDebug-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="19004-136">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)  
    
 [<span data-ttu-id="19004-137">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="19004-137">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
