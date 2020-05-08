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
ms.openlocfilehash: 0ef49d2d833841eac62b2b964a0fdc902b4fb6a9
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894774"
---
# <a name="icordebugblockingobjectenumnext-method"></a>ICorDebugBlockingObjectEnum::Next-Methode
Ruft die angegebene Anzahl von [Cordebug-blockingobject](cordebugblockingobject-structure.md) -Objekten ab der aktuellen Position aus der-Enumeration ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT Next([in] ULONG  celt,  
             [out, size_is(celt), length_is(*pceltFetched)]  
                           CorDebugBlockingObject values[],  
             [out] ULONG *pceltFetched;  
```  
  
## <a name="parameters"></a>Parameter  
 `celt`  
 in Die Anzahl der abzurufenden-Objekte.  
  
 `values`  
 vorgenommen Ein Array von Zeigern auf [corentbugblockingobject](cordebugblockingobject-structure.md) -Objekte.  
  
 `pceltFetched`  
 vorgenommen Ein Zeiger auf die Anzahl der abgerufenen Objekte.  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt die folgenden spezifischen HRESULTs zurück.  
  
|HRESULT|BESCHREIBUNG|  
|-------------|-----------------|  
|S_OK|Die Methode wurde erfolgreich abgeschlossen.|  
|S_FALSE|`pceltFetched` entspricht nicht `celt`.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Methode funktioniert wie ein typischer com-Enumerator.  
  
 Die Eingabe Array Werte müssen mindestens eine Größe `celt`aufweisen. Das Array wird entweder mit den nächsten `celt` Werten in der-Enumeration oder mit allen verbleibenden Werten aufgefüllt, wenn `celt` weniger als vorhanden sind. Wenn diese Methode zurückgegeben `pceltFetched` wird, wird mit der Anzahl der abgerufenen Werte aufgefüllt. Wenn `values` ungültige Zeiger enthält oder auf einen Puffer verweist, der kleiner `celt`als ist, `pceltFetched` oder wenn ein ungültiger Zeiger ist, ist das Ergebnis nicht definiert.  
  
> [!NOTE]
> Obwohl die [Cordebug-blockingobject](cordebugblockingobject-structure.md) -Struktur nicht freigegeben werden muss, muss die Schnittstelle "ICorDebug Value" in der IT-Abteilung freigegeben werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [ICorDebugDataTarget-Schnittstelle](icordebugdatatarget-interface.md)
- [Debugschnittstellen](debugging-interfaces.md)
- [Debuggen](index.md)
