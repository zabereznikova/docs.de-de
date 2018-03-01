---
title: ICorDebugNativeFrame Schnittstelle1
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
- ICorDebugNativeFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame
helpviewer_keywords:
- ICorDebugNativeFrame interface [.NET Framework debugging]
ms.assetid: 04819c58-7246-4b32-befb-680cf1dbc436
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: edd49d745be9db0c4c5309cf5febc3ff651a860f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugnativeframe-interface1"></a>ICorDebugNativeFrame Schnittstelle1
Eine spezielle Implementierung von ICorDebugFrame für systemeigene Rahmen verwendet werden soll.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[CanSetIP-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-cansetip-method.md)|Ruft einen Wert, der angibt, ob den Anweisungszeiger auf die angegebene Offsetposition in systemeigenem Code festgelegt werden kann.|  
|[GetIP-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getip-method.md)|Ruft den Offset des Stapelrahmens in systemeigenen Code ab.|  
|[GetLocalDoubleRegisterValue-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocaldoubleregistervalue-method.md)|Ruft einen Zeiger auf einen ICorDebugValue den Wert eines Arguments oder einer lokalen Variablen in zwei Speicher-Register vom systemeigenen Frames gespeichert.|  
|[GetLocalMemoryRegisterValue-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocalmemoryregistervalue-method.md)|Ruft einen Zeiger auf eine `ICorDebugValue` , die den Wert einer lokalen Variablen, von denen die niedrigen Bits im angegebenen Register gespeichert sind, und die oberen Bits an der angegebenen Speicheradresse gespeichert sind darstellt.|  
|[GetLocalMemoryValue-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocalmemoryvalue-method.md)|Ruft einen Zeiger auf eine `ICorDebugValue` , die den Wert einer lokalen Variablen, die an der angegebenen Speicheradresse gespeichert darstellt.|  
|[GetLocalRegisterMemoryValue-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocalregistermemoryvalue-method.md)|Ruft einen Zeiger auf ein `ICorDebugValue` , das den Wert einer lokalen Variablen, von denen die oberen Bits im angegebenen Register gespeichert sind, und die niedrigen Bits an der angegebenen Speicheradresse gespeichert sind darstellt.|  
|[GetLocalRegisterValue-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocalregistervalue-method.md)|Ruft einen Zeiger auf eine `ICorDebugValue` , die den Wert eines Arguments oder einer lokalen Variablen in der angegebenen systemeigenen Register gespeichert darstellt.|  
|[GetRegisterSet-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getregisterset-method.md)|Ruft einen Zeiger auf eine [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) , die den Registersatz dafür darstellt `ICorDebugNativeFrame`.|  
|[SetIP-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md)|Legt den Anweisungszeiger am angegebenen Offset Speicherort in systemeigenem Code.|  
  
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
