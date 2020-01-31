---
title: ICorDebugModuleDebugEvent-Schnittstelle
ms.date: 03/30/2017
ms.assetid: 41950c52-1ac8-4212-b814-c77e20879f91
ms.openlocfilehash: a2c7eaa8a2c811c1696024d9af4b715cc49e7caa
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792898"
---
# <a name="icordebugmoduledebugevent-interface"></a>ICorDebugModuleDebugEvent-Schnittstelle
Erweitert die [icordebugdebugevent](icordebugdebugevent-interface.md) -Schnittstelle, um Ereignisse auf Modulebene zu unterstützen.  
  
## <a name="methods"></a>Methoden  
  
|-Methode|Beschreibung|  
|------------|-----------------|  
|[GetModule-Methode](icordebugmoduledebugevent-getmodule-method.md)|Ruft das zusammengeführte Modul ab, das soeben geladen oder entladen wurde.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Schnittstelle wird von den Ereignis Typen [MODULE_LOADED](cordebugdebugeventkind-enumeration.md) und [MODULE_UNLOADED](cordebugdebugeventkind-enumeration.md) implementiert.  
  
> [!NOTE]
> Diese Schnittstelle ist nur in Verbindung mit .NET Native verfügbar. Bei dem Versuch, `QueryInterface` aufzurufen, um einen Schnittstellenzeiger abzurufen, wird für ICorDebug-Szenarien außerhalb von .NET Native `E_NOINTERFACE` zurückgegeben.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Schnittstellen](debugging-interfaces.md)
- [Debuggen](index.md)
