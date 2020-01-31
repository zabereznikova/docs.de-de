---
title: ICorDebugMergedAssemblyRecord-Schnittstelle
ms.date: 03/30/2017
ms.assetid: fe280b11-9479-4e34-a07c-0d1ea8088422
ms.openlocfilehash: 6d5d862110cd91e8ac81c96e50486be10c579903
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793061"
---
# <a name="icordebugmergedassemblyrecord-interface"></a>ICorDebugMergedAssemblyRecord-Schnittstelle
Enthält Informationen zu einer zusammengeführten Assembly.  
  
## <a name="methods"></a>Methoden  
  
|-Methode|Beschreibung|  
|------------|-----------------|  
|[GetCulture-Methode](icordebugmergedassemblyrecord-getculture-method.md)|Ruft die Kulturnamen-Zeichenfolge der Assembly ab.|  
|[GetIndex-Methode](icordebugmergedassemblyrecord-getindex-method.md)|Ruft den Präfixindex der Assembly ab.|  
|[GetPublicKey-Methode](icordebugmergedassemblyrecord-getpublickey-method.md)|Ruft den öffentlichen Schlüssel der Assembly ab.|  
|[GetPublicKeyToken-Methode](icordebugmergedassemblyrecord-getpublickeytoken-method.md)|Ruft das öffentliche Schlüsseltoken der Assembly ab.|  
|[GetSimpleName-Methode](icordebugmergedassemblyrecord-getsimplename-method.md)|Ruft den einfachen Namen der Assembly ab.|  
|[GetVersion-Methode](icordebugmergedassemblyrecord-getversion-method.md)|Ruft Versionsinformationen zur Assembly ab.|  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
> Diese Schnittstelle ist nur in Verbindung mit .NET Native verfügbar. Wenn Sie diese Schnittstelle für ICorDebug-Szenarien außerhalb von .NET Native implementieren, ignoriert die Common Language Runtime diese Schnittstelle.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Schnittstellen](debugging-interfaces.md)
- [Debuggen](index.md)
