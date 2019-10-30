---
title: ICorDebugThread3::GetActiveInternalFrames-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugThread3.GetActiveInternalFrames Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread3::GetActiveInternalFrames
helpviewer_keywords:
- ICorDebugThread3::GetActiveInternalFrames method [.NET Framework debugging]
- GetActiveInternalFrames method [.NET Framework debugging]
ms.assetid: d69796b4-5b6d-457c-85f6-2cf42e8a8773
topic_type:
- apiref
ms.openlocfilehash: b4f228d55c9ffd6b85ebd0b430a7f5db404320f6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124346"
---
# <a name="icordebugthread3getactiveinternalframes-method"></a>ICorDebugThread3::GetActiveInternalFrames-Methode
Gibt ein Array interner Frames ([ICorDebugInternalFrame2](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md) -Objekte) auf dem Stapel zurück.  
  
## <a name="syntax"></a>Syntax  
  
```cpp 
HRESULT GetActiveInternalFrames  
      (  
      [in] ULONG32 cInternalFrames,  
      [out] ULONG32 *pcInternalFrames,  
      [in, out,size_is(cInternalFrames), length_is(*pcInternalFrames)]  
            ICorDebugInternalFrame2 * ppInternalFrames[]  
      );  
```  
  
## <a name="parameters"></a>Parameter  
 `cInternalFrames`  
 in Die Anzahl der in `ppInternalFrames`erwarteten internen Frames.  
  
 `pcInternalFrames`  
 vorgenommen Ein Zeiger auf eine `ULONG32`, die die Anzahl der internen Frames im Stapel enthält.  
  
 `ppInternalFrames`  
 [in, out] Ein Zeiger auf die Adresse eines Arrays interner Frames auf dem Stapel.  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|Das [ICorDebugInternalFrame2](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md) -Objekt wurde erfolgreich erstellt.|  
|E_INVALIDARG|`cInternalFrames` ist nicht 0 (null), `ppInternalFrames` ist `null`, oder `pcInternalFrames` ist `null`.|  
|HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)|`ppInternalFrames` ist kleiner als die Anzahl interner Frames.|  
  
## <a name="exceptions"></a>Ausnahmen  
  
## <a name="remarks"></a>Hinweise  
 Interne Frames sind Datenstrukturen, die von der Laufzeit zur Speicherung temporärer Daten auf den Stapel verschoben werden.  
  
 Wenn Sie `GetActiveInternalFrames`zum ersten Mal aufrufen, sollten Sie den `cInternalFrames`-Parameter auf 0 (null) und den `ppInternalFrames`-Parameter auf NULL festlegen. Wenn `GetActiveInternalFrames` zuerst zurückgibt, enthält `pcInternalFrames` die Anzahl der internen Frames auf dem Stapel.  
  
 `GetActiveInternalFrames` sollten dann ein zweites Mal aufgerufen werden. Übergeben Sie die richtige Anzahl (`pcInternalFrames`) im `cInternalFrames` Parameter, und geben Sie einen Zeiger auf ein Array mit entsprechender Größenangabe in `ppInternalFrames`an.  
  
 Verwenden Sie die [ICorDebugStackWalk:: GetFrame](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-getactiveinternalframes-method.md) -Methode, um tatsächliche Stapel Rahmen zurückzugeben.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Debuggen](../../../../docs/framework/unmanaged-api/debugging/index.md)
