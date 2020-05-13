---
title: ICorDebugThread4::GetBlockingObjects-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugThread4.GetBlockingObjects Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread4::GetBlockingObjects
helpviewer_keywords:
- GetBlockingObjects method [.NET Framework debugging]
- ICorDebugThread4::GetBlockingObjects method [.NET Framework debugging]
ms.assetid: a7e6c54e-7be9-4e52-bbb4-95f52458e8e4
topic_type:
- apiref
ms.openlocfilehash: 366b5124cc66a4e9a1c3bd4e77f604f15ba8d8a8
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379672"
---
# <a name="icordebugthread4getblockingobjects-method"></a>ICorDebugThread4::GetBlockingObjects-Methode
Stellt eine geordnete Enumeration von [CorDebugBlockingObject](cordebugblockingobject-structure.md) -Strukturen bereit, die Thread Blockierungs Informationen bereitstellen.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetBlockingObjects (  
    [out] ICorDebugBlockingObjectEnum **ppBlockingObjectEnum  
```  
  
## <a name="parameters"></a>Parameter  
 `ppBlockingObjectEnum`  
 vorgenommen Ein Zeiger auf eine geordnete Enumeration von [corentbugblockingobject](cordebugblockingobject-structure.md) -Strukturen.  
  
## <a name="remarks"></a>Hinweise  
 Das erste Element in der zurückgegebenen Enumeration entspricht der ersten Struktur, die den Thread blockiert. Das zweite Element entspricht einem blockierenden Element, das beim Ausführen eines asynchronen Prozedur Aufrufes (APC) bei Blockierung auf dem ersten fest steht, usw.  
  
 Die Enumeration ist nur für die Dauer des aktuellen synchronisierten Zustands gültig.  
  
 Diese Methode muss aufgerufen werden, während sich die zu debuggende Komponente in einem synchronisierten Zustand befindet.  
  
 Wenn `ppBlockingObjectEnum` kein gültiger Zeiger ist, ist das Ergebnis nicht definiert.  
  
 Wenn ein Thread blockiert wird und der Fehler nicht bestimmt werden kann, gibt die Methode ein HRESULT zurück, das einen Fehler anzeigt. Andernfalls wird S_OK zurückgegeben.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugThread4-Schnittstelle](icordebugthread4-interface.md)
- [Debugschnittstellen](debugging-interfaces.md)
- [Debuggen](index.md)
