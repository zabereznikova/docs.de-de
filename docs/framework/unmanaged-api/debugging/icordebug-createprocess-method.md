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
ms.openlocfilehash: b9ae2b36bff9b4a6c048a8de99fa7d09350b1401
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2020
ms.locfileid: "82859712"
---
# <a name="icordebugcreateprocess-method"></a>ICorDebug::CreateProcess-Methode
Startet einen Prozess und seinen primären Thread unter der Kontrolle des Debuggers.  
  
## <a name="syntax"></a>Syntax  
  
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
  
## <a name="parameters"></a>Parameter  
 `lpApplicationName`  
 in Zeiger auf eine auf NULL endende Zeichenfolge, die das Modul angibt, das vom gestarteten Prozess ausgeführt werden soll. Das Modul wird im Sicherheitskontext des aufrufenden Prozesses ausgeführt.  
  
 `lpCommandLine`  
 in Zeiger auf eine auf NULL endende Zeichenfolge, die die Befehlszeile angibt, die vom gestarteten Prozess ausgeführt werden soll. Der Anwendungsname (z. b. "someapp. exe") muss das erste Argument sein.  
  
 `lpProcessAttributes`  
 in Ein Zeiger auf eine `SECURITY_ATTRIBUTES` Win32--Struktur, die die Sicherheits Beschreibung für den Prozess angibt. Wenn `lpProcessAttributes` NULL ist, erhält der Prozess eine Standard Sicherheits Beschreibung.  
  
 `lpThreadAttributes`  
 in Ein Zeiger auf eine `SECURITY_ATTRIBUTES` Win32--Struktur, die die Sicherheits Beschreibung für den primären Thread des Prozesses angibt. Wenn `lpThreadAttributes` NULL ist, erhält der Thread eine Standard Sicherheits Beschreibung.  
  
 `bInheritHandles`  
 in Legen Sie `true` auf fest, um anzugeben, dass jedes vererbbare Handle im aufrufenden Prozess vom gestarteten Prozess `false` geerbt wird, oder, um anzugeben, dass die Handles nicht vererbt werden. Die geerbten Handles haben den gleichen Wert und die gleichen Zugriffsrechte wie die ursprünglichen Handles.  
  
 `dwCreationFlags`  
 in Eine bitweise Kombination der [Win32-Prozesserstellungsflags](/windows/win32/procthread/process-creation-flags) , die die Prioritäts Klasse und das Verhalten des gestarteten Prozesses steuern.  
  
 `lpEnvironment`  
 in Zeiger auf einen Umgebungsblock für den neuen Prozess.  
  
 `lpCurrentDirectory`  
 in Ein Zeiger auf eine mit NULL endenden Zeichenfolge, die den vollständigen Pfad zum aktuellen Verzeichnis für den Prozess angibt. Wenn dieser Parameter NULL ist, weist der neue Prozess dasselbe aktuelle Laufwerk und Verzeichnis wie der aufrufende Prozess auf.  
  
 `lpStartupInfo`  
 in Ein Zeiger auf eine `STARTUPINFOW` Win32-Struktur, die die Fenster Station, den Desktop, die Standard Handles und die Darstellung des Hauptfensters für den gestarteten Prozess angibt.  
  
 `lpProcessInformation`  
 in Ein Zeiger auf eine `PROCESS_INFORMATION` Win32-Struktur, die die Identifikationsinformationen zum zu startenden Prozess angibt.  
  
 `debuggingFlags`  
 in Ein Wert der cordebugkreateprocessflags-Enumeration, der die Debugoptionen angibt.  
  
 `ppProcess`  
 vorgenommen Ein Zeiger auf die Adresse eines ICorDebugProcess-Objekts, das den Prozess darstellt.  
  
## <a name="remarks"></a>Hinweise  
 Die Parameter dieser Methode sind identisch mit denen der Win32 `CreateProcess` -Methode.  
  
 Um das nicht verwaltete Debuggen im gemischten Modus `dwCreationFlags` zu aktivieren, legen Sie auf DEBUG_PROCESS &#124; DEBUG_ONLY_THIS_PROCESS fest. Wenn Sie nur verwaltetes Debuggen verwenden möchten, legen Sie diese Flags nicht fest.  
  
 Wenn der Debugger und der zu debuggende Prozess (der angefügte Prozess) eine einzelne Konsole gemeinsam verwenden und das Interop-Debuggen verwendet wird, ist es möglich, dass der angefügte Prozess Konsolen Sperren aufrechterhalten und bei einem Debugereignis angehalten wird. Der Debugger blockiert dann den Versuch, die Konsole zu verwenden. Um dieses Problem zu vermeiden, legen Sie das CREATE_NEW_CONSOLE- `dwCreationFlags` Flag im-Parameter fest.  
  
 Interop-Debuggen wird auf Win9x-und nicht-x86-Plattformen wie IA-64-basierten und AMD64-basierten Plattformen nicht unterstützt.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen:

- [ICorDebug-Schnittstelle](icordebug-interface.md)
