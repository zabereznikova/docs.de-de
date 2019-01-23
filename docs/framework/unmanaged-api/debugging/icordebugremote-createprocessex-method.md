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
ms.openlocfilehash: efc46a0128a4fb9a0edaa86ad20689fda0c2710b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54521776"
---
# <a name="icordebugremotecreateprocessex-method"></a><span data-ttu-id="bcd2c-102">ICorDebugRemote::CreateProcessEx-Methode</span><span class="sxs-lookup"><span data-stu-id="bcd2c-102">ICorDebugRemote::CreateProcessEx Method</span></span>
<span data-ttu-id="bcd2c-103">Startet einen Prozess auf einem Remotecomputer unter dem Debugger.</span><span class="sxs-lookup"><span data-stu-id="bcd2c-103">Launches a process on a remote machine under the debugger.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bcd2c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="bcd2c-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="bcd2c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="bcd2c-105">Parameters</span></span>  
 `pRemoteTarget`  
 <span data-ttu-id="bcd2c-106">[in] Zeiger auf eine [ICorDebugRemoteTarget-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md).</span><span class="sxs-lookup"><span data-stu-id="bcd2c-106">[in] Pointer to an [ICorDebugRemoteTarget Interface](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md).</span></span> <span data-ttu-id="bcd2c-107">Wird verwendet, um den Remotecomputer zu ermitteln, auf dem der Prozess gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="bcd2c-107">Used to determine the remote machine on which the process will be launched.</span></span>  
  
 `lpApplicationName`  
 <span data-ttu-id="bcd2c-108">[in] Zeiger auf eine auf Null endende Zeichenfolge, die angibt, das Modul der gestartete Prozess ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="bcd2c-108">[in] Pointer to a null-terminated string that specifies the module to be executed by the launched process.</span></span> <span data-ttu-id="bcd2c-109">Das Modul wird im Kontext des aufrufenden Prozesses ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="bcd2c-109">The module is executed in the security context of the calling process.</span></span>  
  
 `lpCommandLine`  
 <span data-ttu-id="bcd2c-110">[in] Zeiger auf eine auf Null endende Zeichenfolge, die angibt, die Befehlszeile der gestartete Prozess ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="bcd2c-110">[in] Pointer to a null-terminated string that specifies the command line to be executed by the launched process.</span></span>  
  
 `lpProcessAttributes`  
 <span data-ttu-id="bcd2c-111">[in] Wenn Sie nicht für das Remotedebuggen verwendet.</span><span class="sxs-lookup"><span data-stu-id="bcd2c-111">[in] Unused for remote debugging.</span></span>  
  
 `lpThreadAttributes`  
 <span data-ttu-id="bcd2c-112">[in] Wenn Sie nicht für das Remotedebuggen verwendet.</span><span class="sxs-lookup"><span data-stu-id="bcd2c-112">[in] Unused for remote debugging.</span></span>  
  
 `bInheritHandles`  
 <span data-ttu-id="bcd2c-113">[in] Wenn Sie nicht für das Remotedebuggen verwendet.</span><span class="sxs-lookup"><span data-stu-id="bcd2c-113">[in] Unused for remote debugging.</span></span>  
  
 `dwCreationFlags`  
 <span data-ttu-id="bcd2c-114">[in] Wenn Sie nicht für das Remotedebuggen verwendet.</span><span class="sxs-lookup"><span data-stu-id="bcd2c-114">[in] Unused for remote debugging.</span></span>  
  
 `lpEnvironment`  
 <span data-ttu-id="bcd2c-115">[in] Zeiger auf eine Umgebungsblock für den neuen Prozess.</span><span class="sxs-lookup"><span data-stu-id="bcd2c-115">[in] Pointer to an environment block for the new process.</span></span>  
  
 `lpCurrentDirectory`  
 <span data-ttu-id="bcd2c-116">[in] Zeiger auf eine auf Null endende Zeichenfolge, die den vollständigen Pfad zum aktuellen Verzeichnis für den Prozess angibt.</span><span class="sxs-lookup"><span data-stu-id="bcd2c-116">[in] Pointer to a null-terminated string that specifies the full path to the current directory for the process.</span></span> <span data-ttu-id="bcd2c-117">Wenn dieser Parameter null ist, wird der neue Prozess das gleiche aktuelle Laufwerk und Verzeichnis wie der aufrufende Prozess haben.</span><span class="sxs-lookup"><span data-stu-id="bcd2c-117">If this parameter is null, the new process will have the same current drive and directory as the calling process.</span></span>  
  
 `lpStartupInfo`  
 <span data-ttu-id="bcd2c-118">[in] Wenn Sie nicht für das Remotedebuggen verwendet.</span><span class="sxs-lookup"><span data-stu-id="bcd2c-118">[in] Unused for remote debugging.</span></span>  
  
 `lpProcessInformation`  
 <span data-ttu-id="bcd2c-119">[in] Wenn Sie nicht für das Remotedebuggen verwendet.</span><span class="sxs-lookup"><span data-stu-id="bcd2c-119">[in] Unused for remote debugging.</span></span>  
  
 `debuggingFlags`  
 <span data-ttu-id="bcd2c-120">[in] Wenn Sie nicht für das Remotedebuggen verwendet.</span><span class="sxs-lookup"><span data-stu-id="bcd2c-120">[in] Unused for remote debugging.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="bcd2c-121">[out] Ein Zeiger auf die Adresse ein "ICorDebugProcess-Schnittstelle"-Objekt, das den Prozess darstellt.</span><span class="sxs-lookup"><span data-stu-id="bcd2c-121">[out] A pointer to the address of a"ICorDebugProcess Interface" object that represents the process.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bcd2c-122">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="bcd2c-122">Return Value</span></span>  
 <span data-ttu-id="bcd2c-123">S_OK</span><span class="sxs-lookup"><span data-stu-id="bcd2c-123">S_OK</span></span>  
 <span data-ttu-id="bcd2c-124">Wurde erfolgreich gestartet den Prozess auf dem Remotecomputer und zurückgegebenen ein "ICorDebugProcess-Schnittstelle" für das Debuggen.</span><span class="sxs-lookup"><span data-stu-id="bcd2c-124">Successfully launched the process on the remote machine and returned an "ICorDebugProcess Interface" for debugging.</span></span>  
  
 <span data-ttu-id="bcd2c-125">E_FAIL (oder andere E_-Rückgabecodes)</span><span class="sxs-lookup"><span data-stu-id="bcd2c-125">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="bcd2c-126">Starten Sie den Prozess auf dem Remotecomputer und Zurückgeben von "ICorDebugProcess-Schnittstelle" für das Debuggen nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="bcd2c-126">Unable to launch the process on the remote machine and return an "ICorDebugProcess Interface" for debugging.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bcd2c-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="bcd2c-127">Remarks</span></span>  
 <span data-ttu-id="bcd2c-128">Debuggen im gemischten Modus wird in Silverlight nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="bcd2c-128">Mixed-mode debugging is not supported in Silverlight.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bcd2c-129">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="bcd2c-129">Requirements</span></span>  
 <span data-ttu-id="bcd2c-130">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bcd2c-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bcd2c-131">**Header:** CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="bcd2c-131">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="bcd2c-132">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bcd2c-132">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bcd2c-133">**.NET Framework-Versionen:** 4.5, 4, 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="bcd2c-133">**.NET Framework Versions:** 4.5, 4, 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bcd2c-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bcd2c-134">See also</span></span>
- [<span data-ttu-id="bcd2c-135">ICorDebugRemote-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bcd2c-135">ICorDebugRemote Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremote-interface.md)
- [<span data-ttu-id="bcd2c-136">ICorDebug-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bcd2c-136">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)

- [<span data-ttu-id="bcd2c-137">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="bcd2c-137">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
