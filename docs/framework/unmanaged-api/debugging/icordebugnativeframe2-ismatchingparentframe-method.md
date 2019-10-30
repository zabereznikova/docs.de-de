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
ms.openlocfilehash: aa06b7db6b7371e66853ed242f5e118fb5e5ff0c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73096201"
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
 [out] `true`, wenn `pPotentialParentFrame` das übergeordnete Element des aktuellen Frames ist. Andernfalls `false`.  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|Der übergeordnete Status wurde erfolgreich zurückgegeben.|  
|E_FAIL|Der übergeordnete Status konnte nicht zurückgegeben werden.|  
|E_INVALIDARG|`pPotentialParentFrame` oder `pIsParent` ist NULL.|  
  
## <a name="exceptions"></a>Ausnahmen  
  
## <a name="remarks"></a>Hinweise  
 `IsMatchingParentFrame` gibt `true` zurück, wenn das Frame Objekt, das Sie an die Methode übergeben, das übergeordnete Element des Frame Objekts ist, für das die Methode aufgerufen wurde. Wenn Sie die-Methode für einen Frame aufzurufen, der kein untergeordnetes Element des angegebenen Frames ist, wird ein Fehler zurückgegeben.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugNativeFrame2-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-interface.md)
- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Debuggen](../../../../docs/framework/unmanaged-api/debugging/index.md)
