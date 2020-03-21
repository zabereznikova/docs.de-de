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
ms.openlocfilehash: 680af5afa3ebef5bcaf9e34580e421dcc8093aaf
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178466"
---
# <a name="icordebugthread3getactiveinternalframes-method"></a>ICorDebugThread3::GetActiveInternalFrames-Methode
Gibt ein Array interner Frames ([ICorDebugInternalFrame2-Objekte)](icordebuginternalframe2-interface.md) auf dem Stapel zurück.  
  
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
 [in] Die Anzahl der internen `ppInternalFrames`Frames, die in erwartet werden.  
  
 `pcInternalFrames`  
 [out] Ein Zeiger auf `ULONG32` eine, der die Anzahl der internen Frames auf dem Stapel enthält.  
  
 `ppInternalFrames`  
 [in, out] Ein Zeiger auf die Adresse eines Arrays interner Frames auf dem Stapel.  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|Das [ICorDebugInternalFrame2-Objekt](icordebuginternalframe2-interface.md) wurde erfolgreich erstellt.|  
|E_INVALIDARG|`cInternalFrames`ist nicht `ppInternalFrames` Null `null`und `pcInternalFrames` `null`ist , oder ist .|  
|HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)|`ppInternalFrames`ist kleiner als die Anzahl der internen Frames.|  
  
## <a name="exceptions"></a>Ausnahmen  
  
## <a name="remarks"></a>Bemerkungen  
 Interne Frames sind Datenstrukturen, die von der Laufzeit auf den Stapel geschoben werden, um temporäre Daten zu speichern.  
  
 Wenn Sie `GetActiveInternalFrames`zum ersten Mal `cInternalFrames` aufrufen, sollten Sie `ppInternalFrames` den Parameter auf 0 (Null) und den Parameter auf null setzen. Wenn `GetActiveInternalFrames` das `pcInternalFrames` erste Zurückrückgabe, enthält die Anzahl der internen Frames auf dem Stapel.  
  
 `GetActiveInternalFrames`sollte dann ein zweites Mal aufgerufen werden. Sie sollten die richtige`pcInternalFrames`Anzahl `cInternalFrames` ( ) im Parameter übergeben und einen `ppInternalFrames`Zeiger auf ein Array in der entsprechenden Größe angeben.  
  
 Verwenden Sie die [ICorDebugStackWalk::GetFrame-Methode,](icordebugthread3-getactiveinternalframes-method.md) um tatsächliche Stackframes zurückzugeben.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Debugschnittstellen](debugging-interfaces.md)
- [Debuggen](index.md)
