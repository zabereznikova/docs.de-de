---
title: ICorDebugStackWalk::GetContext-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugStackWalk.GetContext Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStackWalk::GetContext
helpviewer_keywords:
- GetContext method, ICorDebugStackWalk interface [.NET Framework debugging]
- ICorDebugStackWalk::GetContext method [.NET Framework debugging]
ms.assetid: 081d1c95-152b-4797-8552-18453eb7b14b
topic_type:
- apiref
ms.openlocfilehash: 743b0c8016ca5c0401046166a770d857215429a3
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379223"
---
# <a name="icordebugstackwalkgetcontext-method"></a>ICorDebugStackWalk::GetContext-Methode
Gibt den Kontext für den aktuellen Frame im [ICorDebugStackWalk](icordebugstackwalk-interface.md) -Objekt zurück.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetContext([in]  ULONG32 contextFlags,  
                   [in]  ULONG32 contextBufSize,  
                   [out] ULONG32* contextSize,  
                   [out, size_is(contextBufSize)] BYTE contextBuf[]);  
```  
  
## <a name="parameters"></a>Parameter  
 `contextFlags`  
 in Flags, die den angeforderten Inhalt des Kontext Puffers angeben (in "Winnt. h" definiert).  
  
 `contextBufSize`  
 in Die zugeordnete Größe des Kontext Puffers.  
  
 `contextSize`  
 vorgenommen Die tatsächliche Größe des Kontexts. Dieser Wert muss kleiner oder gleich der Größe des Kontext Puffers sein.  
  
 `contextBuf`  
 vorgenommen Der Kontext Puffer.  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.  
  
|HRESULT|BESCHREIBUNG|  
|-------------|-----------------|  
|S_OK|Der Kontext für den aktuellen Frame wurde erfolgreich zurückgegeben.|  
|E_FAIL|Der Kontext konnte nicht zurückgegeben werden.|  
|HRESULT_FROM_WIN32 (ERROR_INSUFFICIENT Puffer)|Der Kontext Puffer ist zu klein.|  
|CORDBG_E_PAST_END_OF_STACK|Der Frame Zeiger befindet sich bereits am Ende des Stapels. Daher können keine weiteren Frames aufgerufen werden.|  
  
## <a name="exceptions"></a>Ausnahmen  
  
## <a name="remarks"></a>Hinweise  
 Da bei der Entwicklung nur eine Teilmenge der Register wieder hergestellt wird, z. b. nicht flüchtige Register, stimmt der Kontext möglicherweise nicht genau mit dem Registrierungs Zustand zum Zeitpunkt des Aufrufes überein.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debugschnittstellen](debugging-interfaces.md)
- [Debuggen](index.md)
