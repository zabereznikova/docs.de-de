---
title: ICorDebugFrame-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame
helpviewer_keywords:
- ICorDebugFrame interface [.NET Framework debugging]
ms.assetid: 0c48f764-3c64-4602-b2f4-4ffc60eb2c65
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d4744ea67d0ce0d9ad2b13c45bdef65f884ef925
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69937008"
---
# <a name="icordebugframe-interface"></a>ICorDebugFrame-Schnittstelle

Stellt einen Rahmen auf dem aktuellen Stapel dar.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[CreateStepper-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-createstepper-method.md)|Ruft einen ICorDebugStepper ab, um schrittweise Vorgänge in `ICorDebugFrame`Bezug auf diesen auszuführen.|  
|[GetCallee-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcallee-method.md)|Ruft einen Zeiger auf den `ICorDebugFrame` in der aktuellen Kette ab, den dieser Frame aufrief, oder gibt NULL zurück, wenn dies der innerste Frame in der Kette ist.|  
|[GetCaller-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcaller-method.md)|Ruft einen Zeiger auf den `ICorDebugFrame` in der aktuellen Kette ab, der diesen Frame aufgerufen hat, oder gibt NULL zurück, wenn dies der äußerste Frame in der Kette ist.|  
|[GetChain-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getchain-method.md)|Ruft einen Zeiger auf die ICorDebug-Kette `ICorDebugFrame` ab, zu der gehört.|  
|[GetCode-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md)|Ruft einen Zeiger auf den ICorDebugCode ab, der diesem Stapel Rahmen zugeordnet ist.|  
|[GetFunction-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getfunction-method.md)|Ruft einen Zeiger auf die ICorDebugFunction ab, die den Code enthält, der diesem Stapel Rahmen zugeordnet ist.|  
|[GetFunctionToken-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getfunctiontoken-method.md)|Ruft das Metadatentoken für die Funktion ab, die den Code enthält, der diesem Stapel Rahmen zugeordnet ist.|  
|[GetStackRange-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getstackrange-method.md)|Ruft den absoluten Adressbereich des Stapel Rahmens ab, der von `ICorDebugFrame`diesem dargestellt wird.|  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
> Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cordebug. idl, Cordebug. h  
  
 **Fern** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
