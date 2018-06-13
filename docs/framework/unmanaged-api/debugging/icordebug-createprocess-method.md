---
title: ICorDebug::CreateProcess-Methode
ms.date: 03/30/2017
api_name:
- ICorDebug.CreateProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::CreateProcess
helpviewer_keywords:
- ICorDebug::CreateProcess method [.NET Framework debugging]
- CreateProcess method, ICorDebugProcess interface [.NET Framework debugging]
ms.assetid: b6128694-11ed-46e7-bd4e-49ea1914c46a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 044f94a567dc4bc2b169ba2a5f2a5d7b4f98e516
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33408576"
---
# <a name="icordebugcreateprocess-method"></a><span data-ttu-id="a57cf-102">ICorDebug::CreateProcess-Methode</span><span class="sxs-lookup"><span data-stu-id="a57cf-102">ICorDebug::CreateProcess Method</span></span>
<span data-ttu-id="a57cf-103">Startet einen Prozess und seine primäre Thread unter der Kontrolle des Debuggers.</span><span class="sxs-lookup"><span data-stu-id="a57cf-103">Launches a process and its primary thread under the control of the debugger.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a57cf-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a57cf-104">Syntax</span></span>  
  
```  
HRESULT CreateProcess (  
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
    [out] ICorDebugProcess            **ppProcess  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a57cf-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a57cf-105">Parameters</span></span>  
 `lpApplicationName`  
 <span data-ttu-id="a57cf-106">[in] Ein Zeiger auf eine auf Null endende Zeichenfolge, die angibt, das Modul der gestartete Prozess ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="a57cf-106">[in] Pointer to a null-terminated string that specifies the module to be executed by the launched process.</span></span> <span data-ttu-id="a57cf-107">Das Modul wird im Sicherheitskontext des aufrufenden Prozesses ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="a57cf-107">The module is executed in the security context of the calling process.</span></span>  
  
 `lpCommandLine`  
 <span data-ttu-id="a57cf-108">[in] Ein Zeiger auf eine auf Null endende Zeichenfolge, die angibt, die Befehlszeile der gestartete Prozess ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="a57cf-108">[in] Pointer to a null-terminated string that specifies the command line to be executed by the launched process.</span></span> <span data-ttu-id="a57cf-109">Der Anwendungsname (z. B. "SomeApp.exe") muss das erste Argument.</span><span class="sxs-lookup"><span data-stu-id="a57cf-109">The application name (for example, "SomeApp.exe") must be the first argument.</span></span>  
  
 `lpProcessAttributes`  
 <span data-ttu-id="a57cf-110">[in] Zeiger auf eine Win32- `SECURITY_ATTRIBUTES` -Struktur, die Sicherheitsbeschreibung für den Prozess angibt.</span><span class="sxs-lookup"><span data-stu-id="a57cf-110">[in] Pointer to a Win32 `SECURITY_ATTRIBUTES` structure that specifies the security descriptor for the process.</span></span> <span data-ttu-id="a57cf-111">Wenn `lpProcessAttributes` ist null, ruft der Prozess eine standardsicherheitsbeschreibung.</span><span class="sxs-lookup"><span data-stu-id="a57cf-111">If `lpProcessAttributes` is null, the process gets a default security descriptor.</span></span>  
  
 `lpThreadAttributes`  
 <span data-ttu-id="a57cf-112">[in] Zeiger auf eine Win32- `SECURITY_ATTRIBUTES` -Struktur, die Sicherheitsbeschreibung für den primären Thread des Prozesses angibt.</span><span class="sxs-lookup"><span data-stu-id="a57cf-112">[in] Pointer to a Win32 `SECURITY_ATTRIBUTES` structure that specifies the security descriptor for the primary thread of the process.</span></span> <span data-ttu-id="a57cf-113">Wenn `lpThreadAttributes` ist null, der Thread Ruft eine standardsicherheitsbeschreibung.</span><span class="sxs-lookup"><span data-stu-id="a57cf-113">If `lpThreadAttributes` is null, the thread gets a default security descriptor.</span></span>  
  
 `bInheritHandles`  
 <span data-ttu-id="a57cf-114">[in] Legen Sie auf `true` , um anzugeben, dass jeder vererbbare Handle im aufrufenden Prozess, von der gestartete Prozess geerbt wird oder `false` , um anzugeben, dass die Handles nicht geerbt werden.</span><span class="sxs-lookup"><span data-stu-id="a57cf-114">[in] Set to `true` to indicate that each inheritable handle in the calling process is inherited by the launched process, or `false` to indicate that the handles are not inherited.</span></span> <span data-ttu-id="a57cf-115">Die vererbten Handles besitzen den gleichen Wert und Zugriffsrechte wie die ursprünglichen Handles.</span><span class="sxs-lookup"><span data-stu-id="a57cf-115">The inherited handles have the same value and access rights as the original handles.</span></span>  
  
 `dwCreationFlags`  
 <span data-ttu-id="a57cf-116">[in] Eine bitweise Kombination der [Win32-Prozess Erstellung Flags](http://go.microsoft.com/fwlink/?linkid=69981) steuern die Prioritätsklasse und das Verhalten der gestartete Prozess.</span><span class="sxs-lookup"><span data-stu-id="a57cf-116">[in] A bitwise combination of the [Win32 Process Creation Flags](http://go.microsoft.com/fwlink/?linkid=69981) that control the priority class and the behavior of the launched process.</span></span>  
  
 `lpEnvironment`  
 <span data-ttu-id="a57cf-117">[in] Ein Zeiger auf einen Umgebungsblock für den neuen Prozess.</span><span class="sxs-lookup"><span data-stu-id="a57cf-117">[in] Pointer to an environment block for the new process.</span></span>  
  
 `lpCurrentDirectory`  
 <span data-ttu-id="a57cf-118">[in] Ein Zeiger auf eine auf Null endende Zeichenfolge, die den vollständigen Pfad zum aktuellen Verzeichnis für den Prozess angibt.</span><span class="sxs-lookup"><span data-stu-id="a57cf-118">[in] Pointer to a null-terminated string that specifies the full path to the current directory for the process.</span></span> <span data-ttu-id="a57cf-119">Wenn dieser Parameter null ist, müssen der neue Prozess die gleichen aktuelle Laufwerk und Verzeichnis als der aufrufende Prozess.</span><span class="sxs-lookup"><span data-stu-id="a57cf-119">If this parameter is null, the new process will have the same current drive and directory as the calling process.</span></span>  
  
 `lpStartupInfo`  
 <span data-ttu-id="a57cf-120">[in] Zeiger auf eine Win32- `STARTUPINFOW` -Struktur, Windowstation, Desktop, standard-Handles und die Darstellung des Hauptfensters der gestartete Prozess angibt.</span><span class="sxs-lookup"><span data-stu-id="a57cf-120">[in] Pointer to a Win32 `STARTUPINFOW` structure that specifies the window station, desktop, standard handles, and appearance of the main window for the launched process.</span></span>  
  
 `lpProcessInformation`  
 <span data-ttu-id="a57cf-121">[in] Zeiger auf eine Win32- `PROCESS_INFORMATION` Struktur, der angibt, die Identifikationsinformationen über den Prozess gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="a57cf-121">[in] Pointer to a Win32 `PROCESS_INFORMATION` structure that specifies the identification information about the process to be launched.</span></span>  
  
 `debuggingFlags`  
 <span data-ttu-id="a57cf-122">[in] Der Wert der CorDebugCreateProcessFlags-Enumeration, die angibt, die Optionen für das Debuggen.</span><span class="sxs-lookup"><span data-stu-id="a57cf-122">[in] A value of the CorDebugCreateProcessFlags enumeration that specifies the debugging options.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="a57cf-123">[out] Ein Zeiger auf die Adresse eines ICorDebugProcess-Objekts, das den Prozess darstellt.</span><span class="sxs-lookup"><span data-stu-id="a57cf-123">[out] A pointer to the address of a ICorDebugProcess object that represents the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a57cf-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a57cf-124">Remarks</span></span>  
 <span data-ttu-id="a57cf-125">Die Parameter dieser Methode sind identisch mit denen der Win32- `CreateProcess` Methode.</span><span class="sxs-lookup"><span data-stu-id="a57cf-125">The parameters of this method are the same as those of the Win32 `CreateProcess` method.</span></span>  
  
 <span data-ttu-id="a57cf-126">Legen Sie zum Aktivieren von nicht verwaltetem Debuggen im gemischten Modus `dwCreationFlags` auf DEBUG_PROCESS &#124; nur diesen Prozess debuggen.</span><span class="sxs-lookup"><span data-stu-id="a57cf-126">To enable unmanaged mixed-mode debugging, set `dwCreationFlags` to DEBUG_PROCESS &#124; DEBUG_ONLY_THIS_PROCESS.</span></span> <span data-ttu-id="a57cf-127">Wenn Sie nur das verwaltete Debuggen verwenden möchten, sollten Sie diese Flags festlegen.</span><span class="sxs-lookup"><span data-stu-id="a57cf-127">If you want to use only managed debugging, do not set these flags.</span></span>  
  
 <span data-ttu-id="a57cf-128">Wenn der Debugger als auch den Prozess erforderlich (den angefügten Prozess) debuggt Freigeben einer einzelnen Konsole aus, und wenn Interop-Debuggen verwendet wird, ist es möglich, dass der angefügte Prozess Konsole sperren, und beenden Sie ein Debug-Ereignis.</span><span class="sxs-lookup"><span data-stu-id="a57cf-128">If the debugger and the process to be debugged (the attached process) share a single console, and if interop debugging is used, it is possible for the attached process to hold console locks and stop at a debug event.</span></span> <span data-ttu-id="a57cf-129">Der Debugger wird dann jeder Versuch, verwenden die Konsole blockiert.</span><span class="sxs-lookup"><span data-stu-id="a57cf-129">The debugger will then block any attempt to use the console.</span></span> <span data-ttu-id="a57cf-130">Um dieses Problem zu vermeiden, legen Sie die CREATE_NEW_CONSOLE-Flag in der `dwCreationFlags` Parameter.</span><span class="sxs-lookup"><span data-stu-id="a57cf-130">To avoid this problem, set the CREATE_NEW_CONSOLE flag in the `dwCreationFlags` parameter.</span></span>  
  
 <span data-ttu-id="a57cf-131">Interop-Debuggen wird auf Win9x und nicht X86 Plattformen wie z. B. IA-64-basierten und AMD64-basierten Plattformen nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a57cf-131">Interop debugging is not supported on Win9x and non-x86 platforms such as IA-64-based and AMD64-based platforms.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a57cf-132">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a57cf-132">Requirements</span></span>  
 <span data-ttu-id="a57cf-133">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a57cf-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a57cf-134">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a57cf-134">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a57cf-135">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a57cf-135">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a57cf-136">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a57cf-136">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a57cf-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a57cf-137">See Also</span></span>  
 [<span data-ttu-id="a57cf-138">ICorDebug-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a57cf-138">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
