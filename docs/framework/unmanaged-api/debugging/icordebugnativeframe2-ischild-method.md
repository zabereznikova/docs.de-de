---
title: ICorDebugNativeFrame2::IsChild-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame2.IsChild Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame2::IsChild
helpviewer_keywords:
- IsChild method [.NET Framework debugging]
- ICorDebugNativeFrame2::IsChild method [.NET Framework debugging]
ms.assetid: 9e2aae09-49cb-4fbd-81e5-e29cd864a88b
topic_type:
- apiref
ms.openlocfilehash: 0d65849aba08c7d143a6977e7dfb8cff85274a64
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95695568"
---
# <a name="icordebugnativeframe2ischild-method"></a>ICorDebugNativeFrame2::IsChild-Methode

Bestimmt, ob der aktuelle Frame ein untergeordneter Frame ist.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT IsChild([out] BOOL * pIsChild);  
```  
  
## <a name="parameters"></a>Parameter  

 `pIsChild`  
 vorgenommen Ein boolescher Wert, der angibt, ob der aktuelle Frame ein untergeordneter Frame ist.  
  
## <a name="return-value"></a>Rückgabewert  

 Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.  
  
|HRESULT|BESCHREIBUNG|  
|-------------|-----------------|  
|S_OK|Der untergeordnete Status wurde erfolgreich zurückgegeben.|  
|E_FAIL|Der untergeordnete Status konnte nicht zurückgegeben werden.|  
|E_INVALIDARG|`pIsChild` ist NULL.|  
  
## <a name="exceptions"></a>Ausnahmen  
  
## <a name="remarks"></a>Bemerkungen  

 Die `IsChild` Methode gibt zurück, `true` Wenn das Frame Objekt, für das Sie die Methode aufzurufen, ein untergeordnetes Element eines anderen Frames ist. Wenn dies der Fall ist, verwenden Sie die [ismatchingparameterframe](icordebugnativeframe2-ismatchingparentframe-method.md) -Methode, um zu überprüfen, ob ein Frame das übergeordnete Element ist.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorDebugNativeFrame2-Schnittstelle](icordebugnativeframe2-interface.md)
- [Debugschnittstellen](debugging-interfaces.md)
- [Debuggen](index.md)
