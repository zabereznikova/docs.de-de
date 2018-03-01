---
title: ICorDebugFrame Schnittstelle1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: caa3ef9cd52cc872d4ebc96376c104a7b90fb4f2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugframe-interface1"></a>ICorDebugFrame Schnittstelle1
Stellt einen Rahmen auf dem aktuellen Stapel dar.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[CreateStepper-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-createstepper-method.md)|Ruft ein ICorDebugStepper schrittweisen relativ zu dieser Operationen `ICorDebugFrame`.|  
|[GetCallee-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcallee-method.md)|Ruft einen Zeiger auf die `ICorDebugFrame` in der aktuellen Kette, in denen dieses Rahmens aufgerufen oder Null zurück, wenn dies der innerste Rahmen in der Kette.|  
|[GetCaller-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcaller-method.md)|Ruft einen Zeiger auf die `ICorDebugFrame` in der aktuellen Kette, die dieses Rahmens aufgerufen werden soll, oder Null zurück, wenn diese ist die äußerste Rahmen in der Kette.|  
|[GetChain-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getchain-method.md)|Ruft einen Zeiger auf die ICorDebugChain dies `ICorDebugFrame` gehört.|  
|[GetCode-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md)|Ruft einen Zeiger auf den dieser Stapelrahmen zugeordneten ICorDebugCode ab.|  
|[GetFunction-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getfunction-method.md)|Ruft einen Zeiger auf ICorDebugFunction ab, die den Stapelrahmen zugeordneten Code enthält.|  
|[GetFunctionToken-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getfunctiontoken-method.md)|Ruft das Metadatentoken für die Funktion mit dem Code zugeordneten dieses Stapelrahmens ab.|  
|[GetStackRange-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getstackrange-method.md)|Ruft den Bereich der absoluten Adresse des Stapelrahmens dargestellt, die von diesem `ICorDebugFrame`.|  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
