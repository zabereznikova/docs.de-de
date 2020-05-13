---
title: ICorDebugRegisterSet2-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet2
helpviewer_keywords:
- ICorDebugRegisterSet2 interface [.NET Framework debugging]
ms.assetid: d7fbccbf-3b6b-4db8-a96d-768e1cb6b1a6
topic_type:
- apiref
ms.openlocfilehash: f989f1c1f29c63af54ff125f4ad1aaa2bcee6757
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378200"
---
# <a name="icordebugregisterset2-interface"></a>ICorDebugRegisterSet2-Schnittstelle
Erweitert die Funktionen der [ICorDebugRegisterSet](icordebugregisterset-interface.md) -Schnittstelle für Hardwareplattformen mit mehr als 64 Registern.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[GetRegisters-Methode](icordebugregisterset2-getregisters-method.md)|Ruft den Wert der einzelnen Register (auf dem momentan ausgeführten Code) ab, der durch die Bitmaske angegeben wird.|  
|[GetRegistersAvailable-Methode](icordebugregisterset2-getregistersavailable-method.md)|Ruft ein Bytearray ab, das eine Bitmap der verfügbaren Register bereitstellt.|  
|[SetRegisters-Methode](icordebugregisterset2-setregisters-method.md)|Nicht in der .NET Framework Version 2,0 implementiert.|  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
> Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debugschnittstellen](debugging-interfaces.md)
- [ICorDebugRegisterSet-Schnittstelle](icordebugregisterset-interface.md)
