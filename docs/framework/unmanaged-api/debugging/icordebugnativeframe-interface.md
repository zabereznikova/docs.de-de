---
title: ICorDebugNativeFrame-Schnittstelle
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c01346b42fff812f8358482ae0e8570c03ee9231
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69912796"
---
# <a name="icordebugnativeframe-interface"></a>ICorDebugNativeFrame-Schnittstelle

Eine spezielle Implementierung von ICorDebug Frame, die für Native Frames verwendet wird.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[CanSetIP-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-cansetip-method.md)|Ruft einen Wert ab, der angibt, ob es sicher ist, den Anweisungs Zeiger auf die angegebene Offset Position in nativem Code festzulegen.|  
|[GetIP-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getip-method.md)|Ruft den Offset des Stapel Rahmens in systemeigenen Code ab.|  
|[GetLocalDoubleRegisterValue-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocaldoubleregistervalue-method.md)|Ruft einen Zeiger auf einen ICorDebug-Wert ab, der den Wert eines Arguments oder einer lokalen Variablen darstellt, die in zwei Speicher Registern eines systemeigenen Frames gespeichert ist.|  
|[GetLocalMemoryRegisterValue-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocalmemoryregistervalue-method.md)|Ruft einen Zeiger auf einen `ICorDebugValue` ab, der den Wert einer lokalen Variablen darstellt, von der die unteren Bits im angegebenen Register gespeichert werden und die hohen Bits an der angegebenen Speicheradresse gespeichert werden.|  
|[GetLocalMemoryValue-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocalmemoryvalue-method.md)|Ruft einen Zeiger auf einen `ICorDebugValue` ab, der den Wert einer lokalen Variablen darstellt, die an der angegebenen Speicheradresse gespeichert ist.|  
|[GetLocalRegisterMemoryValue-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocalregistermemoryvalue-method.md)|Ruft einen Zeiger auf einen `ICorDebugValue` ab, der den Wert einer lokalen Variablen darstellt, von der die hohen Bits im angegebenen Register gespeichert werden und die unteren Bits an der angegebenen Speicheradresse gespeichert werden.|  
|[GetLocalRegisterValue-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getlocalregistervalue-method.md)|Ruft einen Zeiger auf einen `ICorDebugValue` ab, der den Wert eines Arguments oder eine lokale Variable darstellt, die im angegebenen systemeigenen Register gespeichert ist.|  
|[GetRegisterSet-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-getregisterset-method.md)|Ruft einen Zeiger auf ein [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) ab, das den Register Satz für `ICorDebugNativeFrame`diese darstellt.|  
|[SetIP-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md)|Legt den Anweisungs Zeiger auf die angegebene Offset Position in nativem Code fest.|  
  
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
