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
ms.openlocfilehash: ca742ba9e89e1d189cfa38dead314df0d8b4e9d1
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792765"
---
# <a name="icordebugnativeframe2getstackparametersize-method"></a>ICorDebugNativeFrame2::GetStackParameterSize-Methode
Gibt die kumulierte Größe der Parameter auf dem Stapel unter x86-Betriebssystemen zurück.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetStackParameterSize([out] ULONG32 * pSize)  
```  
  
## <a name="parameters"></a>Parameters  
 `pSize`  
 vorgenommen Ein Zeiger auf die kumulierte Größe der Parameter im Stapel.  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|Die Stapelgröße wurde erfolgreich zurückgegeben.|  
|S_FALSE|`GetStackParameterSize` wurde auf einer nicht-x86-Plattform aufgerufen.|  
|E_FAIL|`The size of the parameters could not be returned`.|  
|E_INVALIDARG|`pSize` ist `null`.|  
  
## <a name="exceptions"></a>Ausnahmen  
  
## <a name="remarks"></a>Hinweise  
 Die [ICorDebugStackWalk](icordebugstackwalk-interface.md) -Methoden passen den Stapelzeiger nicht für Parameter an, die auf dem Stapel abgelegt werden. Stattdessen können Sie den von `GetStackParameterSize` zurückgegebenen Wert verwenden, um den Stapelzeiger auf einen Ausgangswert für einen nativen Unwinder festzulegen, der für die Parameter angepasst wird.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugNativeFrame2-Schnittstelle](icordebugnativeframe2-interface.md)
- [Debuggen von Schnittstellen](debugging-interfaces.md)
- [Debuggen](index.md)
