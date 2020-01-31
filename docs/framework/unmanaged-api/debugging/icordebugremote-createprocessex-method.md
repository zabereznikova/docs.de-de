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
ms.openlocfilehash: cfec84483d387630623f77c176c668171303dd0f
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791990"
---
# <a name="icordebugremotecreateprocessex-method"></a>ICorDebugRemote::CreateProcessEx-Methode
Startet einen Prozess auf einem Remote Computer unter dem Debugger.  
  
## <a name="syntax"></a>Syntax  
  
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
  
## <a name="parameters"></a>Parameters  
 `pRemoteTarget`  
 [in] Zeiger auf eine [ICorDebugRemoteTarget-Schnittstelle](icordebugremotetarget-interface.md). Wird verwendet, um den Remote Computer zu ermitteln, auf dem der Prozess gestartet wird.  
  
 `lpApplicationName`  
 in Zeiger auf eine auf NULL endende Zeichenfolge, die das Modul angibt, das vom gestarteten Prozess ausgeführt werden soll. Das Modul wird im Sicherheitskontext des aufrufenden Prozesses ausgeführt.  
  
 `lpCommandLine`  
 in Zeiger auf eine auf NULL endende Zeichenfolge, die die Befehlszeile angibt, die vom gestarteten Prozess ausgeführt werden soll.  
  
 `lpProcessAttributes`  
 in Nicht für Remote Debuggen verwendet.  
  
 `lpThreadAttributes`  
 in Nicht für Remote Debuggen verwendet.  
  
 `bInheritHandles`  
 in Nicht für Remote Debuggen verwendet.  
  
 `dwCreationFlags`  
 in Nicht für Remote Debuggen verwendet.  
  
 `lpEnvironment`  
 in Zeiger auf einen Umgebungsblock für den neuen Prozess.  
  
 `lpCurrentDirectory`  
 in Ein Zeiger auf eine mit NULL endenden Zeichenfolge, die den vollständigen Pfad zum aktuellen Verzeichnis für den Prozess angibt. Wenn dieser Parameter NULL ist, weist der neue Prozess dasselbe aktuelle Laufwerk und Verzeichnis wie der aufrufende Prozess auf.  
  
 `lpStartupInfo`  
 in Nicht für Remote Debuggen verwendet.  
  
 `lpProcessInformation`  
 in Nicht für Remote Debuggen verwendet.  
  
 `debuggingFlags`  
 in Nicht für Remote Debuggen verwendet.  
  
 `ppProcess`  
 vorgenommen Ein Zeiger auf die Adresse eines ICorDebugProcess-Schnittstellen Objekts, das den Prozess darstellt.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK  
 Wurde erfolgreich gestartet den Prozess auf dem Remotecomputer und zurückgegebenen ein "ICorDebugProcess-Schnittstelle" für das Debuggen.  
  
 E_FAIL (oder andere E_-Rückgabecodes)  
 Starten Sie den Prozess auf dem Remotecomputer und Zurückgeben von "ICorDebugProcess-Schnittstelle" für das Debuggen nicht möglich.  
  
## <a name="remarks"></a>Hinweise  
 Das Debuggen im gemischten Modus wird in Silverlight nicht unterstützt.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cordebug. idl  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** 4,5, 4, 3,5 SP1  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugRemote-Schnittstelle](icordebugremote-interface.md)
- [ICorDebug-Schnittstelle](icordebug-interface.md)

- [Debuggen von Schnittstellen](debugging-interfaces.md)
