---
title: ICorDebug::CreateProcess-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 16e45f3bad92914ce8c7fb0044534789a7a28b2e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugcreateprocess-method"></a>ICorDebug::CreateProcess-Methode
Startet einen Prozess und seine primäre Thread unter der Kontrolle des Debuggers.  
  
## <a name="syntax"></a>Syntax  
  
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
  
#### <a name="parameters"></a>Parameter  
 `lpApplicationName`  
 [in] Ein Zeiger auf eine auf Null endende Zeichenfolge, die angibt, das Modul der gestartete Prozess ausgeführt werden soll. Das Modul wird im Sicherheitskontext des aufrufenden Prozesses ausgeführt.  
  
 `lpCommandLine`  
 [in] Ein Zeiger auf eine auf Null endende Zeichenfolge, die angibt, die Befehlszeile der gestartete Prozess ausgeführt werden soll. Der Anwendungsname (z. B. "SomeApp.exe") muss das erste Argument.  
  
 `lpProcessAttributes`  
 [in] Zeiger auf eine Win32- `SECURITY_ATTRIBUTES` -Struktur, die Sicherheitsbeschreibung für den Prozess angibt. Wenn `lpProcessAttributes` ist null, ruft der Prozess eine standardsicherheitsbeschreibung.  
  
 `lpThreadAttributes`  
 [in] Zeiger auf eine Win32- `SECURITY_ATTRIBUTES` -Struktur, die Sicherheitsbeschreibung für den primären Thread des Prozesses angibt. Wenn `lpThreadAttributes` ist null, der Thread Ruft eine standardsicherheitsbeschreibung.  
  
 `bInheritHandles`  
 [in] Legen Sie auf `true` , um anzugeben, dass jeder vererbbare Handle im aufrufenden Prozess, von der gestartete Prozess geerbt wird oder `false` , um anzugeben, dass die Handles nicht geerbt werden. Die vererbten Handles besitzen den gleichen Wert und Zugriffsrechte wie die ursprünglichen Handles.  
  
 `dwCreationFlags`  
 [in] Eine bitweise Kombination der [Win32-Prozess Erstellung Flags](http://go.microsoft.com/fwlink/?linkid=69981) steuern die Prioritätsklasse und das Verhalten der gestartete Prozess.  
  
 `lpEnvironment`  
 [in] Ein Zeiger auf einen Umgebungsblock für den neuen Prozess.  
  
 `lpCurrentDirectory`  
 [in] Ein Zeiger auf eine auf Null endende Zeichenfolge, die den vollständigen Pfad zum aktuellen Verzeichnis für den Prozess angibt. Wenn dieser Parameter null ist, müssen der neue Prozess die gleichen aktuelle Laufwerk und Verzeichnis als der aufrufende Prozess.  
  
 `lpStartupInfo`  
 [in] Zeiger auf eine Win32- `STARTUPINFOW` -Struktur, Windowstation, Desktop, standard-Handles und die Darstellung des Hauptfensters der gestartete Prozess angibt.  
  
 `lpProcessInformation`  
 [in] Zeiger auf eine Win32- `PROCESS_INFORMATION` Struktur, der angibt, die Identifikationsinformationen über den Prozess gestartet werden.  
  
 `debuggingFlags`  
 [in] Der Wert der CorDebugCreateProcessFlags-Enumeration, die angibt, die Optionen für das Debuggen.  
  
 `ppProcess`  
 [out] Ein Zeiger auf die Adresse eines ICorDebugProcess-Objekts, das den Prozess darstellt.  
  
## <a name="remarks"></a>Hinweise  
 Die Parameter dieser Methode sind identisch mit denen der Win32- `CreateProcess` Methode.  
  
 Legen Sie zum Aktivieren von nicht verwaltetem Debuggen im gemischten Modus `dwCreationFlags` DEBUG_PROCESS & #124; NUR DIESEN PROZESS ZU DEBUGGEN. Wenn Sie nur das verwaltete Debuggen verwenden möchten, sollten Sie diese Flags festlegen.  
  
 Wenn der Debugger als auch den Prozess erforderlich (den angefügten Prozess) debuggt Freigeben einer einzelnen Konsole aus, und wenn Interop-Debuggen verwendet wird, ist es möglich, dass der angefügte Prozess Konsole sperren, und beenden Sie ein Debug-Ereignis. Der Debugger wird dann jeder Versuch, verwenden die Konsole blockiert. Um dieses Problem zu vermeiden, legen Sie die CREATE_NEW_CONSOLE-Flag in der `dwCreationFlags` Parameter.  
  
 Interop-Debuggen wird auf Win9x und nicht X86 Plattformen wie z. B. IA-64-basierten und AMD64-basierten Plattformen nicht unterstützt.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICorDebug-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
