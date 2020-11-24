---
title: ICorDebugManagedCallback::LogMessage-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.LogMessage
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::LogMessage
helpviewer_keywords:
- ICorDebugManagedCallback::LogMessage method [.NET Framework debugging]
- LogMessage method [.NET Framework debugging]
ms.assetid: d218554a-bf42-4d88-833d-ede30de67a53
topic_type:
- apiref
ms.openlocfilehash: 92b2a7f7f1dd98f0d847119a6431e3816c16d5da
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679571"
---
# <a name="icordebugmanagedcallbacklogmessage-method"></a>ICorDebugManagedCallback::LogMessage-Methode

Benachrichtigt den Debugger, dass ein von Common Language Runtime (CLR) verwalteter Thread eine Methode in der-Klasse aufgerufen hat <xref:System.Diagnostics.EventLog> , um ein Ereignis zu protokollieren.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT LogMessage (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] LONG                 lLevel,  
    [in] WCHAR               *pLogSwitchName,  
    [in] WCHAR               *pMessage  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `pAppDomain`  
 in Ein Zeiger auf ein ICorDebugAppDomain-Objekt, das die Anwendungsdomäne darstellt, die den verwalteten Thread enthält, der das Ereignis protokolliert hat.  
  
 `pThread`  
 in Ein Zeiger auf ein ICorDebugThread-Objekt, das den verwalteten Thread darstellt.  
  
 `lLevel`  
 in Ein Wert der [logginglevelenumum](logginglevelenum-enumeration.md) -Enumeration, der den Schweregrad der beschreibenden Meldung angibt, die in das Ereignisprotokoll geschrieben wurde.  
  
 `pLogSwitchName`  
 in Ein Zeiger auf den Namen des Ablaufverfolgungs-Schalters.  
  
 `pMessage`  
 in Ein Zeiger auf die Meldung, die in das Ereignisprotokoll geschrieben wurde.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorDebugManagedCallback-Schnittstelle](icordebugmanagedcallback-interface.md)
