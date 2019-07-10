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
ms.openlocfilehash: 5d6220270634dd8e2d15787d717020b8f6f86bb9
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67738332"
---
# <a name="icordebugcreateprocess-method"></a><span data-ttu-id="e193f-102">ICorDebug::CreateProcess-Methode</span><span class="sxs-lookup"><span data-stu-id="e193f-102">ICorDebug::CreateProcess Method</span></span>
<span data-ttu-id="e193f-103">Startet einen Prozess und seine primäre Thread unter der Kontrolle des Debuggers.</span><span class="sxs-lookup"><span data-stu-id="e193f-103">Launches a process and its primary thread under the control of the debugger.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e193f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e193f-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="e193f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e193f-105">Parameters</span></span>  
 `lpApplicationName`  
 <span data-ttu-id="e193f-106">[in] Zeiger auf eine auf Null endende Zeichenfolge, die angibt, das Modul der gestartete Prozess ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="e193f-106">[in] Pointer to a null-terminated string that specifies the module to be executed by the launched process.</span></span> <span data-ttu-id="e193f-107">Das Modul wird im Kontext des aufrufenden Prozesses ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="e193f-107">The module is executed in the security context of the calling process.</span></span>  
  
 `lpCommandLine`  
 <span data-ttu-id="e193f-108">[in] Zeiger auf eine auf Null endende Zeichenfolge, die angibt, die Befehlszeile der gestartete Prozess ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="e193f-108">[in] Pointer to a null-terminated string that specifies the command line to be executed by the launched process.</span></span> <span data-ttu-id="e193f-109">Der Name der Anwendung (z. B. "SomeApp.exe") muss das erste Argument sein.</span><span class="sxs-lookup"><span data-stu-id="e193f-109">The application name (for example, "SomeApp.exe") must be the first argument.</span></span>  
  
 `lpProcessAttributes`  
 <span data-ttu-id="e193f-110">[in] Zeiger auf eine Win32- `SECURITY_ATTRIBUTES` -Struktur, die die Sicherheitsbeschreibung für den Prozess angibt.</span><span class="sxs-lookup"><span data-stu-id="e193f-110">[in] Pointer to a Win32 `SECURITY_ATTRIBUTES` structure that specifies the security descriptor for the process.</span></span> <span data-ttu-id="e193f-111">Wenn `lpProcessAttributes` ist null ist, ruft der Prozess eine standardmäßige Sicherheitsbeschreibung.</span><span class="sxs-lookup"><span data-stu-id="e193f-111">If `lpProcessAttributes` is null, the process gets a default security descriptor.</span></span>  
  
 `lpThreadAttributes`  
 <span data-ttu-id="e193f-112">[in] Zeiger auf eine Win32- `SECURITY_ATTRIBUTES` -Struktur, die die Sicherheitsbeschreibung für den primären Thread des Prozesses angibt.</span><span class="sxs-lookup"><span data-stu-id="e193f-112">[in] Pointer to a Win32 `SECURITY_ATTRIBUTES` structure that specifies the security descriptor for the primary thread of the process.</span></span> <span data-ttu-id="e193f-113">Wenn `lpThreadAttributes` ist null, der Thread Ruft eine standardmäßige Sicherheitsbeschreibung.</span><span class="sxs-lookup"><span data-stu-id="e193f-113">If `lpThreadAttributes` is null, the thread gets a default security descriptor.</span></span>  
  
 `bInheritHandles`  
 <span data-ttu-id="e193f-114">[in] Legen Sie auf `true` um anzugeben, dass jede vererbbar Handle in den aufrufenden Prozess, durch den Prozess gestartet geerbt wird oder `false` , um anzugeben, dass die Handles nicht geerbt werden.</span><span class="sxs-lookup"><span data-stu-id="e193f-114">[in] Set to `true` to indicate that each inheritable handle in the calling process is inherited by the launched process, or `false` to indicate that the handles are not inherited.</span></span> <span data-ttu-id="e193f-115">Die vererbten Handles besitzen die gleichen Wert und dieselben Zugriffsrechte wie die ursprünglichen Handles.</span><span class="sxs-lookup"><span data-stu-id="e193f-115">The inherited handles have the same value and access rights as the original handles.</span></span>  
  
 `dwCreationFlags`  
 <span data-ttu-id="e193f-116">[in] Eine bitweise Kombination der [Win32 Prozesserstellungsflags](https://go.microsoft.com/fwlink/?linkid=69981) , die die Prioritätsklasse und das Verhalten des gestarteten Prozess steuern.</span><span class="sxs-lookup"><span data-stu-id="e193f-116">[in] A bitwise combination of the [Win32 Process Creation Flags](https://go.microsoft.com/fwlink/?linkid=69981) that control the priority class and the behavior of the launched process.</span></span>  
  
 `lpEnvironment`  
 <span data-ttu-id="e193f-117">[in] Zeiger auf eine Umgebungsblock für den neuen Prozess.</span><span class="sxs-lookup"><span data-stu-id="e193f-117">[in] Pointer to an environment block for the new process.</span></span>  
  
 `lpCurrentDirectory`  
 <span data-ttu-id="e193f-118">[in] Zeiger auf eine auf Null endende Zeichenfolge, die den vollständigen Pfad zum aktuellen Verzeichnis für den Prozess angibt.</span><span class="sxs-lookup"><span data-stu-id="e193f-118">[in] Pointer to a null-terminated string that specifies the full path to the current directory for the process.</span></span> <span data-ttu-id="e193f-119">Wenn dieser Parameter null ist, wird der neue Prozess das gleiche aktuelle Laufwerk und Verzeichnis wie der aufrufende Prozess haben.</span><span class="sxs-lookup"><span data-stu-id="e193f-119">If this parameter is null, the new process will have the same current drive and directory as the calling process.</span></span>  
  
 `lpStartupInfo`  
 <span data-ttu-id="e193f-120">[in] Zeiger auf eine Win32- `STARTUPINFOW` Struktur, die der Windowstation, Desktop, standard-Handles und der Darstellung des Hauptfensters der gestartete Prozess angibt.</span><span class="sxs-lookup"><span data-stu-id="e193f-120">[in] Pointer to a Win32 `STARTUPINFOW` structure that specifies the window station, desktop, standard handles, and appearance of the main window for the launched process.</span></span>  
  
 `lpProcessInformation`  
 <span data-ttu-id="e193f-121">[in] Zeiger auf eine Win32- `PROCESS_INFORMATION` Struktur, die erforderlichen Informationen zu den zu startenden Prozess angibt.</span><span class="sxs-lookup"><span data-stu-id="e193f-121">[in] Pointer to a Win32 `PROCESS_INFORMATION` structure that specifies the identification information about the process to be launched.</span></span>  
  
 `debuggingFlags`  
 <span data-ttu-id="e193f-122">[in] Der Wert, die angibt, die Debugoptionen CorDebugCreateProcessFlags-Enumeration.</span><span class="sxs-lookup"><span data-stu-id="e193f-122">[in] A value of the CorDebugCreateProcessFlags enumeration that specifies the debugging options.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="e193f-123">[out] Ein Zeiger auf die Adresse des ein ICorDebugProcess-Objekt, das den Prozess darstellt.</span><span class="sxs-lookup"><span data-stu-id="e193f-123">[out] A pointer to the address of a ICorDebugProcess object that represents the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e193f-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e193f-124">Remarks</span></span>  
 <span data-ttu-id="e193f-125">Die Parameter dieser Methode sind identisch mit denen der Win32- `CreateProcess` Methode.</span><span class="sxs-lookup"><span data-stu-id="e193f-125">The parameters of this method are the same as those of the Win32 `CreateProcess` method.</span></span>  
  
 <span data-ttu-id="e193f-126">Legen Sie zum Aktivieren von nicht verwaltetem Debuggen im gemischten Modus `dwCreationFlags` auf DEBUG_PROCESS &#124; nur diesen Prozess debuggen.</span><span class="sxs-lookup"><span data-stu-id="e193f-126">To enable unmanaged mixed-mode debugging, set `dwCreationFlags` to DEBUG_PROCESS &#124; DEBUG_ONLY_THIS_PROCESS.</span></span> <span data-ttu-id="e193f-127">Wenn Sie nur verwaltete Debuggen verwenden möchten, legen Sie diese Flags nicht.</span><span class="sxs-lookup"><span data-stu-id="e193f-127">If you want to use only managed debugging, do not set these flags.</span></span>  
  
 <span data-ttu-id="e193f-128">Wenn der Debugger und der Prozess debuggt (den angefügten Prozess) gemeinsam eine Konsole, und wenn interop-Debuggen verwendet wird, es ist möglich, dass der angefügte Prozess Konsole sperren und ein Debug-Ereignis beenden.</span><span class="sxs-lookup"><span data-stu-id="e193f-128">If the debugger and the process to be debugged (the attached process) share a single console, and if interop debugging is used, it is possible for the attached process to hold console locks and stop at a debug event.</span></span> <span data-ttu-id="e193f-129">Der Debugger wird dann jeder Versuch, verwenden Sie die Konsole blockiert.</span><span class="sxs-lookup"><span data-stu-id="e193f-129">The debugger will then block any attempt to use the console.</span></span> <span data-ttu-id="e193f-130">Um dieses Problem zu vermeiden, legen Sie die CREATE_NEW_CONSOLE-Flag in der `dwCreationFlags` Parameter.</span><span class="sxs-lookup"><span data-stu-id="e193f-130">To avoid this problem, set the CREATE_NEW_CONSOLE flag in the `dwCreationFlags` parameter.</span></span>  
  
 <span data-ttu-id="e193f-131">Interop-Debuggen wird auf Win9x und nicht-X86 Plattformen wie z. B. IA-64- und AMD64-basierten Plattformen nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e193f-131">Interop debugging is not supported on Win9x and non-x86 platforms such as IA-64-based and AMD64-based platforms.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e193f-132">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e193f-132">Requirements</span></span>  
 <span data-ttu-id="e193f-133">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e193f-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e193f-134">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e193f-134">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e193f-135">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e193f-135">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e193f-136">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e193f-136">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e193f-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e193f-137">See also</span></span>

- [<span data-ttu-id="e193f-138">ICorDebug-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e193f-138">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
