---
title: ICorDebugNativeFrame2::GetStackParameterSize-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame2.GetStackParameterSize Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame2::GetStackParameterSize
helpviewer_keywords:
- ICorDebugNativeFrame2::GetStackParameterSize method [.NET Framework debugging]
- GetStackParameterSize method [.NET Framework debugging]
ms.assetid: f6a449c8-a941-43ba-9a90-c98b29ae3c36
topic_type:
- apiref
ms.openlocfilehash: 21af3980de9b5a768b6af9a8aca74b693c7ac528
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95695490"
---
# <a name="icordebugnativeframe2getstackparametersize-method"></a>ICorDebugNativeFrame2::GetStackParameterSize-Methode

Gibt die kumulierte Größe der Parameter auf dem Stapel unter x86-Betriebssystemen zurück.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetStackParameterSize([out] ULONG32 * pSize)  
```  
  
## <a name="parameters"></a>Parameter  

 `pSize`  
 vorgenommen Ein Zeiger auf die kumulierte Größe der Parameter im Stapel.  
  
## <a name="return-value"></a>Rückgabewert  

 Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.  
  
|HRESULT|BESCHREIBUNG|  
|-------------|-----------------|  
|S_OK|Die Stapelgröße wurde erfolgreich zurückgegeben.|  
|S_FALSE|`GetStackParameterSize` wurde für eine nicht-x86-Plattform aufgerufen.|  
|E_FAIL|`The size of the parameters could not be returned`.|  
|E_INVALIDARG|`pSize` Ist `null` .|  
  
## <a name="exceptions"></a>Ausnahmen  
  
## <a name="remarks"></a>Bemerkungen  

 Die [ICorDebugStackWalk](icordebugstackwalk-interface.md) -Methoden passen den Stapelzeiger nicht für Parameter an, die auf dem Stapel abgelegt werden. Stattdessen können Sie den von zurückgegebenen Wert verwenden, `GetStackParameterSize` um den Stapelzeiger auf einen Ausgangswert für einen nativen Unwinder festzulegen, der für die Parameter angepasst wird.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorDebugNativeFrame2-Schnittstelle](icordebugnativeframe2-interface.md)
- [Debugschnittstellen](debugging-interfaces.md)
- [Debuggen](index.md)
