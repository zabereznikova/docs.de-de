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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 30cecaa1832ba9d45782b164ee65a2f39f28a8f8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54605405"
---
# <a name="icordebugregisterset2-interface"></a>ICorDebugRegisterSet2-Schnittstelle
Erweitert die Fähigkeiten der [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) Schnittstelle für die Hardwareplattformen, die mehr als 64 Registern.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[GetRegisters-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-getregisters-method.md)|Ruft den Wert jedes Register (auf dem Computer, die gerade Code ausführt) ab, das durch die Bitmaske angegeben ist.|  
|[GetRegistersAvailable-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-getregistersavailable-method.md)|Ruft ein Array von Bytes, die eine Bitmap der die verfügbaren Register bereitstellt.|  
|[SetRegisters-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-setregisters-method.md)|In .NET Framework, Version 2.0 implementiert nicht.|  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [ICorDebugRegisterSet-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
