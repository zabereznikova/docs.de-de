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
ms.openlocfilehash: e4d5582b7a3df16db58ea0ed001dcbffcdcaab79
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122463"
---
# <a name="icordebugthread4getblockingobjects-method"></a>ICorDebugThread4::GetBlockingObjects-Methode
Stellt eine geordnete Enumeration von [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) -Strukturen bereit, die Thread Blockierungs Informationen bereitstellen.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetBlockingObjects (  
    [out] ICorDebugBlockingObjectEnum **ppBlockingObjectEnum  
```  
  
## <a name="parameters"></a>Parameter  
 `ppBlockingObjectEnum`  
 vorgenommen Ein Zeiger auf eine geordnete Enumeration von [corentbugblockingobject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) -Strukturen.  
  
## <a name="remarks"></a>Hinweise  
 Das erste Element in der zurückgegebenen Enumeration entspricht der ersten Struktur, die den Thread blockiert. Das zweite Element entspricht einem blockierenden Element, das beim Ausführen eines asynchronen Prozedur Aufrufes (APC) bei Blockierung auf dem ersten fest steht, usw.  
  
 Die Enumeration ist nur für die Dauer des aktuellen synchronisierten Zustands gültig.  
  
 Diese Methode muss aufgerufen werden, während sich die zu debuggende Komponente in einem synchronisierten Zustand befindet.  
  
 Wenn `ppBlockingObjectEnum` kein gültiger Zeiger ist, ist das Ergebnis nicht definiert.  
  
 Wenn ein Thread blockiert wird und der Fehler nicht bestimmt werden kann, gibt die Methode ein HRESULT zurück, das einen Fehler anzeigt. Andernfalls wird S_OK zurückgegeben.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugThread4-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-interface.md)
- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Debuggen](../../../../docs/framework/unmanaged-api/debugging/index.md)
