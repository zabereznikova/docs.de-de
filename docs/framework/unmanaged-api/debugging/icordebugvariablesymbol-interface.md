---
title: ICorDebugVariableSymbol-Schnittstelle
ms.date: 03/30/2017
ms.assetid: 0e58b85e-69bd-41ff-bedb-8cdc8be6a7a2
ms.openlocfilehash: 3d808fd49eb7767f1f48ad4e07d8ba7e47c8f34b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679480"
---
# <a name="icordebugvariablesymbol-interface"></a>ICorDebugVariableSymbol-Schnittstelle

Ruft Debugsymbolinformationen für eine Variable ab.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[GetName-Methode](icordebugvariablesymbol-getname-method.md)|Ruft den Namen einer Variablen ab.|  
|[GetSize-Methode](icordebugvariablesymbol-getsize-method.md)|Ruft die Größe einer Variablen in Bytes ab.|  
|[GetSlotIndex-Methode](icordebugvariablesymbol-getslotindex-method.md)|Ruft den verwalteten Slotindex einer lokalen Variablen ab.|  
|[GetValue-Methode](icordebugvariablesymbol-getvalue-method.md)|Ruft den Wert einer Variablen als Bytearray ab.|  
|[SetValue-Methode](icordebugvariablesymbol-setvalue-method.md)|Weist einer Variablen den Wert eines Bytearrays zu.|  
  
## <a name="remarks"></a>Hinweise  
  
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
