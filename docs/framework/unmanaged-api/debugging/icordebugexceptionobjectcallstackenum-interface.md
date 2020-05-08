---
title: ICorDebugExceptionObjectCallStackEnum-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugExceptionObjectCallStackEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugExceptionObjectCallStackEnum
helpviewer_keywords:
- ICorDebugExceptionObjectCallStackEnum interface [.NET Framework debugging]
ms.assetid: 39dffa18-c71b-48c4-b11d-e814631ab1e9
topic_type:
- apiref
ms.openlocfilehash: e6dd951b0f432d455d95bb60f4c42df64d5bee24
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2020
ms.locfileid: "82975991"
---
# <a name="icordebugexceptionobjectcallstackenum-interface"></a>ICorDebugExceptionObjectCallStackEnum-Schnittstelle
Stellt einen Enumerator für Aufruflisteninformationen bereit, die in einem Ausnahmeobjekt eingebettet sind. Diese Schnittstelle ist eine Unterklasse von der ICorDebugEnum-Schnittstelle.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[Icordebugexceptionobjectcallstackenum:: Next](icordebugexceptionobjectcallstackenum-next-method.md)|Ruft eine angegebene Anzahl von [cordebugexceptionobjectstackframe](cordebugexceptionobjectstackframe-structure.md) -Objekten ab, die Informationen über die Rückruf Stapel eines Ausnahme Objekts enthalten.|  
  
## <a name="remarks"></a>Hinweise  
 Die `ICorDebugExceptionObjectCallStackEnum` Schnittstelle implementiert die ICorDebugEnum-Schnittstelle.  
  
 Eine `ICorDebugExceptionObjectCallStackEnum` Instanz wird mit [cordebugexceptionobjectstackframe](cordebugexceptionobjectstackframe-structure.md) -Objekten aufgefüllt, indem die [icordebugexceptionobjectvalue:: enumerateexceptioncallstack](icordebugexceptionobjectvalue-enumerateexceptioncallstack-method.md) -Methode aufgerufen wird. Die Aufruf Listenelemente in der Auflistung können durch Aufrufen der [icordebugexceptionobjectcallstackenum:: Next](icordebugexceptionobjectcallstackenum-next-method.md) -Methode aufgelistet werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Debugschnittstellen](debugging-interfaces.md)
- [Debuggen](index.md)
