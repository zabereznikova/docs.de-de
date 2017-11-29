---
title: ICorDebugStackWalk::SetContext-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugStackWalk.SetContext Method
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugStackWalk::SetContext
helpviewer_keywords:
- SetContext method [.NET Framework debugging]
- ICorDebugStackWalk::SetContext method [.NET Framework debugging]
ms.assetid: bac0b156-31a3-4e7f-be4d-ab21789c81f1
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 374092c500d4263a172219c38cbc1b2f0ce293a8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugstackwalksetcontext-method"></a>ICorDebugStackWalk::SetContext-Methode
Legt die [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) aktuellen Kontext des Objekts, um einen gültigen Kontext für den Thread.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT SetContext([in] CorDebugSetContextFlag flag,  
                   [in] ULONG32 contextSize,  
                   [in, size_is(contextSize)] BYTE context[]);  
```  
  
#### <a name="parameters"></a>Parameter  
 `flag`  
 [in] Ein [CorDebugSetContextFlag](../../../../docs/framework/unmanaged-api/debugging/cordebugsetcontextflag-enumeration.md) Flag, das angibt, ob der Kontext aus dem aktiven Frame auf dem Stapel oder ein Kontext abgerufen werden, durch das Entladen des Stapels.  
  
 `contextSize`  
 [in] Die Größe des reservierten der `CONTEXT` Puffer.  
  
 `context`  
 [in] Die `CONTEXT` Puffer.  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|Die `ICorDebugStackWalk` der Objektkontext wurde erfolgreich festgelegt.|  
|E_FAIL|Die `ICorDebugStackWalk` der Objektkontext wurde nicht festgelegt.|  
|E_INVALIDARG|Der Kontext ist null.|  
|HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)|Der Kontextpuffer ist zu klein.|  
  
## <a name="exceptions"></a>Ausnahmen  
  
## <a name="remarks"></a>Hinweise  
 Diese Methode wird der aktuelle Kontext des Threads nicht verändert.  
  
 Festlegen des aktuellen Kontexts auf einen ungültigen Kontext kann zu unvorhersehbaren Ergebnissen aus der Stapeldurchlauf führen.  
  
 Sie können eine genaue bitweise Kopie dieses Kontexts abrufen, indem Sie direkt aufrufen der [ICorDebugStackWalk:: GetContext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md) Methode.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Debugschnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [Debuggen](../../../../docs/framework/unmanaged-api/debugging/index.md)
