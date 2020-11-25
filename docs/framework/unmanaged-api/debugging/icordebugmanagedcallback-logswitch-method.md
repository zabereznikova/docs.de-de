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
ms.openlocfilehash: db6ccd63bbeadd7dcff1c7f8491b59017d431d12
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720697"
---
# <a name="icordebugmanagedcallbacklogswitch-method"></a>ICorDebugManagedCallback::LogSwitch-Methode

Benachrichtigt den Debugger, dass ein von Common Language Runtime (CLR) verwalteter Thread eine Methode in der-Klasse aufgerufen hat, <xref:System.Diagnostics.Switch> um einen Debug/Tracing-Switch zu erstellen, zu ändern oder zu löschen.  
  
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
 in Ein Wert der [LogSwitchCallReason](logswitchcallreason-enumeration.md) -Enumeration, der den Vorgang angibt, der für den Debugger-oder Ablauf Verfolgungs Schalter ausgeführt wird.  
  
 `pLogSwitchName`  
 in Ein Zeiger auf den Namen des Schalters für Debugging/Ablauf Verfolgung.  
  
 `pParentName`  
 in Ein Zeiger auf den Namen des übergeordneten Elements des Schalters für Debuggen/Ablauf Verfolgung.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorDebugManagedCallback-Schnittstelle](icordebugmanagedcallback-interface.md)
