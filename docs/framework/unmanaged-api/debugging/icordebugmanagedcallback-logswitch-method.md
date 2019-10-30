---
title: ICorDebugManagedCallback::LogSwitch-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.LogSwitch
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::LogSwitch
helpviewer_keywords:
- LogSwitch method [.NET Framework debugging]
- ICorDebugManagedCallback::LogSwitch method [.NET Framework debugging]
ms.assetid: 0ac59d27-783f-4a87-b7a8-baa3ccc54582
topic_type:
- apiref
ms.openlocfilehash: a72eabb1b405c67f5603164e56a589a237603d2f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130692"
---
# <a name="icordebugmanagedcallbacklogswitch-method"></a>ICorDebugManagedCallback::LogSwitch-Methode
Benachrichtigt den Debugger, dass ein von Common Language Runtime (CLR) verwalteter Thread eine Methode in der <xref:System.Diagnostics.Switch>-Klasse aufgerufen hat, um einen Debug/Tracing-Switch zu erstellen, zu ändern oder zu löschen.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT LogSwitch (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] LONG                 lLevel,  
    [in] ULONG                ulReason,  
    [in] WCHAR               *pLogSwitchName,  
    [in] WCHAR               *pParentName);  
```  
  
## <a name="parameters"></a>Parameter  
 `PAppDomain`  
 in Ein Zeiger auf ein ICorDebugAppDomain-Objekt, das die Anwendungsdomäne mit dem verwalteten Thread darstellt, der einen Debug/Tracing-Switch erstellt, geändert oder gelöscht hat.  
  
 `pThread`  
 in Ein Zeiger auf ein ICorDebugThread-Objekt, das den verwalteten Thread darstellt.  
  
 `lLevel`  
 in Ein-Wert, der den Schweregrad der beschreibenden Meldung angibt, die in das Ereignisprotokoll geschrieben wurde.  
  
 `ulReason`  
 in Ein Wert der [LogSwitchCallReason](../../../../docs/framework/unmanaged-api/debugging/logswitchcallreason-enumeration.md) -Enumeration, der den Vorgang angibt, der für den Debugger-oder Ablauf Verfolgungs Schalter ausgeführt wird.  
  
 `pLogSwitchName`  
 in Ein Zeiger auf den Namen des Schalters für Debugging/Ablauf Verfolgung.  
  
 `pParentName`  
 in Ein Zeiger auf den Namen des übergeordneten Elements des Schalters für Debuggen/Ablauf Verfolgung.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugManagedCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
