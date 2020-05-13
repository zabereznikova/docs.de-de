---
title: ICorDebugRemote-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugRemote
api_location:
- CorDebug.dll
api_type:
- COM
f1_keywords:
- ICorDebugRemote
helpviewer_keywords:
- ICorDebugRemote interface [.NET Framework debugging]
ms.assetid: 53d073c6-fa02-40d2-82e1-b9452bb6abaa
topic_type:
- apiref
ms.openlocfilehash: ef11aa48f679592126f736c2877c697f02cb5e62
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379249"
---
# <a name="icordebugremote-interface"></a>ICorDebugRemote-Schnittstelle
Bietet die Möglichkeit, einen verwalteten Debugger an einen Remotezielprozess anzufügen oder dort zu starten.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
interface ICorDebugRemote : IUnknown  
{  
    HRESULT CreateProcessEx  
      (  
      [in] ICorDebugRemoteTarget *     pRemoteTarget,  
      [in] LPCWSTR                     lpApplicationName,  
      [in] LPWSTR                      lpCommandLine,  
      [in] LPSECURITY_ATTRIBUTES       lpProcessAttributes,  
      [in] LPSECURITY_ATTRIBUTES       lpThreadAttributes,  
      [in] BOOL                        bInheritHandles,  
      [in] DWORD                       dwCreationFlags,  
      [in] PVOID                       lpEnvironment,  
      [in] LPCWSTR                     lpCurrentDirectory,  
      [in] LPSTARTUPINFOW              lpStartupInfo,  
      [in] LPPROCESS_INFORMATION       lpProcessInformation,  
      [in] CorDebugCreateProcessFlags  debuggingFlags,  
      [out] ICorDebugProcess **        ppProcess  
      );  
  
    HRESULT DebugActiveProcessEx  
      (  
      [in] ICorDebugRemoteTarget *   pRemoteTarget,  
      [in] DWORD                     dwProcessId,  
      [in] BOOL                      fWin32Attach,  
      [out] ICorDebugProcess **      ppProcess  
      );  
};  
```  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[ICorDebugRemote::CreateProcessEx-Methode](icordebugremote-createprocessex-method.md)|Erstellt einen Prozess auf einem Remote Computer für verwaltetes Debuggen.|  
|[ICorDebugRemote::DebugActiveProcessEx-Methode](icordebugremote-debugactiveprocessex-method.md)|Startet einen Prozess auf einem Remote Computer unter dem Debugger.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Funktion wird zurzeit nur für das Debuggen eines Silverlight-basierten Anwendungs Ziels unterstützt, das auf einem Macintosh-Remote Computer ausgeführt wird.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** 4,5, 4, 3,5 SP1  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugRemoteTarget-Schnittstelle](icordebugremotetarget-interface.md)
- [ICorDebug-Schnittstelle](icordebug-interface.md)

- [Debugschnittstellen](debugging-interfaces.md)
