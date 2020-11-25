---
title: ICorDebugModuleDebugEvent-Schnittstelle
ms.date: 03/30/2017
ms.assetid: 41950c52-1ac8-4212-b814-c77e20879f91
ms.openlocfilehash: 62d419a193cff000e1dd748d0cbb6b61775a81aa
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95695815"
---
# <a name="icordebugmoduledebugevent-interface"></a>ICorDebugModuleDebugEvent-Schnittstelle

Erweitert die [icordebugdebugevent](icordebugdebugevent-interface.md) -Schnittstelle, um Ereignisse auf Modulebene zu unterstützen.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[GetModule-Methode](icordebugmoduledebugevent-getmodule-method.md)|Ruft das zusammengeführte Modul ab, das soeben geladen oder entladen wurde.|  
  
## <a name="remarks"></a>Hinweise  

 Diese Schnittstelle wird von den Ereignis Typen [MODULE_LOADED](cordebugdebugeventkind-enumeration.md) und [MODULE_UNLOADED](cordebugdebugeventkind-enumeration.md) implementiert.  
  
> [!NOTE]
> Diese Schnittstelle ist nur in Verbindung mit .NET Native verfügbar. Bei dem Versuch, `QueryInterface` aufzurufen, um einen Schnittstellenzeiger abzurufen, wird für ICorDebug-Szenarien außerhalb von .NET Native `E_NOINTERFACE` zurückgegeben.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Debugschnittstellen](debugging-interfaces.md)
- [Debuggen](index.md)
