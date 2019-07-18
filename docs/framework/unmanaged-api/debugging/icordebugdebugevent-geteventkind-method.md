---
title: ICorDebugDebugEvent::GetEventKind-Methode
ms.date: 03/30/2017
ms.assetid: c37aaceb-c948-46bd-a943-08be4cbb76f4
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fdbc320e13e0cb140f5ef7aa63b878b43ca0189b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67750053"
---
# <a name="icordebugdebugeventgeteventkind-method"></a>ICorDebugDebugEvent::GetEventKind-Methode
Gibt an, welche Art von Ereignis dieses `ICorDebugDebugEvent`-Objekt darstellt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetEventKind(  
    [out]CorDebugDebugEventKind *pDebugEventKind  
);  
```  
  
## <a name="parameters"></a>Parameter  
 pDebugEventKind  
 Ein Zeiger auf eine [CorDebugDebugEventKind](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md) -Enumerationsmember, der den Typ des Ereignisses angibt.  
  
## <a name="remarks"></a>Hinweise  
 Basierend auf dem `pDebugEventKind`-Wert können Sie `QueryInterface` aufrufen, um eine präzisere Debug-Ereignisschnittstelle abzurufen, welche zusätzliche Daten enthält.  
  
> [!NOTE]
>  Diese Methode ist nur mit .NET Native verfügbar.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugDebugEvent-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md)
- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
