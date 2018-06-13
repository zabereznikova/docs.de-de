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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2ac87de35478e5eabdc8cdc3568baf2086923e38
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33423018"
---
# <a name="icordebugthread3getactiveinternalframes-method"></a>ICorDebugThread3::GetActiveInternalFrames-Methode
Gibt ein Array von internen Frames ([ICorDebugInternalFrame2](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md) Objekte) auf dem Stapel.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetActiveInternalFrames  
      (  
      [in] ULONG32 cInternalFrames,  
      [out] ULONG32 *pcInternalFrames,  
      [in, out,size_is(cInternalFrames), length_is(*pcInternalFrames)]  
            ICorDebugInternalFrame2 * ppInternalFrames[]  
      );  
```  
  
#### <a name="parameters"></a>Parameter  
 `cInternalFrames`  
 [in] Die Anzahl der erwarteten internen Frames `ppInternalFrames`.  
  
 `pcInternalFrames`  
 [out] Ein Zeiger auf eine `ULONG32` , enthält die Anzahl der internen Frames auf dem Stapel.  
  
 `ppInternalFrames`  
 [in, out] Ein Zeiger auf die Adresse eines Arrays von internen Frames auf dem Stapel.  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|Die [ICorDebugInternalFrame2](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md) Objekt wurde erfolgreich erstellt.|  
|E_INVALIDARG|`cInternalFrames` ist ungleich NULL und `ppInternalFrames` ist `null`, oder `pcInternalFrames` ist `null`.|  
|HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)|`ppInternalFrames` ist kleiner als die Anzahl der internen Frames.|  
  
## <a name="exceptions"></a>Ausnahmen  
  
## <a name="remarks"></a>Hinweise  
 Interne Frames sind Datenstrukturen, die von der Runtime zum Speichern temporärer Daten auf dem Stapel abgelegt.  
  
 Beim ersten Aufruf `GetActiveInternalFrames`, sollten Sie festlegen, die `cInternalFrames` Parameter auf 0 (null), und die `ppInternalFrames` Parameter auf null. Wenn `GetActiveInternalFrames` zuerst zurückgegeben wird, `pcInternalFrames` enthält die Anzahl der internen Frames auf dem Stapel.  
  
 `GetActiveInternalFrames` Klicken Sie dann werden ein zweites Mal aufgerufen. Übergeben Sie die richtige Anzahl (`pcInternalFrames`) in der `cInternalFrames` Parameter, und geben Sie einen Zeiger auf ein entsprechend skalierten Array in `ppInternalFrames`.  
  
 Verwenden der [ICorDebugStackWalk:: GetFrame](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-getactiveinternalframes-method.md) Stapelrahmen der Methode, um tatsächliche zurückzugeben.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [Debuggen](../../../../docs/framework/unmanaged-api/debugging/index.md)
