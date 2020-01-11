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
ms.openlocfilehash: a69fb861f7c2671a5c26245aa544ee99bcbdb56b
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901014"
---
# <a name="icordebugcreateprocess-method"></a><span data-ttu-id="b0f9a-102">ICorDebug::CreateProcess-Methode</span><span class="sxs-lookup"><span data-stu-id="b0f9a-102">ICorDebug::CreateProcess Method</span></span>
<span data-ttu-id="b0f9a-103">Startet einen Prozess und seinen primären Thread unter der Kontrolle des Debuggers.</span><span class="sxs-lookup"><span data-stu-id="b0f9a-103">Launches a process and its primary thread under the control of the debugger.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0f9a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b0f9a-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="b0f9a-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="b0f9a-105">Parameters</span></span>  
 `lpApplicationName`  
 <span data-ttu-id="b0f9a-106">in Zeiger auf eine auf NULL endende Zeichenfolge, die das Modul angibt, das vom gestarteten Prozess ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="b0f9a-106">[in] Pointer to a null-terminated string that specifies the module to be executed by the launched process.</span></span> <span data-ttu-id="b0f9a-107">Das Modul wird im Sicherheitskontext des aufrufenden Prozesses ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="b0f9a-107">The module is executed in the security context of the calling process.</span></span>  
  
 `lpCommandLine`  
 <span data-ttu-id="b0f9a-108">in Zeiger auf eine auf NULL endende Zeichenfolge, die die Befehlszeile angibt, die vom gestarteten Prozess ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="b0f9a-108">[in] Pointer to a null-terminated string that specifies the command line to be executed by the launched process.</span></span> <span data-ttu-id="b0f9a-109">Der Anwendungsname (z. b. "someapp. exe") muss das erste Argument sein.</span><span class="sxs-lookup"><span data-stu-id="b0f9a-109">The application name (for example, "SomeApp.exe") must be the first argument.</span></span>  
  
 `lpProcessAttributes`  
 <span data-ttu-id="b0f9a-110">in Ein Zeiger auf eine Win32-`SECURITY_ATTRIBUTES`-Struktur, die die Sicherheits Beschreibung für den Prozess angibt.</span><span class="sxs-lookup"><span data-stu-id="b0f9a-110">[in] Pointer to a Win32 `SECURITY_ATTRIBUTES` structure that specifies the security descriptor for the process.</span></span> <span data-ttu-id="b0f9a-111">Wenn `lpProcessAttributes` NULL ist, erhält der Prozess eine Standard Sicherheits Beschreibung.</span><span class="sxs-lookup"><span data-stu-id="b0f9a-111">If `lpProcessAttributes` is null, the process gets a default security descriptor.</span></span>  
  
 `lpThreadAttributes`  
 <span data-ttu-id="b0f9a-112">in Ein Zeiger auf eine Win32-`SECURITY_ATTRIBUTES`-Struktur, die die Sicherheits Beschreibung für den primären Thread des Prozesses angibt.</span><span class="sxs-lookup"><span data-stu-id="b0f9a-112">[in] Pointer to a Win32 `SECURITY_ATTRIBUTES` structure that specifies the security descriptor for the primary thread of the process.</span></span> <span data-ttu-id="b0f9a-113">Wenn `lpThreadAttributes` NULL ist, erhält der Thread eine Standard Sicherheits Beschreibung.</span><span class="sxs-lookup"><span data-stu-id="b0f9a-113">If `lpThreadAttributes` is null, the thread gets a default security descriptor.</span></span>  
  
 `bInheritHandles`  
 <span data-ttu-id="b0f9a-114">in Legen Sie diese Einstellung auf `true` fest, um anzugeben, dass jedes vererbbare Handle im aufrufenden Prozess vom gestarteten Prozess geerbt wird, oder `false`, um anzugeben, dass die Handles nicht vererbt werden.</span><span class="sxs-lookup"><span data-stu-id="b0f9a-114">[in] Set to `true` to indicate that each inheritable handle in the calling process is inherited by the launched process, or `false` to indicate that the handles are not inherited.</span></span> <span data-ttu-id="b0f9a-115">Die geerbten Handles haben den gleichen Wert und die gleichen Zugriffsrechte wie die ursprünglichen Handles.</span><span class="sxs-lookup"><span data-stu-id="b0f9a-115">The inherited handles have the same value and access rights as the original handles.</span></span>  
  
 `dwCreationFlags`  
 <span data-ttu-id="b0f9a-116">in Eine bitweise Kombination der [Win32-Prozesserstellungsflags](/windows/win32/procthread/process-creation-flags) , die die Prioritäts Klasse und das Verhalten des gestarteten Prozesses steuern.</span><span class="sxs-lookup"><span data-stu-id="b0f9a-116">[in] A bitwise combination of the [Win32 Process Creation Flags](/windows/win32/procthread/process-creation-flags) that control the priority class and the behavior of the launched process.</span></span>  
  
 `lpEnvironment`  
 <span data-ttu-id="b0f9a-117">in Zeiger auf einen Umgebungsblock für den neuen Prozess.</span><span class="sxs-lookup"><span data-stu-id="b0f9a-117">[in] Pointer to an environment block for the new process.</span></span>  
  
 `lpCurrentDirectory`  
 <span data-ttu-id="b0f9a-118">in Ein Zeiger auf eine mit NULL endenden Zeichenfolge, die den vollständigen Pfad zum aktuellen Verzeichnis für den Prozess angibt.</span><span class="sxs-lookup"><span data-stu-id="b0f9a-118">[in] Pointer to a null-terminated string that specifies the full path to the current directory for the process.</span></span> <span data-ttu-id="b0f9a-119">Wenn dieser Parameter NULL ist, weist der neue Prozess dasselbe aktuelle Laufwerk und Verzeichnis wie der aufrufende Prozess auf.</span><span class="sxs-lookup"><span data-stu-id="b0f9a-119">If this parameter is null, the new process will have the same current drive and directory as the calling process.</span></span>  
  
 `lpStartupInfo`  
 <span data-ttu-id="b0f9a-120">in Ein Zeiger auf eine Win32-`STARTUPINFOW`-Struktur, die die Fenster Station, den Desktop, die Standard Handles und die Darstellung des Hauptfensters für den gestarteten Prozess angibt.</span><span class="sxs-lookup"><span data-stu-id="b0f9a-120">[in] Pointer to a Win32 `STARTUPINFOW` structure that specifies the window station, desktop, standard handles, and appearance of the main window for the launched process.</span></span>  
  
 `lpProcessInformation`  
 <span data-ttu-id="b0f9a-121">in Ein Zeiger auf eine Win32-`PROCESS_INFORMATION`-Struktur, die die Identifikationsinformationen über den Prozess angibt, der gestartet werden soll.</span><span class="sxs-lookup"><span data-stu-id="b0f9a-121">[in] Pointer to a Win32 `PROCESS_INFORMATION` structure that specifies the identification information about the process to be launched.</span></span>  
  
 `debuggingFlags`  
 <span data-ttu-id="b0f9a-122">in Ein Wert der cordebugkreateprocessflags-Enumeration, der die Debugoptionen angibt.</span><span class="sxs-lookup"><span data-stu-id="b0f9a-122">[in] A value of the CorDebugCreateProcessFlags enumeration that specifies the debugging options.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="b0f9a-123">vorgenommen Ein Zeiger auf die Adresse eines ICorDebugProcess-Objekts, das den Prozess darstellt.</span><span class="sxs-lookup"><span data-stu-id="b0f9a-123">[out] A pointer to the address of a ICorDebugProcess object that represents the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b0f9a-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b0f9a-124">Remarks</span></span>  
 <span data-ttu-id="b0f9a-125">Die Parameter dieser Methode sind identisch mit denen der Win32-`CreateProcess`-Methode.</span><span class="sxs-lookup"><span data-stu-id="b0f9a-125">The parameters of this method are the same as those of the Win32 `CreateProcess` method.</span></span>  
  
 <span data-ttu-id="b0f9a-126">Um das nicht verwaltete Debuggen im gemischten Modus zu aktivieren, &#124; legen Sie `dwCreationFlags` auf DEBUG_PROCESS DEBUG_ONLY_THIS_PROCESS fest.</span><span class="sxs-lookup"><span data-stu-id="b0f9a-126">To enable unmanaged mixed-mode debugging, set `dwCreationFlags` to DEBUG_PROCESS &#124; DEBUG_ONLY_THIS_PROCESS.</span></span> <span data-ttu-id="b0f9a-127">Wenn Sie nur verwaltetes Debuggen verwenden möchten, legen Sie diese Flags nicht fest.</span><span class="sxs-lookup"><span data-stu-id="b0f9a-127">If you want to use only managed debugging, do not set these flags.</span></span>  
  
 <span data-ttu-id="b0f9a-128">Wenn der Debugger und der zu debuggende Prozess (der angefügte Prozess) eine einzelne Konsole gemeinsam verwenden und das Interop-Debuggen verwendet wird, ist es möglich, dass der angefügte Prozess Konsolen Sperren aufrechterhalten und bei einem Debugereignis angehalten wird.</span><span class="sxs-lookup"><span data-stu-id="b0f9a-128">If the debugger and the process to be debugged (the attached process) share a single console, and if interop debugging is used, it is possible for the attached process to hold console locks and stop at a debug event.</span></span> <span data-ttu-id="b0f9a-129">Der Debugger blockiert dann den Versuch, die Konsole zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="b0f9a-129">The debugger will then block any attempt to use the console.</span></span> <span data-ttu-id="b0f9a-130">Um dieses Problem zu vermeiden, legen Sie das CREATE_NEW_CONSOLE-Flag im `dwCreationFlags`-Parameter fest.</span><span class="sxs-lookup"><span data-stu-id="b0f9a-130">To avoid this problem, set the CREATE_NEW_CONSOLE flag in the `dwCreationFlags` parameter.</span></span>  
  
 <span data-ttu-id="b0f9a-131">Interop-Debuggen wird auf Win9x-und nicht-x86-Plattformen wie IA-64-basierten und AMD64-basierten Plattformen nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="b0f9a-131">Interop debugging is not supported on Win9x and non-x86 platforms such as IA-64-based and AMD64-based platforms.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b0f9a-132">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b0f9a-132">Requirements</span></span>  
 <span data-ttu-id="b0f9a-133">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b0f9a-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b0f9a-134">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b0f9a-134">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b0f9a-135">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b0f9a-135">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b0f9a-136">**.NET Framework Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b0f9a-136">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0f9a-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b0f9a-137">See also</span></span>

- [<span data-ttu-id="b0f9a-138">ICorDebug-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b0f9a-138">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
