---
title: ICorDebugStackWalk::SetContext-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugStackWalk.SetContext Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStackWalk::SetContext
helpviewer_keywords:
- SetContext method [.NET Framework debugging]
- ICorDebugStackWalk::SetContext method [.NET Framework debugging]
ms.assetid: bac0b156-31a3-4e7f-be4d-ab21789c81f1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d6eb97fc70fec25f4b225c3fd5bad1e780091f7c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67771035"
---
# <a name="icordebugstackwalksetcontext-method"></a>ICorDebugStackWalk::SetContext-Methode
Legt die [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) aktuellen Kontext des Objekts, auf einen gültigen Kontext für den Thread.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT SetContext([in] CorDebugSetContextFlag flag,  
                   [in] ULONG32 contextSize,  
                   [in, size_is(contextSize)] BYTE context[]);  
```  
  
## <a name="parameters"></a>Parameter  
 `flag`  
 [in] Ein [CorDebugSetContextFlag](../../../../docs/framework/unmanaged-api/debugging/cordebugsetcontextflag-enumeration.md) Flag, das angibt, ob der Kontext aus dem aktiven Frame im Stapel ist oder ein Kontext an, die durch das Entladen des Stapels abgerufen.  
  
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
 Diese Methode wird den aktuellen Kontext des Threads nicht geändert werden.  
  
 Festlegen des aktuellen Kontexts auf einen ungültigen Kontext kann zu unvorhersehbaren Ergebnissen aus der Stapeldurchlauf führen.  
  
 Sie können eine genaue bitweise Kopie dieses Kontexts abrufen, indem Sie sofort Aufrufen der [ICorDebugStackWalk:: GetContext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md) Methode.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Debuggen](../../../../docs/framework/unmanaged-api/debugging/index.md)
