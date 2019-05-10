---
title: ICorDebugDebugEvent-Schnittstelle
ms.date: 03/30/2017
ms.assetid: a226737a-cb99-4e97-bd94-9a37094ded41
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 013cdfbb6a2904e60d6f7b4df6d40e3d65606fcd
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64606814"
---
# <a name="icordebugdebugevent-interface"></a>ICorDebugDebugEvent-Schnittstelle
Definiert die Basisschnittstelle, von der alle `ICorDebug` Debug-Ereignisse abgeleitet werden.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[GetEventKind-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md)|Gibt an, welche Art von Ereignis dieses `ICorDebugDebugEvent`-Objekt darstellt.|  
|[GetThread-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-getthread-method.md)|Ruft den Thread auf, auf dem das Ereignis aufgetreten ist.|  
  
## <a name="remarks"></a>Hinweise  
 Die folgenden Schnittstellen sind aus der `ICorDebugDebugEvent`-Schnittstelle abgeleitet:  
  
- [ICorDebugExceptionDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-interface.md)  
  
- [ICorDebugModuleDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugmoduledebugevent-interface.md)  
  
> [!NOTE]
>  Diese Schnittstelle ist nur in Verbindung mit .NET Native verfügbar. Bei dem Versuch, `QueryInterface` aufzurufen, um einen Schnittstellenzeiger abzurufen, wird für ICorDebug-Szenarien außerhalb von .NET Native `E_NOINTERFACE` zurückgegeben.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Debuggen](../../../../docs/framework/unmanaged-api/debugging/index.md)
