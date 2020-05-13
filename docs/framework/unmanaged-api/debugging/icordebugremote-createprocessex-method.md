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
ms.openlocfilehash: 4b2689f04228c9ecbbbb18531a0aefd3c40e3072
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "83377980"
---
# <a name="icordebugremotecreateprocessex-method"></a><span data-ttu-id="eeee2-102">ICorDebugRemote::CreateProcessEx-Methode</span><span class="sxs-lookup"><span data-stu-id="eeee2-102">ICorDebugRemote::CreateProcessEx Method</span></span>
<span data-ttu-id="eeee2-103">Startet einen Prozess auf einem Remote Computer unter dem Debugger.</span><span class="sxs-lookup"><span data-stu-id="eeee2-103">Launches a process on a remote machine under the debugger.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eeee2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="eeee2-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="eeee2-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="eeee2-105">Parameters</span></span>  
 `pRemoteTarget`  
 <span data-ttu-id="eeee2-106">in Zeiger auf eine [icordebugremotetarget-Schnittstelle](icordebugremotetarget-interface.md).</span><span class="sxs-lookup"><span data-stu-id="eeee2-106">[in] Pointer to an [ICorDebugRemoteTarget Interface](icordebugremotetarget-interface.md).</span></span> <span data-ttu-id="eeee2-107">Wird verwendet, um den Remote Computer zu ermitteln, auf dem der Prozess gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="eeee2-107">Used to determine the remote machine on which the process will be launched.</span></span>  
  
 `lpApplicationName`  
 <span data-ttu-id="eeee2-108">in Zeiger auf eine auf NULL endende Zeichenfolge, die das Modul angibt, das vom gestarteten Prozess ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="eeee2-108">[in] Pointer to a null-terminated string that specifies the module to be executed by the launched process.</span></span> <span data-ttu-id="eeee2-109">Das Modul wird im Sicherheitskontext des aufrufenden Prozesses ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="eeee2-109">The module is executed in the security context of the calling process.</span></span>  
  
 `lpCommandLine`  
 <span data-ttu-id="eeee2-110">in Zeiger auf eine auf NULL endende Zeichenfolge, die die Befehlszeile angibt, die vom gestarteten Prozess ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="eeee2-110">[in] Pointer to a null-terminated string that specifies the command line to be executed by the launched process.</span></span>  
  
 `lpProcessAttributes`  
 <span data-ttu-id="eeee2-111">in Nicht für Remote Debuggen verwendet.</span><span class="sxs-lookup"><span data-stu-id="eeee2-111">[in] Unused for remote debugging.</span></span>  
  
 `lpThreadAttributes`  
 <span data-ttu-id="eeee2-112">in Nicht für Remote Debuggen verwendet.</span><span class="sxs-lookup"><span data-stu-id="eeee2-112">[in] Unused for remote debugging.</span></span>  
  
 `bInheritHandles`  
 <span data-ttu-id="eeee2-113">in Nicht für Remote Debuggen verwendet.</span><span class="sxs-lookup"><span data-stu-id="eeee2-113">[in] Unused for remote debugging.</span></span>  
  
 `dwCreationFlags`  
 <span data-ttu-id="eeee2-114">in Nicht für Remote Debuggen verwendet.</span><span class="sxs-lookup"><span data-stu-id="eeee2-114">[in] Unused for remote debugging.</span></span>  
  
 `lpEnvironment`  
 <span data-ttu-id="eeee2-115">in Zeiger auf einen Umgebungsblock für den neuen Prozess.</span><span class="sxs-lookup"><span data-stu-id="eeee2-115">[in] Pointer to an environment block for the new process.</span></span>  
  
 `lpCurrentDirectory`  
 <span data-ttu-id="eeee2-116">in Ein Zeiger auf eine mit NULL endenden Zeichenfolge, die den vollständigen Pfad zum aktuellen Verzeichnis für den Prozess angibt.</span><span class="sxs-lookup"><span data-stu-id="eeee2-116">[in] Pointer to a null-terminated string that specifies the full path to the current directory for the process.</span></span> <span data-ttu-id="eeee2-117">Wenn dieser Parameter NULL ist, weist der neue Prozess dasselbe aktuelle Laufwerk und Verzeichnis wie der aufrufende Prozess auf.</span><span class="sxs-lookup"><span data-stu-id="eeee2-117">If this parameter is null, the new process will have the same current drive and directory as the calling process.</span></span>  
  
 `lpStartupInfo`  
 <span data-ttu-id="eeee2-118">in Nicht für Remote Debuggen verwendet.</span><span class="sxs-lookup"><span data-stu-id="eeee2-118">[in] Unused for remote debugging.</span></span>  
  
 `lpProcessInformation`  
 <span data-ttu-id="eeee2-119">in Nicht für Remote Debuggen verwendet.</span><span class="sxs-lookup"><span data-stu-id="eeee2-119">[in] Unused for remote debugging.</span></span>  
  
 `debuggingFlags`  
 <span data-ttu-id="eeee2-120">in Nicht für Remote Debuggen verwendet.</span><span class="sxs-lookup"><span data-stu-id="eeee2-120">[in] Unused for remote debugging.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="eeee2-121">vorgenommen Ein Zeiger auf die Adresse eines ICorDebugProcess-Schnittstellen Objekts, das den Prozess darstellt.</span><span class="sxs-lookup"><span data-stu-id="eeee2-121">[out] A pointer to the address of a"ICorDebugProcess Interface" object that represents the process.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="eeee2-122">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="eeee2-122">Return Value</span></span>  
 <span data-ttu-id="eeee2-123">S_OK</span><span class="sxs-lookup"><span data-stu-id="eeee2-123">S_OK</span></span>  
 <span data-ttu-id="eeee2-124">Der Prozess wurde erfolgreich auf dem Remote Computer gestartet, und es wurde eine ICorDebugProcess-Schnittstelle für das Debuggen zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="eeee2-124">Successfully launched the process on the remote machine and returned an "ICorDebugProcess Interface" for debugging.</span></span>  
  
 <span data-ttu-id="eeee2-125">E_FAIL (oder andere E_-Rückgabecodes)</span><span class="sxs-lookup"><span data-stu-id="eeee2-125">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="eeee2-126">Der Prozess kann auf dem Remote Computer nicht gestartet werden, und es wird eine ICorDebugProcess-Schnittstelle für das Debuggen zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="eeee2-126">Unable to launch the process on the remote machine and return an "ICorDebugProcess Interface" for debugging.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="eeee2-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="eeee2-127">Remarks</span></span>  
 <span data-ttu-id="eeee2-128">Das Debuggen im gemischten Modus wird in Silverlight nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="eeee2-128">Mixed-mode debugging is not supported in Silverlight.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eeee2-129">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="eeee2-129">Requirements</span></span>  
 <span data-ttu-id="eeee2-130">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eeee2-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eeee2-131">**Header:** Cordebug. idl</span><span class="sxs-lookup"><span data-stu-id="eeee2-131">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="eeee2-132">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eeee2-132">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="eeee2-133">**.NET Framework Versionen:** 4,5, 4, 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="eeee2-133">**.NET Framework Versions:** 4.5, 4, 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eeee2-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="eeee2-134">See also</span></span>

- [<span data-ttu-id="eeee2-135">ICorDebugRemote-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="eeee2-135">ICorDebugRemote Interface</span></span>](icordebugremote-interface.md)
- [<span data-ttu-id="eeee2-136">ICorDebug-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="eeee2-136">ICorDebug Interface</span></span>](icordebug-interface.md)

- [<span data-ttu-id="eeee2-137">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="eeee2-137">Debugging Interfaces</span></span>](debugging-interfaces.md)
