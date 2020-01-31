---
title: ICorDebugILCode2-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugILCode2
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: f9dc2afd-df8a-464d-bdbf-5af0a1d4bf85
topic_type:
- apiref
ms.openlocfilehash: 30008d6cc98f7d0d0501d67e18703ed5a344d43a
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794364"
---
# <a name="icordebugilcode2-interface"></a>ICorDebugILCode2-Schnittstelle
[Wird nur in .NET Framework 4.5.2 und neueren Versionen unterstützt]  
  
 Erweitert logisch die [icordebugilcode](icordebugilcode-interface.md) -Schnittstelle so, dass Methoden bereitgestellt werden, die das Token für die Signatur der lokalen Variablen einer Funktion zurückgeben und die instrumentierten Intermediate Language (IL)-Offsets eines Profilers den ursprünglichen Methoden-IL-Offsets zuordnen.  
  
## <a name="methods"></a>Methoden  
  
|-Methode|Beschreibung|  
|------------|-----------------|  
|[GetInstrumentedILMap-Methode](icordebugilcode2-getinstrumentedilmap-method.md)|Gibt eine Zuordnung von Profiler-instrumentierten IL-Offsets zu ILs der ursprünglichen Methode für diese Instanz aus.|  
|[GetLocalVarSigToken-Methode](icordebugilcode2-getlocalvarsigtoken-method.md)|Ruft den Metadatentoken für die lokale Variablensignatur für die Funktion auf, die in dieser Instanz repräsentiert wird.|  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorDebugILCode-Schnittstelle](icordebugilcode-interface.md)
- [Debuggen von Schnittstellen](debugging-interfaces.md)
- [Debuggen](index.md)
