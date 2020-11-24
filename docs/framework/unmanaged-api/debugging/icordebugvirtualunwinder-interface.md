---
title: ICorDebugVirtualUnwinder-Schnittstelle
ms.date: 03/30/2017
ms.assetid: a09e9ccc-0b37-43e3-95c1-bc5fa7ee5f42
ms.openlocfilehash: 67f2234d37165e421874815bdc2ef34f8f50749a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679376"
---
# <a name="icordebugvirtualunwinder-interface"></a>ICorDebugVirtualUnwinder-Schnittstelle

Stellt Methoden bereit, um die Stapelentladung zu unterstützen.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Name|  
|------------|----------|  
|[GetContext-Methode](icordebugvirtualunwinder-getcontext-method.md)|Ruft den aktuellen Kontext dieses Entladers ab.|  
|[Next-Methode](icordebugvirtualunwinder-next-method.md)|Wechselt zum Kontext eines Aufrufers.|  
  
## <a name="remarks"></a>Hinweise  

 Die Elemente der `ICorDebugVirtualUnwinder`-Schnittstelle werden durch den Debugger implementiert, damit die Stapelentladung unterstützt wird.  
  
> [!NOTE]
> Diese Schnittstelle ist nur in Verbindung mit .NET Native verfügbar. Wenn Sie diese Schnittstelle für ICorDebug-Szenarien außerhalb von .NET Native implementieren, ignoriert die Common Language Runtime diese Schnittstelle.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Debugschnittstellen](debugging-interfaces.md)
- [Debuggen](index.md)
