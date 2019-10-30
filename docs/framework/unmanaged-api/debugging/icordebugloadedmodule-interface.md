---
title: ICorDebugLoadedModule-Schnittstelle
ms.date: 03/30/2017
ms.assetid: 34be6369-2e75-4a95-a538-3b29ac97cf6d
ms.openlocfilehash: 9fe36497844b9c33cefcf8c63711941196847525
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122614"
---
# <a name="icordebugloadedmodule-interface"></a>ICorDebugLoadedModule-Schnittstelle
Stellt Informationen zu einem geladenen Modul bereit.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[GetBaseAddress-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-getbaseaddress-method.md)|Ruft die Basisadresse für das geladene Modul ab oder legt diese fest.|  
|[GetName-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-getname-method.md)|Ruft den Namen des geladenen Moduls ab.|  
|[GetSize-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-getsize-method.md)|Ruft die Größe des geladenen Moduls in Bytes ab.|  
  
## <a name="remarks"></a>Hinweise  
 Die `ICorDebugLoadedModule`-Schnittstelle wird von einem Debugger implementiert und von den CLR-Debugschnittstellen verwendet, um Informationen vom Debugger zum geladenen Modul zu erhalten.  
  
> [!NOTE]
> Diese Schnittstelle ist nur in Verbindung mit .NET Native verfügbar. Wenn Sie diese Schnittstelle für ICorDebug-Szenarien außerhalb von .NET Native implementieren, ignoriert die Common Language Runtime diese Schnittstelle.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Debuggen](../../../../docs/framework/unmanaged-api/debugging/index.md)
