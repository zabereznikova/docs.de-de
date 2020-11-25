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
ms.openlocfilehash: 2ca3bf94298b45e404c930ffe52e101085ee482d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726209"
---
# <a name="icordebugthread3getactiveinternalframes-method"></a>ICorDebugThread3::GetActiveInternalFrames-Methode

Gibt ein Array interner Frames ([ICorDebugInternalFrame2](icordebuginternalframe2-interface.md) -Objekte) auf dem Stapel zurück.  
  
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
 in Die Anzahl der in erwarteten internen Frames `ppInternalFrames` .  
  
 `pcInternalFrames`  
 vorgenommen Ein Zeiger auf einen-Wert `ULONG32` , der die Anzahl der internen Frames im Stapel enthält.  
  
 `ppInternalFrames`  
 [in, out] Ein Zeiger auf die Adresse eines Arrays interner Frames auf dem Stapel.  
  
## <a name="return-value"></a>Rückgabewert  

 Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.  
  
|HRESULT|BESCHREIBUNG|  
|-------------|-----------------|  
|S_OK|Das [ICorDebugInternalFrame2](icordebuginternalframe2-interface.md) -Objekt wurde erfolgreich erstellt.|  
|E_INVALIDARG|`cInternalFrames` ist nicht NULL `ppInternalFrames` , und ist `null` , oder `pcInternalFrames` ist `null` .|  
|HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)|`ppInternalFrames` ist kleiner als die Anzahl interner Frames.|  
  
## <a name="exceptions"></a>Ausnahmen  
  
## <a name="remarks"></a>Bemerkungen  

 Interne Frames sind Datenstrukturen, die von der Laufzeit zur Speicherung temporärer Daten auf den Stapel verschoben werden.  
  
 Beim ersten Aufrufen `GetActiveInternalFrames` von sollten Sie den `cInternalFrames` -Parameter auf 0 (null) und den- `ppInternalFrames` Parameter auf NULL festlegen. `GetActiveInternalFrames`Enthält bei der ersten Rückgabe `pcInternalFrames` die Anzahl der internen Frames auf dem Stapel.  
  
 `GetActiveInternalFrames` sollte dann ein zweites Mal aufgerufen werden. Sie sollten die richtige Anzahl ( `pcInternalFrames` ) im `cInternalFrames` -Parameter übergeben und einen Zeiger auf ein Array mit entsprechender Größenangabe in angeben `ppInternalFrames` .  
  
 Verwenden Sie die [ICorDebugStackWalk:: GetFrame](icordebugthread3-getactiveinternalframes-method.md) -Methode, um tatsächliche Stapel Rahmen zurückzugeben.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Debugschnittstellen](debugging-interfaces.md)
- [Debuggen](index.md)
