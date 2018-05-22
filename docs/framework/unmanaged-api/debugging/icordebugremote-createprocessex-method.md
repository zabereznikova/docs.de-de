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
# <a name="icordebugremotecreateprocessex-method"></a>ICorDebugRemote::CreateProcessEx-Methode
Startet einen Prozess auf einem Remotecomputer unter dem Debugger.  
  
## <a name="syntax"></a>Syntax  
  
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
  
#### <a name="parameters"></a>Parameter  
 `pRemoteTarget`  
 [in] Zeiger auf eine [ICorDebugRemoteTarget-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md). Verwendet, um den Remotecomputer zu bestimmen, auf dem der Prozess gestartet wird.  
  
 `lpApplicationName`  
 [in] Ein Zeiger auf eine auf Null endende Zeichenfolge, die angibt, das Modul der gestartete Prozess ausgeführt werden soll. Das Modul wird im Sicherheitskontext des aufrufenden Prozesses ausgeführt.  
  
 `lpCommandLine`  
 [in] Ein Zeiger auf eine auf Null endende Zeichenfolge, die angibt, die Befehlszeile der gestartete Prozess ausgeführt werden soll.  
  
 `lpProcessAttributes`  
 [in] Für das Remotedebuggen wird nicht verwendet werden.  
  
 `lpThreadAttributes`  
 [in] Für das Remotedebuggen wird nicht verwendet werden.  
  
 `bInheritHandles`  
 [in] Für das Remotedebuggen wird nicht verwendet werden.  
  
 `dwCreationFlags`  
 [in] Für das Remotedebuggen wird nicht verwendet werden.  
  
 `lpEnvironment`  
 [in] Ein Zeiger auf einen Umgebungsblock für den neuen Prozess.  
  
 `lpCurrentDirectory`  
 [in] Ein Zeiger auf eine auf Null endende Zeichenfolge, die den vollständigen Pfad zum aktuellen Verzeichnis für den Prozess angibt. Wenn dieser Parameter null ist, müssen der neue Prozess die gleichen aktuelle Laufwerk und Verzeichnis als der aufrufende Prozess.  
  
 `lpStartupInfo`  
 [in] Für das Remotedebuggen wird nicht verwendet werden.  
  
 `lpProcessInformation`  
 [in] Für das Remotedebuggen wird nicht verwendet werden.  
  
 `debuggingFlags`  
 [in] Für das Remotedebuggen wird nicht verwendet werden.  
  
 `ppProcess`  
 [out] Ein Zeiger auf die Adresse eines Objekts "ICorDebugProcess-Schnittstelle", das den Prozess darstellt.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK  
 Wurde erfolgreich gestartet den Prozess auf dem Remotecomputer und zurückgegebenen ein "ICorDebugProcess-Schnittstelle" für das Debuggen.  
  
 E_FAIL (oder andere E_-Rückgabecodes)  
 Starten Sie den Prozess auf dem Remotecomputer und Zurückgeben von "ICorDebugProcess-Schnittstelle" für das Debuggen nicht möglich.  
  
## <a name="remarks"></a>Hinweise  
 Debuggen im gemischten Modus ist in Silverlight nicht unterstützt.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** 4.5, 4, 3.5 SP1  
  
## <a name="see-also"></a>Siehe auch  
 [ICorDebugRemote-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugremote-interface.md)  
 [ICorDebug-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)  
    
 [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
