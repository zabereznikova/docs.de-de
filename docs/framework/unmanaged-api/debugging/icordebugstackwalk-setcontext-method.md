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
ms.openlocfilehash: 896e797acc76e8d8034bd964e488317a62eed97b
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378777"
---
# <a name="icordebugstackwalksetcontext-method"></a>ICorDebugStackWalk::SetContext-Methode
Legt den aktuellen Kontext des [ICorDebugStackWalk](icordebugstackwalk-interface.md) -Objekts auf einen gültigen Kontext für den Thread fest.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT SetContext([in] CorDebugSetContextFlag flag,  
                   [in] ULONG32 contextSize,  
                   [in, size_is(contextSize)] BYTE context[]);  
```  
  
## <a name="parameters"></a>Parameter  
 `flag`  
 in Ein [CorDebugSetContextFlag](cordebugsetcontextflag-enumeration.md) -Flag, das angibt, ob der Kontext vom aktiven Frame im Stapel stammt, oder ein Kontext, der durch das Entwickeln des Stapels abgerufen wird.  
  
 `contextSize`  
 in Die zugeordnete Größe des `CONTEXT` Puffers.  
  
 `context`  
 in Der `CONTEXT` Puffer.  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.  
  
|HRESULT|BESCHREIBUNG|  
|-------------|-----------------|  
|S_OK|Der `ICorDebugStackWalk` Kontext des-Objekts wurde erfolgreich festgelegt.|  
|E_FAIL|Der `ICorDebugStackWalk` Kontext des Objekts wurde nicht festgelegt.|  
|E_INVALIDARG|Der Kontext ist null.|  
|HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)|Der Kontext Puffer ist zu klein.|  
  
## <a name="exceptions"></a>Ausnahmen  
  
## <a name="remarks"></a>Hinweise  
 Diese Methode ändert nicht den aktuellen Kontext des Threads.  
  
 Wenn Sie den aktuellen Kontext auf einen ungültigen Kontext festlegen, kann dies zu unvorhersehbaren Ergebnissen des Stapel Spaziergängers führen.  
  
 Sie können eine genaue bitweise Kopie dieses Kontexts abrufen, indem Sie direkt die [ICorDebugStackWalk:: GetContext](icordebugstackwalk-getcontext-method.md) -Methode aufrufen.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debugschnittstellen](debugging-interfaces.md)
- [Debuggen](index.md)
