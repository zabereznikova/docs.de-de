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
ms.openlocfilehash: cf7480eaa0fa38651d139a2fa9d533b43dbdce1b
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57496468"
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
  
## <a name="parameters"></a>Parameter  
 `lpApplicationName`  
 [in] Zeiger auf eine auf Null endende Zeichenfolge, die angibt, das Modul der gestartete Prozess ausgeführt werden soll. Das Modul wird im Kontext des aufrufenden Prozesses ausgeführt.  
  
 `lpCommandLine`  
 [in] Zeiger auf eine auf Null endende Zeichenfolge, die angibt, die Befehlszeile der gestartete Prozess ausgeführt werden soll. Der Name der Anwendung (z. B. "SomeApp.exe") muss das erste Argument sein.  
  
 `lpProcessAttributes`  
 [in] Zeiger auf eine Win32- `SECURITY_ATTRIBUTES` -Struktur, die die Sicherheitsbeschreibung für den Prozess angibt. Wenn `lpProcessAttributes` ist null ist, ruft der Prozess eine standardmäßige Sicherheitsbeschreibung.  
  
 `lpThreadAttributes`  
 [in] Zeiger auf eine Win32- `SECURITY_ATTRIBUTES` -Struktur, die die Sicherheitsbeschreibung für den primären Thread des Prozesses angibt. Wenn `lpThreadAttributes` ist null, der Thread Ruft eine standardmäßige Sicherheitsbeschreibung.  
  
 `bInheritHandles`  
 [in] Legen Sie auf `true` um anzugeben, dass jede vererbbar Handle in den aufrufenden Prozess, durch den Prozess gestartet geerbt wird oder `false` , um anzugeben, dass die Handles nicht geerbt werden. Die vererbten Handles besitzen die gleichen Wert und dieselben Zugriffsrechte wie die ursprünglichen Handles.  
  
 `dwCreationFlags`  
 [in] Eine bitweise Kombination der [Win32 Prozesserstellungsflags](https://go.microsoft.com/fwlink/?linkid=69981) , die die Prioritätsklasse und das Verhalten des gestarteten Prozess steuern.  
  
 `lpEnvironment`  
 [in] Zeiger auf eine Umgebungsblock für den neuen Prozess.  
  
 `lpCurrentDirectory`  
 [in] Zeiger auf eine auf Null endende Zeichenfolge, die den vollständigen Pfad zum aktuellen Verzeichnis für den Prozess angibt. Wenn dieser Parameter null ist, wird der neue Prozess das gleiche aktuelle Laufwerk und Verzeichnis wie der aufrufende Prozess haben.  
  
 `lpStartupInfo`  
 [in] Zeiger auf eine Win32- `STARTUPINFOW` Struktur, die der Windowstation, Desktop, standard-Handles und der Darstellung des Hauptfensters der gestartete Prozess angibt.  
  
 `lpProcessInformation`  
 [in] Zeiger auf eine Win32- `PROCESS_INFORMATION` Struktur, die erforderlichen Informationen zu den zu startenden Prozess angibt.  
  
 `debuggingFlags`  
 [in] Der Wert, die angibt, die Debugoptionen CorDebugCreateProcessFlags-Enumeration.  
  
 `ppProcess`  
 [out] Ein Zeiger auf die Adresse des ein ICorDebugProcess-Objekt, das den Prozess darstellt.  
  
## <a name="remarks"></a>Hinweise  
 Die Parameter dieser Methode sind identisch mit denen der Win32- `CreateProcess` Methode.  
  
 Legen Sie zum Aktivieren von nicht verwaltetem Debuggen im gemischten Modus `dwCreationFlags` auf DEBUG_PROCESS &#124; nur diesen Prozess debuggen. Wenn Sie nur verwaltete Debuggen verwenden möchten, legen Sie diese Flags nicht.  
  
 Wenn der Debugger und der Prozess debuggt (den angefügten Prozess) gemeinsam eine Konsole, und wenn interop-Debuggen verwendet wird, es ist möglich, dass der angefügte Prozess Konsole sperren und ein Debug-Ereignis beenden. Der Debugger wird dann jeder Versuch, verwenden Sie die Konsole blockiert. Um dieses Problem zu vermeiden, legen Sie die CREATE_NEW_CONSOLE-Flag in der `dwCreationFlags` Parameter.  
  
 Interop-Debuggen wird auf Win9x und nicht-X86 Plattformen wie z. B. IA-64- und AMD64-basierten Plattformen nicht unterstützt.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [ICorDebug-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
