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
ms.openlocfilehash: a15d7f16676b8b9d66f8d1ba7484f3fec5735a44
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59222562"
---
# <a name="icordebugframe-interface"></a>ICorDebugFrame-Schnittstelle

Stellt einen Rahmen auf dem aktuellen Stapel dar.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[CreateStepper-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-createstepper-method.md)|Ruft eine ICorDebugStepper relativ zu diesem schrittweisen Operationen `ICorDebugFrame`.|  
|[GetCallee-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcallee-method.md)|Ruft einen Zeiger auf die `ICorDebugFrame` in der aktuellen Kette, in denen dieses Bild aufgerufen, oder Null zurück, wenn diese die innerste Rahmen in der Kette.|  
|[GetCaller-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcaller-method.md)|Ruft einen Zeiger auf die `ICorDebugFrame` in der aktuellen Kette, die diesem Frame aufgerufen werden soll, oder Null zurück, wenn diese ist der äußerste Frame in der Kette.|  
|[GetChain-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getchain-method.md)|Ruft einem Zeiger auf die ICorDebugChain dies `ICorDebugFrame` gehört.|  
|[GetCode-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md)|Ruft einen Zeiger auf den ICorDebugCode, die diesen Stapelrahmen zugeordnet.|  
|[GetFunction-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getfunction-method.md)|Ruft einen Zeiger auf die ICorDebugFunction ab, die den Code für diesen Stapelrahmen enthält.|  
|[GetFunctionToken-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getfunctiontoken-method.md)|Ruft das Metadatentoken für die Funktion, die den Code für diesen Stapelrahmen enthält.|  
|[GetStackRange-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getstackrange-method.md)|Ruft den Bereich der absoluten Adresse des Stapelrahmens dargestellt durch diese `ICorDebugFrame`.|  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
