---
title: ICorDebugNativeFrame2::IsMatchingParentFrame-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame2.IsMatchingParentFrame Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame2::IsMatchingParentFrame
helpviewer_keywords:
- IsMatchingParentFrame method [.NET Framework debugging]
- ICorDebugNativeFrame2::IsMatchingParentFrame method [.NET Framework debugging]
ms.assetid: d2ca20db-df22-4528-a0dd-a09ea62c8998
topic_type:
- apiref
ms.openlocfilehash: 5bcced647af6436bd8f5b1f3779d9368b6173d11
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213035"
---
# <a name="icordebugnativeframe2ismatchingparentframe-method"></a>ICorDebugNativeFrame2::IsMatchingParentFrame-Methode
Bestimmt, ob der angegebene Frame dem aktuellen Frame übergeordnet ist.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT IsMatchingParentFrame([in] ICorDebugNativeFrame2  
                                      *pPotentialParentFrame,  
                              [out] BOOL *pIsParent);  
```  
  
## <a name="parameters"></a>Parameter  
 `pPotentialParentFrame`  
 in Ein Zeiger auf das Frame Objekt, das Sie für den übergeordneten Status auswerten möchten.  
  
 `pIsParent`  
 [out] `true` `pPotentialParentFrame`, wenn das übergeordnete Element des aktuellen Frames ist, andernfalls `false` .  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.  
  
|HRESULT|BESCHREIBUNG|  
|-------------|-----------------|  
|S_OK|Der übergeordnete Status wurde erfolgreich zurückgegeben.|  
|E_FAIL|Der übergeordnete Status konnte nicht zurückgegeben werden.|  
|E_INVALIDARG|`pPotentialParentFrame` oder `pIsParent` ist NULL.|  
  
## <a name="exceptions"></a>Ausnahmen  
  
## <a name="remarks"></a>Hinweise  
 `IsMatchingParentFrame`Gibt zurück `true` , wenn das Frame Objekt, das Sie an die Methode übergeben, das übergeordnete Element des Frame Objekts ist, für das die Methode aufgerufen wurde. Wenn Sie die-Methode für einen Frame aufzurufen, der kein untergeordnetes Element des angegebenen Frames ist, wird ein Fehler zurückgegeben.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugNativeFrame2-Schnittstelle](icordebugnativeframe2-interface.md)
- [Debugschnittstellen](debugging-interfaces.md)
- [Debuggen](index.md)
