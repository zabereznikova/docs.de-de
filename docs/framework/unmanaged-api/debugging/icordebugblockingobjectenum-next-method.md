---
title: ICorDebugBlockingObjectEnum::Next-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugBlockingObjectEnum.Next Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBlockingObjectEnum::Next
helpviewer_keywords:
- Next method, ICorDebugBlockingObjectEnum interface [.NET Framework debugging]
- ICorDebugBlockingObjectEnum::Next method [.NET Framework debugging]
ms.assetid: 0121753f-ebea-48d0-aeb2-ed7fda76dc60
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8fd82418da26ab0cd32b007b4613d588dfa695eb
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67745295"
---
# <a name="icordebugblockingobjectenumnext-method"></a>ICorDebugBlockingObjectEnum::Next-Methode
Ruft die angegebene Anzahl von [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) Objekte aus der Enumeration, die an der aktuellen Position ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT Next([in] ULONG  celt,  
             [out, size_is(celt), length_is(*pceltFetched)]  
                           CorDebugBlockingObject values[],  
             [out] ULONG *pceltFetched;  
```  
  
## <a name="parameters"></a>Parameter  
 `celt`  
 [in] Die Anzahl der Objekte abgerufen werden soll.  
  
 `values`  
 [out] Ein Array von Zeigern auf [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) Objekte.  
  
 `pceltFetched`  
 [out] Ein Zeiger auf die Anzahl der Objekte, die abgerufen wurden.  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt die folgenden spezifischen HRESULTs zurück.  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|Die Methode wurde erfolgreich abgeschlossen.|  
|S_FALSE|`pceltFetched` entspricht nicht `celt`.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Methode funktioniert wie einen typische com-Enumerator.  
  
 Die Werte für die Eingabe-Array muss mindestens der Größe `celt`. Das Array gefüllt entweder mit den nächsten `celt` Werte in der Enumeration und alle anderen Werte, wenn weniger als `celt` bleiben. Bei der Rückgabe dieser Methode `pceltFetched` wird übernommen, die Anzahl der Werte, die abgerufen wurden. Wenn `values` enthält ungültige Verweise oder verweist auf einen Puffer, der kleiner ist als `celt`, oder wenn `pceltFetched` ist ein ungültiger Zeiger, das Ergebnis nicht definiert ist.  
  
> [!NOTE]
>  Obwohl die [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) Struktur wird nicht freigegeben werden müssen, die Schnittstelle "ICorDebugValue" darin freigegeben werden müssen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugDataTarget-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)
- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Debuggen](../../../../docs/framework/unmanaged-api/debugging/index.md)
