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
ms.openlocfilehash: 5aeea11b7e61869968aafe3425e27d6004f495ea
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124075"
---
# <a name="icordebugframe-interface"></a>ICorDebugFrame-Schnittstelle

Stellt einen Rahmen auf dem aktuellen Stapel dar.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[CreateStepper-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-createstepper-method.md)|Ruft ein ICorDebugStepper-Element ab, um schrittweise Vorgänge in Relation zu diesem `ICorDebugFrame`auszuführen.|  
|[GetCallee-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcallee-method.md)|Ruft einen Zeiger auf den `ICorDebugFrame` in der aktuellen Kette ab, den dieser Frame aufrief, oder gibt NULL zurück, wenn dies der innerste Frame in der Kette ist.|  
|[GetCaller-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcaller-method.md)|Ruft einen Zeiger auf den `ICorDebugFrame` in der aktuellen Kette ab, der diesen Frame aufgerufen hat, oder gibt NULL zurück, wenn dies der äußerste Frame in der Kette ist.|  
|[GetChain-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getchain-method.md)|Ruft einen Zeiger auf die ICorDebug-Kette ab, zu der dieser `ICorDebugFrame` gehört.|  
|[GetCode-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md)|Ruft einen Zeiger auf den ICorDebugCode ab, der diesem Stapel Rahmen zugeordnet ist.|  
|[GetFunction-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getfunction-method.md)|Ruft einen Zeiger auf die ICorDebugFunction ab, die den Code enthält, der diesem Stapel Rahmen zugeordnet ist.|  
|[GetFunctionToken-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getfunctiontoken-method.md)|Ruft das Metadatentoken für die Funktion ab, die den Code enthält, der diesem Stapel Rahmen zugeordnet ist.|  
|[GetStackRange-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getstackrange-method.md)|Ruft den absoluten Adressbereich des von diesem `ICorDebugFrame`dargestellten Stapel Rahmens ab.|  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
> Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
